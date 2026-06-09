# Windows::UsoDatabase::GetActionRecords(UpdateIdentity const &,std::optional<uint>)

- ea: `0x140194350`
- end: `0x14019469d`
- name: `?GetActionRecords@UsoDatabase@Windows@@UEBA?AV?$vector@UActionRecord@SystemInterface@@V?$allocator@UActionRecord@SystemInterface@@@std@@@std@@AEBUUpdateIdentity@@V?$optional@I@4@@Z`
- size: `845`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x1400447ac`
- `0x140045404`
- `0x1401741c8`
- `0x140194350`
- `0x14019f510`
- `0x1401a2a14`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x1401945fa`
- `winsqlite3!sqlite3_step` at `0x1401945fa`
- `winsqlite3!sqlite3_bind_text16` at `0x14019440b`
- `winsqlite3!sqlite3_bind_text16` at `0x14019444d`
- `winsqlite3!sqlite3_bind_text16` at `0x14019440b`
- `winsqlite3!sqlite3_bind_text16` at `0x14019444d`
- `winsqlite3!sqlite3_bind_int` at `0x140194482`
- `winsqlite3!sqlite3_bind_int` at `0x140194482`
- `winsqlite3!sqlite3_column_int` at `0x1401945ba`
- `winsqlite3!sqlite3_column_int` at `0x1401945ba`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401943c7`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401943c7`
- `winsqlite3!sqlite3_finalize` at `0x140194612`
- `winsqlite3!sqlite3_finalize` at `0x140194612`
- `winsqlite3!sqlite3_column_text16` at `0x140194503`
- `winsqlite3!sqlite3_column_text16` at `0x14019454f`
- `winsqlite3!sqlite3_column_text16` at `0x140194587`
- `winsqlite3!sqlite3_column_text16` at `0x140194503`
- `winsqlite3!sqlite3_column_text16` at `0x14019454f`
- `winsqlite3!sqlite3_column_text16` at `0x140194587`

## string_xrefs

- `0x14019439a`: `SELECT TIME, ACTION, ACTIONCLASS, RESULT FROM ACTIONRECORDS WHERE PROVIDERID = ? AND UPDATEID = ? ORDER BY TIME DESC LIMIT ?`
- `0x1401943a1`: `SELECT TIME, ACTION, ACTIONCLASS, RESULT FROM ACTIONRECORDS WHERE PROVIDERID = ? AND UPDATEID = ? ORDER BY TIME DESC`

## pseudocode

```c

```
