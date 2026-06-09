# BipEnumerateUserContextIds

- ea: `0x180006808`
- end: `0x1800069bb`
- name: `BipEnumerateUserContextIds`
- size: `435`
- prototype: `__int64 __fastcall(unsigned __int64 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006760`

## callees

- `0x180006808`
- `0x1800069c4`
- `0x1800121b0`
- `0x18006a8d4`
- `0x18009467a`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000691b`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000691b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180006857`
- `ntdll!RtlAcquireSRWLockShared` at `0x180006857`
- `ntdll!RtlFreeHeap` at `0x18000694a`
- `ntdll!RtlFreeHeap` at `0x18000694a`
- `ntdll!RtlAllocateHeap` at `0x18000688c`
- `ntdll!RtlAllocateHeap` at `0x18000688c`
- `ntdll!RtlCopySid` at `0x1800068eb`
- `ntdll!RtlCopySid` at `0x1800068eb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006963`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006963`

## pseudocode

```c

```
