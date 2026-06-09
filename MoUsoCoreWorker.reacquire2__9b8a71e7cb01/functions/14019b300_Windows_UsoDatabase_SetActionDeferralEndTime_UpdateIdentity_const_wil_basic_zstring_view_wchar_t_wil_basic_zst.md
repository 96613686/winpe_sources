# Windows::UsoDatabase::SetActionDeferralEndTime(UpdateIdentity const &,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &)

- ea: `0x14019b300`
- end: `0x14019ba32`
- name: `?SetActionDeferralEndTime@UsoDatabase@Windows@@UEAAXAEBUUpdateIdentity@@V?$basic_zstring_view@_W@wil@@1AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `1842`
- prototype: `__int64 __usercall@<rax>(Windows::UsoDatabase *this@<rcx>, struct UpdateIdentity *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140044b18`
- `0x140045404`
- `0x1400c6fb4`
- `0x14012d7d8`
- `0x14018d1a4`
- `0x14019af90`
- `0x14019b300`
- `0x14019eef8`
- `0x14019f5d8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `winsqlite3!sqlite3_step` at `0x14019b64f`
- `winsqlite3!sqlite3_step` at `0x14019b64f`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b5ab`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b5ee`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b627`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b6c4`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b707`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b740`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b77b`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b7ba`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b7f9`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b5ab`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b5ee`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b627`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b6c4`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b707`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b740`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b77b`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b7ba`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b7f9`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019b569`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019b682`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019b569`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019b682`
- `winsqlite3!sqlite3_finalize` at `0x14019b835`
- `winsqlite3!sqlite3_finalize` at `0x14019b8ce`
- `winsqlite3!sqlite3_finalize` at `0x14019b835`
- `winsqlite3!sqlite3_finalize` at `0x14019b8ce`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019b342`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019b342`

## string_xrefs

- `0x14019b678`: `INSERT INTO DEFERRALHISTORY (PROVIDERID, UPDATEID, UPDATEGROUP, ACTION, ACTIONATTEMPT, DEFERRALREASON, ISPRIMARYDEFERRAL, DEFERRALSTARTTIME, DEFERRALENDTIME) VALUES (?, ?, ?, ?, 0, 'NO_TAILORED_DEFERRALS', 'FALSE', ?, ?)`
- `0x14019b3c2`: `SELECT DEFERRALREASON FROM DEFERRALHISTORY WHERE PROVIDERID = ? AND UPDATEID = ? AND ACTION = ?`

## pseudocode

```c

```
