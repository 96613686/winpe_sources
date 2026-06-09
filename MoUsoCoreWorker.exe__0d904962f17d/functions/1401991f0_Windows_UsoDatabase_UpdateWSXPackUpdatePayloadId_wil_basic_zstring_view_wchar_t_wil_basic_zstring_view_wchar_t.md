# Windows::UsoDatabase::UpdateWSXPackUpdatePayloadId(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x1401991f0`
- end: `0x140199384`
- name: `?UpdateWSXPackUpdatePayloadId@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x1401991f0`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x14019927a`
- `winsqlite3!sqlite3_bind_text16` at `0x1401992ae`
- `winsqlite3!sqlite3_bind_text16` at `0x1401992e2`
- `winsqlite3!sqlite3_bind_text16` at `0x14019927a`
- `winsqlite3!sqlite3_bind_text16` at `0x1401992ae`
- `winsqlite3!sqlite3_bind_text16` at `0x1401992e2`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140199240`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140199240`
- `winsqlite3!sqlite3_finalize` at `0x14019931d`
- `winsqlite3!sqlite3_finalize` at `0x14019931d`

## string_xrefs

- `0x140199236`: `INSERT INTO WSXPACKUPDATES (UNIQUEID, PAYLOADID) VALUES (?, ?) ON CONFLICT(UNIQUEID) DO UPDATE SET PAYLOADID = ?`

## pseudocode

```c

```
