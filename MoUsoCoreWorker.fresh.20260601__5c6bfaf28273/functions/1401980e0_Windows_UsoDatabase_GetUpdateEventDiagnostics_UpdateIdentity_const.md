# Windows::UsoDatabase::GetUpdateEventDiagnostics(UpdateIdentity const &)

- ea: `0x1401980e0`
- end: `0x140198522`
- name: `?GetUpdateEventDiagnostics@UsoDatabase@Windows@@UEBA?AV?$vector@UUpdateEventHistoryDiagnosticStorage@SystemInterface@@V?$allocator@UUpdateEventHistoryDiagnosticStorage@SystemInterface@@@std@@@std@@AEBUUpdateIdentity@@@Z`
- size: `1090`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x140053618`
- `0x1400b7a20`
- `0x1400b7cd4`
- `0x1400bdb64`
- `0x14018d1a4`
- `0x140197b90`
- `0x140197fc4`
- `0x1401980e0`
- `0x1401a0638`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140198136`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140198136`
- `winsqlite3!sqlite3_bind_text16` at `0x1401981d8`
- `winsqlite3!sqlite3_bind_text16` at `0x140198221`
- `winsqlite3!sqlite3_bind_text16` at `0x1401981d8`
- `winsqlite3!sqlite3_bind_text16` at `0x140198221`
- `winsqlite3!sqlite3_column_int` at `0x14019836b`
- `winsqlite3!sqlite3_column_int` at `0x1401983c4`
- `winsqlite3!sqlite3_column_int` at `0x14019836b`
- `winsqlite3!sqlite3_column_int` at `0x1401983c4`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198194`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198194`
- `winsqlite3!sqlite3_finalize` at `0x1401984a7`
- `winsqlite3!sqlite3_finalize` at `0x1401984a7`
- `winsqlite3!sqlite3_column_text16` at `0x140198296`
- `winsqlite3!sqlite3_column_text16` at `0x1401982b1`
- `winsqlite3!sqlite3_column_text16` at `0x140198302`
- `winsqlite3!sqlite3_column_text16` at `0x140198325`
- `winsqlite3!sqlite3_column_text16` at `0x140198348`
- `winsqlite3!sqlite3_column_text16` at `0x14019837e`
- `winsqlite3!sqlite3_column_text16` at `0x1401983a1`
- `winsqlite3!sqlite3_column_text16` at `0x1401983da`
- `winsqlite3!sqlite3_column_text16` at `0x1401983fd`
- `winsqlite3!sqlite3_column_text16` at `0x140198427`
- `winsqlite3!sqlite3_column_text16` at `0x140198296`
- `winsqlite3!sqlite3_column_text16` at `0x1401982b1`
- `winsqlite3!sqlite3_column_text16` at `0x140198302`
- `winsqlite3!sqlite3_column_text16` at `0x140198325`
- `winsqlite3!sqlite3_column_text16` at `0x140198348`
- `winsqlite3!sqlite3_column_text16` at `0x14019837e`
- `winsqlite3!sqlite3_column_text16` at `0x1401983a1`
- `winsqlite3!sqlite3_column_text16` at `0x1401983da`
- `winsqlite3!sqlite3_column_text16` at `0x1401983fd`
- `winsqlite3!sqlite3_column_text16` at `0x140198427`

## string_xrefs

- `0x140198189`: `SELECT PROVIDERID, UPDATEID, STARTTIME, ENDTIME, EVENT, CATEGORY, TITLE, RESULT, REASON, APPROVALS, ISSEEKER, FLIGHTID, UPDATEMETADATA, OTHER FROM UPDATEEVENTHISTORYDIAGNOSTICS WHERE PROVIDERID = ? AND UPDATEID = ? ORDER BY STARTTIME DESC`

## pseudocode

```c

```
