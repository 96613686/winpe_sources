# CWwanIpAddr::EventHandler(_TP_WAIT *)

- ea: `0x180056468`
- end: `0x18005663f`
- name: `?EventHandler@CWwanIpAddr@@AEAAXPEAU_TP_WAIT@@@Z`
- size: `471`
- prototype: `void __fastcall(CWwanIpAddr *__hidden this, struct _TP_WAIT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180056e00`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180016c50`
- `0x180056468`
- `0x18005b49c`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800564cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800564cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800565e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800565f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800565e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800565f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180056518`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180056518`
- `WS2_32!WSAIoctl` at `0x180056594`
- `WS2_32!WSAIoctl` at `0x180056594`
- `WS2_32!WSAEnumNetworkEvents` at `0x18005652d`
- `WS2_32!WSAEnumNetworkEvents` at `0x18005652d`
- `WS2_32!__imp_WSAGetLastError` at `0x180056538`
- `WS2_32!__imp_WSAGetLastError` at `0x18005659f`
- `WS2_32!__imp_WSAGetLastError` at `0x180056538`
- `WS2_32!__imp_WSAGetLastError` at `0x18005659f`

## pseudocode

```c

```
