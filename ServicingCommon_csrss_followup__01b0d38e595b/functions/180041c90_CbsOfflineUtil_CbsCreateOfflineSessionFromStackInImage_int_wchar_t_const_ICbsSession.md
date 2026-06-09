# CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(int,wchar_t const *,ICbsSession * *)

- ea: `0x180041c90`
- end: `0x180041d68`
- name: `?CbsCreateOfflineSessionFromStackInImage@CbsOfflineUtil@@UEAAJHPEB_WPEAPEAUICbsSession@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this, int, const wchar_t *, struct ICbsSession **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180043850`
- `0x18007c1b4`

## callees

- `0x18002d2b0`
- `0x180040f00`
- `0x180041c90`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180041d30`
- `KERNEL32!GetProcessHeap` at `0x180041d30`
- `KERNEL32!HeapFree` at `0x180041d44`
- `KERNEL32!HeapFree` at `0x180041d44`

## string_xrefs

- `0x180041cc9`: `cbscore.dll`

## pseudocode

```c

```
