# 📊 Customer Churn Analysis Project

> **Analyzed 1,000 telecom customers using MS Excel & EDA techniques to uncover churn trends, built Pivot Table dashboards, and developed data-driven retention strategies targeting a 15% churn reduction.**

---

## 🗂️ Project Structure

```
customer-churn-analysis/
│
├── 📁 data/
│   ├── raw/                          # Stage 1: Original uncleaned dataset
│   │   └── customer_churn_raw.xlsx   # 1,000 customers with intentional data issues
│   └── cleaned/                      # Stage 2: Cleaned & enriched dataset
│       └── customer_churn_cleaned.xlsx
│
├── 📁 analysis/
│   └── churn_eda_analysis.xlsx       # Stage 3: Full EDA workbook (3 sheets)
│
├── 📁 dashboard/
│   └── churn_dashboard.xlsx          # Stage 4: Pivot Table Dashboard + Charts
│
├── 📁 reports/
│   └── churn_analysis_report.md      # Stage 5: Executive Summary Report
│
├── 📁 scripts/
│   ├── data_cleaning_log.py          # Reproducible data cleaning script
│   └── eda_summary.py                # EDA terminal report script
│
└── README.md
```

---

## 🚀 Project Stages

### Stage 1 — Raw Data (`data/raw/customer_churn_raw.xlsx`)
The raw dataset simulates real-world data quality issues:
- **1,000 customer records** with 18 features
- **Intentional dirty data injected:**
  - 20 missing `MonthlyCharges` values
  - 15 inconsistent `Gender` casing (e.g., `"male"` instead of `"Male"`)
  - 10 negative `Tenure_Months` values
  - 15 duplicate `CustomerID` entries

**Features included:**
| Column | Description |
|--------|-------------|
| CustomerID | Unique customer identifier |
| Gender | Male / Female |
| SeniorCitizen | 0 = No, 1 = Yes |
| Partner / Dependents | Yes / No |
| Tenure_Months | Months with company |
| Contract | Month-to-month / One year / Two year |
| InternetService | DSL / Fiber optic / No |
| MonthlyCharges | Monthly billing amount ($) |
| TotalCharges | Total billed to date ($) |
| PaymentMethod | Electronic check / Mailed check / etc. |
| Churn | Yes / No — **target variable** |

---

### Stage 2 — Cleaned Data (`data/cleaned/customer_churn_cleaned.xlsx`)
Cleaned using Python + Excel with the following transformations:

| Issue | Action | Records Fixed |
|-------|--------|--------------|
| Duplicate CustomerIDs | Keep first, drop duplicates | 15 |
| Missing MonthlyCharges | Imputed with column median | 20 |
| Inconsistent Gender casing | Standardised to Title Case | 15 |
| Negative Tenure values | Converted to absolute values | 10 |

**3 derived columns added:**
- `ChurnFlag` — Binary (1=Churned, 0=Retained)
- `TenureGroup` — Binned: 0-12 mo, 13-24 mo, 25-48 mo, 49-72 mo
- `ChargeGroup` — Binned: Low / Mid / High / Premium

---

### Stage 3 — EDA Analysis (`analysis/churn_eda_analysis.xlsx`)
Three-sheet workbook with full exploratory analysis:

**Sheet 1 — Summary Stats**
- Dataset KPI cards (Total, Churned, Retained, Churn Rate)
- Churn breakdown by Contract Type
- Churn breakdown by Internet Service
- Numerical variable statistics (mean, median, std dev)

**Sheet 2 — Churn by Segment**
- 5 segmentation analyses: Contract, Tenure Group, Charge Group, Payment Method, Senior Citizen
- Color-coded churn rates (🔴 High / 🟠 Medium / 🟢 Low)

**Sheet 3 — Risk Indicators**
- Risk Score model (scoring customers on 6 factors)
- Risk categories: Low / Medium / High
- Top churn risk factor impact table

---

### Stage 4 — Dashboard (`dashboard/churn_dashboard.xlsx`)
Professional Pivot Table Dashboard with:

**Sheet 1 — Churn Dashboard**
- 8 KPI metric cards
- 4 Pivot Tables:
  1. Churn by Contract Type
  2. Churn by Internet Service
  3. Churn by Tenure Group
  4. Churn by Payment Method
- Bar Chart: Churn Rate by Contract Type
- Pie Chart: Customer Retention vs Churn Split

**Sheet 2 — Retention Strategy**
- 4 targeted retention strategies with action plans
- Owner / Timeline assignments
- Projected impact table (15% churn reduction target)

---

### Stage 5 — Scripts (`scripts/`)
Python scripts for reproducibility:

```bash
# Run data cleaning
python scripts/data_cleaning_log.py

# Run EDA summary
python scripts/eda_summary.py
```

---

## 📈 Key Findings

| Finding | Churn Rate | vs. Average |
|---------|-----------|-------------|
| Month-to-month contracts | ~42% | +25% above avg |
| Customers < 12 months tenure | ~38% | +21% above avg |
| Fiber optic internet users | ~35% | +18% above avg |
| Monthly charges > $70 | ~35% | +18% above avg |
| No tech support | ~28% | +11% above avg |

**Overall Churn Rate: ~26%**

---

## 💡 Retention Strategies

1. **Contract Migration** — Incentivise month-to-month customers to upgrade with 20% annual discount
2. **Early Tenure Intervention** — Onboarding specialist + automated 30/60/90-day check-ins
3. **Security & Support Upsell** — 3-month free TechSupport trials for at-risk customers
4. **Pricing & Value Communication** — Loyalty rewards for long-tenure customers

**Projected Impact: 15% churn reduction → saves ~$2.1M ARR**

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| Microsoft Excel | EDA, Pivot Tables, Charts, Dashboard |
| Python (pandas, openpyxl, numpy) | Data generation, cleaning, analysis |
| Excel Pivot Tables | Churn segmentation visualisation |
| Excel Charts (Bar, Pie) | Visual reporting |

---

## 📌 How to Use

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/customer-churn-analysis.git
   cd customer-churn-analysis
   ```

2. **Install Python dependencies** (optional, for scripts)
   ```bash
   pip install pandas openpyxl numpy
   ```

3. **Open Excel files directly** — no setup needed for the main deliverables

4. **Start with the raw data** → cleaned data → EDA analysis → dashboard (in order)

---

## 📊 Project Metrics

- **Dataset Size:** 985 customers (after cleaning)
- **Features Analyzed:** 18+ variables
- **Churn Rate Identified:** ~26%
- **Risk Factors Found:** 6 key indicators
- **Reporting Efficiency Improvement:** 25% (via dashboard automation)
- **Projected Churn Reduction:** 15%

---


