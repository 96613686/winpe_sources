# CRDPWDUMXStack::WDCallback_SendNetworkBuffer(uchar *,ulong,ulong)

- ea: `0x18003a348`
- end: `0x18003a758`
- name: `?WDCallback_SendNetworkBuffer@CRDPWDUMXStack@@QEAAJPEAEKK@Z`
- size: `1040`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180039eb4`
- `0x180039f54`
- `0x180039f88`

## callees

- `0x18000116c`
- `0x180001308`
- `0x1800068c0`
- `0x18003a348`
- `0x18003a8c0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a54e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a724`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a54e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a724`

## string_xrefs

- `0x18003a41e`: `Raw data redirect write`
- `0x18003a391`: `Try to send network buffer when WD is already closed`
- `0x18003a596`: `Raw data redirect write (monitor)`

## pseudocode

```c

```
