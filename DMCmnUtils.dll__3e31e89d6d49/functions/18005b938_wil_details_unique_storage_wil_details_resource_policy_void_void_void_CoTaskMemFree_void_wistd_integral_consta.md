# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18005b938`
- end: `0x18005b956`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180071b24`
- `0x180074bf8`
- `0x1800787f0`
- `0x180078c24`
- `0x180079ce4`

## callees

- `0x18005b938`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b944`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18005b938  sub     rsp, 28h
0x18005b93c  mov     rcx, [rcx]; pv
0x18005b93f  test    rcx, rcx
0x18005b942  jz      short loc_18005B950
0x18005b944  call    cs:__imp_CoTaskMemFree
0x18005b94b  nop     dword ptr [rax+rax+00h]
0x18005b950  add     rsp, 28h
0x18005b954  retn
```
