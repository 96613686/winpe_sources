# FlightSettingsReader::GetFlightingAccountIdForCurrentUser(ushort * *)

- ea: `0x180090a00`
- end: `0x180091081`
- name: `?GetFlightingAccountIdForCurrentUser@FlightSettingsReader@@UEAAJPEAPEAG@Z`
- size: `1665`
- prototype: `__int64 __fastcall(FlightSettingsReader *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x18001146c`
- `0x180013da0`
- `0x1800177bc`
- `0x18001c6f4`
- `0x1800754c4`
- `0x1800859a4`
- `0x180085a24`
- `0x18008a2fc`
- `0x18008aaf0`
- `0x18008f5a4`
- `0x18008f63c`
- `0x18008f6b4`
- `0x18008f9a0`
- `0x18008fbd8`
- `0x18008fe9c`
- `0x180090a00`
- `0x180091088`
- `0x180091210`
- `0x1800928cc`
- `0x180095c88`
- `0x180095f90`
- `0x1800960cc`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090f63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090f63`

## string_xrefs

- `0x180090d62`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180090a80`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090b8c`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090c1e`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090c5e`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090c9c`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090ce6`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090d31`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090d91`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090df9`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090e2e`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090ef3`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180090f3e`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x180091016`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall FlightSettingsReader::GetFlightingAccountIdForCurrentUser(
        FlightSettingsReader *this,
        unsigned __int16 **a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdi
  __int64 v5; // rcx
  FlightSettingsReader *v6; // rcx
  int IsCallingProcessAppContainer; // ebx
  __int64 v8; // rdx
  unsigned __int16 **v9; // rdx
  int CallingProcessPackageFamilyName; // eax
  int active; // eax
  FlightSettingsReader *v12; // rcx
  int MsaProvider; // eax
  char v14; // r8
  int v15; // eax
  char v16; // r8
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  unsigned __int64 v21; // rdx
  unsigned __int8 v22; // cl
  __int64 v23; // rcx
  FlightSettingsAPITelemetryClass *v24; // rax
  int v26; // eax
  int v27; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int16 *v31; // rax
  unsigned __int64 v32; // rdx
  unsigned __int8 v33; // cl
  __int64 v34; // rcx
  FlightSettingsAPITelemetryClass *v35; // rax
  int v36; // [rsp+20h] [rbp-E0h]
  char v37; // [rsp+30h] [rbp-D0h] BYREF
  bool v38[3]; // [rsp+31h] [rbp-CFh] BYREF
  int FlightingRegDWORD; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v40; // [rsp+38h] [rbp-C8h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v41; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v42; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  int v44[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h]
  __int64 v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  unsigned int v53; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v55[3]; // [rsp+B0h] [rbp-50h] BYREF
  char v56; // [rsp+C8h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+E8h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  *a2 = 0;
  v40 = 0;
  FlightingRegDWORD = 0;
  v55[1] = (__int64)&v40;
  v55[2] = (__int64)&FlightingRegDWORD;
  v56 = 1;
  v38[0] = 0;
  FlightSettingsAPICommon::IsLocalSystem(v38);
  v37 = 0;
  if ( v38[0] && (int)ImpersonationHelper::ImpersonateActiveUser((struct UstCommon::CImpersonator *)&v37) < 0 )
  {
    v3 = 329;
LABEL_4:
    FlightingRegDWORD = -2147023579;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
      (const char *)0x80070525LL,
      v36);
LABEL_43:
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v37);
    if ( FlightSettingsAPITelemetryClass::IsEnabled(v22, v21) )
    {
      v24 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v23,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::GetFlightingAccountId_(v24, v40, FlightingRegDWORD);
    }
    return 2147943717LL;
  }
  v38[0] = 0;
  if ( !CFlightingAdmin::IsFlightingOwner(v38) )
  {
    v3 = 334;
    goto LABEL_4;
  }
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v37);
  string = (HSTRING)-2147483646LL;
  FlightingRegDWORD = FSRegUtils::GetFlightingRegDWORD((HKEY *)&string, 4u, L"Status", &v40);
  if ( FlightingRegDWORD < 0 )
  {
    v3 = 341;
    goto LABEL_4;
  }
  if ( (v40 & 1) == 0 )
  {
    v3 = 345;
    goto LABEL_4;
  }
  v53 = 0;
  string = (HSTRING)-2147483646LL;
  FSRegUtils::GetFlightingRegDWORD((HKEY *)&string, 4u, L"Type", &v53);
  if ( v53 == 2 )
    goto LABEL_43;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
  v4 = -1;
  v48 = -1;
  v49 = -1;
  string = (HSTRING)-2147483646LL;
  FlightingRegDWORD = FSRegUtils::GetFlightingRegString((HKEY *)&string, 4u, L"Id", &v47);
  if ( FlightingRegDWORD < 0 )
  {
    FlightingRegDWORD = -2147023579;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
      (const char *)0x80070525LL,
      v36);
LABEL_42:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
    goto LABEL_43;
  }
  v38[0] = 1;
  IsCallingProcessAppContainer = CallerIdentity::IsCallingProcessAppContainer(v5, v38);
  FlightingRegDWORD = IsCallingProcessAppContainer;
  if ( IsCallingProcessAppContainer == -2147024891 )
  {
    IsCallingProcessAppContainer = FlightSettingsReader::CheckCallerIsAppContainer(v6, v38);
    FlightingRegDWORD = IsCallingProcessAppContainer;
  }
  if ( IsCallingProcessAppContainer < 0 )
  {
    v8 = 368;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
      (const char *)(unsigned int)IsCallingProcessAppContainer,
      v36);
    goto LABEL_58;
  }
  if ( v38[0] )
  {
    v50 = 0;
    v51 = 0;
    v52 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
    v51 = -1;
    v52 = -1;
    CallingProcessPackageFamilyName = CallerIdentity::GetCallingProcessPackageFamilyName((CallerIdentity *)&v50, v9);
    IsCallingProcessAppContainer = CallingProcessPackageFamilyName;
    FlightingRegDWORD = CallingProcessPackageFamilyName;
    if ( CallingProcessPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x176,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)CallingProcessPackageFamilyName,
        v36);
LABEL_21:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
      goto LABEL_58;
    }
    v38[0] = 0;
    active = ImpersonationHelper::ImpersonateActiveUser((struct UstCommon::CImpersonator *)v38);
    IsCallingProcessAppContainer = active;
    FlightingRegDWORD = active;
    if ( active < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)active,
        v36);
LABEL_24:
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v38);
      goto LABEL_21;
    }
    v41 = 0;
    MsaProvider = FlightSettingsReader::GetMsaProvider(v12, &v41);
    IsCallingProcessAppContainer = MsaProvider;
    FlightingRegDWORD = MsaProvider;
    if ( MsaProvider < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)MsaProvider,
        v36);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      goto LABEL_24;
    }
    v42 = 0;
    v55[0] = v50;
    v15 = Windows::Internal::String::Initialize<unsigned short const *>(&v42, v55, v14);
    IsCallingProcessAppContainer = v15;
    FlightingRegDWORD = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v15,
        v36);
LABEL_30:
      Windows::Internal::String::~String((Windows::Internal::String *)&v42);
      goto LABEL_27;
    }
    *(_QWORD *)v44 = 0;
    v55[0] = (__int64)v47;
    v17 = Windows::Internal::String::Initialize<unsigned short const *>((HSTRING *)v44, v55, v16);
    IsCallingProcessAppContainer = v17;
    FlightingRegDWORD = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v17,
        v36);
LABEL_33:
      Windows::Internal::String::~String((Windows::Internal::String *)v44);
      goto LABEL_30;
    }
    v46 = 0;
    v58 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
      0x41u,
      0x40u);
    v18 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
            v58,
            (__int64)&v46);
    IsCallingProcessAppContainer = v18;
    FlightingRegDWORD = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v18,
        v36);
LABEL_36:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      goto LABEL_33;
    }
    v45 = 0;
    v19 = _lambda_577cf68a17f7c9a179dfc656e6a23bcf_::_lambda_577cf68a17f7c9a179dfc656e6a23bcf_(
            (unsigned int)&hstringHeader,
            (unsigned int)&v46,
            (unsigned int)&v41,
            (unsigned int)&v42,
            (__int64)v44,
            (__int64)&v45);
    v20 = FlightSettingsAPICommon::SwitchToBrokerCallingContext__lambda_81b7ac996c6c6b393ccd031617c0776e___(v19);
    IsCallingProcessAppContainer = v20;
    FlightingRegDWORD = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v20,
        v36);
LABEL_39:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
      goto LABEL_36;
    }
    if ( !v45 )
    {
      FlightingRegDWORD = -2147023579;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x196,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)0x80070525LL,
        v36);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      Windows::Internal::String::~String((Windows::Internal::String *)v44);
      Windows::Internal::String::~String((Windows::Internal::String *)&v42);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v38);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
      goto LABEL_42;
    }
    v54 = 0;
    v26 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
            &v45,
            (__int64)&v54);
    IsCallingProcessAppContainer = v26;
    FlightingRegDWORD = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v26,
        v36);
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
      goto LABEL_39;
    }
    string = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 48LL))(v54, &string);
    IsCallingProcessAppContainer = v27;
    FlightingRegDWORD = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)v27,
        v36);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      goto LABEL_48;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    do
      ++v4;
    while ( StringRawBuffer[v4] );
    FlightingRegDWORD = _AllocStringWorker<CTCoAllocPolicy>(v30, v29, StringRawBuffer);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    Windows::Internal::String::~String((Windows::Internal::String *)v44);
    Windows::Internal::String::~String((Windows::Internal::String *)&v42);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)v38);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v50);
    IsCallingProcessAppContainer = FlightingRegDWORD;
  }
  else
  {
    IsCallingProcessAppContainer = 0;
    FlightingRegDWORD = 0;
    v31 = v47;
    v47 = 0;
    v49 = 0;
    v48 = 0;
    *a2 = v31;
  }
  if ( IsCallingProcessAppContainer < 0 )
  {
    v8 = 426;
    goto LABEL_57;
  }
LABEL_58:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v47);
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v37);
  if ( FlightSettingsAPITelemetryClass::IsEnabled(v33, v32) )
  {
    v35 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v34,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::GetFlightingAccountId_(v35, v40, FlightingRegDWORD);
  }
  return (unsigned int)IsCallingProcessAppContainer;
}

```

## disassembly

```asm
0x180090a00  push    rbp
0x180090a02  push    rbx
0x180090a03  push    rsi
0x180090a04  push    rdi
0x180090a05  push    r14
0x180090a07  push    r15
0x180090a09  lea     rbp, [rsp-8]
0x180090a0e  sub     rsp, 108h
0x180090a15  mov     rax, cs:__security_cookie
0x180090a1c  xor     rax, rsp
0x180090a1f  mov     [rbp+30h+var_38], rax
0x180090a23  mov     rsi, rdx
0x180090a26  xor     r14d, r14d
0x180090a29  mov     [rdx], r14
0x180090a2c  mov     [rsp+130h+var_F8], r14d
0x180090a31  mov     [rsp+130h+var_FC], r14d
0x180090a36  lea     rax, [rsp+130h+var_F8]
0x180090a3b  mov     [rbp+30h+var_78], rax
0x180090a3f  lea     rax, [rsp+130h+var_FC]
0x180090a44  mov     [rbp+30h+var_70], rax
0x180090a48  mov     [rbp+30h+var_68], 1
0x180090a4c  mov     [rsp+130h+var_FF], r14b
0x180090a51  lea     rcx, [rsp+130h+var_FF]; bool *
0x180090a56  call    ?IsLocalSystem@FlightSettingsAPICommon@@SAJPEA_N@Z; FlightSettingsAPICommon::IsLocalSystem(bool *)
0x180090a5b  mov     [rsp+130h+var_100], r14b
0x180090a60  mov     r15d, 80070525h
0x180090a66  cmp     [rsp+130h+var_FF], r14b
0x180090a6b  jz      short loc_180090A9D
0x180090a6d  lea     rcx, [rsp+130h+var_100]; this
0x180090a72  call    ?ImpersonateActiveUser@ImpersonationHelper@@SAJPEAVCImpersonator@UstCommon@@@Z; ImpersonationHelper::ImpersonateActiveUser(UstCommon::CImpersonator *)
0x180090a77  test    eax, eax
0x180090a79  jns     short loc_180090A9D
0x180090a7b  mov     edx, 149h; void *
0x180090a80  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090a87  mov     r9d, r15d; char *
0x180090a8a  mov     rcx, [rbp+38h]; this
0x180090a8e  mov     [rsp+130h+var_FC], r15d
0x180090a93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090a98  jmp     loc_180090E97
0x180090a9d  mov     [rsp+130h+var_FF], r14b
0x180090aa2  lea     rcx, [rsp+130h+var_FF]; bool *
0x180090aa7  call    ?IsFlightingOwner@CFlightingAdmin@@SA_NPEA_N@Z; CFlightingAdmin::IsFlightingOwner(bool *)
0x180090aac  test    al, al
0x180090aae  jnz     short loc_180090AB7
0x180090ab0  mov     edx, 14Eh
0x180090ab5  jmp     short loc_180090A80
0x180090ab7  lea     rcx, [rsp+130h+var_100]; this
0x180090abc  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180090ac1  mov     rbx, 0FFFFFFFF80000002h
0x180090ac8  mov     [rsp+130h+string], rbx
0x180090acd  lea     r9, [rsp+130h+var_F8]
0x180090ad2  lea     r8, aStatus; "Status"
0x180090ad9  mov     edx, 4
0x180090ade  lea     rcx, [rsp+130h+string]
0x180090ae3  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x180090ae8  mov     [rsp+130h+var_FC], eax
0x180090aec  test    eax, eax
0x180090aee  jns     short loc_180090AF7
0x180090af0  mov     edx, 155h
0x180090af5  jmp     short loc_180090A80
0x180090af7  test    byte ptr [rsp+130h+var_F8], 1
0x180090afc  jnz     short loc_180090B08
0x180090afe  mov     edx, 159h
0x180090b03  jmp     loc_180090A80
0x180090b08  mov     [rbp+30h+var_90], r14d
0x180090b0c  mov     [rsp+130h+string], rbx
0x180090b11  lea     r9, [rbp+30h+var_90]
0x180090b15  lea     r8, aType; "Type"
0x180090b1c  mov     edx, 4
0x180090b21  lea     rcx, [rsp+130h+string]
0x180090b26  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x180090b2b  cmp     [rbp+30h+var_90], 2
0x180090b2f  jz      loc_180090E97
0x180090b35  mov     [rsp+130h+var_C0], r14
0x180090b3a  mov     [rsp+130h+var_B8], r14
0x180090b3f  mov     [rbp+30h+var_B0], r14
0x180090b43  lea     rcx, [rsp+130h+var_C0]
0x180090b48  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180090b4d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180090b51  mov     [rsp+130h+var_B8], rdi
0x180090b56  mov     [rbp+30h+var_B0], rdi
0x180090b5a  mov     [rsp+130h+string], rbx
0x180090b5f  lea     r9, [rsp+130h+var_C0]
0x180090b64  lea     r8, aId; "Id"
0x180090b6b  lea     edx, [rdi+5]
0x180090b6e  lea     rcx, [rsp+130h+string]
0x180090b73  call    ?GetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAPEAG@Z; FSRegUtils::GetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort * *)
0x180090b78  mov     [rsp+130h+var_FC], eax
0x180090b7c  test    eax, eax
0x180090b7e  jns     short loc_180090BA2
0x180090b80  mov     [rsp+130h+var_FC], r15d
0x180090b85  mov     rcx, [rbp+38h]; this
0x180090b89  mov     r9d, r15d; char *
0x180090b8c  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090b93  mov     edx, 163h; void *
0x180090b98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090b9d  jmp     loc_180090E8C
0x180090ba2  mov     [rsp+130h+var_FF], 1
0x180090ba7  lea     rdx, [rsp+130h+var_FF]
0x180090bac  call    ?IsCallingProcessAppContainer@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEA_N@Z; CallerIdentity::IsCallingProcessAppContainer(RUNTIMEBROKER_CALLERIDENTITY_CHECK,bool *)
0x180090bb1  mov     ebx, eax
0x180090bb3  mov     [rsp+130h+var_FC], eax
0x180090bb7  cmp     eax, 80070005h
0x180090bbc  jnz     short loc_180090BCE
0x180090bbe  lea     rdx, [rsp+130h+var_FF]; bool *
0x180090bc3  call    ?CheckCallerIsAppContainer@FlightSettingsReader@@AEAAJPEA_N@Z; FlightSettingsReader::CheckCallerIsAppContainer(bool *)
0x180090bc8  mov     ebx, eax
0x180090bca  mov     [rsp+130h+var_FC], eax
0x180090bce  test    ebx, ebx
0x180090bd0  jns     short loc_180090BDC
0x180090bd2  mov     edx, 170h
0x180090bd7  jmp     loc_180091013
0x180090bdc  cmp     [rsp+130h+var_FF], r14b
0x180090be1  jz      loc_180090FED
0x180090be7  mov     [rbp+30h+var_A8], r14
0x180090beb  mov     [rbp+30h+var_A0], r14
0x180090bef  mov     [rbp+30h+var_98], r14
0x180090bf3  lea     rcx, [rbp+30h+var_A8]
0x180090bf7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180090bfc  mov     [rbp+30h+var_A0], rdi
0x180090c00  mov     [rbp+30h+var_98], rdi
0x180090c04  lea     rcx, [rbp+30h+var_A8]; this
0x180090c08  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x180090c0d  mov     ebx, eax
0x180090c0f  mov     [rsp+130h+var_FC], eax
0x180090c13  test    eax, eax
0x180090c15  jns     short loc_180090C3E
0x180090c17  mov     rcx, [rbp+38h]; this
0x180090c1b  mov     r9d, eax; char *
0x180090c1e  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090c25  mov     edx, 176h; void *
0x180090c2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090c2f  nop
0x180090c30  lea     rcx, [rbp+30h+var_A8]
0x180090c34  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180090c39  jmp     loc_180091027
0x180090c3e  mov     [rsp+130h+var_FF], r14b
0x180090c43  lea     rcx, [rsp+130h+var_FF]; this
0x180090c48  call    ?ImpersonateActiveUser@ImpersonationHelper@@SAJPEAVCImpersonator@UstCommon@@@Z; ImpersonationHelper::ImpersonateActiveUser(UstCommon::CImpersonator *)
0x180090c4d  mov     ebx, eax
0x180090c4f  mov     [rsp+130h+var_FC], eax
0x180090c53  test    eax, eax
0x180090c55  jns     short loc_180090C7C
0x180090c57  mov     rcx, [rbp+38h]; this
0x180090c5b  mov     r9d, eax; char *
0x180090c5e  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090c65  mov     edx, 17Bh; void *
0x180090c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090c6f  nop
0x180090c70  lea     rcx, [rsp+130h+var_FF]; this
0x180090c75  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180090c7a  jmp     short loc_180090C30
0x180090c7c  mov     [rsp+130h+var_F0], r14
0x180090c81  lea     rdx, [rsp+130h+var_F0]; struct Windows::Security::Credentials::IWebAccountProvider **
0x180090c86  call    ?GetMsaProvider@FlightSettingsReader@@AEAAJPEAPEAUIWebAccountProvider@Credentials@Security@Windows@@@Z; FlightSettingsReader::GetMsaProvider(Windows::Security::Credentials::IWebAccountProvider * *)
0x180090c8b  mov     ebx, eax
0x180090c8d  mov     [rsp+130h+var_FC], eax
0x180090c91  test    eax, eax
0x180090c93  jns     short loc_180090CBA
0x180090c95  mov     rcx, [rbp+38h]; this
0x180090c99  mov     r9d, eax; char *
0x180090c9c  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090ca3  mov     edx, 17Fh; void *
0x180090ca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090cad  nop
0x180090cae  lea     rcx, [rsp+130h+var_F0]
0x180090cb3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090cb8  jmp     short loc_180090C70
0x180090cba  mov     [rsp+130h+var_E8], r14
0x180090cbf  mov     rax, [rbp+30h+var_A8]
0x180090cc3  mov     [rbp+30h+var_80], rax
0x180090cc7  lea     rdx, [rbp+30h+var_80]
0x180090ccb  lea     rcx, [rsp+130h+var_E8]
0x180090cd0  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180090cd5  mov     ebx, eax
0x180090cd7  mov     [rsp+130h+var_FC], eax
0x180090cdb  test    eax, eax
0x180090cdd  jns     short loc_180090D04
0x180090cdf  mov     rcx, [rbp+38h]; this
0x180090ce3  mov     r9d, eax; char *
0x180090ce6  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090ced  mov     edx, 183h; void *
0x180090cf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090cf7  nop
0x180090cf8  lea     rcx, [rsp+130h+var_E8]; this
0x180090cfd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180090d02  jmp     short loc_180090CAE
0x180090d04  mov     qword ptr [rsp+130h+var_D8], r14
0x180090d09  mov     rax, [rsp+130h+var_C0]
0x180090d0e  mov     [rbp+30h+var_80], rax
0x180090d12  lea     rdx, [rbp+30h+var_80]
0x180090d16  lea     rcx, [rsp+130h+var_D8]
0x180090d1b  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180090d20  mov     ebx, eax
0x180090d22  mov     [rsp+130h+var_FC], eax
0x180090d26  test    eax, eax
0x180090d28  jns     short loc_180090D4F
0x180090d2a  mov     rcx, [rbp+38h]; this
0x180090d2e  mov     r9d, eax; char *
0x180090d31  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090d38  mov     edx, 187h; void *
0x180090d3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090d42  nop
0x180090d43  lea     rcx, [rsp+130h+var_D8]; this
0x180090d48  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180090d4d  jmp     short loc_180090CF8
0x180090d4f  mov     [rsp+130h+var_C8], r14
0x180090d54  mov     [rbp+30h+var_48], r14
0x180090d58  mov     r9d, 40h ; '@'; unsigned int
0x180090d5e  lea     r8d, [r9+1]; unsigned int
0x180090d62  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180090d69  lea     rcx, [rbp+30h+hstringHeader]; hstringHeader
0x180090d6d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090d72  lea     rdx, [rsp+130h+var_C8]
0x180090d77  mov     rcx, [rbp+30h+var_48]
0x180090d7b  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x180090d80  mov     ebx, eax
0x180090d82  mov     [rsp+130h+var_FC], eax
0x180090d86  test    eax, eax
0x180090d88  jns     short loc_180090DAF
0x180090d8a  mov     rcx, [rbp+38h]; this
0x180090d8e  mov     r9d, eax; char *
0x180090d91  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090d98  mov     edx, 18Ch; void *
0x180090d9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090da2  nop
0x180090da3  lea     rcx, [rsp+130h+var_C8]
0x180090da8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090dad  jmp     short loc_180090D43
0x180090daf  mov     [rsp+130h+var_D0], r14
0x180090db4  lea     rax, [rsp+130h+var_D0]
0x180090db9  mov     [rsp+130h+var_108], rax
0x180090dbe  lea     rax, [rsp+130h+var_D8]
0x180090dc3  mov     qword ptr [rsp+130h+var_110], rax; int
0x180090dc8  lea     r9, [rsp+130h+var_E8]
0x180090dcd  lea     r8, [rsp+130h+var_F0]
0x180090dd2  lea     rdx, [rsp+130h+var_C8]
0x180090dd7  lea     rcx, [rbp+30h+hstringHeader]
0x180090ddb  call    ??0_lambda_577cf68a17f7c9a179dfc656e6a23bcf_@@QEAA@PEAV?$SimpleVectorIterator@UVariantConfiguration@FeatureConfiguration@Flighting@Internal@Windows@@V?$Vector@UVariantConfiguration@FeatureConfiguration@Flighting@Internal@Windows@@UVariantEquality@@UPodLifetimeTraits@XWinRT@@U?$DefaultVectorOptions@UVariantConfiguration@FeatureConfiguration@Flighting@Internal@Windows@@@4Collections@Foundation@5@@4Collections@Foundation@5@UPodLifetimeTraits@XWinRT@@UIntVersionTag@XWinRT@@$0A@@Internal@Collections@Foundation@Windows@@AEAIAEAPEAUVariantConfiguration@FeatureConfiguration@Flighting@25@AEAPEAIAEAV_lambda_b3713df90f78350991b55584c0512741_@@@Z; _lambda_577cf68a17f7c9a179dfc656e6a23bcf_::_lambda_577cf68a17f7c9a179dfc656e6a23bcf_(Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration,VariantEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration>>,XWinRT::PodLifetimeTraits,XWinRT::IntVersionTag,0> *,uint &,Windows::Internal::Flighting::FeatureConfiguration::VariantConfiguration * &,uint * &,_lambda_b3713df90f78350991b55584c0512741_ &)
0x180090de0  mov     rcx, rax
0x180090de3  call    FlightSettingsAPICommon__SwitchToBrokerCallingContext__lambda_81b7ac996c6c6b393ccd031617c0776e___
0x180090de8  mov     ebx, eax
0x180090dea  mov     [rsp+130h+var_FC], eax
0x180090dee  test    eax, eax
0x180090df0  jns     short loc_180090E17
0x180090df2  mov     rcx, [rbp+38h]; this
0x180090df6  mov     r9d, eax; char *
0x180090df9  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090e00  mov     edx, 195h; void *
0x180090e05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090e0a  nop
0x180090e0b  lea     rcx, [rsp+130h+var_D0]
0x180090e10  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090e15  jmp     short loc_180090DA3
0x180090e17  cmp     [rsp+130h+var_D0], r14
0x180090e1c  jnz     loc_180090ED0
0x180090e22  mov     [rsp+130h+var_FC], r15d
0x180090e27  mov     rcx, [rbp+38h]; this
0x180090e2b  mov     r9d, r15d; char *
0x180090e2e  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x180090e35  mov     edx, 196h; void *
0x180090e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090e3f  nop
0x180090e40  lea     rcx, [rsp+130h+var_D0]
0x180090e45  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090e4a  nop
0x180090e4b  lea     rcx, [rsp+130h+var_C8]
0x180090e50  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090e55  nop
0x180090e56  lea     rcx, [rsp+130h+var_D8]; this
0x180090e5b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180090e60  nop
0x180090e61  lea     rcx, [rsp+130h+var_E8]; this
0x180090e66  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180090e6b  nop
0x180090e6c  lea     rcx, [rsp+130h+var_F0]
0x180090e71  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090e76  nop
0x180090e77  lea     rcx, [rsp+130h+var_FF]; this
0x180090e7c  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180090e81  nop
0x180090e82  lea     rcx, [rbp+30h+var_A8]
0x180090e86  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180090e8b  nop
0x180090e8c  lea     rcx, [rsp+130h+var_C0]
0x180090e91  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180090e96  nop
0x180090e97  lea     rcx, [rsp+130h+var_100]; this
0x180090e9c  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x180090ea1  nop
0x180090ea2  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x180090ea7  test    al, al
0x180090ea9  jz      short loc_180090EC8
0x180090eab  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180090eb2  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x180090eb7  mov     r8d, [rsp+130h+var_FC]; int
0x180090ebc  mov     edx, [rsp+130h+var_F8]; unsigned int
0x180090ec0  mov     rcx, rax; this
0x180090ec3  call    ?GetFlightingAccountId_@FlightSettingsAPITelemetryClass@@QEAAXKJ@Z; FlightSettingsAPITelemetryClass::GetFlightingAccountId_(ulong,long)
0x180090ec8  mov     eax, r15d
  ... truncated ...
```
