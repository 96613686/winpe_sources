# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator&(void)

- ea: `0x14000ccd0`
- end: `0x14000cd1d`
- name: `??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ`
- size: `77`
- prototype: `HSTRING *__fastcall(HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140019a6c`

## callees

- `0x14000ccd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ccea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ccea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ccfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ccfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ccf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ccf5`

## pseudocode

```c
HSTRING *__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::operator&(
        HSTRING *a1)
{
  HSTRING v1; // rsi
  DWORD LastError; // ebx
  HSTRING *result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    WindowsDeleteString(v1);
    SetLastError(LastError);
  }
  result = a1;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x14000ccd0  mov     [rsp+arg_0], rbx
0x14000ccd5  mov     [rsp+arg_8], rsi
0x14000ccda  push    rdi
0x14000ccdb  sub     rsp, 20h
0x14000ccdf  mov     rsi, [rcx]
0x14000cce2  mov     rdi, rcx
0x14000cce5  test    rsi, rsi
0x14000cce8  jz      short loc_14000CD03
0x14000ccea  call    cs:__imp_GetLastError
0x14000ccf0  mov     rcx, rsi; string
0x14000ccf3  mov     ebx, eax
0x14000ccf5  call    cs:__imp_WindowsDeleteString
0x14000ccfb  mov     ecx, ebx; dwErrCode
0x14000ccfd  call    cs:__imp_SetLastError
0x14000cd03  mov     rbx, [rsp+28h+arg_0]
0x14000cd08  mov     rax, rdi
0x14000cd0b  mov     rsi, [rsp+28h+arg_8]
0x14000cd10  mov     qword ptr [rdi], 0
0x14000cd17  add     rsp, 20h
0x14000cd1b  pop     rdi
0x14000cd1c  retn
```
