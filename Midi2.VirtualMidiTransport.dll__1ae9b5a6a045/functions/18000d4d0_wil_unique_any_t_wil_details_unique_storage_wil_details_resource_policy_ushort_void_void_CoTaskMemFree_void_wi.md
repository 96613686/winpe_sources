# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x18000d4d0`
- end: `0x18000d4e7`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001feb1`
- `0x18001ff77`

## callees

- `0x18000d4d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4dc`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
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
0x18000d4d0  sub     rsp, 28h
0x18000d4d4  mov     rcx, [rcx]; pv
0x18000d4d7  test    rcx, rcx
0x18000d4da  jz      short loc_18000D4E2
0x18000d4dc  call    cs:__imp_CoTaskMemFree
0x18000d4e2  add     rsp, 28h
0x18000d4e6  retn
```
