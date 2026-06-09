# wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000f610`
- end: `0x18000f627`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `NTSTATUS __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f864`

## callees

- `0x18000f610`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000f61c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000f61c`

## pseudocode

```c
NTSTATUS __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  NTSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return LsaClose(v1);
  return result;
}

```

## disassembly

```asm
0x18000f610  sub     rsp, 28h
0x18000f614  mov     rcx, [rcx]; ObjectHandle
0x18000f617  test    rcx, rcx
0x18000f61a  jz      short loc_18000F622
0x18000f61c  call    cs:__imp_LsaClose
0x18000f622  add     rsp, 28h
0x18000f626  retn
```
