# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)

- ea: `0x1800186b0`
- end: `0x1800186f7`
- name: `?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016540`
- `0x1800169d8`

## callees

- `0x1800050ac`
- `0x18000593c`
- `0x1800186b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800186d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800186d2`

## pseudocode

```c
HSTRING *__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(
        HSTRING *a1)
{
  HSTRING v1; // rdi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v4);
    WindowsDeleteString(v1);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v4);
  }
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x1800186b0  mov     [rsp+arg_8], rbx
0x1800186b5  push    rdi
0x1800186b6  sub     rsp, 20h
0x1800186ba  mov     rdi, [rcx]
0x1800186bd  mov     rbx, rcx
0x1800186c0  test    rdi, rdi
0x1800186c3  jz      short loc_1800186E2
0x1800186c5  lea     rcx, [rsp+28h+arg_0]; this
0x1800186ca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800186cf  mov     rcx, rdi; string
0x1800186d2  call    cs:__imp_WindowsDeleteString
0x1800186d8  lea     rcx, [rsp+28h+arg_0]; this
0x1800186dd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800186e2  mov     qword ptr [rbx], 0
0x1800186e9  mov     rax, rbx
0x1800186ec  mov     rbx, [rsp+28h+arg_8]
0x1800186f1  add     rsp, 20h
0x1800186f5  pop     rdi
0x1800186f6  retn
```
