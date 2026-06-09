# WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)

- ea: `0x18003a670`
- end: `0x18003a780`
- name: `?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003e878`
- `0x18006c87c`

## callees

- `0x18003a670`
- `0x18003e68c`
- `0x18004165c`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18003a6bd`
- `ntdll!NtQuerySystemInformation` at `0x18003a6bd`
- `ntdll!RtlNtStatusToDosError` at `0x18003a737`
- `ntdll!RtlNtStatusToDosError` at `0x18003a737`
- `KERNEL32!LocalFree` at `0x18003a696`
- `KERNEL32!LocalFree` at `0x18003a6df`
- `KERNEL32!LocalFree` at `0x18003a763`
- `KERNEL32!LocalFree` at `0x18003a696`
- `KERNEL32!LocalFree` at `0x18003a6df`
- `KERNEL32!LocalFree` at `0x18003a763`

## pseudocode

```c

```
