# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001b940`
- end: `0x18001b9de`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a5f0`
- `0x18000b330`
- `0x180023eec`
- `0x18002401c`
- `0x1800255e4`
- `0x180025818`
- `0x1800267f4`

## callees

- `0x18001b940`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b989`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b989`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b99e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b99e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b954`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b954`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b965`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b965`

## string_xrefs

- `0x18001b982`: `ntdll.dll`

## pseudocode

```c

```
