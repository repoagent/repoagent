# RepoAgent

Work with a coding agent from GitHub Discussions.

`@repoagent` is the mention account for **RepoAgent**, which connects GitHub conversations to native coding-agent sessions. The current implementation uses Codex. This account represents the connector, not a person.

## How it works

In a repository where [**Repo Agent Connector**](https://github.com/apps/repo-agent-connector) is installed and the bridge is running, mention `@repoagent` in a Discussion, comment, or reply to start a conversation.

Each Discussion gets its own persistent Codex session, shared across all its comment threads. Follow-up messages continue that session with its existing history. The agent works in the configured workspace, using its normal tools, skills, and repository guidance.

Replies and 👀 receipts come from the GitHub App, currently `repo-agent-connector[bot]`. The `@repoagent` account provides the short mention handle. A 👀 receipt means Codex accepted the input; it does not mean the work is finished.

GitHub Discussions are supported today. Mentions in issues and pull requests do not currently start an agent.

## Set it up

RepoAgent is self-hosted. Run the bridge in Docker with your Codex sign-in and GitHub App installation. The [installation guide](https://github.com/repoagent/controller/blob/main/docs/container-setup.md) covers setup on Windows and Linux, additional skills, and persistent storage.

The bridge can observe Discussions by polling or respond to webhooks. For webhooks, use [your own HTTPS endpoint](https://github.com/repoagent/controller/blob/main/docs/webhooks.md) or a [Cloudflare Quick Tunnel](https://github.com/repoagent/controller/blob/main/docs/quick-tunnel.md) for local development.

Project, documentation, and issue tracker: [**repoagent/controller**](https://github.com/repoagent/controller) — repository access may be required.

For questions about this account, contact [@egil](https://github.com/egil).
