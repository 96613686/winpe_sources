# StoreApplication::GetStoreAppLanguage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IAppxManifestPackageId *)

- ea: `0x1800dafb8`
- end: `0x1800db160`
- name: `?GetStoreAppLanguage@StoreApplication@@SAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIAppxManifestPackageId@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800dc88c`

## callees

- `0x180005890`
- `0x18000edf0`
- `0x18001082c`
- `0x180016af0`
- `0x18001c5f0`
- `0x18002248c`
- `0x1800c3478`
- `0x1800c97f0`
- `0x1800d5518`
- `0x1800dafb8`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800db131`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800db131`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db056`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800db056`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db00d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db00d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db110`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800db110`
- `Bcp47Langs!GetApplicationLanguages` at `0x1800db02d`
- `Bcp47Langs!GetApplicationLanguages` at `0x1800db02d`

## string_xrefs

- `0x1800db03e`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800db0d7`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StoreApplication::GetStoreAppLanguage(_QWORD *a1, __int64 a2, unsigned __int16 a3)
{
  int ApplicationLanguages; // eax
  PCWSTR StringRawBuffer; // rax
  int v8; // eax
  HSTRING v9; // rcx
  __int64 v10; // r8
  LCID v11; // ebx
  const WCHAR *v12; // rcx
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v14[3]; // [rsp+28h] [rbp-48h] BYREF
  LPCWSTR lpName[2]; // [rsp+40h] [rbp-30h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *(_OWORD *)lpName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpName[0]) = 0;
  string = 0;
  if ( IsWindowsVersionOrGreater(0xAu, 0, a3) )
  {
    WindowsDeleteString(0);
    string = 0;
    if ( a1[3] > 7u )
      a1 = (_QWORD *)*a1;
    ApplicationLanguages = GetApplicationLanguages(a1, 59, &string);
    if ( ApplicationLanguages < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x258,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)ApplicationLanguages,
        (int)string);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    VectorFromDelimitedString(v14, StringRawBuffer);
    if ( v14[1] == v14[0] )
    {
      std::vector<std::wstring>::_Tidy(v14);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::wstring::_Tidy_deallocate(lpName);
      return 1033;
    }
    std::wstring::operator=(lpName);
    std::vector<std::wstring>::_Tidy(v14);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL))(a2, &string);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x266,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v8,
        (int)string);
    v9 = string;
    if ( string )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)string + v10) );
      std::wstring::_Assign<unsigned short>(lpName, string);
      v9 = string;
    }
    CoTaskMemFree(v9);
  }
  v11 = 1033;
  if ( si128.m128i_i64[0] )
  {
    v12 = (const WCHAR *)lpName;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = lpName[0];
    v11 = LocaleNameToLCID(v12, 0);
  }
  std::wstring::_Tidy_deallocate(lpName);
  return v11;
}

```

## disassembly

```asm
0x1800dafb8  mov     [rsp-18h+arg_10], rbx
0x1800dafbd  push    rbp
0x1800dafbe  push    rsi
0x1800dafbf  push    rdi
0x1800dafc0  mov     rbp, rsp
0x1800dafc3  sub     rsp, 70h
0x1800dafc7  mov     rax, cs:__security_cookie
0x1800dafce  xor     rax, rsp
0x1800dafd1  mov     [rbp+var_10], rax
0x1800dafd5  mov     rdi, rdx
0x1800dafd8  mov     rbx, rcx
0x1800dafdb  xorps   xmm0, xmm0
0x1800dafde  movups  xmmword ptr [rbp+lpName], xmm0
0x1800dafe2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800dafea  movdqu  [rbp+var_20], xmm1
0x1800dafef  xor     esi, esi
0x1800daff1  mov     word ptr [rbp+lpName], si
0x1800daff5  xor     edx, edx; unsigned __int16
0x1800daff7  lea     ecx, [rsi+0Ah]; unsigned __int16
0x1800daffa  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800dafff  mov     [rbp+string], rsi
0x1800db003  test    al, al
0x1800db005  jz      loc_1800DB0B9
0x1800db00b  xor     ecx, ecx; string
0x1800db00d  call    cs:__imp_WindowsDeleteString
0x1800db013  mov     [rbp+string], rsi
0x1800db017  cmp     qword ptr [rbx+18h], 7
0x1800db01c  jbe     short loc_1800DB021
0x1800db01e  mov     rbx, [rbx]
0x1800db021  mov     edx, 3Bh ; ';'
0x1800db026  lea     r8, [rbp+string]
0x1800db02a  mov     rcx, rbx
0x1800db02d  call    cs:__imp_GetApplicationLanguages
0x1800db033  mov     rcx, [rbp+18h]; this
0x1800db037  test    eax, eax
0x1800db039  jns     short loc_1800DB050
0x1800db03b  mov     r9d, eax; char *
0x1800db03e  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db045  mov     edx, 258h; void *
0x1800db04a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db050  xor     edx, edx; length
0x1800db052  mov     rcx, [rbp+string]; string
0x1800db056  call    cs:__imp_WindowsGetStringRawBuffer
0x1800db05c  mov     rdx, rax
0x1800db05f  lea     rcx, [rbp+var_48]
0x1800db063  call    ?VectorFromDelimitedString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; VectorFromDelimitedString(ushort const *,ushort)
0x1800db068  nop
0x1800db069  mov     rdx, [rbp+var_48]
0x1800db06d  cmp     [rbp+var_40], rdx
0x1800db071  jnz     short loc_1800DB09A
0x1800db073  lea     rcx, [rbp+var_48]
0x1800db077  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800db07c  nop
0x1800db07d  lea     rcx, [rbp+string]; this
0x1800db081  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800db086  nop
0x1800db087  lea     rcx, [rbp+lpName]
0x1800db08b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800db090  mov     eax, 409h
0x1800db095  jmp     loc_1800DB144
0x1800db09a  lea     rcx, [rbp+lpName]
0x1800db09e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800db0a3  nop
0x1800db0a4  lea     rcx, [rbp+var_48]
0x1800db0a8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800db0ad  nop
0x1800db0ae  lea     rcx, [rbp+string]; this
0x1800db0b2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800db0b7  jmp     short loc_1800DB116
0x1800db0b9  mov     rax, [rdi]
0x1800db0bc  lea     rdx, [rbp+string]
0x1800db0c0  mov     rcx, rdi
0x1800db0c3  mov     rax, [rax+38h]
0x1800db0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db0cc  mov     rcx, [rbp+18h]; this
0x1800db0d0  test    eax, eax
0x1800db0d2  jns     short loc_1800DB0E9
0x1800db0d4  mov     r9d, eax; char *
0x1800db0d7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800db0de  mov     edx, 266h; void *
0x1800db0e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800db0e9  mov     rcx, [rbp+string]
0x1800db0ed  test    rcx, rcx
0x1800db0f0  jz      short loc_1800DB110
0x1800db0f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800db0f6  inc     r8
0x1800db0f9  cmp     [rcx+r8*2], si
0x1800db0fe  jnz     short loc_1800DB0F6
0x1800db100  mov     rdx, rcx
0x1800db103  lea     rcx, [rbp+lpName]
0x1800db107  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800db10c  mov     rcx, [rbp+string]; pv
0x1800db110  call    cs:__imp_CoTaskMemFree
0x1800db116  mov     ebx, 409h
0x1800db11b  cmp     qword ptr [rbp+var_20], rsi
0x1800db11f  jbe     short loc_1800DB139
0x1800db121  lea     rcx, [rbp+lpName]
0x1800db125  cmp     qword ptr [rbp+var_20+8], 7
0x1800db12a  cmova   rcx, [rbp+lpName]; lpName
0x1800db12f  xor     edx, edx; dwFlags
0x1800db131  call    cs:__imp_LocaleNameToLCID
0x1800db137  mov     ebx, eax
0x1800db139  lea     rcx, [rbp+lpName]
0x1800db13d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800db142  mov     eax, ebx
0x1800db144  mov     rcx, [rbp+var_10]
0x1800db148  xor     rcx, rsp; StackCookie
0x1800db14b  call    __security_check_cookie
0x1800db150  mov     rbx, [rsp+70h+arg_10]
0x1800db158  add     rsp, 70h
0x1800db15c  pop     rdi
0x1800db15d  pop     rsi
0x1800db15e  pop     rbp
0x1800db15f  retn
```
