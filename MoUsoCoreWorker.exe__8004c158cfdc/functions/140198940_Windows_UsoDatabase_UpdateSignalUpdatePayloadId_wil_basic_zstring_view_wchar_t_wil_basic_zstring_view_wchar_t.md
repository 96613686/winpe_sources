# Windows::UsoDatabase::UpdateSignalUpdatePayloadId(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x140198940`
- end: `0x140198ad4`
- name: `?UpdateSignalUpdatePayloadId@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x14018d1a4`
- `0x140198940`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401989ca`
- `winsqlite3!sqlite3_bind_text16` at `0x1401989fe`
- `winsqlite3!sqlite3_bind_text16` at `0x140198a32`
- `winsqlite3!sqlite3_bind_text16` at `0x1401989ca`
- `winsqlite3!sqlite3_bind_text16` at `0x1401989fe`
- `winsqlite3!sqlite3_bind_text16` at `0x140198a32`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198990`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140198990`
- `winsqlite3!sqlite3_finalize` at `0x140198a6d`
- `winsqlite3!sqlite3_finalize` at `0x140198a6d`

## string_xrefs

- `0x140198986`: `INSERT INTO SIGNALUPDATES (UNIQUEID, PAYLOADID) VALUES (?, ?) ON CONFLICT(UNIQUEID) DO UPDATE SET PAYLOADID = ?`

## pseudocode

```c

```
