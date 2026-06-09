# Windows::Compat::Inventory::SqliteInvCacheItem::SqliteInvCacheItem(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<IAmiInventoryItem::_CacheItemProperty,std::allocator<IAmiInventoryItem::_CacheItemProperty>> const &,sqlite3_stmt *,sqlite3_stmt *)

- ea: `0x18009ccf8`
- end: `0x18009cf4f`
- name: `??0SqliteInvCacheItem@Inventory@Compat@Windows@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@5@PEAUsqlite3_stmt@@2@Z`
- size: `599`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18009cf58`
- `0x18009e360`

## callees

- `0x180012920`
- `0x180018348`
- `0x180018768`
- `0x1800189e4`
- `0x180019210`
- `0x180056256`
- `0x18009cb6c`
- `0x18009ccf8`
- `0x18009d058`
- `0x1800a684c`
- `0x1800a693c`
- `0x1800a6d94`

## import_xrefs

- `winsqlite3!sqlite3_column_int` at `0x18009cf03`
- `winsqlite3!sqlite3_column_int` at `0x18009cf03`
- `winsqlite3!sqlite3_column_blob` at `0x18009ce88`
- `winsqlite3!sqlite3_column_blob` at `0x18009ce88`
- `winsqlite3!sqlite3_column_bytes` at `0x18009ce33`
- `winsqlite3!sqlite3_column_bytes` at `0x18009ce79`
- `winsqlite3!sqlite3_column_bytes` at `0x18009ce33`
- `winsqlite3!sqlite3_column_bytes` at `0x18009ce79`
- `winsqlite3!sqlite3_column_int64` at `0x18009cee4`
- `winsqlite3!sqlite3_column_int64` at `0x18009cee4`
- `winsqlite3!sqlite3_column_text16` at `0x18009cd86`
- `winsqlite3!sqlite3_column_text16` at `0x18009ceab`
- `winsqlite3!sqlite3_column_text16` at `0x18009cd86`
- `winsqlite3!sqlite3_column_text16` at `0x18009ceab`

## string_xrefs

- `0x18009cdfd`: `Unsupported CacheItemPropertyType '%d' for column %d in SqliteInvCacheItem.`
- `0x18009ce0a`: `Windows::Compat::Inventory::SqliteInvCacheItem::SqliteInvCacheItem`

## pseudocode

```c

```
