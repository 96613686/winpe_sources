# ThemeAwareSplashScreen::CThemeAwareSplashScreenConfiguration::RetrievePackageFullNameFromFullyQualifiedResourceIfApplicable(HSTRING__ *)

- ea: `0x180037c5c`
- end: `0x180037d8d`
- name: `?RetrievePackageFullNameFromFullyQualifiedResourceIfApplicable@CThemeAwareSplashScreenConfiguration@ThemeAwareSplashScreen@@QEAA?AUhstring@winrt@@PEAUHSTRING__@@@Z`
- size: `305`
- prototype: `struct winrt::hstring __high(HSTRING)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000471c`

## callees

- `0x180037c5c`
- `0x18003e418`
- `0x18003eeec`
- `0x18004bb84`
- `0x180051e88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180037d0d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180037d0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180037cad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180037cad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037cde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037cde`

## string_xrefs

- `0x180037cbe`: `shellcommon\internal\shell\inc\ThemeAwareSplashScreenConfiguration.h`
- `0x180037d39`: `shellcommon\internal\shell\inc\ThemeAwareSplashScreenConfiguration.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ThemeAwareSplashScreen::CThemeAwareSplashScreenConfiguration::RetrievePackageFullNameFromFullyQualifiedResourceIfApplicable(
        __int64 a1,
        _QWORD *a2,
        HSTRING a3)
{
  HSTRING hstring_on_heap; // rax
  HRESULT v6; // eax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v8; // rbx
  wchar_t *v9; // rax
  int v10; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 length; // [rsp+50h] [rbp+20h] BYREF
  _QWORD *v14; // [rsp+58h] [rbp+28h]
  HSTRING newString; // [rsp+60h] [rbp+30h] BYREF

  v14 = a2;
  length = a1;
  hstring_on_heap = 0;
  newString = 0;
  *a2 = 0;
  if ( a3 )
  {
    WindowsDeleteString(0);
    newString = 0;
    v6 = WindowsDuplicateString(a3, &newString);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\ThemeAwareSplashScreenConfiguration.h",
        (const char *)(unsigned int)v6,
        1);
    LODWORD(length) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a3, (UINT32 *)&length);
    v8 = StringRawBuffer;
    if ( (unsigned int)length >= 3
      && *StringRawBuffer == 64
      && StringRawBuffer[1] == 123
      && StringRawBuffer[(unsigned int)(length - 1)] == 125 )
    {
      v9 = wcschr(StringRawBuffer, 0x3Fu);
      if ( v9 )
      {
        v10 = Microsoft::WRL::Wrappers::HString::Set(
                (Microsoft::WRL::Wrappers::HString *)&newString,
                v8 + 2,
                v9 - (v8 + 2));
        if ( v10 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x5D,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\ThemeAwareSplashScreenConfiguration.h",
            (const char *)(unsigned int)v10,
            1);
      }
    }
    hstring_on_heap = newString;
  }
  if ( hstring_on_heap )
  {
    if ( (*(_BYTE *)hstring_on_heap & 1) != 0 )
      hstring_on_heap = (HSTRING)winrt::impl::create_hstring_on_heap(
                                   *((winrt::impl **)hstring_on_heap + 2),
                                   (winrt::impl *)*((unsigned int *)hstring_on_heap + 1),
                                   (unsigned int)a3);
    else
      _InterlockedIncrement((volatile signed __int32 *)hstring_on_heap + 6);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::attach(a2, hstring_on_heap);
  WindowsDeleteString(newString);
  return a2;
}

```

## disassembly

```asm
0x180037c5c  mov     [rsp-18h+arg_8], rdx
0x180037c61  mov     [rsp-18h+length], rcx
0x180037c66  push    rbp
0x180037c67  push    rbx
0x180037c68  push    rdi
0x180037c69  mov     rbp, rsp
0x180037c6c  sub     rsp, 30h
0x180037c70  mov     rbx, r8
0x180037c73  mov     rdi, rdx
0x180037c76  mov     [rbp+var_10], 0
0x180037c7d  xor     eax, eax
0x180037c7f  mov     [rbp+newString], rax
0x180037c83  mov     [rdx], rax
0x180037c86  mov     [rbp+var_10], 1
0x180037c8d  test    r8, r8
0x180037c90  jz      loc_180037D4F
0x180037c96  xor     ecx, ecx; string
0x180037c98  call    cs:__imp_WindowsDeleteString
0x180037c9e  mov     [rbp+newString], 0
0x180037ca6  lea     rdx, [rbp+newString]; newString
0x180037caa  mov     rcx, rbx; string
0x180037cad  call    cs:__imp_WindowsDuplicateString
0x180037cb3  mov     rcx, [rbp+18h]; this
0x180037cb7  test    eax, eax
0x180037cb9  jns     short loc_180037CD0
0x180037cbb  mov     r9d, eax; char *
0x180037cbe  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Them"...
0x180037cc5  mov     edx, 54h ; 'T'; void *
0x180037cca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180037cd0  mov     dword ptr [rbp+length], 0
0x180037cd7  lea     rdx, [rbp+length]; length
0x180037cdb  mov     rcx, rbx; string
0x180037cde  call    cs:__imp_WindowsGetStringRawBuffer
0x180037ce4  mov     rbx, rax
0x180037ce7  mov     ecx, dword ptr [rbp+length]
0x180037cea  cmp     ecx, 3
0x180037ced  jb      short loc_180037D4B
0x180037cef  cmp     word ptr [rax], 40h ; '@'
0x180037cf3  jnz     short loc_180037D4B
0x180037cf5  cmp     word ptr [rax+2], 7Bh ; '{'
0x180037cfa  jnz     short loc_180037D4B
0x180037cfc  dec     ecx
0x180037cfe  cmp     word ptr [rax+rcx*2], 7Dh ; '}'
0x180037d03  jnz     short loc_180037D4B
0x180037d05  mov     edx, 3Fh ; '?'; Ch
0x180037d0a  mov     rcx, rax; Str
0x180037d0d  call    cs:__imp_wcschr
0x180037d13  test    rax, rax
0x180037d16  jz      short loc_180037D4B
0x180037d18  lea     rdx, [rbx+4]; unsigned __int16 *
0x180037d1c  sub     rax, rdx
0x180037d1f  sar     rax, 1
0x180037d22  mov     r8d, eax; unsigned int
0x180037d25  lea     rcx, [rbp+newString]; this
0x180037d29  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180037d2e  mov     rcx, [rbp+18h]; this
0x180037d32  test    eax, eax
0x180037d34  jns     short loc_180037D4B
0x180037d36  mov     r9d, eax; char *
0x180037d39  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Them"...
0x180037d40  mov     edx, 5Dh ; ']'; void *
0x180037d45  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180037d4b  mov     rax, [rbp+newString]
0x180037d4f  test    rax, rax
0x180037d52  jz      short loc_180037D6B
0x180037d54  test    byte ptr [rax], 1
0x180037d57  jnz     short loc_180037D5F
0x180037d59  lock inc dword ptr [rax+18h]
0x180037d5d  jmp     short loc_180037D6B
0x180037d5f  mov     edx, [rax+4]; winrt::impl *
0x180037d62  mov     rcx, [rax+10h]; this
0x180037d66  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180037d6b  mov     rdx, rax
0x180037d6e  mov     rcx, rdi
0x180037d71  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180037d76  nop
0x180037d77  mov     rcx, [rbp+newString]; string
0x180037d7b  call    cs:__imp_WindowsDeleteString
0x180037d81  mov     rax, rdi
0x180037d84  add     rsp, 30h
0x180037d88  pop     rdi
0x180037d89  pop     rbx
0x180037d8a  pop     rbp
0x180037d8b  retn
```
