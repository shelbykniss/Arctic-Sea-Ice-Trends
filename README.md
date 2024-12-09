# Arctic-Sea-Ice-Trends
Comparing historical trends in Arctic Sea Ice on three different scales.

Data Access:

1. NOAA Optimum Interpolation SST V2 Dataset can be accessed here: https://psl.noaa.gov/data/gridded/data.noaa.oisst.v2.highres.html
   - Monthly Mean: /Datasets/noaa.oisst.v2.highres/icec.mon.mean.nc
   - Long-Term Mean: /Datasets/noaa.oisst.v2.highres/icec.mon.ltm.1991-2020.nc
2. Arctic Sea Routes can be accessed here: https://arctic-nga.opendata.arcgis.com/datasets/nga::arctic-sea-routes/explore
3. NSIDC Sea Ice Index V3 can be accessed here: https://nsidc.org/data/g02135/versions/3 
    - Navigate here for specific file: https://noaadata.apps.nsidc.org/NOAA/G02135/north/monthly/data/
  
Code Notebooks:

Data_Processing.ipynb: Download, clean and fill missing Sea Ice Concentration Data. Mask data to only include sea route geometries. Export to netCDF files for easy access later.

Arctic_Analysis.ipynb: Calculate percent area of sea ice coverage for the overall Arctic using NSIDC's Sea Ice Index V3 data. Export to csv for easier access later.

Route_Analysis.ipynb: Calculate the percent length of each sea route containing greater than 15% SIC for each September using NOAA OISST V2 Data.

Trouble_Spot_Analysis.ipynb: Identify trouble spots along each sea route by plotting increasing SIC using NOAA OISST V2 long term mean SIC Data. Then, use monthly mean SIC data to replicate calculations from Route-Analysis to generate a time series of percent coverage data for each trouble spot in September.

Trend_Analysis.ipynb: Plot time series for each scale and location, fit a linear regression model to each, calculate slope and RMSE for each model, then resample residuals with replacement to generate 1000 bootstraps for each model to calculate 95% CIs and inform projection estimates to 2100.


