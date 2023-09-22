<h1 align="center"> Play Store App Review Analysis</h1>

<p align="center"> 
<img src="GIF/google play.gif" alt="Animated gif" height="282px">
</p>

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Table Of Contents

- [Project Description](project-description)
- [Project Files Description](project-files-description)
- [Dataset Contents](dataset-contents)
- [Variables Details Of Dataset](variables-details-of-dataset)
- [Problem Statements](problem-statements)
- [Technologies Used](technologies-used)
- [Steps Involved](#steps-involved)
- [Key Insights](key-insights)
- [Conclusion](conclusion)

## 📋 Project Description
This project focuses on conducting an in-depth analysis of Play Store app reviews to extract valuable insights. It involves data cleaning, visualization, and statistical analysis to uncover patterns, trends, and user sentiments. The primary objectives include understanding user behavior, identifying factors influencing app ratings, and providing actionable recommendations for app developers and marketers.
The objective of this experiment is to deliver insights to understand customer demands better and thus help developers to popularize the product. We have tried to discover the relationships among various attributes such as which application is free or paid, what are the user reviews, rating of the application.
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

##  💾 Project Files Description

<p>This Project includes 1 google colab notebook and 2 data set in the fromat of csv file:</p>

### Executable Files:
- [Play Store App Review Analysis](https://github.com/San13deep/Play-Store-App-Review-Analysis/blob/main/Play_Store_App_Review_Analysis_Capstone_Project.ipynb) - Includes all functions required for clustering operations.

### Output:
- [Google Colab](https://github.com/San13deep/Play-Store-App-Review-Analysis/blob/main/Play_Store_App_Review_Analysis_Capstone_Project.ipynb) - All the outputs are visible in the provided colab notebook.

### Input Files:
  <li><b>Play Store Data.csv</b> - It contains the basic details of the app like number of user reviews, ratings, etc.</li>
  <li><b>User Reviews.csv</b> - It contains the user reviews and its sentiment score for the respective app.</li>


![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Dataset Contents

- This **[data set](https://drive.google.com/file/d/19fVBgoQJr5jkupe0O9Ht8VeMqSVaBJae/view?usp=share_link)** contains two csv  files of data scraped from google play store app for the period of 2010 - 2018.  The first dataset - `apps` contains data on play store apps and its attributes, while the other dataset - `reviews` containing data on customer reviews for each playstore app.  

- Key variables in the dataset includes :

**Apps Dataset:**

| variables | Details |
| --------------------- | ---------------------- |
| App | google play store app name |
| Category | This section gives the category to which an app belongs. In this dataset, the apps are divided among 33 categories.|
| Rating | app rating on a scale of 1-5 |
| Reviews | The number of reviews given by users for app |
| Size | The size of the app in KB or MB |
| Installs | Total installs or downloads of the app |
| Type | Is it free or paid app?|
| Price | Amount charged for the app in doller($) |
| Content Rating | It states which age group is suitable to consume the content of the respective app. |
| Genres | It gives the genre(s) to which the respective app belongs. |
| Last Updated | The date the app was last updated |
| Current Ver | The current version of the app |
| Android Ver | The minimum android version app can run on |

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

**User Reviews Dataset:**

| Variables | Details |
| --------------------- | ---------------------- |
| App | It contains the name of the app with a short description (optional). |
| Translated Review | It contains the English translation of the review dropped by the user of the app.  |
| Sentiment | It gives positive, negative or neutral sentiment for an app. |
| Sentiment_Polarity |  Polarity score based on user reviews | 
| Sentiment_Subjectivity | Subjectivity score based on user reviews |

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 📋Problem Statements

1. What are the top categories on Play Store?
2. Are majority of the apps Paid or Free?
3. How importance is the rating of the application?
4. Which categories from the audience should the app be based on?
5. Which category has the most no. of installations?
6. How does the count of apps varies by Genres?
7. How does the last update has an effect on the rating?
8. How are ratings affected when the app is a paid one?
9. How are reviews and ratings co-related?
10. Lets us discuss the sentiment subjectivity.
11. Is subjectivity and polarity proportional to each other?
12. What is the percentage of review sentiments?
13. How is sentiment polarity varying for paid and free apps?
14. How Content Rating affect over the App?
15. Does Last Update date has an effects on rating?
16. Distribution of App update over the Year.
17. Distribution of Paid and Free app updated over the Month.

********************************************************************************************************************************************************************

## 📔 **What are the technolgies used?**
1. Python
2. Numpy library
3. Pandas library
4. Matplotlib
5. Seaborn
   
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 📖	Steps Involved

### Data Cleaning
Our data set contains a large number of null values in the rating column, so we drop them. Some of the columns have a smaller number of null values, so we replace the null values in these columns with the mode value of that particular column. Our data set also contain the duplicate rows for a single application. We also drop the duplicate rows because the rows contain the identical data. Also drop the rows, which have rating greater than 5.

### Data Transforming 
From the information of data frame, we can see that all the columns except rating have the object data type but some of the columns like, reviews, size, installs and price have the numerical value. So, we have to transform them in proper data type and also remove the unwanted values from the numerical columns like ‘+’ and ‘,’ from installs and ‘$’ from price. In the size column we have some values in KB and some values in MB, so we transform all the values in MB.

### Exploratory Data Analysis
After establishing a good sense of each feature, we proceeded with plotting a pairwise plot between all the quantitative variables to look for any evident patterns or relationships between the features. There is a high variance in the number of installs and in number of reviews. To overcome this problem, we add two new columns to the data frame named: log_installs and log_review, which contain the logarithmic values of installs and review columns, respectively.

### Single Variate Analysis
After that we analysis all the columns one by one to examine whether the particular column contain some useful information or not:

### Category
We breakdown the apps by category and observe that family and game categories have the maximum number of apps in the play store. Weather, house and home, comics, events, beauty, and parenting are the categories which have a few numbers of apps.

### Data wrangling
Apart from this, two new columns were added to the main data frame, namely, “Rating Group”, and “Revenue”. This is done to improve simplify the analysis and come up with different meaningful visualizations

* <b>Rating Group:</b> This column groups the apps based on the average user rating. (4-5: Top rated, 3-4: Above average, 2-3: Average, 1-2: Below average).
*	<b>Revenue:</b> This column gives the revenue generated by the app through app installs alone.
By doing these operations on the original dataset, we are ready with the data pipeline, and data visualizations can be done on it.
All the apps in play store have the rating between 0.5 to 5. Maximum apps have the rating between 3.8 to 4.5.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)


### Key Insights:

*	Percentage of free apps = ~92%
*	Percentage of apps with no age restrictions = ~82%
*	Most competitive category: Family
*	Category with the highest number of installs: Game
*	Category with the highest average app installs: Communication
*	Percentage of apps that are top rated = ~80%
*	There are 20 free apps that have been installed over a billion times
*	Minecraft is the only app in the paid category with over 10M installs. This app has also produced the most revenue only from the installation fee.
*	Category in which the paid apps have the highest average installation fee: Finance
*	Most popular app in the Play Store based on the number of reviews: Facebook
*	The median size of all apps in the play store is 12 MB.
*	The apps whose size varies with device has the highest number average app installs.
*	The apps whose size is greater than 90 MB has the highest number of average user reviews, i.e., they are more popular than the rest.
*	Helix Jump has the highest number of positive reviews and Angry Birds Classic has the highest number of negative reviews.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 📋 Conclusion:

Most of the apps are free so developers should focus on creating free apps to have a huge customer base. If developing paid apps then apps size should not be greater than 40mb. More Apps should be in the category like Events,Beauty,Parenting as they have not been explored much but still quite popular with huge installations. In order to retain the customer base apps should be updated regularly Developers should develop apps such that their content is available for everyone. Bulky apps should be developed in the category like Game, Family. If developing paid apps then its price should not be high and size should be less than 20mb. Apps belonging to Game and Family Category have high negative reviews therefore they should be developed carefully. Like this there can be a lot of conclusions but we have tried to cover the most important ones.
These are some of the aspects that the developer should research before proceeding with the app development. By conducting a simple exploratory data analysis (EDA) on the play store dataset, we not only eliminate avoidable risks of failure, but we may also be able to provide better ideas for building the app.


![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
