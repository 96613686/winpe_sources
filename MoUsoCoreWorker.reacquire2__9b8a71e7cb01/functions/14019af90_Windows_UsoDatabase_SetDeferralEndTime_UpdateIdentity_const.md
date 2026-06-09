# Windows::UsoDatabase::SetDeferralEndTime(UpdateIdentity const &)

- ea: `0x14019af90`
- end: `0x14019b2f1`
- name: `?SetDeferralEndTime@UsoDatabase@Windows@@UEAAXAEBUUpdateIdentity@@@Z`
- size: `865`
- prototype: `void __fastcall(Windows::UsoDatabase *__hidden this, const struct UpdateIdentity *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x14019b300`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1400c6fb4`
- `0x14012d7d8`
- `0x14018d1a4`
- `0x14019af90`
- `0x14019f5d8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `winsqlite3!sqlite3_bind_text16` at `0x14019b09c`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b0da`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b119`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b09c`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b0da`
- `winsqlite3!sqlite3_bind_text16` at `0x14019b119`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019b058`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019b058`
- `winsqlite3!sqlite3_finalize` at `0x14019b276`
- `winsqlite3!sqlite3_finalize` at `0x14019b276`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019afc8`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019afc8`

## string_xrefs

- `0x14019b04d`: `UPDATE DEFERRALHISTORY SET DEFERRALENDTIME = ? WHERE PROVIDERID = ?   AND UPDATEID = ?   AND DEFERRALENDTIME IS NULL;`

## pseudocode

```c

```
