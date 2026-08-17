# Maternal Factors and Child Intelligence: A Regression Analysis

A statistical analysis investigating how maternal age and educational attainment relate to child cognitive outcomes (IQ and PPVT scores), using exploratory data analysis, hypothesis-driven visualisation, and simple/multiple linear regression with full diagnostic checking.

## Objective

To examine whether maternal age and education level at the time of childbirth are associated with, and predictive of, child intelligence — measured via PPVT (Peabody Picture Vocabulary Test) scores in one dataset and IQ scores in a second, independent dataset.

## Data

Two publicly available datasets (sourced via Kaggle), each recording a child's cognitive test score alongside maternal age and educational attainment at childbirth. Outliers were identified and removed prior to analysis (originally done in Jamovi via boxplot inspection), and both datasets were checked for missing values.

## Method

- **Exploratory data analysis** — descriptive statistics and null-value checks for both datasets
- **Visualisation** — box plots comparing child test scores across maternal education categories
- **Simple linear regression** — maternal age as a sole predictor of child test scores, for both datasets independently
- **Model diagnostics** — residuals-vs-fitted plots and Q-Q plots to check regression assumptions (homoscedasticity, normality of residuals)
- **Multiple regression** — combining maternal education, age, and (in the second dataset) maternal IQ to assess their joint predictive power
- **Correlation analysis** — a heatmap of relationships between all variables under consideration

## Key findings

- Maternal age alone was a **weak** predictor of child test scores in both datasets (R² of 0.03 and 0.01 respectively), despite reaching statistical significance in isolation
- Maternal education showed a **stronger, statistically significant** positive association with child scores
- When age and education were modelled together, maternal age's apparent effect was largely explained by its correlation with education — i.e. it was a **confounded**, not independent, predictor
- Adding maternal IQ into the model for the second dataset raised the explained variance to ~21%, the best-performing model overall, though a majority of the variance in child scores remained unexplained — indicating other unmeasured factors are also at play

## Repository structure

```
notebooks/
├── 01_eda_and_visualisation.ipynb           # Background, descriptive stats, box plots
├── 02_regression_maternal_age.ipynb         # Simple regression + diagnostics for maternal age
└── 03_multiple_regression_and_conclusion.ipynb  # Multiple regression, correlation heatmap, conclusion
data/
├── child_iq_outliers_removed.csv
└── kid_iq_outliers_removed.csv
requirements.txt
```

## Tools

Python — pandas, NumPy, matplotlib, seaborn, SciPy, statsmodels

## Running it

```bash
pip install -r requirements.txt
jupyter notebook notebooks/
```

Each notebook loads its own data from `../data/` and runs independently.

## Note

This analysis was originally completed as part of a university group project; this repository contains the data cleaning, statistical analysis, visualisation, and interpretation I carried out myself, restructured here into a standalone, runnable form.
