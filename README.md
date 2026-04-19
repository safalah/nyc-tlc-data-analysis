# NYC TLC Green Taxi Trip Record Analysis

This project analyzes New York City Green Taxi (boro taxi) trip records from January 2023. The goal is to identify operational patterns, understand revenue distribution, and provide actionable insights for fleet management and urban transport planning.

## Dataset

The analysis uses the following datasets:

- `nyc_tlc_trip_record.csv`: The raw dataset containing 68,211 trip records with 20 columns (e.g., timestamps, pickup/dropoff locations, fare amounts, etc.).
- `taxi_zone_lookup.csv`: A lookup table to map location IDs to specific NYC boroughs and zones.
- `nyc_tlc_dataset_clean.csv`: A cleaned version of the dataset used for final analysis.

## Key Steps & Workflow

1. **Data Cleaning**: Handling missing values, removing outliers in fare and distance, and correcting data-type inconsistencies.
2. **Feature Engineering**: Creating time-based features (pickup hour, day of the week) and calculating trip durations.
3. **Exploratory Data Analysis (EDA)**:
   - **Temporal Analysis**: Identifying peak-demand hours and busy days.
   - **Financial Analysis**: Analyzing fare structures, tip percentages, and surcharges.
   - **Operational Patterns**: Comparing vendor performance and trip types (street-hail vs. dispatch).
   - **Geographic Analysis**: Pinpointing high-demand zones and popular routes.
4. **Statistical Testing**: Using Mann-Whitney U and Kruskal-Wallis tests to validate differences in trip metrics across different categories.

## Requirements

The analysis is performed using Python in a Jupyter Notebook environment. The following libraries are required:

- `pandas`: Data manipulation and analysis.
- `numpy`: Numerical operations.
- `matplotlib`: Basic data visualization.
- `seaborn`: Statistical data visualization.
- `scipy`: Statistical tests.

## How to Run

1. Ensure you have Python installed (preferably via Anaconda).
2. Install the required libraries if you haven't already:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy jupyter
   ```
3. Open the terminal or command prompt in the project directory.
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
5. Open and run `nyc_tlc_analysis_falah.ipynb`.

## Results & Outputs

The analysis highlights key operational patterns and data issues in NYC TLC Green Taxi trips (Jan 2023), along with practical recommendations:

- **Peak Demand Hours**: Weekday peaks occur during 6–9 AM and 4–8 PM, with weekend late-night spikes (1–3 AM).  
  → Align driver shifts and incentives with these high-demand periods.

- **High-Volume Zones**: A small number of zones dominate pickups, with some imbalance between dropoffs and pickups.  
  → Use demand heatmaps and optimize driver repositioning.

- **Rate Code Issues**: Presence of `RatecodeID = 99 (Unknown)` and possible mis-coded airport trips.  
  → Enforce validation and monitor as a data-quality KPI.

- **Payment Patterns**: Cash trips show $0 tips, while card payments yield higher recorded revenue.  
  → Encourage card usage and ensure POS reliability.

- **Vendor Differences**: CMT and VeriFone show statistically different trip patterns.  
  → Standardize reporting and investigate disparities.

- **Data Quality Gap**: ~6.3% of rows missing multiple fields due to ingestion failure.  
  → Add validation checks and alert systems.

- **Surcharge Inconsistencies**: Some trips show incorrect congestion surcharge values.  
  → Automate surcharge rules based on zones.

Overall, the results provide a foundation for improving fleet efficiency, regulatory compliance, and data reliability.

## Dashboard

View the interactive dashboard here: [Tableu Public Link](https://public.tableau.com/app/profile/zal.falah/viz/NYCTLCDA/Dashboard)
