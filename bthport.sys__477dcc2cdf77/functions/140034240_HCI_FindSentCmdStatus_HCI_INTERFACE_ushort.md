# HCI_FindSentCmdStatus(HCI_INTERFACE *,ushort)

- ea: `0x140034240`
- end: `0x1400342fc`
- name: `?HCI_FindSentCmdStatus@@YAPEAU_BIP@@PEAUHCI_INTERFACE@@G@Z`
- size: `188`
- prototype: `struct _BIP *__fastcall(struct HCI_INTERFACE *, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14006b1dc`

## callees

- `0x140034240`
- `0x140077a20`
- `0x140161a44`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003425d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003425d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400342da`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400342da`

## string_xrefs

- `0x14003429b`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hcicommand.cpp`

## pseudocode

```c

```
