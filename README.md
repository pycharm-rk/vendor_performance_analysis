# Vendor Sales, Purchase & Inventory Performance Analysis

## 📌 Project Overview
This project analyzes vendor-level sales, purchasing behavior, profitability, and inventory efficiency using transactional data. The objective is to uncover actionable business insights related to supplier dependency, pricing strategies, inventory turnover, and profit optimization.

The project follows an end-to-end analytics workflow:
**Raw CSV Data → SQLite Database → Python Analysis → Power BI Dashboard**

---

## 📊 Business Objectives
- Identify top vendors and brands by sales and purchase contribution
- Analyze supplier concentration and dependency risk
- Evaluate the impact of bulk purchasing on unit cost
- Detect slow-moving inventory and capital locked in unsold stock
- Compare profitability between high- and low-performing vendors
- Provide actionable, data-driven business recommendations

---

## 🗂 Data Sources
The project uses multiple large CSV files containing transactional data:

- `begin_inventory.csv`
- `end_inventory.csv`
- `purchase_prices.csv`
- `purchases.csv`
- `sales.csv`
- `vendor_invoice.csv`

⚠️ **Note:** Due to file size limitations, raw data files and the SQLite database are not included in this repository.

---

## 🛠 Data Ingestion & Storage
- Raw CSV files are ingested using a Python script
- Data is stored in a SQLite database (`inventory.db`)
- SQLAlchemy is used for database interaction
- Logging is implemented to track ingestion progress and execution time

---

## 🔄 Data Transformation & Feature Engineering
A consolidated analytical table `vendor_sales_summary` was created after:
- Removing inconsistent records (zero sales, negative profit/margin)
- Engineering business metrics such as:
  - Gross Profit
  - Profit Margin (%)
  - Stock Turnover
  - Sales-to-Purchase Ratio
  - Unsold Inventory Value
  - Order Size Segmentation (Small / Medium / Large)

---

## 📈 Exploratory Data Analysis (EDA)
Key analyses include:
- Distribution and outlier analysis
- Correlation analysis between pricing, sales, and profitability
- Vendor and brand contribution analysis (Pareto / 80–20 rule)
- Inventory efficiency and capital lock-in assessment

---

## 📊 Statistical Analysis
- Vendors segmented using 25th and 75th percentiles of total sales
- Compared profit margins between high- and low-performing vendors
- Applied Welch’s two-sample t-test
- 95% confidence intervals calculated

**Result:**  
A statistically significant difference exists in profit margins between vendor groups.

---

## 📉 Power BI Dashboard
An interactive Power BI dashboard was built using the processed dataset.

### Dashboard Highlights:
- KPI cards: Total Sales, Total Purchases, Gross Profit, Profit Margin, Unsold Capital
- Top vendors and brands by sales
- Purchase contribution (Pareto & donut charts)
- Low-performing vendors and brands
- Sales vs Profit Margin scatter analysis

📷 Dashboard screenshots are available in the `powerbi/` folder.

---

## 💡 Key Insights
- Top 10 vendors contribute ~65% of total purchases (supplier concentration risk)
- Bulk purchasing reduces unit cost by ~72%
- Low-performing vendors maintain higher margins but struggle with sales volume
- ~$2.71M capital locked in unsold inventory
- High sales volume does not always translate to higher profitability

---

## ✅ Business Recommendations
- Diversify vendor partnerships to reduce dependency risk
- Leverage bulk purchasing while optimizing inventory control
- Address slow-moving inventory through demand planning and clearance strategies
- Improve marketing and distribution for high-margin, low-sales vendors
- Focus cost efficiency initiatives on top-selling vendors

---

## 🧰 Tools & Technologies
- **Python:** Pandas, NumPy, Matplotlib, Seaborn, SciPy
- **SQL:** SQLite, SQLAlchemy
- **Visualization:** Power BI, Matplotlib, Seaborn
- **Notebook Environment:** Jupyter

---

## 📁 Repository Structure
```
├── data/
│ ├── readme.md
│ ├── vendor_sales_summary.csv
|
├── notebooks/
│ ├── 01_data_ingestion.ipynb
│ ├── 02_exploratory_analysis.ipynb
│ └── 03_vendor_performance_analysis.ipynb
│
├── scripts/
| ├── get_vendor_summary.py
│ └── ingestion_db.py
│
├── powerbi/
| ├── vendor_performance_analysis.pbix
│ └── dashboard_screenshot.png
│
├── reports/
│ └── project_report.docx
│
└── README.md
```

---

## 🚀 Conclusion
This project demonstrates an end-to-end data analytics pipeline that transforms raw transactional data into actionable business insights using Python, SQL, statistical analysis, and Power BI.
