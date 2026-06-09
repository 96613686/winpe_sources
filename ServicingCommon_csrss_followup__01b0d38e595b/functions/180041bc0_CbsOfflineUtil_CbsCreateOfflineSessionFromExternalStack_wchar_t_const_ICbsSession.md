# CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack(wchar_t const *,ICbsSession * *)

- ea: `0x180041bc0`
- end: `0x180041c82`
- name: `?CbsCreateOfflineSessionFromExternalStack@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUICbsSession@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this, const wchar_t *, struct ICbsSession **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18007c1b4`

## callees

- `0x18001bae0`
- `0x180040f00`
- `0x180041bc0`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180041c4d`
- `KERNEL32!GetProcessHeap` at `0x180041c4d`
- `KERNEL32!HeapFree` at `0x180041c63`
- `KERNEL32!HeapFree` at `0x180041c63`

## string_xrefs

- `0x180041bf7`: `\cbscore.dll`

## pseudocode

```c

```
