# Windows::UsoDatabase::SetProviderProperty(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::variant<bool,long,uint,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &)

- ea: `0x140193770`
- end: `0x14019391e`
- name: `?SetProviderProperty@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0AEBV?$variant@_NJI_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@Z`
- size: `430`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140192ad8`
- `0x140193770`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140193801`
- `winsqlite3!sqlite3_bind_text16` at `0x140193835`
- `winsqlite3!sqlite3_bind_text16` at `0x140193801`
- `winsqlite3!sqlite3_bind_text16` at `0x140193835`
- `winsqlite3!sqlite3_bind_int` at `0x140193877`
- `winsqlite3!sqlite3_bind_int` at `0x140193877`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401937c7`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401937c7`
- `winsqlite3!sqlite3_finalize` at `0x1401938b3`
- `winsqlite3!sqlite3_finalize` at `0x1401938b3`

## string_xrefs

- `0x1401937bc`: `INSERT OR REPLACE INTO PROVIDERSPROP (PROVIDERID, VARIABLE, VALUE, TYPE) VALUES (?, ?, ?, ?)`

## pseudocode

```c

```
