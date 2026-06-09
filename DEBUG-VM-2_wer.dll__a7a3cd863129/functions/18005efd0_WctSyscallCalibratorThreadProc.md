# WctSyscallCalibratorThreadProc

- ea: `0x18005efd0`
- end: `0x18005f0ab`
- name: `WctSyscallCalibratorThreadProc`
- size: `219`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18005efd0`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18005f041`
- `ntdll!NtWaitForSingleObject` at `0x18005f041`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f04d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f04d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f064`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f064`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005f05a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005f05a`

## pseudocode

```c

```
