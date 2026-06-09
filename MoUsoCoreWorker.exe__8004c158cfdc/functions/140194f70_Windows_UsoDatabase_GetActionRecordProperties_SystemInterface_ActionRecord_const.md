# Windows::UsoDatabase::GetActionRecordProperties(SystemInterface::ActionRecord const &)

- ea: `0x140194f70`
- end: `0x14019534a`
- name: `?GetActionRecordProperties@UsoDatabase@Windows@@UEBA?AV?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@AEBUActionRecord@SystemInterface@@@Z`
- size: `986`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400c6f6c`
- `0x1400ddb98`
- `0x14018d1a4`
- `0x140192f5c`
- `0x140194f70`
- `0x1401a0f18`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140195011`
- `winsqlite3!sqlite3_bind_text16` at `0x140195050`
- `winsqlite3!sqlite3_bind_text16` at `0x1401950d2`
- `winsqlite3!sqlite3_bind_text16` at `0x140195011`
- `winsqlite3!sqlite3_bind_text16` at `0x140195050`
- `winsqlite3!sqlite3_bind_text16` at `0x1401950d2`
- `winsqlite3!sqlite3_column_int` at `0x140195143`
- `winsqlite3!sqlite3_column_int` at `0x140195143`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140194fcd`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140194fcd`
- `winsqlite3!sqlite3_finalize` at `0x1401952b3`
- `winsqlite3!sqlite3_finalize` at `0x1401952b3`
- `winsqlite3!sqlite3_column_text16` at `0x14019511f`
- `winsqlite3!sqlite3_column_text16` at `0x140195131`
- `winsqlite3!sqlite3_column_text16` at `0x14019511f`
- `winsqlite3!sqlite3_column_text16` at `0x140195131`

## string_xrefs

- `0x140194fc3`: `SELECT VARIABLE, VALUE, TYPE FROM ACTIONRECORDSPROP WHERE PROVIDERID = ? AND UPDATEID = ? AND TIME = ?`

## pseudocode

```c

```
