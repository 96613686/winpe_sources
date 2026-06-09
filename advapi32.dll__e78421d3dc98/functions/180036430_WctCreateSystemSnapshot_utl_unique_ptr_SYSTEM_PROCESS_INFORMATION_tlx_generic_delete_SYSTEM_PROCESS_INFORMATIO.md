# WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)

- ea: `0x180036430`
- end: `0x180036521`
- name: `?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003a080`
- `0x18005ff74`

## callees

- `0x180036430`
- `0x18003b548`
- `0x18003d048`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180036477`
- `ntdll!NtQuerySystemInformation` at `0x180036477`
- `ntdll!RtlNtStatusToDosError` at `0x1800364e5`
- `ntdll!RtlNtStatusToDosError` at `0x1800364e5`
- `KERNEL32!LocalFree` at `0x180036456`
- `KERNEL32!LocalFree` at `0x180036493`
- `KERNEL32!LocalFree` at `0x18003650b`
- `KERNEL32!LocalFree` at `0x180036456`
- `KERNEL32!LocalFree` at `0x180036493`
- `KERNEL32!LocalFree` at `0x18003650b`

## pseudocode

```c

```
