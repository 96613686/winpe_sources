# PiiFilterDelete

- ea: `0x18005ac0c`
- end: `0x18005ac9a`
- name: `PiiFilterDelete`
- size: `142`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800505a8`
- `0x180050ca8`

## callees

- `0x18003fd58`
- `0x18005ac0c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18005ac35`
- `KERNEL32!HeapFree` at `0x18005ac63`
- `KERNEL32!HeapFree` at `0x18005ac35`
- `KERNEL32!HeapFree` at `0x18005ac63`
- `ntdll!RtlFreeHeap` at `0x18005ac89`
- `ntdll!RtlFreeHeap` at `0x18005ac89`

## pseudocode

```c

```
