# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000bc08`
- end: `0x18000bcbf`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a660`
- `0x18000e8ec`
- `0x18002bab0`
- `0x180030a3c`

## callees

- `0x18000bc08`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bc33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bc33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc1c`

## string_xrefs

- `0x18000bc56`: `ntdll.dll`

## pseudocode

```c

```
