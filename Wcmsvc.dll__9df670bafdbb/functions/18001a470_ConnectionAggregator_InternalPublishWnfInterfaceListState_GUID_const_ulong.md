# ConnectionAggregator::InternalPublishWnfInterfaceListState(_GUID const *,ulong)

- ea: `0x18001a470`
- end: `0x18001a8c6`
- name: `?InternalPublishWnfInterfaceListState@ConnectionAggregator@@AEAAXPEBU_GUID@@K@Z`
- size: `1110`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x180017c94`

## callees

- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180015690`
- `0x180019434`
- `0x18001a470`
- `0x18001a8cc`
- `0x180041a20`
- `0x180085460`
- `0x180089ee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a4ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a4ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a654`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a78a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a654`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a78a`
- `ntdll!RtlPublishWnfStateData` at `0x18001a5f6`
- `ntdll!RtlPublishWnfStateData` at `0x18001a5f6`

## string_xrefs

- `0x18001a86e`: `onecoreuap\net\wcm\service\base\server\aggregator.cpp`

## pseudocode

```c

```
