# SystemSettings::ContinuumSetting::GetPCNameHandler::GetComputerShortName(ushort *,ulong,bool)

- ea: `0x1801ea5a4`
- end: `0x1801ea78d`
- name: `?GetComputerShortName@GetPCNameHandler@ContinuumSetting@SystemSettings@@IEAAJPEAGK_N@Z`
- size: `489`
- prototype: `int(SystemSettings::ContinuumSetting::GetPCNameHandler *__hidden this, unsigned __int16 *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801eb1e0`

## callees

- `0x18004e5f0`
- `0x1801ea5a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801ea6ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801ea726`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801ea6ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801ea726`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801ea765`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1801ea765`
- `SHLWAPI!SHRegGetValueW` at `0x1801ea5ff`
- `SHLWAPI!SHRegGetValueW` at `0x1801ea652`
- `SHLWAPI!SHRegGetValueW` at `0x1801ea5ff`
- `SHLWAPI!SHRegGetValueW` at `0x1801ea652`

## string_xrefs

- `0x1801ea6fe`: `ComputerName`
- `0x1801ea711`: `System\CurrentControlSet\Control\ComputerName\ComputerName`
- `0x1801ea696`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x1801ea636`: `System\CurrentControlSet\Services\Tcpip\Linkage`

## pseudocode

```c

```
