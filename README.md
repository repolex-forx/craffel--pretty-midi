# Repolex Knowledge Graph of craffel/pretty-midi

RDF knowledge graph data for [craffel/pretty-midi](https://github.com/craffel/pretty-midi), parsed by [repolex](https://repolex.ai).

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
rlex download craffel/pretty-midi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 60f6bce899eb2b84957b806301d9a462aea53c99
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 60f6bce899eb2b84957b806301d9a462aea53c99
│           └── chunk-001.nq.gz
├── blob
│   ├── 1453f97c615011c278228eb7246345a93a3ed59e.nq.gz
│   ├── 198a76a8a5cf33aa5063109ff214d990f09aafe1.nq.gz
│   ├── 19df5e78a7ae529abe52bb47873b4153f8148fcc.nq.gz
│   ├── 21d563b8eb7570c2dfd00e785acfdf1146497704.nq.gz
│   ├── 286830581b7e4e78016262e213a9c7a3b141c40d.nq.gz
│   ├── 3159e4a63d7f5dab35004e16c402d29fc3ebf95e.nq.gz
│   ├── 369e87d6ce1487db28275aeaa45c6d70f156f3b3.nq.gz
│   ├── 3bb55bbf5acc017705617adb168cc2dedf105d70.nq.gz
│   ├── 413c344f7dc9f5984dd40b60eefe4774ccc2bd21.nq.gz
│   ├── 471d40b039825f2ba255af2a14fff3d795836a51.nq.gz
│   ├── 4e411a54b2ec66daa7541cab39090946a94502d2.nq.gz
│   ├── 626376f53a73619cf4d4125375632490e631a2ee.nq.gz
│   ├── 69bc0407b8c8bdc451a8ea73ae5a154b0c5f69a1.nq.gz
│   ├── 7b61ad17073af34f9f17f94ec95cadbfd508f7fa.nq.gz
│   ├── 8e0f81fe144584359c297aa41e0330c4657a163d.nq.gz
│   ├── 90815204fc54780ab0efcf1560d8e092c11f99b0.nq.gz
│   ├── 90d85a004ebabc67b629c9ceac4015e2d3f3f29b.nq.gz
│   ├── 987e18cb41b2853c076d86fdb9c383037e8fe29c.nq.gz
│   ├── a4ec7abd60e975037985b4101396feea37fc619b.nq.gz
│   ├── ae0c0b8eb2b3ac302264f925c4c58892c7759722.nq.gz
│   ├── af386b376620880a41f0d16a34ca1d2f0ffa89d7.nq.gz
│   ├── bcda9a74b84bd89f78ca885f48a7ab85fa163868.nq.gz
│   ├── bdad6e895f36070aa2b1beb27800e921d5f9fc77.nq.gz
│   ├── c86b317ffc19cfb1b7e43eb70800080fc42ca3e1.nq.gz
│   ├── df667888e6a78a01bb38b5850d6f50d53bdd5620.nq.gz
│   ├── e985d1a69fef85d9ca20b771997f0f08979548ee.nq.gz
│   ├── eee76514d03f564e79a934a5efde75464c13261a.nq.gz
│   ├── f23361bfb070320591707852398c98b75c8b7c2c.nq.gz
│   └── f374bafd7a71400694902c6a89cf01b261a0850b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 60f6bce899eb2b84957b806301d9a462aea53c99.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
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

[craffel/pretty-midi](https://github.com/craffel/pretty-midi)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
