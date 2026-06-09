# Windows::UsoDatabase::DeleteProviderProperty(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x140193b50`
- end: `0x140193ca6`
- name: `?DeleteProviderProperty@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140193b50`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140193bd8`
- `winsqlite3!sqlite3_bind_text16` at `0x140193c10`
- `winsqlite3!sqlite3_bind_text16` at `0x140193bd8`
- `winsqlite3!sqlite3_bind_text16` at `0x140193c10`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140193ba0`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140193ba0`
- `winsqlite3!sqlite3_finalize` at `0x140193c4f`
- `winsqlite3!sqlite3_finalize` at `0x140193c4f`

## string_xrefs

- `0x140193b96`: `DELETE FROM PROVIDERSPROP WHERE PROVIDERID = ? AND VARIABLE = ?`

## pseudocode

```c

```
