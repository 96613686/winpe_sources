# SqliteDatabase::GetTransientDetailsForNotification(ulong,ITransientNotificationDetails * *)

- ea: `0x180049240`
- end: `0x180049521`
- name: `?GetTransientDetailsForNotification@SqliteDatabase@@UEAAJKPEAPEAUITransientNotificationDetails@@@Z`
- size: `737`
- prototype: `int(SqliteDatabase *__hidden this, unsigned int, struct ITransientNotificationDetails **)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x1800077f8`
- `0x1800082c4`
- `0x18000d404`
- `0x18000e5f4`
- `0x1800117c0`
- `0x180011a90`
- `0x1800132a0`
- `0x18001575c`
- `0x18001592c`
- `0x18002b7a8`
- `0x180049240`
- `0x180049528`
- `0x180049644`
- `0x18004d6f0`
- `0x1800b99f0`
- `0x1800effc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049280`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004931b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004931b`
- `winsqlite3!sqlite3_column_int` at `0x18004933e`
- `winsqlite3!sqlite3_column_int` at `0x1800493c4`
- `winsqlite3!sqlite3_column_int` at `0x18004933e`
- `winsqlite3!sqlite3_column_int` at `0x1800493c4`

## string_xrefs

- `0x1800492d3`: `SELECT [T].[OfflineCacheCount], [T].[OfflineBundleId], [T].[ServerCacheRollover], [T].[CrossDeviceMatchId], [T].[SuppressPopup], [T].[IsMirroringDisabled], [T].[RecurrenceId], [T].[MessageId], [T].[Priority], [T].[CV] from [TransientTable] AS [T] WHERE [T].[NotificationId]=?`

## pseudocode

```c

```
