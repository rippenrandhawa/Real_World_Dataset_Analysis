# Real-World Dataset Analysis

**Task 3 — Data Analyst Internship portfolio project**

A complete, reproducible analysis of a genuine real-world e-commerce dataset:
**Online Retail** from the UCI Machine Learning Repository (dataset 352,
[DOI 10.24432/C5BW33](https://doi.org/10.24432/C5BW33)).

## 1. Project overview

This project takes 541,909 raw online-retail transaction lines, documents every
data-quality problem, cleans and flags the data without discarding meaningful
records, then performs exploratory, statistical and visual analysis to answer
commercial questions about revenue, customers, products and cancellations.

## 2. Business problem

An online retailer needs to understand where its revenue comes from, which
customers matter most, which products drive sales, and how much revenue is lost
to cancellations — using one year of real transaction data.

## 3. Dataset information

| Property | Value |
|---|---|
| Name | Online Retail |
| Source | UCI Machine Learning Repository |
| DOI | 10.24432/C5BW33 |
| Direct file | `https://archive.ics.uci.edu/ml/machine-learning-databases/00352/Online%20Retail.xlsx` |
| Publisher | UCI (data donated by a UK-based online retail company) |
| Records | 541,909 rows |
| Variables | 8 |
| Period | 1 December 2010 – 9 December 2011 |
| Currency | GBP (£) |

## 4. Tools and technologies

Python 3.13 · pandas · NumPy · SciPy · Matplotlib · Seaborn · Jupyter

## 5. Project objectives

1. Select and document a real-world dataset with verifiable provenance.
2. Profile the data and quantify every quality problem.
3. Clean and flag the data with documented, defensible decisions.
4. Perform univariate, bivariate and multivariate EDA.
5. Apply appropriate statistical tests with explicit hypotheses.
6. Produce publication-quality visualisations.
7. Convert findings into business recommendations.

## 6. Methodology

Load → profile → clean (dedupe, impute, flag) → build a sales view →
univariate / bivariate / multivariate EDA → hypothesis testing →
visualisation → findings → recommendations. All random operations use
`RANDOM_STATE = 42`.

## 7. Directory structure

```
Real_World_Dataset_Analysis/
├── README.md
├── requirements.txt
├── Real_World_Dataset_Analysis.ipynb
├── Real_World_Dataset_Analysis_Report.docx
├── data/
│   ├── Online_Retail_original.xlsx          # original UCI file, preserved
│   ├── raw_dataset.csv                      # raw data exactly as loaded
│   └── cleaned_dataset.csv                  # cleaned + enriched data (536,641 x 14)
└── outputs/
    ├── charts/
    │   ├── 01_monthly_revenue_trend.png
    │   ├── 02_revenue_by_country.png
    │   ├── 03_price_distribution.png
    │   ├── 04_quantity_vs_unit_price.png
    │   ├── 05_invoice_value_by_country.png
    │   ├── 06_correlation_heatmap.png
    │   ├── 07_rfm_scatter.png
    │   └── 08_top_products_revenue.png
    └── summary_tables/
        ├── country_summary.csv
        ├── monthly_summary.csv
        ├── rfm_segment_summary.csv
        └── top_products.csv
```

## 8. Installation

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## 9. Running the notebook

```bash
jupyter lab
# open Real_World_Dataset_Analysis.ipynb and run all cells

# or reproduce headlessly
jupyter nbconvert --execute --to notebook --inplace Real_World_Dataset_Analysis.ipynb
```

## 10. Exercises covered

Data profiling, missing-value analysis, duplicate removal, categorical
standardisation, date parsing, outlier detection (IQR), feature engineering,
univariate / bivariate / multivariate EDA, Welch's t-test, Mann-Whitney U,
Kruskal-Wallis, chi-square, confidence intervals, Spearman correlation and
ordinary least squares regression.

## 11. Key findings

* The UK accounts for **85.1%** of revenue (GBP 8,724,835 of GBP 10,247,610).
* Revenue peaks in **November 2011** at GBP 1,452,113.
* The top 20% of registered customers generate **74.6%** of customer revenue.
* Overseas orders average **GBP 813.45** versus **GBP 487.39** in the UK (p < 0.001).
* Quantity and unit price are negatively rank-correlated (**Spearman −0.41**).
* Cancellations remove **GBP 893,980** of value across 10,587 lines.

## 12. Visualisation previews

| Chart 1 — Monthly revenue | Chart 2 — Revenue by country |
|---|---|
| ![Chart 1](outputs/charts/01_monthly_revenue_trend.png) | ![Chart 2](outputs/charts/02_revenue_by_country.png) |

| Chart 3 — Price distribution | Chart 4 — Quantity vs price |
|---|---|
| ![Chart 3](outputs/charts/03_price_distribution.png) | ![Chart 4](outputs/charts/04_quantity_vs_unit_price.png) |

## 13. Limitations

* One retailer, one year (2010–2011); findings may not transfer to today's market.
* 24.9% of rows have no customer ID, so guest purchases cannot be attributed.
* Prices are in GBP and no cost data is provided, so profit cannot be computed.
* Cancellations and returns are recorded together.
* Extreme bulk orders are retained and can distort means.

## 14. Future improvements

* Repeat the analysis on recent data and compare year on year.
* Add cost and margin data to measure true profitability.
* Build customer lifetime value, churn and cohort models.
* Attribute orders to marketing channels to test causation.

## 15. References

1. D. Chen, S. L. Sain, K. Guo, "Data mining for the online retail industry:
   A case study of RFM model-based customer segmentation using data mining",
   *Journal of Intelligent Computing*, 2012.
2. UCI Machine Learning Repository, "Online Retail" dataset 352,
   https://doi.org/10.24432/C5BW33
3. pandas, NumPy, SciPy, Matplotlib and Seaborn official documentation.

## 16. Author

Prepared as Task 3 of the Data Analyst Internship portfolio. Environment
versions are pinned in `requirements.txt`.
