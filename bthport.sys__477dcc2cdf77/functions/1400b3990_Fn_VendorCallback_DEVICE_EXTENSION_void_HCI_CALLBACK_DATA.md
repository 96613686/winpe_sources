# Fn_VendorCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)

- ea: `0x1400b3990`
- end: `0x1400b3bf2`
- name: `?Fn_VendorCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z`
- size: `610`
- prototype: `void __fastcall(struct DEVICE_EXTENSION *, PVOID P, struct _HCI_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140005748`
- `0x14004d920`
- `0x1400b3990`
- `0x1400b9d78`
- `0x14016235c`
- `0x140165640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3b53`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3b6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3b53`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3b6c`

## pseudocode

```c

```
