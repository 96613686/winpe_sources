# WinStoreAuth::AuthenticationInternal::GetAccountProvider(HSTRING__ *,HSTRING__ *,Windows::System::IUser *,Windows::Security::Credentials::IWebAccountProvider * *)

- ea: `0x18003e414`
- end: `0x18003e81f`
- name: `?GetAccountProvider@AuthenticationInternal@WinStoreAuth@@YAJPEAUHSTRING__@@0PEAUIUser@System@Windows@@PEAPEAUIWebAccountProvider@Credentials@Security@6@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, HSTRING, HSTRING, struct Windows::System::IUser *, struct Windows::Security::Credentials::IWebAccountProvider **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003d56c`
- `0x18003e828`
- `0x180040ef8`

## callees

- `0x180010b84`
- `0x180038220`
- `0x180038550`
- `0x18003a9a8`
- `0x18003e414`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003e596`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003e5f3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003e596`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003e5f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetAccountProvider(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **a2,
        IUnknown *a3,
        struct Windows::System::IUser *a4)
{
  int TokenBroker; // eax
  unsigned int v8; // ebx
  __int64 *v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // edi
  IUnknown *v14; // rcx
  int v15; // eax
  IUnknown *v16; // rcx
  IUnknown *v17; // rdi
  HRESULT v18; // esi
  HRESULT v19; // eax
  IUnknown *v20; // rcx
  IUnknown *v21; // rcx
  IUnknown *v22; // rcx
  IUnknown *v23; // rcx
  int v24; // eax
  IUnknown *v25; // rcx
  IUnknown *v26; // rcx
  IUnknown *v27; // rax
  int v28; // eax
  IUnknown *v29; // rcx
  IUnknown *v30; // rcx
  IUnknown *v31; // rcx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-30h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-30h]
  DWORD dwAuthnLevelb; // [rsp+20h] [rbp-30h]
  IUnknown *v35; // [rsp+40h] [rbp-10h] BYREF
  __int64 *v36; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  IUnknown *pProxy; // [rsp+90h] [rbp+40h] BYREF
  IUnknown *v39; // [rsp+98h] [rbp+48h] BYREF

  pProxy = a3;
  *(_QWORD *)a4 = 0;
  v36 = 0;
  TokenBroker = WinStoreAuth::AuthenticationInternal::CreateTokenBroker(
                  (WinStoreAuth::AuthenticationInternal *)&v36,
                  a2);
  v8 = TokenBroker;
  if ( TokenBroker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)TokenBroker,
      dwAuthnLevel);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    return v8;
  }
  pProxy = 0;
  v10 = v36;
  v11 = *v36;
  if ( a2 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64 *, WinStoreAuth::AuthenticationInternal *, struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **, IUnknown **))(v11 + 96))(
            v36,
            this,
            a2,
            &pProxy);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6FC,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v12,
        dwAuthnLevel);
      v14 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
      return v13;
    }
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(__int64 *, WinStoreAuth::AuthenticationInternal *, IUnknown **))(v11 + 88))(
            v36,
            this,
            &pProxy);
    v13 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x700,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v15,
        dwAuthnLevel);
      v16 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v16->lpVtbl->Release)(v16);
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
      return v13;
    }
  }
  v39 = 0;
  v17 = pProxy;
  v18 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
  if ( v18 != -2147467262 )
  {
    v35 = 0;
    if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v17->lpVtbl->QueryInterface)(
           v17,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v35) >= 0 )
    {
      v19 = CoSetProxyBlanket(v35, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
      v13 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v19,
          dwAuthnLevela);
        v20 = v35;
        if ( v35 )
        {
          v35 = 0;
          ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
        }
        goto LABEL_28;
      }
    }
    v21 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
    }
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v18,
        dwAuthnLevela);
      v13 = v18;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x705,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)v13,
        dwAuthnLevelb);
      v22 = v39;
      if ( v39 )
      {
        v39 = 0;
        ((void (__fastcall *)(IUnknown *))v22->lpVtbl->Release)(v22);
      }
      v23 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v23->lpVtbl->Release)(v23);
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
      return v13;
    }
  }
  v24 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
          (__int64)pProxy,
          (__int64 *)&v39);
  v13 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x706,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v24,
      dwAuthnLevela);
    v25 = v39;
    if ( v39 )
    {
      v39 = 0;
      ((void (__fastcall *)(IUnknown *))v25->lpVtbl->Release)(v25);
    }
    v26 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v26->lpVtbl->Release)(v26);
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    return v13;
  }
  v27 = v39;
  if ( v39 )
  {
    v28 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v39);
    v13 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x709,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v28,
        dwAuthnLevela);
      v29 = v39;
      if ( v39 )
      {
        v39 = 0;
        ((void (__fastcall *)(IUnknown *))v29->lpVtbl->Release)(v29);
      }
      v30 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
      return v13;
    }
    v27 = v39;
  }
  v39 = 0;
  *(_QWORD *)a4 = v27;
  v31 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v31->lpVtbl->Release)(v31);
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
  return 0;
}

```

## disassembly

```asm
0x18003e414  mov     [rsp-28h+arg_0], rbx
0x18003e419  mov     [rsp-28h+pProxy], r8
0x18003e41e  push    rbp
0x18003e41f  push    rsi
0x18003e420  push    rdi
0x18003e421  push    r14
0x18003e423  push    r15
0x18003e425  mov     rbp, rsp
0x18003e428  sub     rsp, 50h
0x18003e42c  mov     r14, r9
0x18003e42f  mov     rdi, rdx
0x18003e432  mov     rsi, rcx
0x18003e435  xor     r15d, r15d
0x18003e438  mov     [r9], r15
0x18003e43b  mov     [rbp+var_8], r15
0x18003e43f  lea     rcx, [rbp+var_8]; this
0x18003e443  call    ?CreateTokenBroker@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenBroker(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics * *)
0x18003e448  mov     ebx, eax
0x18003e44a  test    eax, eax
0x18003e44c  jns     short loc_18003E484
0x18003e44e  mov     rcx, [rbp+28h]; this
0x18003e452  mov     r9d, eax; char *
0x18003e455  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e45c  mov     edx, 6EEh; void *
0x18003e461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e466  nop
0x18003e467  mov     rcx, [rbp+var_8]
0x18003e46b  test    rcx, rcx
0x18003e46e  jz      short loc_18003E47D
0x18003e470  mov     rax, [rcx]
0x18003e473  mov     rax, [rax+10h]
0x18003e477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e47c  nop
0x18003e47d  mov     eax, ebx
0x18003e47f  jmp     loc_18003E80B
0x18003e484  mov     [rbp+pProxy], r15
0x18003e488  mov     rbx, [rbp+var_8]
0x18003e48c  mov     rax, [rbx]
0x18003e48f  test    rdi, rdi
0x18003e492  jz      short loc_18003E503
0x18003e494  lea     r9, [rbp+pProxy]
0x18003e498  mov     r8, rdi
0x18003e49b  mov     rdx, rsi
0x18003e49e  mov     rcx, rbx
0x18003e4a1  mov     rax, [rax+60h]
0x18003e4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4aa  mov     edi, eax
0x18003e4ac  test    eax, eax
0x18003e4ae  jns     loc_18003E566
0x18003e4b4  mov     rcx, [rbp+28h]; this
0x18003e4b8  mov     r9d, eax; char *
0x18003e4bb  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e4c2  mov     edx, 6FCh; void *
0x18003e4c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e4cc  nop
0x18003e4cd  mov     rcx, [rbp+pProxy]
0x18003e4d1  test    rcx, rcx
0x18003e4d4  jz      short loc_18003E4E7
0x18003e4d6  mov     [rbp+pProxy], r15
0x18003e4da  mov     rax, [rcx]
0x18003e4dd  mov     rax, [rax+10h]
0x18003e4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4e6  nop
0x18003e4e7  test    rbx, rbx
0x18003e4ea  jz      short loc_18003E4FC
0x18003e4ec  mov     rax, [rbx]
0x18003e4ef  mov     rcx, rbx
0x18003e4f2  mov     rax, [rax+10h]
0x18003e4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4fb  nop
0x18003e4fc  mov     eax, edi
0x18003e4fe  jmp     loc_18003E80B
0x18003e503  lea     r8, [rbp+pProxy]
0x18003e507  mov     rdx, rsi
0x18003e50a  mov     rcx, rbx
0x18003e50d  mov     rax, [rax+58h]
0x18003e511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e516  mov     edi, eax
0x18003e518  test    eax, eax
0x18003e51a  jns     short loc_18003E566
0x18003e51c  mov     rcx, [rbp+28h]; this
0x18003e520  mov     r9d, eax; char *
0x18003e523  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e52a  mov     edx, 700h; void *
0x18003e52f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e534  nop
0x18003e535  mov     rcx, [rbp+pProxy]
0x18003e539  test    rcx, rcx
0x18003e53c  jz      short loc_18003E54F
0x18003e53e  mov     [rbp+pProxy], r15
0x18003e542  mov     rax, [rcx]
0x18003e545  mov     rax, [rax+10h]
0x18003e549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e54e  nop
0x18003e54f  test    rbx, rbx
0x18003e552  jz      short loc_18003E564
0x18003e554  mov     rax, [rbx]
0x18003e557  mov     rcx, rbx
0x18003e55a  mov     rax, [rax+10h]
0x18003e55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e563  nop
0x18003e564  jmp     short loc_18003E4FC
0x18003e566  mov     [rbp+arg_18], r15
0x18003e56a  mov     rdi, [rbp+pProxy]
0x18003e56e  mov     [rsp+50h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003e576  mov     [rsp+50h+pAuthInfo], r15; pAuthInfo
0x18003e57b  mov     [rsp+50h+dwImpLevel], 3; dwImpLevel
0x18003e583  mov     [rsp+50h+dwAuthnLevel], r15d; int
0x18003e588  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003e58c  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18003e590  or      edx, r8d; dwAuthnSvc
0x18003e593  mov     rcx, rdi; pProxy
0x18003e596  call    cs:__imp_CoSetProxyBlanket
0x18003e59c  mov     esi, eax
0x18003e59e  cmp     eax, 80004002h
0x18003e5a3  jz      loc_18003E6D7
0x18003e5a9  mov     [rbp+var_10], r15
0x18003e5ad  mov     rdx, [rdi]
0x18003e5b0  mov     rax, [rdx]
0x18003e5b3  lea     r8, [rbp+var_10]
0x18003e5b7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003e5be  mov     rcx, rdi
0x18003e5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5c6  test    eax, eax
0x18003e5c8  js      short loc_18003E634
0x18003e5ca  mov     [rsp+50h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18003e5d2  mov     [rsp+50h+pAuthInfo], r15; pAuthInfo
0x18003e5d7  mov     [rsp+50h+dwImpLevel], 3; dwImpLevel
0x18003e5df  mov     [rsp+50h+dwAuthnLevel], r15d; int
0x18003e5e4  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003e5e8  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18003e5ec  or      edx, r8d; dwAuthnSvc
0x18003e5ef  mov     rcx, [rbp+var_10]; pProxy
0x18003e5f3  call    cs:__imp_CoSetProxyBlanket
0x18003e5f9  mov     edi, eax
0x18003e5fb  test    eax, eax
0x18003e5fd  jns     short loc_18003E634
0x18003e5ff  mov     rcx, [rbp+28h]; this
0x18003e603  mov     r9d, eax; char *
0x18003e606  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e60d  mov     edx, 0F0h; void *
0x18003e612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e617  nop
0x18003e618  mov     rcx, [rbp+var_10]
0x18003e61c  test    rcx, rcx
0x18003e61f  jz      short loc_18003E632
0x18003e621  mov     [rbp+var_10], r15
0x18003e625  mov     rax, [rcx]
0x18003e628  mov     rax, [rax+10h]
0x18003e62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e631  nop
0x18003e632  jmp     short loc_18003E670
0x18003e634  mov     rcx, [rbp+var_10]
0x18003e638  test    rcx, rcx
0x18003e63b  jz      short loc_18003E64E
0x18003e63d  mov     [rbp+var_10], r15
0x18003e641  mov     rax, [rcx]
0x18003e644  mov     rax, [rax+10h]
0x18003e648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e64d  nop
0x18003e64e  test    esi, esi
0x18003e650  jns     loc_18003E6D7
0x18003e656  mov     rcx, [rbp+28h]; this
0x18003e65a  mov     r9d, esi; char *
0x18003e65d  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e664  mov     edx, 0F3h; void *
0x18003e669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e66e  mov     edi, esi
0x18003e670  mov     rcx, [rbp+28h]; this
0x18003e674  mov     r9d, edi; char *
0x18003e677  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e67e  mov     edx, 705h; void *
0x18003e683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e688  nop
0x18003e689  mov     rcx, [rbp+arg_18]
0x18003e68d  test    rcx, rcx
0x18003e690  jz      short loc_18003E6A3
0x18003e692  mov     [rbp+arg_18], r15
0x18003e696  mov     rax, [rcx]
0x18003e699  mov     rax, [rax+10h]
0x18003e69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6a2  nop
0x18003e6a3  mov     rcx, [rbp+pProxy]
0x18003e6a7  test    rcx, rcx
0x18003e6aa  jz      short loc_18003E6BD
0x18003e6ac  mov     [rbp+pProxy], r15
0x18003e6b0  mov     rax, [rcx]
0x18003e6b3  mov     rax, [rax+10h]
0x18003e6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6bc  nop
0x18003e6bd  test    rbx, rbx
0x18003e6c0  jz      short loc_18003E6D2
0x18003e6c2  mov     rcx, [rbx]
0x18003e6c5  mov     rax, [rcx+10h]
0x18003e6c9  mov     rcx, rbx
0x18003e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6d1  nop
0x18003e6d2  jmp     loc_18003E4FC
0x18003e6d7  lea     rdx, [rbp+arg_18]
0x18003e6db  mov     rcx, [rbp+pProxy]
0x18003e6df  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAXK@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *,ulong)
0x18003e6e4  mov     edi, eax
0x18003e6e6  test    eax, eax
0x18003e6e8  jns     short loc_18003E751
0x18003e6ea  mov     rcx, [rbp+28h]; this
0x18003e6ee  mov     r9d, eax; char *
0x18003e6f1  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e6f8  mov     edx, 706h; void *
0x18003e6fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e702  nop
0x18003e703  mov     rcx, [rbp+arg_18]
0x18003e707  test    rcx, rcx
0x18003e70a  jz      short loc_18003E71D
0x18003e70c  mov     [rbp+arg_18], r15
0x18003e710  mov     rax, [rcx]
0x18003e713  mov     rax, [rax+10h]
0x18003e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e71c  nop
0x18003e71d  mov     rcx, [rbp+pProxy]
0x18003e721  test    rcx, rcx
0x18003e724  jz      short loc_18003E737
0x18003e726  mov     [rbp+pProxy], r15
0x18003e72a  mov     rax, [rcx]
0x18003e72d  mov     rax, [rax+10h]
0x18003e731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e736  nop
0x18003e737  test    rbx, rbx
0x18003e73a  jz      short loc_18003E74C
0x18003e73c  mov     rax, [rbx]
0x18003e73f  mov     rcx, rbx
0x18003e742  mov     rax, [rax+10h]
0x18003e746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e74b  nop
0x18003e74c  jmp     loc_18003E4FC
0x18003e751  mov     rax, [rbp+arg_18]
0x18003e755  test    rax, rax
0x18003e758  jz      short loc_18003E7D3
0x18003e75a  mov     rcx, rax
0x18003e75d  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18003e762  mov     edi, eax
0x18003e764  test    eax, eax
0x18003e766  jns     short loc_18003E7CF
0x18003e768  mov     rcx, [rbp+28h]; this
0x18003e76c  mov     r9d, eax; char *
0x18003e76f  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003e776  mov     edx, 709h; void *
0x18003e77b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e780  nop
0x18003e781  mov     rcx, [rbp+arg_18]
0x18003e785  test    rcx, rcx
0x18003e788  jz      short loc_18003E79B
0x18003e78a  mov     [rbp+arg_18], r15
0x18003e78e  mov     rax, [rcx]
0x18003e791  mov     rax, [rax+10h]
0x18003e795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e79a  nop
0x18003e79b  mov     rcx, [rbp+pProxy]
0x18003e79f  test    rcx, rcx
0x18003e7a2  jz      short loc_18003E7B5
0x18003e7a4  mov     [rbp+pProxy], r15
0x18003e7a8  mov     rax, [rcx]
0x18003e7ab  mov     rax, [rax+10h]
0x18003e7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7b4  nop
0x18003e7b5  test    rbx, rbx
0x18003e7b8  jz      short loc_18003E7CA
0x18003e7ba  mov     rax, [rbx]
0x18003e7bd  mov     rcx, rbx
0x18003e7c0  mov     rax, [rax+10h]
0x18003e7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7c9  nop
0x18003e7ca  jmp     loc_18003E4FC
0x18003e7cf  mov     rax, [rbp+arg_18]
0x18003e7d3  mov     [rbp+arg_18], r15
0x18003e7d7  mov     [r14], rax
0x18003e7da  mov     rcx, [rbp+pProxy]
0x18003e7de  test    rcx, rcx
0x18003e7e1  jz      short loc_18003E7F4
0x18003e7e3  mov     [rbp+pProxy], r15
0x18003e7e7  mov     rax, [rcx]
0x18003e7ea  mov     rax, [rax+10h]
0x18003e7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7f3  nop
0x18003e7f4  test    rbx, rbx
0x18003e7f7  jz      short loc_18003E809
0x18003e7f9  mov     rax, [rbx]
0x18003e7fc  mov     rcx, rbx
0x18003e7ff  mov     rax, [rax+10h]
0x18003e803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e808  nop
0x18003e809  xor     eax, eax
0x18003e80b  mov     rbx, [rsp+50h+arg_0]
0x18003e813  add     rsp, 50h
0x18003e817  pop     r15
0x18003e819  pop     r14
0x18003e81b  pop     rdi
0x18003e81c  pop     rsi
0x18003e81d  pop     rbp
0x18003e81e  retn
```
