# SqliteDatabase::GetHandlerDetails(ushort const *,INotificationHandler * *)

- ea: `0x180016280`
- end: `0x18001650a`
- name: `?GetHandlerDetails@SqliteDatabase@@UEAAJPEBGPEAPEAUINotificationHandler@@@Z`
- size: `650`
- prototype: `int(SqliteDatabase *__hidden this, const unsigned __int16 *, struct INotificationHandler **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000e0c4`
- `0x18000e5f4`
- `0x180014340`
- `0x18001592c`
- `0x180016280`
- `0x180016900`
- `0x180016c6c`
- `0x180049644`
- `0x1800a0b2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800162d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800162d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001644b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001644b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164c7`
- `winsqlite3!sqlite3_bind_text16` at `0x180016400`
- `winsqlite3!sqlite3_bind_text16` at `0x180016400`

## string_xrefs

- `0x180016377`: `SELECT [H].[RecordId], [H].[PrimaryId], [H].[WNSId], [H].[HandlerType], [H].[WNFEventName], [H].[SystemDataPropertySet], [H].[ParentId], [H].[ContainerSid] FROM [NotificationHandler] AS [H] WHERE [H].[PrimaryId]=?`

## pseudocode

```c

```
