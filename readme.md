################# MKT Analytics Report Ing. Nicolas Yapur ############################

# MKT Analytics Report

## Índice

- About
- ETL
- EDA
- Files/Links

## About
This is a CRM data analysis project. The task consists of analyzing and building a dashboard that helps the team gain a clearer picture of their processes over time. The insights and results obtained through ETL, EDA, and dashboard visualizations will be explained in detail in each section of the report.

## ETL

The ETL was performed over a .xlsx file named "test_analysis.xlsx" and the result is a transformed xlsx file named "test_analysis_etl.xlsx" ans a transformed csv file named "test_analysis_etc.csv". Heere are the ETL Insights and Conclusions:

### Dataset Errors:

- The column "intro_call_satus" has typing errors, we must fix them in the source, we are now aware of this error and we must find the way to avoid the error. I have resolved the error for this dataset.

- The column "intro_call_scheduled_date" has schechuled dates that are before we even acquired the lead "lead_date".I have resolved the error for this dataset.

### Missing Data

- Lots of missing data in general.

- Columns "intro_call_status" and "intro_call_scheduled_date" contain very important information, we must keep a track of the contacted leads and the schedule date for contacting them, through this data we could also study a optimal contact period. We should try not to have null values heere.

- Filled "NA" values of string columns with "no_data".

### Dataset Expansion and Transformations

- Created the "channel_type" to study the inbound_channel and outbound_channel efficiency.

- Created the "channel" column to slice by in reports.

- Deleted str "Mkt: Inbound: " from inbound_channel.

### Ideas/Suggestions

- We could add the info of last_time_contacted, could be usefull for following leads that sowed a possitive response and have probability of conversion. We should keep in contact with this type of leeds that might convert into clients after more contacting times. We should also study the optimal time between client contact.

- The more data columns we have the more chances we have of clusterize clients and define more effective actions for the sales people based on the clusterization (we could apply a sentyment and response analysis).  

- Lead_stage status columm should be divided into more status options than just "closed" and "client", we should be able to give the sales department data to track the progress of each lead through the various stages of the sales, to help with priorization based on the state of the lead and to highlight and find potential bottlenecks in the sales pipeline.we must try not to have null values heere. I assume we keep track of the full client convertion steps becouse we have the "Closed" status in the lead_stage column.

## EDA

The exploratory data analysis has been conducted in python, in power bi and in looker studio using the "test_analysis_etl.xlsx" & "test_analysis_etl.csv" files as the input data.

### Insights:
- Channels, Our most important channel for lead acquisitiom is the Outbound channel 79.31% of the leads acquiren in the 8 months analyzed. In the whole period The top 3 Outbound channels are Warms Email, Mass Email and Warm LinkedIn, but there are 3 months where the linkedin channel rises to the top 3. This months are February,march and April 2024. I cant tell if this behabiour is continuous due to seasonality or if the Linkedin channel got a rise up this last 3 months.
- Summary: Outbound channel is our top channel for lead acquisition, the top outbound channels are Warm Email,Mass Email and Warm Linkedin. The Linkedin channel became more relevant and rised up to the top 3 channels in the last 3 months.

- On the other hand the Inbound channel acquired the 20.69% of our Leads in this period.Our main Inbound channel is Google adds, this channel was responsable of the 31,25% of the leads for the Inbound channel in September 2023. This channel has experimented a notorious rise over the months.In the last 3 months (February,March,April) it became responsable for over the 50% of the leads acquired by the Inbound channel. Again I cant tell if the up and downs of the other Inbound channels are due to a rise up in the channel or due to seasonality becouse of the short data period i have available.
- Summary: The Inbound channel is responsable for 20.69% of the Lead acquisition, our most important Inbound channel is Google Adds and it became more relevant in February,March,April where it is responsable for over the 50% of the leads acquired for this channel.

- Lead over time, there are three spikes that indicate strong months for data acquisition: November,February and April.It would be interesting to further analyze this with more available data. The pattern indicates that although the Outbound Channel is the most relevant, we can observe that in the November pick the Outbound channel lead acquisition goes down while the Inbound channel has its highest spike. It would be a good strategy to potentiate the Inbound channel in the month of November. A similar behabiour happends in the month of February, but this time is the Outbound channel the one that experiments its highest spike. Again it's necessary to evaluate a larger period of data to confirm this insights.
- Summary: We have 3 spikes for lead acquisition (November,February,April), The November spike is the month where the Inbound channel performed the best and the outbound channel performed its lowest lead count. If this is a pattern over the years we could potentiate the Inbound channel in this month.

- Call Status, for the "intro_call_status" columns we have around 70% of blank data in every month. We have no scheduled calls between Oct-23 and Jan-24.
Leaving the blank values out of the analysis, 68% of our calls are being completed and 19% of our calls are being canceled.The month with the most calls completion pct is March-24.For the lead stage status we have < 10% of blank data except for Apr-2024 where we have 37% of blank data. Leaving the blank data out of the analysis, 99% of the lead_stage status is "Closed", assuming "Closed" means contacted and no sale made and "Client" means the lead convertion into a client, we have a very low convertion rate of 0.33% in general,0.58% Inbound and 0,27% Outbound for the 8 months of period.
- summary: We have lots of blank data in the "intro_call_status" column and a reasonable ammount of blank data in the "lead_stage" column. March is the month where we compleet the most of the calls. Our convertion rate is very low, we should take action. 

### Ideas/Suggestions

- Lead_stage status columm should be divided into more status options than just "closed" and "client", we should be able to give the sales department data to tracking the progress of each lead through the various stages of the sales, to help with priorization based on the state of the lead and to highlight and find potential bottlenecks in the sales pipeline.we must try not to have null values heere. I assume we keep track of the full client convertion steps becouse we have the "Closed" status in the lead_stage column.

- We should analyze a larger dataset to better understand seasonality and trends. With this information, we can promote inbound or outbound channels during the specific months when they perform best.

## Files/Links: 

- Github:   
    [ver Github](https://github.com/yapurnico/MKT_ANALYTICS)
- Dashboard PowerBi:
    [PBI Dashboard](https://drive.google.com/drive/folders/10FfkGUc0230mWs3uLy-ri9xjpKw3Gv7p?usp=sharing)
- Dashboard Looker:
    [Looker Dashboard](https://lookerstudio.google.com/reporting/6bcd33ad-c2a7-4365-af7c-849009acba67)     
- Video with Explanation:
    [Video](https://drive.google.com/drive/folders/10FfkGUc0230mWs3uLy-ri9xjpKw3Gv7p?usp=sharing)