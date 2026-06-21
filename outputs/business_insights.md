# Business Insights Report
## Retail Executive Dashboard — Sales & Business Intelligence (2024–2025)

---

## Calculated Fields Used

| Field | Formula | Purpose |
|---|---|---|
| Profit Margin | SUM([profit]) / SUM([sales]) | % of revenue that becomes profit |
| Cost | SUM([sales]) - SUM([profit]) | Derived cost per order |
| Average Order Value | SUM([sales]) / COUNTD([order_id]) | Revenue per unique order |
| Return Rate | SUM([return_flag]) / COUNT([order_id]) | % of orders returned |
| Return Rate Avg | AVG([return_flag]) | Average return rate for segment comparisons |
| Shipping Delay Bucket | IF/ELSEIF on delivery_days | Groups delivery speed into 5 categories |

---

## Insight 1: Sales Trend — Volatile Monthly Pattern With No Clear Peak Season

**Observation:** The monthly sales trend line shows high volatility throughout 2024–2025 with no consistent seasonal peak.

**Data Evidence:** Sales ranged from a low of ₹63,03,795 (August 2024) to a high of ₹1,08,61,500 (August 2025). January 2024 started strong at ₹94,46,558 but dipped significantly mid-year. Total sales across both years = ₹21,70,17,652.

**Business Interpretation:** The absence of a clear seasonal pattern suggests sales are driven by individual large orders rather than consistent demand cycles. This makes forecasting and inventory planning difficult.

**Recommended Action:** Investigate the top 20 orders by value to check if a few large B2B orders are driving monthly spikes. Consider implementing demand smoothing strategies or promotional campaigns during historically low months (April–May, July–August 2024).

---

## Insight 2: Regional Performance — South Leads in Sales But All Regions Have Similar Margins

**Observation:** The South region leads total sales but profit margins are nearly identical across all four regions.

**Data Evidence:**
- South: ₹6,46,93,707 sales | ₹99,87,912 profit | 15.44% margin
- North: ₹5,45,55,801 sales | ₹83,14,884 profit | 15.24% margin
- West: ₹4,89,08,980 sales | ₹74,04,073 profit | 15.14% margin
- East: ₹4,88,59,164 sales | ₹75,99,443 profit | 15.55% margin

**Business Interpretation:** Regional pricing and discount strategies are remarkably consistent. The South's higher sales volume is a market size advantage, not a margin advantage. East has the highest margin (15.55%) despite lower sales volume.

**Recommended Action:** Investigate why East achieves the best margin. Apply East's pricing or discount discipline to other regions, particularly West which has the lowest margin (15.14%).

---

## Insight 3: Category Profitability — Technology Dominates, Furniture Underperforms

**Observation:** Technology generates the vast majority of profit while Furniture and Office Supplies contribute minimally despite significant sales volume.

**Data Evidence:**
- Technology: ₹15,38,95,268 sales | ₹2,80,43,310 profit | 18.2% margin
- Furniture: ₹5,16,41,016 sales | ₹35,57,835 profit | 6.9% margin
- Office Supplies: ₹1,14,81,368 sales | ₹17,05,168 profit | 14.9% margin

**Business Interpretation:** Technology is the profit engine of the business — generating 84% of total profit from 71% of total sales. Furniture has extremely low margins at 6.9%, suggesting pricing issues, high costs, or excessive discounting.

**Recommended Action:** Prioritize Technology in marketing and sales efforts. Conduct a full margin review for Furniture — particularly Tables and Bookcases which have the lowest profit values despite reasonable sales.

---

## Insight 4: Sub-Category Profitability — Copiers and Accessories Are Star Performers

**Observation:** Within Technology, four sub-categories dominate profitability while all Furniture sub-categories underperform.

**Data Evidence:**
- Copiers: ₹4,06,12,515 sales | ₹73,10,055 profit (18.0% margin)
- Accessories: ₹3,91,98,321 sales | ₹71,86,863 profit (18.3% margin)
- Phones: ₹3,83,93,924 sales | ₹70,97,291 profit (18.5% margin)
- Machines: ₹3,56,90,508 sales | ₹64,49,101 profit (18.1% margin)
- Tables: ₹1,28,95,345 sales | ₹7,31,534 profit (5.7% margin)
- Bookcases: ₹1,24,68,764 sales | ₹7,11,733 profit (5.7% margin)

**Business Interpretation:** All four Technology sub-categories achieve ~18% margins consistently. Tables and Bookcases are the weakest performers — their low margins likely reflect high discounting or high delivery costs due to size and weight.

**Recommended Action:** Increase stock and promotional focus on Copiers and Accessories. Review discount caps for Tables and Bookcases — consider minimum margin thresholds before approving discounts.

---

## Insight 5: Customer Segment Behavior — Home Office Has Highest Sales and Profit

**Observation:** All three customer segments perform similarly, but Home Office edges ahead in both sales and profit.

**Data Evidence:**
- Home Office: ₹7,45,00,746 sales | ₹1,15,55,047 profit | 15.5% margin
- Consumer: ₹7,18,86,173 sales | ₹1,10,30,581 profit | 15.3% margin
- Corporate: ₹7,06,30,733 sales | ₹1,07,20,685 profit | 15.2% margin

**Business Interpretation:** The three segments are nearly equal in revenue contribution, which indicates a healthy, diversified customer base. Home Office segment's slight edge may reflect higher average order values or lower return rates compared to Consumer.

**Recommended Action:** Maintain balanced investment across all three segments. Explore upselling opportunities in the Corporate segment given its slightly lower average performance.

---

## Insight 6: Discount Impact — Negative Correlation With Profit, High Discounts Drive Losses

**Observation:** The scatter plot shows a clear negative relationship between discount rate and profit — higher discounts consistently reduce profitability.

**Data Evidence:**
- Discount-Profit correlation: -0.27 (negative relationship confirmed)
- Orders with discount ≥ 30%: 592 orders
- Of those 592 high-discount orders: 161 have negative profit (27.2% loss rate)
- Average profit on 30%+ discount orders: ₹2,729 (vs overall average much higher)

**Business Interpretation:** Discounts above 20% are eroding margins significantly. Nearly 1 in 4 orders with 30%+ discounts results in a loss. The trend line on the scatter plot shows this most steeply for Furniture.

**Recommended Action:** Implement a discount approval policy — require manager sign-off for discounts above 20%. Set a hard cap at 25% for Furniture products where margins are already thin.

---

## Insight 7: Shipping Performance — Standard Class Is Most Used But Slowest

**Observation:** Standard Class dominates order volume but has the highest average delivery time, while Same Day and First Class deliver significantly faster.

**Data Evidence:**
- Standard Class: 2,435 orders (58% of all orders) | avg 4.71 delivery days
- Second Class: 894 orders | avg 2.68 delivery days
- First Class: 630 orders | avg 1.77 delivery days
- Same Day: 241 orders | avg 0.40 delivery days
- Heatmap shows Standard Class + Standard (3-4 Days) cell = darkest (1,141 orders)

**Business Interpretation:** Most customers are using Standard Class, likely due to cost. However, with avg 4.71 days, this may be contributing to customer dissatisfaction. The 201 orders in Standard Class + Very Slow (7+ days) category are a risk for negative reviews.

**Recommended Action:** Investigate the 201 Standard Class orders taking 7+ days — identify if specific regions or product types are causing delays. Consider offering free First Class upgrades for high-value orders.

---

## Insight 8: Return Patterns — Furniture and Home Office Segment Have Highest Return Rates

**Observation:** Furniture has the highest return rate by category, and Home Office has the highest return rate by customer segment.

**Data Evidence:**
- Return rate by category:
  - Furniture: 7.67% (88 returns from 1,147 orders)
  - Office Supplies: 3.65% (61 returns from 1,669 orders)
  - Technology: 3.03% (42 returns from 1,384 orders)
- Return rate by segment:
  - Home Office: 5.67% (82 returns from 1,446 orders)
  - Corporate: 4.00% (56 returns from 1,399 orders)
  - Consumer: 3.91% (53 returns from 1,355 orders)
- Return rate by region: East highest at 4.91%, West lowest at 4.34%

**Business Interpretation:** Furniture's 7.67% return rate is more than double Technology's 3.03%. This suggests product quality issues, inaccurate product descriptions, or damage during shipping for large items. Home Office segment returning more may reflect stricter quality expectations for work-from-home setups.

**Recommended Action:** Conduct a return reason analysis for Furniture — add detailed product photos, dimensions, and assembly guides to reduce expectation mismatches. For Home Office segment, improve product quality checks before dispatch.
