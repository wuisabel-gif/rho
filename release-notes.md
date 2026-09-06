## Release preparation

This automated PR prepares the next Rho releases. The sections below list each package version, its generated release notes, and the version files that will be updated.

Merging this PR creates draft GitHub releases, validates and publishes the selected crates, publishes the GitHub releases, and builds the release artifacts.
---


<details><summary>rho-agent-tools: 2.0.0</summary>

## [2.0.0](https://github.com/wuisabel-gif/rho/compare/rho-agent-tools-v1.0.2...rho-agent-tools-v2.0.0) (2026-09-06)


###   BREAKING CHANGES

* rho-sdk removes RunEvent::ProviderActivity and the PROVIDER_ACTIVITY_* constants, collapses ProviderStreamResetReason retryable variants into RetryableFailure { kind, retry_after }, removes ModelCallMetrics::output_tokens_per_second, adds revision to RunEvent::Failed, folds ContextEstimated into StepStarted, and replaces the stringly generation-output-token carriers with a typed ModelCallMetrics::generation_output_tokens metric and ModelEvent::GenerationOutputTokens variant. rho-providers adds ProviderId::OpenAiCompatible for config-defined hosts, folds CustomProviderOptions into CustomProviderSpec (removing the _with_lookup/ _with_options funnels), makes providers() include custom hosts (removing visible_providers), removes deprecated registry API-base re-exports and ProviderRuntime::same_family, and drops the CredentialStore parameter from OpenAiProvider::new_with_identity. rho-tools removes the edit_file tool-name alias, the write_file frontmatter alias, and the EditToolKind type alias.

### Features

* **acp:** let hosts set reasoning through thought_level ([#1015](https://github.com/wuisabel-gif/rho/issues/1015)) ([5cda8e8](https://github.com/wuisabel-gif/rho/commit/5cda8e8308682fa13c9d6001ec12989f0d030bb4))
* **config:** mid-session edit tool, advisor, and auto preference ([#840](https://github.com/wuisabel-gif/rho/issues/840)) ([423d026](https://github.com/wuisabel-gif/rho/commit/423d02690edee36a6dc692ac25d8fd9013d33139))
* **documents:** add bounded document extraction and attachments ([#669](https://github.com/wuisabel-gif/rho/issues/669)) ([d1ec3cd](https://github.com/wuisabel-gif/rho/commit/d1ec3cd5d8f5683c7b8de0047070a6029bb1ec33))
* **permission:** rename Auto to Bypass and add classifier Auto ([#870](https://github.com/wuisabel-gif/rho/issues/870)) ([3192daa](https://github.com/wuisabel-gif/rho/commit/3192daa713f7202f44727ec4acb83d0c646d1286))
* **sessions:** add workspace rewind checkpoints ([#638](https://github.com/wuisabel-gif/rho/issues/638)) ([5a90b2d](https://github.com/wuisabel-gif/rho/commit/5a90b2db5b1170f2701cbac1c0c7d056f9158754))
* **subagents:** add parent-child plain-text messaging for Rho runtime ([#852](https://github.com/wuisabel-gif/rho/issues/852)) ([dd25d8e](https://github.com/wuisabel-gif/rho/commit/dd25d8e3e48fd531e777e31fcad9c948a2a9ebfe))
* **tools:** add in-process grep and glob workspace tools ([#554](https://github.com/wuisabel-gif/rho/issues/554)) ([e422a99](https://github.com/wuisabel-gif/rho/commit/e422a990332afff330b096d8960d4e0fa07a5838))
* **tools:** add selectable edit formats ([#820](https://github.com/wuisabel-gif/rho/issues/820)) ([5db37d0](https://github.com/wuisabel-gif/rho/commit/5db37d0bf714afbf28e91e3f0e66c2e8b807b659))
* **tools:** extract pdf content with pdf-inspector ([#687](https://github.com/wuisabel-gif/rho/issues/687)) ([ce92355](https://github.com/wuisabel-gif/rho/commit/ce92355e74a56ab11d7f2cf35ff3d246e34310d2))
* **tools:** mint hashline tags only for the hashline edit tool ([#1000](https://github.com/wuisabel-gif/rho/issues/1000)) ([2fa3c2c](https://github.com/wuisabel-gif/rho/commit/2fa3c2c35280f79cb53826cf3cc863421fcd18d0))
* **tools:** replace edit_file with codex-style apply_patch ([#653](https://github.com/wuisabel-gif/rho/issues/653)) ([eef1555](https://github.com/wuisabel-gif/rho/commit/eef155521c5492b9c7f34507e82b6b7f46b896a8))
* **tools:** restore simple edit_file ([#658](https://github.com/wuisabel-gif/rho/issues/658)) ([ffac70f](https://github.com/wuisabel-gif/rho/commit/ffac70f6d58d1532a4eedefbdc99463402adbf7b))
* **tui:** borderless code, mermaid, and math blocks with syntect highlighting ([#825](https://github.com/wuisabel-gif/rho/issues/825)) ([f0614a8](https://github.com/wuisabel-gif/rho/commit/f0614a88d035f0465adbddccc830207d5366450f))
* **tui:** count up shell runtime next to timeout ([#871](https://github.com/wuisabel-gif/rho/issues/871)) ([7c55124](https://github.com/wuisabel-gif/rho/commit/7c55124aa43fb40db414c7be01ab68e36dfb0441))
* **tui:** stream apply_patch diff cards ([#657](https://github.com/wuisabel-gif/rho/issues/657)) ([e2c932e](https://github.com/wuisabel-gif/rho/commit/e2c932e377f15ddfaab1e4700aa7d6f4e8ed0417))
* **tui:** unify tool transcript cards as Call + Children ([#586](https://github.com/wuisabel-gif/rho/issues/586)) ([ce52cdd](https://github.com/wuisabel-gif/rho/commit/ce52cddb6dbf0ac1b2878b6f3bd468a87547f8fa))
* **xai:** let grok generate and edit images in the conversation ([#967](https://github.com/wuisabel-gif/rho/issues/967)) ([47c03c1](https://github.com/wuisabel-gif/rho/commit/47c03c1d2b13864d32a69b27c21da4db54572e0e))


### Bug Fixes

* **agents:** clarify foreground agent batch behavior ([#606](https://github.com/wuisabel-gif/rho/issues/606)) ([9574e48](https://github.com/wuisabel-gif/rho/commit/9574e4836a3c6e14eb28bc5863b8d2abc334e140))
* **deps:** patch h2, lopdf, webbrowser, and quick-xml CVEs ([#1069](https://github.com/wuisabel-gif/rho/issues/1069)) ([453be34](https://github.com/wuisabel-gif/rho/commit/453be34aadd44faa3063bf813fd14007e95c2774))
* **errors:** surface failures that were silently swallowed ([#546](https://github.com/wuisabel-gif/rho/issues/546)) ([1d4eee3](https://github.com/wuisabel-gif/rho/commit/1d4eee3ea2e45d459897198d48babbe3ded3bf19))
* **sdk:** recover failed 1.17.1 release packaging ([#587](https://github.com/wuisabel-gif/rho/issues/587)) ([224189e](https://github.com/wuisabel-gif/rho/commit/224189e2d4fc2ec5f23cb88d80065d82c91ef40b))
* **sdk:** recover failed 1.32.0 release packaging ([#792](https://github.com/wuisabel-gif/rho/issues/792)) ([a782145](https://github.com/wuisabel-gif/rho/commit/a782145820f2924a47140f9e8cd8e3cbd13be8a3))
* **tools:** reject shell timeout_seconds of zero consistently ([#843](https://github.com/wuisabel-gif/rho/issues/843)) ([c379aec](https://github.com/wuisabel-gif/rho/commit/c379aeca8ad0dd2ad53a33df66f967782206db78))
* **tools:** scrub provider credential env vars from child processes ([#502](https://github.com/wuisabel-gif/rho/issues/502)) ([6d66913](https://github.com/wuisabel-gif/rho/commit/6d669135caa7aa160f8c81c109f0c99736b70e63))
* **tools:** search a named file path ([#1084](https://github.com/wuisabel-gif/rho/issues/1084)) ([f9dc51b](https://github.com/wuisabel-gif/rho/commit/f9dc51b45bf2dd8bdd6eab9bba04ee2e57db5759))
* **tui:** drop duplicate paths on multi-file edit cards ([#826](https://github.com/wuisabel-gif/rho/issues/826)) ([16c98e3](https://github.com/wuisabel-gif/rho/commit/16c98e3c1898cbb885e71366a940efeaa52aa688))
* **tui:** paste image paths and fall back kitty under herdr ([#504](https://github.com/wuisabel-gif/rho/issues/504)) ([c140bfe](https://github.com/wuisabel-gif/rho/commit/c140bfe6994f4ffc42756075ec801eff6e63ce40))
* **tui:** validate dropped file attachments ([#677](https://github.com/wuisabel-gif/rho/issues/677)) ([1c62a3d](https://github.com/wuisabel-gif/rho/commit/1c62a3d638328bc829350f1cf32649fd58f7abcb))


### Performance Improvements

* cut hot-path costs in grep, session persistence, and live TUI rendering ([#1027](https://github.com/wuisabel-gif/rho/issues/1027)) ([9cf4ad7](https://github.com/wuisabel-gif/rho/commit/9cf4ad73149ebcaffbe760481618cac9bb02a061))
* **tools:** cut tokens from web, process, and shell results ([#980](https://github.com/wuisabel-gif/rho/issues/980)) ([c103ec0](https://github.com/wuisabel-gif/rho/commit/c103ec0d6d46896f735074413369cc471c95a750))
* **tools:** stream hashline digest, zero-alloc grep lines, and dirty-check shell stream ([#927](https://github.com/wuisabel-gif/rho/issues/927)) ([580a774](https://github.com/wuisabel-gif/rho/commit/580a7742e6f268240874bf0df4987353c90bf4b4))


### Code Refactoring

* pay down all NEXT_MAJOR debt for the next major, net -986 lines ([#1062](https://github.com/wuisabel-gif/rho/issues/1062)) ([0e17bdb](https://github.com/wuisabel-gif/rho/commit/0e17bdb5e9fa21440fffbbe00171830ac0d1d3c2))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * rho-sdk bumped from 5.1.0 to 6.0.0
</details>

<details><summary>rho-coding-agent: 3.0.0</summary>

## [3.0.0](https://github.com/wuisabel-gif/rho/compare/rho-coding-agent-v2.3.1...rho-coding-agent-v3.0.0) (2026-09-06)


###   BREAKING CHANGES

* rho-sdk removes RunEvent::ProviderActivity and the PROVIDER_ACTIVITY_* constants, collapses ProviderStreamResetReason retryable variants into RetryableFailure { kind, retry_after }, removes ModelCallMetrics::output_tokens_per_second, adds revision to RunEvent::Failed, folds ContextEstimated into StepStarted, and replaces the stringly generation-output-token carriers with a typed ModelCallMetrics::generation_output_tokens metric and ModelEvent::GenerationOutputTokens variant. rho-providers adds ProviderId::OpenAiCompatible for config-defined hosts, folds CustomProviderOptions into CustomProviderSpec (removing the _with_lookup/ _with_options funnels), makes providers() include custom hosts (removing visible_providers), removes deprecated registry API-base re-exports and ProviderRuntime::same_family, and drops the CredentialStore parameter from OpenAiProvider::new_with_identity. rho-tools removes the edit_file tool-name alias, the write_file frontmatter alias, and the EditToolKind type alias.
* **providers:** own HTTP transport errors and collapse reqwest onto 0.13 ([#1060](https://github.com/wuisabel-gif/rho/issues/1060))
* **hooks:** `AuthorizationDenialKind` and `ApprovalAuditDecision` gain a hook variant. Both are `#[non_exhaustive]`, so only exhaustive matches written before this change need updating.
* **xai:** ModelEvent::WebSearch and RunEvent::WebSearch now carry a name field so hosts can distinguish web_search from x_search.

### Features

* **acp:** let hosts discover and switch models per-session ([#1012](https://github.com/wuisabel-gif/rho/issues/1012)) ([9ddaf37](https://github.com/wuisabel-gif/rho/commit/9ddaf373c90565248896044e57fa9d7da8c8efee))
* **acp:** let hosts set reasoning through thought_level ([#1015](https://github.com/wuisabel-gif/rho/issues/1015)) ([5cda8e8](https://github.com/wuisabel-gif/rho/commit/5cda8e8308682fa13c9d6001ec12989f0d030bb4))
* add advisor mode with a selectable advisor model ([#752](https://github.com/wuisabel-gif/rho/issues/752)) ([13c1ebb](https://github.com/wuisabel-gif/rho/commit/13c1ebb89edfde2924ee760c7621b099fd510708))
* add native MCP client and Agent Plugins ([#776](https://github.com/wuisabel-gif/rho/issues/776)) ([c148fa4](https://github.com/wuisabel-gif/rho/commit/c148fa4319d37190e1c084977b573d6e4fef9ce6))
* **advisor:** add selectable advisor reasoning level ([#767](https://github.com/wuisabel-gif/rho/issues/767)) ([b9eb143](https://github.com/wuisabel-gif/rho/commit/b9eb1437b629aa4c7ce89ed2e8f12bea3e7d99f8))
* **advisor:** run the advisor on Claude Code from the model picker ([#833](https://github.com/wuisabel-gif/rho/issues/833)) ([b663739](https://github.com/wuisabel-gif/rho/commit/b6637391a4ade6edcc14bc5b98d7f7790d5a0a68))
* **agents:** add Claude Code subagent runtime ([#541](https://github.com/wuisabel-gif/rho/issues/541)) ([c1385ec](https://github.com/wuisabel-gif/rho/commit/c1385ecae9b2eb967ae73ecc09c20cc80bc63479))
* **agents:** allow pinning auth profiles on rho agents ([#781](https://github.com/wuisabel-gif/rho/issues/781)) ([3e1f691](https://github.com/wuisabel-gif/rho/commit/3e1f691e693dd93bf888cb5c3eb3093a7169525a))
* **attach:** expand tool cards on click and ctrl+o ([#911](https://github.com/wuisabel-gif/rho/issues/911)) ([061bf10](https://github.com/wuisabel-gif/rho/commit/061bf10e1aa28b435eac2a9a46458074ec2c15f3))
* **attach:** honor hide-reasoning and other display config ([#873](https://github.com/wuisabel-gif/rho/issues/873)) ([813f22f](https://github.com/wuisabel-gif/rho/commit/813f22ff4651da1c716ad13dcb6e4553ca3f117d))
* **attach:** show live tok/s in the subagent attach header ([#1011](https://github.com/wuisabel-gif/rho/issues/1011)) ([75f2db5](https://github.com/wuisabel-gif/rho/commit/75f2db5dd9c61e07436f2d4775111fb9e9b6b98c))
* **attach:** show reasoning level next to model and provider ([#1044](https://github.com/wuisabel-gif/rho/issues/1044)) ([2b1f912](https://github.com/wuisabel-gif/rho/commit/2b1f912e1233b5769e250a4bf53538661afa9126))
* **auth:** add active auth mode switcher ([#609](https://github.com/wuisabel-gif/rho/issues/609)) ([a2b0f68](https://github.com/wuisabel-gif/rho/commit/a2b0f68f71033ca6f8594a35368a79b2388916ca))
* **auth:** always show a copyable login URL across every provider ([#1095](https://github.com/wuisabel-gif/rho/issues/1095)) ([9e2670b](https://github.com/wuisabel-gif/rho/commit/9e2670bd0892c579cad5f1d916046c16632ec9e1))
* **claude-cli:** show Claude tool names on attach cards ([#909](https://github.com/wuisabel-gif/rho/issues/909)) ([1bcdaba](https://github.com/wuisabel-gif/rho/commit/1bcdabaf2bdf1a5d991adf6330b95f1bddaf503f))
* **cli:** expand export formats and session browsing ([#725](https://github.com/wuisabel-gif/rho/issues/725)) ([037aaf5](https://github.com/wuisabel-gif/rho/commit/037aaf56ed9b2cf60e1020bd18851f8d003b7046))
* **cli:** let editor hosts drive Rho over stdio ([#910](https://github.com/wuisabel-gif/rho/issues/910)) ([3f10136](https://github.com/wuisabel-gif/rho/commit/3f10136d39ed6a428a4b4e7dca40c2fec882fe67))
* **cli:** open the tui with the first prompt already running ([#1003](https://github.com/wuisabel-gif/rho/issues/1003)) ([20b9d43](https://github.com/wuisabel-gif/rho/commit/20b9d43b4dcb71f231f1022e7c2e4c4d48a8a9b4))
* **config:** mid-session edit tool, advisor, and auto preference ([#840](https://github.com/wuisabel-gif/rho/issues/840)) ([423d026](https://github.com/wuisabel-gif/rho/commit/423d02690edee36a6dc692ac25d8fd9013d33139))
* **documents:** add bounded document extraction and attachments ([#669](https://github.com/wuisabel-gif/rho/issues/669)) ([d1ec3cd](https://github.com/wuisabel-gif/rho/commit/d1ec3cd5d8f5683c7b8de0047070a6029bb1ec33))
* **hooks:** add typed lifecycle hooks ([#668](https://github.com/wuisabel-gif/rho/issues/668)) ([4a69c3d](https://github.com/wuisabel-gif/rho/commit/4a69c3dfbc2136a8c23dff515909e23886b8651f))
* **mcp:** add prompts, resources, elicitation, and sampling ([#837](https://github.com/wuisabel-gif/rho/issues/837)) ([29cf0ea](https://github.com/wuisabel-gif/rho/commit/29cf0ea8e6179df94826c18b857cf6f20120be3e))
* **mcp:** allow opt-in cleartext http for remote servers ([#1072](https://github.com/wuisabel-gif/rho/issues/1072)) ([15abb91](https://github.com/wuisabel-gif/rho/commit/15abb91d34c257be5f9d0ac841bde112f1b6a81a))
* **mcp:** answer server-initiated protocol traffic ([#834](https://github.com/wuisabel-gif/rho/issues/834)) ([95104ea](https://github.com/wuisabel-gif/rho/commit/95104ea6f4bb910604688b69b0724cccc90dde9a))
* **mcp:** authorize remote servers with OAuth 2.1 ([#838](https://github.com/wuisabel-gif/rho/issues/838)) ([1971a19](https://github.com/wuisabel-gif/rho/commit/1971a19a0e425f7a2b4887757b2a25c6e250ffca))
* **mcp:** render tool results by content kind ([#836](https://github.com/wuisabel-gif/rho/issues/836)) ([9ac86ea](https://github.com/wuisabel-gif/rho/commit/9ac86ead85ce742a1d3567f94000174ca636a0ab))
* **openai:** add fast mode ([#610](https://github.com/wuisabel-gif/rho/issues/610)) ([8c5cd6d](https://github.com/wuisabel-gif/rho/commit/8c5cd6d19e1758b85fc25c345769e49426f10ad0))
* **permission:** let Auto skip review of tracked workspace edits ([#892](https://github.com/wuisabel-gif/rho/issues/892)) ([2babff2](https://github.com/wuisabel-gif/rho/commit/2babff25ddd4788433adbdb40babf38a59c4ec29))
* **permission:** rename Auto to Bypass and add classifier Auto ([#870](https://github.com/wuisabel-gif/rho/issues/870)) ([3192daa](https://github.com/wuisabel-gif/rho/commit/3192daa713f7202f44727ec4acb83d0c646d1286))
* **permission:** screen Auto requests with a two-stage classifier ([#893](https://github.com/wuisabel-gif/rho/issues/893)) ([4149f11](https://github.com/wuisabel-gif/rho/commit/4149f1157aa2c8ee10561a21a919a0e530b8f3cc))
* **prompt:** prefer top-down mermaid flowcharts ([#849](https://github.com/wuisabel-gif/rho/issues/849)) ([ed7d59a](https://github.com/wuisabel-gif/rho/commit/ed7d59ae39d24ddc7a08a69f441309c126ca0981))
* **prompt:** put session cwd in the system prompt ([#857](https://github.com/wuisabel-gif/rho/issues/857)) ([e614d9b](https://github.com/wuisabel-gif/rho/commit/e614d9b942869caa6cd36139bc08ad038c63b982))
* **prompt:** tell the agent which model runs it, its subagents, and the advisor ([#860](https://github.com/wuisabel-gif/rho/issues/860)) ([d18c377](https://github.com/wuisabel-gif/rho/commit/d18c3774a20657cc1214e2936251cc993b69dd14))
* **providers:** add Meta Model API and collapse provider registration ([#755](https://github.com/wuisabel-gif/rho/issues/755)) ([b41ef92](https://github.com/wuisabel-gif/rho/commit/b41ef92dcbeeba12351df4711f4817761fda0a79))
* **providers:** add MiniMax as a first-party Anthropic-compatible host ([#1059](https://github.com/wuisabel-gif/rho/issues/1059)) ([aa71132](https://github.com/wuisabel-gif/rho/commit/aa7113215ed9601dd9bf74241a031febd9ee2c85))
* **providers:** add Ollama Cloud API provider ([#597](https://github.com/wuisabel-gif/rho/issues/597)) ([f6a62dd](https://github.com/wuisabel-gif/rho/commit/f6a62ddb8c77bae1f6ba386328b79db625ec1e5d))
* **providers:** add Qwen Token Plan OpenAI-compatible provider ([#738](https://github.com/wuisabel-gif/rho/issues/738)) ([6aa6df2](https://github.com/wuisabel-gif/rho/commit/6aa6df2e812674b721bedd3b65c7c2cdb359a1e4))
* **providers:** add xAI server-side context compaction ([#542](https://github.com/wuisabel-gif/rho/issues/542)) ([2d43f13](https://github.com/wuisabel-gif/rho/commit/2d43f134669414b3d9b7332a4c9d17aaa1346d9f))
* **providers:** let /login add custom hosts that work with CLIProxyAPI ([#984](https://github.com/wuisabel-gif/rho/issues/984)) ([5ec9a44](https://github.com/wuisabel-gif/rho/commit/5ec9a445db5ff9c47cc814d2cbd282172c827a5a))
* **providers:** let config name openai-compatible hosts ([#888](https://github.com/wuisabel-gif/rho/issues/888)) ([a87649a](https://github.com/wuisabel-gif/rho/commit/a87649a9e76332f53f125c52e7eccd8a14bc14f1))
* **providers:** let custom hosts speak OpenAI Responses ([#1041](https://github.com/wuisabel-gif/rho/issues/1041)) ([381383d](https://github.com/wuisabel-gif/rho/commit/381383d9f5f5d13746e23518d152075b63e6128d))
* **providers:** look up models.dev from custom host model ids ([#1004](https://github.com/wuisabel-gif/rho/issues/1004)) ([da477da](https://github.com/wuisabel-gif/rho/commit/da477da84b401f3bc2b299e481851dfd5278aded))
* **providers:** read Ollama context and thinking from native tags ([#993](https://github.com/wuisabel-gif/rho/issues/993)) ([dfd0f01](https://github.com/wuisabel-gif/rho/commit/dfd0f0145ac26a34365f16446bc924ef1de125b5))
* **providers:** set up ollama through /login instead of first-run defaults ([#994](https://github.com/wuisabel-gif/rho/issues/994)) ([1fbe5f8](https://github.com/wuisabel-gif/rho/commit/1fbe5f853d9f9b8f02251b5e9dbad2258e82a20c))
* **providers:** sign in to OpenCode Go and use its models ([#913](https://github.com/wuisabel-gif/rho/issues/913)) ([db501a6](https://github.com/wuisabel-gif/rho/commit/db501a6ab5b64c44114d6ecf1a1bf3a75ac597b6))
* **providers:** use OpenAI server-side compaction for codex and api-key ([#514](https://github.com/wuisabel-gif/rho/issues/514)) ([b18eadd](https://github.com/wuisabel-gif/rho/commit/b18eadd6752de2945361cd59a60ffc4cc7b807ad))
* **questionnaire:** add focused default selection ([#530](https://github.com/wuisabel-gif/rho/issues/530)) ([47d1853](https://github.com/wuisabel-gif/rho/commit/47d185377a68881c96db18ee186b3173215e39ee))
* **questionnaire:** support choice descriptions ([#510](https://github.com/wuisabel-gif/rho/issues/510)) ([066899c](https://github.com/wuisabel-gif/rho/commit/066899c2ad12ca23c2b7772de4b0a6a3c6161497))
* **sessions:** add /title and sessions rename ([#660](https://github.com/wuisabel-gif/rho/issues/660)) ([fe492d3](https://github.com/wuisabel-gif/rho/commit/fe492d35fdb5123fbe8d268290e9f19f500f4304))
* **sessions:** add workspace rewind checkpoints ([#638](https://github.com/wuisabel-gif/rho/issues/638)) ([5a90b2d](https://github.com/wuisabel-gif/rho/commit/5a90b2db5b1170f2701cbac1c0c7d056f9158754))
* **sessions:** delete sessions and cascade parent-linked runs ([#563](https://github.com/wuisabel-gif/rho/issues/563)) ([ded020d](https://github.com/wuisabel-gif/rho/commit/ded020d6763c2d078ed245b4ead2bd5c1790c394))
* **sessions:** nest subagent artifacts with parent sessions ([#567](https://github.com/wuisabel-gif/rho/issues/567)) ([3edf433](https://github.com/wuisabel-gif/rho/commit/3edf433d691e1d5f6d3525334fade75025349d32))
* **skills:** add built-in rho-config skill ([#685](https://github.com/wuisabel-gif/rho/issues/685)) ([91abfaf](https://github.com/wuisabel-gif/rho/commit/91abfaf2c3bbca4a21a9aac32ff53f30f918dfee))
* **subagents:** add parent-child plain-text messaging for Rho runtime ([#852](https://github.com/wuisabel-gif/rho/issues/852)) ([dd25d8e](https://github.com/wuisabel-gif/rho/commit/dd25d8e3e48fd531e777e31fcad9c948a2a9ebfe))
* **subagents:** enable parent messaging for claude-cli children ([#854](https://github.com/wuisabel-gif/rho/issues/854)) ([22caf60](https://github.com/wuisabel-gif/rho/commit/22caf6070f32b5152913255bbdd050091eba90cc))
* **subagents:** route background questionnaires to parent ([#539](https://github.com/wuisabel-gif/rho/issues/539)) ([e0cab31](https://github.com/wuisabel-gif/rho/commit/e0cab3182e9fc833fbf304c7dad5714f73b89952))
* **tools:** add in-process grep and glob workspace tools ([#554](https://github.com/wuisabel-gif/rho/issues/554)) ([e422a99](https://github.com/wuisabel-gif/rho/commit/e422a990332afff330b096d8960d4e0fa07a5838))
* **tools:** add selectable edit formats ([#820](https://github.com/wuisabel-gif/rho/issues/820)) ([5db37d0](https://github.com/wuisabel-gif/rho/commit/5db37d0bf714afbf28e91e3f0e66c2e8b807b659))
* **tools:** extract pdf content with pdf-inspector ([#687](https://github.com/wuisabel-gif/rho/issues/687)) ([ce92355](https://github.com/wuisabel-gif/rho/commit/ce92355e74a56ab11d7f2cf35ff3d246e34310d2))
* **tools:** mint hashline tags only for the hashline edit tool ([#1000](https://github.com/wuisabel-gif/rho/issues/1000)) ([2fa3c2c](https://github.com/wuisabel-gif/rho/commit/2fa3c2c35280f79cb53826cf3cc863421fcd18d0))
* **tools:** replace edit_file with codex-style apply_patch ([#653](https://github.com/wuisabel-gif/rho/issues/653)) ([eef1555](https://github.com/wuisabel-gif/rho/commit/eef155521c5492b9c7f34507e82b6b7f46b896a8))
* **tools:** restore simple edit_file ([#658](https://github.com/wuisabel-gif/rho/issues/658)) ([ffac70f](https://github.com/wuisabel-gif/rho/commit/ffac70f6d58d1532a4eedefbdc99463402adbf7b))
* **tui:** add /changelog for recent release notes ([#681](https://github.com/wuisabel-gif/rho/issues/681)) ([4269020](https://github.com/wuisabel-gif/rho/commit/4269020cc967173ab7efbc2a30a65677658baa65))
* **tui:** add /clear and /usage command aliases ([#942](https://github.com/wuisabel-gif/rho/issues/942)) ([312ada1](https://github.com/wuisabel-gif/rho/commit/312ada1608d93984904e1b3481d86b8aa0128397))
* **tui:** add /copy for the last assistant message ([#998](https://github.com/wuisabel-gif/rho/issues/998)) ([991c147](https://github.com/wuisabel-gif/rho/commit/991c1471a94e67260ef3bad3aa986166903920df))
* **tui:** add /sessions hub for cross-directory session management ([#818](https://github.com/wuisabel-gif/rho/issues/818)) ([5a933db](https://github.com/wuisabel-gif/rho/commit/5a933db1cb5c1c6029234a8be8ef54eaa1f824b6))
* **tui:** add /side overlay for frozen-context asides ([#1094](https://github.com/wuisabel-gif/rho/issues/1094)) ([3ebbdf9](https://github.com/wuisabel-gif/rho/commit/3ebbdf951f01c6a32e827d4b819bdd9441c76684))
* **tui:** add composer prompt marker ([#614](https://github.com/wuisabel-gif/rho/issues/614)) ([1994ff5](https://github.com/wuisabel-gif/rho/commit/1994ff5280bf60fc4594d4a602fa8ab60c88f052))
* **tui:** add help overlay and clarify shell mode ([#515](https://github.com/wuisabel-gif/rho/issues/515)) ([f1e4d20](https://github.com/wuisabel-gif/rho/commit/f1e4d201ee559c385413d50b8b7eb451fb298815))
* **tui:** add in-app editor for user-defined agents ([#630](https://github.com/wuisabel-gif/rho/issues/630)) ([7243fcc](https://github.com/wuisabel-gif/rho/commit/7243fcce4c7261d38547a9e3c9e5a51aea7e9db0))
* **tui:** add model handoff compaction choice ([#513](https://github.com/wuisabel-gif/rho/issues/513)) ([c7bdf84](https://github.com/wuisabel-gif/rho/commit/c7bdf8439672dc4f741db3ab505accad1ff2dac1))
* **tui:** add zen mode display policy ([#736](https://github.com/wuisabel-gif/rho/issues/736)) ([0f1d4c5](https://github.com/wuisabel-gif/rho/commit/0f1d4c5c809240d60af179ca5afdd96096c36580))
* **tui:** borderless code, mermaid, and math blocks with syntect highlighting ([#825](https://github.com/wuisabel-gif/rho/issues/825)) ([f0614a8](https://github.com/wuisabel-gif/rho/commit/f0614a88d035f0465adbddccc830207d5366450f))
* **tui:** bundle popular color schemes as built-in themes ([#1014](https://github.com/wuisabel-gif/rho/issues/1014)) ([b0a1ad6](https://github.com/wuisabel-gif/rho/commit/b0a1ad622f19684d1b47e528171e38225031c04e))
* **tui:** count up shell runtime next to timeout ([#871](https://github.com/wuisabel-gif/rho/issues/871)) ([7c55124](https://github.com/wuisabel-gif/rho/commit/7c55124aa43fb40db414c7be01ab68e36dfb0441))
* **tui:** create agents from a guided slash command ([#1057](https://github.com/wuisabel-gif/rho/issues/1057)) ([b14e4d9](https://github.com/wuisabel-gif/rho/commit/b14e4d9ca92c50b3c4ab7079d7cc1ed5aac3359f))
* **tui:** cycle pinned models without opening the catalogue ([#988](https://github.com/wuisabel-gif/rho/issues/988)) ([c0d0292](https://github.com/wuisabel-gif/rho/commit/c0d029261852a91ae24ec5ced355de8ef7c876f9))
* **tui:** edit composer in external editor ([#523](https://github.com/wuisabel-gif/rho/issues/523)) ([113e8c4](https://github.com/wuisabel-gif/rho/commit/113e8c43929b1981d9d9a00ed97873c1db4628cd))
* **tui:** explain hidden tool cards in zen mode ([#1037](https://github.com/wuisabel-gif/rho/issues/1037)) ([f523866](https://github.com/wuisabel-gif/rho/commit/f523866e8cf9dd459cedde2cfb8858700944f1d0))
* **tui:** flag finished turns on the jump chip and toast collapsed pastes ([#1021](https://github.com/wuisabel-gif/rho/issues/1021)) ([a16a4d4](https://github.com/wuisabel-gif/rho/commit/a16a4d4de94ac1c09a39ed9970dce0cf74053569))
* **tui:** fold advisor cost into session total ([#761](https://github.com/wuisabel-gif/rho/issues/761)) ([2360599](https://github.com/wuisabel-gif/rho/commit/23605992b408199c60cd79d9441e6aceab5bfef2))
* **tui:** include subagent costs in status and info ([#548](https://github.com/wuisabel-gif/rho/issues/548)) ([9517f00](https://github.com/wuisabel-gif/rho/commit/9517f0012dd2001213fd10294287f8a0739e5d2c))
* **tui:** keep Entry::Error readable without color ([#866](https://github.com/wuisabel-gif/rho/issues/866)) ([1cf70d2](https://github.com/wuisabel-gif/rho/commit/1cf70d2f13b85651131864f22cc2b06f1755ea02))
* **tui:** keep up-arrow prompts across sessions ([#982](https://github.com/wuisabel-gif/rho/issues/982)) ([5ec18c2](https://github.com/wuisabel-gif/rho/commit/5ec18c240d49a4473203b10969b7e3445873a4e4))
* **tui:** lift tool-card text on hover in main TUI and attach ([#928](https://github.com/wuisabel-gif/rho/issues/928)) ([344f79a](https://github.com/wuisabel-gif/rho/commit/344f79a49cf5c4fa754c87a18d6b53b34bcffe5d))
* **tui:** make MCP tool cards readable instead of raw wire names and JSON blobs ([#1092](https://github.com/wuisabel-gif/rho/issues/1092)) ([c57ba6c](https://github.com/wuisabel-gif/rho/commit/c57ba6cf79a75d627af37c977c5b2d4f9535a2d7))
* **tui:** make the activity rail a trustworthy ambient view of agents and jobs ([#1049](https://github.com/wuisabel-gif/rho/issues/1049)) ([d1c2289](https://github.com/wuisabel-gif/rho/commit/d1c2289d8fc1d94212d5dbcd46bac97a71513010))
* **tui:** make the composer mouse-selectable ([#832](https://github.com/wuisabel-gif/rho/issues/832)) ([3cc9490](https://github.com/wuisabel-gif/rho/commit/3cc9490f724a077ea69f19fd8599eaefeb7aac11))
* **tui:** open a full-screen setup on the first launch ([#715](https://github.com/wuisabel-gif/rho/issues/715)) ([19b14b5](https://github.com/wuisabel-gif/rho/commit/19b14b53c5693de91de870b4ef6b2a1ca1146e42))
* **tui:** open or copy subagent attach from the activity rail ([#552](https://github.com/wuisabel-gif/rho/issues/552)) ([95e4ca6](https://github.com/wuisabel-gif/rho/commit/95e4ca698ab92f858587356ba16e29476bcfd972))
* **tui:** oversized mermaid diagrams now clip instead of dumping source ([#1082](https://github.com/wuisabel-gif/rho/issues/1082)) ([0f52503](https://github.com/wuisabel-gif/rho/commit/0f5250344452dfe4d6aaac537f6874e36ba77cad))
* **tui:** paint everyday mermaid instead of dumping source ([#974](https://github.com/wuisabel-gif/rho/issues/974)) ([076444b](https://github.com/wuisabel-gif/rho/commit/076444bd7fe0d1790e571068a0de11ca25e83da4))
* **tui:** paint gitGraph, gantt, and mindmap in the transcript ([#1088](https://github.com/wuisabel-gif/rho/issues/1088)) ([e22adb6](https://github.com/wuisabel-gif/rho/commit/e22adb64c84d5480de317290ed8477a180e93b91))
* **tui:** pick Chat Completions or Responses when adding a custom host ([#1042](https://github.com/wuisabel-gif/rho/issues/1042)) ([586c995](https://github.com/wuisabel-gif/rho/commit/586c9954134f1b241ee6e5d8a31056d22977be8e))
* **tui:** pick running subagents by title instead of run id ([#950](https://github.com/wuisabel-gif/rho/issues/950)) ([dffd205](https://github.com/wuisabel-gif/rho/commit/dffd2053eb4d22bc0b86d364c31fc44c8317667d))
* **tui:** print a compact session receipt after interactive exit ([#1077](https://github.com/wuisabel-gif/rho/issues/1077)) ([4f75c2a](https://github.com/wuisabel-gif/rho/commit/4f75c2acf885529a960b39df00422a43be8775f5))
* **tui:** queue follow-ups with Ctrl+Enter when Alt+Enter is fullscreen ([#1064](https://github.com/wuisabel-gif/rho/issues/1064)) ([67cd423](https://github.com/wuisabel-gif/rho/commit/67cd423e8d7f8f99e23eafea425d99df53aaa910))
* **tui:** regroup the /config category browser ([#983](https://github.com/wuisabel-gif/rho/issues/983)) ([bf0008b](https://github.com/wuisabel-gif/rho/commit/bf0008bbef289d607f7fdaf2572de7005fd8efc8))
* **tui:** render display and inline math with txm ([#770](https://github.com/wuisabel-gif/rho/issues/770)) ([c681deb](https://github.com/wuisabel-gif/rho/commit/c681deb6097d36dcccc5bf5f5ef05b513751f824))
* **tui:** render workflow dependencies as a graph ([#779](https://github.com/wuisabel-gif/rho/issues/779)) ([fc8bdd9](https://github.com/wuisabel-gif/rho/commit/fc8bdd9bcfc3541fca183fc14951a03ebb1a5fe5))
* **tui:** scale feed image height with the history viewport ([#856](https://github.com/wuisabel-gif/rho/issues/856)) ([3bee525](https://github.com/wuisabel-gif/rho/commit/3bee5251f7f2e61e19cbdf7cfd8c85d32b891ac8))
* **tui:** selectable color themes with live preview ([#817](https://github.com/wuisabel-gif/rho/issues/817)) ([c43ba0e](https://github.com/wuisabel-gif/rho/commit/c43ba0efbd89ee7eb88ff4716f56697c346737ff))
* **tui:** show /limits in a single-pane overlay ([#940](https://github.com/wuisabel-gif/rho/issues/940)) ([273b830](https://github.com/wuisabel-gif/rho/commit/273b830d42b8225eb7dbc416515aacbeb1567590))
* **tui:** show how long a turn took ([#1038](https://github.com/wuisabel-gif/rho/issues/1038)) ([7b45897](https://github.com/wuisabel-gif/rho/commit/7b458979af6250f159e26005acef0988ccb5bd5a))
* **tui:** show live background processes in the activity rail ([#935](https://github.com/wuisabel-gif/rho/issues/935)) ([f396b72](https://github.com/wuisabel-gif/rho/commit/f396b72542abf17c2ef108c91bfa04351125031a))
* **tui:** show model output token rate ([#623](https://github.com/wuisabel-gif/rho/issues/623)) ([a5aa688](https://github.com/wuisabel-gif/rho/commit/a5aa688686d9f4f08d064462ccfa4fd542aa979d))
* **tui:** show OpenCode Go usage bars in /limits ([#930](https://github.com/wuisabel-gif/rho/issues/930)) ([2ea9628](https://github.com/wuisabel-gif/rho/commit/2ea9628e05f6118677bc7f508d125a389150c98e))
* **tui:** show prompt-cache misses in /info and optional notices ([#989](https://github.com/wuisabel-gif/rho/issues/989)) ([4b35cb6](https://github.com/wuisabel-gif/rho/commit/4b35cb661a75e355bd0405a39a7b1dcace7a1c43))
* **tui:** show provider label next to model in statusline ([#686](https://github.com/wuisabel-gif/rho/issues/686)) ([274c18b](https://github.com/wuisabel-gif/rho/commit/274c18b805074d9cce0c0ea95db0ec48c876ece9))
* **tui:** show runtime and elapsed in attach header ([#816](https://github.com/wuisabel-gif/rho/issues/816)) ([0ab34fc](https://github.com/wuisabel-gif/rho/commit/0ab34fc02f304d4c6f88cfc9cfb647e6a22b8397))
* **tui:** show the advisor on the composer divider ([#968](https://github.com/wuisabel-gif/rho/issues/968)) ([3af67ce](https://github.com/wuisabel-gif/rho/commit/3af67ce3da780dedc0fe35c28e82bcaf0fc7e858))
* **tui:** show the current github pr on the statusline ([#1067](https://github.com/wuisabel-gif/rho/issues/1067)) ([cccee94](https://github.com/wuisabel-gif/rho/commit/cccee943c17250727447f691aac6f736e4890eb7))
* **tui:** soft-wash diff add/remove rows with readable content ([#867](https://github.com/wuisabel-gif/rho/issues/867)) ([bfccb02](https://github.com/wuisabel-gif/rho/commit/bfccb02516e71d187f4799d3692c9750a19e9c09))
* **tui:** spatial workflow graph navigation, mouse pan, and skip-edge routing ([#823](https://github.com/wuisabel-gif/rho/issues/823)) ([e691235](https://github.com/wuisabel-gif/rho/commit/e69123517ea35fa2fb78922e8ed6da5be671cc2f))
* **tui:** stream apply_patch diff cards ([#657](https://github.com/wuisabel-gif/rho/issues/657)) ([e2c932e](https://github.com/wuisabel-gif/rho/commit/e2c932e377f15ddfaab1e4700aa7d6f4e8ed0417))
* **tui:** stream mermaid diagrams as they arrive instead of popping in at fence close ([#1085](https://github.com/wuisabel-gif/rho/issues/1085)) ([29c70cc](https://github.com/wuisabel-gif/rho/commit/29c70cc5a0b28f66b13006dac8d3d6e4b01a31fa))
* **tui:** unify pickers, scroll both panes, fuzzy-match visible fields, size overlays to content ([#805](https://github.com/wuisabel-gif/rho/issues/805)) ([8a60fbf](https://github.com/wuisabel-gif/rho/commit/8a60fbfd6761a986263c4077a81a688d37b6172a))
* **tui:** unify tool transcript cards as Call + Children ([#586](https://github.com/wuisabel-gif/rho/issues/586)) ([ce52cdd](https://github.com/wuisabel-gif/rho/commit/ce52cddb6dbf0ac1b2878b6f3bd468a87547f8fa))
* **tui:** wake the agent when a background process exits ([#934](https://github.com/wuisabel-gif/rho/issues/934)) ([b3b4ada](https://github.com/wuisabel-gif/rho/commit/b3b4adac05f09390f475b7a9bde2d07976d09d5d))
* **tui:** watch subagents in the same terminal ([#1002](https://github.com/wuisabel-gif/rho/issues/1002)) ([966f3e8](https://github.com/wuisabel-gif/rho/commit/966f3e8315f8d2c39f91ef31577aa4b81f3a1e80))
* **web:** prefer hosted search with backup provider config ([#649](https://github.com/wuisabel-gif/rho/issues/649)) ([2e136e9](https://github.com/wuisabel-gif/rho/commit/2e136e9025ebc318f7fac5da8e45a3134d785430))
* **workflow:** add deterministic DAG workflows ([#680](https://github.com/wuisabel-gif/rho/issues/680)) ([77f36f9](https://github.com/wuisabel-gif/rho/commit/77f36f9cc6992f78ab59ac481a1f2dc4e00350a0))
* **xai:** let grok generate and edit images in the conversation ([#967](https://github.com/wuisabel-gif/rho/issues/967)) ([47c03c1](https://github.com/wuisabel-gif/rho/commit/47c03c1d2b13864d32a69b27c21da4db54572e0e))
* **xai:** support hosted x_search tool ([#647](https://github.com/wuisabel-gif/rho/issues/647)) ([cd0c897](https://github.com/wuisabel-gif/rho/commit/cd0c897570376cf39d2d99b40c58c55b22fc6133))


### Bug Fixes

* **advisor:** discourage first-turn advisor calls ([#969](https://github.com/wuisabel-gif/rho/issues/969)) ([cec3198](https://github.com/wuisabel-gif/rho/commit/cec3198841c18ae9d75459f3efd3c3a6f38ab011))
* **advisor:** stop Claude plan mode from poisoning guidance ([#853](https://github.com/wuisabel-gif/rho/issues/853)) ([5209474](https://github.com/wuisabel-gif/rho/commit/52094742d99a2f53fa2bafb377f4df44abba0f39))
* **advisor:** stop the reviewer from inventing empty-call failures ([#961](https://github.com/wuisabel-gif/rho/issues/961)) ([061fbbe](https://github.com/wuisabel-gif/rho/commit/061fbbe7040eebbc1caa07021b1e1c609fc6ea09))
* **advisor:** stream guidance into the tool card ([#796](https://github.com/wuisabel-gif/rho/issues/796)) ([465c3ed](https://github.com/wuisabel-gif/rho/commit/465c3eded483699a2a0fc397af5eec75b8720a72))
* **agents:** clarify foreground agent batch behavior ([#606](https://github.com/wuisabel-gif/rho/issues/606)) ([9574e48](https://github.com/wuisabel-gif/rho/commit/9574e4836a3c6e14eb28bc5863b8d2abc334e140))
* **anthropic:** derive reasoning levels from models api capabilities ([#907](https://github.com/wuisabel-gif/rho/issues/907)) ([f057529](https://github.com/wuisabel-gif/rho/commit/f057529128be880c640e5dd9b5d5e42071eed792))
* **anthropic:** stop opus 5 from sending thinking.type.enabled ([#904](https://github.com/wuisabel-gif/rho/issues/904)) ([d76a398](https://github.com/wuisabel-gif/rho/commit/d76a3984d37d299850de6fabf9d7135c047c137c))
* **attach:** keep recording at high token rates ([#824](https://github.com/wuisabel-gif/rho/issues/824)) ([d4fec84](https://github.com/wuisabel-gif/rho/commit/d4fec8494dfd125023ef1af195fede058df9a6e4))
* **attach:** list only this directory's subagents in the picker ([#951](https://github.com/wuisabel-gif/rho/issues/951)) ([9fc35d9](https://github.com/wuisabel-gif/rho/commit/9fc35d99b6c0d004788d802cacfd3fd8920210d9))
* **attach:** open an empty picker and include finished runs ([#955](https://github.com/wuisabel-gif/rho/issues/955)) ([7055695](https://github.com/wuisabel-gif/rho/commit/7055695654674f4b051e3adcc589ed6adb049acf))
* **auth:** prefer credential-backed auth and fix Ollama Cloud reasoning ([#619](https://github.com/wuisabel-gif/rho/issues/619)) ([1a57f6f](https://github.com/wuisabel-gif/rho/commit/1a57f6f24292b63a6ba4ba314843c2fb308792cf))
* **auth:** restore ollama device test key dir on unwind and isolate temp dir ([#621](https://github.com/wuisabel-gif/rho/issues/621)) ([d2a345d](https://github.com/wuisabel-gif/rho/commit/d2a345df56b1ae815007829a04cc21172500530d))
* **auth:** stop waiting for Ollama device callback ([#616](https://github.com/wuisabel-gif/rho/issues/616)) ([54288d2](https://github.com/wuisabel-gif/rho/commit/54288d28f7bcc68a36f0424e5de6c28e470fb479))
* **ci:** repair macOS stdin guard and supervised approval PTY smoke ([#1055](https://github.com/wuisabel-gif/rho/issues/1055)) ([8b6654f](https://github.com/wuisabel-gif/rho/commit/8b6654ff86b34cd4f2a41d11520085f0a1ea5c01))
* **claude-cli:** keep Auto dontAsk on the bound tool set ([#903](https://github.com/wuisabel-gif/rho/issues/903)) ([fb2de07](https://github.com/wuisabel-gif/rho/commit/fb2de0793939ce4034303718efadb03fba858ab9))
* **claude:** surface stream-json API errors on nonzero exit ([#847](https://github.com/wuisabel-gif/rho/issues/847)) ([29ac39c](https://github.com/wuisabel-gif/rho/commit/29ac39cd3b59e4bd9c7b850488cc108b9a0b41ba))
* **cli:** show changelog for dependency-only releases ([#919](https://github.com/wuisabel-gif/rho/issues/919)) ([3488499](https://github.com/wuisabel-gif/rho/commit/34884997edf2f582cbd1952ef530214786f19b51))
* **config:** warn on bad keys and stop silent CLI auto-save ([#731](https://github.com/wuisabel-gif/rho/issues/731)) ([83cfa9d](https://github.com/wuisabel-gif/rho/commit/83cfa9d346b8a6da5af434ce963f6108cbe8ed62))
* **errors:** print user-facing errors without Debug dumps ([#728](https://github.com/wuisabel-gif/rho/issues/728)) ([e8a98d7](https://github.com/wuisabel-gif/rho/commit/e8a98d72e4b8e87ac9320b4efdb8cf07b3fa887f))
* **errors:** surface failures that were silently swallowed ([#546](https://github.com/wuisabel-gif/rho/issues/546)) ([1d4eee3](https://github.com/wuisabel-gif/rho/commit/1d4eee3ea2e45d459897198d48babbe3ded3bf19))
* exclude reasoning tokens from throughput ([#819](https://github.com/wuisabel-gif/rho/issues/819)) ([d261b5b](https://github.com/wuisabel-gif/rho/commit/d261b5b35bfb119f49a81d83b33ca06b62b383e7))
* **mcp:** escape underscore-edged exported tool names ([#1096](https://github.com/wuisabel-gif/rho/issues/1096)) ([86c7ea1](https://github.com/wuisabel-gif/rho/commit/86c7ea15e28d4ff237823e5f1c26ae22479bcf94))
* **metrics:** include reasoning latency in output rate ([#632](https://github.com/wuisabel-gif/rho/issues/632)) ([7f7fa39](https://github.com/wuisabel-gif/rho/commit/7f7fa39d88e3032a4433a105e07a785989406944))
* **models:** stop clamping GPT-5.5 and GPT-5.6 context to 272k ([#966](https://github.com/wuisabel-gif/rho/issues/966)) ([c5984e5](https://github.com/wuisabel-gif/rho/commit/c5984e5d04d6f4ab1d24c250cb6b2e74c4362187))
* **permission:** stop silent reads of files outside the workspace ([#1033](https://github.com/wuisabel-gif/rho/issues/1033)) ([21e5e20](https://github.com/wuisabel-gif/rho/commit/21e5e20d5727b6c72132c819495114d3d9788150))
* **plugins:** gate project plugins behind workspace trust ([#1030](https://github.com/wuisabel-gif/rho/issues/1030)) ([60297fc](https://github.com/wuisabel-gif/rho/commit/60297fc5396f53729f78c0b5e034d96748fc9abe))
* **plugins:** silence clippy failures on main ([#790](https://github.com/wuisabel-gif/rho/issues/790)) ([b44151d](https://github.com/wuisabel-gif/rho/commit/b44151d0d40dfbfda4bf23b49feb88d6bb0bdff3))
* **process:** terminate process tree when shell leader exits ([#1023](https://github.com/wuisabel-gif/rho/issues/1023)) ([d53747e](https://github.com/wuisabel-gif/rho/commit/d53747e16ba2553543de4c21493d16c8d8a9f228))
* **prompt:** guide agents to use supported mermaid diagrams ([#555](https://github.com/wuisabel-gif/rho/issues/555)) ([a92c928](https://github.com/wuisabel-gif/rho/commit/a92c928b684fc54fdb89152ba395b972e33fb45e))
* **prompt:** wait for catalog names before model labels ([#863](https://github.com/wuisabel-gif/rho/issues/863)) ([71fa544](https://github.com/wuisabel-gif/rho/commit/71fa544e86e5dd046b898be76632996d92915c19))
* **providers:** keep a stored custom key after /login and restart ([#995](https://github.com/wuisabel-gif/rho/issues/995)) ([5e404f6](https://github.com/wuisabel-gif/rho/commit/5e404f6d584dcfe1ec22ffbe2fa2b472754d6cca))
* **providers:** keep anthropic tool schemas typed after composition strip ([#753](https://github.com/wuisabel-gif/rho/issues/753)) ([207e74c](https://github.com/wuisabel-gif/rho/commit/207e74cc577d4c7c905f9bcf6b6b49e7153c9db5))
* **providers:** keep prompt-cache hits across tool turns ([#1040](https://github.com/wuisabel-gif/rho/issues/1040)) ([e139d99](https://github.com/wuisabel-gif/rho/commit/e139d99e6abb4e0ee9315305958e357da3afe715))
* **providers:** source Meta Muse Spark reasoning from models.dev ([#758](https://github.com/wuisabel-gif/rho/issues/758)) ([a11eea0](https://github.com/wuisabel-gif/rho/commit/a11eea0756cedfd2f1bb879603355c28a9c4a037))
* **providers:** surface rate-limit reset time and /limits pointer ([#733](https://github.com/wuisabel-gif/rho/issues/733)) ([b9371fc](https://github.com/wuisabel-gif/rho/commit/b9371fc69fb9b195f9f400d872195c91f031a6b2))
* **release:** recover provider 2.1.0 ([#1099](https://github.com/wuisabel-gif/rho/issues/1099)) ([15f9403](https://github.com/wuisabel-gif/rho/commit/15f9403a38c9edf62f7bd46900b05299e99a48ea))
* **run:** keep error detail and stabilize automation contracts ([#735](https://github.com/wuisabel-gif/rho/issues/735)) ([d7bb0dd](https://github.com/wuisabel-gif/rho/commit/d7bb0ddcbc69703b5a8e1f9499792290f83985e3))
* **sdk:** recover failed 1.17.1 release packaging ([#587](https://github.com/wuisabel-gif/rho/issues/587)) ([224189e](https://github.com/wuisabel-gif/rho/commit/224189e2d4fc2ec5f23cb88d80065d82c91ef40b))
* **sdk:** recover failed 1.32.0 release packaging ([#792](https://github.com/wuisabel-gif/rho/issues/792)) ([a782145](https://github.com/wuisabel-gif/rho/commit/a782145820f2924a47140f9e8cd8e3cbd13be8a3))
* **sessions:** generate titles after first turn ([#652](https://github.com/wuisabel-gif/rho/issues/652)) ([4b55d26](https://github.com/wuisabel-gif/rho/commit/4b55d26ca0330aba4c2ec024c37e66ade3aa7bb3))
* **sessions:** resolve sessions by id from any directory ([#492](https://github.com/wuisabel-gif/rho/issues/492)) ([f88ff1b](https://github.com/wuisabel-gif/rho/commit/f88ff1b38cecbfebbc1046be14f9e0964c45d364))
* **session:** v1 upgrades no longer write an unloadable transcript ([#939](https://github.com/wuisabel-gif/rho/issues/939)) ([1dc1002](https://github.com/wuisabel-gif/rho/commit/1dc1002c5c60ddc2a2889a12d92ead905cd4b6d3))
* **skills:** load skills with nested metadata ([#901](https://github.com/wuisabel-gif/rho/issues/901)) ([b75c6e6](https://github.com/wuisabel-gif/rho/commit/b75c6e69ad1310a18dd54f3900f8f8f323ff9c47))
* **subagents:** allow questionnaire on parent-bridged delegated runs ([#851](https://github.com/wuisabel-gif/rho/issues/851)) ([127510b](https://github.com/wuisabel-gif/rho/commit/127510bd0a7098233f5d46ee7b7a13f82e754f87))
* **subagents:** run multi-agent batches in parallel ([#544](https://github.com/wuisabel-gif/rho/issues/544)) ([7dd6706](https://github.com/wuisabel-gif/rho/commit/7dd6706f6aade0a45d70336a42d259b4a3c12a4f))
* **subagents:** tolerate concurrent session subagents dir creation ([#1020](https://github.com/wuisabel-gif/rho/issues/1020)) ([0a68625](https://github.com/wuisabel-gif/rho/commit/0a68625102e153321119d98ca7655e18e36e6890))
* **tools:** allow file paths outside workspace ([#537](https://github.com/wuisabel-gif/rho/issues/537)) ([8a3cc24](https://github.com/wuisabel-gif/rho/commit/8a3cc24468e89bb509fefbefced738b706b1e43d))
* **tools:** block private fetch targets with resolve-then-check SSRF guard ([#499](https://github.com/wuisabel-gif/rho/issues/499)) ([5dbc11c](https://github.com/wuisabel-gif/rho/commit/5dbc11c9f8692d9d46f9c1008b87de054c9fb3df))
* **tools:** pin fetch connections to SSRF-vetted addresses ([#572](https://github.com/wuisabel-gif/rho/issues/572)) ([45cdd40](https://github.com/wuisabel-gif/rho/commit/45cdd40b144fb5f5045bf28bce0c712e949750f1)), closes [#525](https://github.com/wuisabel-gif/rho/issues/525)
* **tools:** scrub provider credential env vars from child processes ([#502](https://github.com/wuisabel-gif/rho/issues/502)) ([6d66913](https://github.com/wuisabel-gif/rho/commit/6d669135caa7aa160f8c81c109f0c99736b70e63))
* **tui-pty:** simplify proof-plate palette and version pin ([#810](https://github.com/wuisabel-gif/rho/issues/810)) ([8553e91](https://github.com/wuisabel-gif/rho/commit/8553e915e7cd4ea0ac74a8724e8d08fc634e32f3))
* **tui:** adapt reasoning contrast to terminal palette ([#582](https://github.com/wuisabel-gif/rho/issues/582)) ([5361522](https://github.com/wuisabel-gif/rho/commit/53615229f2a7c160763757636b48c9e5d7d72526))
* **tui:** add statusline hierarchy and severity escalation ([#720](https://github.com/wuisabel-gif/rho/issues/720)) ([befb91b](https://github.com/wuisabel-gif/rho/commit/befb91bdb5b750166cc6d6ebe18790c648c512a8))
* **tui:** applied steers now show up in the transcript ([#1032](https://github.com/wuisabel-gif/rho/issues/1032)) ([48ee37f](https://github.com/wuisabel-gif/rho/commit/48ee37f4aa21aae896a02c24e4eadaaad1242523))
* **tui:** bound inline shell output and size pickers to the terminal ([#634](https://github.com/wuisabel-gif/rho/issues/634)) ([3535df4](https://github.com/wuisabel-gif/rho/commit/3535df45f9168a75b75bee60c0c16165fb923b2b))
* **tui:** clear bare slash when Esc dismisses command palette ([#1054](https://github.com/wuisabel-gif/rho/issues/1054)) ([465897d](https://github.com/wuisabel-gif/rho/commit/465897de2b9175215cf6f71531f601ffe0c95926))
* **tui:** collapse soft-wrap break spaces at emit ([#744](https://github.com/wuisabel-gif/rho/issues/744)) ([0490a4d](https://github.com/wuisabel-gif/rho/commit/0490a4d5de3d73ce69abaf48391212c12ef9c1f0))
* **tui:** compile smoke_injection for release chrome version ([#828](https://github.com/wuisabel-gif/rho/issues/828)) ([3ef3357](https://github.com/wuisabel-gif/rho/commit/3ef335773845e583789c1540ad5498e35a38c883))
* **tui:** correct attach token breakdown and add scrollbar ([#550](https://github.com/wuisabel-gif/rho/issues/550)) ([fbe18e7](https://github.com/wuisabel-gif/rho/commit/fbe18e750d180ab911ce85f12301735cea6246e1))
* **tui:** drop duplicate paths on multi-file edit cards ([#826](https://github.com/wuisabel-gif/rho/issues/826)) ([16c98e3](https://github.com/wuisabel-gif/rho/commit/16c98e3c1898cbb885e71366a940efeaa52aa688))
* **tui:** filter /agents reasoning choices by models.dev capabilities ([#1005](https://github.com/wuisabel-gif/rho/issues/1005)) ([098a9d1](https://github.com/wuisabel-gif/rho/commit/098a9d1d7d4c0aacd64ee734262fa51a78b0e1ed))
* **tui:** floor terminal size and keep composer visible ([#727](https://github.com/wuisabel-gif/rho/issues/727)) ([392aba1](https://github.com/wuisabel-gif/rho/commit/392aba18d08e499cfbcf3babc8c2d7f4510d5a74))
* **tui:** keep activity rail and hide Thinking... in zen mode ([#742](https://github.com/wuisabel-gif/rho/issues/742)) ([d377de7](https://github.com/wuisabel-gif/rho/commit/d377de7275bfc5b7abeea5079974a24f0156b019))
* **tui:** keep activity rail text readable on terminal themes ([#1065](https://github.com/wuisabel-gif/rho/issues/1065)) ([98bb0eb](https://github.com/wuisabel-gif/rho/commit/98bb0ebc1a6f1e72bac66925a0e424dd415de10f))
* **tui:** keep critical context fill visible in narrow statuslines ([#1052](https://github.com/wuisabel-gif/rho/issues/1052)) ([e497dbd](https://github.com/wuisabel-gif/rho/commit/e497dbd1dc9103fd1e35cfde4cf8d7f34b37c120))
* **tui:** keep cwd basename visible in status line ([#591](https://github.com/wuisabel-gif/rho/issues/591)) ([3390a4d](https://github.com/wuisabel-gif/rho/commit/3390a4d6ad8954d2c4bcc712cff664777c7aaa36))
* **tui:** keep empty /model guidance in the transcript ([#1034](https://github.com/wuisabel-gif/rho/issues/1034)) ([42e7e87](https://github.com/wuisabel-gif/rho/commit/42e7e8792786a2f16373181b7a9acd2c8a9e6dfd))
* **tui:** keep full resume scrollback ([#956](https://github.com/wuisabel-gif/rho/issues/956)) ([553f3fc](https://github.com/wuisabel-gif/rho/commit/553f3fc0d5305189f6cadf5c003fd2d5b6eb4b89))
* **tui:** keep images visible across viewport clipping ([#1100](https://github.com/wuisabel-gif/rho/issues/1100)) ([4c50ca6](https://github.com/wuisabel-gif/rho/commit/4c50ca677a6af8fd177380d90278c7af0ca1fb88))
* **tui:** keep markdown list markers with long tokens ([#611](https://github.com/wuisabel-gif/rho/issues/611)) ([90dafc9](https://github.com/wuisabel-gif/rho/commit/90dafc9901cc75eefcf096011c463f6e7d9043d0))
* **tui:** keep mermaid loops from gluing onto skip edges ([#1087](https://github.com/wuisabel-gif/rho/issues/1087)) ([5baa60d](https://github.com/wuisabel-gif/rho/commit/5baa60d6e70a422e3af045f2dd25467a5bb07c3f))
* **tui:** keep picker keybinds from clipping mid-hint ([#996](https://github.com/wuisabel-gif/rho/issues/996)) ([f7bca1e](https://github.com/wuisabel-gif/rho/commit/f7bca1eedbb2c6f1b86bc14426a5d30948b9d614))
* **tui:** keep stable prose while stream emphasis completes ([#598](https://github.com/wuisabel-gif/rho/issues/598)) ([2f61fb0](https://github.com/wuisabel-gif/rho/commit/2f61fb044939dcb86ede9db205bfe7e94e957d42))
* **tui:** keep the history scrollbar from darkening on tool cards ([#1063](https://github.com/wuisabel-gif/rho/issues/1063)) ([5f69a8c](https://github.com/wuisabel-gif/rho/commit/5f69a8cee685f8500e5c2bc17b41021d98ca7afa))
* **tui:** keep Thinking... on the Thought for row ([#1047](https://github.com/wuisabel-gif/rho/issues/1047)) ([9f01d0b](https://github.com/wuisabel-gif/rho/commit/9f01d0b560644d8707cc6164e229c9d03defd4c5))
* **tui:** keep up-arrow history out of the command palette ([#990](https://github.com/wuisabel-gif/rho/issues/990)) ([3a5b048](https://github.com/wuisabel-gif/rho/commit/3a5b0481d6f00e54862b48af6cfb37cd31549631))
* **tui:** keep Worked for off the last line of the reply ([#1046](https://github.com/wuisabel-gif/rho/issues/1046)) ([eb3099d](https://github.com/wuisabel-gif/rho/commit/eb3099d941305268ea3d28194392af6c38a62dd6))
* **tui:** lead approval prompts with the command ([#846](https://github.com/wuisabel-gif/rho/issues/846)) ([413063c](https://github.com/wuisabel-gif/rho/commit/413063c9d169e10ca369d83172fbbb952619f07c))
* **tui:** let you cancel claude-code login before the handoff ([#953](https://github.com/wuisabel-gif/rho/issues/953)) ([849ba3b](https://github.com/wuisabel-gif/rho/commit/849ba3b74ad3eb34afd20e0bb9ab1e17addb4d72))
* **tui:** let you type while compact runs on the main loop ([#957](https://github.com/wuisabel-gif/rho/issues/957)) ([07ef7c1](https://github.com/wuisabel-gif/rho/commit/07ef7c14719427e4a77a23056761ca6f7532954f))
* **tui:** lighten overlay chrome and fix picker polish ([#581](https://github.com/wuisabel-gif/rho/issues/581)) ([1ee1cdf](https://github.com/wuisabel-gif/rho/commit/1ee1cdfcfbe72c6d74436d4a4ee356af2c6cf151))
* **tui:** live drag selection highlight and screen-wide text copy ([#633](https://github.com/wuisabel-gif/rho/issues/633)) ([71e6a35](https://github.com/wuisabel-gif/rho/commit/71e6a35279ea63885be460124b262c4ce4339a86))
* **tui:** make active-turn controls visible ([#1028](https://github.com/wuisabel-gif/rho/issues/1028)) ([1246e44](https://github.com/wuisabel-gif/rho/commit/1246e4458ab842384c21de9de935f2da5ff5697a))
* **tui:** make add/remove diff wash visible on sampled themes ([#1086](https://github.com/wuisabel-gif/rho/issues/1086)) ([4f660a0](https://github.com/wuisabel-gif/rho/commit/4f660a035de61d864b992a643358758d7dee4b56))
* **tui:** match during-turn ctrl-c quit hint to idle ([#726](https://github.com/wuisabel-gif/rho/issues/726)) ([7d8e818](https://github.com/wuisabel-gif/rho/commit/7d8e818af4ce1f462c586bfcee2321d1409307ed))
* **tui:** omit trailing blank on open stream entries ([#531](https://github.com/wuisabel-gif/rho/issues/531)) ([5bb0046](https://github.com/wuisabel-gif/rho/commit/5bb0046c93bca07e80a7dffcfb3b1bf46a701bbb))
* **tui:** open approval prompts at the start and default to deny ([#636](https://github.com/wuisabel-gif/rho/issues/636)) ([59efc07](https://github.com/wuisabel-gif/rho/commit/59efc07b26bf67597ebbe05551cd22f3affedc96))
* **tui:** open workflow hub when workspace has no workflows ([#693](https://github.com/wuisabel-gif/rho/issues/693)) ([ff8d51c](https://github.com/wuisabel-gif/rho/commit/ff8d51c680ba91f8e226624aa3c37edce579e543))
* **tui:** paste image paths and fall back kitty under herdr ([#504](https://github.com/wuisabel-gif/rho/issues/504)) ([c140bfe](https://github.com/wuisabel-gif/rho/commit/c140bfe6994f4ffc42756075ec801eff6e63ce40))
* **tui:** place pending input below active work ([#1097](https://github.com/wuisabel-gif/rho/issues/1097)) ([c3cf135](https://github.com/wuisabel-gif/rho/commit/c3cf135d521fbdf5fc7ba1ecf6ae8973b5648587))
* **tui:** preserve newlines in multi-line tool header wrap ([#608](https://github.com/wuisabel-gif/rho/issues/608)) ([1194088](https://github.com/wuisabel-gif/rho/commit/11940882591bc4b2f752ae9456e9d1bb4de77e53))
* **tui:** prompt for Auto classifier model at startup ([#877](https://github.com/wuisabel-gif/rho/issues/877)) ([c8cba48](https://github.com/wuisabel-gif/rho/commit/c8cba4879f6e7b698412ee098ee86ea506deed85))
* **tui:** raise paste collapse threshold to 5 lines ([#729](https://github.com/wuisabel-gif/rho/issues/729)) ([7267f54](https://github.com/wuisabel-gif/rho/commit/7267f54fd23aabec94a48351c8218bb9795f2ee3))
* **tui:** refresh the github pr chip after create ([#1080](https://github.com/wuisabel-gif/rho/issues/1080)) ([af367bd](https://github.com/wuisabel-gif/rho/commit/af367bd80a5326b26d0670842fb47d48be61cdf4))
* **tui:** render command suggestions above composer ([#612](https://github.com/wuisabel-gif/rho/issues/612)) ([9a81647](https://github.com/wuisabel-gif/rho/commit/9a81647aace42ea97b461dcd17112dbd3f1a8459))
* **tui:** render mermaid state start and end without empty boxes ([#1089](https://github.com/wuisabel-gif/rho/issues/1089)) ([8545b9f](https://github.com/wuisabel-gif/rho/commit/8545b9ff34a940d44a703e81df01dd45461f7be5))
* **tui:** render narrow mermaid flowcharts and explain fallbacks ([#565](https://github.com/wuisabel-gif/rho/issues/565)) ([0bf7ad7](https://github.com/wuisabel-gif/rho/commit/0bf7ad719fa32d00bc6d1bc7857307032fd9f1f6))
* **tui:** report generation token throughput ([#803](https://github.com/wuisabel-gif/rho/issues/803)) ([4772f68](https://github.com/wuisabel-gif/rho/commit/4772f68ccad3fc1edf65aa666d9a49f74bfab960))
* **tui:** report herdr blocked during questionnaire ([#500](https://github.com/wuisabel-gif/rho/issues/500)) ([1dcdbe9](https://github.com/wuisabel-gif/rho/commit/1dcdbe9e86bb61cf0cd55a705c28941d9dfcb241))
* **tui:** report missing clipboard image helpers clearly ([#549](https://github.com/wuisabel-gif/rho/issues/549)) ([774e965](https://github.com/wuisabel-gif/rho/commit/774e965e851ca622197ffb0e5469d69db270967a))
* **tui:** resolve dim chrome from bright black, not white ([#741](https://github.com/wuisabel-gif/rho/issues/741)) ([4b41737](https://github.com/wuisabel-gif/rho/commit/4b4173784da5d9d9654f2a258661d97ff4524011))
* **tui:** reuse tool stream previews and allow codex parallel tools ([#566](https://github.com/wuisabel-gif/rho/issues/566)) ([fa0074a](https://github.com/wuisabel-gif/rho/commit/fa0074ae125972ac533ae09b30915f7e479674bd))
* **tui:** share mermaid fan-out source stems ([#562](https://github.com/wuisabel-gif/rho/issues/562)) ([e244b45](https://github.com/wuisabel-gif/rho/commit/e244b45ddae6a0f227cb4003b6e809342dbb696c))
* **tui:** show codex fast mode and report tier fallback ([#663](https://github.com/wuisabel-gif/rho/issues/663)) ([177043f](https://github.com/wuisabel-gif/rho/commit/177043f5022a1798ae45b0d987e6c6ceaf470d1c))
* **tui:** show context tokens when no window limit is reported ([#1019](https://github.com/wuisabel-gif/rho/issues/1019)) ([a4d8909](https://github.com/wuisabel-gif/rho/commit/a4d890987535c09c1ac8469977e87c1100b6a9df))
* **tui:** show help shortcut descriptions ([#613](https://github.com/wuisabel-gif/rho/issues/613)) ([3e8a034](https://github.com/wuisabel-gif/rho/commit/3e8a034385e28c9cbc48ac973167eba9a92a9579))
* **tui:** show hosted x_search tool cards ([#662](https://github.com/wuisabel-gif/rho/issues/662)) ([4381667](https://github.com/wuisabel-gif/rho/commit/438166754b79645d31b4fcefd92b3ea665567c94))
* **tui:** show relative age in resume picker ([#723](https://github.com/wuisabel-gif/rho/issues/723)) ([a1654d8](https://github.com/wuisabel-gif/rho/commit/a1654d85e3cbf9d71b839d05834648d98cd612e7))
* **tui:** silence routine status toast noise ([#721](https://github.com/wuisabel-gif/rho/issues/721)) ([1559dae](https://github.com/wuisabel-gif/rho/commit/1559daeee657fe0f96bf3e23fb349273594314b2))
* **tui:** skip modifyOtherKeys on Windows under ConPTY ([#507](https://github.com/wuisabel-gif/rho/issues/507)) ([2bb3b49](https://github.com/wuisabel-gif/rho/commit/2bb3b49f2435714dc010ba6fe21cb088acd8f115))
* **tui:** smooth external editor terminal handoff ([#527](https://github.com/wuisabel-gif/rho/issues/527)) ([387e355](https://github.com/wuisabel-gif/rho/commit/387e355e1ce049df1920ff96147b9108e9c33f52))
* **tui:** smooth streamed text and hold bare tool previews ([#590](https://github.com/wuisabel-gif/rho/issues/590)) ([591d271](https://github.com/wuisabel-gif/rho/commit/591d2715b04a4e836648b2e7a4db1dc41cf5119b))
* **tui:** sort slash commands and provider pickers alphabetically ([#498](https://github.com/wuisabel-gif/rho/issues/498)) ([0e2c16c](https://github.com/wuisabel-gif/rho/commit/0e2c16cd9b5ac6b5c9c28259a09c0428f64a72ab))
* **tui:** stabilize live stream tool cards and markdown previews ([#595](https://github.com/wuisabel-gif/rho/issues/595)) ([752794f](https://github.com/wuisabel-gif/rho/commit/752794f407d65533e97924d6e89ceeba443886c0))
* **tui:** stop link underlines from spilling into gutters ([#858](https://github.com/wuisabel-gif/rho/issues/858)) ([fdde28c](https://github.com/wuisabel-gif/rho/commit/fdde28cd28eb5913e4a1b5dea2ca742fa29e552c))
* **tui:** stop openai-compatible cost jumping on submit ([#1008](https://github.com/wuisabel-gif/rho/issues/1008)) ([51f881f](https://github.com/wuisabel-gif/rho/commit/51f881f68d663b1d15a0b280f0fef76cbcf9a8ba))
* **tui:** stream live agent tool-call prompt previews ([#543](https://github.com/wuisabel-gif/rho/issues/543)) ([bca0596](https://github.com/wuisabel-gif/rho/commit/bca059632b80b87708e4a32f66c7a77375f3ad3d))
* **tui:** suppress false fast notice and preserve pasted commands ([#675](https://github.com/wuisabel-gif/rho/issues/675)) ([5a354f0](https://github.com/wuisabel-gif/rho/commit/5a354f04dea76de50cd784652bec4f42e2b36fb4))
* **tui:** surface status feedback as a top-right toast ([#716](https://github.com/wuisabel-gif/rho/issues/716)) ([cb4e8a5](https://github.com/wuisabel-gif/rho/commit/cb4e8a599203f0d2ab30e36cdbb824e9a0242b8d))
* **tui:** surface structured picker key hints and empty states ([#724](https://github.com/wuisabel-gif/rho/issues/724)) ([3174af7](https://github.com/wuisabel-gif/rho/commit/3174af7c69297a3a93c2cbc13620a51d1590f9ea))
* **tui:** unify key hints, picker titles, and transcript errors ([#1053](https://github.com/wuisabel-gif/rho/issues/1053)) ([8dbb2a5](https://github.com/wuisabel-gif/rho/commit/8dbb2a568263234c6eb4140df34252a04f27e93c))
* **tui:** use plain language in session delete confirms ([#1051](https://github.com/wuisabel-gif/rho/issues/1051)) ([55ccd83](https://github.com/wuisabel-gif/rho/commit/55ccd83d3c2b700180c57668a548dcb0e9cc297e))
* **tui:** validate dropped file attachments ([#677](https://github.com/wuisabel-gif/rho/issues/677)) ([1c62a3d](https://github.com/wuisabel-gif/rho/commit/1c62a3d638328bc829350f1cf32649fd58f7abcb))
* **tui:** warn when external editor is unset ([#533](https://github.com/wuisabel-gif/rho/issues/533)) ([fa556be](https://github.com/wuisabel-gif/rho/commit/fa556be42935b8f64f651dba15c20d2d994f90be))
* **update:** fetch the install script from the release tag, not main ([#536](https://github.com/wuisabel-gif/rho/issues/536)) ([332401a](https://github.com/wuisabel-gif/rho/commit/332401a5d14e93d1b609c5a667aa45e9d4276bb1)), closes [#497](https://github.com/wuisabel-gif/rho/issues/497)
* **usage:** normalize cache write token accounting ([#511](https://github.com/wuisabel-gif/rho/issues/511)) ([4e15982](https://github.com/wuisabel-gif/rho/commit/4e15982a1e6f4738d40611d77c721ac26051bfda))
* **web:** inline fetch content and session-folder web sidecars ([#532](https://github.com/wuisabel-gif/rho/issues/532)) ([76e2f45](https://github.com/wuisabel-gif/rho/commit/76e2f4534fd5618fffbebd0861089654a234f181))
* **web:** keep github tokens out of git argv and harden fetch targets ([#547](https://github.com/wuisabel-gif/rho/issues/547)) ([7b32573](https://github.com/wuisabel-gif/rho/commit/7b3257399ea75223531859323142a17c6d000500))
* **workflow:** gate RLIMIT_AS to linux so the planner runs on macOS ([#689](https://github.com/wuisabel-gif/rho/issues/689)) ([dabbf99](https://github.com/wuisabel-gif/rho/commit/dabbf99fe1825cd1a3966aa333d0ab759f9884c4))
* **workflow:** raise planner RLIMIT_AS above startup VmPeak ([#749](https://github.com/wuisabel-gif/rho/issues/749)) ([def515e](https://github.com/wuisabel-gif/rho/commit/def515e0eea9abfaf92ee0e440b43040be5bb972))
* **xai:** add grok-4.6 to the static model allowlist ([#882](https://github.com/wuisabel-gif/rho/issues/882)) ([52ebd71](https://github.com/wuisabel-gif/rho/commit/52ebd716456edcd9bd41d44d35afc7fc283cb31c))


### Performance Improvements

* cut hot-path costs in grep, session persistence, and live TUI rendering ([#1027](https://github.com/wuisabel-gif/rho/issues/1027)) ([9cf4ad7](https://github.com/wuisabel-gif/rho/commit/9cf4ad73149ebcaffbe760481618cac9bb02a061))
* cut per-frame palette discovery, layout rework, and git spawn churn ([#1017](https://github.com/wuisabel-gif/rho/issues/1017)) ([39952ce](https://github.com/wuisabel-gif/rho/commit/39952ce4177da242f172b6a6bbcc30721424924b))
* optimize orchestration and session hot paths ([#603](https://github.com/wuisabel-gif/rho/issues/603)) ([62aa8f5](https://github.com/wuisabel-gif/rho/commit/62aa8f50358fc82f1e6bef5bf0d2348fc6c0aaac))
* **session:** eliminate double transcript deserialization and message clones during turn save ([#936](https://github.com/wuisabel-gif/rho/issues/936)) ([4c60e8d](https://github.com/wuisabel-gif/rho/commit/4c60e8d346d8318bee6bbde984e69bcee2049bf3))
* **session:** keep one transcript in ram instead of one per turn ([#964](https://github.com/wuisabel-gif/rho/issues/964)) ([c2a0c7d](https://github.com/wuisabel-gif/rho/commit/c2a0c7d1a82036743789df3d571f9e062840bfa4))
* shrink release binary 38% and stop repeating startup work ([#947](https://github.com/wuisabel-gif/rho/issues/947)) ([3fc397d](https://github.com/wuisabel-gif/rho/commit/3fc397dd8d2926c20354471741a4d74a873a82c1))
* **tls:** drop OpenSSL and run rustls+ring everywhere ([#1061](https://github.com/wuisabel-gif/rho/issues/1061)) ([3ab2016](https://github.com/wuisabel-gif/rho/commit/3ab20166d06d805a9554786904dc16ec2544a2c7))
* **tools:** cut tokens from web, process, and shell results ([#980](https://github.com/wuisabel-gif/rho/issues/980)) ([c103ec0](https://github.com/wuisabel-gif/rho/commit/c103ec0d6d46896f735074413369cc471c95a750))
* **tui,session:** cut truncation allocations and cache tree branch count ([#629](https://github.com/wuisabel-gif/rho/issues/629)) ([a1c53f0](https://github.com/wuisabel-gif/rho/commit/a1c53f0894b20268a96f17a770291ba2a2c31eaa))
* **tui:** keep first resume paint off the syntax dump ([#972](https://github.com/wuisabel-gif/rho/issues/972)) ([81aa8fa](https://github.com/wuisabel-gif/rho/commit/81aa8fa0248255efa6567a83095b05123a773b10))
* **tui:** keep long streamed replies from stalling on open fences ([#1043](https://github.com/wuisabel-gif/rho/issues/1043)) ([4d5adfa](https://github.com/wuisabel-gif/rho/commit/4d5adfab9421f98f987eee7a9f1e0d03de6e53d1))
* **tui:** make rho attach scrolling smooth on long transcripts ([#985](https://github.com/wuisabel-gif/rho/issues/985)) ([8e1e243](https://github.com/wuisabel-gif/rho/commit/8e1e2430c026d9adc6b968dfed0ab89fcdc5513e))
* **tui:** paint the first frame before MCP connect and other startup tails ([#948](https://github.com/wuisabel-gif/rho/issues/948)) ([cdc1bbf](https://github.com/wuisabel-gif/rho/commit/cdc1bbfeabd93bf2bf5b615911048a2eebb6a947))
* **tui:** scale render hot paths for long transcripts ([#876](https://github.com/wuisabel-gif/rho/issues/876)) ([62d2500](https://github.com/wuisabel-gif/rho/commit/62d25006e104887654962c821578c4e1158b1425))
* **tui:** stop keeping a second transcript after resume ([#965](https://github.com/wuisabel-gif/rho/issues/965)) ([52fd5c6](https://github.com/wuisabel-gif/rho/commit/52fd5c68457c9114d258148c2ea8c10e86b70e4e))
* **tui:** stop long transcripts rebuilding on image-budget jitter ([#874](https://github.com/wuisabel-gif/rho/issues/874)) ([c888e94](https://github.com/wuisabel-gif/rho/commit/c888e946599dba4f9afcf01d1d4f4927772f8249))
* **tui:** stop recompiling search regex on every painted line ([#938](https://github.com/wuisabel-gif/rho/issues/938)) ([74689ae](https://github.com/wuisabel-gif/rho/commit/74689ae30ec784b5a49fcbfb3df8e0bcddc0fd4e))
* **web:** stop keeping every fetched page in ram ([#977](https://github.com/wuisabel-gif/rho/issues/977)) ([4b392e8](https://github.com/wuisabel-gif/rho/commit/4b392e8c1dbeda2bbd7cbe206320962100514a60))


### Code Refactoring

* pay down all NEXT_MAJOR debt for the next major, net -986 lines ([#1062](https://github.com/wuisabel-gif/rho/issues/1062)) ([0e17bdb](https://github.com/wuisabel-gif/rho/commit/0e17bdb5e9fa21440fffbbe00171830ac0d1d3c2))
* **providers:** own HTTP transport errors and collapse reqwest onto 0.13 ([#1060](https://github.com/wuisabel-gif/rho/issues/1060)) ([701dd29](https://github.com/wuisabel-gif/rho/commit/701dd297d1b3e17df55f9dbf6f13e9c2a1d0ccb5))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * rho-sdk bumped from 5.1.0 to 6.0.0
    * rho-providers bumped from 2.1.0 to 3.0.0
</details>

<details><summary>rho-providers: 3.0.0</summary>

## [3.0.0](https://github.com/wuisabel-gif/rho/compare/rho-providers-v2.1.0...rho-providers-v3.0.0) (2026-09-06)


###   BREAKING CHANGES

* rho-sdk removes RunEvent::ProviderActivity and the PROVIDER_ACTIVITY_* constants, collapses ProviderStreamResetReason retryable variants into RetryableFailure { kind, retry_after }, removes ModelCallMetrics::output_tokens_per_second, adds revision to RunEvent::Failed, folds ContextEstimated into StepStarted, and replaces the stringly generation-output-token carriers with a typed ModelCallMetrics::generation_output_tokens metric and ModelEvent::GenerationOutputTokens variant. rho-providers adds ProviderId::OpenAiCompatible for config-defined hosts, folds CustomProviderOptions into CustomProviderSpec (removing the _with_lookup/ _with_options funnels), makes providers() include custom hosts (removing visible_providers), removes deprecated registry API-base re-exports and ProviderRuntime::same_family, and drops the CredentialStore parameter from OpenAiProvider::new_with_identity. rho-tools removes the edit_file tool-name alias, the write_file frontmatter alias, and the EditToolKind type alias.
* **providers:** own HTTP transport errors and collapse reqwest onto 0.13 ([#1060](https://github.com/wuisabel-gif/rho/issues/1060))
* **xai:** ModelEvent::WebSearch and RunEvent::WebSearch now carry a name field so hosts can distinguish web_search from x_search.

### Features

* add advisor mode with a selectable advisor model ([#752](https://github.com/wuisabel-gif/rho/issues/752)) ([13c1ebb](https://github.com/wuisabel-gif/rho/commit/13c1ebb89edfde2924ee760c7621b099fd510708))
* **agents:** add Claude Code subagent runtime ([#541](https://github.com/wuisabel-gif/rho/issues/541)) ([c1385ec](https://github.com/wuisabel-gif/rho/commit/c1385ecae9b2eb967ae73ecc09c20cc80bc63479))
* **agents:** allow pinning auth profiles on rho agents ([#781](https://github.com/wuisabel-gif/rho/issues/781)) ([3e1f691](https://github.com/wuisabel-gif/rho/commit/3e1f691e693dd93bf888cb5c3eb3093a7169525a))
* **attach:** show reasoning level next to model and provider ([#1044](https://github.com/wuisabel-gif/rho/issues/1044)) ([2b1f912](https://github.com/wuisabel-gif/rho/commit/2b1f912e1233b5769e250a4bf53538661afa9126))
* **auth:** add active auth mode switcher ([#609](https://github.com/wuisabel-gif/rho/issues/609)) ([a2b0f68](https://github.com/wuisabel-gif/rho/commit/a2b0f68f71033ca6f8594a35368a79b2388916ca))
* **auth:** always show a copyable login URL across every provider ([#1095](https://github.com/wuisabel-gif/rho/issues/1095)) ([9e2670b](https://github.com/wuisabel-gif/rho/commit/9e2670bd0892c579cad5f1d916046c16632ec9e1))
* **config:** mid-session edit tool, advisor, and auto preference ([#840](https://github.com/wuisabel-gif/rho/issues/840)) ([423d026](https://github.com/wuisabel-gif/rho/commit/423d02690edee36a6dc692ac25d8fd9013d33139))
* **openai:** add fast mode ([#610](https://github.com/wuisabel-gif/rho/issues/610)) ([8c5cd6d](https://github.com/wuisabel-gif/rho/commit/8c5cd6d19e1758b85fc25c345769e49426f10ad0))
* **permission:** rename Auto to Bypass and add classifier Auto ([#870](https://github.com/wuisabel-gif/rho/issues/870)) ([3192daa](https://github.com/wuisabel-gif/rho/commit/3192daa713f7202f44727ec4acb83d0c646d1286))
* **permission:** screen Auto requests with a two-stage classifier ([#893](https://github.com/wuisabel-gif/rho/issues/893)) ([4149f11](https://github.com/wuisabel-gif/rho/commit/4149f1157aa2c8ee10561a21a919a0e530b8f3cc))
* **prompt:** tell the agent which model runs it, its subagents, and the advisor ([#860](https://github.com/wuisabel-gif/rho/issues/860)) ([d18c377](https://github.com/wuisabel-gif/rho/commit/d18c3774a20657cc1214e2936251cc993b69dd14))
* **providers:** add Meta Model API and collapse provider registration ([#755](https://github.com/wuisabel-gif/rho/issues/755)) ([b41ef92](https://github.com/wuisabel-gif/rho/commit/b41ef92dcbeeba12351df4711f4817761fda0a79))
* **providers:** add MiniMax as a first-party Anthropic-compatible host ([#1059](https://github.com/wuisabel-gif/rho/issues/1059)) ([aa71132](https://github.com/wuisabel-gif/rho/commit/aa7113215ed9601dd9bf74241a031febd9ee2c85))
* **providers:** add Ollama Cloud API provider ([#597](https://github.com/wuisabel-gif/rho/issues/597)) ([f6a62dd](https://github.com/wuisabel-gif/rho/commit/f6a62ddb8c77bae1f6ba386328b79db625ec1e5d))
* **providers:** add Qwen Token Plan OpenAI-compatible provider ([#738](https://github.com/wuisabel-gif/rho/issues/738)) ([6aa6df2](https://github.com/wuisabel-gif/rho/commit/6aa6df2e812674b721bedd3b65c7c2cdb359a1e4))
* **providers:** add xAI server-side context compaction ([#542](https://github.com/wuisabel-gif/rho/issues/542)) ([2d43f13](https://github.com/wuisabel-gif/rho/commit/2d43f134669414b3d9b7332a4c9d17aaa1346d9f))
* **providers:** let /login add custom hosts that work with CLIProxyAPI ([#984](https://github.com/wuisabel-gif/rho/issues/984)) ([5ec9a44](https://github.com/wuisabel-gif/rho/commit/5ec9a445db5ff9c47cc814d2cbd282172c827a5a))
* **providers:** let config name openai-compatible hosts ([#888](https://github.com/wuisabel-gif/rho/issues/888)) ([a87649a](https://github.com/wuisabel-gif/rho/commit/a87649a9e76332f53f125c52e7eccd8a14bc14f1))
* **providers:** let custom hosts speak OpenAI Responses ([#1041](https://github.com/wuisabel-gif/rho/issues/1041)) ([381383d](https://github.com/wuisabel-gif/rho/commit/381383d9f5f5d13746e23518d152075b63e6128d))
* **providers:** look up models.dev from custom host model ids ([#1004](https://github.com/wuisabel-gif/rho/issues/1004)) ([da477da](https://github.com/wuisabel-gif/rho/commit/da477da84b401f3bc2b299e481851dfd5278aded))
* **providers:** read Ollama context and thinking from native tags ([#993](https://github.com/wuisabel-gif/rho/issues/993)) ([dfd0f01](https://github.com/wuisabel-gif/rho/commit/dfd0f0145ac26a34365f16446bc924ef1de125b5))
* **providers:** set up ollama through /login instead of first-run defaults ([#994](https://github.com/wuisabel-gif/rho/issues/994)) ([1fbe5f8](https://github.com/wuisabel-gif/rho/commit/1fbe5f853d9f9b8f02251b5e9dbad2258e82a20c))
* **providers:** sign in to OpenCode Go and use its models ([#913](https://github.com/wuisabel-gif/rho/issues/913)) ([db501a6](https://github.com/wuisabel-gif/rho/commit/db501a6ab5b64c44114d6ecf1a1bf3a75ac597b6))
* **providers:** use OpenAI server-side compaction for codex and api-key ([#514](https://github.com/wuisabel-gif/rho/issues/514)) ([b18eadd](https://github.com/wuisabel-gif/rho/commit/b18eadd6752de2945361cd59a60ffc4cc7b807ad))
* **questionnaire:** support choice descriptions ([#510](https://github.com/wuisabel-gif/rho/issues/510)) ([066899c](https://github.com/wuisabel-gif/rho/commit/066899c2ad12ca23c2b7772de4b0a6a3c6161497))
* **subagents:** add parent-child plain-text messaging for Rho runtime ([#852](https://github.com/wuisabel-gif/rho/issues/852)) ([dd25d8e](https://github.com/wuisabel-gif/rho/commit/dd25d8e3e48fd531e777e31fcad9c948a2a9ebfe))
* **subagents:** route background questionnaires to parent ([#539](https://github.com/wuisabel-gif/rho/issues/539)) ([e0cab31](https://github.com/wuisabel-gif/rho/commit/e0cab3182e9fc833fbf304c7dad5714f73b89952))
* **tools:** replace edit_file with codex-style apply_patch ([#653](https://github.com/wuisabel-gif/rho/issues/653)) ([eef1555](https://github.com/wuisabel-gif/rho/commit/eef155521c5492b9c7f34507e82b6b7f46b896a8))
* **tui:** cycle pinned models without opening the catalogue ([#988](https://github.com/wuisabel-gif/rho/issues/988)) ([c0d0292](https://github.com/wuisabel-gif/rho/commit/c0d029261852a91ae24ec5ced355de8ef7c876f9))
* **tui:** include subagent costs in status and info ([#548](https://github.com/wuisabel-gif/rho/issues/548)) ([9517f00](https://github.com/wuisabel-gif/rho/commit/9517f0012dd2001213fd10294287f8a0739e5d2c))
* **tui:** lift tool-card text on hover in main TUI and attach ([#928](https://github.com/wuisabel-gif/rho/issues/928)) ([344f79a](https://github.com/wuisabel-gif/rho/commit/344f79a49cf5c4fa754c87a18d6b53b34bcffe5d))
* **tui:** open or copy subagent attach from the activity rail ([#552](https://github.com/wuisabel-gif/rho/issues/552)) ([95e4ca6](https://github.com/wuisabel-gif/rho/commit/95e4ca698ab92f858587356ba16e29476bcfd972))
* **tui:** pick running subagents by title instead of run id ([#950](https://github.com/wuisabel-gif/rho/issues/950)) ([dffd205](https://github.com/wuisabel-gif/rho/commit/dffd2053eb4d22bc0b86d364c31fc44c8317667d))
* **tui:** show live background processes in the activity rail ([#935](https://github.com/wuisabel-gif/rho/issues/935)) ([f396b72](https://github.com/wuisabel-gif/rho/commit/f396b72542abf17c2ef108c91bfa04351125031a))
* **tui:** show model output token rate ([#623](https://github.com/wuisabel-gif/rho/issues/623)) ([a5aa688](https://github.com/wuisabel-gif/rho/commit/a5aa688686d9f4f08d064462ccfa4fd542aa979d))
* **tui:** stream apply_patch diff cards ([#657](https://github.com/wuisabel-gif/rho/issues/657)) ([e2c932e](https://github.com/wuisabel-gif/rho/commit/e2c932e377f15ddfaab1e4700aa7d6f4e8ed0417))
* **tui:** stream mermaid diagrams as they arrive instead of popping in at fence close ([#1085](https://github.com/wuisabel-gif/rho/issues/1085)) ([29c70cc](https://github.com/wuisabel-gif/rho/commit/29c70cc5a0b28f66b13006dac8d3d6e4b01a31fa))
* **tui:** unify tool transcript cards as Call + Children ([#586](https://github.com/wuisabel-gif/rho/issues/586)) ([ce52cdd](https://github.com/wuisabel-gif/rho/commit/ce52cddb6dbf0ac1b2878b6f3bd468a87547f8fa))
* **tui:** watch subagents in the same terminal ([#1002](https://github.com/wuisabel-gif/rho/issues/1002)) ([966f3e8](https://github.com/wuisabel-gif/rho/commit/966f3e8315f8d2c39f91ef31577aa4b81f3a1e80))
* **web:** prefer hosted search with backup provider config ([#649](https://github.com/wuisabel-gif/rho/issues/649)) ([2e136e9](https://github.com/wuisabel-gif/rho/commit/2e136e9025ebc318f7fac5da8e45a3134d785430))
* **xai:** let grok generate and edit images in the conversation ([#967](https://github.com/wuisabel-gif/rho/issues/967)) ([47c03c1](https://github.com/wuisabel-gif/rho/commit/47c03c1d2b13864d32a69b27c21da4db54572e0e))
* **xai:** support hosted x_search tool ([#647](https://github.com/wuisabel-gif/rho/issues/647)) ([cd0c897](https://github.com/wuisabel-gif/rho/commit/cd0c897570376cf39d2d99b40c58c55b22fc6133))


### Bug Fixes

* **anthropic:** derive reasoning levels from models api capabilities ([#907](https://github.com/wuisabel-gif/rho/issues/907)) ([f057529](https://github.com/wuisabel-gif/rho/commit/f057529128be880c640e5dd9b5d5e42071eed792))
* **anthropic:** stop opus 5 from sending thinking.type.enabled ([#904](https://github.com/wuisabel-gif/rho/issues/904)) ([d76a398](https://github.com/wuisabel-gif/rho/commit/d76a3984d37d299850de6fabf9d7135c047c137c))
* **auth:** prefer credential-backed auth and fix Ollama Cloud reasoning ([#619](https://github.com/wuisabel-gif/rho/issues/619)) ([1a57f6f](https://github.com/wuisabel-gif/rho/commit/1a57f6f24292b63a6ba4ba314843c2fb308792cf))
* **auth:** restore ollama device test key dir on unwind and isolate temp dir ([#621](https://github.com/wuisabel-gif/rho/issues/621)) ([d2a345d](https://github.com/wuisabel-gif/rho/commit/d2a345df56b1ae815007829a04cc21172500530d))
* **auth:** stop waiting for Ollama device callback ([#616](https://github.com/wuisabel-gif/rho/issues/616)) ([54288d2](https://github.com/wuisabel-gif/rho/commit/54288d28f7bcc68a36f0424e5de6c28e470fb479))
* **ci:** repair macOS stdin guard and supervised approval PTY smoke ([#1055](https://github.com/wuisabel-gif/rho/issues/1055)) ([8b6654f](https://github.com/wuisabel-gif/rho/commit/8b6654ff86b34cd4f2a41d11520085f0a1ea5c01))
* **claude-cli:** keep Auto dontAsk on the bound tool set ([#903](https://github.com/wuisabel-gif/rho/issues/903)) ([fb2de07](https://github.com/wuisabel-gif/rho/commit/fb2de0793939ce4034303718efadb03fba858ab9))
* exclude reasoning tokens from throughput ([#819](https://github.com/wuisabel-gif/rho/issues/819)) ([d261b5b](https://github.com/wuisabel-gif/rho/commit/d261b5b35bfb119f49a81d83b33ca06b62b383e7))
* **models:** stop clamping GPT-5.5 and GPT-5.6 context to 272k ([#966](https://github.com/wuisabel-gif/rho/issues/966)) ([c5984e5](https://github.com/wuisabel-gif/rho/commit/c5984e5d04d6f4ab1d24c250cb6b2e74c4362187))
* **openai:** align Codex Responses wire contracts ([#644](https://github.com/wuisabel-gif/rho/issues/644)) ([76cf855](https://github.com/wuisabel-gif/rho/commit/76cf8554c390dfa112801016f2c05bd929c35eee))
* **openai:** route gpt-5.6 Codex models through standard Responses ([#651](https://github.com/wuisabel-gif/rho/issues/651)) ([219b9f5](https://github.com/wuisabel-gif/rho/commit/219b9f593a42858bdbd47cac7d23ce224b81b84c))
* **poolside:** publish final stream usage snapshot ([#516](https://github.com/wuisabel-gif/rho/issues/516)) ([d51ebab](https://github.com/wuisabel-gif/rho/commit/d51ebabcc4823ef11b21b8fadecd6625956146d2))
* **prompt:** wait for catalog names before model labels ([#863](https://github.com/wuisabel-gif/rho/issues/863)) ([71fa544](https://github.com/wuisabel-gif/rho/commit/71fa544e86e5dd046b898be76632996d92915c19))
* **providers:** compile openai-compatible hosts in release builds ([#917](https://github.com/wuisabel-gif/rho/issues/917)) ([4625ab8](https://github.com/wuisabel-gif/rho/commit/4625ab8151b348575bdc951af3ac08190ed868d5))
* **providers:** disable parallel tools on codex responses lite ([#583](https://github.com/wuisabel-gif/rho/issues/583)) ([84ca3f5](https://github.com/wuisabel-gif/rho/commit/84ca3f5ff0e6d535f40ebf92594e5c60df70a711))
* **providers:** drop flaky catalog invalidate readiness test ([#1006](https://github.com/wuisabel-gif/rho/issues/1006)) ([8ba4f27](https://github.com/wuisabel-gif/rho/commit/8ba4f27b203c268797f82eb0bd79845b0b412a08))
* **providers:** enrich empty SSE content diagnostic ([#684](https://github.com/wuisabel-gif/rho/issues/684)) ([79e4d48](https://github.com/wuisabel-gif/rho/commit/79e4d48c735de05e1ceccde7cd3ae72a8e31e62f))
* **providers:** keep anthropic tool schemas typed after composition strip ([#753](https://github.com/wuisabel-gif/rho/issues/753)) ([207e74c](https://github.com/wuisabel-gif/rho/commit/207e74cc577d4c7c905f9bcf6b6b49e7153c9db5))
* **providers:** keep prompt-cache hits across tool turns ([#1040](https://github.com/wuisabel-gif/rho/issues/1040)) ([e139d99](https://github.com/wuisabel-gif/rho/commit/e139d99e6abb4e0ee9315305958e357da3afe715))
* **providers:** restore models.dev metadata for catalog = "openrouter" ([#987](https://github.com/wuisabel-gif/rho/issues/987)) ([e8fb9f1](https://github.com/wuisabel-gif/rho/commit/e8fb9f16d17038168fcae7701c13fa03123722d4))
* **providers:** retry codex server_is_overloaded as unavailable ([#641](https://github.com/wuisabel-gif/rho/issues/641)) ([9bb2c12](https://github.com/wuisabel-gif/rho/commit/9bb2c124c758a2ee6bc4b8deb8d8b502f6145ff7)), closes [#639](https://github.com/wuisabel-gif/rho/issues/639)
* **providers:** retry empty assistant completions ([b50aa7b](https://github.com/wuisabel-gif/rho/commit/b50aa7b5968cf9ab38fa1c10d1a26666f48332ac))
* **providers:** say why a transport request failed ([#1036](https://github.com/wuisabel-gif/rho/issues/1036)) ([79fd9c1](https://github.com/wuisabel-gif/rho/commit/79fd9c1d2c72fd76fab03dc5f41ac9342f5b2028))
* **providers:** send prompt_cache_key on openai-compatible chat ([#1007](https://github.com/wuisabel-gif/rho/issues/1007)) ([5c10feb](https://github.com/wuisabel-gif/rho/commit/5c10feb8331e20543967128200ce5f4c09ae271b))
* **providers:** source Meta Muse Spark reasoning from models.dev ([#758](https://github.com/wuisabel-gif/rho/issues/758)) ([a11eea0](https://github.com/wuisabel-gif/rho/commit/a11eea0756cedfd2f1bb879603355c28a9c4a037))
* **providers:** stop inflated and deflated TPS for reasoning models ([#890](https://github.com/wuisabel-gif/rho/issues/890)) ([a2c673d](https://github.com/wuisabel-gif/rho/commit/a2c673dc48743e77689a67e4852fb6d3d094bc47))
* **providers:** stop model-id hosts inheriting builtin reasoning ([#1018](https://github.com/wuisabel-gif/rho/issues/1018)) ([05acadd](https://github.com/wuisabel-gif/rho/commit/05acadd28fc9058d10d13b029785f6fa53dfe36e))
* **providers:** surface rate-limit reset time and /limits pointer ([#733](https://github.com/wuisabel-gif/rho/issues/733)) ([b9371fc](https://github.com/wuisabel-gif/rho/commit/b9371fc69fb9b195f9f400d872195c91f031a6b2))
* **release:** recover provider 2.1.0 ([#1099](https://github.com/wuisabel-gif/rho/issues/1099)) ([15f9403](https://github.com/wuisabel-gif/rho/commit/15f9403a38c9edf62f7bd46900b05299e99a48ea))
* **sdk:** recover failed 1.17.1 release packaging ([#587](https://github.com/wuisabel-gif/rho/issues/587)) ([224189e](https://github.com/wuisabel-gif/rho/commit/224189e2d4fc2ec5f23cb88d80065d82c91ef40b))
* **sdk:** recover failed 1.32.0 release packaging ([#792](https://github.com/wuisabel-gif/rho/issues/792)) ([a782145](https://github.com/wuisabel-gif/rho/commit/a782145820f2924a47140f9e8cd8e3cbd13be8a3))
* **tools:** allow file paths outside workspace ([#537](https://github.com/wuisabel-gif/rho/issues/537)) ([8a3cc24](https://github.com/wuisabel-gif/rho/commit/8a3cc24468e89bb509fefbefced738b706b1e43d))
* **tools:** scrub provider credential env vars from child processes ([#502](https://github.com/wuisabel-gif/rho/issues/502)) ([6d66913](https://github.com/wuisabel-gif/rho/commit/6d669135caa7aa160f8c81c109f0c99736b70e63))
* **tui:** lead approval prompts with the command ([#846](https://github.com/wuisabel-gif/rho/issues/846)) ([413063c](https://github.com/wuisabel-gif/rho/commit/413063c9d169e10ca369d83172fbbb952619f07c))
* **tui:** let you type while compact runs on the main loop ([#957](https://github.com/wuisabel-gif/rho/issues/957)) ([07ef7c1](https://github.com/wuisabel-gif/rho/commit/07ef7c14719427e4a77a23056761ca6f7532954f))
* **tui:** render narrow mermaid flowcharts and explain fallbacks ([#565](https://github.com/wuisabel-gif/rho/issues/565)) ([0bf7ad7](https://github.com/wuisabel-gif/rho/commit/0bf7ad719fa32d00bc6d1bc7857307032fd9f1f6))
* **tui:** reuse tool stream previews and allow codex parallel tools ([#566](https://github.com/wuisabel-gif/rho/issues/566)) ([fa0074a](https://github.com/wuisabel-gif/rho/commit/fa0074ae125972ac533ae09b30915f7e479674bd))
* **tui:** show codex fast mode and report tier fallback ([#663](https://github.com/wuisabel-gif/rho/issues/663)) ([177043f](https://github.com/wuisabel-gif/rho/commit/177043f5022a1798ae45b0d987e6c6ceaf470d1c))
* **tui:** show hosted x_search tool cards ([#662](https://github.com/wuisabel-gif/rho/issues/662)) ([4381667](https://github.com/wuisabel-gif/rho/commit/438166754b79645d31b4fcefd92b3ea665567c94))
* **tui:** sort slash commands and provider pickers alphabetically ([#498](https://github.com/wuisabel-gif/rho/issues/498)) ([0e2c16c](https://github.com/wuisabel-gif/rho/commit/0e2c16cd9b5ac6b5c9c28259a09c0428f64a72ab))
* **tui:** stop openai-compatible cost jumping on submit ([#1008](https://github.com/wuisabel-gif/rho/issues/1008)) ([51f881f](https://github.com/wuisabel-gif/rho/commit/51f881f68d663b1d15a0b280f0fef76cbcf9a8ba))
* **usage:** normalize cache write token accounting ([#511](https://github.com/wuisabel-gif/rho/issues/511)) ([4e15982](https://github.com/wuisabel-gif/rho/commit/4e15982a1e6f4738d40611d77c721ac26051bfda))
* **xai:** add grok-4.6 to the static model allowlist ([#882](https://github.com/wuisabel-gif/rho/issues/882)) ([52ebd71](https://github.com/wuisabel-gif/rho/commit/52ebd716456edcd9bd41d44d35afc7fc283cb31c))
* **xai:** keep optional grok Off as wire none ([#883](https://github.com/wuisabel-gif/rho/issues/883)) ([e92f0a9](https://github.com/wuisabel-gif/rho/commit/e92f0a96d5d53e61d295f8ac5be4a887fcb0a8f5))


### Performance Improvements

* cut hot-path costs in grep, session persistence, and live TUI rendering ([#1027](https://github.com/wuisabel-gif/rho/issues/1027)) ([9cf4ad7](https://github.com/wuisabel-gif/rho/commit/9cf4ad73149ebcaffbe760481618cac9bb02a061))
* **providers:** avoid cloning message history and batch SQLite model metadata caching ([#929](https://github.com/wuisabel-gif/rho/issues/929)) ([e40926c](https://github.com/wuisabel-gif/rho/commit/e40926c4449051c23340dca5fd9afe436d22d3dc))
* **providers:** eliminate LineDecoder per-chunk compaction, SIMD-accelerate newlines, and optimize Gemini SSE decoder ([#931](https://github.com/wuisabel-gif/rho/issues/931)) ([76957a5](https://github.com/wuisabel-gif/rho/commit/76957a55b4d475a718d78f3c109893d1bd6d6cce))
* **providers:** stop building a 40 MB JSON tree on catalog hydrate ([#971](https://github.com/wuisabel-gif/rho/issues/971)) ([611fb08](https://github.com/wuisabel-gif/rho/commit/611fb08bbfd93031135b35f0cd26cd0919e4032e))
* **tls:** drop OpenSSL and run rustls+ring everywhere ([#1061](https://github.com/wuisabel-gif/rho/issues/1061)) ([3ab2016](https://github.com/wuisabel-gif/rho/commit/3ab20166d06d805a9554786904dc16ec2544a2c7))
* **tui:** paint the first frame before MCP connect and other startup tails ([#948](https://github.com/wuisabel-gif/rho/issues/948)) ([cdc1bbf](https://github.com/wuisabel-gif/rho/commit/cdc1bbfeabd93bf2bf5b615911048a2eebb6a947))
* **tui:** stop keeping a second transcript after resume ([#965](https://github.com/wuisabel-gif/rho/issues/965)) ([52fd5c6](https://github.com/wuisabel-gif/rho/commit/52fd5c68457c9114d258148c2ea8c10e86b70e4e))


### Code Refactoring

* pay down all NEXT_MAJOR debt for the next major, net -986 lines ([#1062](https://github.com/wuisabel-gif/rho/issues/1062)) ([0e17bdb](https://github.com/wuisabel-gif/rho/commit/0e17bdb5e9fa21440fffbbe00171830ac0d1d3c2))
* **providers:** own HTTP transport errors and collapse reqwest onto 0.13 ([#1060](https://github.com/wuisabel-gif/rho/issues/1060)) ([701dd29](https://github.com/wuisabel-gif/rho/commit/701dd297d1b3e17df55f9dbf6f13e9c2a1d0ccb5))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * rho-sdk bumped from 5.1.0 to 6.0.0
</details>

<details><summary>rho-sdk: 6.0.0</summary>

## [6.0.0](https://github.com/wuisabel-gif/rho/compare/rho-sdk-v5.1.0...rho-sdk-v6.0.0) (2026-09-06)


###   BREAKING CHANGES

* rho-sdk removes RunEvent::ProviderActivity and the PROVIDER_ACTIVITY_* constants, collapses ProviderStreamResetReason retryable variants into RetryableFailure { kind, retry_after }, removes ModelCallMetrics::output_tokens_per_second, adds revision to RunEvent::Failed, folds ContextEstimated into StepStarted, and replaces the stringly generation-output-token carriers with a typed ModelCallMetrics::generation_output_tokens metric and ModelEvent::GenerationOutputTokens variant. rho-providers adds ProviderId::OpenAiCompatible for config-defined hosts, folds CustomProviderOptions into CustomProviderSpec (removing the _with_lookup/ _with_options funnels), makes providers() include custom hosts (removing visible_providers), removes deprecated registry API-base re-exports and ProviderRuntime::same_family, and drops the CredentialStore parameter from OpenAiProvider::new_with_identity. rho-tools removes the edit_file tool-name alias, the write_file frontmatter alias, and the EditToolKind type alias.
* **hooks:** `AuthorizationDenialKind` and `ApprovalAuditDecision` gain a hook variant. Both are `#[non_exhaustive]`, so only exhaustive matches written before this change need updating.
* **xai:** ModelEvent::WebSearch and RunEvent::WebSearch now carry a name field so hosts can distinguish web_search from x_search.

### Features

* **acp:** let hosts set reasoning through thought_level ([#1015](https://github.com/wuisabel-gif/rho/issues/1015)) ([5cda8e8](https://github.com/wuisabel-gif/rho/commit/5cda8e8308682fa13c9d6001ec12989f0d030bb4))
* add advisor mode with a selectable advisor model ([#752](https://github.com/wuisabel-gif/rho/issues/752)) ([13c1ebb](https://github.com/wuisabel-gif/rho/commit/13c1ebb89edfde2924ee760c7621b099fd510708))
* **config:** mid-session edit tool, advisor, and auto preference ([#840](https://github.com/wuisabel-gif/rho/issues/840)) ([423d026](https://github.com/wuisabel-gif/rho/commit/423d02690edee36a6dc692ac25d8fd9013d33139))
* **hooks:** add typed lifecycle hooks ([#668](https://github.com/wuisabel-gif/rho/issues/668)) ([4a69c3d](https://github.com/wuisabel-gif/rho/commit/4a69c3dfbc2136a8c23dff515909e23886b8651f))
* **openai:** add fast mode ([#610](https://github.com/wuisabel-gif/rho/issues/610)) ([8c5cd6d](https://github.com/wuisabel-gif/rho/commit/8c5cd6d19e1758b85fc25c345769e49426f10ad0))
* **permission:** rename Auto to Bypass and add classifier Auto ([#870](https://github.com/wuisabel-gif/rho/issues/870)) ([3192daa](https://github.com/wuisabel-gif/rho/commit/3192daa713f7202f44727ec4acb83d0c646d1286))
* **providers:** add Qwen Token Plan OpenAI-compatible provider ([#738](https://github.com/wuisabel-gif/rho/issues/738)) ([6aa6df2](https://github.com/wuisabel-gif/rho/commit/6aa6df2e812674b721bedd3b65c7c2cdb359a1e4))
* **providers:** use OpenAI server-side compaction for codex and api-key ([#514](https://github.com/wuisabel-gif/rho/issues/514)) ([b18eadd](https://github.com/wuisabel-gif/rho/commit/b18eadd6752de2945361cd59a60ffc4cc7b807ad))
* **questionnaire:** add focused default selection ([#530](https://github.com/wuisabel-gif/rho/issues/530)) ([47d1853](https://github.com/wuisabel-gif/rho/commit/47d185377a68881c96db18ee186b3173215e39ee))
* **questionnaire:** support choice descriptions ([#510](https://github.com/wuisabel-gif/rho/issues/510)) ([066899c](https://github.com/wuisabel-gif/rho/commit/066899c2ad12ca23c2b7772de4b0a6a3c6161497))
* **sdk:** put the requested capability on after_tool_use ([#1090](https://github.com/wuisabel-gif/rho/issues/1090)) ([90f1a0e](https://github.com/wuisabel-gif/rho/commit/90f1a0ec781930f8ed98b6f7b80953ffc04a7587))
* **subagents:** add parent-child plain-text messaging for Rho runtime ([#852](https://github.com/wuisabel-gif/rho/issues/852)) ([dd25d8e](https://github.com/wuisabel-gif/rho/commit/dd25d8e3e48fd531e777e31fcad9c948a2a9ebfe))
* **subagents:** route background questionnaires to parent ([#539](https://github.com/wuisabel-gif/rho/issues/539)) ([e0cab31](https://github.com/wuisabel-gif/rho/commit/e0cab3182e9fc833fbf304c7dad5714f73b89952))
* **tui:** add /side overlay for frozen-context asides ([#1094](https://github.com/wuisabel-gif/rho/issues/1094)) ([3ebbdf9](https://github.com/wuisabel-gif/rho/commit/3ebbdf951f01c6a32e827d4b819bdd9441c76684))
* **tui:** show model output token rate ([#623](https://github.com/wuisabel-gif/rho/issues/623)) ([a5aa688](https://github.com/wuisabel-gif/rho/commit/a5aa688686d9f4f08d064462ccfa4fd542aa979d))
* **workflow:** add deterministic DAG workflows ([#680](https://github.com/wuisabel-gif/rho/issues/680)) ([77f36f9](https://github.com/wuisabel-gif/rho/commit/77f36f9cc6992f78ab59ac481a1f2dc4e00350a0))
* **xai:** let grok generate and edit images in the conversation ([#967](https://github.com/wuisabel-gif/rho/issues/967)) ([47c03c1](https://github.com/wuisabel-gif/rho/commit/47c03c1d2b13864d32a69b27c21da4db54572e0e))
* **xai:** support hosted x_search tool ([#647](https://github.com/wuisabel-gif/rho/issues/647)) ([cd0c897](https://github.com/wuisabel-gif/rho/commit/cd0c897570376cf39d2d99b40c58c55b22fc6133))


### Bug Fixes

* exclude reasoning tokens from throughput ([#819](https://github.com/wuisabel-gif/rho/issues/819)) ([d261b5b](https://github.com/wuisabel-gif/rho/commit/d261b5b35bfb119f49a81d83b33ca06b62b383e7))
* **metrics:** include reasoning latency in output rate ([#632](https://github.com/wuisabel-gif/rho/issues/632)) ([7f7fa39](https://github.com/wuisabel-gif/rho/commit/7f7fa39d88e3032a4433a105e07a785989406944))
* **openai:** align Codex Responses wire contracts ([#644](https://github.com/wuisabel-gif/rho/issues/644)) ([76cf855](https://github.com/wuisabel-gif/rho/commit/76cf8554c390dfa112801016f2c05bd929c35eee))
* **poolside:** publish final stream usage snapshot ([#516](https://github.com/wuisabel-gif/rho/issues/516)) ([d51ebab](https://github.com/wuisabel-gif/rho/commit/d51ebabcc4823ef11b21b8fadecd6625956146d2))
* **providers:** surface rate-limit reset time and /limits pointer ([#733](https://github.com/wuisabel-gif/rho/issues/733)) ([b9371fc](https://github.com/wuisabel-gif/rho/commit/b9371fc69fb9b195f9f400d872195c91f031a6b2))
* **sdk:** commit turn history on provider failure ([#739](https://github.com/wuisabel-gif/rho/issues/739)) ([b4158ab](https://github.com/wuisabel-gif/rho/commit/b4158ab1a58974dd29e43f6970dbe2fd08f714b5))
* **sdk:** recover failed 1.17.1 release packaging ([#587](https://github.com/wuisabel-gif/rho/issues/587)) ([224189e](https://github.com/wuisabel-gif/rho/commit/224189e2d4fc2ec5f23cb88d80065d82c91ef40b))
* **sdk:** recover failed 1.32.0 release packaging ([#792](https://github.com/wuisabel-gif/rho/issues/792)) ([a782145](https://github.com/wuisabel-gif/rho/commit/a782145820f2924a47140f9e8cd8e3cbd13be8a3))
* **sdk:** stabilize compaction release benchmark ([#561](https://github.com/wuisabel-gif/rho/issues/561)) ([8364edc](https://github.com/wuisabel-gif/rho/commit/8364edc7f8d1acb3967a061b0da02fd4a102a787))
* **session:** v1 upgrades no longer write an unloadable transcript ([#939](https://github.com/wuisabel-gif/rho/issues/939)) ([1dc1002](https://github.com/wuisabel-gif/rho/commit/1dc1002c5c60ddc2a2889a12d92ead905cd4b6d3))
* **subagents:** run multi-agent batches in parallel ([#544](https://github.com/wuisabel-gif/rho/issues/544)) ([7dd6706](https://github.com/wuisabel-gif/rho/commit/7dd6706f6aade0a45d70336a42d259b4a3c12a4f))
* **tools:** allow file paths outside workspace ([#537](https://github.com/wuisabel-gif/rho/issues/537)) ([8a3cc24](https://github.com/wuisabel-gif/rho/commit/8a3cc24468e89bb509fefbefced738b706b1e43d))
* **tools:** scrub provider credential env vars from child processes ([#502](https://github.com/wuisabel-gif/rho/issues/502)) ([6d66913](https://github.com/wuisabel-gif/rho/commit/6d669135caa7aa160f8c81c109f0c99736b70e63))
* **tui:** open approval prompts at the start and default to deny ([#636](https://github.com/wuisabel-gif/rho/issues/636)) ([59efc07](https://github.com/wuisabel-gif/rho/commit/59efc07b26bf67597ebbe05551cd22f3affedc96))
* **tui:** report generation token throughput ([#803](https://github.com/wuisabel-gif/rho/issues/803)) ([4772f68](https://github.com/wuisabel-gif/rho/commit/4772f68ccad3fc1edf65aa666d9a49f74bfab960))
* **tui:** report herdr blocked during questionnaire ([#500](https://github.com/wuisabel-gif/rho/issues/500)) ([1dcdbe9](https://github.com/wuisabel-gif/rho/commit/1dcdbe9e86bb61cf0cd55a705c28941d9dfcb241))
* **tui:** show codex fast mode and report tier fallback ([#663](https://github.com/wuisabel-gif/rho/issues/663)) ([177043f](https://github.com/wuisabel-gif/rho/commit/177043f5022a1798ae45b0d987e6c6ceaf470d1c))
* **tui:** show hosted x_search tool cards ([#662](https://github.com/wuisabel-gif/rho/issues/662)) ([4381667](https://github.com/wuisabel-gif/rho/commit/438166754b79645d31b4fcefd92b3ea665567c94))
* **tui:** stabilize live stream tool cards and markdown previews ([#595](https://github.com/wuisabel-gif/rho/issues/595)) ([752794f](https://github.com/wuisabel-gif/rho/commit/752794f407d65533e97924d6e89ceeba443886c0))
* **tui:** stop openai-compatible cost jumping on submit ([#1008](https://github.com/wuisabel-gif/rho/issues/1008)) ([51f881f](https://github.com/wuisabel-gif/rho/commit/51f881f68d663b1d15a0b280f0fef76cbcf9a8ba))


### Performance Improvements

* optimize orchestration and session hot paths ([#603](https://github.com/wuisabel-gif/rho/issues/603)) ([62aa8f5](https://github.com/wuisabel-gif/rho/commit/62aa8f50358fc82f1e6bef5bf0d2348fc6c0aaac))


### Code Refactoring

* pay down all NEXT_MAJOR debt for the next major, net -986 lines ([#1062](https://github.com/wuisabel-gif/rho/issues/1062)) ([0e17bdb](https://github.com/wuisabel-gif/rho/commit/0e17bdb5e9fa21440fffbbe00171830ac0d1d3c2))
</details>

---
This PR was generated with [Release Please](https://github.com/googleapis/release-please). See [documentation](https://github.com/googleapis/release-please#release-please).