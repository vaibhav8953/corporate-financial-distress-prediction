# Corporate Financial Distress Prediction

This MSc dissertation project evaluates whether adding lagged macroeconomic indicators improves corporate financial distress prediction across six horizons (H1–H6). It compares logistic regression, random forest and XGBoost using financial-only and hybrid feature sets. The notebook includes company-grouped validation, calibration and threshold analysis, and SHAP explanations for the H2 hybrid XGBoost model.

## Data sources

- **Company financial data:** Download the six horizon Parquet files from
  [V4FinBench on Kaggle](https://www.kaggle.com/datasets/sebastiantomczak10/v4-group-corporate-bankruptcy/data)
  and place them in `data/`.
- **Macroeconomic data:** The notebook uses a separate CSV compiled from the
  [World Bank's World Development Indicators](https://data.worldbank.org/).
  Place `V4FinBench_Macroeconomic_Variables_2006_2021.csv` in `data/`.

## Run the notebook

From the repository root, install the dependencies and start JupyterLab. The submission notebook used Python 3.13.9.

```sh
python -m pip install -r requirements.txt
python -m jupyterlab
```

Place your V4FinBench inputs under `data/` before opening `financial_distress_prediction.ipynb` and running its cells in order. The inputs are required and are excluded from this repository.

- `V4FinBench_Macroeconomic_Variables_2006_2021.csv`
- `company_years_h1.parquet` through `company_years_h6.parquet`. For split data, use `company_years_h{n}_part_*.parquet` files in `data/` or in `data/h{n}_parts/` (uppercase `H` also works).

The notebook writes generated results, predictions and model artifacts under `results/`.
