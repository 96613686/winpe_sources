# Windows::UsoDatabase::GetAllUpdateEventDiagnostics(void)

- ea: `0x140197c30`
- end: `0x140197fbd`
- name: `?GetAllUpdateEventDiagnostics@UsoDatabase@Windows@@QEBA?AV?$vector@UUpdateEventHistoryDiagnosticStorage@SystemInterface@@V?$allocator@UUpdateEventHistoryDiagnosticStorage@SystemInterface@@@std@@@std@@XZ`
- size: `909`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x14018eaa4`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x140053618`
- `0x1400b7a20`
- `0x1400b7cd4`
- `0x1400bdb64`
- `0x14018d1a4`
- `0x140197b90`
- `0x140197c30`
- `0x140197fc4`
- `0x1401a0638`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140197c85`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140197c85`
- `winsqlite3!sqlite3_column_int` at `0x140197e29`
- `winsqlite3!sqlite3_column_int` at `0x140197e82`
- `winsqlite3!sqlite3_column_int` at `0x140197e29`
- `winsqlite3!sqlite3_column_int` at `0x140197e82`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140197cde`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140197cde`
- `winsqlite3!sqlite3_finalize` at `0x140197f65`
- `winsqlite3!sqlite3_finalize` at `0x140197f65`
- `winsqlite3!sqlite3_column_text16` at `0x140197d52`
- `winsqlite3!sqlite3_column_text16` at `0x140197d6c`
- `winsqlite3!sqlite3_column_text16` at `0x140197dc0`
- `winsqlite3!sqlite3_column_text16` at `0x140197de3`
- `winsqlite3!sqlite3_column_text16` at `0x140197e06`
- `winsqlite3!sqlite3_column_text16` at `0x140197e3c`
- `winsqlite3!sqlite3_column_text16` at `0x140197e5f`
- `winsqlite3!sqlite3_column_text16` at `0x140197e98`
- `winsqlite3!sqlite3_column_text16` at `0x140197ebb`
- `winsqlite3!sqlite3_column_text16` at `0x140197ee5`
- `winsqlite3!sqlite3_column_text16` at `0x140197d52`
- `winsqlite3!sqlite3_column_text16` at `0x140197d6c`
- `winsqlite3!sqlite3_column_text16` at `0x140197dc0`
- `winsqlite3!sqlite3_column_text16` at `0x140197de3`
- `winsqlite3!sqlite3_column_text16` at `0x140197e06`
- `winsqlite3!sqlite3_column_text16` at `0x140197e3c`
- `winsqlite3!sqlite3_column_text16` at `0x140197e5f`
- `winsqlite3!sqlite3_column_text16` at `0x140197e98`
- `winsqlite3!sqlite3_column_text16` at `0x140197ebb`
- `winsqlite3!sqlite3_column_text16` at `0x140197ee5`

## string_xrefs

- `0x140197cd3`: `SELECT PROVIDERID, UPDATEID, STARTTIME, ENDTIME, EVENT, CATEGORY, TITLE, RESULT, REASON, APPROVALS, ISSEEKER, FLIGHTID, UPDATEMETADATA, OTHER FROM UPDATEEVENTHISTORYDIAGNOSTICS`

## pseudocode

```c

```
