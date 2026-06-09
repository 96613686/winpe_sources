# CSession::_SmartCardReadersPresent(void)

- ea: `0x18000f138`
- end: `0x18000f755`
- name: `?_SmartCardReadersPresent@CSession@@AEAA_NXZ`
- size: `1565`
- prototype: `char __fastcall(CSession *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000d754`

## callees

- `0x180006d40`
- `0x180007178`
- `0x1800071d4`
- `0x18000c8c8`
- `0x18000d1bc`
- `0x18000d534`
- `0x18000d5a4`
- `0x18000d890`
- `0x18000d8b0`
- `0x18000f138`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f325`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f44a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f53a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f44a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f53a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f319`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f3dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f516`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f557`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f63c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f685`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f6c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f70a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f319`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f3dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f516`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f557`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f63c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f685`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f6c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f70a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f1ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f1ca`
- `WinSCard!SCardEstablishContext` at `0x18000f488`
- `WinSCard!SCardEstablishContext` at `0x18000f488`
- `WinSCard!SCardListReadersW` at `0x18000f5a4`
- `WinSCard!SCardListReadersW` at `0x18000f5a4`
- `WinSCard!SCardAccessStartedEvent` at `0x18000f259`
- `WinSCard!SCardAccessStartedEvent` at `0x18000f259`

## string_xrefs

- `0x18000f17c`: `CSession::_SmartCardReadersPresent`
- `0x18000f590`: `SCard$AllReaders`

## pseudocode

```c
char __fastcall CSession::_SmartCardReadersPresent(CSession *this)
{
  void *v2; // rdx
  __int64 v3; // rcx
  char LastError; // al
  HANDLE v6; // rax
  __int64 v7; // rcx
  char v8; // al
  int v9; // eax
  DWORD v10; // eax
  __int64 v11; // rcx
  char v12; // al
  int v13; // eax
  int v14; // eax
  LONG v15; // eax
  __int64 v16; // rcx
  char v17; // di
  int v18; // eax
  int v19; // eax
  LONG v20; // eax
  __int64 v21; // rcx
  char v22; // di
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  char v27; // bl
  char v28; // [rsp+30h] [rbp-89h] BYREF
  void **v29; // [rsp+38h] [rbp-81h] BYREF
  HANDLE v30; // [rsp+40h] [rbp-79h]
  void **v31; // [rsp+48h] [rbp-71h] BYREF
  SCARDCONTEXT phContext; // [rsp+50h] [rbp-69h] BYREF
  int v33; // [rsp+58h] [rbp-61h] BYREF
  _QWORD *v34; // [rsp+60h] [rbp-59h] BYREF
  DWORD pcchReaders; // [rsp+68h] [rbp-51h] BYREF
  WCHAR mszReaders[4]; // [rsp+70h] [rbp-49h] BYREF
  char *v37; // [rsp+78h] [rbp-41h] BYREF
  __int16 v38; // [rsp+80h] [rbp-39h]
  _QWORD v39[2]; // [rsp+88h] [rbp-31h] BYREF
  __int16 v40; // [rsp+98h] [rbp-21h]
  _QWORD v41[3]; // [rsp+A0h] [rbp-19h] BYREF
  char v42[40]; // [rsp+B8h] [rbp-1h] BYREF

  v28 = 1;
  v41[0] = v42;
  v41[1] = &v33;
  v41[2] = &v28;
  v33 = 0;
  strcpy(v42, "CSession::_SmartCardReadersPresent");
  lambda_c99f3daa81d7a44352f9375834bc78d6_::operator()(v41);
  v2 = (void *)*((_QWORD *)this + 3);
  v34 = v41;
  v33 = 1;
  if ( !SetThreadToken(0, v2) )
  {
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError);
    }
    v28 = 0;
    goto LABEL_7;
  }
  v38 = 258;
  v37 = &v28;
  v6 = SCardAccessStartedEvent();
  v30 = v6;
  v29 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable';
  if ( !v6 )
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = GetLastError();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v8);
    }
    v28 = 0;
    v29 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable';
    if ( !v30 )
      goto LABEL_55;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(&v29) )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      RaiseException(v9, 1u, 0, 0);
      __debugbreak();
    }
LABEL_54:
    v30 = 0;
LABEL_55:
    wil::details::ScopeExitFnGuard__lambda_b5f6e3736ce8738e22e5d7c49ff256da___::operator()(&v37);
LABEL_7:
    WppTraceUnwinder__lambda_c99f3daa81d7a44352f9375834bc78d6____::_WppTraceUnwinder__lambda_c99f3daa81d7a44352f9375834bc78d6____(&v34);
    return 0;
  }
  v10 = WaitForSingleObject(v6, 0);
  if ( v10 )
  {
    if ( v10 == -1 )
    {
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = GetLastError();
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
          (_DWORD)WPP_pszIndent,
          v12);
      }
      v28 = 0;
      v29 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable';
      if ( !v30 )
        goto LABEL_55;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(&v29) )
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        RaiseException(v13, 1u, 0, 0);
        __debugbreak();
      }
    }
    else
    {
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          &WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
          WPP_pszIndent);
      }
      v28 = 0;
      v29 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable';
      if ( !v30 )
        goto LABEL_55;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(&v29) )
      {
        v14 = GetLastError();
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        RaiseException(v14, 1u, 0, 0);
        __debugbreak();
      }
    }
    goto LABEL_54;
  }
  phContext = 0;
  v31 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
  v15 = SCardEstablishContext(0, 0, 0, &phContext);
  v17 = v15;
  if ( v15 )
  {
    WppTraceIndent(v16, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v17);
    }
    v28 = 0;
    v31 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
    if ( phContext )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(&v31) )
      {
        v18 = GetLastError();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        RaiseException(v18, 1u, 0, 0);
        __debugbreak();
      }
      phContext = 0;
    }
    v29 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable';
    if ( !v30 )
      goto LABEL_55;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(&v29) )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      RaiseException(v19, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_54;
  }
  v39[0] = mszReaders;
  *(_QWORD *)mszReaders = 0;
  v39[1] = &v31;
  v40 = 256;
  pcchReaders = -1;
  v20 = SCardListReadersW(phContext, L"SCard$AllReaders", mszReaders, &pcchReaders);
  v22 = v20;
  if ( v20 )
  {
    WppTraceIndent(v21, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v22);
    }
    v28 = 0;
    wil::details::ScopeExitFnGuard__lambda_3f4643eed9ab8028b196189063c974a7___::operator()(v39);
    v31 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
    if ( phContext )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(&v31) )
      {
        v23 = GetLastError();
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        RaiseException(v23, 1u, 0, 0);
        __debugbreak();
      }
      phContext = 0;
    }
    v29 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable';
    if ( !v30 )
      goto LABEL_55;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(&v29) )
    {
      v24 = GetLastError();
      if ( v24 > 0 )
        v24 = (unsigned __int16)v24 | 0x80070000;
      RaiseException(v24, 1u, 0, 0);
      __debugbreak();
    }
    goto LABEL_54;
  }
  wil::details::ScopeExitFnGuard__lambda_3f4643eed9ab8028b196189063c974a7___::operator()(v39);
  v31 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable';
  if ( phContext )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(&v31) )
    {
      v25 = GetLastError();
      if ( v25 > 0 )
        v25 = (unsigned __int16)v25 | 0x80070000;
      RaiseException(v25, 1u, 0, 0);
      __debugbreak();
    }
    phContext = 0;
  }
  v29 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable';
  if ( v30 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(&v29) )
    {
      v26 = GetLastError();
      if ( v26 > 0 )
        v26 = (unsigned __int16)v26 | 0x80070000;
      RaiseException(v26, 1u, 0, 0);
      __debugbreak();
    }
    v30 = 0;
  }
  wil::details::ScopeExitFnGuard__lambda_b5f6e3736ce8738e22e5d7c49ff256da___::operator()(&v37);
  v27 = v28;
  WppTraceUnwinder__lambda_c99f3daa81d7a44352f9375834bc78d6____::_WppTraceUnwinder__lambda_c99f3daa81d7a44352f9375834bc78d6____(&v34);
  return v27;
}

```

## disassembly

```asm
0x18000f138  mov     [rsp-8+arg_8], rbx
0x18000f13d  mov     [rsp-8+arg_10], rsi
0x18000f142  push    rbp
0x18000f143  push    rdi
0x18000f144  push    r12
0x18000f146  push    r14
0x18000f148  push    r15
0x18000f14a  lea     rbp, [rsp-37h]
0x18000f14f  sub     rsp, 0F0h
0x18000f156  mov     rax, cs:__security_cookie
0x18000f15d  xor     rax, rsp
0x18000f160  mov     [rbp+57h+var_30], rax
0x18000f164  mov     eax, dword ptr cs:aCsessionSmartc+1Fh; "ent"
0x18000f16a  mov     rbx, rcx
0x18000f16d  movups  xmm1, xmmword ptr cs:aCsessionSmartc+10h; "CardReadersPresent"
0x18000f174  mov     r14d, 1
0x18000f17a  xor     esi, esi
0x18000f17c  movups  xmm0, xmmword ptr cs:aCsessionSmartc; "CSession::_SmartCardReadersPresent"
0x18000f183  lea     rcx, [rbp+57h+var_70]
0x18000f187  mov     [rsp+110h+var_E0], r14b
0x18000f18c  movups  xmmword ptr [rbp+57h+var_58+10h], xmm1
0x18000f190  mov     dword ptr [rbp+57h+var_58+1Fh], eax
0x18000f193  lea     rax, [rbp+57h+var_58]
0x18000f197  mov     [rbp+57h+var_70], rax
0x18000f19b  lea     rax, [rbp+57h+var_B8]
0x18000f19f  mov     [rbp+57h+var_68], rax
0x18000f1a3  lea     rax, [rsp+110h+var_E0]
0x18000f1a8  mov     [rbp+57h+var_60], rax
0x18000f1ac  mov     [rbp+57h+var_B8], esi
0x18000f1af  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18000f1b3  call    _lambda_c99f3daa81d7a44352f9375834bc78d6___operator__
0x18000f1b8  mov     rdx, [rbx+18h]; Token
0x18000f1bc  lea     rax, [rbp+57h+var_70]
0x18000f1c0  xor     ecx, ecx; Thread
0x18000f1c2  mov     [rbp+57h+var_B0], rax
0x18000f1c6  mov     [rbp+57h+var_B8], r14d
0x18000f1ca  call    cs:__imp_SetThreadToken
0x18000f1d0  lea     ebx, [rsi+2]
0x18000f1d3  test    eax, eax
0x18000f1d5  jnz     short loc_18000F24A
0x18000f1d7  mov     edx, ebx
0x18000f1d9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1e5  lea     rax, WPP_GLOBAL_Control
0x18000f1ec  cmp     rcx, rax
0x18000f1ef  jz      short loc_18000F235
0x18000f1f1  test    [rcx+1Ch], r14b
0x18000f1f5  jz      short loc_18000F235
0x18000f1f7  cmp     [rcx+19h], bl
0x18000f1fa  jb      short loc_18000F235
0x18000f1fc  call    cs:__imp_GetLastError
0x18000f202  test    eax, eax
0x18000f204  jle     short loc_18000F20E
0x18000f206  movzx   eax, ax
0x18000f209  or      eax, 80070000h
0x18000f20e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f215  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000f21c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f223  mov     edx, 1Fh
0x18000f228  mov     [rsp+110h+var_F0], eax
0x18000f22c  mov     rcx, [rcx+10h]
0x18000f230  call    WPP_SF_sd
0x18000f235  mov     [rsp+110h+var_E0], sil
0x18000f23a  lea     rcx, [rbp+57h+var_B0]
0x18000f23e  call    WppTraceUnwinder__lambda_c99f3daa81d7a44352f9375834bc78d6_______WppTraceUnwinder__lambda_c99f3daa81d7a44352f9375834bc78d6____
0x18000f243  xor     al, al
0x18000f245  jmp     loc_18000F72D
0x18000f24a  lea     rax, [rsp+110h+var_E0]
0x18000f24f  mov     [rbp+57h+var_90], 102h
0x18000f255  mov     [rbp+57h+var_98], rax
0x18000f259  call    cs:__imp_SCardAccessStartedEvent
0x18000f25f  mov     [rbp+57h+var_D0], rax
0x18000f263  lea     r15, ??_7?$HandleT@USCardStartedEventTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::`vftable'
0x18000f26a  mov     [rsp+110h+var_D8], r15
0x18000f26f  test    rax, rax
0x18000f272  jnz     loc_18000F320
0x18000f278  mov     edx, ebx
0x18000f27a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f27f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f286  lea     rax, WPP_GLOBAL_Control
0x18000f28d  cmp     rcx, rax
0x18000f290  jz      short loc_18000F2D6
0x18000f292  test    [rcx+1Ch], r14b
0x18000f296  jz      short loc_18000F2D6
0x18000f298  cmp     [rcx+19h], bl
0x18000f29b  jb      short loc_18000F2D6
0x18000f29d  call    cs:__imp_GetLastError
0x18000f2a3  test    eax, eax
0x18000f2a5  jle     short loc_18000F2AF
0x18000f2a7  movzx   eax, ax
0x18000f2aa  or      eax, 80070000h
0x18000f2af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2b6  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000f2bd  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f2c4  mov     edx, 20h ; ' '
0x18000f2c9  mov     [rsp+110h+var_F0], eax
0x18000f2cd  mov     rcx, [rcx+10h]
0x18000f2d1  call    WPP_SF_sd
0x18000f2d6  mov     [rsp+110h+var_E0], sil
0x18000f2db  mov     [rsp+110h+var_D8], r15
0x18000f2e0  cmp     [rbp+57h+var_D0], rsi
0x18000f2e4  jz      loc_18000F562
0x18000f2ea  lea     rcx, [rsp+110h+var_D8]
0x18000f2ef  call    ?InternalClose@?$HandleT@USCardStartedEventTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(void)
0x18000f2f4  test    al, al
0x18000f2f6  jnz     loc_18000F55E
0x18000f2fc  call    cs:__imp_GetLastError
0x18000f302  test    eax, eax
0x18000f304  jle     short loc_18000F30E
0x18000f306  movzx   eax, ax
0x18000f309  or      eax, 80070000h
0x18000f30e  xor     r9d, r9d; lpArguments
0x18000f311  xor     r8d, r8d; nNumberOfArguments
0x18000f314  mov     edx, r14d; dwExceptionFlags
0x18000f317  mov     ecx, eax; dwExceptionCode
0x18000f319  call    cs:__imp_RaiseException
0x18000f31f  int     3; Trap to Debugger
0x18000f320  xor     edx, edx; dwMilliseconds
0x18000f322  mov     rcx, rax; hHandle
0x18000f325  call    cs:__imp_WaitForSingleObject
0x18000f32b  test    eax, eax
0x18000f32d  jz      loc_18000F46E
0x18000f333  mov     edx, ebx
0x18000f335  cmp     eax, 0FFFFFFFFh
0x18000f338  jnz     loc_18000F3E4
0x18000f33e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f343  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f34a  lea     rax, WPP_GLOBAL_Control
0x18000f351  cmp     rcx, rax
0x18000f354  jz      short loc_18000F39A
0x18000f356  test    [rcx+1Ch], r14b
0x18000f35a  jz      short loc_18000F39A
0x18000f35c  cmp     [rcx+19h], bl
0x18000f35f  jb      short loc_18000F39A
0x18000f361  call    cs:__imp_GetLastError
0x18000f367  test    eax, eax
0x18000f369  jle     short loc_18000F373
0x18000f36b  movzx   eax, ax
0x18000f36e  or      eax, 80070000h
0x18000f373  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f37a  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000f381  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f388  mov     edx, 21h ; '!'
0x18000f38d  mov     [rsp+110h+var_F0], eax
0x18000f391  mov     rcx, [rcx+10h]
0x18000f395  call    WPP_SF_sd
0x18000f39a  mov     [rsp+110h+var_E0], sil
0x18000f39f  mov     [rsp+110h+var_D8], r15
0x18000f3a4  cmp     [rbp+57h+var_D0], rsi
0x18000f3a8  jz      loc_18000F562
0x18000f3ae  lea     rcx, [rsp+110h+var_D8]
0x18000f3b3  call    ?InternalClose@?$HandleT@USCardStartedEventTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(void)
0x18000f3b8  test    al, al
0x18000f3ba  jnz     loc_18000F55E
0x18000f3c0  call    cs:__imp_GetLastError
0x18000f3c6  test    eax, eax
0x18000f3c8  jle     short loc_18000F3D2
0x18000f3ca  movzx   eax, ax
0x18000f3cd  or      eax, 80070000h
0x18000f3d2  xor     r9d, r9d; lpArguments
0x18000f3d5  xor     r8d, r8d; nNumberOfArguments
0x18000f3d8  mov     edx, r14d; dwExceptionFlags
0x18000f3db  mov     ecx, eax; dwExceptionCode
0x18000f3dd  call    cs:__imp_RaiseException
0x18000f3e3  int     3; Trap to Debugger
0x18000f3e4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3f0  lea     rax, WPP_GLOBAL_Control
0x18000f3f7  cmp     rcx, rax
0x18000f3fa  jz      short loc_18000F424
0x18000f3fc  test    [rcx+1Ch], r14b
0x18000f400  jz      short loc_18000F424
0x18000f402  cmp     byte ptr [rcx+19h], 4
0x18000f406  jb      short loc_18000F424
0x18000f408  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f40f  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000f416  mov     rcx, [rcx+10h]
0x18000f41a  mov     edx, 22h ; '"'
0x18000f41f  call    WPP_SF_s
0x18000f424  mov     [rsp+110h+var_E0], sil
0x18000f429  mov     [rsp+110h+var_D8], r15
0x18000f42e  cmp     [rbp+57h+var_D0], rsi
0x18000f432  jz      loc_18000F562
0x18000f438  lea     rcx, [rsp+110h+var_D8]
0x18000f43d  call    ?InternalClose@?$HandleT@USCardStartedEventTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(void)
0x18000f442  test    al, al
0x18000f444  jnz     loc_18000F55E
0x18000f44a  call    cs:__imp_GetLastError
0x18000f450  test    eax, eax
0x18000f452  jle     short loc_18000F45C
0x18000f454  movzx   eax, ax
0x18000f457  or      eax, 80070000h
0x18000f45c  xor     r9d, r9d; lpArguments
0x18000f45f  xor     r8d, r8d; nNumberOfArguments
0x18000f462  mov     edx, r14d; dwExceptionFlags
0x18000f465  mov     ecx, eax; dwExceptionCode
0x18000f467  call    cs:__imp_RaiseException
0x18000f46d  int     3; Trap to Debugger
0x18000f46e  lea     r12, ??_7?$HandleT@USCardContextTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::`vftable'
0x18000f475  mov     [rbp+57h+phContext], rsi
0x18000f479  lea     r9, [rbp+57h+phContext]; phContext
0x18000f47d  mov     [rbp+57h+var_C8], r12
0x18000f481  xor     r8d, r8d; pvReserved2
0x18000f484  xor     edx, edx; pvReserved1
0x18000f486  xor     ecx, ecx; dwScope
0x18000f488  call    cs:__imp_SCardEstablishContext
0x18000f48e  mov     edi, eax
0x18000f490  test    eax, eax
0x18000f492  jz      loc_18000F570
0x18000f498  mov     edx, ebx
0x18000f49a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f49f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4a6  lea     rax, WPP_GLOBAL_Control
0x18000f4ad  cmp     rcx, rax
0x18000f4b0  jz      short loc_18000F4DD
0x18000f4b2  test    [rcx+1Ch], r14b
0x18000f4b6  jz      short loc_18000F4DD
0x18000f4b8  cmp     [rcx+19h], bl
0x18000f4bb  jb      short loc_18000F4DD
0x18000f4bd  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f4c4  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000f4cb  mov     rcx, [rcx+10h]
0x18000f4cf  mov     edx, 23h ; '#'
0x18000f4d4  mov     [rsp+110h+var_F0], edi
0x18000f4d8  call    WPP_SF_sd
0x18000f4dd  mov     [rsp+110h+var_E0], sil
0x18000f4e2  mov     [rbp+57h+var_C8], r12
0x18000f4e6  cmp     [rbp+57h+phContext], rsi
0x18000f4ea  jz      short loc_18000F521
0x18000f4ec  lea     rcx, [rbp+57h+var_C8]
0x18000f4f0  call    ?InternalClose@?$HandleT@USCardContextTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardContextTraits>::InternalClose(void)
0x18000f4f5  test    al, al
0x18000f4f7  jnz     short loc_18000F51D
0x18000f4f9  call    cs:__imp_GetLastError
0x18000f4ff  test    eax, eax
0x18000f501  jle     short loc_18000F50B
0x18000f503  movzx   eax, ax
0x18000f506  or      eax, 80070000h
0x18000f50b  xor     r9d, r9d; lpArguments
0x18000f50e  xor     r8d, r8d; nNumberOfArguments
0x18000f511  mov     edx, r14d; dwExceptionFlags
0x18000f514  mov     ecx, eax; dwExceptionCode
0x18000f516  call    cs:__imp_RaiseException
0x18000f51c  int     3; Trap to Debugger
0x18000f51d  mov     [rbp+57h+phContext], rsi
0x18000f521  mov     [rsp+110h+var_D8], r15
0x18000f526  cmp     [rbp+57h+var_D0], rsi
0x18000f52a  jz      short loc_18000F562
0x18000f52c  lea     rcx, [rsp+110h+var_D8]
0x18000f531  call    ?InternalClose@?$HandleT@USCardStartedEventTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SCardStartedEventTraits>::InternalClose(void)
0x18000f536  test    al, al
0x18000f538  jnz     short loc_18000F55E
0x18000f53a  call    cs:__imp_GetLastError
0x18000f540  test    eax, eax
0x18000f542  jle     short loc_18000F54C
0x18000f544  movzx   eax, ax
0x18000f547  or      eax, 80070000h
0x18000f54c  xor     r9d, r9d; lpArguments
0x18000f54f  xor     r8d, r8d; nNumberOfArguments
0x18000f552  mov     edx, r14d; dwExceptionFlags
0x18000f555  mov     ecx, eax; dwExceptionCode
0x18000f557  call    cs:__imp_RaiseException
0x18000f55d  int     3; Trap to Debugger
0x18000f55e  mov     [rbp+57h+var_D0], rsi
0x18000f562  lea     rcx, [rbp+57h+var_98]
0x18000f566  call    wil__details__ScopeExitFnGuard__lambda_b5f6e3736ce8738e22e5d7c49ff256da_____operator__
0x18000f56b  jmp     loc_18000F23A
0x18000f570  mov     rcx, [rbp+57h+phContext]; hContext
0x18000f574  lea     rax, [rbp+57h+mszReaders]
0x18000f578  mov     [rbp+57h+var_88], rax
0x18000f57c  lea     r9, [rbp+57h+pcchReaders]; pcchReaders
0x18000f580  lea     rax, [rbp+57h+var_C8]
0x18000f584  mov     qword ptr [rbp+57h+mszReaders], rsi
0x18000f588  lea     r8, [rbp+57h+mszReaders]; mszReaders
0x18000f58c  mov     [rbp+57h+var_80], rax
0x18000f590  lea     rdx, mszGroups; "SCard$AllReaders"
0x18000f597  mov     [rbp+57h+var_78], 100h
0x18000f59d  mov     [rbp+57h+pcchReaders], 0FFFFFFFFh
0x18000f5a4  call    cs:__imp_SCardListReadersW
0x18000f5aa  mov     edi, eax
0x18000f5ac  test    eax, eax
0x18000f5ae  jz      loc_18000F68C
0x18000f5b4  mov     edx, ebx
0x18000f5b6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5c2  lea     rax, WPP_GLOBAL_Control
0x18000f5c9  cmp     rcx, rax
0x18000f5cc  jz      short loc_18000F5FA
0x18000f5ce  test    [rcx+1Ch], r14b
0x18000f5d2  jz      short loc_18000F5FA
0x18000f5d4  cmp     byte ptr [rcx+19h], 4
0x18000f5d8  jb      short loc_18000F5FA
0x18000f5da  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f5e1  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000f5e8  mov     rcx, [rcx+10h]
0x18000f5ec  mov     edx, 24h ; '$'
0x18000f5f1  mov     [rsp+110h+var_F0], edi
0x18000f5f5  call    WPP_SF_sd
0x18000f5fa  lea     rcx, [rbp+57h+var_88]
0x18000f5fe  mov     [rsp+110h+var_E0], sil
  ... truncated ...
```
