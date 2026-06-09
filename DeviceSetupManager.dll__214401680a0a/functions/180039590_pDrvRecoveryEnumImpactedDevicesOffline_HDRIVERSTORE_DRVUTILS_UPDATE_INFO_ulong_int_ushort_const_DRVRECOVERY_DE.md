# pDrvRecoveryEnumImpactedDevicesOffline(HDRIVERSTORE__ *,_DRVUTILS_UPDATE_INFO *,ulong,int (*)(ushort const *,_DRVRECOVERY_DEVICE_FLAG,__int64),__int64)

- ea: `0x180039590`
- end: `0x1800395f7`
- name: `?pDrvRecoveryEnumImpactedDevicesOffline@@YAHPEAUHDRIVERSTORE__@@PEAU_DRVUTILS_UPDATE_INFO@@KP6AHPEBGW4_DRVRECOVERY_DEVICE_FLAG@@_J@Z4@Z`
- size: `103`
- prototype: `__int64 __fastcall(struct HDRIVERSTORE__ *, struct _DRVUTILS_UPDATE_INFO *, unsigned int, int (__high *)(const unsigned __int16 *, enum _DRVRECOVERY_DEVICE_FLAG, __int64), __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180037354`

## callees

- `0x180039590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800395e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800395e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395d4`
- `drvstore!DriverStoreEnumObjectsW` at `0x1800395ca`
- `drvstore!DriverStoreEnumObjectsW` at `0x1800395ca`

## pseudocode

```c

```
