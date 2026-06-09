# wil::details::unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>(void)

- ea: `0x14000c6b4`
- end: `0x14000c6cb`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHFONT__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000ef30`

## callees

- `0x14000c6b4`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x14000c6c0`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x14000c6c0`

## pseudocode

```c
BOOL __fastcall wil::details::unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HFONT__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HFONT__ *,HFONT__ *,0,std::nullptr_t>>(
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
0x14000c6b4  sub     rsp, 28h
0x14000c6b8  mov     rcx, [rcx]; ho
0x14000c6bb  test    rcx, rcx
0x14000c6be  jz      short loc_14000C6C6
0x14000c6c0  call    cs:__imp_DeleteObject
0x14000c6c6  add     rsp, 28h
0x14000c6ca  retn
```
