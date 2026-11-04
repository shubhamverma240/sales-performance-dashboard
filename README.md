# 📊 Sales Performance Analysis & Reporting Dashboard

An end-to-end data analytics project that turns messy retail sales exports into clean data, SQL insights, monthly reports, and an interactive Power BI dashboard.

![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoftexcel&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black)

---

## 🎯 Project Goal

Track sales performance by **region**, **product**, and **month**, and present the results in an easy-to-read, interactive dashboard that helps spot trends and anomalies at a glance.

## 🛠️ Tools & Skills

| Area | Details |
|------|---------|
| **Excel** | Data cleaning, Pivot Tables, XLOOKUP, monthly reporting |
| **SQL** | `SELECT`, `WHERE`, `JOIN`, `GROUP BY` for sales summaries |
| **Power BI** | KPIs, charts, slicers/filters, documented metric definitions |
| **Skills** | Data cleaning, data analysis, data visualization, reporting |

## 🔄 Workflow

1. **Excel: Data Cleaning**
   Standardized the raw multi-source data into one consistent dataset:
   - Trimmed extra spaces (e.g. `" Mobile"`, `"South "`)
   - Fixed inconsistent casing (e.g. `WEST`, `west`, `West` → `West`)
   - Handled missing Region and Quantity values
   - Removed duplicate orders
2. **SQL: Analysis**
   Loaded the cleaned data into a `sales` table with a `product_list` lookup (product → category) and summarized sales by region, product, and month.
3. **Excel: Monthly Reporting**
   Built monthly reports with Pivot Tables and XLOOKUP.
4. **Power BI: Dashboard**
   Built an interactive dashboard with KPIs, filters, and a metric definitions sheet.

## 📁 Repository Structure

```
├── data/
│   ├── sales_data_raw.csv        # Original raw dataset (310 rows)
│   ├── sales_data_raw.xlsx       # Raw dataset in Excel format
│   └── clean_data.xlsx           # Cleaned data (300 rows) + pivot summaries
├── sql/
│   └── sales_setup.sql           # Table creation + data inserts
├── dashboard/
│   └── sales_dashboard.pbix      # Power BI dashboard
├── presentation/
│   └── Sales_Performance_Analysis___Reporting_Dashboard.pptx
└── README.md
```

## 🗂️ Dataset

| Column | Description |
|--------|-------------|
| `Order_ID` | Unique order identifier |
| `Order_Date` | Date of the order (2025) |
| `Region` | North, South, East, West |
| `Product` | Laptop, Mobile, Monitor, Headphones, Keyboard, Mouse |
| `Quantity` | Units sold |
| `Unit_Price` | Price per unit |
| `Sales` | Quantity × Unit_Price (calculated) |

## 📈 Key Insights

- **Total sales: ₹12.28M** across 300 cleaned orders (average order value ≈ ₹40.9K).
- **Laptops and Mobiles drive the business:** together they bring in about **81%** of total sales.
- **East is the top region** (₹3.44M), followed by South (₹3.06M), West (₹2.96M), and North (₹2.47M).
- **Strongest month: August** (₹1.86M), followed by May (₹1.69M). **Weakest: July** (₹0.46M).
- Some orders had no region recorded (₹0.35M of sales), a data-quality gap worth fixing at the source.

> Currency is assumed to be INR; change the symbol if your data uses another.

## 🚀 How to Use

**SQL**
```sql
-- Run in SQLite / any SQL client
-- 1. Open sql/sales_setup.sql and execute it to create and fill the tables
-- 2. Example query: sales by region
SELECT Region, SUM(Sales) AS Total_Sales
FROM sales
GROUP BY Region
ORDER BY Total_Sales DESC;
```

**Power BI**
1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows).
2. Open `dashboard/sales_dashboard.pbix`.
3. Use the slicers to filter by region, product, and month.

## 🖼️ Dashboard Preview

<!-- Upload a screenshot of your dashboard to the repo, then update the path below -->
![Dashboard Preview](images/dashboard.png)

## 👤 Author

**Shubham Verma**
Data Analytics | Excel · SQL · Power BI


---

⭐ If you found this project useful, consider giving it a star!
