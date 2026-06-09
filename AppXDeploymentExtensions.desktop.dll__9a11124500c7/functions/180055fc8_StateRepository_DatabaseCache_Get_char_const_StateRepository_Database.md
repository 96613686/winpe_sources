# StateRepository::DatabaseCache::Get(char const *,StateRepository::Database &)

- ea: `0x180055fc8`
- end: `0x180056201`
- name: `?Get@DatabaseCache@StateRepository@@QEAAPEAVDatabase@2@PEBDAEAV32@@Z`
- size: `569`
- prototype: `struct StateRepository::Database *__fastcall(StateRepository::DatabaseCache *__hidden this, const char *, struct StateRepository::Database *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007576c`

## callees

- `0x180003764`
- `0x180012fc8`
- `0x1800415c0`
- `0x180055fc8`
- `0x18007aeec`
- `0x1800ba475`
- `0x18012253c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180056057`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180056057`
- `StateRepository.Core!sqlite3_log` at `0x18005602a`
- `StateRepository.Core!sqlite3_log` at `0x18005611f`
- `StateRepository.Core!sqlite3_log` at `0x1800561e1`
- `StateRepository.Core!sqlite3_log` at `0x18005602a`
- `StateRepository.Core!sqlite3_log` at `0x18005611f`
- `StateRepository.Core!sqlite3_log` at `0x1800561e1`

## string_xrefs

- `0x18005613f`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x18005601d`: `[pre-DatabaseCache.Get] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s`
- `0x180056110`: `[DatabaseCache.Get(Hit)] #%u DatabaseCache Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: Filename %s`
- `0x1800561cb`: `[DatabaseCache.Get(Miss)] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s`

## pseudocode

```c

```
