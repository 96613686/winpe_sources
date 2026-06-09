# SystemSettings::DataModel::ShellExecuteProcess<SystemSettings::DataModel::Details::DesktopSkuLaunchTraits>::ExecuteAndWait(_SHELLEXECUTEINFOW *)

- ea: `0x1800886f0`
- end: `0x180088843`
- name: `?ExecuteAndWait@?$ShellExecuteProcess@UDesktopSkuLaunchTraits@Details@DataModel@SystemSettings@@@DataModel@SystemSettings@@SAJPEAU_SHELLEXECUTEINFOW@@@Z`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800868ec`

## callees

- `0x180019a00`
- `0x180019a20`
- `0x18002e1a4`
- `0x18008864c`
- `0x1800886f0`
- `0x1800897e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800887d1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800887d1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180088808`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180088808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008881f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008881f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800887eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800887eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180088759`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180088759`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800887bc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800887bc`

## pseudocode

```c

```
