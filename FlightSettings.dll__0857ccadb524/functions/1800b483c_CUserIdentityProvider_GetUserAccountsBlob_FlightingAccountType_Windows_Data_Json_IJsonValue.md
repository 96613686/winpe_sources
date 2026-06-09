# CUserIdentityProvider::GetUserAccountsBlob(FlightingAccountType,Windows::Data::Json::IJsonValue * *)

- ea: `0x1800b483c`
- end: `0x1800b53f1`
- name: `?GetUserAccountsBlob@CUserIdentityProvider@@QEAAJW4FlightingAccountType@@PEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `2997`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800be044`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x180013da0`
- `0x1800177bc`
- `0x1800325f4`
- `0x1800327ac`
- `0x1800328bc`
- `0x1800334f0`
- `0x18008a2fc`
- `0x18008f5a4`
- `0x18008f6b4`
- `0x1800960cc`
- `0x1800980c4`
- `0x1800996b4`
- `0x1800afad0`
- `0x1800afb54`
- `0x1800b1e24`
- `0x1800b2374`
- `0x1800b24cc`
- `0x1800b3600`
- `0x1800b3af0`
- `0x1800b3ebc`
- `0x1800b483c`
- `0x1800b6200`
- `0x1800b6360`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b48d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b48d0`

## string_xrefs

- `0x1800b4bfb`: `Windows.Data.Json.JsonArray`
- `0x1800b4b56`: `Windows.Data.Json.JsonValue`
- `0x1800b48e3`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b49d0`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b4a54`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b4ae8`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b4b83`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b4c2c`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b4cd0`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b4fb1`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b50a5`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b515f`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b520f`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b52b5`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b535b`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CUserIdentityProvider::GetUserAccountsBlob(CUserIdentityProvider *a1, int a2, _QWORD *a3)
{
  HRESULT active; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  unsigned __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 *v15; // rax
  int v16; // eax
  unsigned __int64 v17; // rdx
  __int64 *v18; // rax
  int v19; // eax
  unsigned __int64 v20; // rdx
  int v21; // eax
  unsigned __int64 v22; // rdx
  unsigned int v23; // esi
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **); // rbx
  int v26; // eax
  struct Windows::Security::Credentials::IWebAccount *v27; // rdi
  __int64 (__fastcall *v28)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v29; // eax
  CUserIdentityProvider *v30; // rcx
  int AccountTypeFromProvider; // eax
  int v32; // edi
  int v33; // eax
  int v34; // eax
  int AADUserTicketForAccountId; // eax
  char v36; // r8
  const unsigned __int16 **v37; // rdx
  Flighting::Helpers *v38; // rcx
  int v39; // ebx
  CUserIdentityProvider *v40; // rcx
  int v41; // eax
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  unsigned __int8 v44; // cl
  __int64 v45; // rcx
  FlightSettingsAPITelemetryClass *v46; // rax
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  char v54; // [rsp+40h] [rbp-C0h] BYREF
  char v55; // [rsp+41h] [rbp-BFh] BYREF
  int v56; // [rsp+44h] [rbp-BCh] BYREF
  HSTRING v57; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v58; // [rsp+50h] [rbp-B0h] BYREF
  bool v59[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v60; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v61; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v64; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v65)(_QWORD, GUID *, __int64); // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Data::Json::IJsonValueStatics *v66; // [rsp+90h] [rbp-70h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v67; // [rsp+98h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v69; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v72; // [rsp+C0h] [rbp-40h] BYREF
  struct Windows::Data::Json::IJsonValue *v73[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v74; // [rsp+D8h] [rbp-28h]
  LPVOID *v75; // [rsp+E0h] [rbp-20h]
  char *v76; // [rsp+E8h] [rbp-18h]
  __int64 *v77; // [rsp+F0h] [rbp-10h]
  char v78; // [rsp+F8h] [rbp-8h]
  HSTRING string[4]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *a3 = 0;
  v56 = 0;
  v73[1] = (struct Windows::Data::Json::IJsonValue *)&v56;
  v74 = 1;
  v54 = 0;
  active = ImpersonationHelper::ImpersonateActiveUser((struct UstCommon::CImpersonator *)&v54);
  if ( active < 0 )
    goto LABEL_66;
  v58 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
  active = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v58);
  if ( active < 0
    || (v62 = 0,
        active = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v58 + 32LL))(v58, 5, &v62),
        active < 0) )
  {
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40E,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)active,
      ppv);
    goto LABEL_65;
  }
  if ( v62 == 1 )
  {
    v55 = 0;
  }
  else
  {
    v55 = 1;
    active = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, 1);
    if ( active < 0 )
      goto LABEL_3;
  }
  v75 = &v58;
  v76 = &v55;
  v77 = &v62;
  v78 = 1;
  LODWORD(v57) = 0;
  v61 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
  CUserIdentityProvider::GetPrimaryAccount(a1, (enum FlightingAccountType *)&v57, &v61);
  v60 = 0;
  v7 = *((_QWORD *)a1 + 2);
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 96LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
  v9 = v8(v7, &v60);
  active = v9;
  v56 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    if ( v55 )
    {
      LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
      if ( (int)v57 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v10);
    }
    goto LABEL_65;
  }
  v63 = 0;
  v11 = BlockOnCompletionAndGetResults<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *>>(
          v60,
          (__int64)&v63);
  active = v11;
  v56 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41A,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    if ( v55 )
    {
      LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
      if ( (int)v57 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v12);
    }
    goto LABEL_65;
  }
  v70 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 56LL))(v63, &v70);
  active = v13;
  v56 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    if ( v55 )
    {
      LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
      if ( (int)v57 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v14);
    }
    goto LABEL_65;
  }
  v66 = 0;
  v15 = (__int64 *)Windows::Internal::StringReference::StringReference(string, L"Windows.Data.Json.JsonValue");
  v16 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(
          *v15,
          (__int64)&v66);
  active = v16;
  v56 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x420,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v16,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    if ( v55 )
    {
      LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
      if ( (int)v57 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v17);
    }
    goto LABEL_65;
  }
  v65 = 0;
  v18 = (__int64 *)Windows::Internal::StringReference::StringReference(string, L"Windows.Data.Json.JsonArray");
  v19 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(*v18, &v65);
  active = v19;
  v56 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x423,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v19,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    if ( v55 )
    {
      LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
      if ( (int)v57 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v20);
    }
    goto LABEL_65;
  }
  v68 = 0;
  v21 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
          &v65,
          (__int64)&v68);
  active = v21;
  v56 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x426,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v21,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    if ( v55 )
    {
      LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
      if ( (int)v57 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v22);
    }
    goto LABEL_65;
  }
  v23 = 0;
  if ( !v70 )
  {
LABEL_60:
    v41 = (**v65)(v65, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, (__int64)a3);
    active = v41;
    v56 = v41;
    if ( v41 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x468,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v41,
        ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
    if ( v55 )
    {
      LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
      if ( (int)v57 < 0 )
        FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v42);
    }
    goto LABEL_65;
  }
  while ( 1 )
  {
    v64 = 0;
    v24 = v63;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v63 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
    v26 = v25(v24, v23, &v64);
    active = v26;
    v56 = v26;
    if ( v26 < 0 )
      break;
    v67 = 0;
    v27 = v64;
    v28 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v64 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v67);
    v29 = v28(v27, &v67);
    active = v29;
    v56 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42E,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v29,
        ppv);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v67);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
      if ( v55 )
      {
        LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
        if ( (int)v57 < 0 )
          FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v51);
      }
      goto LABEL_65;
    }
    LODWORD(v57) = 0;
    AccountTypeFromProvider = CUserIdentityProvider::GetAccountTypeFromProvider(
                                v30,
                                v67,
                                (enum FlightingAccountType *)&v57);
    active = AccountTypeFromProvider;
    v56 = AccountTypeFromProvider;
    if ( AccountTypeFromProvider < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x431,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)AccountTypeFromProvider,
        ppv);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v67);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
      if ( v55 )
      {
        LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
        if ( (int)v57 < 0 )
          FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v50);
      }
      goto LABEL_65;
    }
    v32 = (int)v57;
    if ( ((unsigned int)v57 & a2) != 0 )
    {
      v71 = 0;
      v33 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v64,
              (__int64)&v71);
      active = v33;
      v56 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x437,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
          (const char *)(unsigned int)v33,
          ppv);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v67);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
        if ( v55 )
        {
          LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
          if ( (int)v57 < 0 )
            FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v49);
        }
        goto LABEL_65;
      }
      v69 = 0;
      v34 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v71 + 48LL))(v71, &v69);
      active = v34;
      v56 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x43A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
          (const char *)(unsigned int)v34,
          ppv);
        Windows::Internal::String::~String((Windows::Internal::String *)&v69);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v67);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
        if ( v55 )
        {
          LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
          if ( (int)v57 < 0 )
            FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v48);
        }
        goto LABEL_65;
      }
      v59[0] = 0;
      CUserIdentityProvider::IsSameMappedAccount(a1, v64, v61, v59);
      v72 = 0;
      v57 = 0;
      if ( v32 == 2 )
      {
        AADUserTicketForAccountId = CUserIdentityProvider::GetAADUserTicketForAccountId(a1, v69, &v57);
        v37 = (const unsigned __int16 **)&CUserIdentityProvider::s_accountTypeAadString;
LABEL_54:
        v39 = AADUserTicketForAccountId;
        Windows::Internal::String::Initialize<unsigned short const *>(&v72, (__int64 *)v37, v36);
        if ( v39 >= 0 )
        {
          v73[0] = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v73);
          if ( (int)CUserIdentityProvider::MakeAccountJsonObject(v40, v66, v69, v72, v59[0], v57, v73) >= 0 )
            (*(void (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v68 + 104LL))(
              v68,
              v73[0]);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v73);
        }
      }
      else if ( v32 == 1 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59227329>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59227329>::GetImpl'::`2'::impl)
          && Flighting::Helpers::GetFlightingMsaV2UserEnabled(v38) )
        {
          AADUserTicketForAccountId = CUserIdentityProvider::GetMSAUserJsonWebTokenForAccountId(a1, v69, &v57);
        }
        else
        {
          AADUserTicketForAccountId = CUserIdentityProvider::GetMSAUserTicketForAccountId(a1, v69, &v57);
        }
        v37 = (const unsigned __int16 **)&CUserIdentityProvider::s_accountTypeMsaString;
        goto LABEL_54;
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&v57);
      Windows::Internal::String::~String((Windows::Internal::String *)&v72);
      Windows::Internal::String::~String((Windows::Internal::String *)&v69);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
    if ( ++v23 >= v70 )
      goto LABEL_60;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x42B,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
    (const char *)(unsigned int)v26,
    ppv);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
  if ( v55 )
  {
    LODWORD(v57) = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v58 + 24LL))(v58, 5, v62);
    if ( (int)v57 < 0 )
      FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>((int *)&v57, v52);
  }
LABEL_65:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
LABEL_66:
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v54);
  if ( v56 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v44, v43) )
  {
    v46 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v45,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::GetAccountsBlobFailed_(v46, v56);
  }
  return (unsigned int)active;
}

```

## disassembly

```asm
0x1800b483c  mov     [rsp-8+arg_8], rbx
0x1800b4841  push    rbp
0x1800b4842  push    rsi
0x1800b4843  push    rdi
0x1800b4844  push    r12
0x1800b4846  push    r13
0x1800b4848  push    r14
0x1800b484a  push    r15
0x1800b484c  lea     rbp, [rsp-30h]
0x1800b4851  sub     rsp, 130h
0x1800b4858  mov     rax, cs:__security_cookie
0x1800b485f  xor     rax, rsp
0x1800b4862  mov     [rbp+60h+var_40], rax
0x1800b4866  mov     r15, r8
0x1800b4869  mov     r12d, edx
0x1800b486c  mov     r14, rcx
0x1800b486f  xor     r13d, r13d
0x1800b4872  mov     [r8], r13
0x1800b4875  mov     [rsp+160h+var_11C], r13d
0x1800b487a  lea     rax, [rsp+160h+var_11C]
0x1800b487f  mov     [rbp+60h+var_90], rax
0x1800b4883  lea     edi, [r13+1]
0x1800b4887  mov     [rbp+60h+var_88], dil
0x1800b488b  mov     [rsp+160h+var_120], r13b
0x1800b4890  lea     rcx, [rsp+160h+var_120]; this
0x1800b4895  call    ?ImpersonateActiveUser@ImpersonationHelper@@SAJPEAVCImpersonator@UstCommon@@@Z; ImpersonationHelper::ImpersonateActiveUser(UstCommon::CImpersonator *)
0x1800b489a  mov     ebx, eax
0x1800b489c  test    eax, eax
0x1800b489e  js      loc_1800B5042
0x1800b48a4  mov     [rsp+160h+var_110], r13
0x1800b48a9  lea     rcx, [rsp+160h+var_110]
0x1800b48ae  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b48b3  lea     rax, [rsp+160h+var_110]
0x1800b48b8  mov     [rsp+160h+ppv], rax; int
0x1800b48bd  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800b48c4  mov     r8d, edi; dwClsContext
0x1800b48c7  xor     edx, edx; pUnkOuter
0x1800b48c9  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800b48d0  call    cs:__imp_CoCreateInstance
0x1800b48d6  mov     ebx, eax
0x1800b48d8  test    eax, eax
0x1800b48da  jns     short loc_1800B48F9
0x1800b48dc  mov     rcx, [rbp+68h]; this
0x1800b48e0  mov     r9d, ebx; char *
0x1800b48e3  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b48ea  mov     edx, 40Eh; void *
0x1800b48ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b48f4  jmp     loc_1800B5037
0x1800b48f9  mov     [rsp+160h+var_F0], r13
0x1800b48fe  mov     rcx, [rsp+160h+var_110]
0x1800b4903  mov     rax, [rcx]
0x1800b4906  lea     r8, [rsp+160h+var_F0]
0x1800b490b  mov     esi, 5
0x1800b4910  mov     edx, esi
0x1800b4912  mov     rax, [rax+20h]
0x1800b4916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b491b  mov     ebx, eax
0x1800b491d  test    eax, eax
0x1800b491f  js      short loc_1800B48DC
0x1800b4921  cmp     [rsp+160h+var_F0], rdi
0x1800b4926  jz      short loc_1800B494B
0x1800b4928  mov     [rsp+160h+var_11F], dil
0x1800b492d  mov     rcx, [rsp+160h+var_110]
0x1800b4932  mov     rax, [rcx]
0x1800b4935  mov     r8, rdi
0x1800b4938  mov     edx, esi
0x1800b493a  mov     rax, [rax+18h]
0x1800b493e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4943  mov     ebx, eax
0x1800b4945  test    eax, eax
0x1800b4947  jns     short loc_1800B4950
0x1800b4949  jmp     short loc_1800B48DC
0x1800b494b  mov     [rsp+160h+var_11F], r13b
0x1800b4950  lea     rax, [rsp+160h+var_110]
0x1800b4955  mov     [rbp+60h+var_80], rax
0x1800b4959  lea     rax, [rsp+160h+var_11F]
0x1800b495e  mov     [rbp+60h+var_78], rax
0x1800b4962  lea     rax, [rsp+160h+var_F0]
0x1800b4967  mov     [rbp+60h+var_70], rax
0x1800b496b  mov     [rbp+60h+var_68], dil
0x1800b496f  mov     dword ptr [rsp+160h+var_118], r13d
0x1800b4974  mov     [rsp+160h+var_F8], r13
0x1800b4979  lea     rcx, [rsp+160h+var_F8]
0x1800b497e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4983  lea     r8, [rsp+160h+var_F8]; struct Windows::Security::Credentials::IWebAccount **
0x1800b4988  lea     rdx, [rsp+160h+var_118]; enum FlightingAccountType *
0x1800b498d  mov     rcx, r14; this
0x1800b4990  call    ?GetPrimaryAccount@CUserIdentityProvider@@AEAAJPEAW4FlightingAccountType@@PEAPEAUIWebAccount@Credentials@Security@Windows@@@Z; CUserIdentityProvider::GetPrimaryAccount(FlightingAccountType *,Windows::Security::Credentials::IWebAccount * *)
0x1800b4995  mov     [rsp+160h+var_100], r13
0x1800b499a  mov     rdi, [r14+10h]
0x1800b499e  mov     rax, [rdi]
0x1800b49a1  mov     rbx, [rax+60h]
0x1800b49a5  lea     rcx, [rsp+160h+var_100]
0x1800b49aa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b49af  lea     rdx, [rsp+160h+var_100]
0x1800b49b4  mov     rcx, rdi
0x1800b49b7  mov     rax, rbx
0x1800b49ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b49bf  mov     ebx, eax
0x1800b49c1  mov     [rsp+160h+var_11C], eax
0x1800b49c5  test    eax, eax
0x1800b49c7  jns     short loc_1800B4A2F
0x1800b49c9  mov     rcx, [rbp+68h]; this
0x1800b49cd  mov     r9d, eax; char *
0x1800b49d0  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b49d7  mov     edx, 417h; void *
0x1800b49dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b49e1  nop
0x1800b49e2  lea     rcx, [rsp+160h+var_100]
0x1800b49e7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b49ec  nop
0x1800b49ed  lea     rcx, [rsp+160h+var_F8]
0x1800b49f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b49f7  nop
0x1800b49f8  cmp     [rsp+160h+var_11F], r13b
0x1800b49fd  jz      short loc_1800B4A2A
0x1800b49ff  mov     rcx, [rsp+160h+var_110]
0x1800b4a04  mov     rax, [rcx]
0x1800b4a07  mov     r8, [rsp+160h+var_F0]
0x1800b4a0c  mov     edx, esi
0x1800b4a0e  mov     rax, [rax+18h]
0x1800b4a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4a17  mov     dword ptr [rsp+160h+var_118], eax
0x1800b4a1b  test    eax, eax
0x1800b4a1d  jns     short loc_1800B4A2A
0x1800b4a1f  lea     rcx, [rsp+160h+var_118]
0x1800b4a24  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b4a29  nop
0x1800b4a2a  jmp     loc_1800B5037
0x1800b4a2f  mov     [rsp+160h+var_E8], r13
0x1800b4a34  lea     rdx, [rsp+160h+var_E8]
0x1800b4a39  mov     rcx, [rsp+160h+var_100]
0x1800b4a3e  call    ??$BlockOnCompletionAndGetResults@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@U?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *>>>,tagCOWAIT_FLAGS,void *)
0x1800b4a43  mov     ebx, eax
0x1800b4a45  mov     [rsp+160h+var_11C], eax
0x1800b4a49  test    eax, eax
0x1800b4a4b  jns     short loc_1800B4ABE
0x1800b4a4d  mov     rcx, [rbp+68h]; this
0x1800b4a51  mov     r9d, eax; char *
0x1800b4a54  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b4a5b  mov     edx, 41Ah; void *
0x1800b4a60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4a65  nop
0x1800b4a66  lea     rcx, [rsp+160h+var_E8]
0x1800b4a6b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4a70  nop
0x1800b4a71  lea     rcx, [rsp+160h+var_100]
0x1800b4a76  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4a7b  nop
0x1800b4a7c  lea     rcx, [rsp+160h+var_F8]
0x1800b4a81  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4a86  nop
0x1800b4a87  cmp     [rsp+160h+var_11F], r13b
0x1800b4a8c  jz      short loc_1800B4AB9
0x1800b4a8e  mov     rcx, [rsp+160h+var_110]
0x1800b4a93  mov     rax, [rcx]
0x1800b4a96  mov     r8, [rsp+160h+var_F0]
0x1800b4a9b  mov     edx, esi
0x1800b4a9d  mov     rax, [rax+18h]
0x1800b4aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4aa6  mov     dword ptr [rsp+160h+var_118], eax
0x1800b4aaa  test    eax, eax
0x1800b4aac  jns     short loc_1800B4AB9
0x1800b4aae  lea     rcx, [rsp+160h+var_118]
0x1800b4ab3  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b4ab8  nop
0x1800b4ab9  jmp     loc_1800B5037
0x1800b4abe  mov     [rbp+60h+var_B0], r13d
0x1800b4ac2  mov     rcx, [rsp+160h+var_E8]
0x1800b4ac7  mov     rax, [rcx]
0x1800b4aca  lea     rdx, [rbp+60h+var_B0]
0x1800b4ace  mov     rax, [rax+38h]
0x1800b4ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ad7  mov     ebx, eax
0x1800b4ad9  mov     [rsp+160h+var_11C], eax
0x1800b4add  test    eax, eax
0x1800b4adf  jns     short loc_1800B4B52
0x1800b4ae1  mov     rcx, [rbp+68h]; this
0x1800b4ae5  mov     r9d, eax; char *
0x1800b4ae8  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b4aef  mov     edx, 41Dh; void *
0x1800b4af4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4af9  nop
0x1800b4afa  lea     rcx, [rsp+160h+var_E8]
0x1800b4aff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4b04  nop
0x1800b4b05  lea     rcx, [rsp+160h+var_100]
0x1800b4b0a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4b0f  nop
0x1800b4b10  lea     rcx, [rsp+160h+var_F8]
0x1800b4b15  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4b1a  nop
0x1800b4b1b  cmp     [rsp+160h+var_11F], r13b
0x1800b4b20  jz      short loc_1800B4B4D
0x1800b4b22  mov     rcx, [rsp+160h+var_110]
0x1800b4b27  mov     rax, [rcx]
0x1800b4b2a  mov     r8, [rsp+160h+var_F0]
0x1800b4b2f  mov     edx, esi
0x1800b4b31  mov     rax, [rax+18h]
0x1800b4b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b3a  mov     dword ptr [rsp+160h+var_118], eax
0x1800b4b3e  test    eax, eax
0x1800b4b40  jns     short loc_1800B4B4D
0x1800b4b42  lea     rcx, [rsp+160h+var_118]
0x1800b4b47  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b4b4c  nop
0x1800b4b4d  jmp     loc_1800B5037
0x1800b4b52  mov     [rbp+60h+var_D0], r13
0x1800b4b56  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800b4b5d  lea     rcx, [rbp+60h+string]; string
0x1800b4b61  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800b4b66  lea     rdx, [rbp+60h+var_D0]
0x1800b4b6a  mov     rcx, [rax]
0x1800b4b6d  call    ??$GetActivationFactory@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonValueStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValueStatics>>)
0x1800b4b72  mov     ebx, eax
0x1800b4b74  mov     [rsp+160h+var_11C], eax
0x1800b4b78  test    eax, eax
0x1800b4b7a  jns     short loc_1800B4BF7
0x1800b4b7c  mov     rcx, [rbp+68h]; this
0x1800b4b80  mov     r9d, eax; char *
0x1800b4b83  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b4b8a  mov     edx, 420h; void *
0x1800b4b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4b94  nop
0x1800b4b95  lea     rcx, [rbp+60h+var_D0]
0x1800b4b99  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4b9e  nop
0x1800b4b9f  lea     rcx, [rsp+160h+var_E8]
0x1800b4ba4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4ba9  nop
0x1800b4baa  lea     rcx, [rsp+160h+var_100]
0x1800b4baf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4bb4  nop
0x1800b4bb5  lea     rcx, [rsp+160h+var_F8]
0x1800b4bba  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4bbf  nop
0x1800b4bc0  cmp     [rsp+160h+var_11F], r13b
0x1800b4bc5  jz      short loc_1800B4BF2
0x1800b4bc7  mov     rcx, [rsp+160h+var_110]
0x1800b4bcc  mov     rax, [rcx]
0x1800b4bcf  mov     r8, [rsp+160h+var_F0]
0x1800b4bd4  mov     edx, esi
0x1800b4bd6  mov     rax, [rax+18h]
0x1800b4bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4bdf  mov     dword ptr [rsp+160h+var_118], eax
0x1800b4be3  test    eax, eax
0x1800b4be5  jns     short loc_1800B4BF2
0x1800b4be7  lea     rcx, [rsp+160h+var_118]
0x1800b4bec  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b4bf1  nop
0x1800b4bf2  jmp     loc_1800B5037
0x1800b4bf7  mov     [rbp+60h+var_D8], r13
0x1800b4bfb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800b4c02  lea     rcx, [rbp+60h+string]; string
0x1800b4c06  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1800b4c0b  lea     rdx, [rbp+60h+var_D8]
0x1800b4c0f  mov     rcx, [rax]
0x1800b4c12  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x1800b4c17  mov     ebx, eax
0x1800b4c19  mov     [rsp+160h+var_11C], eax
0x1800b4c1d  test    eax, eax
0x1800b4c1f  jns     loc_1800B4CAA
0x1800b4c25  mov     rcx, [rbp+68h]; this
0x1800b4c29  mov     r9d, eax; char *
0x1800b4c2c  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b4c33  mov     edx, 423h; void *
0x1800b4c38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4c3d  nop
0x1800b4c3e  lea     rcx, [rbp+60h+var_D8]
0x1800b4c42  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4c47  nop
0x1800b4c48  lea     rcx, [rbp+60h+var_D0]
0x1800b4c4c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4c51  nop
0x1800b4c52  lea     rcx, [rsp+160h+var_E8]
0x1800b4c57  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4c5c  nop
0x1800b4c5d  lea     rcx, [rsp+160h+var_100]
0x1800b4c62  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4c67  nop
0x1800b4c68  lea     rcx, [rsp+160h+var_F8]
0x1800b4c6d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4c72  nop
0x1800b4c73  cmp     [rsp+160h+var_11F], r13b
0x1800b4c78  jz      short loc_1800B4CA5
0x1800b4c7a  mov     rcx, [rsp+160h+var_110]
0x1800b4c7f  mov     rax, [rcx]
0x1800b4c82  mov     r8, [rsp+160h+var_F0]
0x1800b4c87  mov     edx, esi
0x1800b4c89  mov     rax, [rax+18h]
0x1800b4c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c92  mov     dword ptr [rsp+160h+var_118], eax
0x1800b4c96  test    eax, eax
0x1800b4c98  jns     short loc_1800B4CA5
0x1800b4c9a  lea     rcx, [rsp+160h+var_118]
0x1800b4c9f  call    ??$EnableCOMMarshallingFailed@AEBJ@FlightSettingsAPITelemetryClass@@SAXAEBJ@Z; FlightSettingsAPITelemetryClass::EnableCOMMarshallingFailed<long const &>(long const &)
0x1800b4ca4  nop
0x1800b4ca5  jmp     loc_1800B5037
0x1800b4caa  mov     [rbp+60h+var_C0], r13
0x1800b4cae  lea     rdx, [rbp+60h+var_C0]
  ... truncated ...
```
