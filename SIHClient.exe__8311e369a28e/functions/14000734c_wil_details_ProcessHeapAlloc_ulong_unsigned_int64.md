# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000734c`
- end: `0x1400073ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000312c`
- `0x14000923c`
- `0x1400096a0`
- `0x14000aabc`

## callees

- `0x14000734c`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007360`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007371`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007371`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400073aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400073aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007395`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007395`

## string_xrefs

- `0x14000738e`: `ntdll.dll`

## pseudocode

```c

```
