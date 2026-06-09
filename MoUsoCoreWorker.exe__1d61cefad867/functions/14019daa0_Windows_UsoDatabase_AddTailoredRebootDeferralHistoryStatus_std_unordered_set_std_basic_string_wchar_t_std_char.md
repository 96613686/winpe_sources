# Windows::UsoDatabase::AddTailoredRebootDeferralHistoryStatus(std::unordered_set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)

- ea: `0x14019daa0`
- end: `0x14019dfd2`
- name: `?AddTailoredRebootDeferralHistoryStatus@UsoDatabase@Windows@@UEAAXV?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z`
- size: `1330`
- prototype: `__int64 __fastcall(Windows::UsoDatabase *this)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update`

## callees

- `0x140029f9c`
- `0x140040184`
- `0x1400413a8`
- `0x140043284`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400a5368`
- `0x1400aa014`
- `0x1400c6f6c`
- `0x14012d7d8`
- `0x140191240`
- `0x14019daa0`
- `0x14019f5d8`
- `0x1401a271c`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019daee`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019daee`
- `winsqlite3!sqlite3_step` at `0x14019dd64`
- `winsqlite3!sqlite3_step` at `0x14019dd64`
- `winsqlite3!sqlite3_bind_text16` at `0x14019dcb1`
- `winsqlite3!sqlite3_bind_text16` at `0x14019dcf6`
- `winsqlite3!sqlite3_bind_text16` at `0x14019dd3f`
- `winsqlite3!sqlite3_bind_text16` at `0x14019dcb1`
- `winsqlite3!sqlite3_bind_text16` at `0x14019dcf6`
- `winsqlite3!sqlite3_bind_text16` at `0x14019dd3f`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019dbad`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019dbad`
- `winsqlite3!sqlite3_reset` at `0x14019dd90`
- `winsqlite3!sqlite3_reset` at `0x14019dd90`
- `winsqlite3!sqlite3_clear_bindings` at `0x14019ddb5`
- `winsqlite3!sqlite3_clear_bindings` at `0x14019ddb5`
- `winsqlite3!sqlite3_finalize` at `0x14019dec2`
- `winsqlite3!sqlite3_finalize` at `0x14019dec2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019dbdd`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019dbdd`

## string_xrefs

- `0x14019dba2`: `INSERT INTO REBOOTDEFERRALHISTORYSTATUS (REBOOTATTEMPTTIMESTAMP, DEFERRALREASON, REBOOTREQUIREDTIMEUTC) VALUES (?, ?, ?)`

## pseudocode

```c

```
