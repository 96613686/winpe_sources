# Windows::UsoDatabase::GetRebootHistory(void)

- ea: `0x14019dfe0`
- end: `0x14019e4ed`
- name: `?GetRebootHistory@UsoDatabase@Windows@@UEBA?AV?$vector@URebootHistoryRecord@SystemInterface@@V?$allocator@URebootHistoryRecord@SystemInterface@@@std@@@std@@XZ`
- size: `1293`
- prototype: `__int64 __fastcall(Windows::UsoDatabase *this)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x14012d7d8`
- `0x140191240`
- `0x14019dfe0`
- `0x14019f5d8`
- `0x1401a0314`
- `0x1401a271c`
- `0x1401a2a14`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019e037`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019e037`
- `winsqlite3!sqlite3_step` at `0x14019e152`
- `winsqlite3!sqlite3_step` at `0x14019e152`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e11a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e11a`
- `winsqlite3!sqlite3_finalize` at `0x14019e24c`
- `winsqlite3!sqlite3_finalize` at `0x14019e24c`
- `winsqlite3!sqlite3_column_text16` at `0x14019e2b0`
- `winsqlite3!sqlite3_column_text16` at `0x14019e2c6`
- `winsqlite3!sqlite3_column_text16` at `0x14019e2e1`
- `winsqlite3!sqlite3_column_text16` at `0x14019e2b0`
- `winsqlite3!sqlite3_column_text16` at `0x14019e2c6`
- `winsqlite3!sqlite3_column_text16` at `0x14019e2e1`

## string_xrefs

- `0x14019e10f`: `SELECT REBOOTATTEMPTTIMESTAMP, DEFERRALREASON, REBOOTREQUIREDTIMEUTC FROM REBOOTDEFERRALHISTORYSTATUS ORDER BY REBOOTATTEMPTTIMESTAMP`

## pseudocode

```c

```
