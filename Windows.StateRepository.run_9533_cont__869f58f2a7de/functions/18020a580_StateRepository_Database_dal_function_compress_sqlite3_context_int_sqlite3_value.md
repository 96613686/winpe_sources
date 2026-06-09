# StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x18020a580`
- end: `0x18020a7c0`
- name: `?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `576`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180017a58`
- `0x180062828`
- `0x18018f650`
- `0x180190234`
- `0x180191220`
- `0x18019914d`
- `0x18020a580`

## import_xrefs

- `StateRepository.Core!sqlite3_free` at `0x18020a786`
- `StateRepository.Core!sqlite3_free` at `0x18020a76e`
- `StateRepository.Core!sqlite3_free` at `0x18020a786`
- `StateRepository.Core!sqlite3_result_blob` at `0x18020a77b`
- `StateRepository.Core!sqlite3_result_blob` at `0x18020a77b`
- `StateRepository.Core!sqlite3_malloc` at `0x18020a6d9`
- `StateRepository.Core!sqlite3_malloc` at `0x18020a6d9`
- `StateRepository.Core!sqlite3_value_bytes` at `0x18020a6b4`
- `StateRepository.Core!sqlite3_value_bytes` at `0x18020a6b4`
- `StateRepository.Core!sqlite3_value_blob` at `0x18020a6a7`
- `StateRepository.Core!sqlite3_value_blob` at `0x18020a6a7`
- `StateRepository.Core!sqlite3_value_int` at `0x18020a65c`
- `StateRepository.Core!sqlite3_value_int` at `0x18020a65c`
- `StateRepository.Core!sqlite3_result_error` at `0x18020a64d`
- `StateRepository.Core!sqlite3_result_error` at `0x18020a64d`
- `StateRepository.Core!sqlite3_value_type` at `0x18020a5c7`
- `StateRepository.Core!sqlite3_value_type` at `0x18020a5ee`
- `StateRepository.Core!sqlite3_value_type` at `0x18020a5c7`
- `StateRepository.Core!sqlite3_value_type` at `0x18020a5ee`
- `StateRepository.Core!sqlite3_result_error_code` at `0x18020a793`
- `StateRepository.Core!sqlite3_result_error_code` at `0x18020a793`

## string_xrefs

- `0x18020a62f`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18020a680`: `Compress(x[,level]) error: Invalid level (%d)`
- `0x18020a610`: `Compress(x[,level]) error: Invalid type for level (%d)`

## pseudocode

```c

```
