# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140027708`
- end: `0x1400277bf`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003240`
- `0x140003b30`
- `0x14000cf88`
- `0x14002717c`
- `0x1400272b0`
- `0x140028314`
- `0x1400287c0`

## callees

- `0x140027708`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140027778`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140027778`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002775d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002775d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002771c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002771c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140027733`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140027733`

## string_xrefs

- `0x140027756`: `ntdll.dll`

## pseudocode

```c

```
