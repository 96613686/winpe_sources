# StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800a75c0`
- end: `0x1800a7800`
- name: `?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `576`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x18000d835`
- `0x18000d850`
- `0x1800210d4`
- `0x1800a626c`
- `0x1800a75c0`

## import_xrefs

- `winsqlite3!sqlite3_result_error_code` at `0x1800a77d3`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a77d3`
- `winsqlite3!sqlite3_value_type` at `0x1800a7607`
- `winsqlite3!sqlite3_value_type` at `0x1800a762e`
- `winsqlite3!sqlite3_value_type` at `0x1800a7607`
- `winsqlite3!sqlite3_value_type` at `0x1800a762e`
- `winsqlite3!sqlite3_result_error` at `0x1800a768d`
- `winsqlite3!sqlite3_result_error` at `0x1800a768d`
- `winsqlite3!sqlite3_value_int` at `0x1800a769c`
- `winsqlite3!sqlite3_value_int` at `0x1800a769c`
- `winsqlite3!sqlite3_value_blob` at `0x1800a76e7`
- `winsqlite3!sqlite3_value_blob` at `0x1800a76e7`
- `winsqlite3!sqlite3_value_bytes` at `0x1800a76f4`
- `winsqlite3!sqlite3_value_bytes` at `0x1800a76f4`
- `winsqlite3!sqlite3_malloc` at `0x1800a7719`
- `winsqlite3!sqlite3_malloc` at `0x1800a7719`
- `winsqlite3!sqlite3_result_blob` at `0x1800a77bb`
- `winsqlite3!sqlite3_result_blob` at `0x1800a77bb`
- `winsqlite3!sqlite3_free` at `0x1800a77c6`
- `winsqlite3!sqlite3_free` at `0x1800a77ae`
- `winsqlite3!sqlite3_free` at `0x1800a77c6`

## string_xrefs

- `0x1800a766f`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a76c0`: `Compress(x[,level]) error: Invalid level (%d)`
- `0x1800a7650`: `Compress(x[,level]) error: Invalid type for level (%d)`

## pseudocode

```c

```
