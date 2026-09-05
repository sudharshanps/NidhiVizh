<p align=“center”>   <strong>Beyond Alerts. Into Evidence.</strong><br/>
  Evidence-Driven Transaction Risk Investigation Assistant for Banking
</p> <p align=“center”>   <a
href=“https://github.com/sudharshanps/NidhiVizh”>   <img
src=“https://img.shields.io/badge/Track-PS06-0072CE?style=for-the-badge”
alt=“PS06”/>   </a>   <img
src=“https://img.shields.io/badge/AI-Google%20Gemini-FFC700?style=for-the-badge”
alt=“Google Gemini”/>   <img
src=“https://img.shields.io/badge/Backend-FastAPI-00A3E0?style=for-the-badge”
alt=“FastAPI”/>   <img
src=“https://img.shields.io/badge/Frontend-React-002B49?style=for-the-badge”
alt=“React”/> </p>

  NidhiVizh helps investigators understand unusual transaction activity
  without turning the workflow into a black-box fraud detector.

------------------------------------------------------------------------

🎬 Animated Product Journey

Raw Transactions → Risk Signals → Customer Context → Connected Activity
→ Traceable Evidence → Human Decision
  The animation mirrors the core design: deterministic analysis finds
  measurable signals, grounded AI explains verified evidence, and the
  investigator keeps the final decision.

------------------------------------------------------------------------

⚡ Investigation Flow

    flowchart LR
        A["Raw Transactions"] --> B["Deterministic Risk Engine"]
        B --> C["Customer Behavioral Baseline"]
        C --> D["Related Activity + Clusters"]
        D --> E["Evidence Chain"]
        E --> F["Gemini AI Investigator"]
        F --> G["Human Decision"]

        B -. "R01–R05" .-> E
        C -. "Counter-Evidence" .-> E
        E -. "Observed / Inferred / Unknown" .-> F

🖼️ Project Screenshots

Place your actual screenshots in docs/screenshots/.

Investigation Command Center

<img src=“./docs/screenshots/dashboard.png” alt=“NidhiVizh Dashboard”
width=“100%”/>

Transaction Risk Investigation

<img src=“./docs/screenshots/investigation.png” alt=“NidhiVizh
Investigation Workspace” width=“100%”/>

AI Investigator & Evidence

<img src=“./docs/screenshots/ai-investigator.png” alt=“NidhiVizh AI
Investigator” width=“100%”/>

Relationship Graph

<img src=“./docs/screenshots/relationship-graph.png” alt=“NidhiVizh
Relationship Graph” width=“100%”/>

Customer Behavioral Fingerprint

<img src=“./docs/screenshots/customer-baseline.png” alt=“NidhiVizh
Customer Baseline” width=“100%”/>

------------------------------------------------------------------------

🎯 Problem

Bank investigators may need to review months of transaction history to
understand whether unusual activity deserves attention. A single large
transaction does not automatically mean suspicious behavior.
Investigators need context: the customer’s normal transaction pattern,
payee history, transaction timing, bursts, related activity, and
available evidence. NidhiVizh turns raw transaction history into a
structured investigation workspace. It detects measurable risk signals,
compares them against the customer’s historical behavior, connects
related transactions, traces findings to source data, and provides
grounded Gemini-powered investigation assistance. NidhiVizh does not
confirm fraud. The investigator makes the final decision.

------------------------------------------------------------------------

✨ Key Features

  -----------------------------------------------------------------------
  CapabilityNidhiVizh      
  ------------------------ ----------------------------------------------
  🧭 Investigation Command Prioritized investigation queue
  Center                   

  📊 Behavioral Baseline   Customer-specific transaction fingerprint

  ⚠️ Deterministic Risk    Explainable rule-based signals
  Rules                    

  🧮 Investigation         Transparent score with rule contributions
  Priority Score           

  🔗 Relationship Graph    Customer → Transaction → Payee → Rule →
                           Cluster

  🧩 Risk Clusters         Groups connected transaction activity

  🕐 Timeline Intelligence Chronological activity replay

  🔍 Evidence Chain        Finding → Rule → Transaction → Baseline →
                           Source

  ⚖️ Counter-Evidence      Context that may reduce concern

  🧠 AI Investigator       Gemini summaries, questions and next checks

  👀 Observed / Inferred / Clear separation of fact, interpretation and
  Unknown                  missing data

  📚 Local RAG             Local retrieval with gemini-embedding-001 +
                           FAISS

  📝 Investigator          Notes, checklists, status and decisions
  Workspace                

  🧾 Audit Trail           Investigation activity history

  📄 Reports               Investigation briefs and exports

  🛡️ Safe Fallback         Deterministic analysis remains available if AI
                           is unavailable

  🧪 Demo Scenarios        Normal, high-signal and ambiguous cases
  -----------------------------------------------------------------------

------------------------------------------------------------------------

🎞️ Risk Signal Motion

R01 LARGE TRANSFER  →  R02 NEW PAYEE  →  R03 ODD HOURS  → 
R04 BEHAVIOR DEVIATION  →  R05 RAPID BURST

  The visual is intentionally a journey rather than a “fraud meter”:
  NidhiVizh prioritizes investigation and evidence, not a black-box
  fraud verdict.

------------------------------------------------------------------------

🔬 Deterministic Risk Rules

R01 — Unusually Large Transfer

Detects a transaction that is significantly larger than the customer’s
established behavior.

R02 — New Payee Burst

Detects rapid activity involving a newly observed or recently introduced
payee.

R03 — Odd-Hours Activity

Highlights activity outside the customer’s normal transaction-time
window.

R04 — Behavioral Deviation

Measures how current activity differs from the customer’s own historical
pattern.

R05 — Rapid Transaction Burst

Detects multiple transactions occurring within a short time window.

  Important: The deterministic engine calculates the measurable signals.
  Gemini explains verified findings; it does not replace the rule
  engine.

------------------------------------------------------------------------

🧮 Explainable Investigation Priority

NidhiVizh does not expose an unexplained “fraud probability”. Instead,
investigators can inspect a score breakdown:

    Investigation Priority Score
            │
            ├── R01 Large Transfer          +20
            ├── R02 New Payee               +25
            ├── R03 Odd Hours               +15
            ├── R04 Behavior Deviation      +12
            ├── R05 Rapid Burst             +10
            │
            └── Context / Counter-Evidence   -8
                                  ─────────────
                                      Final: 74

The actual values are calculated by the application’s deterministic
logic.

------------------------------------------------------------------------

⚖️ Counter-Evidence

One of NidhiVizh’s key ideas:

  Do not only search for evidence that supports an alert. Search for
  evidence that explains it.

Example:

    Signal:
    ₹98,000 transfer

    Supporting Evidence:
    Amount is much larger than the customer's typical transfer.

    Counter-Evidence:
    Similar high-value transfers are already present
    in the customer's historical activity.

    Result:
    Historical context can reduce investigation priority.

This helps investigators distinguish between genuinely unusual activity
and activity that is unusual only at first glance.

------------------------------------------------------------------------

🧠 AI Investigator

Gemini receives verified and relevant investigation context rather than
unnecessary raw data.

    Raw Transactions
          ↓
    Deterministic Analysis
          ↓
    Relevant Signals
          ↓
    Customer Baseline
          ↓
    Related Transactions
          ↓
    Evidence / RAG
          ↓
    Gemini Investigation Assistance

The investigator can ask NidhiVizh to:

-   Summarize a case
-   Explain why it needs attention
-   Compare current activity with the customer baseline
-   Find related transactions
-   Generate investigation questions
-   Suggest the first checks to perform
-   Explain counter-evidence
-   Identify missing information

Grounding

AI output must map back to real source data. Gemini must not invent:

-   transaction IDs
-   amounts
-   customers
-   payees
-   rules
-   evidence
-   source records

------------------------------------------------------------------------

👀 Observed / Inferred / Unknown

Each AI investigation brief separates information into three layers.

Observed

Facts directly present in the provided transaction data.

Inferred

Interpretations derived from verified observations and deterministic
calculations.

Unknown

Information that is not available in the supplied dataset. Example:

    OBSERVED
    • Transaction occurred at 02:41 AM
    • Payee was newly observed
    • Amount was ₹40,000

    INFERRED
    • Activity differs from the customer's established pattern

    UNKNOWN
    • Whether the customer authorized the transaction
    • Purpose of the payment
    • Whether the customer recognizes the payee

------------------------------------------------------------------------

🔗 Evidence Traceability

Every important finding should be traceable through:

    Finding
       ↓
    Risk Rule
       ↓
    Transaction
       ↓
    Customer Baseline
       ↓
    Source Dataset

A transaction citation should point back to a real transaction ID and
source record.

------------------------------------------------------------------------

🕸️ Relationship Graph

NidhiVizh connects:

    Customer
       │
       ├── Transaction
       │      ├── Payee
       │      ├── Channel
       │      ├── Location
       │      ├── Risk Rule
       │      └── Risk Cluster
       │
       └── Investigation Case

The graph helps investigators inspect surrounding context rather than
viewing transactions in isolation.

------------------------------------------------------------------------

🕐 Timeline Intelligence

The timeline highlights:

-   Normal activity
-   New payee introduction
-   First unusual transaction
-   Repeated transactions
-   Risk-rule triggers
-   Cluster formation
-   Case creation
-   Investigator review
-   Final decision

Investigators can switch between focused windows such as 7 days, 30
days, 90 days, or all history.

------------------------------------------------------------------------

📚 Local RAG

NidhiVizh supports a local knowledge-retrieval workflow.

    Knowledge Documents
           ↓
    Chunking
           ↓
    Gemini Embeddings
           ↓
    Local FAISS Index
           ↓
    Relevant Evidence
           ↓
    Grounded Gemini Response

Embedding model: gemini-embedding-001 The design keeps retrieval local
instead of depending on a hosted vector database.

------------------------------------------------------------------------

🧑‍💼 Human-in-the-Loop Decision

NidhiVizh supports investigator decisions such as:

-   Reviewed — No Further Action
-   Additional Information Required
-   Escalate for Investigation
-   Monitoring Recommended

There is intentionally no “Confirm Fraud” action. The system assists the
investigator; it does not replace the investigator.

------------------------------------------------------------------------

🧪 Demo Scenarios

1. Normal Customer

Activity remains consistent with the historical baseline.

2. Large Transfer

A high-value transaction is far above typical behavior.

3. New Payee Burst

Several payments occur rapidly to a newly observed payee.

4. Odd-Hours Activity

Transactions occur outside the customer’s established activity window.

5. Ambiguous / Historically Explained

A large transaction looks unusual initially, but similar historical
behavior provides counter-context.

6. Multi-Signal Investigation

Multiple risk signals occur together inside a connected transaction
cluster.

------------------------------------------------------------------------

🏗️ Architecture

    flowchart TB
        UI["React + Vite UI<br/>Dashboard • Cases • Evidence • AI • Reports"]
        API["FastAPI Backend<br/>REST API + Orchestration"]

        subgraph CORE["Deterministic Investigation Core"]
          RULES["R01–R05 Risk Rules"]
          BASE["Customer Behavioral Baseline"]
          CLUSTER["Risk Clusters + Relationships"]
          SCORE["Explainable Priority Score"]
          EVID["Evidence + Audit Services"]
        end

        subgraph AI["Grounded AI Layer"]
          RETR["Local RAG<br/>gemini-embedding-001 + FAISS"]
          GEM["Google Gemini<br/>Summaries • Questions • Next Checks"]
        end

        DATA["SQLite + Synthetic CSV Data"]

        UI --> API
        API --> RULES
        API --> BASE
        API --> CLUSTER
        API --> SCORE
        API --> EVID
        DATA --> RULES
        DATA --> BASE
        DATA --> CLUSTER
        EVID --> RETR
        RETR --> GEM
        RULES --> GEM
        BASE --> GEM
        CLUSTER --> GEM
        GEM --> UI

GitHub renders Mermaid diagrams directly inside Markdown, so the
architecture stays editable as text rather than becoming a flat
screenshot. citeturn0search0turn0search6

🛠️ Technology Stack

Frontend

-   React
-   TypeScript
-   Vite
-   Tailwind CSS
-   Recharts
-   React Flow
-   Lucide

Backend

-   Python
-   FastAPI
-   SQLite

AI

-   Google Gemini API
-   gemini-embedding-001
-   Structured, grounded AI responses

Retrieval

-   Local FAISS vector search
-   Local knowledge-base documents

Data

-   Synthetic customers
-   Synthetic transactions
-   Synthetic payees
-   Deterministic risk-rule configuration

------------------------------------------------------------------------

📁 Suggested Repository Structure

    NidhiVizh/
    ├── README.md
    ├── app.py
    ├── requirements.txt
    ├── package.json
    ├── index.html
    ├── public/
    ├── src/
    ├── docs/
    │   ├── demo.gif
    │   └── screenshots/
    │       ├── dashboard.png
    │       ├── investigation.png
    │       ├── ai-investigator.png
    │       ├── relationship-graph.png
    │       └── customer-baseline.png
    ├── data/
    │   ├── customers.csv
    │   ├── transactions.csv
    │   ├── payees.csv
    │   └── risk_rules.csv
    └── .env.example

  Keep API keys and secrets out of GitHub. Commit only placeholder
  variable names in .env.example.

------------------------------------------------------------------------

⚙️ Setup

Clone:

    git clone https://github.com/sudharshanps/NidhiVizh.git
    cd NidhiVizh

Install Python dependencies:

    pip install -r requirements.txt

Install frontend dependencies:

    npm install

Configure environment variables using the project’s .env.example.

------------------------------------------------------------------------

▶️ Run

Hackathon-compatible entry point:

    python app.py

Expected application address:

    http://localhost:8000

Use the project’s local development instructions if a separate Vite
development server is required.

------------------------------------------------------------------------

🔐 Reliability & Safety

NidhiVizh is designed around these principles:

-   Human-in-the-loop: AI does not make the final fraud decision.
-   Deterministic core: risk rules, baseline statistics and priority
    calculations remain outside the LLM.
-   Traceable evidence: findings reference source transactions.
-   Counter-evidence: contextual evidence is surfaced alongside
    supporting evidence.
-   Explicit unknowns: missing information is shown instead of
    fabricated.
-   AI fallback: core deterministic analysis remains available when
    Gemini is unavailable.
-   Untrusted text handling: descriptions and documents are treated as
    data, not instructions.
-   Synthetic data: demo datasets contain synthetic records.

------------------------------------------------------------------------

🎨 Design System

  TokenValue           
  -------------------- ---------
  Primary Top Header   #00A3E0
  Accent               #FFC700
  Primary Action       #0072CE
  Dark Header          #002B49
  Background           #F4F6F8
  Text                 #1E1E1E

------------------------------------------------------------------------

🏆 Hackathon

Track: PS06 — Banking: Transaction Risk Investigation Assistant Project:
NidhiVizh Tagline: Beyond Alerts. Into Evidence. NidhiVizh is built to
turn transaction-risk alerts into traceable evidence and investigation
context while keeping final judgement with the human investigator.

------------------------------------------------------------------------

🎥 3-Minute Demo

Raw Data → Alert → Evidence → AI Brief → Investigator Decision

  For the final submission, replace the placeholder below with the real
  3-minute demo video.

------------------------------------------------------------------------

📹 Demo Video

Add your final demo link here: Watch the NidhiVizh Demo Replace # with
your YouTube demo URL.

------------------------------------------------------------------------

🚀 Core Idea

  Step   What NidhiVizh does
  ------ ------------------------------------------------------
  01     Ingest months of transaction history
  02     Detect measurable risk signals
  03     Compare activity against the customer’s own baseline
  04     Connect transactions, payees, clusters and rules
  05     Trace findings back to source evidence
  06     Give Gemini only verified investigation context
  07     Present the investigator with an explainable case
  08     Keep the final decision human

  NidhiVizh

  Beyond Alerts. Into Evidence.
