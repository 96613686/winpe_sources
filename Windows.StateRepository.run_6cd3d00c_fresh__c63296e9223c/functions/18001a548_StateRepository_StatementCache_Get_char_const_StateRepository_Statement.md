# StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)

- ea: `0x18001a548`
- end: `0x18001a727`
- name: `?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z`
- size: `479`
- prototype: `struct StateRepository::Statement *(StateRepository::StatementCache *__hidden this, const char *, struct StateRepository::Statement *)`
- caller_count: `28`
- callee_count: `7`
- tags: ``

## callers

- `0x180005c60`
- `0x18000629c`
- `0x1800065fc`
- `0x180006950`
- `0x180006ca8`
- `0x180006fec`
- `0x180007384`
- `0x1800076c0`
- `0x18000bb70`
- `0x18000dc60`
- `0x18000e144`
- `0x180010260`
- `0x180010a48`
- `0x180011bfc`
- `0x180012e84`
- `0x1800140f4`
- `0x1800189bc`
- `0x180018de8`
- `0x180019324`
- `0x180019d90`
- `0x18001a070`
- `0x18001a450`
- `0x18001a730`
- `0x180030c58`
- `0x18005319c`
- `0x1800590fc`
- `0x180062ee0`
- `0x1800640b0`

## callees

- `0x180017a58`
- `0x180018d78`
- `0x18001a548`
- `0x18001cc00`
- `0x180056520`
- `0x1800631dc`
- `0x18027b98c`

## import_xrefs

- `StateRepository.Core!sqlite3_db_handle` at `0x18001a61c`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001a61c`
- `StateRepository.Core!sqlite3_log` at `0x18001a59b`
- `StateRepository.Core!sqlite3_log` at `0x18001a690`
- `StateRepository.Core!sqlite3_log` at `0x18001a712`
- `StateRepository.Core!sqlite3_log` at `0x18001a59b`
- `StateRepository.Core!sqlite3_log` at `0x18001a690`
- `StateRepository.Core!sqlite3_log` at `0x18001a712`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001a62c`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001a62c`

## string_xrefs

- `0x18001a6aa`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x18001a6fc`: `[StatementCache.Get(Miss)] #%u StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x18001a681`: `[StatementCache.Get(Hit)] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x18001a58a`: `[pre-StatementCache.Get] #%u StatementCache Size/Hits/Misses %u/%llu/%llu`

## pseudocode

```c

```
