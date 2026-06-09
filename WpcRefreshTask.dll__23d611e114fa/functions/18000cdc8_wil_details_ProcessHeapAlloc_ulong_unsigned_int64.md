# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000cdc8`
- end: `0x18000ce66`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b298`
- `0x18000bc50`
- `0x18000c220`
- `0x18000d384`
- `0x180010e64`
- `0x180013a84`

## callees

- `0x18000cdc8`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cded`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cddc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cddc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ce26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ce26`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ce11`

## string_xrefs

- `0x18000ce0a`: `ntdll.dll`

## pseudocode

```c

```
