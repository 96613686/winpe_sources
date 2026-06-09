# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x1800253ec`
- end: `0x180025403`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800253e0`
- `0x180025944`
- `0x180025a10`
- `0x18002833c`
- `0x180029cb4`
- `0x18002a7a0`
- `0x18002afd4`
- `0x18002cec8`
- `0x18002d414`
- `0x18004cfc4`
- `0x18004d518`
- `0x180056188`

## callees

- `0x1800253ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800253f8`

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
0x1800253ec  sub     rsp, 28h
0x1800253f0  mov     rcx, [rcx]; pv
0x1800253f3  test    rcx, rcx
0x1800253f6  jz      short loc_1800253FE
0x1800253f8  call    cs:__imp_CoTaskMemFree
0x1800253fe  add     rsp, 28h
0x180025402  retn
```
