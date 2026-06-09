# Service::HostCallback::OnStatusUpdated(CDPStatusCode)

- ea: `0x180002b30`
- end: `0x180002cac`
- name: `?OnStatusUpdated@HostCallback@Service@@UEAAXW4CDPStatusCode@@@Z`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180002b30`
- `0x180003384`
- `0x18000cb8c`
- `0x18001a44c`
- `0x18003a980`
- `0x18003c188`
- `0x180040630`
- `0x180042cd4`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180002b9f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180002c28`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180002c51`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180002c28`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180002c51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002bed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002bed`

## string_xrefs

- `0x180002c70`: `{"text":"Host signalled that we are idle and there were no local apps connected to the service. Signalling SCM to stop the service, which will stop the host."}`
- `0x180002be6`: `DllGetObjectCount`

## pseudocode

```c

```
