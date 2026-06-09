# Windows::UsoDatabase::GetActionRecordProperty(SystemInterface::ActionRecord const &,wil::basic_zstring_view<wchar_t>)

- ea: `0x1401949a0`
- end: `0x140194cce`
- name: `?GetActionRecordProperty@UsoDatabase@Windows@@UEBA?AV?$optional@V?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@AEBUActionRecord@SystemInterface@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `814`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400c6f6c`
- `0x1400ddb98`
- `0x140192f5c`
- `0x1401949a0`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140194b57`
- `winsqlite3!sqlite3_step` at `0x140194b57`
- `winsqlite3!sqlite3_bind_text16` at `0x140194a3c`
- `winsqlite3!sqlite3_bind_text16` at `0x140194a7b`
- `winsqlite3!sqlite3_bind_text16` at `0x140194af6`
- `winsqlite3!sqlite3_bind_text16` at `0x140194b33`
- `winsqlite3!sqlite3_bind_text16` at `0x140194a3c`
- `winsqlite3!sqlite3_bind_text16` at `0x140194a7b`
- `winsqlite3!sqlite3_bind_text16` at `0x140194af6`
- `winsqlite3!sqlite3_bind_text16` at `0x140194b33`
- `winsqlite3!sqlite3_column_int` at `0x140194b7e`
- `winsqlite3!sqlite3_column_int` at `0x140194b7e`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401949f8`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401949f8`
- `winsqlite3!sqlite3_finalize` at `0x140194c0f`
- `winsqlite3!sqlite3_finalize` at `0x140194c25`
- `winsqlite3!sqlite3_finalize` at `0x140194c0f`
- `winsqlite3!sqlite3_finalize` at `0x140194c25`
- `winsqlite3!sqlite3_column_text16` at `0x140194b6c`
- `winsqlite3!sqlite3_column_text16` at `0x140194b6c`

## string_xrefs

- `0x1401949ed`: `SELECT VALUE, TYPE FROM ACTIONRECORDSPROP WHERE PROVIDERID = ? AND UPDATEID = ? AND TIME = ? AND VARIABLE = ?`

## pseudocode

```c

```
