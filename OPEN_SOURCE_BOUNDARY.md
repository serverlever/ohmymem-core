# Open Source Boundary

This repository provides the open implementation and reference materials for:

- Cross-LLM **Work Continuity** (Work + WorkState / Current State)
- **Work Pack** compilation (copy/paste friendly context packaging)
- Long-term memory **search** (read-only; verifiable results)
- Long-term memory **capture** (proposal-only; human review required)
- MCP Server (standard MCP protocol) and HTTP API
- Go SDK structs and client for integrations

## Design Principles

1. **Human-in-the-loop for long-term writes**
   - `memory.capture` creates a reviewable proposal.
   - The canonical long-term ledger is updated only after explicit user review in the UI / admin console.

2. **Verifiable memory retrieval**
   - `memory.search` returns results with stable identifiers and a manage/ref pointer so users can verify and correct issues later.

3. **Portability**
   - The ledger data format is designed to be exportable (e.g., Postgres → SQLite export tooling).

## What This Repository Does NOT Include

The Project intentionally does not publish certain components here, including (but not limited to):

- Commercial licensing, billing, subscription management, anti-abuse systems, and update delivery channels
- Proprietary UI implementations and proprietary integrations

This separation exists to protect user privacy, ensure predictable behavior, and allow commercial sustainability while keeping the core protocol and portability open.

## Compatibility

Third parties may implement compatible clients/servers using the published protocol and SDK types, subject to the repository license and trademark policy.

For protocol definitions, see: `docs/mcp/tools.md` and `protocol/mcp-tools.v0.json`.
