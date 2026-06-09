# WinStoreAuth::AuthenticationInternal::CreateTokenBroker(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics * *)

- ea: `0x18003a9a8`
- end: `0x18003acd3`
- name: `?CreateTokenBroker@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003d56c`
- `0x18003e414`
- `0x18003ebd8`
- `0x180040ef8`

## callees

- `0x1800026b0`
- `0x180010b84`
- `0x18002fbb4`
- `0x180038550`
- `0x18003a9a8`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a9f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003a9f2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003ab58`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003abb5`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003ab58`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003abb5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003aa2c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003aa2c`

## string_xrefs

- `0x18003a9eb`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateTokenBroker(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **a2)
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
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18003ACD2LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v27);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C5,
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
      (void *)0x6C6,
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
          &GUID_6aca7c92_a581_4479_9c10_752eff44fd34,
          &pProxy);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C9,
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
        (void *)0x6CA,
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
0x18003a9a8  mov     [rsp-18h+arg_8], rbx
0x18003a9ad  mov     [rsp-18h+arg_10], rsi
0x18003a9b2  push    rbp
0x18003a9b3  push    rdi
0x18003a9b4  push    r14
0x18003a9b6  mov     rbp, rsp
0x18003a9b9  sub     rsp, 80h
0x18003a9c0  mov     rax, cs:__security_cookie
0x18003a9c7  xor     rax, rsp
0x18003a9ca  mov     [rbp+var_8], rax
0x18003a9ce  mov     rsi, rcx
0x18003a9d1  xor     r14d, r14d
0x18003a9d4  mov     [rcx], r14
0x18003a9d7  mov     [rbp+var_40], r14
0x18003a9db  mov     [rbp+string], r14
0x18003a9df  lea     r9, [rbp+string]; string
0x18003a9e3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003a9e7  lea     edx, [r14+45h]; length
0x18003a9eb  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18003a9f2  call    cs:__imp_WindowsCreateStringReference
0x18003a9f8  test    eax, eax
0x18003a9fa  js      loc_18003ACCB
0x18003aa00  mov     rbx, [rbp+string]
0x18003aa04  mov     rcx, [rbp+var_40]
0x18003aa08  test    rcx, rcx
0x18003aa0b  jz      short loc_18003AA1E
0x18003aa0d  mov     [rbp+var_40], r14
0x18003aa11  mov     rax, [rcx]
0x18003aa14  mov     rax, [rax+10h]
0x18003aa18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa1d  nop
0x18003aa1e  lea     r8, [rbp+var_40]
0x18003aa22  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18003aa29  mov     rcx, rbx
0x18003aa2c  call    cs:__imp_RoGetActivationFactory
0x18003aa32  mov     ebx, eax
0x18003aa34  test    eax, eax
0x18003aa36  jns     short loc_18003AA72
0x18003aa38  mov     rcx, [rbp+18h]; this
0x18003aa3c  mov     r9d, eax; char *
0x18003aa3f  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003aa46  mov     edx, 6C5h; void *
0x18003aa4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa50  nop
0x18003aa51  mov     rcx, [rbp+var_40]
0x18003aa55  test    rcx, rcx
0x18003aa58  jz      short loc_18003AA6B
0x18003aa5a  mov     [rbp+var_40], r14
0x18003aa5e  mov     rax, [rcx]
0x18003aa61  mov     rax, [rax+10h]
0x18003aa65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa6a  nop
0x18003aa6b  mov     eax, ebx
0x18003aa6d  jmp     loc_18003ACA7
0x18003aa72  mov     rcx, [rbp+var_40]
0x18003aa76  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18003aa7b  mov     ebx, eax
0x18003aa7d  test    eax, eax
0x18003aa7f  jns     short loc_18003AAB6
0x18003aa81  mov     rcx, [rbp+18h]; this
0x18003aa85  mov     r9d, eax; char *
0x18003aa88  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003aa8f  mov     edx, 6C6h; void *
0x18003aa94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa99  nop
0x18003aa9a  mov     rcx, [rbp+var_40]
0x18003aa9e  test    rcx, rcx
0x18003aaa1  jz      short loc_18003AAB4
0x18003aaa3  mov     [rbp+var_40], r14
0x18003aaa7  mov     rax, [rcx]
0x18003aaaa  mov     rax, [rax+10h]
0x18003aaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aab3  nop
0x18003aab4  jmp     short loc_18003AA6B
0x18003aab6  mov     [rbp+pProxy], r14
0x18003aaba  mov     rcx, [rbp+var_40]
0x18003aabe  mov     rax, [rcx]
0x18003aac1  lea     r8, [rbp+pProxy]
0x18003aac5  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18003aacc  mov     rax, [rax]
0x18003aacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aad4  mov     ebx, eax
0x18003aad6  test    eax, eax
0x18003aad8  jns     short loc_18003AB2C
0x18003aada  mov     rcx, [rbp+18h]; this
0x18003aade  mov     r9d, eax; char *
0x18003aae1  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003aae8  mov     edx, 6C9h; void *
0x18003aaed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aaf2  nop
0x18003aaf3  mov     rcx, [rbp+pProxy]
0x18003aaf7  test    rcx, rcx
0x18003aafa  jz      short loc_18003AB0D
0x18003aafc  mov     [rbp+pProxy], r14
0x18003ab00  mov     rax, [rcx]
0x18003ab03  mov     rax, [rax+10h]
0x18003ab07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab0c  nop
0x18003ab0d  mov     rcx, [rbp+var_40]
0x18003ab11  test    rcx, rcx
0x18003ab14  jz      short loc_18003AB27
0x18003ab16  mov     [rbp+var_40], r14
0x18003ab1a  mov     rax, [rcx]
0x18003ab1d  mov     rax, [rax+10h]
0x18003ab21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab26  nop
0x18003ab27  jmp     loc_18003AA6B
0x18003ab2c  mov     rbx, [rbp+pProxy]
0x18003ab30  mov     [rsp+80h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003ab38  mov     [rsp+80h+pAuthInfo], r14; pAuthInfo
0x18003ab3d  mov     [rsp+80h+dwImpLevel], 3; dwImpLevel
0x18003ab45  mov     [rsp+80h+dwAuthnLevel], r14d; int
0x18003ab4a  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003ab4e  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18003ab52  or      edx, r8d; dwAuthnSvc
0x18003ab55  mov     rcx, rbx; pProxy
0x18003ab58  call    cs:__imp_CoSetProxyBlanket
0x18003ab5e  mov     edi, eax
0x18003ab60  cmp     eax, 80004002h
0x18003ab65  jz      loc_18003AC80
0x18003ab6b  mov     [rbp+var_30], r14
0x18003ab6f  mov     rdx, [rbx]
0x18003ab72  mov     rax, [rdx]
0x18003ab75  lea     r8, [rbp+var_30]
0x18003ab79  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003ab80  mov     rcx, rbx
0x18003ab83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab88  test    eax, eax
0x18003ab8a  js      short loc_18003ABF6
0x18003ab8c  mov     [rsp+80h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003ab94  mov     [rsp+80h+pAuthInfo], r14; pAuthInfo
0x18003ab99  mov     [rsp+80h+dwImpLevel], 3; dwImpLevel
0x18003aba1  mov     [rsp+80h+dwAuthnLevel], r14d; int
0x18003aba6  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003abaa  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18003abae  or      edx, r8d; dwAuthnSvc
0x18003abb1  mov     rcx, [rbp+var_30]; pProxy
0x18003abb5  call    cs:__imp_CoSetProxyBlanket
0x18003abbb  mov     ebx, eax
0x18003abbd  test    eax, eax
0x18003abbf  jns     short loc_18003ABF6
0x18003abc1  mov     rcx, [rbp+18h]; this
0x18003abc5  mov     r9d, eax; char *
0x18003abc8  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003abcf  mov     edx, 0F0h; void *
0x18003abd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003abd9  nop
0x18003abda  mov     rcx, [rbp+var_30]
0x18003abde  test    rcx, rcx
0x18003abe1  jz      short loc_18003ABF4
0x18003abe3  mov     [rbp+var_30], r14
0x18003abe7  mov     rax, [rcx]
0x18003abea  mov     rax, [rax+10h]
0x18003abee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abf3  nop
0x18003abf4  jmp     short loc_18003AC2E
0x18003abf6  mov     rcx, [rbp+var_30]
0x18003abfa  test    rcx, rcx
0x18003abfd  jz      short loc_18003AC10
0x18003abff  mov     [rbp+var_30], r14
0x18003ac03  mov     rax, [rcx]
0x18003ac06  mov     rax, [rax+10h]
0x18003ac0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac0f  nop
0x18003ac10  test    edi, edi
0x18003ac12  jns     short loc_18003AC80
0x18003ac14  mov     rcx, [rbp+18h]; this
0x18003ac18  mov     r9d, edi; char *
0x18003ac1b  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003ac22  mov     edx, 0F3h; void *
0x18003ac27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac2c  mov     ebx, edi
0x18003ac2e  mov     rcx, [rbp+18h]; this
0x18003ac32  mov     r9d, ebx; char *
0x18003ac35  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003ac3c  mov     edx, 6CAh; void *
0x18003ac41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac46  nop
0x18003ac47  mov     rcx, [rbp+pProxy]
0x18003ac4b  test    rcx, rcx
0x18003ac4e  jz      short loc_18003AC61
0x18003ac50  mov     [rbp+pProxy], r14
0x18003ac54  mov     rax, [rcx]
0x18003ac57  mov     rax, [rax+10h]
0x18003ac5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac60  nop
0x18003ac61  mov     rcx, [rbp+var_40]
0x18003ac65  test    rcx, rcx
0x18003ac68  jz      short loc_18003AC7B
0x18003ac6a  mov     [rbp+var_40], r14
0x18003ac6e  mov     rdx, [rcx]
0x18003ac71  mov     rax, [rdx+10h]
0x18003ac75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac7a  nop
0x18003ac7b  jmp     loc_18003AA6B
0x18003ac80  mov     rax, [rbp+pProxy]
0x18003ac84  mov     [rbp+pProxy], r14
0x18003ac88  mov     [rsi], rax
0x18003ac8b  mov     rcx, [rbp+var_40]
0x18003ac8f  test    rcx, rcx
0x18003ac92  jz      short loc_18003ACA5
0x18003ac94  mov     [rbp+var_40], r14
0x18003ac98  mov     rax, [rcx]
0x18003ac9b  mov     rax, [rax+10h]
0x18003ac9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aca4  nop
0x18003aca5  xor     eax, eax
0x18003aca7  mov     rcx, [rbp+var_8]
0x18003acab  xor     rcx, rsp; StackCookie
0x18003acae  call    __security_check_cookie
0x18003acb3  lea     r11, [rsp+80h+var_s0]
0x18003acbb  mov     rbx, [r11+28h]
0x18003acbf  mov     rsi, [r11+30h]
0x18003acc3  mov     rsp, r11
0x18003acc6  pop     r14
0x18003acc8  pop     rdi
0x18003acc9  pop     rbp
0x18003acca  retn
0x18003accb  mov     ecx, eax; this
0x18003accd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
