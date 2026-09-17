# Supply Chain Late Delivery Prediction

## Background
Late deliveries cost businesses millions in customer satisfaction and operational costs. 
This project builds a machine learning model to predict whether an order will be delivered 
late using only information available at the time of order placement — making it genuinely 
deployable in a real supply chain environment.

## Objectives
- Can we predict late delivery risk before an order ships?
- Which factors most strongly influence late delivery?
- Which shipping modes and markets have the highest late delivery rates?

## Data & Tools
- Dataset: DataCo Smart Supply Chain for Big Data Analysis (Kaggle)
- 180,519 orders across multiple markets and shipping modes
- Python: Pandas, Scikit-learn, XGBoost, LightGBM
- Visualization: Tableau Public

## Dashboard
👉 [View Interactive Dashboard](https://public.tableau.com/app/profile/seshu.vungarala/viz/SupplyChainLateDeliveryPredictionDashboard/Dashboard1)

## Methodology
- Strict data leakage prevention — only pre-shipment features used
- Feature engineering — extracted temporal features (hour, day of week, month)
- Compared 4 models — Logistic Regression, Random Forest, XGBoost, LightGBM
- XGBoost selected as best model — 73% accuracy, ROC-AUC 0.82

## Key Findings
- First Class shipping has the highest late delivery rate at 95.24% — counter intuitive finding suggesting unrealistic scheduled delivery windows
- Standard Class is most reliable at only 37.94% late delivery rate
- USCA has the highest late delivery rate by market at 55.81%
- Shipping Mode and Days Scheduled account for 83% of predictive power
- Model correctly identified 12,036 late orders out of 19,796 total

## Why 73% and not higher?
Strict data leakage prevention means we only used information available at order time. 
Many public notebooks achieve 95%+ by including actual shipping days and delivery status — 
features only known after delivery. My model is genuinely deployable in production.

## Recommendations
- Review First Class shipping scheduling — windows appear consistently unrealistic
- Focus operational improvements on USCA market — highest late delivery rate
- Use model to flag high risk orders before shipping for proactive intervention
- Collect additional features (weather, supplier performance, warehouse capacity) to improve accuracy

## Model Performance

| Model | Accuracy | ROC-AUC |
|---|---|---|
| Logistic Regression | 69.01% | 0.7268 |
| Random Forest | 72.19% | 0.8298 |
| XGBoost | 72.92% | 0.8229 |
| LightGBM | 72.90% | 0.8184 |

## Tools & Technologies
- Python — Pandas, NumPy, Scikit-learn, XGBoost, LightGBM
- Jupyter Notebook
- Tableau Public
