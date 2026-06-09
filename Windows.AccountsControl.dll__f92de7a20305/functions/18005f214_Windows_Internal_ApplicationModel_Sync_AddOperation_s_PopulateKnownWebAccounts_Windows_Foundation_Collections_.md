# Windows::Internal::ApplicationModel::Sync::AddOperation::s_PopulateKnownWebAccounts(Windows::Foundation::Collections::IVector<Windows::Internal::UI::ApplicationSettings::WebAccountData *> *)

- ea: `0x18005f214`
- end: `0x18005fccd`
- name: `?s_PopulateKnownWebAccounts@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAU?$IVector@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@Collections@Foundation@5@@Z`
- size: `2745`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005aca0`

## callees

- `0x180006eac`
- `0x180008ea4`
- `0x180008ee0`
- `0x18000e5f0`
- `0x18000e87c`
- `0x180011ffc`
- `0x18004a7c8`
- `0x18005552c`
- `0x1800568fc`
- `0x18005d4a0`
- `0x18005d72c`
- `0x18005da74`
- `0x18005df74`
- `0x18005f214`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f4ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f5ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f7bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f7f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f8e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f8f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f9a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f9da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fb15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fb25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fbef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fc21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f4ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f5ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f7bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f7f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f8e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f8f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f9a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f9da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fa7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fb15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fb25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fbef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fc21`

## string_xrefs

- `0x18005f396`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_PopulateKnownWebAccounts(__int64 a1)
{
  unsigned int v2; // ebx
  int OneSyncAccounts; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int AllWamAccounts; // eax
  __int64 v8; // rcx
  int ProviderSpecificWamAccounts; // eax
  __int64 v10; // rdx
  unsigned int i; // esi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  unsigned int j; // r15d
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, _QWORD, struct PhoneInternal::Experiences::Sync::IAccount **); // rbx
  int v29; // eax
  int OneSyncAccountProperty; // eax
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // eax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64, __int64 *); // rbx
  int v40; // eax
  int v41; // eax
  unsigned int k; // esi
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, _QWORD, __int64 *); // rbx
  int v45; // eax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, HSTRING *); // rbx
  int v48; // eax
  HSTRING v49; // r8
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64, __int64 *); // rbx
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  int v58[2]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING v59; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v60; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v61; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v62; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v63; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v64[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v65; // [rsp+58h] [rbp-A8h] BYREF
  struct PhoneInternal::Experiences::Sync::IAccount *v66; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v67; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v68; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v69; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v71; // [rsp+88h] [rbp-78h] BYREF
  __int64 v72; // [rsp+90h] [rbp-70h] BYREF
  __int64 v73; // [rsp+98h] [rbp-68h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v75; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v76; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v77; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v78; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v79; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v80; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v82; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v83; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v86; // [rsp+108h] [rbp+8h]
  HSTRING *v87; // [rsp+110h] [rbp+10h]
  __int64 *v88; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  if ( a1 )
  {
    v84 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
    OneSyncAccounts = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetOneSyncAccounts(&v84);
    v2 = OneSyncAccounts;
    if ( OneSyncAccounts < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x397,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)OneSyncAccounts,
        v58[0]);
LABEL_110:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      return v2;
    }
    v75 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v84 + 56LL))(v84, &v75);
    if ( v75 )
    {
      *(_QWORD *)v58 = 0;
      v86 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.UI.ApplicationSettings.WebAccountData",
        0x37u,
        0x36u);
      v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>(
             v86,
             v58);
      v2 = v4;
      if ( v4 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A2,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v4,
          v58[0]);
LABEL_8:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v58);
        goto LABEL_110;
      }
      v60 = 0;
      v86 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"PhoneInternal.Experiences.Sync.AccountsManager",
        0x2Fu,
        0x2Eu);
      v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>(
             v86,
             &v60);
      v2 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A7,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v5,
          v58[0]);
LABEL_11:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
        goto LABEL_8;
      }
      v63 = 0;
      v86 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
        0x46u,
        0x45u);
      v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
             v86,
             &v63);
      v2 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3AC,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v6,
          v58[0]);
LABEL_14:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
        goto LABEL_11;
      }
      v62 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      AllWamAccounts = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAllWamAccounts(&v62);
      v2 = AllWamAccounts;
      if ( AllWamAccounts < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3AF,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)AllWamAccounts,
          v58[0]);
LABEL_17:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
        goto LABEL_14;
      }
      v61 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      ProviderSpecificWamAccounts = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Credentials::WebAccount *>>>(
                                      v8,
                                      &v61);
      v2 = ProviderSpecificWamAccounts;
      if ( ProviderSpecificWamAccounts < 0 )
      {
        v10 = 946;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)ProviderSpecificWamAccounts,
          v58[0]);
LABEL_21:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
        goto LABEL_17;
      }
      ProviderSpecificWamAccounts = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetProviderSpecificWamAccounts(
                                      5,
                                      v62,
                                      v61);
      v2 = ProviderSpecificWamAccounts;
      if ( ProviderSpecificWamAccounts < 0 )
      {
        v10 = 948;
        goto LABEL_20;
      }
      v82 = 0;
      ProviderSpecificWamAccounts = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v61 + 56LL))(
                                      v61,
                                      &v82);
      v2 = ProviderSpecificWamAccounts;
      if ( ProviderSpecificWamAccounts < 0 )
      {
        v10 = 951;
        goto LABEL_20;
      }
      for ( i = 0; i < v82; ++i )
      {
        v72 = 0;
        v12 = v61;
        v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v61 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
        v14 = v13(v12, i, &v72);
        v2 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3BC,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
            (const char *)(unsigned int)v14,
            v58[0]);
          goto LABEL_44;
        }
        string = 0;
        v15 = v72;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v72 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        v17 = v16(v15, &string);
        v2 = v17;
        if ( v17 < 0 )
        {
          v22 = 959;
          goto LABEL_41;
        }
        v64[0] = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, HSTRING, _BYTE *))(*(_QWORD *)v60 + 128LL))(v60, string, v64);
        v2 = v17;
        if ( v17 < 0 )
        {
          v22 = 962;
LABEL_41:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
            (const char *)(unsigned int)v17,
            v58[0]);
          goto LABEL_42;
        }
        if ( v64[0] )
        {
          v79 = 0;
          v18 = *(_QWORD *)v58;
          v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v58 + 72LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
          v20 = v19(v18, v72, &v79);
          v2 = v20;
          if ( v20 < 0 )
          {
            v21 = 967;
LABEL_38:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v21,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v20,
              v58[0]);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
LABEL_42:
            WindowsDeleteString(string);
            string = 0;
LABEL_44:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
            goto LABEL_21;
          }
          v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, v79);
          v2 = v20;
          if ( v20 < 0 )
          {
            v21 = 968;
            goto LABEL_38;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
        }
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      }
      v65 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      v24 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Credentials::WebAccount *>>>(
              v23,
              &v65);
      v2 = v24;
      if ( v24 < 0 )
      {
        v25 = 973;
        goto LABEL_47;
      }
      v24 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetProviderSpecificWamAccounts(3, v62, v65);
      v2 = v24;
      if ( v24 < 0 )
      {
        v25 = 975;
        goto LABEL_47;
      }
      v77 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v65 + 56LL))(v65, &v77);
      v2 = v24;
      if ( v24 < 0 )
      {
        v25 = 978;
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
          (const char *)(unsigned int)v24,
          v58[0]);
LABEL_48:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
        goto LABEL_21;
      }
      for ( j = 0; j < v75; ++j )
      {
        v66 = 0;
        v27 = v84;
        v28 = *(__int64 (__fastcall **)(__int64, _QWORD, struct PhoneInternal::Experiences::Sync::IAccount **))(*(_QWORD *)v84 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
        v29 = v28(v27, j, &v66);
        v2 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3D7,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
            (const char *)(unsigned int)v29,
            v58[0]);
          goto LABEL_107;
        }
        v59 = 0;
        WindowsDeleteString(0);
        v59 = 0;
        OneSyncAccountProperty = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetOneSyncAccountProperty(
                                   v66,
                                   L"SSOAccountId",
                                   &v59);
        v2 = OneSyncAccountProperty;
        if ( OneSyncAccountProperty < 0 )
        {
          v56 = 988;
          goto LABEL_104;
        }
        v76 = 0;
        OneSyncAccountProperty = (*(__int64 (__fastcall **)(struct PhoneInternal::Experiences::Sync::IAccount *, unsigned int *))(*(_QWORD *)v66 + 136LL))(
                                   v66,
                                   &v76);
        v2 = OneSyncAccountProperty;
        if ( OneSyncAccountProperty < 0 )
        {
          v56 = 991;
LABEL_104:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v56,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
            (const char *)(unsigned int)OneSyncAccountProperty,
            v58[0]);
          goto LABEL_105;
        }
        if ( v59 )
        {
          v73 = 0;
          v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v60 + 112LL))(v60, v76, &v73);
          v2 = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E4,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v31,
              v58[0]);
            goto LABEL_92;
          }
          v68 = 0;
          v67 = 0;
          v32 = v73;
          v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v73 + 56LL);
          WindowsDeleteString(0);
          v68 = 0;
          v34 = v33(v32, &v68);
          v2 = v34;
          if ( v34 < 0 )
          {
            v54 = 1001;
            goto LABEL_89;
          }
          v35 = v73;
          v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v73 + 48LL);
          WindowsDeleteString(v67);
          v67 = 0;
          v34 = v36(v35, &v67);
          v2 = v34;
          if ( v34 < 0 )
          {
            v54 = 1002;
LABEL_89:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v54,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v34,
              v58[0]);
            goto LABEL_90;
          }
          v83 = 0;
          v78 = 0;
          hstringHeader.Reserved.Reserved1 = &v63;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v68;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v67;
          v86 = &v83;
          v87 = &v59;
          v88 = &v78;
          v37 = RunInBrokerContext__lambda_6f86910c529d8a093be6f97e57d6a93b_(&hstringHeader);
          v2 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x40D,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v37,
              v58[0]);
            goto LABEL_86;
          }
          if ( v78 )
          {
            v80 = 0;
            v38 = *(_QWORD *)v58;
            v39 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v58 + 72LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
            v40 = v39(v38, v78, &v80);
            v2 = v40;
            if ( v40 < 0 )
            {
              v53 = 1044;
LABEL_84:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v53,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
                (const char *)(unsigned int)v40,
                v58[0]);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
LABEL_86:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
LABEL_90:
              WindowsDeleteString(v67);
              v67 = 0;
              WindowsDeleteString(v68);
              v68 = 0;
LABEL_92:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
              goto LABEL_105;
            }
            v40 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, v80);
            v2 = v40;
            if ( v40 < 0 )
            {
              v53 = 1045;
              goto LABEL_84;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
          WindowsDeleteString(v67);
          v67 = 0;
          WindowsDeleteString(v68);
          v68 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
        }
        else if ( v76 == 3 && v77 )
        {
          v69 = 0;
          WindowsDeleteString(0);
          v69 = 0;
          v41 = Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetOneSyncAccountProperty(
                  v66,
                  L"ActiveSync_UserName",
                  &v69);
          v2 = v41;
          if ( v41 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x420,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v41,
              v58[0]);
          }
          else
          {
            for ( k = 0; ; ++k )
            {
              if ( k >= v77 )
                goto LABEL_80;
              v74 = 0;
              v43 = v65;
              v44 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
              v45 = v44(v43, k, &v74);
              v2 = v45;
              if ( v45 < 0 )
                break;
              v71 = 0;
              v46 = v74;
              v47 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v74 + 56LL);
              WindowsDeleteString(0);
              v71 = 0;
              v48 = v47(v46, &v71);
              v2 = v48;
              if ( v48 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x428,
                  (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
                  (const char *)(unsigned int)v48,
                  v58[0]);
LABEL_97:
                WindowsDeleteString(v71);
                v71 = 0;
                goto LABEL_99;
              }
              if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                    (Microsoft::WRL::Wrappers::Details *)v69,
                                    v71,
                                    v49) )
              {
                v81 = 0;
                v50 = *(_QWORD *)v58;
                v51 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v58 + 72LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
                v52 = v51(v50, v74, &v81);
                v2 = v52;
                if ( v52 < 0 )
                {
                  v55 = 1069;
                }
                else
                {
                  v52 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, v81);
                  v2 = v52;
                  if ( v52 >= 0 )
                  {
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
                    WindowsDeleteString(v71);
                    v71 = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
LABEL_80:
                    WindowsDeleteString(v69);
                    goto LABEL_81;
                  }
                  v55 = 1070;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v55,
                  (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
                  (const char *)(unsigned int)v52,
                  v58[0]);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
                goto LABEL_97;
              }
              WindowsDeleteString(v71);
              v71 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x425,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
              (const char *)(unsigned int)v45,
              v58[0]);
LABEL_99:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
          }
          WindowsDeleteString(v69);
          v69 = 0;
LABEL_105:
          WindowsDeleteString(v59);
          v59 = 0;
LABEL_107:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
          goto LABEL_48;
        }
LABEL_81:
        WindowsDeleteString(v59);
        v59 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v58);
    }
    v2 = 0;
    goto LABEL_110;
  }
  v2 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x393,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
    (const char *)0x80070057LL,
    v58[0]);
  return v2;
}

```

## disassembly

```asm
0x18005f214  mov     [rsp-8+arg_8], rbx
0x18005f219  mov     [rsp-8+arg_10], rsi
0x18005f21e  push    rbp
0x18005f21f  push    rdi
0x18005f220  push    r12
0x18005f222  push    r14
0x18005f224  push    r15
0x18005f226  lea     rbp, [rsp-30h]
0x18005f22b  sub     rsp, 130h
0x18005f232  mov     rax, cs:__security_cookie
0x18005f239  xor     rax, rsp
0x18005f23c  mov     [rbp+50h+var_30], rax
0x18005f240  mov     r14, rcx
0x18005f243  xor     r12d, r12d
0x18005f246  test    rcx, rcx
0x18005f249  jnz     short loc_18005F26D
0x18005f24b  mov     rcx, [rbp+58h]; this
0x18005f24f  mov     ebx, 80070057h
0x18005f254  mov     r9d, ebx; char *
0x18005f257  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f25e  mov     edx, 393h; void *
0x18005f263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f268  jmp     loc_18005FCA3
0x18005f26d  mov     [rbp+50h+var_68], r12
0x18005f271  lea     rcx, [rbp+50h+var_68]
0x18005f275  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f27a  lea     rcx, [rbp+50h+var_68]
0x18005f27e  call    ?s_GetOneSyncAccounts@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAPEAU?$IVector@PEAVAccount@Sync@Experiences@PhoneInternal@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetOneSyncAccounts(Windows::Foundation::Collections::IVector<PhoneInternal::Experiences::Sync::Account *> * *)
0x18005f283  mov     ebx, eax
0x18005f285  test    eax, eax
0x18005f287  jns     short loc_18005F2A6
0x18005f289  mov     rcx, [rbp+58h]; this
0x18005f28d  mov     r9d, eax; char *
0x18005f290  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f297  mov     edx, 397h; void *
0x18005f29c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f2a1  jmp     loc_18005FC9A
0x18005f2a6  mov     [rbp+50h+var_A8], r12d
0x18005f2aa  mov     rcx, [rbp+50h+var_68]
0x18005f2ae  mov     rax, [rcx]
0x18005f2b1  lea     rdx, [rbp+50h+var_A8]
0x18005f2b5  mov     rax, [rax+38h]
0x18005f2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2be  cmp     [rbp+50h+var_A8], r12d
0x18005f2c2  jz      loc_18005FC97
0x18005f2c8  mov     qword ptr [rsp+150h+var_130], r12; int
0x18005f2cd  mov     [rbp+50h+var_48], r12
0x18005f2d1  mov     r9d, 36h ; '6'; unsigned int
0x18005f2d7  lea     r8d, [r9+1]; unsigned int
0x18005f2db  lea     rdx, ?RuntimeClass_Windows_Internal_UI_ApplicationSettings_WebAccountData@@3QBGB; "Windows.Internal.UI.ApplicationSettings"...
0x18005f2e2  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x18005f2e6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005f2eb  lea     rdx, [rsp+150h+var_130]
0x18005f2f0  mov     rcx, [rbp+50h+var_48]
0x18005f2f4  call    ??$GetActivationFactory@V?$ComPtr@UIWebAccountDataFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAccountDataFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>)
0x18005f2f9  mov     ebx, eax
0x18005f2fb  test    eax, eax
0x18005f2fd  jns     short loc_18005F327
0x18005f2ff  mov     rcx, [rbp+58h]; this
0x18005f303  mov     r9d, eax; char *
0x18005f306  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f30d  mov     edx, 3A2h; void *
0x18005f312  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f317  nop
0x18005f318  lea     rcx, [rsp+150h+var_130]
0x18005f31d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f322  jmp     loc_18005FC9A
0x18005f327  mov     [rsp+150h+var_120], r12
0x18005f32c  mov     [rbp+50h+var_48], r12
0x18005f330  mov     r9d, 2Eh ; '.'; unsigned int
0x18005f336  lea     r8d, [r9+1]; unsigned int
0x18005f33a  lea     rdx, ?RuntimeClass_PhoneInternal_Experiences_Sync_AccountsManager@@3QBGB; "PhoneInternal.Experiences.Sync.Accounts"...
0x18005f341  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x18005f345  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005f34a  lea     rdx, [rsp+150h+var_120]
0x18005f34f  mov     rcx, [rbp+50h+var_48]
0x18005f353  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsManagerStatics@Sync@Experiences@PhoneInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsManagerStatics@Sync@Experiences@PhoneInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<PhoneInternal::Experiences::Sync::IAccountsManagerStatics>>)
0x18005f358  mov     ebx, eax
0x18005f35a  test    eax, eax
0x18005f35c  jns     short loc_18005F383
0x18005f35e  mov     rcx, [rbp+58h]; this
0x18005f362  mov     r9d, eax; char *
0x18005f365  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f36c  mov     edx, 3A7h; void *
0x18005f371  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f376  nop
0x18005f377  lea     rcx, [rsp+150h+var_120]
0x18005f37c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f381  jmp     short loc_18005F318
0x18005f383  mov     [rsp+150h+var_108], r12
0x18005f388  mov     [rbp+50h+var_48], r12
0x18005f38c  mov     r9d, 45h ; 'E'; unsigned int
0x18005f392  lea     r8d, [r9+1]; unsigned int
0x18005f396  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18005f39d  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x18005f3a1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005f3a6  lea     rdx, [rsp+150h+var_108]
0x18005f3ab  mov     rcx, [rbp+50h+var_48]
0x18005f3af  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x18005f3b4  mov     ebx, eax
0x18005f3b6  test    eax, eax
0x18005f3b8  jns     short loc_18005F3DF
0x18005f3ba  mov     rcx, [rbp+58h]; this
0x18005f3be  mov     r9d, eax; char *
0x18005f3c1  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f3c8  mov     edx, 3ACh; void *
0x18005f3cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f3d2  nop
0x18005f3d3  lea     rcx, [rsp+150h+var_108]
0x18005f3d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f3dd  jmp     short loc_18005F377
0x18005f3df  mov     [rsp+150h+var_110], r12
0x18005f3e4  lea     rcx, [rsp+150h+var_110]
0x18005f3e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f3ee  lea     rcx, [rsp+150h+var_110]
0x18005f3f3  call    ?s_GetAllWamAccounts@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetAllWamAccounts(Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *)
0x18005f3f8  mov     ebx, eax
0x18005f3fa  test    eax, eax
0x18005f3fc  jns     short loc_18005F423
0x18005f3fe  mov     rcx, [rbp+58h]; this
0x18005f402  mov     r9d, eax; char *
0x18005f405  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f40c  mov     edx, 3AFh; void *
0x18005f411  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f416  nop
0x18005f417  lea     rcx, [rsp+150h+var_110]
0x18005f41c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f421  jmp     short loc_18005F3D3
0x18005f423  mov     [rsp+150h+var_118], r12
0x18005f428  lea     rcx, [rsp+150h+var_118]
0x18005f42d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f432  lea     rdx, [rsp+150h+var_118]
0x18005f437  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$Vector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@U?$DefaultVectorOptions@PEAVWebAccount@Credentials@Security@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@U?$DefaultVectorOptions@PEAVWebAccount@Credentials@Security@Windows@@@6784@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Credentials::WebAccount *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Credentials::WebAccount *>> * *)
0x18005f43c  mov     ebx, eax
0x18005f43e  test    eax, eax
0x18005f440  jns     short loc_18005F467
0x18005f442  mov     edx, 3B2h; void *
0x18005f447  mov     rcx, [rbp+58h]; this
0x18005f44b  mov     r9d, eax; char *
0x18005f44e  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f45a  nop
0x18005f45b  lea     rcx, [rsp+150h+var_118]
0x18005f460  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f465  jmp     short loc_18005F417
0x18005f467  mov     r8, [rsp+150h+var_118]
0x18005f46c  mov     rdx, [rsp+150h+var_110]
0x18005f471  mov     ecx, 5
0x18005f476  call    ?s_GetProviderSpecificWamAccounts@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJW4PartnershipType@2Experiences@PhoneInternal@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAU?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetProviderSpecificWamAccounts(PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *> *)
0x18005f47b  mov     ebx, eax
0x18005f47d  test    eax, eax
0x18005f47f  jns     short loc_18005F488
0x18005f481  mov     edx, 3B4h
0x18005f486  jmp     short loc_18005F447
0x18005f488  mov     [rbp+50h+var_78], r12d
0x18005f48c  mov     rcx, [rsp+150h+var_118]
0x18005f491  mov     rax, [rcx]
0x18005f494  lea     rdx, [rbp+50h+var_78]
0x18005f498  mov     rax, [rax+38h]
0x18005f49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4a1  mov     ebx, eax
0x18005f4a3  test    eax, eax
0x18005f4a5  jns     short loc_18005F4AE
0x18005f4a7  mov     edx, 3B7h
0x18005f4ac  jmp     short loc_18005F447
0x18005f4ae  mov     esi, r12d
0x18005f4b1  cmp     esi, [rbp+50h+var_78]
0x18005f4b4  jnb     loc_18005F64A
0x18005f4ba  mov     [rbp+50h+var_C0], r12
0x18005f4be  mov     rdi, [rsp+150h+var_118]
0x18005f4c3  mov     rax, [rdi]
0x18005f4c6  mov     rbx, [rax+30h]
0x18005f4ca  lea     rcx, [rbp+50h+var_C0]
0x18005f4ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f4d3  lea     r8, [rbp+50h+var_C0]
0x18005f4d7  mov     edx, esi
0x18005f4d9  mov     rcx, rdi
0x18005f4dc  mov     rax, rbx
0x18005f4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f4e4  mov     ebx, eax
0x18005f4e6  test    eax, eax
0x18005f4e8  js      loc_18005F623
0x18005f4ee  mov     [rbp+50h+string], r12
0x18005f4f2  mov     rdi, [rbp+50h+var_C0]
0x18005f4f6  mov     rax, [rdi]
0x18005f4f9  mov     rbx, [rax+38h]
0x18005f4fd  xor     ecx, ecx; string
0x18005f4ff  call    cs:__imp_WindowsDeleteString
0x18005f505  mov     [rbp+50h+string], r12
0x18005f509  lea     rdx, [rbp+50h+string]
0x18005f50d  mov     rcx, rdi
0x18005f510  mov     rax, rbx
0x18005f513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f518  mov     ebx, eax
0x18005f51a  test    eax, eax
0x18005f51c  js      loc_18005F5FA
0x18005f522  mov     [rsp+150h+var_100], r12b
0x18005f527  mov     rcx, [rsp+150h+var_120]
0x18005f52c  mov     rax, [rcx]
0x18005f52f  lea     r8, [rsp+150h+var_100]
0x18005f534  mov     rdx, [rbp+50h+string]
0x18005f538  mov     rax, [rax+80h]
0x18005f53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f544  mov     ebx, eax
0x18005f546  test    eax, eax
0x18005f548  js      loc_18005F5F3
0x18005f54e  cmp     [rsp+150h+var_100], r12b
0x18005f553  jz      short loc_18005F5AA
0x18005f555  mov     [rbp+50h+var_90], r12
0x18005f559  mov     rdi, qword ptr [rsp+150h+var_130]
0x18005f55e  mov     rax, [rdi]
0x18005f561  mov     rbx, [rax+48h]
0x18005f565  lea     rcx, [rbp+50h+var_90]
0x18005f569  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f56e  lea     r8, [rbp+50h+var_90]
0x18005f572  mov     rdx, [rbp+50h+var_C0]
0x18005f576  mov     rcx, rdi
0x18005f579  mov     rax, rbx
0x18005f57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f581  mov     ebx, eax
0x18005f583  test    eax, eax
0x18005f585  js      short loc_18005F5CF
0x18005f587  mov     rax, [r14]
0x18005f58a  mov     rdx, [rbp+50h+var_90]
0x18005f58e  mov     rcx, r14
0x18005f591  mov     rax, [rax+68h]
0x18005f595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f59a  mov     ebx, eax
0x18005f59c  test    eax, eax
0x18005f59e  js      short loc_18005F5C8
0x18005f5a0  lea     rcx, [rbp+50h+var_90]
0x18005f5a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f5a9  nop
0x18005f5aa  mov     rcx, [rbp+50h+string]; string
0x18005f5ae  call    cs:__imp_WindowsDeleteString
0x18005f5b4  mov     [rbp+50h+string], r12
0x18005f5b8  lea     rcx, [rbp+50h+var_C0]
0x18005f5bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f5c1  inc     esi
0x18005f5c3  jmp     loc_18005F4B1
0x18005f5c8  mov     edx, 3C8h
0x18005f5cd  jmp     short loc_18005F5D4
0x18005f5cf  mov     edx, 3C7h; void *
0x18005f5d4  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f5db  mov     r9d, eax; char *
0x18005f5de  mov     rcx, [rbp+58h]; this
0x18005f5e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f5e7  nop
0x18005f5e8  lea     rcx, [rbp+50h+var_90]
0x18005f5ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f5f1  jmp     short loc_18005F613
0x18005f5f3  mov     edx, 3C2h
0x18005f5f8  jmp     short loc_18005F5FF
0x18005f5fa  mov     edx, 3BFh; void *
0x18005f5ff  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f606  mov     r9d, eax; char *
0x18005f609  mov     rcx, [rbp+58h]; this
0x18005f60d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f612  nop
0x18005f613  mov     rcx, [rbp+50h+string]; string
0x18005f617  call    cs:__imp_WindowsDeleteString
0x18005f61d  mov     [rbp+50h+string], r12
0x18005f621  jmp     short loc_18005F63C
0x18005f623  mov     rcx, [rbp+58h]; this
0x18005f627  mov     r9d, eax; char *
0x18005f62a  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f631  mov     edx, 3BCh; void *
0x18005f636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f63b  nop
0x18005f63c  lea     rcx, [rbp+50h+var_C0]
0x18005f640  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f645  jmp     loc_18005F45B
0x18005f64a  mov     [rsp+150h+var_F8], r12
0x18005f64f  lea     rcx, [rsp+150h+var_F8]
0x18005f654  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f659  lea     rdx, [rsp+150h+var_F8]
0x18005f65e  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$Vector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@U?$DefaultVectorOptions@PEAVWebAccount@Credentials@Security@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@U?$DefaultVectorOptions@PEAVWebAccount@Credentials@Security@Windows@@@6784@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Credentials::WebAccount *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Credentials::WebAccount *>> * *)
0x18005f663  mov     ebx, eax
0x18005f665  test    eax, eax
0x18005f667  jns     short loc_18005F691
0x18005f669  mov     edx, 3CDh; void *
0x18005f66e  mov     rcx, [rbp+58h]; this
0x18005f672  mov     r9d, eax; char *
0x18005f675  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f67c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f681  nop
0x18005f682  lea     rcx, [rsp+150h+var_F8]
0x18005f687  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f68c  jmp     loc_18005F45B
0x18005f691  mov     r8, [rsp+150h+var_F8]
0x18005f696  mov     rdx, [rsp+150h+var_110]
0x18005f69b  mov     ecx, 3
0x18005f6a0  call    ?s_GetProviderSpecificWamAccounts@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJW4PartnershipType@2Experiences@PhoneInternal@@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAU?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::ApplicationModel::Sync::AddOperation::s_GetProviderSpecificWamAccounts(PhoneInternal::Experiences::Sync::PartnershipType,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *> *)
0x18005f6a5  mov     ebx, eax
0x18005f6a7  test    eax, eax
0x18005f6a9  jns     short loc_18005F6B2
0x18005f6ab  mov     edx, 3CFh
0x18005f6b0  jmp     short loc_18005F66E
0x18005f6b2  mov     [rbp+50h+var_A0], r12d
0x18005f6b6  mov     rcx, [rsp+150h+var_F8]
  ... truncated ...
```
