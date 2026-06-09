# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetTokenBrokerProviderIndex(uint,uint *,Windows::Security::Credentials::IWebAccountProvider * *)

- ea: `0x180011448`
- end: `0x180011942`
- name: `?GetTokenBrokerProviderIndex@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJIPEAIPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z`
- size: `1274`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, unsigned int, unsigned int *, struct Windows::Security::Credentials::IWebAccountProvider **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013210`

## callees

- `0x180006eac`
- `0x180008e2c`
- `0x18000aa78`
- `0x18000c58c`
- `0x18000e87c`
- `0x180011448`
- `0x180011f64`
- `0x180011ffc`
- `0x18001667c`
- `0x180016e40`
- `0x1800171ac`
- `0x180017378`
- `0x180069730`
- `0x18006c010`

## string_xrefs

- `0x18001155f`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800115ab`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001161b`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001166e`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800116c0`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180011851`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180011892`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800118f6`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180011697`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18001148a`: `TokenBrokerAccountCommandDispatchActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetTokenBrokerProviderIndex(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        unsigned int a2,
        unsigned int *a3,
        struct Windows::Security::Credentials::IWebAccountProvider **a4)
{
  __int64 v8; // rax
  __int64 v9; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, struct Windows::Security::Credentials::IWebAccount **); // rbx
  int v18; // eax
  __int64 v19; // rdx
  struct Windows::Security::Credentials::IWebAccount *v20; // rdi
  __int64 (__fastcall *v21)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  unsigned int i; // esi
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64 *); // rbx
  int v34; // eax
  struct Windows::Security::Credentials::IWebAccountProvider *v35; // rax
  __int64 v37; // rdx
  __int64 v38; // r9
  __int64 v39; // rdx
  int v40; // [rsp+20h] [rbp-E0h]
  _BYTE v41[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v42; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v50; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-60h]
  _QWORD v54[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  *a3 = 0;
  *a4 = 0;
  wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v54);
  v54[0] = &AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::`vftable';
  v8 = *((_QWORD *)this + 124) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v8 )
    v8 = *((_QWORD *)this + 125) - *(_QWORD *)GUID_NULL.Data4;
  if ( v8 )
    wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      v54,
      (char *)this + 992);
  AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::StartActivity((AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity *)v54);
  v51 = *((_QWORD *)this + 81);
  v9 = v51;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v51);
  v50 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 56LL))(v9, &v50);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = (unsigned int)v10;
    v13 = 781;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)v12,
      v40);
    goto LABEL_47;
  }
  if ( a2 >= v50 )
  {
    v11 = -2147483637;
    v12 = 2147483659LL;
    v13 = 782;
    goto LABEL_46;
  }
  v43 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  v15 = v14(v9, a2, &v43);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v15,
      v40);
    goto LABEL_44;
  }
  v42 = 0;
  v16 = v43;
  v17 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v43 + 96LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v18 = v17(v16, &v42);
  v11 = v18;
  if ( v18 < 0 )
  {
    v19 = 788;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v18,
      v40);
    goto LABEL_43;
  }
  v18 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::SetAppSpecificAccountIdToIDP(
          (Microsoft::WRL::Wrappers::Details **)this,
          v42);
  v11 = v18;
  if ( v18 < 0 )
  {
    v19 = 791;
    goto LABEL_12;
  }
  v44 = 0;
  v20 = v42;
  v21 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v42 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v22 = v21(v20, &v44);
  v11 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v22,
      v40);
    goto LABEL_42;
  }
  v45 = 0;
  v23 = *((_QWORD *)this + 78);
  v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  v25 = v24(v23, &v45);
  v11 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v25,
      v40);
    goto LABEL_41;
  }
  v46 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v26 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
          v53,
          &v46);
  v11 = v26;
  if ( v26 < 0 )
  {
    v27 = 802;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v26,
      v40);
    goto LABEL_40;
  }
  v48 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v45 + 56LL))(v45, &v48);
  v11 = v26;
  if ( v26 < 0 )
  {
    v27 = 805;
    goto LABEL_21;
  }
  v47 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v48 )
      goto LABEL_37;
    v29 = v45;
    v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v31 = v30(v29, i, &v47);
    v11 = v31;
    if ( v31 < 0 )
    {
      v38 = (unsigned int)v31;
      v39 = 811;
      goto LABEL_38;
    }
    v49 = 0;
    v32 = v47;
    v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v34 = v33(v32, &v49);
    v11 = v34;
    if ( v34 < 0 )
    {
      v37 = 814;
      goto LABEL_34;
    }
    v41[0] = 0;
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Security::Credentials::IWebAccountProvider *, _BYTE *))(*(_QWORD *)v46 + 344LL))(
            v46,
            v49,
            v44,
            v41);
    v11 = v34;
    if ( v34 < 0 )
    {
      v37 = 817;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v34,
        v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      goto LABEL_39;
    }
    if ( v41[0] )
      break;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  if ( i < v48 )
  {
    *a3 = i;
    v35 = v44;
    v44 = 0;
    *a4 = v35;
    wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v54);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::~TokenBrokerAccountCommandDispatchActivity((AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity *)v54);
    return 0;
  }
LABEL_37:
  v11 = -2147483637;
  v38 = 2147483659LL;
  v39 = 823;
LABEL_38:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v39,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)v38,
    v40);
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
LABEL_40:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_41:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
LABEL_42:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
LABEL_43:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
LABEL_44:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
LABEL_47:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::~TokenBrokerAccountCommandDispatchActivity((AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity *)v54);
  return v11;
}

```

## disassembly

```asm
0x180011448  push    rbp
0x18001144a  push    rbx
0x18001144b  push    rsi
0x18001144c  push    rdi
0x18001144d  push    r12
0x18001144f  push    r13
0x180011451  push    r14
0x180011453  push    r15
0x180011455  lea     rbp, [rsp-118h]
0x18001145d  sub     rsp, 218h
0x180011464  mov     rax, cs:__security_cookie
0x18001146b  xor     rax, rsp
0x18001146e  mov     [rbp+150h+var_50], rax
0x180011475  mov     r12, r9
0x180011478  mov     r15, r8
0x18001147b  mov     r14d, edx
0x18001147e  mov     rsi, rcx
0x180011481  xor     r13d, r13d
0x180011484  mov     [r8], r13d
0x180011487  mov     [r9], r13
0x18001148a  lea     rdx, aTokenbrokeracc_0; "TokenBrokerAccountCommandDispatchActivi"...
0x180011491  lea     rcx, [rbp+150h+var_1A0]; struct wil::details::IFailureCallback *
0x180011495  call    ??0?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001149a  lea     rax, ??_7TokenBrokerAccountCommandDispatchActivity@AccountsControlTelemetry@@6B@; const AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::`vftable'
0x1800114a1  mov     [rbp+150h+var_1A0], rax
0x1800114a5  lea     rdx, [rsi+3E0h]
0x1800114ac  mov     rax, [rdx]
0x1800114af  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800114b6  jnz     short loc_1800114C3
0x1800114b8  mov     rax, [rdx+8]
0x1800114bc  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800114c3  test    rax, rax
0x1800114c6  jz      short loc_1800114D1
0x1800114c8  lea     rcx, [rbp+150h+var_1A0]
0x1800114cc  call    ?SetRelatedActivityId@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x1800114d1  lea     rcx, [rbp+150h+var_1A0]; this
0x1800114d5  call    ?StartActivity@TokenBrokerAccountCommandDispatchActivity@AccountsControlTelemetry@@QEAAXXZ; AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::StartActivity(void)
0x1800114da  mov     rdi, [rsi+288h]
0x1800114e1  mov     [rbp+150h+var_1D0], rdi
0x1800114e5  lea     rcx, [rbp+150h+var_1D0]
0x1800114e9  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800114ee  nop
0x1800114ef  mov     [rsp+250h+var_1D8], r13d
0x1800114f4  mov     rax, [rdi]
0x1800114f7  lea     rdx, [rsp+250h+var_1D8]
0x1800114fc  mov     rcx, rdi
0x1800114ff  mov     rax, [rax+38h]
0x180011503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011508  mov     ebx, eax
0x18001150a  test    eax, eax
0x18001150c  jns     short loc_18001151B
0x18001150e  mov     r9d, eax
0x180011511  mov     edx, 30Dh
0x180011516  jmp     loc_1800118F6
0x18001151b  cmp     r14d, [rsp+250h+var_1D8]
0x180011520  jnb     loc_1800118E9
0x180011526  mov     [rsp+250h+var_210], r13
0x18001152b  mov     rax, [rdi]
0x18001152e  mov     rbx, [rax+30h]
0x180011532  lea     rcx, [rsp+250h+var_210]
0x180011537  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001153c  lea     r8, [rsp+250h+var_210]
0x180011541  mov     edx, r14d
0x180011544  mov     rcx, rdi
0x180011547  mov     rax, rbx
0x18001154a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001154f  mov     ebx, eax
0x180011551  test    eax, eax
0x180011553  jns     short loc_180011575
0x180011555  mov     rcx, [rbp+158h]; this
0x18001155c  mov     r9d, eax; char *
0x18001155f  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180011566  mov     edx, 311h; void *
0x18001156b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011570  jmp     loc_1800118DD
0x180011575  mov     [rsp+250h+var_218], r13
0x18001157a  mov     rdi, [rsp+250h+var_210]
0x18001157f  mov     rax, [rdi]
0x180011582  mov     rbx, [rax+60h]
0x180011586  lea     rcx, [rsp+250h+var_218]
0x18001158b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011590  lea     rdx, [rsp+250h+var_218]
0x180011595  mov     rcx, rdi
0x180011598  mov     rax, rbx
0x18001159b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115a0  mov     ebx, eax
0x1800115a2  test    eax, eax
0x1800115a4  jns     short loc_1800115C6
0x1800115a6  mov     edx, 314h; void *
0x1800115ab  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800115b2  mov     r9d, eax; char *
0x1800115b5  mov     rcx, [rbp+158h]; this
0x1800115bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115c1  jmp     loc_1800118D2
0x1800115c6  mov     rdx, [rsp+250h+var_218]; struct Windows::Security::Credentials::IWebAccount *
0x1800115cb  mov     rcx, rsi; this
0x1800115ce  call    ?SetAppSpecificAccountIdToIDP@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAUIWebAccount@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::SetAppSpecificAccountIdToIDP(Windows::Security::Credentials::IWebAccount *)
0x1800115d3  mov     ebx, eax
0x1800115d5  test    eax, eax
0x1800115d7  jns     short loc_1800115E0
0x1800115d9  mov     edx, 317h
0x1800115de  jmp     short loc_1800115AB
0x1800115e0  mov     [rsp+250h+var_208], r13
0x1800115e5  mov     rdi, [rsp+250h+var_218]
0x1800115ea  mov     rax, [rdi]
0x1800115ed  mov     rbx, [rax+30h]
0x1800115f1  lea     rcx, [rsp+250h+var_208]
0x1800115f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800115fb  lea     rdx, [rsp+250h+var_208]
0x180011600  mov     rcx, rdi
0x180011603  mov     rax, rbx
0x180011606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001160b  mov     ebx, eax
0x18001160d  test    eax, eax
0x18001160f  jns     short loc_180011631
0x180011611  mov     rcx, [rbp+158h]; this
0x180011618  mov     r9d, eax; char *
0x18001161b  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180011622  mov     edx, 31Bh; void *
0x180011627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001162c  jmp     loc_1800118C7
0x180011631  mov     [rsp+250h+var_200], r13
0x180011636  mov     rdi, [rsi+270h]
0x18001163d  mov     rax, [rdi]
0x180011640  mov     rbx, [rax+30h]
0x180011644  lea     rcx, [rsp+250h+var_200]
0x180011649  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001164e  lea     rdx, [rsp+250h+var_200]
0x180011653  mov     rcx, rdi
0x180011656  mov     rax, rbx
0x180011659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001165e  mov     ebx, eax
0x180011660  test    eax, eax
0x180011662  jns     short loc_180011684
0x180011664  mov     rcx, [rbp+158h]; this
0x18001166b  mov     r9d, eax; char *
0x18001166e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180011675  mov     edx, 31Fh; void *
0x18001167a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001167f  jmp     loc_1800118BC
0x180011684  mov     [rsp+250h+var_1F8], r13
0x180011689  mov     [rbp+150h+var_1B0], r13
0x18001168d  mov     r9d, 40h ; '@'; unsigned int
0x180011693  lea     r8d, [r9+1]; unsigned int
0x180011697  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18001169e  lea     rcx, [rbp+150h+hstringHeader]; hstringHeader
0x1800116a2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800116a7  lea     rdx, [rsp+250h+var_1F8]
0x1800116ac  mov     rcx, [rbp+150h+var_1B0]
0x1800116b0  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x1800116b5  mov     ebx, eax
0x1800116b7  test    eax, eax
0x1800116b9  jns     short loc_1800116DB
0x1800116bb  mov     edx, 322h; void *
0x1800116c0  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800116c7  mov     r9d, eax; char *
0x1800116ca  mov     rcx, [rbp+158h]; this
0x1800116d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116d6  jmp     loc_1800118B1
0x1800116db  mov     [rsp+250h+var_1E8], r13d
0x1800116e0  mov     rcx, [rsp+250h+var_200]
0x1800116e5  mov     rax, [rcx]
0x1800116e8  lea     rdx, [rsp+250h+var_1E8]
0x1800116ed  mov     rax, [rax+38h]
0x1800116f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116f6  mov     ebx, eax
0x1800116f8  test    eax, eax
0x1800116fa  jns     short loc_180011703
0x1800116fc  mov     edx, 325h
0x180011701  jmp     short loc_1800116C0
0x180011703  mov     [rsp+250h+var_1F0], r13
0x180011708  mov     esi, r13d
0x18001170b  cmp     esi, [rsp+250h+var_1E8]
0x18001170f  jnb     loc_180011885
0x180011715  mov     rdi, [rsp+250h+var_200]
0x18001171a  mov     rax, [rdi]
0x18001171d  mov     rbx, [rax+30h]
0x180011721  lea     rcx, [rsp+250h+var_1F0]
0x180011726  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001172b  lea     r8, [rsp+250h+var_1F0]
0x180011730  mov     edx, esi
0x180011732  mov     rcx, rdi
0x180011735  mov     rax, rbx
0x180011738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001173d  mov     ebx, eax
0x18001173f  test    eax, eax
0x180011741  js      loc_18001187B
0x180011747  mov     [rsp+250h+var_1E0], r13
0x18001174c  mov     rdi, [rsp+250h+var_1F0]
0x180011751  mov     rax, [rdi]
0x180011754  mov     rbx, [rax+50h]
0x180011758  lea     rcx, [rsp+250h+var_1E0]
0x18001175d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011762  lea     rdx, [rsp+250h+var_1E0]
0x180011767  mov     rcx, rdi
0x18001176a  mov     rax, rbx
0x18001176d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011772  mov     ebx, eax
0x180011774  test    eax, eax
0x180011776  js      loc_180011874
0x18001177c  mov     [rsp+250h+var_220], r13b
0x180011781  mov     rcx, [rsp+250h+var_1F8]
0x180011786  mov     rax, [rcx]
0x180011789  lea     r9, [rsp+250h+var_220]
0x18001178e  mov     r8, [rsp+250h+var_208]
0x180011793  mov     rdx, [rsp+250h+var_1E0]
0x180011798  mov     rax, [rax+158h]
0x18001179f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a4  mov     ebx, eax
0x1800117a6  test    eax, eax
0x1800117a8  js      loc_18001184C
0x1800117ae  lea     rcx, [rsp+250h+var_1E0]
0x1800117b3  cmp     [rsp+250h+var_220], r13b
0x1800117b8  jnz     short loc_1800117C6
0x1800117ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800117bf  inc     esi
0x1800117c1  jmp     loc_18001170B
0x1800117c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800117cb  cmp     esi, [rsp+250h+var_1E8]
0x1800117cf  jnb     loc_180011885
0x1800117d5  mov     [r15], esi
0x1800117d8  mov     rax, [rsp+250h+var_208]
0x1800117dd  mov     [rsp+250h+var_208], r13
0x1800117e2  mov     [r12], rax
0x1800117e6  lea     rcx, [rbp+150h+var_1A0]
0x1800117ea  call    ?Stop@?$ActivityBase@VAccountsControlTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AccountsControlTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800117ef  nop
0x1800117f0  lea     rcx, [rsp+250h+var_1F0]
0x1800117f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800117fa  nop
0x1800117fb  lea     rcx, [rsp+250h+var_1F8]
0x180011800  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011805  nop
0x180011806  lea     rcx, [rsp+250h+var_200]
0x18001180b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011810  nop
0x180011811  lea     rcx, [rsp+250h+var_208]
0x180011816  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001181b  nop
0x18001181c  lea     rcx, [rsp+250h+var_218]
0x180011821  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011826  nop
0x180011827  lea     rcx, [rsp+250h+var_210]
0x18001182c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011831  nop
0x180011832  lea     rcx, [rbp+150h+var_1D0]
0x180011836  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001183b  nop
0x18001183c  lea     rcx, [rbp+150h+var_1A0]; this
0x180011840  call    ??1TokenBrokerAccountCommandDispatchActivity@AccountsControlTelemetry@@QEAA@XZ; AccountsControlTelemetry::TokenBrokerAccountCommandDispatchActivity::~TokenBrokerAccountCommandDispatchActivity(void)
0x180011845  xor     eax, eax
0x180011847  jmp     loc_18001191F
0x18001184c  mov     edx, 331h; void *
0x180011851  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180011858  mov     r9d, eax; char *
0x18001185b  mov     rcx, [rbp+158h]; this
0x180011862  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011867  nop
0x180011868  lea     rcx, [rsp+250h+var_1E0]
0x18001186d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011872  jmp     short loc_1800118A6
0x180011874  mov     edx, 32Eh
0x180011879  jmp     short loc_180011851
0x18001187b  mov     r9d, eax
0x18001187e  mov     edx, 32Bh
0x180011883  jmp     short loc_180011892
0x180011885  mov     ebx, 8000000Bh
0x18001188a  mov     r9d, ebx; char *
0x18001188d  mov     edx, 337h; void *
0x180011892  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180011899  mov     rcx, [rbp+158h]; this
0x1800118a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118a5  nop
0x1800118a6  lea     rcx, [rsp+250h+var_1F0]
0x1800118ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800118b0  nop
0x1800118b1  lea     rcx, [rsp+250h+var_1F8]
0x1800118b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800118bb  nop
0x1800118bc  lea     rcx, [rsp+250h+var_200]
0x1800118c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800118c6  nop
0x1800118c7  lea     rcx, [rsp+250h+var_208]
0x1800118cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800118d1  nop
0x1800118d2  lea     rcx, [rsp+250h+var_218]
0x1800118d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800118dc  nop
0x1800118dd  lea     rcx, [rsp+250h+var_210]
0x1800118e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800118e7  jmp     short loc_18001190A
0x1800118e9  mov     ebx, 8000000Bh
0x1800118ee  mov     r9d, ebx; char *
0x1800118f1  mov     edx, 30Eh; void *
0x1800118f6  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800118fd  mov     rcx, [rbp+158h]; this
0x180011904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011909  nop
0x18001190a  lea     rcx, [rbp+150h+var_1D0]
0x18001190e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
