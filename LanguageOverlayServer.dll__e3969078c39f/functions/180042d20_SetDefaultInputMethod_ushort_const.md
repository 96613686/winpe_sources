# SetDefaultInputMethod(ushort const *)

- ea: `0x180042d20`
- end: `0x180042e03`
- name: `?SetDefaultInputMethod@@YAJPEBG@Z`
- size: `227`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042460`

## callees

- `0x180003a00`
- `0x1800050b0`
- `0x180009064`
- `0x180009084`
- `0x180034b30`
- `0x180042d20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042de3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042de3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042d94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042d94`
- `ext-ms-win-globalization-input-l1-1-0!WGIGetDefaultInputMethodForLanguage` at `0x180042d81`
- `ext-ms-win-globalization-input-l1-1-0!WGIGetDefaultInputMethodForLanguage` at `0x180042d81`
- `ext-ms-win-tsf-inputsetting-l1-1-0!SetDefaultLayoutOrTip` at `0x180042d9f`
- `ext-ms-win-tsf-inputsetting-l1-1-0!SetDefaultLayoutOrTip` at `0x180042d9f`

## string_xrefs

- `0x180042dae`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`
- `0x180042dca`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deviceinternationalsettings.cpp`

## pseudocode

```c
__int64 __fastcall SetDefaultInputMethod(const unsigned __int16 *a1)
{
  unsigned int v1; // r8d
  int LastError; // ebx
  PVOID Reserved1; // rdi
  PCWSTR StringRawBuffer; // rax
  const char *v5; // r9
  HSTRING_HEADER v7; // [rsp+20h] [rbp-48h] BYREF
  const WCHAR *v8; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = a1;
  WindowsDeleteString(0);
  string = 0;
  LastError = -2147024769;
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v8, v1)[1].Reserved.Reserved1;
  if ( (unsigned __int8)IsWGIGetDefaultInputMethodForLanguagePresent()
    && (LastError = WGIGetDefaultInputMethodForLanguage(Reserved1, &string), LastError >= 0) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( (unsigned int)SetDefaultLayoutOrTip(StringRawBuffer, 0) )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x60,
                    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternati"
                                  "onalsettings.cpp",
                    v5);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deviceinternationalsettings.cpp",
      (const char *)(unsigned int)LastError,
      (int)v7.Reserved.Reserved1);
  }
  WindowsDeleteString(string);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180042d20  mov     [rsp+arg_8], rbx
0x180042d25  push    rdi
0x180042d26  sub     rsp, 60h
0x180042d2a  mov     rax, cs:__security_cookie
0x180042d31  xor     rax, rsp
0x180042d34  mov     [rsp+68h+var_18], rax
0x180042d39  mov     [rsp+68h+var_28], rcx
0x180042d3e  xor     ecx, ecx; string
0x180042d40  mov     [rsp+68h+string], 0
0x180042d49  call    cs:__imp_WindowsDeleteString
0x180042d4f  lea     rdx, [rsp+68h+var_28]
0x180042d54  mov     [rsp+68h+string], 0
0x180042d5d  lea     rcx, [rsp+68h+var_48]
0x180042d62  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180042d67  mov     ebx, 8007007Fh
0x180042d6c  mov     rdi, [rax+18h]
0x180042d70  call    IsWGIGetDefaultInputMethodForLanguagePresent
0x180042d75  test    al, al
0x180042d77  jz      short loc_180042DC5
0x180042d79  lea     rdx, [rsp+68h+string]
0x180042d7e  mov     rcx, rdi
0x180042d81  call    cs:__imp_WGIGetDefaultInputMethodForLanguage
0x180042d87  mov     ebx, eax
0x180042d89  test    eax, eax
0x180042d8b  js      short loc_180042DC5
0x180042d8d  mov     rcx, [rsp+68h+string]; string
0x180042d92  xor     edx, edx; length
0x180042d94  call    cs:__imp_WindowsGetStringRawBuffer
0x180042d9a  mov     rcx, rax
0x180042d9d  xor     edx, edx
0x180042d9f  call    cs:__imp_SetDefaultLayoutOrTip
0x180042da5  test    eax, eax
0x180042da7  jnz     short loc_180042DC1
0x180042da9  mov     rcx, [rsp+68h]; this
0x180042dae  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042db5  lea     edx, [rax+60h]; void *
0x180042db8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042dbd  mov     ebx, eax
0x180042dbf  jmp     short loc_180042DDE
0x180042dc1  xor     ebx, ebx
0x180042dc3  jmp     short loc_180042DDE
0x180042dc5  mov     rcx, [rsp+68h]; this
0x180042dca  lea     r8, aOnecoreBaseLan_19; "onecore\\base\\languageoverlay\\service"...
0x180042dd1  mov     r9d, ebx; char *
0x180042dd4  mov     edx, 5Bh ; '['; void *
0x180042dd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042dde  mov     rcx, [rsp+68h+string]; string
0x180042de3  call    cs:__imp_WindowsDeleteString
0x180042de9  mov     eax, ebx
0x180042deb  mov     rcx, [rsp+68h+var_18]
0x180042df0  xor     rcx, rsp; StackCookie
0x180042df3  call    __security_check_cookie
0x180042df8  mov     rbx, [rsp+68h+arg_8]
0x180042dfd  add     rsp, 60h
0x180042e01  pop     rdi
0x180042e02  retn
```
