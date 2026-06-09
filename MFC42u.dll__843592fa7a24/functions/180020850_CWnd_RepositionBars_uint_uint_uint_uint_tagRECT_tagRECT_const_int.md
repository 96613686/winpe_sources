# CWnd::RepositionBars(uint,uint,uint,uint,tagRECT *,tagRECT const *,int)

- ea: `0x180020850`
- end: `0x180020a5e`
- name: `?RepositionBars@CWnd@@QEAAXIIIIPEAUtagRECT@@PEBU2@H@Z`
- size: `526`
- prototype: `void __fastcall(CWnd *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, LPRECT lprcDst, const struct tagRECT *, int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180041c30`
- `0x180092870`
- `0x180098500`
- `0x1800b2ab0`

## callees

- `0x1800122f0`
- `0x180012d60`
- `0x180020850`
- `0x18002c3b0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!GetWindow` at `0x18002091c`
- `USER32!GetWindow` at `0x18002091c`
- `USER32!SendMessageW` at `0x180020a08`
- `USER32!SendMessageW` at `0x180020a08`
- `USER32!GetDlgCtrlID` at `0x1800208f5`
- `USER32!GetDlgCtrlID` at `0x1800208f5`
- `USER32!GetTopWindow` at `0x1800208dc`
- `USER32!GetTopWindow` at `0x1800208dc`
- `USER32!GetClientRect` at `0x180020975`
- `USER32!GetClientRect` at `0x180020975`
- `USER32!BeginDeferWindowPos` at `0x1800208cf`
- `USER32!BeginDeferWindowPos` at `0x1800208cf`
- `USER32!CopyRect` at `0x180020a1f`
- `USER32!CopyRect` at `0x180020a1f`
- `USER32!EndDeferWindowPos` at `0x1800209d3`
- `USER32!EndDeferWindowPos` at `0x1800209d3`

## pseudocode

```c

```
