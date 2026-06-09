# MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(long,sqlite3 *)

- ea: `0x1800a2cf8`
- end: `0x1800a2d58`
- name: `?MapSqliteBusySnapshotToSqliteBusyIfRaceCondition@@YAJJPEAUsqlite3@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(int, struct sqlite3 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800a32d4`
- `0x1800a6a00`
- `0x1800a8bd8`

## callees

- `0x1800a2cf8`

## import_xrefs

- `winsqlite3!sqlite3_get_autocommit` at `0x1800a2d14`
- `winsqlite3!sqlite3_get_autocommit` at `0x1800a2d14`
- `winsqlite3!sqlite3_next_stmt` at `0x1800a2d26`
- `winsqlite3!sqlite3_next_stmt` at `0x1800a2d26`
- `winsqlite3!sqlite3_stmt_busy` at `0x1800a2d37`
- `winsqlite3!sqlite3_stmt_busy` at `0x1800a2d37`

## pseudocode

```c

```
