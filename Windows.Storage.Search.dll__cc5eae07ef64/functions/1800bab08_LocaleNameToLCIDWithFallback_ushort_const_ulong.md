# LocaleNameToLCIDWithFallback(ushort const *,ulong)

- ea: `0x1800bab08`
- end: `0x1800bac23`
- name: `?LocaleNameToLCIDWithFallback@@YAKPEBGK@Z`
- size: `283`
- prototype: `unsigned int __fastcall(PCWSTR sourceString, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ba670`

## callees

- `0x180071dc0`
- `0x1800bab08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bab9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bac1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bab9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bac1c`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800bab2b`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800babca`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800bab2b`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800babca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bab87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bab87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800babbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800babbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bab44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800babd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bab44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800babd7`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x1800babae`
- `Bcp47Langs!Bcp47GetNlsForm` at `0x1800babae`

## pseudocode

```c
__int64 __fastcall LocaleNameToLCIDWithFallback(PCWSTR sourceString)
{
  LCID v2; // ebx
  unsigned __int64 v3; // rdx
  HRESULT v4; // eax
  const WCHAR *StringRawBuffer; // rax
  HSTRING v7; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  HSTRING string; // [rsp+40h] [rbp-18h] BYREF

  v2 = LocaleNameToLCID(sourceString, 0);
  if ( !v2 )
  {
    WindowsDeleteString(0);
    v3 = -1;
    v7 = 0;
    string = 0;
    do
      ++v3;
    while ( sourceString[v3] );
    if ( v3 > 0xFFFFFFFF || (int)v3 + 1 < (unsigned int)v3 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      JUMPOUT(0x1800BAC22LL);
    }
    v4 = WindowsCreateStringReference(sourceString, v3, &hstringHeader, &string);
    if ( v4 < 0 )
    {
      RaiseException(v4, 1u, 0, 0);
      __debugbreak();
    }
    if ( (int)Bcp47GetNlsForm(string, &v7) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v7, 0);
      v2 = LocaleNameToLCID(StringRawBuffer, 0);
    }
    WindowsDeleteString(v7);
    if ( !v2 )
      return 127;
  }
  if ( v2 == 4096 )
    return 127;
  return v2;
}

```

## disassembly

```asm
0x1800bab08  mov     [rsp+arg_8], rbx
0x1800bab0d  mov     [rsp+arg_10], rsi
0x1800bab12  push    rdi
0x1800bab13  sub     rsp, 50h
0x1800bab17  mov     rax, cs:__security_cookie
0x1800bab1e  xor     rax, rsp
0x1800bab21  mov     [rsp+58h+var_10], rax
0x1800bab26  xor     edx, edx; dwFlags
0x1800bab28  mov     rdi, rcx
0x1800bab2b  call    cs:__imp_LocaleNameToLCID
0x1800bab31  xor     esi, esi
0x1800bab33  mov     ebx, eax
0x1800bab35  test    eax, eax
0x1800bab37  jnz     loc_1800BABE1
0x1800bab3d  xor     ecx, ecx; string
0x1800bab3f  mov     [rsp+58h+var_38], rsi
0x1800bab44  call    cs:__imp_WindowsDeleteString
0x1800bab4a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bab4e  mov     [rsp+58h+var_38], rsi
0x1800bab53  mov     [rsp+58h+string], rsi
0x1800bab58  inc     rdx; length
0x1800bab5b  cmp     [rdi+rdx*2], si
0x1800bab5f  jnz     short loc_1800BAB58
0x1800bab61  mov     eax, 0FFFFFFFFh
0x1800bab66  cmp     rdx, rax
0x1800bab69  ja      loc_1800BAC0D
0x1800bab6f  lea     eax, [rdx+1]
0x1800bab72  cmp     eax, edx
0x1800bab74  jb      loc_1800BAC0D
0x1800bab7a  lea     r9, [rsp+58h+string]; string
0x1800bab7f  mov     rcx, rdi; sourceString
0x1800bab82  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800bab87  call    cs:__imp_WindowsCreateStringReference
0x1800bab8d  test    eax, eax
0x1800bab8f  jns     short loc_1800BABA4
0x1800bab91  xor     r9d, r9d; lpArguments
0x1800bab94  xor     r8d, r8d; nNumberOfArguments
0x1800bab97  mov     ecx, eax; dwExceptionCode
0x1800bab99  lea     edx, [r9+1]; dwExceptionFlags
0x1800bab9d  call    cs:__imp_RaiseException
0x1800baba3  int     3; Trap to Debugger
0x1800baba4  mov     rcx, [rsp+58h+string]
0x1800baba9  lea     rdx, [rsp+58h+var_38]
0x1800babae  call    cs:__imp_Bcp47GetNlsForm
0x1800babb4  test    eax, eax
0x1800babb6  js      short loc_1800BABD2
0x1800babb8  mov     rcx, [rsp+58h+var_38]; string
0x1800babbd  xor     edx, edx; length
0x1800babbf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800babc5  mov     rcx, rax; lpName
0x1800babc8  xor     edx, edx; dwFlags
0x1800babca  call    cs:__imp_LocaleNameToLCID
0x1800babd0  mov     ebx, eax
0x1800babd2  mov     rcx, [rsp+58h+var_38]; string
0x1800babd7  call    cs:__imp_WindowsDeleteString
0x1800babdd  test    ebx, ebx
0x1800babdf  jz      short loc_1800BABE9
0x1800babe1  cmp     ebx, 1000h
0x1800babe7  jnz     short loc_1800BABEE
0x1800babe9  mov     ebx, 7Fh
0x1800babee  mov     eax, ebx
0x1800babf0  mov     rcx, [rsp+58h+var_10]
0x1800babf5  xor     rcx, rsp; StackCookie
0x1800babf8  call    __security_check_cookie
0x1800babfd  mov     rbx, [rsp+58h+arg_8]
0x1800bac02  mov     rsi, [rsp+58h+arg_10]
0x1800bac07  add     rsp, 50h
0x1800bac0b  pop     rdi
0x1800bac0c  retn
0x1800bac0d  xor     r9d, r9d; lpArguments
0x1800bac10  xor     r8d, r8d; nNumberOfArguments
0x1800bac13  mov     ecx, 80070216h; dwExceptionCode
0x1800bac18  lea     edx, [r9+1]; dwExceptionFlags
0x1800bac1c  call    cs:__imp_RaiseException
```
