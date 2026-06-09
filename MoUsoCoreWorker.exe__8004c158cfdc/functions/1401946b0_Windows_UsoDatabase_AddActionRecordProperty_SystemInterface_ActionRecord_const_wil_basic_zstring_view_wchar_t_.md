# Windows::UsoDatabase::AddActionRecordProperty(SystemInterface::ActionRecord const &,wil::basic_zstring_view<wchar_t>,std::variant<bool,long,uint,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &)

- ea: `0x1401946b0`
- end: `0x14019498f`
- name: `?AddActionRecordProperty@UsoDatabase@Windows@@UEAAXAEBUActionRecord@SystemInterface@@V?$basic_zstring_view@_W@wil@@AEBV?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z`
- size: `735`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400c6f6c`
- `0x14018d1a4`
- `0x140192ad8`
- `0x1401946b0`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x14019474e`
- `winsqlite3!sqlite3_bind_text16` at `0x140194791`
- `winsqlite3!sqlite3_bind_text16` at `0x140194819`
- `winsqlite3!sqlite3_bind_text16` at `0x14019485b`
- `winsqlite3!sqlite3_bind_text16` at `0x14019474e`
- `winsqlite3!sqlite3_bind_text16` at `0x140194791`
- `winsqlite3!sqlite3_bind_text16` at `0x140194819`
- `winsqlite3!sqlite3_bind_text16` at `0x14019485b`
- `winsqlite3!sqlite3_bind_int` at `0x14019489e`
- `winsqlite3!sqlite3_bind_int` at `0x14019489e`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019470c`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019470c`
- `winsqlite3!sqlite3_finalize` at `0x1401948d7`
- `winsqlite3!sqlite3_finalize` at `0x1401948d7`

## string_xrefs

- `0x140194701`: `INSERT OR REPLACE INTO ACTIONRECORDSPROP (PROVIDERID, UPDATEID, TIME, VARIABLE, VALUE, TYPE) VALUES (?, ?, ?, ?, ?, ?)`

## pseudocode

```c

```
