# CComMgrIo::StopListening(void)

- ea: `0x180021d00`
- end: `0x180021e15`
- name: `?StopListening@CComMgrIo@@QEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(CComMgrIo *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e60c`
- `0x1800b5770`

## callees

- `0x1800063b0`
- `0x180021d00`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x180021d97`
- `WS2_32!__imp_closesocket` at `0x180021d97`
- `WS2_32!__imp_shutdown` at `0x180021d36`
- `WS2_32!__imp_shutdown` at `0x180021d36`
- `WS2_32!__imp_WSAGetLastError` at `0x180021d41`
- `WS2_32!__imp_WSAGetLastError` at `0x180021da2`
- `WS2_32!__imp_WSAGetLastError` at `0x180021d41`
- `WS2_32!__imp_WSAGetLastError` at `0x180021da2`

## string_xrefs

- `0x180021d6e`: `CComMgrIo::StopListening`
- `0x180021dcf`: `CComMgrIo::StopListening`
- `0x180021d67`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrio.cpp`
- `0x180021dc8`: `com\complus\dtc\dtc\tipgw\commgr\src\commgrio.cpp`

## pseudocode

```c

```
