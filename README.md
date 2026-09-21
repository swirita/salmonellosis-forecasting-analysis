# Prepare Early for Seasonal Salmonellosis Surges

## Using Weekly CDC Reports to Support Earlier Public Health Planning

**Authors:** Siwar, Abdallah, and Husam

## Business Problem

Health departments need time to prepare for seasonal increases in Salmonellosis. This analysis examines when cases rise, which states have higher population-adjusted rates, and how well weekly cases can be forecast.

![Salmonellosis banner](visuals/salmonella-banner.jpg)

## Data

* **Source:** [CDC NNDSS Weekly Data](https://data.cdc.gov/NNDSS/NNDSS-Weekly-Data/x9gk-5huc/about_data)
* **Disease:** Salmonellosis, excluding Typhi and Paratyphi infections
* **Time period:** 2022 to September 2026
* **State rates:** Cases per 100,000 residents, calculated using U.S. Census population estimates

## Methods

We cleaned the weekly reports, reviewed missing-value flags, and studied seasonal patterns. We compared SARIMA and a recursive Random Forest across reporting areas. Both models used data through week 37 of 2025 and were tested on weeks 38 to 52. We then used the latest available data to forecast weeks 38 to 52 of 2026.

## Results

### Weekly Reported Cases

![Weekly reported Salmonellosis cases](visuals/weekly_salmonellosis_cases.png)

Reported cases vary throughout the year, with repeated increases during warmer months.

### Cases Are Highest in Summer

![Average weekly cases by season](visuals/salmonellosis_cases_by_season.png)

Summer averaged about **650 reported cases per week**, compared with **247 in winter**. Cases peaked around week 34, usually in August.

### States With the Highest Reported Rates

![States with the highest Salmonellosis rates](visuals/highest_salmonellosis_rates.png)

Mississippi had the highest year-to-date rate through week 35 of 2026: **26.8 reported cases per 100,000 residents**.

### Weekly Forecast Validation

![Validation performance for SARIMA and Recursive Random Forest](visuals/metrics.png)

SARIMA performed better on the shared 2025 validation period. Its average error was about **7 weekly cases**, compared with **9** for the recursive Random Forest. Their R² scores were **0.971** and **0.902**, respectively.

### Mississippi Recursive Random Forest Forecast

![Mississippi Recursive Random Forest forecast](visuals/recursive_mississipi.png)

The forecast fell from about **8 cases in week 38** to **4 in week 52**.

### Mississippi SARIMA Forecast

![Mississippi SARIMA forecast](visuals/MISSISIPY_FORECAST.png)

The forecast began at about **13 cases in week 38** and reached **0 by week 52**.

### Comparing the Two Mississippi Forecasts

![Mississippi SARIMA and Recursive Random Forest comparison](visuals/missi_forecast_vs_rec.png)

Both models forecast fewer cases by week 52, but SARIMA predicts a sharper decline. These are estimates. Their accuracy was compared using the separate 2025 validation period.

## Recommendations

* Prepare testing and staff before the summer increase, and monitor August closely.
* Use population-adjusted rates when comparing states.
* Compare new case increases with the usual seasonal pattern.
* Use SARIMA for weekly planning based on its stronger validation results, and update forecasts as new reports arrive.

## Limitations and Next Steps

Reported cases may miss infections or arrive late. The 2026 data is incomplete, and the state rates use 2024 population estimates. Combined validation scores may hide weaker results in individual areas. Future work should evaluate areas separately, test more forecast periods, and compare forecasts with new CDC reports.

## For Further Information

* [CDC NNDSS Weekly Data](https://data.cdc.gov/NNDSS/NNDSS-Weekly-Data/x9gk-5huc/about_data)
* [Data preparation notebook](notebooks/01_preparing_data.ipynb)
* [Salmonellosis analysis notebook](notebooks/02_salmonellosis_analysis.ipynb)
* [Salmonellosis forecasting notebook](notebooks/03_salmonellosis_forecasting.ipynb)
* [Machine-learning and deep-learning notebook](notebooks/04_salmonellosis_ml.ipynb)
* [Recursive Random Forest forecasting notebook](notebooks/05_salmonellosis_ml_forecast.ipynb)

For additional questions, please contact [Siwar Ehwass](mailto:siwarehwass@gmail.com).
