# Exploratory Data Analysis of Large-Scale Retail Transaction Data

**Using Univariate, Bivariate, and Multivariate Statistical Techniques**

- **Author:** Roshan Kumar
- **Company:** NextHikes IT Solutions

## Overview

This project performs Exploratory Data Analysis (EDA) on a retail transaction dataset with **100,000 records and 18 variables**. It focuses on distribution analysis, relationships between variables, outlier detection, and business insights, as a foundation for predictive modelling.

## Objectives

- Perform univariate, bivariate and multivariate analysis
- Detect and interpret outliers
- Measure correlation between numerical variables
- Analyze skewness and kurtosis
- Extract statistically meaningful business insights

## Dataset

`retail_large_dataset.csv` has 100,000 rows and 18 columns:

| Type | Columns |
|---|---|
| Customer | `customer_id`, `age`, `gender`, `city`, `state`, `customer_segment` |
| Order | `order_id`, `order_date` |
| Product | `product_category`, `product_subcategory`, `product_price`, `quantity` |
| Pricing | `discount_percentage`, `final_price` |
| Logistics | `payment_method`, `shipping_type`, `delivery_days`, `return_status` |

There are no missing values or duplicate rows. Order dates run from 2023 to 2024 (format `dd-mm-yyyy`).

## What the notebook covers

1. Dataset overview and data quality checks
2. **Univariate analysis**: mean, median, standard deviation, min/max, skewness, kurtosis; frequency distributions of categorical variables
3. **Outlier detection**: boxplots, IQR method, Z-score method
4. **Bivariate analysis**: Pearson correlation, numerical vs categorical comparisons (ANOVA, chi-square, t-test)
5. **Correlation matrix** heatmap and multicollinearity check (VIF)
6. **Multivariate analysis**: category × discount × revenue, segment × age × spending, delivery × shipping × returns
7. **Skewness and kurtosis** interpretation
8. Key statistical findings, comparison with the expected insights in the project brief, and conclusion

## Key findings

- `final_price` is right-skewed (skew ≈ 0.93); mean ≈ 64.2k vs median ≈ 49.8k.
- `product_price` (r ≈ 0.73) and `quantity` (r ≈ 0.58) drive `final_price`; discount has a weak negative effect (r ≈ −0.14).
- Discount is uniformly distributed from 0 to 30%; the low-discount band (0–10%) earns the most total revenue.
- Return rate is about 14.8% and does not differ meaningfully by category, shipping type or delivery time.
- Express and Standard shipping have the same average delivery time (about 5.5 days), which is worth investigating operationally.
- Outliers (1,335 high `final_price` orders) are all valid 4-unit premium or bulk orders, so they were kept.
- Predictors are independent of each other (VIF ≈ 1).

Several example insights in the project brief (for example, "Regular" being the majority segment, or Electronics having the most transactions) are not supported by this data. The dataset looks synthetically generated with independent uniform variables, so the notebook reports what the data actually shows.

## Files

| File | Description |
|---|---|
| `EDA_Retail_Project.ipynb` | Main notebook with code, outputs and charts |
| `EDA_Retail_Project.html` | Same notebook as a static HTML page |
| `retail_large_dataset.csv` | Dataset (100,000 rows) |

## How to run

```bash
pip install numpy pandas matplotlib seaborn scipy jupyter
jupyter notebook EDA_Retail_Project.ipynb
```

Keep `retail_large_dataset.csv` in the same folder as the notebook.

## Tools

Python, NumPy, Pandas, Matplotlib, Seaborn, SciPy
