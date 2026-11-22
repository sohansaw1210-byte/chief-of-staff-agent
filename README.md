# Chief of Staff Agent

An AI agent that reads your emails, figures out what needs doing, and asks for your approval before it does anything.

Built for **Homingo Hack Days, Edition 01 · Agents track · A3: A personal staff for everyone.**

## The problem

Wealthy people have assistants to handle bills, appointments and refunds. Everyone else handles it alone, badly and late. This project is a first step toward a chief-of-staff agent that anyone can have.

## What it does

1. **Reads** a set of emails (currently a sample inbox).
2. **Decides** what each one needs: pay a bill, book an appointment, chase a refund, or nothing.
3. **Drafts** the action, such as a reminder or a message to support.
4. **Asks for approval.** Nothing happens until you type `yes`.
5. **Logs** every decision (approved or rejected) so you can see what the agent did.

## Built to be careful

The brief asks for an agent that is "careful with money and private data". So:
- The agent only **proposes**, and never acts on its own.
- Every action needs explicit human approval.
- Actions are **simulated** for now: no real payments or messages are sent.
- The API key is kept in Colab Secrets, never in the code.

## Tech stack

- Python in Google Colab
- Google Gemini API (`google-genai`) for reading and classifying emails
- Retry logic with backoff to handle temporary API errors (503, 429)

## How to run it

1. Open the notebook in Google Colab.
2. Get a free API key from [Google AI Studio](https://aistudio.google.com).
3. In Colab, open **Secrets** (key icon, left sidebar), add a secret named `GEMINI_API_KEY` with your key, and turn on Notebook access.
4. Run the cells in order: the sample inbox, then the AI analysis, then the approval screen.
5. Type `yes` or `no` when asked about each proposed action.

## Current limitations

- Uses a **sample inbox**, not real email.
- Approved actions are simulated.
- The agent does not yet check a calendar before choosing appointment slots.

## Roadmap

- Look up real company refund and support pages with Olostep to improve drafted refund requests
- Connect a real (test) Gmail account in read-only mode
- Make one approved action real, such as sending a reminder email

## Hackathon

Submitted to Homingo Hack Days, Edition 01.
