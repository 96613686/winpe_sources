# Windows::UsoDatabase::AddApprovedUpdate(wil::basic_zstring_view<wchar_t>)

- ea: `0x140196340`
- end: `0x14019657d`
- name: `?AddApprovedUpdate@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@@Z`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400c6f6c`
- `0x14018d1a4`
- `0x140196340`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401963e8`
- `winsqlite3!sqlite3_bind_text16` at `0x14019649a`
- `winsqlite3!sqlite3_bind_text16` at `0x1401963e8`
- `winsqlite3!sqlite3_bind_text16` at `0x14019649a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401963b1`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401963b1`
- `winsqlite3!sqlite3_finalize` at `0x1401964e0`
- `winsqlite3!sqlite3_finalize` at `0x1401964e0`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140196418`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x140196418`

## string_xrefs

- `0x1401963a6`: `INSERT OR REPLACE INTO APPROVEDUPDATES (UPDATEID, TIME) VALUES (?, ?)`

## pseudocode

```c

```
