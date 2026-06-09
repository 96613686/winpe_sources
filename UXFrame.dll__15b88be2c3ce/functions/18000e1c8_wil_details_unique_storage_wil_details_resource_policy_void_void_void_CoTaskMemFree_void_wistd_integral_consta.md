# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000e1c8`
- end: `0x18000e1df`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cd7c`
- `0x18000e0f8`
- `0x18000ea44`
- `0x180013174`
- `0x180017eb8`
- `0x1800195b0`
- `0x180022958`
- `0x18002cf38`
- `0x18002d810`
- `0x18002e258`
- `0x1800303b8`
- `0x1800438c4`
- `0x180055d04`

## callees

- `0x18000e1c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1d4`

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
0x18000e1c8  sub     rsp, 28h
0x18000e1cc  mov     rcx, [rcx]; pv
0x18000e1cf  test    rcx, rcx
0x18000e1d2  jz      short loc_18000E1DA
0x18000e1d4  call    cs:__imp_CoTaskMemFree
0x18000e1da  add     rsp, 28h
0x18000e1de  retn
```
