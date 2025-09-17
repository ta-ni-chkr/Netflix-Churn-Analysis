# Netflix Churn Analysis

## Table of Contents

- [Project Background](#project-background)
- [Dataset](#dataset)
- [Implementation](#implementation)
- [Key Questions Answered](#key-questions-answered)
- [Executive Summary](#executive-summary)
- [Recommendations](#recommendations)
- [Running the Notebook](#running-the-notebook)

## Project Background

Netflix, established in 1997, has evolved from a DVD rental service into a global streaming powerhouse with over 300 million subscribers across 190+ countries. However, with the streaming landscape becoming increasingly competitive, understanding churn dynamics — the rate at which subscribers cancel or discontinue their service — has become essential for improving retention and strengthening user loyalty.

This project focuses on performing an exploratory data analysis (EDA) to examine the underlying churn patterns among Netflix users, based solely on this demo dataset. By looking at user demographics, subscription details, and engagement indicators, the analysis uncovers key trends and behaviours that may help explain the potential reasons for user drop-off.

## Dataset

The dataset used for this analysis consists of 25140 rows and can be downloaded from [here](https://github.com/user-attachments/files/22368020/Netflix_Churn_Analysis.xlsx).

### Column Overview:

<p align="center">
  <img width="534" height="770" alt="image" src="https://github.com/user-attachments/assets/0486527f-d77f-4ee4-82cb-2199ff7b85af" />
</p>

*Image credit: The Indian Express*

## Implementation

The analysis was carried out in Python using Visual Studio Code, utilizing the following libraries for data manipulation and visualization:

- Pandas  
- NumPy  
- Matplotlib
- Seaborn  

## Key Questions Answered

1. [What is the overall churn rate?](#1-what-is-the-overall-churn-rate)
2. [Which age groups have the highest user numbers and the highest churn rate?](#2-which-age-groups-have-the-highest-user-numbers-and-the-highest-churn-rate)
3. [Which countries show the highest and lowest churn?](#3-which-countries-show-the-highest-and-lowest-churn)
4. [Is churn rate different across subscription types?](#4-is-churn-rate-different-across-subscription-types)
5. [How do satisfaction, engagement, and support interactions vary between churned and retained users across subscription plans?](#5-how-do-satisfaction-engagement-and-support-interactions-vary-between-churned-and-retained-users-across-subscription-plans)
6. [Which device-subscription combinations dominate churned user behaviour?](#6-which-device-subscription-combinations-dominate-churned-user-behaviour)
7. [Does longer subscription length reduce churn?](#7-does-longer-subscription-length-reduce-churn)
8. [How does churn vary by genre?](#8-how-does-churn-vary-by-genre)
9. [Which factors are most strongly correlated with customer churn behaviour?](#9-which-factors-are-most-strongly-correlated-with-customer-churn-behaviour)
10. [What key behavioural differences exist between churned and retained users?](#10-what-key-behavioural-differences-exist-between-churned-and-retained-users)
11. [What percentage of retained users are currently at high risk of churning?](#11-what-percentage-of-retained-users-are-currently-at-high-risk-of-churning)

## Executive Summary

The complete Python script can be downloaded from [here](https://github.com/user-attachments/files/22377953/project_analysis.ipynb), and the findings from the key questions are outlined below.

### 1. What is the overall churn rate?

Roughly 1 out of every 3 users (34.61%) have churned, which indicates that the business has lost a substantial portion of its user base and potentially its long-term revenue.


<p align="center">
  <img width="380" height="262" alt="Image" src="https://github.com/user-attachments/assets/edafb817-d942-4484-906c-8244a86d8063" />
</p>


### 2. Which age groups have the highest user numbers and the highest churn rate?

The 18–29 group has the largest base (4,512) and the highest churn volume (17.37%), followed by the 70–80 group (4,000 users, 15.72% churn share). While churn rates across most groups cluster around ~33.5–35%, the 40–49 segment is highest at 35.40% and 18–29 is lowest at 33.49%, showing its churn volume stems from size, not weak retention. The <18 group, though smallest (1,813 users, 7.17% churn), records a relatively high churn rate (34.42%), even above older age segments like 60–69 (34.22%) and 70–80 (34.20%), suggesting early drop-offs.


<p align="center">
  <img width="1010" height="332" alt="Image" src="https://github.com/user-attachments/assets/39317ef8-8d32-4389-be05-617709eb3ca1" />
</p>


### 3. Which countries show the highest and lowest churn?

The USA, with the largest customer base of 5,859 (23.31%), accounts for 23% of total churn, suggesting that overall churn is a function of scale rather than poor loyalty. The user volume in every other country is approximately one-third or more of that of the USA. Among the 11 countries analyzed, Canada shows the highest churn rate at 36.52% with a total of only 1,985 users, indicating significant user disengagement. Similarly, the UK, despite having the smallest user base of 1,851, records a high churn rate of 35.66%, again pointing to poor retention. India, however, stands out with the lowest overall churn (7.38%) and the lowest churn rate within its user base (33.28%), showcasing strong retention.


<p align="center">
  <img width="997" height="816" alt="Image" src="https://github.com/user-attachments/assets/075b8fcc-4f85-417a-a9bc-e104badbb2ca" />
</p>


### 4. Is churn rate different across subscription types?

The table below showcases details about the various subscription plan Netflix offers.


<p align="center">
  <img width="600" height="254" alt="Image" src="https://github.com/user-attachments/assets/cb8c0369-43e9-4bf2-b239-e4fde249a775" />
</p>


Although, with 29.91% and 28.92%, the Standard and Premium plans dominate the platform, the Mobile plan, with only 18% of the user base, shows a notable weakness. Despite a user gap of approximately 3,000 from the tow other leading plans, it records the highest within-base churn (35.34%). This high churn, likely due to its restrictive functionalities and poor user experience—including 480p standard resolution, single-device viewing, and no large-screen casting—suggests many users opt for the Mobile plan initially due to lower pricing but churn quickly when expectations are not met, highlighting stronger loyalty or satisfaction for higher-tier plans and inefficiencies or discontent in low-tier option.


<p align="center">
  <img width="801" height="320" alt="Image" src="https://github.com/user-attachments/assets/b67da6e8-918e-4c81-b694-9b9a8a7cb47b" />
</p>


### 5. How do satisfaction, engagement, and support interactions vary between churned and retained users across subscription plans?

Out of the 18.21% Mobile plan users who churned, 10.15% are Tablet users—over 55% of total churn— even though tablets, with larger screens and better resolution, are assumed to provide a superior experience. Standard and Premium together contribute nearly 59% of churn, while the Basic plan adds another 23.05%. Across these three plans, larger-screen devices—namely Smart TVs (20.40%), Laptops (20.25%), and Desktops (19.85%)—are the top contributors, highlighting that larger-screen devices dominate the churn landscape among higher-tier users. 

Larger-screen churn likely stems from buffering issues, app crashes, slow load times, or perceived value gap — causing frustration, especially among higher-paying subscribers who expect premium performance and ultimately driving churn when the platform feels subpar or outdated on big screens. For Basic users, churn may be driven by fundamental performance problems or poor resolution even on stable large screens. These are potential causes and need further investigation to validate.


<table>
  <tr>
    <td><img width="480" height="300" alt="image" src="https://github.com/user-attachments/assets/51671d21-2b92-403b-9721-9255dc9c9966" /></td>
    <td><img width="480" height="300" alt="image" src="https://github.com/user-attachments/assets/aab80c18-9b6a-42ac-b00f-9c747f13e78d" /></td>
  </tr>
</table>



### 6. Which device-subscription combinations dominate churned user behaviour?

Churned users report over 55% lower satisfaction than retained ones (3.5 vs 7.9), with Premium users showing the lowest score (3.48) despite paying the most—signaling unmet expectations and price sensitivity as major churn drivers. 
Engagement, however, is not predictive, as usage levels between churned and retained users remain nearly identical (~6.20–6.23), though Mobile churners lag slightly (6.16), likely due to screen exhaustion and reduced cinematic experience, and casual on-the-go viewing during commutes or breaks. It suggests usage alone doesn’t guarantee retention if overall experience is disappointing. 
Support interactions provide another strong cue. On average, a churned user logs ~4.5 support queries—about 3.5× more than a non-churned user (~1.3), linking unresolved issues directly to churn. Marginally high engagement but low satisfaction among churned Premium users could suggest they’re using the service but don’t feel it’s worth the high cost.


<p align="center">
  <img width="1021" height="250" alt="Image" src="https://github.com/user-attachments/assets/928443fe-a414-4313-94e8-32e056afcdcc" />
</p>


### 7. Does longer subscription length reduce churn?

Churn stays fairly stable across all engagement spans, ranging from ~34% to ~36%, showing that longer tenure doesn’t reduce churn. Even users with 24 months of usage churn at rates similar to short-term users, indicating retention is experience-driven rather than duration-driven and tenure length alone is not a reliable predictor of churn. Churn peaks slightly at 6 months compared to 1-month and 3-month users, suggesting accumulated dissatisfaction or unmet expectations. The 6-month point may mark a critical stage where long-term engagement declines and users reassess service value.


<p align="center">
  <img width="650" height="403" alt="Image" src="https://github.com/user-attachments/assets/4f1c7f8d-f964-4ece-9aa4-cb553042d26a" />
</p>


### 8. How does churn vary by genre?

Horror, Comedy and Drama are the most-watched and also top churned genres — together accounting for 45.61% of total churn, indicating high audience drop-off despite popularity, likely due to content fatigue, repetitive storytelling, declining content quality or disappointment from overhyped content. Thriller, with 12% of users, contributes the least to churn (10.39%), suggesting stronger audience loyalty from suspense-driven content that keeps viewers engaged. Documentary, Action, Sci-Fi, and Romance have comparatively lower user proportions and show slightly lower churn. Overall, high popularity does not guarantee retention, while certain genres maintain steadier engagement.


<table>
  <tr>
    <td><img height="320" alt="Image 1" src="https://github.com/user-attachments/assets/bc95723b-5f75-421e-9ba4-1fe5fd4910ae" /></td>
    <td><img height="320" alt="Image 2" src="https://github.com/user-attachments/assets/381449c7-f84e-4fec-97d9-c850cd294e95" /></td>
  </tr>
</table>


### 9. Which factors are most strongly correlated with customer churn behaviour?

Support queries show a strong positive correlation with churn (r = +0.82), indicating users facing frequent issues are much more likely to leave. Customer satisfaction negatively correlates with support queries (r = -0.614) and churn (r = -0.77), showing that unresolved issues lower satisfaction and increase churn risk. Daily watch time and engagement are highly correlated (r = +0.87) but have no meaningful link to churn (r ≈ 0). These correlations reinforce previously observed patterns, underscoring how user behaviour drives churn.


<p align="center">
  <img width="756" height="541" alt="Image" src="https://github.com/user-attachments/assets/a337e3f0-f9fc-4eaa-908e-35443ef82c10" />
</p>


### 10. What key behavioural differences exist between churned and retained users?

Since findings on satisfaction, engagement, and support interactions align with the patterns discussed in the 6th question (across subscription plans), the focus here shifts to other behavioural variables.
The extremely weak correlation of Engagement Score (6.23 vs 6.21) and Daily Watch Time (2.75 vs 2.74 hrs) with churn explains the <0.05% difference between churned and retained users, indicating users often churn despite similar usage.
Both churned and retained users show almost identical promotional offer usage (2.50 vs 2.52), thus proving its poor association with churn. 
A slightly higher proportion of retained users tend to delay payments (50.63%) compared to churned users (49.45%), with just over a 1% difference.


<p align="center">
  <img width="861" height="774" alt="Image" src="https://github.com/user-attachments/assets/aa756091-9615-4fb3-a8ce-2a5c4e93a5e3" />
</p>


### 11. What percentage of retained users are currently at high risk of churning?

As of June 10, 2025, 10.25% of retained (16440) users are at high churn risk due to inactivity for over 45 days, indicating disengagement. Another 3.73% are flagged for potential churn based on moderate satisfaction (scores 3–7) and above-median support query usage, a behavioural signal of rising dissatisfaction.

The PDF with comprehensive insights can be accessed [here](https://github.com/user-attachments/files/22378050/Detailed.Insights.pdf) for reference.

## Recommendations

- Proactive efforts are needed to understand why users under 18, despite forming the smallest group, are churning more than older age groups.
- Countries like Canada, Mexico, UK, France, and Australia require stronger retention strategies, as their churn rates exceed those of larger markets like the USA and Brazil.
- It’s important to uncover why tablet users on the Mobile plan churn more than mobile users, despite a better screen experience.
- Higher churn from larger-screen devices (laptops, desktops, smart TVs) under Standard, Premium, and Basic plans must be examined to improve platform compatibility and user satisfaction.
- Churn levels among long-term subscribers (12–24 months) remain unexpectedly high, suggesting that sustained engagement strategies are lacking and should be revisited to reduce long-term user drop-off.
- Existing variables like age, engagement rate, and watch time, use of promotional offers, show weak correlation with churn; better predictors need to be explored and integrated.
- Users showing early signs of churn should be identified and targeted with timely interventions to improve retention.

## Running the Notebook

To run the notebook:

1. Open [project_analysis.ipynb](https://github.com/user-attachments/files/22377953/project_analysis.ipynb) in VS Code, Jupyter Notebook, or JupyterLab.
2. When prompted to select a kernel:  
   - Choose **Python Environment**. 
   - Then select **Python 3.13.3** from the list of available environments. 
3. Ensure the required libraries are installed.
4. Run the cells sequentially to reproduce the analysis and visualizations.
