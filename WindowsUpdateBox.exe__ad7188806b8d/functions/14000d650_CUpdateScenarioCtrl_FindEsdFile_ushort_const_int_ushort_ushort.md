# CUpdateScenarioCtrl::FindEsdFile(ushort const *,int *,ushort * *,ushort * *)

- ea: `0x14000d650`
- end: `0x14000da8d`
- name: `?FindEsdFile@CUpdateScenarioCtrl@@AEAAJPEBGPEAHPEAPEAG2@Z`
- size: `1085`
- prototype: `__int64 __fastcall(CUpdateScenarioCtrl *__hidden this, const unsigned __int16 *, int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x140009020`
- `0x140011770`

## callees

- `0x140002116`
- `0x140002a98`
- `0x1400076c8`
- `0x140007cb0`
- `0x140009f00`
- `0x14000d650`
- `0x1400135b8`
- `0x140016bb4`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000d78c`
- `KERNEL32!HeapFree` at `0x14000d81f`
- `KERNEL32!HeapFree` at `0x14000d9db`
- `KERNEL32!HeapFree` at `0x14000da08`
- `KERNEL32!HeapFree` at `0x14000da35`
- `KERNEL32!HeapFree` at `0x14000d78c`
- `KERNEL32!HeapFree` at `0x14000d81f`
- `KERNEL32!HeapFree` at `0x14000d9db`
- `KERNEL32!HeapFree` at `0x14000da08`
- `KERNEL32!HeapFree` at `0x14000da35`
- `KERNEL32!GetProcessHeap` at `0x14000d777`
- `KERNEL32!GetProcessHeap` at `0x14000d80a`
- `KERNEL32!GetProcessHeap` at `0x14000d9c6`
- `KERNEL32!GetProcessHeap` at `0x14000d9f3`
- `KERNEL32!GetProcessHeap` at `0x14000da20`
- `KERNEL32!GetProcessHeap` at `0x14000d777`
- `KERNEL32!GetProcessHeap` at `0x14000d80a`
- `KERNEL32!GetProcessHeap` at `0x14000d9c6`
- `KERNEL32!GetProcessHeap` at `0x14000d9f3`
- `KERNEL32!GetProcessHeap` at `0x14000da20`
- `KERNEL32!GetLastError` at `0x14000d8c1`
- `KERNEL32!GetLastError` at `0x14000d8d2`
- `KERNEL32!GetLastError` at `0x14000d8c1`
- `KERNEL32!GetLastError` at `0x14000d8d2`
- `KERNEL32!FindFirstFileW` at `0x14000d753`
- `KERNEL32!FindFirstFileW` at `0x14000d753`
- `KERNEL32!GetFileAttributesW` at `0x14000d862`
- `KERNEL32!GetFileAttributesW` at `0x14000d862`
- `KERNEL32!FindClose` at `0x14000d9b5`
- `KERNEL32!FindClose` at `0x14000d9b5`
- `KERNEL32!FindNextFileW` at `0x14000d8ad`
- `KERNEL32!FindNextFileW` at `0x14000d8ad`

## string_xrefs

- `0x14000d96c`: `CUpdateScenarioCtrl::FindEsdFile`

## pseudocode

```c

```
