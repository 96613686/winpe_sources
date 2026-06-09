# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x18000e530`
- end: `0x18000e547`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000edb4`
- `0x180016400`
- `0x180016718`
- `0x1800183dc`
- `0x180018ac4`
- `0x180019ba6`
- `0x180019bca`
- `0x180019ff4`
- `0x18001a03c`
- `0x18001a04e`

## callees

- `0x18000e530`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e53c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e53c`

## pseudocode

```c
HLOCAL __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
        void **a1)
{
  void *v1; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( v1 )
    return LocalFree(v1);
  return result;
}

```

## disassembly

```asm
0x18000e530  sub     rsp, 28h
0x18000e534  mov     rcx, [rcx]; hMem
0x18000e537  test    rcx, rcx
0x18000e53a  jz      short loc_18000E542
0x18000e53c  call    cs:__imp_LocalFree
0x18000e542  add     rsp, 28h
0x18000e546  retn
```
