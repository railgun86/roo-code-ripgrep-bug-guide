# roo-code-ripgrep-bug-guide
Troubleshooting guide: Roo Code v3.54.0 Could not find ripgrep binary, agent stuck on Requesting API
# Roo Code v3.54.0 Bug: Could not find ripgrep binary, stuck on "Requesting API"
> Original Roo Code repo (RooVetGit/Roo-Code) has been archived and read-only. No new issues can be submitted there.

## Introduction
This document records a tricky bug encountered in Roo Code v3.54.0.
When users run the agent, the UI stays at "Requesting API", which easily misleads people to investigate LLM API / Ollama network issues.
The real root cause is the missing `ripgrep` binary, not the large model service.
This guide helps developers avoid wasting time debugging irrelevant network or API settings.

## Symptom
After installing Roo Code v3.54.0 and sending any agent task, the UI hangs forever and displays `Requesting API`.
Users may mistakenly think this is an Ollama / DeepSeek API network, CORS or connection error.

## Error Log
