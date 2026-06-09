# Windows::UsoDatabase::CleanUpUpdateEventHistoryDiagnosticsTable(wil::basic_zstring_view<wchar_t>,uint,uint)

- ea: `0x14019ced0`
- end: `0x14019d2ab`
- name: `?CleanUpUpdateEventHistoryDiagnosticsTable@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@II@Z`
- size: `987`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1400bdb64`
- `0x14018d1a4`
- `0x14019ced0`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019cf0e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019cf0e`
- `winsqlite3!sqlite3_bind_text16` at `0x14019cfe2`
- `winsqlite3!sqlite3_bind_text16` at `0x14019d0a5`
- `winsqlite3!sqlite3_bind_text16` at `0x14019d1a5`
- `winsqlite3!sqlite3_bind_text16` at `0x14019cfe2`
- `winsqlite3!sqlite3_bind_text16` at `0x14019d0a5`
- `winsqlite3!sqlite3_bind_text16` at `0x14019d1a5`
- `winsqlite3!sqlite3_bind_int` at `0x14019d010`
- `winsqlite3!sqlite3_bind_int` at `0x14019d0d9`
- `winsqlite3!sqlite3_bind_int` at `0x14019d010`
- `winsqlite3!sqlite3_bind_int` at `0x14019d0d9`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019cf9c`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019d064`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019d15f`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019cf9c`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019d064`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019d15f`
- `winsqlite3!sqlite3_finalize` at `0x14019d115`
- `winsqlite3!sqlite3_finalize` at `0x14019d129`
- `winsqlite3!sqlite3_finalize` at `0x14019d1dd`
- `winsqlite3!sqlite3_finalize` at `0x14019d115`
- `winsqlite3!sqlite3_finalize` at `0x14019d129`
- `winsqlite3!sqlite3_finalize` at `0x14019d1dd`

## string_xrefs

- `0x14019d155`: `DELETE FROM UPDATEEVENTHISTORYDIAGNOSTICS WHERE PROVIDERID = ?`
- `0x14019d05a`: `\n            WITH ProviderFilter AS (SELECT ? AS PROV)\n            DELETE FROM UPDATEEVENTHISTORYDIAGNOSTICS\n            WHERE PROVIDERID = (SELECT PROV FROM ProviderFilter) AND ROWID IN (\n                SELECT d.ROWID\n                FROM UPDATEEVENTHISTORYDIAGNOSTICS d\n                INNER JOIN (\n                    SELECT PROVIDERID, UPDATEID, MIN(COALESCE(CAST(STARTTIME AS INTEGER), 0)) AS FIRSTEVENTTIME\n                    FROM UPDATEEVENTHISTORYDIAGNOSTICS\n                    WH`
- `0x14019cf92`: `\n            WITH ProviderFilter AS (SELECT ? AS PROV)\n            DELETE FROM UPDATEEVENTHISTORYDIAGNOSTICS\n            WHERE PROVIDERID = (SELECT PROV FROM ProviderFilter) AND ROWID IN (\n                SELECT d.ROWID\n                FROM UPDATEEVENTHISTORYDIAGNOSTICS d\n                LEFT JOIN (\n                    SELECT PROVIDERID, UPDATEID, CATEGORY,\n                           ROW_NUMBER() OVER (\n                               PARTITION BY CATEGORY\n                              `

## pseudocode

```c

```
