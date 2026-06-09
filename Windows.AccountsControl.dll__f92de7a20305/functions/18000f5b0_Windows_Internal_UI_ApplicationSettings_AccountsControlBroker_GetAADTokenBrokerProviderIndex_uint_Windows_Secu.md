# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetAADTokenBrokerProviderIndex(uint *,Windows::Security::Credentials::IWebAccountProvider * *)

- ea: `0x18000f5b0`
- end: `0x18000fbf9`
- name: `?GetAADTokenBrokerProviderIndex@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAIPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z`
- size: `1609`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, unsigned int *, struct Windows::Security::Credentials::IWebAccountProvider **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013210`

## callees

- `0x180006eac`
- `0x180008e2c`
- `0x18000aa78`
- `0x18000c58c`
- `0x18000e87c`
- `0x18000f5b0`
- `0x18000fc40`
- `0x180010594`
- `0x180011c24`
- `0x180011ffc`
- `0x18001667c`
- `0x180016e40`
- `0x1800171ac`
- `0x180017378`
- `0x180069730`
- `0x18006c010`

## string_xrefs

- `0x18000f698`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000f730`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fa76`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000faa3`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000facd`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fafc`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fb29`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fb53`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000fb80`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000f82a`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18000f5f1`: `TokenBrokerAccountCommandDispatchActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetAADTokenBrokerProviderIndex(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        unsigned int *a2,
        struct Windows::Security::Credentials::IWebAccountProvider **a3)
{
  unsigned int v5; // esi
  __int64 v6; // rax
  int FilteredTokenBrokerAccounts; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  _QWORD *v10; // r12
  __int64 v11; // rcx
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v12; // rcx
  int WebAccountProvider; // eax
  unsigned int i; // r15d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, struct Windows::Security::Credentials::IWebAccount **); // rbx
  int v20; // eax
  struct Windows::Security::Credentials::IWebAccount *v21; // rdi
  __int64 (__fastcall *v22)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 *); // rbx
  int v33; // eax
  struct Windows::Security::Credentials::IWebAccountProvider *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  int v40; // [rsp+20h] [rbp-E0h]
  char v41; // [rsp+30h] [rbp-D0h] BYREF
  char v42[7]; // [rsp+31h] [rbp-CFh] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v43; // [rsp+38h] [rbp-C8h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v44; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v51; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v52; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v53; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider **v55; // [rsp+90h] [rbp-70h]
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  __int64 v57; // [rsp+B0h] [rbp-50h]
  _QWORD v58[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v55 = a3;
  v5 = 0;
  *a2 = 0;
  *a3 = 0;
  wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v58);
  v58[0] = &AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::`vftable';
  v6 = *((_QWORD *)this + 124) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v6 )
    v6 = *((_QWORD *)this + 125) - *(_QWORD *)GUID_NULL.Data4;
  if ( v6 )
    wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v58,
      (char *)this + 992);
  AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::StartActivity((AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity *)v58);
  v54 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  FilteredTokenBrokerAccounts = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetFilteredTokenBrokerAccounts(
                                  this,
                                  *((_QWORD *)this + 78),
                                  &v54);
  v8 = FilteredTokenBrokerAccounts;
  if ( FilteredTokenBrokerAccounts < 0 )
  {
    v9 = 934;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)FilteredTokenBrokerAccounts,
      v40);
    goto LABEL_60;
  }
  v51 = 0;
  FilteredTokenBrokerAccounts = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 78) + 144LL))(
                                  *((_QWORD *)this + 78),
                                  &v51);
  v8 = FilteredTokenBrokerAccounts;
  if ( FilteredTokenBrokerAccounts < 0 )
  {
    v9 = 937;
    goto LABEL_9;
  }
  v10 = (_QWORD *)((char *)this + 648);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 648);
  FilteredTokenBrokerAccounts = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetInternalAccountDataCollectionForTokenBrokerAccounts(
                                  v11,
                                  v51,
                                  v54,
                                  (_QWORD *)this + 81);
  v8 = FilteredTokenBrokerAccounts;
  if ( FilteredTokenBrokerAccounts < 0 )
  {
    v9 = 938;
    goto LABEL_9;
  }
  v52 = 0;
  FilteredTokenBrokerAccounts = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v10 + 56LL))(*v10, &v52);
  v8 = FilteredTokenBrokerAccounts;
  if ( FilteredTokenBrokerAccounts < 0 )
  {
    v9 = 941;
    goto LABEL_9;
  }
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  WebAccountProvider = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(
                         v12,
                         1u,
                         &v43);
  v8 = WebAccountProvider;
  if ( WebAccountProvider >= 0 )
  {
    for ( i = 0; i < v52; ++i )
    {
      v46 = 0;
      v15 = *v10;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*v10 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v17 = v16(v15, i, &v46);
      v8 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B5,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v17,
          v40);
        goto LABEL_58;
      }
      v45 = 0;
      v18 = v46;
      v19 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v46 + 96LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v20 = v19(v18, &v45);
      v8 = v20;
      if ( v20 < 0 )
      {
        v38 = 952;
        goto LABEL_55;
      }
      v20 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::SetAppSpecificAccountIdToIDP(
              (Microsoft::WRL::Wrappers::Details **)this,
              v45);
      v8 = v20;
      if ( v20 < 0 )
      {
        v38 = 955;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v20,
          v40);
        goto LABEL_56;
      }
      v44 = 0;
      v21 = v45;
      v22 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v45 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      v23 = v22(v21, &v44);
      v8 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3BF,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v23,
          v40);
        goto LABEL_52;
      }
      v47 = 0;
      v57 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
        0x41u,
        0x40u);
      v24 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
              v57,
              &v47);
      v8 = v24;
      if ( v24 < 0 )
      {
        v37 = 962;
        goto LABEL_49;
      }
      v41 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Security::Credentials::IWebAccountProvider *, char *))(*(_QWORD *)v47 + 344LL))(
              v47,
              v44,
              v43,
              &v41);
      v8 = v24;
      if ( v24 < 0 )
      {
        v37 = 965;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v24,
          v40);
        goto LABEL_50;
      }
      if ( v41 )
      {
        v48 = 0;
        v25 = *((_QWORD *)this + 78);
        v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        v27 = v26(v25, &v48);
        v8 = v27;
        if ( v27 < 0 )
        {
          v36 = 971;
        }
        else
        {
          v53 = 0;
          v27 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 56LL))(v48, &v53);
          v8 = v27;
          if ( v27 >= 0 )
          {
            v49 = 0;
            while ( 1 )
            {
              if ( v5 >= v53 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                v5 = 0;
                goto LABEL_36;
              }
              v28 = v48;
              v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
              v30 = v29(v28, v5, &v49);
              v8 = v30;
              if ( v30 < 0 )
                break;
              v50 = 0;
              v31 = v49;
              v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 80LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
              v33 = v32(v31, &v50);
              v8 = v33;
              if ( v33 < 0 )
              {
                v35 = 983;
                goto LABEL_40;
              }
              v42[0] = 0;
              v33 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Security::Credentials::IWebAccountProvider *, char *))(*(_QWORD *)v47 + 344LL))(
                      v47,
                      v50,
                      v44,
                      v42);
              v8 = v33;
              if ( v33 < 0 )
              {
                v35 = 986;
LABEL_40:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v35,
                  (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
                  (const char *)(unsigned int)v33,
                  v40);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                goto LABEL_42;
              }
              if ( v42[0] )
              {
                *a2 = v5;
                v34 = v44;
                v44 = 0;
                *v55 = v34;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
                v8 = 0;
                goto LABEL_60;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
              ++v5;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3D4,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
              (const char *)(unsigned int)v30,
              v40);
LABEL_42:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
LABEL_46:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
LABEL_50:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
LABEL_52:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
LABEL_56:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
LABEL_58:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
            goto LABEL_16;
          }
          v36 = 974;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v27,
          v40);
        goto LABEL_46;
      }
LABEL_36:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    }
    wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v58);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    v8 = -2147023728;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B0,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)WebAccountProvider,
      v40);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  }
LABEL_60:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::~TokenBrokerAccountCommandDispatchActivity((AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity *)v58);
  return v8;
}

```

## disassembly

```asm
0x18000f5b0  mov     [rsp-8+arg_18], rbx
0x18000f5b5  push    rbp
0x18000f5b6  push    rsi
0x18000f5b7  push    rdi
0x18000f5b8  push    r12
0x18000f5ba  push    r13
0x18000f5bc  push    r14
0x18000f5be  push    r15
0x18000f5c0  lea     rbp, [rsp-120h]
0x18000f5c8  sub     rsp, 220h
0x18000f5cf  mov     rax, cs:__security_cookie
0x18000f5d6  xor     rax, rsp
0x18000f5d9  mov     [rbp+150h+var_40], rax
0x18000f5e0  mov     [rbp+150h+var_1C0], r8
0x18000f5e4  mov     r13, rdx
0x18000f5e7  mov     r14, rcx
0x18000f5ea  xor     esi, esi
0x18000f5ec  mov     [rdx], esi
0x18000f5ee  mov     [r8], rsi
0x18000f5f1  lea     rdx, aTokenbrokeracc_0; "TokenBrokerAccountCommandDispatchActivi"...
0x18000f5f8  lea     rcx, [rbp+150h+var_190]; struct wil::details::IFailureCallback *
0x18000f5fc  call    ??0?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f601  lea     rax, ??_7TokenBrokerAccountCommandDispatchActivity@AccountsControlTelemetry@@6B@; const AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::`vftable'
0x18000f608  mov     [rbp+150h+var_190], rax
0x18000f60c  lea     rdx, [r14+3E0h]
0x18000f613  mov     rax, [rdx]
0x18000f616  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000f61d  jnz     short loc_18000F62A
0x18000f61f  mov     rax, [rdx+8]
0x18000f623  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000f62a  test    rax, rax
0x18000f62d  jz      short loc_18000F638
0x18000f62f  lea     rcx, [rbp+150h+var_190]
0x18000f633  call    ?SetRelatedActivityId@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18000f638  lea     rcx, [rbp+150h+var_190]; this
0x18000f63c  call    ?StartActivity@TokenBrokerAccountCommandDispatchActivity@AccountsControlTelemetry@@QEAAXXZ; AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::StartActivity(void)
0x18000f641  mov     [rbp+150h+var_1C8], rsi
0x18000f645  lea     rcx, [rbp+150h+var_1C8]
0x18000f649  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f64e  lea     r8, [rbp+150h+var_1C8]
0x18000f652  mov     rdx, [r14+270h]
0x18000f659  mov     rcx, r14; this
0x18000f65c  call    ?GetFilteredTokenBrokerAccounts@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIAccountsControlData@2345@PEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetFilteredTokenBrokerAccounts(Windows::Internal::UI::ApplicationSettings::IAccountsControlData *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *)
0x18000f661  mov     ebx, eax
0x18000f663  test    eax, eax
0x18000f665  jns     short loc_18000F66E
0x18000f667  mov     edx, 3A6h
0x18000f66c  jmp     short loc_18000F698
0x18000f66e  mov     [rsp+250h+var_1D8], esi
0x18000f672  mov     rcx, [r14+270h]
0x18000f679  mov     rax, [rcx]
0x18000f67c  lea     rdx, [rsp+250h+var_1D8]
0x18000f681  mov     rax, [rax+90h]
0x18000f688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f68d  mov     ebx, eax
0x18000f68f  test    eax, eax
0x18000f691  jns     short loc_18000F6B3
0x18000f693  mov     edx, 3A9h; void *
0x18000f698  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000f69f  mov     r9d, eax; char *
0x18000f6a2  mov     rcx, [rbp+158h]; this
0x18000f6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6ae  jmp     loc_18000FBBA
0x18000f6b3  lea     r12, [r14+288h]
0x18000f6ba  mov     rcx, r12
0x18000f6bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f6c2  mov     r9, r12
0x18000f6c5  mov     r8, [rbp+150h+var_1C8]
0x18000f6c9  mov     edx, [rsp+250h+var_1D8]
0x18000f6cd  call    ?GetInternalAccountDataCollectionForTokenBrokerAccounts@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJIPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAPEAU?$IVectorView@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@785@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetInternalAccountDataCollectionForTokenBrokerAccounts(uint,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::WebAccountData *> * *)
0x18000f6d2  mov     ebx, eax
0x18000f6d4  test    eax, eax
0x18000f6d6  jns     short loc_18000F6DF
0x18000f6d8  mov     edx, 3AAh
0x18000f6dd  jmp     short loc_18000F698
0x18000f6df  mov     [rsp+250h+var_1D4], esi
0x18000f6e3  mov     rcx, [r12]
0x18000f6e7  mov     rax, [rcx]
0x18000f6ea  lea     rdx, [rsp+250h+var_1D4]
0x18000f6ef  mov     rax, [rax+38h]
0x18000f6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6f8  mov     ebx, eax
0x18000f6fa  test    eax, eax
0x18000f6fc  jns     short loc_18000F705
0x18000f6fe  mov     edx, 3ADh
0x18000f703  jmp     short loc_18000F698
0x18000f705  mov     [rsp+250h+var_218], rsi
0x18000f70a  lea     rcx, [rsp+250h+var_218]
0x18000f70f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f714  lea     r8, [rsp+250h+var_218]; struct Windows::Security::Credentials::IWebAccountProvider **
0x18000f719  mov     dl, 1; unsigned __int8
0x18000f71b  call    ?GetWebAccountProvider@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJEPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(uchar,Windows::Security::Credentials::IWebAccountProvider * *)
0x18000f720  mov     ebx, eax
0x18000f722  test    eax, eax
0x18000f724  jns     short loc_18000F751
0x18000f726  mov     rcx, [rbp+158h]; this
0x18000f72d  mov     r9d, eax; char *
0x18000f730  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000f737  mov     edx, 3B0h; void *
0x18000f73c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f741  nop
0x18000f742  lea     rcx, [rsp+250h+var_218]
0x18000f747  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f74c  jmp     loc_18000FBBA
0x18000f751  mov     r15d, esi
0x18000f754  cmp     r15d, [rsp+250h+var_1D4]
0x18000f759  jnb     loc_18000FBA1
0x18000f75f  mov     [rsp+250h+var_200], rsi
0x18000f764  mov     rdi, [r12]
0x18000f768  mov     rax, [rdi]
0x18000f76b  mov     rbx, [rax+30h]
0x18000f76f  lea     rcx, [rsp+250h+var_200]
0x18000f774  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f779  lea     r8, [rsp+250h+var_200]
0x18000f77e  mov     edx, r15d
0x18000f781  mov     rcx, rdi
0x18000f784  mov     rax, rbx
0x18000f787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f78c  mov     ebx, eax
0x18000f78e  test    eax, eax
0x18000f790  js      loc_18000FB76
0x18000f796  mov     [rsp+250h+var_208], rsi
0x18000f79b  mov     rdi, [rsp+250h+var_200]
0x18000f7a0  mov     rax, [rdi]
0x18000f7a3  mov     rbx, [rax+60h]
0x18000f7a7  lea     rcx, [rsp+250h+var_208]
0x18000f7ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f7b1  lea     rdx, [rsp+250h+var_208]
0x18000f7b6  mov     rcx, rdi
0x18000f7b9  mov     rax, rbx
0x18000f7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7c1  mov     ebx, eax
0x18000f7c3  test    eax, eax
0x18000f7c5  js      loc_18000FB4E
0x18000f7cb  mov     rdx, [rsp+250h+var_208]; struct Windows::Security::Credentials::IWebAccount *
0x18000f7d0  mov     rcx, r14; this
0x18000f7d3  call    ?SetAppSpecificAccountIdToIDP@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIWebAccount@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::SetAppSpecificAccountIdToIDP(Windows::Security::Credentials::IWebAccount *)
0x18000f7d8  mov     ebx, eax
0x18000f7da  test    eax, eax
0x18000f7dc  js      loc_18000FB47
0x18000f7e2  mov     [rsp+250h+var_210], rsi
0x18000f7e7  mov     rdi, [rsp+250h+var_208]
0x18000f7ec  mov     rax, [rdi]
0x18000f7ef  mov     rbx, [rax+30h]
0x18000f7f3  lea     rcx, [rsp+250h+var_210]
0x18000f7f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f7fd  lea     rdx, [rsp+250h+var_210]
0x18000f802  mov     rcx, rdi
0x18000f805  mov     rax, rbx
0x18000f808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f80d  mov     ebx, eax
0x18000f80f  test    eax, eax
0x18000f811  js      loc_18000FB1F
0x18000f817  mov     [rsp+250h+var_1F8], rsi
0x18000f81c  mov     [rbp+150h+var_1A0], rsi
0x18000f820  mov     r9d, 40h ; '@'; unsigned int
0x18000f826  lea     r8d, [r9+1]; unsigned int
0x18000f82a  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18000f831  lea     rcx, [rbp+150h+hstringHeader]; hstringHeader
0x18000f835  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000f83a  lea     rdx, [rsp+250h+var_1F8]
0x18000f83f  mov     rcx, [rbp+150h+var_1A0]
0x18000f843  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x18000f848  mov     ebx, eax
0x18000f84a  test    eax, eax
0x18000f84c  js      loc_18000FAF7
0x18000f852  mov     [rsp+250h+var_220], sil
0x18000f857  mov     rcx, [rsp+250h+var_1F8]
0x18000f85c  mov     rax, [rcx]
0x18000f85f  lea     r9, [rsp+250h+var_220]
0x18000f864  mov     r8, [rsp+250h+var_218]
0x18000f869  mov     rdx, [rsp+250h+var_210]
0x18000f86e  mov     rax, [rax+158h]
0x18000f875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87a  mov     ebx, eax
0x18000f87c  test    eax, eax
0x18000f87e  js      loc_18000FAF0
0x18000f884  cmp     [rsp+250h+var_220], sil
0x18000f889  jz      loc_18000F9C4
0x18000f88f  mov     [rsp+250h+var_1F0], rsi
0x18000f894  mov     rdi, [r14+270h]
0x18000f89b  mov     rax, [rdi]
0x18000f89e  mov     rbx, [rax+30h]
0x18000f8a2  lea     rcx, [rsp+250h+var_1F0]
0x18000f8a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f8ac  lea     rdx, [rsp+250h+var_1F0]
0x18000f8b1  mov     rcx, rdi
0x18000f8b4  mov     rax, rbx
0x18000f8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8bc  mov     ebx, eax
0x18000f8be  test    eax, eax
0x18000f8c0  js      loc_18000FAC8
0x18000f8c6  mov     [rbp+150h+var_1D0], esi
0x18000f8c9  mov     rcx, [rsp+250h+var_1F0]
0x18000f8ce  mov     rax, [rcx]
0x18000f8d1  lea     rdx, [rbp+150h+var_1D0]
0x18000f8d5  mov     rax, [rax+38h]
0x18000f8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8de  mov     ebx, eax
0x18000f8e0  test    eax, eax
0x18000f8e2  js      loc_18000FAC1
0x18000f8e8  mov     [rsp+250h+var_1E8], rsi
0x18000f8ed  cmp     esi, [rbp+150h+var_1D0]
0x18000f8f0  jnb     loc_18000F9AD
0x18000f8f6  mov     rdi, [rsp+250h+var_1F0]
0x18000f8fb  mov     rax, [rdi]
0x18000f8fe  mov     rbx, [rax+30h]
0x18000f902  lea     rcx, [rsp+250h+var_1E8]
0x18000f907  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f90c  lea     r8, [rsp+250h+var_1E8]
0x18000f911  mov     edx, esi
0x18000f913  mov     rcx, rdi
0x18000f916  mov     rax, rbx
0x18000f919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f91e  mov     ebx, eax
0x18000f920  test    eax, eax
0x18000f922  js      loc_18000FA99
0x18000f928  mov     [rsp+250h+var_1E0], 0
0x18000f931  mov     rdi, [rsp+250h+var_1E8]
0x18000f936  mov     rax, [rdi]
0x18000f939  mov     rbx, [rax+50h]
0x18000f93d  lea     rcx, [rsp+250h+var_1E0]
0x18000f942  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f947  lea     rdx, [rsp+250h+var_1E0]
0x18000f94c  mov     rcx, rdi
0x18000f94f  mov     rax, rbx
0x18000f952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f957  mov     ebx, eax
0x18000f959  xor     edi, edi
0x18000f95b  test    eax, eax
0x18000f95d  js      loc_18000FA71
0x18000f963  mov     [rsp+250h+var_21F], dil
0x18000f968  mov     rcx, [rsp+250h+var_1F8]
0x18000f96d  mov     rax, [rcx]
0x18000f970  lea     r9, [rsp+250h+var_21F]
0x18000f975  mov     r8, [rsp+250h+var_210]
0x18000f97a  mov     rdx, [rsp+250h+var_1E0]
0x18000f97f  mov     rax, [rax+158h]
0x18000f986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f98b  mov     ebx, eax
0x18000f98d  test    eax, eax
0x18000f98f  js      loc_18000FA6A
0x18000f995  cmp     [rsp+250h+var_21F], dil
0x18000f99a  jnz     short loc_18000F9F7
0x18000f99c  lea     rcx, [rsp+250h+var_1E0]
0x18000f9a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f9a6  inc     esi
0x18000f9a8  jmp     loc_18000F8ED
0x18000f9ad  lea     rcx, [rsp+250h+var_1E8]
0x18000f9b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f9b7  nop
0x18000f9b8  lea     rcx, [rsp+250h+var_1F0]
0x18000f9bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f9c2  xor     esi, esi
0x18000f9c4  lea     rcx, [rsp+250h+var_1F8]
0x18000f9c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f9ce  nop
0x18000f9cf  lea     rcx, [rsp+250h+var_210]
0x18000f9d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f9d9  nop
0x18000f9da  lea     rcx, [rsp+250h+var_208]
0x18000f9df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f9e4  nop
0x18000f9e5  lea     rcx, [rsp+250h+var_200]
0x18000f9ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f9ef  inc     r15d
0x18000f9f2  jmp     loc_18000F754
0x18000f9f7  mov     [r13+0], esi
0x18000f9fb  mov     rax, [rsp+250h+var_210]
0x18000fa00  mov     [rsp+250h+var_210], rdi
0x18000fa05  mov     rcx, [rbp+150h+var_1C0]
0x18000fa09  mov     [rcx], rax
0x18000fa0c  lea     rcx, [rsp+250h+var_1E0]
0x18000fa11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa16  nop
0x18000fa17  lea     rcx, [rsp+250h+var_1E8]
0x18000fa1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa21  nop
0x18000fa22  lea     rcx, [rsp+250h+var_1F0]
0x18000fa27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa2c  nop
0x18000fa2d  lea     rcx, [rsp+250h+var_1F8]
0x18000fa32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa37  nop
0x18000fa38  lea     rcx, [rsp+250h+var_210]
0x18000fa3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa42  nop
0x18000fa43  lea     rcx, [rsp+250h+var_208]
0x18000fa48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa4d  nop
0x18000fa4e  lea     rcx, [rsp+250h+var_200]
0x18000fa53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa58  nop
0x18000fa59  lea     rcx, [rsp+250h+var_218]
0x18000fa5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000fa63  mov     ebx, edi
0x18000fa65  jmp     loc_18000FBBA
0x18000fa6a  mov     edx, 3DAh
0x18000fa6f  jmp     short loc_18000FA76
0x18000fa71  mov     edx, 3D7h; void *
  ... truncated ...
```
