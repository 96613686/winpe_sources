# Windows::UsoDatabase::GetSignalUpdateState(wil::basic_zstring_view<wchar_t>)

- ea: `0x1401987e0`
- end: `0x140198931`
- name: `?GetSignalUpdateState@UsoDatabase@Windows@@UEAA?AV?$optional@W4SignalUpdateState@SystemInterface@@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x1401987e0`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140198890`
- `winsqlite3!sqlite3_step` at `0x140198890`
- `winsqlite3!sqlite3_bind_text16` at `0x140198866`
- `winsqlite3!sqlite3_bind_text16` at `0x140198866`
- `winsqlite3!sqlite3_column_int` at `0x1401988a2`
- `winsqlite3!sqlite3_column_int` at `0x1401988a2`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198828`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198828`
- `winsqlite3!sqlite3_finalize` at `0x1401988b9`
- `winsqlite3!sqlite3_finalize` at `0x1401988d4`
- `winsqlite3!sqlite3_finalize` at `0x1401988eb`
- `winsqlite3!sqlite3_finalize` at `0x1401988b9`
- `winsqlite3!sqlite3_finalize` at `0x1401988d4`
- `winsqlite3!sqlite3_finalize` at `0x1401988eb`

## string_xrefs

- `0x14019881d`: `SELECT STATE FROM SIGNALUPDATES WHERE UNIQUEID = ?`

## pseudocode

```c

```
