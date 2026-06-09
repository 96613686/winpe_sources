# AppCapabilityUsageHistoryServer::GetFullUsageHistory(HSTRING__ *,Windows::Foundation::Collections::IVectorView<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *> * *)

- ea: `0x18008c000`
- end: `0x18008c7a7`
- name: `?GetFullUsageHistory@AppCapabilityUsageHistoryServer@@UEAAJPEAUHSTRING__@@PEAPEAU?$IVectorView@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `1959`
- prototype: `__int64 __fastcall(__int64, HSTRING, _QWORD *)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001f5f4`
- `0x180020fcc`
- `0x18002392c`
- `0x18002d638`
- `0x18002e704`
- `0x18002f560`
- `0x18002f978`
- `0x180031698`
- `0x1800349dc`
- `0x1800363b4`
- `0x180036f0c`
- `0x180037034`
- `0x180037460`
- `0x1800400f4`
- `0x18004bd1c`
- `0x18004c310`
- `0x180051e80`
- `0x18008bb6c`
- `0x18008bd10`
- `0x18008bf1c`
- `0x18008bf70`
- `0x18008c000`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008c0b1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008c0b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c1eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c1eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c27f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c29b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c38a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c27f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c29b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c38a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c3a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=34 #try_helpers=1
__int64 __fastcall AppCapabilityUsageHistoryServer::GetFullUsageHistory(__int64 a1, HSTRING a2, _QWORD *a3)
{
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  unsigned int ExpirationPolicyInDays; // ebx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v18; // rax
  PCWSTR v19; // rax
  int v20; // r9d
  __int64 UsageHistoryForNonPackagedApp; // rax
  __int64 (__fastcall *v22)(__int64, unsigned __int64 *); // rbx
  int v23; // eax
  unsigned int v24; // ebx
  PCWSTR v25; // rax
  PCWSTR v26; // rax
  int v27; // r9d
  __int64 UsageHistoryForPackagedApp; // rax
  __int64 i; // rbx
  __int64 v30; // r9
  struct Windows::Foundation::DateTime *v31; // r8
  int v32; // eax
  struct Windows::Foundation::DateTime *v33; // r8
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rax
  const char *v41; // r9
  __int64 result; // rax
  int v43; // [rsp+20h] [rbp-188h]
  int v44; // [rsp+20h] [rbp-188h]
  char v45; // [rsp+40h] [rbp-168h] BYREF
  int v46; // [rsp+44h] [rbp-164h] BYREF
  unsigned __int64 UnbiasedTime[2]; // [rsp+48h] [rbp-160h] BYREF
  HSTRING string; // [rsp+58h] [rbp-150h] BYREF
  int v49; // [rsp+60h] [rbp-148h] BYREF
  __int64 v50; // [rsp+68h] [rbp-140h] BYREF
  __int64 v51; // [rsp+70h] [rbp-138h] BYREF
  __int128 v52; // [rsp+78h] [rbp-130h] BYREF
  __int64 v53; // [rsp+88h] [rbp-120h]
  _BYTE v54[8]; // [rsp+90h] [rbp-118h] BYREF
  std::_Ref_count_base *v55; // [rsp+98h] [rbp-110h]
  _BYTE v56[24]; // [rsp+A0h] [rbp-108h] BYREF
  _QWORD v57[2]; // [rsp+B8h] [rbp-F0h] BYREF
  char v58; // [rsp+C8h] [rbp-E0h]
  _BYTE v59[8]; // [rsp+D0h] [rbp-D8h] BYREF
  std::_Ref_count_base *v60; // [rsp+D8h] [rbp-D0h]
  _BYTE v61[48]; // [rsp+E0h] [rbp-C8h] BYREF
  unsigned __int64 v62; // [rsp+110h] [rbp-98h] BYREF
  int v63; // [rsp+118h] [rbp-90h]
  int v64; // [rsp+11Ch] [rbp-8Ch]
  _BYTE v65[16]; // [rsp+130h] [rbp-78h] BYREF
  __int64 v66; // [rsp+140h] [rbp-68h]
  _BYTE v67[32]; // [rsp+150h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_58c3f1a3935c368f9de145e8a5a03ba2_Traceguids);
  }
  try
  {
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
        (const char *)0x80004003LL,
        v43);
    if ( !Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(retaddr) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
        (const char *)0x80004001LL,
        v43);
    if ( !Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(retaddr) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
        (const char *)0x8000FFFFLL,
        v43);
    UnbiasedTime[0] = 0;
    QueryUnbiasedInterruptTime(UnbiasedTime);
    v46 = 0;
    v57[0] = UnbiasedTime[0];
    v57[1] = &v46;
    v58 = 1;
    v49 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 32) + 72LL))(*(_QWORD *)(a1 + 32), &v49);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
        (const char *)(unsigned int)v6,
        v43);
    v46 = (v49 == 2) + 1;
    v51 = 0;
    v50 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>>>(
           v7,
           &v51);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
        (const char *)(unsigned int)v8,
        v43);
    Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(v59);
    std::make_shared<StateRepository::Database,>(v54);
    v62 = 0x42B17A217C6A5CACLL;
    v63 = 862644144;
    v64 = 1875080158;
    v9 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
           UnbiasedTime,
           v54);
    Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(v61, v9, &v62, 0);
    v52 = 0;
    v53 = 0;
    v10 = *(_QWORD *)(a1 + 32);
    UnbiasedTime[0] = 0;
    if ( v49 == 2 )
    {
      v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v10 + 80LL);
      WindowsDeleteString(0);
      UnbiasedTime[0] = 0;
      v12 = v11(v10, UnbiasedTime);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
          (const char *)(unsigned int)v12,
          v43);
      string = 0;
      v13 = *(_QWORD *)(a1 + 32);
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v13 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v15 = v14(v13, &string);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x94,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
          (const char *)(unsigned int)v15,
          v43);
      ExpirationPolicyInDays = Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(retaddr);
      StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)UnbiasedTime[0], 0);
      std::wstring::wstring(v67, StringRawBuffer);
      v18 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(&v62, v18);
      v19 = WindowsGetStringRawBuffer(a2, 0);
      std::wstring::wstring(v65, v19);
      UsageHistoryForNonPackagedApp = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetUsageHistoryForNonPackagedApp(
                                        (unsigned int)&v62,
                                        (unsigned int)v56,
                                        (unsigned int)v65,
                                        v20,
                                        a1 + 40,
                                        (__int64)&v62,
                                        (__int64)v67,
                                        ExpirationPolicyInDays);
      std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::operator=(
        &v52,
        UsageHistoryForNonPackagedApp);
      std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::_Tidy(v56);
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(&v62);
      std::wstring::_Tidy_deallocate(v67);
      WindowsDeleteString(string);
      string = 0;
    }
    else
    {
      v22 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v10 + 64LL);
      WindowsDeleteString(0);
      UnbiasedTime[0] = 0;
      v23 = v22(v10, UnbiasedTime);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
          (const char *)(unsigned int)v23,
          v43);
      v24 = Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(retaddr);
      v25 = WindowsGetStringRawBuffer((HSTRING)UnbiasedTime[0], 0);
      std::wstring::wstring(v65, v25);
      v26 = WindowsGetStringRawBuffer(a2, 0);
      std::wstring::wstring(v67, v26);
      UsageHistoryForPackagedApp = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetUsageHistoryForPackagedApp(
                                     (unsigned int)v65,
                                     (unsigned int)v56,
                                     (unsigned int)v67,
                                     v27,
                                     a1 + 40,
                                     (__int64)v65,
                                     v24);
      std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::operator=(
        &v52,
        UsageHistoryForPackagedApp);
      std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::_Tidy(v56);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v65);
    }
    WindowsDeleteString((HSTRING)UnbiasedTime[0]);
    for ( i = v52; i != *((_QWORD *)&v52 + 1); i += 96 )
    {
      v30 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
              v56,
              v54);
      Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
        v65,
        *(_QWORD *)(i + 16),
        "Users",
        v30);
      if ( !v66 && *(_QWORD *)(i + 80) )
        std::wstring::operator=(v65, i + 64);
      v62 = 0;
      string = 0;
      v32 = Windows::Internal::CapabilityAccess::Private::DateTimeFromUTC(
              *(Windows::Internal::CapabilityAccess::Private **)(i + 8),
              (unsigned __int64)&v62,
              v31);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
          (const char *)(unsigned int)v32,
          v44);
      v34 = Windows::Internal::CapabilityAccess::Private::DateTimeFromUTC(
              *(Windows::Internal::CapabilityAccess::Private **)i,
              (unsigned __int64)&string,
              v33);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
          (const char *)(unsigned int)v34,
          v44);
      UnbiasedTime[0] = 0;
      v45 = *(_BYTE *)(i + 24);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(UnbiasedTime);
      v35 = Microsoft::WRL::Details::MakeAndInitialize<AppCapabilityUsageInstanceServer,Windows::Internal::CapabilityAccess::UsageHistory::IAppCapabilityUsageInstance,std::wstring &,std::wstring const &,unsigned char,Windows::Foundation::DateTime &,Windows::Foundation::DateTime &>(
              (unsigned int)UnbiasedTime,
              (unsigned int)v65,
              (int)i + 32,
              (unsigned int)&v45,
              (__int64)&v62,
              (__int64)&string);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
          (const char *)(unsigned int)v35,
          v44);
      v36 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v51 + 104LL))(v51, UnbiasedTime[0]);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
          (const char *)(unsigned int)v36,
          v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(UnbiasedTime);
      std::wstring::_Tidy_deallocate(v65);
    }
    v37 = v51;
    v38 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    v39 = v38(v37, &v50);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
        (const char *)(unsigned int)v39,
        v44);
    v40 = v50;
    v50 = 0;
    *a3 = v40;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_58c3f1a3935c368f9de145e8a5a03ba2_Traceguids);
    }
    std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::_Tidy(&v52);
    Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v61);
    if ( v55 )
      std::_Ref_count_base::_Decref(v55);
    if ( v60 )
      std::_Ref_count_base::_Decref(v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v58 = 0;
    lambda_45329aa8baff931999bbaaf992acf742_::operator()(v57);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC4,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityusagehistoryserver.cpp",
                           v41);
  }
  return result;
}

```

## disassembly

```asm
0x18008c000  mov     [rsp+arg_8], rbx
0x18008c005  mov     [rsp+arg_18], rsi
0x18008c00a  push    rdi
0x18008c00b  push    r12
0x18008c00d  push    r13
0x18008c00f  push    r14
0x18008c011  push    r15
0x18008c013  sub     rsp, 180h
0x18008c01a  mov     rax, cs:__security_cookie
0x18008c021  xor     rax, rsp
0x18008c024  mov     [rsp+1A8h+var_38], rax
0x18008c02c  mov     r15, r8
0x18008c02f  mov     r14, rdx
0x18008c032  mov     rsi, rcx
0x18008c035  lea     r13, WPP_GLOBAL_Control
0x18008c03c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c043  cmp     rcx, r13
0x18008c046  jz      short loc_18008C069
0x18008c048  test    byte ptr [rcx+1Ch], 1
0x18008c04c  jz      short loc_18008C069
0x18008c04e  cmp     byte ptr [rcx+19h], 5
0x18008c052  jb      short loc_18008C069
0x18008c054  mov     edx, 10h
0x18008c059  lea     r8, WPP_58c3f1a3935c368f9de145e8a5a03ba2_Traceguids
0x18008c060  mov     rcx, [rcx+10h]
0x18008c064  call    WPP_SF_
0x18008c069  mov     rcx, [rsp+1A8h]; this
0x18008c071  xor     r12d, r12d
0x18008c074  test    r15, r15
0x18008c077  jz      loc_18008C68D
0x18008c07d  call    ?IsDatabaseEnabledByEditionPolicy@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::IsDatabaseEnabledByEditionPolicy(void)
0x18008c082  mov     rcx, [rsp+1A8h]; this
0x18008c08a  test    al, al
0x18008c08c  jz      loc_18008C6A4
0x18008c092  mov     rbx, [rsp+1A8h]
0x18008c09a  call    ?DatabaseReady@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(void)
0x18008c09f  test    al, al
0x18008c0a1  jz      loc_18008C6BB
0x18008c0a7  mov     [rsp+1A8h+UnbiasedTime], r12
0x18008c0ac  lea     rcx, [rsp+1A8h+UnbiasedTime]; UnbiasedTime
0x18008c0b1  call    cs:__imp_QueryUnbiasedInterruptTime
0x18008c0b7  mov     [rsp+1A8h+var_164], r12d
0x18008c0bc  mov     rax, [rsp+1A8h+UnbiasedTime]
0x18008c0c1  mov     [rsp+1A8h+var_F0], rax
0x18008c0c9  lea     rax, [rsp+1A8h+var_164]
0x18008c0ce  mov     [rsp+1A8h+var_E8], rax
0x18008c0d6  mov     [rsp+1A8h+var_E0], 1
0x18008c0de  mov     [rsp+1A8h+var_148], r12d
0x18008c0e3  mov     rcx, [rsi+20h]
0x18008c0e7  mov     rax, [rcx]
0x18008c0ea  lea     rdx, [rsp+1A8h+var_148]
0x18008c0ef  mov     rax, [rax+48h]
0x18008c0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c0f8  mov     rcx, [rsp+1A8h]; this
0x18008c100  test    eax, eax
0x18008c102  js      loc_18008C6D6
0x18008c108  mov     eax, r12d
0x18008c10b  cmp     [rsp+1A8h+var_148], 2
0x18008c110  setz    al
0x18008c113  inc     eax
0x18008c115  mov     [rsp+1A8h+var_164], eax
0x18008c119  mov     [rsp+1A8h+var_138], r12
0x18008c11e  mov     [rsp+1A8h+var_140], r12
0x18008c123  lea     rcx, [rsp+1A8h+var_138]
0x18008c128  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008c12d  lea     rdx, [rsp+1A8h+var_138]
0x18008c132  call    ??$CreateExternalObjectVector@VAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@V?$Vector@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@@4785@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAVAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@@4785@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::CapabilityAccess::UsageHistory::AppCapabilityUsageInstance *>> * *)
0x18008c137  mov     rcx, [rsp+1A8h]; this
0x18008c13f  test    eax, eax
0x18008c141  js      loc_18008C6EB
0x18008c147  lea     rcx, [rsp+1A8h+var_D8]
0x18008c14f  call    ?Instance@?$SingletonWithFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(void)
0x18008c154  nop
0x18008c155  lea     rcx, [rsp+1A8h+var_118]
0x18008c15d  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x18008c162  nop
0x18008c163  mov     dword ptr [rsp+1A8h+var_98], 7C6A5CACh
0x18008c16e  mov     dword ptr [rsp+1A8h+var_98+4], 42B17A21h
0x18008c179  mov     [rsp+1A8h+var_90], 336AE7B0h
0x18008c184  mov     [rsp+1A8h+var_8C], 6FC373DEh
0x18008c18f  lea     rdx, [rsp+1A8h+var_118]
0x18008c197  lea     rcx, [rsp+1A8h+UnbiasedTime]
0x18008c19c  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18008c1a1  xor     r9d, r9d
0x18008c1a4  lea     r8, [rsp+1A8h+var_98]
0x18008c1ac  mov     rdx, rax
0x18008c1af  lea     rcx, [rsp+1A8h+var_C8]
0x18008c1b7  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x18008c1bc  nop
0x18008c1bd  xorps   xmm0, xmm0
0x18008c1c0  movdqu  [rsp+1A8h+var_130], xmm0
0x18008c1c6  mov     [rsp+1A8h+var_120], r12
0x18008c1ce  mov     rdi, [rsi+20h]
0x18008c1d2  mov     [rsp+1A8h+UnbiasedTime], r12
0x18008c1d7  cmp     [rsp+1A8h+var_148], 2
0x18008c1dc  jnz     loc_18008C348
0x18008c1e2  mov     rax, [rdi]
0x18008c1e5  mov     rbx, [rax+50h]
0x18008c1e9  xor     ecx, ecx; string
0x18008c1eb  call    cs:__imp_WindowsDeleteString
0x18008c1f1  mov     [rsp+1A8h+UnbiasedTime], r12
0x18008c1f6  lea     rdx, [rsp+1A8h+UnbiasedTime]
0x18008c1fb  mov     rcx, rdi
0x18008c1fe  mov     rax, rbx
0x18008c201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c206  mov     rcx, [rsp+1A8h]; this
0x18008c20e  test    eax, eax
0x18008c210  js      loc_18008C700
0x18008c216  mov     [rsp+1A8h+string], r12
0x18008c21b  mov     rdi, [rsi+20h]
0x18008c21f  mov     rax, [rdi]
0x18008c222  mov     rbx, [rax+38h]
0x18008c226  xor     ecx, ecx; string
0x18008c228  call    cs:__imp_WindowsDeleteString
0x18008c22e  mov     [rsp+1A8h+string], r12
0x18008c233  lea     rdx, [rsp+1A8h+string]
0x18008c238  mov     rcx, rdi
0x18008c23b  mov     rax, rbx
0x18008c23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c243  mov     rcx, [rsp+1A8h]; this
0x18008c24b  test    eax, eax
0x18008c24d  js      loc_18008C715
0x18008c253  call    ?GetExpirationPolicyInDays@SQL@Private@CapabilityAccess@Internal@Windows@@YAIXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(void)
0x18008c258  mov     ebx, eax
0x18008c25a  xor     edx, edx; length
0x18008c25c  mov     rcx, [rsp+1A8h+UnbiasedTime]; string
0x18008c261  call    cs:__imp_WindowsGetStringRawBuffer
0x18008c267  mov     rdx, rax
0x18008c26a  lea     rcx, [rsp+1A8h+var_58]
0x18008c272  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008c277  nop
0x18008c278  xor     edx, edx; length
0x18008c27a  mov     rcx, [rsp+1A8h+string]; string
0x18008c27f  call    cs:__imp_WindowsGetStringRawBuffer
0x18008c285  mov     rdx, rax
0x18008c288  lea     rcx, [rsp+1A8h+var_98]
0x18008c290  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008c295  nop
0x18008c296  xor     edx, edx; length
0x18008c298  mov     rcx, r14; string
0x18008c29b  call    cs:__imp_WindowsGetStringRawBuffer
0x18008c2a1  mov     rdx, rax
0x18008c2a4  lea     rcx, [rsp+1A8h+var_78]
0x18008c2ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008c2b1  nop
0x18008c2b2  lea     rax, [rsi+28h]
0x18008c2b6  mov     [rsp+1A8h+var_170], ebx
0x18008c2ba  lea     rcx, [rsp+1A8h+var_58]
0x18008c2c2  mov     [rsp+1A8h+var_178], rcx
0x18008c2c7  lea     rcx, [rsp+1A8h+var_98]
0x18008c2cf  mov     [rsp+1A8h+var_180], rcx
0x18008c2d4  mov     qword ptr [rsp+1A8h+var_188], rax
0x18008c2d9  lea     r8, [rsp+1A8h+var_78]
0x18008c2e1  lea     rdx, [rsp+1A8h+var_108]
0x18008c2e9  call    ?GetUsageHistoryForNonPackagedApp@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$vector@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@_K000I@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetUsageHistoryForNonPackagedApp(std::wstring const &,unsigned __int64,std::wstring const &,std::wstring const &,std::wstring const &,uint)
0x18008c2ee  mov     rdx, rax
0x18008c2f1  lea     rcx, [rsp+1A8h+var_130]
0x18008c2f6  call    ??4?$vector@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::operator=(std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance> &&)
0x18008c2fb  lea     rcx, [rsp+1A8h+var_108]
0x18008c303  call    ?_Tidy@?$vector@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::_Tidy(void)
0x18008c308  nop
0x18008c309  lea     rcx, [rsp+1A8h+var_78]
0x18008c311  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008c316  nop
0x18008c317  lea     rcx, [rsp+1A8h+var_98]
0x18008c31f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008c324  nop
0x18008c325  lea     rcx, [rsp+1A8h+var_58]
0x18008c32d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008c332  nop
0x18008c333  mov     rcx, [rsp+1A8h+string]; string
0x18008c338  call    cs:__imp_WindowsDeleteString
0x18008c33e  mov     [rsp+1A8h+string], r12
0x18008c343  jmp     loc_18008C423
0x18008c348  mov     rax, [rdi]
0x18008c34b  mov     rbx, [rax+40h]
0x18008c34f  xor     ecx, ecx; string
0x18008c351  call    cs:__imp_WindowsDeleteString
0x18008c357  mov     [rsp+1A8h+UnbiasedTime], r12
0x18008c35c  lea     rdx, [rsp+1A8h+UnbiasedTime]
0x18008c361  mov     rcx, rdi
0x18008c364  mov     rax, rbx
0x18008c367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c36c  mov     rcx, [rsp+1A8h]; this
0x18008c374  test    eax, eax
0x18008c376  js      loc_18008C72A
0x18008c37c  call    ?GetExpirationPolicyInDays@SQL@Private@CapabilityAccess@Internal@Windows@@YAIXZ; Windows::Internal::CapabilityAccess::Private::SQL::GetExpirationPolicyInDays(void)
0x18008c381  mov     ebx, eax
0x18008c383  xor     edx, edx; length
0x18008c385  mov     rcx, [rsp+1A8h+UnbiasedTime]; string
0x18008c38a  call    cs:__imp_WindowsGetStringRawBuffer
0x18008c390  mov     rdx, rax
0x18008c393  lea     rcx, [rsp+1A8h+var_78]
0x18008c39b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008c3a0  nop
0x18008c3a1  xor     edx, edx; length
0x18008c3a3  mov     rcx, r14; string
0x18008c3a6  call    cs:__imp_WindowsGetStringRawBuffer
0x18008c3ac  mov     rdx, rax
0x18008c3af  lea     rcx, [rsp+1A8h+var_58]
0x18008c3b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008c3bc  nop
0x18008c3bd  lea     rax, [rsi+28h]
0x18008c3c1  mov     dword ptr [rsp+1A8h+var_178], ebx
0x18008c3c5  lea     rcx, [rsp+1A8h+var_78]
0x18008c3cd  mov     [rsp+1A8h+var_180], rcx
0x18008c3d2  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x18008c3d7  lea     r8, [rsp+1A8h+var_58]
0x18008c3df  lea     rdx, [rsp+1A8h+var_108]
0x18008c3e7  call    ?GetUsageHistoryForPackagedApp@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$vector@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@_K00I@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetUsageHistoryForPackagedApp(std::wstring const &,unsigned __int64,std::wstring const &,std::wstring const &,uint)
0x18008c3ec  mov     rdx, rax
0x18008c3ef  lea     rcx, [rsp+1A8h+var_130]
0x18008c3f4  call    ??4?$vector@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::operator=(std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance> &&)
0x18008c3f9  lea     rcx, [rsp+1A8h+var_108]
0x18008c401  call    ?_Tidy@?$vector@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@V?$allocator@UCapabilityUsageInstance@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@AEAAXXZ; std::vector<Windows::Internal::CapabilityAccess::Private::CapabilityUsageInstance>::_Tidy(void)
0x18008c406  nop
0x18008c407  lea     rcx, [rsp+1A8h+var_58]
0x18008c40f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008c414  nop
0x18008c415  lea     rcx, [rsp+1A8h+var_78]
0x18008c41d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008c422  nop
0x18008c423  mov     rcx, [rsp+1A8h+UnbiasedTime]; string
0x18008c428  call    cs:__imp_WindowsDeleteString
0x18008c42e  mov     rbx, qword ptr [rsp+1A8h+var_130]
0x18008c433  cmp     rbx, qword ptr [rsp+1A8h+var_130+8]
0x18008c43b  jz      loc_18008C57D
0x18008c441  lea     rdx, [rsp+1A8h+var_118]
0x18008c449  lea     rcx, [rsp+1A8h+var_108]
0x18008c451  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18008c456  mov     r9, rax
0x18008c459  lea     r8, aUsers; "Users"
0x18008c460  mov     rdx, [rbx+10h]
0x18008c464  lea     rcx, [rsp+1A8h+var_78]
0x18008c46c  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x18008c471  nop
0x18008c472  cmp     [rsp+1A8h+var_68], r12
0x18008c47a  jnz     short loc_18008C493
0x18008c47c  cmp     [rbx+50h], r12
0x18008c480  jz      short loc_18008C493
0x18008c482  lea     rdx, [rbx+40h]
0x18008c486  lea     rcx, [rsp+1A8h+var_78]
0x18008c48e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008c493  mov     [rsp+1A8h+var_98], r12
0x18008c49b  mov     [rsp+1A8h+string], r12
0x18008c4a0  lea     rdx, [rsp+1A8h+var_98]; unsigned __int64
0x18008c4a8  mov     rcx, [rbx+8]; this
0x18008c4ac  call    ?DateTimeFromUTC@Private@CapabilityAccess@Internal@Windows@@YAJ_KPEAUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::DateTimeFromUTC(unsigned __int64,Windows::Foundation::DateTime *)
0x18008c4b1  mov     rcx, [rsp+1A8h]; this
0x18008c4b9  test    eax, eax
0x18008c4bb  js      loc_18008C73F
0x18008c4c1  lea     rdx, [rsp+1A8h+string]; unsigned __int64
0x18008c4c6  mov     rcx, [rbx]; this
0x18008c4c9  call    ?DateTimeFromUTC@Private@CapabilityAccess@Internal@Windows@@YAJ_KPEAUDateTime@Foundation@4@@Z; Windows::Internal::CapabilityAccess::Private::DateTimeFromUTC(unsigned __int64,Windows::Foundation::DateTime *)
0x18008c4ce  mov     rcx, [rsp+1A8h]; this
0x18008c4d6  test    eax, eax
0x18008c4d8  js      loc_18008C753
0x18008c4de  mov     [rsp+1A8h+UnbiasedTime], r12
0x18008c4e3  mov     al, [rbx+18h]
0x18008c4e6  mov     [rsp+1A8h+var_168], al
0x18008c4ea  lea     rcx, [rsp+1A8h+UnbiasedTime]
0x18008c4ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008c4f4  lea     r8, [rbx+20h]
0x18008c4f8  lea     rax, [rsp+1A8h+string]
0x18008c4fd  mov     [rsp+1A8h+var_180], rax
0x18008c502  lea     rax, [rsp+1A8h+var_98]
0x18008c50a  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x18008c50f  lea     r9, [rsp+1A8h+var_168]
0x18008c514  lea     rdx, [rsp+1A8h+var_78]
0x18008c51c  lea     rcx, [rsp+1A8h+UnbiasedTime]
0x18008c521  call    ??$MakeAndInitialize@VAppCapabilityUsageInstanceServer@@UIAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV78@EAEAUDateTime@Foundation@6@AEAU9Foundation@6@@Details@WRL@Microsoft@@YAJPEAPEAUIAppCapabilityUsageInstance@UsageHistory@CapabilityAccess@Internal@Windows@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV89@$$QEAEAEAUDateTime@Foundation@7@4@Z; Microsoft::WRL::Details::MakeAndInitialize<AppCapabilityUsageInstanceServer,Windows::Internal::CapabilityAccess::UsageHistory::IAppCapabilityUsageInstance,std::wstring &,std::wstring const &,uchar,Windows::Foundation::DateTime &,Windows::Foundation::DateTime &>(Windows::Internal::CapabilityAccess::UsageHistory::IAppCapabilityUsageInstance * *,std::wstring &,std::wstring const &,uchar &&,Windows::Foundation::DateTime &,Windows::Foundation::DateTime &)
0x18008c526  mov     rcx, [rsp+1A8h]; this
0x18008c52e  test    eax, eax
0x18008c530  js      loc_18008C768
0x18008c536  mov     rcx, [rsp+1A8h+var_138]
0x18008c53b  mov     rax, [rcx]
0x18008c53e  mov     rdx, [rsp+1A8h+UnbiasedTime]
0x18008c543  mov     rax, [rax+68h]
0x18008c547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c54c  mov     rcx, [rsp+1A8h]; this
0x18008c554  test    eax, eax
0x18008c556  js      loc_18008C77C
0x18008c55c  lea     rcx, [rsp+1A8h+UnbiasedTime]
0x18008c561  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008c566  nop
0x18008c567  lea     rcx, [rsp+1A8h+var_78]
0x18008c56f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008c574  add     rbx, 60h ; '`'
0x18008c578  jmp     loc_18008C433
0x18008c57d  mov     rdi, [rsp+1A8h+var_138]
0x18008c582  mov     rax, [rdi]
0x18008c585  mov     rbx, [rax+40h]
0x18008c589  lea     rcx, [rsp+1A8h+var_140]
0x18008c58e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008c593  lea     rdx, [rsp+1A8h+var_140]
0x18008c598  mov     rcx, rdi
0x18008c59b  mov     rax, rbx
0x18008c59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c5a3  mov     rcx, [rsp+1A8h]; this
0x18008c5ab  test    eax, eax
  ... truncated ...
```
