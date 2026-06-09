# Windows::Security::Authentication::Web::CWebAuthBrokerFactory::GetCurrentApplicationCallbackUri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180002420`
- end: `0x180002a66`
- name: `?GetCurrentApplicationCallbackUri@CWebAuthBrokerFactory@Web@Authentication@Security@Windows@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@5@@Z`
- size: `1606`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::CWebAuthBrokerFactory *this, Windows::Foundation::IUriRuntimeClass **callbackUri)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002420`
- `0x180002b20`
- `0x1800035e0`
- `0x1800053f8`
- `0x18000737c`
- `0x180011b30`
- `0x180011b58`
- `0x180011f80`
- `0x180012128`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800028de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800028de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002860`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002a37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002860`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002a37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800028c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800028c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002579`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000284b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000284b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800029fe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180002913`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180002913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800029e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800029e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800025e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800025e9`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthBrokerFactory::GetCurrentApplicationCallbackUri(
        Windows::Security::Authentication::Web::CWebAuthBrokerFactory *this,
        Windows::Foundation::IUriRuntimeClass **callbackUri)
{
  HSTRING__ *v4; // rdi
  int v5; // eax
  __int64 v6; // r8
  _AUTH_BROKER_CLIENT_CONTEXT *v7; // r15
  int v8; // r14d
  void *tokenHandle; // rcx
  _AUTH_BROKER_CLIENT_CONTEXT *v10; // rbx
  WPP_PROJECT_CONTROL_BLOCK *v11; // r10
  signed int LastError; // eax
  __int64 v13; // r12
  const wchar_t *v14; // rdx
  __int64 v15; // rsi
  wchar_t *v16; // r9
  __int64 v17; // rcx
  wchar_t *v18; // rcx
  int v19; // edx
  int v20; // eax
  wchar_t *v21; // rax
  signed int v22; // eax
  unsigned __int16 v23; // dx
  unsigned __int16 v24; // dx
  _WORD *v25; // rdx
  const wchar_t *v26; // rcx
  _WORD *v27; // rcx
  unsigned __int16 v28; // dx
  unsigned int v29; // r9d
  Windows::Foundation::IUriRuntimeClassFactory *ptr; // rcx
  HSTRING v31; // rbx
  int ActivationFactory; // eax
  int v33; // eax
  wchar_t *dialogTitle; // rcx
  void *v35; // rcx
  Windows::Foundation::IUriRuntimeClassFactory *v36; // rcx
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> uriFactory; // [rsp+30h] [rbp-D0h] BYREF
  _AUTH_BROKER_CLIENT_CONTEXT *clientContext; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int ReturnLength; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  PSID TokenInformation[10]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[260]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v45[8]; // [rsp+2C8h] [rbp+1C8h] BYREF

  clientContext = 0;
  uriFactory.ptr_ = 0;
  if ( !callbackUri )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x16u, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids);
    }
    return 2147942487LL;
  }
  *callbackUri = 0;
  v4 = 0;
  v5 = GetAndVerifyAuthBrokerClientContext(0, &clientContext);
  v7 = clientContext;
  v8 = v5;
  if ( v5 < 0 )
    goto LABEL_98;
  tokenHandle = clientContext->tokenHandle;
  v10 = 0;
  clientContext = 0;
  ReturnLength = 76;
  StringSid = 0;
  if ( !tokenHandle )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Control.Logger, 0x20u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    v8 = -2147024809;
    goto LABEL_47;
  }
  if ( !GetTokenInformation(tokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x21u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v8);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v8 >= 0 )
      goto LABEL_28;
LABEL_47:
    if ( v11 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v11[1].ReserveSpace[28] & 8) != 0
      && v11[1].Control.Level >= 2u )
    {
      v24 = 37;
LABEL_72:
      WPP_SF_d(v11[1].Control.Logger, v24, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v8);
      v11 = WPP_GLOBAL_Control;
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
  {
    if ( StringSid && *StringSid == 83 )
      *StringSid = 115;
  }
  else
  {
    v22 = GetLastError();
    v8 = v22;
    if ( v22 > 0 )
      v8 = (unsigned __int16)v22 | 0x80070000;
    if ( v8 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_73;
      if ( (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0 && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_dd(WPP_GLOBAL_Control[1].Control.Logger, v23, (const _GUID *)v6, 0, v8);
        v11 = WPP_GLOBAL_Control;
      }
      goto LABEL_47;
    }
  }
  v11 = WPP_GLOBAL_Control;
LABEL_28:
  v13 = 2147483646;
  v14 = L"ms-app://";
  v15 = 260;
  v16 = pszDest;
  v17 = 2147483646;
  v6 = 260;
  do
  {
    if ( !v17 )
      break;
    if ( !*v14 )
      break;
    *v16++ = *v14++;
    --v17;
    --v6;
  }
  while ( v6 );
  v18 = v16 - 1;
  v8 = -2147024774;
  v19 = -2147024774;
  if ( v6 )
  {
    v18 = v16;
    v19 = 0;
  }
  *v18 = 0;
  if ( v6 )
  {
    v20 = StringCchCatW(pszDest, 0x104u, StringSid);
    if ( v20 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      v8 = v20;
    }
    else
    {
      v21 = pszDest;
      while ( *v21 )
      {
        ++v21;
        if ( !--v15 )
        {
          v11 = WPP_GLOBAL_Control;
          v8 = -2147024809;
          goto LABEL_68;
        }
      }
      v25 = &v45[-2 * v15];
      v26 = L"/";
      do
      {
        if ( !v13 )
          break;
        if ( !*v26 )
          break;
        *v25++ = *v26++;
        --v13;
        --v15;
      }
      while ( v15 );
      v27 = v25 - 1;
      if ( v15 )
      {
        v27 = v25;
        v8 = 0;
      }
      *v27 = 0;
      if ( v15 )
      {
        v8 = Windows::Internal::String::_InitializeHelper((Windows::Internal::String *)&clientContext, pszDest);
        if ( v8 >= 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 5u )
          {
            WPP_SF_S(
              WPP_GLOBAL_Control[1].Control.Logger,
              0x27u,
              WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
              pszDest);
            v11 = WPP_GLOBAL_Control;
          }
          v4 = (HSTRING__ *)clientContext;
          v8 = 0;
          goto LABEL_73;
        }
        v10 = clientContext;
      }
      v11 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v8 = v19;
  }
LABEL_68:
  if ( v11 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (v11[1].ReserveSpace[28] & 8) != 0
    && v11[1].Control.Level >= 2u )
  {
    v24 = 38;
    goto LABEL_72;
  }
LABEL_73:
  if ( StringSid )
  {
    LocalFree(StringSid);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    WindowsDeleteString((HSTRING)v10);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v8 >= 0 )
  {
    if ( WindowsCreateStringReference(RuntimeClass_Windows_Foundation_Uri, 0x16u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ptr = uriFactory.ptr_;
    v31 = string;
    if ( uriFactory.ptr_ )
    {
      uriFactory.ptr_ = 0;
      ptr->Release(ptr);
    }
    ActivationFactory = RoGetActivationFactory(v31, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &uriFactory);
    v8 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v33 = uriFactory.ptr_->CreateUri(uriFactory.ptr_, v4, callbackUri);
      v8 = v33;
      if ( v33 >= 0 )
      {
        v8 = 0;
        goto LABEL_98;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $Exit;
      }
      v28 = 25;
      v29 = v33;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto $Exit;
      }
      v28 = 24;
      v29 = ActivationFactory;
    }
  }
  else
  {
    if ( v11 == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      || (v11[1].ReserveSpace[28] & 8) == 0
      || v11[1].Control.Level < 2u )
    {
      goto $Exit;
    }
    v28 = 23;
    v29 = v8;
  }
  WPP_SF_d(v11[1].Control.Logger, v28, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids, v29);
LABEL_98:
  v11 = WPP_GLOBAL_Control;
$Exit:
  if ( v7 )
  {
    if ( v11 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (v11[1].ReserveSpace[28] & 0x10) != 0
      && v11[1].Control.Level >= 5u )
    {
      WPP_SF_qd(v11[1].Control.Logger, 0x5Fu, (const _GUID *)v6, v7, v7->refCount);
    }
    if ( _InterlockedExchangeAdd(&v7->refCount, 0xFFFFFFFF) == 1 )
    {
      dialogTitle = v7->dialogTitle;
      if ( dialogTitle )
        CoTaskMemFree(dialogTitle);
      v35 = v7->tokenHandle;
      if ( v35 )
        CloseHandle(v35);
      LocalFree(v7);
    }
  }
  v36 = uriFactory.ptr_;
  if ( uriFactory.ptr_ )
  {
    uriFactory.ptr_ = 0;
    v36->Release(v36);
  }
  if ( v4 )
    WindowsDeleteString(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002420  push    rbp
0x180002422  push    r12
0x180002424  push    r13
0x180002426  push    r14
0x180002428  lea     rbp, [rsp-1E8h]
0x180002430  sub     rsp, 2E8h
0x180002437  mov     rax, cs:__security_cookie
0x18000243e  xor     rax, rsp
0x180002441  mov     [rbp+200h+var_30], rax
0x180002448  xor     r12d, r12d
0x18000244b  mov     r13, callbackUri
0x18000244e  mov     [rsp+300h+clientContext], r12
0x180002453  mov     ecx, r12d; brokerFlags
0x180002456  mov     [rsp+300h+uriFactory.ptr_], this
0x18000245b  test    callbackUri, callbackUri
0x18000245e  jnz     short loc_1800024B9
0x180002460  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002467  lea     callbackUri, WPP_GLOBAL_Control
0x18000246e  cmp     rax, callbackUri
0x180002471  jz      short loc_180002499
0x180002473  test    byte ptr [rax+44h], 8
0x180002477  jz      short loc_180002499
0x180002479  cmp     byte ptr [rax+41h], 2
0x18000247d  jb      short loc_180002499
0x18000247f  mov     this, [rax+38h]; Logger
0x180002483  lea     r8, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x18000248a  mov     edx, 16h; id
0x18000248f  call    WPP_SF_
0x180002494  mov     this, [rsp+300h+uriFactory.ptr_]
0x180002499  test    this, this
0x18000249c  jz      short loc_1800024AF
0x18000249e  mov     [rsp+300h+uriFactory.ptr_], r12
0x1800024a3  mov     rax, [this]
0x1800024a6  mov     rax, [rax+10h]
0x1800024aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024af  mov     eax, 80070057h
0x1800024b4  jmp     loc_180002A48
0x1800024b9  mov     [rsp+300h+arg_0], rbx
0x1800024c1  mov     [rsp+300h+arg_10], rsi
0x1800024c9  mov     [callbackUri], r12
0x1800024cc  lea     callbackUri, [rsp+300h+clientContext]; clientContext
0x1800024d1  mov     [rsp+300h+arg_18], rdi
0x1800024d9  mov     rdi, r12
0x1800024dc  mov     [rsp+300h+var_20], r15
0x1800024e4  call    ?GetAndVerifyAuthBrokerClientContext@@YAJIPEAPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z; GetAndVerifyAuthBrokerClientContext(uint,_AUTH_BROKER_CLIENT_CONTEXT * *)
0x1800024e9  mov     r15, [rsp+300h+clientContext]
0x1800024ee  mov     r14d, eax
0x1800024f1  lea     rsi, WPP_GLOBAL_Control
0x1800024f8  test    eax, eax
0x1800024fa  js      loc_18000298F
0x180002500  mov     this, [r15+20h]; TokenHandle
0x180002504  mov     rbx, r12
0x180002507  mov     [rsp+300h+clientContext], rbx
0x18000250c  mov     [rsp+300h+var_2B8], 4Ch ; 'L'
0x180002514  mov     [rsp+300h+StringSid], r12
0x180002519  test    this, this
0x18000251c  jnz     short loc_18000255F
0x18000251e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002525  cmp     r10, rsi
0x180002528  jz      short loc_180002554
0x18000252a  test    byte ptr [r10+44h], 10h
0x18000252f  jz      short loc_180002554
0x180002531  cmp     byte ptr [r10+41h], 2
0x180002536  jb      short loc_180002554
0x180002538  mov     this, [r10+38h]; Logger
0x18000253c  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180002543  mov     edx, 20h ; ' '; id
0x180002548  call    WPP_SF_
0x18000254d  mov     r10, cs:WPP_GLOBAL_Control
0x180002554  mov     r14d, 80070057h
0x18000255a  jmp     loc_18000270C
0x18000255f  lea     rax, [rsp+300h+var_2B8]
0x180002564  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18000256a  lea     r8, [rsp+300h+TokenInformation]; TokenInformation
0x18000256f  mov     [rsp+300h+ReturnLength], rax; ReturnLength
0x180002574  mov     edx, 1Fh; TokenInformationClass
0x180002579  call    cs:__imp_GetTokenInformation
0x18000257f  test    eax, eax
0x180002581  jnz     short loc_1800025DF
0x180002583  call    cs:__imp_GetLastError
0x180002589  mov     r14d, eax
0x18000258c  test    eax, eax
0x18000258e  jle     short loc_18000259B
0x180002590  movzx   r14d, ax
0x180002594  or      r14d, 80070000h
0x18000259b  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800025a2  cmp     r10, rsi
0x1800025a5  jz      short loc_1800025D4
0x1800025a7  test    byte ptr [r10+44h], 10h
0x1800025ac  jz      short loc_1800025D4
0x1800025ae  cmp     byte ptr [r10+41h], 2
0x1800025b3  jb      short loc_1800025D4
0x1800025b5  mov     this, [r10+38h]; Logger
0x1800025b9  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800025c0  mov     edx, 21h ; '!'; id
0x1800025c5  mov     r9d, r14d; _a1
0x1800025c8  call    WPP_SF_d
0x1800025cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800025d4  test    r14d, r14d
0x1800025d7  js      loc_18000270C
0x1800025dd  jmp     short loc_180002613
0x1800025df  mov     this, [rsp+300h+TokenInformation]; Sid
0x1800025e4  lea     callbackUri, [rsp+300h+StringSid]; StringSid
0x1800025e9  call    cs:__imp_ConvertSidToStringSidW
0x1800025ef  test    eax, eax
0x1800025f1  jz      loc_1800026B5
0x1800025f7  mov     rax, [rsp+300h+StringSid]
0x1800025fc  test    rax, rax
0x1800025ff  jz      short loc_18000260C
0x180002601  cmp     word ptr [rax], 53h ; 'S'
0x180002605  jnz     short loc_18000260C
0x180002607  mov     word ptr [rax], 73h ; 's'
0x18000260c  mov     r10, cs:WPP_GLOBAL_Control
0x180002613  mov     r12d, 7FFFFFFEh
0x180002619  lea     callbackUri, aMsApp_0; "ms-app://"
0x180002620  mov     esi, 104h
0x180002625  lea     r9, [rbp+200h+pszDest]
0x180002629  mov     ecx, r12d
0x18000262c  mov     r8d, esi
0x18000262f  test    this, this
0x180002632  jz      short loc_180002651
0x180002634  movzx   eax, word ptr [callbackUri]
0x180002637  test    ax, ax
0x18000263a  jz      short loc_180002651
0x18000263c  mov     [r9], ax
0x180002640  add     callbackUri, 2
0x180002644  add     r9, 2
0x180002648  dec     this
0x18000264b  sub     r8, 1
0x18000264f  jnz     short loc_18000262F
0x180002651  xor     eax, eax
0x180002653  lea     this, [r9-2]
0x180002657  test    r8, r8
0x18000265a  mov     r14d, 8007007Ah
0x180002660  mov     edx, r14d
0x180002663  cmovnz  this, r9
0x180002667  cmovnz  edx, eax
0x18000266a  mov     [this], ax
0x18000266d  jz      loc_180002802
0x180002673  mov     r8, [rsp+300h+StringSid]; pszSrc
0x180002678  lea     this, [rbp+200h+pszDest]; pszDest
0x18000267c  mov     callbackUri, rsi; cchDest
0x18000267f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180002684  test    eax, eax
0x180002686  js      loc_1800027F6
0x18000268c  lea     rax, [rbp+200h+pszDest]
0x180002690  cmp     [rax], bx
0x180002693  jz      loc_180002735
0x180002699  add     rax, 2
0x18000269d  sub     rsi, 1
0x1800026a1  jnz     short loc_180002690
0x1800026a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800026aa  mov     r14d, 80070057h
0x1800026b0  jmp     loc_180002805
0x1800026b5  call    cs:__imp_GetLastError
0x1800026bb  mov     r14d, eax
0x1800026be  test    eax, eax
0x1800026c0  jle     short loc_1800026CD
0x1800026c2  movzx   r14d, ax
0x1800026c6  or      r14d, 80070000h
0x1800026cd  test    r14d, r14d
0x1800026d0  jns     loc_18000260C
0x1800026d6  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800026dd  cmp     r10, rsi
0x1800026e0  jz      loc_180002841
0x1800026e6  test    byte ptr [r10+44h], 10h
0x1800026eb  jz      short loc_18000270C
0x1800026ed  cmp     byte ptr [r10+41h], 2
0x1800026f2  jb      short loc_18000270C
0x1800026f4  mov     this, [r10+38h]; Logger
0x1800026f8  xor     r9d, r9d; Logger
0x1800026fb  mov     dword ptr [rsp+300h+ReturnLength], r14d; id
0x180002700  call    WPP_SF_dd
0x180002705  mov     r10, cs:WPP_GLOBAL_Control
0x18000270c  cmp     r10, rsi; __annotation("TMF:",
0x18000270f  jz      loc_180002841
0x180002715  test    byte ptr [r10+44h], 8
0x18000271a  jz      loc_180002841
0x180002720  cmp     byte ptr [r10+41h], 2
0x180002725  jb      loc_180002841
0x18000272b  mov     edx, 25h ; '%'
0x180002730  jmp     loc_180002827
0x180002735  lea     rax, [rsi+rsi]
0x180002739  lea     callbackUri, [rbp+200h+var_38]
0x180002740  sub     callbackUri, rax
0x180002743  lea     this, asc_1800267C8; "/"
0x18000274a  test    rsi, rsi
0x18000274d  jz      short loc_180002770
0x18000274f  test    r12, r12
0x180002752  jz      short loc_180002770
0x180002754  movzx   eax, word ptr [this]
0x180002757  test    ax, ax
0x18000275a  jz      short loc_180002770
0x18000275c  mov     [callbackUri], ax
0x18000275f  add     this, 2
0x180002763  add     callbackUri, 2
0x180002767  dec     r12
0x18000276a  sub     rsi, 1
0x18000276e  jnz     short loc_18000274F
0x180002770  xor     r12d, r12d
0x180002773  lea     this, [callbackUri-2]
0x180002777  test    rsi, rsi
0x18000277a  cmovnz  this, callbackUri
0x18000277e  cmovnz  r14d, r12d
0x180002782  mov     [this], r12w
0x180002786  jz      short loc_1800027ED
0x180002788  lea     callbackUri, [rbp+200h+pszDest]; str
0x18000278c  lea     this, [rsp+300h+clientContext]; this
0x180002791  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180002796  mov     r14d, eax
0x180002799  test    eax, eax
0x18000279b  js      short loc_1800027E8
0x18000279d  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800027a4  lea     rsi, WPP_GLOBAL_Control
0x1800027ab  cmp     r10, rsi
0x1800027ae  jz      short loc_1800027DE
0x1800027b0  test    byte ptr [r10+44h], 8
0x1800027b5  jz      short loc_1800027DE
0x1800027b7  cmp     byte ptr [r10+41h], 5
0x1800027bc  jb      short loc_1800027DE
0x1800027be  mov     this, [r10+38h]; Logger
0x1800027c2  lea     r9, [rbp+200h+pszDest]; _a1
0x1800027c6  mov     edx, 27h ; '''; id
0x1800027cb  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800027d2  call    WPP_SF_S
0x1800027d7  mov     r10, cs:WPP_GLOBAL_Control
0x1800027de  mov     rdi, [rsp+300h+clientContext]
0x1800027e3  mov     r14d, r12d
0x1800027e6  jmp     short loc_180002841
0x1800027e8  mov     rbx, [rsp+300h+clientContext]
0x1800027ed  mov     r10, cs:WPP_GLOBAL_Control
0x1800027f4  jmp     short loc_180002808
0x1800027f6  mov     r10, cs:WPP_GLOBAL_Control
0x1800027fd  mov     r14d, eax
0x180002800  jmp     short loc_180002805
0x180002802  mov     r14d, edx
0x180002805  xor     r12d, r12d
0x180002808  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18000280f  cmp     r10, rsi
0x180002812  jz      short loc_180002841
0x180002814  test    byte ptr [r10+44h], 8
0x180002819  jz      short loc_180002841
0x18000281b  cmp     byte ptr [r10+41h], 2
0x180002820  jb      short loc_180002841
0x180002822  mov     edx, 26h ; '&'; id
0x180002827  mov     this, [r10+38h]; Logger
0x18000282b  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x180002832  mov     r9d, r14d; _a1
0x180002835  call    WPP_SF_d
0x18000283a  mov     r10, cs:WPP_GLOBAL_Control
0x180002841  mov     this, [rsp+300h+StringSid]; hMem
0x180002846  test    this, this
0x180002849  jz      short loc_180002858
0x18000284b  call    cs:__imp_LocalFree
0x180002851  mov     r10, cs:WPP_GLOBAL_Control
0x180002858  test    rbx, rbx
0x18000285b  jz      short loc_18000286D
0x18000285d  mov     this, rbx; string
0x180002860  call    cs:__imp_WindowsDeleteString
0x180002866  mov     r10, cs:WPP_GLOBAL_Control
0x18000286d  test    r14d, r14d
0x180002870  jns     short loc_1800028AE
0x180002872  cmp     r10, rsi; __annotation("TMF:",
0x180002875  jz      $Exit
0x18000287b  test    byte ptr [r10+44h], 8
0x180002880  jz      $Exit
0x180002886  cmp     byte ptr [r10+41h], 2
0x18000288b  jb      $Exit
0x180002891  mov     edx, 17h; id
0x180002896  mov     r9d, r14d; _a1
0x180002899  mov     this, [r10+38h]; Logger
0x18000289d  lea     r8, WPP_9fbdb3fdc391393d582c6c107e1b2862_Traceguids; TraceGuid
0x1800028a4  call    WPP_SF_d
0x1800028a9  jmp     loc_18000298F
0x1800028ae  lea     r9, [rsp+300h+string]; string
0x1800028b3  mov     edx, 16h; length
0x1800028b8  lea     r8, [rsp+300h+hstringHeader]; hstringHeader
0x1800028bd  lea     this, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; sourceString
0x1800028c4  call    cs:__imp_WindowsCreateStringReference
0x1800028ca  test    eax, eax
0x1800028cc  jns     short loc_1800028E4
0x1800028ce  xor     r9d, r9d; lpArguments
0x1800028d1  xor     r8d, r8d; nNumberOfArguments
0x1800028d4  mov     edx, 1; dwExceptionFlags
0x1800028d9  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800028de  call    cs:__imp_RaiseException
0x1800028e4  mov     this, [rsp+300h+uriFactory.ptr_]
0x1800028e9  mov     rbx, [rsp+300h+string]
0x1800028ee  test    this, this
0x1800028f1  jz      short loc_180002904
0x1800028f3  mov     [rsp+300h+uriFactory.ptr_], r12
0x1800028f8  mov     rax, [this]
0x1800028fb  mov     rax, [rax+10h]
0x1800028ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002904  lea     r8, [rsp+300h+uriFactory]
0x180002909  mov     this, rbx
0x18000290c  lea     callbackUri, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180002913  call    cs:__imp_RoGetActivationFactory
0x180002919  mov     r14d, eax
0x18000291c  test    eax, eax
  ... truncated ...
```
