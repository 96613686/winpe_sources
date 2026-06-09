# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005998c`
- end: `0x180059a22`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004f404`
- `0x18005d300`
- `0x18005d464`
- `0x180065da0`
- `0x180065fd4`
- `0x180067680`

## callees

- `0x18005998c`
- `0x18005fc24`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800599d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800599d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800599b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800599b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800599a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800599a0`

## string_xrefs

- `0x1800599ce`: `ntdll.dll`

## pseudocode

```c

```
