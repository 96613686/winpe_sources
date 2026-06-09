# Windows::UsoDatabase::GetSignalUpdatePayloadId(wil::basic_zstring_view<wchar_t>)

- ea: `0x140198ae0`
- end: `0x140198c5c`
- name: `?GetSignalUpdatePayloadId@UsoDatabase@Windows@@UEAA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x140198ae0`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140198b8a`
- `winsqlite3!sqlite3_step` at `0x140198b8a`
- `winsqlite3!sqlite3_bind_text16` at `0x140198b62`
- `winsqlite3!sqlite3_bind_text16` at `0x140198b62`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198b2c`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198b2c`
- `winsqlite3!sqlite3_finalize` at `0x140198c01`
- `winsqlite3!sqlite3_finalize` at `0x140198c17`
- `winsqlite3!sqlite3_finalize` at `0x140198c01`
- `winsqlite3!sqlite3_finalize` at `0x140198c17`
- `winsqlite3!sqlite3_column_text16` at `0x140198b9b`
- `winsqlite3!sqlite3_column_text16` at `0x140198b9b`

## string_xrefs

- `0x140198b21`: `SELECT PAYLOADID FROM SIGNALUPDATES WHERE UNIQUEID = ?`

## pseudocode

```c

```
