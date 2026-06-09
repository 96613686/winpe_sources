# StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x180125880`
- end: `0x180125afd`
- name: `?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `637`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180012fc8`
- `0x1800a3a94`
- `0x1800aed10`
- `0x1800af918`
- `0x1800b1120`
- `0x1800ba45d`
- `0x180125880`

## import_xrefs

- `StateRepository.Core!sqlite3_result_error_code` at `0x180125ac9`
- `StateRepository.Core!sqlite3_result_error_code` at `0x180125ac9`
- `StateRepository.Core!sqlite3_value_type` at `0x1801258c7`
- `StateRepository.Core!sqlite3_value_type` at `0x1801258f4`
- `StateRepository.Core!sqlite3_value_type` at `0x1801258c7`
- `StateRepository.Core!sqlite3_value_type` at `0x1801258f4`
- `StateRepository.Core!sqlite3_result_error` at `0x180125959`
- `StateRepository.Core!sqlite3_result_error` at `0x180125959`
- `StateRepository.Core!sqlite3_value_int` at `0x18012596e`
- `StateRepository.Core!sqlite3_value_int` at `0x18012596e`
- `StateRepository.Core!sqlite3_value_blob` at `0x1801259bf`
- `StateRepository.Core!sqlite3_value_blob` at `0x1801259bf`
- `StateRepository.Core!sqlite3_value_bytes` at `0x1801259d2`
- `StateRepository.Core!sqlite3_value_bytes` at `0x1801259d2`
- `StateRepository.Core!sqlite3_malloc` at `0x1801259fd`
- `StateRepository.Core!sqlite3_malloc` at `0x1801259fd`
- `StateRepository.Core!sqlite3_result_blob` at `0x180125aa5`
- `StateRepository.Core!sqlite3_result_blob` at `0x180125aa5`
- `StateRepository.Core!sqlite3_free` at `0x180125ab6`
- `StateRepository.Core!sqlite3_free` at `0x180125a98`
- `StateRepository.Core!sqlite3_free` at `0x180125ab6`

## string_xrefs

- `0x18012593b`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180125998`: `Compress(x[,level]) error: Invalid level (%d)`
- `0x18012591c`: `Compress(x[,level]) error: Invalid type for level (%d)`

## pseudocode

```c

```
