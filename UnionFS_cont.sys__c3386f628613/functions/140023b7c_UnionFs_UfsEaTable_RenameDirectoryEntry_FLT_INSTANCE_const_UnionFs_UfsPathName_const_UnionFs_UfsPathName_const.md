# UnionFs::UfsEaTable::RenameDirectoryEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &)

- ea: `0x140023b7c`
- end: `0x140023d74`
- name: `?RenameDirectoryEntry@UfsEaTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@@Z`
- size: `504`
- prototype: `__int64 __fastcall(UnionFs::UfsEaTable *__hidden this, const struct _FLT_INSTANCE *, const struct UnionFs::UfsPathName *, const struct UnionFs::UfsPathName *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002c9f0`

## callees

- `0x14000efd0`
- `0x140023b7c`
- `0x14004dd90`
- `0x14004e944`
- `0x140056afc`
- `0x140079a6c`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140023cc8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023d39`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023cc8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023d39`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023cd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023d45`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023cd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023d45`

## string_xrefs

- `0x140023c82`: `PUSH: Upadting paths in EA payloads`
- `0x140023c93`: `UnionFs::UfsEaTable::RenameDirectoryEntry`

## pseudocode

```c

```
