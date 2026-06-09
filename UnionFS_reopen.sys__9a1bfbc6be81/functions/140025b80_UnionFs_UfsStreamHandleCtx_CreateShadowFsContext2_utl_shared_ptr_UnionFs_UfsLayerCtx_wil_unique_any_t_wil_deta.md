# UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2(utl::shared_ptr<UnionFs::UfsLayerCtx> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &&,utl::unique_ptr<UnionFs::UfsFsContext2,utl::default_delete<UnionFs::UfsFsContext2>> &,UnionFs::StackEventTracer &)

- ea: `0x140025b80`
- end: `0x140025d41`
- name: `?CreateShadowFsContext2@UfsStreamHandleCtx@UnionFs@@QEAAJ$$QEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAV?$unique_ptr@VUfsFsContext2@UnionFs@@U?$default_delete@VUfsFsContext2@UnionFs@@@utl@@@4@AEAVStackEventTracer@2@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140058fbc`

## callees

- `0x14000f7fc`
- `0x140024bd8`
- `0x140025b80`
- `0x14002ab18`
- `0x140056ac4`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025bc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025cb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025bc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025cb3`
- `ntoskrnl!ExAllocatePool2` at `0x140025bf3`
- `ntoskrnl!ExAllocatePool2` at `0x140025bf3`

## string_xrefs

- `0x140025d15`: `UnionFs::UfsStreamHandleCtx::CreateShadowFsContext2`

## pseudocode

```c

```
