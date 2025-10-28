# Setup Guide

## Step 1: Azure DevOps Configuration

### Create Variable Group
1. Navigate to Pipelines → Library
2. Create variable group: `copilot-credentials`
3. Add variable: `GITHUB_TOKEN` (mark as secret)
   - Value: Personal Access Token from GitHub
   - Ensure token owner has active Copilot license

### Import Pipeline
1. Go to Pipelines → New Pipeline
2. Select "Azure Repos Git" or "GitHub"
3. Choose "Existing Azure Pipelines YAML file"
4. Select `/pipelines/backlog-analyzer.yml`

## Step 2: GitHub Token Generation

1. Go to GitHub → Settings → Developer settings
2. Personal access tokens → Tokens (classic)
3. Generate new token with scopes:
   - `read:user`
   - `read:org` (if using organization Copilot)

## Step 3: First Run

1. Queue pipeline manually
2. Set parameters:
   - `analyzeTop`: 3 (start small)
3. Monitor logs for any errors
4. Download artifact `copilot-analysis-report`

