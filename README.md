# Repolex Knowledge Graph of mitsuhiko/pluginbase

RDF knowledge graph data for [mitsuhiko/pluginbase](https://github.com/mitsuhiko/pluginbase), parsed by [repolex](https://repolex.ai).

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
rlex download mitsuhiko/pluginbase
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2a5db4c0bba11dc6dff0110c298e3ab9d8521532
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2a5db4c0bba11dc6dff0110c298e3ab9d8521532
│           └── chunk-001.nq.gz
├── blob
│   ├── 0370f17f27d1a858d937a78b1489a7d9190ed67b.nq.gz
│   ├── 0b5e1e9758402a3a19303f30a99750979de89252.nq.gz
│   ├── 15f668f2989ad7e98e5bfb1b0b9d8249590888cd.nq.gz
│   ├── 19eb0511787ab425e917e885a10264b345a3e948.nq.gz
│   ├── 1cd3a864e77959400b4791498604e12711b4899d.nq.gz
│   ├── 1dbaa0cf801167bd3ad1dabf554d3a3f8894f4c8.nq.gz
│   ├── 1e941d8ca3dfaa2522e04702ac10f2dd8c9cd9f7.nq.gz
│   ├── 2650773c9b15bfd8249e5ebc58cd5ceb0a708ed6.nq.gz
│   ├── 33f47449c11d241e36c83d7f95d819bbe56e2c8f.nq.gz
│   ├── 3879e8529a60d099ec588e785ad6fc5d39d2bc1a.nq.gz
│   ├── 44ccdb728a86bd18a6b0227c0ca1fad5b9fb2993.nq.gz
│   ├── 4701884ba6be9812d791ea762ebaa2e761d02fe3.nq.gz
│   ├── 49489b58f1c462fa33fb9415e8fb8723d10ec799.nq.gz
│   ├── 49a15c3508c7020c190cc33296425f215e0bd06d.nq.gz
│   ├── 4ef4ca0e753b1d0345964bfa199f0b212806a242.nq.gz
│   ├── 51ed3a4b9069e556bdeb86ee96817ec7d95799f1.nq.gz
│   ├── 58335c38971a7d1171a2a3fdb169b19b3c6967c9.nq.gz
│   ├── 5b6977ef8dd2433035719c5f0834bd02379ccdde.nq.gz
│   ├── 66b6e4c2f3b55b25afd9716f9d3c5afb47b15d4e.nq.gz
│   ├── 678eff65290f231f4909a4e28e81868f8bc4c90f.nq.gz
│   ├── 6a275caef1673c578883b630e179ac745c145000.nq.gz
│   ├── 739db3e438e32ee27b5dadb0d53c6f4a898142ca.nq.gz
│   ├── 818aa6786487616498caa98827176f98b49b07d2.nq.gz
│   ├── 8daab7ee6efe3b6f3c2a2594b711e7a9026eb5e2.nq.gz
│   ├── 9332a2735b6ab5670bc4dc21c1049e5227ab1e7e.nq.gz
│   ├── 9a5ce1b6015cc151710879f197f98dc1f4082aae.nq.gz
│   ├── 9bca27fe9bb3a87f575c2922da56ac7c0f5a9444.nq.gz
│   ├── a113f41571d0771ae069f0153e5d08fc750540e3.nq.gz
│   ├── a670a4e3a0991869aecc92bed6b244a141b95898.nq.gz
│   ├── abbc48ea17b7944ae608df0840e670481b65eb36.nq.gz
│   ├── b3292bdff8ed5429eedd7f409839979d408beb6a.nq.gz
│   ├── b7ea71e3273ee98f4d5b529beeec4473cd82a98f.nq.gz
│   ├── c055cafad5b42d5fd3b4c5fe028abfa0e259c469.nq.gz
│   ├── dc0365099d8d41407cb194d109f5e3fda0ab2371.nq.gz
│   ├── e0a71615b8b557a96186c89638c6c9b727c2e3fb.nq.gz
│   ├── e20513b8b35e6bd8b05566c0d2ecdc589ed06d4e.nq.gz
│   ├── ed4c15907f442d4814d003794c9322828dbd84a2.nq.gz
│   └── ffc853d415f74bc343c5dbd0a867c2b136dc7efb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2a5db4c0bba11dc6dff0110c298e3ab9d8521532.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[mitsuhiko/pluginbase](https://github.com/mitsuhiko/pluginbase)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
