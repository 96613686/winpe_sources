# Windows::UsoDatabase::DeleteUpdate(UpdateIdentity const &)

- ea: `0x140192360`
- end: `0x1401924d1`
- name: `?DeleteUpdate@UsoDatabase@Windows@@UEAAXAEBUUpdateIdentity@@@Z`
- size: `369`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct UpdateIdentity *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140192360`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401923f3`
- `winsqlite3!sqlite3_bind_text16` at `0x140192438`
- `winsqlite3!sqlite3_bind_text16` at `0x1401923f3`
- `winsqlite3!sqlite3_bind_text16` at `0x140192438`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401923af`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401923af`
- `winsqlite3!sqlite3_finalize` at `0x140192477`
- `winsqlite3!sqlite3_finalize` at `0x140192477`

## string_xrefs

- `0x1401923a5`: `DELETE FROM UPDATES WHERE PROVIDERID = ? AND UPDATEID = ?`

## pseudocode

```c

```
