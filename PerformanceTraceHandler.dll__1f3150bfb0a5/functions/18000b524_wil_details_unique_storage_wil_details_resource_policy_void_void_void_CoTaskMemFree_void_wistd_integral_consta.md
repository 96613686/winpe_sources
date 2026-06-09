# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000b524`
- end: `0x18000b53b`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b698`
- `0x18000d5ec`
- `0x18001012c`
- `0x180010af0`
- `0x180011bd4`
- `0x180011e50`
- `0x1800120b8`
- `0x180012ec0`
- `0x180013540`
- `0x180016a30`
- `0x180016b6c`
- `0x180017834`
- `0x18001874c`

## callees

- `0x18000b524`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b530`

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
0x18000b524  sub     rsp, 28h
0x18000b528  mov     rcx, [rcx]; pv
0x18000b52b  test    rcx, rcx
0x18000b52e  jz      short loc_18000B536
0x18000b530  call    cs:__imp_CoTaskMemFree
0x18000b536  add     rsp, 28h
0x18000b53a  retn
```
