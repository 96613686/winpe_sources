# SdpInt_RemoveClientConnection(_SDP_INTERFACE *,void *,void *,uchar *,uchar *)

- ea: `0x14014bc98`
- end: `0x14014c094`
- name: `?SdpInt_RemoveClientConnection@@YAJPEAU_SDP_INTERFACE@@PEAX1PEAE2@Z`
- size: `1020`
- prototype: `int(struct _SDP_INTERFACE *, void *, void *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1401f04e4`

## callees

- `0x140005b4c`
- `0x140005c04`
- `0x14000764c`
- `0x1401484c0`
- `0x14014b848`
- `0x14014bc98`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14014be40`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14014bf32`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14014be40`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14014bf32`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14014bd71`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14014be81`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14014bd71`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14014be81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bd41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bd41`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014c00f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014c00f`

## pseudocode

```c

```
