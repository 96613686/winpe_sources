# wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1400189a8`
- end: `0x1400189bf`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `PVOID __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400189c8`

## callees

- `0x1400189a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400189b4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400189b4`

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
0x1400189a8  sub     rsp, 28h
0x1400189ac  mov     rcx, [rcx]; pSid
0x1400189af  test    rcx, rcx
0x1400189b2  jz      short loc_1400189BA
0x1400189b4  call    cs:__imp_FreeSid
0x1400189ba  add     rsp, 28h
0x1400189be  retn
```
