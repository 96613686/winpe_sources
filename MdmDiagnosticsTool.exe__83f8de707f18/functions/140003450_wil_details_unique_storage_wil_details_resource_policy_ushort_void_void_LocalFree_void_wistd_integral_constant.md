# wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x140003450`
- end: `0x14000346e`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400021bc`
- `0x1400033b8`
- `0x140004d3c`
- `0x140005e44`
- `0x14000812c`

## callees

- `0x140003450`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000345c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000345c`

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
0x140003450  sub     rsp, 28h
0x140003454  mov     rcx, [rcx]; hMem
0x140003457  test    rcx, rcx
0x14000345a  jz      short loc_140003468
0x14000345c  call    cs:__imp_LocalFree
0x140003463  nop     dword ptr [rax+rax+00h]
0x140003468  add     rsp, 28h
0x14000346c  retn
```
