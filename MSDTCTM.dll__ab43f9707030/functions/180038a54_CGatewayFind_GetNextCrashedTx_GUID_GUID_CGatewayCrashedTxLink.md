# CGatewayFind::GetNextCrashedTx(_GUID *,_GUID *,CGatewayCrashedTxLink * *)

- ea: `0x180038a54`
- end: `0x180038b51`
- name: `?GetNextCrashedTx@CGatewayFind@@QEAAHPEAU_GUID@@0PEAPEAVCGatewayCrashedTxLink@@@Z`
- size: `253`
- prototype: `int(CGatewayFind *__hidden this, struct _GUID *, struct _GUID *, struct CGatewayCrashedTxLink **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800462d0`

## callees

- `0x1800386c4`
- `0x180038a54`
- `0x180038ea4`
- `0x180038f00`
- `0x18003916c`
- `0x18006e904`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038b33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038b33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038a88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038a88`

## string_xrefs

- `0x180038b18`: `com\complus\dtc\dtc\tm\src\tmgatewayfind.cpp`

## pseudocode

```c

```
