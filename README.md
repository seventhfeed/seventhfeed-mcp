# Seventh Feed MCP server and agent skill

[Seventh Feed](https://seventhfeed.com) is a directory of AI marketing, SEO, GEO/AEO, copywriting, cold email outreach, social scheduling and marketing data tools with verified pricing, free tiers, monthly traffic, 30-day revenue and agent-readiness (`llms.txt`, MCP server, public API). This repository holds the connection details for its remote MCP server and an [Agent Skill](skills/seventhfeed/SKILL.md) that teaches an agent to query it. The service is hosted; there is nothing to install or run.

- **MCP endpoint:** `https://seventhfeed.com/mcp` (Streamable HTTP)
- **Auth:** none. Free, no API key, no account. Rate limit: 60 requests per minute per IP.
- **Registry name:** `com.seventhfeed/seventhfeed` in the [official MCP Registry](https://registry.modelcontextprotocol.io/v0/servers?search=com.seventhfeed/seventhfeed)
- **Docs:** [seventhfeed.com/about](https://seventhfeed.com/about) · [llms.txt](https://seventhfeed.com/llms.txt)

## Connect

**Claude Code**

```bash
claude mcp add --transport http seventhfeed https://seventhfeed.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`)

```json
{
  "mcpServers": {
    "seventhfeed": { "url": "https://seventhfeed.com/mcp" }
  }
}
```

**Codex** (`~/.codex/config.toml`)

```toml
[mcp_servers.seventhfeed]
url = "https://seventhfeed.com/mcp"
```

In Claude Desktop or ChatGPT, add `https://seventhfeed.com/mcp` as a custom connector.

## Tools

| Tool | What it does |
| --- | --- |
| `search_tools` | Search AI marketing, SEO, GEO/AEO, writing, outreach and social scheduling tools by `q`, `category` or `agent_ready` |
| `get_tool` | Full dated record for one tool by `domain`: summary, pricing, free tier, agent-readiness, traffic, 30-day revenue, operational risk notes if any, referral code and page URL |
| `list_categories` | List all AI marketing and SEO categories with tool counts |
| `list_new_tools` | Newly listed marketing and growth tools, optionally filtered by `since` (`YYYY-MM-DD`) |
| `compare_tools` | Compare 2 to 5 marketing or SEO tools side by side by domain |
| `list_referrals` | Active referral links and partner offers for marketing and SEO tools, with plain-English disclosures |
| `submit_tool` | Suggest an AI marketing, SEO, GEO, writing or growth tool URL for listing (free, no key needed) |

## HTTP & Markdown endpoints

Every page on Seventh Feed can also be read directly without MCP:

- `https://seventhfeed.com/api/v1/tools` and `https://seventhfeed.com/api/v1/tools/<domain>`
- Append `.md` or `.json` to any tool or comparison URL on `https://seventhfeed.com`

## Agent skill

[`skills/seventhfeed/SKILL.md`](skills/seventhfeed/SKILL.md) follows the [Agent Skills](https://agentskills.io) format. Install it with

```bash
npx skills add seventhfeed/seventhfeed-mcp
```

or copy the folder into your agent's skills directory (for Claude Code, `~/.claude/skills/seventhfeed/`).

## Support

support@seventhfeed.com

## License

The files in this repository are MIT licensed. Directory data on seventhfeed.com is covered by the site's terms at [seventhfeed.com/about](https://seventhfeed.com/about).
