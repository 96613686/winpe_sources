# A2DP_Device::EnterActiveACLMode(void)

- ea: `0x140030be0`
- end: `0x140030c5f`
- name: `?EnterActiveACLMode@A2DP_Device@@AEAAXXZ`
- size: `127`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140032f78`
- `0x140033530`

## callees

- `0x140030be0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140030c26`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030c26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030bf6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030bf6`

## pseudocode

```c

```
