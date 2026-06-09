# UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x1400288f0`
- end: `0x140028a96`
- name: `?GetNormalizedScratchRootPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140036c78`

## callees

- `0x14000f7fc`
- `0x1400288f0`
- `0x140044748`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140028933`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028a2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028933`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028a2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028a76`

## string_xrefs

- `0x1400289e3`: `PUSH: Copying scratch root path`
- `0x14002897a`: `UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath`
- `0x1400289f4`: `UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath`

## pseudocode

```c

```
