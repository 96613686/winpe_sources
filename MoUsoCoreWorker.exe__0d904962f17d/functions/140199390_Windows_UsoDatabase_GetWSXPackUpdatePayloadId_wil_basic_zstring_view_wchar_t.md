# Windows::UsoDatabase::GetWSXPackUpdatePayloadId(wil::basic_zstring_view<wchar_t>)

- ea: `0x140199390`
- end: `0x14019950c`
- name: `?GetWSXPackUpdatePayloadId@UsoDatabase@Windows@@UEAA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x140199390`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x14019943a`
- `winsqlite3!sqlite3_step` at `0x14019943a`
- `winsqlite3!sqlite3_bind_text16` at `0x140199412`
- `winsqlite3!sqlite3_bind_text16` at `0x140199412`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401993dc`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401993dc`
- `winsqlite3!sqlite3_finalize` at `0x1401994b1`
- `winsqlite3!sqlite3_finalize` at `0x1401994c7`
- `winsqlite3!sqlite3_finalize` at `0x1401994b1`
- `winsqlite3!sqlite3_finalize` at `0x1401994c7`
- `winsqlite3!sqlite3_column_text16` at `0x14019944b`
- `winsqlite3!sqlite3_column_text16` at `0x14019944b`

## string_xrefs

- `0x1401993d1`: `SELECT PAYLOADID FROM WSXPACKUPDATES WHERE UNIQUEID = ?`

## pseudocode

```c

```
