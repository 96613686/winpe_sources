# SMPDib_SendSecurityRequestForEncryption(_SMP_INTERFACE *,DEVICE_INFO_BLOCK *,uchar)

- ea: `0x140154e70`
- end: `0x1401554e4`
- name: `?SMPDib_SendSecurityRequestForEncryption@@YAJPEAU_SMP_INTERFACE@@PEAUDEVICE_INFO_BLOCK@@E@Z`
- size: `1652`
- prototype: `__int64 __fastcall(struct _SMP_INTERFACE *, struct DEVICE_INFO_BLOCK *, unsigned __int8)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140092fe8`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x1401505a4`
- `0x140150984`
- `0x140153650`
- `0x140154e70`
- `0x140155ab8`
- `0x140161a44`
- `0x140161d7c`
- `0x140165940`
- `0x1401f45a8`
- `0x1401f50d0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140155342`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015540f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015545e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140155342`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015540f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015545e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140155336`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140155403`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140155452`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140155336`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140155403`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140155452`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140154f18`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401553e7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140154f18`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401553e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140154f02`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401553d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140154f02`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401553d8`
- `ntoskrnl!KeSetTimer` at `0x14015529c`
- `ntoskrnl!KeSetTimer` at `0x14015529c`

## pseudocode

```c

```
