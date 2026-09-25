# LeadFlow AI: Multi-Channel Lead Outreach

Multi-channel n8n automation integrating WhatsApp Cloud API, SendGrid, Calendly, and CRM for real-estate lead management.

**Project Type:** Self-Directed Project / Portfolio Case Study  
**Portfolio:** [qasimbuilds.online](https://qasimbuilds.online)

## 📋 Overview
A complex, 7-workflow automation system built entirely in n8n. LeadFlow AI captures incoming leads, qualifies them via AI, and executes a multi-channel outreach sequence (Email + WhatsApp) until a reply is detected or a meeting is booked.

## 🚨 The Problem
* Relying on native CRM automation was too limiting for complex, multi-channel logic.
* High drop-off rates because leads were not contacted quickly on their preferred platforms (WhatsApp/Email).
* Sales reps had to manually stop outreach sequences when a lead replied or booked a meeting, leading to awkward duplicate messages.

## 💡 The Solution
* **Omnichannel Outreach:** Built n8n workflows that trigger personalized WhatsApp messages and SendGrid emails based on the lead's time zone and data.
* **Smart Stop Conditions:** Integrated Calendly webhooks and reply-detection logic to instantly halt automated outreach the moment a prospect engages.
* **CRM Synchronization:** Pushed all engagement data, message statuses, and meeting links back into the centralized CRM to maintain a single source of truth.

## 🏗️ Architecture & Workflow
1. **Ingestion (Webhook):** Catch hook receives lead data from external ad forms.
2. **AI Enrichment:** OpenAI API formats and extracts key intent signals.
3. **Outreach Engine (n8n):** 
   - Day 1: WhatsApp Introduction (WhatsApp Cloud API)
   - Day 2: Follow-up Email (SendGrid API)
   - Day 3: Final WhatsApp ping.
4. **Listener / Stop Logic:** Webhooks listen for Calendly `invitee.created` events. If triggered, the lead is removed from the active sequence and marked as "Meeting Booked" in the CRM.

## 🛠️ Key Technologies
* n8n (Workflow Automation)
* REST APIs & Webhooks
* WhatsApp Cloud API
* SendGrid API
* Calendly Webhooks
* OpenAI API

## 📈 What I Demonstrated
* Architectural design of decoupled automation systems using n8n.
* Handling API authentication, rate limits, and JSON data parsing.
* Building stateful workflows that can "wait" and branch based on external webhook events.
