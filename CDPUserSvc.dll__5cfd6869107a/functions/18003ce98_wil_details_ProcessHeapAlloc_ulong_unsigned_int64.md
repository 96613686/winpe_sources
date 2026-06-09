# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003ce98`
- end: `0x18003cf2e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800123f8`
- `0x18001dbbc`
- `0x18001df88`
- `0x18003d6f8`
- `0x18003da90`

## callees

- `0x18003a4fc`
- `0x18003ce98`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cee1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ceac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ceac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cebd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cebd`

## string_xrefs

- `0x18003ceda`: `ntdll.dll`

## pseudocode

```c

```
