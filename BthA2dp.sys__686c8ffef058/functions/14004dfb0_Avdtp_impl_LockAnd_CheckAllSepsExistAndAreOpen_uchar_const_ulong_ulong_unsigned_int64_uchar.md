# Avdtp_impl::LockAnd_CheckAllSepsExistAndAreOpen(uchar const *,ulong *,ulong *,unsigned __int64,uchar &)

- ea: `0x14004dfb0`
- end: `0x14004e0d4`
- name: `?LockAnd_CheckAllSepsExistAndAreOpen@Avdtp_impl@@AEAAKPEBEPEAK1_KAEAE@Z`
- size: `292`
- prototype: `unsigned int __usercall@<eax>(Avdtp_impl *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int *@<r8>, unsigned int *@<r9>, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14004c1d0`

## callees

- `0x140049904`
- `0x140049cf8`
- `0x14004a2b8`
- `0x14004dfb0`
- `0x14005c8c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004e0b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e0b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004dffe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004dffe`

## pseudocode

```c

```
