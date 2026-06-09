# StateRepository::Logging::_FailFastBusySnapshot_Statement(sqlite3 *,sqlite3_stmt *,uint,char const * &,uint &)

- ea: `0x180028530`
- end: `0x1800287eb`
- name: `?_FailFastBusySnapshot_Statement@Logging@StateRepository@@YAXPEAUsqlite3@@PEAUsqlite3_stmt@@IAEAPEBDAEAI@Z`
- size: `699`
- prototype: `void __fastcall(StateRepository::Logging *__hidden this, struct sqlite3 *, struct sqlite3_stmt *, unsigned int, const char **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18002650c`

## callees

- `0x180001aac`
- `0x180002d3c`
- `0x180003980`
- `0x1800042f4`
- `0x18000a7c0`
- `0x18000baf4`
- `0x18000c3bc`
- `0x18001b0c8`
- `0x180027220`
- `0x1800272b0`
- `0x180027374`
- `0x180028530`

## import_xrefs

- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800285b3`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800285b3`
- `StateRepository.Core!sqlite3_expanded_sql` at `0x180028588`
- `StateRepository.Core!sqlite3_expanded_sql` at `0x180028588`
- `StateRepository.Core!sqlite3_sql` at `0x18002857c`
- `StateRepository.Core!sqlite3_sql` at `0x18002857c`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x180028568`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x180028568`

## string_xrefs

- `0x1800285c9`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c

```
