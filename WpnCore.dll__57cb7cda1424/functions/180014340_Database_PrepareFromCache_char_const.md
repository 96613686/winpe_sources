# Database::PrepareFromCache(char const *)

- ea: `0x180014340`
- end: `0x1800147bb`
- name: `?PrepareFromCache@Database@@QEAA?AV?$shared_ptr@VStatement@@@std@@PEBD@Z`
- size: `1147`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x1800097b0`
- `0x18000fe3c`
- `0x18001575c`
- `0x180015a9c`
- `0x180016280`
- `0x180016510`

## callees

- `0x18000e5f4`
- `0x1800140e0`
- `0x1800142a0`
- `0x180014340`
- `0x1800147d0`
- `0x1800159e4`
- `0x1800a4810`
- `0x1800b99f0`
- `0x1800b9ecc`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800143ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800143ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014596`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001461f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014596`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001461f`
- `winsqlite3!sqlite3_db_handle` at `0x1800144e1`
- `winsqlite3!sqlite3_db_handle` at `0x1800144e1`
- `winsqlite3!sqlite3_log` at `0x1800143c1`
- `winsqlite3!sqlite3_log` at `0x180014521`
- `winsqlite3!sqlite3_log` at `0x18001460c`
- `winsqlite3!sqlite3_log` at `0x1800143c1`
- `winsqlite3!sqlite3_log` at `0x180014521`
- `winsqlite3!sqlite3_log` at `0x18001460c`

## string_xrefs

- `0x1800143b8`: `[pre-StatementCache.Get] StatementCache %p: Cache Size/Hits/Misses %u/%llu/%llu`
- `0x180014518`: `[StatementCache.Get(Hit)] Database %p: StatementCache %p: Statement %p: Cache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x180014603`: `[StatementCache.Get(Miss)] StatementCache %p: Cache Size/Hits/Misses %u/%llu/%llu: SQL %s`

## pseudocode

```c

```
