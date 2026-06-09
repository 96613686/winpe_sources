# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::WorkAccess::DesktopSkuLaunchTraits>::ExecuteFlow<SystemSettings::WorkAccess::AdminFlowTraits>(HWND__ *,ushort const *)

- ea: `0x1800210b8`
- end: `0x180021199`
- name: `??$ExecuteFlow@UAdminFlowTraits@WorkAccess@SystemSettings@@@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@WorkAccess@SystemSettings@@@DataModel@SystemSettings@@SAJPEAUHWND__@@PEBG@Z`
- size: `225`
- prototype: `__int64 __fastcall(HWND, const WCHAR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180023db4`
- `0x180040c40`

## callees

- `0x180003534`
- `0x1800096ec`
- `0x1800210b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002112a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002112a`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18002111a`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x18002111a`

## string_xrefs

- `0x1800210fc`: `%systemroot%\system32\SystemSettingsAdminFlows.exe`

## pseudocode

```c

```
