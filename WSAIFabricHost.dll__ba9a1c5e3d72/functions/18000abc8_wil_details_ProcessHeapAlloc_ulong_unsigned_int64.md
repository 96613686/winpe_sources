# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000abc8`
- end: `0x18000ac66`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009608`
- `0x180009dd0`
- `0x18000a3a0`
- `0x18000b154`
- `0x18000d264`
- `0x1800111dc`

## callees

- `0x18000abc8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ac26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ac26`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abdc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abed`

## string_xrefs

- `0x18000ac0a`: `ntdll.dll`

## pseudocode

```c

```
