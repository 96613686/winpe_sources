# Windows::UsoDatabase::AddUpdate(SystemInterface::UpdateStorage const &)

- ea: `0x140191fe0`
- end: `0x140192192`
- name: `?AddUpdate@UsoDatabase@Windows@@UEAAXAEBUUpdateStorage@SystemInterface@@@Z`
- size: `434`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct SystemInterface::UpdateStorage *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14018eaa4`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140191fe0`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140192072`
- `winsqlite3!sqlite3_bind_text16` at `0x1401920b3`
- `winsqlite3!sqlite3_bind_text16` at `0x140192072`
- `winsqlite3!sqlite3_bind_text16` at `0x1401920b3`
- `winsqlite3!sqlite3_bind_blob` at `0x1401920ee`
- `winsqlite3!sqlite3_bind_blob` at `0x1401920ee`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019202d`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019202d`
- `winsqlite3!sqlite3_finalize` at `0x140192129`
- `winsqlite3!sqlite3_finalize` at `0x140192129`

## string_xrefs

- `0x140192023`: `INSERT OR REPLACE INTO UPDATES (PROVIDERID, UPDATEID, SERIALIZEDUPDATE) VALUES (?, ?, ?)`

## pseudocode

```c

```
