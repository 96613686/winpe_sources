# pDrvRecoveryEnumImpactedDevicesOnline(HDRIVERSTORE__ *,_DRVUTILS_UPDATE_INFO *,ulong,int (*)(ushort const *,_DRVRECOVERY_DEVICE_FLAG,__int64),__int64)

- ea: `0x180039600`
- end: `0x180039850`
- name: `?pDrvRecoveryEnumImpactedDevicesOnline@@YAHPEAUHDRIVERSTORE__@@PEAU_DRVUTILS_UPDATE_INFO@@KP6AHPEBGW4_DRVRECOVERY_DEVICE_FLAG@@_J@Z4@Z`
- size: `592`
- prototype: `__int64 __usercall@<rax>(struct HDRIVERSTORE__ *@<rcx>, struct _DRVUTILS_UPDATE_INFO *@<rdx>, unsigned int@<r8d>, int (__high *)(const unsigned __int16 *, enum _DRVRECOVERY_DEVICE_FLAG, __int64)@<r9>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x180037354`

## callees

- `0x180038fe0`
- `0x1800393a4`
- `0x1800394e0`
- `0x180039600`
- `0x180039b48`
- `0x18003c8c0`
- `0x18003c9f4`
- `0x18003e69c`
- `0x18003e9a4`
- `0x18003f784`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039800`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039817`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039800`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039817`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039828`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397dd`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800396ac`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800396ac`
- `CFGMGR32!CM_MapCrToSpErr` at `0x1800397ec`
- `CFGMGR32!CM_MapCrToSpErr` at `0x1800397ec`

## pseudocode

```c

```
