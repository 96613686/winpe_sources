# UnionFs::UfsFsContext2::ReplaceBacking(utl::shared_ptr<UnionFs::UfsLayerCtx>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140058788`
- end: `0x14005895f`
- name: `?ReplaceBacking@UfsFsContext2@UnionFs@@QEAAJV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140058968`

## callees

- `0x14000f81c`
- `0x140056bd0`
- `0x140058788`
- `0x140079cfc`
- `0x14007a094`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ZwDuplicateObject` at `0x1400587dc`
- `ntoskrnl!ZwDuplicateObject` at `0x1400587dc`
- `ntoskrnl!ZwClose` at `0x140058824`
- `ntoskrnl!ZwClose` at `0x1400588e2`
- `ntoskrnl!ZwClose` at `0x14005892f`
- `ntoskrnl!ZwClose` at `0x140058824`
- `ntoskrnl!ZwClose` at `0x1400588e2`
- `ntoskrnl!ZwClose` at `0x14005892f`
- `ntoskrnl!ObfReferenceObject` at `0x140058848`
- `ntoskrnl!ObfReferenceObject` at `0x140058848`
- `ntoskrnl!ObfDereferenceObject` at `0x140058919`
- `ntoskrnl!ObfDereferenceObject` at `0x140058919`

## string_xrefs

- `0x1400587fd`: `UnionFs::UfsFsContext2::ReplaceBacking`

## pseudocode

```c

```
