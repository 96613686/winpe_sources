# CRdpIceLocalEndpoint::OnReadCompleted(uchar const *,unsigned __int64)

- ea: `0x1801470a0`
- end: `0x180147385`
- name: `?OnReadCompleted@CRdpIceLocalEndpoint@@UEAAXPEBE_K@Z`
- size: `741`
- prototype: `void(CRdpIceLocalEndpoint *__hidden this, const unsigned __int8 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180004a94`
- `0x180016ad0`
- `0x1800506ac`
- `0x180125aa0`
- `0x180125db0`
- `0x1801464f8`
- `0x1801470a0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18014735e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18014735e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18014716f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18014716f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801472f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147341`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801472f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147341`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1801471d8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1801471d8`

## string_xrefs

- `0x180147175`: `OnReadCompleted`
- `0x180147104`: `Ice local endpoint: shortcut triggering the read thread`
- `0x180147190`: `Ice local endpoint read queue is full, need to block further receives.`
- `0x180147232`: `Processing error in CRdpIceLocalEndpoint::OnReadCompleted.`

## pseudocode

```c

```
