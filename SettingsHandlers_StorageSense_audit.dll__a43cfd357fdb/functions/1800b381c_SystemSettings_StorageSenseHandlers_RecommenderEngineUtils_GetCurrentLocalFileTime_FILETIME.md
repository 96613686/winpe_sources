# SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::GetCurrentLocalFileTime(_FILETIME *)

- ea: `0x1800b381c`
- end: `0x1800b38a0`
- name: `?GetCurrentLocalFileTime@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@YAJPEAU_FILETIME@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(LPFILETIME lpFileTime, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800705dc`

## callees

- `0x180006e50`
- `0x1800b381c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3865`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800b3849`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800b3849`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800b385b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800b385b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800b3881`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800b3881`

## pseudocode

```c

```
