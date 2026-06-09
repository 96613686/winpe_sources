# sqlite3_database_creator::get_encryption_status_for_db(sqlite3 *)

- ea: `0x1801abaa4`
- end: `0x1801abb8f`
- name: `?get_encryption_status_for_db@sqlite3_database_creator@@CA?AW4EncryptionStatus@1@PEAUsqlite3@@@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1801ac190`

## callees

- `0x1800996e4`
- `0x18009ab50`
- `0x1801480fc`
- `0x1801484b0`
- `0x180189cda`
- `0x1801abaa4`
- `0x1801ac040`

## import_xrefs

- `SearchIndexerCore!sqlite3_column_int` at `0x1801abafc`
- `SearchIndexerCore!sqlite3_column_int` at `0x1801abafc`
- `SearchIndexerCore!sqlite3_step` at `0x1801abaea`
- `SearchIndexerCore!sqlite3_step` at `0x1801abaea`
- `SearchIndexerCore!sqlite3_errmsg` at `0x1801abb37`
- `SearchIndexerCore!sqlite3_errmsg` at `0x1801abb37`
- `SearchIndexerCore!sqlite3_extended_errcode` at `0x1801abb43`
- `SearchIndexerCore!sqlite3_extended_errcode` at `0x1801abb43`

## string_xrefs

- `0x1801abb69`: `failed to read database`
- `0x1801abb51`: `Failed to read database with error code %d: %s`

## pseudocode

```c

```
