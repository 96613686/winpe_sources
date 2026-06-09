# wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)

- ea: `0x1800a6590`
- end: `0x1800a65a7`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `HRESULT __fastcall(HSTRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800a6584`
- `0x1800a7810`
- `0x1800a7b10`

## callees

- `0x1800a6590`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a659c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a659c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(
        HSTRING *a1)
{
  HSTRING v1; // rcx
  HRESULT result; // eax

  v1 = *a1;
  if ( v1 )
    return WindowsDeleteString(v1);
  return result;
}

```

## disassembly

```asm
0x1800a6590  sub     rsp, 28h
0x1800a6594  mov     rcx, [rcx]; string
0x1800a6597  test    rcx, rcx
0x1800a659a  jz      short loc_1800A65A2
0x1800a659c  call    cs:__imp_WindowsDeleteString
0x1800a65a2  add     rsp, 28h
0x1800a65a6  retn
```
