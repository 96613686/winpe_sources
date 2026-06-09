# CmsBPlusTable::UnlinkAllOldPagesParallel(CmsTransactionContext *,_LIST_ENTRY *,_LIST_ENTRY *)

- ea: `0x140068360`
- end: `0x140068ab1`
- name: `?UnlinkAllOldPagesParallel@CmsBPlusTable@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@1@Z`
- size: `1873`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct _LIST_ENTRY *, struct _LIST_ENTRY *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140016440`
- `0x140068360`
- `0x140069890`
- `0x140091520`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140068408`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14006845a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140068408`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14006845a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400687c5`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1400687c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400688ad`
- `ntoskrnl!ExAllocatePool2` at `0x1400688ad`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400683e4`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140068436`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400686e5`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400683e4`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140068436`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x1400686e5`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1400687e0`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1400687e0`

## pseudocode

```c

```
