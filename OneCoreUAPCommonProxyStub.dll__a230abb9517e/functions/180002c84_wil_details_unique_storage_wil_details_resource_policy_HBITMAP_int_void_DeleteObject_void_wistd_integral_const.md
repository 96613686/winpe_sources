# wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(void)

- ea: `0x180002c84`
- end: `0x180002c9b`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHBITMAP__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003838`
- `0x180006a58`

## callees

- `0x180002c84`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180002c90`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180002c90`

## pseudocode

```c
BOOL __fastcall wil::details::unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HBITMAP__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HBITMAP__ *,HBITMAP__ *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return DeleteObject(v1);
  return result;
}

```

## disassembly

```asm
0x180002c84  sub     rsp, 28h
0x180002c88  mov     rcx, [rcx]; ho
0x180002c8b  test    rcx, rcx
0x180002c8e  jz      short loc_180002C96
0x180002c90  call    cs:__imp_DeleteObject
0x180002c96  add     rsp, 28h
0x180002c9a  retn
```
