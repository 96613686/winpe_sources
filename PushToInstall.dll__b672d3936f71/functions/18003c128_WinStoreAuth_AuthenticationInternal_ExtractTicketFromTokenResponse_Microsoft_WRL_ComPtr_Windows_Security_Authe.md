# WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse> const &,WinStoreAuth::TicketHolder &)

- ea: `0x18003c128`
- end: `0x18003c525`
- name: `?ExtractTicketFromTokenResponse@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEAUTicketHolder@2@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003c52c`

## callees

- `0x180010b84`
- `0x180038550`
- `0x18003bc38`
- `0x18003bd7c`
- `0x18003c128`
- `0x180042680`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c3f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c3f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c1ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c385`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinStoreAuth::AuthenticationInternal::ExtractTicketFromTokenResponse(_QWORD *a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  IUnknown *v6; // rcx
  int v8; // eax
  IUnknown *v9; // rcx
  int v10; // eax
  IUnknown *v11; // rcx
  int v12; // eax
  IUnknown *v13; // rcx
  IUnknown *v14; // rcx
  int v15; // eax
  IUnknown *v16; // rcx
  IUnknown *v17; // rcx
  int v18; // eax
  IUnknown *v19; // rcx
  IUnknown *v20; // rcx
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, __int64); // rdi
  int v23; // eax
  IUnknown *v24; // rcx
  IUnknown *v25; // rcx
  PCWSTR StringRawBuffer; // r8
  const wchar_t *v27; // rax
  IUnknown *v28; // rcx
  IUnknown *v29; // rcx
  IUnknown *v30; // rcx
  IUnknown *v31; // rcx
  int v32; // [rsp+20h] [rbp-20h]
  int v33; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  IUnknown *v35; // [rsp+70h] [rbp+30h] BYREF
  IUnknown *v36; // [rsp+80h] [rbp+40h] BYREF

  v35 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, IUnknown **))(*(_QWORD *)*a1 + 64LL))(*a1, &v35);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x820,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v4,
      v32);
    v6 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
    }
    return v5;
  }
  v8 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v35);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x821,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v8,
      v32);
    v9 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    }
    return v5;
  }
  WindowsDeleteString(*(HSTRING *)(a2 + 16));
  *(_QWORD *)(a2 + 16) = 0;
  v10 = WinStoreAuth::AuthenticationInternal::ExtractAccountId(&v35, (_QWORD *)(a2 + 16));
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x823,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v10,
      v32);
    v11 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
    }
    return v5;
  }
  v36 = 0;
  v12 = ((__int64 (__fastcall *)(IUnknown *, IUnknown **))v35->lpVtbl[2].QueryInterface)(v35, &v36);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x826,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v12,
      v32);
    v13 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(IUnknown *))v13->lpVtbl->Release)(v13);
    }
    v14 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v14->lpVtbl->Release)(v14);
    }
    return v5;
  }
  v15 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v36);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x827,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v15,
      v32);
    v16 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(IUnknown *))v16->lpVtbl->Release)(v16);
    }
    v17 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v17->lpVtbl->Release)(v17);
    }
    return v5;
  }
  v18 = WinStoreAuth::AuthenticationInternal::ExtractProviderType(&v36, (_DWORD *)a2);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x829,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v18,
      v32);
    v19 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
    }
    v20 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
    }
    return v5;
  }
  v21 = *a1;
  v22 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 48LL);
  WindowsDeleteString(*(HSTRING *)(a2 + 8));
  *(_QWORD *)(a2 + 8) = 0;
  v23 = v22(v21, a2 + 8);
  v5 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v23,
      v32);
    v24 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(IUnknown *))v24->lpVtbl->Release)(v24);
    }
    v25 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v25->lpVtbl->Release)(v25);
    }
    return v5;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 16), 0);
  switch ( *(_DWORD *)a2 )
  {
    case 1:
      v27 = L"MSA";
      break;
    case 2:
      v27 = L"AAD";
      break;
    case 4:
      v27 = L"Device";
      break;
    case 8:
      v27 = L"Xbox";
      break;
    default:
      v27 = (const wchar_t *)L"None";
      break;
  }
  LOBYTE(v32) = 1;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0x82D,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)0x80004005LL,
    v32,
    (bool)"Account Ticket succesfully extracted. Ticket providerType: %ws web: %ws ",
    (const char *)v27,
    StringRawBuffer);
  if ( !*(_DWORD *)a2 )
  {
    v5 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)0x8000FFFFLL,
      v33);
    v28 = v36;
    if ( v36 )
    {
      v36 = 0;
      ((void (__fastcall *)(IUnknown *))v28->lpVtbl->Release)(v28);
    }
    v29 = v35;
    if ( v35 )
    {
      v35 = 0;
      ((void (__fastcall *)(IUnknown *))v29->lpVtbl->Release)(v29);
    }
    return v5;
  }
  v30 = v36;
  if ( v36 )
  {
    v36 = 0;
    ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
  }
  v31 = v35;
  if ( v35 )
  {
    v35 = 0;
    ((void (__fastcall *)(IUnknown *))v31->lpVtbl->Release)(v31);
  }
  return 0;
}

```

## disassembly

```asm
0x18003c128  mov     [rsp-28h+arg_8], rbx
0x18003c12d  mov     [rsp-28h+arg_18], rsi
0x18003c132  push    rbp
0x18003c133  push    rdi
0x18003c134  push    r12
0x18003c136  push    r14
0x18003c138  push    r15
0x18003c13a  mov     rbp, rsp
0x18003c13d  sub     rsp, 40h
0x18003c141  mov     r14, rdx
0x18003c144  mov     rsi, rcx
0x18003c147  xor     r12d, r12d
0x18003c14a  mov     [rbp+arg_0], r12
0x18003c14e  mov     rcx, [rcx]
0x18003c151  mov     rax, [rcx]
0x18003c154  lea     rdx, [rbp+arg_0]
0x18003c158  mov     rax, [rax+40h]
0x18003c15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c161  mov     ebx, eax
0x18003c163  test    eax, eax
0x18003c165  jns     short loc_18003C1A1
0x18003c167  mov     rcx, [rbp+28h]; this
0x18003c16b  mov     r9d, eax; char *
0x18003c16e  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c175  mov     edx, 820h; void *
0x18003c17a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c17f  nop
0x18003c180  mov     rcx, [rbp+arg_0]
0x18003c184  test    rcx, rcx
0x18003c187  jz      short loc_18003C19A
0x18003c189  mov     [rbp+arg_0], r12
0x18003c18d  mov     rax, [rcx]
0x18003c190  mov     rax, [rax+10h]
0x18003c194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c199  nop
0x18003c19a  mov     eax, ebx
0x18003c19c  jmp     loc_18003C50C
0x18003c1a1  mov     rcx, [rbp+arg_0]
0x18003c1a5  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18003c1aa  mov     ebx, eax
0x18003c1ac  test    eax, eax
0x18003c1ae  jns     short loc_18003C1E5
0x18003c1b0  mov     rcx, [rbp+28h]; this
0x18003c1b4  mov     r9d, eax; char *
0x18003c1b7  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c1be  mov     edx, 821h; void *
0x18003c1c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c1c8  nop
0x18003c1c9  mov     rcx, [rbp+arg_0]
0x18003c1cd  test    rcx, rcx
0x18003c1d0  jz      short loc_18003C1E3
0x18003c1d2  mov     [rbp+arg_0], r12
0x18003c1d6  mov     rax, [rcx]
0x18003c1d9  mov     rax, [rax+10h]
0x18003c1dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1e2  nop
0x18003c1e3  jmp     short loc_18003C19A
0x18003c1e5  lea     r15, [r14+10h]
0x18003c1e9  mov     rcx, [r15]; string
0x18003c1ec  call    cs:__imp_WindowsDeleteString
0x18003c1f2  mov     [r15], r12
0x18003c1f5  mov     rdx, r15
0x18003c1f8  lea     rcx, [rbp+arg_0]
0x18003c1fc  call    ?ExtractAccountId@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@PEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::ExtractAccountId(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount> const &,HSTRING__ * *)
0x18003c201  mov     ebx, eax
0x18003c203  test    eax, eax
0x18003c205  jns     short loc_18003C23F
0x18003c207  mov     rcx, [rbp+28h]; this
0x18003c20b  mov     r9d, eax; char *
0x18003c20e  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c215  mov     edx, 823h; void *
0x18003c21a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c21f  nop
0x18003c220  mov     rcx, [rbp+arg_0]
0x18003c224  test    rcx, rcx
0x18003c227  jz      short loc_18003C23A
0x18003c229  mov     [rbp+arg_0], r12
0x18003c22d  mov     rax, [rcx]
0x18003c230  mov     rax, [rax+10h]
0x18003c234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c239  nop
0x18003c23a  jmp     loc_18003C19A
0x18003c23f  mov     [rbp+arg_10], r12
0x18003c243  mov     rcx, [rbp+arg_0]
0x18003c247  mov     rax, [rcx]
0x18003c24a  lea     rdx, [rbp+arg_10]
0x18003c24e  mov     rax, [rax+30h]
0x18003c252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c257  mov     ebx, eax
0x18003c259  test    eax, eax
0x18003c25b  jns     short loc_18003C2AF
0x18003c25d  mov     rcx, [rbp+28h]; this
0x18003c261  mov     r9d, eax; char *
0x18003c264  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c26b  mov     edx, 826h; void *
0x18003c270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c275  nop
0x18003c276  mov     rcx, [rbp+arg_10]
0x18003c27a  test    rcx, rcx
0x18003c27d  jz      short loc_18003C290
0x18003c27f  mov     [rbp+arg_10], r12
0x18003c283  mov     rax, [rcx]
0x18003c286  mov     rax, [rax+10h]
0x18003c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c28f  nop
0x18003c290  mov     rcx, [rbp+arg_0]
0x18003c294  test    rcx, rcx
0x18003c297  jz      short loc_18003C2AA
0x18003c299  mov     [rbp+arg_0], r12
0x18003c29d  mov     rax, [rcx]
0x18003c2a0  mov     rax, [rax+10h]
0x18003c2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2a9  nop
0x18003c2aa  jmp     loc_18003C19A
0x18003c2af  mov     rcx, [rbp+arg_10]
0x18003c2b3  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18003c2b8  mov     ebx, eax
0x18003c2ba  test    eax, eax
0x18003c2bc  jns     short loc_18003C310
0x18003c2be  mov     rcx, [rbp+28h]; this
0x18003c2c2  mov     r9d, eax; char *
0x18003c2c5  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c2cc  mov     edx, 827h; void *
0x18003c2d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2d6  nop
0x18003c2d7  mov     rcx, [rbp+arg_10]
0x18003c2db  test    rcx, rcx
0x18003c2de  jz      short loc_18003C2F1
0x18003c2e0  mov     [rbp+arg_10], r12
0x18003c2e4  mov     rax, [rcx]
0x18003c2e7  mov     rax, [rax+10h]
0x18003c2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2f0  nop
0x18003c2f1  mov     rcx, [rbp+arg_0]
0x18003c2f5  test    rcx, rcx
0x18003c2f8  jz      short loc_18003C30B
0x18003c2fa  mov     [rbp+arg_0], r12
0x18003c2fe  mov     rax, [rcx]
0x18003c301  mov     rax, [rax+10h]
0x18003c305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c30a  nop
0x18003c30b  jmp     loc_18003C19A
0x18003c310  mov     rdx, r14
0x18003c313  lea     rcx, [rbp+arg_10]
0x18003c317  call    ?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)
0x18003c31c  mov     ebx, eax
0x18003c31e  test    eax, eax
0x18003c320  jns     short loc_18003C374
0x18003c322  mov     rcx, [rbp+28h]; this
0x18003c326  mov     r9d, eax; char *
0x18003c329  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c330  mov     edx, 829h; void *
0x18003c335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c33a  nop
0x18003c33b  mov     rcx, [rbp+arg_10]
0x18003c33f  test    rcx, rcx
0x18003c342  jz      short loc_18003C355
0x18003c344  mov     [rbp+arg_10], r12
0x18003c348  mov     rax, [rcx]
0x18003c34b  mov     rax, [rax+10h]
0x18003c34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c354  nop
0x18003c355  mov     rcx, [rbp+arg_0]
0x18003c359  test    rcx, rcx
0x18003c35c  jz      short loc_18003C36F
0x18003c35e  mov     [rbp+arg_0], r12
0x18003c362  mov     rax, [rcx]
0x18003c365  mov     rax, [rax+10h]
0x18003c369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c36e  nop
0x18003c36f  jmp     loc_18003C19A
0x18003c374  mov     rsi, [rsi]
0x18003c377  mov     rax, [rsi]
0x18003c37a  mov     rdi, [rax+30h]
0x18003c37e  lea     rbx, [r14+8]
0x18003c382  mov     rcx, [rbx]; string
0x18003c385  call    cs:__imp_WindowsDeleteString
0x18003c38b  mov     [rbx], r12
0x18003c38e  mov     rdx, rbx
0x18003c391  mov     rcx, rsi
0x18003c394  mov     rax, rdi
0x18003c397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c39c  mov     ebx, eax
0x18003c39e  test    eax, eax
0x18003c3a0  jns     short loc_18003C3F4
0x18003c3a2  mov     rcx, [rbp+28h]; this
0x18003c3a6  mov     r9d, eax; char *
0x18003c3a9  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c3b0  mov     edx, 82Ah; void *
0x18003c3b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c3ba  nop
0x18003c3bb  mov     rcx, [rbp+arg_10]
0x18003c3bf  test    rcx, rcx
0x18003c3c2  jz      short loc_18003C3D5
0x18003c3c4  mov     [rbp+arg_10], r12
0x18003c3c8  mov     rax, [rcx]
0x18003c3cb  mov     rax, [rax+10h]
0x18003c3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3d4  nop
0x18003c3d5  mov     rcx, [rbp+arg_0]
0x18003c3d9  test    rcx, rcx
0x18003c3dc  jz      short loc_18003C3EF
0x18003c3de  mov     [rbp+arg_0], r12
0x18003c3e2  mov     rax, [rcx]
0x18003c3e5  mov     rax, [rax+10h]
0x18003c3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3ee  nop
0x18003c3ef  jmp     loc_18003C19A
0x18003c3f4  xor     edx, edx; length
0x18003c3f6  mov     rcx, [r15]; string
0x18003c3f9  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c3ff  mov     r8, rax
0x18003c402  mov     edx, [r14]
0x18003c405  sub     edx, 1
0x18003c408  jz      short loc_18003C43D
0x18003c40a  sub     edx, 1
0x18003c40d  jz      short loc_18003C434
0x18003c40f  sub     edx, 2
0x18003c412  jz      short loc_18003C42B
0x18003c414  cmp     edx, 4
0x18003c417  jz      short loc_18003C422
0x18003c419  lea     rax, aNone_0; "None"
0x18003c420  jmp     short loc_18003C444
0x18003c422  lea     rax, aXbox; "Xbox"
0x18003c429  jmp     short loc_18003C444
0x18003c42b  lea     rax, aDevice; "Device"
0x18003c432  jmp     short loc_18003C444
0x18003c434  lea     rax, aAad; "AAD"
0x18003c43b  jmp     short loc_18003C444
0x18003c43d  lea     rax, aMsa_0; "MSA"
0x18003c444  mov     rcx, [rbp+28h]; this
0x18003c448  mov     [rsp+40h+var_8], r8
0x18003c44d  mov     [rsp+40h+var_10], rax; char *
0x18003c452  lea     rax, aAccountTicketS; "Account Ticket succesfully extracted. T"...
0x18003c459  mov     qword ptr [rsp+40h+var_18], rax; bool
0x18003c45e  mov     byte ptr [rsp+40h+var_20], 1; int
0x18003c463  mov     r9d, 80004005h; char *
0x18003c469  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c470  mov     edx, 82Dh; void *
0x18003c475  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003c47a  cmp     [r14], r12d
0x18003c47d  jnz     short loc_18003C4D6
0x18003c47f  mov     rcx, [rbp+28h]; this
0x18003c483  mov     ebx, 8000FFFFh
0x18003c488  mov     r9d, ebx; char *
0x18003c48b  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c492  mov     edx, 82Fh; void *
0x18003c497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c49c  nop
0x18003c49d  mov     rcx, [rbp+arg_10]
0x18003c4a1  test    rcx, rcx
0x18003c4a4  jz      short loc_18003C4B7
0x18003c4a6  mov     [rbp+arg_10], r12
0x18003c4aa  mov     rax, [rcx]
0x18003c4ad  mov     rax, [rax+10h]
0x18003c4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4b6  nop
0x18003c4b7  mov     rcx, [rbp+arg_0]
0x18003c4bb  test    rcx, rcx
0x18003c4be  jz      short loc_18003C4D1
0x18003c4c0  mov     [rbp+arg_0], r12
0x18003c4c4  mov     rdx, [rcx]
0x18003c4c7  mov     rax, [rdx+10h]
0x18003c4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4d0  nop
0x18003c4d1  jmp     loc_18003C19A
0x18003c4d6  mov     rcx, [rbp+arg_10]
0x18003c4da  test    rcx, rcx
0x18003c4dd  jz      short loc_18003C4F0
0x18003c4df  mov     [rbp+arg_10], r12
0x18003c4e3  mov     rax, [rcx]
0x18003c4e6  mov     rax, [rax+10h]
0x18003c4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4ef  nop
0x18003c4f0  mov     rcx, [rbp+arg_0]
0x18003c4f4  test    rcx, rcx
0x18003c4f7  jz      short loc_18003C50A
0x18003c4f9  mov     [rbp+arg_0], r12
0x18003c4fd  mov     rax, [rcx]
0x18003c500  mov     rax, [rax+10h]
0x18003c504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c509  nop
0x18003c50a  xor     eax, eax
0x18003c50c  lea     r11, [rsp+40h+var_s0]
0x18003c511  mov     rbx, [r11+38h]
0x18003c515  mov     rsi, [r11+48h]
0x18003c519  mov     rsp, r11
0x18003c51c  pop     r15
0x18003c51e  pop     r14
0x18003c520  pop     r12
0x18003c522  pop     rdi
0x18003c523  pop     rbp
0x18003c524  retn
```
