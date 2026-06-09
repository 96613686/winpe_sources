# wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180069b0c`
- end: `0x180069b2a`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006cdd4`
- `0x18006cf10`

## callees

- `0x180069b0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180069b18`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180069b18`

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
0x180069b0c  sub     rsp, 28h
0x180069b10  mov     rcx, [rcx]; pSid
0x180069b13  test    rcx, rcx
0x180069b16  jz      short loc_180069B24
0x180069b18  call    cs:__imp_FreeSid
0x180069b1f  nop     dword ptr [rax+rax+00h]
0x180069b24  add     rsp, 28h
0x180069b28  retn
```
