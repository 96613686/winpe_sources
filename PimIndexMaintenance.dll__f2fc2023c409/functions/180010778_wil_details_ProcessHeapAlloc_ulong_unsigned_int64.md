# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010778`
- end: `0x18001080e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010508`
- `0x180010fdc`
- `0x180011154`

## callees

- `0x18000dd50`
- `0x180010778`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800107c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800107c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001078c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001078c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001079d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001079d`

## string_xrefs

- `0x1800107ba`: `ntdll.dll`

## pseudocode

```c

```
