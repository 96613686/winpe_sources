# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x180006cb0`
- end: `0x180006cc7`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000edea`

## callees

- `0x180006cb0`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180006cbc`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180006cbc`

## pseudocode

```c
__int64 __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return FreeTransientObjectSecurityDescriptor();
  return result;
}

```

## disassembly

```asm
0x180006cb0  sub     rsp, 28h
0x180006cb4  mov     rcx, [rcx]
0x180006cb7  test    rcx, rcx
0x180006cba  jz      short loc_180006CC2
0x180006cbc  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180006cc2  add     rsp, 28h
0x180006cc6  retn
```
