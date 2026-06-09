# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c784`
- end: `0x18000c822`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b43c`
- `0x18000c194`
- `0x18000c2f8`
- `0x18000d6d0`
- `0x18000db60`
- `0x18000edbc`

## callees

- `0x18000c784`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c7a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c7a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c798`

## string_xrefs

- `0x18000c7c6`: `ntdll.dll`

## pseudocode

```c

```
