# HCI_RegUpdateRule001_DisconnectOnPairing(HCI_INTERFACE *)

- ea: `0x1401cf9e0`
- end: `0x1401d0208`
- name: `?HCI_RegUpdateRule001_DisconnectOnPairing@@YAJPEAUHCI_INTERFACE@@@Z`
- size: `2088`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1401b9928`

## callees

- `0x140005608`
- `0x140005690`
- `0x1400a95f0`
- `0x140165540`
- `0x140165640`
- `0x1401cf9e0`
- `0x140209168`
- `0x140209540`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x1401cfc75`
- `ntoskrnl!ZwEnumerateKey` at `0x1401cfce9`
- `ntoskrnl!ZwEnumerateKey` at `0x1401cfc75`
- `ntoskrnl!ZwEnumerateKey` at `0x1401cfce9`
- `ntoskrnl!ZwClose` at `0x1401cfe42`
- `ntoskrnl!ZwClose` at `0x1401d00ec`
- `ntoskrnl!ZwClose` at `0x1401d0105`
- `ntoskrnl!ZwClose` at `0x1401cfe42`
- `ntoskrnl!ZwClose` at `0x1401d00ec`
- `ntoskrnl!ZwClose` at `0x1401d0105`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cfc96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d00b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d00d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d011f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0157`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0178`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cfc96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d00b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d00d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d011f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0157`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0178`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfb0a`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfb92`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfbef`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfcb0`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfd49`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfb0a`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfb92`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfbef`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfcb0`
- `ntoskrnl!ExAllocatePool2` at `0x1401cfd49`

## string_xrefs

- `0x1401cfa91`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters\ExceptionDB\Rules\001_DisconnectOnPairingNotSupported`

## pseudocode

```c

```
