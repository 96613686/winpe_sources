# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x180008930`
- end: `0x180008947`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000cd87`
- `0x18000cdcf`
- `0x18000ce8a`

## callees

- `0x180008930`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000893c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000893c`

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
0x180008930  sub     rsp, 28h
0x180008934  mov     rcx, [rcx]; hMem
0x180008937  test    rcx, rcx
0x18000893a  jz      short loc_180008942
0x18000893c  call    cs:__imp_LocalFree
0x180008942  add     rsp, 28h
0x180008946  retn
```
