# CAvEndpointBuilder::QueryAndSubscribePostureChangeNotification(void)

- ea: `0x1800274dc`
- end: `0x180027705`
- name: `?QueryAndSubscribePostureChangeNotification@CAvEndpointBuilder@@AEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003984c`

## callees

- `0x1800274dc`
- `0x180033464`
- `0x180034c5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002757d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002757d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800276ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800274f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800274f7`
- `ntdll!RtlQueryWnfStateData` at `0x180027550`
- `ntdll!RtlQueryWnfStateData` at `0x180027653`
- `ntdll!RtlQueryWnfStateData` at `0x180027550`
- `ntdll!RtlQueryWnfStateData` at `0x180027653`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800275f3`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800276d0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800275f3`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800276d0`

## string_xrefs

- `0x180027564`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c

```
