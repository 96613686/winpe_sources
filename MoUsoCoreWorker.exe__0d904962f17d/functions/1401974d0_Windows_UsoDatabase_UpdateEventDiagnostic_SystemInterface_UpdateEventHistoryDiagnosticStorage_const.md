# Windows::UsoDatabase::UpdateEventDiagnostic(SystemInterface::UpdateEventHistoryDiagnosticStorage const &)

- ea: `0x1401974d0`
- end: `0x140197b87`
- name: `?UpdateEventDiagnostic@UsoDatabase@Windows@@UEAAXAEBUUpdateEventHistoryDiagnosticStorage@SystemInterface@@@Z`
- size: `1719`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct SystemInterface::UpdateEventHistoryDiagnosticStorage *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14018eaa4`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400bdb64`
- `0x1400c6f6c`
- `0x14018d1a4`
- `0x1401974d0`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140197510`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140197510`
- `winsqlite3!sqlite3_bind_text16` at `0x1401975a6`
- `winsqlite3!sqlite3_bind_text16` at `0x1401975e5`
- `winsqlite3!sqlite3_bind_text16` at `0x14019766c`
- `winsqlite3!sqlite3_bind_text16` at `0x1401976fd`
- `winsqlite3!sqlite3_bind_text16` at `0x140197745`
- `winsqlite3!sqlite3_bind_text16` at `0x140197784`
- `winsqlite3!sqlite3_bind_text16` at `0x1401977c6`
- `winsqlite3!sqlite3_bind_text16` at `0x140197838`
- `winsqlite3!sqlite3_bind_text16` at `0x14019787a`
- `winsqlite3!sqlite3_bind_text16` at `0x1401978f3`
- `winsqlite3!sqlite3_bind_text16` at `0x140197935`
- `winsqlite3!sqlite3_bind_text16` at `0x140197977`
- `winsqlite3!sqlite3_bind_text16` at `0x1401975a6`
- `winsqlite3!sqlite3_bind_text16` at `0x1401975e5`
- `winsqlite3!sqlite3_bind_text16` at `0x14019766c`
- `winsqlite3!sqlite3_bind_text16` at `0x1401976fd`
- `winsqlite3!sqlite3_bind_text16` at `0x140197745`
- `winsqlite3!sqlite3_bind_text16` at `0x140197784`
- `winsqlite3!sqlite3_bind_text16` at `0x1401977c6`
- `winsqlite3!sqlite3_bind_text16` at `0x140197838`
- `winsqlite3!sqlite3_bind_text16` at `0x14019787a`
- `winsqlite3!sqlite3_bind_text16` at `0x1401978f3`
- `winsqlite3!sqlite3_bind_text16` at `0x140197935`
- `winsqlite3!sqlite3_bind_text16` at `0x140197977`
- `winsqlite3!sqlite3_bind_int` at `0x1401977f6`
- `winsqlite3!sqlite3_bind_int` at `0x1401978b1`
- `winsqlite3!sqlite3_bind_int` at `0x1401977f6`
- `winsqlite3!sqlite3_bind_int` at `0x1401978b1`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140197562`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140197562`
- `winsqlite3!sqlite3_finalize` at `0x1401979b0`
- `winsqlite3!sqlite3_finalize` at `0x1401979b0`
- `winsqlite3!sqlite3_bind_null` at `0x1401979e3`
- `winsqlite3!sqlite3_bind_null` at `0x1401979e3`

## string_xrefs

- `0x140197557`: `INSERT OR REPLACE INTO UPDATEEVENTHISTORYDIAGNOSTICS (PROVIDERID, UPDATEID, STARTTIME, ENDTIME, EVENT, CATEGORY, TITLE, RESULT, REASON, APPROVALS, ISSEEKER, FLIGHTID, UPDATEMETADATA, OTHER) VALUES (?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)`

## pseudocode

```c

```
