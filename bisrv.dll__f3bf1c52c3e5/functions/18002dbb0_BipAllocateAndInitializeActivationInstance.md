# BipAllocateAndInitializeActivationInstance

- ea: `0x18002dbb0`
- end: `0x18002dec9`
- name: `BipAllocateAndInitializeActivationInstance`
- size: `793`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011af0`
- `0x1800593b0`
- `0x18007d708`

## callees

- `0x18000b7a8`
- `0x18002dbb0`
- `0x18002ded0`
- `0x18006a8d4`
- `0x1800946a0`
- `0x180094730`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18002dcb0`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002dcb0`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002dc47`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002dc47`
- `ntdll!RtlFreeHeap` at `0x18002dd6e`
- `ntdll!RtlFreeHeap` at `0x18002dd6e`
- `ntdll!RtlAllocateHeap` at `0x18002de83`
- `ntdll!RtlAllocateHeap` at `0x18002de83`
- `ntdll!RtlEqualSid` at `0x18002dc88`
- `ntdll!RtlEqualSid` at `0x18002dc88`
- `ntdll!RtlPublishWnfStateData` at `0x18002de0b`
- `ntdll!RtlPublishWnfStateData` at `0x18002de0b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002de9d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002de9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002de18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002de18`

## pseudocode

```c

```
