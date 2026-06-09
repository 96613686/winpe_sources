# _CreateBitMapFileMapping_::_1_::dtor$0

- ea: `0x18000b210`
- end: `0x18000b21c`
- name: `_CreateBitMapFileMapping_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003800`

## pseudocode

```c
BOOL __fastcall CreateBitMapFileMapping_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>((HDC *)(a2 + 64));
}

```

## disassembly

```asm
0x18000b210  lea     rcx, [rdx+40h]
0x18000b217  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AHPEAU1@@Z$1?DeleteDC@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>(void)
```
