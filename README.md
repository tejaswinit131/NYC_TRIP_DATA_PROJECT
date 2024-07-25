# NYC_TRIP_DATA_PROJECT

**NYC Trip Data**

Project Overview

This project processes New York Taxi Trip data for the year 2019 to derive analytical insights and load the processed data into a SQLite database for further analysis.

Environment Setup

Ensure the following Python packages are installed:

Python 3.7+,

Pandas,

Requests,

TQDM, 

SQLite3,

Matplotlib,

Seaborn

---

Project Structure

The project contains the following scripts:

Extraction Part


NYC_TRIP_DATA_EXTRACTION.py 

I extracted taxi trip data for three months in 2019. Attempting to process data for the entire year or six months resulted in a fatal error: "The Python kernel is unresponsive." 
Due to system limitations, I couldn't execute the extraction for a year and for six months. So , i took one month of trip_data which is easily processed in my system.

Finally, I extracted data for one month and mount to google drive.

ERROR_HANDLING:

I handle network errors and retry error also .
The combination of requests.Session() and Retry from urllib3 provides a robust way to handle network errors and automatically retry requests. This setup helps ensure that transient errors do not cause our script to fail, making the download process more reliable.

**Processing Part**

NYC_TRIP_DATA_PROCESSING.py 

After extracting the parquet files, I checked their schemas using df.printSchema(). The "For-Hire Vehicle Trip Records" files lacked the required columns, so I skipped these files and applied transformations to the remaining ones.

Transformations included:

Cleaning and transforming the data for analysis. Removing trips with missing or corrupt data. Deriving new columns such as trip duration and average speed. Aggregating data to calculate total trips and average fare per day. I displayed five records of each transformed DataFrame.

Loading Part

I loaded processed data into a SQLite database, creating necessary tables and indexes.
And I fillfulled the following requirments ,
Design and implement a schema suitable for querying trip metrics.
Use SQL to load data into the database efficiently.
And the result is shown below.

**Analysis Part**

NYC_TRIP_DATA_ANALYSIS.py

Data Analysis and Reporting

Task: Generate insights and reports from the database.

I fillfued following Requirements:

Develop SQL queries to answer the following questions:
    What are the peak hours for taxi usage?
    How does passenger count affect the trip fare?
    What are the trends in usage over the year?
Create visualizations to represent the findings.
