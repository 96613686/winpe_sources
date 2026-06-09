# StateRepository::DatabaseCache::Get(char const *,StateRepository::Database &)

- ea: `0x1800af2e0`
- end: `0x1800af4ff`
- name: `?Get@DatabaseCache@StateRepository@@QEAAPEAVDatabase@2@PEBDAEAV32@@Z`
- size: `543`
- prototype: `struct StateRepository::Database *__fastcall(StateRepository::DatabaseCache *__hidden this, const char *, struct StateRepository::Database *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800a17a0`

## callees

- `0x180006854`
- `0x18000a044`
- `0x18000d841`
- `0x1800210d4`
- `0x1800a41e8`
- `0x1800ad850`
- `0x1800af2e0`
- `0x1800af620`

## import_xrefs

- `winsqlite3!sqlite3_log` at `0x1800af342`
- `winsqlite3!sqlite3_log` at `0x1800af42a`
- `winsqlite3!sqlite3_log` at `0x1800af4e6`
- `winsqlite3!sqlite3_log` at `0x1800af342`
- `winsqlite3!sqlite3_log` at `0x1800af42a`
- `winsqlite3!sqlite3_log` at `0x1800af4e6`

## string_xrefs

- `0x1800af41b`: `[DatabaseCache.Get(Hit)] #%u DatabaseCache Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: Filename %s`
- `0x1800af335`: `[pre-DatabaseCache.Get] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s`
- `0x1800af444`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800af4d0`: `[DatabaseCache.Get(Miss)] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s`

## pseudocode

```c

```
