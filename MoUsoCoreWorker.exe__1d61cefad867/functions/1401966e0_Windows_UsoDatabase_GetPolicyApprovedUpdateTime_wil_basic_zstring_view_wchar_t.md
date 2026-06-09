# Windows::UsoDatabase::GetPolicyApprovedUpdateTime(wil::basic_zstring_view<wchar_t>)

- ea: `0x1401966e0`
- end: `0x14019689c`
- name: `?GetPolicyApprovedUpdateTime@UsoDatabase@Windows@@UEAA?AV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1401966e0`
- `0x1401a2a14`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x1401967a4`
- `winsqlite3!sqlite3_step` at `0x1401967a4`
- `winsqlite3!sqlite3_bind_text16` at `0x140196780`
- `winsqlite3!sqlite3_bind_text16` at `0x140196780`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140196749`
- `winsqlite3!sqlite3_prepare16_v2` at `0x140196749`
- `winsqlite3!sqlite3_finalize` at `0x140196810`
- `winsqlite3!sqlite3_finalize` at `0x140196835`
- `winsqlite3!sqlite3_finalize` at `0x140196810`
- `winsqlite3!sqlite3_finalize` at `0x140196835`
- `winsqlite3!sqlite3_column_text16` at `0x1401967b5`
- `winsqlite3!sqlite3_column_text16` at `0x1401967b5`

## string_xrefs

- `0x14019673e`: `SELECT TIME FROM APPROVEDUPDATES WHERE ? LIKE UPDATEID || '%'`

## pseudocode

```c

```
