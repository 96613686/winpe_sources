# BipRemoveEventFromTableByPointer

- ea: `0x18000a46c`
- end: `0x18000a55a`
- name: `BipRemoveEventFromTableByPointer`
- size: `238`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800073e4`

## callees

- `0x1800075f8`
- `0x18000a46c`
- `0x18000a9f0`
- `0x18001027c`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18000a533`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000a533`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a48a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a48a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a4be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a4be`
- `ntdll!RtlWakeAddressAll` at `0x18000a50a`
- `ntdll!RtlWakeAddressAll` at `0x18000a50a`
- `ntdll!RtlFreeHeap` at `0x18000a54f`
- `ntdll!RtlFreeHeap` at `0x18000a54f`

## pseudocode

```c

```
