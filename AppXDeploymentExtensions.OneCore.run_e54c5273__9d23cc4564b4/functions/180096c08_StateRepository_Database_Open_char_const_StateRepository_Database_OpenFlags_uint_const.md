# StateRepository::Database::Open(char const *,StateRepository::Database::OpenFlags,uint const *)

- ea: `0x180096c08`
- end: `0x180096f57`
- name: `?Open@Database@StateRepository@@QEAAJPEBDW4OpenFlags@12@PEBI@Z`
- size: `847`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x1800a50a4`

## callees

- `0x18008c3d8`
- `0x18008c514`
- `0x180096c08`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a4e88`
- `0x1800accc0`
- `0x1800c2950`
- `0x1800c9a3c`
- `0x1800da5d4`
- `0x1800e0620`
- `0x1800e8ec8`
- `0x180181b24`
- `0x180181b7c`
- `0x1801821ac`
- `0x180182238`
- `0x180182298`
- `0x180182354`
- `0x1801823d0`

## import_xrefs

- `StateRepository.Core!sqlite3_errmsg` at `0x180096c99`
- `StateRepository.Core!sqlite3_errmsg` at `0x180096c99`
- `StateRepository.Core!sqlite3_close` at `0x180096d56`
- `StateRepository.Core!sqlite3_close` at `0x180096d56`
- `StateRepository.Core!sqlite3_log` at `0x180096cfe`
- `StateRepository.Core!sqlite3_log` at `0x180096cfe`
- `StateRepository.Core!sqlite3_open_v2` at `0x180096c63`
- `StateRepository.Core!sqlite3_open_v2` at `0x180096c63`
- `StateRepository.Core!sqlite3_extended_errcode` at `0x180096c84`
- `StateRepository.Core!sqlite3_extended_errcode` at `0x180096c84`
- `StateRepository.Core!sqlite3_file_control` at `0x180096cc8`
- `StateRepository.Core!sqlite3_file_control` at `0x180096cc8`
- `StateRepository.Core!sqlite3_extended_result_codes` at `0x180096dcd`
- `StateRepository.Core!sqlite3_extended_result_codes` at `0x180096dcd`

## string_xrefs

- `0x180096c2d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180096d34`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180096da2`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180096e8a`: `temp_store`
- `0x180096ce7`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %s`
- `0x180096d42`: `[sqlite3_open: lastErrNo:0x%X filecontrolrc:%d] #%u : %hs`

## pseudocode

```c

```
