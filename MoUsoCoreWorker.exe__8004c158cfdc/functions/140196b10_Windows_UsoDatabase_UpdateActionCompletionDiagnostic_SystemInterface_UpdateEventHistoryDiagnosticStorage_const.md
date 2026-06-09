# Windows::UsoDatabase::UpdateActionCompletionDiagnostic(SystemInterface::UpdateEventHistoryDiagnosticStorage const &)

- ea: `0x140196b10`
- end: `0x140196f92`
- name: `?UpdateActionCompletionDiagnostic@UsoDatabase@Windows@@UEAAXAEBUUpdateEventHistoryDiagnosticStorage@SystemInterface@@@Z`
- size: `1154`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct SystemInterface::UpdateEventHistoryDiagnosticStorage *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400bdb64`
- `0x1400c6f6c`
- `0x14018d1a4`
- `0x140196b10`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140196b50`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140196b50`
- `winsqlite3!sqlite3_bind_text16` at `0x140196c2d`
- `winsqlite3!sqlite3_bind_text16` at `0x140196ca6`
- `winsqlite3!sqlite3_bind_text16` at `0x140196ce8`
- `winsqlite3!sqlite3_bind_text16` at `0x140196d26`
- `winsqlite3!sqlite3_bind_text16` at `0x140196d65`
- `winsqlite3!sqlite3_bind_text16` at `0x140196de2`
- `winsqlite3!sqlite3_bind_text16` at `0x140196e2a`
- `winsqlite3!sqlite3_bind_text16` at `0x140196c2d`
- `winsqlite3!sqlite3_bind_text16` at `0x140196ca6`
- `winsqlite3!sqlite3_bind_text16` at `0x140196ce8`
- `winsqlite3!sqlite3_bind_text16` at `0x140196d26`
- `winsqlite3!sqlite3_bind_text16` at `0x140196d65`
- `winsqlite3!sqlite3_bind_text16` at `0x140196de2`
- `winsqlite3!sqlite3_bind_text16` at `0x140196e2a`
- `winsqlite3!sqlite3_bind_int` at `0x140196c64`
- `winsqlite3!sqlite3_bind_int` at `0x140196c64`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140196ba2`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140196ba2`
- `winsqlite3!sqlite3_finalize` at `0x140196e63`
- `winsqlite3!sqlite3_finalize` at `0x140196e63`

## string_xrefs

- `0x140196b97`: `UPDATE UPDATEEVENTHISTORYDIAGNOSTICS SET ENDTIME = ?, RESULT = ?, REASON = ?, OTHER = json_patch(COALESCE(OTHER, '{}'), ?) WHERE PROVIDERID = ? AND UPDATEID = ? AND STARTTIME = ? AND EVENT = ?`

## pseudocode

```c

```
