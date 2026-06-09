# StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800d60e0`
- end: `0x1800d623e`
- name: `?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `350`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180084210`
- `0x1800a219c`
- `0x1800d60e0`
- `0x1800f0260`
- `0x1800f10e4`

## import_xrefs

- `StateRepository.Core!sqlite3_value_int64` at `0x1800d619e`
- `StateRepository.Core!sqlite3_value_int64` at `0x1800d61f9`
- `StateRepository.Core!sqlite3_value_int64` at `0x1800d619e`
- `StateRepository.Core!sqlite3_value_int64` at `0x1800d61f9`
- `StateRepository.Core!sqlite3_result_error_code` at `0x1800d6111`
- `StateRepository.Core!sqlite3_result_error_code` at `0x1800d6111`
- `StateRepository.Core!sqlite3_result_int64` at `0x1800d6215`
- `StateRepository.Core!sqlite3_result_int64` at `0x1800d6215`
- `StateRepository.Core!sqlite3_value_type` at `0x1800d611f`
- `StateRepository.Core!sqlite3_value_type` at `0x1800d61ab`
- `StateRepository.Core!sqlite3_value_type` at `0x1800d611f`
- `StateRepository.Core!sqlite3_value_type` at `0x1800d61ab`
- `StateRepository.Core!sqlite3_result_error` at `0x1800d6190`
- `StateRepository.Core!sqlite3_result_error` at `0x1800d6190`

## string_xrefs

- `0x1800d6170`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800d61d4`: `Compare_UInt(left,right) error: Invalid type (right=%d)`
- `0x1800d614c`: `Compare_UInt(left,right) error: Invalid type (left=%d)`

## pseudocode

```c

```
