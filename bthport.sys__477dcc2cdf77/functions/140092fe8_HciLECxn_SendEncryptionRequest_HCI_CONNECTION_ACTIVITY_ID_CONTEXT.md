# HciLECxn_SendEncryptionRequest(_HCI_CONNECTION_ACTIVITY_ID_CONTEXT *)

- ea: `0x140092fe8`
- end: `0x1400934c3`
- name: `?HciLECxn_SendEncryptionRequest@@YAXPEAU_HCI_CONNECTION_ACTIVITY_ID_CONTEXT@@@Z`
- size: `1243`
- prototype: `void __fastcall(struct _HCI_CONNECTION_ACTIVITY_ID_CONTEXT *)`
- caller_count: `8`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x140036dac`
- `0x1400386b0`
- `0x140039cc0`
- `0x14003e0f4`
- `0x1401100e0`
- `0x1401f6ec0`
- `0x1401f8f90`
- `0x1401fcd10`

## callees

- `0x140005608`
- `0x140005690`
- `0x1400350f0`
- `0x140058f78`
- `0x140092290`
- `0x140092fe8`
- `0x14014cb50`
- `0x140154e70`
- `0x140161a44`
- `0x140165540`
- `0x140165640`
- `0x140209168`
- `0x140209448`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400933fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400933fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400930b3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400930b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400930d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009314d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400930d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14009314d`

## string_xrefs

- `0x1400931f3`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters\LETestSTKStore`

## pseudocode

```c

```
