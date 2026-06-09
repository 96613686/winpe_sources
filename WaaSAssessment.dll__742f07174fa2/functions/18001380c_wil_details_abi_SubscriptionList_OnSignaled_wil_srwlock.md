# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18001380c`
- end: `0x1800138c9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010760`
- `0x180010790`
- `0x180010890`
- `0x180015df0`

## callees

- `0x18001380c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013822`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013822`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013852`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013852`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013893`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013893`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001385b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001385b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001383c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001383c`

## pseudocode

```c

```
