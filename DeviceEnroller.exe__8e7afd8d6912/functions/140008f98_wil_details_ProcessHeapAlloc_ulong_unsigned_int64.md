# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140008f98`
- end: `0x140009036`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400074e8`
- `0x140007d20`
- `0x1400082f0`
- `0x140009774`
- `0x14000d1ac`
- `0x14001d160`

## callees

- `0x140008f98`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008ff6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008ff6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008fe1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008fe1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008fbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008fac`

## string_xrefs

- `0x140008fda`: `ntdll.dll`

## pseudocode

```c

```
