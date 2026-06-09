# Windows::UsoDatabase::GetCompletedUpdate(UpdateIdentity const &)

- ea: `0x140195da0`
- end: `0x140195f14`
- name: `?GetCompletedUpdate@UsoDatabase@Windows@@UEBA?AV?$optional@UCompletedUpdateStorage@SystemInterface@@@std@@AEBUUpdateIdentity@@@Z`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400413a8`
- `0x140195da0`
- `0x14019c8f0`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x140195e9e`
- `winsqlite3!sqlite3_step` at `0x140195e9e`
- `winsqlite3!sqlite3_bind_text16` at `0x140195e33`
- `winsqlite3!sqlite3_bind_text16` at `0x140195e78`
- `winsqlite3!sqlite3_bind_text16` at `0x140195e33`
- `winsqlite3!sqlite3_bind_text16` at `0x140195e78`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140195def`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140195def`
- `winsqlite3!sqlite3_finalize` at `0x140195ebf`
- `winsqlite3!sqlite3_finalize` at `0x140195ebf`

## string_xrefs

- `0x140195de4`: `SELECT PROVIDERID, UPDATEID, TIME, TITLE, DESCRIPTION, MOREINFOURL, HISTORYCATEGORY, UNINSTALL, WASREBOOTREQUIRED, FOROS, METADATA FROM COMPLETEDUPDATES WHERE PROVIDERID = ? AND UPDATEID = ?`

## pseudocode

```c

```
