# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14001b1b8`
- end: `0x14001b279`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `193`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005330`
- `0x1400056f4`
- `0x14001d978`
- `0x140021218`

## callees

- `0x14001b1b8`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001b217`
- `KERNEL32!GetModuleHandleW` at `0x14001b217`
- `KERNEL32!HeapAlloc` at `0x14001b1ed`
- `KERNEL32!HeapAlloc` at `0x14001b1ed`
- `KERNEL32!GetProcAddress` at `0x14001b232`
- `KERNEL32!GetProcAddress` at `0x14001b232`
- `KERNEL32!GetProcessHeap` at `0x14001b1d6`
- `KERNEL32!GetProcessHeap` at `0x14001b1d6`

## string_xrefs

- `0x14001b210`: `ntdll.dll`

## pseudocode

```c

```
