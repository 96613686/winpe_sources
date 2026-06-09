# Csl::GetDiskVolumePath(void *,Csl::Path &)

- ea: `0x180196724`
- end: `0x180196c1a`
- name: `?GetDiskVolumePath@Csl@@YAJPEAXAEAVPath@1@@Z`
- size: `1270`
- prototype: `__int64 __fastcall(HANDLE hDevice, void *, struct Path *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180183de0`
- `0x180195fcc`
- `0x180197c7c`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x180008bf0`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x180196724`
- `0x180196ff0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180196970`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180196970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801969af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801969af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180196a2a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180196a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196af3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196b70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196af3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196b70`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801968f9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196a86`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196ac1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801968f9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196a86`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196ac1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18019692d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180196988`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18019692d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180196988`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1801967d5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1801967d5`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18019680e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180196b3f`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180196bae`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18019680e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180196b3f`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180196bae`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1801967be`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1801967be`

## string_xrefs

- `0x180196c08`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
