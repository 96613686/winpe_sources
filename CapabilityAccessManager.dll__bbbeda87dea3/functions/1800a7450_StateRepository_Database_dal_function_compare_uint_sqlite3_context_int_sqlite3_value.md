# StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800a7450`
- end: `0x1800a75ae`
- name: `?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `350`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x1800210d4`
- `0x1800a626c`
- `0x1800a7450`

## import_xrefs

- `winsqlite3!sqlite3_result_int64` at `0x1800a7585`
- `winsqlite3!sqlite3_result_int64` at `0x1800a7585`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7481`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7481`
- `winsqlite3!sqlite3_value_type` at `0x1800a748f`
- `winsqlite3!sqlite3_value_type` at `0x1800a751b`
- `winsqlite3!sqlite3_value_type` at `0x1800a748f`
- `winsqlite3!sqlite3_value_type` at `0x1800a751b`
- `winsqlite3!sqlite3_result_error` at `0x1800a7500`
- `winsqlite3!sqlite3_result_error` at `0x1800a7500`
- `winsqlite3!sqlite3_value_int64` at `0x1800a750e`
- `winsqlite3!sqlite3_value_int64` at `0x1800a7569`
- `winsqlite3!sqlite3_value_int64` at `0x1800a750e`
- `winsqlite3!sqlite3_value_int64` at `0x1800a7569`

## string_xrefs

- `0x1800a74e0`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a7544`: `Compare_UInt(left,right) error: Invalid type (right=%d)`
- `0x1800a74bc`: `Compare_UInt(left,right) error: Invalid type (left=%d)`

## pseudocode

```c

```
