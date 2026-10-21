# nyc-weather-forecasting-model-comparison

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yogeshkbahl/nyc-weather-forecasting-model-comparison/blob/main/4.%20Weather%20Forecasting.ipynb)

▶️ **Run it in Google Colab:** click the badge above, then **Runtime → Run all**. The data loads straight from this repo, so no upload is needed (full run takes about a minute).

A weather forecasting project that analyzes daily NYC weather data, engineers time-series features, and compares RNN, LSTM, XGBoost, and Random Forest models for next-day temperature prediction. It also generates a 30-day autoregressive temperature forecast with visualizations.

---

## Description

This project analyzes daily New York City weather data and builds a forecasting pipeline to predict the **next day's mean temperature**. It includes exploratory data analysis, feature engineering for time-series forecasting, model comparison across deep learning and tree-based methods, and a 30-day autoregressive forecast.

---

## Features

- Loads and explores daily NYC weather data from a CSV file
- Generates descriptive statistics and multiple visual analyses
- Creates engineered features for time-series forecasting, including:
  - Calendar-based features
  - Cyclical encodings
  - Lag features
  - Rolling statistics
  - Temperature change and interaction features
- Trains and compares four forecasting models:
  - RNN
  - LSTM
  - XGBoost Regressor
  - Random Forest Regressor
- Evaluates models using:
  - RMSE
  - MAE
  - MAPE
  - R²
  - Training time
- Produces actual-vs-predicted comparison plots
- Generates a 30-day future temperature forecast using an autoregressive approach
- Displays forecast tables and forecast visualization dashboards

---

## Tech Stack

- **Python**
- **Jupyter Notebook**
- **NumPy**
- **pandas**
- **Matplotlib**
- **Seaborn**
- **scikit-learn**
- **XGBoost**
- **TensorFlow / Keras**

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/yogeshkbahl/nyc-weather-forecasting-model-comparison.git
cd nyc-weather-forecasting-model-comparison
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
```

On macOS/Linux:

```bash
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install numpy pandas scipy matplotlib seaborn scikit-learn xgboost tensorflow notebook
```

---

## Usage

### 1. Dataset

`nyc_weather_2023.csv` loads automatically from this GitHub repo, so no download or placement is needed.

### 2. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 3. Open and run the notebook

Open:

```
4. Weather Forecasting.ipynb
```

Run the notebook cells in order to:

- Load the dataset
- Visualize weather patterns
- Engineer forecasting features
- Train and compare models
- Evaluate predictions
- Generate a 30-day temperature forecast

---

## Example Behavior

The notebook performs forecasting for tomorrow's mean temperature using the last 3 days of engineered weather features.

From the notebook output:

```
Dataset shape: 365 rows × 10 columns
Engineered features: 60
Samples available after preprocessing: 357
Train/test split: chronological 80/20
```

The compared models include RNN, LSTM, XGBoost, and Random Forest. In the notebook output, the RNN is reported as the best-performing model by RMSE for the test set.

The future forecast section generates predictions for:

```
2023-12-31 to 2024-01-29
Forecast range: approximately -0.3°C to 5.2°C
Forecast mean: approximately 3.8°C
```

---

## File Structure

```
.
├── 4. Weather Forecasting.ipynb
├── nyc_weather_2023.csv
└── README.md
```

---

## Forecasting Workflow

1. Load daily weather data
2. Perform exploratory analysis and visualization
3. Engineer lag, rolling, calendar, and interaction features
4. Split data chronologically into training and testing sets
5. Scale features for neural network models
6. Train RNN, LSTM, XGBoost, and Random Forest models
7. Compare model performance
8. Use the selected forecasting setup to generate a 30-day future forecast

---

## Notes

- The notebook uses a chronological split rather than shuffled data, which is appropriate for time-series forecasting.
- The target variable is next-day mean temperature.
- The forecasting pipeline uses an autoregressive strategy for future prediction.

---

## Future Improvements

- Add model saving/loading for reproducible inference
- Move notebook logic into reusable Python modules
- Add a `requirements.txt` file
- Support multivariate or multi-step forecasting with sequence windows longer than one timestep
- Add hyperparameter tuning and validation workflows
- Add forecast export to CSV

---

## License

MIT License
