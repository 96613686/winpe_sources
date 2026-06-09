# wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)

- ea: `0x1800113ec`
- end: `0x180011439`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a3ec`
- `0x180010c08`
- `0x18001121c`
- `0x180012f64`

## callees

- `0x1800047c4`
- `0x180004e40`
- `0x1800113ec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011416`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        HSTRING *a1,
        HSTRING a2)
{
  HSTRING v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    WindowsDeleteString(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800113ec  mov     [rsp+arg_8], rbx
0x1800113f1  mov     [rsp+arg_10], rsi
0x1800113f6  push    rdi
0x1800113f7  sub     rsp, 20h
0x1800113fb  mov     rdi, [rcx]
0x1800113fe  mov     rsi, rdx
0x180011401  mov     rbx, rcx
0x180011404  test    rdi, rdi
0x180011407  jz      short loc_180011426
0x180011409  lea     rcx, [rsp+28h+arg_0]; this
0x18001140e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011413  mov     rcx, rdi; string
0x180011416  call    cs:__imp_WindowsDeleteString
0x18001141c  lea     rcx, [rsp+28h+arg_0]; this
0x180011421  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011426  mov     [rbx], rsi
0x180011429  mov     rbx, [rsp+28h+arg_8]
0x18001142e  mov     rsi, [rsp+28h+arg_10]
0x180011433  add     rsp, 20h
0x180011437  pop     rdi
0x180011438  retn
```
