# CApplicationTracker::HostedApplicationInteractivityChanged(ushort const *,unsigned __int64,AppInteractivity)

- ea: `0x1800ddd90`
- end: `0x1800ddf62`
- name: `?HostedApplicationInteractivityChanged@CApplicationTracker@@EEAAJPEBG_KW4AppInteractivity@@@Z`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002670`
- `0x1800126bc`
- `0x18001b3d0`
- `0x1800aedc0`
- `0x1800dd7c0`
- `0x1800ddb8c`
- `0x1800ddc78`
- `0x1800ddd90`

## import_xrefs

- `AUDIOSRVPOLICYMANAGER!PbmReportHostedAppStateChange_2` at `0x1800ddf19`
- `AUDIOSRVPOLICYMANAGER!PbmReportHostedAppStateChange_2` at `0x1800ddf19`
- `ntdll!NtQueryInformationProcess` at `0x1800dde6d`
- `ntdll!NtQueryInformationProcess` at `0x1800dde6d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800dde3c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800dde3c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ddded`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ddf3e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ddded`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ddf3e`
- `ext-ms-win-audiocore-coreaudiopolicymanager-l1-1-0!IsPbmReportHostedAppStateChangeSupported` at `0x1800ddef0`
- `ext-ms-win-audiocore-coreaudiopolicymanager-l1-1-0!IsPbmReportHostedAppStateChangeSupported` at `0x1800ddef0`

## string_xrefs

- `0x1800dddd3`: `avcore\audiocore\server\audiosrv\dll\applicationtracker.cpp`
- `0x1800dde1e`: `avcore\audiocore\server\audiosrv\dll\applicationtracker.cpp`
- `0x1800dde7b`: `avcore\audiocore\server\audiosrv\dll\applicationtracker.cpp`

## pseudocode

```c

```
