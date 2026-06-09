# ShouldCaptureSnapshot

- ea: `0x1400450ac`
- end: `0x1400452c2`
- name: `ShouldCaptureSnapshot`
- size: `534`
- prototype: `__int64 __fastcall(HANDLE hProcess, HANDLE ThreadHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140044abc`

## callees

- `0x1400030a8`
- `0x140011fc8`
- `0x14001211c`
- `0x140014474`
- `0x14001589c`
- `0x1400450ac`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x14004514e`
- `ntdll!NtQueryInformationProcess` at `0x1400451f0`
- `ntdll!NtQueryInformationProcess` at `0x140045262`
- `ntdll!NtQueryInformationProcess` at `0x14004514e`
- `ntdll!NtQueryInformationProcess` at `0x1400451f0`
- `ntdll!NtQueryInformationProcess` at `0x140045262`
- `ntdll!RtlNtStatusToDosError` at `0x140045228`
- `ntdll!RtlNtStatusToDosError` at `0x14004529a`
- `ntdll!RtlNtStatusToDosError` at `0x140045228`
- `ntdll!RtlNtStatusToDosError` at `0x14004529a`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x140045102`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x140045102`

## pseudocode

```c

```
