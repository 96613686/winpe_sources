# Windows::UsoDatabase::UpdateUpdate(SystemInterface::UpdateStorage const &)

- ea: `0x1401921a0`
- end: `0x140192350`
- name: `?UpdateUpdate@UsoDatabase@Windows@@UEAAXAEBUUpdateStorage@SystemInterface@@@Z`
- size: `432`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct SystemInterface::UpdateStorage *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x1401921a0`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x14019226b`
- `winsqlite3!sqlite3_bind_text16` at `0x1401922ac`
- `winsqlite3!sqlite3_bind_text16` at `0x14019226b`
- `winsqlite3!sqlite3_bind_text16` at `0x1401922ac`
- `winsqlite3!sqlite3_bind_blob` at `0x14019222b`
- `winsqlite3!sqlite3_bind_blob` at `0x14019222b`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401921ed`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401921ed`
- `winsqlite3!sqlite3_finalize` at `0x1401922e7`
- `winsqlite3!sqlite3_finalize` at `0x1401922e7`

## string_xrefs

- `0x1401921e3`: `UPDATE UPDATES SET SERIALIZEDUPDATE = ? WHERE PROVIDERID = ? AND UPDATEID = ?`

## pseudocode

```c

```
