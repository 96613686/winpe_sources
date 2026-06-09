# CTxMgr::TxQuerySuspectFrameCompleteStatus(unsigned __int64,_NET_BUFFER_LIST *,uchar *,uchar *,int *)

- ea: `0x14009e238`
- end: `0x14009e4d6`
- name: `?TxQuerySuspectFrameCompleteStatus@CTxMgr@@QEAAX_KPEAU_NET_BUFFER_LIST@@PEAE2PEAH@Z`
- size: `670`
- prototype: `void __fastcall(CTxMgr *__hidden this, unsigned __int64, struct _NET_BUFFER_LIST *, unsigned __int8 *, unsigned __int8 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14009b1f0`

## callees

- `0x1400297a0`
- `0x140034e04`
- `0x14009e238`
- `0x14009e668`
- `0x14009e734`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14009e399`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009e3f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009e399`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009e3f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14009e325`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14009e325`

## pseudocode

```c

```
