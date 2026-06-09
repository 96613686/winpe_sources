# FwProducts::GetPolicyStoreHandle(void * *)

- ea: `0x180023d88`
- end: `0x180023e1e`
- name: `?GetPolicyStoreHandle@FwProducts@@AEAAJPEAPEAX@Z`
- size: `150`
- prototype: `__int64 __fastcall(FwProducts *__hidden this, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800208b0`
- `0x180038450`
- `0x1800389c0`

## callees

- `0x18000c560`
- `0x180023d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023da0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023da0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023df7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023df7`
- `fwbase!FwReportErrorAsWinError` at `0x180023de2`
- `fwbase!FwReportErrorAsWinError` at `0x180023de2`
- `fwbase!FwReportReturnError` at `0x180023e0a`
- `fwbase!FwReportReturnError` at `0x180023e0a`

## string_xrefs

- `0x180023dd4`: `FWOpenPolicyStore`

## pseudocode

```c

```
