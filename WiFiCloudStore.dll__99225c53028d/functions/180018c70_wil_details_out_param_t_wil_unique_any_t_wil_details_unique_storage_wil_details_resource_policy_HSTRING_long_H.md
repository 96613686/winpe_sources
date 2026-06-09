# wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)

- ea: `0x180018c70`
- end: `0x180018cd4`
- name: `??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003e4d0`

## callees

- `0x180018c70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018cc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018cbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018cbf`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        __int64 a1)
{
  HSTRING v1; // rsi
  HSTRING *v2; // rdi
  HSTRING v3; // rbp
  DWORD LastError; // ebx

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = *(HSTRING *)(a1 + 8);
    v2 = *(HSTRING **)a1;
    v3 = **(HSTRING **)a1;
    if ( v3 )
    {
      LastError = GetLastError();
      WindowsDeleteString(v3);
      SetLastError(LastError);
    }
    *v2 = v1;
  }
}

```

## disassembly

```asm
0x180018c70  sub     rsp, 28h
0x180018c74  cmp     byte ptr [rcx+10h], 0
0x180018c78  jz      short loc_180018CAA
0x180018c7a  mov     [rsp+28h+arg_8], rbp
0x180018c7f  mov     [rsp+28h+arg_10], rsi
0x180018c84  mov     rsi, [rcx+8]
0x180018c88  mov     [rsp+28h+var_8], rdi
0x180018c8d  mov     rdi, [rcx]
0x180018c90  mov     rbp, [rdi]
0x180018c93  test    rbp, rbp
0x180018c96  jnz     short loc_180018CAF
0x180018c98  mov     rbp, [rsp+28h+arg_8]
0x180018c9d  mov     [rdi], rsi
0x180018ca0  mov     rdi, [rsp+28h+var_8]
0x180018ca5  mov     rsi, [rsp+28h+arg_10]
0x180018caa  add     rsp, 28h
0x180018cae  retn
0x180018caf  mov     [rsp+28h+arg_0], rbx
0x180018cb4  call    cs:__imp_GetLastError
0x180018cba  mov     rcx, rbp; string
0x180018cbd  mov     ebx, eax
0x180018cbf  call    cs:__imp_WindowsDeleteString
0x180018cc5  mov     ecx, ebx; dwErrCode
0x180018cc7  call    cs:__imp_SetLastError
0x180018ccd  mov     rbx, [rsp+28h+arg_0]
0x180018cd2  jmp     short loc_180018C98
```
