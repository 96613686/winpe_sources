# FSFileOperationServiceDrivenAction::GetEFIESPVolumePath(ushort *)

- ea: `0x1800a6a74`
- end: `0x1800a6b6e`
- name: `?GetEFIESPVolumePath@FSFileOperationServiceDrivenAction@@CAJPEAG@Z`
- size: `250`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a6fa0`

## callees

- `0x18000cc8c`
- `0x18001e6d4`
- `0x1800a6a74`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800a6ab7`
- `ntdll!NtQuerySystemInformation` at `0x1800a6ab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6aca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6af9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6b5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6aca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6af9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6b5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a6add`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a6add`

## string_xrefs

- `0x1800a6b42`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`

## pseudocode

```c

```
