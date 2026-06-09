# StoreApplication::GetStoreAppLanguage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IAppxManifestPackageId *)

- ea: `0x1800fc2d0`
- end: `0x1800fc491`
- name: `?GetStoreAppLanguage@StoreApplication@@SAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIAppxManifestPackageId@@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fc498`

## callees

- `0x18000ddb8`
- `0x1800118d0`
- `0x1800150ac`
- `0x180018a60`
- `0x18001d31c`
- `0x180029388`
- `0x1800293b0`
- `0x18002bdfc`
- `0x1800404c4`
- `0x180045480`
- `0x180052f28`
- `0x180059920`
- `0x1800679f8`
- `0x1800fc2d0`
- `0x180130010`

## import_xrefs

- `KERNEL32!LocaleNameToLCID` at `0x1800fc45f`
- `KERNEL32!LocaleNameToLCID` at `0x1800fc45f`
- `ole32!CoTaskMemFree` at `0x1800fc43e`
- `ole32!CoTaskMemFree` at `0x1800fc43e`
- `Bcp47Langs!GetApplicationLanguages` at `0x1800fc344`
- `Bcp47Langs!GetApplicationLanguages` at `0x1800fc344`

## string_xrefs

- `0x1800fc355`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fc405`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StoreApplication::GetStoreAppLanguage(_QWORD *a1, __int64 a2)
{
  unsigned __int16 v4; // r8
  int ApplicationLanguages; // eax
  PCWSTR StringRawBuffer; // rax
  int v8; // eax
  HSTRING v9; // rcx
  __int64 v10; // r8
  LCID v11; // ebx
  const WCHAR *v12; // rcx
  HSTRING string; // [rsp+28h] [rbp-29h] BYREF
  _QWORD v14[4]; // [rsp+30h] [rbp-21h] BYREF
  LPCWSTR lpName[4]; // [rsp+50h] [rbp-1h] BYREF
  _BYTE v16[32]; // [rsp+70h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v14[3] = -2;
  std::wstring::wstring(lpName);
  string = 0;
  if ( IsWindowsVersionOrGreater(0xAu, 0, v4) )
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
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)ApplicationLanguages,
        (int)string);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v16, StringRawBuffer);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>((__int64)v14);
    std::wstring::~wstring(v16);
    if ( v14[1] == v14[0] )
    {
      std::vector<std::wstring>::_Tidy(v14);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      std::wstring::~wstring(lpName);
      return 1033;
    }
    std::wstring::operator=(lpName, v14[0]);
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
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
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
  if ( lpName[2] )
  {
    v12 = (const WCHAR *)lpName;
    if ( lpName[3] > (LPCWSTR)7 )
      v12 = lpName[0];
    v11 = LocaleNameToLCID(v12, 0);
  }
  std::wstring::~wstring(lpName);
  return v11;
}

```

## disassembly

```asm
0x1800fc2d0  mov     rax, rsp
0x1800fc2d3  push    rbp
0x1800fc2d4  push    rsi
0x1800fc2d5  push    rdi
0x1800fc2d6  lea     rbp, [rax-5Fh]
0x1800fc2da  sub     rsp, 90h
0x1800fc2e1  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1800fc2e9  mov     [rax+18h], rbx
0x1800fc2ed  mov     rax, cs:__security_cookie
0x1800fc2f4  xor     rax, rsp
0x1800fc2f7  mov     [rbp+57h+var_18], rax
0x1800fc2fb  mov     rdi, rdx
0x1800fc2fe  mov     rbx, rcx
0x1800fc301  xor     esi, esi
0x1800fc303  lea     rcx, [rbp+57h+lpName]
0x1800fc307  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800fc30c  nop
0x1800fc30d  xor     edx, edx; unsigned __int16
0x1800fc30f  lea     ecx, [rsi+0Ah]; unsigned __int16
0x1800fc312  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z
0x1800fc317  mov     [rbp+57h+string], rsi
0x1800fc31b  test    al, al
0x1800fc31d  jz      loc_1800FC3E7
0x1800fc323  xor     ecx, ecx; string
0x1800fc325  call    WindowsDeleteString
0x1800fc32a  mov     [rbp+57h+string], rsi
0x1800fc32e  cmp     qword ptr [rbx+18h], 7
0x1800fc333  jbe     short loc_1800FC338
0x1800fc335  mov     rbx, [rbx]
0x1800fc338  mov     edx, 3Bh ; ';'
0x1800fc33d  lea     r8, [rbp+57h+string]
0x1800fc341  mov     rcx, rbx
0x1800fc344  call    cs:__imp_GetApplicationLanguages
0x1800fc34a  mov     rcx, [rbp+5Fh]; this
0x1800fc34e  test    eax, eax
0x1800fc350  jns     short loc_1800FC367
0x1800fc352  mov     r9d, eax; char *
0x1800fc355  lea     r8, aOnecoreInterna_7
0x1800fc35c  mov     edx, 258h; void *
0x1800fc361  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800fc367  xor     edx, edx; length
0x1800fc369  mov     rcx, [rbp+57h+string]; string
0x1800fc36d  call    WindowsGetStringRawBuffer
0x1800fc372  nop
0x1800fc373  mov     rdx, rax
0x1800fc376  lea     rcx, [rbp+57h+var_38]
0x1800fc37a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z
0x1800fc37f  nop
0x1800fc380  mov     rdx, rax
0x1800fc383  lea     rcx, [rbp+57h+var_78]
0x1800fc387  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z
0x1800fc38c  nop
0x1800fc38d  lea     rcx, [rbp+57h+var_38]
0x1800fc391  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800fc396  nop
0x1800fc397  mov     rdx, [rbp+57h+var_78]
0x1800fc39b  cmp     [rbp+57h+var_70], rdx
0x1800fc39f  jnz     short loc_1800FC3C8
0x1800fc3a1  lea     rcx, [rbp+57h+var_78]
0x1800fc3a5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ
0x1800fc3aa  nop
0x1800fc3ab  lea     rcx, [rbp+57h+string]; this
0x1800fc3af  call    ??1String@Internal@Windows@@QEAA@XZ
0x1800fc3b4  nop
0x1800fc3b5  lea     rcx, [rbp+57h+lpName]
0x1800fc3b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800fc3be  mov     eax, 409h
0x1800fc3c3  jmp     loc_1800FC472
0x1800fc3c8  lea     rcx, [rbp+57h+lpName]
0x1800fc3cc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z
0x1800fc3d1  nop
0x1800fc3d2  lea     rcx, [rbp+57h+var_78]
0x1800fc3d6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ
0x1800fc3db  nop
0x1800fc3dc  lea     rcx, [rbp+57h+string]; this
0x1800fc3e0  call    ??1String@Internal@Windows@@QEAA@XZ
0x1800fc3e5  jmp     short loc_1800FC444
0x1800fc3e7  mov     rax, [rdi]
0x1800fc3ea  lea     rdx, [rbp+57h+string]
0x1800fc3ee  mov     rcx, rdi
0x1800fc3f1  mov     rax, [rax+38h]
0x1800fc3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc3fa  mov     rcx, [rbp+5Fh]; this
0x1800fc3fe  test    eax, eax
0x1800fc400  jns     short loc_1800FC417
0x1800fc402  mov     r9d, eax; char *
0x1800fc405  lea     r8, aOnecoreInterna_7
0x1800fc40c  mov     edx, 266h; void *
0x1800fc411  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800fc417  mov     rcx, [rbp+57h+string]
0x1800fc41b  test    rcx, rcx
0x1800fc41e  jz      short loc_1800FC43E
0x1800fc420  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800fc424  inc     r8
0x1800fc427  cmp     [rcx+r8*2], si
0x1800fc42c  jnz     short loc_1800FC424
0x1800fc42e  mov     rdx, rcx
0x1800fc431  lea     rcx, [rbp+57h+lpName]
0x1800fc435  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z
0x1800fc43a  mov     rcx, [rbp+57h+string]; pv
0x1800fc43e  call    cs:__imp_CoTaskMemFree
0x1800fc444  mov     ebx, 409h
0x1800fc449  cmp     [rbp+57h+var_48], rsi
0x1800fc44d  jbe     short loc_1800FC467
0x1800fc44f  lea     rcx, [rbp+57h+lpName]
0x1800fc453  cmp     [rbp+57h+var_40], 7
0x1800fc458  cmova   rcx, [rbp+57h+lpName]; lpName
0x1800fc45d  xor     edx, edx; dwFlags
0x1800fc45f  call    cs:__imp_LocaleNameToLCID
0x1800fc465  mov     ebx, eax
0x1800fc467  lea     rcx, [rbp+57h+lpName]
0x1800fc46b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800fc470  mov     eax, ebx
0x1800fc472  mov     rcx, [rbp+57h+var_18]
0x1800fc476  xor     rcx, rsp; StackCookie
0x1800fc479  call    __security_check_cookie
0x1800fc47e  mov     rbx, [rsp+0A0h+arg_10]
0x1800fc486  add     rsp, 90h
0x1800fc48d  pop     rdi
0x1800fc48e  pop     rsi
0x1800fc48f  pop     rbp
0x1800fc490  retn
```
