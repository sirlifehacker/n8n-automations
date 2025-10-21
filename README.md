# 🔍 LinkedIn Jobs Scraper + Decision Maker Research (n8n Workflow)

This automation discovers **new job postings on LinkedIn**, identifies **decision-makers at hiring companies**, and generates **psychographic profiles + cold outreach hooks** using GPT and Apollo enrichment.  
Built entirely inside **n8n**.

Full video tutorial walkthrough here: https://youtu.be/DC8ftiBiP2c

---

## ⚙️ Overview

**Workflow Purpose:**
1. Scrape recent LinkedIn job postings with [Apify’s LinkedIn Job Scraper](https://apify.com/cheap_scraper/linkedin-job-scraper).
2. Store job data in Notion (company, role, location, date, salary).
3. Look up the company in Apollo to find **key decision-makers** (HR, Talent, Ops, etc.).
4. Enrich and rank those people by **relevance score** (title, seniority, and proximity).
5. Use OpenAI (`gpt-5` or similar) to create a **psychological + communication profile** for outreach.
6. Save all insights back into Notion CRM or a Google Sheet.

---

## 🧩 Required API Integrations

Before importing, you’ll need to add your own credentials for each of the following:

| Integration | Use Case | Credential Name |
|--------------|-----------|-----------------|
| **Apify** | LinkedIn Job Scraper & LinkedIn Profile Scraper | `Apify API key` |
| **Apollo.io** | Organization search + people enrichment | `Apollo API key` |
| **OpenAI** | GPT-powered psychographic analysis | `OpenAI API key` |
| **Notion** | Store jobs, leads, and AI insights | `Notion integration token` |
| *(Optional)* Google Sheets / Airtable | Log or share output | your OAuth2 credentials |

➡️ Replace the placeholder API keys and Notion database IDs inside the workflow before running.

---


---

## 🧩 Setup Instructions

1. **Download the JSON file**  
   `Linkedin Jobs Scraping + Decision Maker Research.json`

2. **Import into n8n**  
   - In your n8n dashboard → *Workflows* → *Import from File* → select the JSON.

3. **Add credentials**  
   - Apify → `https://apify.com/account/integrations`  
   - Apollo → `https://app.apollo.io/#/settings/api`  
   - OpenAI → `https://platform.openai.com/api-keys`  
   - Notion → `https://www.notion.so/my-integrations`

4. **Edit placeholders in workflow**  
   - Replace `[add your API key]` and `[go to api -> api endpoints in apify]` nodes with your credentials.  
   - Update Notion database IDs to match your own “Jobs” and “Lead CRM” databases.  

5. **Run manually or schedule with Cron**  
   - Start manually (click *Execute Workflow*)  
   - Or schedule it to check LinkedIn daily for new postings.

---

## 🧱 Output Example

Your Notion or Google Sheet will include:

| Company | Job Title | Location | Decision Maker | Email | Relevance | LinkedIn | Psychographic Notes |
|----------|------------|----------|----------------|--------|------------|-----------|----------------------|
| XYZ Construction | Superintendent | Austin, TX | Jane Doe | jane@xyz.com | 9.3 | linkedin.com/in/janedoe | Prefers logic-driven communication, results-focused mindset... |

---

## 🧠 AI Research Agent Prompt Summary
The built-in GPT agent analyzes:
- Job titles, education, tone, and achievements.  
- Predicts motivators and communication preferences.  
- Suggests *cold email hooks* tailored to personality.  

Output is formatted in Markdown and saved automatically to Notion.

---

## 🧰 Customization Tips
- Swap `gpt-5` model for `gpt-4o-mini` or `claude-3.5-sonnet` via OpenRouter.
- Adjust keywords inside the **Filter Decision Makers** code node to target specific roles.
- Modify Apify’s LinkedIn search URL to scrape other niches (e.g., “civil engineer,” “AI researcher”).

---

## ⚠️ Notes
- The Apify free tier may limit the number of job listings per run.
- Keep Apollo requests under 10k/day to avoid API throttling.
- Each run processes ~50–100 job postings efficiently.

---

## 🌍 Credits
Built by **Julian Reeves – Founder of Chosen Labs**  
Join the **AI Accelerator Community** → [Skool: The AI Entrepreneur Circle]([https://www.skool.com/the-ai-entrepreneur-circle](https://www.skool.com/the-ai-entrepreneur-circle-5658/about?ref=d0277aefba6d45ac9438d6e9355ba9af))

---

⭐ *If this workflow saves you time, star this repo and tag @sirlifehacker on Reddit to share your results.*


