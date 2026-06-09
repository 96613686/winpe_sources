# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800512d0`
- end: `0x18005136e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180051134`
- `0x18005199c`

## callees

- `0x1800512d0`
- `0x180066010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18005132e`
- `KERNEL32!GetProcAddress` at `0x18005132e`
- `KERNEL32!GetModuleHandleW` at `0x180051319`
- `KERNEL32!GetModuleHandleW` at `0x180051319`
- `KERNEL32!HeapAlloc` at `0x1800512f5`
- `KERNEL32!HeapAlloc` at `0x1800512f5`
- `KERNEL32!GetProcessHeap` at `0x1800512e4`
- `KERNEL32!GetProcessHeap` at `0x1800512e4`

## string_xrefs

- `0x180051312`: `ntdll.dll`

## pseudocode

```c

```
