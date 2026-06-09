# CRichEditView::PrintInsideRect(CDC *,tagRECT &,long,long,int)

- ea: `0x1800a0840`
- end: `0x1800a098a`
- name: `?PrintInsideRect@CRichEditView@@QEAAJPEAVCDC@@AEAUtagRECT@@JJH@Z`
- size: `330`
- prototype: `__int64 __fastcall(CRichEditView *__hidden this, struct CDC *, struct tagRECT *, int, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800a0840`
- `0x1800d1fe0`

## import_xrefs

- `USER32!SendMessageW` at `0x1800a0932`
- `USER32!SendMessageW` at `0x1800a0946`
- `USER32!SendMessageW` at `0x1800a095b`
- `USER32!SendMessageW` at `0x1800a0932`
- `USER32!SendMessageW` at `0x1800a0946`
- `USER32!SendMessageW` at `0x1800a095b`
- `GDI32!ScaleWindowExtEx` at `0x1800a08f2`
- `GDI32!ScaleWindowExtEx` at `0x1800a08f2`
- `GDI32!GetDeviceCaps` at `0x1800a088a`
- `GDI32!GetDeviceCaps` at `0x1800a08a5`
- `GDI32!GetDeviceCaps` at `0x1800a08b3`
- `GDI32!GetDeviceCaps` at `0x1800a08c2`
- `GDI32!GetDeviceCaps` at `0x1800a08d3`
- `GDI32!GetDeviceCaps` at `0x1800a088a`
- `GDI32!GetDeviceCaps` at `0x1800a08a5`
- `GDI32!GetDeviceCaps` at `0x1800a08b3`
- `GDI32!GetDeviceCaps` at `0x1800a08c2`
- `GDI32!GetDeviceCaps` at `0x1800a08d3`

## pseudocode

```c

```
