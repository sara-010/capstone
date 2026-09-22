# Capstone — A Backtested Forecasting Report

## Training Programme

Time Series Forecasting for AI Systems — Cohort 20 Sept – 22 Sept 2026
**Author:** Sarah Aldhawyan

## Project Idea

This project takes a single time series from raw data to a validated,
uncertainty-aware forecast, following the same pattern used throughout the
course's labs (decomposition → classical model → ML/GBM model → walk-forward
backtest → metrics → probabilistic forecast → model-comparison recommendation).

## Dataset

**`data/retail_demand.csv`**, filtered to the **Riyadh / Grocery** series
(daily, 2023‑01‑01 → 2025‑12‑31, 1,096 rows).

**Why this series:** it has ~3 years of clean daily history, a stable
upward trend, and strong weekly seasonality with occasional promo-style
demand shocks — enough real structure to exercise every technique.

## What's in this notebook

| # | Section | What it covers |
|---|---|---|
| 1 | Time Series Structure & Diagnostics | STL decomposition, ACF/PACF, ADF stationarity test |
| 2 | Classical Forecasting Model | SARIMAX (AIC-selected order) + Holt-Winters, with a Ljung-Box residual check |
| 3 | ML/GBM Forecasting & Feature Engineering | LightGBM with lag/rolling/calendar features, leakage-safe recursive multi-step forecasting |
| 4 | Backtesting Framework & Time-Based Validation | 5-fold expanding-window walk-forward backtest, with the window-type choice justified for this series |
| 5 | Evaluation Metrics & Reporting | MAE, RMSE, WAPE and MASE, with the WAPE-over-MAPE choice justified |
| 6 | Probabilistic Forecasting & Prediction Intervals | An 80% interval via quantile LightGBM, plus a second interval via Prophet, both scored on coverage **and** width |
| 7 | Model Comparison & Documentation | A written recommendation reasoning from history length, interpretability, interval support and compute budget |

## How to run it

Click the badge below to open the notebook directly in Google Colab, then
run every cell top to bottom (**Runtime → Run all**). The first cell installs
every required package (`statsmodels`, `lightgbm`, `prophet`, `scikit-learn`);
no other setup is needed.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sara-010/capstone/blob/main/Capstone_Backtested_Forecasting_Report.ipynb)



## Repository structure

```
.
├── Capstone_Backtested_Forecasting_Report.ipynb   
├── data/
│   └── retail_demand.csv                       
├── README.md
└── .gitignore
```


## Acknowledgements

Built on the course infrastructure and conventions from
`MohammadYusif/time-series-forecasting-ai-systems` (SDAIA Academy) https://github.com/SDAIAAcademy
