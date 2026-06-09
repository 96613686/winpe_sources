# Windows::UsoDatabase::GetDowntimeHistoryEntries(void)

- ea: `0x140199bb0`
- end: `0x140199d9e`
- name: `?GetDowntimeHistoryEntries@UsoDatabase@Windows@@UEAA?AV?$vector@UDowntimeHistoryLabelRecord@SystemInterface@@V?$allocator@UDowntimeHistoryLabelRecord@SystemInterface@@@std@@@std@@XZ`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140199bb0`
- `0x14019fcb4`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140199d33`
- `winsqlite3!sqlite3_step` at `0x140199d33`
- `winsqlite3!sqlite3_column_int` at `0x140199c80`
- `winsqlite3!sqlite3_column_int` at `0x140199c91`
- `winsqlite3!sqlite3_column_int` at `0x140199ca2`
- `winsqlite3!sqlite3_column_int` at `0x140199cb7`
- `winsqlite3!sqlite3_column_int` at `0x140199c80`
- `winsqlite3!sqlite3_column_int` at `0x140199c91`
- `winsqlite3!sqlite3_column_int` at `0x140199ca2`
- `winsqlite3!sqlite3_column_int` at `0x140199cb7`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140199c05`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140199c05`
- `winsqlite3!sqlite3_finalize` at `0x140199d4b`
- `winsqlite3!sqlite3_finalize` at `0x140199d4b`
- `winsqlite3!sqlite3_column_text16` at `0x140199c6a`
- `winsqlite3!sqlite3_column_text16` at `0x140199c6a`

## string_xrefs

- `0x140199bfa`: `SELECT UPDATEMETADATA, ESTIMATEDTIME, ESTIMATEDTIMEHIGH, REALLABEL, REALLABELSECONDS FROM DOWNTIMEHISTORY WHERE REALLABEL IS NOT NULL`

## pseudocode

```c

```
