# Windows::UsoDatabase::HasIncompleteWSXPackUpdates(wil::basic_zstring_view<wchar_t>)

- ea: `0x140198d80`
- end: `0x140198edc`
- name: `?HasIncompleteWSXPackUpdates@UsoDatabase@Windows@@UEAA_NV?$basic_zstring_view@_W@wil@@@Z`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400413a8`
- `0x140198d80`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140198e5d`
- `winsqlite3!sqlite3_step` at `0x140198e5d`
- `winsqlite3!sqlite3_bind_text16` at `0x140198e06`
- `winsqlite3!sqlite3_bind_text16` at `0x140198e06`
- `winsqlite3!sqlite3_bind_int` at `0x140198e37`
- `winsqlite3!sqlite3_bind_int` at `0x140198e37`
- `winsqlite3!sqlite3_column_int` at `0x140198e6f`
- `winsqlite3!sqlite3_column_int` at `0x140198e6f`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198dca`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198dca`
- `winsqlite3!sqlite3_finalize` at `0x140198e85`
- `winsqlite3!sqlite3_finalize` at `0x140198e85`

## string_xrefs

- `0x140198dbf`: `SELECT COUNT(*) FROM WSXPACKUPDATES WHERE PAYLOADID = ? AND IFNULL(STATE, 0) <> ?`

## pseudocode

```c

```
