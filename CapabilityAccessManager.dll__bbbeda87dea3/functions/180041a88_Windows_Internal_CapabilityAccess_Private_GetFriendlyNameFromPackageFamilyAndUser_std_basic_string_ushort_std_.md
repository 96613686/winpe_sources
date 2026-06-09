# Windows::Internal::CapabilityAccess::Private::GetFriendlyNameFromPackageFamilyAndUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x180041a88`
- end: `0x180041e23`
- name: `?GetFriendlyNameFromPackageFamilyAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `923`
- prototype: ``
- caller_count: `4`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005fff8`
- `0x180064fe4`
- `0x180067a38`
- `0x18006f230`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x180039e9c`
- `0x18003b518`
- `0x18003e7f4`
- `0x18003f4a0`
- `0x18004065c`
- `0x180041160`
- `0x180041a88`
- `0x180042720`
- `0x180043610`
- `0x1800462b0`
- `0x18005a6b8`
- `0x18005ab88`
- `0x18005aeec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180041ba3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180041d16`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180041ba3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180041d16`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180041be7`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180041be7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041c31`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041c31`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180041b87`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180041cfa`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180041b87`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180041cfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::GetFriendlyNameFromPackageFamilyAndUser(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        HANDLE *a4)
{
  __int64 v8; // rax
  __int128 *v9; // rcx
  const char *v10; // r9
  const char *v11; // r9
  char v12; // al
  const WCHAR *v13; // rax
  HRESULT v14; // eax
  char v15; // r14
  HANDLE *i; // rsi
  HANDLE *v17; // r15
  __int64 UserSidStringFromToken; // rax
  int v19; // ebx
  const char *v20; // r9
  const char *v21; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-E0h]
  HANDLE Token; // [rsp+30h] [rbp-D0h] BYREF
  char v25; // [rsp+39h] [rbp-C7h]
  __int128 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v27; // [rsp+58h] [rbp-A8h]
  _BYTE v28[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v32[40]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  Token = a1;
  if ( !Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_testCode )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59867315>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59867315>::GetImpl'::`2'::impl) )
    {
      v8 = std::wstring::wstring(v31, a2);
      Windows::Internal::CapabilityAccess::Private::Globals::FriendlyNameMapping::GetMappedNameForPackageFamily(
        &v26,
        v8);
      v9 = &v26;
      if ( (_QWORD)v27 )
      {
        a1[2] = 0;
        a1[3] = 0;
        *(_OWORD *)a1 = v26;
        *((_OWORD *)a1 + 1) = v27;
        *(_QWORD *)&v27 = 0;
        *((_QWORD *)&v27 + 1) = 7;
        LOWORD(v26) = 0;
LABEL_29:
        std::wstring::_Tidy_deallocate(v9);
        return a1;
      }
      std::wstring::_Tidy_deallocate(&v26);
    }
    Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(v30, a3, a2);
    Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::GetCachedFriendlyNameForPackageFullName(
      v28,
      v30);
    if ( v29 )
    {
      std::wstring::wstring(a1, v28);
LABEL_28:
      std::wstring::_Tidy_deallocate(v28);
      v9 = (__int128 *)v30;
      goto LABEL_29;
    }
    Windows::Internal::CapabilityAccess::Private::GetDisplayNameReferenceFromPackageFamilyAndUser((__int64)v32, a2, a3);
    Token = 0;
    if ( (char *)*a4 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v15 = 0;
      Windows::Internal::CapabilityAccess::Private::GetAllSessionUserTokens(&v26);
      v17 = (HANDLE *)*((_QWORD *)&v26 + 1);
      for ( i = (HANDLE *)v26; i != v17; ++i )
      {
        UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v31, i);
        v19 = std::wstring::compare(UserSidStringFromToken, a3);
        std::wstring::_Tidy_deallocate(v31);
        if ( !v19 )
        {
          if ( !DuplicateTokenEx(*i, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &Token) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x6F5,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
              v20);
          if ( !SetThreadToken(0, Token) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x6F6,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
              v21);
          v15 = 1;
          break;
        }
      }
      if ( (_QWORD)v26 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
          v26,
          *((_QWORD *)&v26 + 1));
        std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      if ( !v15 )
      {
        v12 = 1;
        goto LABEL_11;
      }
    }
    else
    {
      if ( !DuplicateTokenEx(*a4, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &Token) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x6E9,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
          v10);
      if ( !SetThreadToken(0, Token) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x6EA,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
          v11);
    }
    v12 = 0;
LABEL_11:
    if ( v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6FF,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)0x8000FFFFLL,
        TokenType);
    v25 = 1;
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
    v14 = SHLoadIndirectString(v13, pszOutBuf, 0x104u, 0);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x707,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v14,
        TokenType);
    std::wstring::wstring(&v26, pszOutBuf);
    Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::AddFriendlyNameToPackageFullNameMap(
      v30,
      &v26);
    std::wstring::_Tidy_deallocate(&v26);
    std::wstring::wstring(a1, pszOutBuf);
    RevertToSelf();
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    std::wstring::_Tidy_deallocate(v32);
    goto LABEL_28;
  }
  std::wstring::wstring(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x180041a88  push    rbp
0x180041a8a  push    rbx
0x180041a8b  push    rsi
0x180041a8c  push    rdi
0x180041a8d  push    r12
0x180041a8f  push    r14
0x180041a91  push    r15
0x180041a93  lea     rbp, [rsp-210h]
0x180041a9b  sub     rsp, 310h
0x180041aa2  mov     rax, cs:__security_cookie
0x180041aa9  xor     rax, rsp
0x180041aac  mov     [rbp+240h+var_40], rax
0x180041ab3  mov     rsi, r9
0x180041ab6  mov     r12, r8
0x180041ab9  mov     rbx, rdx
0x180041abc  mov     rdi, rcx
0x180041abf  mov     [rsp+340h+Token], rcx
0x180041ac4  cmp     cs:?m_testCode@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0_NA, 0; bool Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_testCode
0x180041acb  jz      short loc_180041AD7
0x180041acd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180041ad2  jmp     loc_180041D8A
0x180041ad7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59867315@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59867315@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59867315> `wil::Feature<__WilFeatureTraits_Feature_59867315>::GetImpl(void)'::`2'::impl
0x180041ade  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59867315@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59867315>::__private_IsEnabled(void)
0x180041ae3  test    al, al
0x180041ae5  jz      short loc_180041B16
0x180041ae7  mov     rdx, rbx
0x180041aea  lea     rcx, [rbp+240h+var_298]
0x180041aee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180041af3  mov     rdx, rax
0x180041af6  lea     rcx, [rsp+340h+var_2F8]
0x180041afb  call    ?GetMappedNameForPackageFamily@FriendlyNameMapping@Globals@Private@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V78@@Z; Windows::Internal::CapabilityAccess::Private::Globals::FriendlyNameMapping::GetMappedNameForPackageFamily(std::wstring)
0x180041b00  lea     rcx, [rsp+340h+var_2F8]
0x180041b05  cmp     qword ptr [rsp+340h+var_2E8], 0
0x180041b0b  jnz     loc_180041C51
0x180041b11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041b16  mov     r8, rbx
0x180041b19  mov     rdx, r12
0x180041b1c  lea     rcx, [rbp+240h+var_2B8]
0x180041b20  call    ?GetPackageFullNameFromFamilyNameAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(std::wstring const &,std::wstring const &)
0x180041b25  nop
0x180041b26  lea     rdx, [rbp+240h+var_2B8]
0x180041b2a  lea     rcx, [rsp+340h+var_2D8]
0x180041b2f  call    ?GetCachedFriendlyNameForPackageFullName@PackageDataCache@Globals@Private@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV78@@Z; Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::GetCachedFriendlyNameForPackageFullName(std::wstring const &)
0x180041b34  nop
0x180041b35  cmp     [rsp+340h+var_2C8], 0
0x180041b3b  jnz     loc_180041D68
0x180041b41  mov     r8, r12
0x180041b44  mov     rdx, rbx
0x180041b47  lea     rcx, [rbp+240h+var_278]
0x180041b4b  call    ?GetDisplayNameReferenceFromPackageFamilyAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z; Windows::Internal::CapabilityAccess::Private::GetDisplayNameReferenceFromPackageFamilyAndUser(std::wstring const &,std::wstring const &)
0x180041b50  nop
0x180041b51  mov     [rsp+340h+Token], 0
0x180041b5a  mov     rcx, [rsi]; hExistingToken
0x180041b5d  lea     rax, [rcx-1]
0x180041b61  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180041b65  ja      loc_180041C90
0x180041b6b  lea     rax, [rsp+340h+Token]
0x180041b70  mov     [rsp+340h+phNewToken], rax; phNewToken
0x180041b75  mov     r9d, 2; ImpersonationLevel
0x180041b7b  mov     [rsp+340h+TokenType], r9d; int
0x180041b80  xor     r8d, r8d; lpTokenAttributes
0x180041b83  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180041b87  call    cs:__imp_DuplicateTokenEx
0x180041b8d  mov     rcx, [rbp+248h]; this
0x180041b94  test    eax, eax
0x180041b96  jz      loc_180041DC3
0x180041b9c  mov     rdx, [rsp+340h+Token]; Token
0x180041ba1  xor     ecx, ecx; Thread
0x180041ba3  call    cs:__imp_SetThreadToken
0x180041ba9  mov     rcx, [rbp+248h]; this
0x180041bb0  test    eax, eax
0x180041bb2  jz      loc_180041DD5
0x180041bb8  xor     al, al
0x180041bba  mov     rcx, [rbp+248h]; this
0x180041bc1  test    al, al
0x180041bc3  jnz     loc_180041E0B
0x180041bc9  mov     [rsp+340h+var_307], 1
0x180041bce  lea     rcx, [rbp+240h+var_278]
0x180041bd2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041bd7  mov     rcx, rax; pszSource
0x180041bda  xor     r9d, r9d; ppvReserved
0x180041bdd  mov     r8d, 104h; cchOutBuf
0x180041be3  lea     rdx, [rbp+240h+pszOutBuf]; pszOutBuf
0x180041be7  call    cs:__imp_SHLoadIndirectString
0x180041bed  mov     rcx, [rbp+248h]; this
0x180041bf4  test    eax, eax
0x180041bf6  js      loc_180041DAE
0x180041bfc  lea     rdx, [rbp+240h+pszOutBuf]
0x180041c00  lea     rcx, [rsp+340h+var_2F8]
0x180041c05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041c0a  nop
0x180041c0b  lea     rdx, [rsp+340h+var_2F8]
0x180041c10  lea     rcx, [rbp+240h+var_2B8]
0x180041c14  call    ?AddFriendlyNameToPackageFullNameMap@PackageDataCache@Globals@Private@CapabilityAccess@Internal@Windows@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::AddFriendlyNameToPackageFullNameMap(std::wstring const &,std::wstring const &)
0x180041c19  nop
0x180041c1a  lea     rcx, [rsp+340h+var_2F8]
0x180041c1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041c24  lea     rdx, [rbp+240h+pszOutBuf]
0x180041c28  mov     rcx, rdi
0x180041c2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041c30  nop
0x180041c31  call    cs:__imp_RevertToSelf
0x180041c37  nop
0x180041c38  lea     rcx, [rsp+340h+Token]
0x180041c3d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180041c42  nop
0x180041c43  lea     rcx, [rbp+240h+var_278]
0x180041c47  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041c4c  jmp     loc_180041D76
0x180041c51  mov     qword ptr [rdi+10h], 0
0x180041c59  mov     qword ptr [rdi+18h], 0
0x180041c61  movups  xmm0, [rsp+340h+var_2F8]
0x180041c66  movups  xmmword ptr [rdi], xmm0
0x180041c69  movups  xmm1, [rsp+340h+var_2E8]
0x180041c6e  movups  xmmword ptr [rdi+10h], xmm1
0x180041c72  mov     qword ptr [rsp+340h+var_2E8], 0
0x180041c7b  mov     qword ptr [rsp+340h+var_2E8+8], 7
0x180041c84  xor     eax, eax
0x180041c86  mov     word ptr [rsp+340h+var_2F8], ax
0x180041c8b  jmp     loc_180041D85
0x180041c90  xor     r14b, r14b
0x180041c93  lea     rcx, [rsp+340h+var_2F8]
0x180041c98  call    ?GetAllSessionUserTokens@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::GetAllSessionUserTokens(void)
0x180041c9d  nop
0x180041c9e  mov     rsi, qword ptr [rsp+340h+var_2F8]
0x180041ca3  mov     r15, qword ptr [rsp+340h+var_2F8+8]
0x180041ca8  jmp     short loc_180041CD4
0x180041caa  mov     rdx, rsi
0x180041cad  lea     rcx, [rbp+240h+var_298]
0x180041cb1  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180041cb6  mov     rdx, r12
0x180041cb9  mov     rcx, rax
0x180041cbc  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x180041cc1  mov     ebx, eax
0x180041cc3  lea     rcx, [rbp+240h+var_298]
0x180041cc7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041ccc  test    ebx, ebx
0x180041cce  jz      short loc_180041CDB
0x180041cd0  add     rsi, 8
0x180041cd4  cmp     rsi, r15
0x180041cd7  jnz     short loc_180041CAA
0x180041cd9  jmp     short loc_180041D2E
0x180041cdb  lea     rax, [rsp+340h+Token]
0x180041ce0  mov     [rsp+340h+phNewToken], rax; phNewToken
0x180041ce5  mov     r9d, 2; ImpersonationLevel
0x180041ceb  mov     [rsp+340h+TokenType], r9d; TokenType
0x180041cf0  xor     r8d, r8d; lpTokenAttributes
0x180041cf3  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180041cf7  mov     rcx, [rsi]; hExistingToken
0x180041cfa  call    cs:__imp_DuplicateTokenEx
0x180041d00  mov     rcx, [rbp+248h]; this
0x180041d07  test    eax, eax
0x180041d09  jz      loc_180041DE7
0x180041d0f  mov     rdx, [rsp+340h+Token]; Token
0x180041d14  xor     ecx, ecx; Thread
0x180041d16  call    cs:__imp_SetThreadToken
0x180041d1c  mov     rcx, [rbp+248h]; this
0x180041d23  test    eax, eax
0x180041d25  jz      loc_180041DF9
0x180041d2b  mov     r14b, 1
0x180041d2e  mov     rcx, qword ptr [rsp+340h+var_2F8]
0x180041d33  test    rcx, rcx
0x180041d36  jz      short loc_180041D58
0x180041d38  mov     rdx, qword ptr [rsp+340h+var_2F8+8]
0x180041d3d  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &)
0x180041d42  mov     rcx, qword ptr [rsp+340h+var_2F8]
0x180041d47  mov     rdx, qword ptr [rsp+340h+var_2E8]
0x180041d4c  sub     rdx, rcx
0x180041d4f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180041d53  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041d58  test    r14b, r14b
0x180041d5b  jnz     loc_180041BB8
0x180041d61  mov     al, 1
0x180041d63  jmp     loc_180041BBA
0x180041d68  lea     rdx, [rsp+340h+var_2D8]
0x180041d6d  mov     rcx, rdi
0x180041d70  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180041d75  nop
0x180041d76  lea     rcx, [rsp+340h+var_2D8]
0x180041d7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041d80  nop
0x180041d81  lea     rcx, [rbp+240h+var_2B8]
0x180041d85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041d8a  mov     rax, rdi
0x180041d8d  mov     rcx, [rbp+240h+var_40]
0x180041d94  xor     rcx, rsp; StackCookie
0x180041d97  call    __security_check_cookie
0x180041d9c  add     rsp, 310h
0x180041da3  pop     r15
0x180041da5  pop     r14
0x180041da7  pop     r12
0x180041da9  pop     rdi
0x180041daa  pop     rsi
0x180041dab  pop     rbx
0x180041dac  pop     rbp
0x180041dad  retn
0x180041dae  mov     r9d, eax; char *
0x180041db1  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041db8  mov     edx, 707h; void *
0x180041dbd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041dc3  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041dca  mov     edx, 6E9h; void *
0x180041dcf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180041dd5  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041ddc  mov     edx, 6EAh; void *
0x180041de1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180041de7  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041dee  mov     edx, 6F5h; void *
0x180041df3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180041df9  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041e00  mov     edx, 6F6h; void *
0x180041e05  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180041e0b  mov     r9d, 8000FFFFh; char *
0x180041e11  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041e18  mov     edx, 6FFh; void *
0x180041e1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
