# Windows::UsoDatabase::UpdateWSXPackUpdateState(wil::basic_zstring_view<wchar_t>,SystemInterface::WSXPackUpdateState)

- ea: `0x140198ef0`
- end: `0x14019907e`
- name: `?UpdateWSXPackUpdateState@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@W4WSXPackUpdateState@SystemInterface@@@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140198ef0`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140198f7c`
- `winsqlite3!sqlite3_bind_text16` at `0x140198f7c`
- `winsqlite3!sqlite3_bind_int` at `0x140198fab`
- `winsqlite3!sqlite3_bind_int` at `0x140198fda`
- `winsqlite3!sqlite3_bind_int` at `0x140198fab`
- `winsqlite3!sqlite3_bind_int` at `0x140198fda`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198f3d`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198f3d`
- `winsqlite3!sqlite3_finalize` at `0x140199015`
- `winsqlite3!sqlite3_finalize` at `0x140199015`

## string_xrefs

- `0x140198f33`: `INSERT INTO WSXPACKUPDATES (UNIQUEID, STATE) VALUES (?, ?) ON CONFLICT(UNIQUEID) DO UPDATE SET STATE = ?`

## pseudocode

```c

```
