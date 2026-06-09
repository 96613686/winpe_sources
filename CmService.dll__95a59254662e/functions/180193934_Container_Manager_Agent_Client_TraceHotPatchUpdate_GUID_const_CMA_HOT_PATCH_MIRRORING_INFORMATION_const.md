# Container::Manager::Agent::Client::TraceHotPatchUpdate(_GUID const &,_CMA_HOT_PATCH_MIRRORING_INFORMATION const &)

- ea: `0x180193934`
- end: `0x180193f29`
- name: `?TraceHotPatchUpdate@Client@Agent@Manager@Container@@YAJAEBU_GUID@@AEBU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z`
- size: `1525`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Client *__hidden this, const struct _GUID *, const struct _CMA_HOT_PATCH_MIRRORING_INFORMATION *)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x1801935bc`
- `0x1801937a0`
- `0x180193f30`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x18002c5b4`
- `0x18002fc34`
- `0x18003134c`
- `0x180192e10`
- `0x180193164`
- `0x1801933dc`
- `0x180193934`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x1801939f7`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x1801939f7`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180193afc`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180193afc`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193cb7`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193db2`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193e0e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193e5e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193eba`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193cb7`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193db2`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193e0e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193e5e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193eba`

## string_xrefs

- `0x1801939b8`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193c64`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193ce9`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193d3c`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193d71`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193de6`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193e30`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193f11`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193a86`: `Container hot patch installation attempt. ContainerId: %ws, BaseCheckSum: 0x%x, BaseTimeDateStamp: 0x%x, PatchPath: %ws, NtStatus: 0x%x`

## pseudocode

```c

```
