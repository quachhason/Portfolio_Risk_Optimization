
<h1>From Data to Decisions: Analytics-Driven Investment Strategy</h1>
<h2>A Competition-Winning Business Analytics Project - Runner-Up</h2>

<p>Investment decisions require a strategic blend of data analytics, risk management, and financial decision-making. As part of Business Challenge 1, my team and I tackled a real-world investment problem, competing against top analytical minds. We conducted a deep-dive financial analysis to evaluate and optimize Carl Icahn’s $9.88 billion portfolio, identifying risks, analyzing asset performance, and proposing data-driven investment strategies. By leveraging SQL, Python, and Tableau, we developed an insightful, analytics-driven approach that secured us the runner-up position in the competition.</p>

<h2>Our Mission</h2>

<p>Our mission was clear:</p>
<ul>
    <li>✅ Assess the current portfolio’s risk-return performance.</li>
    <li>✅ Identify inefficiencies and underperforming assets.</li>
    <li>✅ Recommend a diversified investment strategy backed by analytics.</li>
</ul>

<p>By leveraging SQL for data extraction, Python for statistical analysis, and Tableau for visualization, we uncovered critical insights that led us to become runner-up in the competition.</p>

<h2>Understanding the Problem: Why the Portfolio Underperformed</h2>
<p>Our first step was evaluating the existing investment landscape.</p>

<h3>Key Portfolio Metrics:</h3>
<ul>
    <li>Total Portfolio Value: $9.88 billion</li>
    <li>2024 Portfolio Performance: -35% return</li>
    <li>S&P 500 Performance: +20% return</li>
</ul>
<p>This significant underperformance indicated a misalignment between risk and reward in the investment strategy.</p>

<h3>Portfolio Allocation by Asset Sector: A Major Risk Identified</h3>
<img src="https://github.com/quachhason/Portfolio_Risk_Optimization/blob/main/Images/1.%20Portfolio%20Allocation%20by%20Asset%20Sector.png">

<p>Our analysis revealed a concerning concentration in the Energy sector (75.45%), significantly increasing portfolio volatility.</p>

<p>A lack of sector diversification meant that fluctuations in the Energy market heavily impacted portfolio returns.</p>

<h3>Historical Performance of Key Holdings: IEP & CVI in Decline</h3>
<p>To further understand why the portfolio was underperforming, we analyzed the historical price trends of Icahn Enterprises (IEP) and CVR Energy (CVI)—the two largest holdings.</p>

<img src="https://github.com/quachhason/Portfolio_Risk_Optimization/blob/main/Images/2.%20Historical%20Performance%20of%20Key%20Holdings.png">
<h4>Findings:</h4>
<ul>
    <li>IEP (Icahn Enterprises) dropped from ~$120 in 2014 to under $20 in 2024.</li>
    <li>CVI (CVR Energy) followed a similar downward trajectory.</li>
</ul>
<p><b>Takeaway:</b> Despite Carl Icahn’s aggressive investment style, these holdings consistently underperformed, highlighting the urgent need for diversification. Notably, IEP (Icahn Enterprises) is Carl Icahn’s own company, and CVI (CVR Energy) is a subsidiary of IEP, further amplifying concentration risk as a significant portion of the portfolio is tied to interconnected entities with declining performance.</p>

<h2>Technical Approach: A Data-Driven Strategy for Portfolio Optimization</h2>

<h3>1. Database Creation & SQL Analysis: Structuring Financial Data</h3>
<p>To organize, store, and extract key insights efficiently, we designed a relational database in MySQL, which structured financial data across multiple entities. This database architecture allowed for seamless integration of investor profiles, portfolio holdings, trade activity, and stock pricing, enabling efficient query execution for financial analysis.</p>

<h4>Database Schema Overview</h4>
<p>Our database consisted of eight tables that mapped different functional components of portfolio management, structured as follows:</p>

<h5>Front Office Tables:</h5>
<ul>
    <li>Client Table: Stores investor profiles, including risk preferences and credit scores.</li>
    <li>Portfolio Table: Tracks investment holdings, performance metrics, and benchmark comparisons.</li>
</ul>

<h5>Mid-Office Tables:</h5>
<ul>
    <li>Trade Table: Logs buy/sell transactions for in-depth trade analysis.</li>
</ul>

<h5>Back Office Tables:</h5>
<ul>
    <li>Asset Table: Categorizes stocks by sector, industry, and risk levels.</li>
    <li>Pricing Table: Maintains historical stock price data for trend analysis.</li>
    <li>Guided Strategy Table: Stores investment strategy recommendations .</li>
    <li>Compliance Table: Ensures adherence to investment policies.</li>
</ul>

<h4>Entity-Relationship Diagram (ERD)</h4>
<img src="https://github.com/quachhason/Portfolio_Risk_Optimization/blob/main/Images/3.%20Entity-Relationship%20Diagram%20(ERD).webp">


<h4>Key SQL Queries for Portfolio Analysis</h4>
<p>Using SQL, we extracted portfolio composition, risk metrics, and asset performance for financial analysis.</p>

<h5>1. Query to Retrieve Portfolio Holdings & Performance</h5>
<p>To assess portfolio allocation and sector risk exposure, we used SQL to extract asset distributions by industry.</p>
<pre><code>SELECT p.ticker, p.risk_metric, p.return_percentage, a.asset_sector
FROM portfolio p
JOIN asset a ON p.ticker = a.ticker
WHERE p.client_id = 1;</code></pre>
<p><b>Insight:</b> This helped us analyze which sectors dominated the portfolio and their associated risk levels.</p>

<h5>2. Query to Identify Underperforming Assets</h5>
<p>To flag inefficient stocks, we filtered assets that had lower returns than the portfolio average.</p>
<pre><code>SELECT ticker, return_percentage
FROM portfolio
WHERE return_percentage < (SELECT AVG(return_percentage) FROM portfolio);</code></pre>
<p><b>Insight:</b> This allowed us to pinpoint investments that were dragging down performance and justify reallocation.</p>

<h3>2. Python for Investment Analytics: Quantifying Risk & Return</h3>
<p>Using Pandas, NumPy, Matplotlib, and Plotly, we performed:</p>
<ul>
    <li>Risk-Return Analysis: Sharpe Ratio calculations to evaluate risk-adjusted performance.</li>
    <li>Portfolio Benchmarking: Comparing returns against the S&P 500 benchmark.</li>
    <li>Stock Trend Analysis: Identifying high-risk, low-return assets.</li>
</ul>

<h4>Portfolio vs. S&P 500 Performance (2024)</h4>
<img src="https://github.com/quachhason/Portfolio_Risk_Optimization/blob/main/Images/4.%20Portfolio%20vs.%20S%26P%20500%20Performance%20(2024).png">

<p>Our visualization revealed persistent underperformance, emphasizing the need for a new investment strategy.</p>

<p>Carl Icahn’s portfolio (blue line) experienced steep losses.</p>
<p>The S&P 500 benchmark (orange line) maintained steady positive returns.</p>
<p>This confirmed that sticking with the current asset allocation was financially unsustainable.</p>

<h4>Risk vs. Return Analysis (Current Portfolio)</h4>
<img src="https://github.com/quachhason/Portfolio_Risk_Optimization/blob/main/Images/5.%20Risk%20vs.%20Return%20Analysis%20(Current%20Portfolio).webp">

<p>We plotted annualized risk (volatility) vs. return to identify inefficient assets.</p>


<p>To better understand the portfolio’s inefficiencies, we conducted a risk vs. return analysis, plotting annualized risk (volatility) against annualized return. This visualization helped us identify assets that contributed disproportionately to risk without delivering sufficient returns.</p>

<h5>Key Insights from the Analysis:</h5>
<ul>
    <li>Many stocks exhibited high volatility but failed to generate proportional returns, making them inefficient holdings in the portfolio. Investments that are highly volatile should ideally offer higher returns to compensate for the risk, but several assets in this portfolio did not meet that standard.</li>
    <li>IEP (Icahn Enterprises) and CVI (CVR Energy), the largest holdings, had negative risk-adjusted returns, reinforcing their role as underperforming, high-risk assets. Given that IEP is Carl Icahn’s own company and CVI is a subsidiary of IEP, this created an increased concentration risk—if one stock underperforms, it significantly affects the overall portfolio performance.</li>
    <li>CTRI had the worst performance in terms of risk-return tradeoff, as it had one of the highest volatilities but delivered negative returns, making it a strong candidate for reconsideration in the portfolio.</li>
    <li>The red dashed line represents the S&P 500 benchmark return, which many of the current holdings failed to surpass. This suggests that the portfolio could have achieved better returns with lower risk simply by investing in the benchmark instead of maintaining its existing stock selection.</li>
</ul>
<p>This analysis further validated our hypothesis that a shift in asset allocation was necessary. The overreliance on interconnected and underperforming stocks exposed the portfolio to unnecessary risks, limiting its potential for sustainable growth. A more diversified investment approach—incorporating assets with better risk-adjusted returns—would help mitigate these issues and enhance long-term performance.</p>

<h3>3. Portfolio Optimization: Constructing a High-Performance Strategy</h3>
<p>To improve risk-adjusted returns, we proposed a diversified portfolio strategy incorporating high-growth and international stocks.</p>

<h4>Recommended Portfolio Allocation by Ticker</h4>


<h5>1. New Stock Recommendations:</h5>
<ul>
    <li>BioNTech (BNTX) – Expands into Biotech & Healthcare.</li>
    <li>NextEra Energy (NEE) – Introduces Renewable Energy exposure.</li>
    <li>Snowflake (SNOW) & Block (SQ) – Positions the portfolio in high-growth Tech & Fintech.</li>
    <li>Tencent Holdings (TCEHY) – Adds International diversification.</li>
    <li>Booking Holdings (BKNG) – Captures growth in the Travel & Consumer sector.</li>
</ul>

<h5>2. Projected Impact of the Optimized Portfolio Strategy</h5>
<p>Implementing a diversified investment strategy using a combination of high-growth, sector-diverse, and international stocks provides several benefits. Here’s a deeper look at how this optimized allocation enhances the portfolio’s overall performance and risk management:</p>

<h6>Reduced Portfolio Volatility</h6>
<ul>
    <li>Lower Exposure to Single-Sector Risk – The previous portfolio was heavily concentrated in the Energy sector (75.45%), making it highly susceptible to market fluctuations in oil and gas. By diversifying into healthcare, technology, and consumer sectors, the portfolio becomes more resilient to sector-specific downturns.</li>
    <li>Balanced Risk-Return Tradeoff – Stocks like NextEra Energy (NEE) and Booking Holdings (BKNG) add stability and defensive characteristics, offsetting the volatility from higher-risk growth stocks like Snowflake (SNOW) and Block (SQ).</li>
    <li>International Diversification Reduces Systemic Risk – Tencent Holdings (TCEHY) adds exposure to global markets, particularly China’s growing tech sector, reducing the dependency on U.S. economic conditions.</li>
</ul>
<p><b>Expected Outcome:</b></p>
<ul>
    <li>Lower standard deviation (volatility) across the portfolio</li>
    <li>Better resilience against economic downturns</li>
    <li>More stable returns over different market cycles</li>
</ul>

<h6>Stronger Sector Diversification</h6>
<ul>
    <li>Broader Industry Representation – By adding biotech (BNTX), fintech (SQ), cloud computing (SNOW), and travel (BKNG), the portfolio reduces over-reliance on one industry’s performance.</li>
    <li>Exposure to High-Growth Markets – The previous portfolio was heavily weighted toward legacy energy stocks with declining growth trends. Our revised allocation positions the portfolio in sectors with long-term expansion potential, such as:
        <ul>
            <li>Biotech & Healthcare (BNTX) – Strong demand for innovative medical treatments and vaccines.</li>
            <li>Cloud Computing (SNOW) – Increasing corporate adoption of data-driven solutions.</li>
            <li>Renewable Energy (NEE) – The global shift toward sustainability and green energy.</li>
        </ul>
    </li>
    <li>Cyclical vs. Defensive Balance – Travel and consumer discretionary stocks like BKNG tend to perform well in economic booms, while healthcare (BNTX) and utilities (NEE) provide stability in downturns.</li>
</ul>
<p><b>Expected Outcome:</b></p>
<ul>
    <li>A well-rounded portfolio that performs across different economic cycles</li>
    <li>Hedge against sector-specific downturns</li>
    <li>Enhanced growth potential without excessive risk concentration</li>
</ul>

<h6>Balanced Risk-Reward Profile</h6>
<ul>
    <li>Higher Sharpe Ratio (Better Risk-Adjusted Returns) – The inclusion of growth-oriented but relatively stable stocks improves the portfolio’s risk-adjusted return, meaning higher returns per unit of risk taken.</li>
    <li>Mix of Value and Growth Investing – The original portfolio leaned heavily toward deep value investing, while the optimized version combines value stocks (BKNG, NEE) with growth stocks (SNOW, SQ, BNTX), balancing long-term appreciation with current stability.</li>
    <li>Improved Expected Return Distribution – By incorporating stocks with a strong historical return-to-risk ratio, the probability of extreme portfolio losses is reduced, making it more suitable for long-term compounding of wealth.</li>
</ul>
<p><b>Expected Outcome:</b></p>
<ul>
    <li>Higher probability of outperforming the S&P 500 benchmark over the long term</li>
    <li>Optimized balance between aggressive and defensive investment styles</li>
    <li>More sustainable, long-term growth with controlled downside risk</li>
</ul>

<h2>Key Takeaways: The Power of Business Analytics in Investment Strategy</h2>
<ul>
    <li><b>Data-Driven Decisions Lead to Smarter Investments</b> – Structured analytics can identify inefficiencies and enhance financial decision-making.</li>
    <li><b>Diversification is Key to Managing Risk</b> – A portfolio overly concentrated in one sector is highly vulnerable to market fluctuations.</li>
    <li><b>Visualization is a Game-Changer</b> – Python and Tableau helped us present complex findings in an impactful and easy-to-understand manner.</li>
</ul>

<h2>Conclusion: The Impact of This Project</h2>

<p>This project was a real-world application of business analytics in investment strategy, where we leveraged SQL, Python, and Tableau to analyze a $9.88 billion portfolio, identify inefficiencies, and propose a data-driven optimization strategy. By uncovering sector concentration risks, underperforming assets, and diversification opportunities, we demonstrated how data-driven decisions can enhance portfolio performance.</p>

<p>Our runner-up position in the competition was a testament to the strength of our analysis, technical execution, and strategic recommendations. This experience reinforced the power of business analytics in financial decision-making and the value of applying coding, data visualization, and statistical modeling to solve complex business challenges.</p>

<p>This project not only sharpened my technical and analytical skills but also deepened my understanding of how data can drive smarter, more strategic investment decisions. Moving forward, I’m excited to continue applying these skills to real-world challenges and making an impact through data-driven insights.</p>

</body>
</html>
