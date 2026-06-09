# Windows::UsoDatabase::GetActionDeferredCount(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::optional<uint>)

- ea: `0x14019ba40`
- end: `0x14019be45`
- name: `?GetActionDeferredCount@UsoDatabase@Windows@@UEBAIV?$basic_zstring_view@_W@wil@@0V?$optional@I@std@@@Z`
- size: `1029`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140044b18`
- `0x140045404`
- `0x1400c6fb4`
- `0x14012d7d8`
- `0x14019ba40`
- `0x14019f5d8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x14019bcee`
- `winsqlite3!sqlite3_step` at `0x14019bcee`
- `winsqlite3!sqlite3_bind_text16` at `0x14019bb27`
- `winsqlite3!sqlite3_bind_text16` at `0x14019bb61`
- `winsqlite3!sqlite3_bind_text16` at `0x14019bc2d`
- `winsqlite3!sqlite3_bind_text16` at `0x14019bb27`
- `winsqlite3!sqlite3_bind_text16` at `0x14019bb61`
- `winsqlite3!sqlite3_bind_text16` at `0x14019bc2d`
- `winsqlite3!sqlite3_column_int` at `0x14019bce2`
- `winsqlite3!sqlite3_column_int` at `0x14019bce2`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019baef`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019baef`
- `winsqlite3!sqlite3_finalize` at `0x14019bdbb`
- `winsqlite3!sqlite3_finalize` at `0x14019bdbb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019bb96`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019bb96`

## string_xrefs

- `0x14019ba8e`: `SELECT SUM(ACTIONATTEMPT) AS Count FROM DEFERRALHISTORY WHERE ACTION = ?   AND DEFERRALREASON = ?`

## pseudocode

```c

```
