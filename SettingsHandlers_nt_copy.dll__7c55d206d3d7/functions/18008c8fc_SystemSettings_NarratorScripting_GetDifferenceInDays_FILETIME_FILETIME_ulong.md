# SystemSettings::NarratorScripting::GetDifferenceInDays(_FILETIME,_FILETIME,ulong *)

- ea: `0x18008c8fc`
- end: `0x18008ca9f`
- name: `?GetDifferenceInDays@NarratorScripting@SystemSettings@@YAJU_FILETIME@@0PEAK@Z`
- size: `419`
- prototype: `__int64 __fastcall(SystemSettings::NarratorScripting *__hidden this, struct _FILETIME, struct _FILETIME, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180086580`

## callees

- `0x18000c840`
- `0x180019a00`
- `0x180019a20`
- `0x18008c8fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18008c93d`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18008c96d`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18008c93d`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18008c96d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008ca24`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008ca24`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008c9e4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008ca04`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008c9e4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18008ca04`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008c998`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008c9b5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008c998`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008c9b5`

## string_xrefs

- `0x18008c954`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\scripthandlerhelpers.cpp`
- `0x18008ca38`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\scripthandlerhelpers.cpp`

## pseudocode

```c

```
