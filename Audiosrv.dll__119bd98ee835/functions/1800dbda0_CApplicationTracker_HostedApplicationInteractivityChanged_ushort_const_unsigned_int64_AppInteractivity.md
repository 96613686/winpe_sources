# CApplicationTracker::HostedApplicationInteractivityChanged(ushort const *,unsigned __int64,AppInteractivity)

- ea: `0x1800dbda0`
- end: `0x1800dbf72`
- name: `?HostedApplicationInteractivityChanged@CApplicationTracker@@EEAAJPEBG_KW4AppInteractivity@@@Z`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002670`
- `0x18001280c`
- `0x18001b520`
- `0x1800ad0c0`
- `0x1800db7d0`
- `0x1800dbb9c`
- `0x1800dbc88`
- `0x1800dbda0`

## import_xrefs

- `AUDIOSRVPOLICYMANAGER!PbmReportHostedAppStateChange_2` at `0x1800dbf29`
- `AUDIOSRVPOLICYMANAGER!PbmReportHostedAppStateChange_2` at `0x1800dbf29`
- `ntdll!NtQueryInformationProcess` at `0x1800dbe7d`
- `ntdll!NtQueryInformationProcess` at `0x1800dbe7d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800dbe4c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800dbe4c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800dbdfd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800dbf4e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800dbdfd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800dbf4e`
- `ext-ms-win-audiocore-coreaudiopolicymanager-l1-1-0!IsPbmReportHostedAppStateChangeSupported` at `0x1800dbf00`
- `ext-ms-win-audiocore-coreaudiopolicymanager-l1-1-0!IsPbmReportHostedAppStateChangeSupported` at `0x1800dbf00`

## string_xrefs

- `0x1800dbde3`: `avcore\audiocore\server\audiosrv\dll\applicationtracker.cpp`
- `0x1800dbe2e`: `avcore\audiocore\server\audiosrv\dll\applicationtracker.cpp`
- `0x1800dbe8b`: `avcore\audiocore\server\audiosrv\dll\applicationtracker.cpp`

## pseudocode

```c

```
