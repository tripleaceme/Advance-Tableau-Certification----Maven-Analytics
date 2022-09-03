# Advance Tableau Certification -  Maven Analytics
Note from my Advance Tableau Certification by Maven Analytics.

## Difference between Relationship and Joins:
**It is important to note that Relationship keeps your tables seperate and only join them during visualization while Unions and Joins merge your tables together before visualization.**

When you create a data source, it has two layers. The top-level layer is the logical layer of the data source. You combine data between tables in the logical layer using relationships.

The next layer is the physical layer of the data source. You combine data between tables at the physical layer using joins.

In the newer versions of Tableau, you get the Relationship interface (Logical) by default. However, you can still use the Joins interface (Physical). [Click Here](#new)

## Relationships
Relationships are a dynamic, flexible way to combine data from multiple tables for analysis. You don’t define join types for relationships, so you won’t see a Venn diagram when you create them.

Think of a relationship as a contract between two tables. When you are building a viz with fields from these tables, Tableau brings in data from these tables using that contract to build a query with the appropriate joins.

- Are displayed as flexible noodles between logical tables
- Require you to select matching fields between two logical tables
- Do not require you to select join types
- Make all row and column data from related tables potentially available in the data source
- Maintain each table's level of detail in the data source and during analysis
- Create independent domains at multiple levels of detail. Tables aren't merged together in the data source.
- During analysis, create the appropriate joins automatically, based on the fields in use.
- Do not duplicate aggregate values (when Performance Options are set to Many-to-Many)
- Keep unmatched measure values (when Performance Options are set to Some Records Match)
- No up-front join type:  You only need to select matching fields to define a relationship (no join types). Tableau first attempts to create the relationship based on existing key constraints and matching field names. You can then check to ensure they are the fields you want to use, or add more field pairs to better define how the tables should be related.
- Automatic and context-aware:  Relationships defer joins to the time and context of analysis. Tableau automatically selects join types based on the fields being used in the visualisation. During analysis, Tableau adjusts join types intelligently and preserves the native level of detail in your data. You can see aggregations at the level of detail of the fields in your viz rather than having to think about the underlying joins. You don't need to use LOD expressions such as FIXED to deduplicate data in related tables.
- Flexible:  Relationships can be many-to-many and support full outer joins. When you combine tables using relationships, it’s like creating a custom, flexible data source for every viz, all in a single data source for the workbook. Because Tableau queries only tables that are needed based on fields and filters in a viz, you can build a data source that can be used for a variety of analytic flows.


## Joins
Joins are a more static way to combine data. Joins must be defined between physical tables up front, before analysis and can’t be changed without impacting all sheets using that data source. Joined tables are always merged into a single table. As a result, sometimes joined data is missing unmatched values, or duplicates aggregated values.

- Are displayed with Venn diagram icons between physical tables
- Require you to select join types and join clauses
- Joined physical tables are merged into a single logical table with a fixed combination of data
- May drop unmatched measure values
- May duplicate aggregate values when fields are at different levels of detail
- Support scenarios that require a single table of data, such as extract filters and aggregation


## Requirements for using relationships over joins or unions
- When relating tables, the fields that define the relationships must have the same data type. Changing the data type in the Data Source page does not change this requirement. Tableau will still use the data type in the underlying database for queries.
- You can't define relationships based on geographic fields.
- Circular relationships aren't supported in the data model.
- You can't define relationships between published data sources.

## Factors that limit the benefits of using related tables (joins)
- Dirty data in tables (i.e. tables that weren't created with a well-structured model in mind and contain a mix of measures and dimensions in multiple tables) can make multi-table analysis more complex.
- Using data source filters will limit Tableau's ability to do join culling in the data. Join culling is a term for how Tableau simplifies queries by removing unnecessary joins.
- Tables with a lot of unmatched values across relationships.
- Interrelating multiple fact tables with multiple dimension tables (attempting to model shared or conformed dimensions).

## Where did joins go?(Newer Versions of Tableau i.e 2020.2 Upward)
- You can still specify joins between tables in the physical layer of a data source. Double-click a logical table to go to the Join/Union canvas in the physical layer and add joins or unions.
- Every top-level, logical table contains at least one physical table. Open a logical table to view, edit or create joins between its physical tables. Right-click a logical table, and then click Open. Or, just double-click the table to open it.

<a href="#new"><img src="https://github.com/tripleaceme/Advance-Tableau-Certification----Maven-Analytics/blob/main/images/data_model_singletable_joins.gif" alt="Joins in Newer Tableau"/></a>


- In the new data pane interface, the measures showing at the bottom of the table are the values relating to  multiple tables. Each value relating to a single table are shown in the table
panes. So if you create a **calculated field involving multiple tables, it will be shown in the bottom measures section of the data pane**.

# The 8 R’s of Relationships

## The 8 R’s of Relationships help to describe the behavior caused by different relationship types
- It is divided into Contextual Joins & Smart Aggregations.
    - **Contextual Joins includes:**
        - Remain
        <details>
        <summary>Check Visual</summary>
        <img src="" alt="Remain" />
        </details>

        - Relevant
        <details>
        <summary>Check Visual</summary>
        
        </details>

        - Retain
        <details>
        <summary>Check Visual</summary>
        
        </details>

        - Recover
        <details>
        <summary>Check Visual</summary>
        
        </details>
        - Represent

        <details>
        <summary>Check Visual</summary>
        
        </details>

        - Remove
        <details>
        <summary>Check Visual</summary>
        
        </details>
        
    - **Smart Aggregations:**
        - Replicate
        <details>
        <summary>Check Visual</summary>
        
        </details>

        - Resolve
        <details>
        <summary>Check Visual</summary>
        
        </details>

















I used [Markdown to PDF](http://markdown2pdf.com/) to convert this.