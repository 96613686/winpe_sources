# Windows::Internal::Spelling::RoamingDictionary::get_Path(HSTRING__ * *)

- ea: `0x1800554e0`
- end: `0x180055623`
- name: `?get_Path@RoamingDictionary@Spelling@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `323`
- prototype: `int(Windows::Internal::Spelling::RoamingDictionary *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x18001e9a8`
- `0x1800202e4`
- `0x180021b80`
- `0x180021c74`
- `0x1800425a8`
- `0x18004aa2c`
- `0x1800554e0`
- `0x180055630`
- `0x180061320`
- `0x180070530`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800555ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800555ba`

## string_xrefs

- `0x180055513`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x18005553f`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x1800555cf`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Windows::Internal::Spelling::RoamingDictionary::get_Path(
        Windows::Internal::Spelling::RoamingDictionary *this,
        HSTRING *a2)
{
  int v4; // eax
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rcx
  HRESULT String; // eax
  int v8; // [rsp+20h] [rbp-78h]
  PCNZWCH sourceString[2]; // [rsp+28h] [rbp-70h] BYREF
  UINT32 length; // [rsp+38h] [rbp-60h]
  unsigned __int64 v11; // [rsp+40h] [rbp-58h]
  LPCWSTR lpFileName[4]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v13[32]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( a2 )
  {
    v4 = Windows::Internal::Spelling::RoamingDictionary::EnsureInitialized(this);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
        (const char *)(unsigned int)v4,
        v8);
    Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryExtension(v13);
    Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryDirectory(
      (unsigned int)lpFileName,
      (LPCWSTR)qword_18013FAB8,
      0);
    v5 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v5 = lpFileName[0];
    Windows::Globalization::Spelling::UserDictionaries::EnsureDirectoryPathExists(v5, 0);
    Windows::Globalization::Spelling::UserDictionaries::GetDefaultUserDictionaryFilePath(sourceString, lpFileName, v13);
    v6 = (const WCHAR *)sourceString;
    if ( v11 > 7 )
      v6 = sourceString[0];
    String = WindowsCreateString(v6, length, a2);
    if ( String < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
        (const char *)(unsigned int)String,
        v8);
    std::wstring::_Tidy_deallocate(sourceString);
    std::wstring::_Tidy_deallocate(lpFileName);
    std::wstring::_Tidy_deallocate(v13);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
      (const char *)0x80070057LL,
      v8);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800554e0  push    rbx
0x1800554e2  sub     rsp, 90h
0x1800554e9  mov     rax, cs:__security_cookie
0x1800554f0  xor     rax, rsp
0x1800554f3  mov     [rsp+98h+var_10], rax
0x1800554fb  mov     rbx, rdx
0x1800554fe  test    rdx, rdx
0x180055501  jnz     short loc_18005552B
0x180055503  mov     rcx, [rsp+98h]; this
0x18005550b  mov     ebx, 80070057h
0x180055510  mov     r9d, ebx; char *
0x180055513  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x18005551a  mov     edx, 62h ; 'b'; void *
0x18005551f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055524  mov     eax, ebx
0x180055526  jmp     loc_180055609
0x18005552b  call    ?EnsureInitialized@RoamingDictionary@Spelling@Internal@Windows@@AEAAJXZ; Windows::Internal::Spelling::RoamingDictionary::EnsureInitialized(void)
0x180055530  mov     rcx, [rsp+98h]; this
0x180055538  test    eax, eax
0x18005553a  jns     short loc_180055550
0x18005553c  mov     r9d, eax; char *
0x18005553f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180055546  mov     edx, 63h ; 'c'; void *
0x18005554b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055550  mov     edx, 1
0x180055555  lea     rcx, [rsp+98h+var_30]; void *
0x18005555a  call    ?GetUserDictionaryExtension@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WORDLIST_TYPE@@@Z; Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryExtension(WORDLIST_TYPE)
0x18005555f  nop
0x180055560  xor     r8d, r8d
0x180055563  lea     rdx, qword_18013FAB8
0x18005556a  lea     rcx, [rsp+98h+lpFileName]
0x18005556f  call    ?GetUserDictionaryDirectory@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@PEBG@Z; Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryDirectory(std::wstring const &,ushort const *)
0x180055574  nop
0x180055575  lea     rcx, [rsp+98h+lpFileName]
0x18005557a  cmp     [rsp+98h+var_38], 7
0x180055580  cmova   rcx, [rsp+98h+lpFileName]; lpFileName
0x180055586  xor     edx, edx; unsigned __int16 *
0x180055588  call    ?EnsureDirectoryPathExists@UserDictionaries@Spelling@Globalization@Windows@@SAXPEBG0@Z; Windows::Globalization::Spelling::UserDictionaries::EnsureDirectoryPathExists(ushort const *,ushort const *)
0x18005558d  lea     r8, [rsp+98h+var_30]
0x180055592  lea     rdx, [rsp+98h+lpFileName]
0x180055597  lea     rcx, [rsp+98h+sourceString]
0x18005559c  call    ?GetDefaultUserDictionaryFilePath@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z; Windows::Globalization::Spelling::UserDictionaries::GetDefaultUserDictionaryFilePath(std::wstring const &,std::wstring const &)
0x1800555a1  nop
0x1800555a2  lea     rcx, [rsp+98h+sourceString]
0x1800555a7  cmp     [rsp+98h+var_58], 7
0x1800555ad  cmova   rcx, [rsp+98h+sourceString]; sourceString
0x1800555b3  mov     r8, rbx; string
0x1800555b6  mov     edx, [rsp+98h+length]; length
0x1800555ba  call    cs:__imp_WindowsCreateString
0x1800555c0  mov     rcx, [rsp+98h]; this
0x1800555c8  test    eax, eax
0x1800555ca  jns     short loc_1800555E1
0x1800555cc  mov     r9d, eax; char *
0x1800555cf  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800555d6  mov     edx, 69h ; 'i'; void *
0x1800555db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800555e1  lea     rcx, [rsp+98h+sourceString]
0x1800555e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800555eb  nop
0x1800555ec  lea     rcx, [rsp+98h+lpFileName]
0x1800555f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800555f6  nop
0x1800555f7  lea     rcx, [rsp+98h+var_30]
0x1800555fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055601  xor     eax, eax
0x180055603  jmp     short loc_180055609
0x180055605  mov     eax, [rsp+98h+var_78]
0x180055609  mov     rcx, [rsp+98h+var_10]
0x180055611  xor     rcx, rsp; StackCookie
0x180055614  call    __security_check_cookie
0x180055619  add     rsp, 90h
0x180055620  pop     rbx
0x180055621  retn
```
