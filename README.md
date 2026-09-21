# 🛒 Online Grocery Store Sales Dashboard – Power BI

An end-to-end Power BI project that analyzes sales performance for an online grocery store across outlet types, locations, item categories, and product attributes. The dashboard turns raw retail data into an interactive, single-page report that supports quick, data-driven business decisions.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Project Overview

The goal of this project is to build a fully interactive Power BI dashboard that helps stakeholders at an online grocery store understand:

- Overall sales performance and average order/item value
- How sales and ratings vary by outlet type, outlet size, and outlet location (tier)
- Which item categories and fat-content segments drive the most revenue
- How outlet establishment year relates to sales performance
- Store-level KPIs to compare Supermarket Type 1/2/3 and standalone Grocery Stores

---

## 🖼️ Dashboard Preview

The report is built as a single dashboard page combining KPI cards, a filter panel, trend analysis, categorical breakdowns, and a detailed outlet-type table.

**Key sections on the page:**
- **Filter Panel** – slicers for Outlet Location Type, Outlet Size, and Item Type
- **KPI Cards** – Total Sales, Average Sales, Number of Items, Average Rating
- **Outlet Establishment Trend** – area/line chart of sales by outlet establishment year
- **Tabbed Analysis Panel** – switch between Total Sales, Average Sales, No. of Items, and Average Rating views, broken down by Fat Content, Item Type, and Fat by Outlet Tier
- **Outlet Size Donut Chart** – sales split across Small, Medium, and High outlet sizes
- **Outlet Location Chart** – sales by location Tier 1, Tier 2, Tier 3
- **Outlet Type Table** – Total Sales, Average Sales, No. of Items, Average Rating, and Item Visibility by outlet type

---

## 🎯 Business KPIs

| KPI | Description |
|---|---|
| **Total Sales** | Sum of all sales revenue generated across outlets |
| **Average Sales** | Average sales value per item/transaction |
| **Number of Items** | Total count of distinct items sold |
| **Average Rating** | Average customer/outlet rating |
| **Sales by Fat Content** | Revenue split between Low Fat and Regular products |
| **Sales by Item Type** | Revenue contribution of each product category (Fruits, Snacks, Household, Frozen, Dairy, Canned, Baking, Health, Meat, Soft Drinks, Breads, Hard Drinks, Others) |
| **Sales by Outlet Size** | Revenue split across Small, Medium, and High outlet sizes |
| **Sales by Outlet Location Tier** | Revenue split across Tier 1, Tier 2, and Tier 3 locations |
| **Sales by Outlet Type** | Comparison across Grocery Store, Supermarket Type 1, Type 2, and Type 3 |
| **Item Visibility** | Average shelf/listing visibility score per outlet type |

---

## 🛠️ Project Workflow

### 1. Data Walkthrough
- Reviewed the raw dataset structure, column definitions, and business context before building anything.
- Identified key dimensions (Outlet Type, Outlet Size, Outlet Location Tier, Item Type, Fat Content, Establishment Year) and measures (Sales, Item Visibility, Rating).
- Mapped out which fields would drive the KPIs and which visuals would best answer core business questions.

### 2. Data Connection
- Connected Power BI Desktop to the source data (e.g., Excel/CSV/SQL) using **Get Data**.
- Configured the connection mode (Import/DirectQuery) and set up data source credentials.
- Loaded the raw tables into Power Query for transformation.

### 3. Data Cleaning & Quality Check
- Checked and corrected data types for each column (numeric, text, date).
- Standardized inconsistent category labels (e.g., merging duplicate "Low Fat" naming variants such as "LF", "low fat").
- Handled missing values in key fields (e.g., item weight, outlet size) using appropriate imputation or exclusion logic.
- Removed duplicate records and validated referential integrity between item and outlet dimensions.
- Verified row counts and totals against the source data after each transformation step.

### 4. Data Modeling
- Structured the dataset following a **star schema** approach: fact table (sales transactions) linked to dimension tables (Item, Outlet, Date).
- Defined relationships between tables using appropriate cardinality and cross-filter direction.
- Hid unnecessary technical columns from the report view and organized fields into display folders for usability.

### 5. Data Processing
- Applied Power Query transformations: filtering, grouping, merging queries, and pivoting/unpivoting where needed.
- Created calculated columns for derived attributes (e.g., outlet age from establishment year, fat content grouping).
- Optimized query steps for performance and maintainability.

### 6. DAX Calculations
- Built core measures using DAX, including:
  - `Total Sales = SUM(Sales[Amount])`
  - `Average Sales = AVERAGE(Sales[Amount])`
  - `No of Items = DISTINCTCOUNT(Item[Item_ID])`
  - `Average Rating = AVERAGE(Outlet[Rating])`
- Created supporting measures for percentage contribution, year-over-year comparisons, and dynamic tab switching (via a disconnected parameter/field parameter table driving the Total Sales / Average Sales / No of Items / Average Rating tab selector).

### 7. Dashboard Layouting
- Planned the page layout with a left-hand filter panel, top KPI card row, and a right-hand trend chart, following a natural top-to-bottom, left-to-right visual hierarchy.
- Balanced whitespace and grouped related visuals (fat content and item type analysis together; outlet size and outlet location together).

### 8. Charts Development & Formatting
- Built donut charts for Fat Content and Outlet Size, a bar chart for Item Type and Fat by Outlet, an area/line chart for Outlet Establishment trends, and a bar-style breakdown for Outlet Location tiers.
- Applied a consistent green-based color theme aligned with the "grocery/fresh" brand feel.
- Formatted data labels, axis titles, and tooltips for readability; added conditional formatting (color-coded cells) to the Outlet Type table.

### 9. Dashboard Report Development
- Assembled all visuals into a cohesive single-page report.
- Added interactivity: slicers (Outlet Location Type, Outlet Size, Item Type) and a tab-style button group to toggle between KPI views.
- Configured cross-filtering and drill-through behavior so selections in one visual filter the rest of the page.
- Tested interactions and edge cases (e.g., empty filter states) before finalizing.

### 10. Insights Generation
- Reviewed the finished dashboard to extract key business takeaways, for example:
  - **Supermarket Type1** is the largest revenue contributor by a wide margin compared to other outlet types.
  - **Tier 3** locations generate the highest sales, followed by Tier 2 and Tier 1.
  - **Regular** fat-content products outsell **Low Fat** products.
  - **Fruits & Vegetables** and **Snack Foods** are the top-performing item categories.
  - Sales peaked for outlets established around a specific year, suggesting a strong-performing outlet cohort worth investigating further.
- Documented these insights to support business decisions on outlet expansion, inventory focus, and product mix.

---

## 📂 Repository Structure

```
├── grocery.pbix              # Power BI project file
├── data/                     # Source/raw data (if shareable)
├── screenshots/              # Dashboard preview images
└── README.md                 # Project documentation
```

---

## 🚀 Tools & Technologies

- **Power BI Desktop** – data modeling, DAX, and report building
- **Power Query (M)** – data cleaning and transformation
- **DAX** – calculated measures and dynamic KPI logic

---

## 📈 Key Takeaways

This project demonstrates a complete BI workflow — from raw data to a polished, decision-ready dashboard — covering data connection, cleaning, modeling, DAX-based analysis, and visual storytelling, packaged as a single interactive report for business stakeholders.

---

## 📬 Contact

Feel free to reach out or open an issue if you have questions or suggestions about this project.
