# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140048d98`
- end: `0x140048e2e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400488c8`
- `0x140048a1c`
- `0x140049ce4`
- `0x14004a168`
- `0x14004b1d4`

## callees

- `0x14004433c`
- `0x140048d98`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140048dac`
- `KERNEL32!GetProcessHeap` at `0x140048dac`
- `KERNEL32!GetModuleHandleW` at `0x140048de1`
- `KERNEL32!GetModuleHandleW` at `0x140048de1`
- `KERNEL32!HeapAlloc` at `0x140048dbd`
- `KERNEL32!HeapAlloc` at `0x140048dbd`

## string_xrefs

- `0x140048dda`: `ntdll.dll`

## pseudocode

```c

```
