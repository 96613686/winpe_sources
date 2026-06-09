# sqlite3_database_creator::read_probe(sqlite3 *)

- ea: `0x180177108`
- end: `0x180177252`
- name: `?read_probe@sqlite3_database_creator@@CA_NPEAUsqlite3@@@Z`
- size: `330`
- prototype: `bool __fastcall(struct sqlite3 *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x1801758f4`
- `0x180176f34`
- `0x180215640`

## callees

- `0x18004e5d8`
- `0x180083e54`
- `0x1800859f8`
- `0x180085de0`
- `0x180085ea0`
- `0x1800865e8`
- `0x1800fd618`
- `0x1801244c0`
- `0x18012541a`
- `0x1801719d0`
- `0x180177108`

## import_xrefs

- `SearchIndexerCore!sqlite3_free` at `0x1801771b7`
- `SearchIndexerCore!sqlite3_free` at `0x1801771b7`
- `SearchIndexerCore!sqlite3_extended_errcode` at `0x180177208`
- `SearchIndexerCore!sqlite3_extended_errcode` at `0x180177208`
- `SearchIndexerCore!sqlite3_errmsg` at `0x1801771fc`
- `SearchIndexerCore!sqlite3_errmsg` at `0x1801771fc`
- `SearchIndexerCore!sqlite3_step` at `0x18017716e`
- `SearchIndexerCore!sqlite3_step` at `0x18017716e`
- `SearchIndexerCore!sqlite3_malloc` at `0x1801771a9`
- `SearchIndexerCore!sqlite3_malloc` at `0x1801771a9`

## string_xrefs

- `0x18017722e`: `failed to read database`
- `0x180177216`: `Failed to read database with error code %d: %s`

## pseudocode

```c

```
