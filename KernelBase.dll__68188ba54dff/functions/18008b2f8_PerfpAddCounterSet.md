# PerfpAddCounterSet

- ea: `0x18008b2f8`
- end: `0x18008b4fb`
- name: `PerfpAddCounterSet`
- size: `515`
- prototype: `__int64 __fastcall(PVOID TableContext, void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18008b510`

## callees

- `0x18008a7b8`
- `0x18008b2f8`
- `0x180188eb9`
- `0x180197010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18008b421`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18008b421`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18008b44b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18008b44b`
- `ntdll!RtlInitializeSRWLock` at `0x18008b473`
- `ntdll!RtlInitializeSRWLock` at `0x18008b4af`
- `ntdll!RtlInitializeSRWLock` at `0x18008b473`
- `ntdll!RtlInitializeSRWLock` at `0x18008b4af`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18008b436`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18008b436`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18008b4a2`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18008b4a2`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18008b4dc`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18008b4dc`

## pseudocode

```c

```
