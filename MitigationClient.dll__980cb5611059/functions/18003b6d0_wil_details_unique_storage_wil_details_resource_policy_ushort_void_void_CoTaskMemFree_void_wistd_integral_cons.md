# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x18003b6d0`
- end: `0x18003b6e7`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e2cc`
- `0x18004e444`
- `0x18004ec30`
- `0x18004ed34`
- `0x18004edd8`
- `0x18004fcac`
- `0x18004fe98`

## callees

- `0x18003b6d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b6dc`

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
0x18003b6d0  sub     rsp, 28h
0x18003b6d4  mov     rcx, [rcx]; pv
0x18003b6d7  test    rcx, rcx
0x18003b6da  jz      short loc_18003B6E2
0x18003b6dc  call    cs:__imp_CoTaskMemFree
0x18003b6e2  add     rsp, 28h
0x18003b6e6  retn
```
