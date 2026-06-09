# StateRepository::Database::FailFastIfNestingTransaction(sqlite3 *)

- ea: `0x180018cb4`
- end: `0x180018d0c`
- name: `?FailFastIfNestingTransaction@Database@StateRepository@@CAXPEAUsqlite3@@@Z`
- size: `88`
- prototype: `static void(struct sqlite3 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a0e0`
- `0x18001abec`

## callees

- `0x180014ca0`
- `0x180018cb4`
- `0x18002dc64`

## import_xrefs

- `StateRepository.Core!sqlite3_errmsg` at `0x180018ccb`
- `StateRepository.Core!sqlite3_errmsg` at `0x180018ccb`
- `StateRepository.Core!sqlite3_errcode` at `0x180018cbd`
- `StateRepository.Core!sqlite3_errcode` at `0x180018cbd`

## string_xrefs

- `0x180018cee`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c

```
