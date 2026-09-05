# E-Commerce Product Analytics & Conversion Prediction

> End-to-end **SQL Server + Python + Machine Learning + Power BI** analytics project for an e-commerce business.

This project analyzes website sessions, pageviews, orders, products, order items, and refunds to understand **sales performance, marketing efficiency, conversion behavior, product profitability, customer retention, and refund risk**.

**Author:** Shubham Vishwakarma  
**Stack:** SQL Server · T-SQL · Python · Pandas · NumPy · Scikit-learn · Jupyter · Power BI

---

## 📌 Project Overview

The business had data across multiple operational tables but lacked a unified, decision-ready analytical view.

The project builds an end-to-end workflow:

```text
Raw E-Commerce Data
        ↓
SQL Server
Audit → Cleaning → Validation → Analytical Views
        ↓
Python
EDA → Diagnostic Analysis → Business Findings
        ↓
Machine Learning
Logistic Regression → Conversion Prediction → Evaluation
        ↓
Power BI
Interactive Dashboards
        ↓
Business Recommendations
```

---

## 1. Business Problem

The business needs a unified view of performance to answer questions such as:

- Which marketing channels generate valuable traffic?
- Which devices convert better?
- Which products drive revenue and gross profit?
- Where are refunds concentrated?
- How do repeat and new sessions perform?
- How has session and order performance changed over time?
- Can website-session characteristics provide useful signals for conversion prediction?

The objective is to turn raw operational data into **reliable, decision-ready business insights**.

---

## 2. Project Objectives

- Build a clean and reproducible SQL Server analytical layer.
- Audit and validate source data.
- Create consistent KPI definitions and analytical views.
- Perform descriptive analysis — **what happened?**
- Perform diagnostic analysis — **where are the important differences and risks?**
- Build four Power BI dashboards for self-service reporting.
- Develop a first-pass Logistic Regression model for session conversion.
- Evaluate the model honestly, including class imbalance.
- Translate findings into practical business recommendations.

---

## 3. Headline Results

| KPI | Value |
|---|---:|
| Gross Revenue | **$1.94M** |
| Net Revenue | **$1.85M** |
| Total Orders | **32,313** |
| Total Sessions | **472,871** |
| Conversion Rate | **6.83%** |
| Average Order Value | **$59.99** |
| Gross Margin | **62.74%** |
| Refund % of Revenue | **4.40%** |

### Key findings

- **The Original Mr. Fuzzy** contributes approximately **62% of total revenue**.
- Mobile conversion is **3.09%**, compared with **8.50% on desktop**.
- Repeat sessions convert at **7.83%**, compared with **6.64% for new sessions**.
- High traffic volume does not automatically mean high marketing efficiency.
- Refund dollars are concentrated in the highest-volume product.
- Session volume has declined since late 2014, contributing to lower order volume.

---

## 4. Repository Structure

```text
ecommerce-product-analytics/
│
├── 01_SQL_Codes/
│   ├── FINAL_SQL_MASTER.sql
│   ├── 01_Final_Audit_Revalidation.sql
│   ├── 02_Data_Cleaning_and_Transformation.sql
│   ├── 03_KPI_Definitions.sql
│   ├── 04_EDA_Executive_Sales.sql
│   ├── 05_EDA_Website_Marketing.sql
│   ├── 06_EDA_Product_Refund.sql
│   ├── 07_EDA_Customer.sql
│   ├── 08_Diagnostic_Analysis.sql
│   ├── 09_Final_Data_Quality_Reconciliation.sql
│   ├── 10_Final_KPI_Snapshot.sql
│   └── ER-Diagram.png
│
├── 02_PowerBI_Dashboard/
│   ├── PRP_Ecommerce_Digital_Analytics_Dashboard.pbix
│   └── Power BI Dashboards.pdf
│
├── 03_Python_Analysis_ML/
│   ├── ECommerce_Analytics_Python_ML_Analysis.ipynb
│   ├── conversion_prediction_model.pkl
│   └── outputs/
│
├── 04_Presentation/
│   ├── PRP_Ecommerce_Digital_Analytics_Final_Presentation.pptx
│   └── PRP_Ecommerce_Digital_Analytics_Final_Presentation.pdf
│
├── screenshots/
├── data/
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

---

## 5. Data Model

The analytical model is based on six core source tables:

- `products`
- `website_sessions`
- `website_pageviews`
- `orders`
- `order_items`
- `order_item_refunds`

### Entity Relationship Diagram

![E-commerce entity relationship diagram](screenshots/conversiongap_by_device_and _repeat_status.png)

The SQL layer keeps the raw `dbo` tables intact and creates cleaned analytical views under the `analytics` schema.

```text
dbo raw tables
      ↓
analytics.vw_* clean analytical views
      ↓
Python + Power BI
```

---

## 6. SQL Server Analysis

SQL Server is the foundation of the project.

### Data-quality and analytical work

- Row-count validation
- Missing-value checks
- Duplicate checks
- Invalid-value checks
- Key and relationship validation
- Data cleaning and transformation
- KPI definitions
- Executive sales analysis
- Website and marketing analysis
- Product and refund analysis
- Customer/session analysis
- Diagnostic analysis
- Final KPI reconciliation

The SQL scripts are organized so the analytical workflow is **reproducible and traceable**.

---

## 7. KPI Framework

### Gross Revenue

Sum of order-line selling prices.

### Gross Profit

```text
Gross Profit = Revenue - COGS
```

### Gross Margin %

```text
Gross Margin % = (Revenue - COGS) / Revenue × 100
```

### Average Order Value

```text
AOV = Revenue / Number of Orders
```

### Net Revenue

```text
Net Revenue = Gross Revenue - Refunds
```

### Conversion Rate

```text
Conversion Rate =
Converted Sessions / Total Sessions × 100
```

### Revenue per Session

```text
Revenue per Session =
Revenue / Sessions
```

### Refund Rate

```text
Refund Rate =
Refund Amount / Revenue × 100
```

---

## 8. Power BI Dashboards

Four dashboards were created for interactive business analysis.

### Executive Overview

![Executive Overview dashboard](screenshots/Executive-Overview.png)

High-level view of revenue, orders, sessions, conversion, AOV, profitability, and business performance.

### Marketing & Session Funnel

![Marketing and Session Funnel dashboard](screenshots/Marketing_Analysis_Python_Code.png)

Analyzes marketing sources, session behavior, conversion, device performance, and trends.

### Product & Refunds

![Product and Refunds dashboard](screenshots/Gross_Profit_by_Product_Python_Visualization.png)

Analyzes product revenue, gross profit, margins, refund amounts, and refund rates.

### Sales & Profitability

![Sales and Profitability dashboard](screenshots/Produt_sales_profit_margin__By_SQL.png)

Analyzes sales trends, profitability, and supporting KPIs.

**Power BI file:** `02_PowerBI_Dashboard/PRP_Ecommerce_Digital_Analytics_Dashboard.pbix`  
**Static export:** `02_PowerBI_Dashboard/Power BI Dashboards.pdf`

---

## 9. Python EDA & Business Analysis

Python was used after the SQL analytical layer for:

- SQL Server data extraction
- Data validation
- Missing-value analysis
- Duplicate analysis
- Descriptive statistics
- Time-series analysis
- Marketing analysis
- Device analysis
- Product analysis
- Refund analysis
- Repeat vs new-session analysis
- Business rankings and findings

### Main libraries

```text
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
pyodbc
Jupyter
```

The Jupyter notebook documents the complete Python analysis workflow.

---

## 10. Machine Learning — Conversion Prediction

A first-pass **Logistic Regression** model was developed to predict whether a website session converts.

### Target

```text
converted_session

0 = Not converted
1 = Converted
```

### Session features

- Reporting device type
- UTM source
- UTM campaign
- UTM content
- HTTP referrer
- Repeat-session flag
- Session hour
- Day
- Month
- Year

### Leakage control

`order_count` and `session_revenue` were intentionally excluded because they are outcome-related variables and could reveal conversion information.

This prevents **data leakage** and makes the prediction setup more realistic.

---

## 11. Model Evaluation

| Metric | Score |
|---|---:|
| Accuracy | **93.17%** |
| Precision | **0.00** |
| Recall | **0.00** |
| F1 Score | **0.00** |
| ROC-AUC | **0.632** |

### Simple interpretation

Only about **6.8% of sessions convert**, so the target is highly imbalanced.

Therefore, 93% accuracy can look strong even when the model predicts "not converted" for almost every session.

**ROC-AUC = 0.632** means:

> The model is **better than random at distinguishing converters from non-converters, but its predictive ability is still limited**.

The model should therefore be treated as a **first-pass analytical baseline**, not a production-ready prediction system.

### Potential next steps

- `class_weight='balanced'`
- SMOTE / oversampling
- Decision-threshold tuning
- Precision-recall analysis
- Additional feature engineering
- Tree-based model comparison
- Cross-validation and model selection

---

## 12. Key Business Insights

### Revenue concentration

**The Original Mr. Fuzzy** contributes approximately **62% of total revenue**, creating both strong business importance and product concentration risk.

### Mobile conversion gap

```text
Mobile   = 3.09%
Desktop  = 8.50%
```

This gap suggests investigating mobile UX, navigation, page performance, and checkout friction.

### Marketing efficiency

`gsearch` generates high traffic volume, but traffic volume alone does not represent business value.

Channels should be evaluated using:

- Conversion rate
- Revenue per session
- Revenue
- Profitability

### Repeat-session performance

```text
Repeat sessions = 7.83%
New sessions    = 6.64%
```

Repeat visitors show stronger conversion performance, supporting further retention and remarketing analysis.

### Product and refund risk

Refund dollars are concentrated in the highest-volume product, so refund monitoring should consider both **absolute refund dollars and refund rate**.

### Session decline

Session volume has declined since late 2014, contributing to lower order volume and representing an area for further investigation.

---

## 13. Business Recommendations

| Area | Recommendation | Expected Direction |
|---|---|---|
| Mobile Experience | Audit and improve the mobile checkout funnel | Improve mobile conversion |
| Marketing | Evaluate channels using conversion and revenue/session rather than traffic alone | Improve marketing efficiency |
| Product Mix | Protect high-revenue products and promote strong-margin, low-refund products | Improve profitability |
| Product Quality | Investigate high-refund products | Reduce refund leakage |
| Customer Retention | Develop incentives for repeat visitors | Increase repeat-session contribution |
| ML Model | Address class imbalance and tune the prediction threshold | Improve useful predictive performance |

---

## 14. How to Run

### SQL Server

1. Create a database, for example `PRP_Ecommerce_Analytics`.
2. Import the six source CSV files into matching `dbo.*` tables.
3. Run `01_SQL_Codes/FINAL_SQL_MASTER.sql`.
4. Verify the generated `analytics.vw_*` views.
5. Individual EDA scripts can also be executed separately.

### Python / Jupyter

Create a virtual environment:

```bash
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Open:

```text
03_Python_Analysis_ML/ECommerce_Analytics_Python_ML_Analysis.ipynb
```

The notebook connects to SQL Server using `pyodbc`. Update the connection variables for your own SQL Server environment before running.

### Power BI

Open:

```text
02_PowerBI_Dashboard/PRP_Ecommerce_Digital_Analytics_Dashboard.pbix
```

and configure the SQL Server connection for your environment.

The PDF export and screenshots can be viewed without Power BI Desktop.

---

## 15. Deliverables

| Deliverable | Location |
|---|---|
| SQL analysis and data-quality scripts | `01_SQL_Codes/` |
| Power BI dashboard | `02_PowerBI_Dashboard/` |
| Python EDA & ML notebook | `03_Python_Analysis_ML/` |
| Saved ML model | `03_Python_Analysis_ML/conversion_prediction_model.pkl` |
| Python business outputs | `03_Python_Analysis_ML/outputs/` |
| Final presentation | `04_Presentation/` |
| Dashboard and project images | `screenshots/` |

---

## 16. Data Availability

The project uses six raw CSV files:

```text
products.csv
website_sessions.csv
website_pageviews.csv
orders.csv
order_items.csv
order_item_refunds.csv
```

Large raw files may be excluded from the public GitHub repository to keep the repository lightweight.

If the data is hosted separately, add the approved access link below:

```text
Data access: <ADD YOUR DATA LINK HERE>
```

Do not commit confidential, restricted, or sensitive business data to a public repository.

---

## 17. Skills Demonstrated

### SQL / Data Analytics

- SQL Server / T-SQL
- Data cleaning
- Data validation
- Data-quality checks
- Joins
- CTEs
- Aggregations
- Window functions
- CASE expressions
- Date functions
- Views
- KPI development
- Descriptive analysis
- Diagnostic analysis

### Python

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Data manipulation
- Visualization
- Business analysis

### Machine Learning

- Binary classification
- Logistic Regression
- Train/test split
- Feature preprocessing
- Pipeline
- ColumnTransformer
- Probability prediction
- Confusion matrix
- Classification report
- ROC curve
- ROC-AUC
- Class imbalance
- Data leakage prevention

### Power BI

- Power Query
- Data modeling
- DAX
- KPI cards
- Interactive filters
- Time-series analysis
- Product analysis
- Marketing analysis
- Business dashboards

---

## 18. Final Conclusion

This project demonstrates an end-to-end analytics workflow:

```text
SQL Server
    ↓
Data Auditing & Cleaning
    ↓
KPI & Analytical Views
    ↓
Python EDA
    ↓
Diagnostic Business Analysis
    ↓
Logistic Regression
    ↓
Model Evaluation
    ↓
Power BI Dashboards
    ↓
Business Insights
    ↓
Recommendations
```

The analysis highlights **mobile conversion, marketing efficiency, product concentration, refund risk, repeat-session performance, and declining session volume** as important areas for business attention.

The Logistic Regression model provides some useful signal, but its current performance is limited by **class imbalance and weak positive-class performance**. It should therefore be treated as a baseline for further experimentation rather than a production decision engine.

Overall, the project demonstrates how raw e-commerce data can be transformed into **validated metrics, interactive reporting, analytical insights, and actionable business recommendations**.

---

## 👤 Author

**Shubham Vishwakarma**  
**Data Analyst | SQL | Python | Power BI | Machine Learning**

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
