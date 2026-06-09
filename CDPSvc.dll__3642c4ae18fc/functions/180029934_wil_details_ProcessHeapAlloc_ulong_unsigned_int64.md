# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180029934`
- end: `0x1800299ca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001961c`
- `0x18002896c`
- `0x180029310`
- `0x180029440`
- `0x18002a0c4`
- `0x18002a2f8`

## callees

- `0x180027880`
- `0x180029934`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002997d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002997d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029959`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029959`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029948`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029948`

## string_xrefs

- `0x180029976`: `ntdll.dll`

## pseudocode

```c

```
