# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003dfc0`
- end: `0x18003e068`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002ad5c`
- `0x18003de88`
- `0x1800481c4`
- `0x180106cec`
- `0x18011374c`
- `0x180113974`

## callees

- `0x18003dfc0`
- `0x180130010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003e013`
- `KERNEL32!GetModuleHandleW` at `0x18003e013`
- `KERNEL32!GetProcessHeap` at `0x18003dfde`
- `KERNEL32!GetProcessHeap` at `0x18003dfde`
- `KERNEL32!GetProcAddress` at `0x18003e028`
- `KERNEL32!GetProcAddress` at `0x18003e028`
- `KERNEL32!HeapAlloc` at `0x18003dfef`
- `KERNEL32!HeapAlloc` at `0x18003dfef`

## string_xrefs

- `0x18003e00c`: `ntdll.dll`

## pseudocode

```c

```
