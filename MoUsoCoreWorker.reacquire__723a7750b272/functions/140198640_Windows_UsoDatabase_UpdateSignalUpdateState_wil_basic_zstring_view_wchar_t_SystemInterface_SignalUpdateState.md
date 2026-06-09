# Windows::UsoDatabase::UpdateSignalUpdateState(wil::basic_zstring_view<wchar_t>,SystemInterface::SignalUpdateState)

- ea: `0x140198640`
- end: `0x1401987ce`
- name: `?UpdateSignalUpdateState@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@W4SignalUpdateState@SystemInterface@@@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140198640`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401986cc`
- `winsqlite3!sqlite3_bind_text16` at `0x1401986cc`
- `winsqlite3!sqlite3_bind_int` at `0x1401986fb`
- `winsqlite3!sqlite3_bind_int` at `0x14019872a`
- `winsqlite3!sqlite3_bind_int` at `0x1401986fb`
- `winsqlite3!sqlite3_bind_int` at `0x14019872a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019868d`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019868d`
- `winsqlite3!sqlite3_finalize` at `0x140198765`
- `winsqlite3!sqlite3_finalize` at `0x140198765`

## string_xrefs

- `0x140198683`: `INSERT INTO SIGNALUPDATES (UNIQUEID, STATE) VALUES (?, ?) ON CONFLICT(UNIQUEID) DO UPDATE SET STATE = ?`

## pseudocode

```c

```
