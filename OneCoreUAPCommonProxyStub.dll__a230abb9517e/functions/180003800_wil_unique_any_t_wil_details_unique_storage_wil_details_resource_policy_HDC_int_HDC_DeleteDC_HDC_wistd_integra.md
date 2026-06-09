# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>(void)

- ea: `0x180003800`
- end: `0x180003805`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AHPEAU1@@Z$1?DeleteDC@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b210`
- `0x18000b290`

## callees

- `0x180002d14`

## pseudocode

```c
// attributes: thunk
BOOL __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>>(
        HDC *a1)
{
  return wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&int DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>(a1);
}

```

## disassembly

```asm
0x180003800  jmp     ??1?$unique_storage@U?$resource_policy@PEAUHDC__@@P6AHPEAU1@@Z$1?DeleteDC@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HDC__ *,int (*)(HDC__ *),&DeleteDC(HDC__ *),wistd::integral_constant<unsigned __int64,0>,HDC__ *,HDC__ *,0,std::nullptr_t>>(void)
```
