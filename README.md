# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
from matplotlib import pyplot as plt
import pandas as pd
```

```
df = pd.read_csv("DailyDelhiClimate.csv")
df.columns = df.columns.str.strip()
```


```
#Convert date column
df['date'] = pd.to_datetime(df['date'])

# Set index
df.set_index('date', inplace=True)

# Resample (optional, since data is already daily)
df_resampled = df['meantemp'].resample('D').mean()
```
```

# Plot
df_resampled.plot(label='Mean Temperature')

plt.title('Time Series Plot of Daily Mean Temperature')
plt.xlabel('Day')
plt.ylabel('Temperature')
plt.legend()
plt.grid(True)

plt.show()

```

# OUTPUT:
<img width="562" height="471" alt="bf5c9d4d-5314-4ca3-ab6a-72e902412aad" src="https://github.com/user-attachments/assets/157101ee-906e-4ccc-b742-17a289470f73" />






# RESULT:
The time series plot of the dataset shows that the daily mean temperature gradually increases over time with minor fluctuations, indicating a seasonal trend.
