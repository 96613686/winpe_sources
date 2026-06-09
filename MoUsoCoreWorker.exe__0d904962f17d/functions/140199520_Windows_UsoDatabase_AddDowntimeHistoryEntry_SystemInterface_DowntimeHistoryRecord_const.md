# Windows::UsoDatabase::AddDowntimeHistoryEntry(SystemInterface::DowntimeHistoryRecord const &)

- ea: `0x140199520`
- end: `0x1401997db`
- name: `?AddDowntimeHistoryEntry@UsoDatabase@Windows@@UEAAXAEBUDowntimeHistoryRecord@SystemInterface@@@Z`
- size: `699`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct SystemInterface::DowntimeHistoryRecord *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400c6f6c`
- `0x14018d1a4`
- `0x140199520`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x1401995be`
- `winsqlite3!sqlite3_bind_text16` at `0x14019969c`
- `winsqlite3!sqlite3_bind_text16` at `0x1401996e4`
- `winsqlite3!sqlite3_bind_text16` at `0x1401995be`
- `winsqlite3!sqlite3_bind_text16` at `0x14019969c`
- `winsqlite3!sqlite3_bind_text16` at `0x1401996e4`
- `winsqlite3!sqlite3_bind_int` at `0x1401995eb`
- `winsqlite3!sqlite3_bind_int` at `0x140199618`
- `winsqlite3!sqlite3_bind_int` at `0x1401995eb`
- `winsqlite3!sqlite3_bind_int` at `0x140199618`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019957a`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019957a`
- `winsqlite3!sqlite3_finalize` at `0x14019971c`
- `winsqlite3!sqlite3_finalize` at `0x14019971c`

## string_xrefs

- `0x140199570`: `INSERT OR REPLACE INTO DOWNTIMEHISTORY (UNIQUEID, ESTIMATEDTIME, ESTIMATEDTIMEHIGH, TIMESTAMP, UPDATEMETADATA) VALUES (?, ?, ?, ?, ?)`

## pseudocode

```c

```
