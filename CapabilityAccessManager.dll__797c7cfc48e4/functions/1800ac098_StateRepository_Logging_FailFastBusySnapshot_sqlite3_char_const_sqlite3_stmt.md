# StateRepository::Logging::FailFastBusySnapshot(sqlite3 *,char const *,sqlite3_stmt *)

- ea: `0x1800ac098`
- end: `0x1800ac2de`
- name: `?FailFastBusySnapshot@Logging@StateRepository@@YAXPEAUsqlite3@@PEBDPEAUsqlite3_stmt@@@Z`
- size: `582`
- prototype: `void __fastcall(StateRepository::Logging *__hidden this, struct sqlite3 *, const char *, struct sqlite3_stmt *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a32d4`
- `0x1800a6a00`
- `0x1800a8bd8`

## callees

- `0x18000186c`
- `0x1800062cc`
- `0x1800210d4`
- `0x1800a1610`
- `0x1800ac098`
- `0x1800ac500`
- `0x1800ac590`
- `0x1800ac654`
- `0x1800ad120`

## import_xrefs

- `winsqlite3!sqlite3_next_stmt` at `0x1800ac0e3`
- `winsqlite3!sqlite3_next_stmt` at `0x1800ac10c`
- `winsqlite3!sqlite3_next_stmt` at `0x1800ac0e3`
- `winsqlite3!sqlite3_next_stmt` at `0x1800ac10c`

## string_xrefs

- `0x1800ac13d`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c

```
