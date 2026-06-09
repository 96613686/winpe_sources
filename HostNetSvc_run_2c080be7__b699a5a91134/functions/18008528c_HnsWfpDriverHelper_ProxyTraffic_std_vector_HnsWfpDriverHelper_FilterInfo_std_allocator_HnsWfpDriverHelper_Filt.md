# HnsWfpDriverHelper::ProxyTraffic(std::vector<HnsWfpDriverHelper::FilterInfo,std::allocator<HnsWfpDriverHelper::FilterInfo>> const &,std::vector<HnsWfpDriverHelper::ProviderContextInfo,std::allocator<HnsWfpDriverHelper::ProviderContextInfo>> const &)

- ea: `0x18008528c`
- end: `0x180085602`
- name: `?ProxyTraffic@HnsWfpDriverHelper@@QEAAJAEBV?$vector@UFilterInfo@HnsWfpDriverHelper@@V?$allocator@UFilterInfo@HnsWfpDriverHelper@@@std@@@std@@AEBV?$vector@UProviderContextInfo@HnsWfpDriverHelper@@V?$allocator@UProviderContextInfo@HnsWfpDriverHelper@@@std@@@3@@Z`
- size: `886`
- prototype: `__int64 __fastcall(HnsWfpDriverHelper *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1801f8d04`

## callees

- `0x18005f0c0`
- `0x18005ffc4`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x18007de54`
- `0x18007f21c`
- `0x180081d44`
- `0x180082998`
- `0x1800851c4`
- `0x18008528c`
- `0x180085608`
- `0x180088bac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008558c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008558c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085309`
- `fwpuclnt!FwpmFilterAdd0` at `0x180085475`
- `fwpuclnt!FwpmFilterAdd0` at `0x180085475`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180085355`
- `fwpuclnt!FwpmTransactionBegin0` at `0x180085355`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18008553b`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18008553b`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18008555c`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18008555c`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800853dd`
- `fwpuclnt!FwpmProviderContextAdd3` at `0x1800853dd`

## string_xrefs

- `0x18008533b`: `FwpmEngineOpen failed with %d\n`
- `0x180085547`: `FwpmTransactionCommit failed with %d\n`

## pseudocode

```c

```
