# Diamond Price Prediction

This repository contains a dataset and code for predicting diamond prices based on various features of gemstones. The dataset includes information on dimensions (x, y, z), carat, table, depth, color, clarity, and cut of the gemstones.

## Dataset Description

The dataset contains the following columns:

- `carat`: Physical weight measured in metric carats.
- `table`: Width of the top of the diamond relative to the widest point.
- `depth`: The depth of height (in mm) measured from the culet (bottom) to the table (top).
- `color`: Color of the gemstone.
- `clarity`: Clarity of the gemstone.
- `cut`: Quality of the cut.
- `x`: Length in mm.
- `y`: Width in mm.
- `z`: Depth in mm.

## Predictive Modeling

The goal is to predict diamond prices using various predictive models. The following steps were taken:

### 1. Exploratory Data Analysis (EDA)

Exploratory Data Analysis (EDA) was performed to gain insights into the dataset and understand the relationships between variables.

### 2. Baseline Model

A baseline model was created using the following machine learning algorithms:

```python
models = {
    "Linear Regression": LinearRegression(),
    "XGBoost Regressor": XGBRegressor(),
    "CatBoost Regressor": CatBoostRegressor(),
    "LightGBM Regressor": LGBMRegressor(),
    "HistGradientBoostingRegressor": HistGradientBoostingRegressor(),
    "GradientBoostingRegressor": GradientBoostingRegressor(),
    "RandomForestRegressor": RandomForestRegressor(),
    "ExtraTreesRegressor": ExtraTreesRegressor(),
    "KNeighborsRegressor": KNeighborsRegressor(),
    "BaggingRegressor": BaggingRegressor(),
    "PoissonRegressor": PoissonRegressor(),
    "DecisionTreeRegressor": DecisionTreeRegressor(),
    "ExtraTreeRegressor": ExtraTreeRegressor(),
    "OrthogonalMatchingPursuitCV": OrthogonalMatchingPursuitCV(),
}
```

The models with the lowest Root Mean Square Error (RMSE) were selected for further evaluation.

### 3. Model with High Correlation Features

Based on EDA results, columns with high correlation with the target variable were selected. The chosen models were used to predict diamond prices.

### 4. Model with Diamond Volume

A new feature, diamond volume, was created based on the available factors. The selected models were used to predict diamond prices using this additional feature.

### 5. Model with Diamond Volume and High Correlation

The models were reevaluated using both diamond volume and high correlation features.

### 6. XGB Model with Adjustment and Diamond Volume

The XGBoost model was fine-tuned by optimizing its parameters until the RMSE reached the expected value. This tuned model was used to predict diamond prices.

### 7. CatBoost Model with Adjustment and Diamond Volume

A similar tuning process was applied to the CatBoost model, and the tuned model was used for predictions.

### 8. LGBM Model with Adjustment and Diamond Volume

The LGBM model was fine-tuned and adjusted with diamond volume as well, and the tuned model was used for predictions.

### 9. CatBoost Model with Baseline and Adjustment Parameters

The CatBoost model with baseline parameters and adjustment was evaluated, and its performance was compared to other models.

## Conclusion

The CatBoost Regressor model, using baseline data and adjusted parameters, achieved the lowest RMSE of 573.381 for predicting diamond prices. This model can be considered as the most accurate predictive model for diamond price prediction based on the given dataset.
