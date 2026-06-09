# ShieldProvider::AccountProtectionShield::GetUserAccountName(ushort * *)

- ea: `0x1800c6b00`
- end: `0x1800c6f00`
- name: `?GetUserAccountName@AccountProtectionShield@ShieldProvider@@UEAAJPEAPEAG@Z`
- size: `1024`
- prototype: `int(ShieldProvider::AccountProtectionShield *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c6f10`

## callees

- `0x180004710`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x18006e0a4`
- `0x1800c4690`
- `0x1800c4d40`
- `0x1800c6b00`
- `0x1800e1764`
- `0x1800e7010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x1800c6c2a`
- `ole32!CoSetProxyBlanket` at `0x1800c6c2a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c6bb0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c6bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6e09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6e09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6e1a`

## string_xrefs

- `0x1800c6b91`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ShieldProvider::AccountProtectionShield::GetUserAccountName(
        ShieldProvider::AccountProtectionShield *this,
        unsigned __int16 **a2)
{
  int DefaultSignInAccount; // ebx
  HRESULT ActivationFactory; // eax
  _QWORD *v5; // r10
  __int64 v6; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  _QWORD *v13; // r10
  __int64 v14; // rdx
  unsigned __int16 **StringRawBuffer; // rax
  unsigned __int16 *v16; // r8
  IUnknown *pProxy; // [rsp+40h] [rbp-29h] BYREF
  __int64 v19; // [rsp+48h] [rbp-21h] BYREF
  __int64 v20; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v21; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+60h] [rbp-9h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v25; // [rsp+88h] [rbp+1Fh]

  v23 = 0;
  DefaultSignInAccount = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v23);
  if ( DefaultSignInAccount < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)DefaultSignInAccount);
    goto LABEL_47;
  }
  pProxy = 0;
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  ActivationFactory = RoGetActivationFactory(v25, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &pProxy);
  DefaultSignInAccount = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_46;
    v6 = 86;
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
  DefaultSignInAccount = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_46;
    v6 = 87;
LABEL_9:
    WPP_SF_d(v5[2], v6, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, (unsigned int)ActivationFactory);
LABEL_46:
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&pProxy);
    goto LABEL_47;
  }
  v19 = 0;
  lpVtbl = pProxy->lpVtbl;
  v19 = 0;
  v8 = ((__int64 (__fastcall *)(IUnknown *, __int64 *))lpVtbl[9].Release)(pProxy, &v19);
  DefaultSignInAccount = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)v8);
    goto LABEL_45;
  }
  v21 = 0;
  v9 = v19;
  DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(v19);
  if ( DefaultSignInAccount < 0
    || (DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v9 + 64LL))(v9, &v21),
        DefaultSignInAccount < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)DefaultSignInAccount);
    goto LABEL_44;
  }
  v20 = 0;
  v10 = *v21;
  v20 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v10 + 48))(v21, &v20);
  DefaultSignInAccount = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)v11);
LABEL_24:
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v20);
LABEL_44:
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v21);
LABEL_45:
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v19);
    goto LABEL_46;
  }
  if ( !v20 )
  {
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v20);
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v21);
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v19);
    wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&pProxy);
    DefaultSignInAccount = -2147023579;
    goto LABEL_47;
  }
  string = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 56LL))(v20, &string);
  DefaultSignInAccount = v12;
  if ( v12 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 91;
LABEL_31:
      WPP_SF_d(v13[2], v14, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, (unsigned int)v12);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  StringRawBuffer = (unsigned __int16 **)WindowsGetStringRawBuffer(string, 0);
  v12 = CommonUtil::UtilCoDuplicateString((CommonUtil *)a2, StringRawBuffer, v16);
  DefaultSignInAccount = v12;
  if ( v12 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 92;
      goto LABEL_31;
    }
LABEL_32:
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_24;
  }
  if ( string )
    WindowsDeleteString(string);
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v20);
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v21);
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&v19);
  wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(&pProxy);
  DefaultSignInAccount = 0;
LABEL_47:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v23);
  return (unsigned int)DefaultSignInAccount;
}

```

## disassembly

```asm
0x1800c6b00  push    rbp
0x1800c6b02  push    rbx
0x1800c6b03  push    rsi
0x1800c6b04  push    rdi
0x1800c6b05  lea     rbp, [rsp-3Fh]
0x1800c6b0a  sub     rsp, 0A8h
0x1800c6b11  mov     rax, cs:__security_cookie
0x1800c6b18  xor     rax, rsp
0x1800c6b1b  mov     [rbp+57h+var_30], rax
0x1800c6b1f  mov     rsi, rdx
0x1800c6b22  mov     [rbp+57h+var_58], 0
0x1800c6b2a  lea     rcx, [rbp+57h+var_58]
0x1800c6b2e  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800c6b33  mov     ebx, eax
0x1800c6b35  test    eax, eax
0x1800c6b37  jns     short loc_1800C6B77
0x1800c6b39  lea     rcx, WPP_GLOBAL_Control
0x1800c6b40  mov     rax, cs:WPP_GLOBAL_Control
0x1800c6b47  cmp     rax, rcx
0x1800c6b4a  jz      loc_1800C6EDD
0x1800c6b50  test    byte ptr [rax+1Ch], 1
0x1800c6b54  jz      loc_1800C6EDD
0x1800c6b5a  mov     edx, 55h ; 'U'
0x1800c6b5f  mov     r9d, ebx
0x1800c6b62  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c6b69  mov     rcx, [rax+10h]
0x1800c6b6d  call    WPP_SF_d
0x1800c6b72  jmp     loc_1800C6EDD
0x1800c6b77  mov     [rbp+57h+pProxy], 0
0x1800c6b7f  mov     [rbp+57h+var_38], 0
0x1800c6b87  mov     r9d, 40h ; '@'; unsigned int
0x1800c6b8d  lea     r8d, [r9+1]; unsigned int
0x1800c6b91  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800c6b98  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800c6b9c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c6ba1  lea     r8, [rbp+57h+pProxy]
0x1800c6ba5  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x1800c6bac  mov     rcx, [rbp+57h+var_38]
0x1800c6bb0  call    cs:__imp_RoGetActivationFactory
0x1800c6bb6  mov     ebx, eax
0x1800c6bb8  test    eax, eax
0x1800c6bba  jns     short loc_1800C6BFB
0x1800c6bbc  lea     rcx, WPP_GLOBAL_Control
0x1800c6bc3  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6bca  cmp     r10, rcx
0x1800c6bcd  jz      loc_1800C6ED3
0x1800c6bd3  test    byte ptr [r10+1Ch], 1
0x1800c6bd8  jz      loc_1800C6ED3
0x1800c6bde  mov     edx, 56h ; 'V'
0x1800c6be3  mov     r9d, eax
0x1800c6be6  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c6bed  mov     rcx, [r10+10h]
0x1800c6bf1  call    WPP_SF_d
0x1800c6bf6  jmp     loc_1800C6ED3
0x1800c6bfb  mov     [rsp+0C0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800c6c03  mov     [rsp+0C0h+pAuthInfo], 0; pAuthInfo
0x1800c6c0c  mov     [rsp+0C0h+dwImpLevel], 3; dwImpLevel
0x1800c6c14  mov     [rsp+0C0h+dwAuthnLevel], 2; dwAuthnLevel
0x1800c6c1c  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800c6c20  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800c6c23  mov     r8d, edx; dwAuthzSvc
0x1800c6c26  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800c6c2a  call    cs:__imp_CoSetProxyBlanket
0x1800c6c30  mov     ebx, eax
0x1800c6c32  test    eax, eax
0x1800c6c34  jns     short loc_1800C6C5F
0x1800c6c36  lea     rcx, WPP_GLOBAL_Control
0x1800c6c3d  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6c44  cmp     r10, rcx
0x1800c6c47  jz      loc_1800C6ED3
0x1800c6c4d  test    byte ptr [r10+1Ch], 1
0x1800c6c52  jz      loc_1800C6ED3
0x1800c6c58  mov     edx, 57h ; 'W'
0x1800c6c5d  jmp     short loc_1800C6BE3
0x1800c6c5f  mov     [rbp+57h+var_78], 0
0x1800c6c67  mov     rcx, [rbp+57h+pProxy]
0x1800c6c6b  mov     rax, [rcx]
0x1800c6c6e  mov     [rbp+57h+var_78], 0
0x1800c6c76  lea     rdx, [rbp+57h+var_78]
0x1800c6c7a  mov     rax, [rax+0E8h]
0x1800c6c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c86  mov     ebx, eax
0x1800c6c88  test    eax, eax
0x1800c6c8a  jns     short loc_1800C6CCB
0x1800c6c8c  lea     rcx, WPP_GLOBAL_Control
0x1800c6c93  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6c9a  cmp     r10, rcx
0x1800c6c9d  jz      loc_1800C6EC9
0x1800c6ca3  test    byte ptr [r10+1Ch], 1
0x1800c6ca8  jz      loc_1800C6EC9
0x1800c6cae  mov     edx, 58h ; 'X'
0x1800c6cb3  mov     r9d, eax
0x1800c6cb6  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c6cbd  mov     rcx, [r10+10h]
0x1800c6cc1  call    WPP_SF_d
0x1800c6cc6  jmp     loc_1800C6EC9
0x1800c6ccb  mov     [rbp+57h+var_68], 0
0x1800c6cd3  mov     rdi, [rbp+57h+var_78]
0x1800c6cd7  mov     rcx, rdi
0x1800c6cda  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x1800c6cdf  mov     ebx, eax
0x1800c6ce1  test    eax, eax
0x1800c6ce3  js      loc_1800C6E8D
0x1800c6ce9  mov     rax, [rdi]
0x1800c6cec  lea     rdx, [rbp+57h+var_68]
0x1800c6cf0  mov     rcx, rdi
0x1800c6cf3  mov     rax, [rax+40h]
0x1800c6cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6cfc  mov     ebx, eax
0x1800c6cfe  test    eax, eax
0x1800c6d00  js      loc_1800C6E8D
0x1800c6d06  mov     [rbp+57h+var_70], 0
0x1800c6d0e  mov     rcx, [rbp+57h+var_68]
0x1800c6d12  mov     rax, [rcx]
0x1800c6d15  mov     [rbp+57h+var_70], 0
0x1800c6d1d  lea     rdx, [rbp+57h+var_70]
0x1800c6d21  mov     rax, [rax+30h]
0x1800c6d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d2a  mov     ebx, eax
0x1800c6d2c  test    eax, eax
0x1800c6d2e  jns     short loc_1800C6D71
0x1800c6d30  lea     rcx, WPP_GLOBAL_Control
0x1800c6d37  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6d3e  cmp     r10, rcx
0x1800c6d41  jz      short loc_1800C6D63
0x1800c6d43  test    byte ptr [r10+1Ch], 1
0x1800c6d48  jz      short loc_1800C6D63
0x1800c6d4a  mov     edx, 5Ah ; 'Z'
0x1800c6d4f  mov     r9d, eax
0x1800c6d52  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c6d59  mov     rcx, [r10+10h]
0x1800c6d5d  call    WPP_SF_d
0x1800c6d62  nop
0x1800c6d63  lea     rcx, [rbp+57h+var_70]
0x1800c6d67  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6d6c  jmp     loc_1800C6EBF
0x1800c6d71  mov     rcx, [rbp+57h+var_70]
0x1800c6d75  test    rcx, rcx
0x1800c6d78  jnz     short loc_1800C6DAB
0x1800c6d7a  lea     rcx, [rbp+57h+var_70]
0x1800c6d7e  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6d83  nop
0x1800c6d84  lea     rcx, [rbp+57h+var_68]
0x1800c6d88  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6d8d  nop
0x1800c6d8e  lea     rcx, [rbp+57h+var_78]
0x1800c6d92  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6d97  nop
0x1800c6d98  lea     rcx, [rbp+57h+pProxy]
0x1800c6d9c  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6da1  mov     ebx, 80070525h
0x1800c6da6  jmp     loc_1800C6EDD
0x1800c6dab  mov     [rbp+57h+string], 0
0x1800c6db3  mov     rax, [rcx]
0x1800c6db6  lea     rdx, [rbp+57h+string]
0x1800c6dba  mov     rax, [rax+38h]
0x1800c6dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6dc3  mov     ebx, eax
0x1800c6dc5  test    eax, eax
0x1800c6dc7  jns     short loc_1800C6E14
0x1800c6dc9  lea     rcx, WPP_GLOBAL_Control
0x1800c6dd0  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6dd7  cmp     r10, rcx
0x1800c6dda  jz      short loc_1800C6DFC
0x1800c6ddc  test    byte ptr [r10+1Ch], 1
0x1800c6de1  jz      short loc_1800C6DFC
0x1800c6de3  mov     edx, 5Bh ; '['
0x1800c6de8  mov     r9d, eax
0x1800c6deb  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c6df2  mov     rcx, [r10+10h]
0x1800c6df6  call    WPP_SF_d
0x1800c6dfb  nop
0x1800c6dfc  mov     rcx, [rbp+57h+string]; string
0x1800c6e00  test    rcx, rcx
0x1800c6e03  jz      loc_1800C6D63
0x1800c6e09  call    cs:__imp_WindowsDeleteString
0x1800c6e0f  jmp     loc_1800C6D63
0x1800c6e14  xor     edx, edx; length
0x1800c6e16  mov     rcx, [rbp+57h+string]; string
0x1800c6e1a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c6e20  mov     rdx, rax; unsigned __int16 **
0x1800c6e23  mov     rcx, rsi; this
0x1800c6e26  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800c6e2b  mov     ebx, eax
0x1800c6e2d  test    eax, eax
0x1800c6e2f  jns     short loc_1800C6E52
0x1800c6e31  lea     rcx, WPP_GLOBAL_Control
0x1800c6e38  mov     r10, cs:WPP_GLOBAL_Control
0x1800c6e3f  cmp     r10, rcx
0x1800c6e42  jz      short loc_1800C6DFC
0x1800c6e44  test    byte ptr [r10+1Ch], 1
0x1800c6e49  jz      short loc_1800C6DFC
0x1800c6e4b  mov     edx, 5Ch ; '\'
0x1800c6e50  jmp     short loc_1800C6DE8
0x1800c6e52  mov     rcx, [rbp+57h+string]; string
0x1800c6e56  test    rcx, rcx
0x1800c6e59  jz      short loc_1800C6E62
0x1800c6e5b  call    cs:__imp_WindowsDeleteString
0x1800c6e61  nop
0x1800c6e62  lea     rcx, [rbp+57h+var_70]
0x1800c6e66  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6e6b  nop
0x1800c6e6c  lea     rcx, [rbp+57h+var_68]
0x1800c6e70  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6e75  nop
0x1800c6e76  lea     rcx, [rbp+57h+var_78]
0x1800c6e7a  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6e7f  nop
0x1800c6e80  lea     rcx, [rbp+57h+pProxy]
0x1800c6e84  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6e89  xor     ebx, ebx
0x1800c6e8b  jmp     short loc_1800C6EDD
0x1800c6e8d  lea     rcx, WPP_GLOBAL_Control
0x1800c6e94  mov     rax, cs:WPP_GLOBAL_Control
0x1800c6e9b  cmp     rax, rcx
0x1800c6e9e  jz      short loc_1800C6EBF
0x1800c6ea0  test    byte ptr [rax+1Ch], 1
0x1800c6ea4  jz      short loc_1800C6EBF
0x1800c6ea6  mov     edx, 59h ; 'Y'
0x1800c6eab  mov     r9d, ebx
0x1800c6eae  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c6eb5  mov     rcx, [rax+10h]
0x1800c6eb9  call    WPP_SF_d
0x1800c6ebe  nop
0x1800c6ebf  lea     rcx, [rbp+57h+var_68]
0x1800c6ec3  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6ec8  nop
0x1800c6ec9  lea     rcx, [rbp+57h+var_78]
0x1800c6ecd  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6ed2  nop
0x1800c6ed3  lea     rcx, [rbp+57h+pProxy]
0x1800c6ed7  call    ??1?$com_ptr_t@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult,wil::err_returncode_policy>(void)
0x1800c6edc  nop
0x1800c6edd  lea     rcx, [rbp+57h+var_58]
0x1800c6ee1  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800c6ee6  mov     eax, ebx
0x1800c6ee8  mov     rcx, [rbp+57h+var_30]
0x1800c6eec  xor     rcx, rsp; StackCookie
0x1800c6eef  call    __security_check_cookie
0x1800c6ef4  add     rsp, 0A8h
0x1800c6efb  pop     rdi
0x1800c6efc  pop     rsi
0x1800c6efd  pop     rbx
0x1800c6efe  pop     rbp
0x1800c6eff  retn
```
