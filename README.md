# Kickstarting with Excel

## Overview of Project

This analysis focuses on Kickstarter data, which is used to focus on the success of theater production kickstarters based on varying factors.
Specifically these factors include the launch date of the theater kickstarter and the monetary goal set by the kickstarter which will be used to determine whether or not there is a pattern in success or failure based on these variables.  

### Purpose

The purpose of this analysis is to help a client determine the optimal conditions necessary for them to achieve a successful outcome with their own theater kickstarter. 
By visualizing the outcomes of similar previous kickstarters, the client will be better able to make informed decisions about when they should begin the kickstarter and how high they should set their goal in order to achieve a successful outcome. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

To start, I needed to create a new column that would separate the Year from the "Date Created Conversion" column using the YEAR() function to perform the extraction.
I then created a pivot table that filtered variables based on "Parent Category" to focus on Theater Kickstarters, and "Years" to see how theater kickstarters have changed over time. 
In the columns field in the pivot table I placed "outcomes", in the rows field I placed "Date Created Conversion" and in the Values field I placed the "Count of outcomes."
Once the fields were properly formatted to remove unnecessary data, I was able to create a line chart that showed how successful, failed, and canceled theater kickstarters varied by different months. 
This analysis would help the client determine the best month in which to start a new theater kickstarter and which months show the least success. 
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/90734050/139594563-39e5bcc2-52e7-44fd-8906-d1c339589df7.png)


### Analysis of Outcomes Based on Goals

For this analysis, I focused on the subcategory "plays" which was the type of fundraiser the client was intending to focus on. 
I created a new sheet which included columns of the goal amount, number of successful, failed, canceled, and total projects, and the percentage of each of those outcomes. 
I separated rows under the "Goals" column into denominations that included "less than 1000", "1000 to 4999", "5000 to 9999", ..., to "Greater than 50000"
I  used the "COUNTIFS()" function to fill in the "Numbers (Outcome)" columns. 
	For cell B2 the formula was "=COUNTIFS(Kickstarter!$D:$D, "<=1000", Kickstarter!$F:$F, "successful", Kickstarter!$O:$O, "plays")" 
	I changed each successive formula to match the "Goals" conditions in Column A. 
	I then changed each outcome of the formula to match the outcome in the column. 
I used the "SUM()" function to count the number of total projects within the "Goal" denominations. 
To calculate the percentage of each outcome, I divided the number of projects with a particular outcome by the total outcome within the Goal denominations and multiplied by 100.
	(i.e. (Number successful/total projects)*100) or ((B2/BE)*100) for number of successful outcomes with a goal of Less than 1000. 
Once each of the percentages had been calculated, I created a line chart to visualize changes in outcomes based on goal amount putting percentage on the y-axis, goal denominations on the x-axis. 
![Outcomes_vs_Goals](https://user-images.githubusercontent.com/90734050/139594596-dacef3a2-f13a-458c-a627-0047e6781612.png)


### Challenges and Difficulties Encountered

While this project was very clear with the direcctions we needed to follow, I found it difficult to use the COUNTIFS() function while keeping all of the parameters in order and it was a time consuming process. 
I also struggled to figure out what exactly the visualizations were telling me about the data. 
	I could see some trends in what was happening, but it was not always clear how I should interpret what was being shown. Such as certain spikes in success rates during certain months, or the fluctuations in success and fail rate based on goal amounts. 


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

I found that success rates spiked in the months between May and July which would be the best time to launch a theater kickstarter campaign. 
I also found that failed outcomes spiked in October and Successful outcomes continued moving downward from October to December, with December having an almost equal number of failed and successful campaigns, making this period between October and December the worst time to start a theater campagin. 

- What can you conclude about the Outcomes based on Goals?

Overall, it appears that plays with fundraisers that are lower than $5000 had the highest success rate and trended toward lower success rate as the goal amount went up (especially between $15000 and $35000 and greater than $45000). 
The exception to this occurred between $35000 and $45000 in which a number of plays were able to be more successful than the number of failed plays. 


- What are some limitations of this dataset?

This dataset does not give us more information about the types of plays and theater productions that were involved. The genre of theater production may influence the success of the theater campaign. It may also influence whether certain production will be more popular in certain times of years over another (i.e. holiday themed productions, outdoor sytle events, etc). 
Another possible limitation is the lack of information about how the kickstarter was advertised (i.e. how long it was advertised, the mediums used to get the word out, and who the advertisements were geared toward). 
I am also curious as to what the column "Staff_Pick" means in the dataset as it may be a predictor as to whether or not a kickstarter is successful. 

- What are some other possible tables and/or graphs that we could create?

I would be interested in looking at the success rate based on how many backers are behind a project. I would guess that more backers would correlate with a higher success rate, but it would depend on how much the backers contributed. It would also be interesting to see if backers contributed larger amounts in certain times of the year. 



