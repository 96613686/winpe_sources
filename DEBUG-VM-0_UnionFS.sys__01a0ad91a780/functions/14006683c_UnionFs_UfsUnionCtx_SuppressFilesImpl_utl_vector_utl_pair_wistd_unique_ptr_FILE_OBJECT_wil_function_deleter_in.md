# UnionFs::UfsUnionCtx::SuppressFilesImpl(utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>> &,utl::vector<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,utl::allocator<utl::pair<wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>>> &,utl::vector<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsPathCachePayload>>> &,utl::vector<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>,utl::allocator<utl::unique_ptr<UnionFs::CollapseContext,utl::default_delete<UnionFs::CollapseContext>>>> &,bool,UnionFs::StackEventTracer &)

- ea: `0x14006683c`
- end: `0x140066af0`
- name: `?SuppressFilesImpl@UfsUnionCtx@UnionFs@@AEAAJAEAV?$vector@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@utl@@@2@@utl@@0AEAV?$vector@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@2@@4@AEAV?$vector@V?$unique_ptr@UCollapseContext@UnionFs@@U?$default_delete@UCollapseContext@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UCollapseContext@UnionFs@@U?$default_delete@UCollapseContext@UnionFs@@@utl@@@utl@@@2@@4@_NAEAVStackEventTracer@2@@Z`
- size: `692`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x140065798`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x14000f81c`
- `0x14003d79c`
- `0x140042328`
- `0x140056974`
- `0x140056bd0`
- `0x140056c7c`
- `0x14005dadc`
- `0x14006683c`
- `0x140079d44`
- `0x14007a0c0`
- `0x14007baf0`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x140066904`
- `FLTMGR!FltSetInformationFile` at `0x1400669c6`
- `FLTMGR!FltSetInformationFile` at `0x140066904`
- `FLTMGR!FltSetInformationFile` at `0x1400669c6`
- `FLTMGR!FltClose` at `0x140066947`
- `FLTMGR!FltClose` at `0x140066947`

## string_xrefs

- `0x14006691c`: `API: Setting delete on close on scratch file`
- `0x1400669d6`: `API: Setting delete on close on scratch directory`

## pseudocode

```c

```
