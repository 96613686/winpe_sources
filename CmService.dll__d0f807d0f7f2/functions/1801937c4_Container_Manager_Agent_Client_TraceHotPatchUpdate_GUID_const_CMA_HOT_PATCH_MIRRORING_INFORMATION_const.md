# Container::Manager::Agent::Client::TraceHotPatchUpdate(_GUID const &,_CMA_HOT_PATCH_MIRRORING_INFORMATION const &)

- ea: `0x1801937c4`
- end: `0x180193db9`
- name: `?TraceHotPatchUpdate@Client@Agent@Manager@Container@@YAJAEBU_GUID@@AEBU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@@Z`
- size: `1525`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Client *__hidden this, const struct _GUID *, const struct _CMA_HOT_PATCH_MIRRORING_INFORMATION *)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x18019344c`
- `0x180193630`
- `0x180193dc0`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x18002c5b4`
- `0x18002fc34`
- `0x18003134c`
- `0x180192ca0`
- `0x180192ff4`
- `0x18019326c`
- `0x1801937c4`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180193887`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180193887`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18019398c`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18019398c`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193b47`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193c42`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193c9e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193cee`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193d4a`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193b47`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193c42`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193c9e`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193cee`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180193d4a`

## string_xrefs

- `0x180193848`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193af4`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193b79`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193bcc`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193c01`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193c76`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193cc0`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193da1`: `onecore\base\gendrv\silos\clem\agent\client\lib\cmagentclient.cpp`
- `0x180193916`: `Container hot patch installation attempt. ContainerId: %ws, BaseCheckSum: 0x%x, BaseTimeDateStamp: 0x%x, PatchPath: %ws, NtStatus: 0x%x`

## pseudocode

```c

```
