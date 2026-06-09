# FwProducts::GetPolicyStoreHandle(void * *)

- ea: `0x1800258dc`
- end: `0x18002598b`
- name: `?GetPolicyStoreHandle@FwProducts@@AEAAJPEAPEAX@Z`
- size: `175`
- prototype: `__int64 __fastcall(FwProducts *__hidden this, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800220c0`
- `0x18003ade0`
- `0x18003b3c0`

## callees

- `0x18000d0f0`
- `0x1800258dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800258f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025957`
- `fwbase!FwReportErrorAsWinError` at `0x18002593c`
- `fwbase!FwReportErrorAsWinError` at `0x18002593c`
- `fwbase!FwReportReturnError` at `0x180025970`
- `fwbase!FwReportReturnError` at `0x180025970`

## string_xrefs

- `0x18002592e`: `FWOpenPolicyStore`

## pseudocode

```c

```
