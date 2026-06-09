# CUserIdentityProvider::GetMSADeviceTicket(ushort const *,ushort * *)

- ea: `0x1800b2e58`
- end: `0x1800b35f9`
- name: `?GetMSADeviceTicket@CUserIdentityProvider@@QEAAJPEBGPEAPEAG@Z`
- size: `1953`
- prototype: `int(CUserIdentityProvider *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009c980`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180019214`
- `0x18001c6f4`
- `0x18008a2fc`
- `0x18008aaf0`
- `0x18008fbd8`
- `0x1800960cc`
- `0x1800afb88`
- `0x1800b0650`
- `0x1800b12ac`
- `0x1800b2e58`
- `0x1800b6cd4`
- `0x1800b6ea4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2f39`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2fd6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b3024`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b30b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2f39`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2fd6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b3024`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b30b1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b3163`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b3163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b3039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b3098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b3039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b3098`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b33f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b351c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b33f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b351c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3447`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2f5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b30d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2f5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b30d4`

## string_xrefs

- `0x1800b2f19`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x1800b3091`: `Windows.Security.Authentication.OnlineId.OnlineIdSystemAuthenticator`
- `0x1800b2f70`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b3069`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b30ea`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b3140`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b321f`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b328a`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b32f1`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b3397`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b3479`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b35bc`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CUserIdentityProvider::GetMSADeviceTicket(
        CUserIdentityProvider *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 *v4; // r14
  __int64 v5; // rsi
  unsigned int v6; // edx
  unsigned __int64 v7; // rdx
  PVOID Reserved1; // rbx
  int ActivationFactory; // eax
  int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, PVOID, __int64 *); // r12
  unsigned __int64 v13; // rcx
  const ULONG_PTR *v14; // r9
  PVOID v15; // rbx
  unsigned __int64 v16; // rcx
  const ULONG_PTR *v17; // r9
  int v18; // eax
  HSTRING v19; // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  HRESULT v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 v29; // rdx
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, __int64 *); // rdi
  int v32; // eax
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, __int64 *); // rdi
  int v35; // eax
  __int64 v36; // rdx
  unsigned __int64 v37; // r9
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, HSTRING *); // rbx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r9
  PCWSTR StringRawBuffer; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r9
  unsigned int v47; // edx
  __int64 v48; // r8
  int v49; // eax
  int v51; // [rsp+20h] [rbp-E0h]
  char v52; // [rsp+30h] [rbp-D0h] BYREF
  bool v53; // [rsp+31h] [rbp-CFh] BYREF
  __int64 v54; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v55; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 length; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v60; // [rsp+68h] [rbp-98h] BYREF
  __int64 v61; // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h] BYREF
  int v63; // [rsp+80h] [rbp-80h] BYREF
  __int64 v64; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  GUID pclsid; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER v68; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v69[42]; // [rsp+E0h] [rbp-20h] BYREF
  char v70; // [rsp+230h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  v4 = (__int64 *)((char *)this + 112);
  v5 = -1;
  if ( !*((_QWORD *)this + 14) )
  {
    wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v69);
    v69[0] = &FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest::`vftable';
    v70 = 0;
    FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest::StartActivity(
      (FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest *)v69,
      v6);
    v52 = 0;
    v53 = 0;
    FlightSettingsAPICommon::IsLocalSystem(&v53);
    if ( v53 )
    {
      length = ImpersonationHelper::ImpersonateActiveUser((struct UstCommon::CImpersonator *)&v52);
      if ( (length & 0x80000000) != 0 )
        FlightSettingsAPITelemetryClass::ImpersonationFailed<long &>((int *)&length, v7);
    }
    v64 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
           0x45u,
           (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
           (HSTRING *)&hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    Reserved1 = hstringHeader.Reserved.Reserved1;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
    ActivationFactory = RoGetActivationFactory(Reserved1, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v64);
    v10 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v51);
LABEL_72:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
      UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v52);
      FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest::~FlightingDeviceTicketRequest((FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest *)v69);
      return (unsigned int)v10;
    }
    v54 = 0;
    v11 = v64;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING, PVOID, __int64 *))(*(_QWORD *)v64 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
    length = 0;
    v13 = -1;
    do
      ++v13;
    while ( CUserIdentityProvider::c_AuthPolicy[v13] );
    if ( (int)ULongLongToUInt(v13, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v14);
    WindowsCreateStringReference(
      CUserIdentityProvider::c_AuthPolicy,
      length,
      (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
      (HSTRING *)&hstringHeader);
    v15 = hstringHeader.Reserved.Reserved1;
    length = 0;
    v16 = -1;
    do
      ++v16;
    while ( a2[v16] );
    if ( (int)ULongLongToUInt(v16, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v17);
    WindowsCreateStringReference(a2, length, &v68, &string);
    v18 = v12(v11, string, v15, &v54);
    v10 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v18,
        v51);
LABEL_71:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
      goto LABEL_72;
    }
    v56 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Security.Authentication.OnlineId.OnlineIdSystemAuthenticator",
           0x44u,
           &v68,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v19 = string;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
    v20 = RoGetActivationFactory(v19, &GUID_85047792_f634_41e3_96a4_5164e902c740, &v56);
    v10 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v20,
        v51);
LABEL_70:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      goto LABEL_71;
    }
    v55 = 0;
    v21 = v56;
    v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    v23 = v22(v21, &v55);
    v10 = v23;
    if ( v23 < 0 )
    {
      v24 = 115;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v23,
        v51);
LABEL_69:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      goto LABEL_70;
    }
    pclsid = 0;
    v23 = CLSIDFromString(L"{0CB4A94A-6E8C-477B-88C8-A3799FC97414}", &pclsid);
    v10 = v23;
    if ( v23 < 0 )
    {
      v24 = 119;
      goto LABEL_25;
    }
    *(GUID *)&hstringHeader.Reserved.Reserved1 = pclsid;
    v23 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v55 + 56LL))(v55, &hstringHeader);
    v10 = v23;
    if ( v23 < 0 )
    {
      v24 = 120;
      goto LABEL_25;
    }
    v57 = 0;
    v25 = v55;
    v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    v27 = v26(v25, v54, &v57);
    v10 = v27;
    if ( v27 == -2147023665 )
    {
LABEL_31:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
      v10 = -2147023665;
      goto LABEL_72;
    }
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v27,
        v51);
LABEL_68:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
      goto LABEL_69;
    }
    v59 = 0;
    v28 = v57;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
    v10 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::OnlineId::OnlineIdSystemTicketResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::OnlineId::OnlineIdSystemTicketResult *>>(v28);
    if ( v10 >= 0 )
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 64LL))(v28, &v59);
    if ( v10 == -2147023665 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      goto LABEL_31;
    }
    if ( v10 < 0 )
    {
      v29 = 138;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v10,
        v51);
LABEL_67:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      goto LABEL_68;
    }
    v30 = v59;
    if ( !v59 )
    {
      v10 = -2147023728;
      v29 = 139;
      goto LABEL_40;
    }
    v61 = 0;
    v31 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    v32 = v31(v30, &v61);
    v10 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v32,
        v51);
LABEL_66:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
      goto LABEL_67;
    }
    v33 = v61;
    if ( !v61 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
      v10 = -2146698736;
      goto LABEL_72;
    }
    v62 = 0;
    v34 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
    v35 = v34(v33, &v62);
    v10 = v35;
    if ( v35 < 0 )
    {
      v36 = 148;
LABEL_49:
      v37 = (unsigned int)v35;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)v37,
        v51);
LABEL_65:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
      goto LABEL_66;
    }
    v63 = 0;
    v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v62 + 64LL))(v62, &v63);
    v10 = v35;
    if ( v35 < 0 )
    {
      v36 = 152;
      goto LABEL_49;
    }
    v10 = v63;
    if ( v63 < 0 )
    {
      v37 = (unsigned int)v63;
      v36 = 153;
      goto LABEL_50;
    }
    v60 = 0;
    v38 = v62;
    v39 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v62 + 48LL);
    WindowsDeleteString(0);
    v60 = 0;
    v40 = v39(v38, &v60);
    v10 = v40;
    if ( v40 < 0 )
    {
      v41 = 156;
LABEL_63:
      v42 = (unsigned int)v40;
      goto LABEL_64;
    }
    if ( !v60 )
    {
      v10 = -2146698736;
      v42 = 2148268560LL;
      v41 = 159;
LABEL_64:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)v42,
        v51);
      WindowsDeleteString(v60);
      v60 = 0;
      goto LABEL_65;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v4);
    v4[1] = -1;
    v4[2] = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(v60, 0);
    v46 = -1;
    do
      ++v46;
    while ( StringRawBuffer[v46] );
    v40 = _AllocStringWorker<CTCoAllocPolicy>(v45, v44, StringRawBuffer);
    v10 = v40;
    if ( v40 < 0 )
    {
      v41 = 161;
      goto LABEL_63;
    }
    FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest::Stop(
      (FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest *)v69,
      v47);
    WindowsDeleteString(v60);
    v60 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v52);
    FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest::~FlightingDeviceTicketRequest((FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest *)v69);
  }
  v48 = *v4;
  do
    ++v5;
  while ( *(_WORD *)(v48 + 2 * v5) );
  v49 = _AllocStringWorker<CTCoAllocPolicy>(this, a2, v48);
  v10 = v49;
  if ( v49 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v49,
      v51);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800b2e58  mov     [rsp-8+arg_18], rbx
0x1800b2e5d  push    rbp
0x1800b2e5e  push    rsi
0x1800b2e5f  push    rdi
0x1800b2e60  push    r12
0x1800b2e62  push    r13
0x1800b2e64  push    r14
0x1800b2e66  push    r15
0x1800b2e68  lea     rbp, [rsp-150h]
0x1800b2e70  sub     rsp, 250h
0x1800b2e77  mov     rax, cs:__security_cookie
0x1800b2e7e  xor     rax, rsp
0x1800b2e81  mov     [rbp+180h+var_40], rax
0x1800b2e88  mov     r13, r8
0x1800b2e8b  mov     r15, rdx
0x1800b2e8e  xor     r12d, r12d
0x1800b2e91  mov     [r8], r12
0x1800b2e94  lea     r14, [rcx+70h]
0x1800b2e98  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b2e9c  cmp     [r14], r12
0x1800b2e9f  jnz     loc_1800B3592
0x1800b2ea5  lea     rdx, aFlightingdevic; "FlightingDeviceTicketRequest"
0x1800b2eac  lea     rcx, [rbp+180h+var_1A0]; struct wil::details::IFailureCallback *
0x1800b2eb0  call    ??0?$ActivityBase@VFlightSettingsAPITelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FlightSettingsAPITelemetryProvider,1,35184372088832,5,33554432,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800b2eb5  lea     rax, ??_7FlightingDeviceTicketRequest@FlightSettingsAPITelemetryClass@@6B@; const FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest::`vftable'
0x1800b2ebc  mov     [rbp+180h+var_1A0], rax
0x1800b2ec0  mov     [rbp+180h+var_50], r12b
0x1800b2ec7  lea     rcx, [rbp+180h+var_1A0]; this
0x1800b2ecb  call    ?StartActivity@FlightingDeviceTicketRequest@FlightSettingsAPITelemetryClass@@QEAAXK@Z; FlightSettingsAPITelemetryClass::FlightingDeviceTicketRequest::StartActivity(ulong)
0x1800b2ed0  nop
0x1800b2ed1  mov     [rsp+280h+var_250], r12b
0x1800b2ed6  mov     [rsp+280h+var_24F], r12b
0x1800b2edb  lea     rcx, [rsp+280h+var_24F]; bool *
0x1800b2ee0  call    ?IsLocalSystem@FlightSettingsAPICommon@@SAJPEA_N@Z; FlightSettingsAPICommon::IsLocalSystem(bool *)
0x1800b2ee5  cmp     [rsp+280h+var_24F], r12b
0x1800b2eea  jz      short loc_1800B2F08
0x1800b2eec  lea     rcx, [rsp+280h+var_250]; this
0x1800b2ef1  call    ?ImpersonateActiveUser@ImpersonationHelper@@SAJPEAVCImpersonator@UstCommon@@@Z; ImpersonationHelper::ImpersonateActiveUser(UstCommon::CImpersonator *)
0x1800b2ef6  mov     [rsp+280h+length], eax
0x1800b2efa  test    eax, eax
0x1800b2efc  jns     short loc_1800B2F08
0x1800b2efe  lea     rcx, [rsp+280h+length]
0x1800b2f03  call    ??$ImpersonationFailed@AEAJ@FlightSettingsAPITelemetryClass@@SAXAEAJ@Z; FlightSettingsAPITelemetryClass::ImpersonationFailed<long &>(long &)
0x1800b2f08  mov     [rbp+180h+var_1F8], r12
0x1800b2f0c  lea     r9, [rbp+180h+hstringHeader]; string
0x1800b2f10  lea     r8, [rbp+180h+hstringHeader.Reserved+8]; hstringHeader
0x1800b2f14  mov     edx, 45h ; 'E'; length
0x1800b2f19  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x1800b2f20  call    cs:__imp_WindowsCreateStringReference
0x1800b2f26  test    eax, eax
0x1800b2f28  jns     short loc_1800B2F3F
0x1800b2f2a  xor     r9d, r9d; lpArguments
0x1800b2f2d  xor     r8d, r8d; nNumberOfArguments
0x1800b2f30  lea     edx, [r9+1]; dwExceptionFlags
0x1800b2f34  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b2f39  call    cs:__imp_RaiseException
0x1800b2f3f  mov     rbx, qword ptr [rbp+180h+hstringHeader.Reserved]
0x1800b2f43  lea     rcx, [rbp+180h+var_1F8]
0x1800b2f47  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b2f4c  lea     r8, [rbp+180h+var_1F8]
0x1800b2f50  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x1800b2f57  mov     rcx, rbx
0x1800b2f5a  call    cs:__imp_RoGetActivationFactory
0x1800b2f60  mov     ebx, eax
0x1800b2f62  test    eax, eax
0x1800b2f64  jns     short loc_1800B2F86
0x1800b2f66  mov     rcx, [rbp+188h]; this
0x1800b2f6d  mov     r9d, eax; char *
0x1800b2f70  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b2f77  mov     edx, 62h ; 'b'; void *
0x1800b2f7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2f81  jmp     loc_1800B34EA
0x1800b2f86  mov     [rsp+280h+var_248], r12
0x1800b2f8b  mov     rdi, [rbp+180h+var_1F8]
0x1800b2f8f  mov     rax, [rdi]
0x1800b2f92  mov     r12, [rax+30h]
0x1800b2f96  lea     rcx, [rsp+280h+var_248]
0x1800b2f9b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b2fa0  mov     rbx, cs:?c_AuthPolicy@CUserIdentityProvider@@0QEBGEB; ushort const * const CUserIdentityProvider::c_AuthPolicy
0x1800b2fa7  xor     r9d, r9d
0x1800b2faa  mov     [rsp+280h+length], r9d
0x1800b2faf  mov     rcx, rsi
0x1800b2fb2  inc     rcx; unsigned __int64
0x1800b2fb5  cmp     [rbx+rcx*2], r9w
0x1800b2fba  jnz     short loc_1800B2FB2
0x1800b2fbc  lea     rdx, [rsp+280h+length]; unsigned int *
0x1800b2fc1  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800b2fc6  test    eax, eax
0x1800b2fc8  jns     short loc_1800B2FDC
0x1800b2fca  xor     r8d, r8d; nNumberOfArguments
0x1800b2fcd  lea     edx, [r8+1]; dwExceptionFlags
0x1800b2fd1  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b2fd6  call    cs:__imp_RaiseException
0x1800b2fdc  lea     r9, [rbp+180h+hstringHeader]; string
0x1800b2fe0  lea     r8, [rbp+180h+hstringHeader.Reserved+8]; hstringHeader
0x1800b2fe4  mov     edx, [rsp+280h+length]; length
0x1800b2fe8  mov     rcx, rbx; sourceString
0x1800b2feb  call    cs:__imp_WindowsCreateStringReference
0x1800b2ff1  mov     rbx, qword ptr [rbp+180h+hstringHeader.Reserved]
0x1800b2ff5  xor     r9d, r9d
0x1800b2ff8  mov     [rsp+280h+length], r9d
0x1800b2ffd  mov     rcx, rsi
0x1800b3000  inc     rcx; unsigned __int64
0x1800b3003  cmp     [r15+rcx*2], r9w
0x1800b3008  jnz     short loc_1800B3000
0x1800b300a  lea     rdx, [rsp+280h+length]; unsigned int *
0x1800b300f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800b3014  test    eax, eax
0x1800b3016  jns     short loc_1800B302A
0x1800b3018  xor     r8d, r8d; nNumberOfArguments
0x1800b301b  lea     edx, [r8+1]; dwExceptionFlags
0x1800b301f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b3024  call    cs:__imp_RaiseException
0x1800b302a  lea     r9, [rbp+180h+string]; string
0x1800b302e  lea     r8, [rbp+180h+var_1B8]; hstringHeader
0x1800b3032  mov     edx, [rsp+280h+length]; length
0x1800b3036  mov     rcx, r15; sourceString
0x1800b3039  call    cs:__imp_WindowsCreateStringReference
0x1800b303f  lea     r9, [rsp+280h+var_248]
0x1800b3044  mov     r8, rbx
0x1800b3047  mov     rdx, [rbp+180h+string]
0x1800b304b  mov     rcx, rdi
0x1800b304e  mov     rax, r12
0x1800b3051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3056  mov     ebx, eax
0x1800b3058  xor     r12d, r12d
0x1800b305b  test    eax, eax
0x1800b305d  jns     short loc_1800B307F
0x1800b305f  mov     rcx, [rbp+188h]; this
0x1800b3066  mov     r9d, eax; char *
0x1800b3069  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b3070  lea     edx, [r12+68h]; void *
0x1800b3075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b307a  jmp     loc_1800B34DF
0x1800b307f  mov     [rsp+280h+var_238], r12
0x1800b3084  lea     r9, [rbp+180h+string]; string
0x1800b3088  lea     r8, [rbp+180h+var_1B8]; hstringHeader
0x1800b308c  mov     edx, 44h ; 'D'; length
0x1800b3091  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdSystemAuthenticator@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x1800b3098  call    cs:__imp_WindowsCreateStringReference
0x1800b309e  test    eax, eax
0x1800b30a0  jns     short loc_1800B30B7
0x1800b30a2  xor     r9d, r9d; lpArguments
0x1800b30a5  xor     r8d, r8d; nNumberOfArguments
0x1800b30a8  lea     edx, [r9+1]; dwExceptionFlags
0x1800b30ac  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b30b1  call    cs:__imp_RaiseException
0x1800b30b7  mov     rbx, [rbp+180h+string]
0x1800b30bb  lea     rcx, [rsp+280h+var_238]
0x1800b30c0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b30c5  lea     r8, [rsp+280h+var_238]
0x1800b30ca  lea     rdx, _GUID_85047792_f634_41e3_96a4_5164e902c740
0x1800b30d1  mov     rcx, rbx
0x1800b30d4  call    cs:__imp_RoGetActivationFactory
0x1800b30da  mov     ebx, eax
0x1800b30dc  test    eax, eax
0x1800b30de  jns     short loc_1800B3100
0x1800b30e0  mov     rcx, [rbp+188h]; this
0x1800b30e7  mov     r9d, eax; char *
0x1800b30ea  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b30f1  mov     edx, 6Fh ; 'o'; void *
0x1800b30f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b30fb  jmp     loc_1800B34D4
0x1800b3100  mov     [rsp+280h+var_240], r12
0x1800b3105  mov     rdi, [rsp+280h+var_238]
0x1800b310a  mov     rax, [rdi]
0x1800b310d  mov     rbx, [rax+30h]
0x1800b3111  lea     rcx, [rsp+280h+var_240]
0x1800b3116  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b311b  lea     rdx, [rsp+280h+var_240]
0x1800b3120  mov     rcx, rdi
0x1800b3123  mov     rax, rbx
0x1800b3126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b312b  mov     ebx, eax
0x1800b312d  test    eax, eax
0x1800b312f  jns     short loc_1800B3151
0x1800b3131  mov     edx, 73h ; 's'; void *
0x1800b3136  mov     rcx, [rbp+188h]; this
0x1800b313d  mov     r9d, eax; char *
0x1800b3140  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b3147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b314c  jmp     loc_1800B34C9
0x1800b3151  xorps   xmm0, xmm0
0x1800b3154  movups  xmmword ptr [rbp+180h+pclsid.Data1], xmm0
0x1800b3158  lea     rdx, [rbp+180h+pclsid]; pclsid
0x1800b315c  lea     rcx, a0cb4a94a6e8c47; "{0CB4A94A-6E8C-477B-88C8-A3799FC97414}"
0x1800b3163  call    cs:__imp_CLSIDFromString
0x1800b3169  mov     ebx, eax
0x1800b316b  test    eax, eax
0x1800b316d  jns     short loc_1800B3176
0x1800b316f  mov     edx, 77h ; 'w'
0x1800b3174  jmp     short loc_1800B3136
0x1800b3176  mov     rcx, [rsp+280h+var_240]
0x1800b317b  movaps  xmm0, xmmword ptr [rbp+180h+pclsid.Data1]
0x1800b317f  movdqa  xmmword ptr [rbp+180h+hstringHeader.Reserved], xmm0
0x1800b3184  mov     rax, [rcx]
0x1800b3187  lea     rdx, [rbp+180h+hstringHeader]
0x1800b318b  mov     rax, [rax+38h]
0x1800b318f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3194  mov     ebx, eax
0x1800b3196  test    eax, eax
0x1800b3198  jns     short loc_1800B31A1
0x1800b319a  mov     edx, 78h ; 'x'
0x1800b319f  jmp     short loc_1800B3136
0x1800b31a1  mov     [rsp+280h+var_230], r12
0x1800b31a6  mov     rdi, [rsp+280h+var_240]
0x1800b31ab  mov     rax, [rdi]
0x1800b31ae  mov     rbx, [rax+30h]
0x1800b31b2  lea     rcx, [rsp+280h+var_230]
0x1800b31b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b31bc  lea     r8, [rsp+280h+var_230]
0x1800b31c1  mov     rdx, [rsp+280h+var_248]
0x1800b31c6  mov     rcx, rdi
0x1800b31c9  mov     rax, rbx
0x1800b31cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b31d1  mov     ebx, eax
0x1800b31d3  mov     r15d, 800704CFh
0x1800b31d9  cmp     eax, r15d
0x1800b31dc  jnz     short loc_1800B3211
0x1800b31de  lea     rcx, [rsp+280h+var_230]
0x1800b31e3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b31e8  nop
0x1800b31e9  lea     rcx, [rsp+280h+var_240]
0x1800b31ee  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b31f3  nop
0x1800b31f4  lea     rcx, [rsp+280h+var_238]
0x1800b31f9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b31fe  nop
0x1800b31ff  lea     rcx, [rsp+280h+var_248]
0x1800b3204  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b3209  mov     ebx, r15d
0x1800b320c  jmp     loc_1800B34EA
0x1800b3211  test    eax, eax
0x1800b3213  jns     short loc_1800B3235
0x1800b3215  mov     rcx, [rbp+188h]; this
0x1800b321c  mov     r9d, eax; char *
0x1800b321f  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b3226  mov     edx, 82h; void *
0x1800b322b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3230  jmp     loc_1800B34BE
0x1800b3235  mov     [rsp+280h+var_220], r12
0x1800b323a  mov     rdi, [rsp+280h+var_230]
0x1800b323f  lea     rcx, [rsp+280h+var_220]
0x1800b3244  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b3249  mov     rcx, rdi
0x1800b324c  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVOnlineIdSystemTicketResult@OnlineId@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVOnlineIdSystemTicketResult@OnlineId@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVOnlineIdSystemTicketResult@OnlineId@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::OnlineId::OnlineIdSystemTicketResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::OnlineId::OnlineIdSystemTicketResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::OnlineId::OnlineIdSystemTicketResult *> *,tagCOWAIT_FLAGS,void *)
0x1800b3251  mov     ebx, eax
0x1800b3253  test    eax, eax
0x1800b3255  js      short loc_1800B326D
0x1800b3257  mov     rax, [rdi]
0x1800b325a  lea     rdx, [rsp+280h+var_220]
0x1800b325f  mov     rcx, rdi
0x1800b3262  mov     rax, [rax+40h]
0x1800b3266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b326b  mov     ebx, eax
0x1800b326d  cmp     ebx, r15d
0x1800b3270  jnz     short loc_1800B3281
0x1800b3272  lea     rcx, [rsp+280h+var_220]
0x1800b3277  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b327c  jmp     loc_1800B31DE
0x1800b3281  test    ebx, ebx
0x1800b3283  jns     short loc_1800B32A5
0x1800b3285  mov     edx, 8Ah; void *
0x1800b328a  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b3291  mov     r9d, ebx; char *
0x1800b3294  mov     rcx, [rbp+188h]; this
0x1800b329b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b32a0  jmp     loc_1800B34B3
0x1800b32a5  mov     rbx, [rsp+280h+var_220]
0x1800b32aa  test    rbx, rbx
0x1800b32ad  jnz     short loc_1800B32BB
0x1800b32af  mov     ebx, 80070490h
0x1800b32b4  mov     edx, 8Bh
0x1800b32b9  jmp     short loc_1800B328A
0x1800b32bb  mov     [rsp+280h+var_210], r12
0x1800b32c0  mov     rax, [rbx]
0x1800b32c3  mov     rdi, [rax+30h]
0x1800b32c7  lea     rcx, [rsp+280h+var_210]
0x1800b32cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b32d1  lea     rdx, [rsp+280h+var_210]
0x1800b32d6  mov     rcx, rbx
0x1800b32d9  mov     rax, rdi
0x1800b32dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b32e1  mov     ebx, eax
0x1800b32e3  test    eax, eax
0x1800b32e5  jns     short loc_1800B3307
0x1800b32e7  mov     rcx, [rbp+188h]; this
0x1800b32ee  mov     r9d, eax; char *
0x1800b32f1  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b32f8  mov     edx, 90h; void *
0x1800b32fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3302  jmp     loc_1800B34A8
0x1800b3307  mov     rbx, [rsp+280h+var_210]
0x1800b330c  test    rbx, rbx
0x1800b330f  jnz     short loc_1800B335C
0x1800b3311  lea     rcx, [rsp+280h+var_210]
0x1800b3316  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b331b  nop
0x1800b331c  lea     rcx, [rsp+280h+var_220]
0x1800b3321  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
  ... truncated ...
```
