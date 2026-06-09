# StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)

- ea: `0x1800a9a2c`
- end: `0x1800a9bf8`
- name: `?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z`
- size: `460`
- prototype: `struct StateRepository::Statement *(StateRepository::StatementCache *__hidden this, const char *, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800a5520`

## callees

- `0x18000d841`
- `0x1800210d4`
- `0x180030fa4`
- `0x1800a2bd0`
- `0x1800a97d4`
- `0x1800a9a2c`
- `0x1800a9c00`

## import_xrefs

- `winsqlite3!sqlite3_log` at `0x1800a9a7f`
- `winsqlite3!sqlite3_log` at `0x1800a9b61`
- `winsqlite3!sqlite3_log` at `0x1800a9be3`
- `winsqlite3!sqlite3_log` at `0x1800a9a7f`
- `winsqlite3!sqlite3_log` at `0x1800a9b61`
- `winsqlite3!sqlite3_log` at `0x1800a9be3`
- `winsqlite3!sqlite3_db_handle` at `0x1800a9b00`
- `winsqlite3!sqlite3_db_handle` at `0x1800a9b00`

## string_xrefs

- `0x1800a9b7b`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x1800a9bcd`: `[StatementCache.Get(Miss)] #%u StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x1800a9b52`: `[StatementCache.Get(Hit)] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x1800a9a6e`: `[pre-StatementCache.Get] #%u StatementCache Size/Hits/Misses %u/%llu/%llu`

## pseudocode

```c

```
