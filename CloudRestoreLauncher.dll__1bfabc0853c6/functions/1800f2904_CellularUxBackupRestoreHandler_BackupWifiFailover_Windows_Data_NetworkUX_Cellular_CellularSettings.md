# CellularUxBackupRestoreHandler::BackupWifiFailover(Windows::Data::NetworkUX::Cellular::CellularSettings &)

- ea: `0x1800f2904`
- end: `0x1800f2abc`
- name: `?BackupWifiFailover@CellularUxBackupRestoreHandler@@AEAA_NAEAUCellularSettings@Cellular@NetworkUX@Data@Windows@@@Z`
- size: `440`
- prototype: `bool __fastcall(CellularUxBackupRestoreHandler *__hidden this, struct Windows::Data::NetworkUX::Cellular::CellularSettings *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800f2fe0`

## callees

- `0x18000c6e0`
- `0x18001cf84`
- `0x18001d0a8`
- `0x18001daf4`
- `0x180031774`
- `0x1800f2904`
- `0x1800f2f30`
- `0x1800f414c`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x1800f2984`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800f2984`
- `ADVAPI32!RegGetValueW` at `0x1800f29ef`
- `ADVAPI32!RegGetValueW` at `0x1800f29ef`

## string_xrefs

- `0x1800f2a39`: `Registry value out of range`
- `0x1800f2a03`: `Incorrect registry data type`

## pseudocode

```c

```
