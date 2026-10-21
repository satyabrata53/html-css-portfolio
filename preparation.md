# YottaFlex AI Forward Deployed Engineer --- Interview Preparation

**Candidate:** Satyabrata Jena\
**Round:** Round 2 --- AI Screening (video Q&A)\
**Source documents:** YottaFlex AI screening email and the resume
provided for this application\
**Purpose:** Prepare to explain your real experience clearly, reason
through unfamiliar problems, and connect technical decisions to
user/business outcomes.

> **Important:** The email says the assessment has 10 questions, takes
> about 20 minutes, gives you 10 seconds to gather your thoughts, and
> allows up to 90 seconds per recorded answer. It describes the assessed
> areas as self-introduction, design thinking, communication, analytical
> thinking, and technical fundamentals. It does not disclose the exact
> questions. The practice questions below are preparation prompts, not
> claims about the actual test.

------------------------------------------------------------------------

## 1. Understand the interview format

-   **Deadline in the email:** Thursday, October 22, 2026 at 1:00 PM
    IST.
-   **Format:** Video Q&A; each question is read aloud.
-   **Thinking time:** 10 seconds per question.
-   **Answer limit:** Up to 90 seconds.
-   **Attempt policy:** The email says the link works once and there are
    no retakes.
-   **Technical setup:** Use Chrome or Edge; allow camera and
    microphone; keep the webcam on; use a quiet, well-lit place and
    stable internet.
-   **Technical issues:** The email says to contact
    `contactus@yottaflex.ai`, including your name and what happened.

Because the link is single-use, do not open it until you have tested
your setup and are ready to begin.

## 2. Your candidate story

### Your strongest positioning

You are a backend and AI systems developer with hands-on experience
building systems that connect **audio or user input → processing →
model/decision logic → structured output → monitoring/storage**. Your
resume gives you three particularly relevant stories:

1.  **Production QC Agent at Telezer Technologies:** VICIdial
    recordings, Faster-Whisper transcription, local LLM-based scoring,
    call insights, Streamlit monitoring, SQLite storage, and on-premise
    Linux deployment.
2.  **Real-time conversational AI pipeline:** LiveKit WebRTC SFU
    integrated with Asterisk/VICIdial over SIP for low-latency voice
    interactions with LLM-backed agents.
3.  **Custom local ReAct agent:** Python and Ollama, custom multi-step
    loop, tool calling, memory retrieval, structured JSON actions,
    retries, fallbacks, and termination conditions.

Your MedGuard AI project is another useful design story: deterministic,
database-driven clinical safety checks are applied before AI response
generation, with a hybrid entity-resolution layer and fail-safe
workflows.

### A concise self-introduction (practice, do not recite mechanically)

"Hi, I'm Satyabrata Jena, a Computer Science Engineering graduate from
2025. I work across backend development and applied AI systems. At
Telezer Technologies, I worked on a production QC agent that retrieves
BPO call recordings, transcribes them with Faster-Whisper, uses a local
LLM to evaluate calls, and presents insights through a monitoring
dashboard. I also worked on real-time voice-agent infrastructure
involving LiveKit, Asterisk, VICIdial, and SIP. Separately, I built a
custom local ReAct agent with Python and Ollama, including tool calling,
memory, retries, and structured actions. I'm interested in the Forward
Deployed Engineer role because I enjoy understanding a practical
problem, building a reliable technical solution, and explaining the
trade-offs clearly."

**Personalize before the interview:** Be precise about what you
personally implemented versus what your team built. If asked about an
exact metric, do not invent one; explain how you would measure it.

## 3. Answer structure for 90-second responses

Use this four-part structure for most questions:

1.  **Direct answer (10--15 sec):** State your approach or conclusion.
2.  **Concrete example (30--40 sec):** Use a project from your resume.
3.  **Trade-off / reasoning (20--25 sec):** Explain why you chose that
    approach and what you considered.
4.  **Outcome / next step (10--15 sec):** Give the result, or say what
    you would measure or improve.

For project and behavioral questions, use **STAR**: - **Situation:**
What was the problem? - **Task:** What needed to be achieved? -
**Action:** What did you do and why? - **Result:** What changed, what
was learned, or how would success be measured?

For technical design questions, use **Requirements → Architecture →
Failure cases → Evaluation**.

### The 10-second thinking routine

When the question appears: - **Seconds 1--2:** Identify the question
type: experience, design, debugging, or fundamentals. - **Seconds
3--5:** Pick one relevant example or principle. - **Seconds 6--8:**
Choose two or three points to explain. - **Seconds 9--10:** Decide your
opening sentence.

If you blank, say: "I'd break this into three parts..." and reason
through the problem. The email explicitly says they care about how you
think, not just polished delivery.

------------------------------------------------------------------------

## 4. Project deep dives

Prepare each project at three levels: a 20-second summary, a
60--90-second explanation, and a deeper technical follow-up.

### A. Production QC Agent --- highest-priority project

**Resume-supported flow**

`VICIdial recording → Faster-Whisper STT → local LLM evaluation → call scores and insights → SQLite storage / Streamlit monitoring`

**Explain the problem** Manual quality review of BPO calls can be slow
and difficult to scale. The system helps evaluate calls consistently and
highlight missed opportunities.

**Explain the architecture** - Fetch recordings from VICIdial. -
Transcribe audio using Faster-Whisper. - Pass transcript/context to a
locally hosted LLM for evaluation. - Produce scores and per-call
insights. - Store transcripts and scores in SQLite. - Present monitoring
information through Streamlit. - Deploy on an on-premise Linux server.

**Be ready to discuss** - Why separate transcription from evaluation? -
What happens when transcription is incomplete or noisy? - How do you
make LLM outputs structured and consistent? - How would you prevent
fabricated findings? - How would you evaluate whether scores match human
reviewers? - How would you handle failed jobs, duplicate recordings,
retries, and logs? - Why local inference/on-premise deployment, and what
trade-offs does it create? - What would you monitor: processing
failures, latency, transcription quality, scoring agreement, and cost
per call?

**Honest result statement:** Your resume says the system is live and
processing real client calls. Do not add unverified throughput,
accuracy, or time-saving percentages. If you know real figures, prepare
them; otherwise explain the metrics you would collect.

**Sample answer: "Tell me about a system you built."**

"One project I'd highlight is a production QC agent for BPO calls. The
problem was to make call evaluation more scalable and produce useful
feedback from recordings. The pipeline fetches recordings from VICIdial,
transcribes them with Faster-Whisper, and sends the transcript through a
locally run LLM evaluation workflow to score agent performance and
identify missed opportunities. I also worked with SQLite for transcript
and score storage and Streamlit for monitoring, and the system was
deployed on an on-premise Linux server. The main design consideration is
that an LLM score should not be treated as automatically correct, so I'd
evaluate it against human-reviewed examples, use a consistent rubric and
structured output, and track failures and disagreement. The system is
live and processes real client calls. I would measure quality through
reviewer agreement, processing latency, failure rate, and the usefulness
of the generated insights."

Adapt the answer to your exact contribution and be prepared to explain
the components you personally worked on.

### B. Real-time conversational voice pipeline

**Resume-supported components:** LiveKit WebRTC SFU, Asterisk/VICIdial,
SIP, LLM-backed agents, and low-latency voice interactions.

**Explain the flow at a high level**

`Caller / telephony → SIP/Asterisk integration → real-time media handling → speech recognition → LLM response → text-to-speech → audio returned to caller`

Treat this as a conceptual explanation of a typical pipeline;
distinguish it from the exact components and configuration you
personally implemented.

**Concepts to revise** - **WebRTC:** Real-time audio/video communication
in browsers and applications. - **SIP:** Signaling used to establish,
manage, and end communication sessions. - **Asterisk:** Telephony/PBX
platform that handles call routing and telephony integration. -
**VICIdial:** Contact-center dialer/call-center platform built around
telephony infrastructure. - **LiveKit SFU:** Selective Forwarding Unit
that routes media streams between participants. - **STT:**
Speech-to-text transcription. - **LLM:** Generates a response based on
the conversation and instructions. - **TTS:** Converts response text
into speech.

**Likely follow-ups** - Where can latency accumulate? - How would you
measure end-to-end response latency? - How do you handle silence,
interruptions, noisy audio, or a slow LLM? - What happens if STT, LLM,
or TTS fails? - How would you trace a call across multiple services? -
Why separate telephony, media transport, inference, and application
logic?

A strong answer mentions measuring each stage separately, streaming
where appropriate, timeouts, cancellation of stale responses, fallbacks,
and correlation IDs/logs---while making clear which mechanisms you
actually implemented and which you propose.

### C. Answering Machine Detection (AMD)

Your resume says you built an AMD system using Turbo Whisper and an LLM,
connected to the Asterisk pipeline through AGI (`amd.py`), to replace
heuristic-based detection with AI-driven audio classification.

Prepare to explain: - The classification problem: human, answering
machine, or uncertain/other, depending on the system's labels. - Why
audio timing, pauses, greetings, and transcription can provide
signals. - Why an LLM-based decision can be flexible but may add latency
and variability. - The cost of false positives and false negatives. -
How to evaluate using labeled recordings, a confusion matrix, precision,
recall, and latency. - How the Asterisk Gateway Interface (AGI) connects
application logic to an Asterisk call flow.

Do not claim a specific accuracy improvement unless you have measured
data.

### D. Custom local ReAct AI agent

**Resume-supported features:** Python, Ollama, custom agent loop, tool
calling, memory retrieval, JSON-based actions, retry/fallback handling,
and loop termination.

**Explain ReAct simply:** The agent alternates between reasoning about
what to do and taking an action through a tool, then uses the
observation to decide the next step. In production, keep tool execution
constrained and validate actions rather than trusting free-form model
text.

**Be ready to explain** - How the agent decides whether to answer or
call a tool. - How you route a model-produced action to a Python
function. - Why a structured JSON action schema is safer than parsing
arbitrary prose. - How memory differs from the current conversation
context. - How you avoid infinite loops (step limits, repeated-action
checks, stop conditions). - How retries and fallbacks work when a tool
or model call fails. - Why run a local model, and the trade-offs in
hardware, latency, quality, and operations. - How you would log each
step for debugging without exposing sensitive data.

**Potential improvement:** Add explicit tool allowlists, input
validation, per-tool timeouts, output validation, maximum step counts,
and human approval for consequential actions.

### E. MedGuard AI --- safety-oriented design

Your resume describes a clinical drug-safety platform that checks drug
interactions, allergy cross-reactivity, renal dosing risks, and
medication safety using database-driven rules before AI response
generation. It also includes hybrid entity resolution, FastAPI, Supabase
PostgreSQL, Groq LLM, REST APIs, caching, and fail-safe workflows.

**Core design principle:** Use deterministic rules for safety-critical
validation and use the LLM for constrained assistance, not as the sole
source of truth.

Prepare to discuss: - Why deterministic checks precede AI generation. -
How medication-name typos and abbreviations can be resolved safely. -
What to do when a medication is ambiguous or the database lacks a
rule. - Why fail-safe behavior matters. - How you would test rules, API
behavior, and edge cases. - How to protect sensitive data and control
access.

Do not imply that a prototype or personal project is clinically
certified. Clearly state its actual deployment and validation status if
asked.

------------------------------------------------------------------------

## 5. Technical fundamentals checklist

Use this as a revision checklist. Prioritize concepts you list on your
resume and can connect to real work.

### Python and backend APIs

-   [ ] Functions, arguments, exceptions, classes, modules, virtual
    environments.
-   [ ] Sync vs async code; when I/O-bound tasks benefit from async.
-   [ ] HTTP methods: GET, POST, PUT, PATCH, DELETE.
-   [ ] Common status codes: 200, 201, 400, 401, 403, 404, 409, 422,
    429, 500, 502, 503.
-   [ ] Request validation, response schemas, error handling, logging.
-   [ ] Authentication vs authorization.
-   [ ] Timeouts, retries with backoff, idempotency, rate limits.
-   [ ] REST API design and API testing with Postman.

### Java / Spring fundamentals

-   [ ] OOP: encapsulation, inheritance, polymorphism, abstraction.
-   [ ] Interfaces vs abstract classes.
-   [ ] Collections: List, Set, Map; HashMap basics.
-   [ ] Checked vs unchecked exceptions.
-   [ ] JDBC vs Hibernate/JPA at a high level.
-   [ ] Dependency injection and inversion of control in Spring.
-   [ ] Controller, service, repository layers.
-   [ ] REST controllers and request/response DTOs.

### SQL and data storage

-   [ ] SELECT, WHERE, JOIN, GROUP BY, ORDER BY, HAVING.
-   [ ] Primary key, foreign key, unique constraint, indexes.
-   [ ] Normalization and transactions.
-   [ ] SQLite vs PostgreSQL/MySQL use cases.
-   [ ] Why store job status, timestamps, errors, and outputs
    separately.
-   [ ] Avoiding duplicate work and designing idempotent processing.

### LLMs, RAG, and agentic systems

-   [ ] Tokens, context windows, temperature, system instructions.
-   [ ] Prompting vs fine-tuning vs retrieval-augmented generation
    (RAG).
-   [ ] Embeddings, chunking, vector search, top-k retrieval.
-   [ ] Hallucination, grounding, citations, and output validation.
-   [ ] Tool calling: schema → validation → execution → observation.
-   [ ] Agent loop, planning, state, memory, stop conditions.
-   [ ] Deterministic workflows vs autonomous agents.
-   [ ] Offline/local inference vs hosted APIs: privacy, latency,
    quality, cost, operations.
-   [ ] Evaluation sets, human review, regression tests, prompt/model
    versioning.
-   [ ] Guardrails, tool permissions, prompt injection, sensitive-data
    handling.

### Speech and real-time systems

-   [ ] STT vs TTS.
-   [ ] Streaming vs batch transcription.
-   [ ] Word error rate (WER) as one way to evaluate transcription.
-   [ ] End-to-end latency and per-stage latency.
-   [ ] SIP vs WebRTC; signaling vs media.
-   [ ] Asterisk, VICIdial, LiveKit, SFU, and AGI at a conceptual level.
-   [ ] Noisy audio, silence detection, interruptions, retries, and
    fallbacks.

### Linux, deployment, and operations

-   [ ] Processes, environment variables, ports, logs, permissions.
-   [ ] Basic commands: `pwd`, `ls`, `cd`, `grep`, `tail`, `ps`, `top`,
    `curl`, `ss`.
-   [ ] Service health checks and restart behavior.
-   [ ] Docker basics and environment-based configuration.
-   [ ] Monitoring: latency, error rate, throughput, resource use.
-   [ ] Secrets should not be hard-coded or written into logs.

------------------------------------------------------------------------

## 6. Practice question bank --- 10-question mock screening

These are practice questions inferred from the categories in the email
and the content of your resume. They are not the employer's actual
questions. Answer each aloud in 60--90 seconds, then review whether your
answer has a clear structure and a concrete example.

### 1. Tell us about yourself and why this role interests you.

**Include:** CS degree, backend + applied AI focus, QC Agent, local
ReAct agent, and interest in solving real operational problems. Keep the
introduction under 90 seconds.

### 2. Walk us through a technical project you built end to end.

**Best example:** QC Agent. Explain the problem, data flow, your
contribution, deployment, and how you would evaluate quality.

### 3. How would you design an AI solution for a customer whose requirements are initially unclear?

**Strong structure:** 1. Ask who the user is and what decision/task they
need help with. 2. Map the current workflow and pain points. 3. Agree on
success metrics and constraints. 4. Build the smallest useful prototype.
5. Test with representative cases and real users. 6. Add monitoring,
feedback, security, and a rollout plan.

### 4. How would you reduce hallucinations in an LLM-powered system?

**Discuss:** Ground answers in approved data where possible, use RAG or
deterministic rules when suitable, request structured outputs, validate
outputs, handle uncertainty, test with representative examples, and use
human review for high-risk cases. Explain that prompting alone cannot
guarantee correctness.

### 5. Describe how your ReAct agent uses tools and memory.

**Discuss:** Model-selected structured action, validation and routing to
a permitted tool, tool result as an observation, next step or
termination, and memory retrieval when relevant. Include retry limits
and failure handling.

### 6. How would you debug a voice agent that responds too slowly?

**Discuss:** Reproduce and timestamp the call; measure audio capture,
STT, LLM, TTS, and transport separately; inspect logs and resource
usage; test streaming and model/runtime settings; then compare latency
and quality before and after a change. Do not assume the LLM is always
the bottleneck.

### 7. What would you do if the AI score disagreed with a human reviewer?

**Discuss:** Review the transcript and rubric, check whether the
disagreement comes from STT or scoring, compare across a labeled sample,
measure agreement by category, refine instructions/rules, and keep a
human escalation path. Do not silently treat either output as
infallible.

### 8. Explain an important technical trade-off you made.

**Possible example:** Local LLM inference/on-premise deployment versus
hosted inference. Discuss privacy and control versus
hardware/maintenance burden, latency, model quality, and scaling. Tie
the choice to the project's requirements and avoid claiming it is
universally better.

### 9. How do you make an AI workflow reliable in production?

**Discuss:** Input validation, bounded retries, timeouts, idempotency,
structured outputs, failure states, observability, test cases,
versioning, security controls, and graceful fallback. Give an example
from the QC agent or ReAct agent.

### 10. If you had one week to improve an existing AI product, how would you decide what to work on?

**Discuss:** Establish the user pain and baseline metrics, identify the
largest failure or bottleneck, estimate impact/effort/risk, choose one
measurable improvement, test it with representative data, compare
against the baseline, and communicate limitations and next steps.

------------------------------------------------------------------------

## 7. Design-thinking framework for an unfamiliar prompt

For a design question, answer in this order:

1.  **Clarify the user and goal:** Who uses it, and what outcome do they
    need?
2.  **Define constraints:** Latency, accuracy, privacy, cost, scale,
    integrations, and safety.
3.  **Describe a simple architecture:** Inputs, processing, model/rules,
    storage, API/UI, and monitoring.
4.  **Handle failures:** Bad input, model timeout, invalid output,
    unavailable dependency, and uncertain results.
5.  **Define evaluation:** Baseline, representative test set, quality
    metric, latency, reliability, and user feedback.
6.  **Explain rollout:** Prototype, limited pilot, monitor, iterate, and
    expand.

If time is short, say: "I'd start by clarifying the user and success
metric, then design the smallest reliable solution, test it on
representative cases, and add monitoring and fallbacks before scaling."

## 8. Metrics you should know how to discuss

You do not need to invent project results. Be able to explain how you
would measure them.

  -----------------------------------------------------------------------
  Area                                Useful metrics
  ----------------------------------- -----------------------------------
  Speech-to-text                      Word error rate, transcription
                                      completeness, processing latency

  LLM evaluation                      Agreement with human reviewers,
                                      precision/recall by criterion,
                                      unsupported-claim rate

  Voice agent                         Time to first response, end-to-end
                                      latency, interruption handling,
                                      call completion rate

  Agent workflow                      Task success rate, tool-call
                                      success, invalid-action rate, steps
                                      per task, timeout rate

  Backend service                     p50/p95 latency, error rate,
                                      throughput, uptime

  Product outcome                     Time saved, reviewer usefulness,
                                      adoption, user satisfaction
  -----------------------------------------------------------------------

Know the difference between **latency** (how long a response takes),
**throughput** (how much work completes per unit time), **precision**
(how many positive predictions are correct), and **recall** (how many
actual positives are found).

## 9. How to speak about your experience accurately

-   Use "I built," "I implemented," or "I designed" only for work you
    personally did.
-   Use "I worked with the team on" when the work was shared.
-   Separate **what exists today** from **what you would improve next**.
-   If you do not know an exact number, say so and propose a measurement
    plan.
-   If you do not know an answer, explain your assumptions and work
    through the problem.
-   Never claim a model is perfectly accurate or hallucination-free.
-   Keep explanations understandable to a technical interviewer who has
    not seen your system.
-   Use one project example per answer rather than listing every
    technology you know.

## 10. Practice schedule before opening the test

### Pass 1 --- Story preparation (30--40 minutes)

-   [ ] Rehearse the self-introduction 3 times.
-   [ ] Explain the QC Agent from memory using a simple flow.
-   [ ] Explain the voice pipeline and define SIP, WebRTC, STT, LLM, and
    TTS.
-   [ ] Explain your ReAct loop, tool routing, memory, and stopping
    conditions.
-   [ ] Prepare one trade-off and one debugging story.

### Pass 2 --- Technical revision (30--45 minutes)

-   [ ] Review the fundamentals checklist.
-   [ ] Practise explaining RAG, hallucination mitigation, tool calling,
    structured output, retries, and evaluation.
-   [ ] Review latency and failure handling in multi-stage pipelines.
-   [ ] Prepare a concise example of deterministic rules working
    alongside an LLM.

### Pass 3 --- Timed mock (20 minutes)

-   [ ] Record yourself answering the 10 mock questions.
-   [ ] Limit each answer to 60--90 seconds.
-   [ ] Watch the recording once. Check clarity, pace, eye contact, and
    whether you answered the question directly.
-   [ ] Remove long introductions and unnecessary jargon.
-   [ ] Repeat only the answers where the explanation was unclear.

### Pass 4 --- Final setup (10 minutes)

-   [ ] Charge the laptop and keep the charger connected.
-   [ ] Test the camera, microphone, Chrome/Edge, and internet.
-   [ ] Close unnecessary apps and notifications.
-   [ ] Keep water nearby and sit in a quiet, well-lit place.
-   [ ] Keep brief topic reminders nearby only if permitted; do not read
    a script during the recording.
-   [ ] Open the one-time exam link only when fully ready.

## 11. Final quick-reference sheet

**Three strongest examples** 1. QC Agent: production workflow, STT +
local LLM evaluation, storage, monitoring, on-prem deployment. 2. Voice
pipeline: LiveKit + Asterisk/VICIdial + SIP + LLM-backed real-time
interactions. 3. Local ReAct agent: agent loop, tool calling, memory,
structured JSON, retries, termination.

**Four phrases that communicate sound engineering** - "I would measure
each stage separately before deciding where the bottleneck is." - "I'd
validate the model output rather than trusting it blindly." - "I'd
define a baseline and evaluate against representative examples." - "I'd
design an explicit failure path, not just the happy path."

**One answer pattern to remember:**\
**Problem → Approach → Trade-off → Validation / Result**

**Before submitting:** Check the deadline and instructions in the
original email. The email warns that assessment content must not be
shared, copied, recorded, or published; use this document for personal
preparation and do not distribute the actual assessment content.

------------------------------------------------------------------------

## Source alignment and limitations

This guide is based on the supplied email and resume. The email confirms
the interview format, broad evaluation areas, setup requirements,
one-time link warning, and deadline. The resume supports the candidate
background and project descriptions used above. The mock questions,
technical revision checklist, sample responses, and suggested metrics
are preparation material created from those source details; they are not
confirmed YottaFlex interview questions or company-specific evaluation
criteria.
