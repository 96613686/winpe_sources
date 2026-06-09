# StateRepository::Logging::FailFastBusySnapshot(sqlite3 *,char const *,sqlite3_stmt *)

- ea: `0x18002650c`
- end: `0x18002675e`
- name: `?FailFastBusySnapshot@Logging@StateRepository@@YAXPEAUsqlite3@@PEBDPEAUsqlite3_stmt@@@Z`
- size: `594`
- prototype: `void __fastcall(StateRepository::Logging *__hidden this, struct sqlite3 *, const char *, struct sqlite3_stmt *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18001a0e0`
- `0x18001abec`
- `0x18001c314`

## callees

- `0x180001aac`
- `0x180002c24`
- `0x18000baf4`
- `0x18000c3bc`
- `0x18002650c`
- `0x180027220`
- `0x1800272b0`
- `0x180027374`
- `0x180028530`

## import_xrefs

- `StateRepository.Core!sqlite3_next_stmt` at `0x180026555`
- `StateRepository.Core!sqlite3_next_stmt` at `0x180026581`
- `StateRepository.Core!sqlite3_next_stmt` at `0x180026555`
- `StateRepository.Core!sqlite3_next_stmt` at `0x180026581`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800265ac`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800265ac`

## string_xrefs

- `0x1800265b6`: `onecore\base\appmodel\staterepository\dataaccesslayer\logging.cpp`

## pseudocode

```c

```
