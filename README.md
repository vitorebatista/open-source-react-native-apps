# Open-Source React Native Apps

A curated hub for learning React Native by reading real code. This list collects production-grade open-source apps, starter kits, core libraries, and learning resources — so you can go from "hello world" to shipping an app, and study how large teams ship RN in the real world.

[![](https://img.shields.io/badge/Twitter-@vitorebatista-blue.svg)](https://twitter.com/vitorebatista)

> Contributions welcome — open a PR against this README or file an issue suggesting an app, library, or resource.

## Contents

- [AI & On-Device ML](#ai--on-device-ml) `NEW` — running LLMs, vision, and ML inside your RN app
- [Production Apps](#production-apps) — large, actively maintained apps you can learn from
- [Starters & Boilerplates](#starters--boilerplates)
- [Learning Resources](#learning-resources)
- [Core Libraries & Ecosystem](#core-libraries--ecosystem)
- [Sample & Demo Apps](#sample--demo-apps)
- [Classic Apps](#classic-apps) — historically interesting, many unmaintained
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)

---

## AI & On-Device ML

> `NEW` — The fastest-growing area of the React Native ecosystem. Tools for talking to hosted LLMs, running models on-device, and building AI features without leaving JavaScript.

### Agent skills & MCP servers

> Tools that let AI coding agents (Claude Code, Cursor, VS Code, etc.) actually understand and operate your React Native / Expo project.

- **[expo/skills](https://github.com/expo/skills)** — Official Expo "agent skills" pack. A curated collection of nine AI-agent skills covering native UI patterns, data fetching, API routes, custom dev builds, Tailwind styling, CI/CD, and deployment — all teaching agents how to do things *the Expo way*. Install with `bunx skills add expo/skills`. *(1.6k★)*
- **[callstackincubator/agent-skills](https://github.com/callstackincubator/agent-skills)** — Generic React Native agent skills by Callstack. Complements `expo/skills` with framework-agnostic skills: `react-native-best-practices` (perf guide), `upgrading-react-native`, `react-native-brownfield-migration`, plus `github` and `github-actions` workflow patterns. Compatible with Claude Code, Cursor, Codex, and Gemini CLI. *(1.2k★)*
- **[Expo MCP Server](https://docs.expo.dev/eas/ai/mcp/)** — Official MCP server hosted at `mcp.expo.dev`. Gives any MCP-aware agent access to Expo docs, intelligent package installation, config generation, plus local capabilities (screenshots, UI automation, DevTools) when paired with an Expo dev server on SDK 54+. See the [announcement post](https://expo.dev/blog/become-an-ai-native-developer-with-the-expo-mcp-server).

### SDKs & frameworks

- **[vercel/ai](https://github.com/vercel/ai)** — The Vercel AI SDK. The de-facto TypeScript toolkit for building AI features. Has [first-class Expo support](https://ai-sdk.dev/docs/getting-started/expo) via `@ai-sdk/react` (`useChat`, `useCompletion`) and works with every major model provider through one unified API. *(23k★)*
- **[EvanBacon/expo-ai](https://github.com/EvanBacon/expo-ai)** — Reference AI chat app from Expo Router's lead, built on Expo Router + RSC + the Vercel AI SDK with tool calls to OpenAI. The canonical "how does Expo do AI" example. *(842★)*

### On-device LLMs

- **[software-mansion/react-native-executorch](https://github.com/software-mansion/react-native-executorch)** — Declarative on-device AI for React Native, powered by PyTorch's ExecuTorch. Out-of-the-box support for Llama 3.2, Qwen 3, SmolLM 2, plus computer vision and speech models. Maintained by Software Mansion. *(1.4k★)*
- **[callstackincubator/ai](https://github.com/callstackincubator/ai)** — On-device LLM execution for React Native, fully compatible with the Vercel AI SDK (`useChat` etc. work with local models). Powered by MLC LLM Engine. Maintained by Callstack. *(1.3k★)*
- **[mybigday/llama.rn](https://github.com/mybigday/llama.rn)** — Native binding to `llama.cpp` for loading GGUF models in React Native. The lowest-level option, used under the hood by many higher-level libraries. *(897★)*
- **[daviddaytw/react-native-transformers](https://github.com/daviddaytw/react-native-transformers)** — Run Hugging Face transformer models locally via ONNX Runtime. Works in Expo. *(131★)*

### RAG & vision

- **[software-mansion-labs/react-native-rag](https://github.com/software-mansion-labs/react-native-rag)** — Local, offline Retrieval-Augmented Generation. Pairs with `react-native-executorch` for inference and SQLite (via `op-sqlite`) for the vector store. Powers Software Mansion's *Private Mind* app. *(306★)*
- **[mrousavy/react-native-vision-camera](https://github.com/mrousavy/react-native-vision-camera)** — Not AI-specific, but the de-facto camera library and the entry point for any frame-processor-based ML pipeline (MediaPipe, TFLite, custom models).

---

## Production Apps

Real apps shipped to the App Store / Google Play by companies and communities. Reading these codebases is the fastest way to see how RN is used at scale — navigation, state, native modules, CI, testing, monorepos.

- **[Expensify/App](https://github.com/Expensify/App)** — Expensify's New Expensify super-app. One of the largest open-source React Native codebases on GitHub. Ships to iOS, Android, web, and desktop from a single repo.
- **[bluesky-social/social-app](https://github.com/bluesky-social/social-app)** — The official Bluesky client. Excellent reference for a modern Expo + TypeScript social app with a complex feed, lexicons, and i18n.
- **[mattermost/mattermost-mobile](https://github.com/mattermost/mattermost-mobile)** — Mattermost's official mobile client. Strong example of offline-first architecture, WatermelonDB, and WebSocket sync.
- **[RocketChat/Rocket.Chat.ReactNative](https://github.com/RocketChat/Rocket.Chat.ReactNative)** — Rocket.Chat mobile client. Good patterns for realtime chat, E2EE, and navigation.
- **[artsy/eigen](https://github.com/artsy/eigen)** — Artsy's iOS/Android app. Long-running RN codebase with detailed engineering blog posts and GraphQL/Relay usage.
- **[status-im/status-mobile](https://github.com/status-im/status-mobile)** — Ethereum messenger, wallet, and Web3 browser. RN + ClojureScript — unusual but instructive.
- **[jitsi/jitsi-meet](https://github.com/jitsi/jitsi-meet)** — The Jitsi Meet video-conferencing mobile app is built with React Native.
- **[chatwoot/chatwoot-mobile-app](https://github.com/chatwoot/chatwoot-mobile-app)** — Open-source customer engagement platform's mobile client.
- **[tiajinsha/JKVideo](https://github.com/tiajinsha/JKVideo)** — Feature-rich Bilibili-like client. Real-world example of DASH playback, real-time danmaku via WebSocket, global mini-player with Zustand, QR-code login, and offline downloads. RN 0.83 + Expo SDK 55 + expo-router.
- **[alichherawalla/off-grid-mobile](https://github.com/alichherawalla/off-grid-mobile)** — Runs LLMs, vision models, and Stable Diffusion entirely on-device (llama.cpp / llm.rn, Core ML). Excellent reference for on-device ML in React Native.
- **[wordpress-mobile/WordPress-iOS](https://github.com/wordpress-mobile/WordPress-iOS)** / **[WordPress-Android](https://github.com/wordpress-mobile/WordPress-Android)** — Native shells that embed the React Native Gutenberg block editor. See also [gutenberg-mobile](https://github.com/WordPress/gutenberg-mobile).
- **[HabitRPG/habitica-mobile](https://github.com/HabitRPG/habitica-mobile)** — Gamified habit tracker.
- **[gitpoint/git-point](https://github.com/gitpoint/git-point)** — Fully featured GitHub client. Classic reference for Redux + RN structure.
- **[oblador/react-native-vector-icons (example app)](https://github.com/oblador/react-native-vector-icons)** — Not an app, but the example app and fabric integration are widely studied.
- **[microsoft/react-native-windows-samples](https://github.com/microsoft/react-native-windows-samples)** — Samples for running React Native on Windows / Xbox.

## Starters & Boilerplates

Production-ready templates — the fastest way to bootstrap a serious app.

- **[infinitered/ignite](https://github.com/infinitered/ignite)** — Infinite Red's battle-tested boilerplate. Ships with MobX State Tree, Reactotron, TypeScript, and a generators CLI.
- **[akveo/kittenTricks](https://github.com/akveo/kittenTricks)** — Design-system–heavy starter built on UI Kitten. Dozens of screens you can lift wholesale.
- **[expo/examples](https://github.com/expo/examples)** — Official Expo examples for every major library and pattern.
- **[obytes/react-native-template-obytes](https://github.com/obytes/react-native-template-obytes)** — Opinionated Expo + TypeScript + NativeWind + i18n starter.
- **[thecodingmachine/react-native-boilerplate](https://github.com/thecodingmachine/react-native-boilerplate)** — Long-running community boilerplate with clean architecture.
- **[rainbow-me/rainbow](https://github.com/rainbow-me/rainbow)** — Rainbow wallet. Not strictly a "starter" but frequently forked as a reference for a polished, animation-heavy RN app.

## Learning Resources

Official docs and tutorials. Start here if you're new.

- **[React Native docs](https://reactnative.dev)** — Official documentation. The "Guides" section is the canonical starting point.
- **[Expo docs](https://docs.expo.dev)** — Expo is the recommended way to start new RN projects as of the 2024 docs.
- **[React Navigation docs](https://reactnavigation.org)** — The de-facto navigation library. Read the "Fundamentals" guide early.
- **[React Native Directory](https://reactnative.directory)** — Searchable index of RN libraries with platform compatibility and maintenance signals.
- **[reactnative.express](https://www.reactnative.express)** — Free online book, great second stop after the official tutorial.
- **[Ignite Cookbook](https://ignitecookbook.com)** — Recipe-style solutions to common RN problems, curated by Infinite Red.
- **[Callstack blog](https://www.callstack.com/blog)** and **[Software Mansion blog](https://blog.swmansion.com)** — The two companies behind most of the core native-facing libraries (Reanimated, Gesture Handler, Re.Pack, Skia bindings). High-signal engineering writing.

## Core Libraries & Ecosystem

The libraries you'll encounter in almost every serious React Native app.

### Navigation & Routing
- **[react-navigation/react-navigation](https://github.com/react-navigation/react-navigation)** — Default navigation stack.
- **[wix/react-native-navigation](https://github.com/wix/react-native-navigation)** — Fully native navigation alternative.
- **[expo/router](https://github.com/expo/expo/tree/main/packages/expo-router)** — File-based routing built on React Navigation.

### Animation & Gestures
- **[software-mansion/react-native-reanimated](https://github.com/software-mansion/react-native-reanimated)** — The animation library.
- **[software-mansion/react-native-gesture-handler](https://github.com/software-mansion/react-native-gesture-handler)** — Native-threaded gesture system.
- **[Shopify/react-native-skia](https://github.com/Shopify/react-native-skia)** — Skia graphics for RN. Powers complex drawing, charts, shaders.
- **[gorhom/react-native-bottom-sheet](https://github.com/gorhom/react-native-bottom-sheet)** — The standard bottom sheet.

### UI & Styling
- **[callstack/react-native-paper](https://github.com/callstack/react-native-paper)** — Material Design components.
- **[tamagui/tamagui](https://github.com/tamagui/tamagui)** — Universal (RN + web) styling and component system with a compiler.
- **[nativewind/nativewind](https://github.com/nativewind/nativewind)** — Tailwind CSS for React Native.
- **[GeekyAnts/NativeBase](https://github.com/GeekyAnts/NativeBase)** — Component library (maintenance mode but still referenced).
- **[akveo/react-native-ui-kitten](https://github.com/akveo/react-native-ui-kitten)** — Eva Design–based components.

### Lists & Performance
- **[Shopify/flash-list](https://github.com/Shopify/flash-list)** — High-performance list component, drop-in `FlatList` replacement.
- **[software-mansion/react-native-screens](https://github.com/software-mansion/react-native-screens)** — Native screen container primitives.

### Charts & Visualization
- **[Abhinandan-Kushwaha/react-native-gifted-charts](https://github.com/Abhinandan-Kushwaha/react-native-gifted-charts)** — The most-used charting library for React Native: line, bar, pie, donut, stacked, and animated charts.

### Storage & Data
- **[mrousavy/react-native-mmkv](https://github.com/mrousavy/react-native-mmkv)** — Fast key-value storage backed by MMKV.
- **[Nozbe/WatermelonDB](https://github.com/Nozbe/WatermelonDB)** — Reactive, offline-first database for large datasets.
- **[TanStack/query](https://github.com/TanStack/query)** — Server-state caching; works great with RN.
- **[pmndrs/zustand](https://github.com/pmndrs/zustand)** — Minimal state manager that plays well with RN.

### Native & Tooling
- **[expo/expo](https://github.com/expo/expo)** — The Expo platform, SDK, and tools.
- **[mrousavy/react-native-vision-camera](https://github.com/mrousavy/react-native-vision-camera)** — Modern camera library with frame processors.
- **[margelo/react-native-worklets-core](https://github.com/margelo/react-native-worklets-core)** — Run JS on background threads (used by Vision Camera, Skia).
- **[callstack/repack](https://github.com/callstack/repack)** — Webpack-based bundler toolkit for RN, useful for code-splitting and module federation.
- **[jhen0409/react-native-debugger](https://github.com/jhen0409/react-native-debugger)** — Standalone debugger app.

### Universal (RN + Web)
- **[nandorojo/solito](https://github.com/nandorojo/solito)** — React Native + Next.js, share code across mobile and web.
- **[necolas/react-native-web](https://github.com/necolas/react-native-web)** — Run RN components in the browser.

## Sample & Demo Apps

Smaller focused examples — good for reading in one sitting.

- **[react-native-community/releases](https://github.com/react-native-community/releases)** and **[facebook/react-native](https://github.com/facebook/react-native)** — The official RNTester app (`packages/rn-tester`) is the best place to see every core component in isolation.
- **[satya164/PocketGear](https://github.com/satya164/PocketGear)** — Pokédex-style app by the maintainer of React Navigation.
- **[infinitered/ChainReactApp](https://github.com/infinitered/ChainReactApp)** — The Chain React conference app — updated yearly, always reflects current best practices.

## Classic Apps

Older apps kept here for historical reference. Many are unmaintained and target very old RN versions, but the commit history and structure are still educational.

<details><summary>Show classic entries</summary>

- [catalinmiron/react-native-dribbble-app](https://github.com/catalinmiron/react-native-dribbble-app) — Famous early parallax example.
- [7kfpun/FinanceReactNative](https://github.com/7kfpun/FinanceReactNative) — iOS Stocks clone.
- [wwayne/react-native-nba-app](https://github.com/wwayne/react-native-nba-app) — NBA scores app.
- [fbsamples/f8app](https://github.com/fbsamples/f8app) — The original F8 2016 conference app. Historic — the first large open-source RN app Facebook shipped.
- [buildreactnative/assemblies](https://github.com/buildreactnative/assemblies) — Meetup-style clone from a well-known 2016 book.
- [jsdf/ReactNativeHackerNews](https://github.com/jsdf/ReactNativeHackerNews) / [iSimar/HackerNews-React-Native](https://github.com/iSimar/HackerNews-React-Native) — HN clients.
- [brentvatne/react-native-login](https://github.com/brentvatne/react-native-login) — Early Facebook Login example by Brent Vatne.
- [ColinEberhardt/ReactNative-PropertyFinder](https://github.com/ColinEberhardt/ReactNative-PropertyFinder) — Companion app for one of the first widely read RN tutorials.

</details>

## Related Awesome Lists

- **[jondot/awesome-react-native](https://github.com/jondot/awesome-react-native)** — The canonical awesome-list for RN libraries, articles, and tools.
- **[madhavanmalolan/awesome-reactnative-ui](https://github.com/madhavanmalolan/awesome-reactnative-ui)** — RN UI component catalog.
- **[dkhamsing/open-source-ios-apps](https://github.com/dkhamsing/open-source-ios-apps)** — Open-source iOS apps (the original inspiration for this list).
- **[pcqpcq/open-source-android-apps](https://github.com/pcqpcq/open-source-android-apps)** — Open-source Android apps.
- **[Solido/awesome-flutter](https://github.com/Solido/awesome-flutter)** — For cross-referencing with Flutter.

## Contributing

Found a broken link, an app that's no longer maintained, or a great project that belongs here? Open an issue or PR. Guidelines:

- Apps must be **open source** (link to the repo, not just a store page).
- Prefer apps that are **actively maintained** or **historically significant**.
- For libraries, prefer ones that are widely used and still maintained.

## Thanks

This list was originally inspired by [open-source-ios-apps](https://github.com/dkhamsing/open-source-ios-apps). Thanks to all the [contributors](https://github.com/vitorebatista/open-source-react-native-apps/graphs/contributors).

## Contact

- [github.com/vitorebatista](https://github.com/vitorebatista)
- [twitter.com/vitorebatista](https://twitter.com/vitorebatista)
