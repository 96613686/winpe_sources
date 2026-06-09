# UnionFs::UfsEaManager::GetPathsFromPayloadBuffer(UnionFs::UfsPathName const &,gsl::span<ushort const,-1> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &)

- ea: `0x140020178`
- end: `0x140020360`
- name: `?GetPathsFromPayloadBuffer@UfsEaManager@UnionFs@@CAJAEBVUfsPathName@2@AEBV?$span@$$CBG$0?0@gsl@@AEAV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAVStackEventTracer@2@@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001fc50`

## callees

- `0x14001014c`
- `0x14001c820`
- `0x14001f41c`
- `0x140020178`
- `0x140043f40`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020268`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400202ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020347`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020268`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400202ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020347`

## string_xrefs

- `0x1400202fa`: `PUSH: Combining ScratchRootPath, tempPath`
- `0x1400202ab`: `UnionFs::UfsEaManager::GetPathsFromPayloadBuffer`
- `0x14002030b`: `UnionFs::UfsEaManager::GetPathsFromPayloadBuffer`
- `0x140020298`: `ORIGIN: Adding payloadPath to vector`

## pseudocode

```c

```
