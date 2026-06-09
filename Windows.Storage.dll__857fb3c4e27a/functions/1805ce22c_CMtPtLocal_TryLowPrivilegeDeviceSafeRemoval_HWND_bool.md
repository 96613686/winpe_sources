# CMtPtLocal::_TryLowPrivilegeDeviceSafeRemoval(HWND__ *,bool *)

- ea: `0x1805ce22c`
- end: `0x1805ce79a`
- name: `?_TryLowPrivilegeDeviceSafeRemoval@CMtPtLocal@@AEAAJPEAUHWND__@@PEA_N@Z`
- size: `1390`
- prototype: `__int64 __fastcall(CMtPtLocal *__hidden this, HWND, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1805cd100`

## callees

- `0x18000ee84`
- `0x18009d164`
- `0x1800a3080`
- `0x1800a5580`
- `0x18016faa4`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1805cd6a0`
- `0x1805ce22c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce52c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce768`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce52c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1805ce768`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805ce6c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1805ce6c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1805ce64f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1805ce64f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1805ce6a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1805ce6a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1805ce412`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1805ce412`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ce535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ce74c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ce535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805ce74c`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1805ce286`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1805ce286`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ce2b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ce4ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ce2b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1805ce4ae`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ce310`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ce507`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ce310`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1805ce507`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1805ce6dd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1805ce6dd`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805ce33a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1805ce33a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ce3f5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ce470`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ce3f5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1805ce470`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805ce3bf`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1805ce3bf`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805ce371`
- `DEVOBJ!DevObjGetClassDevs` at `0x1805ce371`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1805ce597`
- `CFGMGR32!CM_Locate_DevNodeW` at `0x1805ce597`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ce57b`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ce60f`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ce57b`
- `CFGMGR32!CM_Get_Device_IDW` at `0x1805ce60f`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x1805ce5e7`
- `CFGMGR32!CM_Get_Parent_Ex` at `0x1805ce5e7`

## pseudocode

```c

```
