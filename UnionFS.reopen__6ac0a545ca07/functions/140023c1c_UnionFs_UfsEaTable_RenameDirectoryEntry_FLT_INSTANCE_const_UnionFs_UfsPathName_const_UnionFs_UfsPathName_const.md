# UnionFs::UfsEaTable::RenameDirectoryEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &)

- ea: `0x140023c1c`
- end: `0x140023e14`
- name: `?RenameDirectoryEntry@UfsEaTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@@Z`
- size: `504`
- prototype: `__int64 __fastcall(UnionFs::UfsEaTable *__hidden this, const struct _FLT_INSTANCE *, const struct UnionFs::UfsPathName *, const struct UnionFs::UfsPathName *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002ca90`

## callees

- `0x14000efa0`
- `0x140023c1c`
- `0x14004df10`
- `0x14004eac4`
- `0x140056c7c`
- `0x140079d8c`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140023d68`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023dd9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023d68`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023dd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023d74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023de5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023d74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023de5`

## string_xrefs

- `0x140023d22`: `PUSH: Upadting paths in EA payloads`
- `0x140023d33`: `UnionFs::UfsEaTable::RenameDirectoryEntry`

## pseudocode

```c

```
