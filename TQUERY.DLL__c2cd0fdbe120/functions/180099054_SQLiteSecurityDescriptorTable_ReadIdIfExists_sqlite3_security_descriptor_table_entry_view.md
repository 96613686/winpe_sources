# SQLiteSecurityDescriptorTable::ReadIdIfExists(sqlite3 *,security_descriptor_table_entry_view)

- ea: `0x180099054`
- end: `0x1800991ac`
- name: `?ReadIdIfExists@SQLiteSecurityDescriptorTable@@CA?AV?$optional@H@std@@PEAUsqlite3@@Usecurity_descriptor_table_entry_view@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009dc04`

## callees

- `0x18002a3e0`
- `0x180099054`
- `0x1800996e4`
- `0x18009aac8`
- `0x18009c6ec`
- `0x18009d508`
- `0x18009e21c`
- `0x1800e885c`
- `0x18018128c`
- `0x180189cda`
- `0x18019fdd8`
- `0x1801ad2c0`
- `0x1801ae278`
- `0x1801ae6f0`

## import_xrefs

- `SearchIndexerCore!sqlite3_bind_text64` at `0x1800990bb`
- `SearchIndexerCore!sqlite3_bind_text64` at `0x180099129`
- `SearchIndexerCore!sqlite3_bind_text64` at `0x1800990bb`
- `SearchIndexerCore!sqlite3_bind_text64` at `0x180099129`
- `SearchIndexerCore!sqlite3_bind_null` at `0x1800990e0`
- `SearchIndexerCore!sqlite3_bind_null` at `0x1800990e0`
- `SearchIndexerCore!sqlite3_db_handle` at `0x180099136`
- `SearchIndexerCore!sqlite3_db_handle` at `0x18009915c`
- `SearchIndexerCore!sqlite3_db_handle` at `0x180099136`
- `SearchIndexerCore!sqlite3_db_handle` at `0x18009915c`

## string_xrefs

- `0x180099074`: `SELECT Id from SecurityDescriptor WHERE Value = ? AND EnterpriseIds IS ?;`

## pseudocode

```c

```
