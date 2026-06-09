# Windows::UsoDatabase::SetUpdateProperty(UpdateIdentity const &,wil::basic_zstring_view<wchar_t>,std::variant<bool,long,uint,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &)

- ea: `0x140192d40`
- end: `0x140192f53`
- name: `?SetUpdateProperty@UsoDatabase@Windows@@UEAAXAEBUUpdateIdentity@@V?$basic_zstring_view@_W@wil@@AEBV?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140192ad8`
- `0x140192d40`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140192ddd`
- `winsqlite3!sqlite3_bind_text16` at `0x140192e1e`
- `winsqlite3!sqlite3_bind_text16` at `0x140192e54`
- `winsqlite3!sqlite3_bind_text16` at `0x140192ddd`
- `winsqlite3!sqlite3_bind_text16` at `0x140192e1e`
- `winsqlite3!sqlite3_bind_text16` at `0x140192e54`
- `winsqlite3!sqlite3_bind_int` at `0x140192e9a`
- `winsqlite3!sqlite3_bind_int` at `0x140192e9a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140192d97`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140192d97`
- `winsqlite3!sqlite3_finalize` at `0x140192ed6`
- `winsqlite3!sqlite3_finalize` at `0x140192ed6`

## string_xrefs

- `0x140192d8c`: `INSERT OR REPLACE INTO UPDATESPROP (PROVIDERID, UPDATEID, VARIABLE, VALUE, TYPE) VALUES (?, ?, ?, ?, ?)`

## pseudocode

```c

```
