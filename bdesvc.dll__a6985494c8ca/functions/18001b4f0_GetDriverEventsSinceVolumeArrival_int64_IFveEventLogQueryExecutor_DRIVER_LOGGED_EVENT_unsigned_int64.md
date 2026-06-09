# GetDriverEventsSinceVolumeArrival(__int64,IFveEventLogQueryExecutor *,_DRIVER_LOGGED_EVENT * *,unsigned __int64 *)

- ea: `0x18001b4f0`
- end: `0x18001b7db`
- name: `?GetDriverEventsSinceVolumeArrival@@YAJ_JPEAVIFveEventLogQueryExecutor@@PEAPEAU_DRIVER_LOGGED_EVENT@@PEA_K@Z`
- size: `747`
- prototype: `__int64 __fastcall(__int64, struct IFveEventLogQueryExecutor *, struct _DRIVER_LOGGED_EVENT **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800429e0`

## callees

- `0x180009f60`
- `0x18001b4f0`
- `0x18001b7f0`
- `0x180034070`
- `0x180034d28`
- `0x180039828`
- `0x1800398a8`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b768`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b7b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b768`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b7b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b754`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b79e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b754`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b79e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b559`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b559`

## string_xrefs

- `0x18001b576`: `<QueryList><Query Id="0" Path="System"><Select Path="System">*[System[(Level &lt;= 3) and Provider[@Name = "Microsoft-Windows-BitLocker-Driver"] and TimeCreated[timediff(@SystemTime) &lt;= %lu]]]</Select></Query></QueryList>`

## pseudocode

```c

```
