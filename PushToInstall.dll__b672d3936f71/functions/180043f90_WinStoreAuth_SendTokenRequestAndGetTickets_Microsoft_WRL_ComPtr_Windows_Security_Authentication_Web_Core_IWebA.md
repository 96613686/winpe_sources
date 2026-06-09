# WinStoreAuth::_SendTokenRequestAndGetTickets(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> const &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> const &,WinStoreAuth::PromptType,HWND__ *,Windows::Security::Credentials::IWebAccount *,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)

- ea: `0x180043f90`
- end: `0x180044413`
- name: `?_SendTokenRequestAndGetTickets@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@34@W4PromptType@1@PEAUHWND__@@PEAUIWebAccount@Credentials@Security@Windows@@PEAUTicketHolder@1@_KPEA_KPEAUIUser@System@Windows@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Z`
- size: `1155`
- prototype: `__int64 __fastcall(__int64 **, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, int, IUnknown *pProxy)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043bb0`

## callees

- `0x180010b84`
- `0x18003827c`
- `0x180038550`
- `0x1800393f8`
- `0x18003c52c`
- `0x180043f90`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044086`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044086`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043fcb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043fcb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800440bf`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180044128`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800440bf`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180044128`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinStoreAuth::_SendTokenRequestAndGetTickets(
        __int64 **a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        IUnknown *pProxy)
{
  IUnknown **v12; // rsi
  char i; // r14
  __int64 *v14; // rbx
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64 *, _QWORD, __int64, IUnknown **); // rdi
  IUnknown *v17; // rcx
  int v18; // eax
  __int64 (__fastcall *v19)(__int64 *, _QWORD, IUnknown **); // rdi
  IUnknown *v20; // rcx
  unsigned int v21; // ebx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  IUnknown *v25; // rbx
  HRESULT v26; // edi
  HRESULT v27; // eax
  IUnknown *v28; // rcx
  IUnknown *v29; // rcx
  IUnknown *v30; // rcx
  IUnknown *v31; // rcx
  int v32; // eax
  DWORD v33; // edx
  __int64 v34; // r8
  int v35; // r9d
  int v36; // eax
  IUnknown *v37; // rcx
  IUnknown *v38; // rcx
  IUnknown *v39; // rcx
  IUnknown *v40; // rcx
  IUnknown *v41; // rcx
  IUnknown *v42; // rcx
  IUnknown *v43; // rcx
  IUnknown *v44; // rcx
  IUnknown *v45; // rcx
  IUnknown *v47; // rcx
  int dwAuthnLevel; // [rsp+20h] [rbp-20h]
  int dwAuthnLevela; // [rsp+20h] [rbp-20h]
  int dwAuthnLevelb; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  IUnknown *v52; // [rsp+88h] [rbp+48h] BYREF

  v52 = 0;
  v12 = (IUnknown **)pProxy;
  pProxy->lpVtbl = 0;
  for ( i = 0; ; i = 1 )
  {
    AcquireSRWLockExclusive(&WinStoreAuth::g_srwTickets);
    v14 = *a1;
    v15 = **a1;
    if ( a5 )
    {
      v16 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, IUnknown **))(v15 + 56);
      v17 = v52;
      if ( v52 )
      {
        v52 = 0;
        ((void (__fastcall *)(IUnknown *))v17->lpVtbl->Release)(v17);
      }
      v18 = v16(v14, *a2, a5, &v52);
    }
    else
    {
      v19 = *(__int64 (__fastcall **)(__int64 *, _QWORD, IUnknown **))(v15 + 48);
      v20 = v52;
      if ( v52 )
      {
        v52 = 0;
        ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
      }
      v18 = v19(v14, *a2, &v52);
    }
    v21 = v18;
    if ( v18 >= 0 )
    {
      v22 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v52);
      v21 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x967,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v22,
          dwAuthnLevel);
        v38 = v52;
        if ( v52 )
        {
          v52 = 0;
          ((void (__fastcall *)(IUnknown *))v38->lpVtbl->Release)(v38);
        }
        return v21;
      }
      v21 = BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *>(
              (__int64)v52,
              (__int64)v12,
              v23,
              v24,
              0x7530u);
    }
    ReleaseSRWLockExclusive(&WinStoreAuth::g_srwTickets);
    if ( (v21 & 0x80000000) == 0 )
    {
      v25 = *v12;
      v26 = CoSetProxyBlanket(*v12, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
      if ( v26 != -2147467262 )
      {
        pProxy = 0;
        if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v25->lpVtbl->QueryInterface)(
               v25,
               &GUID_00000000_0000_0000_c000_000000000046,
               &pProxy) >= 0 )
        {
          v27 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
          v21 = v27;
          if ( v27 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF0,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)(unsigned int)v27,
              dwAuthnLevela);
            v39 = pProxy;
            if ( pProxy )
            {
              pProxy = 0;
              ((void (__fastcall *)(IUnknown *))v39->lpVtbl->Release)(v39);
            }
LABEL_40:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x985,
              (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
              (const char *)v21,
              dwAuthnLevelb);
            v40 = v52;
            if ( v52 )
            {
              v52 = 0;
              ((void (__fastcall *)(IUnknown *))v40->lpVtbl->Release)(v40);
            }
            return v21;
          }
        }
        v28 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v28->lpVtbl->Release)(v28);
        }
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF3,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v26,
            dwAuthnLevela);
          v21 = v26;
          goto LABEL_40;
        }
      }
      v29 = *v12;
      pProxy = v29;
      if ( v29 )
        ((void (__fastcall *)(IUnknown *))v29->lpVtbl->AddRef)(v29);
      dwAuthnLevel = 0;
      v21 = WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(&pProxy, a6, a7, a8);
      v30 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
      }
    }
    if ( i || (v21 & 0x80000000) == 0 )
      break;
    if ( v21 == -2147023673 )
      goto LABEL_58;
    if ( v21 == -2147023579 )
      goto LABEL_59;
    v31 = *v12;
    if ( *v12 )
    {
      pProxy = 0;
      v32 = ((__int64 (__fastcall *)(IUnknown *, IUnknown **))v31->lpVtbl[3].QueryInterface)(v31, &pProxy);
      v21 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x990,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v32,
          dwAuthnLevel);
        v43 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v43->lpVtbl->Release)(v43);
        }
        v44 = v52;
        if ( v52 )
        {
          v52 = 0;
          ((void (__fastcall *)(IUnknown *))v44->lpVtbl->Release)(v44);
        }
        return v21;
      }
      v36 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
              pProxy,
              v33,
              v34,
              v35);
      v21 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x991,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v36,
          dwAuthnLevel);
        v41 = pProxy;
        if ( pProxy )
        {
          pProxy = 0;
          ((void (__fastcall *)(IUnknown *))v41->lpVtbl->Release)(v41);
        }
        v42 = v52;
        if ( v52 )
        {
          v52 = 0;
          ((void (__fastcall *)(IUnknown *))v42->lpVtbl->Release)(v42);
        }
        return v21;
      }
      v37 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v37->lpVtbl->Release)(v37);
      }
    }
  }
  if ( v21 == -2147023579 )
  {
LABEL_59:
    v47 = v52;
    if ( v52 )
    {
      v52 = 0;
      ((void (__fastcall *)(IUnknown *))v47->lpVtbl->Release)(v47);
    }
    return v21;
  }
  if ( (v21 & 0x80000000) != 0 )
  {
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v21,
      dwAuthnLevel);
    goto LABEL_59;
  }
  v45 = v52;
  if ( v52 )
  {
    v52 = 0;
    ((void (__fastcall *)(IUnknown *))v45->lpVtbl->Release)(v45);
  }
  return 0;
}

```

## disassembly

```asm
0x180043f90  mov     [rsp-28h+arg_0], rbx
0x180043f95  mov     [rsp-28h+arg_8], rsi
0x180043f9a  mov     [rsp-28h+arg_18], r9
0x180043f9f  push    rbp
0x180043fa0  push    rdi
0x180043fa1  push    r12
0x180043fa3  push    r13
0x180043fa5  push    r14
0x180043fa7  mov     rbp, rsp
0x180043faa  sub     rsp, 40h
0x180043fae  mov     r12, rdx
0x180043fb1  mov     r13, rcx
0x180043fb4  xor     edi, edi
0x180043fb6  mov     [rbp+arg_18], rdi
0x180043fba  mov     rsi, [rbp+pProxy]
0x180043fbe  mov     [rsi], rdi
0x180043fc1  mov     r14b, dil
0x180043fc4  lea     rcx, ?g_srwTickets@WinStoreAuth@@3U_RTL_SRWLOCK@@A; SRWLock
0x180043fcb  call    cs:__imp_AcquireSRWLockExclusive
0x180043fd1  mov     rbx, [r13+0]
0x180043fd5  mov     rax, [rbx]
0x180043fd8  cmp     [rbp+arg_20], rdi
0x180043fdc  jz      short loc_180044019
0x180043fde  mov     rdi, [rax+38h]
0x180043fe2  mov     rcx, [rbp+arg_18]
0x180043fe6  test    rcx, rcx
0x180043fe9  jz      short loc_180044000
0x180043feb  mov     [rbp+arg_18], 0
0x180043ff3  mov     rax, [rcx]
0x180043ff6  mov     rax, [rax+10h]
0x180043ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fff  nop
0x180044000  lea     r9, [rbp+arg_18]
0x180044004  mov     r8, [rbp+arg_20]
0x180044008  mov     rdx, [r12]
0x18004400c  mov     rcx, rbx
0x18004400f  mov     rax, rdi
0x180044012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044017  jmp     short loc_18004404E
0x180044019  mov     rdi, [rax+30h]
0x18004401d  mov     rcx, [rbp+arg_18]
0x180044021  test    rcx, rcx
0x180044024  jz      short loc_18004403B
0x180044026  mov     [rbp+arg_18], 0
0x18004402e  mov     rdx, [rcx]
0x180044031  mov     rax, [rdx+10h]
0x180044035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004403a  nop
0x18004403b  lea     r8, [rbp+arg_18]
0x18004403f  mov     rdx, [r12]
0x180044043  mov     rcx, rbx
0x180044046  mov     rax, rdi
0x180044049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004404e  mov     ebx, eax
0x180044050  xor     edi, edi
0x180044052  test    eax, eax
0x180044054  js      short loc_18004407F
0x180044056  mov     rcx, [rbp+arg_18]
0x18004405a  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18004405f  mov     ebx, eax
0x180044061  test    eax, eax
0x180044063  js      loc_180044233
0x180044069  mov     [rsp+40h+dwAuthnLevel], 7530h
0x180044071  mov     rdx, rsi
0x180044074  mov     rcx, [rbp+arg_18]
0x180044078  call    ??$BlockOnCompletionAndGetResults@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@PEAUIWebTokenRequestResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@2@W4tagCOWAIT_FLAGS@@PEAXK@Z; BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *,tagCOWAIT_FLAGS,void *,ulong)
0x18004407d  mov     ebx, eax
0x18004407f  lea     rcx, ?g_srwTickets@WinStoreAuth@@3U_RTL_SRWLOCK@@A; SRWLock
0x180044086  call    cs:__imp_ReleaseSRWLockExclusive
0x18004408c  test    ebx, ebx
0x18004408e  js      loc_1800441AF
0x180044094  mov     rbx, [rsi]
0x180044097  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18004409f  mov     [rsp+40h+pAuthInfo], rdi; pAuthInfo
0x1800440a4  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x1800440ac  mov     [rsp+40h+dwAuthnLevel], edi; dwAuthnLevel
0x1800440b0  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800440b4  or      eax, 0FFFFFFFFh
0x1800440b7  mov     r8d, eax; dwAuthzSvc
0x1800440ba  mov     edx, eax; dwAuthnSvc
0x1800440bc  mov     rcx, rbx; pProxy
0x1800440bf  call    cs:__imp_CoSetProxyBlanket
0x1800440c5  mov     edi, eax
0x1800440c7  cmp     eax, 80004002h
0x1800440cc  jz      loc_18004415E
0x1800440d2  mov     [rbp+pProxy], 0
0x1800440da  mov     rdx, [rbx]
0x1800440dd  mov     rax, [rdx]
0x1800440e0  lea     r8, [rbp+pProxy]
0x1800440e4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800440eb  mov     rcx, rbx
0x1800440ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440f3  test    eax, eax
0x1800440f5  js      short loc_180044138
0x1800440f7  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800440ff  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x180044108  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x180044110  mov     [rsp+40h+dwAuthnLevel], 0; int
0x180044118  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18004411c  or      eax, 0FFFFFFFFh
0x18004411f  mov     r8d, eax; dwAuthzSvc
0x180044122  mov     edx, eax; dwAuthnSvc
0x180044124  mov     rcx, [rbp+pProxy]; pProxy
0x180044128  call    cs:__imp_CoSetProxyBlanket
0x18004412e  mov     ebx, eax
0x180044130  test    eax, eax
0x180044132  js      loc_18004426B
0x180044138  mov     rcx, [rbp+pProxy]
0x18004413c  test    rcx, rcx
0x18004413f  jz      short loc_180044156
0x180044141  mov     [rbp+pProxy], 0
0x180044149  mov     rax, [rcx]
0x18004414c  mov     rax, [rax+10h]
0x180044150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044155  nop
0x180044156  test    edi, edi
0x180044158  js      loc_1800442A4
0x18004415e  mov     rcx, [rsi]
0x180044161  mov     [rbp+pProxy], rcx
0x180044165  xor     edi, edi
0x180044167  test    rcx, rcx
0x18004416a  jz      short loc_180044179
0x18004416c  mov     rax, [rcx]
0x18004416f  mov     rax, [rax+8]
0x180044173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044178  nop
0x180044179  mov     qword ptr [rsp+40h+dwAuthnLevel], rdi; int
0x18004417e  mov     r9, [rbp+arg_38]
0x180044182  mov     r8, [rbp+arg_30]
0x180044186  mov     rdx, [rbp+arg_28]
0x18004418a  lea     rcx, [rbp+pProxy]
0x18004418e  call    ?ExtractTicketsFromTokenResult@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@@Z; WinStoreAuth::AuthenticationInternal::ExtractTicketsFromTokenResult(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> const &,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *)
0x180044193  mov     ebx, eax
0x180044195  mov     rcx, [rbp+pProxy]
0x180044199  test    rcx, rcx
0x18004419c  jz      short loc_1800441AF
0x18004419e  mov     [rbp+pProxy], rdi
0x1800441a2  mov     rax, [rcx]
0x1800441a5  mov     rax, [rax+10h]
0x1800441a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441ae  nop
0x1800441af  test    r14b, r14b
0x1800441b2  jnz     loc_18004439B
0x1800441b8  test    ebx, ebx
0x1800441ba  jns     loc_18004439B
0x1800441c0  cmp     ebx, 800704C7h
0x1800441c6  jz      loc_1800443C5
0x1800441cc  cmp     ebx, 80070525h
0x1800441d2  jz      loc_1800443E0
0x1800441d8  mov     rcx, [rsi]
0x1800441db  test    rcx, rcx
0x1800441de  jz      short loc_18004422B
0x1800441e0  mov     [rbp+pProxy], rdi
0x1800441e4  mov     rax, [rcx]
0x1800441e7  lea     rdx, [rbp+pProxy]
0x1800441eb  mov     rax, [rax+48h]
0x1800441ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441f4  mov     ebx, eax
0x1800441f6  test    eax, eax
0x1800441f8  js      loc_18004434C
0x1800441fe  mov     rcx, [rbp+pProxy]
0x180044202  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *,ulong)
0x180044207  mov     ebx, eax
0x180044209  test    eax, eax
0x18004420b  js      loc_1800442FA
0x180044211  mov     rcx, [rbp+pProxy]
0x180044215  test    rcx, rcx
0x180044218  jz      short loc_18004422B
0x18004421a  mov     [rbp+pProxy], rdi
0x18004421e  mov     rax, [rcx]
0x180044221  mov     rax, [rax+10h]
0x180044225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004422a  nop
0x18004422b  mov     r14b, 1
0x18004422e  jmp     loc_180043FC4
0x180044233  mov     rcx, [rbp+28h]; this
0x180044237  mov     r9d, ebx; char *
0x18004423a  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180044241  mov     edx, 967h; void *
0x180044246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004424b  nop
0x18004424c  mov     rcx, [rbp+arg_18]
0x180044250  test    rcx, rcx
0x180044253  jz      short loc_180044266
0x180044255  mov     [rbp+arg_18], rdi
0x180044259  mov     rax, [rcx]
0x18004425c  mov     rax, [rax+10h]
0x180044260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044265  nop
0x180044266  jmp     loc_1800443FA
0x18004426b  mov     rcx, [rbp+28h]; this
0x18004426f  mov     r9d, eax; char *
0x180044272  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180044279  mov     edx, 0F0h; void *
0x18004427e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044283  nop
0x180044284  mov     rcx, [rbp+pProxy]
0x180044288  test    rcx, rcx
0x18004428b  jz      short loc_1800442A2
0x18004428d  mov     [rbp+pProxy], 0
0x180044295  mov     rax, [rcx]
0x180044298  mov     rax, [rax+10h]
0x18004429c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442a1  nop
0x1800442a2  jmp     short loc_1800442BE
0x1800442a4  mov     rcx, [rbp+28h]; this
0x1800442a8  mov     r9d, edi; char *
0x1800442ab  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800442b2  mov     edx, 0F3h; void *
0x1800442b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442bc  mov     ebx, edi
0x1800442be  mov     rcx, [rbp+28h]; this
0x1800442c2  mov     r9d, ebx; char *
0x1800442c5  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800442cc  mov     edx, 985h; void *
0x1800442d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442d6  nop
0x1800442d7  mov     rcx, [rbp+arg_18]
0x1800442db  test    rcx, rcx
0x1800442de  jz      short loc_1800442F5
0x1800442e0  mov     [rbp+arg_18], 0
0x1800442e8  mov     rdx, [rcx]
0x1800442eb  mov     rax, [rdx+10h]
0x1800442ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442f4  nop
0x1800442f5  jmp     loc_1800443FA
0x1800442fa  mov     rcx, [rbp+28h]; this
0x1800442fe  mov     r9d, ebx; char *
0x180044301  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180044308  mov     edx, 991h; void *
0x18004430d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044312  nop
0x180044313  mov     rcx, [rbp+pProxy]
0x180044317  test    rcx, rcx
0x18004431a  jz      short loc_18004432D
0x18004431c  mov     [rbp+pProxy], rdi
0x180044320  mov     rax, [rcx]
0x180044323  mov     rax, [rax+10h]
0x180044327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004432c  nop
0x18004432d  mov     rcx, [rbp+arg_18]
0x180044331  test    rcx, rcx
0x180044334  jz      short loc_180044347
0x180044336  mov     [rbp+arg_18], rdi
0x18004433a  mov     rax, [rcx]
0x18004433d  mov     rax, [rax+10h]
0x180044341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044346  nop
0x180044347  jmp     loc_1800443FA
0x18004434c  mov     rcx, [rbp+28h]; this
0x180044350  mov     r9d, ebx; char *
0x180044353  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18004435a  mov     edx, 990h; void *
0x18004435f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044364  nop
0x180044365  mov     rcx, [rbp+pProxy]
0x180044369  test    rcx, rcx
0x18004436c  jz      short loc_18004437F
0x18004436e  mov     [rbp+pProxy], rdi
0x180044372  mov     rax, [rcx]
0x180044375  mov     rax, [rax+10h]
0x180044379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004437e  nop
0x18004437f  mov     rcx, [rbp+arg_18]
0x180044383  test    rcx, rcx
0x180044386  jz      short loc_180044399
0x180044388  mov     [rbp+arg_18], rdi
0x18004438c  mov     rax, [rcx]
0x18004438f  mov     rax, [rax+10h]
0x180044393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044398  nop
0x180044399  jmp     short loc_1800443FA
0x18004439b  cmp     ebx, 80070525h
0x1800443a1  jz      short loc_1800443E0
0x1800443a3  test    ebx, ebx
0x1800443a5  js      short loc_1800443C5
0x1800443a7  mov     rcx, [rbp+arg_18]
0x1800443ab  test    rcx, rcx
0x1800443ae  jz      short loc_1800443C1
0x1800443b0  mov     [rbp+arg_18], rdi
0x1800443b4  mov     rax, [rcx]
0x1800443b7  mov     rax, [rax+10h]
0x1800443bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443c0  nop
0x1800443c1  xor     eax, eax
0x1800443c3  jmp     short loc_1800443FC
0x1800443c5  mov     rcx, [rbp+28h]; this
0x1800443c9  mov     r9d, ebx; char *
0x1800443cc  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800443d3  mov     edx, 99Ch; void *
0x1800443d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800443dd  nop
0x1800443de  jmp     short $+2
0x1800443e0  mov     rcx, [rbp+arg_18]
0x1800443e4  test    rcx, rcx
0x1800443e7  jz      short loc_1800443FA
0x1800443e9  mov     [rbp+arg_18], rdi
0x1800443ed  mov     rax, [rcx]
0x1800443f0  mov     rax, [rax+10h]
0x1800443f4  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
