# Windows::UsoDatabase::GetLatestActionRecordProperties(UpdateIdentity const &)

- ea: `0x140195350`
- end: `0x140195725`
- name: `?GetLatestActionRecordProperties@UsoDatabase@Windows@@UEBA?AV?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@AEBUUpdateIdentity@@@Z`
- size: `981`
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
- `0x140195350`
- `0x1401a0f18`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401953f1`
- `winsqlite3!sqlite3_bind_text16` at `0x140195435`
- `winsqlite3!sqlite3_bind_text16` at `0x140195475`
- `winsqlite3!sqlite3_bind_text16` at `0x1401954b5`
- `winsqlite3!sqlite3_bind_text16` at `0x1401953f1`
- `winsqlite3!sqlite3_bind_text16` at `0x140195435`
- `winsqlite3!sqlite3_bind_text16` at `0x140195475`
- `winsqlite3!sqlite3_bind_text16` at `0x1401954b5`
- `winsqlite3!sqlite3_column_int` at `0x140195538`
- `winsqlite3!sqlite3_column_int` at `0x140195538`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401953ad`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401953ad`
- `winsqlite3!sqlite3_finalize` at `0x1401956a3`
- `winsqlite3!sqlite3_finalize` at `0x1401956a3`
- `winsqlite3!sqlite3_column_text16` at `0x140195514`
- `winsqlite3!sqlite3_column_text16` at `0x140195526`
- `winsqlite3!sqlite3_column_text16` at `0x140195514`
- `winsqlite3!sqlite3_column_text16` at `0x140195526`

## string_xrefs

- `0x1401953a2`: `SELECT VARIABLE, VALUE, TYPE FROM ACTIONRECORDSPROP WHERE PROVIDERID = ? AND UPDATEID = ? AND TIME = (SELECT MAX(TIME) FROM ACTIONRECORDS WHERE PROVIDERID = ? AND UPDATEID = ?)`

## pseudocode

```c

```
