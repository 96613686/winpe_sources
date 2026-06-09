# StateRepository::Statement::GetColumnBlob(int,void const * *)

- ea: `0x18001ba84`
- end: `0x18001bb08`
- name: `?GetColumnBlob@Statement@StateRepository@@QEBAJHPEAPEBX@Z`
- size: `132`
- prototype: `__int64 __fastcall(StateRepository::Statement *__hidden this, int, const void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b9d4`

## callees

- `0x180014ca0`
- `0x18001ba84`
- `0x18001bfc4`

## import_xrefs

- `StateRepository.Core!sqlite3_errcode` at `0x18001bad6`
- `StateRepository.Core!sqlite3_errcode` at `0x18001bad6`
- `StateRepository.Core!sqlite3_column_blob` at `0x18001babd`
- `StateRepository.Core!sqlite3_column_blob` at `0x18001babd`

## string_xrefs

- `0x18001baa2`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c

```
