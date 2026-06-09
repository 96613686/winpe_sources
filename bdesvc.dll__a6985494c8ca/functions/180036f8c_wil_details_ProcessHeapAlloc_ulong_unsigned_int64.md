# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180036f8c`
- end: `0x180037043`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002bcb8`
- `0x180036b9c`
- `0x180036cd4`
- `0x1800375f4`
- `0x1800379a8`

## callees

- `0x180036f8c`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036ffc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036ffc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036fe1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036fb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036fb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036fa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036fa0`

## string_xrefs

- `0x180036fda`: `ntdll.dll`

## pseudocode

```c

```
