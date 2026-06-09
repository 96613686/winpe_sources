# _ReplaceOOPBitmaps_::_1_::dtor$0

- ea: `0x18000b290`
- end: `0x18000b29c`
- name: `_ReplaceOOPBitmaps_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003800`

## pseudocode

```c
BOOL __fastcall ReplaceOOPBitmaps_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>((HDC *)(a2 + 80));
}

```

## disassembly

```asm
0x18000b290  lea     rcx, [rdx+50h]
0x18000b297  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AHPEAU1@@Z$1?DeleteDC@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>(void)
```
