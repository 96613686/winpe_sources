# ShieldProvider::AccountProtectionShield::IsAccountVerified(int *,int)

- ea: `0x1800c7630`
- end: `0x1800c7d7f`
- name: `?IsAccountVerified@AccountProtectionShield@ShieldProvider@@AEAAJPEAHH@Z`
- size: `1871`
- prototype: `int(ShieldProvider::AccountProtectionShield *__hidden this, int *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c8b44`

## callees

- `0x180004710`
- `0x18000a7ec`
- `0x18000d7fc`
- `0x18000f4e0`
- `0x18001c9f8`
- `0x18006e0a4`
- `0x1800c4690`
- `0x1800c482c`
- `0x1800c4d40`
- `0x1800c7630`
- `0x1800c9d64`
- `0x1800c9f14`
- `0x1800e7010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x1800c7712`
- `ole32!CoSetProxyBlanket` at `0x1800c7712`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c76b3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c7910`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c7a3f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c76b3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c7910`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c7a3f`

## string_xrefs

- `0x1800c799a`: `service::spaces.microsoft.com::mbi_ssl_sa`
- `0x1800c7baf`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\accountprotectionshield\accountprotectionshield.cpp`
- `0x1800c7c2c`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\accountprotectionshield\accountprotectionshield.cpp`
- `0x1800c7694`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x1800c7a20`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1800c78f1`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShieldProvider::AccountProtectionShield::IsAccountVerified(
        ShieldProvider::AccountProtectionShield *this,
        int *a2,
        int a3)
{
  HRESULT ActivationFactory; // eax
  int DefaultSignInAccount; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64, __int64, __int64); // rdi
  __int64 v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  int v22; // eax
  ShieldProvider::AccountProtectionShield *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rbx
  int v31; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  int *dwAuthnLevel; // [rsp+20h] [rbp-A9h]
  __int64 v36; // [rsp+40h] [rbp-89h] BYREF
  __int64 v37; // [rsp+48h] [rbp-81h] BYREF
  __int64 v38; // [rsp+50h] [rbp-79h] BYREF
  __int64 v39; // [rsp+58h] [rbp-71h] BYREF
  __int64 v40; // [rsp+60h] [rbp-69h] BYREF
  int v41[2]; // [rsp+68h] [rbp-61h] BYREF
  __int64 v42; // [rsp+70h] [rbp-59h] BYREF
  __int64 v43; // [rsp+78h] [rbp-51h] BYREF
  __int64 v44; // [rsp+80h] [rbp-49h] BYREF
  __int64 v45; // [rsp+88h] [rbp-41h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp-39h] BYREF
  int v47; // [rsp+98h] [rbp-31h] BYREF
  int v48; // [rsp+9Ch] [rbp-2Dh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-11h]
  HSTRING_HEADER v51; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v52; // [rsp+D8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  *a2 = 0;
  if ( ShieldProvider::AccountProtectionShield::RegGetValueDword(this, (const unsigned __int16 *)&stru_180100C10, a2) >= 0
    && (*a2 || !a3) )
  {
    return 0;
  }
  pProxy = 0;
  v50 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  ActivationFactory = RoGetActivationFactory(v50, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &pProxy);
  DefaultSignInAccount = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_83;
    v9 = 39;
    goto LABEL_13;
  }
  ActivationFactory = CoSetProxyBlanket(
                        pProxy,
                        0xFFFFFFFF,
                        0xFFFFFFFF,
                        (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                        2u,
                        3u,
                        0,
                        0x20u);
  DefaultSignInAccount = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v36 = 0;
    v10 = ((__int64 (__fastcall *)(IUnknown *, __int64 *))pProxy->lpVtbl[9].Release)(pProxy, &v36);
    DefaultSignInAccount = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v10);
      goto LABEL_82;
    }
    v38 = 0;
    v11 = v36;
    DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(v36);
    if ( DefaultSignInAccount < 0
      || (DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 64LL))(v11, &v38),
          DefaultSignInAccount < 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)DefaultSignInAccount);
      goto LABEL_81;
    }
    v37 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v37);
    DefaultSignInAccount = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v12);
      goto LABEL_24;
    }
    if ( !v37 )
    {
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v37);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v38);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v36);
      DefaultSignInAccount = -2147023579;
      goto LABEL_83;
    }
    v39 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL))(v37, &v39);
    DefaultSignInAccount = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v13);
      goto LABEL_31;
    }
    v40 = 0;
    v50 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
      0x39u,
      0x38u);
    v14 = RoGetActivationFactory(v50, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v40);
    DefaultSignInAccount = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v14);
      goto LABEL_36;
    }
    *(_QWORD *)v41 = 0;
    v15 = v40;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v40 + 48LL);
    v50 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"8A9AF170-1E1F-423E-8B43-466BA857DF5B",
      0x25u,
      0x24u);
    v17 = v50;
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v51,
      L"service::spaces.microsoft.com::mbi_ssl_sa",
      0x2Au,
      0x29u);
    dwAuthnLevel = v41;
    v18 = v16(v15, v39, v52, v17);
    DefaultSignInAccount = v18;
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v18);
      goto LABEL_41;
    }
    v42 = 0;
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v51,
      L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
      0x46u,
      0x45u);
    v19 = RoGetActivationFactory(v52, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v42);
    DefaultSignInAccount = v19;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v19);
      goto LABEL_46;
    }
    v44 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v42 + 56LL))(
            v42,
            *(_QWORD *)v41,
            v37,
            &v44);
    DefaultSignInAccount = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v20);
      goto LABEL_51;
    }
    v43 = 0;
    v21 = v44;
    DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v44);
    if ( DefaultSignInAccount < 0
      || (DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 64LL))(v21, &v43),
          DefaultSignInAccount < 0) )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_59;
      v25 = 49;
      v26 = (unsigned int)DefaultSignInAccount;
LABEL_58:
      WPP_SF_d(v24[2], v25, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, v26);
LABEL_59:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v43);
LABEL_51:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v44);
LABEL_46:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v42);
LABEL_41:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(v41);
LABEL_36:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v40);
LABEL_31:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v39);
LABEL_24:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v37);
LABEL_81:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v38);
LABEL_82:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v36);
      goto LABEL_83;
    }
    v47 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 56LL))(v43, &v47);
    DefaultSignInAccount = v22;
    if ( v22 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_59;
      v25 = 50;
      v26 = (unsigned int)v22;
      goto LABEL_58;
    }
    if ( !v47 )
    {
      *a2 = 1;
      v27 = ShieldProvider::AccountProtectionShield::RegSetValueDword(v23, (const unsigned __int16 *)&stru_180100C10, 1);
      if ( v27 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x208,
          (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\accountprotectionsh"
                        "ield\\accountprotectionshield.cpp",
          (const char *)(unsigned int)v27,
          (int)v41);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v43);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v44);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v42);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(v41);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v39);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v37);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v38);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v36);
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&pProxy);
      return 0;
    }
    *a2 = 0;
    v28 = ShieldProvider::AccountProtectionShield::RegSetValueDword(v23, (const unsigned __int16 *)&stru_180100C10, 0);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20E,
        (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\accountprotectionshie"
                      "ld\\accountprotectionshield.cpp",
        (const char *)(unsigned int)v28,
        (int)v41);
    v45 = 0;
    v29 = v43;
    v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    v31 = v30(v29, &v45);
    DefaultSignInAccount = v31;
    if ( v31 >= 0 )
    {
      v48 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 48LL))(v45, &v48);
      DefaultSignInAccount = v31;
      v32 = retaddr;
      if ( v31 >= 0 )
      {
        DefaultSignInAccount = v48;
        if ( v48 >= 0 )
        {
          DefaultSignInAccount = -2147467259;
          v34 = 2147500037LL;
          v33 = 535;
        }
        else
        {
          v34 = (unsigned int)v48;
          v33 = 533;
        }
        goto LABEL_69;
      }
      v33 = 532;
    }
    else
    {
      v32 = retaddr;
      v33 = 529;
    }
    v34 = (unsigned int)v31;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      v32,
      (void *)v33,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\accountprotectionshield"
                    "\\accountprotectionshield.cpp",
      (const char *)v34,
      (int)dwAuthnLevel);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    goto LABEL_59;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_83;
  v9 = 40;
LABEL_13:
  WPP_SF_d(v8[2], v9, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, (unsigned int)ActivationFactory);
LABEL_83:
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&pProxy);
  return (unsigned int)DefaultSignInAccount;
}

```

## disassembly

```asm
0x1800c7630  push    rbp
0x1800c7632  push    rbx
0x1800c7633  push    rsi
0x1800c7634  push    rdi
0x1800c7635  push    r14
0x1800c7637  push    r15
0x1800c7639  lea     rbp, [rsp-2Fh]
0x1800c763e  sub     rsp, 0F8h
0x1800c7645  mov     rax, cs:__security_cookie
0x1800c764c  xor     rax, rsp
0x1800c764f  mov     [rbp+57h+var_40], rax
0x1800c7653  mov     ebx, r8d
0x1800c7656  mov     r14, rdx
0x1800c7659  xor     r15d, r15d
0x1800c765c  mov     [rdx], r15d
0x1800c765f  mov     r8, rdx; int *
0x1800c7662  lea     rdx, stru_180100C10; unsigned __int16 *
0x1800c7669  call    ?RegGetValueDword@AccountProtectionShield@ShieldProvider@@AEAAJPEBGPEAH@Z; ShieldProvider::AccountProtectionShield::RegGetValueDword(ushort const *,int *)
0x1800c766e  test    eax, eax
0x1800c7670  js      short loc_1800C7682
0x1800c7672  cmp     [r14], r15d
0x1800c7675  jnz     short loc_1800C767B
0x1800c7677  test    ebx, ebx
0x1800c7679  jnz     short loc_1800C7682
0x1800c767b  xor     eax, eax
0x1800c767d  jmp     loc_1800C7D63
0x1800c7682  mov     [rbp+57h+pProxy], r15
0x1800c7686  mov     [rbp+57h+var_68], r15
0x1800c768a  mov     r9d, 40h ; '@'; unsigned int
0x1800c7690  lea     r8d, [r9+1]; unsigned int
0x1800c7694  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800c769b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800c769f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c76a4  lea     r8, [rbp+57h+pProxy]
0x1800c76a8  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x1800c76af  mov     rcx, [rbp+57h+var_68]
0x1800c76b3  call    cs:__imp_RoGetActivationFactory
0x1800c76b9  mov     ebx, eax
0x1800c76bb  test    eax, eax
0x1800c76bd  jns     short loc_1800C76E7
0x1800c76bf  lea     rdx, WPP_GLOBAL_Control
0x1800c76c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c76cd  cmp     rcx, rdx
0x1800c76d0  jz      loc_1800C7D58
0x1800c76d6  test    byte ptr [rcx+1Ch], 1
0x1800c76da  jz      loc_1800C7D58
0x1800c76e0  mov     edx, 27h ; '''
0x1800c76e5  jmp     short loc_1800C7744
0x1800c76e7  mov     [rsp+120h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800c76ef  mov     [rsp+120h+pAuthInfo], r15; pAuthInfo
0x1800c76f4  mov     [rsp+120h+dwImpLevel], 3; dwImpLevel
0x1800c76fc  mov     [rsp+120h+dwAuthnLevel], 2; dwAuthnLevel
0x1800c7704  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800c7708  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800c770b  mov     r8d, edx; dwAuthzSvc
0x1800c770e  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800c7712  call    cs:__imp_CoSetProxyBlanket
0x1800c7718  mov     ebx, eax
0x1800c771a  test    eax, eax
0x1800c771c  jns     short loc_1800C775C
0x1800c771e  lea     rdx, WPP_GLOBAL_Control
0x1800c7725  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c772c  cmp     rcx, rdx
0x1800c772f  jz      loc_1800C7D58
0x1800c7735  test    byte ptr [rcx+1Ch], 1
0x1800c7739  jz      loc_1800C7D58
0x1800c773f  mov     edx, 28h ; '('
0x1800c7744  mov     r9d, eax
0x1800c7747  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c774e  mov     rcx, [rcx+10h]
0x1800c7752  call    WPP_SF_d
0x1800c7757  jmp     loc_1800C7D58
0x1800c775c  mov     [rsp+120h+var_E0], r15
0x1800c7761  mov     rcx, [rbp+57h+pProxy]
0x1800c7765  mov     rax, [rcx]
0x1800c7768  lea     rdx, [rsp+120h+var_E0]
0x1800c776d  mov     rax, [rax+0E8h]
0x1800c7774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7779  mov     ebx, eax
0x1800c777b  test    eax, eax
0x1800c777d  jns     short loc_1800C77BD
0x1800c777f  lea     rdx, WPP_GLOBAL_Control
0x1800c7786  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c778d  cmp     rcx, rdx
0x1800c7790  jz      loc_1800C7D4E
0x1800c7796  test    byte ptr [rcx+1Ch], 1
0x1800c779a  jz      loc_1800C7D4E
0x1800c77a0  mov     edx, 29h ; ')'
0x1800c77a5  mov     r9d, eax
0x1800c77a8  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c77af  mov     rcx, [rcx+10h]
0x1800c77b3  call    WPP_SF_d
0x1800c77b8  jmp     loc_1800C7D4E
0x1800c77bd  mov     [rbp+57h+var_D0], r15
0x1800c77c1  mov     rdi, [rsp+120h+var_E0]
0x1800c77c6  mov     rcx, rdi
0x1800c77c9  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x1800c77ce  mov     ebx, eax
0x1800c77d0  test    eax, eax
0x1800c77d2  js      loc_1800C7D14
0x1800c77d8  mov     rax, [rdi]
0x1800c77db  lea     rdx, [rbp+57h+var_D0]
0x1800c77df  mov     rcx, rdi
0x1800c77e2  mov     rax, [rax+40h]
0x1800c77e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c77eb  mov     ebx, eax
0x1800c77ed  test    eax, eax
0x1800c77ef  js      loc_1800C7D14
0x1800c77f5  mov     [rsp+120h+var_D8], r15
0x1800c77fa  mov     rcx, [rbp+57h+var_D0]
0x1800c77fe  mov     rax, [rcx]
0x1800c7801  lea     rdx, [rsp+120h+var_D8]
0x1800c7806  mov     rax, [rax+30h]
0x1800c780a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c780f  mov     ebx, eax
0x1800c7811  test    eax, eax
0x1800c7813  jns     short loc_1800C7855
0x1800c7815  lea     rdx, WPP_GLOBAL_Control
0x1800c781c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7823  cmp     rcx, rdx
0x1800c7826  jz      short loc_1800C7846
0x1800c7828  test    byte ptr [rcx+1Ch], 1
0x1800c782c  jz      short loc_1800C7846
0x1800c782e  mov     edx, 2Bh ; '+'
0x1800c7833  mov     r9d, eax
0x1800c7836  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c783d  mov     rcx, [rcx+10h]
0x1800c7841  call    WPP_SF_d
0x1800c7846  lea     rcx, [rsp+120h+var_D8]
0x1800c784b  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7850  jmp     loc_1800C7D45
0x1800c7855  mov     rcx, [rsp+120h+var_D8]
0x1800c785a  test    rcx, rcx
0x1800c785d  jnz     short loc_1800C7886
0x1800c785f  lea     rcx, [rsp+120h+var_D8]
0x1800c7864  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7869  lea     rcx, [rbp+57h+var_D0]
0x1800c786d  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7872  lea     rcx, [rsp+120h+var_E0]
0x1800c7877  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c787c  mov     ebx, 80070525h
0x1800c7881  jmp     loc_1800C7D58
0x1800c7886  mov     [rbp+57h+var_C8], r15
0x1800c788a  mov     rax, [rcx]
0x1800c788d  lea     rdx, [rbp+57h+var_C8]
0x1800c7891  mov     rax, [rax+30h]
0x1800c7895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c789a  mov     ebx, eax
0x1800c789c  test    eax, eax
0x1800c789e  jns     short loc_1800C78DF
0x1800c78a0  lea     rdx, WPP_GLOBAL_Control
0x1800c78a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c78ae  cmp     rcx, rdx
0x1800c78b1  jz      short loc_1800C78D1
0x1800c78b3  test    byte ptr [rcx+1Ch], 1
0x1800c78b7  jz      short loc_1800C78D1
0x1800c78b9  mov     edx, 2Ch ; ','
0x1800c78be  mov     r9d, eax
0x1800c78c1  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c78c8  mov     rcx, [rcx+10h]
0x1800c78cc  call    WPP_SF_d
0x1800c78d1  lea     rcx, [rbp+57h+var_C8]
0x1800c78d5  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c78da  jmp     loc_1800C7846
0x1800c78df  mov     [rbp+57h+var_C0], r15
0x1800c78e3  mov     [rbp+57h+var_68], r15
0x1800c78e7  mov     r9d, 38h ; '8'; unsigned int
0x1800c78ed  lea     r8d, [r9+1]; unsigned int
0x1800c78f1  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800c78f8  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800c78fc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c7901  lea     r8, [rbp+57h+var_C0]
0x1800c7905  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x1800c790c  mov     rcx, [rbp+57h+var_68]
0x1800c7910  call    cs:__imp_RoGetActivationFactory
0x1800c7916  mov     ebx, eax
0x1800c7918  test    eax, eax
0x1800c791a  jns     short loc_1800C795B
0x1800c791c  lea     rdx, WPP_GLOBAL_Control
0x1800c7923  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c792a  cmp     rcx, rdx
0x1800c792d  jz      short loc_1800C794D
0x1800c792f  test    byte ptr [rcx+1Ch], 1
0x1800c7933  jz      short loc_1800C794D
0x1800c7935  mov     edx, 2Dh ; '-'
0x1800c793a  mov     r9d, eax
0x1800c793d  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7944  mov     rcx, [rcx+10h]
0x1800c7948  call    WPP_SF_d
0x1800c794d  lea     rcx, [rbp+57h+var_C0]
0x1800c7951  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7956  jmp     loc_1800C78D1
0x1800c795b  mov     qword ptr [rbp+57h+var_B8], r15
0x1800c795f  mov     rsi, [rbp+57h+var_C0]
0x1800c7963  mov     rax, [rsi]
0x1800c7966  mov     rdi, [rax+30h]
0x1800c796a  mov     [rbp+57h+var_68], r15
0x1800c796e  mov     r9d, 24h ; '$'; unsigned int
0x1800c7974  lea     r8d, [r9+1]; unsigned int
0x1800c7978  lea     rdx, sourceString; "8A9AF170-1E1F-423E-8B43-466BA857DF5B"
0x1800c797f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800c7983  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c7988  mov     rbx, [rbp+57h+var_68]
0x1800c798c  mov     [rbp+57h+var_48], r15
0x1800c7990  mov     r9d, 29h ; ')'; unsigned int
0x1800c7996  lea     r8d, [r9+1]; unsigned int
0x1800c799a  lea     rdx, aServiceSpacesM; "service::spaces.microsoft.com::mbi_ssl_"...
0x1800c79a1  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x1800c79a5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c79aa  lea     rax, [rbp+57h+var_B8]
0x1800c79ae  mov     qword ptr [rsp+120h+dwAuthnLevel], rax; int
0x1800c79b3  mov     r9, rbx
0x1800c79b6  mov     r8, [rbp+57h+var_48]
0x1800c79ba  mov     rdx, [rbp+57h+var_C8]
0x1800c79be  mov     rcx, rsi
0x1800c79c1  mov     rax, rdi
0x1800c79c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c79c9  mov     ebx, eax
0x1800c79cb  test    eax, eax
0x1800c79cd  jns     short loc_1800C7A0E
0x1800c79cf  lea     rdx, WPP_GLOBAL_Control
0x1800c79d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c79dd  cmp     rcx, rdx
0x1800c79e0  jz      short loc_1800C7A00
0x1800c79e2  test    byte ptr [rcx+1Ch], 1
0x1800c79e6  jz      short loc_1800C7A00
0x1800c79e8  mov     edx, 2Eh ; '.'
0x1800c79ed  mov     r9d, eax
0x1800c79f0  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c79f7  mov     rcx, [rcx+10h]
0x1800c79fb  call    WPP_SF_d
0x1800c7a00  lea     rcx, [rbp+57h+var_B8]
0x1800c7a04  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7a09  jmp     loc_1800C794D
0x1800c7a0e  mov     [rbp+57h+var_B0], r15
0x1800c7a12  mov     [rbp+57h+var_48], r15
0x1800c7a16  mov     r9d, 45h ; 'E'; unsigned int
0x1800c7a1c  lea     r8d, [r9+1]; unsigned int
0x1800c7a20  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800c7a27  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x1800c7a2b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c7a30  lea     r8, [rbp+57h+var_B0]
0x1800c7a34  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1800c7a3b  mov     rcx, [rbp+57h+var_48]
0x1800c7a3f  call    cs:__imp_RoGetActivationFactory
0x1800c7a45  mov     ebx, eax
0x1800c7a47  test    eax, eax
0x1800c7a49  jns     short loc_1800C7A8A
0x1800c7a4b  lea     rdx, WPP_GLOBAL_Control
0x1800c7a52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7a59  cmp     rcx, rdx
0x1800c7a5c  jz      short loc_1800C7A7C
0x1800c7a5e  test    byte ptr [rcx+1Ch], 1
0x1800c7a62  jz      short loc_1800C7A7C
0x1800c7a64  mov     edx, 2Fh ; '/'
0x1800c7a69  mov     r9d, eax
0x1800c7a6c  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7a73  mov     rcx, [rcx+10h]
0x1800c7a77  call    WPP_SF_d
0x1800c7a7c  lea     rcx, [rbp+57h+var_B0]
0x1800c7a80  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7a85  jmp     loc_1800C7A00
0x1800c7a8a  mov     [rbp+57h+var_A0], r15
0x1800c7a8e  mov     rcx, [rbp+57h+var_B0]
0x1800c7a92  mov     rax, [rcx]
0x1800c7a95  lea     r9, [rbp+57h+var_A0]
0x1800c7a99  mov     r8, [rsp+120h+var_D8]
0x1800c7a9e  mov     rdx, qword ptr [rbp+57h+var_B8]
0x1800c7aa2  mov     rax, [rax+38h]
0x1800c7aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7aab  mov     ebx, eax
0x1800c7aad  test    eax, eax
0x1800c7aaf  jns     short loc_1800C7AED
0x1800c7ab1  lea     rdx, WPP_GLOBAL_Control
0x1800c7ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7abf  cmp     rcx, rdx
0x1800c7ac2  jz      short loc_1800C7AE2
0x1800c7ac4  test    byte ptr [rcx+1Ch], 1
0x1800c7ac8  jz      short loc_1800C7AE2
0x1800c7aca  mov     edx, 30h ; '0'
0x1800c7acf  mov     r9d, eax
0x1800c7ad2  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7ad9  mov     rcx, [rcx+10h]
0x1800c7add  call    WPP_SF_d
0x1800c7ae2  lea     rcx, [rbp+57h+var_A0]
0x1800c7ae6  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7aeb  jmp     short loc_1800C7A7C
0x1800c7aed  mov     [rbp+57h+var_A8], r15
0x1800c7af1  mov     rdi, [rbp+57h+var_A0]
0x1800c7af5  mov     rcx, rdi
0x1800c7af8  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)
0x1800c7afd  mov     ebx, eax
0x1800c7aff  test    eax, eax
0x1800c7b01  js      loc_1800C7CE6
0x1800c7b07  mov     rax, [rdi]
0x1800c7b0a  lea     rdx, [rbp+57h+var_A8]
0x1800c7b0e  mov     rcx, rdi
0x1800c7b11  mov     rax, [rax+40h]
0x1800c7b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7b1a  mov     ebx, eax
  ... truncated ...
```
