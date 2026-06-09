# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000b370`
- end: `0x18000b387`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004388`
- `0x18000b4a4`
- `0x18000d3ec`
- `0x18000daac`
- `0x18000ed24`
- `0x1800116b0`
- `0x180011890`
- `0x180011aa0`
- `0x180011ea0`
- `0x180011f10`
- `0x1800120d0`

## callees

- `0x18000b370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b37c`

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
0x18000b370  sub     rsp, 28h
0x18000b374  mov     rcx, [rcx]; pv
0x18000b377  test    rcx, rcx
0x18000b37a  jz      short loc_18000B382
0x18000b37c  call    cs:__imp_CoTaskMemFree
0x18000b382  add     rsp, 28h
0x18000b386  retn
```
