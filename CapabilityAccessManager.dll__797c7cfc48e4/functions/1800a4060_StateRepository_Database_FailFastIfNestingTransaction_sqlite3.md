# StateRepository::Database::FailFastIfNestingTransaction(sqlite3 *)

- ea: `0x1800a4060`
- end: `0x1800a40b8`
- name: `?FailFastIfNestingTransaction@Database@StateRepository@@CAXPEAUsqlite3@@@Z`
- size: `88`
- prototype: `static void(struct sqlite3 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a6a00`
- `0x1800a8bd8`

## callees

- `0x180021074`
- `0x1800a4060`
- `0x1800ba224`

## import_xrefs

- `winsqlite3!sqlite3_errmsg` at `0x1800a4077`
- `winsqlite3!sqlite3_errmsg` at `0x1800a4077`
- `winsqlite3!sqlite3_errcode` at `0x1800a4069`
- `winsqlite3!sqlite3_errcode` at `0x1800a4069`

## string_xrefs

- `0x1800a409a`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c

```
