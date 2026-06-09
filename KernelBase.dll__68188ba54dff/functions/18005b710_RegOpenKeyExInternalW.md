# RegOpenKeyExInternalW

- ea: `0x18005b710`
- end: `0x18005bb6c`
- name: `RegOpenKeyExInternalW`
- size: `1116`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, PCWSTR SourceString@<rdx>, PHANDLE, __int64)`
- caller_count: `42`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800496e0`
- `0x18004cdd0`
- `0x18004d3b0`
- `0x18004f930`
- `0x180050aa0`
- `0x180050ee0`
- `0x180051190`
- `0x180051660`
- `0x1800521a0`
- `0x180053f44`
- `0x180058910`
- `0x180059550`
- `0x18005b6e0`
- `0x180061b00`
- `0x180092a10`
- `0x180093cec`
- `0x18009484c`
- `0x180095960`
- `0x180095b20`
- `0x180095e50`
- `0x1800962c4`
- `0x18009858c`
- `0x180099a60`
- `0x1800a5fac`
- `0x1800a6520`
- `0x1800b5200`
- `0x1800d8f00`
- `0x1800de1d4`
- `0x1800f4f90`
- `0x180101fd0`
- `0x180107630`
- `0x18010b6a8`
- `0x18010bed4`
- `0x180124590`
- `0x18012469c`
- `0x180133220`
- `0x1801334e0`
- `0x18014258c`
- `0x1801500d8`
- `0x180157f00`
- `0x180174054`
- `0x180181ab8`

## callees

- `0x18005b460`
- `0x18005b710`
- `0x18005bb80`
- `0x18005bf10`
- `0x18005d2c0`
- `0x1800a6e58`
- `0x18012d578`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18005b8b2`
- `ntdll!RtlEnterCriticalSection` at `0x18005b8b2`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b8e4`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b8e4`
- `ntdll!RtlNtStatusToDosError` at `0x18005ba83`
- `ntdll!RtlNtStatusToDosError` at `0x18005bb3d`
- `ntdll!RtlNtStatusToDosError` at `0x18005ba83`
- `ntdll!RtlNtStatusToDosError` at `0x18005bb3d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005b8a0`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005b8a0`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005b7fb`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005b7fb`
- `ntdll!NtClose` at `0x18005b8ef`
- `ntdll!NtClose` at `0x18005b8ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b974`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b974`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b9a5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b9a5`
- `ntdll!RtlFreeHeap` at `0x18005b962`
- `ntdll!RtlFreeHeap` at `0x18005b9ce`
- `ntdll!RtlFreeHeap` at `0x18005b962`
- `ntdll!RtlFreeHeap` at `0x18005b9ce`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005bb0e`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005bb0e`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005ba2e`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005ba2e`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18005bac8`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18005bac8`

## pseudocode

```c

```
