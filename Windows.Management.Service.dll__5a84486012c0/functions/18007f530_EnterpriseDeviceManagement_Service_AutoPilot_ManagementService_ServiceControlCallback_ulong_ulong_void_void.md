# EnterpriseDeviceManagement::Service::AutoPilot::ManagementService::ServiceControlCallback(ulong,ulong,void *,void *)

- ea: `0x18007f530`
- end: `0x18007f598`
- name: `?ServiceControlCallback@ManagementService@AutoPilot@Service@EnterpriseDeviceManagement@@CAKKKPEAX0@Z`
- size: `104`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18007f530`
- `0x18008013c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007f567`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007f567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f58a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f58a`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18007f550`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18007f550`

## string_xrefs

- `0x18007f576`: `onecoreuap\admin\moderndeployment\autopilot\service\dllsrv\servicemain.cpp`

## pseudocode

```c

```
