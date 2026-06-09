# Windows::UsoDatabase::GetApprovedUpdates(void)

- ea: `0x1401968b0`
- end: `0x140196afc`
- name: `?GetApprovedUpdates@UsoDatabase@Windows@@UEAA?AV?$vector@UApprovalRecord@SystemInterface@@V?$allocator@UApprovalRecord@SystemInterface@@@std@@@std@@XZ`
- size: `588`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1401968b0`
- `0x1401a0850`
- `0x1401a2a14`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140196966`
- `winsqlite3!sqlite3_step` at `0x140196a74`
- `winsqlite3!sqlite3_step` at `0x140196966`
- `winsqlite3!sqlite3_step` at `0x140196a74`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140196926`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140196926`
- `winsqlite3!sqlite3_finalize` at `0x140196a8c`
- `winsqlite3!sqlite3_finalize` at `0x140196a8c`
- `winsqlite3!sqlite3_column_text16` at `0x1401969a1`
- `winsqlite3!sqlite3_column_text16` at `0x1401969b3`
- `winsqlite3!sqlite3_column_text16` at `0x1401969a1`
- `winsqlite3!sqlite3_column_text16` at `0x1401969b3`

## string_xrefs

- `0x14019691b`: `SELECT UPDATEID, TIME FROM APPROVEDUPDATES`

## pseudocode

```c

```
