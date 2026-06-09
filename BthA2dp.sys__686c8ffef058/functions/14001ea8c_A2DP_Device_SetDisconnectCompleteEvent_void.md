# A2DP_Device::SetDisconnectCompleteEvent(void)

- ea: `0x14001ea8c`
- end: `0x14001eb02`
- name: `?SetDisconnectCompleteEvent@A2DP_Device@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(A2DP_Device *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140011bcc`
- `0x140014d40`
- `0x14001e940`
- `0x140030740`

## callees

- `0x14001ea8c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001eae5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001eae5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001eaa8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001eaa8`
- `ntoskrnl!KeSetEvent` at `0x14001eacc`
- `ntoskrnl!KeSetEvent` at `0x14001eacc`

## pseudocode

```c

```
