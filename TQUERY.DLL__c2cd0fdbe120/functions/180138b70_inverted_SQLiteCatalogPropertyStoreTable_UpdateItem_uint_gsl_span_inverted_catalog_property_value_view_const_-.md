# inverted::SQLiteCatalogPropertyStoreTable::UpdateItem(uint,gsl::span<inverted::catalog_property_value_view const,-1>)

- ea: `0x180138b70`
- end: `0x180139032`
- name: `?UpdateItem@SQLiteCatalogPropertyStoreTable@inverted@@UEAA_NIV?$span@$$CBUcatalog_property_value_view@inverted@@$0?0@gsl@@@Z`
- size: `1218`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, installer_update`

## callees

- `0x180097748`
- `0x180097790`
- `0x180097b24`
- `0x180098390`
- `0x180098818`
- `0x1800995d8`
- `0x1800996e4`
- `0x18009995c`
- `0x18009a1a8`
- `0x18009a334`
- `0x18009aac8`
- `0x18009b1bc`
- `0x18009c75c`
- `0x18009ca10`
- `0x18009e1dc`
- `0x18009e2c0`
- `0x18009e6d8`
- `0x180138b70`
- `0x18013e868`
- `0x1801480fc`
- `0x18014a918`
- `0x18014a9e8`
- `0x18015d2fc`
- `0x180188d90`
- `0x180189cda`
- `0x18018f47c`
- `0x18018f49c`
- `0x18019f874`
- `0x1801a7d60`
- `0x1801ae620`
- `0x18023087c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180138fd2`
- `msvcp_win!_Mtx_unlock` at `0x180138fd2`
- `SearchIndexerCore!sqlite3_changes` at `0x180138ed9`
- `SearchIndexerCore!sqlite3_changes` at `0x180138f43`
- `SearchIndexerCore!sqlite3_changes` at `0x180138ed9`
- `SearchIndexerCore!sqlite3_changes` at `0x180138f43`
- `SearchIndexerCore!sqlite3_db_filename` at `0x180138c32`
- `SearchIndexerCore!sqlite3_db_filename` at `0x180138c32`

## string_xrefs

- `0x180138d04`: `DELETE FROM `
- `0x180139011`: `Failed to insert or update the value in the property store.`
- `0x180138df8`: ` (WorkId, ColumnId, Value) VALUES (?, ?, ?) ON CONFLICT(WorkId, ColumnId) DO UPDATE SET Value = excluded.Value;`

## pseudocode

```c

```
