# ConnectedStorage::Service::GetServiceShutdownTime(_FILETIME *)

- ea: `0x180014e64`
- end: `0x180014f2c`
- name: `?GetServiceShutdownTime@Service@ConnectedStorage@@CAXPEAU_FILETIME@@@Z`
- size: `200`
- prototype: `void __fastcall(struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180015fd4`

## callees

- `0x180014e64`
- `0x180015f7c`
- `0x180016d28`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e7d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014edf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014edf`

## string_xrefs

- `0x180014eaa`: `ServiceIdleTimeout`
- `0x180014e86`: `System\CurrentControlSet\Services\XblGameSave\Parameters`

## pseudocode

```c

```
