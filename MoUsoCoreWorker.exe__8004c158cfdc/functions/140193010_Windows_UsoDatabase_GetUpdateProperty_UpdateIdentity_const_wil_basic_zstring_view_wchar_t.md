# Windows::UsoDatabase::GetUpdateProperty(UpdateIdentity const &,wil::basic_zstring_view<wchar_t>)

- ea: `0x140193010`
- end: `0x140193281`
- name: `?GetUpdateProperty@UsoDatabase@Windows@@UEBA?AV?$optional@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@AEBUUpdateIdentity@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `625`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1400ddb98`
- `0x140192f5c`
- `0x140193010`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140193143`
- `winsqlite3!sqlite3_step` at `0x140193143`
- `winsqlite3!sqlite3_bind_text16` at `0x1401930ac`
- `winsqlite3!sqlite3_bind_text16` at `0x1401930eb`
- `winsqlite3!sqlite3_bind_text16` at `0x14019311f`
- `winsqlite3!sqlite3_bind_text16` at `0x1401930ac`
- `winsqlite3!sqlite3_bind_text16` at `0x1401930eb`
- `winsqlite3!sqlite3_bind_text16` at `0x14019311f`
- `winsqlite3!sqlite3_column_int` at `0x14019316a`
- `winsqlite3!sqlite3_column_int` at `0x14019316a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140193068`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140193068`
- `winsqlite3!sqlite3_finalize` at `0x1401931fb`
- `winsqlite3!sqlite3_finalize` at `0x140193211`
- `winsqlite3!sqlite3_finalize` at `0x1401931fb`
- `winsqlite3!sqlite3_finalize` at `0x140193211`
- `winsqlite3!sqlite3_column_text16` at `0x140193158`
- `winsqlite3!sqlite3_column_text16` at `0x140193158`

## string_xrefs

- `0x14019305d`: `SELECT VALUE, TYPE FROM UPDATESPROP WHERE PROVIDERID = ? AND UPDATEID = ? AND VARIABLE = ?`

## pseudocode

```c

```
