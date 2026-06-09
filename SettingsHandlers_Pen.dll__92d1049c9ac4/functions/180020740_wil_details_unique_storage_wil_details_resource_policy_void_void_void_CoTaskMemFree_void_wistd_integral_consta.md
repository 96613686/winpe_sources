# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180020740`
- end: `0x180020757`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020678`
- `0x18002668c`
- `0x18002674c`
- `0x18002c1d0`
- `0x18002c3c8`
- `0x18003f068`
- `0x1800414a0`
- `0x1800416a8`
- `0x180042b14`

## callees

- `0x180020740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002074c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002074c`

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
0x180020740  sub     rsp, 28h
0x180020744  mov     rcx, [rcx]; pv
0x180020747  test    rcx, rcx
0x18002074a  jz      short loc_180020752
0x18002074c  call    cs:__imp_CoTaskMemFree
0x180020752  add     rsp, 28h
0x180020756  retn
```
