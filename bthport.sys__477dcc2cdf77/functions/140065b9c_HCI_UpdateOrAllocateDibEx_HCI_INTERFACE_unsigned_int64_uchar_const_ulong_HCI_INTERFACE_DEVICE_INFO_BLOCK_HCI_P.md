# HCI_UpdateOrAllocateDibEx(HCI_INTERFACE *,unsigned __int64 *,uchar const *,ulong (*)(HCI_INTERFACE *,DEVICE_INFO_BLOCK *,_HCI_PHY_TYPE,void *,LinkedDibAction *),void *,uchar *,uchar,uchar,_HCI_PHY_TYPE,_GUID *,uchar)

- ea: `0x140065b9c`
- end: `0x1400672b3`
- name: `?HCI_UpdateOrAllocateDibEx@@YAPEAUDEVICE_INFO_BLOCK@@PEAUHCI_INTERFACE@@PEA_KPEBEP6AK0PEAU1@W4_HCI_PHY_TYPE@@PEAXPEAW4LinkedDibAction@@@Z5PEAEEE4PEAU_GUID@@E@Z`
- size: `5911`
- prototype: `struct DEVICE_INFO_BLOCK *__usercall@<rax>(struct HCI_INTERFACE *@<rcx>, unsigned __int64 *@<rdx>, const unsigned __int8 *@<r8>, unsigned int (*)(struct HCI_INTERFACE *, struct DEVICE_INFO_BLOCK *, enum _HCI_PHY_TYPE, void *, enum LinkedDibAction *)@<r9>, void *, unsigned __int8 *, char, char, enum _HCI_PHY_TYPE, struct _GUID *, unsigned __int8)`
- caller_count: `8`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x140042460`
- `0x1400645d0`
- `0x140065b40`
- `0x14007a680`
- `0x14007dfc0`
- `0x140112ef8`
- `0x1401f2b50`
- `0x1401f2dd8`

## callees

- `0x140005608`
- `0x140005748`
- `0x140005b4c`
- `0x14000764c`
- `0x140013820`
- `0x14005123c`
- `0x140052db8`
- `0x140055238`
- `0x14005a290`
- `0x14005a518`
- `0x14005ad28`
- `0x14005efc4`
- `0x14005eff8`
- `0x14005f774`
- `0x14005fe30`
- `0x140065b9c`
- `0x140068ebc`
- `0x140161a44`
- `0x140161d7c`
- `0x140165580`
- `0x140206478`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065ccb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065ccb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006711d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006711d`

## pseudocode

```c

```
