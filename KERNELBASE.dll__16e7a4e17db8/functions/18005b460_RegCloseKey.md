# RegCloseKey

- ea: `0x18005b460`
- end: `0x18005b6cc`
- name: `RegCloseKey`
- size: `620`
- prototype: `LSTATUS __stdcall(HKEY hKey)`
- caller_count: `91`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180034810`
- `0x1800496e0`
- `0x18004cdd0`
- `0x18004d3b0`
- `0x18004f558`
- `0x18004f930`
- `0x180050aa0`
- `0x180050ee0`
- `0x180051190`
- `0x180051660`
- `0x1800521a0`
- `0x180058910`
- `0x180059030`
- `0x180059550`
- `0x18005a800`
- `0x18005af10`
- `0x18005b710`
- `0x18005bb80`
- `0x18005d0a0`
- `0x18005e9c0`
- `0x180061b00`
- `0x180064d94`
- `0x180064e90`
- `0x180065588`
- `0x180092a10`
- `0x1800930b0`
- `0x180093380`
- `0x180093cec`
- `0x180093d60`
- `0x1800945b4`
- `0x18009484c`
- `0x180094fc0`
- `0x180095b20`
- `0x180095e50`
- `0x180096070`
- `0x1800962c4`
- `0x1800963c0`
- `0x180096db0`
- `0x180097a88`
- `0x180097b10`
- `0x180097ca0`
- `0x1800984c0`
- `0x180099814`
- `0x180099b64`
- `0x180099bb0`
- `0x180099f10`
- `0x1800a5fac`
- `0x1800a6520`
- `0x1800a6590`
- `0x1800a6880`

## callees

- `0x18005b460`
- `0x18005d2c0`
- `0x1800df540`
- `0x18012d578`
- `0x180197010`

## import_xrefs

- `ntdll!SbSelectProcedure` at `0x18005b4c4`
- `ntdll!SbSelectProcedure` at `0x18005b4c4`
- `ntdll!RtlEnterCriticalSection` at `0x18005b52e`
- `ntdll!RtlEnterCriticalSection` at `0x18005b52e`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b564`
- `ntdll!RtlLeaveCriticalSection` at `0x18005b564`
- `ntdll!RtlNtStatusToDosError` at `0x18005b69c`
- `ntdll!RtlNtStatusToDosError` at `0x18005b69c`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005b51c`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180190012`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005b51c`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180190012`
- `ntdll!NtClose` at `0x18005b56f`
- `ntdll!NtClose` at `0x18005b56f`
- `ntdll!NtResetEvent` at `0x180190053`
- `ntdll!NtResetEvent` at `0x180190053`
- `ntdll!NtQueryEvent` at `0x180190031`
- `ntdll!NtQueryEvent` at `0x180190031`
- `ntdll!RtlFreeHeap` at `0x18005b5e1`
- `ntdll!RtlFreeHeap` at `0x18005b5e1`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005b682`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005b682`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCloseKey` at `0x18005b6b4`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCloseKey` at `0x18005b6b4`

## pseudocode

```c

```
