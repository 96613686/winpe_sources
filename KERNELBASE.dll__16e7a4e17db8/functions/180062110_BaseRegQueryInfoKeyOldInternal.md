# BaseRegQueryInfoKeyOldInternal

- ea: `0x180062110`
- end: `0x18006273d`
- name: `BaseRegQueryInfoKeyOldInternal`
- size: `1581`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180061d20`
- `0x180111580`

## callees

- `0x18005e150`
- `0x180061588`
- `0x180062110`
- `0x180062750`
- `0x180062d3c`
- `0x180062ea0`
- `0x180063310`
- `0x18012d119`
- `0x18012d578`
- `0x180188ec5`
- `0x180188f10`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x180062415`
- `ntdll!NtQuerySecurityObject` at `0x18006243f`
- `ntdll!NtQuerySecurityObject` at `0x180062415`
- `ntdll!NtQuerySecurityObject` at `0x18006243f`
- `ntdll!RtlNtStatusToDosError` at `0x1800623f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800626f1`
- `ntdll!RtlNtStatusToDosError` at `0x1800623f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800626f1`
- `ntdll!NtClose` at `0x1800625cd`
- `ntdll!NtClose` at `0x1800625cd`
- `ntdll!NtQueryKey` at `0x180062271`
- `ntdll!NtQueryKey` at `0x1800626b6`
- `ntdll!NtQueryKey` at `0x180062271`
- `ntdll!NtQueryKey` at `0x1800626b6`
- `ntdll!RtlFreeHeap` at `0x1800626d5`
- `ntdll!RtlFreeHeap` at `0x18006271e`
- `ntdll!RtlFreeHeap` at `0x1800626d5`
- `ntdll!RtlFreeHeap` at `0x18006271e`
- `ntdll!RtlAllocateHeap` at `0x18006268a`
- `ntdll!RtlAllocateHeap` at `0x18006268a`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegQueryInfoKey` at `0x1800623c2`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegQueryInfoKey` at `0x1800623c2`

## pseudocode

```c

```
