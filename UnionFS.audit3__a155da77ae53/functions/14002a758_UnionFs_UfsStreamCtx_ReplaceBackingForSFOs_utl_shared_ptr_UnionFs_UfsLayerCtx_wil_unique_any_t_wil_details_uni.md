# UnionFs::UfsStreamCtx::ReplaceBackingForSFOs(utl::shared_ptr<UnionFs::UfsLayerCtx>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x14002a758`
- end: `0x14002ab43`
- name: `?ReplaceBackingForSFOs@UfsStreamCtx@UnionFs@@QEAAJV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `1003`
- prototype: `__int64 __fastcall(int, int, int, int, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400761d8`

## callees

- `0x140005a8c`
- `0x14000f81c`
- `0x14000ffd4`
- `0x140010168`
- `0x14002a758`
- `0x140056bd0`
- `0x140056c7c`
- `0x140058968`
- `0x140058bb0`
- `0x140079cc4`
- `0x140079d8c`

## import_xrefs

- `ntoskrnl!FsRtlCurrentOplock` at `0x14002a880`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14002a880`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002a8a7`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002a8a7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a800`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002a800`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a901`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a978`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002aa3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a901`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002a978`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002aa3b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a90d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a984`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002aa47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a90d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a984`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002aa47`
- `FLTMGR!FltFsControlFile` at `0x14002a9d2`
- `FLTMGR!FltFsControlFile` at `0x14002a9d2`

## string_xrefs

- `0x14002aa64`: `UnionFs::UfsStreamCtx::ReplaceBackingForSFOs`
- `0x14002aae5`: `UnionFs::UfsStreamCtx::ReplaceBackingForSFOs`

## pseudocode

```c

```
