# StateRepository::Logging::_FailFastBusySnapshot_Statement(sqlite3 *,sqlite3_stmt *,uint,char const * &,uint &)

- ea: `0x18012a9f0`
- end: `0x18012acc4`
- name: `?_FailFastBusySnapshot_Statement@Logging@StateRepository@@YAXPEAUsqlite3@@PEAUsqlite3_stmt@@IAEAPEBDAEAI@Z`
- size: `724`
- prototype: `void __fastcall(StateRepository::Logging *__hidden this, struct sqlite3 *, struct sqlite3_stmt *, unsigned int, const char **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18012951c`

## callees

- `0x180003448`
- `0x180012fc8`
- `0x180015590`
- `0x180059570`
- `0x1800ab918`
- `0x1800aed10`
- `0x1800af918`
- `0x1801273f8`
- `0x180129918`
- `0x1801299ac`
- `0x180129a60`
- `0x18012a9f0`

## import_xrefs

- `StateRepository.Core!sqlite3_sql` at `0x18012aa42`
- `StateRepository.Core!sqlite3_sql` at `0x18012aa42`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18012aa28`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18012aa28`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18012aa85`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18012aa85`
- `StateRepository.Core!sqlite3_expanded_sql` at `0x18012aa54`
- `StateRepository.Core!sqlite3_expanded_sql` at `0x18012aa54`

## string_xrefs

- `0x18012aaa1`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c

```
