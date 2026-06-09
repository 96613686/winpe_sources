# CRDPWDUMXStack::ProcessKeyboardAndMouseInput(uchar,uchar *,ulong,int)

- ea: `0x180125000`
- end: `0x1801251e3`
- name: `?ProcessKeyboardAndMouseInput@CRDPWDUMXStack@@UEAAJEPEAEKH@Z`
- size: `483`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this, unsigned __int8, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000202c`
- `0x18007015c`
- `0x18007e9e0`
- `0x180125000`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1801251b6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1801251b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801251bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801251bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180125036`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180125036`

## string_xrefs

- `0x180125125`: `Ignoring call for process BasicInput PDU. Stack is already closed.`

## pseudocode

```c

```
