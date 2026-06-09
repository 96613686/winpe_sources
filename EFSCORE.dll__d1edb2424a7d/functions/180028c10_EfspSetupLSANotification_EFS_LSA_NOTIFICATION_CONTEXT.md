# EfspSetupLSANotification(_EFS_LSA_NOTIFICATION_CONTEXT *)

- ea: `0x180028c10`
- end: `0x180028d34`
- name: `?EfspSetupLSANotification@@YAKPEAU_EFS_LSA_NOTIFICATION_CONTEXT@@@Z`
- size: `292`
- prototype: `unsigned int __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180028d3c`

## callees

- `0x180028c10`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028c34`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d16`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x180028d0d`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x180028d0d`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180028c9a`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180028c9a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180028cd1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180028cd1`
- `ntdll!RtlNtStatusToDosError` at `0x180028ca6`
- `ntdll!RtlNtStatusToDosError` at `0x180028ca6`

## pseudocode

```c

```
