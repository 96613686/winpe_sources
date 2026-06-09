# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ca84`
- end: `0x18000cb1a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b6ec`
- `0x18000c344`
- `0x18000c494`
- `0x18000e574`
- `0x18000e9f4`
- `0x18001018c`

## callees

- `0x18000878c`
- `0x18000ca84`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cacd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cacd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000caa9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000caa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca98`

## string_xrefs

- `0x18000cac6`: `ntdll.dll`

## pseudocode

```c

```
