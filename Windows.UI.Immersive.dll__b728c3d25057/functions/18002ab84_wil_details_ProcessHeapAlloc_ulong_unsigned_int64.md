# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002ab84`
- end: `0x18002ac22`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180023790`
- `0x1800267c0`
- `0x18003c5a8`
- `0x180058024`
- `0x180058794`
- `0x1800588d0`
- `0x180065030`

## callees

- `0x18002ab84`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002abe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002abe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002abcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002abcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ab98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ab98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002aba9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002aba9`

## string_xrefs

- `0x18002abc6`: `ntdll.dll`

## pseudocode

```c

```
