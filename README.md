# Used Car Price Prediction - CRISP-DM

This repository contains the project for **Practical Application Assignment 11.1: What Drives the Price of a Car?**. The objective of this project is to analyze what factors influence the price of used cars using the CRISP-DM (Cross Industry Standard Process for Data Mining) methodology.

## Table of Contents
- [View the Jupyter Notebook](prompt_II.ipynb)
- [Project Description](#project-description)
- [CRISP-DM Process](#crisp-dm-process)
- [Findings](#findings)
- [Results](#results)
- [Repository Structure](#repository-structure)
- [How to Run](#how-to-run)
- [Conclusion](#conclusion)

## Project Description

The goal of my project is to determine the factors that drive the prices of used cars. By analyzing a dataset containing various attributes of used cars, I aim to provide insights that can help used car dealerships better understand consumer preferences and fine-tune their inventory.

#### Note on Data Transformation:

To better model the price distribution and handle skewness in the data, the target variable (car price) was transformed using a logarithmic scale. This transformation helps stabilize variance and meets the linear regression assumptions more effectively. However, all final interpretations and evaluations of the model's performance are presented on the original price scale (actual car prices) by exponentiating the predictions, providing practical relevance for dealerships.

### CRISP-DM Process

This project follows the CRISP-DM framework, which involves the following steps:

1. **Business Understanding**: Understanding the business problem—what factors make a car more or less expensive.
2. **Data Understanding**: Gathering and exploring the dataset to understand its structure, quality, and any initial insights.
3. **Data Preparation**: Cleaning and preprocessing the data, including handling missing values, encoding categorical variables, and feature engineering.
4. **Modeling**: Building regression models to predict car prices and determining the most influential features.
5. **Evaluation**: Evaluating the model performance using metrics like MAE (Mean Absolute Error) to identify the best model.
6. **Deployment**: Preparing the final model for deployment, including creating a plan for monitoring and maintenance.

## Findings

After applying feature selection using three different regression models with polynomial features (Lasso, RFE with Ridge, and SFS with Ridge) and evaluating the performance of four regression models, I found that:

- **Feature Selection Process**: Three regression models (Lasso, RFE with Ridge, and SFS with Ridge) with polynomial features were used for feature selection to identify the most influential predictors of car prices.
- **Most Influential Features**: The key factors affecting car prices included `condition`, `manufacturer`, `car age`, `fuel type`, and `odometer reading`.
- **Model Evaluation and Best Model**: After selecting the most relevant features, four regression models (Linear Regression, Lasso, Ridge, and Elastic Net with the selected features) were evaluated for their performance. The **Ridge Regression** model with polynomial features (degree 2) provided the most accurate predictions. The model achieved a Mean Absolute Error (MAE) of **0.4559** on the logarithmic scale. When converting predictions back to the original price scale, the MAE was **6415.7464** on the test set, indicating the average prediction error in actual dollar amounts.
- **Practical Insights**: Car dealerships can leverage these insights to adjust pricing strategies and optimize inventory based on consumer preferences, making informed decisions supported by the model's predictions.

## Results

The notebook `prompt_II.ipynb` contains all the steps from data preparation to model evaluation. It provides a detailed walkthrough of the analysis performed, including visualizations, feature engineering, model building, and evaluation metrics.

### Key Metrics:

- **Ridge Regression Model**:
  - **MAE (Logarithmic Scale, Test Set)**: 0.4559
  - **MAE (Original Scale, Test Set)**: 6415.7464 (representing the average error in predicting car prices in dollars)
  - **Key Features**: `car age`, `condition`, `manufacturer`, `fuel type`, and `odometer`.


## Repository Structure

- `data/`: Contains the dataset (`vehicles.csv`).
- `images/`: Contains images used in the notebook (`crisp.png`, `kurt.jpeg`).
- `prompt_II.ipynb`: Jupyter Notebook with all analysis and modeling steps.
- `.gitignore`: Specifies files and directories to be ignored by Git.

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/stirelli/used-car-price-prediction-crispdm.git

2. Install the necessary packages:

   ```bash
   pip install -r requirements.txt

3. Run the Jupyter Notebook:

   ```bash
   jupyter notebook prompt_II.ipynb

## Conclusion

This project demonstrates the application of data mining techniques in a real-world scenario using the CRISP-DM framework. The findings provide actionable insights for used car dealerships to optimize their pricing strategy based on data-driven analysis.
