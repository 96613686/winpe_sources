# WpnDowncaseStr(ushort const *,ushort * *)

- ea: `0x1800658bc`
- end: `0x180065a37`
- name: `?WpnDowncaseStr@@YAJPEBGPEAPEAG@Z`
- size: `379`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180064d7c`

## callees

- `0x18002ee38`
- `0x1800658bc`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800bc541`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800659a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800659a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065994`
- `ntdll!RtlFreeUnicodeString` at `0x180065a1f`
- `ntdll!RtlFreeUnicodeString` at `0x180065a1f`
- `ntdll!RtlInitUnicodeString` at `0x1800658fc`
- `ntdll!RtlInitUnicodeString` at `0x1800658fc`
- `ntdll!RtlDowncaseUnicodeString` at `0x18006590f`
- `ntdll!RtlDowncaseUnicodeString` at `0x18006590f`
- `ntdll!RtlNtStatusToDosError` at `0x18006591f`
- `ntdll!RtlNtStatusToDosError` at `0x18006591f`

## string_xrefs

- `0x18006593d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x1800659b9`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`

## pseudocode

```c

```
