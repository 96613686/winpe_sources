# FSPropertyBag::GetPropertyBag(ushort * *)

- ea: `0x1800be044`
- end: `0x1800be871`
- name: `?GetPropertyBag@FSPropertyBag@@QEAAJPEAPEAG@Z`
- size: `2093`
- prototype: `__int64 __fastcall(FSPropertyBag *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180098278`
- `0x1800987a4`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18001f01c`
- `0x18002035c`
- `0x1800325f4`
- `0x180032640`
- `0x1800327e4`
- `0x18003290c`
- `0x1800334f0`
- `0x1800859a4`
- `0x180085a24`
- `0x180085e88`
- `0x180086644`
- `0x18008fbd8`
- `0x18009c3ec`
- `0x1800b483c`
- `0x1800b6c94`
- `0x1800bb5ec`
- `0x1800bb934`
- `0x1800bdaf0`
- `0x1800be044`
- `0x1800bec84`
- `0x1800c0bf0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be27e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be317`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be3a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be437`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be60b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be6f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be27e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be317`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be3a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be437`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be60b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be6f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be32c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be3bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be44c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be623`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be70b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be32c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be3bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be44c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be623`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be70b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800be7b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800be7b1`

## string_xrefs

- `0x1800be1f0`: `Windows.Data.Json.JsonValue`
- `0x1800be53e`: `FlightSettingsServiceUrl`
- `0x1800be55a`: `https://insideruser.microsoft.com/api/FlightSettings`
- `0x1800be14b`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be1d5`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be21a`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be2b8`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be577`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be648`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be730`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be773`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800be7e7`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall FSPropertyBag::GetPropertyBag(FSPropertyBag *this, unsigned __int16 **a2)
{
  __int64 v3; // rdi
  int v4; // ebx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int FlightIdEntriesAsJsonValue; // r12d
  FSPropertyBag *v9; // rcx
  int ServiceDrivenActionResultsAsJsonValue; // r13d
  const unsigned __int16 (*v11)[29]; // rdx
  __int64 *v12; // rax
  int v13; // eax
  __int64 *v14; // rax
  int v15; // eax
  struct Windows::Data::Json::IJsonValueStatics *v16; // rsi
  __int64 (__fastcall *v17)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *); // r14
  const WCHAR *v18; // rbx
  unsigned __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64); // r15
  __int64 v24; // r14
  unsigned __int64 v25; // rcx
  const ULONG_PTR *v26; // r9
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64); // r15
  struct Windows::Data::Json::IJsonValue *v29; // r14
  unsigned __int64 v30; // rcx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v32)(_QWORD, GUID *, __int64); // r15
  struct Windows::Data::Json::IJsonValue *v33; // r14
  unsigned __int64 v34; // rcx
  FSPropertyBag *v35; // r15
  int v36; // eax
  CUserIdentityProvider *v37; // rbx
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64); // rbx
  __int64 (__fastcall *v39)(_QWORD, GUID *, __int64); // r14
  FSPropertyBag *v40; // rsi
  int v41; // ecx
  int v42; // eax
  FSPropertyBag *v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64); // rbx
  __int64 (__fastcall *v45)(_QWORD, GUID *, __int64); // r14
  HKEY v46; // rsi
  int v47; // ecx
  int v48; // eax
  HKEY *v49; // rcx
  int v50; // eax
  int v51; // eax
  __int64 v52; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v54; // rdx
  int v56; // [rsp+20h] [rbp-B9h]
  UINT32 length; // [rsp+30h] [rbp-A9h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-A1h] BYREF
  struct Windows::Data::Json::IJsonValue *v59; // [rsp+40h] [rbp-99h] BYREF
  struct Windows::Data::Json::IJsonValue *v60; // [rsp+48h] [rbp-91h] BYREF
  struct Windows::Data::Json::IJsonValueStatics *v61; // [rsp+50h] [rbp-89h] BYREF
  __int64 v62; // [rsp+58h] [rbp-81h] BYREF
  HKEY v63; // [rsp+60h] [rbp-79h] BYREF
  UINT32 v64; // [rsp+68h] [rbp-71h] BYREF
  CUserIdentityProvider *v65; // [rsp+70h] [rbp-69h] BYREF
  FSPropertyBag *v66; // [rsp+78h] [rbp-61h] BYREF
  __int64 v67; // [rsp+80h] [rbp-59h] BYREF
  HSTRING v68; // [rsp+88h] [rbp-51h] BYREF
  PCWSTR sourceString; // [rsp+90h] [rbp-49h] BYREF
  __int64 v70; // [rsp+98h] [rbp-41h]
  __int64 v71; // [rsp+A0h] [rbp-39h]
  unsigned __int16 **v72; // [rsp+A8h] [rbp-31h]
  HSTRING string; // [rsp+B0h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-21h] BYREF
  HSTRING v75; // [rsp+D0h] [rbp-9h] BYREF
  HSTRING_HEADER v76; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v72 = a2;
  v66 = this;
  *a2 = 0;
  sourceString = 0;
  v70 = 0;
  v71 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  v3 = -1;
  v70 = -1;
  v71 = -1;
  v4 = FSPropertyBag::ConstructPropertyBag(this, (unsigned __int16 **)&sourceString);
  if ( v4 >= 0 )
    goto LABEL_9;
  v63 = HKEY_LOCAL_MACHINE;
  FSRegUtils::SetFlightingRegDWORD(&v63, 1, L"LastHR", 2148268563LL);
  string = 0;
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         &string,
         L"%lu",
         (unsigned int)v4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                &sourceString,
                L"&%s=%s",
                L"PropertyBagHr",
                string) < 0 )
    {
      v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
             &sourceString,
             L"&%s=%s",
             L"PropertyBagHr",
             string);
      v6 = v5;
      if ( v5 < 0 )
      {
        v7 = 503;
        goto LABEL_7;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
LABEL_9:
    v60 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    FlightIdEntriesAsJsonValue = FSPropertyBag::GetFlightIdEntriesAsJsonValue(this, &v60);
    v59 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
    ServiceDrivenActionResultsAsJsonValue = FSPropertyBag::GetServiceDrivenActionResultsAsJsonValue(v9, &v59);
    v58 = 0;
    v12 = (__int64 *)Windows::Internal::StringReference::StringReference(&v75, v11);
    v13 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v12, &v58);
    v6 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v13,
        v56);
LABEL_77:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
      goto LABEL_78;
    }
    v61 = 0;
    v14 = (__int64 *)Windows::Internal::StringReference::StringReference(&v75, L"Windows.Data.Json.JsonValue");
    v15 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
            *v14,
            (__int64)&v61);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v15,
        v56);
LABEL_76:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
      goto LABEL_77;
    }
    v62 = 0;
    v16 = v61;
    v17 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *))(*(_QWORD *)v61 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
    v18 = sourceString;
    length = 0;
    v19 = -1;
    do
      ++v19;
    while ( sourceString[v19] );
    if ( (int)ULongLongToUInt(v19, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(v18, length, &hstringHeader, &string);
    v20 = v17(v16, string, &v62);
    v6 = v20;
    if ( v20 < 0 )
    {
      v21 = 521;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v20,
        v56);
LABEL_75:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v62);
      goto LABEL_76;
    }
    v22 = v58;
    v23 = (*v58)[7];
    v24 = v62;
    length = 0;
    v25 = -1;
    do
      ++v25;
    while ( FSPropertyBag::s_postPropertyBag[v25] );
    if ( (int)ULongLongToUInt(v25, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v26);
    WindowsCreateStringReference(FSPropertyBag::s_postPropertyBag, length, &hstringHeader, &string);
    v20 = v23(v22, (GUID *)string, v24);
    v6 = v20;
    if ( v20 < 0 )
    {
      v21 = 522;
      goto LABEL_19;
    }
    if ( FlightIdEntriesAsJsonValue >= 0 )
    {
      v27 = v58;
      v28 = (*v58)[7];
      v29 = v60;
      length = 0;
      v30 = -1;
      do
        ++v30;
      while ( FSPropertyBag::s_postFlightIDBlob[v30] );
      if ( (int)ULongLongToUInt(v30, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(FSPropertyBag::s_postFlightIDBlob, length, &hstringHeader, &string);
      v20 = v28(v27, (GUID *)string, (__int64)v29);
      v6 = v20;
      if ( v20 < 0 )
      {
        v21 = 527;
        goto LABEL_19;
      }
    }
    if ( ServiceDrivenActionResultsAsJsonValue >= 0 )
    {
      v31 = v58;
      v32 = (*v58)[7];
      v33 = v59;
      length = 0;
      v34 = -1;
      do
        ++v34;
      while ( FSPropertyBag::s_postServiceDrivenActionResults[v34] );
      if ( (int)ULongLongToUInt(v34, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(FSPropertyBag::s_postServiceDrivenActionResults, length, &hstringHeader, &string);
      v20 = v32(v31, (GUID *)string, (__int64)v33);
      v6 = v20;
      if ( v20 < 0 )
      {
        v21 = 533;
        goto LABEL_19;
      }
    }
    v35 = v66;
    if ( FSPropertyBag::ShouldIncludeProperty(v66, L"AccountsBlob") )
    {
      length = 0;
      v63 = HKEY_LOCAL_MACHINE;
      if ( (int)FSRegUtils::GetFlightingRegDWORD(&v63, 4u, L"SupportedTypes", &length) >= 0 )
      {
        v65 = 0;
        if ( (int)Microsoft::WRL::Details::MakeAndInitialize<CUserIdentityProvider,CUserIdentityProvider,>(&v65) >= 0
          && v65 )
        {
          string = 0;
          *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
          hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
          v63 = HKEY_LOCAL_MACHINE;
          if ( (int)FSRegUtils::GetRegString(
                      &v63,
                      L"Software\\Microsoft\\Windows\\CurrentVersion\\FlightSettings",
                      L"DomainFilter",
                      (unsigned __int16 **)&string,
                      0) < 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
            hstringHeader.Reserved.Reserved1 = (PVOID)-1LL;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
            v63 = HKEY_LOCAL_MACHINE;
            if ( FSRegUtils::GetFlightingRegString(&v63, 3u, L"FlightSettingsServiceUrl", (unsigned __int16 **)&string) < 0 )
            {
              v36 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                      &string,
                      L"https://insideruser.microsoft.com/api/FlightSettings",
                      -1);
              v6 = v36;
              if ( v36 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x228,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
                  (const char *)(unsigned int)v36,
                  v56);
LABEL_48:
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
                goto LABEL_75;
              }
            }
          }
          CUserIdentityProvider::ServiceEndpointInitialize(v65, (const unsigned __int16 *)string);
          v66 = 0;
          v37 = v65;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
          if ( (int)CUserIdentityProvider::GetUserAccountsBlob(v37, length, &v66) >= 0 )
          {
            v38 = v58;
            v39 = (*v58)[7];
            v40 = v66;
            v64 = 0;
            if ( (int)ULongLongToUInt(0xCu, &v64) < 0 )
              RaiseException(0xC000000D, v41 - 11, 0, 0);
            WindowsCreateStringReference(L"AccountsBlob", v64, &v76, &v75);
            v42 = v39(v38, (GUID *)v75, (__int64)v40);
            v6 = v42;
            if ( v42 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x231,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
                (const char *)(unsigned int)v42,
                v56);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
              goto LABEL_48;
            }
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
      }
    }
    if ( FSPropertyBag::ShouldIncludeProperty(v35, L"CTACCollections") )
    {
      v63 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
      if ( FSPropertyBag::GetCtacBlob(v43, v61, (struct Windows::Data::Json::IJsonValue **)&v63) >= 0 )
      {
        v44 = v58;
        v45 = (*v58)[7];
        v46 = v63;
        v64 = 0;
        if ( (int)ULongLongToUInt(0xFu, &v64) < 0 )
          RaiseException(0xC000000D, v47 - 14, 0, 0);
        WindowsCreateStringReference(L"CTACCollections", v64, &v76, &v75);
        v48 = v45(v44, (GUID *)v75, (__int64)v46);
        v6 = v48;
        if ( v48 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23C,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
            (const char *)(unsigned int)v48,
            v56);
          v49 = &v63;
LABEL_74:
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v49);
          goto LABEL_75;
        }
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    }
    v67 = 0;
    v50 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
            &v58,
            (__int64)&v67);
    v6 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x242,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v50,
        v56);
LABEL_73:
      v49 = (HKEY *)&v67;
      goto LABEL_74;
    }
    v68 = 0;
    v51 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v67 + 56LL))(v67, &v68);
    v6 = v51;
    if ( v51 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v68, 0);
      do
        ++v3;
      while ( StringRawBuffer[v3] );
      v51 = _AllocStringWorker<CTCoAllocPolicy>(v72, v54, StringRawBuffer);
      v6 = v51;
      if ( v51 >= 0 )
        goto LABEL_72;
      v52 = 582;
    }
    else
    {
      v52 = 581;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v52,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v51,
      v56);
LABEL_72:
    Windows::Internal::String::~String((Windows::Internal::String *)&v68);
    goto LABEL_73;
  }
  v7 = 500;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
    (const char *)(unsigned int)v5,
    v56);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
LABEL_78:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  return v6;
}

```

## disassembly

```asm
0x1800be044  mov     [rsp-8+arg_10], rbx
0x1800be049  push    rbp
0x1800be04a  push    rsi
0x1800be04b  push    rdi
0x1800be04c  push    r12
0x1800be04e  push    r13
0x1800be050  push    r14
0x1800be052  push    r15
0x1800be054  lea     rbp, [rsp-27h]
0x1800be059  sub     rsp, 100h
0x1800be060  mov     rax, cs:__security_cookie
0x1800be067  xor     rax, rsp
0x1800be06a  mov     [rbp+57h+var_40], rax
0x1800be06e  mov     [rbp+57h+var_88], rdx
0x1800be072  mov     rsi, rcx
0x1800be075  mov     [rbp+57h+var_B8], rcx
0x1800be079  xor     r15d, r15d
0x1800be07c  mov     [rdx], r15
0x1800be07f  mov     [rbp+57h+sourceString], r15
0x1800be083  mov     [rbp+57h+var_98], r15
0x1800be087  mov     [rbp+57h+var_90], r15
0x1800be08b  lea     rcx, [rbp+57h+sourceString]
0x1800be08f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be094  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800be098  mov     [rbp+57h+var_98], rdi
0x1800be09c  mov     [rbp+57h+var_90], rdi
0x1800be0a0  lea     rdx, [rbp+57h+sourceString]; unsigned __int16 **
0x1800be0a4  mov     rcx, rsi; this
0x1800be0a7  call    ?ConstructPropertyBag@FSPropertyBag@@AEAAJPEAPEAG@Z; FSPropertyBag::ConstructPropertyBag(ushort * *)
0x1800be0ac  mov     ebx, eax
0x1800be0ae  test    eax, eax
0x1800be0b0  jns     loc_1800BE172
0x1800be0b6  mov     [rbp+57h+var_D0], 0FFFFFFFF80000002h
0x1800be0be  mov     r9d, 800BFA13h
0x1800be0c4  lea     r8, aLasthr; "LastHR"
0x1800be0cb  lea     edx, [rdi+2]
0x1800be0ce  lea     rcx, [rbp+57h+var_D0]
0x1800be0d2  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800be0d7  mov     [rbp+57h+string], r15
0x1800be0db  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r15
0x1800be0df  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r15
0x1800be0e3  mov     r8d, ebx
0x1800be0e6  lea     rdx, aLu; "%lu"
0x1800be0ed  lea     rcx, [rbp+57h+string]
0x1800be0f1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800be0f6  mov     ebx, eax
0x1800be0f8  test    eax, eax
0x1800be0fa  jns     short loc_1800BE103
0x1800be0fc  mov     edx, 1F4h
0x1800be101  jmp     short loc_1800BE148
0x1800be103  mov     r9, [rbp+57h+string]
0x1800be107  lea     r8, aPropertybaghr; "PropertyBagHr"
0x1800be10e  lea     rdx, aSS_6; "&%s=%s"
0x1800be115  lea     rcx, [rbp+57h+sourceString]
0x1800be119  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800be11e  test    eax, eax
0x1800be120  jns     short loc_1800BE169
0x1800be122  mov     r9, [rbp+57h+string]
0x1800be126  lea     r8, aPropertybaghr; "PropertyBagHr"
0x1800be12d  lea     rdx, aSS_6; "&%s=%s"
0x1800be134  lea     rcx, [rbp+57h+sourceString]
0x1800be138  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800be13d  mov     ebx, eax
0x1800be13f  test    eax, eax
0x1800be141  jns     short loc_1800BE169
0x1800be143  mov     edx, 1F7h; void *
0x1800be148  mov     r9d, eax; char *
0x1800be14b  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be152  mov     rcx, [rbp+5Fh]; this
0x1800be156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be15b  lea     rcx, [rbp+57h+string]
0x1800be15f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be164  jmp     loc_1800BE83F
0x1800be169  lea     rcx, [rbp+57h+string]
0x1800be16d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be172  mov     [rsp+130h+var_E8], r15
0x1800be177  lea     rcx, [rsp+130h+var_E8]
0x1800be17c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be181  lea     rdx, [rsp+130h+var_E8]; struct Windows::Data::Json::IJsonValue **
0x1800be186  mov     rcx, rsi; this
0x1800be189  call    ?GetFlightIdEntriesAsJsonValue@FSPropertyBag@@AEAAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z; FSPropertyBag::GetFlightIdEntriesAsJsonValue(Windows::Data::Json::IJsonValue * *)
0x1800be18e  mov     r12d, eax
0x1800be191  mov     [rsp+130h+var_F0], r15
0x1800be196  lea     rcx, [rsp+130h+var_F0]
0x1800be19b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be1a0  lea     rdx, [rsp+130h+var_F0]; struct Windows::Data::Json::IJsonValue **
0x1800be1a5  call    ?GetServiceDrivenActionResultsAsJsonValue@FSPropertyBag@@AEAAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z; FSPropertyBag::GetServiceDrivenActionResultsAsJsonValue(Windows::Data::Json::IJsonValue * *)
0x1800be1aa  mov     r13d, eax
0x1800be1ad  mov     [rsp+130h+var_F8], r15
0x1800be1b2  lea     rcx, [rbp+57h+var_60]; string
0x1800be1b6  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800be1bb  lea     rdx, [rsp+130h+var_F8]
0x1800be1c0  mov     rcx, [rax]
0x1800be1c3  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800be1c8  mov     ebx, eax
0x1800be1ca  test    eax, eax
0x1800be1cc  jns     short loc_1800BE1EB
0x1800be1ce  mov     rcx, [rbp+5Fh]; this
0x1800be1d2  mov     r9d, eax; char *
0x1800be1d5  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be1dc  mov     edx, 202h; void *
0x1800be1e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be1e6  jmp     loc_1800BE81E
0x1800be1eb  mov     [rsp+130h+var_E0], r15
0x1800be1f0  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800be1f7  lea     rcx, [rbp+57h+var_60]; string
0x1800be1fb  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800be200  lea     rdx, [rsp+130h+var_E0]
0x1800be205  mov     rcx, [rax]
0x1800be208  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x1800be20d  mov     ebx, eax
0x1800be20f  test    eax, eax
0x1800be211  jns     short loc_1800BE230
0x1800be213  mov     rcx, [rbp+5Fh]; this
0x1800be217  mov     r9d, eax; char *
0x1800be21a  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be221  mov     edx, 205h; void *
0x1800be226  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be22b  jmp     loc_1800BE813
0x1800be230  mov     [rsp+130h+var_D8], r15
0x1800be235  mov     rsi, [rsp+130h+var_E0]
0x1800be23a  mov     rax, [rsi]
0x1800be23d  mov     r14, [rax+50h]
0x1800be241  lea     rcx, [rsp+130h+var_D8]
0x1800be246  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800be24b  mov     rbx, [rbp+57h+sourceString]
0x1800be24f  mov     [rsp+130h+length], r15d
0x1800be254  mov     rcx, rdi
0x1800be257  inc     rcx; unsigned __int64
0x1800be25a  cmp     [rbx+rcx*2], r15w
0x1800be25f  jnz     short loc_1800BE257
0x1800be261  lea     rdx, [rsp+130h+length]; unsigned int *
0x1800be266  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800be26b  test    eax, eax
0x1800be26d  jns     short loc_1800BE284
0x1800be26f  xor     r9d, r9d; lpArguments
0x1800be272  xor     r8d, r8d; nNumberOfArguments
0x1800be275  lea     edx, [r9+1]; dwExceptionFlags
0x1800be279  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800be27e  call    cs:__imp_RaiseException
0x1800be284  lea     r9, [rbp+57h+string]; string
0x1800be288  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800be28c  mov     edx, [rsp+130h+length]; length
0x1800be290  mov     rcx, rbx; sourceString
0x1800be293  call    cs:__imp_WindowsCreateStringReference
0x1800be299  lea     r8, [rsp+130h+var_D8]
0x1800be29e  mov     rdx, [rbp+57h+string]
0x1800be2a2  mov     rcx, rsi
0x1800be2a5  mov     rax, r14
0x1800be2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be2ad  mov     ebx, eax
0x1800be2af  test    eax, eax
0x1800be2b1  jns     short loc_1800BE2D0
0x1800be2b3  mov     edx, 209h; void *
0x1800be2b8  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800be2bf  mov     r9d, eax; char *
0x1800be2c2  mov     rcx, [rbp+5Fh]; this
0x1800be2c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be2cb  jmp     loc_1800BE808
0x1800be2d0  mov     rsi, [rsp+130h+var_F8]
0x1800be2d5  mov     rax, [rsi]
0x1800be2d8  mov     r15, [rax+38h]
0x1800be2dc  mov     r14, [rsp+130h+var_D8]
0x1800be2e1  mov     rbx, cs:?s_postPropertyBag@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_postPropertyBag
0x1800be2e8  xor     r9d, r9d
0x1800be2eb  mov     [rsp+130h+length], r9d
0x1800be2f0  mov     rcx, rdi
0x1800be2f3  inc     rcx; unsigned __int64
0x1800be2f6  cmp     [rbx+rcx*2], r9w
0x1800be2fb  jnz     short loc_1800BE2F3
0x1800be2fd  lea     rdx, [rsp+130h+length]; unsigned int *
0x1800be302  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800be307  test    eax, eax
0x1800be309  jns     short loc_1800BE31D
0x1800be30b  xor     r8d, r8d; nNumberOfArguments
0x1800be30e  lea     edx, [r8+1]; dwExceptionFlags
0x1800be312  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800be317  call    cs:__imp_RaiseException
0x1800be31d  lea     r9, [rbp+57h+string]; string
0x1800be321  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800be325  mov     edx, [rsp+130h+length]; length
0x1800be329  mov     rcx, rbx; sourceString
0x1800be32c  call    cs:__imp_WindowsCreateStringReference
0x1800be332  mov     r8, r14
0x1800be335  mov     rdx, [rbp+57h+string]
0x1800be339  mov     rcx, rsi
0x1800be33c  mov     rax, r15
0x1800be33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be344  mov     ebx, eax
0x1800be346  test    eax, eax
0x1800be348  jns     short loc_1800BE354
0x1800be34a  mov     edx, 20Ah
0x1800be34f  jmp     loc_1800BE2B8
0x1800be354  test    r12d, r12d
0x1800be357  js      loc_1800BE3E4
0x1800be35d  mov     rsi, [rsp+130h+var_F8]
0x1800be362  mov     rax, [rsi]
0x1800be365  mov     r15, [rax+38h]
0x1800be369  mov     r14, [rsp+130h+var_E8]
0x1800be36e  mov     rbx, cs:?s_postFlightIDBlob@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_postFlightIDBlob
0x1800be375  xor     r12d, r12d
0x1800be378  mov     [rsp+130h+length], r12d
0x1800be37d  mov     rcx, rdi
0x1800be380  inc     rcx; unsigned __int64
0x1800be383  cmp     [rbx+rcx*2], r12w
0x1800be388  jnz     short loc_1800BE380
0x1800be38a  lea     rdx, [rsp+130h+length]; unsigned int *
0x1800be38f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800be394  test    eax, eax
0x1800be396  jns     short loc_1800BE3AD
0x1800be398  xor     r9d, r9d; lpArguments
0x1800be39b  xor     r8d, r8d; nNumberOfArguments
0x1800be39e  lea     edx, [r9+1]; dwExceptionFlags
0x1800be3a2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800be3a7  call    cs:__imp_RaiseException
0x1800be3ad  lea     r9, [rbp+57h+string]; string
0x1800be3b1  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800be3b5  mov     edx, [rsp+130h+length]; length
0x1800be3b9  mov     rcx, rbx; sourceString
0x1800be3bc  call    cs:__imp_WindowsCreateStringReference
0x1800be3c2  mov     r8, r14
0x1800be3c5  mov     rdx, [rbp+57h+string]
0x1800be3c9  mov     rcx, rsi
0x1800be3cc  mov     rax, r15
0x1800be3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be3d4  mov     ebx, eax
0x1800be3d6  test    eax, eax
0x1800be3d8  jns     short loc_1800BE3E7
0x1800be3da  mov     edx, 20Fh
0x1800be3df  jmp     loc_1800BE2B8
0x1800be3e4  xor     r12d, r12d
0x1800be3e7  test    r13d, r13d
0x1800be3ea  js      loc_1800BE474
0x1800be3f0  mov     rsi, [rsp+130h+var_F8]
0x1800be3f5  mov     rax, [rsi]
0x1800be3f8  mov     r15, [rax+38h]
0x1800be3fc  mov     r14, [rsp+130h+var_F0]
0x1800be401  mov     rbx, cs:?s_postServiceDrivenActionResults@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_postServiceDrivenActionResults
0x1800be408  mov     [rsp+130h+length], r12d
0x1800be40d  mov     rcx, rdi
0x1800be410  inc     rcx; unsigned __int64
0x1800be413  cmp     [rbx+rcx*2], r12w
0x1800be418  jnz     short loc_1800BE410
0x1800be41a  lea     rdx, [rsp+130h+length]; unsigned int *
0x1800be41f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800be424  test    eax, eax
0x1800be426  jns     short loc_1800BE43D
0x1800be428  xor     r9d, r9d; lpArguments
0x1800be42b  xor     r8d, r8d; nNumberOfArguments
0x1800be42e  lea     edx, [r9+1]; dwExceptionFlags
0x1800be432  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800be437  call    cs:__imp_RaiseException
0x1800be43d  lea     r9, [rbp+57h+string]; string
0x1800be441  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800be445  mov     edx, [rsp+130h+length]; length
0x1800be449  mov     rcx, rbx; sourceString
0x1800be44c  call    cs:__imp_WindowsCreateStringReference
0x1800be452  mov     r8, r14
0x1800be455  mov     rdx, [rbp+57h+string]
0x1800be459  mov     rcx, rsi
0x1800be45c  mov     rax, r15
0x1800be45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be464  mov     ebx, eax
0x1800be466  test    eax, eax
0x1800be468  jns     short loc_1800BE474
0x1800be46a  mov     edx, 215h
0x1800be46f  jmp     loc_1800BE2B8
0x1800be474  lea     rdx, aAccountsblob; "AccountsBlob"
0x1800be47b  mov     r15, [rbp+57h+var_B8]
0x1800be47f  mov     rcx, r15; this
0x1800be482  call    ?ShouldIncludeProperty@FSPropertyBag@@AEAA_NPEBG@Z; FSPropertyBag::ShouldIncludeProperty(ushort const *)
0x1800be487  test    al, al
0x1800be489  jz      loc_1800BE685
0x1800be48f  mov     [rsp+130h+length], r12d
0x1800be494  mov     rbx, 0FFFFFFFF80000002h
0x1800be49b  mov     [rbp+57h+var_D0], rbx
0x1800be49f  lea     r9, [rsp+130h+length]
0x1800be4a4  lea     r8, aSupportedtypes; "SupportedTypes"
0x1800be4ab  mov     edx, 4
0x1800be4b0  lea     rcx, [rbp+57h+var_D0]
0x1800be4b4  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x1800be4b9  test    eax, eax
0x1800be4bb  js      loc_1800BE685
0x1800be4c1  mov     [rbp+57h+var_C0], r12
0x1800be4c5  lea     rcx, [rbp+57h+var_C0]
0x1800be4c9  call    ??$MakeAndInitialize@VCUserIdentityProvider@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCUserIdentityProvider@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUserIdentityProvider,CUserIdentityProvider,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CUserIdentityProvider>>)
0x1800be4ce  test    eax, eax
0x1800be4d0  js      loc_1800BE67C
0x1800be4d6  cmp     [rbp+57h+var_C0], r12
0x1800be4da  jz      loc_1800BE67C
0x1800be4e0  mov     [rbp+57h+string], r12
0x1800be4e4  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x1800be4e8  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x1800be4ec  lea     rcx, [rbp+57h+string]
0x1800be4f0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800be4f5  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdi
0x1800be4f9  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rdi
0x1800be4fd  mov     [rbp+57h+var_D0], rbx
0x1800be501  mov     [rsp+130h+var_110], r12; int
0x1800be506  lea     r9, [rbp+57h+string]; unsigned __int16 **
  ... truncated ...
```
