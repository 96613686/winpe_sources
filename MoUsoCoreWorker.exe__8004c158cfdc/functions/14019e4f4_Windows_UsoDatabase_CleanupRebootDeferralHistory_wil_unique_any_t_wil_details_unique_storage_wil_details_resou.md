# Windows::UsoDatabase::CleanupRebootDeferralHistory(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &)

- ea: `0x14019e4f4`
- end: `0x14019e710`
- name: `?CleanupRebootDeferralHistory@UsoDatabase@Windows@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x14018db34`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x14018d1a4`
- `0x14019e4f4`
- `0x1401a271c`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019e525`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019e525`
- `winsqlite3!sqlite3_bind_int` at `0x14019e5b5`
- `winsqlite3!sqlite3_bind_int` at `0x14019e63f`
- `winsqlite3!sqlite3_bind_int` at `0x14019e5b5`
- `winsqlite3!sqlite3_bind_int` at `0x14019e63f`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e57e`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e60e`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e57e`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e60e`
- `winsqlite3!sqlite3_finalize` at `0x14019e67e`
- `winsqlite3!sqlite3_finalize` at `0x14019e68f`
- `winsqlite3!sqlite3_finalize` at `0x14019e67e`
- `winsqlite3!sqlite3_finalize` at `0x14019e68f`

## string_xrefs

- `0x14019e577`: `DELETE FROM REBOOTDEFERRALHISTORY WHERE ROWID IN (    SELECT ROWID     FROM REBOOTDEFERRALHISTORY     ORDER BY CAST(DATETIMECHECKED AS INTEGER) DESC     LIMIT -1 OFFSET ?);`
- `0x14019e604`: `DELETE FROM REBOOTDEFERRALHISTORYSTATUS WHERE ROWID IN (    SELECT ROWID     FROM REBOOTDEFERRALHISTORYSTATUS     ORDER BY CAST(REBOOTATTEMPTTIMESTAMP AS INTEGER) DESC     LIMIT -1 OFFSET ?);`

## pseudocode

```c

```
