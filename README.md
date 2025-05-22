# 🗺️ Exploring and Modeling Tourism Trends in Ireland

This project investigates the economic and demographic factors influencing tourism event pricing and distribution across Ireland. Using real-world open data, we applied a complete data science workflow—from data cleaning and visualization to predictive modeling and inferential statistics—focused on understanding the dynamics of tourism-driven events.

📄 Full Report: `CA1_report.pdf`

---

## 🎯 Project Objectives

- Analyze the **pricing and availability** of tourism events
- Investigate the **distribution of free vs. paid events**
- Identify key **geographic, seasonal, and platform-driven patterns**
- Predict event prices using **regression models**
- Apply **inferential statistics** to model distributions

---

## 🧰 Tools & Technologies

- **Language**: Python (Jupyter Notebooks)
- **Libraries**: `pandas`, `numpy`, `scikit-learn`, `xgboost`, `matplotlib`, `seaborn`, `scipy`, `haversine`
- **Visualization**: `squarify`, `scienceplots`, `pydot`
- **Data Wrangling**: `Box-Cox`, robust scaling, outlier removal, feature encoding

---

## 📦 Datasets Used

- **Fáilte Ireland Events API**: National event data
- **CSO Population Data**: County-level demographic info
- **CSO Tourism Stats**: Monthly foreign visitor counts
- **Google Places API**: Venue ratings, types, and metadata

See `Appendix A` in the report for full source links and licensing.

---

## 🔍 Analysis Overview

### ✅ Data Cleaning & Feature Engineering
- Missing value imputation and logical handling (e.g., free events = price 0)
- Calculated features: `duration`, `distance from Dublin`, `venue_rating`
- Merged county-level population and visitor data

### 📊 Exploratory Data Analysis
- **Free events** are more frequent in less populated counties
- **Spring** has the highest proportion of free events (~28%)
- Venue types and booking platforms strongly influence price

### 🧪 Inferential Statistics
- Applied **binomial, Poisson**, and **normal** distributions
- Used **Shapiro-Wilk test** to assess price normality post-transformation

---

## 🤖 Predictive Modeling

### Models Evaluated:
| Model            | Test R² | MAE  | RMSE |
|------------------|---------|------|------|
| OLS Regression   | 0.33    | 6.79 | 10.15|
| Elastic Net      | 0.13    | 8.15 | 11.53|
| Decision Tree    | 0.36    | 6.49 | 9.88 |
| Random Forest    | 0.46    | 6.22 | 9.09 |
| **XGBoost**      | **0.53**| 5.48 | 8.48 |

- **XGBoost** performed best, explaining over **50% of variance**
- Most important features: `booking_platform`, `venue_type`, and `county`

---

## 📌 Key Insights

- **Location and platform** are better predictors than time-based features
- **Non-linear models** like XGBoost outperform linear baselines
- **Free events** cluster in smaller counties and spring seasons

---

## 🧩 Future Work

- Apply SHAP for feature interpretability
- Use deep learning or hybrid models (e.g., wide & deep networks)
- Expand data with weather, reviews, and social sentiment signals
- Deploy as interactive dashboard using Streamlit or Dash
