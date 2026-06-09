# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x180008fa8`
- end: `0x180008fbf`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c1ec`
- `0x18000c2b8`
- `0x18000c4f1`

## callees

- `0x180008fa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fb4`

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
0x180008fa8  sub     rsp, 28h
0x180008fac  mov     rcx, [rcx]; pv
0x180008faf  test    rcx, rcx
0x180008fb2  jz      short loc_180008FBA
0x180008fb4  call    cs:__imp_CoTaskMemFree
0x180008fba  add     rsp, 28h
0x180008fbe  retn
```
