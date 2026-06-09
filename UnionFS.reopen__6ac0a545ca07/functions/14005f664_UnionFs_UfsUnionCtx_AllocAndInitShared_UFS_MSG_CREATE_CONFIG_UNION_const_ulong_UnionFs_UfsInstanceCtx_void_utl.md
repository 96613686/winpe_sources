# UnionFs::UfsUnionCtx::AllocAndInitShared(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::UfsInstanceCtx &,void *,utl::shared_ptr<UnionFs::UfsUnionCtx> &,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x14005f664`
- end: `0x14005fa97`
- name: `?AllocAndInitShared@UfsUnionCtx@UnionFs@@SAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVUfsInstanceCtx@2@PEAXAEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400093cc`

## callees

- `0x14000f81c`
- `0x140025030`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005a87c`
- `0x14005d0b0`
- `0x14005d17c`
- `0x14005f664`
- `0x140062fd4`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14005f781`
- `ntoskrnl!PsIsHostSilo` at `0x14005f781`
- `ntoskrnl!PsGetJobSilo` at `0x14005f758`
- `ntoskrnl!PsGetJobSilo` at `0x14005f758`
- `ntoskrnl!ObIsKernelHandle` at `0x14005f69d`
- `ntoskrnl!ObIsKernelHandle` at `0x14005f69d`
- `ntoskrnl!PsJobType` at `0x14005f6a9`
- `ntoskrnl!ExAllocatePool2` at `0x14005f841`
- `ntoskrnl!ExAllocatePool2` at `0x14005f841`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f818`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f8d2`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f9bc`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005fa5a`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f818`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f8d2`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005f9bc`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005fa5a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f6cd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f6cd`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f6f4`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f739`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f8eb`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f9d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005fa77`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f6f4`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f739`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f8eb`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f9d9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005fa77`

## string_xrefs

- `0x14005f934`: `newUnionCtx->GetSiloContext()->GetPathCache()`

## pseudocode

```c

```
