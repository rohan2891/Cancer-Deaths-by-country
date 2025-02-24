# Cancer-Deaths-by-country
📌 Project Overview 

This projects analyzes global cancer related deaths by Country using SQL , Python , PowerBI. 
The dataset includes the mortality rates across different regions , helping to identify 
trends , patterns.

📊 Objectives

✔ Identify countries with the highest cancer mortality rates.
✔ Analyze trends in cancer deaths from 1990 to 2016.
✔ Find correlations between smoking rates and healthcare access.
✔ Visualize insights using Power BI


📂 Dataset : Cancer Deaths by Country and Type (1990-2016)






Time Range : 1990-2016

Format: Excel/CSV





🔹 Data Cleaning & Processing (Python)

 import pandas as pd 
 
 import matplotlib.pyplot as plt 
 
 import seaborn as sns
 

#Loading of the data for cleaning



 df = pd.read_csv('data/CancerDeaths.csv')





#Checking for any missing values in data



print(df.isnull().sum())

#Filling missing values with 0

 df.fillna(0, inplace = True)

#Checking data after cleaning



df.head(20)






🔹 SQL Analysis

🔹 Top 10 Countries with Highest Cancer Deaths (All Types)


SELECT TOP 10 Country, SUM(
    Liver_Cancer + Kidney_Cancer + Larynx_Cancer + Breast_Cancer + Thyroid_Cancer +
    Stomach_Cancer + Bladder_Cancer + Uterine_Cancer + Ovarian_Cancer + Cervical_Cancer +
    Prostate_Cancer + Pancreatic_Cancer + Esophageal_Cancer + Testicular_Cancer +
    Nasopharynx_Cancer + Other_Pharynx_Cancer + Colon_and_Rectum_Cancer +
    Non_Melanoma_Skin_Cancer + Lip_and_Oral_Cavity_Cancer + Brain_and_Nervous_System_Cancer +
    Tracheal_Bronchus_Lung_Cancer + Gallbladder_and_Biliary_Tract_Cancer +
    Malignant_Skin_Melanoma + Leukemia + Hodgkin_Lymphoma + Multiple_Myeloma + Other_Cancers
) AS Total_Deaths
FROM cancer_deaths
GROUP BY Country
ORDER BY Total_Deaths DESC ;






🔹 Top 10 Countries by Specific Cancer Type (Example: Uterine cancer)


SELECT TOP 10 Country, SUM(Uterine cancer) AS Total_Deaths

FROM cancer_deaths

GROUP BY Country

ORDER BY Total_Deaths DESC
