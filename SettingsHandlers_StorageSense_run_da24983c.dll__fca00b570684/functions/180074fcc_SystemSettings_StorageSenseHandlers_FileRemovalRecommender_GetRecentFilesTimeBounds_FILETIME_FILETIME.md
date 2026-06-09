# SystemSettings::StorageSenseHandlers::FileRemovalRecommender::GetRecentFilesTimeBounds(_FILETIME *,_FILETIME *)

- ea: `0x180074fcc`
- end: `0x180075104`
- name: `?GetRecentFilesTimeBounds@FileRemovalRecommender@StorageSenseHandlers@SystemSettings@@IEAAJPEAU_FILETIME@@0@Z`
- size: `312`
- prototype: `int(SystemSettings::StorageSenseHandlers::FileRemovalRecommender *__hidden this, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077ae0`

## callees

- `0x180006e50`
- `0x180012374`
- `0x180074fcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007505e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007505e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180075046`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180075046`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180075054`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800750af`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180075054`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800750af`

## string_xrefs

- `0x180074ffa`: `CleanupRecommendations`
- `0x180075006`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c

```
