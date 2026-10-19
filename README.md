# Concrete-Compressive-Strength-Prediction
A machine-learning regression project that analyzes concrete mix ingredients and curing age to predict compressive strength. Includes exploratory data analysis, comparison of eight regression models, cross-validation, and model evaluation using MAE, RMSE, and R².

# Concrete Compressive Strength Prediction Using Machine Learning
## Project Overview
Concrete compressive strength is an important property for evaluating concrete used in construction. Its strength depends on the proportions of its ingredients and the age of the concrete. This project explores the concrete dataset and develops machine-learning regression models to estimate compressive strength from mix composition and age.
The project was prepared as a Jupyter Notebook and includes data analysis, visualization, model comparison, evaluation, and an example prediction.

## Objectives
- Analyze the concrete dataset and understand its variables.
- Check data quality, including missing values and duplicate records.
- Perform exploratory data analysis (EDA) and correlation analysis.
- Explore relationships between concrete ingredients, age, and compressive strength.
- Train and compare multiple regression models.
- Evaluate model performance using MAE, RMSE, and R².
- Select a candidate model using five-fold cross-validation.
- Demonstrate a prediction for a sample concrete mix.

## Dataset
The dataset contains 1,030 observations, eight quantitative input features, and one target variable. The notebook reports 25 duplicate rows and removes them during cleaning, leaving 1,005 rows.
### Input Features
Feature	Description	Unit
cement	Cement quantity	kg/m³
slag	Blast furnace slag quantity	kg/m³
ash	Fly ash quantity	kg/m³
water	Water quantity	kg/m³
superplastic	Superplasticizer quantity	kg/m³
coarseagg	Coarse aggregate quantity	kg/m³
fineagg	Fine aggregate quantity	kg/m³
age	Age of the concrete	Days


### Target: strength — concrete compressive strength, measured in megapascals (MPa).
Dataset source provided in the project brief: Download the Concrete Strength dataset
## Project Workflow
1. Load the dataset and inspect its dimensions, columns, and data types.
2. Check for missing values and duplicate records.
3. Remove duplicate records and review descriptive statistics.
4. Perform EDA using histograms, distribution plots, scatter plots, and a correlation heatmap.
5. Split the data into training and test sets (80% / 20%).
6. Train and compare regression models using preprocessing pipelines.
7. Compare test-set metrics and five-fold cross-validation results.
8. Select a candidate model based on mean cross-validation RMSE.
9. Inspect actual-versus-predicted results and feature importance.
10. Generate an illustrative prediction for a sample mix.

## Machine-Learning Models
The notebook compares the following regression approaches:
- Dummy Regressor (baseline)
- Linear Regression
- Ridge Regression
- Random Forest Regressor
- Extra Trees Regressor
- Gradient Boosting Regressor
- HistGradientBoosting Regressor
- Support Vector Regression (SVR)

## Tools and Libraries
- Python
- Jupyter Notebook
- pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn

## Evaluation Metrics
- **MAE (Mean Absolute Error)**: average absolute difference between actual and predicted strength.
- **RMSE (Root Mean Squared Error)**: gives greater weight to larger prediction errors.
- **R² (Coefficient of Determination)**: indicates how much variation in the target is explained by the model.
Lower MAE and RMSE values indicate better performance; a higher R² is generally preferable.

## Results
According to the notebook's reported results, HistGradientBoosting was selected as the candidate model because it achieved the lowest mean RMSE during five-fold cross-validation.
Reported held-out test-set performance:
- **MAE**: approximately 2.813 MPa
- **RMSE**: approximately 4.015 MPa
- **R²**: approximately 0.939
The notebook's Random Forest feature-importance analysis identified concrete age and cement as the two most influential features under that model's importance measure. These findings describe this dataset and modelling setup; they do not establish causation.

## How to Run
1. Clone or download this repository.
2. Install Python and Jupyter Notebook (or use JupyterLab).
3. Install the required libraries:pip install pandas numpy matplotlib seaborn scikit-learn jupyter
4. Place the dataset file in the location expected by the notebook, or update the data-loading path in the notebook.
5. Open Concrete Compressive Strength Prediction(5).ipynb in Jupyter Notebook.
6. Run the notebook cells from top to bottom.
Note: The uploaded notebook currently loads the CSV from a local Windows path (C:\Users\DELL\concrete.csv). Update this path to match your dataset location before running the notebook on another computer.

## Challenges and Considerations
- Duplicate observations: the notebook identifies and removes 25 duplicate rows to reduce repeated records.
- Nonlinear relationships: concrete strength depends on multiple ingredients and curing age; nonlinear ensemble models are included to capture patterns that a simple linear model may miss.
- Fair model comparison: a held-out test set and five-fold cross-validation are used to compare models.
- Generalization: strong results on this dataset do not guarantee similar accuracy for different concrete mixes or laboratory conditions.

## Limitations and Safety
This is an educational machine-learning project. Predictions are estimates, not a replacement for laboratory testing, engineering review, or applicable construction standards. Do not use the model as the sole basis for structural design or safety decisions. Validate it on independent data before any real-world deployment.

## Repository Contents
- Concrete Compressive Strength Prediction(5).ipynb — data analysis, visualizations, model training, evaluation, and example prediction.
- README.md — project overview, setup instructions, workflow, and results.
- Repository Description.txt — short description suitable for the GitHub repository description field.

## Future Improvements
- Tune model hyperparameters using cross-validation.
- Validate performance on an independent dataset.
- Compare feature importance across models using additional methods.
- Save the trained model and create a reusable prediction interface.
