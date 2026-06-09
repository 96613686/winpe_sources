# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180041148`
- end: `0x1800411f1`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002088c`
- `0x180041010`
- `0x180041304`
- `0x180041488`
- `0x180047bf8`

## callees

- `0x1800403e4`
- `0x180041148`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18004119d`
- `KERNEL32!GetModuleHandleW` at `0x18004119d`
- `KERNEL32!HeapAlloc` at `0x180041173`
- `KERNEL32!HeapAlloc` at `0x180041173`
- `KERNEL32!GetProcessHeap` at `0x18004115c`
- `KERNEL32!GetProcessHeap` at `0x18004115c`

## string_xrefs

- `0x180041196`: `ntdll.dll`

## pseudocode

```c

```
