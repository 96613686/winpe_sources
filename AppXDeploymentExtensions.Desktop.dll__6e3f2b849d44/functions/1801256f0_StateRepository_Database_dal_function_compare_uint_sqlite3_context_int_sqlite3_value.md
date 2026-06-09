# StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1801256f0`
- end: `0x180125879`
- name: `?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `393`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180012fc8`
- `0x1800a3a94`
- `0x1800aed10`
- `0x1800af918`
- `0x1801256f0`

## import_xrefs

- `StateRepository.Core!sqlite3_result_error_code` at `0x180125721`
- `StateRepository.Core!sqlite3_result_error_code` at `0x180125721`
- `StateRepository.Core!sqlite3_result_int64` at `0x180125849`
- `StateRepository.Core!sqlite3_result_int64` at `0x180125849`
- `StateRepository.Core!sqlite3_value_type` at `0x180125735`
- `StateRepository.Core!sqlite3_value_type` at `0x1801257d3`
- `StateRepository.Core!sqlite3_value_type` at `0x180125735`
- `StateRepository.Core!sqlite3_value_type` at `0x1801257d3`
- `StateRepository.Core!sqlite3_result_error` at `0x1801257ac`
- `StateRepository.Core!sqlite3_result_error` at `0x1801257ac`
- `StateRepository.Core!sqlite3_value_int64` at `0x1801257c0`
- `StateRepository.Core!sqlite3_value_int64` at `0x180125827`
- `StateRepository.Core!sqlite3_value_int64` at `0x1801257c0`
- `StateRepository.Core!sqlite3_value_int64` at `0x180125827`

## string_xrefs

- `0x18012578c`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180125802`: `Compare_UInt(left,right) error: Invalid type (right=%d)`
- `0x180125768`: `Compare_UInt(left,right) error: Invalid type (left=%d)`

## pseudocode

```c

```
