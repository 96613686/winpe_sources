# HCI_RegUpdateInquiryFilter(HCI_INTERFACE *,void *,_KEY_VALUE_PARTIAL_INFORMATION *,uchar,_GUID *)

- ea: `0x1400a8e70`
- end: `0x1400a91c1`
- name: `?HCI_RegUpdateInquiryFilter@@YAJPEAUHCI_INTERFACE@@PEAXPEAU_KEY_VALUE_PARTIAL_INFORMATION@@EPEAU_GUID@@@Z`
- size: `849`
- prototype: `int(struct HCI_INTERFACE *, void *, struct _KEY_VALUE_PARTIAL_INFORMATION *, unsigned __int8, struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140005608`
- `0x14000764c`
- `0x14001be50`
- `0x1400a8e70`
- `0x1400a9938`
- `0x140209448`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400a8f36`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a8f80`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a8f36`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a8f80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a9106`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a9106`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a9125`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a9125`

## pseudocode

```c

```
