# Windows::UsoDatabase::GetActionRecords(void)

- ea: `0x140193fe0`
- end: `0x140194346`
- name: `?GetActionRecords@UsoDatabase@Windows@@UEBA?AV?$vector@UActionRecord@SystemInterface@@V?$allocator@UActionRecord@SystemInterface@@@std@@@std@@XZ`
- size: `870`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1401741c8`
- `0x140193fe0`
- `0x14019f510`
- `0x1401a2a14`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140194084`
- `winsqlite3!sqlite3_step` at `0x1401942d8`
- `winsqlite3!sqlite3_step` at `0x140194084`
- `winsqlite3!sqlite3_step` at `0x1401942d8`
- `winsqlite3!sqlite3_column_int` at `0x1401941f4`
- `winsqlite3!sqlite3_column_int` at `0x1401941f4`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140194040`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140194040`
- `winsqlite3!sqlite3_finalize` at `0x1401942f0`
- `winsqlite3!sqlite3_finalize` at `0x1401942f0`
- `winsqlite3!sqlite3_column_text16` at `0x1401940c2`
- `winsqlite3!sqlite3_column_text16` at `0x1401940fa`
- `winsqlite3!sqlite3_column_text16` at `0x140194132`
- `winsqlite3!sqlite3_column_text16` at `0x140194184`
- `winsqlite3!sqlite3_column_text16` at `0x1401941bc`
- `winsqlite3!sqlite3_column_text16` at `0x1401940c2`
- `winsqlite3!sqlite3_column_text16` at `0x1401940fa`
- `winsqlite3!sqlite3_column_text16` at `0x140194132`
- `winsqlite3!sqlite3_column_text16` at `0x140194184`
- `winsqlite3!sqlite3_column_text16` at `0x1401941bc`

## string_xrefs

- `0x140194035`: `SELECT PROVIDERID, UPDATEID, TIME, ACTION, ACTIONCLASS, RESULT FROM ACTIONRECORDS ORDER BY TIME DESC`

## pseudocode

```c

```
