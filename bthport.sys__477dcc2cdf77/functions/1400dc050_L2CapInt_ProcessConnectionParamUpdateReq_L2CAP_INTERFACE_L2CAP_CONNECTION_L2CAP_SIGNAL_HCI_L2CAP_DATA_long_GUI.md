# L2CapInt_ProcessConnectionParamUpdateReq(L2CAP_INTERFACE *,L2CAP_CONNECTION *,_L2CAP_SIGNAL *,HCI_L2CAP_DATA *,long *,_GUID *)

- ea: `0x1400dc050`
- end: `0x1400dc61f`
- name: `?L2CapInt_ProcessConnectionParamUpdateReq@@YA?AW4_PROCESS_STATUS@@PEAUL2CAP_INTERFACE@@PEAUL2CAP_CONNECTION@@PEFAT_L2CAP_SIGNAL@@PEAUHCI_L2CAP_DATA@@PEAJPEAU_GUID@@@Z`
- size: `1487`
- prototype: `enum _PROCESS_STATUS __high(struct L2CAP_INTERFACE *, struct L2CAP_CONNECTION *, union _L2CAP_SIGNAL *, struct HCI_L2CAP_DATA *, int *, struct _GUID *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x140041e7c`
- `0x1400461b0`
- `0x14004631c`
- `0x1400dc050`
- `0x1400df2bc`
- `0x140161a44`
- `0x140161d7c`
- `0x140165540`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400dc583`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dc594`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dc583`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dc594`
- `ntoskrnl!ExAllocatePool2` at `0x1400dc285`
- `ntoskrnl!ExAllocatePool2` at `0x1400dc2b1`
- `ntoskrnl!ExAllocatePool2` at `0x1400dc285`
- `ntoskrnl!ExAllocatePool2` at `0x1400dc2b1`

## pseudocode

```c

```
