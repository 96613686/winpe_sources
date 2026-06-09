# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18001f8c8`
- end: `0x18001f8df`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b9b0`
- `0x180026630`
- `0x18002711c`
- `0x180035110`
- `0x1800361e4`
- `0x1800367d0`
- `0x180036b70`
- `0x180037068`
- `0x1800377f0`
- `0x18004a394`
- `0x18004a680`
- `0x18004c768`
- `0x180055570`

## callees

- `0x18001f8c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f8d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f8d4`

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
0x18001f8c8  sub     rsp, 28h
0x18001f8cc  mov     rcx, [rcx]; pv
0x18001f8cf  test    rcx, rcx
0x18001f8d2  jz      short loc_18001F8DA
0x18001f8d4  call    cs:__imp_CoTaskMemFree
0x18001f8da  add     rsp, 28h
0x18001f8de  retn
```
