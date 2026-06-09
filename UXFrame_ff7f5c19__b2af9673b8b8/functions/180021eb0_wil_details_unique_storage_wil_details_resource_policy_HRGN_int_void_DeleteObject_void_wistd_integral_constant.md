# wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>(void)

- ea: `0x180021eb0`
- end: `0x180021ec7`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHRGN__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180028940`

## callees

- `0x180021eb0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180021ebc`
- `GDI32!DeleteObject` at `0x180021ebc`

## pseudocode

```c
BOOL __fastcall wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>(
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
0x180021eb0  sub     rsp, 28h
0x180021eb4  mov     rcx, [rcx]; ho
0x180021eb7  test    rcx, rcx
0x180021eba  jz      short loc_180021EC2
0x180021ebc  call    cs:__imp_DeleteObject
0x180021ec2  add     rsp, 28h
0x180021ec6  retn
```
