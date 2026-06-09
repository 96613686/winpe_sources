# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x1800091ec`
- end: `0x180009203`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800114c3`

## callees

- `0x1800091ec`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800091f8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800091f8`

## pseudocode

```c
__int64 __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return FreeTransientObjectSecurityDescriptor(v1);
  return result;
}

```

## disassembly

```asm
0x1800091ec  sub     rsp, 28h
0x1800091f0  mov     rcx, [rcx]
0x1800091f3  test    rcx, rcx
0x1800091f6  jz      short loc_1800091FE
0x1800091f8  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800091fe  add     rsp, 28h
0x180009202  retn
```
