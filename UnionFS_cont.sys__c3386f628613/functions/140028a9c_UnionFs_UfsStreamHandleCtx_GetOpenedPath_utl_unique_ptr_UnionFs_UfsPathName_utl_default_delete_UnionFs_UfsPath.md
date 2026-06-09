# UnionFs::UfsStreamHandleCtx::GetOpenedPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140028a9c`
- end: `0x140028ba1`
- name: `?GetOpenedPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140025168`
- `0x140036c78`

## callees

- `0x140028a9c`
- `0x140043dc0`
- `0x140056afc`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140028ad6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028ad6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b89`

## string_xrefs

- `0x140028b06`: `PUSH: Combining OpenedScratchRoot, OpenedRelativePath`
- `0x140028b17`: `UnionFs::UfsStreamHandleCtx::GetOpenedPath`

## pseudocode

```c

```
