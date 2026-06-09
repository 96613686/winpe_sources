# CTimeZoneLogicSingleton::_EnablePrivilege(_TOKEN_PRIVILEGES * *,ulong *,long)

- ea: `0x1800ec040`
- end: `0x1800ec170`
- name: `?_EnablePrivilege@CTimeZoneLogicSingleton@@AEAA_NPEAPEAU_TOKEN_PRIVILEGES@@PEAKJ@Z`
- size: `304`
- prototype: `bool(CTimeZoneLogicSingleton *__hidden this, struct _TOKEN_PRIVILEGES **, unsigned int *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800e893c`

## callees

- `0x1800ec040`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ec09d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ec0da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ec09d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ec0da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec141`
- `ntdll!NtClose` at `0x1800ec152`
- `ntdll!NtClose` at `0x1800ec152`
- `ntdll!NtAdjustPrivilegesToken` at `0x1800ec108`
- `ntdll!NtAdjustPrivilegesToken` at `0x1800ec108`
- `ntdll!NtOpenProcessToken` at `0x1800ec078`
- `ntdll!NtOpenProcessToken` at `0x1800ec078`

## pseudocode

```c

```
