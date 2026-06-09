# BipIsUserActive

- ea: `0x180014ea0`
- end: `0x180014f92`
- name: `BipIsUserActive`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000e610`
- `0x1800144f4`

## callees

- `0x180014ea0`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180014f4f`
- `ntdll!RtlReleaseSRWLockShared` at `0x180014f4f`
- `ntdll!RtlAcquireSRWLockShared` at `0x180014eec`
- `ntdll!RtlAcquireSRWLockShared` at `0x180014eec`
- `ntdll!RtlEqualSid` at `0x180014f24`
- `ntdll!RtlEqualSid` at `0x180014f24`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180014f73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180014f73`

## pseudocode

```c

```
