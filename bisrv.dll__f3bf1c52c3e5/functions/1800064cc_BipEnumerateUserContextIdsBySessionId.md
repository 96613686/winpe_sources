# BipEnumerateUserContextIdsBySessionId

- ea: `0x1800064cc`
- end: `0x1800066c4`
- name: `BipEnumerateUserContextIdsBySessionId`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004b10`

## callees

- `0x1800064cc`
- `0x1800066cc`
- `0x1800069c4`
- `0x1800121b0`
- `0x18006a8d4`
- `0x18009467a`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000664e`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000664e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000653d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000653d`
- `ntdll!RtlFreeHeap` at `0x1800066a7`
- `ntdll!RtlFreeHeap` at `0x1800066a7`
- `ntdll!RtlAllocateHeap` at `0x1800065bb`
- `ntdll!RtlAllocateHeap` at `0x1800065bb`
- `ntdll!RtlCopySid` at `0x180006611`
- `ntdll!RtlCopySid` at `0x180006611`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006520`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006520`

## pseudocode

```c

```
