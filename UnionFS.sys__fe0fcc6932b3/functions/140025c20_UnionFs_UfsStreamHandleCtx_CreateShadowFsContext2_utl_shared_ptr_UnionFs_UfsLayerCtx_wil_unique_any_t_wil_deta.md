# UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2(utl::shared_ptr<UnionFs::UfsLayerCtx> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &&,utl::unique_ptr<UnionFs::UfsFsContext2,utl::default_delete<UnionFs::UfsFsContext2>> &,UnionFs::StackEventTracer &)

- ea: `0x140025c20`
- end: `0x140025de1`
- name: `?CreateShadowFsContext2@UfsStreamHandleCtx@UnionFs@@QEAAJ$$QEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAV?$unique_ptr@VUfsFsContext2@UnionFs@@U?$default_delete@VUfsFsContext2@UnionFs@@@utl@@@4@AEAVStackEventTracer@2@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14005913c`

## callees

- `0x14000f81c`
- `0x140024c78`
- `0x140025c20`
- `0x14002abb8`
- `0x140056c44`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025c61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025c61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025d53`
- `ntoskrnl!ExAllocatePool2` at `0x140025c93`
- `ntoskrnl!ExAllocatePool2` at `0x140025c93`

## string_xrefs

- `0x140025db5`: `UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2`

## pseudocode

```c

```
