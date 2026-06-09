# BaseRegSetValueInternal

- ea: `0x180094aa0`
- end: `0x180094d61`
- name: `BaseRegSetValueInternal`
- size: `705`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, ULONG Type, PVOID Data, ULONG)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180096490`
- `0x1800980d0`

## callees

- `0x18005e150`
- `0x180094aa0`
- `0x18012d578`
- `0x18012ffa4`
- `0x1801839dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180094beb`
- `ntdll!RtlNtStatusToDosError` at `0x180094d49`
- `ntdll!RtlNtStatusToDosError` at `0x180094d56`
- `ntdll!RtlNtStatusToDosError` at `0x180094beb`
- `ntdll!RtlNtStatusToDosError` at `0x180094d49`
- `ntdll!RtlNtStatusToDosError` at `0x180094d56`
- `ntdll!NtSetValueKey` at `0x180094bc3`
- `ntdll!NtSetValueKey` at `0x180094d25`
- `ntdll!NtSetValueKey` at `0x180191268`
- `ntdll!NtSetValueKey` at `0x180094bc3`
- `ntdll!NtSetValueKey` at `0x180094d25`
- `ntdll!NtSetValueKey` at `0x180191268`
- `ntdll!NtClose` at `0x180094c93`
- `ntdll!NtClose` at `0x180191275`
- `ntdll!NtClose` at `0x180094c93`
- `ntdll!NtClose` at `0x180191275`
- `ntdll!RtlFreeHeap` at `0x180094d41`
- `ntdll!RtlFreeHeap` at `0x180094d41`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegSetValue` at `0x180094c48`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegSetValue` at `0x180094c48`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvGetPreSetValue` at `0x180094b60`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvGetPreSetValue` at `0x180094b60`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetValueKey` at `0x180094b91`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvSetValueKey` at `0x180094b91`

## pseudocode

```c

```
