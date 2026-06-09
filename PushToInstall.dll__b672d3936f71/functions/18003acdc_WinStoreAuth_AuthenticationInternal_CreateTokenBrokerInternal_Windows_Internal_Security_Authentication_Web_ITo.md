# WinStoreAuth::AuthenticationInternal::CreateTokenBrokerInternal(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics * *)

- ea: `0x18003acdc`
- end: `0x18003b007`
- name: `?CreateTokenBrokerInternal@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003ebd8`

## callees

- `0x1800026b0`
- `0x180010b84`
- `0x18002fbb4`
- `0x180038550`
- `0x18003acdc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ad26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ad26`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003ae8c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003aee9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003ae8c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003aee9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003ad60`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003ad60`

## string_xrefs

- `0x18003ad1f`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateTokenBrokerInternal(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics **a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  IUnknown *v8; // rcx
  int v10; // eax
  IUnknown *v11; // rcx
  int v12; // eax
  IUnknown *v13; // rcx
  IUnknown *v14; // rcx
  IUnknown *v15; // rbx
  HRESULT v16; // edi
  HRESULT v17; // eax
  IUnknown *v18; // rcx
  IUnknown *v19; // rcx
  IUnknown *v20; // rcx
  IUnknown *v21; // rcx
  IUnknown *v22; // rax
  IUnknown *v23; // rcx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-60h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-60h]
  DWORD dwAuthnLevelb; // [rsp+20h] [rbp-60h]
  IUnknown *v27; // [rsp+40h] [rbp-40h] BYREF
  IUnknown *pProxy; // [rsp+48h] [rbp-38h] BYREF
  IUnknown *v29; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_QWORD *)this = 0;
  v27 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18003B006LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v27);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)ActivationFactory,
      dwAuthnLevel);
    v8 = v27;
    if ( v27 )
    {
      v27 = 0;
      ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
    }
    return v7;
  }
  v10 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v27);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v10,
      dwAuthnLevel);
    v11 = v27;
    if ( v27 )
    {
      v27 = 0;
      ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    }
    return v7;
  }
  pProxy = 0;
  v12 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v27->lpVtbl->QueryInterface)(
          v27,
          &GUID_07650a66_66ea_489d_aa90_0dabc75f3567,
          &pProxy);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v12,
      dwAuthnLevel);
    v13 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v13->lpVtbl->Release)(v13);
    }
    v14 = v27;
    if ( v27 )
    {
      v27 = 0;
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
    }
    return v7;
  }
  v15 = pProxy;
  v16 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v16 != -2147467262 )
  {
    v29 = 0;
    if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v15->lpVtbl->QueryInterface)(
           v15,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v29) >= 0 )
    {
      v17 = CoSetProxyBlanket(v29, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
      v7 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v17,
          dwAuthnLevela);
        v18 = v29;
        if ( v29 )
        {
          v29 = 0;
          ((void (__fastcall *)(IUnknown *))v18->lpVtbl->Release)(v18);
        }
        goto LABEL_26;
      }
    }
    v19 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
    }
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v16,
        dwAuthnLevela);
      v7 = v16;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6DE,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v7,
        dwAuthnLevelb);
      v20 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
      }
      v21 = v27;
      if ( v27 )
      {
        v27 = 0;
        ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
      }
      return v7;
    }
  }
  v22 = pProxy;
  pProxy = 0;
  *(_QWORD *)this = v22;
  v23 = v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(IUnknown *))v23->lpVtbl->Release)(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18003acdc  mov     [rsp-18h+arg_8], rbx
0x18003ace1  mov     [rsp-18h+arg_10], rsi
0x18003ace6  push    rbp
0x18003ace7  push    rdi
0x18003ace8  push    r14
0x18003acea  mov     rbp, rsp
0x18003aced  sub     rsp, 80h
0x18003acf4  mov     rax, cs:__security_cookie
0x18003acfb  xor     rax, rsp
0x18003acfe  mov     [rbp+var_8], rax
0x18003ad02  mov     rsi, rcx
0x18003ad05  xor     r14d, r14d
0x18003ad08  mov     [rcx], r14
0x18003ad0b  mov     [rbp+var_40], r14
0x18003ad0f  mov     [rbp+string], r14
0x18003ad13  lea     r9, [rbp+string]; string
0x18003ad17  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003ad1b  lea     edx, [r14+40h]; length
0x18003ad1f  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18003ad26  call    cs:__imp_WindowsCreateStringReference
0x18003ad2c  test    eax, eax
0x18003ad2e  js      loc_18003AFFF
0x18003ad34  mov     rbx, [rbp+string]
0x18003ad38  mov     rcx, [rbp+var_40]
0x18003ad3c  test    rcx, rcx
0x18003ad3f  jz      short loc_18003AD52
0x18003ad41  mov     [rbp+var_40], r14
0x18003ad45  mov     rax, [rcx]
0x18003ad48  mov     rax, [rax+10h]
0x18003ad4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad51  nop
0x18003ad52  lea     r8, [rbp+var_40]
0x18003ad56  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18003ad5d  mov     rcx, rbx
0x18003ad60  call    cs:__imp_RoGetActivationFactory
0x18003ad66  mov     ebx, eax
0x18003ad68  test    eax, eax
0x18003ad6a  jns     short loc_18003ADA6
0x18003ad6c  mov     rcx, [rbp+18h]; this
0x18003ad70  mov     r9d, eax; char *
0x18003ad73  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003ad7a  mov     edx, 6D9h; void *
0x18003ad7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ad84  nop
0x18003ad85  mov     rcx, [rbp+var_40]
0x18003ad89  test    rcx, rcx
0x18003ad8c  jz      short loc_18003AD9F
0x18003ad8e  mov     [rbp+var_40], r14
0x18003ad92  mov     rax, [rcx]
0x18003ad95  mov     rax, [rax+10h]
0x18003ad99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad9e  nop
0x18003ad9f  mov     eax, ebx
0x18003ada1  jmp     loc_18003AFDB
0x18003ada6  mov     rcx, [rbp+var_40]
0x18003adaa  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18003adaf  mov     ebx, eax
0x18003adb1  test    eax, eax
0x18003adb3  jns     short loc_18003ADEA
0x18003adb5  mov     rcx, [rbp+18h]; this
0x18003adb9  mov     r9d, eax; char *
0x18003adbc  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003adc3  mov     edx, 6DAh; void *
0x18003adc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003adcd  nop
0x18003adce  mov     rcx, [rbp+var_40]
0x18003add2  test    rcx, rcx
0x18003add5  jz      short loc_18003ADE8
0x18003add7  mov     [rbp+var_40], r14
0x18003addb  mov     rax, [rcx]
0x18003adde  mov     rax, [rax+10h]
0x18003ade2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ade7  nop
0x18003ade8  jmp     short loc_18003AD9F
0x18003adea  mov     [rbp+pProxy], r14
0x18003adee  mov     rcx, [rbp+var_40]
0x18003adf2  mov     rax, [rcx]
0x18003adf5  lea     r8, [rbp+pProxy]
0x18003adf9  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x18003ae00  mov     rax, [rax]
0x18003ae03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae08  mov     ebx, eax
0x18003ae0a  test    eax, eax
0x18003ae0c  jns     short loc_18003AE60
0x18003ae0e  mov     rcx, [rbp+18h]; this
0x18003ae12  mov     r9d, eax; char *
0x18003ae15  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003ae1c  mov     edx, 6DDh; void *
0x18003ae21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ae26  nop
0x18003ae27  mov     rcx, [rbp+pProxy]
0x18003ae2b  test    rcx, rcx
0x18003ae2e  jz      short loc_18003AE41
0x18003ae30  mov     [rbp+pProxy], r14
0x18003ae34  mov     rax, [rcx]
0x18003ae37  mov     rax, [rax+10h]
0x18003ae3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae40  nop
0x18003ae41  mov     rcx, [rbp+var_40]
0x18003ae45  test    rcx, rcx
0x18003ae48  jz      short loc_18003AE5B
0x18003ae4a  mov     [rbp+var_40], r14
0x18003ae4e  mov     rax, [rcx]
0x18003ae51  mov     rax, [rax+10h]
0x18003ae55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae5a  nop
0x18003ae5b  jmp     loc_18003AD9F
0x18003ae60  mov     rbx, [rbp+pProxy]
0x18003ae64  mov     [rsp+80h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003ae6c  mov     [rsp+80h+pAuthInfo], r14; pAuthInfo
0x18003ae71  mov     [rsp+80h+dwImpLevel], 3; dwImpLevel
0x18003ae79  mov     [rsp+80h+dwAuthnLevel], r14d; int
0x18003ae7e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003ae82  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18003ae86  or      edx, r8d; dwAuthnSvc
0x18003ae89  mov     rcx, rbx; pProxy
0x18003ae8c  call    cs:__imp_CoSetProxyBlanket
0x18003ae92  mov     edi, eax
0x18003ae94  cmp     eax, 80004002h
0x18003ae99  jz      loc_18003AFB4
0x18003ae9f  mov     [rbp+var_30], r14
0x18003aea3  mov     rdx, [rbx]
0x18003aea6  mov     rax, [rdx]
0x18003aea9  lea     r8, [rbp+var_30]
0x18003aead  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003aeb4  mov     rcx, rbx
0x18003aeb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aebc  test    eax, eax
0x18003aebe  js      short loc_18003AF2A
0x18003aec0  mov     [rsp+80h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003aec8  mov     [rsp+80h+pAuthInfo], r14; pAuthInfo
0x18003aecd  mov     [rsp+80h+dwImpLevel], 3; dwImpLevel
0x18003aed5  mov     [rsp+80h+dwAuthnLevel], r14d; int
0x18003aeda  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003aede  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18003aee2  or      edx, r8d; dwAuthnSvc
0x18003aee5  mov     rcx, [rbp+var_30]; pProxy
0x18003aee9  call    cs:__imp_CoSetProxyBlanket
0x18003aeef  mov     ebx, eax
0x18003aef1  test    eax, eax
0x18003aef3  jns     short loc_18003AF2A
0x18003aef5  mov     rcx, [rbp+18h]; this
0x18003aef9  mov     r9d, eax; char *
0x18003aefc  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003af03  mov     edx, 0F0h; void *
0x18003af08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003af0d  nop
0x18003af0e  mov     rcx, [rbp+var_30]
0x18003af12  test    rcx, rcx
0x18003af15  jz      short loc_18003AF28
0x18003af17  mov     [rbp+var_30], r14
0x18003af1b  mov     rax, [rcx]
0x18003af1e  mov     rax, [rax+10h]
0x18003af22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af27  nop
0x18003af28  jmp     short loc_18003AF62
0x18003af2a  mov     rcx, [rbp+var_30]
0x18003af2e  test    rcx, rcx
0x18003af31  jz      short loc_18003AF44
0x18003af33  mov     [rbp+var_30], r14
0x18003af37  mov     rax, [rcx]
0x18003af3a  mov     rax, [rax+10h]
0x18003af3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af43  nop
0x18003af44  test    edi, edi
0x18003af46  jns     short loc_18003AFB4
0x18003af48  mov     rcx, [rbp+18h]; this
0x18003af4c  mov     r9d, edi; char *
0x18003af4f  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003af56  mov     edx, 0F3h; void *
0x18003af5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003af60  mov     ebx, edi
0x18003af62  mov     rcx, [rbp+18h]; this
0x18003af66  mov     r9d, ebx; char *
0x18003af69  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003af70  mov     edx, 6DEh; void *
0x18003af75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003af7a  nop
0x18003af7b  mov     rcx, [rbp+pProxy]
0x18003af7f  test    rcx, rcx
0x18003af82  jz      short loc_18003AF95
0x18003af84  mov     [rbp+pProxy], r14
0x18003af88  mov     rax, [rcx]
0x18003af8b  mov     rax, [rax+10h]
0x18003af8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af94  nop
0x18003af95  mov     rcx, [rbp+var_40]
0x18003af99  test    rcx, rcx
0x18003af9c  jz      short loc_18003AFAF
0x18003af9e  mov     [rbp+var_40], r14
0x18003afa2  mov     rdx, [rcx]
0x18003afa5  mov     rax, [rdx+10h]
0x18003afa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afae  nop
0x18003afaf  jmp     loc_18003AD9F
0x18003afb4  mov     rax, [rbp+pProxy]
0x18003afb8  mov     [rbp+pProxy], r14
0x18003afbc  mov     [rsi], rax
0x18003afbf  mov     rcx, [rbp+var_40]
0x18003afc3  test    rcx, rcx
0x18003afc6  jz      short loc_18003AFD9
0x18003afc8  mov     [rbp+var_40], r14
0x18003afcc  mov     rax, [rcx]
0x18003afcf  mov     rax, [rax+10h]
0x18003afd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afd8  nop
0x18003afd9  xor     eax, eax
0x18003afdb  mov     rcx, [rbp+var_8]
0x18003afdf  xor     rcx, rsp; StackCookie
0x18003afe2  call    __security_check_cookie
0x18003afe7  lea     r11, [rsp+80h+var_s0]
0x18003afef  mov     rbx, [r11+28h]
0x18003aff3  mov     rsi, [r11+30h]
0x18003aff7  mov     rsp, r11
0x18003affa  pop     r14
0x18003affc  pop     rdi
0x18003affd  pop     rbp
0x18003affe  retn
0x18003afff  mov     ecx, eax; this
0x18003b001  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
