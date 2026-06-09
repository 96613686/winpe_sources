# Windows::UsoDatabase::UpdateActionAttemptDiagnostic(SystemInterface::UpdateEventHistoryDiagnosticStorage const &)

- ea: `0x140196fa0`
- end: `0x1401974bb`
- name: `?UpdateActionAttemptDiagnostic@UsoDatabase@Windows@@UEAAXAEBUUpdateEventHistoryDiagnosticStorage@SystemInterface@@@Z`
- size: `1307`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct SystemInterface::UpdateEventHistoryDiagnosticStorage *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400bdb64`
- `0x1400c6f6c`
- `0x14018d1a4`
- `0x140196fa0`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140196fe2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140196fe2`
- `winsqlite3!sqlite3_bind_text16` at `0x140197078`
- `winsqlite3!sqlite3_bind_text16` at `0x1401970b7`
- `winsqlite3!sqlite3_bind_text16` at `0x14019713b`
- `winsqlite3!sqlite3_bind_text16` at `0x140197183`
- `winsqlite3!sqlite3_bind_text16` at `0x1401971c2`
- `winsqlite3!sqlite3_bind_text16` at `0x140197204`
- `winsqlite3!sqlite3_bind_text16` at `0x140197246`
- `winsqlite3!sqlite3_bind_text16` at `0x1401972bf`
- `winsqlite3!sqlite3_bind_text16` at `0x140197301`
- `winsqlite3!sqlite3_bind_text16` at `0x140197343`
- `winsqlite3!sqlite3_bind_text16` at `0x140197078`
- `winsqlite3!sqlite3_bind_text16` at `0x1401970b7`
- `winsqlite3!sqlite3_bind_text16` at `0x14019713b`
- `winsqlite3!sqlite3_bind_text16` at `0x140197183`
- `winsqlite3!sqlite3_bind_text16` at `0x1401971c2`
- `winsqlite3!sqlite3_bind_text16` at `0x140197204`
- `winsqlite3!sqlite3_bind_text16` at `0x140197246`
- `winsqlite3!sqlite3_bind_text16` at `0x1401972bf`
- `winsqlite3!sqlite3_bind_text16` at `0x140197301`
- `winsqlite3!sqlite3_bind_text16` at `0x140197343`
- `winsqlite3!sqlite3_bind_int` at `0x14019727d`
- `winsqlite3!sqlite3_bind_int` at `0x14019727d`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140197034`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140197034`
- `winsqlite3!sqlite3_finalize` at `0x14019737c`
- `winsqlite3!sqlite3_finalize` at `0x14019737c`

## string_xrefs

- `0x140197029`: `INSERT OR REPLACE INTO UPDATEEVENTHISTORYDIAGNOSTICS (PROVIDERID, UPDATEID, STARTTIME, ENDTIME, EVENT, CATEGORY, TITLE, RESULT, REASON, APPROVALS, ISSEEKER, FLIGHTID, UPDATEMETADATA, OTHER) VALUES (?, ?, ?, NULL, ?, ?, ?, NULL, NULL, ?, ?, ?, ?, ?)`

## pseudocode

```c

```
