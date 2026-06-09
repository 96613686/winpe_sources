# Csl::GetDiskVolumePath(void *,Csl::Path &)

- ea: `0x1801965b4`
- end: `0x180196aaa`
- name: `?GetDiskVolumePath@Csl@@YAJPEAXAEAVPath@1@@Z`
- size: `1270`
- prototype: `__int64 __fastcall(HANDLE hDevice, void *, struct Path *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180183c70`
- `0x180195e5c`
- `0x180197b0c`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x180008bf0`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x1801965b4`
- `0x180196e80`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180196800`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180196800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019683f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019683f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801968ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801968ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196a00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180196a00`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196789`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196916`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196951`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196789`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196916`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180196951`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1801967bd`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180196818`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1801967bd`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180196818`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180196665`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180196665`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18019669e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1801969cf`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180196a3e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18019669e`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1801969cf`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180196a3e`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18019664e`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18019664e`

## string_xrefs

- `0x180196a98`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
