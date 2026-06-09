# ShouldCaptureSnapshot

- ea: `0x1400481cc`
- end: `0x140048407`
- name: `ShouldCaptureSnapshot`
- size: `571`
- prototype: `__int64 __fastcall(HANDLE hProcess, HANDLE ThreadHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140047b58`

## callees

- `0x1400030f8`
- `0x14001282c`
- `0x140012994`
- `0x140014f14`
- `0x140016434`
- `0x1400481cc`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140048274`
- `ntdll!NtQueryInformationProcess` at `0x14004831c`
- `ntdll!NtQueryInformationProcess` at `0x14004839a`
- `ntdll!NtQueryInformationProcess` at `0x140048274`
- `ntdll!NtQueryInformationProcess` at `0x14004831c`
- `ntdll!NtQueryInformationProcess` at `0x14004839a`
- `ntdll!RtlNtStatusToDosError` at `0x14004835a`
- `ntdll!RtlNtStatusToDosError` at `0x1400483d8`
- `ntdll!RtlNtStatusToDosError` at `0x14004835a`
- `ntdll!RtlNtStatusToDosError` at `0x1400483d8`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x140048222`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x140048222`

## pseudocode

```c

```
