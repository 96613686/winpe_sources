# Windows::Management::Setup::ProvisioningSessionLogger::LogNotifyMachineProvisioningUpdateData(_GUID const &,Windows::Management::Setup::IAgentProvisioningProgressReport *)

- ea: `0x180100e70`
- end: `0x180101147`
- name: `?LogNotifyMachineProvisioningUpdateData@ProvisioningSessionLogger@Setup@Management@Windows@@UEAAJAEBU_GUID@@PEAUIAgentProvisioningProgressReport@234@@Z`
- size: `727`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct _GUID *, struct Windows::Management::Setup::IAgentProvisioningProgressReport *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18006e0a8`
- `0x18007755c`
- `0x18008019c`
- `0x1800853a0`
- `0x180089b58`
- `0x18008b9c4`
- `0x18008e438`
- `0x18008e584`
- `0x18008e6c0`
- `0x180100280`
- `0x180100e70`
- `0x180101cb4`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180100e9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180100e9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180100f0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180100f0e`

## string_xrefs

- `0x180100ec3`: `Windows.Data.Json.JsonObject`
- `0x180100eed`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180100f46`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180100fc8`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180101015`: `DeploymentAgentProgressState`

## pseudocode

```c

```
