# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x180005100`
- end: `0x180005117`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004924`
- `0x180009928`
- `0x18000a504`
- `0x18000a5d0`
- `0x180010f48`
- `0x18001492c`
- `0x180014f90`
- `0x18001503c`
- `0x180015358`
- `0x1800173ac`
- `0x18002615c`
- `0x180033d80`
- `0x1800350a8`
- `0x180036cd8`
- `0x18004216b`
- `0x18004218f`
- `0x1800425eb`
- `0x180042928`
- `0x18004293e`
- `0x180042954`
- `0x180043c9d`

## callees

- `0x180005100`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000510c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000510c`

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
0x180005100  sub     rsp, 28h
0x180005104  mov     rcx, [rcx]; pv
0x180005107  test    rcx, rcx
0x18000510a  jz      short loc_180005112
0x18000510c  call    cs:__imp_CoTaskMemFree
0x180005112  add     rsp, 28h
0x180005116  retn
```
