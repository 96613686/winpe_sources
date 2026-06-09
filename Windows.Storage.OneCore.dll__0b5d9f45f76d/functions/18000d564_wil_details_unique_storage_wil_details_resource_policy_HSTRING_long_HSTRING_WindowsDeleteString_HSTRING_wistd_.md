# wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)

- ea: `0x18000d564`
- end: `0x18000d57b`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `HRESULT __fastcall(HSTRING *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a3ec`
- `0x18000d434`
- `0x18000d48c`
- `0x18000f5cc`
- `0x180012f64`
- `0x1800137e8`

## callees

- `0x18000d564`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d570`

## pseudocode

```c
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
0x18000d564  sub     rsp, 28h
0x18000d568  mov     rcx, [rcx]; string
0x18000d56b  test    rcx, rcx
0x18000d56e  jz      short loc_18000D576
0x18000d570  call    cs:__imp_WindowsDeleteString
0x18000d576  add     rsp, 28h
0x18000d57a  retn
```
