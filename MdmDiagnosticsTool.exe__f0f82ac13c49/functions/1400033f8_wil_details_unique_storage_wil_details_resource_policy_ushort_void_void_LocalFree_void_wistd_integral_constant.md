# wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x1400033f8`
- end: `0x14000340f`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002168`
- `0x140003370`
- `0x140004a60`
- `0x140005b1c`
- `0x140007cf4`

## callees

- `0x1400033f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140003404`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140003404`

## pseudocode

```c
HLOCAL __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
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
0x1400033f8  sub     rsp, 28h
0x1400033fc  mov     rcx, [rcx]; hMem
0x1400033ff  test    rcx, rcx
0x140003402  jz      short loc_14000340A
0x140003404  call    cs:__imp_LocalFree
0x14000340a  add     rsp, 28h
0x14000340e  retn
```
