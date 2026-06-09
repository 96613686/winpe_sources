# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18001b360`
- end: `0x18001b377`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015e84`
- `0x18001b92c`
- `0x180023034`
- `0x180023708`
- `0x180023a04`
- `0x180024144`
- `0x180024dd0`
- `0x180025af0`

## callees

- `0x18001b360`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b36c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b36c`

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
0x18001b360  sub     rsp, 28h
0x18001b364  mov     rcx, [rcx]; pv
0x18001b367  test    rcx, rcx
0x18001b36a  jz      short loc_18001B372
0x18001b36c  call    cs:__imp_CoTaskMemFree
0x18001b372  add     rsp, 28h
0x18001b376  retn
```
