# EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceControlCallback(ulong,ulong,void *,void *)

- ea: `0x18007fed0`
- end: `0x18007ff4b`
- name: `?ServiceControlCallback@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@CAKKKPEAX0@Z`
- size: `123`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18007fed0`
- `0x180080b4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007ff0d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007ff0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ff36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ff36`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18007fef0`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18007fef0`

## string_xrefs

- `0x18007ff22`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`

## pseudocode

```c

```
