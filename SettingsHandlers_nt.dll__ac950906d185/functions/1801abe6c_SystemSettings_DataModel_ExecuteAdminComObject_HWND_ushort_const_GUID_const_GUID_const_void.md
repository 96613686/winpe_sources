# SystemSettings::DataModel::ExecuteAdminComObject(HWND__ *,ushort const *,_GUID const &,_GUID const &,void * *)

- ea: `0x1801abe6c`
- end: `0x1801ac079`
- name: `?ExecuteAdminComObject@DataModel@SystemSettings@@YAJPEAUHWND__@@PEBGAEBU_GUID@@2PEAPEAX@Z`
- size: `525`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, HWND, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801ab390`
- `0x1801abd00`

## callees

- `0x18000d44c`
- `0x180011bb0`
- `0x1801abe6c`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abfb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abfb0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801ac018`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801ac018`
- `SHELL32!ShellExecuteExW` at `0x1801abf9c`
- `SHELL32!ShellExecuteExW` at `0x1801abf9c`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x1801abeb9`
- `ext-ms-win-com-ole32-l1-1-0!GetRunningObjectTable` at `0x1801abeb9`
- `ext-ms-win-com-ole32-l1-1-5!CreateClassMoniker` at `0x1801abedf`
- `ext-ms-win-com-ole32-l1-1-5!CreateClassMoniker` at `0x1801abedf`

## string_xrefs

- `0x1801abf77`: `%systemroot%\system32\SystemSettingsAdminFlows.exe`

## pseudocode

```c

```
