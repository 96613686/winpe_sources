# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x1800182cc`
- end: `0x1800182e3`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800182b4`
- `0x1800229ac`
- `0x180022ef0`
- `0x180026f64`
- `0x180027f60`
- `0x1800296a0`
- `0x18002b4d0`

## callees

- `0x1800182cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800182d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800182cc  sub     rsp, 28h
0x1800182d0  mov     rcx, [rcx]; pv
0x1800182d3  test    rcx, rcx
0x1800182d6  jz      short loc_1800182DE
0x1800182d8  call    cs:__imp_CoTaskMemFree
0x1800182de  add     rsp, 28h
0x1800182e2  retn
```
