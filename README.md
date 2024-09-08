# README for Nearest Earth Objects Analysis

## Overview

This project analyzes a dataset of Near-Earth Objects (NEOs) from 1910 to 2024, focusing on their characteristics to predict whether they are hazardous. The analysis includes data cleaning, exploratory data analysis (EDA), and predictive modeling using K-Nearest Neighbors (KNN) and Logistic Regression.

## Table of Contents

- [Dataset](#dataset)
- [Setup](#setup)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Modeling](#modeling)
  - [K-Nearest Neighbors](#k-nearest-neighbors)
  - [Logistic Regression](#logistic-regression)
- [Performance Metrics](#performance-metrics)
- [Visualization](#visualization)
- [Conclusion](#conclusion)

## Dataset

The dataset used in this project is a CSV file containing information about NEOs. The columns include:

- `neo_id`: Unique identifier for the NEO
- `name`: Name of the NEO
- `absolute_magnitude`: Measure of the NEO's brightness
- `estimated_diameter_min`: Minimum estimated diameter
- `estimated_diameter_max`: Maximum estimated diameter
- `orbiting_body`: The celestial body the NEO orbits
- `relative_velocity`: Speed of the NEO relative to Earth
- `miss_distance`: Distance from Earth at closest approach
- `is_hazardous`: Boolean indicating whether the NEO is hazardous

## Setup

To run the code, ensure you have the following libraries installed:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Data Cleaning

The data was cleaned by:

1. Removing rows with missing values.
2. Dropping columns with unique values that do not contribute to the analysis (`orbiting_body` and `name`).
3. Identifying and removing outliers based on the Interquartile Range (IQR) method for relevant features.

## Exploratory Data Analysis

- Histograms were created to visualize the distribution of `absolute_magnitude` and `estimated_diameter_min`.
- A pie chart was used to show the distribution of hazardous vs. non-hazardous NEOs.

## Modeling

### K-Nearest Neighbors

1. The dataset was split into training and testing sets (80/20 split).
2. A KNN classifier was trained using the training data.
3. The optimal number of neighbors was determined by evaluating the accuracy for different values of `k`.

### Logistic Regression

1. A logistic regression model was fitted to the training data.
2. The model's probabilities for the test set were calculated.
3. Predictions were made, and performance was evaluated.

## Performance Metrics

- Accuracy scores for both KNN and Logistic Regression were calculated.
- Confusion matrices and classification reports were generated to assess model performance.
- ROC curves were plotted to visualize the true positive rate vs. false positive rate.

## Visualization

Visualizations include:

- Histograms for feature distributions.
- Pie charts for class distributions.
- Accuracy plots for varying numbers of neighbors in KNN.
- ROC curves for model performance.

## Conclusion

The analysis successfully predicts whether NEOs are hazardous using KNN and Logistic Regression. The models provide a reasonable accuracy, with KNN achieving approximately 87% accuracy. Further improvements could include hyperparameter tuning and exploring additional features.
