# wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180026758`
- end: `0x18002676f`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001218c`

## callees

- `0x180026758`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026764`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180026764`

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
0x180026758  sub     rsp, 28h
0x18002675c  mov     rcx, [rcx]; pSid
0x18002675f  test    rcx, rcx
0x180026762  jz      short loc_18002676A
0x180026764  call    cs:__imp_FreeSid
0x18002676a  add     rsp, 28h
0x18002676e  retn
```
