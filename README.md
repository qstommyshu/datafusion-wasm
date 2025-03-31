# Google Summer of Code 2025 Proposal

## Project Title: Robust WASM Support for Apache DataFusion

**Student**: Qi (Tommy) Shu  
**Email**: qstommyshu@gmail.com  
**Location**: Canada  
**GitHub**: [qstommyshu](https://github.com/qstommyshu)  
**LinkedIn**: [linkedin.com/in/qi-shu](https://www.linkedin.com/in/qi-shu/)  
**Resume**: [Link](./tommy_resume.pdf) to Resume

**Previous Contributions to DataFusion**:

- Migrate subtrait tests to `insta` (part [1](https://github.com/apache/datafusion/pull/15444) & [2](https://github.com/apache/datafusion/pull/15480))
- Migrate optimizer tests to `insta` ([pull request](https://github.com/apache/datafusion/pull/15446))
- Migrate datafusion/sql tests to `insta` (part [1](https://github.com/apache/datafusion/pull/15497) & [2](https://github.com/apache/datafusion/pull/15499))

---

## 🌟 Abstract

This project focuses on enabling robust WebAssembly (WASM) support for Apache DataFusion. By compiling core DataFusion components to WASM, exposing stable JS interfaces, and delivering a live playground, this work allows users to execute SQL queries directly in the browser — securely, privately, and without backend infrastructure.

Deliverables include a browser-based demo, improved bindings, test coverage, CI integration, and a release plan for long-term WASM maintenance.

---

## ✅ Benefits to the Community

- Empower **local-first SQL analytics** directly in the browser
- Lower the entry barrier for learning and using DataFusion
- Enable **privacy-aware data processing** (no server or upload)
- Lay the foundation for notebook and visualization integrations
- Establish a maintainable WASM support pipeline

---

## ✅ Deliverables

| Feature / Task                                         | Time Estimate |
| ------------------------------------------------------ | ------------- |
| Familiarize with codebase (DataFusion + WASM bindings) | 24h           |
| Create repo & guide to compile DataFusion into WASM    | 20h           |
| Write documentation for setup and usage                | 3h            |
| Blog post: “Compiling DataFusion to WASM”              | 12h           |
| Develop browser-based SQL playground demo              | 20h           |
| Investigate & identify public APIs to expose           | 10h           |
| Expose interfaces via `wasm-bindgen`                   | 35h           |
| Study Python bindings SoP (as reference)               | 3h            |
| Design SoP for Rust/WASM bindings                      | 3h            |
| Integrate SoP into workflow                            | 10h           |
| Write WASM test suite                                  | 40h           |
| Add WASM build/test CI via GitHub Actions              | 25h           |
| Blog series reflecting on development journey          | 30h           |
| Buffer time (in case anything is off the timeline)     | 15h           |

---

## 🗂️ Stretch Goals

These will be explored **only if core deliverables are completed ahead of schedule**.

| Stretch Goal                                                                                             | Time Estimate | Notes                                                                                                    |
| -------------------------------------------------------------------------------------------------------- | ------------- | -------------------------------------------------------------------------------------------------------- |
| Compile more DataFusion features/crates to WASM                                                          | 40h           | [Complex](https://github.com/apache/datafusion/issues/7652) due to feature flags & upstream dependencies |
| Add WASM UDF support (e.g. via [`datafusion-dft`](https://github.com/datafusion-contrib/datafusion-dft)) | 30h           | Requires careful design for cross-runtime execution                                                      |
| Improve public interface exposure                                                                        | 30h           | Explore planner-level or advanced APIs                                                                   |
| Enhance CI/release automation beyond basics                                                              | —             | Optional long-term maintenance track                                                                     |

---

**Total Estimated Time: ~350 hours**

## 🗓️ Timeline

### Community Bonding (Before May)

- Review WASM build process & `datafusion-wasm-bindings`
- Connect with mentors, discuss architecture & priorities
- Read through relevant issues (#7652, #13513, #13815)

---

### Week 1–3: WASM Setup + Playground MVP

- Set up working WASM build
- Build a live browser playground for SQL queries
- Write accompanying blog and documentation

**Deliverables**:

- Live SQL-in-browser playground
- Blog post: Compiling DataFusion to WASM
- Guide: Setup and usage

---

### Week 4–6: Interface Exposure

- Investigate which internal APIs to expose via `wasm-bindgen`
- Implement bindings for common operations (query context, register table, etc.)
- Define stable JS interface contract

**Deliverables**:

- API reference doc
- Extended JS-accessible WASM bindings

---

### Week 7: Midterm Evaluation

- Fully working browser app using new bindings
- Core APIs stable and functional
- Continue writing integration tests

**Deliverables**:

- Playground running against self-exposed APIs
- Midterm progress blog
- Interface testing suite (WIP)

---

### Week 8–10: UDF Prototype & CI Integration

- Investigate UDF-in-WASM feasibility (e.g. via [`datafusion-dft`](https://github.com/datafusion-contrib/datafusion-dft))
- Add GitHub Actions workflow for building/testing WASM
- Continue interface improvements and testing

**Deliverables**:

- Basic UDF call prototype (if feasible)
- WASM test suite + CI job

---

### Week 11–13: SOP + Docs Finalization

- Design WASM release checklist (inspired by Python bindings)
- Finalize test suite
- Write developer documentation and blog posts

**Deliverables**:

- SOP doc: Build, test, and release
- End-user and contributor docs
- Blog: Reflections & learnings

---

### Week 14–Final: Wrap Up & Final Evaluation

- Final bugfixes & polish
- Submit playground, tests, docs, and blog series

**Final Deliverables**:

- Live demo + repo
- Stable test/CI coverage
- Documentation + blog series

---

## 🔧 Technical Details

- **Rust Crates**: `datafusion`, `arrow`, `datafusion-expr`, etc.
- **Tooling**: `wasm-bindgen`, `wasm-pack`, `wasm-opt`, `wasm-bindgen-test`
- **Frontend**: HTML/JS/TS playground + bundler (Vite/Webpack)
- **CI/CD**: GitHub Actions for WASM test matrix
- **Docs**: Blog series and repo markdown

---

## 👋 Why Me?

- I'm already faimilairing myself with DataFusion with PRs!
- I have a strong interest in DBMS/OS/Compiler area (I was very excited when I saw logical plans, external sort, predicate pushdown optimization implemented in DataFusion)
- I enjoy writing developer tools and working across frontend/backend boundaries
- I have real experience with Rust, WASM, JS/TS — the exact stack needed
- I’m excited about local-first, browser-native computation
- I want to help make DataFusion more accessible and widely adopted

---

## 🧭 Future Work After GSoC

After the program, I’d like to continue contributing to:

- Maintaining `datafusion-wasm-bindings`
- Expanding WASM API coverage
- Experimenting with Jupyter / Observable notebook integration
- Building visual query editors or lightweight dashboards
- Exploring Arrow Flight + WASM streaming

---

## ✅ GSoC Participation

- **Have you participated in GSoC before?** No
- **Do you plan to continue contributing after GSoC?** Yes
