# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007028`
- end: `0x1800070ee`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `198`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036b0`
- `0x1800036e0`
- `0x180003790`
- `0x1800099c0`

## callees

- `0x180007028`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007047`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007047`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007061`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007061`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007080`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007080`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800070b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800070b8`

## pseudocode

```c

```
