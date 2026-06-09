# Windows::UsoDatabase::GetUpdate(UpdateIdentity const &)

- ea: `0x1401924e0`
- end: `0x14019279d`
- name: `?GetUpdate@UsoDatabase@Windows@@UEBA?AV?$optional@UUpdateStorage@SystemInterface@@@std@@AEBUUpdateIdentity@@@Z`
- size: `701`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x14003f4bc`
- `0x1400413a8`
- `0x1400447ac`
- `0x14004519c`
- `0x140045404`
- `0x14004d3b8`
- `0x1401924e0`
- `0x140379070`
- `0x140380f90`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x1401925e3`
- `winsqlite3!sqlite3_step` at `0x1401925e3`
- `winsqlite3!sqlite3_bind_text16` at `0x14019257d`
- `winsqlite3!sqlite3_bind_text16` at `0x1401925bf`
- `winsqlite3!sqlite3_bind_text16` at `0x14019257d`
- `winsqlite3!sqlite3_bind_text16` at `0x1401925bf`
- `winsqlite3!sqlite3_column_bytes` at `0x140192611`
- `winsqlite3!sqlite3_column_bytes` at `0x140192611`
- `winsqlite3!sqlite3_column_blob` at `0x140192620`
- `winsqlite3!sqlite3_column_blob` at `0x140192620`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019253a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019253a`
- `winsqlite3!sqlite3_finalize` at `0x1401925ff`
- `winsqlite3!sqlite3_finalize` at `0x140192730`
- `winsqlite3!sqlite3_finalize` at `0x1401925ff`
- `winsqlite3!sqlite3_finalize` at `0x140192730`

## string_xrefs

- `0x14019252f`: `SELECT SERIALIZEDUPDATE FROM UPDATES WHERE PROVIDERID = ? AND UPDATEID = ?`

## pseudocode

```c

```
