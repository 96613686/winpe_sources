# UnionFs::UfsStreamHandleCtx::GetOpenedPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x140028b3c`
- end: `0x140028c41`
- name: `?GetOpenedPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140025208`
- `0x140036db8`

## callees

- `0x140028b3c`
- `0x140043f40`
- `0x140056c7c`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140028b76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028bf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028b76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028bf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c29`

## string_xrefs

- `0x140028ba6`: `PUSH: Combining OpenedScratchRoot, OpenedRelativePath`
- `0x140028bb7`: `UnionFs::UfsStreamHandleCtx::GetOpenedPath`

## pseudocode

```c

```
