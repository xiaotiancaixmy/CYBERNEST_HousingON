# **Project 1: Canada Real Estate Analysis**
* Project name: CYBERNEST_Housing
* Course title: Fintech Bootcamp
* Group members: Emma, Parastoo, Shewta, Haihua
* Date: July 10th

## **Table of Contents**

- [Project Objective](#project-objective)
- [Dependencies](#dependencies)
- [Data Cleanup & Exploration](#data-cleanup--exploration)
- [How to Use](#how-to-use)
- [Data Analysis](#data-analysis)
- [Results](#results)
- [Postmortem](#postmortem)
- [Conclusion](#conclusion)

</br>

## **Project Objective**

This project conducts a comprehensive analysis of Canada's real estate market using various data sets. The objective is to understand the housing market in different provinces, identify the most popular house types, understand market demand based on price range, and evaluate the affordability of houses in different provinces. Additionally, we will perform a risk analysis of real estate-related stocks.


Here's a summary of the questions answered in this analysis:

1. **How have housing prices changed over the years across different provinces?**
    
    - *Why*: Understanding housing price changes over time allows us to identify market trends and potential investment opportunities.

2. **What's the overall housing market return in each province over the past 4 years?**
    
    - *Why*: By assessing the market trend in each province, we can identify areas of high growth and potential areas of concern.

3. **What is the most popular type of house and its corresponding units sold in each province in 2022?**

    - *Why*: Knowledge about the most popular housing types can be beneficial for real estate developers and investors to plan their projects effectively.

4. **Which price range demonstrates the highest market demand, indicated by the most absorbed units, and how does this demand vary across different provinces?**

    - *Why*: Understanding market demand by price range can help developers price their projects competitively and investors to make informed decisions.

5. **Given the average income for each province, what type of house can the average person or household realistically afford? How does this vary across different provinces?**

    - *Why*: This can provide insights into affordability levels and identify provinces where housing is more or less affordable based on average income levels.

6. **How have the real estate-related stocks performed over the past 4 years? What is the stock beta for selected real estate and construction companies, and how does it contribute to our understanding of their risk profiles and market performances?**
    
    - *Why*: Given the high cost associated with direct property ownership, investing in real estate-related stocks provides a more affordable avenue for individuals to gain exposure to the real estate market. Evaluating the performance and risk of these stocks can offer invaluable insights for potential investors, guiding them to make informed decisions and better understand the inherent risk profiles and market performance of these companies.

</br>

**Summary of findings**
The questions were  answered in our detailed analysis, and they provided valuable insights into the real estate market in Canada.

Our findings showed that there were significant variations in housing trends and market demand across provinces. Some provinces had more preference for certain types of houses, and affordability also varied greatly. Additionally, we found that the risk and performance of real estate-related stocks varied, providing an additional perspective for potential investors.  

</br>

## **Dependencies**

This project requires the following Python libraries:

- Pandas
- NumPy
- Path
- Datetime
- HvPlot
- Holoviews
- Matplotlib
- Seaborn
- Plotly (new)
- Mortgage (new)

</br>

## **How to Use**

The notebook includes a interactive function. During the affordability analysis, users will be prompted to input their personal financial details. Please follow the on-screen instructions to input the necessary information. 

The `find_affordable_house()` function will ask the user for their mortgage rate, term, down payment percentage, and income, and then print the provinces and house types that they can afford. If they don't provide any input and just press enter, the function will use the default values (5% rate, 25 years term, 20% down payment, $50000 annual income).

</br>

## **Data Cleanup & Exploration**

### Data
The project uses the following data sources:

- Housing price data from the Canada Mortgage and Housing Corporation ([CMHC](https://www.cmhc-schl.gc.ca/professionals/housing-markets-data-and-research/housing-data/data-tables/housing-market-data/absorbed-units-price-range))
- Average income data for each province (From [CMHC](https://www.cmhc-schl.gc.ca/search#q=average%20income&sort=relevancy))
- Real estate-related stocks data (From [Yahoo Finance](https://ca.finance.yahoo.com/quote/REI-UN.TO/history?p=REI-UN.TO)) 
- Gerographic data for each province (From [LatLong.net](https://www.latlong.net/category/provinces-40-60.html))

</br>

### Cleanup & Exploration Process

Upon determining that our research topic would revolve around Canada real estate, we initially attempted to acquire the necessary data from Statistics Canada and MLS. However, this process came with its own set of challenges.

We discovered that the data from MLS was embedded within PDF files, which made extraction of the necessary information quite challenging. Meanwhile, the data from Statistics Canada had a high level of redundancy. There were inconsistencies in the statistical calibrations across different years, complications in terms of housing classification, regional differences, and issues related to level of detail of the data.

After much exploration, we found a more reliable source of data from the Canadian Mortgage and Housing Corporation (CMHC). The CMHC data encompassed details of 'absorbed units,' representing sales data of newly constructed houses. Interestingly, from our initial observation of MLS data, we found no significant difference in prices between new and pre-owned houses within the same area. Moreover, the CMHC provided us with data from several consistent years in a uniform format. This led us to use CMHC's data for our core housing information, specifically focusing on absorbed units by price range (from year 2019 to 2022).

Despite the issues encountered during the data cleanup and exploration phase, they led us to a more robust and reliable dataset. This unexpected outcome gave us greater confidence in the subsequent analysis. The visualization and further exploration of this data are available within our Jupyter Notebook, demonstrating intriguing trends and insights in the Canadian real estate market.

Additionally, we obtained historical stock data of two highly representative companies related to real estate from Yahoo Finance. One is a **Real Estate Investment Trust (REIT)**, and the other is a **Construction Development Company**.

> A Real Estate Investment Trust (REIT) is a company that owns, operates, or finances income-generating real estate. Modeled after mutual funds, REITs pool the capital of numerous investors. This makes it possible for individual investors to earn dividends from real estate investments—without having to buy, manage, or finance any properties themselves. 

Through our study, we aim to explore the stock performance of these two representative entities in the real estate market, providing a view of real estate related stocks as an alternative investment.

</br>

## **Data Analysis**

In order to effectively analyze the data we gathered and respond to our proposed questions, we carried out several steps.

### Step 1: Data Parsing and Cleaning
As mentioned earlier, we acquired housing data from CMHC and stock data from Yahoo Finance. Both sets of data came in different formats and had their own quirks. In order to make them work together, we had to clean and parse them accordingly.

For the housing data, we parsed the absorbed unit data by price range from CMHC's data. We also had to handle multiple issues such as data duplication, inconsistencies in statistical measurements across different years, and varying data accuracy across provinces. We mitigated these issues as much as possible to ensure the integrity of our data.

In regards to the stock data, we downloaded historical data for a Real Estate Investment Trust (REIT) and a construction development company, which are the two representative entities in our study. The data was already well structured, hence only minimal cleaning was required.

### Step 2: Data Merging
After cleaning and parsing the data, we merged the datasets to allow for comparison and analysis. We implemented the merge on the basis of date to enable us to track changes over time in both housing and stock data.

### Step 3: Data Analysis and Visualization
Following the data merge, we started analyzing the combined data. Our focus was on understanding how the real estate market and stock market performed over the same period, and how various factors influenced both. We implemented various data visualization techniques to illustrate these relationships. We used Jupyter Notebook to create these visualizations, which included time series plots, histograms, scatter plots, and more.

### Step 4: Upload Plot Files and Write Up

</br>

## **Results**

The analysis results are presented as data tables, charts, graphs and interacted function. These visualizations provide a detailed insight into the Canadian housing market, showcasing variations in housing prices, market trends, popular house types, demand by price range, and affordability across provinces.

</br>

## **Postmortem**

  * Discuss any difficulties that arose, and how they were handled.
  * Discuss any additional questions that arose, which couldn't be answered due to time constraints. 
  * What would you research next if you had two more weeks?

</br>

## **Conclusion**

This project provides a comprehensive overview of the real estate market in Canada. It's a useful resource for understanding housing trends and affordability across different provinces. The risk analysis of real estate-related stocks offers valuable insights for investors interested in this sector.
