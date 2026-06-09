# MsWaitForEvent(MS_EVENT_USERMODE *,_LARGE_INTEGER *)

- ea: `0x1400ab594`
- end: `0x1400ab607`
- name: `?MsWaitForEvent@@YAJPEAUMS_EVENT_USERMODE@@PEAT_LARGE_INTEGER@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct MS_EVENT_USERMODE *, union _LARGE_INTEGER *)`
- caller_count: `50`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140086e24`
- `0x14008d5ac`
- `0x14008d634`
- `0x14008d750`
- `0x14008e220`
- `0x14008e4a4`
- `0x14008ff90`
- `0x1400916fc`
- `0x140097850`
- `0x140098a38`
- `0x14009bb10`
- `0x1400a42d8`
- `0x1400a48d4`
- `0x1400b1a10`
- `0x1400c575c`
- `0x1400c5cb4`
- `0x1400c647c`
- `0x1400c8eb4`
- `0x1400d3458`
- `0x1400d37c8`
- `0x1400d3f60`
- `0x1400d4d3c`
- `0x1400d4d74`
- `0x1400d5ea0`
- `0x1400db730`
- `0x1400db900`
- `0x1400dbad0`
- `0x1400dbca0`
- `0x1400dbe70`
- `0x1400dc0fc`
- `0x1400dd758`
- `0x1400de68c`
- `0x1400df970`
- `0x1400e2e70`
- `0x1400e310c`
- `0x1400f360c`
- `0x1400f4f3c`
- `0x1400f69e8`
- `0x1400f88ac`
- `0x1400fb2b0`
- `0x1400fce80`
- `0x1400fe7f0`
- `0x1400fe828`
- `0x1400fe8fc`
- `0x1401021d0`
- `0x140111814`
- `0x14011b5f4`
- `0x140127d78`
- `0x140128d90`
- `0x1401319c0`

## callees

- `0x1400ab594`

## import_xrefs

- `ntdll!RtlSleepConditionVariableSRW` at `0x1400ab5cb`
- `ntdll!RtlSleepConditionVariableSRW` at `0x1400ab5cb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400ab5ac`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400ab5ac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400ab5ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400ab5ef`

## pseudocode

```c

```
