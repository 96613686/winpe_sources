# Windows::UsoDatabase::GetAllUpdates(void)

- ea: `0x1401927b0`
- end: `0x140192ad0`
- name: `?GetAllUpdates@UsoDatabase@Windows@@UEBA?AV?$vector@UUpdateStorage@SystemInterface@@V?$allocator@UUpdateStorage@SystemInterface@@@std@@@std@@XZ`
- size: `800`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x14018eaa4`

## callees

- `0x14003f4bc`
- `0x1400413a8`
- `0x140043284`
- `0x14004519c`
- `0x140045404`
- `0x14004d3b8`
- `0x1401927b0`
- `0x1401a11c4`
- `0x140379070`
- `0x140380f90`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x14019284b`
- `winsqlite3!sqlite3_step` at `0x140192a5c`
- `winsqlite3!sqlite3_step` at `0x14019284b`
- `winsqlite3!sqlite3_step` at `0x140192a5c`
- `winsqlite3!sqlite3_column_bytes` at `0x1401928f8`
- `winsqlite3!sqlite3_column_bytes` at `0x1401928f8`
- `winsqlite3!sqlite3_column_blob` at `0x14019290a`
- `winsqlite3!sqlite3_column_blob` at `0x14019290a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019280a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019280a`
- `winsqlite3!sqlite3_finalize` at `0x140192a74`
- `winsqlite3!sqlite3_finalize` at `0x140192a74`
- `winsqlite3!sqlite3_column_text16` at `0x140192886`
- `winsqlite3!sqlite3_column_text16` at `0x1401928bf`
- `winsqlite3!sqlite3_column_text16` at `0x140192886`
- `winsqlite3!sqlite3_column_text16` at `0x1401928bf`

## string_xrefs

- `0x1401927ff`: `SELECT PROVIDERID, UPDATEID, SERIALIZEDUPDATE FROM UPDATES`

## pseudocode

```c

```
