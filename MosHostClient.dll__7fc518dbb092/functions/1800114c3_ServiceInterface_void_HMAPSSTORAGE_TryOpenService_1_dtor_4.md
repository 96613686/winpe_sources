# _ServiceInterface_void___HMAPSSTORAGE_____::TryOpenService_::_1_::dtor$4

- ea: `0x1800114c3`
- end: `0x1800114cf`
- name: `_ServiceInterface_void___HMAPSSTORAGE_____::TryOpenService_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800091ec`

## pseudocode

```c
__int64 __fastcall ServiceInterface_void___HMAPSSTORAGE_____::TryOpenService_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x1800114c3  lea     rcx, [rdx+30h]
0x1800114ca  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
```
