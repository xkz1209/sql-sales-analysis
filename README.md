# Sales Performance & Customer Analytics | SQL Server (T-SQL)

**End-to-End SQL Analytics Portfolio Project | Business Intelligence & Customer Analytics**

## Project Overview

This project analyzes historical retail sales data using Microsoft SQL Server (T-SQL) to evaluate revenue performance, purchasing behavior, product profitability opportunities, and customer value.

The objective is to transform transactional data into actionable business insights by developing key performance indicators (KPIs), examining sales trends, identifying revenue concentration, and building reusable reporting views.

The analysis supports common business intelligence questions:

- How has revenue performance changed over time?
- Which product categories and individual products drive sales?
- Which customer segments contribute the most revenue?
- How can customer and product performance be monitored through standardized reporting?
- What business opportunities can be identified from historical sales patterns?

## Tech Stack

- **Database:** Microsoft SQL Server
- **Query Language:** T-SQL
- **Development Environment:** SQL Server Management Studio (SSMS)
- **SQL Techniques:** Joins, Aggregations, CTEs, Subqueries, Window Functions, CASE Expressions, Date Functions, SQL Views
- **Analytical Methods:** KPI Reporting, Time-Series Analysis, Revenue Contribution Analysis, Customer Segmentation, Product Performance Analysis

## Dataset & Data Model

The project uses a retail sales dataset organized into three relational tables:

| Table | Description |
|---|---|
| `gold.fact_sales` | Transaction-level sales, orders, quantities, prices, and dates |
| `gold.dim_customers` | Customer attributes and demographic information |
| `gold.dim_products` | Product descriptions, categories, subcategories, and costs |

**Analysis scope:**

- 60,398 sales records
- 27,659 distinct orders
- 18,484 purchasing customers
- Historical sales data covering multiple years

The analysis joins sales transactions with customer and product dimensions to evaluate business performance at the order, customer, product, and category levels.

## Analytical Framework

### 1. Exploratory Data Analysis (EDA)

Explored the database structure, dimensions, dates, and business measures to understand the underlying dataset.

Key activities included:

- Inspecting database tables and column structures.
- Examining customer demographics and product categories.
- Identifying transaction date ranges.
- Calculating sales, order, quantity, product, and customer metrics.
- Ranking customers and products by revenue contribution.

**Business purpose:** Establish a reliable understanding of sales activity and define baseline KPIs for subsequent analysis.

### 2. Sales Trends & Change-Over-Time Analysis

Analyzed monthly and annual revenue patterns to evaluate historical business performance.

Methods included:

- Monthly and annual revenue aggregation.
- Year-over-year (YoY) growth calculations.
- Cumulative sales using window functions.
- Comparisons against historical averages and prior-year performance.

**Key findings:**

- Revenue declined by approximately **17.4% YoY in 2012**.
- Revenue subsequently increased by approximately **179.8% YoY in 2013**.

**Business implication:** Large fluctuations in annual revenue warrant further investigation into demand changes, product mix, and sales activity.

### 3. Product Performance & Revenue Contribution

Evaluated revenue concentration across product categories and individual products.

The analysis included:

- Revenue contribution by product category.
- Top- and bottom-performing product rankings.
- Product performance comparisons against historical benchmarks.
- Revenue-based product segmentation.

**Key findings:**

- The Bikes category accounted for approximately **96.5% of total sales revenue**.
- The top five products contributed approximately **22.7% of total revenue**.
- Among 130 revenue-generating products, **66 high-performing products accounted for approximately 94.2% of reported product revenue**.

**Business implication:** Revenue is highly concentrated in a limited set of categories and products. These findings can inform inventory prioritization, product portfolio reviews, and sales planning.

### 4. Customer Segmentation & Revenue Analysis

Segmented purchasing customers based on cumulative spending and purchasing-history duration.

The SQL segmentation logic defines three groups:

| Segment | Classification |
|---|---|
| VIP | Purchase history of at least 12 months and cumulative spending above 5,000 |
| Regular | Purchase history of at least 12 months and cumulative spending of 5,000 or less |
| New | Purchase history shorter than 12 months |

**Key findings:**

- **18,484 purchasing customers** were included in the analysis.
- **1,655 customers** were classified as VIP.
- VIP customers represented approximately **9.0% of purchasing customers**.
- This segment contributed approximately **36.7% of total revenue**.

**Business implication:** A relatively small customer segment generates a disproportionately large share of revenue, suggesting opportunities for targeted retention, loyalty initiatives, and customer-value monitoring.

### 5. Reusable SQL Reporting Views

Developed two reusable SQL reporting views to consolidate customer- and product-level performance metrics.

**Customer Reporting — `gold.report_customers`**

Includes:

- Customer information and age groups
- Customer segmentation (VIP, Regular, New)
- Total orders and sales
- Total quantity and distinct products purchased
- Purchasing-history duration
- Purchase recency
- Average Order Value (AOV)
- Average monthly spending

**Product Reporting — `gold.report_products`**

Includes:

- Product and category information
- Product revenue segmentation
- Total orders, revenue, and quantity sold
- Distinct purchasing customers
- Product sales recency and lifespan
- Average selling price
- Average Order Revenue (AOR)
- Average monthly revenue

These reporting views provide reusable analytical datasets for recurring performance analysis and potential downstream BI reporting.

## Key Business Insights

| Business Area | Key Finding | Potential Business Application |
|---|---|---|
| Revenue Performance | 17.4% YoY decline in 2012, followed by 179.8% growth in 2013 | Investigate revenue volatility and underlying sales drivers |
| Category Concentration | Bikes generated 96.5% of revenue | Review category dependence and product diversification opportunities |
| Product Performance | Top five products contributed 22.7% of revenue | Support product prioritization and inventory planning |
| Customer Value | VIP customers represented 9.0% of customers but generated 36.7% of revenue | Inform customer retention and loyalty strategies |
| Product Segmentation | 66 high-performing products contributed 94.2% of reported product revenue | Support product portfolio evaluation |
| Reporting | Two reusable SQL reporting views | Enable standardized customer and product KPI analysis |

**Note:** These are analytical findings and potential business recommendations derived from a historical dataset. They do not represent measured improvements from implemented business decisions.

## Repository Structure

- **`sales_analysis.sql`** — SQL queries for exploratory analysis, trend analysis, revenue contribution, segmentation, performance benchmarking, and reporting views.
- **`data-set/`** — Source data files used for the analysis.
- **`README.md`** — Project overview, methodology, analytical findings, and business implications.

## How to Explore the Project

1. Review the CSV files in the `data-set/` directory to understand the source data.
2. Open `sales_analysis.sql` in SQL Server Management Studio.
3. Prepare the three source tables in the `gold` schema: `fact_sales`, `dim_customers`, and `dim_products`.
4. Run the analytical queries section by section to examine business metrics and findings.
5. Create the customer and product reporting views after the required tables are available.
6. Query `gold.report_customers` and `gold.report_products` to explore the resulting reporting datasets.

**Setup note:** The SQL script assumes that the source tables have already been loaded into SQL Server under the `gold` schema. Database creation and CSV import steps are not included in the analytical script.

## Project Scope & Limitations

- This is a portfolio analytics project using historical retail sales data, not a production business intelligence deployment.
- Revenue trends are descriptive and do not establish the causes of sales changes.
- Customer and product segments use predefined business rules rather than predictive modeling.
- Revenue concentration highlights potential opportunities but does not independently measure profitability.
- Reporting views provide reusable SQL outputs; no automated dashboard deployment or production scheduling is claimed.

## Skills Demonstrated

**Technical:** SQL Server, T-SQL, CTEs, Window Functions, Joins, Aggregations, SQL Views, Data Reporting

**Analytical:** KPI Development, Revenue Analysis, Customer Segmentation, Trend Analysis, Product Performance Evaluation

**Business:** Translating transactional data into business insights, identifying performance drivers, interpreting customer value, and communicating data-driven recommendations

---

**Author:** Jimmy Xu  
**Focus:** Business Analytics | Business Intelligence | SQL Reporting
