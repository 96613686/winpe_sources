# UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140028990`
- end: `0x140028b36`
- name: `?GetNormalizedScratchRootPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140036db8`

## callees

- `0x14000f81c`
- `0x140028990`
- `0x1400448c8`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400289d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028acd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400289d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028acd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b16`

## string_xrefs

- `0x140028a83`: `PUSH: Copying scratch root path`
- `0x140028a1a`: `UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath`
- `0x140028a94`: `UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath`

## pseudocode

```c

```
