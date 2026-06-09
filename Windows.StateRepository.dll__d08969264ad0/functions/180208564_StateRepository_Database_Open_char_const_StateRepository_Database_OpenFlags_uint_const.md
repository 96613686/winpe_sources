# StateRepository::Database::Open(char const *,StateRepository::Database::OpenFlags,uint const *)

- ea: `0x180208564`
- end: `0x1802088e1`
- name: `?Open@Database@StateRepository@@QEAAJPEBDW4OpenFlags@12@PEBI@Z`
- size: `893`
- prototype: `__int64 __fastcall(StateRepository::Database *, __int64, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `20`
- tags: ``

## callers

- `0x180053ff0`
- `0x180054a9c`

## callees

- `0x180017a58`
- `0x180017a88`
- `0x18001843c`
- `0x18001a9e0`
- `0x180064c44`
- `0x180064d30`
- `0x180068c44`
- `0x180086750`
- `0x1800871d0`
- `0x180089390`
- `0x180131444`
- `0x180207e08`
- `0x180207e60`
- `0x180208564`
- `0x1802088e8`
- `0x180208974`
- `0x1802089d4`
- `0x180208a90`
- `0x180208b0c`
- `0x1802093d0`

## import_xrefs

- `StateRepository.Core!sqlite3_log` at `0x180208650`
- `StateRepository.Core!sqlite3_log` at `0x180208650`
- `StateRepository.Core!sqlite3_close` at `0x1802086a5`
- `StateRepository.Core!sqlite3_close` at `0x1802086a5`
- `StateRepository.Core!sqlite3_errmsg` at `0x1802085f4`
- `StateRepository.Core!sqlite3_errmsg` at `0x1802085f4`
- `StateRepository.Core!sqlite3_open_v2` at `0x1802085be`
- `StateRepository.Core!sqlite3_open_v2` at `0x1802085be`
- `StateRepository.Core!sqlite3_extended_errcode` at `0x1802085df`
- `StateRepository.Core!sqlite3_extended_errcode` at `0x1802085df`
- `StateRepository.Core!sqlite3_file_control` at `0x18020861d`
- `StateRepository.Core!sqlite3_file_control` at `0x18020861d`
- `StateRepository.Core!sqlite3_extended_result_codes` at `0x18020871c`
- `StateRepository.Core!sqlite3_extended_result_codes` at `0x18020871c`

## string_xrefs

- `0x180208588`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180208683`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1802086f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180208639`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s`
- `0x180208814`: `temp_store`
- `0x180208691`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs`

## pseudocode

```c

```
