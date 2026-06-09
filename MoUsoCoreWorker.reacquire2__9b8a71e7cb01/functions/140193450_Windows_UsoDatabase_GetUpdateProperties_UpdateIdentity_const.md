# Windows::UsoDatabase::GetUpdateProperties(UpdateIdentity const &)

- ea: `0x140193450`
- end: `0x140193760`
- name: `?GetUpdateProperties@UsoDatabase@Windows@@UEBA?AV?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@AEBUUpdateIdentity@@@Z`
- size: `784`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1400ddb98`
- `0x14018d1a4`
- `0x140192f5c`
- `0x140193450`
- `0x1401a0f18`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401934f0`
- `winsqlite3!sqlite3_bind_text16` at `0x14019352f`
- `winsqlite3!sqlite3_bind_text16` at `0x1401934f0`
- `winsqlite3!sqlite3_bind_text16` at `0x14019352f`
- `winsqlite3!sqlite3_column_int` at `0x140193597`
- `winsqlite3!sqlite3_column_int` at `0x140193597`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401934ad`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401934ad`
- `winsqlite3!sqlite3_finalize` at `0x140193702`
- `winsqlite3!sqlite3_finalize` at `0x140193702`
- `winsqlite3!sqlite3_column_text16` at `0x140193573`
- `winsqlite3!sqlite3_column_text16` at `0x140193585`
- `winsqlite3!sqlite3_column_text16` at `0x140193573`
- `winsqlite3!sqlite3_column_text16` at `0x140193585`

## string_xrefs

- `0x1401934a3`: `SELECT VARIABLE, VALUE, TYPE FROM UPDATESPROP WHERE PROVIDERID = ? AND UPDATEID = ?`

## pseudocode

```c

```
