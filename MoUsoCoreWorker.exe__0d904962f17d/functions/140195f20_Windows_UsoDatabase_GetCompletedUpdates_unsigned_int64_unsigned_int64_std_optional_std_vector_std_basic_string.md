# Windows::UsoDatabase::GetCompletedUpdates(unsigned __int64,unsigned __int64,std::optional<std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> const &)

- ea: `0x140195f20`
- end: `0x140196332`
- name: `?GetCompletedUpdates@UsoDatabase@Windows@@UEAA?AV?$vector@UCompletedUpdateStorage@SystemInterface@@V?$allocator@UCompletedUpdateStorage@SystemInterface@@@std@@@std@@_K0AEBV?$optional@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@4@@Z`
- size: `1042`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401672e0`
- `0x14018eaa4`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140043814`
- `0x140044b18`
- `0x140045404`
- `0x140075a18`
- `0x14016e94c`
- `0x14017dd00`
- `0x140195f20`
- `0x14019c8f0`
- `0x1401a0aa0`
- `0x140379070`
- `0x14037b4b0`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x14019611f`
- `winsqlite3!sqlite3_step` at `0x14019611f`
- `winsqlite3!sqlite3_bind_text16` at `0x1401960ad`
- `winsqlite3!sqlite3_bind_text16` at `0x1401960ad`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019601b`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401961b3`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019601b`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1401961b3`
- `winsqlite3!sqlite3_finalize` at `0x140196256`
- `winsqlite3!sqlite3_finalize` at `0x140196256`

## string_xrefs

- `0x1401961a8`: `SELECT PROVIDERID, UPDATEID, TIME, TITLE, DESCRIPTION, MOREINFOURL, HISTORYCATEGORY, UNINSTALL, WASREBOOTREQUIRED, FOROS, METADATA FROM COMPLETEDUPDATES ORDER BY TIME DESC`
- `0x140195faa`: `SELECT PROVIDERID, UPDATEID, TIME, TITLE, DESCRIPTION, MOREINFOURL, HISTORYCATEGORY, UNINSTALL, WASREBOOTREQUIRED, FOROS, METADATA FROM COMPLETEDUPDATES WHERE PROVIDERID IN (?`

## pseudocode

```c

```
