readme = r'''# Marketing Performance Analysis

End-to-end marketing analytics project using Python, pandas, matplotlib, and seaborn.

## Project Overview
This project analyzes a synthetic marketing performance dataset with around 3,000 rows across 4 related tables. The goal was to clean the data, define meaningful KPIs, explore performance across multiple business dimensions, and translate the findings into clear business actions.

The analysis focused on channel performance, campaign efficiency, regional opportunities, device behavior, seasonality, and lead funnel performance.

## Business Problem
Marketing teams often assume the main problem is traffic volume. This project showed that the bigger issue was how budget was allocated and what happened after leads entered the funnel.

## Business Questions Answered
- Where is the marketing budget being wasted?
- Which channels, campaigns, and regions deserve more investment?
- Which campaigns should be repeated?
- Are the generated leads actually good quality?
- What is the best-performing region and channel combination?
- Is the issue in acquisition, or in the lead conversion process after acquisition?

## Dataset Overview
The project used 4 tables:

- **marketing_dataset**: campaign, channel, region, spend, revenue, clicks, conversions, device
- **campaigns**: campaign budget and campaign dates
- **channels**: channel names and types
- **leads**: lead status and score

## Tools Used
- Python
- pandas
- matplotlib
- seaborn

## Project Workflow
### 1. Data Cleaning
I cleaned and standardized the data before analysis.

Main fixes included:
- Standardized column names across all tables
- Cleaned inconsistent text values in channels and campaigns
- Removed trailing spaces in regions
- Filled missing region values with `Unknown`
- Filled missing lead statuses with `Unknown`
- Replaced null impressions using the mean
- Replaced negative revenue values with 0 when conversions were 0
- Prevented division-by-zero errors in CPA calculations
- Checked impressions for outliers using the IQR method

### 2. KPI Definition
I calculated key marketing performance metrics, including:
- CTR = clicks / impressions
- CVR = conversions / clicks
- CPC = spend / clicks
- CPA = spend / conversions
- ROI = (revenue - spend) / spend
- ROAS = revenue / spend

### 3. Exploratory Data Analysis
I analyzed performance across:
- Channel
- Campaign
- Region
- Device
- Time / seasonality
- Lead funnel

## Key Insights and Business Answers

### 1) Where is the budget being wasted?
The analysis showed multiple waste points instead of one single issue:

- **Google Ads** had the highest spend in the dataset but only average returns and a very high lost lead rate.
- **CMP103 (Black Friday)** had a major overspend compared with its planned budget.
- **CMP105 (Discount Blast)** had a large budget but barely spent any of it.
- **Alex** had the weakest regional performance with the highest CPA and lowest revenue.

**Answer:** budget waste came from inefficient channels, poor campaign budget control, and weak regional allocation.

### 2) Where should the company invest more?
The best opportunities were clearly underfunded:

- **Instagram** delivered the best ROI while receiving relatively low spend.
- **Tanta** showed the strongest regional efficiency.
- **Mansoura** also performed strongly across efficiency and revenue.
- **Ramadan Offer (CMP104)** was the top revenue campaign and still left budget unused.

**Answer:** shift more budget toward Instagram, Tanta, Mansoura, and Ramadan Offer.

### 3) Which campaigns should be repeated?
Two seasonal campaigns stood out:

- **Ramadan Offer** generated the highest revenue.
- **Summer Sale** delivered the second-highest revenue.

**Answer:** Ramadan Offer and Summer Sale are the clearest candidates to repeat and scale.

### 4) Are the leads good quality?
Lead quality was average, and the bigger issue was conversion after acquisition:

- Only **27.1%** of leads converted
- Around **15.4%** of leads were stuck in `Contacted`
- Lost rate varied significantly by campaign

**Answer:** the company does not only have a lead quality problem. It also has a follow-up and conversion process problem.

### 5) What is the best-performing region and channel combination?
Two combinations stood out depending on the goal:

- **Tanta + Instagram** for the highest return and efficiency
- **Cairo + Facebook** for stronger volume and cost efficiency

**Answer:** the best combination depends on the objective. Tanta + Instagram is strongest for ROI, while Cairo + Facebook is stronger for scale.

## Insights by Dimension

### Channel Insights
- Instagram delivered the highest ROI and appears underfunded
- Facebook had the cheapest CPA and balanced performance
- Google Ads consumed the most budget but did not lead on return
- TikTok had the lowest ROI and needs review
- Email was affordable but less efficient in return

### Campaign Insights
- Ramadan Offer was the strongest campaign by revenue
- Summer Sale was a strong second performer
- Some campaigns showed serious budget execution issues
- The business problem was not only strategy, but also campaign control and budget execution

### Region Insights
- Cairo generated the most total revenue
- Tanta and Mansoura were the most efficient regions
- Alex was the weakest region and needs review
- Unknown region values reduced actionability and highlighted a tracking issue

### Device Insights
- Device performance was nearly identical across mobile, desktop, and tablet
- Mobile slightly led on ROI and CPA, but not enough to justify a strong decision
- The even device split looked unrealistic and suggested synthetic data behavior

### Time and Seasonality Insights
- Q1 was consistently the strongest period
- Mid-year performance weakened
- October and November were the weakest months
- December drove high revenue but not necessarily the highest efficiency
- There was no strong long-term growth trend

## Data Quality Flags
This project also highlighted important data quality concerns:

- ROI values looked unusually high and likely reflected total revenue, not net profit
- Some lead campaign IDs did not match the campaigns table
- Campaign dates did not align meaningfully with transaction dates
- Device budget split was unrealistically equal
- Some channel-level patterns looked too uniform, which is common in synthetic datasets

## Business Impact
This analysis helped the company:

- Identify where budget was being wasted
- Spot underfunded high-performing opportunities
- Understand that lead follow-up needed improvement before increasing acquisition spend
- Improve decision-making around channels, campaigns, and regions
- Turn raw data into clear, actionable recommendations


    
