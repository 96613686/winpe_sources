# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180024240`
- end: `0x1800242d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `13`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001f30c`
- `0x18003b370`
- `0x18003b7b0`
- `0x18003bbe0`
- `0x18003cb10`
- `0x18003cc3c`
- `0x18003d2f0`
- `0x18003d9b0`
- `0x18003dd48`
- `0x180048760`
- `0x180048b90`
- `0x180049f10`
- `0x18004a400`

## callees

- `0x180024240`
- `0x18003a4f0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024289`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024289`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024265`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024265`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024254`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024254`

## string_xrefs

- `0x180024282`: `ntdll.dll`

## pseudocode

```c

```
