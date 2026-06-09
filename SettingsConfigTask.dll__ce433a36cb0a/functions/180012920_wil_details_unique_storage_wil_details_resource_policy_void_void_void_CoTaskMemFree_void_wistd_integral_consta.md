# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180012920`
- end: `0x180012937`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cad0`
- `0x18000fff8`
- `0x1800128d8`
- `0x180012ce8`
- `0x1800194b4`
- `0x18001d3f0`
- `0x18001de88`
- `0x18001dfc0`
- `0x18001e4bc`
- `0x18001e6f8`
- `0x18001efd4`
- `0x18001f51c`
- `0x18001fd2c`
- `0x180020e54`
- `0x180020f74`

## callees

- `0x180012920`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001292c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001292c`

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
0x180012920  sub     rsp, 28h
0x180012924  mov     rcx, [rcx]; pv
0x180012927  test    rcx, rcx
0x18001292a  jz      short loc_180012932
0x18001292c  call    cs:__imp_CoTaskMemFree
0x180012932  add     rsp, 28h
0x180012936  retn
```
