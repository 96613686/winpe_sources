# UnionFs::UfsStreamCtx::ReplaceBackingForSFOs(utl::shared_ptr<UnionFs::UfsLayerCtx>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x14002a6b8`
- end: `0x14002aaa3`
- name: `?ReplaceBackingForSFOs@UfsStreamCtx@UnionFs@@QEAAJV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `1003`
- prototype: `__int64 __fastcall(int, int, int, int, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140075fd8`

## callees

- `0x140005a8c`
- `0x14000f7fc`
- `0x14000ffb4`
- `0x140010148`
- `0x14002a6b8`
- `0x140056a50`
- `0x140056afc`
- `0x1400587e8`
- `0x140058a30`
- `0x1400799a4`
- `0x140079a6c`

## import_xrefs

- `ntoskrnl!FsRtlCurrentOplock` at `0x14002a7e0`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14002a7e0`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002a807`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002a807`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a760`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a760`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a861`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a8d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a99b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a861`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a8d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a99b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a86d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a8e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a9a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a86d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a8e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a9a7`
- `FLTMGR!FltFsControlFile` at `0x14002a932`
- `FLTMGR!FltFsControlFile` at `0x14002a932`

## string_xrefs

- `0x14002a9c4`: `UnionFs::UfsStreamCtx::ReplaceBackingForSFOs`
- `0x14002aa45`: `UnionFs::UfsStreamCtx::ReplaceBackingForSFOs`

## pseudocode

```c

```
