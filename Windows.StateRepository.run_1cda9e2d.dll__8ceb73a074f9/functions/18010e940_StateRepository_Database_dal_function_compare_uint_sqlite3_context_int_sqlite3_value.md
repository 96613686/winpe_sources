# StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x18010e940`
- end: `0x18010ea9e`
- name: `?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `350`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180017a58`
- `0x180062828`
- `0x18010e940`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `StateRepository.Core!sqlite3_value_int64` at `0x18010e9fe`
- `StateRepository.Core!sqlite3_value_int64` at `0x18010ea59`
- `StateRepository.Core!sqlite3_value_int64` at `0x18010e9fe`
- `StateRepository.Core!sqlite3_value_int64` at `0x18010ea59`
- `StateRepository.Core!sqlite3_result_error` at `0x18010e9f0`
- `StateRepository.Core!sqlite3_result_error` at `0x18010e9f0`
- `StateRepository.Core!sqlite3_value_type` at `0x18010e97f`
- `StateRepository.Core!sqlite3_value_type` at `0x18010ea0b`
- `StateRepository.Core!sqlite3_value_type` at `0x18010e97f`
- `StateRepository.Core!sqlite3_value_type` at `0x18010ea0b`
- `StateRepository.Core!sqlite3_result_int64` at `0x18010ea75`
- `StateRepository.Core!sqlite3_result_int64` at `0x18010ea75`
- `StateRepository.Core!sqlite3_result_error_code` at `0x18010e971`
- `StateRepository.Core!sqlite3_result_error_code` at `0x18010e971`

## string_xrefs

- `0x18010e9d0`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18010ea34`: `Compare_UInt(left,right) error: Invalid type (right=%d)`
- `0x18010e9ac`: `Compare_UInt(left,right) error: Invalid type (left=%d)`

## pseudocode

```c

```
