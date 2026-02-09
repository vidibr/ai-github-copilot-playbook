---
name: 'Session Logger'
description: 'Logs all Copilot coding agent session activity for audit and analysis'
tags: ['logging', 'audit', 'analytics']
---

# Session Logger Hook

Comprehensive logging for GitHub Copilot coding agent sessions, tracking session starts, ends, and user prompts for audit trails and usage analytics.

## Overview

This hook provides detailed logging of Copilot coding agent activity:
- Session start/end times
- User prompts and questions
- Session duration
- Working directory context

## Features

- **Complete Audit Trail**: Track all Copilot interactions
- **Structured Logging**: JSON format for easy parsing
- **Searchable History**: Review past sessions and prompts
- **Analytics Ready**: Export data for usage analysis
- **Privacy Aware**: Configurable to exclude sensitive data

## Installation

1. Copy this hook folder to your repository's `.github/hooks/` directory:
   ```bash
   cp -r hooks/session-logger .github/hooks/
   ```

2. Create the logs directory:
   ```bash
   mkdir -p logs/copilot
   ```

3. Ensure scripts are executable:
   ```bash
   chmod +x .github/hooks/session-logger/*.sh
   ```

4. Commit the hook configuration to your repository's default branch

## Log Format

Logs are written to `logs/copilot/session.log` in JSON format:

```json
{
  "timestamp": "2024-01-15T10:30:00Z",
  "event": "sessionStart",
  "sessionId": "abc123",
  "cwd": "/workspace/project"
}
```

## Privacy & Security

- Add `logs/` to `.gitignore` to avoid committing session data
- Use `LOG_LEVEL=ERROR` to only log errors
- Set `SKIP_LOGGING=true` environment variable to disable
- Logs are stored locally only
