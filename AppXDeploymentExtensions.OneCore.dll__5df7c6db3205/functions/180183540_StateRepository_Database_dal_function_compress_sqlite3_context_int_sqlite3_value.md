# StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x180183540`
- end: `0x180183780`
- name: `?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `576`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180084210`
- `0x1800a219c`
- `0x1800f0260`
- `0x1800f10e4`
- `0x1800f3790`
- `0x1800fc211`
- `0x180183540`

## import_xrefs

- `StateRepository.Core!sqlite3_free` at `0x180183746`
- `StateRepository.Core!sqlite3_free` at `0x18018372e`
- `StateRepository.Core!sqlite3_free` at `0x180183746`
- `StateRepository.Core!sqlite3_result_blob` at `0x18018373b`
- `StateRepository.Core!sqlite3_result_blob` at `0x18018373b`
- `StateRepository.Core!sqlite3_malloc` at `0x180183699`
- `StateRepository.Core!sqlite3_malloc` at `0x180183699`
- `StateRepository.Core!sqlite3_value_bytes` at `0x180183674`
- `StateRepository.Core!sqlite3_value_bytes` at `0x180183674`
- `StateRepository.Core!sqlite3_result_error_code` at `0x180183753`
- `StateRepository.Core!sqlite3_result_error_code` at `0x180183753`
- `StateRepository.Core!sqlite3_value_blob` at `0x180183667`
- `StateRepository.Core!sqlite3_value_blob` at `0x180183667`
- `StateRepository.Core!sqlite3_value_type` at `0x180183587`
- `StateRepository.Core!sqlite3_value_type` at `0x1801835ae`
- `StateRepository.Core!sqlite3_value_type` at `0x180183587`
- `StateRepository.Core!sqlite3_value_type` at `0x1801835ae`
- `StateRepository.Core!sqlite3_result_error` at `0x18018360d`
- `StateRepository.Core!sqlite3_result_error` at `0x18018360d`
- `StateRepository.Core!sqlite3_value_int` at `0x18018361c`
- `StateRepository.Core!sqlite3_value_int` at `0x18018361c`

## string_xrefs

- `0x1801835ef`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1801835d0`: `Compress(x[,level]) error: Invalid type for level (%d)`
- `0x180183640`: `Compress(x[,level]) error: Invalid level (%d)`

## pseudocode

```c

```
