# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x1800094f4`
- end: `0x18000950b`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d100`
- `0x18000d490`
- `0x18000d7d0`

## callees

- `0x1800094f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009500`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
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
0x1800094f4  sub     rsp, 28h
0x1800094f8  mov     rcx, [rcx]; pv
0x1800094fb  test    rcx, rcx
0x1800094fe  jz      short loc_180009506
0x180009500  call    cs:__imp_CoTaskMemFree
0x180009506  add     rsp, 28h
0x18000950a  retn
```
