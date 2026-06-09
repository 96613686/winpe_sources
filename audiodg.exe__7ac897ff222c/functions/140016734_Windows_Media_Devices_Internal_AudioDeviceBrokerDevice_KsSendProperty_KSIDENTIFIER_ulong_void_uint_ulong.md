# Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(KSIDENTIFIER *,ulong,void *,uint,ulong *)

- ea: `0x140016734`
- end: `0x140016841`
- name: `?KsSendProperty@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@AEAAJPEAUKSIDENTIFIER@@KPEAXIPEAK@Z`
- size: `269`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct KSIDENTIFIER *, __int64, void *, DWORD nOutBufferSize, unsigned int *lpBytesReturned)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001631c`
- `0x1400163c0`
- `0x14008b1c0`

## callees

- `0x140016734`
- `0x140016848`
- `0x1400378e4`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400167cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016826`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400167cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016826`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016769`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016769`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400167b6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400167b6`

## pseudocode

```c

```
