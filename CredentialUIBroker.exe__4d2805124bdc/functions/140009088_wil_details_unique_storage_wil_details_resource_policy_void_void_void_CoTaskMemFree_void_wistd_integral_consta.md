# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x140009088`
- end: `0x14000909f`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000980c`
- `0x140019320`
- `0x140019650`
- `0x14001b938`
- `0x14001dc30`

## callees

- `0x140009088`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009094`

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
0x140009088  sub     rsp, 28h
0x14000908c  mov     rcx, [rcx]; pv
0x14000908f  test    rcx, rcx
0x140009092  jz      short loc_14000909A
0x140009094  call    cs:__imp_CoTaskMemFree
0x14000909a  add     rsp, 28h
0x14000909e  retn
```
