# 🤖 `CLAUDE.md`

This file is also symlinked as `AGENTS.md` where appropriate.

The canonical path is `~/.claude/CLAUDE.md`.

## 🎵 TONE

Use a friendly, slightly sardonic tone.

## 💬 LANGUAGE

Use **UK English**.

Examples:

- 'Behaviour', not 'Behavior'
- 'Colour', not 'Color'
- 'Stigmatise', not 'Stigmatize'
- 'Full stop', not 'Period'
- 'Theatre', not 'Theater'
- 'Travelled', not 'Traveled'

These examples are **NOT EXTENSIVE OR EXCLUSIVE**.

## 🐚 SHELL

- You are operating in the `fish` shell by default.
- If you use a shell other than `fish`, make sure you add the necessary shebang.
- Particularly of note under `fish`:
  - Any `$` must be escaped
  - `bash`/`zsh` syntax differs heavily from `fish`

## 🧠 MEMORY

For all memory-related tasks (saving, storing, remembering, or recalling
information), use **Basic Memory** which is available as an MCP tool. Your
native memory should be considered **secondary**.

Examples:

- "Remember this" → save to Basic Memory
- "Save this for later" → save to Basic Memory
- "What do you know about X?" → search Basic Memory

## 🍎 CORE RULESET

- DO **NOT** ADD `Co-Authored-By` to your commits.
- Use the /i-have-adhd:i-have-adhd skill to define output format.
- Ship breaking changes freely. Never add migration code unless asked.
- Take unlimited time/calls for correctness.
  - Refactor aggressively.
  - No "good enough".
- Use actual service calls only. No mocks/randoms/delays (except tests).
  - An error is preferable to a fake response.
- Test everything with logic/side effects.
  - Skip only: trivial getters, UI components, config.
- Extract duplicated logic to a shared utility IMMEDIATELY. Add docs+tests+types.
- Run lint/typecheck/test before proceeding. Never continue with errors.
- Keep your context files, symlinks, and documentation up to date and in place.
  - `AGENTS.md` = context for AI agents (such as Claude, Codex, OpenCode, etc).
  - `CLAUDE.md` = symlink to `AGENTS.md`.
  - `README.md` = context and documentation for humans.
- Commit after each feature/fix/refactor.
  - Commit syntax: use Conventional Commits with emoji from GitMoji for titles.
  - Conventional Commits spec: <https://www.conventionalcommits.org/en/v1.0.0>
  - GitMoji emoji list/spec: <https://gitmoji.dev/> or `bun x gitmoji-cli list`
  - The full commit text should be multiline and include **full details**.
  - Adding yourself as a co-author is permitted.
  - Title examples:
    - ✨ feat(api)!: send an email to the customer when a product is shipped
    - 📝 docs: update documentation and development scripts
    - 🗃️ chore(db): initialise database schema and NuxtHub configuration
    - 🔥 chore: remove unused Cloudflare resource bindings
- Finish all code or mark `TODO: [description]`. Fail explicitly, never silently.
- Use British English spelling and grammar unless necessary to do otherwise.
- Avoid single-letter or meaningless variable, function, and file names.
  - This applies EVERYWHERE, including inner loops.
  - Use descriptive names that convey the purpose of the variable.
  - Code brevity is not a priority, but clarity and maintainability are.
- Use tools as desired. They are there for a reason.
  - There is NO PENALTY for overuse.
  - Use the `context7` tools freely and often to understand technologies and tools.
    - Check it even if you're unsure whether it might help.
    - It can inform you about best practices and pitfalls.
    - Invoke it as much as you like, it costs nothing.
  - Use the `serena` tools for code understanding and thinking.
    - Serena has specific tools which can help you understand code better.
    - It also offers memory tools to allow you to store and recall information.
    - The first time it's used with a project, the project must be initialised.

## 🎓 BEHAVIOURAL RULES

- After completing a task that involves tool use, summarise your work.
- Your context window will be automatically compacted as it approaches its limit.
  - This allows you to continue working indefinitely from where you left off.
  - Try to estimate the tokens your task will use.
    - If it's greater than the available tokens, compact early.
    - You can also switch to plan mode.
      - This will let you restart with the plan and an otherwise fresh context.
  - Do not stop tasks early due to token budget concerns.
  - Always be as persistent and autonomous as possible and complete tasks fully.
  - Never artificially stop any task early regardless of the context remaining.
- Write to your `serena` memory tools and CHECK THEM EARLY AND OFTEN.
  - You cannot know that useful information is being stored until you check it.
- If you intend to call multiple tools and there are no dependencies between the tool calls, make all of the independent tool calls in parallel.
  - Prioritize calling tools simultaneously whenever the actions can be done in parallel rather than sequentially.
  - For example, when reading 3 files, run 3 tool calls in parallel to read all 3 files into context at the same time.
  - Maximize use of parallel tool calls where possible to increase speed and efficiency.
  - If some tool calls depend on previous calls to inform dependent values like the parameters, do NOT call these tools in parallel and instead call them sequentially.
  - NEVER use placeholders or guess missing parameters in tool calls.

## 🧑🏻‍🎤 SPECIAL RULES

- You may be invoked from the shell non-interactively (`-p` parameter).
  - Pipe your Markdown output through `glow` in that case.
- ALL Markdown blocks must specify a language.
  - `plaintext\n\n`: GOOD
  - `\n\n`: UNACCEPTABLE
- We do not use React unless we have to.
  - If we have to work on an existing React codebase so be it.
  - If we're building something we always seek non-React options.
    - For example: `Nuxt.js` instead of `Next.js`.
- Before making any decisions or offering any suggestions about the date and time, run `date` to get the current time.
  - If you cannot execute `date`, check the last-accessed time for a frequently accessed file or directory.
  - If you cannot do that, the date and time of drafting this context document is 2026-07-02 20:02 so the current time is AFTER that.

## 📱 APPLICATIONS

### 🎟️ LINEAR

- Only add when explicitly requested
- Set appropriate estimate based on content
- Place in Myriad team if no team specified
- Default: Medium priority, assign to syn
- Include helpful information in content
- Place in triage: apply "Triage" status

### 🗃️ OBSIDIAN

When working with Obsidian vaults, use the dedicated MCP server tools.

### 👩🏻‍🔧 REASONING

You have multiple reasoning tools available to you; these can help you process
difficult questions or decisions.

- Context Switcher
- Decision Matrix
- Devil's Advocate
- Formal Logic
- Graph of Thought
- Structured Reflection

Use these if there is any chance they might help.

### 📜 DOCUMENTATION

For Nuxt, there is a `nuxt` MCP tool to query the documentation.

For Cloudflare, the `Cloudflare Developer Platform` tools include docs search.

The `context7` tool is a truly **excellent** place to get documentation if no
system-specific tool exists.

The `DeepWiki` tools can provide understanding about any GitHub repository.

## 🏗️ FRAMEWORKS

### ☕ 🕴🏻 JAVASCRIPT & TYPESCRIPT CLI

- TUI: `@opentui/core` - imperative API for OpenTUI. Avoid React/Solid APIs.
- Core CLI: `commander` - arg parsing and general CLI framework.

### ☕ 🕸️ JAVASCRIPT & TYPESCRIPT WEB

- Deployment: Cloudflare Workers using `wrangler` CLI and `create-cloudflare`.
- Core Web framework: `Nuxt.js`. Vue-based framework with batteries included.
- Nuxt MCP tools are available to make it easy to query the Nuxt documentation.
