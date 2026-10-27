# Project Deliverable 2: Regression Modeling and Performance Evaluation

**Course:** MSCS-634-B01 — Advanced Big Data and Data Mining  
**Student:** Xhon Pelushi  
**University:** University of the Cumberlands

## Dataset

This deliverable continues with the telecom customer churn dataset prepared in
Deliverable 1 (650 records, 11 attributes). The target variable for regression
is **MonthlyCharges**, predicted from customer demographics, service attributes,
and engineered features.

## Modeling Process

1. **Feature Engineering** — Created `ChargesPerMonth_Tenure` (normalized spending
   rate), `HighSupportTickets` (binary flag), and tenure groupings. Encoded all
   categorical variables with one-hot encoding.
2. **Multiple Linear Regression** — Baseline model using all engineered features.
3. **Ridge Regression (L2)** — Tested across multiple alpha values to find optimal
   regularization strength.
4. **Lasso Regression (L1)** — Applied L1 penalty for simultaneous regularization
   and feature selection.
5. **Cross-Validation** — 5-fold CV on all models to assess generalization.

## Key Insights

- All three models achieved comparable R² scores, indicating that the linear
  relationship between customer attributes and monthly charges is well-captured
  by standard regression.
- **TotalCharges** and **Tenure** are the strongest predictors, as expected.
- **Contract type** and **Internet service** significantly influence charges.
- Lasso's feature selection revealed which attributes carry minimal predictive
  value, simplifying interpretation.
- Cross-validation confirmed consistent performance across folds, indicating
  no overfitting.

## Challenges

- The telecom churn dataset required careful handling of NaN values produced
  during tenure-based binning (pd.cut creates NaN for out-of-range values).
- Feature scaling was applied before regularization to ensure fair coefficient
  penalization across all features.

## Files

| File | Description |
|------|-------------|
| `ProjectDeliverable2_Regression_Modeling_Evaluation.ipynb` | Jupyter Notebook with all code, models, and visualizations |
| `telecom_churn_data.csv` | Telecom churn dataset (from Deliverable 1) |
| `README.md` | This file |
