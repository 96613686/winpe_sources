# ShieldProvider::AccountProtectionShield::IsAccountAssociated(bool *)

- ea: `0x1800c70c0`
- end: `0x1800c7628`
- name: `?IsAccountAssociated@AccountProtectionShield@ShieldProvider@@AEAAJPEA_N@Z`
- size: `1384`
- prototype: `__int64 __fastcall(ShieldProvider::AccountProtectionShield *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c8b44`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x18006e0a4`
- `0x1800c44f4`
- `0x1800c4d40`
- `0x1800c70c0`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800c7386`
- `KERNEL32!CompareStringOrdinal` at `0x1800c73b5`
- `KERNEL32!CompareStringOrdinal` at `0x1800c7386`
- `KERNEL32!CompareStringOrdinal` at `0x1800c73b5`
- `ole32!CoSetProxyBlanket` at `0x1800c717c`
- `ole32!CoSetProxyBlanket` at `0x1800c717c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c711b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c711b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c73cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c73e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c740f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c749b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c74b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c73cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c73e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c740f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c749b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c74b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c7397`

## string_xrefs

- `0x1800c737c`: `https://login.microsoft.com`
- `0x1800c70fc`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShieldProvider::AccountProtectionShield::IsAccountAssociated(
        ShieldProvider::AccountProtectionShield *this,
        bool *a2)
{
  HRESULT ActivationFactory; // eax
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdi
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int i; // ebx
  int v14; // eax
  int v15; // edi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v21; // rax
  __int64 v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  __int64 v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 v26; // [rsp+58h] [rbp-31h] BYREF
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  __int64 v28; // [rsp+68h] [rbp-21h] BYREF
  IUnknown *pProxy; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v30; // [rsp+78h] [rbp-11h] BYREF
  HSTRING v31; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  __int64 v33; // [rsp+A0h] [rbp+17h]

  *a2 = 0;
  pProxy = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  ActivationFactory = RoGetActivationFactory(v33, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &pProxy);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_68;
    v6 = 12;
    goto LABEL_9;
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
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_68;
    v6 = 13;
LABEL_9:
    WPP_SF_d(v5[2], v6, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, (unsigned int)ActivationFactory);
    goto LABEL_68;
  }
  v24 = 0;
  v7 = ((__int64 (__fastcall *)(IUnknown *, __int64 *))pProxy->lpVtbl[4].QueryInterface)(pProxy, &v24);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)v7);
    goto LABEL_67;
  }
  v23 = 0;
  v8 = v24;
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(v24);
  if ( v4 < 0 || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL))(v8, &v23), v4 < 0) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v11 = 15;
    v12 = (unsigned int)v4;
    goto LABEL_65;
  }
  v30 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 56LL))(v23, &v30);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v11 = 16;
    v12 = (unsigned int)v9;
LABEL_65:
    WPP_SF_d(v10[2], v11, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, v12);
LABEL_66:
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v23);
LABEL_67:
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v24);
    goto LABEL_68;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v30 )
      goto LABEL_39;
    v26 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 48LL))(v23, i, &v26);
    v15 = v14;
    if ( v14 < 0 )
      break;
    v25 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL))(v26, &v25);
    v15 = v16;
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v16);
      goto LABEL_48;
    }
    string = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 48LL))(v25, &string);
    v15 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v17);
      goto LABEL_46;
    }
    v28 = 0;
    v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(
            v25,
            &GUID_4a01eb05_4e42_41d4_b518_e008a5163614,
            &v28);
    v15 = v18;
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v18);
LABEL_45:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v28);
LABEL_46:
      if ( string )
        WindowsDeleteString(string);
LABEL_48:
      wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v25);
      goto LABEL_61;
    }
    v31 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 56LL))(v28, &v31);
    v15 = v19;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v19);
      if ( v31 )
        WindowsDeleteString(v31);
      goto LABEL_45;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"https://login.microsoft.com", -1, 1) == 2 )
    {
      v21 = WindowsGetStringRawBuffer(v31, 0);
      if ( CompareStringOrdinal(v21, -1, L"consumers", -1, 1) == 2 )
      {
        *a2 = 1;
        if ( v31 )
          WindowsDeleteString(v31);
        wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v28);
        if ( string )
          WindowsDeleteString(string);
        wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v25);
        wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v26);
LABEL_39:
        wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v23);
        wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v24);
        wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&pProxy);
        return 0;
      }
    }
    *a2 = 0;
    if ( v31 )
      WindowsDeleteString(v31);
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v28);
    if ( string )
      WindowsDeleteString(string);
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v25);
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v26);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
      (unsigned int)v14);
LABEL_61:
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v26);
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v23);
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v24);
  v4 = v15;
LABEL_68:
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&pProxy);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c70c0  push    rbp
0x1800c70c2  push    rbx
0x1800c70c3  push    rsi
0x1800c70c4  push    rdi
0x1800c70c5  push    r14
0x1800c70c7  push    r15
0x1800c70c9  lea     rbp, [rsp-2Fh]
0x1800c70ce  sub     rsp, 0B8h
0x1800c70d5  mov     rax, cs:__security_cookie
0x1800c70dc  xor     rax, rsp
0x1800c70df  mov     [rbp+57h+var_38], rax
0x1800c70e3  mov     rsi, rdx
0x1800c70e6  xor     r14d, r14d
0x1800c70e9  mov     [rdx], r14b
0x1800c70ec  mov     [rbp+57h+pProxy], r14
0x1800c70f0  mov     [rbp+57h+var_40], r14
0x1800c70f4  lea     r9d, [r14+40h]; unsigned int
0x1800c70f8  lea     r8d, [r14+41h]; unsigned int
0x1800c70fc  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800c7103  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800c7107  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c710c  lea     r8, [rbp+57h+pProxy]
0x1800c7110  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x1800c7117  mov     rcx, [rbp+57h+var_40]
0x1800c711b  call    cs:__imp_RoGetActivationFactory
0x1800c7121  mov     ebx, eax
0x1800c7123  test    eax, eax
0x1800c7125  jns     short loc_1800C714E
0x1800c7127  lea     rdx, WPP_GLOBAL_Control
0x1800c712e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7135  cmp     rcx, rdx
0x1800c7138  jz      loc_1800C7601
0x1800c713e  test    byte ptr [rcx+1Ch], 1
0x1800c7142  jz      loc_1800C7601
0x1800c7148  lea     edx, [r14+0Ch]
0x1800c714c  jmp     short loc_1800C71AD
0x1800c714e  mov     [rsp+0E0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800c7156  mov     [rsp+0E0h+pAuthInfo], r14; pAuthInfo
0x1800c715b  mov     [rsp+0E0h+dwImpLevel], 3; dwImpLevel
0x1800c7163  mov     [rsp+0E0h+dwAuthnLevel], 2; dwAuthnLevel
0x1800c716b  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800c716f  mov     r9, r15; pServerPrincName
0x1800c7172  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800c7175  mov     r8d, edx; dwAuthzSvc
0x1800c7178  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800c717c  call    cs:__imp_CoSetProxyBlanket
0x1800c7182  mov     ebx, eax
0x1800c7184  test    eax, eax
0x1800c7186  jns     short loc_1800C71C5
0x1800c7188  lea     rdx, WPP_GLOBAL_Control
0x1800c718f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7196  cmp     rcx, rdx
0x1800c7199  jz      loc_1800C7601
0x1800c719f  test    byte ptr [rcx+1Ch], 1
0x1800c71a3  jz      loc_1800C7601
0x1800c71a9  lea     edx, [r15+0Eh]
0x1800c71ad  mov     r9d, eax
0x1800c71b0  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c71b7  mov     rcx, [rcx+10h]
0x1800c71bb  call    WPP_SF_d
0x1800c71c0  jmp     loc_1800C7601
0x1800c71c5  mov     [rbp+57h+var_98], r14
0x1800c71c9  mov     rcx, [rbp+57h+pProxy]
0x1800c71cd  mov     rax, [rcx]
0x1800c71d0  lea     rdx, [rbp+57h+var_98]
0x1800c71d4  mov     rax, [rax+60h]
0x1800c71d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c71dd  mov     ebx, eax
0x1800c71df  test    eax, eax
0x1800c71e1  jns     short loc_1800C7221
0x1800c71e3  lea     rdx, WPP_GLOBAL_Control
0x1800c71ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c71f1  cmp     rcx, rdx
0x1800c71f4  jz      loc_1800C75F8
0x1800c71fa  test    byte ptr [rcx+1Ch], 1
0x1800c71fe  jz      loc_1800C75F8
0x1800c7204  mov     edx, 0Eh
0x1800c7209  mov     r9d, eax
0x1800c720c  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7213  mov     rcx, [rcx+10h]
0x1800c7217  call    WPP_SF_d
0x1800c721c  jmp     loc_1800C75F8
0x1800c7221  mov     [rbp+57h+var_A0], r14
0x1800c7225  mov     rdi, [rbp+57h+var_98]
0x1800c7229  mov     rcx, rdi
0x1800c722c  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)
0x1800c7231  mov     ebx, eax
0x1800c7233  test    eax, eax
0x1800c7235  js      loc_1800C75BE
0x1800c723b  mov     rax, [rdi]
0x1800c723e  lea     rdx, [rbp+57h+var_A0]
0x1800c7242  mov     rcx, rdi
0x1800c7245  mov     rax, [rax+40h]
0x1800c7249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c724e  mov     ebx, eax
0x1800c7250  test    eax, eax
0x1800c7252  js      loc_1800C75BE
0x1800c7258  mov     [rbp+57h+var_68], r14d
0x1800c725c  mov     rcx, [rbp+57h+var_A0]
0x1800c7260  mov     rax, [rcx]
0x1800c7263  lea     rdx, [rbp+57h+var_68]
0x1800c7267  mov     rax, [rax+38h]
0x1800c726b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7270  mov     ebx, eax
0x1800c7272  test    eax, eax
0x1800c7274  jns     short loc_1800C72A4
0x1800c7276  lea     rdx, WPP_GLOBAL_Control
0x1800c727d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7284  cmp     rcx, rdx
0x1800c7287  jz      loc_1800C75EF
0x1800c728d  test    byte ptr [rcx+1Ch], 1
0x1800c7291  jz      loc_1800C75EF
0x1800c7297  mov     edx, 10h
0x1800c729c  mov     r9d, eax
0x1800c729f  jmp     loc_1800C75DF
0x1800c72a4  mov     ebx, r14d
0x1800c72a7  cmp     ebx, [rbp+57h+var_68]
0x1800c72aa  jnb     loc_1800C743F
0x1800c72b0  mov     [rbp+57h+var_88], r14
0x1800c72b4  mov     rcx, [rbp+57h+var_A0]
0x1800c72b8  mov     rax, [rcx]
0x1800c72bb  lea     r8, [rbp+57h+var_88]
0x1800c72bf  mov     edx, ebx
0x1800c72c1  mov     rax, [rax+30h]
0x1800c72c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c72ca  mov     edi, eax
0x1800c72cc  test    eax, eax
0x1800c72ce  js      loc_1800C756E
0x1800c72d4  mov     [rbp+57h+var_90], r14
0x1800c72d8  mov     rcx, [rbp+57h+var_88]
0x1800c72dc  mov     rax, [rcx]
0x1800c72df  lea     rdx, [rbp+57h+var_90]
0x1800c72e3  mov     rax, [rax+30h]
0x1800c72e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c72ec  mov     edi, eax
0x1800c72ee  test    eax, eax
0x1800c72f0  js      loc_1800C7530
0x1800c72f6  mov     [rbp+57h+string], r14
0x1800c72fa  mov     rcx, [rbp+57h+var_90]
0x1800c72fe  mov     rax, [rcx]
0x1800c7301  lea     rdx, [rbp+57h+string]
0x1800c7305  mov     rax, [rax+30h]
0x1800c7309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c730e  mov     edi, eax
0x1800c7310  test    eax, eax
0x1800c7312  js      loc_1800C74FA
0x1800c7318  mov     [rbp+57h+var_78], r14
0x1800c731c  mov     rcx, [rbp+57h+var_90]
0x1800c7320  mov     rax, [rcx]
0x1800c7323  lea     r8, [rbp+57h+var_78]
0x1800c7327  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x1800c732e  mov     rax, [rax]
0x1800c7331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7336  mov     edi, eax
0x1800c7338  test    eax, eax
0x1800c733a  js      loc_1800C74C7
0x1800c7340  mov     [rbp+57h+var_60], r14
0x1800c7344  mov     rcx, [rbp+57h+var_78]
0x1800c7348  mov     rax, [rcx]
0x1800c734b  lea     rdx, [rbp+57h+var_60]
0x1800c734f  mov     rax, [rax+38h]
0x1800c7353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7358  mov     edi, eax
0x1800c735a  test    eax, eax
0x1800c735c  js      loc_1800C7461
0x1800c7362  xor     edx, edx; length
0x1800c7364  mov     rcx, [rbp+57h+string]; string
0x1800c7368  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c736e  mov     rcx, rax; lpString1
0x1800c7371  mov     [rsp+0E0h+dwAuthnLevel], 1; bIgnoreCase
0x1800c7379  mov     r9d, r15d; cchCount2
0x1800c737c  lea     r8, aHttpsLoginMicr; "https://login.microsoft.com"
0x1800c7383  mov     edx, r15d; cchCount1
0x1800c7386  call    cs:__imp_CompareStringOrdinal
0x1800c738c  cmp     eax, 2
0x1800c738f  jnz     short loc_1800C73C0
0x1800c7391  xor     edx, edx; length
0x1800c7393  mov     rcx, [rbp+57h+var_60]; string
0x1800c7397  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c739d  mov     rcx, rax; lpString1
0x1800c73a0  mov     [rsp+0E0h+dwAuthnLevel], 1; bIgnoreCase
0x1800c73a8  mov     r9d, r15d; cchCount2
0x1800c73ab  lea     r8, aConsumers; "consumers"
0x1800c73b2  mov     edx, r15d; cchCount1
0x1800c73b5  call    cs:__imp_CompareStringOrdinal
0x1800c73bb  cmp     eax, 2
0x1800c73be  jz      short loc_1800C7403
0x1800c73c0  mov     [rsi], r14b
0x1800c73c3  mov     rcx, [rbp+57h+var_60]; string
0x1800c73c7  test    rcx, rcx
0x1800c73ca  jz      short loc_1800C73D2
0x1800c73cc  call    cs:__imp_WindowsDeleteString
0x1800c73d2  lea     rcx, [rbp+57h+var_78]
0x1800c73d6  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c73db  mov     rcx, [rbp+57h+string]; string
0x1800c73df  test    rcx, rcx
0x1800c73e2  jz      short loc_1800C73EA
0x1800c73e4  call    cs:__imp_WindowsDeleteString
0x1800c73ea  lea     rcx, [rbp+57h+var_90]
0x1800c73ee  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c73f3  lea     rcx, [rbp+57h+var_88]
0x1800c73f7  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c73fc  inc     ebx
0x1800c73fe  jmp     loc_1800C72A7
0x1800c7403  mov     byte ptr [rsi], 1
0x1800c7406  mov     rcx, [rbp+57h+var_60]; string
0x1800c740a  test    rcx, rcx
0x1800c740d  jz      short loc_1800C7415
0x1800c740f  call    cs:__imp_WindowsDeleteString
0x1800c7415  lea     rcx, [rbp+57h+var_78]
0x1800c7419  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c741e  mov     rcx, [rbp+57h+string]; string
0x1800c7422  test    rcx, rcx
0x1800c7425  jz      short loc_1800C742D
0x1800c7427  call    cs:__imp_WindowsDeleteString
0x1800c742d  lea     rcx, [rbp+57h+var_90]
0x1800c7431  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7436  lea     rcx, [rbp+57h+var_88]
0x1800c743a  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c743f  lea     rcx, [rbp+57h+var_A0]
0x1800c7443  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7448  lea     rcx, [rbp+57h+var_98]
0x1800c744c  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c7451  lea     rcx, [rbp+57h+pProxy]
0x1800c7455  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c745a  xor     eax, eax
0x1800c745c  jmp     loc_1800C760C
0x1800c7461  lea     rdx, WPP_GLOBAL_Control
0x1800c7468  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c746f  cmp     rcx, rdx
0x1800c7472  jz      short loc_1800C7492
0x1800c7474  test    byte ptr [rcx+1Ch], 1
0x1800c7478  jz      short loc_1800C7492
0x1800c747a  mov     edx, 15h
0x1800c747f  mov     r9d, edi
0x1800c7482  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7489  mov     rcx, [rcx+10h]
0x1800c748d  call    WPP_SF_d
0x1800c7492  mov     rcx, [rbp+57h+var_60]; string
0x1800c7496  test    rcx, rcx
0x1800c7499  jz      short loc_1800C74A1
0x1800c749b  call    cs:__imp_WindowsDeleteString
0x1800c74a1  lea     rcx, [rbp+57h+var_78]
0x1800c74a5  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c74aa  mov     rcx, [rbp+57h+string]; string
0x1800c74ae  test    rcx, rcx
0x1800c74b1  jz      short loc_1800C74B9
0x1800c74b3  call    cs:__imp_WindowsDeleteString
0x1800c74b9  lea     rcx, [rbp+57h+var_90]
0x1800c74bd  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c74c2  jmp     loc_1800C759F
0x1800c74c7  lea     rdx, WPP_GLOBAL_Control
0x1800c74ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c74d5  cmp     rcx, rdx
0x1800c74d8  jz      short loc_1800C74A1
0x1800c74da  test    byte ptr [rcx+1Ch], 1
0x1800c74de  jz      short loc_1800C74A1
0x1800c74e0  mov     edx, 14h
0x1800c74e5  mov     r9d, edi
0x1800c74e8  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c74ef  mov     rcx, [rcx+10h]
0x1800c74f3  call    WPP_SF_d
0x1800c74f8  jmp     short loc_1800C74A1
0x1800c74fa  lea     rdx, WPP_GLOBAL_Control
0x1800c7501  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7508  cmp     rcx, rdx
0x1800c750b  jz      short loc_1800C74AA
0x1800c750d  test    byte ptr [rcx+1Ch], 1
0x1800c7511  jz      short loc_1800C74AA
0x1800c7513  mov     edx, 13h
0x1800c7518  mov     r9d, edi
0x1800c751b  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7522  mov     rcx, [rcx+10h]
0x1800c7526  call    WPP_SF_d
0x1800c752b  jmp     loc_1800C74AA
0x1800c7530  lea     rdx, WPP_GLOBAL_Control
0x1800c7537  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c753e  cmp     rcx, rdx
0x1800c7541  jz      loc_1800C74B9
0x1800c7547  test    byte ptr [rcx+1Ch], 1
0x1800c754b  jz      loc_1800C74B9
0x1800c7551  mov     edx, 12h
0x1800c7556  mov     r9d, edi
0x1800c7559  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7560  mov     rcx, [rcx+10h]
0x1800c7564  call    WPP_SF_d
0x1800c7569  jmp     loc_1800C74B9
0x1800c756e  lea     rdx, WPP_GLOBAL_Control
0x1800c7575  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c757c  cmp     rcx, rdx
0x1800c757f  jz      short loc_1800C759F
0x1800c7581  test    byte ptr [rcx+1Ch], 1
0x1800c7585  jz      short loc_1800C759F
0x1800c7587  mov     edx, 11h
0x1800c758c  mov     r9d, edi
0x1800c758f  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c7596  mov     rcx, [rcx+10h]
0x1800c759a  call    WPP_SF_d
0x1800c759f  lea     rcx, [rbp+57h+var_88]
0x1800c75a3  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
  ... truncated ...
```
