# CWnd::ScrollWindow(int,int,tagRECT const *,tagRECT const *)

- ea: `0x180040aa0`
- end: `0x180040baa`
- name: `?ScrollWindow@CWnd@@QEAAXHHPEBUtagRECT@@0@Z`
- size: `266`
- prototype: `void __fastcall(CWnd *__hidden this, int XAmount, int YAmount, RECT *lpRect, RECT *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180067750`
- `0x180067a90`
- `0x1800c9e10`

## callees

- `0x180020710`
- `0x180040aa0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!GetWindowRect` at `0x180040af8`
- `USER32!GetWindowRect` at `0x180040af8`
- `USER32!SetWindowPos` at `0x180040b38`
- `USER32!SetWindowPos` at `0x180040b38`
- `USER32!GetWindow` at `0x180040b46`
- `USER32!GetWindow` at `0x180040b46`
- `USER32!IsWindowVisible` at `0x180040ad3`
- `USER32!IsWindowVisible` at `0x180040ad3`
- `USER32!ScrollWindow` at `0x180040b68`
- `USER32!ScrollWindow` at `0x180040b68`

## pseudocode

```c

```
