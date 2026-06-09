# Windows::UsoDatabase::DeleteUpdateProperty(UpdateIdentity const &,wil::basic_zstring_view<wchar_t>)

- ea: `0x140193290`
- end: `0x14019343f`
- name: `?DeleteUpdateProperty@UsoDatabase@Windows@@UEAAXAEBUUpdateIdentity@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140193290`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140193326`
- `winsqlite3!sqlite3_bind_text16` at `0x140193367`
- `winsqlite3!sqlite3_bind_text16` at `0x14019339d`
- `winsqlite3!sqlite3_bind_text16` at `0x140193326`
- `winsqlite3!sqlite3_bind_text16` at `0x140193367`
- `winsqlite3!sqlite3_bind_text16` at `0x14019339d`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401932e0`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401932e0`
- `winsqlite3!sqlite3_finalize` at `0x1401933d8`
- `winsqlite3!sqlite3_finalize` at `0x1401933d8`

## string_xrefs

- `0x1401932d6`: `DELETE FROM UPDATESPROP WHERE PROVIDERID = ? AND UPDATEID = ? AND VARIABLE = ?`

## pseudocode

```c

```
