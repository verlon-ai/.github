# Verlon AI

Verlon AI is an LLM gateway. It scores response quality on your real production traffic, routes across 100+ LLMs from OpenAI, Anthropic, Google, and every major provider without code changes, tracks every dollar of spend and every step your agents take, and lets you switch providers without a rewrite, no vendor lock-in.

**[verlon.ai](https://verlon.ai)** · **[Docs](https://docs.verlon.ai)** · **[Quickstart](https://docs.verlon.ai/getting-started/quickstart)**

## Calling models

Use the official OpenAI, Anthropic, Gemini or Mistral SDK and point it at Verlon. No Verlon package is needed:

```typescript
import OpenAI from 'openai';

const openai = new OpenAI({
  baseURL: 'https://api.verlon.ai/v1',
  apiKey: process.env.VERLON_API_KEY,
});

const reply = await openai.chat.completions.create({
  model: process.env.VERLON_GATE_ID, // your gate's id
  messages: [{ role: 'user', content: 'Hello' }],
});
```

[OpenAI SDK guide](https://docs.verlon.ai/integrations/openai-sdk) · [Agent tracing with OpenTelemetry](https://docs.verlon.ai/platform/agent-gates)

## Tools

| Package | What it is |
|---|---|
| [`@verlon-ai/cli`](https://www.npmjs.com/package/@verlon-ai/cli) | CLI for managing gates and keys from a terminal |
| [`@verlon-ai/mcp`](https://github.com/verlon-ai/mcp) | MCP server — connect Claude Code, Cursor, and other agent hosts to your Verlon account |
| [`@verlon-ai/admin`](https://www.npmjs.com/package/@verlon-ai/admin) | Admin SDK for B2B platforms provisioning gates for end-users |

## For coding agents

Integrating Verlon on behalf of a developer? Read [`verlon.ai/AGENTS.md`](https://verlon.ai/AGENTS.md) and [`verlon.ai/openapi.json`](https://verlon.ai/openapi.json) — the authoritative agent contract.

---

Not affiliated with Vorlon (vorlon.io), Perlon, or Verlo. Formerly known as Layer.
