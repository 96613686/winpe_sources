# Windows::UsoDatabase::GetActionDeferralAggregateStats(wil::basic_zstring_view<wchar_t>,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>)

- ea: `0x14019be50`
- end: `0x14019c426`
- name: `?GetActionDeferralAggregateStats@UsoDatabase@Windows@@UEBA?AUDeferralAggregateStats@SystemInterface@@V?$basic_zstring_view@_W@wil@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `1494`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140043504`
- `0x140044b18`
- `0x140045404`
- `0x14007c0e8`
- `0x1400b3eb4`
- `0x14012d7d8`
- `0x14019be50`
- `0x14019eef8`
- `0x14019f5d8`
- `0x140378f3c`
- `0x140378f6c`
- `0x140379070`
- `0x140379140`
- `0x140380b50`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x14019c25b`
- `winsqlite3!sqlite3_step` at `0x14019c25b`
- `winsqlite3!sqlite3_bind_text16` at `0x14019c176`
- `winsqlite3!sqlite3_bind_text16` at `0x14019c1bc`
- `winsqlite3!sqlite3_bind_text16` at `0x14019c176`
- `winsqlite3!sqlite3_bind_text16` at `0x14019c1bc`
- `winsqlite3!sqlite3_column_int` at `0x14019c26c`
- `winsqlite3!sqlite3_column_int` at `0x14019c26c`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019c121`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019c121`
- `winsqlite3!sqlite3_column_double` at `0x14019c27e`
- `winsqlite3!sqlite3_column_double` at `0x14019c2bb`
- `winsqlite3!sqlite3_column_double` at `0x14019c27e`
- `winsqlite3!sqlite3_column_double` at `0x14019c2bb`
- `winsqlite3!sqlite3_finalize` at `0x14019c39c`
- `winsqlite3!sqlite3_finalize` at `0x14019c39c`

## string_xrefs

- `0x14019bebb`: `FeatureUpdate`
- `0x14019bede`: `QualityUpdate`
- `0x14019bf60`: `SELECT COUNT(DISTINCT UpdateId) AS UpdateCount, AVG(DeferralCount) AS AverageDeferralCount, AVG(TotalDeferralDurationInMins) AS AverageTotalDeferralDurationInMins FROM(SELECT UPDATEID AS UpdateId, ACTION, SUM(ACTIONATTEMPT) AS DeferralCount, SUM((julianday(DEFERRALENDTIME) - julianday(DEFERRALSTARTTIME)) * 24 * 60) AS TotalDeferralDurationInMins FROM DEFERRALHISTORY WHERE UPDATEGROUP IN (?, ?, ?) AND ACTION = ? AND DEFERRALENDTIME >= DEFERRALSTARTTIME AND DEFERRALENDTIME IS NOT NULL`
- `0x14019c0ee`: ` GROUP BY UPDATEID)`

## pseudocode

```c

```
