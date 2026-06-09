# Windows::UsoDatabase::GetWSXPackUpdateState(wil::basic_zstring_view<wchar_t>)

- ea: `0x140199090`
- end: `0x1401991e1`
- name: `?GetWSXPackUpdateState@UsoDatabase@Windows@@UEAA?AV?$optional@W4WSXPackUpdateState@SystemInterface@@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140199090`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140199140`
- `winsqlite3!sqlite3_step` at `0x140199140`
- `winsqlite3!sqlite3_bind_text16` at `0x140199116`
- `winsqlite3!sqlite3_bind_text16` at `0x140199116`
- `winsqlite3!sqlite3_column_int` at `0x140199152`
- `winsqlite3!sqlite3_column_int` at `0x140199152`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401990d8`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401990d8`
- `winsqlite3!sqlite3_finalize` at `0x140199169`
- `winsqlite3!sqlite3_finalize` at `0x140199184`
- `winsqlite3!sqlite3_finalize` at `0x14019919b`
- `winsqlite3!sqlite3_finalize` at `0x140199169`
- `winsqlite3!sqlite3_finalize` at `0x140199184`
- `winsqlite3!sqlite3_finalize` at `0x14019919b`

## string_xrefs

- `0x1401990cd`: `SELECT STATE FROM WSXPACKUPDATES WHERE UNIQUEID = ?`

## pseudocode

```c

```
