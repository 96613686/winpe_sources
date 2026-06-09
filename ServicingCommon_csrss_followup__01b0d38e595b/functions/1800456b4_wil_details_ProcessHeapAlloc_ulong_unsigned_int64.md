# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800456b4`
- end: `0x18004575d`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800232ac`
- `0x180045520`
- `0x180045938`
- `0x180045abc`
- `0x18004ad18`

## callees

- `0x180043e2c`
- `0x1800456b4`
- `0x18009e020`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800456df`
- `KERNEL32!HeapAlloc` at `0x1800456df`
- `KERNEL32!GetProcessHeap` at `0x1800456c8`
- `KERNEL32!GetProcessHeap` at `0x1800456c8`
- `KERNEL32!GetModuleHandleW` at `0x180045709`
- `KERNEL32!GetModuleHandleW` at `0x180045709`

## string_xrefs

- `0x180045702`: `ntdll.dll`

## pseudocode

```c

```
