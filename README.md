# Global CO2 Emissions Analysis (2019–2023)

## Overview
This repository contains a comprehensive analysis of global CO2 emissions from January 2019 to May 2023. The project focuses on preprocessing raw emission data, creating calculated insights, and visualizing key trends using Power BI. The analysis highlights sector-specific trends, country-level comparisons, and global contributions to CO2 emissions, providing actionable insights into climate patterns.

---

## Dataset Details
The dataset includes global CO2 emission data with the following columns:
- **`date`**: Date of observation.
- **`value`**: CO2 emissions (in metric tons).
- **`country`**: Country of emission.
- **`sector`**: Emission sector (e.g., transport, energy).

### **Preprocessed Dataset Columns**
The final dataset includes the following columns:
1. `date`
2. `value`
3. `normalized_value` (scaled CO2 emissions)
4. `Total_CO2_per_country` (total CO2 per country)
5. `Sector_percentage_per_country` (sectoral contribution within a country)
6. `Year` (year extracted from the date)
7. `Yearly_CO2_per_country` (yearly CO2 total for each country)
8. `Yearly_growth_rate` (year-over-year growth in emissions)
9. `Global_CO2_percentage_per_country` (country’s share in global CO2 emissions)
10. `Cumulative_CO2_per_sector` (cumulative sectoral emissions)

---

## Preprocessing Steps
### **Data Cleaning**
- Ensured no null or duplicate rows in the dataset.
- Standardized the date format and converted it to `datetime`.
- Scaled the `value` column using MinMaxScaler for normalization.

### **Calculated Columns**
- **Total_CO2_per_country**: Total emissions by each country.
- **Sector_percentage_per_country**: Sectoral percentage contribution within each country.
- **Year**: Extracted year from the date for yearly analysis.
- **Yearly_CO2_per_country**: Summed emissions for each country per year.
- **Yearly_growth_rate**: Year-over-year growth rate of emissions (handled NaN and negative values).
- **Global_CO2_percentage_per_country**: Country’s share in global emissions.
- **Cumulative_CO2_per_sector**: Cumulative emissions for each sector.

### **Filtered Dataset**
For focused analysis, the dataset was filtered to include the following five countries:
- China
- India
- Russia
- United States
- World (global totals)

---

## Power BI Visualizations
The cleaned and preprocessed dataset was imported into Power BI for visualization.

### **Key Insights**
1. **Sector-Specific Trends**: Analyze the emissions contributed by different sectors over time.
2. **Cross-Sector Correlations**: Identify interdependencies among sectors.
3. **Country-Level Comparisons**: Compare emissions of top contributors like China, India, Russia, and the US.
4. **Global Contributions**: Understand each country’s share of global emissions.
5. **Anomalies and Patterns**: Detect any outliers or anomalies in emission trends.

### **Visualizations**
1. **Sum of Emissions by Year and Quarter**  
   - Chart Type: Line and Stacked Column Chart.  
   - Purpose: Show emission trends over time for selected countries.  
   - Fields:  
     - X-Axis: `Year` and `Quarter`  
     - Legend: `Country`  
     - Values: Sum of `value`  

2. **Sum of Emissions by Year and Sector**  
   - Chart Type: Stacked Bar Chart.  
   - Purpose: Highlight sectoral contributions over time.  
   - Fields:  
     - X-Axis: `Year`  
     - Legend: `Sector`  
     - Values: Sum of `value`  

3. **Global Contribution by Country**  
   - Chart Type: Pie Chart.  
   - Purpose: Visualize each country’s percentage contribution to global emissions.  
   - Fields:  
     - Legend: `Country`  
     - Values: Sum of `Global_CO2_percentage_per_country`  

4. **Total Emissions by Country**  
   - Chart Type: Bar Chart.  
   - Purpose: Compare the total emissions of key countries.  
   - Fields:  
     - Y-Axis: `Country`  
     - Values: Sum of `Total_CO2_per_country`  

5. **Country-Sector Relationship**  
   - Chart Type: Matrix Table.  
   - Purpose: Analyze the relationship between countries and their sectoral emissions.  
   - Fields:  
     - Rows: `Country`  
     - Columns: `Sector`  
     - Values: Sum of `value`  

6. **Dynamic Slicer**  
   - Feature: Slicer with `Country` field for dynamic filtering.  
   - Purpose: Allows detailed exploration of data for China, India, Russia, US, or World.

---

## Repository Contents
- **`data/`**: Contains the raw and processed datasets.
- **`notebooks/`**: Jupyter notebooks for data preprocessing.
- **`visualizations/`**: Power BI `.pbix` file with all the dashboards.
- **`README.md`**: This documentation file.

---

## Technologies Used
### **Tools and Frameworks**
- **Python**: Used for data preprocessing. Key libraries include:
  - `pandas`, `numpy` for data manipulation.
  - `matplotlib`, `seaborn` for basic visualizations.
  - `scikit-learn` for data normalization.
- **Power BI**: Used for advanced data visualization and dashboards.

### **Dataset Source**
- Data collected from publicly available global CO2 emissions records.

---

## License

This project is licensed under the MIT License.

