# Food_Sales_Prediction_Project
First pandas project for Coding Dojo bootcamp

## Overview of the Project


Acme Foods is a fictional grocery store which has assigned me the task of analyzing sales trends and building a predictive model that will determine future sales. This project was completed to fulfill the requirements of Coding Dojo’s Data Science - Machine Learning program.


## Explanation of the Data
### Initial Observations
The given dataset contained 12 categories of information: 5 numeric and 7 object categories. However, only 3 numeric categories contained data that was usable for our machine learning model: the weight of each product (‘Item_Weight’), its list price (‘Item_MRP’), and its visibility on the shelves (‘Item_Visibility’, expressed as a percentage). Other numeric categories were either designated as the predictive model’s target (‘Item_Outlet_Sales’) or a date (‘Outlet_Establishment_Year’). This lack of numeric data would cause issues with the predictive model. Even the highest model (a Random Forest model), yielded only a 61% R^2 score.

### Cleaning the Data

The original dataset contained null values in Outlet_Size and Item_Weight categories. Additionally, over 5% of the Item_Visibility category (526 values) were listed as 0%. These were also treated as nulls.

After reviewing the data the following decisions were made for filling in the null values. I filled Outlet_Size with its most frequent values based on its assigned Tier in the ‘Outlet_Location_Type’ column. I selected this strategy based on determining that each Tier corresponded roughly to a particular Outlet_Size. 

Because of the limited distribution range for the Item_Weight column, I imputed the median values for its nulls. I also filled 0% Item_Visibility products with that column’s median value. 

I also cleaned inconsistent values in the ‘Item_Fat_Content’ column.

### Analysis of the Data

**Sales by Tier**
My analysis of the data first focused on the differences in item sales across location types. From my analysis I determined that a product is more likely to sell well at a Tier 3 store. There is a far greater distribution of items that had a high Item_MRP than in either Tier 1 or 2. 

![Outlet tiers and sales](https://github.com/rgnemasters/Food_Sales_Prediction_Project/blob/main/Unit%20Sales%20by%20Tier%20(1).png)

Viewed as boxplots, the distribution of the cumulative sum of item sales by Tier reveals both greater sales and a wider distribution for Tier 3. Size and location are pivotal to the success of each product. 

![Cumulative Sales by Tier](https://github.com/rgnemasters/Food_Sales_Prediction_Project/blob/main/Cumulative%20Sales%20by%20Tier%20(1).png)

**Sales by Category and Visibility**
I also observed that certain food categories did very well on average that were not getting high visibility. 

Optimal visibility seemed to be in the 7-15% range, but most stores set up their products in the 5% range.
![Cumulative Sales by Tier](https://github.com/rgnemasters/Food_Sales_Prediction_Project/blob/main/item_vis_image_final2%20(1).png)
