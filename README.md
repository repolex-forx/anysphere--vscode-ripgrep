# Repolex Knowledge Graph of anysphere/vscode-ripgrep

RDF knowledge graph data for [anysphere/vscode-ripgrep](https://github.com/anysphere/vscode-ripgrep), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download anysphere/vscode-ripgrep
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── 0ad56375c60fc4fea14e920a1059c1479045da75
│   │   │   └── chunk-001.nq.gz
│   │   └── 3d13812ea1d9d7a71100eaa03d2953232911997a
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   ├── 0ad56375c60fc4fea14e920a1059c1479045da75.nq.gz
│   │   └── 3d13812ea1d9d7a71100eaa03d2953232911997a.nq.gz
│   └── repolex
│       ├── 0ad56375c60fc4fea14e920a1059c1479045da75
│       │   └── chunk-001.nq.gz
│       └── 3d13812ea1d9d7a71100eaa03d2953232911997a
│           └── chunk-001.nq.gz
├── blob
│   ├── 14186abbc4956dfbfcdb74d09b4062782d1c1d2c.nq.gz
│   ├── 156033afb9d87f8f2f74022ad40e91b9e6d232f8.nq.gz
│   ├── 1f9d3d4421465c1719737a73696c38d943be9afe.nq.gz
│   ├── 2c1e7c0f3e8e232055fbe16d5bf82681b2c997a0.nq.gz
│   ├── 2ed9fc3e7040e3a377a8fc15a17509fbb68f4694.nq.gz
│   ├── 4bde4340215c99e57e95b9cc304b670f79d0ec9a.nq.gz
│   ├── 4e2bb26d00e1531cf21bea629d88fb752ce0e630.nq.gz
│   ├── 4e5e1b5f4f518f10647adb23a82812bb376ccf6f.nq.gz
│   ├── 79823e4dbf7fe10bfb3c3219882ef5e35dc030e5.nq.gz
│   ├── 873f0cd0399c88407b481d14b832e9d527215206.nq.gz
│   ├── 903613429605883f93db0fabfd553e3ee7c5769e.nq.gz
│   ├── 9585146eaec1fe3b7e639b1c1ed593af32f825df.nq.gz
│   ├── aaeaffc8800924dc71c6c98e6a72e019b2630526.nq.gz
│   ├── ad3c1561f7c3bc68a044192f2e34055b1b2c4904.nq.gz
│   ├── ad4702997099146d2abf9d905563dc6f2ff17bfa.nq.gz
│   ├── cca8d9403a0a5e28e857a520134e077ad997f92a.nq.gz
│   ├── e660fd93d3196215552065b1e63bf6a2f393ed86.nq.gz
│   ├── f009950bf7e068587eed5cf088d80dcdec58943d.nq.gz
│   └── f89c1cc7e319cffda8ec22f2be1210c75ae9728a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   ├── 0ad56375c60fc4fea14e920a1059c1479045da75.nq.gz
│   └── 3d13812ea1d9d7a71100eaa03d2953232911997a.nq.gz
├── filetree
│   ├── 0ad56375c60fc4fea14e920a1059c1479045da75.nq.gz
│   └── 3d13812ea1d9d7a71100eaa03d2953232911997a.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

16 directories, 33 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[anysphere/vscode-ripgrep](https://github.com/anysphere/vscode-ripgrep)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
