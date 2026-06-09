# StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)

- ea: `0x180046fd0`
- end: `0x180047409`
- name: `?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z`
- size: `1081`
- prototype: `struct StateRepository::Statement *__fastcall(StateRepository::StatementCache *__hidden this, const char *, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180046f00`

## callees

- `0x180012fc8`
- `0x18001adb4`
- `0x180046fd0`
- `0x1800af1bc`
- `0x1800ba475`

## import_xrefs

- `StateRepository.Core!sqlite3_db_handle` at `0x1800470fa`
- `StateRepository.Core!sqlite3_db_handle` at `0x18004721b`
- `StateRepository.Core!sqlite3_db_handle` at `0x1800470fa`
- `StateRepository.Core!sqlite3_db_handle` at `0x18004721b`
- `StateRepository.Core!sqlite3_log` at `0x18004702b`
- `StateRepository.Core!sqlite3_log` at `0x180047198`
- `StateRepository.Core!sqlite3_log` at `0x180047292`
- `StateRepository.Core!sqlite3_log` at `0x18004732e`
- `StateRepository.Core!sqlite3_log` at `0x180047375`
- `StateRepository.Core!sqlite3_log` at `0x1800473eb`
- `StateRepository.Core!sqlite3_log` at `0x18004702b`
- `StateRepository.Core!sqlite3_log` at `0x180047198`
- `StateRepository.Core!sqlite3_log` at `0x180047292`
- `StateRepository.Core!sqlite3_log` at `0x18004732e`
- `StateRepository.Core!sqlite3_log` at `0x180047375`
- `StateRepository.Core!sqlite3_log` at `0x1800473eb`
- `StateRepository.Core!sqlite3_finalize` at `0x1800472a1`
- `StateRepository.Core!sqlite3_finalize` at `0x1800472a1`
- `StateRepository.Core!sqlite3_errmsg` at `0x1800472dd`
- `StateRepository.Core!sqlite3_errmsg` at `0x1800472dd`
- `StateRepository.Core!sqlite3_sql` at `0x180047063`
- `StateRepository.Core!sqlite3_sql` at `0x180047128`
- `StateRepository.Core!sqlite3_sql` at `0x180047147`
- `StateRepository.Core!sqlite3_sql` at `0x180047063`
- `StateRepository.Core!sqlite3_sql` at `0x180047128`
- `StateRepository.Core!sqlite3_sql` at `0x180047147`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x180047252`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x180047252`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180047110`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180047240`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800472cf`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800472f6`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180047350`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180047110`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180047240`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800472cf`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800472f6`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180047350`

## string_xrefs

- `0x1800471db`: `onecore\base\appmodel\StateRepository\DataAccessLayer\StatementCache.hpp`
- `0x1800471ef`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x18004701a`: `[pre-StatementCache.Get] #%u StatementCache Size/Hits/Misses %u/%llu/%llu`
- `0x180047191`: `[StatementCache.Get(Hit)] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x1800473dd`: `[StatementCache.Get(Miss)] #%u StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`

## pseudocode

```c

```
