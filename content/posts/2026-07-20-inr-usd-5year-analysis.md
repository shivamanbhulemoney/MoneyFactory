---
title: "Indian Rupee vs US Dollar: 5-Year Exchange Rate Analysis (2021-2025)"
date: 2026-07-20T10:00:00Z
draft: false
tags: ["india", "forex", "usd", "inr", "economy", "investing"]
categories: ["Forex & Economy"]
featured_image: "/images/posts/inr-usd-chart.png"
description: "Interactive analysis of Indian Rupee depreciation against US Dollar over the last 5 years with HTML5 charts and key insights for investors."
author: "MoneyFactory Team"
---

# 🇮🇳 Indian Rupee vs 🇺🇸 US Dollar: 5-Year Exchange Rate Analysis

The Indian Rupee has been on a **depreciation journey** against the US Dollar over the past 5 years. Understanding this trend is crucial for investors, importers, exporters, and anyone dealing with foreign currency.

---

## 📊 Interactive 5-Year Exchange Rate Chart

&lt;div id="inr-usd-chart" style="width:100%;max-width:700px;margin:20px auto;font-family:system-ui,sans-serif;"&gt;
  &lt;h3 style="text-align:center;color:#1a1a2e;"&gt;🇮🇳 INR vs 🇺🇸 USD Exchange Rate (Last 5 Years)&lt;/h3&gt;
  &lt;canvas id="exchangeCanvas" width="700" height="400" style="background:#f8f9fa;border-radius:12px;box-shadow:0 4px 15px rgba(0,0,0,0.1);"&gt;&lt;/canvas&gt;
  &lt;div style="display:flex;justify-content:center;gap:20px;margin-top:15px;font-size:13px;"&gt;
    &lt;span style="display:flex;align-items:center;gap:5px;"&gt;&lt;span style="width:12px;height:12px;background:#ff6b35;border-radius:2px;display:inline-block;"&gt;&lt;/span&gt; INR per USD&lt;/span&gt;
    &lt;span style="display:flex;align-items:center;gap:5px;"&gt;&lt;span style="width:12px;height:12px;background:#00d4aa;border-radius:2px;display:inline-block;"&gt;&lt;/span&gt; Trend Line&lt;/span&gt;
  &lt;/div&gt;
  &lt;p style="text-align:center;font-size:12px;color:#666;margin-top:10px;"&gt;Data Source: World Bank / RBI | Approximate annual averages&lt;/p&gt;
&lt;/div&gt;

&lt;script&gt;
(function(){
  const canvas = document.getElementById('exchangeCanvas');
  const ctx = canvas.getContext('2d');
  const dpr = window.devicePixelRatio || 1;
  canvas.width = 700 * dpr;
  canvas.height = 400 * dpr;
  ctx.scale(dpr, dpr);
  canvas.style.width = '700px';
  canvas.style.height = '400px';

  const data = [
    {year:'2021', rate:73.9, change:'Baseline'},
    {year:'2022', rate:78.6, change:'+6.4%'},
    {year:'2023', rate:82.7, change:'+5.2%'},
    {year:'2024', rate:83.4, change:'+0.8%'},
    {year:'2025', rate:85.5, change:'+2.5%'}
  ];

  const padding = {top:40, right:40, bottom:60, left:60};
  const chartW = 700 - padding.left - padding.right;
  const chartH = 400 - padding.top - padding.bottom;
  const barW = chartW / data.length * 0.6;
  const maxRate = 90;
  const minRate = 70;

  ctx.fillStyle = '#f8f9fa';
  ctx.fillRect(0, 0, 700, 400);

  ctx.strokeStyle = '#e0e0e0';
  ctx.lineWidth = 1;
  for(let i=0; i&lt;=5; i++){
    const y = padding.top + (chartH/5)*i;
    ctx.beginPath();
    ctx.moveTo(padding.left, y);
    ctx.lineTo(padding.left+chartW, y);
    ctx.stroke();
    ctx.fillStyle = '#666';
    ctx.font = '12px sans-serif';
    ctx.textAlign = 'right';
    const val = Math.round(maxRate - (maxRate-minRate)/5*i);
    ctx.fillText('₹'+val, padding.left-10, y+4);
  }

  data.forEach((d, i) =&gt; {
    const x = padding.left + (chartW/data.length)*i + (chartW/data.length - barW)/2;
    const barH = ((d.rate - minRate)/(maxRate - minRate)) * chartH;
    const y = padding.top + chartH - barH;

    const grad = ctx.createLinearGradient(x, y, x, y+barH);
    grad.addColorStop(0, '#ff6b35');
    grad.addColorStop(1, '#ff8c5a');
    ctx.fillStyle = grad;
    ctx.fillRect(x, y, barW, barH);

    ctx.fillStyle = '#1a1a2e';
    ctx.font = 'bold 14px sans-serif';
    ctx.textAlign = 'center';
    ctx.fillText('₹'+d.rate, x + barW/2, y - 8);

    if(i &gt; 0){
      ctx.fillStyle = '#e74c3c';
      ctx.font = '11px sans-serif';
      ctx.fillText(d.change, x + barW/2, y - 22);
    }

    ctx.fillStyle = '#333';
    ctx.font = '13px sans-serif';
    ctx.fillText(d.year, x + barW/2, padding.top + chartH + 20);
  });

  ctx.strokeStyle = '#00d4aa';
  ctx.lineWidth = 3;
  ctx.beginPath();
  data.forEach((d, i) =&gt; {
    const x = padding.left + (chartW/data.length)*i + (chartW/data.length)/2;
    const barH = ((d.rate - minRate)/(maxRate - minRate)) * chartH;
    const y = padding.top + chartH - barH;
    if(i===0) ctx.moveTo(x, y);
    else ctx.lineTo(x, y);
  });
  ctx.stroke();

  ctx.fillStyle = '#1a1a2e';
  ctx.font = 'bold 16px sans-serif';
  ctx.textAlign = 'center';
  ctx.fillText('Indian Rupee Depreciation Against US Dollar', 350, 25);

  ctx.save();
  ctx.translate(15, 200);
  ctx.rotate(-Math.PI/2);
  ctx.fillStyle = '#666';
  ctx.font = '12px sans-serif';
  ctx.textAlign = 'center';
  ctx.fillText('INR per 1 USD', 0, 0);
  ctx.restore();
})();
&lt;/script&gt;

---

## 📈 Key Statistics

| Year | INR per USD | YoY Change | Impact |
|------|-------------|------------|--------|
| **2021** | ₹73.9 | Baseline | Pre-pandemic recovery |
| **2022** | ₹78.6 | **+6.4%** | Fed rate hikes begin |
| **2023** | ₹82.7 | **+5.2%** | Strong dollar dominance |
| **2024** | ₹83.4 | **+0.8%** | RBI intervention |
| **2025** | ₹85.5 | **+2.5%** | Geopolitical tensions |

**Total Depreciation (2021-2025): ~15.7%**

---

## 🔍 Why is INR Depreciating?

### 1. **US Federal Reserve Rate Hikes**
- Higher US interest rates attract global capital
- Foreign investors pull money from India
- Increased demand for USD, weaker INR

### 2. **Trade Deficit**
- India imports more than it exports
- Oil imports (priced in USD) put pressure on INR
- Current account deficit widens

### 3. **Global Risk Sentiment**
- During global uncertainty, investors flee to "safe haven" USD
- Emerging market currencies like INR suffer

### 4. **RBI's Managed Float**
- Reserve Bank of India intervenes to prevent sharp falls
- Uses forex reserves to stabilize INR
- But cannot fully stop depreciation

---

## 💡 What This Means for You

### For Investors:
- **US Stock Investors**: Your returns in INR terms are boosted by depreciation
- **Indian Stock Investors**: FII outflows can cause market volatility
- **Gold Investors**: Gold priced in USD becomes more expensive in INR

### For Travelers:
- **Studying Abroad**: Education in US/UK becomes 15% more expensive
- **Foreign Travel**: Your trips cost more in INR terms

### For Businesses:
- **Exporters**: Benefit from weaker INR (products cheaper for foreigners)
- **Importers**: Hurts by weaker INR (raw materials cost more)

---

## 🎯 How to Protect Against INR Depreciation

| Strategy | How It Works | Risk Level |
|----------|--------------|------------|
| **USD ETFs/Mutual Funds** | Invest in US markets directly | Medium |
| **Gold** | Traditional hedge against currency risk | Low-Medium |
| **Export-Oriented Stocks** | Companies that earn in USD | Medium |
| **Forex Trading** | Direct USD/INR trading | High |
| **NRI Deposits** | If you have USD income, keep it in USD | Low |

---

## 🔮 Future Outlook

**Analysts predict:**
- INR may touch **₹87-90 per USD** by end of 2026
- Much depends on:
  - US Fed policy decisions
  - India's economic growth
  - Global oil prices
  - Geopolitical stability

**Key Levels to Watch:**
- **Support**: ₹82-83 (RBI defense zone)
- **Resistance**: ₹88-90 (psychological barrier)

---

## 📚 Sources

- [World Bank - Official Exchange Rate Data](https://data.worldbank.org/indicator/PA.NUS.FCRF)
- [Reserve Bank of India - Exchange Rates](https://www.rbi.org.in/Scripts/ReferenceRateArchive.aspx)
- [Investopedia - Currency Depreciation](https://www.investopedia.com/terms/c/currency-depreciation.asp)

---

**Disclaimer:** *This analysis is for educational purposes only. Exchange rates are subject to market risks. Please consult a financial advisor before making investment decisions.*

---

**Want more forex insights?** Subscribe to our newsletter for weekly currency updates! 🚀
