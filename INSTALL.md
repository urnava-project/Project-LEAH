# Install

Apply the complete `LEAH.md` to the user's target workspace through the instruction file their agent actually loads.

## Choose the file

Inspect the target agent's active instructions and select its destination below. Update an existing LEAH block in that file. If LEAH is inherited from outside the workspace, report its location and any version difference without adding another copy.

Before creating a new instruction file, verify that doing so will not stop any currently loaded workspace instructions from being loaded. If it would, report the conflict and ask how to proceed instead of creating the file.

| Environment | Destination |
|---|---|
| Codex | The active workspace file: `AGENTS.override.md`, `AGENTS.md`, or a configured fallback. Otherwise create `AGENTS.md`. |
| Claude Code | An existing loaded workspace `CLAUDE.md`, `.claude/CLAUDE.md`, or `CLAUDE.local.md`. Otherwise create `CLAUDE.md` at the workspace root. |

Put LEAH directly in the selected file. When both agents use the workspace, each may have its own LEAH block in its own instruction file. Do not add imports or change the other agent's instructions.

Check the official loading rules for [Codex](https://learn.chatgpt.com/docs/agent-configuration/agents-md) or [Claude Code](https://code.claude.com/docs/en/memory#claudemd-files), including ancestor instructions and configuration. If automatic loading is unavailable, read the selected file for the current session and report the limitation.

## Add or update LEAH

Create the selected file if needed, once the loading check above passes. Insert the full, unchanged contents of `LEAH.md` at the top, wrapped in these markers:

```markdown
<!-- PROJECT-LEAH:START -->
[ full contents of LEAH.md ]
<!-- PROJECT-LEAH:END -->
```

Replace an existing block in place, keeping one complete LEAH block in the selected file. Preserve content outside LEAH markers and leave other files untouched. If markers are incomplete or ambiguous, report the affected section without guessing its boundaries.

## Confirm

Compare the installed block with `LEAH.md`. Confirm that existing instructions are preserved. Report the changed file and whether the block was added or updated. Check the target agent's loaded instruction chain for duplicate LEAH content, including existing imports and inherited files; report any duplicate sources without modifying them.

Read the installed identity for use in the current session. Verify automatic loading separately in a fresh session using the host's available instruction-loading indicators; otherwise report it as unverified. Manual reading alone does not establish automatic loading.
