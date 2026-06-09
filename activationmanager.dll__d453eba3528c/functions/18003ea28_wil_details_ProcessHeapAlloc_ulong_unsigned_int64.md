# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003ea28`
- end: `0x18003eabe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180046f1c`
- `0x18004be1c`
- `0x1800607ec`
- `0x18006091c`
- `0x180061030`

## callees

- `0x18003ea28`
- `0x18005f3b0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ea71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ea71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ea3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ea3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ea4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ea4d`

## string_xrefs

- `0x18003ea6a`: `ntdll.dll`

## pseudocode

```c

```
