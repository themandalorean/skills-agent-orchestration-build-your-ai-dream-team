# Agent team

To build Mona's Project Pulse dashboard, I will use a four-agent custom team defined under `.github/agents/`.

- **Orchestrator**
	- **Target model:** Claude Opus 4.7 (copilot)
	- **Responsibility:** Coordinates end-to-end delivery by delegating to Planner, Coder, and Designer, sequencing phases based on file ownership and dependencies, and ensuring the final integrated result is coherent.
	- **Definition:** `.github/agents/orchestrator.agent.md`

- **Planner**
	- **Target model:** Claude Opus 4.7 (copilot)
	- **Responsibility:** Researches repository context and constraints, then produces a practical implementation plan with ordered steps, file assignments, dependencies, risks, edge cases, and validation expectations.
	- **Definition:** `.github/agents/planner.agent.md`

- **Coder**
	- **Target model:** GPT-5.5 (copilot)
	- **Responsibility:** Implements code changes, fixes logic issues, and validates behavior in assigned files, including runnable-app support such as `.vscode/launch.json` for the Project Pulse app when requested.
	- **Definition:** `.github/agents/coder.agent.md`

- **Designer**
	- **Target model:** Gemini 3.1 Pro (copilot)
	- **Responsibility:** Owns UI/UX quality for assigned scope, including accessibility, information hierarchy, responsive behavior, and polished Project Pulse dashboard styling.
	- **Definition:** `.github/agents/designer.agent.md`

This workflow is orchestrated with GitHub Copilot CLI in a Codespace, where the Orchestrator delegates focused tasks to specialists and then integrates their outputs.
