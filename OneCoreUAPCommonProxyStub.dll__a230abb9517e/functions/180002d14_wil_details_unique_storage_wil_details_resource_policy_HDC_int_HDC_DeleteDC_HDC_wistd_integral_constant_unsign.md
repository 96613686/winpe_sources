# wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>(void)

- ea: `0x180002d14`
- end: `0x180002d2b`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AHPEAU1@@Z$1?DeleteDC@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003800`

## callees

- `0x180002d14`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180002d20`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180002d20`

## pseudocode

```c
BOOL __fastcall wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>(
        HDC *a1)
{
  HDC v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return DeleteDC(v1);
  return result;
}

```

## disassembly

```asm
0x180002d14  sub     rsp, 28h
0x180002d18  mov     rcx, [rcx]; hdc
0x180002d1b  test    rcx, rcx
0x180002d1e  jz      short loc_180002D26
0x180002d20  call    cs:__imp_DeleteDC
0x180002d26  add     rsp, 28h
0x180002d2a  retn
```
