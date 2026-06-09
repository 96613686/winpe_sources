# SystemSettings::StorageSenseHandlers::ConvertDOSAppPathToDriveAppPath(ushort const *,ushort *,ulong)

- ea: `0x18005222c`
- end: `0x18005234b`
- name: `?ConvertDOSAppPathToDriveAppPath@StorageSenseHandlers@SystemSettings@@YAJPEBGPEAGK@Z`
- size: `287`
- prototype: `int(SystemSettings::StorageSenseHandlers *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18005249c`

## callees

- `0x1800028d0`
- `0x18000a8fc`
- `0x18005222c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800522d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800522d8`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800522b0`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800522b0`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180052275`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180052275`

## pseudocode

```c

```
