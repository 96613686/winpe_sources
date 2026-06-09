# WluipStartServer

- ea: `0x18003cee0`
- end: `0x18003d208`
- name: `WluipStartServer`
- size: `808`
- prototype: `__int64 __fastcall(ULONG SessionId, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003cd50`

## callees

- `0x18003cee0`
- `0x18003d210`
- `0x180062e6c`
- `0x18006c000`
- `0x18006cad0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18003d101`
- `KERNEL32!CreateEventW` at `0x18003d101`
- `KERNEL32!GetLastError` at `0x18003d1f3`
- `KERNEL32!GetLastError` at `0x18003d1f3`
- `KERNEL32!Sleep` at `0x18003d1e8`
- `KERNEL32!Sleep` at `0x18003d1e8`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18003d152`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18003d152`
- `ntdll!RtlPublishWnfStateData` at `0x18003d1b8`
- `ntdll!RtlPublishWnfStateData` at `0x18003d1b8`
- `RPCRT4!RpcServerListen` at `0x18003d0e8`
- `RPCRT4!RpcServerListen` at `0x18003d0e8`
- `RPCRT4!RpcEpRegisterW` at `0x18003d0c1`
- `RPCRT4!RpcEpRegisterW` at `0x18003d0c1`
- `RPCRT4!RpcServerInqBindings` at `0x18003d034`
- `RPCRT4!RpcServerInqBindings` at `0x18003d034`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18003d013`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18003d013`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003cfdd`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003cfdd`
- `RPCRT4!UuidFromStringW` at `0x18003d083`
- `RPCRT4!UuidFromStringW` at `0x18003d083`

## pseudocode

```c

```
