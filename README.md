# QuickBites Crisis – End-to-End Power BI Case Study
## Problem Statement
QuickBite Express is a Bengaluru-based food-tech startup (founded in 2020) that connects customers with nearby restaurants and cloud kitchens.
In June 2025, QuickBite faced a major crisis. A viral social media incident involving food safety violations at partner restaurants, combined with a week-long delivery outage during the monsoon season, triggered massive customer backlash. Competitors capitalized with aggressive campaigns, worsening the situation.
 

# The challenges were severe: 

A large portion of active users disengaged within a short period. 

Daily orders saw a sharp decline compared to earlier months. 

Customer satisfaction scores fell sharply, signaling trust issues. 

Many partner restaurants shifted to competing platforms. 

Customer acquisition costs rose significantly. 

QuickBite has allocated a major recovery budget, overhauled food safety protocols, and upgraded its delivery infrastructure.
 

# The management expects detailed insights into the following: 

Customer Segments: Identify which customers can be recovered and which need new strategies. 

Order Patterns: Analyse order trends to uncover behavioral changes across phases (pre-crisis, crisis, recovery). 

Delivery Performance: Assess delivery times, cancellations, and SLA compliance to pinpoint operational gaps. 

Campaign Opportunities: Recommend targeted initiatives to rebuild trust and loyalty across demographics. 

Restaurant Partnerships: Predict which partnerships are most valuable for long-term retention. 

Feedback & Sentiment: Monitor real-time ratings, reviews, and sentiment to guide ongoing recovery efforts. 


## 🎯 2. Project Goals

- Measure revenue, churn, SLA breach, and customer satisfaction across **Pre-Crisis, Crisis, Recovery** phases  
- Identify **high value lost** and **recoverable** customer groups  
- Analyse **order patterns, cancellations, COD behavior**  
- Evaluate **delivery performance** and SLA issues  
- Assess **restaurant partner retention** and campaign opportunities  
- Provide **clear recommendations** for management

---

## 🛠️ 3. Tools & Tech

- **Power BI** – Data modelling & dashboards  
- **Excel/CSV** – Raw data files  
- Advance **DAX** for measures (churn, revenue at risk, retention score, AOV, SLA, etc.)

---

## 🗂️ 4. Data Sources

Files stored in the Dataset folder:

dim_customer.csv

dim_delivery_partner_.csv

dim_menu_item.csv

dim_restaurant.csv

fact_delivery_performance.csv

fact_order_items.csv

fact_orders.csv

fact_ratings.csv


> Note: Data is anonymised / sample-based for portfolio purpose.

---

# 📊 5. Dashboard Pages

## 1. **Executive Summary**  
💰 Revenue Story (Say This)

Before the crisis, total revenue was 38 million. After the crisis, revenue dropped sharply to 2.9 million. During the recovery phase, revenue improved and reached 8 million, but it is still far below the pre-crisis level. Even after recovery, we have not been able to regain even half of the original revenue.

Before the crisis, the business had a strong customer base of 105,000 users. After the crisis, 76,000 customers churned, meaning nearly 75% of users stopped ordering, which is a serious threat to business stability. The highest churn has occurred in Bengaluru, Mumbai, Delhi, and Hyderabad, making these cities the most critical focus areas for recovery.

Operational performance has also worsened significantly. The SLA breach rate increased from 56% before the crisis to 88% after the crisis, and it remains extremely high at 87% even during recovery, showing that service issues are still unresolved.

Business volumes have dropped sharply as well. Total orders declined from 22,000 in May to just 8,000 after the crisis, and average customer ratings fell from 4.5 to 2.4, clearly reflecting poor customer experience and reduced trust.

## 2. **Customer Recovery & Churn**

**How we created customer segments**
We used the RFM method, which means:
• Recency – how recently the customer placed an order
• Frequency – how many times the customer ordered
• Monetary (Spend) – how much money the customer spent

First, we created a separate RFM table in Power Query. In this table, we calculated the last order date of each customer using the MAX function. From this, we calculated how many days have passed since the last order (Recency Days), total number of orders (Frequency), and total spending (Monetary value).

**Highly Recoverable Customers**

If a customer ordered within the last 90 days, spent more than ₹500, and placed 2 or more orders, we marked them as Highly Recoverable.
These customers are very likely to return because they ordered recently and have a good spending history.
This group needs small cashback, fast delivery, and trust-building messages to come back quickly.

**Warm – Recoverable Customers**

If a customer ordered within the last 120 days, spent more than ₹500, and placed at least 1 order, we marked them as Warm – Recoverable.
These customers are still interested but need a reminder or small festive offer to start ordering again.
They are medium-easy to recover.

**High Value Lost Customers**

If a customer ordered more than 120 days ago but had spent more than ₹500, we marked them as High Value Lost.
These customers were good spenders earlier but completely stopped ordering.
This is the biggest revenue recovery opportunity, but they will need strong offers and service improvements to return.

**Needs New Strategy Customers**

All remaining customers are marked as Needs New Strategy.
These customers have low activity or very old transactions.
They are hard to recover using normal discounts and will need brand campaigns, trust building, and long-term engagement.

**Why this method is important**

The RFM method helps us clearly identify which customers can be recovered quickly, which ones need special offers, and which ones need a completely new marketing strategy.
This allows the company to use money wisely instead of giving discounts to everyone.

**Business Impact**

Highly Recoverable and Warm Recoverable customers can give quick revenue growth.
High Value Lost customers offer the largest revenue comeback potential.
Needs New Strategy customers should be handled with branding and awareness campaigns instead of heavy discounts.

**Final One-Line Summary**

By using the RFM method, QuickBite can separate customers by recovery probability, focus on high-value lost customers for revenue jump, and apply smart offers only where they will work best.

**Customer Base Before, During, and After Crisis**

Before the crisis, the platform had a strong base of 1,05,000 total customers.
After the crisis, 76,000 customers stopped ordering, which means nearly 3 out of every 4 customers were lost.
Only 11,000 customers are truly loyal, meaning they placed orders in all three phases – Pre-Crisis, Crisis, and Recovery.
These loyal customers are our most stable and trustworthy revenue base.

**How Loyal Customers Were Identified**
A customer is marked as Loyal only if they placed at least one order in all three phases:

• Pre-Crisis

• Crisis

• Recovery

This ensures that loyal customers are those who stayed with the brand even during the worst phase, showing high trust and repeat behavior.

**What is Revenue at Risk and How It Was Calculated**

Revenue at Risk means money that we may permanently lose from customers who left after the crisis.

It was calculated in 3 simple steps using the formula:

• First, we took all customers who ordered in the Pre-Crisis phase

• Then, we took all customers who ordered in the Recovery phase

• Then, we removed Recovery customers from Pre-Crisis customers

→ The remaining customers are Churned Customers

After that, we added up their Total Past Spend from the RFM table.

The result shows ₹31.02 million (₹3.1 crore) is currently at high risk because these customers have not returned yet.

**City-Level Churn Clearly Shows Major Problem Areas**

The highest customer loss has come from:

• Bengaluru – 20.6K customers lost

• Mumbai – 11.8K customers lost

• Delhi – 10.2K customers lost

These three cities alone contribute to more than half of total churn.
Because these are top revenue cities, business impact is very high here and they must be fixed first.

**Customer Segmentation Using RFM**

Customers were divided into four groups using Recency (days), Frequency (orders), and Total Spend:

• Highly Recoverable – Recent orders + good spend + multiple orders

• Warm – Recoverable – Slightly older orders + good spend

• High Value Lost – Old orders but very high past spend

• Needs New Strategy – Very old + low activity

**From the dashboard:**

• 69% customers (69K) are in Needs New Strategy

• 25K customers are in High Value Lost

• 9K customers are Warm – Recoverable

• 3K customers are Highly Recoverable

This clearly shows that a large part of revenue recovery depends on High Value Lost and Warm Recoverable customers.

**How Customer Ratings Changed by Segment**

Ratings clearly show the trust problem:

• High Value Lost – 4.2 rating (used to love the brand, but left)

• Needs New Strategy – 4.1 rating

• Warm – Recoverable – 3.4 rating

• Highly Recoverable – 3.4 rating

Low ratings in recoverable groups show that delivery issues, service quality, and experience broke customer trust, not pricing alone.

**Signup Pattern Story**

Most customers joined the platform before the crisis through organic and paid sources.
During the crisis, new signups dropped sharply.
In recovery, signups improved but are still far below Pre-Crisis level, showing that brand growth is still weak.

**What This Story Clearly Tells the Business**

• The business lost most of its customers after the crisis

• ₹3.1 crore revenue is still stuck at risk

• Only 11K customers are truly loyal

• Bengaluru, Mumbai, and Delhi are the biggest damage zones

• High Value Lost + Warm Recoverable customers are the fastest recovery opportunity

• Low ratings confirm that service and delivery problems caused churn

**Final One-Line Business Story**

The crisis caused massive customer loss and ₹3.1 crore revenue at risk, but by fixing service issues in top cities and targeting High Value Lost and Warm Recoverable customers, QuickBite can recover a large part of its lost business quickly.

## 4. Order Patterns & Behaviour
Order Patterns, Crisis Phases & Business Impact (Easy Version)

**How Pre-Crisis, Crisis, and Recovery phases were defined**

To clearly understand customer behavior and business impact, the full timeline was divided into three phases:

• Pre-Crisis Phase: January to May

This period represents normal and stable business operations before any disruption.

• Crisis Phase: June

The crisis started in June, so all activity during this month is treated as the crisis period.

• Recovery Phase: July to September

This period shows how the business started recovering after the crisis.

All analysis, comparisons, and trends are based on this clear phase separation.

Before the crisis, the platform was operating in a stable growth phase with a low cancellation rate of 6.06%, a strong Average Order Value (AOV) of ₹330, and total orders at 114K. This indicates high customer confidence, smooth restaurant operations, and strong purchasing power.

As the crisis hit, there was a sharp behavioral shift. The cancellation rate jumped to 11.56%, while AOV dropped to ₹310, and total orders collapsed to just 9,292. This clearly reflects loss of customer trust, supply-side disruption, and hesitation to place orders. Customers likely experienced frequent order failures, food quality issues, or delivery delays during this period.

In the recovery phase, total orders rebounded strongly to 26K, showing that customer demand has started returning. However, the cancellation rate increased further to 12.06%, and AOV reduced slightly to ₹309, which indicates that operational stability is still not fully restored. Customers are placing orders again, but confidence in order fulfillment is still weak.

A critical behavioral signal is visible in the Cash-on-Delivery (COD) share, which increased from 30% (Pre-Crisis) to nearly 35% during Crisis and Recovery. This clearly suggests that customers are avoiding prepaid orders due to fear of cancellations and delayed refunds. Since cancelled orders typically lead to 3–4 days refund delays, customers are choosing COD to avoid cash being stuck. This confirms low trust in platform reliability during and after the crisis.

From the cuisine and time-based trends, North Indian, Biryani, and Pizza categories continue to dominate order volume across all phases, showing that core demand remains strong. The time-series trend also clearly shows a steep order drop immediately after the crisis onset (June–July), followed by a slow and unstable recovery.

The weekly and hourly order matrix reveals that evening hours (7 PM–10 PM) and weekends (Friday–Sunday) continue to be the highest demand periods, which means user behavior patterns remain intact despite the crisis.

**Key Business Interpretation:**

•	Trust erosion is the biggest challenge, not demand.

•	Customers are returning, but they are protecting themselves with COD.

•	Operational reliability (restaurant fulfillment + refunds) is still a weak link.

•	Recovery is volume-led, not value-led, as seen from falling AOV.

•	Cancellation control is now more critical than growth marketing.

**Strategic Implication:**

QuickBite must now shift focus from acquisition to execution excellence—especially:

•	Reducing cancellations

•	Speeding up refunds

•	Restoring prepaid order confidence

•	Tightening restaurant SLAs during peak hours

Only after operational trust is restored will AOV and prepaid share normalize and revenue stabilize sustainably.

 
## 5. Delivery Efficiency & SLA Performance

**✅ Pre-Crisis (Before Problem)**

Delivery was working well:

• Avg delivery time: 37.5 min

• Avg delay: 2 min only

• Delivery rating: 4.2 (good)

• Active partners: 88%

• On-time delivery: 43%

• SLA breach: 56%

👉 Deliveries were mostly smooth with very low delay.

**❌ Crisis Phase (System Breakdown)**

Delivery performance collapsed:

• Avg delivery time: 42.5 min

• Avg delay jumped to: 18 min

• Delivery rating: 4.2

• Active partners: 88%

• On-time delivery dropped to: 11%

• SLA breach increased to: 88%

👉 Partners were available, but the system failed badly.

**⚠️ Recovery Phase (Orders Back, Delivery Still Weak)**

Orders improved, but delivery did not:

• Avg delivery time: 42.5 min

• Avg delay: 17.5 min

• On-time delivery: 12.5%

• SLA breach: 87%

👉 Customers are ordering again, but delivery is still unreliable.

**📊 Extra Key Insights**

• Orders dropped sharply after May (crisis impact)

• SLA breach is high in all major cities → company-wide issue

• Delays even for short distances → problem is operational, not traffic

**✅ Final Conclusion (Most Important)**

• Crisis badly damaged delivery operations

• Even in recovery, SLA breach is still above 85%

• Customers returned, but delivery trust is still broken

**Immediate fixes needed in:**

– Restaurant-to-rider coordination

– Dispatch delays

– City-level SLA monitoring

👉 If delivery speed is not fixed fast, churn and refund complaints will rise again.

## 6. Restaurant Partnership & Retention

**✅ Overall Summary**

• Total restaurants: 20K

• Active restaurants: 18K → Supply is strong and stable

• Total revenue: ₹48.56M

• Repeat orders: 78K

• Retention score: 12.75% (low) → Weak long-term customer loyalty

**💰 Top Revenue Restaurants**

• Punjabi Express Central is the highest revenue partner (~₹36K)

• Other strong performers:

– Hot & Crispy Biryani

– Thindi Mane

– Classic Tandoor

👉 Revenue is spread across many restaurants → Good for business stability

**🔁 Restaurant Retention Reality**

• Only 2 restaurants show real repeat customers:

– Taste of Biryani Darbar (best)

– Spicy Kitchen Palace (second)

• Most restaurants fail to retain customers

**🧁 Restaurant Tier Risk**

• 100% restaurants fall in Low Retention tier

• No medium or high-retention tier exists

👉 Business is running mostly on one-time customers

**📊 Repeat Orders vs Revenue Insight**

• Some restaurants earn good revenue even with very low repeats

• This shows revenue is coming more from new users, not loyal users

**✅ Final Business Conclusion**

• Revenue is strong, but restaurant loyalty is very weak

• Customers are ordering, but not returning regularly

• Long-term risk:

– Higher marketing cost

– Weak loyalty

– Unstable future revenue

**🎯 Simple Business Actions**

• Start restaurant loyalty programs

• Promote high-repeat restaurants on homepage

• Give visibility to trusted restaurants

• Improve food quality + delivery consistency

## 7. Campaign Opportunities

**✅ Overall Customer Situation**
• Total customers: 105K

• Churned users: 76K → Most customers have stopped ordering

• Recoverable customers: 5,819 → Only this small group can be won back now

• Revenue at risk: ₹31.02M

👉 Big message: Recovery pool is now very small, so campaigns must be highly focused.

**📊 Recoverable Customers by Acquisition Channel**

• Organic: 52K

• Paid: 23K

• Referral: 14K

• Social: 10K

👉 Best recovery tools:

Email offers, app notifications, retargeting ads (Google & Meta)

👉 Organic + Paid users are the strongest recovery base.

**🧩 Customer Segmentation Snapshot**

• Needs New Strategy: 69K (69.02%) → Very hard to recover

• High Value Lost: 25K (25.14%) → Biggest revenue recovery group

• Warm – Recoverable: 3K (3.29%)

• Highly Recoverable: Very small share

👉 Only about 6K users are realistically recoverable now.

**🏙️ Recoverable Customers by City**

Top cities to focus recovery campaigns:

Bengaluru – 723

Mumbai – 403

Delhi – 334

Chennai – 295

Hyderabad – 229

Pune – 188

Ahmedabad – 184

Kolkata – 184
👉 Bengaluru, Mumbai, and Delhi should get the highest campaign budget.

**✅ Final Business Conclusion**

• Customer base is heavily inactive

• ₹31.02M revenue is still at high risk

• Only ~5.8K users can be actively recovered now

• Organic + Paid users are the best recovery targets

• Top recovery cities: Bengaluru, Mumbai, Delhi

**🎯 Fresh Campaign Strategy**

• Give discount + free delivery to:

– Highly Recoverable
– Warm – Recoverable
**• Give loyalty rewards & premium offers to:**
– High Value Lost users
• Run separate city campaigns for:
– Bengaluru
– Mumbai
– Delhi

**👉 One-Line Final Summary:**|

With only 5,819 recoverable users left and ₹31.02M revenue at risk, QuickBite must run laser-focused recovery campaigns in Bengaluru, Mumbai, and Delhi using Organic & Paid channels to prevent permanent revenue loss.
 

## 8. Feedback & Sentiment 

**✅ Total Reviews by Phase**

• Pre-Crisis: 53K reviews

• Crisis: 4,095 reviews

• Recovery: 11K reviews

👉 Customer activity collapsed during crisis and only partially recovered.

**⭐ Average Rating by Phase**

• Pre-Crisis: 4.5 (very good)

• Crisis: 2.58 (very poor)

• Recovery: 2.47 (still poor)

👉 Customer trust broke during crisis and is still not fixed.

**😊 Average Sentiment Score**

• Pre-Crisis: 0.75 (positive)

• Crisis: -0.21 (negative)

• Recovery: -0.27 (still negative)

👉 Even after recovery, customers are still unhappy.

**⚠️ Low Rating %**

• Crisis: 18.46% low ratings

• Recovery: 25% low ratings (even worse)

👉 More customers are unhappy after the crisis than during it — a big warning sign.

**✅ Final Business Insight (Simple)**

• Before crisis → Customers were happy

• During crisis → Trust collapsed

• During recovery → Orders improved, but ratings and trust did NOT improve

• 25% low ratings is dangerous for future growth

**🎯 Simple Business Actions**

• Improve food quality

• Reduce late deliveries

• Fix cold food & packaging issues

• Target low-rating customers with apology offers

• Run quality + trust-focused campaigns

**👉 One-Line Summary:**

Customers came back to order, but they are still unhappy, and unless food and delivery quality improve fast, churn will rise again.


# ✅ How to Open the Report

1. Download `QuickBites_Crisis.pbix` from this repo  
2. Open it using **Power BI Desktop**  
3. Explore each page using the left-side tabs (Executive, Customer, Delivery, Restaurant, etc.)

---
