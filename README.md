# CodeAtlas — Architecture Diagrams for Any Codebase

> **A zoomable structural map of your codebase — like Google Maps for code.**
> Auto-generated architecture diagrams, API sequence flows, dependency graphs, and code health reports for 30+ frameworks across 13 languages.

Navigate from service topology down to a single function. Live differential rendering highlights exactly what changed and where it ripples — across every layer, automatically.

**Works with:** Express, NestJS, Next.js, React, Django, FastAPI, Flask, Spring Boot, Laravel, Rails, Gin, Actix, ASP.NET, and 20+ more frameworks. Supports JavaScript, TypeScript, Python, Java, Kotlin, Go, Rust, C#, PHP, Ruby, Swift, C/C++.

---

## How It Works

Install the extension. CodeAtlas **auto-scans your workspace on launch** and builds interactive architecture diagrams — no setup required.

**View diagrams in your browser** at `http://localhost:7742` for the best experience — full screen, multi-monitor, DevTools access.

Watch the demo video
  
https://github.com/vamsikk7/codeatlas-live-issues/raw/main/videos/demo-yc-may-export.mp4


<!-- <div align="center">
<video width="100%" controls>
  <source src="https://github.com/vamsikk7/codeatlas-live-issues/raw/main/videos/demo-yc-may-export.mp4" type="video/mp4">
  ▶ <a href="https://github.com/vamsikk7/codeatlas-live-issues/raw/main/videos/demo-yc-may-export.mp4">Watch the demo video</a>
</video>

</div> -->

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/carousel.gif" alt="Continuous carousel: L1 System Design, L2a Features, L2b API List, L3 Sequence, L4 File, L5 Flow, Diff Colors" width="100%"/>
</div>

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/layer-overview.png" alt="6 diagram layers: System Design, Feature Areas, API List, Sequence, File, Flow" width="100%"/>
</div>

---

## Getting Started

1. **Install** from the VS Code Marketplace
2. **Diagrams build automatically** on extension launch — no manual step needed
3. **Click "Open in Browser"** in the welcome panel or run `CodeAtlas: Open in Browser`
4. **Sign in** (free account) to view diagrams in the browser UI
5. Navigate: click any node to drill deeper through all 6 layers

> Diagrams are built and synced without authentication. Sign-in is only required to view them.

### Browser UI

CodeAtlas runs a local server at `http://localhost:7742` that serves the full diagram viewer:

- **Home page** — workspace stats, quick-nav buttons, commands, sign-in
- **Floating explorer sidebar** — Services, Feature Areas, APIs, Files, Functions (toggle with ☰)
- **Live updates** — save a file in VS Code, browser updates in real time
- **Auto-reconnect** — if VS Code reloads, browser reconnects automatically

The port is configurable via `codeatlas.browserPort` setting (default: 7742).

---

## The 6 Diagram Layers

### L1 — System Design

See all your services and infrastructure at a glance. Services connect to databases, caches, queues, and each other. Polyglot services show all detected technologies.

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/l1-system-design.png" alt="L1 System Design diagram showing services, databases, caches, and connections" width="100%"/>
</div>

---

### L2a — Feature Areas

Zoom into a service to see its domain clusters — automatically detected using Louvain community detection with Jaccard stability matching.

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/l2a-features.png" alt="L2a Feature Areas: clusters with cohesion bars and inter-cluster edges" width="100%"/>
</div>

---

### L2b — API & Screen List

Browse every API endpoint, screen, navigation route, network call, and DI binding in a cluster. Filter by method, search by route or handler. Press `/` to search.

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/l2b-apilist.png" alt="L2b API List: method badges, search filter, mobile sections" width="100%"/>
</div>

---

### L3 — Sequence Diagram

See the full interaction flow for any API call — classes or files as participants, functions as messages. Cross-file resolution traces up to 8 hops deep.

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/l3-sequence.png" alt="L3 Sequence Diagram: participants, messages, return values" width="100%"/>
</div>

---

### L4 — File / Class Diagram

See a file's structure: imports, classes, functions, variables, and their dependency edges. Unused imports are dimmed (45% opacity). Class hierarchy shown.

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/l4-file.png" alt="L4 File Diagram: imports, functions, variables with dependency edges" width="100%"/>
</div>

---

### L5 — Function Flow

Control flow inside a single function: if/else as diamonds, loops with dashed back-edges, try/catch/finally as three-way splits. Every branch gets diff highlighting.

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/l5-flow.png" alt="L5 Function Flow: decisions, loops, try/catch/finally, return paths" width="100%"/>
</div>

---

### Health Dashboard
Run **Show Health Report** to see dead functions, god files, cyclic dependencies, high coupling, and orphaned clusters — sorted by severity with color-coded borders.

---

## Live Change Tracking

CodeAtlas watches your files. When you save, every diagram updates instantly — in both VS Code webview panels and the browser UI. Changes propagate upward through all 6 layers:

### Diff Propagation Example

| Layer | What Changes | Visual |
|-------|-------------|--------|
| **L5 Flow** | Changed function body highlighted | `~ login()` dotted border |
| **L4 File** | Function node shows modified | `~ authController.js` |
| **L3 Sequence** | Affected participants + messages | `~ POST /login` orange swimlane |
| **L2b API List** | Changed endpoints show badge | `~ login` endpoint |
| **L2a Features** | Cluster border turns orange | `~ Auth cluster` |
| **L1 System** | Service node shows badge | `~ backend` |

### Colorblind-Safe Diff Indicators (WCAG 1.4.1)

Every change shows **three independent visual channels** — not just color:

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/diff-colors.png" alt="Diff color legend: Added (green, solid), Deleted (red, dashed), Modified (orange, dotted), Unchanged (gray)" width="100%"/>
</div>

---

## Git Diff Mode

Compare **any two commits** visually across all diagram layers.

1. Click **Compare Commits** in the diagram header (or browser home page)
2. Pick a base and head commit
3. Navigate all layers with full diff coloring
4. Click **Reset** to return to live mode

Works with branches, tags, and pull requests.

---

## Supported Languages & Frameworks

**14 languages:** JavaScript, TypeScript, Python, Java, Kotlin, Go, Rust, C, C++, C#, PHP, Ruby, Swift, Dart

| Category | Frameworks |
|----------|-----------|
| **Node.js** | Express, Koa, Fastify, NestJS, Hono |
| **Meta-frameworks** | Next.js (App + Pages), Nuxt, Remix, SvelteKit |
| **API protocols** | tRPC, GraphQL, gRPC |
| **Python** | Django, FastAPI, Flask, Starlette |
| **Java/Kotlin** | Spring Boot, Micronaut, JAX-RS, Ktor |
| **Go** | Gin, Echo, Chi, Fiber |
| **PHP** | Laravel, Symfony |
| **Ruby** | Rails, Sinatra |
| **Rust** | Actix, Axum, Rocket |
| **C#** | ASP.NET Core, Minimal API |
| **Swift** | Vapor |
| **Dart** | Flutter (StatelessWidget, StatefulWidget, GoRouter, Dio, GetIt, Riverpod) |

### Mobile & UI Frameworks

| Platform | Detection |
|----------|-----------|
| **Android** | Activities, Fragments, Jetpack Compose, Navigation Component, Retrofit, Room DAO, Hilt/Dagger/Koin |
| **iOS** | UIViewController, SwiftUI Views, NavigationStack, URLSession/Alamofire, CoreData/SwiftData, Combine |
| **React / Next.js** | Pages, react-router, useSWR/useQuery/useMutation/useInfiniteQuery, Redux/Context/Zustand/Jotai |
| **React Native** | Screen components, Stack/Tab navigators, navigation routes |
| **Expo Router** | Stack.Screen, Tabs.Screen, router.push/replace, Redirect, (group) route stripping |
| **Flutter** | StatelessWidget/StatefulWidget, Navigator/GoRouter, Dio/http, GetIt/Provider/Riverpod |
| **KMP** | commonMain/androidMain/iosMain source sets, expect/actual declarations |

Mobile items appear in 4 sections: **Screens**, **Navigation**, **Network**, **Dependencies** — each with a platform badge.

**Infrastructure auto-detected:** PostgreSQL, MySQL, MongoDB, Redis, RabbitMQ, Kafka, Celery, Sidekiq, Entity Framework, Eloquent, Room, CoreData, Realm, Firebase, and more.

---

## Blast Radius Analysis

Right-click any function or run **Impact Analysis** from the sidebar/command palette to see:

- **Will Break** — direct callers that will fail
- **Likely Affected** — transitive callers up to 4 hops
- **Review Required** — modules that import your code but may not call it

Know what breaks before you ship.

---

## AI Query Engine

Ask questions about your codebase in plain English. CodeAtlas highlights matching entities in **blue** across all 6 diagram layers.

**How to use:**
1. Click the **Ask AI** button (sparkle icon) in the toolbar, or press `Cmd+Shift+Q`
2. Type a question: *"Show me the authentication flow"*, *"How does payment connect to the database?"*, *"What are the service controllers?"*
3. Matching services, clusters, APIs, files, classes, and functions light up in blue
4. **Navigate freely** — highlights persist as you drill through layers
5. **Hover** any highlighted node to see WHY it matched (e.g., "API handler: POST /auth/login")
6. Click **Clear** or press `Esc` to remove all highlights

**What gets highlighted:**
- Services, feature clusters, and sub-cluster pills at L1/L2
- API endpoints with blue left-border at L2b
- Sequence diagram participants AND message arrows between them at L3
- File/function nodes AND connecting edges at L4/L5
- Config files and type definitions (even without functions)

**Smart features:**
- Zero results show suggested query examples to help you get started
- Progress indicators for long-running queries ("Analyzing codebase...", "Still working...")
- Results cached for 5 minutes — repeated queries return instantly
- Concurrent queries handled safely — only the latest result is displayed
- Works in both VS Code webview and standalone browser mode
- Set your API key inline from the browser (no VS Code command palette needed)

**Setup:** Enable LLM features in settings (`codeatlas.llmNaming: true`), then run **CodeAtlas: Set LLM API Key** to enter your OpenRouter, OpenAI, or Anthropic key. Free tier available via OpenRouter.

---

## Commit Timeline Replay

Watch your codebase evolve commit-by-commit with a cinematic visual replay.

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/timeline-replay.gif" alt="Timeline Replay: commit range picker, then auto-navigating through L5 Flow, L4 File, L3 Sequence, L2a Feature, L1 System with diff colors" width="100%"/>
</div>

1. Click **Timeline Replay** (⏯) in the toolbar
2. **Select a branch** from the dropdown — commits load automatically
3. The **merge-base** with main/master is auto-detected and marked with a yellow badge
4. **Click the start and end commits** — the range highlights in blue
5. Click **Start Replay** — CodeAtlas builds diffs on-demand and auto-navigates:
   - **L5 Flow** — each changed function's control flow
   - **L4 File** — changed file dependency graphs
   - **L3 Sequence** — affected API interaction diagrams
   - **L2a Feature** — impacted feature clusters
   - **L1 System** — full system design with propagated diff colors

**Playback controls:**
- ⏸ Pause / ▶ Resume — freeze on any diagram to explore
- ⏭ Skip — jump to the next commit
- ■ Stop — end replay and return to live mode
- Speed slider — adjust from 0.5s to 5s per step

All diagrams use the full 3-channel WCAG diff colors (green/added, orange/modified, red/deleted) so you can see exactly what each commit changed.

---

## Comments for AI Agents

<div align="center">
<img src="https://raw.githubusercontent.com/vamsikk7/codeatlas-live-issues/main/docs/diagrams/comments.gif" alt="Right-click a node, add comment, exported to comments.md with full layer context" width="100%"/>
</div>

Right-click any node in any diagram to add a comment. Comments are exported to `comments.md` in your workspace root with full architectural context — service, cluster, API, file, and function — so LLM agents can pick them up and understand exactly where to make changes.

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Cmd+Shift+D` | Open System Design |
| `Cmd+Shift+A` | Search APIs |
| `Cmd+Shift+I` | Initialize Visuals |
| `Cmd+Shift+Q` | Ask AI — natural language query |
| `Cmd+Shift+F5` | Global Search |
| `/` | Focus search in API List |
| `Esc` | Close panels / clear AI query |

---

## Export

| Format | How |
|--------|-----|
| **SVG** | Click **Export** in diagram header (copies to clipboard) |
| **Markdown** | `CodeAtlas: Export Architecture Docs` — Mermaid diagrams for L1-L3 + API tables + health |
| **JSON** | `CodeAtlas: Export Diagrams JSON` |

---

## AI Assistant Integration (MCP)

CodeAtlas exposes tools for AI coding assistants via the Model Context Protocol:

- **Impact analysis** — "What breaks if I change this file?"
- **Dependency lookup** — "Who calls this function?"
- **Architecture context** — services, APIs, and feature clusters as structured data

Works with Claude Desktop and compatible IDE integrations.

---

## Commands

| Command | Description |
|---------|-------------|
| Open in Browser | View diagrams at localhost:7742 |
| Initialize Visuals | Scan workspace and build all diagrams |
| Re-sync Everything | Full rebuild + reset baseline |
| Search | Find APIs, files, clusters, services |
| Show Health Report | Code quality dashboard |
| Impact Analysis | Blast radius for selected file/function |
| Compare Commits | Git diff across all layers |
| Compare Pull Request | PR diff across all layers |
| Load Test Coverage | Import lcov/Istanbul coverage data |
| Export Architecture Docs | Markdown + Mermaid export |
| Copy API Route | Copy `METHOD /route` to clipboard |
| Toggle Auto Update | Enable/disable live updates |

---

## Settings

| Setting | Default | Description |
|---------|---------|-------------|
| Auto Update on Save | On | Refresh diagrams when you save |
| Browser Port | 7742 | Port for standalone browser UI (localhost) |
| Ignore Patterns | node_modules, dist, build | Glob patterns to skip |
| LSP Fallback | Off | Better type resolution for complex TypeScript |
| LLM Naming | Off | AI-powered cluster naming via OpenRouter |
| God File Threshold | 15 | Symbols count to flag large files |
| High Coupling Threshold | 10 | Cross-file edges to flag tight coupling |

---

## Privacy & Security

- **Your code stays local.** All analysis runs on your machine.
- **Browser UI is localhost-only.** Server binds to 127.0.0.1 with WebSocket origin validation.
- **LLM naming is opt-in.** Only short snippets sent; sensitive values are filtered before transmission.
- **Sensitive data never persisted.** Automatically stripped from the state file.
- **CSP enforced.** Webview uses nonce-based Content Security Policy.
- **Atomic writes.** State file uses write-rename pattern with backup recovery.

### Telemetry

CodeAtlas sends anonymous product-usage events to Amplitude to understand which features
are used and to debug issues across editors and platforms.

**What we collect:**

- **Lifecycle events** — first install, update, launch (`extension_installed`,
  `extension_updated`, `extension_launched`), with extension version and
  days-since-install.
- **Interaction events** — which features get clicked: AI Review, NL Query, Replay,
  Git Diff, Initialize, Resync, Sign-In nudge.
- **Editor context** — `appName` (e.g. `Visual Studio Code`, `Cursor`, `VSCodium`),
  uri scheme, distribution channel (Marketplace vs Open VSX), platform, architecture,
  remote-mode kind (`wsl` / `ssh-remote` / `dev-container`).
- **Anonymous device ID** — `vscode.env.machineId`, a per-device hash provided by
  VS Code. Never tied to your real identity unless you sign in.
- **User account when signed in** — your email + Clerk user id, only after explicit
  sign-in. Used to merge anonymous device events with your account.
- **Error and notification events** — feature failures, parse errors, warning toasts
  shown.

**What we do NOT collect:**

- Your source code or any file content
- File names or directory structure
- Git history, commit messages, branch names, or repo URLs
- Search queries or natural-language prompts (only their length is recorded)
- LLM responses or AI Review findings text
- Any value entered into a password field, API key, or secret

**How to opt out:**

Set VS Code's telemetry level to `off` (or `crash` / `error` for partial opt-out):

```jsonc
// In settings.json
"telemetry.telemetryLevel": "off"
```

Note: at the time of writing, CodeAtlas does not yet honor this setting at runtime
(planned). For full opt-out today, disable network access for the extension or use
firewall rules to block `api2.amplitude.com`.

The Amplitude project is `codeatlas-live-java`. See
[Amplitude's data usage policy](https://amplitude.com/legal/privacy) for how the data
is processed downstream.

---

## Why CodeAtlas?

| Feature | CodeAtlas | Other tools |
|---------|-----------|-------------|
| **Layers** | 6 zoomable layers (system → function) | Usually 1-2 static views |
| **Frameworks** | 30+ auto-detected | Manual configuration |
| **Diff visualization** | 3-channel colorblind-safe across all layers | Basic or none |
| **AI Code Review** | LLM-powered review on diffs with severity bubbles | Separate tool |
| **Timeline Replay** | Cinematic commit walkthrough through all layers | Not available |
| **Health Report** | Dead code, cycles, coupling, god files | Separate linter |
| **Browser mode** | Full UI at localhost:7742 | Editor only |
| **Offline** | Code analysis fully local; anonymous usage telemetry only — see Privacy section | Often cloud-dependent |
| **MCP Server** | AI assistants can query your architecture | Not available |

---

## Supported Frameworks & Languages

**JavaScript/TypeScript:** Express, NestJS, Next.js (App + Pages Router), Nuxt, Remix, SvelteKit, Hono, tRPC, GraphQL, gRPC
**Python:** Django, Django REST Framework, FastAPI, Flask, Starlette
**Java/Kotlin:** Spring Boot, Spring WebFlux, Micronaut, JAX-RS, Ktor
**Go:** Gin, Echo, Chi, Fiber, net/http
**Rust:** Actix, Axum, Rocket
**C#:** ASP.NET Core, Minimal API
**PHP:** Laravel, Symfony
**Ruby:** Rails, Sinatra
**Swift:** Vapor
**Mobile:** Android (Jetpack Compose, Hilt, Room), iOS (SwiftUI, UIKit), React Native, Flutter/Dart, Expo Router

**Infrastructure detection:** MongoDB, PostgreSQL, MySQL, Redis, RabbitMQ, Kafka, Celery, Sidekiq, Prisma, Sequelize, and more.

---

## Quality Gate (for contributors)

Every release is validated against 33 real-world framework repos before publishing:

```bash
npm run fetch:real-projects        # one-time clone of 33 repos (~250 MB) into e2e/real-repos/
npm run verify:real                # regression baseline — fails if pipeline output drops below committed expectations
npm run verify:real:invariants     # 1,159 layered assertions (L1-L5, integrity, drift guard, anchor validity, perf budget)
npm run verify:real:invariants:fast # 5-repo smoke (~3 s) for local dev cycles
```

The suite covers Express, NestJS, Fastify, Next.js, Nuxt, Remix, SvelteKit, tRPC, Apollo, Django, FastAPI, Flask, Spring, Ktor, Gin, Echo, Chi, Fiber, Laravel, Symfony, Rails, Sinatra, Actix, Axum, Rocket, ASP.NET, Vapor, plus mobile (React Native, Flutter, Compose, SwiftUI). See [docs/ADR-008](docs/ADR-008-real-world-verification.md) and [docs/ADR-009](docs/ADR-009-extractor-v32-refinements.md) for the design and what each layer asserts.

---

## Feedback & Support

- Report issues: [GitHub Issues](https://github.com/vamsikk7/codeatlas-live-issues/issues)
- Documentation: [codeatlas.live](https://codeatlas.live)

---

## License

See [LICENSE.md](LICENSE.md)
