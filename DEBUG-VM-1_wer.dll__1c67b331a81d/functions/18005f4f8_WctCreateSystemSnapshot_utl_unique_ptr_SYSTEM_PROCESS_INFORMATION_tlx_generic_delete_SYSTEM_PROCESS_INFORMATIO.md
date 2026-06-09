# WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)

- ea: `0x18005f4f8`
- end: `0x18005f611`
- name: `?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z`
- size: `281`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005e338`
- `0x18005f104`

## callees

- `0x18001c650`
- `0x18002cdd0`
- `0x18005f4f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f56b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005f56b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f58c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f58c`
- `ntdll!NtQuerySystemInformation` at `0x18005f541`
- `ntdll!NtQuerySystemInformation` at `0x18005f541`
- `ntdll!RtlNtStatusToDosError` at `0x18005f5e5`
- `ntdll!RtlNtStatusToDosError` at `0x18005f5e5`

## pseudocode

```c

```
