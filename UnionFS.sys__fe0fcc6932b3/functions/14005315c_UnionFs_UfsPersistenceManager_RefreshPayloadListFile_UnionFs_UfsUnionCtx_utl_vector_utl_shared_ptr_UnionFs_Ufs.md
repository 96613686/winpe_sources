# UnionFs::UfsPersistenceManager::RefreshPayloadListFile(UnionFs::UfsUnionCtx &,utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>> const &,bool *,UnionFs::StackEventTracer &)

- ea: `0x14005315c`
- end: `0x140053692`
- name: `?RefreshPayloadListFile@UfsPersistenceManager@UnionFs@@IEBAJAEAVUfsUnionCtx@2@AEBV?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@PEA_NAEAVStackEventTracer@2@@Z`
- size: `1334`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x140053698`

## callees

- `0x140001008`
- `0x14000f81c`
- `0x14004fee4`
- `0x14004ff4c`
- `0x1400503c0`
- `0x1400517b0`
- `0x1400519c0`
- `0x14005315c`
- `0x140054048`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007bbd0`
- `0x14007bc40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400532ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053316`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053360`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053413`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053590`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400535b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005360f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005362f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400532ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053316`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053360`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053413`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053590`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400535b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005360f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005362f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005337d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400535cd`
- `ntoskrnl!ObfDereferenceObject` at `0x14005364c`
- `ntoskrnl!ObfDereferenceObject` at `0x14005337d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400535cd`
- `ntoskrnl!ObfDereferenceObject` at `0x14005364c`
- `FLTMGR!FltSetInformationFile` at `0x14005353e`
- `FLTMGR!FltSetInformationFile` at `0x14005353e`
- `FLTMGR!FltClose` at `0x140053396`
- `FLTMGR!FltClose` at `0x1400535e2`
- `FLTMGR!FltClose` at `0x140053661`
- `FLTMGR!FltClose` at `0x140053396`
- `FLTMGR!FltClose` at `0x1400535e2`
- `FLTMGR!FltClose` at `0x140053661`

## string_xrefs

- `0x140053498`: `ORIGIN: Allocating rename info buffer`
- `0x140053236`: `PUSH: Getting temporary payload file`
- `0x140053563`: `API: Renaming temp payload file`

## pseudocode

```c

```
