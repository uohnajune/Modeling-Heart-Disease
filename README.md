# Modeling-Heart-Disease
### Using Data Science to develop risk assessment models to assess the risk of Coronary Heart Disease

For this analysis, I used the Framingham Heart Study Data set. 
The data was obtained from the Kaggle open source data repository.
The analysis was conducted in the ipython environment

**1. First I imported the several libraries using the following code:**
  `import numpy as np`
  <br />`import pandas as pd`
  <br />`import matplotlib.pyplot as plt`
  <br />`from sklearn.linear_model import LinearRegression`
  <br />`from sklearn.model_selection import train_test_split`
  <br />`from sklearn.metrics import r2_score, mean_squared_error`
  <br />`import seaborn as sns`
  <br />`%matplotlib inline`

**2. I loaded the various modules from the libraries**
  <br />`import scipy`
  <br />`scipy.stats import spearmanr`
  <br />`pylab import rcParams`
  <br />`sklearn.preprocessing import scale`
  <br />`sklearn.linear_model import LogisticRegression`
  <br />`sklearn import metrics`
  <br />`sklearn import preprocessing`

**3. Conducted descriptive statistics on the data set**
  <br />-list of column headings
  <br />-mean, standard deviation, min, mix, percentile
  <br />-replace column head 'head' with 'gender', and change '0/1' to 'male/female'
  
**4. Correlation analysis**
  <br />-generate correlation heat map for whole data set, then for each gender
  <br />-bar chart of the CHD outcome distribution
  <br />-stacked bar chart of the gender distribution for CHD vs no-CHD

**5. Modeling the data (logistic regression)** 
 <br />-using only continuous variables and fill in missing variables
    <br />-explanatory variables: age, sysBP, currentSmoker, totChol, diabetes 
    <br />-outcome:TenYearCHD
 <br />-train and split data set and fit model
 <br />-first for entire data set, then model each gender separately
 
 **6. Use following code to generate the coefficients for each variable**
   <br />`import statsmodels.api as sm`
   <br />`mlr_model=sm.Logit(Y_test, X_test)`
   <br />`result_gen=mlr_model.fit()`
   <br />`print(result_gen.summary2())`
   
 **7. Generate scatterplots that were grouped by gender, to show the differences between male and female risk factor effect**
 <br />-`sns.lmplot( x="age", y="sysBP", data=fhs_df, fit_reg=True, hue='gender', legend=True, palette="Set1", scatter_kws={"s": 7})`
  <br />-sysBP vs age
  <br />-totChol vs age
  <br />-totChol vs SysBp
  <br />-BMI vs age
  <br />-BMI vs sysBp
