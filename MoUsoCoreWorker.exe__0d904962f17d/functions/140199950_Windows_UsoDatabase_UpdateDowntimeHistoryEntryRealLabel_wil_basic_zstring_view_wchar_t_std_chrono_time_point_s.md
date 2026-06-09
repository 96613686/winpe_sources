# Windows::UsoDatabase::UpdateDowntimeHistoryEntryRealLabel(wil::basic_zstring_view<wchar_t>,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,unsigned __int64)

- ea: `0x140199950`
- end: `0x140199b9f`
- name: `?UpdateDowntimeHistoryEntryRealLabel@UsoDatabase@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@_K@Z`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140041338`
- `0x1400413a8`
- `0x14018d1a4`
- `0x140199950`
- `0x1401a2d44`
- `0x140379070`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x140199ac1`
- `winsqlite3!sqlite3_bind_text16` at `0x140199ac1`
- `winsqlite3!sqlite3_bind_int` at `0x140199a59`
- `winsqlite3!sqlite3_bind_int` at `0x140199a87`
- `winsqlite3!sqlite3_bind_int` at `0x140199a59`
- `winsqlite3!sqlite3_bind_int` at `0x140199a87`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140199a25`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140199a25`
- `winsqlite3!sqlite3_finalize` at `0x140199afd`
- `winsqlite3!sqlite3_finalize` at `0x140199afd`

## string_xrefs

- `0x140199a1a`: `UPDATE DOWNTIMEHISTORY SET REALLABEL = ?, REALLABELSECONDS = ? WHERE UNIQUEID = ?`

## pseudocode

```c

```
