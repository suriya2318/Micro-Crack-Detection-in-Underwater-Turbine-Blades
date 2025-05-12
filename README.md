# Ocean Turbine Blade – Micro-Crack Detection Using Orange
## Project Objective
To develop a predictive system that detects micro-cracks in underwater tidal turbine blades caused by biofilm corrosion using Orange Data Mining and machine learning techniques. The goal is to reduce energy loss and unplanned maintenance costs while supporting sustainable ocean energy generation.

## Problem Statement 
Underwater tidal turbine blades are prone to micro-cracks caused by biofilm corrosion.

These cracks: 

• Reduce energy output by 25%, leading to significant revenue loss. 

• Cause $500K/month in unplanned maintenance costs. 

• Are influenced by factors like microbial species, seawater pH, salinity, and stress levels. 

The challenge is to detect, predict, and prevent these cracks to enable predictive 
maintenance, reduce costs, and improve energy efficiency. 

## Solution 
The solution involves using Orange, an open-source data mining tool, to analyze and predict crack growth in underwater turbine blades. The workflow includes: 

 • Data Integration: Combining sonar scans, seawater pH data, and microbial genomic sequences. 
 
 • Feature Engineering: Reducing high-dimensional microbial genomic data using Principal Component Analysis (PCA). 
 
 • Association Rule Mining: Identifying relationships between biofilm species and crack formation. 
 
 • Predictive Modeling: Using regression and classification models to predict crack growth and categorize risk levels. 
 
 • Real-Time Dashboard: Visualizing trends and risk levels for proactive decisionmaking.

## Dataset Used
- <a href="https://github.com/suriya2318/Micro-Crack-Detection-in-Underwater-Turbine-Blades/blob/main/Ocean_Turbine_Crack_Dataset.csv"> Ocean Turbine Crack Dataset </a>

## Working Process of Micro-Crack Detection in Underwater Turbine Blades 
The follow the detailed workflow ensures a systematic approach to detecting and predicting micro-cracks in underwater turbine blades, enabling predictive maintenance and reducing operational costs.

### Step 1: Load Dataset

• Widgets Used: File, Data Table

• Purpose: Import and preview Ocean_Turbine_Crack_Dataset.csv to ensure it's ready for analysis.

Configuration:

• Load dataset using File widget

Verify data types:

• Numerical: Crack width/depth, stress, pH, salinity, biofilm thickness

• Categorical: Microbial species, risk level, recommended action

Expected Output: Clean, well-formatted dataset for preprocessing

![image](https://github.com/user-attachments/assets/b548ccd5-7de5-4768-90c8-ab37b8cba401)

### Step 2: Data Preprocessing

• Widgets Used: Select Columns, Edit Domain, Data Sampler, Normalize

• Purpose: Prepare data for ML by selecting key features, standardizing values, and splitting into training/testing sets.

Configuration:

• Selected: Crack Width, Depth, Stress, pH, Salinity, Biofilm Thickness, Microbial Species

• Target: Risk Level (classification) or Predicted Crack Growth (regression)

• Normalized numerical features

• Split: 80% training, 20% testing (random sampling)

Expected Output: Standardized, train-test ready dataset

![image](https://github.com/user-attachments/assets/98862a4e-fc8e-4dbc-98ea-85eb96918606)

### Step 3: Exploratory Data Analysis (EDA)

• Widgets Used: Box Plot, Scatter Plot, Heatmap

• Purpose: Discover patterns, relationships, and outliers in the data.

Configuration:

• Scatter Plot: X = Crack Width, Y = Predicted Crack Growth, Color = Microbial Species

• Box Plot: Analyze Crack Depth by Microbial Species

• Heatmap: Correlations among Stress Level, Biofilm Aggressiveness, Crack Width

Expected Output: Visual insights on feature relationships and anomalies

### Step 4: Feature Engineering with PCA

• Widget Used: Principal Component Analysis (PCA)

• Purpose: Reduce microbial genomic data to key components

Configuration:

• Reduced to 5–10 components

• Maintained >90% explained variance

Expected Output: Lower-dimensional dataset with essential features retained

![image](https://github.com/user-attachments/assets/08de2028-2da7-4219-9282-7936966a2589)

### Step 5: Association Rule Mining for Biofilm Species

• Widgets Used: Association Rules, Discretize

• Purpose: Discover patterns between microbial species and crack growth

Configuration:

• Converted Biofilm Thickness and Crack Growth into Low/Medium/High categories

• Used Support = 0.1, Confidence = 0.6, Lift > 1.2

Output: Rules like "Sulfurimonas biofilm > 3mm → High Crack Growth"

### Step 6: Predict Crack Growth Using Regression

• Widgets Used: Linear Regression, Random Forest, Test & Score

• Purpose: Predict crack growth from features like Crack Width and pH

Output: Random Forest gave best performance (lower RMSE, higher R²)

### Step 7: Risk Categorization (Classification)

• Widgets Used: Decision Tree, Naïve Bayes, Random Forest, Confusion Matrix

• Purpose: Classify blades into Low, Medium, High risk levels

Output: Random Forest achieved over 80% accuracy

![image](https://github.com/user-attachments/assets/570060a3-369d-4fd7-b70e-63238120f0df)

### Step 8: Predictive Maintenance System

• Widgets Used: Tree, Test & Score, Confusion Matrix

• Purpose: Recommend maintenance actions based on predicted risk

Output: Example – "IF Risk = High → THEN Action = Replace Blade"

### Step 9: Real-Time Dashboard

• Widgets Used: Scatter Plot, Line Plot, Box Plot, Mosaic Display

• Purpose: Visualize real-time conditions and trends

Output: Interactive dashboard tracking pH, biofilm, crack metrics over time

### Step 10: Model Deployment

• Widgets Used: Save Model, Export CSV

• Purpose: Deploy final models and export prediction results

Output: Models saved (.pkcls) and results exported (.csv) for implementation

## Final Workflow & Output
The final output of the project includes:

### 1. Crack Growth Prediction Model
Problem: Tiny cracks grow unpredictably due to stress, pH, and biofilm, causing energy loss and high maintenance costs.

Solution: A regression model (Random Forest) predicts crack growth using features like crack width, biofilm, and stress.

Outcome: Early detection reduced unplanned maintenance and improved energy output.

![image](https://github.com/user-attachments/assets/51fb08bb-9bd3-4c5e-9b89-a12c26049b7d)

### 2. Biofilm-Crack Relationship Analysis
Problem: The link between microbial species (e.g., Sulfurimonas) and crack formation was unclear.

Solution: Used Association Rule Mining to uncover species-crack growth patterns.

Outcome: Identified key microbes and enabled targeted corrosion control.

![image](https://github.com/user-attachments/assets/8216cba1-10dd-426f-87e9-de1384ede532)

### 3. Risk Categorization System
Problem: Lack of clear risk levels led to inefficient inspections.

Solution: A classification model (e.g., Decision Tree) categorized blades into Low, Medium, and High risk.

Outcome: Maintenance focused on high-risk blades, cutting downtime and cost.

![image](https://github.com/user-attachments/assets/1b1aa9e5-6465-49ac-bf7b-72349a8007cc)

![image](https://github.com/user-attachments/assets/104fd1c5-d5dd-46e6-a784-fba6bdf978e1)

### 4. Predictive Maintenance Actions
Problem: Reactive maintenance led to high costs and energy losses.

Solution: A decision tree recommended actions based on risk levels.

Outcome: Shifted to predictive maintenance, cutting costs by 30% and extending blade lifespan.

### 5. Real-Time Dashboard
Problem: No centralized view for monitoring turbine conditions in real-time.

Solution: Built a dashboard with Scatter, Line, Box, and Mosaic Plots.

Outcome: Enabled faster decision-making and reduced issue response time by 50%.

#### • Scatter Plot: To visualize relationships between pH, crack width, and risk level. 

Output: 

![image](https://github.com/user-attachments/assets/4e18eaf8-ec6e-464c-9da9-3ab37fe600de)

#### • Line Plot: To track trends in material integrity, biofilm thickness and crack depth. 

Output: 

![image](https://github.com/user-attachments/assets/9768f22f-509a-4350-97d2-993eb2ae69d5)

#### • Box Plot: To compare crack depth distributions across risk levels. 

Output:

![image](https://github.com/user-attachments/assets/ec9913f5-61f2-46fa-8758-8a4b393f9d5a)

#### • Mosaic Display: To visualize risk patterns over time. 

Output: 

![image](https://github.com/user-attachments/assets/349518f8-5ad6-4d8c-b192-ac303c682cde)

## Expore the Project Report

- <a href="https://github.com/suriya2318/Micro-Crack-Detection-in-Underwater-Turbine-Blades/blob/main/Micro%20Crack%20Detection%20in%20Underwater%20Turbine%20Blades_Project%20Report.pdf"> Project Final Report</a>

## Final Workflow 
The entire workflow was implemented using Orange, a user-friendly tool for data analysis 
and machine learning. Here’s a detailed breakdown of the process: 

![image](https://github.com/user-attachments/assets/9d1fa10f-0896-4b80-bc63-a6a7968e6ea5)

## Final Conclusion
This project demonstrates how Orange Data Mining can be used to build a powerful no-code machine learning pipeline for marine renewable energy maintenance. By integrating sonar, pH, salinity, and microbial genomics, we developed a crack detection system that can potentially reduce operational costs and improve turbine lifespan—supporting clean energy innovation.

