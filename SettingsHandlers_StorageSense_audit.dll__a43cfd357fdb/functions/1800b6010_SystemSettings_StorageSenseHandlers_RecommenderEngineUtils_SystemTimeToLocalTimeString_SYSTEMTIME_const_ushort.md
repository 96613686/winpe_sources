# SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::SystemTimeToLocalTimeString(_SYSTEMTIME const *,ushort * *)

- ea: `0x1800b6010`
- end: `0x1800b613a`
- name: `?SystemTimeToLocalTimeString@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@YAJPEBU_SYSTEMTIME@@PEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(SYSTEMTIME *lpDate, const struct _SYSTEMTIME *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074e30`
- `0x18007911c`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000e6cc`
- `0x180026670`
- `0x1800b6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6080`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800b6074`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x1800b6074`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800b60c1`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1800b60c1`

## pseudocode

```c

```
