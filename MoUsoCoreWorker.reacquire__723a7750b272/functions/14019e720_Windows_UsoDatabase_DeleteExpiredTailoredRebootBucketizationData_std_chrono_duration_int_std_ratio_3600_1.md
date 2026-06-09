# Windows::UsoDatabase::DeleteExpiredTailoredRebootBucketizationData(std::chrono::duration<int,std::ratio<3600,1>>)

- ea: `0x14019e720`
- end: `0x14019eba1`
- name: `?DeleteExpiredTailoredRebootBucketizationData@UsoDatabase@Windows@@UEAAXV?$duration@HU?$ratio@$0OBA@$00@std@@@chrono@std@@@Z`
- size: `1153`
- prototype: `__int64 __fastcall(Windows::UsoDatabase *this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x140043284`
- `0x1400452ec`
- `0x140045404`
- `0x140075a18`
- `0x1400a5368`
- `0x1400c6f6c`
- `0x14012d7d8`
- `0x140191240`
- `0x14019e720`
- `0x14019f5d8`
- `0x1401a271c`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019e767`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14019e767`
- `winsqlite3!sqlite3_step` at `0x14019e919`
- `winsqlite3!sqlite3_step` at `0x14019e9ec`
- `winsqlite3!sqlite3_step` at `0x14019e919`
- `winsqlite3!sqlite3_step` at `0x14019e9ec`
- `winsqlite3!sqlite3_bind_text16` at `0x14019e884`
- `winsqlite3!sqlite3_bind_text16` at `0x14019e9bf`
- `winsqlite3!sqlite3_bind_text16` at `0x14019e884`
- `winsqlite3!sqlite3_bind_text16` at `0x14019e9bf`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e823`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e963`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e823`
- `winsqlite3!sqlite3_prepare16_v2` at `0x14019e963`
- `winsqlite3!sqlite3_finalize` at `0x14019ea9c`
- `winsqlite3!sqlite3_finalize` at `0x14019eaed`
- `winsqlite3!sqlite3_finalize` at `0x14019ea9c`
- `winsqlite3!sqlite3_finalize` at `0x14019eaed`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019e79e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14019e79e`

## string_xrefs

- `0x14019ea5d`: `DeleteExpiredTailoredRebootBucketizationData`
- `0x14019e9f7`: `Unable to delete expired history in REBOOTDEFERRALHISTORYSTATUS`
- `0x14019e818`: `DELETE FROM REBOOTDEFERRALHISTORY WHERE DATETIMECHECKED < ?`
- `0x14019e958`: `DELETE FROM REBOOTDEFERRALHISTORYSTATUS WHERE REBOOTATTEMPTTIMESTAMP < ?`
- `0x14019e924`: `Unable to delete expired history in REBOOTDEFERRALHISTORY`

## pseudocode

```c

```
