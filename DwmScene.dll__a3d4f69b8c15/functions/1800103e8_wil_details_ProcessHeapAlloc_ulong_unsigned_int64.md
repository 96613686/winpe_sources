# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800103e8`
- end: `0x180010486`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800101dc`
- `0x1800107f0`
- `0x180010b88`

## callees

- `0x1800103e8`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010431`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010431`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010446`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001040d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001040d`

## string_xrefs

- `0x18001042a`: `ntdll.dll`

## pseudocode

```c

```
