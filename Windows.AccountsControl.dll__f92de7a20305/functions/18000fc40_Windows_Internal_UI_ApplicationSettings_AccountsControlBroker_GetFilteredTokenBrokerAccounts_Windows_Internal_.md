# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetFilteredTokenBrokerAccounts(Windows::Internal::UI::ApplicationSettings::IAccountsControlData *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *)

- ea: `0x18000fc40`
- end: `0x18001039e`
- name: `?GetFilteredTokenBrokerAccounts@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIAccountsControlData@2345@PEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z`
- size: `1886`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f5b0`
- `0x1800137b0`

## callees

- `0x180006eac`
- `0x18000891c`
- `0x180008e2c`
- `0x180009bc4`
- `0x180009df4`
- `0x18000aa04`
- `0x18000e4f0`
- `0x18000e87c`
- `0x18000fc40`
- `0x180011ffc`
- `0x1800120b0`
- `0x18001908c`
- `0x180069730`
- `0x18006c010`

## string_xrefs

- `0x18000fc9c`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fcf0`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fd59`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fdb4`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fe4e`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fecc`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010139`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010166`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800101a2`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001022d`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010253`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010283`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800102a9`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800102cb`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800102f1`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fcc5`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetFilteredTokenBrokerAccounts(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  unsigned int i; // r14d
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **); // rbx
  int v23; // eax
  struct Windows::Security::Credentials::IWebAccount *v24; // rdi
  __int64 (__fastcall *v25)(struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  int v26; // eax
  unsigned int j; // esi
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING_HEADER *); // rbx
  int v33; // eax
  unsigned int k; // esi
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, __int64 *); // rbx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, struct Windows::Security::Credentials::IWebAccount **); // rbx
  int v40; // eax
  __int64 v41; // rax
  int IsAADAccount; // eax
  int v43; // eax
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v44; // rcx
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rdx
  int v50; // [rsp+20h] [rbp-B9h]
  unsigned __int8 v51[8]; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v52; // [rsp+38h] [rbp-A1h] BYREF
  char v53; // [rsp+40h] [rbp-99h] BYREF
  unsigned __int8 v54; // [rsp+41h] [rbp-98h] BYREF
  unsigned __int8 v55[6]; // [rsp+42h] [rbp-97h] BYREF
  __int64 v56; // [rsp+48h] [rbp-91h] BYREF
  __int64 v57; // [rsp+50h] [rbp-89h] BYREF
  __int64 v58; // [rsp+58h] [rbp-81h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v59; // [rsp+60h] [rbp-79h] BYREF
  __int64 v60; // [rsp+68h] [rbp-71h] BYREF
  __int64 v61; // [rsp+70h] [rbp-69h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v62; // [rsp+78h] [rbp-61h] BYREF
  __int64 v63; // [rsp+80h] [rbp-59h] BYREF
  __int64 v64; // [rsp+88h] [rbp-51h] BYREF
  unsigned int v65; // [rsp+90h] [rbp-49h] BYREF
  unsigned int v66; // [rsp+94h] [rbp-45h] BYREF
  unsigned int v67; // [rsp+98h] [rbp-41h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-39h] BYREF
  char v69; // [rsp+A8h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v71; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  *a3 = 0;
  v68 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
         v6,
         &v68);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x443,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v7,
      v50);
    goto LABEL_83;
  }
  v52 = 0;
  v71 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
         v71,
         &v52);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x447,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v9,
      v50);
    goto LABEL_5;
  }
  v57 = 0;
  hstringHeader.Reserved.Reserved1 = &v57;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v52;
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
  v8 = RunInBrokerContext__lambda_09c04f21ecf16a0f216f1d90e9db888b_(&hstringHeader);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x450,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v8,
      v50);
    goto LABEL_10;
  }
  v56 = 0;
  v10 = v57;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v57 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  v12 = v11(v10, &v56);
  v8 = v12;
  if ( v12 < 0 )
  {
    v13 = 1107;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v12,
      v50);
    goto LABEL_14;
  }
  v65 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v56 + 56LL))(v56, &v65);
  v8 = v12;
  if ( v12 < 0 )
  {
    v13 = 1109;
    goto LABEL_13;
  }
  if ( !v65 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v68 + 64LL))(v68, a3);
    v8 = v12;
    if ( v12 < 0 )
    {
      v13 = 1114;
      goto LABEL_13;
    }
LABEL_82:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    v8 = 0;
    goto LABEL_83;
  }
  v58 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  v15 = v14(a2, &v58);
  v8 = v15;
  if ( v15 < 0 )
  {
    v16 = 1120;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v15,
      v50);
    goto LABEL_23;
  }
  v67 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 56LL))(v58, &v67);
  v8 = v15;
  if ( v15 < 0 )
  {
    v16 = 1122;
    goto LABEL_22;
  }
  v60 = 0;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
  v18 = v17(a2, &v60);
  v8 = v18;
  if ( v18 < 0 )
  {
    v19 = 1126;
    goto LABEL_28;
  }
  v66 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v60 + 56LL))(v60, &v66);
  v8 = v18;
  if ( v18 < 0 )
  {
    v19 = 1128;
    goto LABEL_28;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v65 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v68 + 64LL))(v68, a3);
      v8 = v18;
      if ( v18 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        goto LABEL_82;
      }
      v19 = 1225;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v18,
        v50);
      goto LABEL_29;
    }
    v59 = 0;
    v21 = v56;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v56 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    v23 = v22(v21, i, &v59);
    v8 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46F,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v23,
        v50);
      goto LABEL_78;
    }
    v61 = 0;
    v24 = v59;
    v25 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)v59 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    v26 = v25(v24, &v61);
    v8 = v26;
    if ( v26 < 0 )
    {
      v47 = 1139;
      goto LABEL_75;
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= v66 )
        goto LABEL_62;
      v64 = 0;
      v28 = v60;
      v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v60 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      v30 = v29(v28, j, &v64);
      v8 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x47A,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v30,
          v50);
        goto LABEL_73;
      }
      hstringHeader.Reserved.Reserved1 = 0;
      v31 = v64;
      v32 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v64 + 80LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
      v33 = v32(v31, &hstringHeader);
      v8 = v33;
      if ( v33 < 0 )
      {
        v48 = 1149;
        goto LABEL_71;
      }
      v53 = 0;
      v33 = (*(__int64 (__fastcall **)(__int64, PVOID, __int64, char *))(*(_QWORD *)v52 + 344LL))(
              v52,
              hstringHeader.Reserved.Reserved1,
              v61,
              &v53);
      v8 = v33;
      if ( v33 < 0 )
      {
        v48 = 1152;
LABEL_71:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v48,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v33,
          v50);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
LABEL_73:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
        goto LABEL_76;
      }
      if ( v53 )
        break;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    if ( j < v66 )
      break;
LABEL_62:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  }
  for ( k = 0; ; ++k )
  {
    if ( k >= v67 )
      goto LABEL_61;
    v63 = 0;
    v35 = v58;
    v36 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v58 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    v37 = v36(v35, k, &v63);
    v8 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x492,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v37,
        v50);
      goto LABEL_67;
    }
    v62 = 0;
    v38 = v63;
    v39 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v63 + 96LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v40 = v39(v38, &v62);
    v8 = v40;
    if ( v40 < 0 )
    {
      v46 = 1173;
      goto LABEL_65;
    }
    v51[0] = 0;
    v41 = _lambda_ea3c615d7b6ac0412bf00512c875ea32_::_lambda_ea3c615d7b6ac0412bf00512c875ea32_(
            (unsigned int)&v69,
            (unsigned int)&v52,
            (unsigned int)&v62,
            (_DWORD)this,
            (__int64)&v59,
            (__int64)v51);
    v40 = RunInBrokerContext__lambda_90df9b894be69e2445eacee6f6f87d6e_(v41);
    v8 = v40;
    if ( v40 < 0 )
    {
      v46 = 1188;
LABEL_65:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v46,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v40,
        v50);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
LABEL_67:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      goto LABEL_76;
    }
    if ( v51[0] )
      break;
    v54 = 0;
    v55[0] = 0;
    IsAADAccount = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAADAccount(this, v59, &v54);
    if ( IsAADAccount < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4B0,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)IsAADAccount,
        v50);
    v43 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAADAccount(this, v59, v55);
    v44 = retaddr;
    if ( v43 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4B1,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v43,
        v50);
    if ( v54 )
    {
      if ( v55[0] )
      {
        v45 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::CompareAADAccounts(
                v44,
                v59,
                v62,
                (bool *)v51);
        if ( v45 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4B5,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
            (const char *)(unsigned int)v45,
            v50);
      }
    }
    if ( v51[0] )
      break;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  if ( k < v67 )
    goto LABEL_62;
LABEL_61:
  v26 = (*(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount *))(*(_QWORD *)v68 + 104LL))(
          v68,
          v59);
  v8 = v26;
  if ( v26 >= 0 )
    goto LABEL_62;
  v47 = 1222;
LABEL_75:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v47,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)(unsigned int)v26,
    v50);
LABEL_76:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
LABEL_78:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
LABEL_29:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
LABEL_23:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
LABEL_10:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
LABEL_5:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
LABEL_83:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fc40  mov     [rsp-8+arg_18], rbx
0x18000fc45  push    rbp
0x18000fc46  push    rsi
0x18000fc47  push    rdi
0x18000fc48  push    r12
0x18000fc4a  push    r13
0x18000fc4c  push    r14
0x18000fc4e  push    r15
0x18000fc50  lea     rbp, [rsp-27h]
0x18000fc55  sub     rsp, 100h
0x18000fc5c  mov     rax, cs:__security_cookie
0x18000fc63  xor     rax, rsp
0x18000fc66  mov     [rbp+57h+var_40], rax
0x18000fc6a  mov     r15, r8
0x18000fc6d  mov     rsi, rdx
0x18000fc70  mov     r12, rcx
0x18000fc73  xor     r13d, r13d
0x18000fc76  mov     [r8], r13
0x18000fc79  mov     [rbp+57h+var_90], r13
0x18000fc7d  lea     rcx, [rbp+57h+var_90]
0x18000fc81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fc86  lea     rdx, [rbp+57h+var_90]
0x18000fc8a  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0> * *)
0x18000fc8f  mov     ebx, eax
0x18000fc91  test    eax, eax
0x18000fc93  jns     short loc_18000FCB2
0x18000fc95  mov     rcx, [rbp+5Fh]; this
0x18000fc99  mov     r9d, eax; char *
0x18000fc9c  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000fca3  mov     edx, 443h; void *
0x18000fca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fcad  jmp     loc_18001036C
0x18000fcb2  mov     [rsp+130h+var_F8], r13
0x18000fcb7  mov     [rbp+57h+var_48], r13
0x18000fcbb  mov     r9d, 40h ; '@'; unsigned int
0x18000fcc1  lea     r8d, [r9+1]; unsigned int
0x18000fcc5  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18000fccc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000fcd0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000fcd5  lea     rdx, [rsp+130h+var_F8]
0x18000fcda  mov     rcx, [rbp+57h+var_48]
0x18000fcde  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x18000fce3  mov     ebx, eax
0x18000fce5  test    eax, eax
0x18000fce7  jns     short loc_18000FD11
0x18000fce9  mov     rcx, [rbp+5Fh]; this
0x18000fced  mov     r9d, eax; char *
0x18000fcf0  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000fcf7  mov     edx, 447h; void *
0x18000fcfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd01  nop
0x18000fd02  lea     rcx, [rsp+130h+var_F8]
0x18000fd07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fd0c  jmp     loc_18001036C
0x18000fd11  mov     [rsp+130h+var_E0], r13
0x18000fd16  lea     rax, [rsp+130h+var_E0]
0x18000fd1b  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18000fd1f  mov     rcx, [rsp+130h+var_F8]
0x18000fd24  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rcx
0x18000fd28  test    rcx, rcx
0x18000fd2b  jz      short loc_18000FD3A
0x18000fd2d  mov     rax, [rcx]
0x18000fd30  mov     rax, [rax+8]
0x18000fd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd39  nop
0x18000fd3a  lea     rcx, [rbp+57h+hstringHeader]
0x18000fd3e  call    RunInBrokerContext__lambda_09c04f21ecf16a0f216f1d90e9db888b___; RunInBrokerContext__lambda_09c04f21ecf16a0f216f1d90e9db888b_
0x18000fd43  mov     ebx, eax
0x18000fd45  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]
0x18000fd49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fd4e  test    ebx, ebx
0x18000fd50  jns     short loc_18000FD77
0x18000fd52  mov     rcx, [rbp+5Fh]; this
0x18000fd56  mov     r9d, ebx; char *
0x18000fd59  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000fd60  mov     edx, 450h; void *
0x18000fd65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd6a  nop
0x18000fd6b  lea     rcx, [rsp+130h+var_E0]
0x18000fd70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fd75  jmp     short loc_18000FD02
0x18000fd77  mov     [rsp+130h+var_E8], r13
0x18000fd7c  mov     rdi, [rsp+130h+var_E0]
0x18000fd81  mov     rax, [rdi]
0x18000fd84  mov     rbx, [rax+40h]
0x18000fd88  lea     rcx, [rsp+130h+var_E8]
0x18000fd8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fd92  lea     rdx, [rsp+130h+var_E8]
0x18000fd97  mov     rcx, rdi
0x18000fd9a  mov     rax, rbx
0x18000fd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fda2  mov     ebx, eax
0x18000fda4  test    eax, eax
0x18000fda6  jns     short loc_18000FDCD
0x18000fda8  mov     edx, 453h; void *
0x18000fdad  mov     rcx, [rbp+5Fh]; this
0x18000fdb1  mov     r9d, eax; char *
0x18000fdb4  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000fdbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fdc0  nop
0x18000fdc1  lea     rcx, [rsp+130h+var_E8]
0x18000fdc6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fdcb  jmp     short loc_18000FD6B
0x18000fdcd  mov     [rbp+57h+var_A0], r13d
0x18000fdd1  mov     rcx, [rsp+130h+var_E8]
0x18000fdd6  mov     rax, [rcx]
0x18000fdd9  lea     rdx, [rbp+57h+var_A0]
0x18000fddd  mov     rax, [rax+38h]
0x18000fde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fde6  mov     ebx, eax
0x18000fde8  test    eax, eax
0x18000fdea  jns     short loc_18000FDF3
0x18000fdec  mov     edx, 455h
0x18000fdf1  jmp     short loc_18000FDAD
0x18000fdf3  cmp     [rbp+57h+var_A0], r13d
0x18000fdf7  jnz     short loc_18000FE1D
0x18000fdf9  mov     rcx, [rbp+57h+var_90]
0x18000fdfd  mov     rax, [rcx]
0x18000fe00  mov     rdx, r15
0x18000fe03  mov     rax, [rax+40h]
0x18000fe07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe0c  mov     ebx, eax
0x18000fe0e  test    eax, eax
0x18000fe10  jns     loc_180010349
0x18000fe16  mov     edx, 45Ah
0x18000fe1b  jmp     short loc_18000FDAD
0x18000fe1d  mov     [rsp+130h+var_D8], r13
0x18000fe22  mov     rax, [rsi]
0x18000fe25  mov     rbx, [rax+38h]
0x18000fe29  lea     rcx, [rsp+130h+var_D8]
0x18000fe2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fe33  lea     rdx, [rsp+130h+var_D8]
0x18000fe38  mov     rcx, rsi
0x18000fe3b  mov     rax, rbx
0x18000fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe43  mov     ebx, eax
0x18000fe45  test    eax, eax
0x18000fe47  jns     short loc_18000FE71
0x18000fe49  mov     edx, 460h; void *
0x18000fe4e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000fe55  mov     r9d, eax; char *
0x18000fe58  mov     rcx, [rbp+5Fh]; this
0x18000fe5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe61  nop
0x18000fe62  lea     rcx, [rsp+130h+var_D8]
0x18000fe67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fe6c  jmp     loc_18000FDC1
0x18000fe71  mov     [rbp+57h+var_98], r13d
0x18000fe75  mov     rcx, [rsp+130h+var_D8]
0x18000fe7a  mov     rax, [rcx]
0x18000fe7d  lea     rdx, [rbp+57h+var_98]
0x18000fe81  mov     rax, [rax+38h]
0x18000fe85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe8a  mov     ebx, eax
0x18000fe8c  test    eax, eax
0x18000fe8e  jns     short loc_18000FE97
0x18000fe90  mov     edx, 462h
0x18000fe95  jmp     short loc_18000FE4E
0x18000fe97  mov     [rbp+57h+var_C8], r13
0x18000fe9b  mov     rax, [rsi]
0x18000fe9e  mov     rbx, [rax+30h]
0x18000fea2  lea     rcx, [rbp+57h+var_C8]
0x18000fea6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000feab  lea     rdx, [rbp+57h+var_C8]
0x18000feaf  mov     rcx, rsi
0x18000feb2  mov     rax, rbx
0x18000feb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feba  mov     ebx, eax
0x18000febc  test    eax, eax
0x18000febe  jns     short loc_18000FEE7
0x18000fec0  mov     edx, 466h; void *
0x18000fec5  mov     rcx, [rbp+5Fh]; this
0x18000fec9  mov     r9d, eax; char *
0x18000fecc  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000fed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fed8  nop
0x18000fed9  lea     rcx, [rbp+57h+var_C8]
0x18000fedd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fee2  jmp     loc_18000FE62
0x18000fee7  mov     [rbp+57h+var_9C], r13d
0x18000feeb  mov     rcx, [rbp+57h+var_C8]
0x18000feef  mov     rax, [rcx]
0x18000fef2  lea     rdx, [rbp+57h+var_9C]
0x18000fef6  mov     rax, [rax+38h]
0x18000fefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feff  mov     ebx, eax
0x18000ff01  test    eax, eax
0x18000ff03  jns     short loc_18000FF0C
0x18000ff05  mov     edx, 468h
0x18000ff0a  jmp     short loc_18000FEC5
0x18000ff0c  mov     r14d, r13d
0x18000ff0f  cmp     r14d, [rbp+57h+var_A0]
0x18000ff13  jnb     loc_180010311
0x18000ff19  mov     [rbp+57h+var_D0], r13
0x18000ff1d  mov     rdi, [rsp+130h+var_E8]
0x18000ff22  mov     rax, [rdi]
0x18000ff25  mov     rbx, [rax+30h]
0x18000ff29  lea     rcx, [rbp+57h+var_D0]
0x18000ff2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ff32  lea     r8, [rbp+57h+var_D0]
0x18000ff36  mov     edx, r14d
0x18000ff39  mov     rcx, rdi
0x18000ff3c  mov     rax, rbx
0x18000ff3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff44  mov     ebx, eax
0x18000ff46  test    eax, eax
0x18000ff48  js      loc_1800102EA
0x18000ff4e  mov     [rbp+57h+var_C0], r13
0x18000ff52  mov     rdi, [rbp+57h+var_D0]
0x18000ff56  mov     rax, [rdi]
0x18000ff59  mov     rbx, [rax+30h]
0x18000ff5d  lea     rcx, [rbp+57h+var_C0]
0x18000ff61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ff66  lea     rdx, [rbp+57h+var_C0]
0x18000ff6a  mov     rcx, rdi
0x18000ff6d  mov     rax, rbx
0x18000ff70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff75  mov     ebx, eax
0x18000ff77  test    eax, eax
0x18000ff79  js      loc_1800102C6
0x18000ff7f  mov     esi, r13d
0x18000ff82  cmp     esi, [rbp+57h+var_9C]
0x18000ff85  jnb     loc_180010206
0x18000ff8b  mov     [rbp+57h+var_A8], r13
0x18000ff8f  mov     rdi, [rbp+57h+var_C8]
0x18000ff93  mov     rax, [rdi]
0x18000ff96  mov     rbx, [rax+30h]
0x18000ff9a  lea     rcx, [rbp+57h+var_A8]
0x18000ff9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ffa3  lea     r8, [rbp+57h+var_A8]
0x18000ffa7  mov     edx, esi
0x18000ffa9  mov     rcx, rdi
0x18000ffac  mov     rax, rbx
0x18000ffaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb4  mov     ebx, eax
0x18000ffb6  test    eax, eax
0x18000ffb8  js      loc_1800102A2
0x18000ffbe  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x18000ffc2  mov     rdi, [rbp+57h+var_A8]
0x18000ffc6  mov     rax, [rdi]
0x18000ffc9  mov     rbx, [rax+50h]
0x18000ffcd  lea     rcx, [rbp+57h+hstringHeader]
0x18000ffd1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ffd6  lea     rdx, [rbp+57h+hstringHeader]
0x18000ffda  mov     rcx, rdi
0x18000ffdd  mov     rax, rbx
0x18000ffe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe5  mov     ebx, eax
0x18000ffe7  test    eax, eax
0x18000ffe9  js      loc_18001027E
0x18000ffef  mov     [rsp+130h+var_F0], r13b
0x18000fff4  mov     rcx, [rsp+130h+var_F8]
0x18000fff9  mov     rax, [rcx]
0x18000fffc  lea     r9, [rsp+130h+var_F0]
0x180010001  mov     r8, [rbp+57h+var_C0]
0x180010005  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180010009  mov     rax, [rax+158h]
0x180010010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010015  mov     ebx, eax
0x180010017  test    eax, eax
0x180010019  js      loc_180010277
0x18001001f  lea     rcx, [rbp+57h+hstringHeader]
0x180010023  cmp     [rsp+130h+var_F0], r13b
0x180010028  jnz     short loc_180010040
0x18001002a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001002f  nop
0x180010030  lea     rcx, [rbp+57h+var_A8]
0x180010034  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010039  inc     esi
0x18001003b  jmp     loc_18000FF82
0x180010040  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010045  nop
0x180010046  lea     rcx, [rbp+57h+var_A8]
0x18001004a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001004f  cmp     esi, [rbp+57h+var_9C]
0x180010052  jnb     loc_180010206
0x180010058  mov     esi, r13d
0x18001005b  cmp     esi, [rbp+57h+var_98]
0x18001005e  jnb     loc_1800101EC
0x180010064  mov     [rbp+57h+var_B0], r13
0x180010068  mov     rdi, [rsp+130h+var_D8]
0x18001006d  mov     rax, [rdi]
0x180010070  mov     rbx, [rax+30h]
0x180010074  lea     rcx, [rbp+57h+var_B0]
0x180010078  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001007d  lea     r8, [rbp+57h+var_B0]
0x180010081  mov     edx, esi
0x180010083  mov     rcx, rdi
0x180010086  mov     rax, rbx
0x180010089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001008e  mov     ebx, eax
0x180010090  test    eax, eax
0x180010092  js      loc_18001024C
0x180010098  mov     [rbp+57h+var_B8], r13
0x18001009c  mov     rdi, [rbp+57h+var_B0]
0x1800100a0  mov     rax, [rdi]
0x1800100a3  mov     rbx, [rax+60h]
0x1800100a7  lea     rcx, [rbp+57h+var_B8]
0x1800100ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800100b0  lea     rdx, [rbp+57h+var_B8]
  ... truncated ...
```
