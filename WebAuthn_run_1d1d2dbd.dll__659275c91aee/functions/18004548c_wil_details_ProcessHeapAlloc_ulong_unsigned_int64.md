# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004548c`
- end: `0x18004552a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d0e0`
- `0x18000d1d0`
- `0x18005ea30`
- `0x18005f010`
- `0x18005f160`
- `0x18005fc00`
- `0x18005fd3c`

## callees

- `0x18004548c`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800454ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800454ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800454d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800454d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800454b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800454b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800454a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800454a0`

## string_xrefs

- `0x1800454ce`: `ntdll.dll`

## pseudocode

```c

```
