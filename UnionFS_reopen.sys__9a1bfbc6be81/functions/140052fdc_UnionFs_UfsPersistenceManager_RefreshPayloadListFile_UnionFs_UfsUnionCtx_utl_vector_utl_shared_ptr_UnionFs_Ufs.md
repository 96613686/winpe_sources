# UnionFs::UfsPersistenceManager::RefreshPayloadListFile(UnionFs::UfsUnionCtx &,utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>> const &,bool *,UnionFs::StackEventTracer &)

- ea: `0x140052fdc`
- end: `0x140053512`
- name: `?RefreshPayloadListFile@UfsPersistenceManager@UnionFs@@IEBAJAEAVUfsUnionCtx@2@AEBV?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@PEA_NAEAVStackEventTracer@2@@Z`
- size: `1334`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x140053518`

## callees

- `0x140001008`
- `0x14000f7fc`
- `0x14004fd64`
- `0x14004fdcc`
- `0x140050240`
- `0x140051630`
- `0x140051840`
- `0x140052fdc`
- `0x140053ec8`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007b8b0`
- `0x14007b900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005317f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400531e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053293`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053410`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053430`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005348f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400534af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005317f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400531e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053293`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053410`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053430`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005348f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400534af`
- `ntoskrnl!ObfDereferenceObject` at `0x1400531fd`
- `ntoskrnl!ObfDereferenceObject` at `0x14005344d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400534cc`
- `ntoskrnl!ObfDereferenceObject` at `0x1400531fd`
- `ntoskrnl!ObfDereferenceObject` at `0x14005344d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400534cc`
- `FLTMGR!FltSetInformationFile` at `0x1400533be`
- `FLTMGR!FltSetInformationFile` at `0x1400533be`
- `FLTMGR!FltClose` at `0x140053216`
- `FLTMGR!FltClose` at `0x140053462`
- `FLTMGR!FltClose` at `0x1400534e1`
- `FLTMGR!FltClose` at `0x140053216`
- `FLTMGR!FltClose` at `0x140053462`
- `FLTMGR!FltClose` at `0x1400534e1`

## string_xrefs

- `0x140053318`: `ORIGIN: Allocating rename info buffer`
- `0x1400530b6`: `PUSH: Getting temporary payload file`
- `0x1400533e3`: `API: Renaming temp payload file`

## pseudocode

```c

```
