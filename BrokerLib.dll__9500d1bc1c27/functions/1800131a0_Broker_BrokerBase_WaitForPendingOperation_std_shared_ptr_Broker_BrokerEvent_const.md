# Broker::BrokerBase::WaitForPendingOperation(std::shared_ptr<Broker::BrokerEvent> const &)

- ea: `0x1800131a0`
- end: `0x180013207`
- name: `?WaitForPendingOperation@BrokerBase@Broker@@AEAAXAEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ff8`
- `0x180002868`

## callees

- `0x1800131a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800131e6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800131e6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800131bd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800131bd`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800131dd`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800131dd`

## pseudocode

```c

```
