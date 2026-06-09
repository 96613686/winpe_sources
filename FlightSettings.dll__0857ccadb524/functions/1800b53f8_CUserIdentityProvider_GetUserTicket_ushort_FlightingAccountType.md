# CUserIdentityProvider::GetUserTicket(ushort * *,FlightingAccountType *)

- ea: `0x1800b53f8`
- end: `0x1800b5e17`
- name: `?GetUserTicket@CUserIdentityProvider@@QEAAJPEAPEAGPEAW4FlightingAccountType@@@Z`
- size: `2591`
- prototype: `__int64 __fastcall(CUserIdentityProvider *__hidden this, unsigned __int16 **, enum FlightingAccountType *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009c980`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x180019214`
- `0x18001c6f4`
- `0x18001d244`
- `0x18001ec78`
- `0x1800859a4`
- `0x180085a24`
- `0x180086644`
- `0x180086944`
- `0x180089b68`
- `0x18008a2fc`
- `0x18008aaf0`
- `0x18008f6b4`
- `0x18008fbd8`
- `0x1800960cc`
- `0x1800961e0`
- `0x1800980c4`
- `0x1800996b4`
- `0x1800afb54`
- `0x1800afb88`
- `0x1800b12d8`
- `0x1800b1e24`
- `0x1800b2934`
- `0x1800b3600`
- `0x1800b3af0`
- `0x1800b53f8`
- `0x1800b60b4`
- `0x1800b6dbc`
- `0x1800b70e0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b576c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b580e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b576c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b580e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b5762`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b5804`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b5762`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b5804`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b5819`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5524`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b5524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b5c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b5c59`

## string_xrefs

- `0x1800b5a7f`: `##DELETE##`
- `0x1800b54da`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b553a`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b584d`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b5bdd`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b5c83`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b5dda`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CUserIdentityProvider::GetUserTicket(
        CUserIdentityProvider *this,
        unsigned __int16 **a2,
        enum FlightingAccountType *a3)
{
  int v4; // esi
  __int64 *v5; // r12
  _WORD *v6; // rax
  __int64 v7; // r15
  _DWORD *v8; // r14
  unsigned int v9; // edx
  unsigned __int64 v10; // rdx
  int active; // ebx
  int DefaultAccount; // edi
  HRESULT v13; // eax
  int FlightingRegString; // eax
  unsigned __int64 v15; // rdx
  char v16; // r8
  unsigned __int64 v17; // rdx
  int v18; // eax
  unsigned __int64 v19; // rdx
  HSTRING v20; // rbx
  int AADUserTicketForAccountId; // eax
  Flighting::Helpers *v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  PCWSTR StringRawBuffer; // rax
  int v29; // eax
  unsigned int v30; // edx
  unsigned __int64 v31; // rdx
  unsigned __int64 v33; // rdx
  enum FlightingAccountType *v34; // rcx
  __int64 v35; // r8
  int v36; // eax
  unsigned int v37; // ebx
  int ppv; // [rsp+20h] [rbp-E0h]
  char v39; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v40[7]; // [rsp+31h] [rbp-CFh] BYREF
  HSTRING v41; // [rsp+38h] [rbp-C8h] BYREF
  bool v42; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v43; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Token; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v45[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v46; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h]
  __int64 v51; // [rsp+80h] [rbp-80h]
  LPWSTR ppwsz; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h]
  unsigned __int16 **v55; // [rsp+A0h] [rbp-60h]
  enum FlightingAccountType *v56; // [rsp+A8h] [rbp-58h]
  LPVOID *v57; // [rsp+B0h] [rbp-50h]
  char *v58; // [rsp+B8h] [rbp-48h]
  __int64 *v59; // [rsp+C0h] [rbp-40h]
  char v60; // [rsp+C8h] [rbp-38h]
  _QWORD v61[42]; // [rsp+D0h] [rbp-30h] BYREF
  char v62; // [rsp+220h] [rbp+120h]
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v56 = a3;
  v55 = a2;
  v4 = 0;
  *a2 = 0;
  *(_DWORD *)a3 = 0;
  v5 = (__int64 *)((char *)this + 80);
  v6 = (_WORD *)*((_QWORD *)this + 10);
  v7 = -1;
  if ( v6 )
  {
    if ( *v6 )
    {
      v8 = (_DWORD *)((char *)this + 104);
      if ( *((_DWORD *)this + 26) )
        goto LABEL_90;
    }
  }
  wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v61);
  v61[0] = &FlightSettingsAPITelemetryClass::FlightingUserTicketRequest::`vftable';
  v62 = 0;
  FlightSettingsAPITelemetryClass::FlightingUserTicketRequest::StartActivity(
    (FlightSettingsAPITelemetryClass::FlightingUserTicketRequest *)v61,
    v9);
  v40[0] = 0;
  v42 = 0;
  FlightSettingsAPICommon::IsLocalSystem(&v42);
  if ( v42 )
  {
    active = ImpersonationHelper::ImpersonateActiveUser((struct UstCommon::CImpersonator *)v40);
    v46 = active;
    if ( active < 0 )
    {
      FlightSettingsAPITelemetryClass::ImpersonationFailed<long &>(&v46, v10);
      DefaultAccount = -2146698748;
      if ( active != -2146698748 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
          (const char *)(unsigned int)active,
          ppv);
        DefaultAccount = active;
      }
      goto LABEL_85;
    }
  }
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  v13 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v43);
  DefaultAccount = v13;
  if ( v13 < 0 )
    goto LABEL_9;
  v48 = 0;
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v43 + 32LL))(v43, 5, &v48);
  DefaultAccount = v13;
  if ( v13 < 0 )
    goto LABEL_9;
  if ( v48 == 1 )
  {
    v39 = 0;
  }
  else
  {
    v39 = 1;
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, 1);
    DefaultAccount = v13;
    if ( v13 < 0 )
    {
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v13,
        ppv);
LABEL_84:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
      goto LABEL_85;
    }
  }
  v57 = &v43;
  v58 = &v39;
  v59 = &v48;
  v60 = 1;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
  v50 = -1;
  v51 = -1;
  Token = (HANDLE)-2147483646LL;
  FlightingRegString = FSRegUtils::GetFlightingRegString((HKEY *)&Token, 4u, L"Id", &v49);
  v46 = 0;
  Token = (HANDLE)-2147483646LL;
  if ( FlightingRegString >= 0 )
  {
    v8 = (_DWORD *)((char *)this + 104);
    if ( (int)FSRegUtils::GetFlightingRegDWORD((HKEY *)&Token, 4u, L"Type", (unsigned int *)&v46) >= 0 )
    {
      *v8 = v46;
    }
    else
    {
      Token = 0;
      UstCommon::CComTemporaryRevertToSelf::RevertToSelf(&Token);
      *v8 = 1;
      v47 = -2147483646;
      FSRegUtils::SetFlightingRegDWORD(&v47, 4, L"Type", 1);
      if ( Token )
      {
        if ( !SetThreadToken(0, Token) )
          GetLastError();
        CloseHandle(Token);
      }
    }
    LODWORD(v41) = 0;
    v47 = -2147483646;
    if ( (int)FSRegUtils::GetFlightingRegDWORD((HKEY *)&v47, 4u, L"IsPrimary", (unsigned int *)&v41) < 0 )
    {
      v45[0] = 0;
      CUserIdentityProvider::IsPrimaryAccount(this, v49, (unsigned int)*v8, v45);
      Token = 0;
      UstCommon::CComTemporaryRevertToSelf::RevertToSelf(&Token);
      v47 = -2147483646;
      FSRegUtils::SetFlightingRegDWORD(&v47, 4, L"IsPrimary", v45[0]);
      if ( Token )
      {
        if ( !SetThreadToken(0, Token) )
          GetLastError();
        CloseHandle(Token);
      }
    }
  }
  else
  {
    FSRegUtils::GetFlightingRegDWORD((HKEY *)&Token, 4u, L"Status", (unsigned int *)&v46);
    if ( (v46 & 8) != 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
      if ( v39 )
      {
        LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
        if ( (int)v41 < 0 )
          FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v15);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
      DefaultAccount = -2147023579;
      goto LABEL_85;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    v50 = -1;
    v51 = -1;
    v8 = (_DWORD *)((char *)this + 104);
    DefaultAccount = CUserIdentityProvider::GetDefaultAccount(this, (CUserIdentityProvider *)((char *)this + 104), &v49);
    if ( DefaultAccount < 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
      if ( v39 )
      {
        LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
        if ( (int)v41 < 0 )
          FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v17);
      }
      goto LABEL_84;
    }
  }
  v41 = 0;
  v47 = (__int64)v49;
  v18 = Windows::Internal::String::Initialize<unsigned short const *>(&v41, &v47, v16);
  DefaultAccount = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v18,
      ppv);
    Windows::Internal::String::~String((Windows::Internal::String *)&v41);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    if ( v39 )
    {
      LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
      if ( (int)v41 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v19);
    }
    goto LABEL_84;
  }
  v20 = 0;
  Token = 0;
  if ( *v8 == 2 )
  {
    AADUserTicketForAccountId = CUserIdentityProvider::GetAADUserTicketForAccountId(this, v41, (HSTRING *)&Token);
LABEL_49:
    v4 = AADUserTicketForAccountId;
    if ( AADUserTicketForAccountId == -895025145 || AADUserTicketForAccountId == -2146893802 )
    {
      Windows::Internal::String::~String((Windows::Internal::String *)&Token);
      Windows::Internal::String::~String((Windows::Internal::String *)&v41);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
      if ( v39 )
      {
        LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
        if ( (int)v41 < 0 )
          FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v24);
      }
      goto LABEL_62;
    }
    v20 = (HSTRING)Token;
    goto LABEL_52;
  }
  if ( *v8 == 1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59227329>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59227329>::GetImpl'::`2'::impl)
      && Flighting::Helpers::GetFlightingMsaV2UserEnabled(v22) )
    {
      AADUserTicketForAccountId = CUserIdentityProvider::GetMSAUserJsonWebTokenForAccountId(
                                    this,
                                    v41,
                                    (HSTRING *)&Token);
    }
    else
    {
      AADUserTicketForAccountId = CUserIdentityProvider::GetMSAUserTicketForAccountId(this, v41, (HSTRING *)&Token);
    }
    goto LABEL_49;
  }
LABEL_52:
  ppwsz = 0;
  v53 = 0;
  v54 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppwsz);
  v53 = -1;
  v54 = -1;
  if ( (int)FlightSettingsAPICommon::GetCallerImageName(&ppwsz) >= 0
    && (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       &ppwsz,
                       L"systemsettings.exe",
                       -1) != 2 )
  {
    DefaultAccount = -2138701812;
    if ( v4 == -2138701812 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppwsz);
      Windows::Internal::String::~String((Windows::Internal::String *)&Token);
      Windows::Internal::String::~String((Windows::Internal::String *)&v41);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
      if ( v39 )
      {
        LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
        if ( (int)v41 < 0 )
          FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v23);
      }
      goto LABEL_84;
    }
  }
  DefaultAccount = -2147023579;
  if ( v4 == -2147023579 )
  {
    if ( v42 )
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v40);
    v47 = -2147483646;
    FSRegUtils::SetFlightingRegString((HKEY *)&v47, 4u, L"Id", L"##DELETE##");
    v47 = -2147483646;
    FSRegUtils::SetFlightingRegString((HKEY *)&v47, 4u, L"Type", L"##DELETE##");
    v47 = -2147483646;
    FSRegUtils::SetFlightingRegString((HKEY *)&v47, 4u, L"IsPrimary", L"##DELETE##");
    v47 = -2147483646;
    FSRegUtils::SetFlightingRegDWORD(&v47, 4, L"Status", 8);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppwsz);
    Windows::Internal::String::~String((Windows::Internal::String *)&Token);
    Windows::Internal::String::~String((Windows::Internal::String *)&v41);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    if ( v39 )
    {
      LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
      if ( (int)v41 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v25);
    }
    goto LABEL_84;
  }
  DefaultAccount = -895025148;
  if ( v4 == -895025148 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppwsz);
    Windows::Internal::String::~String((Windows::Internal::String *)&Token);
    Windows::Internal::String::~String((Windows::Internal::String *)&v41);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    if ( v39 )
    {
      LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
      if ( (int)v41 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v26);
    }
    goto LABEL_84;
  }
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppwsz);
    Windows::Internal::String::~String((Windows::Internal::String *)&Token);
    Windows::Internal::String::~String((Windows::Internal::String *)&v41);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    if ( v39 )
    {
      LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
      if ( (int)v41 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v27);
    }
LABEL_62:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    DefaultAccount = v4;
LABEL_85:
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v40);
    FlightSettingsAPITelemetryClass::FlightingUserTicketRequest::~FlightingUserTicketRequest((FlightSettingsAPITelemetryClass::FlightingUserTicketRequest *)v61);
    return (unsigned int)DefaultAccount;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v20, 0);
  v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          v5,
          StringRawBuffer,
          -1);
  DefaultAccount = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v29,
      ppv);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppwsz);
    Windows::Internal::String::~String((Windows::Internal::String *)&Token);
    Windows::Internal::String::~String((Windows::Internal::String *)&v41);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    if ( v39 )
    {
      LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
      if ( (int)v41 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v31);
    }
    goto LABEL_84;
  }
  FlightSettingsAPITelemetryClass::FlightingUserTicketRequest::Stop(
    (FlightSettingsAPITelemetryClass::FlightingUserTicketRequest *)v61,
    v30);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppwsz);
  Windows::Internal::String::~String((Windows::Internal::String *)&Token);
  Windows::Internal::String::~String((Windows::Internal::String *)&v41);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
  if ( v39 )
  {
    LODWORD(v41) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, 5, v48);
    if ( (int)v41 < 0 )
      FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v41, v33);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v40);
  FlightSettingsAPITelemetryClass::FlightingUserTicketRequest::~FlightingUserTicketRequest((FlightSettingsAPITelemetryClass::FlightingUserTicketRequest *)v61);
  a2 = v55;
LABEL_90:
  v34 = v56;
  *(_DWORD *)v56 = *v8;
  v35 = *v5;
  do
    ++v7;
  while ( *(_WORD *)(v35 + 2 * v7) );
  v36 = _AllocStringWorker<CTCoAllocPolicy>(v34, a2, v35);
  v37 = v36;
  if ( v36 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v36,
      ppv);
  return v37;
}

```

## disassembly

```asm
0x1800b53f8  mov     [rsp-8+arg_18], rbx
0x1800b53fd  push    rbp
0x1800b53fe  push    rsi
0x1800b53ff  push    rdi
0x1800b5400  push    r12
0x1800b5402  push    r13
0x1800b5404  push    r14
0x1800b5406  push    r15
0x1800b5408  lea     rbp, [rsp-140h]
0x1800b5410  sub     rsp, 240h
0x1800b5417  mov     rax, cs:__security_cookie
0x1800b541e  xor     rax, rsp
0x1800b5421  mov     [rbp+170h+var_40], rax
0x1800b5428  mov     [rbp+170h+var_1C8], r8
0x1800b542c  mov     [rbp+170h+var_1D0], rdx
0x1800b5430  mov     r13, rcx
0x1800b5433  xor     esi, esi
0x1800b5435  mov     [rdx], rsi
0x1800b5438  mov     [r8], esi
0x1800b543b  lea     r12, [rcx+50h]
0x1800b543f  mov     rax, [r12]
0x1800b5443  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800b5447  test    rax, rax
0x1800b544a  jz      short loc_1800B545E
0x1800b544c  cmp     [rax], si
0x1800b544f  jz      short loc_1800B545E
0x1800b5451  lea     r14, [rcx+68h]
0x1800b5455  cmp     [r14], esi
0x1800b5458  jnz     loc_1800B5DA6
0x1800b545e  lea     rdx, aFlightingusert; "FlightingUserTicketRequest"
0x1800b5465  lea     rcx, [rbp+170h+var_1A0]; struct wil::details::IFailureCallback *
0x1800b5469  call    ??0?$ActivityBase@VFlightSettingsAPITelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800b546e  lea     rax, ??_7FlightingUserTicketRequest@FlightSettingsAPITelemetryClass@@6B@; const FlightSettingsAPITelemetryClass::FlightingUserTicketRequest::`vftable'
0x1800b5475  mov     [rbp+170h+var_1A0], rax
0x1800b5479  mov     [rbp+170h+var_50], sil
0x1800b5480  lea     rcx, [rbp+170h+var_1A0]; this
0x1800b5484  call    ?StartActivity@FlightingUserTicketRequest@FlightSettingsAPITelemetryClass@@QEAAXK@Z; FlightSettingsAPITelemetryClass::FlightingUserTicketRequest::StartActivity(ulong)
0x1800b5489  nop
0x1800b548a  mov     [rsp+270h+var_23F], sil
0x1800b548f  mov     [rsp+270h+var_230], sil
0x1800b5494  lea     rcx, [rsp+270h+var_230]; bool *
0x1800b5499  call    ?IsLocalSystem@FlightSettingsAPICommon@@SAJPEA_N@Z; FlightSettingsAPICommon::IsLocalSystem(bool *)
0x1800b549e  cmp     [rsp+270h+var_230], sil
0x1800b54a3  jz      short loc_1800B54F2
0x1800b54a5  lea     rcx, [rsp+270h+var_23F]; this
0x1800b54aa  call    ?ImpersonateActiveUser@ImpersonationHelper@@SAJPEAVCImpersonator@UstCommon@@@Z; ImpersonationHelper::ImpersonateActiveUser(UstCommon::CImpersonator *)
0x1800b54af  mov     ebx, eax
0x1800b54b1  mov     [rsp+270h+var_214], eax
0x1800b54b5  test    eax, eax
0x1800b54b7  jns     short loc_1800B54F2
0x1800b54b9  lea     rcx, [rsp+270h+var_214]
0x1800b54be  call    ??$ImpersonationFailed@AEAJ@FlightSettingsAPITelemetryClass@@SAXAEAJ@Z; FlightSettingsAPITelemetryClass::ImpersonationFailed<long &>(long &)
0x1800b54c3  mov     edi, 800BFA04h
0x1800b54c8  cmp     ebx, edi
0x1800b54ca  jz      loc_1800B5CFE
0x1800b54d0  mov     rcx, [rbp+178h]; this
0x1800b54d7  mov     r9d, ebx; char *
0x1800b54da  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b54e1  mov     edx, 0C4h; void *
0x1800b54e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b54eb  mov     edi, ebx
0x1800b54ed  jmp     loc_1800B5CFE
0x1800b54f2  mov     [rsp+270h+var_228], rsi
0x1800b54f7  lea     rcx, [rsp+270h+var_228]
0x1800b54fc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b5501  lea     rax, [rsp+270h+var_228]
0x1800b5506  mov     [rsp+270h+ppv], rax; int
0x1800b550b  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800b5512  mov     r14d, 1
0x1800b5518  mov     r8d, r14d; dwClsContext
0x1800b551b  xor     edx, edx; pUnkOuter
0x1800b551d  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800b5524  call    cs:__imp_CoCreateInstance
0x1800b552a  mov     edi, eax
0x1800b552c  test    eax, eax
0x1800b552e  jns     short loc_1800B5550
0x1800b5530  mov     rcx, [rbp+178h]; this
0x1800b5537  mov     r9d, eax; char *
0x1800b553a  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b5541  mov     edx, 0CAh; void *
0x1800b5546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b554b  jmp     loc_1800B5CF3
0x1800b5550  mov     [rsp+270h+var_208], rsi
0x1800b5555  mov     rcx, [rsp+270h+var_228]
0x1800b555a  mov     rax, [rcx]
0x1800b555d  lea     r8, [rsp+270h+var_208]
0x1800b5562  mov     ebx, 5
0x1800b5567  mov     edx, ebx
0x1800b5569  mov     rax, [rax+20h]
0x1800b556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5572  mov     edi, eax
0x1800b5574  test    eax, eax
0x1800b5576  js      short loc_1800B5530
0x1800b5578  cmp     [rsp+270h+var_208], r14
0x1800b557d  jz      short loc_1800B55A2
0x1800b557f  mov     [rsp+270h+var_240], r14b
0x1800b5584  mov     rcx, [rsp+270h+var_228]
0x1800b5589  mov     rax, [rcx]
0x1800b558c  mov     r8, r14
0x1800b558f  mov     edx, ebx
0x1800b5591  mov     rax, [rax+18h]
0x1800b5595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b559a  mov     edi, eax
0x1800b559c  test    eax, eax
0x1800b559e  jns     short loc_1800B55A7
0x1800b55a0  jmp     short loc_1800B5530
0x1800b55a2  mov     [rsp+270h+var_240], sil
0x1800b55a7  lea     rax, [rsp+270h+var_228]
0x1800b55ac  mov     [rbp+170h+var_1C0], rax
0x1800b55b0  lea     rax, [rsp+270h+var_240]
0x1800b55b5  mov     [rbp+170h+var_1B8], rax
0x1800b55b9  lea     rax, [rsp+270h+var_208]
0x1800b55be  mov     [rbp+170h+var_1B0], rax
0x1800b55c2  mov     [rbp+170h+var_1A8], r14b
0x1800b55c6  mov     [rsp+270h+var_200], rsi
0x1800b55cb  mov     [rsp+270h+var_1F8], rsi
0x1800b55d0  mov     [rbp+170h+var_1F0], rsi
0x1800b55d4  lea     rcx, [rsp+270h+var_200]
0x1800b55d9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b55de  mov     [rsp+270h+var_1F8], r15
0x1800b55e3  mov     [rbp+170h+var_1F0], r15
0x1800b55e7  mov     rdi, 0FFFFFFFF80000002h
0x1800b55ee  mov     [rsp+270h+Token], rdi
0x1800b55f3  lea     r9, [rsp+270h+var_200]
0x1800b55f8  lea     r8, aId; "Id"
0x1800b55ff  mov     r14d, 4
0x1800b5605  mov     edx, r14d
0x1800b5608  lea     rcx, [rsp+270h+Token]
0x1800b560d  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x1800b5612  mov     [rsp+270h+var_214], esi
0x1800b5616  mov     [rsp+270h+Token], rdi
0x1800b561b  lea     r9, [rsp+270h+var_214]
0x1800b5620  lea     rcx, [rsp+270h+Token]
0x1800b5625  test    eax, eax
0x1800b5627  jns     loc_1800B5707
0x1800b562d  lea     r8, aStatus; "Status"
0x1800b5634  mov     edx, r14d
0x1800b5637  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x1800b563c  test    byte ptr [rsp+270h+var_214], 8
0x1800b5641  jz      short loc_1800B5694
0x1800b5643  lea     rcx, [rsp+270h+var_200]
0x1800b5648  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b564d  nop
0x1800b564e  cmp     [rsp+270h+var_240], sil
0x1800b5653  jz      short loc_1800B5680
0x1800b5655  mov     rcx, [rsp+270h+var_228]
0x1800b565a  mov     rax, [rcx]
0x1800b565d  mov     r8, [rsp+270h+var_208]
0x1800b5662  mov     edx, ebx
0x1800b5664  mov     rax, [rax+18h]
0x1800b5668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b566d  mov     dword ptr [rsp+270h+var_238], eax
0x1800b5671  test    eax, eax
0x1800b5673  jns     short loc_1800B5680
0x1800b5675  lea     rcx, [rsp+270h+var_238]
0x1800b567a  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b567f  nop
0x1800b5680  lea     rcx, [rsp+270h+var_228]
0x1800b5685  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b568a  mov     edi, 80070525h
0x1800b568f  jmp     loc_1800B5CFE
0x1800b5694  lea     rcx, [rsp+270h+var_200]
0x1800b5699  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b569e  mov     [rsp+270h+var_1F8], r15
0x1800b56a3  mov     [rbp+170h+var_1F0], r15
0x1800b56a7  lea     r14, [r13+68h]
0x1800b56ab  lea     r8, [rsp+270h+var_200]; unsigned __int16 **
0x1800b56b0  mov     rdx, r14; enum FlightingAccountType *
0x1800b56b3  mov     rcx, r13; this
0x1800b56b6  call    ?GetDefaultAccount@CUserIdentityProvider@@AEAAJPEAW4FlightingAccountType@@PEAPEAG@Z; CUserIdentityProvider::GetDefaultAccount(FlightingAccountType *,ushort * *)
0x1800b56bb  mov     edi, eax
0x1800b56bd  test    eax, eax
0x1800b56bf  jns     loc_1800B581F
0x1800b56c5  lea     rcx, [rsp+270h+var_200]
0x1800b56ca  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b56cf  nop
0x1800b56d0  cmp     [rsp+270h+var_240], sil
0x1800b56d5  jz      short loc_1800B5702
0x1800b56d7  mov     rcx, [rsp+270h+var_228]
0x1800b56dc  mov     rax, [rcx]
0x1800b56df  mov     r8, [rsp+270h+var_208]
0x1800b56e4  mov     edx, ebx
0x1800b56e6  mov     rax, [rax+18h]
0x1800b56ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b56ef  mov     dword ptr [rsp+270h+var_238], eax
0x1800b56f3  test    eax, eax
0x1800b56f5  jns     short loc_1800B5702
0x1800b56f7  lea     rcx, [rsp+270h+var_238]
0x1800b56fc  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b5701  nop
0x1800b5702  jmp     loc_1800B5CF3
0x1800b5707  lea     r14, [r13+68h]
0x1800b570b  lea     r8, aType; "Type"
0x1800b5712  mov     edx, 4
0x1800b5717  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x1800b571c  test    eax, eax
0x1800b571e  jns     short loc_1800B577F
0x1800b5720  mov     [rsp+270h+Token], rsi
0x1800b5725  lea     rcx, [rsp+270h+Token]; TokenHandle
0x1800b572a  call    ?RevertToSelf@CComTemporaryRevertToSelf@UstCommon@@QEAAJXZ; UstCommon::CComTemporaryRevertToSelf::RevertToSelf(void)
0x1800b572f  mov     dword ptr [r14], 1
0x1800b5736  mov     [rsp+270h+var_210], rdi
0x1800b573b  mov     r9d, 1
0x1800b5741  lea     r8, aType; "Type"
0x1800b5748  lea     edx, [r9+3]
0x1800b574c  lea     rcx, [rsp+270h+var_210]
0x1800b5751  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800b5756  mov     rdx, [rsp+270h+Token]; Token
0x1800b575b  test    rdx, rdx
0x1800b575e  jz      short loc_1800B5786
0x1800b5760  xor     ecx, ecx; Thread
0x1800b5762  call    cs:__imp_SetThreadToken
0x1800b5768  test    eax, eax
0x1800b576a  jnz     short loc_1800B5772
0x1800b576c  call    cs:__imp_GetLastError
0x1800b5772  mov     rcx, [rsp+270h+Token]; hObject
0x1800b5777  call    cs:__imp_CloseHandle
0x1800b577d  jmp     short loc_1800B5786
0x1800b577f  mov     eax, [rsp+270h+var_214]
0x1800b5783  mov     [r14], eax
0x1800b5786  mov     dword ptr [rsp+270h+var_238], esi
0x1800b578a  mov     [rsp+270h+var_210], rdi
0x1800b578f  lea     r9, [rsp+270h+var_238]
0x1800b5794  lea     r8, aIsprimary; "IsPrimary"
0x1800b579b  mov     edx, 4
0x1800b57a0  lea     rcx, [rsp+270h+var_210]
0x1800b57a5  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x1800b57aa  test    eax, eax
0x1800b57ac  jns     short loc_1800B581F
0x1800b57ae  mov     [rsp+270h+var_218], sil
0x1800b57b3  lea     r9, [rsp+270h+var_218]
0x1800b57b8  mov     r8d, [r14]
0x1800b57bb  mov     rdx, [rsp+270h+var_200]
0x1800b57c0  mov     rcx, r13
0x1800b57c3  call    ?IsPrimaryAccount@CUserIdentityProvider@@AEAAJPEBGW4FlightingAccountType@@PEA_N@Z; CUserIdentityProvider::IsPrimaryAccount(ushort const *,FlightingAccountType,bool *)
0x1800b57c8  mov     [rsp+270h+Token], rsi
0x1800b57cd  lea     rcx, [rsp+270h+Token]; TokenHandle
0x1800b57d2  call    ?RevertToSelf@CComTemporaryRevertToSelf@UstCommon@@QEAAJXZ; UstCommon::CComTemporaryRevertToSelf::RevertToSelf(void)
0x1800b57d7  mov     [rsp+270h+var_210], rdi
0x1800b57dc  movzx   r9d, [rsp+270h+var_218]
0x1800b57e2  lea     r8, aIsprimary; "IsPrimary"
0x1800b57e9  mov     edx, 4
0x1800b57ee  lea     rcx, [rsp+270h+var_210]
0x1800b57f3  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800b57f8  mov     rdx, [rsp+270h+Token]; Token
0x1800b57fd  test    rdx, rdx
0x1800b5800  jz      short loc_1800B581F
0x1800b5802  xor     ecx, ecx; Thread
0x1800b5804  call    cs:__imp_SetThreadToken
0x1800b580a  test    eax, eax
0x1800b580c  jnz     short loc_1800B5814
0x1800b580e  call    cs:__imp_GetLastError
0x1800b5814  mov     rcx, [rsp+270h+Token]; hObject
0x1800b5819  call    cs:__imp_CloseHandle
0x1800b581f  mov     [rsp+270h+var_238], rsi
0x1800b5824  mov     rax, [rsp+270h+var_200]
0x1800b5829  mov     [rsp+270h+var_210], rax
0x1800b582e  lea     rdx, [rsp+270h+var_210]
0x1800b5833  lea     rcx, [rsp+270h+var_238]
0x1800b5838  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800b583d  mov     edi, eax
0x1800b583f  test    eax, eax
0x1800b5841  jns     short loc_1800B58AC
0x1800b5843  mov     rcx, [rbp+178h]; this
0x1800b584a  mov     r9d, eax; char *
0x1800b584d  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b5854  mov     edx, 105h; void *
0x1800b5859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b585e  nop
0x1800b585f  lea     rcx, [rsp+270h+var_238]; this
0x1800b5864  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b5869  nop
0x1800b586a  lea     rcx, [rsp+270h+var_200]
0x1800b586f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b5874  nop
0x1800b5875  cmp     [rsp+270h+var_240], sil
0x1800b587a  jz      short loc_1800B58A7
0x1800b587c  mov     rcx, [rsp+270h+var_228]
0x1800b5881  mov     rax, [rcx]
0x1800b5884  mov     r8, [rsp+270h+var_208]
0x1800b5889  mov     edx, ebx
0x1800b588b  mov     rax, [rax+18h]
0x1800b588f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5894  mov     dword ptr [rsp+270h+var_238], eax
0x1800b5898  test    eax, eax
0x1800b589a  jns     short loc_1800B58A7
0x1800b589c  lea     rcx, [rsp+270h+var_238]
0x1800b58a1  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b58a6  nop
0x1800b58a7  jmp     loc_1800B5CF3
0x1800b58ac  mov     rbx, rsi
0x1800b58af  mov     [rsp+270h+Token], rbx
0x1800b58b4  cmp     dword ptr [r14], 2
0x1800b58b8  jnz     short loc_1800B58CE
0x1800b58ba  lea     r8, [rsp+270h+Token]; HSTRING *
0x1800b58bf  mov     rdx, [rsp+270h+var_238]; HSTRING
0x1800b58c4  mov     rcx, r13; this
0x1800b58c7  call    ?GetAADUserTicketForAccountId@CUserIdentityProvider@@AEAAJPEAUHSTRING__@@PEAPEAU2@@Z; CUserIdentityProvider::GetAADUserTicketForAccountId(HSTRING__ *,HSTRING__ * *)
0x1800b58cc  jmp     short loc_1800B5913
0x1800b58ce  cmp     dword ptr [r14], 1
  ... truncated ...
```
