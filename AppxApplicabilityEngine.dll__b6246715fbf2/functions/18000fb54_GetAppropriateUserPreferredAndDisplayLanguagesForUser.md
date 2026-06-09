# GetAppropriateUserPreferredAndDisplayLanguagesForUser

- ea: `0x18000fb54`
- end: `0x18000ff64`
- name: `GetAppropriateUserPreferredAndDisplayLanguagesForUser`
- size: `1040`
- prototype: `__int64 __fastcall(void *, __int64, HSTRING *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d2e4`

## callees

- `0x180004080`
- `0x180009da8`
- `0x18000a1ec`
- `0x18000b658`
- `0x18000b8b8`
- `0x18000e6ac`
- `0x18000fb54`
- `0x18000ff6c`
- `0x180010050`
- `0x180010dd0`
- `0x18001577c`
- `0x18001681c`
- `0x18001e55c`
- `0x18001e5ec`
- `0x18001e910`
- `0x18001e964`
- `0x18001ec68`
- `0x18001f1c0`
- `0x1800223f8`
- `0x18002249c`
- `0x1800227c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fbc9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fbc9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000fbaf`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000fbaf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fce2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fce2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000fb96`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000fcf7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000fd63`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000fb96`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000fcf7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000fd63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000fe7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000fe7c`

## string_xrefs

- `0x18000fba8`: `bcp47langs.dll`
- `0x18000fe93`: `onecore\base\mrt\langs\common\src\bcp47app.cpp`

## pseudocode

```c
__int64 __fastcall GetAppropriateUserPreferredAndDisplayLanguagesForUser(void *a1, __int64 a2, HSTRING *a3)
{
  BOOL v5; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 result; // rax
  __int64 UserLanguages; // rdx
  __int64 v12; // rdx
  int v13; // ebx
  __int64 PreferredLanguages; // rdx
  bool v15; // zf
  __int64 v16; // rbx
  __int64 InstalledLanguages; // rdx
  unsigned __int64 i; // rdi
  const WCHAR *v19; // rdx
  __int64 v20; // rax
  HRESULT v21; // eax
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-208h]
  PSID pSid1; // [rsp+30h] [rbp-1F8h] BYREF
  __int128 v25; // [rsp+38h] [rbp-1F0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-1E0h]
  __int128 v27; // [rsp+58h] [rbp-1D0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-1C0h]
  _QWORD v29[6]; // [rsp+78h] [rbp-1B0h] BYREF
  long *v30; // [rsp+A8h] [rbp-180h] BYREF
  const wil::ResultException *v31; // [rsp+B0h] [rbp-178h] BYREF
  PCWSTR sourceString[2]; // [rsp+B8h] [rbp-170h] BYREF
  unsigned int v33; // [rsp+C8h] [rbp-160h]
  unsigned __int64 v34; // [rsp+D0h] [rbp-158h]
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-148h] BYREF
  _BYTE v36[160]; // [rsp+100h] [rbp-128h] BYREF
  _BYTE v37[40]; // [rsp+1A0h] [rbp-88h] BYREF
  _BYTE v38[72]; // [rsp+1C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v29[4] = -2;
  *a3 = 0;
  v5 = IsWellKnownSid(a1, WinAccountDefaultSystemManagedSid);
  try
  {
    if ( v5 )
    {
      Library = LoadLibraryExW(L"bcp47langs.dll", 0, 0x800u);
      pSid1 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "GetUserLanguagesForAllUsers");
        if ( ProcAddress )
        {
          LOBYTE(v8) = 1;
          v9 = ((__int64 (__fastcall *)(__int64, HSTRING *, _QWORD, __int64))ProcAddress)(59, a3, 0, v8);
          if ( v9 != -2147024891 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&pSid1);
            return v9;
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&pSid1);
    }
    v25 = 0;
    v26 = 0;
    SerializedReadOnlyUserLanguages::SerializedReadOnlyUserLanguages((SerializedReadOnlyUserLanguages *)v37, a1);
    UserLanguages = SerializedReadOnlyUserLanguagesRegistrar::GetUserLanguages(v38, v29);
    std::vector<std::wstring>::_Assign_rv(&v25, UserLanguages);
    std::vector<std::wstring>::_Tidy(v29);
    if ( *((_QWORD *)&v25 + 1) == (_QWORD)v25 )
    {
      ReadOnlyUserLanguages::ReadOnlyUserLanguages((ReadOnlyUserLanguages *)v36, a1);
      v12 = UserLanguages::GetUserLanguages(v36, v29);
      std::vector<std::wstring>::_Assign_rv(&v25, v12);
      std::vector<std::wstring>::_Tidy(v29);
      ReadOnlyUserLanguages::~ReadOnlyUserLanguages((ReadOnlyUserLanguages *)v36);
    }
    pSid1 = 0;
    GetCurrentUserSid(&pSid1);
    v27 = 0;
    v28 = 0;
    if ( pSid1 && EqualSid(pSid1, a1) )
    {
      v13 = 1;
      if ( !IsWellKnownSid(a1, WinLocalSystemSid) )
      {
        v29[0] = &std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::wstring> (*const)(void),0>,std::vector<std::wstring>>::`vftable';
        v29[1] = UserDisplayLanguage::DefaultGetUserDisplayLanguageList;
        v29[3] = v29;
        PreferredLanguages = UserDisplayLanguage::GetPreferredLanguages(&hstringHeader, v29);
        std::vector<std::wstring>::_Assign_rv(&v27, PreferredLanguages);
        std::vector<std::wstring>::_Tidy(&hstringHeader);
      }
    }
    else
    {
      v13 = 0;
    }
    if ( IsWellKnownSid(a1, WinLocalSystemSid)
      || (v15 = v13 == 0, v16 = v27, !v15) && *((_QWORD *)&v27 + 1) == (_QWORD)v27 )
    {
      InstalledLanguages = UserDisplayLanguage::GetInstalledLanguages((LONG_PTR)&hstringHeader);
      std::vector<std::wstring>::_Assign_rv(&v27, InstalledLanguages);
      std::vector<std::wstring>::_Tidy(&hstringHeader);
      v16 = v27;
    }
    for ( i = 0; i < 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)&v27 + 1) - v16) >> 3); ++i )
      std::vector<std::wstring>::push_back(&v25, v16 + 40 * i);
    NormalizeAllLanguageTags<std::vector<std::wstring>>(&v25);
    RemoveDuplicates<std::vector<std::wstring>>(&v25);
    if ( *((_QWORD *)&v25 + 1) == (_QWORD)v25 )
    {
      std::vector<std::wstring>::_Tidy(&v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid1);
      ReadOnlyUserLanguages::~ReadOnlyUserLanguages((ReadOnlyUserLanguages *)v37);
      std::vector<std::wstring>::_Tidy(&v25);
      result = 2147942413LL;
    }
    else
    {
      DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::wstring>>>(sourceString);
      v19 = (const WCHAR *)sourceString;
      if ( v34 >= 8 )
        v19 = sourceString[0];
      v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v19, v33);
      v21 = WindowsDuplicateString(*(HSTRING *)(v20 + 24), a3);
      v22 = v21;
      if ( v21 >= 0 )
      {
        std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(sourceString);
        std::vector<std::wstring>::_Tidy(&v27);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid1);
        ReadOnlyUserLanguages::~ReadOnlyUserLanguages((ReadOnlyUserLanguages *)v37);
        std::vector<std::wstring>::_Tidy(&v25);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"onecore\\base\\mrt\\langs\\common\\src\\bcp47app.cpp",
          (const char *)(unsigned int)v21,
          v23);
        std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(sourceString);
        std::vector<std::wstring>::_Tidy(&v27);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid1);
        ReadOnlyUserLanguages::~ReadOnlyUserLanguages((ReadOnlyUserLanguages *)v37);
        std::vector<std::wstring>::_Tidy(&v25);
        result = v22;
      }
    }
  }
  catch ( long *v30 )
  {
    LODWORD(pSid1) = *(_DWORD *)v30;
    return (unsigned int)pSid1;
  }
  catch ( const wil::ResultException *v31 )
  {
    LODWORD(pSid1) = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)((char *)v31 + 24), 8));
    return (unsigned int)pSid1;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( std::out_of_range )
  {
    return 2147942487LL;
  }
  catch ( std::invalid_argument )
  {
    return 2147942487LL;
  }
  catch ( std::length_error )
  {
    return 2147942414LL;
  }
  catch ( exception )
  {
    return 2147549183LL;
  }
  if ( v5 )
  {
    Library = LoadLibraryExW(L"bcp47langs.dll", 0, 0x800u);
    pSid1 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetUserLanguagesForAllUsers");
      if ( ProcAddress )
      {
        LOBYTE(v8) = 1;
        v9 = ((__int64 (__fastcall *)(__int64, HSTRING *, _QWORD, __int64))ProcAddress)(59, a3, 0, v8);
        if ( v9 != -2147024891 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&pSid1);
          return v9;
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&pSid1);
  }
}

```

## disassembly

```asm
0x18000fb54  mov     rax, rsp
0x18000fb57  push    rdi
0x18000fb58  sub     rsp, 220h
0x18000fb5f  mov     qword ptr [rax-190h], 0FFFFFFFFFFFFFFFEh
0x18000fb6a  mov     [rax+10h], rbx
0x18000fb6e  mov     [rax+20h], rsi
0x18000fb72  mov     rax, cs:__security_cookie
0x18000fb79  xor     rax, rsp
0x18000fb7c  mov     [rsp+228h+var_18], rax
0x18000fb84  mov     rsi, r8
0x18000fb87  mov     rdi, rcx
0x18000fb8a  mov     qword ptr [r8], 0
0x18000fb91  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x18000fb96  call    cs:__imp_IsWellKnownSid
0x18000fb9c  test    eax, eax
0x18000fb9e  jz      short loc_18000FC0B
0x18000fba0  xor     edx, edx; hFile
0x18000fba2  mov     r8d, 800h; dwFlags
0x18000fba8  lea     rcx, LibFileName; "bcp47langs.dll"
0x18000fbaf  call    cs:__imp_LoadLibraryExW
0x18000fbb5  mov     [rsp+228h+pSid1], rax
0x18000fbba  test    rax, rax
0x18000fbbd  jz      short loc_18000FC01
0x18000fbbf  lea     rdx, aGetuserlanguag; "GetUserLanguagesForAllUsers"
0x18000fbc6  mov     rcx, rax; hModule
0x18000fbc9  call    cs:__imp_GetProcAddress
0x18000fbcf  test    rax, rax
0x18000fbd2  jz      short loc_18000FC01
0x18000fbd4  mov     ecx, 3Bh ; ';'
0x18000fbd9  mov     r9b, 1
0x18000fbdc  xor     r8d, r8d
0x18000fbdf  mov     rdx, rsi
0x18000fbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbe7  mov     ebx, eax
0x18000fbe9  cmp     eax, 80070005h
0x18000fbee  jz      short loc_18000FC01
0x18000fbf0  lea     rcx, [rsp+228h+pSid1]
0x18000fbf5  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000fbfa  mov     eax, ebx
0x18000fbfc  jmp     loc_18000FF3E
0x18000fc01  lea     rcx, [rsp+228h+pSid1]
0x18000fc06  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000fc0b  xorps   xmm0, xmm0
0x18000fc0e  movdqu  [rsp+228h+var_1F0], xmm0
0x18000fc14  mov     [rsp+228h+var_1E0], 0
0x18000fc1d  mov     rdx, rdi; void *
0x18000fc20  lea     rcx, [rsp+228h+var_88]; this
0x18000fc28  call    ??0SerializedReadOnlyUserLanguages@@QEAA@PEAX@Z; SerializedReadOnlyUserLanguages::SerializedReadOnlyUserLanguages(void *)
0x18000fc2d  nop
0x18000fc2e  lea     rdx, [rsp+228h+var_1B0]
0x18000fc33  lea     rcx, [rsp+228h+var_60]
0x18000fc3b  call    ?GetUserLanguages@SerializedReadOnlyUserLanguagesRegistrar@@UEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; SerializedReadOnlyUserLanguagesRegistrar::GetUserLanguages(void)
0x18000fc40  nop
0x18000fc41  mov     rdx, rax
0x18000fc44  lea     rcx, [rsp+228h+var_1F0]
0x18000fc49  call    ?_Assign_rv@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV12@@Z; std::vector<std::wstring>::_Assign_rv(std::vector<std::wstring> &&)
0x18000fc4e  nop
0x18000fc4f  lea     rcx, [rsp+228h+var_1B0]
0x18000fc54  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fc59  mov     rax, qword ptr [rsp+228h+var_1F0+8]
0x18000fc5e  cmp     rax, qword ptr [rsp+228h+var_1F0]
0x18000fc63  jnz     short loc_18000FCB0
0x18000fc65  mov     rdx, rdi; void *
0x18000fc68  lea     rcx, [rsp+228h+var_128]; this
0x18000fc70  call    ??0ReadOnlyUserLanguages@@QEAA@PEAX@Z; ReadOnlyUserLanguages::ReadOnlyUserLanguages(void *)
0x18000fc75  nop
0x18000fc76  lea     rdx, [rsp+228h+var_1B0]
0x18000fc7b  lea     rcx, [rsp+228h+var_128]
0x18000fc83  call    ?GetUserLanguages@UserLanguages@@QEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; UserLanguages::GetUserLanguages(void)
0x18000fc88  nop
0x18000fc89  mov     rdx, rax
0x18000fc8c  lea     rcx, [rsp+228h+var_1F0]
0x18000fc91  call    ?_Assign_rv@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV12@@Z; std::vector<std::wstring>::_Assign_rv(std::vector<std::wstring> &&)
0x18000fc96  nop
0x18000fc97  lea     rcx, [rsp+228h+var_1B0]
0x18000fc9c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fca1  nop
0x18000fca2  lea     rcx, [rsp+228h+var_128]; this
0x18000fcaa  call    ??1ReadOnlyUserLanguages@@QEAA@XZ; ReadOnlyUserLanguages::~ReadOnlyUserLanguages(void)
0x18000fcaf  nop
0x18000fcb0  mov     [rsp+228h+pSid1], 0
0x18000fcb9  lea     rcx, [rsp+228h+pSid1]; void **
0x18000fcbe  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18000fcc3  xorps   xmm0, xmm0
0x18000fcc6  movdqu  [rsp+228h+var_1D0], xmm0
0x18000fccc  mov     [rsp+228h+var_1C0], 0
0x18000fcd5  mov     rcx, [rsp+228h+pSid1]; pSid1
0x18000fcda  test    rcx, rcx
0x18000fcdd  jz      short loc_18000FD59
0x18000fcdf  mov     rdx, rdi; pSid2
0x18000fce2  call    cs:__imp_EqualSid
0x18000fce8  test    eax, eax
0x18000fcea  jz      short loc_18000FD59
0x18000fcec  mov     ebx, 1
0x18000fcf1  lea     edx, [rbx+15h]; WellKnownSidType
0x18000fcf4  mov     rcx, rdi; pSid
0x18000fcf7  call    cs:__imp_IsWellKnownSid
0x18000fcfd  test    eax, eax
0x18000fcff  jnz     short loc_18000FD5B
0x18000fd01  lea     rax, ??_7?$_Impl_no_alloc0@U?$_Callable_fun@Q6A?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ$0A@@tr1@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@tr1@std@@6B@; const std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::wstring> (*const)(void),0>,std::vector<std::wstring>>::`vftable'
0x18000fd08  mov     [rsp+228h+var_1B0], rax
0x18000fd0d  lea     rax, ?DefaultGetUserDisplayLanguageList@UserDisplayLanguage@@CA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; UserDisplayLanguage::DefaultGetUserDisplayLanguageList(void)
0x18000fd14  mov     [rsp+228h+var_1A8], rax
0x18000fd1c  lea     rax, [rsp+228h+var_1B0]
0x18000fd21  mov     [rsp+228h+var_198], rax
0x18000fd29  lea     rdx, [rsp+228h+var_1B0]
0x18000fd2e  lea     rcx, [rsp+228h+hstringHeader]
0x18000fd36  call    ?GetPreferredLanguages@UserDisplayLanguage@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$function@$$A6A?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ@tr1@3@@Z; UserDisplayLanguage::GetPreferredLanguages(std::tr1::function<std::vector<std::wstring> (void)>)
0x18000fd3b  nop
0x18000fd3c  mov     rdx, rax
0x18000fd3f  lea     rcx, [rsp+228h+var_1D0]
0x18000fd44  call    ?_Assign_rv@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV12@@Z; std::vector<std::wstring>::_Assign_rv(std::vector<std::wstring> &&)
0x18000fd49  nop
0x18000fd4a  lea     rcx, [rsp+228h+hstringHeader]
0x18000fd52  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fd57  jmp     short loc_18000FD5B
0x18000fd59  xor     ebx, ebx
0x18000fd5b  mov     edx, 16h; WellKnownSidType
0x18000fd60  mov     rcx, rdi; pSid
0x18000fd63  call    cs:__imp_IsWellKnownSid
0x18000fd69  test    eax, eax
0x18000fd6b  jnz     short loc_18000FD7D
0x18000fd6d  test    ebx, ebx
0x18000fd6f  mov     rbx, qword ptr [rsp+228h+var_1D0]
0x18000fd74  jz      short loc_18000FDAB
0x18000fd76  cmp     qword ptr [rsp+228h+var_1D0+8], rbx
0x18000fd7b  jnz     short loc_18000FDAB
0x18000fd7d  lea     rcx, [rsp+228h+hstringHeader]; lParam
0x18000fd85  call    ?GetInstalledLanguages@UserDisplayLanguage@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; UserDisplayLanguage::GetInstalledLanguages(void)
0x18000fd8a  nop
0x18000fd8b  mov     rdx, rax
0x18000fd8e  lea     rcx, [rsp+228h+var_1D0]
0x18000fd93  call    ?_Assign_rv@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV12@@Z; std::vector<std::wstring>::_Assign_rv(std::vector<std::wstring> &&)
0x18000fd98  nop
0x18000fd99  lea     rcx, [rsp+228h+hstringHeader]
0x18000fda1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fda6  mov     rbx, qword ptr [rsp+228h+var_1D0]
0x18000fdab  xor     edi, edi
0x18000fdad  mov     rax, qword ptr [rsp+228h+var_1D0+8]
0x18000fdb2  sub     rax, rbx
0x18000fdb5  sar     rax, 3
0x18000fdb9  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18000fdc3  imul    rax, rcx
0x18000fdc7  lea     rcx, [rsp+228h+var_1F0]
0x18000fdcc  cmp     rdi, rax
0x18000fdcf  jnb     short loc_18000FDE3
0x18000fdd1  lea     rax, [rdi+rdi*4]
0x18000fdd5  lea     rdx, [rbx+rax*8]
0x18000fdd9  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18000fdde  inc     rdi
0x18000fde1  jmp     short loc_18000FDAD
0x18000fde3  call    ??$NormalizeAllLanguageTags@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; NormalizeAllLanguageTags<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x18000fde8  lea     rcx, [rsp+228h+var_1F0]
0x18000fded  call    ??$RemoveDuplicates@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RemoveDuplicates<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x18000fdf2  mov     r8, qword ptr [rsp+228h+var_1F0+8]
0x18000fdf7  mov     rdx, qword ptr [rsp+228h+var_1F0]
0x18000fdfc  cmp     r8, rdx
0x18000fdff  jnz     short loc_18000FE39
0x18000fe01  lea     rcx, [rsp+228h+var_1D0]
0x18000fe06  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fe0b  nop
0x18000fe0c  lea     rcx, [rsp+228h+pSid1]
0x18000fe11  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000fe16  nop
0x18000fe17  lea     rcx, [rsp+228h+var_88]; this
0x18000fe1f  call    ??1ReadOnlyUserLanguages@@QEAA@XZ; ReadOnlyUserLanguages::~ReadOnlyUserLanguages(void)
0x18000fe24  nop
0x18000fe25  lea     rcx, [rsp+228h+var_1F0]
0x18000fe2a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fe2f  mov     eax, 8007000Dh
0x18000fe34  jmp     loc_18000FF3E
0x18000fe39  lea     rcx, [rsp+228h+sourceString]
0x18000fe41  call    ??$DelimitedStringFromItems@V?$_Vector_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_iterator<std::_Vector_val<std::wstring>>>(std::_Vector_iterator<std::_Vector_val<std::wstring>>,std::_Vector_iterator<std::_Vector_val<std::wstring>>,ushort)
0x18000fe46  lea     rdx, [rsp+228h+sourceString]
0x18000fe4e  cmp     [rsp+228h+var_158], 8
0x18000fe57  cmovnb  rdx, [rsp+228h+sourceString]; sourceString
0x18000fe60  mov     r8d, [rsp+228h+var_160]; unsigned int
0x18000fe68  lea     rcx, [rsp+228h+hstringHeader]; hstringHeader
0x18000fe70  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x18000fe75  mov     rdx, rsi; newString
0x18000fe78  mov     rcx, [rax+18h]; string
0x18000fe7c  call    cs:__imp_WindowsDuplicateString
0x18000fe82  mov     ebx, eax
0x18000fe84  test    eax, eax
0x18000fe86  jns     short loc_18000FEE4
0x18000fe88  mov     rcx, [rsp+228h]; this
0x18000fe90  mov     r9d, eax; char *
0x18000fe93  lea     r8, aOnecoreBaseMrt; "onecore\\base\\mrt\\langs\\common\\src"...
0x18000fe9a  mov     edx, 84h; void *
0x18000fe9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fea4  lea     rcx, [rsp+228h+sourceString]
0x18000feac  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000feb1  nop
0x18000feb2  lea     rcx, [rsp+228h+var_1D0]
0x18000feb7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000febc  nop
0x18000febd  lea     rcx, [rsp+228h+pSid1]
0x18000fec2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000fec7  nop
0x18000fec8  lea     rcx, [rsp+228h+var_88]; this
0x18000fed0  call    ??1ReadOnlyUserLanguages@@QEAA@XZ; ReadOnlyUserLanguages::~ReadOnlyUserLanguages(void)
0x18000fed5  nop
0x18000fed6  lea     rcx, [rsp+228h+var_1F0]
0x18000fedb  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fee0  mov     eax, ebx
0x18000fee2  jmp     short loc_18000FF3E
0x18000fee4  lea     rcx, [rsp+228h+sourceString]
0x18000feec  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000fef1  nop
0x18000fef2  lea     rcx, [rsp+228h+var_1D0]
0x18000fef7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000fefc  nop
0x18000fefd  lea     rcx, [rsp+228h+pSid1]
0x18000ff02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ff07  nop
0x18000ff08  lea     rcx, [rsp+228h+var_88]; this
0x18000ff10  call    ??1ReadOnlyUserLanguages@@QEAA@XZ; ReadOnlyUserLanguages::~ReadOnlyUserLanguages(void)
0x18000ff15  nop
0x18000ff16  lea     rcx, [rsp+228h+var_1F0]
0x18000ff1b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000ff20  nop
0x18000ff21  xor     eax, eax
0x18000ff23  jmp     short loc_18000FF3E
0x18000ff25  mov     eax, dword ptr [rsp+228h+pSid1]
0x18000ff29  jmp     short loc_18000FF30
0x18000ff2b  mov     eax, 8007000Eh
0x18000ff30  jmp     short loc_18000FF3E
0x18000ff32  mov     eax, 80070057h
0x18000ff37  jmp     short loc_18000FF30
0x18000ff39  mov     eax, 8000FFFFh
0x18000ff3e  mov     rcx, [rsp+228h+var_18]
0x18000ff46  xor     rcx, rsp; StackCookie
0x18000ff49  call    __security_check_cookie
0x18000ff4e  lea     r11, [rsp+228h+var_8]
0x18000ff56  mov     rbx, [r11+18h]
0x18000ff5a  mov     rsi, [r11+28h]
0x18000ff5e  mov     rsp, r11
0x18000ff61  pop     rdi
0x18000ff62  retn
```
