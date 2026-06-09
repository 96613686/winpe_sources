# wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180008e24`
- end: `0x180008e3b`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `PVOID __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008df4`
- `0x1800094d4`

## callees

- `0x180008e24`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008e30`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008e30`

## pseudocode

```c
PVOID __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  PVOID result; // rax

  v1 = *a1;
  if ( v1 )
    return FreeSid(v1);
  return result;
}

```

## disassembly

```asm
0x180008e24  sub     rsp, 28h
0x180008e28  mov     rcx, [rcx]; pSid
0x180008e2b  test    rcx, rcx
0x180008e2e  jz      short loc_180008E36
0x180008e30  call    cs:__imp_FreeSid
0x180008e36  add     rsp, 28h
0x180008e3a  retn
```
