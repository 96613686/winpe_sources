# CEventNotificationService::GetAllSessions(int *,__MIDL___MIDL_itf_wmssvc_0000_0010_0004 * *)

- ea: `0x1400192b0`
- end: `0x1400197fd`
- name: `?GetAllSessions@CEventNotificationService@@UEAAJPEAHPEAPEAU__MIDL___MIDL_itf_wmssvc_0000_0010_0004@@@Z`
- size: `1357`
- prototype: `__int64 __fastcall(CEventNotificationService *__hidden this, int *, struct __MIDL___MIDL_itf_wmssvc_0000_0010_0004 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x1400192b0`
- `0x1400282a8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140068884`
- `0x14006c590`
- `0x1400733b0`
- `0x140076348`
- `0x14007e010`

## import_xrefs

- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x140019438`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x140019438`
- `KERNEL32!GetLastError` at `0x140019482`
- `KERNEL32!GetLastError` at `0x14001968d`
- `KERNEL32!GetLastError` at `0x14001969c`
- `KERNEL32!GetLastError` at `0x1400196e6`
- `KERNEL32!GetLastError` at `0x1400196f5`
- `KERNEL32!GetLastError` at `0x140019482`
- `KERNEL32!GetLastError` at `0x14001968d`
- `KERNEL32!GetLastError` at `0x14001969c`
- `KERNEL32!GetLastError` at `0x1400196e6`
- `KERNEL32!GetLastError` at `0x1400196f5`
- `KERNEL32!IsDebuggerPresent` at `0x140019368`
- `KERNEL32!IsDebuggerPresent` at `0x14001941d`
- `KERNEL32!IsDebuggerPresent` at `0x1400194dd`
- `KERNEL32!IsDebuggerPresent` at `0x140019577`
- `KERNEL32!IsDebuggerPresent` at `0x140019368`
- `KERNEL32!IsDebuggerPresent` at `0x14001941d`
- `KERNEL32!IsDebuggerPresent` at `0x1400194dd`
- `KERNEL32!IsDebuggerPresent` at `0x140019577`
- `ole32!CoTaskMemFree` at `0x1400197dd`
- `ole32!CoTaskMemFree` at `0x1400197dd`
- `ole32!CoTaskMemAlloc` at `0x140019528`
- `ole32!CoTaskMemAlloc` at `0x140019528`
- `WINSTA!WinStationQueryInformationW` at `0x140019683`
- `WINSTA!WinStationQueryInformationW` at `0x140019683`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x140019474`
- `WTSAPI32!WTSEnumerateSessionsExW` at `0x140019474`
- `WTSAPI32!WTSFreeMemory` at `0x140019650`
- `WTSAPI32!WTSFreeMemory` at `0x1400197c5`
- `WTSAPI32!WTSFreeMemory` at `0x1400197d4`
- `WTSAPI32!WTSFreeMemory` at `0x140019650`
- `WTSAPI32!WTSFreeMemory` at `0x1400197c5`
- `WTSAPI32!WTSFreeMemory` at `0x1400197d4`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400196dc`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400196dc`

## string_xrefs

- `0x14001933b`: `CEventNotificationService::GetAllSessions`
- `0x1400193f0`: `CEventNotificationService::GetAllSessions`
- `0x1400194a2`: `CEventNotificationService::GetAllSessions`
- `0x140019542`: `CEventNotificationService::GetAllSessions`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::GetAllSessions(
        CEventNotificationService *this,
        int *a2,
        struct __MIDL___MIDL_itf_wmssvc_0000_0010_0004 **a3)
{
  struct __MIDL___MIDL_itf_wmssvc_0000_0010_0004 *v3; // r12
  int IsWmsShellSession; // ebx
  unsigned int v8; // r13d
  bool v9; // zf
  const unsigned __int16 *v10; // rax
  int *v11; // rdx
  signed int LastError; // eax
  struct __MIDL___MIDL_itf_wmssvc_0000_0010_0004 *v13; // rax
  __int64 v14; // r14
  struct __MIDL___MIDL_itf_wmssvc_0000_0010_0004 *v15; // rdi
  __int64 v16; // rsi
  DWORD SessionId; // ecx
  signed int v18; // eax
  DWORD v19; // edx
  signed int v20; // eax
  const unsigned __int16 *v21; // rcx
  const unsigned __int16 *v23; // [rsp+28h] [rbp-48h]
  const unsigned __int16 *v24; // [rsp+30h] [rbp-40h]
  int v25; // [rsp+30h] [rbp-40h]
  int v26; // [rsp+38h] [rbp-38h]
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+40h] [rbp-30h] BYREF
  int v28; // [rsp+48h] [rbp-28h] BYREF
  int v29; // [rsp+4Ch] [rbp-24h] BYREF
  int v30; // [rsp+50h] [rbp-20h] BYREF
  DWORD active; // [rsp+54h] [rbp-1Ch]
  DWORD pBytesReturned; // [rsp+58h] [rbp-18h] BYREF
  int v33; // [rsp+5Ch] [rbp-14h] BYREF
  PVOID pMemory; // [rsp+60h] [rbp-10h] BYREF
  DWORD pLevel; // [rsp+68h] [rbp-8h] BYREF
  DWORD pCount; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v29 = 0;
  pLevel = 1;
  ppSessionInfo = 0;
  pCount = 0;
  pBytesReturned = 0;
  pMemory = 0;
  v33 = 0;
  v30 = 0;
  IsWmsShellSession = CUserManagement::s_VerifyAccessLevelEx(3u, 0);
  if ( IsWmsShellSession < 0 )
    goto LABEL_62;
  if ( !a2 )
  {
    v8 = 3309;
    IsWmsShellSession = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xCEDu,
      L"CEventNotificationService::GetAllSessions",
      L"CBRAEx",
      L"pcSessionInfo",
      -2147467261);
    v9 = !IsDebuggerPresent();
    v10 = L"pcSessionInfo";
LABEL_4:
    if ( !v9 )
    {
      v26 = -2147467261;
      v24 = v10;
      goto LABEL_6;
    }
    v25 = -2147467261;
    v23 = v10;
    goto LABEL_9;
  }
  if ( !a3 )
  {
    v8 = 3310;
    IsWmsShellSession = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xCEEu,
      L"CEventNotificationService::GetAllSessions",
      L"CBRAEx",
      L"pprgWmsSessionInfo",
      -2147467261);
    v9 = !IsDebuggerPresent();
    v10 = L"pprgWmsSessionInfo";
    goto LABEL_4;
  }
  *a2 = 0;
  *a3 = 0;
  active = WTSGetActiveConsoleSessionId();
  IsWmsShellSession = (*(__int64 (__fastcall **)(CEventNotificationService *, int *))(*(_QWORD *)this + 104LL))(
                        this,
                        &v29);
  if ( IsWmsShellSession < 0 )
    goto LABEL_62;
  if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &pCount) )
  {
    LastError = GetLastError();
    IsWmsShellSession = LastError;
    if ( LastError > 0 )
      IsWmsShellSession = (unsigned __int16)LastError | 0x80070000;
    v8 = 3323;
    goto LABEL_18;
  }
  if ( !pCount )
  {
    IsWmsShellSession = 0;
    goto LABEL_62;
  }
  v28 = 0;
  PlatformSkuUtils::IsRole((PlatformSkuUtils *)&v28, v11);
  v13 = (struct __MIDL___MIDL_itf_wmssvc_0000_0010_0004 *)CoTaskMemAlloc(40LL * pCount);
  v3 = v13;
  if ( !v13 )
  {
    IsWmsShellSession = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0xD02u,
      L"CEventNotificationService::GetAllSessions",
      L"CPR",
      L"prgWmsSessionInfo",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        3330,
        L"CEventNotificationService::GetAllSessions",
        L"CPR",
        L"prgWmsSessionInfo",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        3330,
        L"CEventNotificationService::GetAllSessions",
        L"CPR",
        L"prgWmsSessionInfo",
        -2147024882);
    goto LABEL_62;
  }
  v14 = 0;
  v15 = v13;
  if ( !pCount )
  {
LABEL_61:
    *a2 = -858993459 * ((v15 - v3) >> 3);
    *a3 = v3;
    v3 = 0;
    goto LABEL_62;
  }
  while ( 1 )
  {
    v16 = v14;
    SessionId = ppSessionInfo[v14].SessionId;
    if ( !SessionId || ppSessionInfo[v16].State == WTSListen || ppSessionInfo[v16].State == WTSConnected )
      goto LABEL_60;
    if ( v28 && SessionId == active )
    {
      if ( v29 == 1 )
        goto LABEL_60;
      IsWmsShellSession = CEventNotificationService::s_IsWmsShellSession(SessionId, &v30);
      if ( IsWmsShellSession < 0 )
        goto LABEL_62;
      if ( v30 )
        goto LABEL_60;
    }
    if ( ppSessionInfo[v16].pHostName
      || !ppSessionInfo[v16].pUserName
      || (unsigned int)GetSessionType(ppSessionInfo[v16].SessionId) == 6 )
    {
      goto LABEL_60;
    }
    if ( pMemory )
    {
      WTSFreeMemory(pMemory);
      pMemory = 0;
    }
    if ( (unsigned __int8)WinStationQueryInformationW(0, ppSessionInfo[v16].SessionId, 39, &v33, 4, &pBytesReturned) )
      break;
    if ( GetLastError() != 2 )
    {
      v18 = GetLastError();
      IsWmsShellSession = v18;
      if ( v18 > 0 )
        IsWmsShellSession = (unsigned __int16)v18 | 0x80070000;
      v8 = 3420;
      goto LABEL_18;
    }
LABEL_60:
    if ( ++v14 >= (unsigned __int64)pCount )
      goto LABEL_61;
  }
  v19 = ppSessionInfo[v16].SessionId;
  if ( v19 == active )
  {
    v21 = (const unsigned __int16 *)((char *)this + 880);
LABEL_56:
    IsWmsShellSession = SafeSysAllocString(v21, (unsigned __int16 **)v15 + 3);
    if ( IsWmsShellSession < 0 )
      goto LABEL_62;
    *(_DWORD *)v15 = ppSessionInfo[v16].SessionId;
    *((_DWORD *)v15 + 1) = ppSessionInfo[v16].State;
    *((_DWORD *)v15 + 8) = v33 == 5;
    IsWmsShellSession = SafeSysAllocString(ppSessionInfo[v16].pUserName, (unsigned __int16 **)v15 + 1);
    if ( IsWmsShellSession < 0 )
      goto LABEL_62;
    IsWmsShellSession = SafeSysAllocString(ppSessionInfo[v16].pDomainName, (unsigned __int16 **)v15 + 2);
    if ( IsWmsShellSession < 0 )
      goto LABEL_62;
    v15 = (struct __MIDL___MIDL_itf_wmssvc_0000_0010_0004 *)((char *)v15 + 40);
    goto LABEL_60;
  }
  if ( WTSQuerySessionInformationW(0, v19, WTSClientName, (LPWSTR *)&pMemory, &pBytesReturned) )
  {
    v21 = (const unsigned __int16 *)pMemory;
    goto LABEL_56;
  }
  if ( GetLastError() == 2 )
    goto LABEL_60;
  v20 = GetLastError();
  IsWmsShellSession = v20;
  if ( v20 > 0 )
    IsWmsShellSession = (unsigned __int16)v20 | 0x80070000;
  v8 = 3434;
LABEL_18:
  if ( IsWmsShellSession >= 0 )
    IsWmsShellSession = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
    v8,
    L"CEventNotificationService::GetAllSessions",
    L"CBRAEx",
    L"fSuccess",
    IsWmsShellSession);
  if ( !IsDebuggerPresent() )
  {
    v25 = IsWmsShellSession;
    v23 = L"fSuccess";
LABEL_9:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v8,
      L"CEventNotificationService::GetAllSessions",
      L"CBRAEx",
      v23,
      v25);
    goto LABEL_62;
  }
  v26 = IsWmsShellSession;
  v24 = L"fSuccess";
LABEL_6:
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
    v8,
    L"CEventNotificationService::GetAllSessions",
    L"CBRAEx",
    v24,
    v26);
LABEL_62:
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  if ( pMemory )
    WTSFreeMemory(pMemory);
  CoTaskMemFree(v3);
  return (unsigned int)IsWmsShellSession;
}

```

## disassembly

```asm
0x1400192b0  mov     [rsp-38h+arg_8], rbx
0x1400192b5  mov     [rsp-38h+arg_0], rcx
0x1400192ba  push    rbp
0x1400192bb  push    rsi
0x1400192bc  push    rdi
0x1400192bd  push    r12
0x1400192bf  push    r13
0x1400192c1  push    r14
0x1400192c3  push    r15
0x1400192c5  mov     rbp, rsp
0x1400192c8  sub     rsp, 70h
0x1400192cc  xor     r12d, r12d
0x1400192cf  mov     [rbp+var_24], 0
0x1400192d6  mov     r13, rdx
0x1400192d9  mov     [rbp+pLevel], 1
0x1400192e0  xor     edx, edx
0x1400192e2  mov     [rbp+ppSessionInfo], 0
0x1400192ea  mov     rdi, rcx
0x1400192ed  mov     [rbp+arg_18], 0
0x1400192f4  mov     r15, r8
0x1400192f7  mov     [rbp+pBytesReturned], r12d
0x1400192fb  mov     [rbp+pMemory], r12
0x1400192ff  lea     ecx, [rdx+3]
0x140019302  mov     [rbp+var_14], r12d
0x140019306  mov     [rbp+var_20], r12d
0x14001930a  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x14001930f  mov     ebx, eax
0x140019311  test    eax, eax
0x140019313  js      loc_1400197BC
0x140019319  test    r13, r13
0x14001931c  jnz     loc_1400193D2
0x140019322  mov     r15d, 80004003h
0x140019328  lea     rax, aPcsessioninfo_0; "pcSessionInfo"
0x14001932f  lea     r14, aCbraex; "CBRAEx"
0x140019336  mov     [rsp+70h+var_48], r15d; int
0x14001933b  lea     rsi, aCeventnotifica_135; "CEventNotificationService::GetAllSessio"...
0x140019342  mov     [rsp+70h+pCount], rax; unsigned __int16 *
0x140019347  mov     r13d, 0CEDh
0x14001934d  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140019354  mov     r9, r14; unsigned __int16 *
0x140019357  mov     r8, rsi; unsigned __int16 *
0x14001935a  mov     edx, r13d; unsigned int
0x14001935d  mov     rcx, rdi; unsigned __int16 *
0x140019360  mov     ebx, r15d
0x140019363  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140019368  call    cs:__imp_IsDebuggerPresent
0x14001936e  test    eax, eax
0x140019370  lea     rax, aPcsessioninfo_0; "pcSessionInfo"
0x140019377  jz      short loc_1400193A9
0x140019379  mov     [rsp+70h+var_38], r15d
0x14001937e  mov     [rsp+70h+var_40], rax
0x140019383  mov     qword ptr [rsp+70h+var_48], r14
0x140019388  mov     r9d, r13d
0x14001938b  mov     r8, rdi
0x14001938e  mov     [rsp+70h+pCount], rsi
0x140019393  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001939a  mov     ecx, 2; unsigned __int8
0x14001939f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400193a4  jmp     loc_1400197BC
0x1400193a9  mov     dword ptr [rsp+70h+var_40], r15d
0x1400193ae  mov     qword ptr [rsp+70h+var_48], rax
0x1400193b3  mov     [rsp+70h+pCount], r14
0x1400193b8  mov     r8d, r13d
0x1400193bb  mov     r9, rsi
0x1400193be  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400193c5  mov     rdx, rdi
0x1400193c8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400193cd  jmp     loc_1400197BC
0x1400193d2  test    r15, r15
0x1400193d5  jnz     short loc_140019431
0x1400193d7  mov     r15d, 80004003h
0x1400193dd  lea     rax, aPprgwmssession_0; "pprgWmsSessionInfo"
0x1400193e4  lea     r14, aCbraex; "CBRAEx"
0x1400193eb  mov     [rsp+70h+var_48], r15d; int
0x1400193f0  lea     rsi, aCeventnotifica_135; "CEventNotificationService::GetAllSessio"...
0x1400193f7  mov     [rsp+70h+pCount], rax; unsigned __int16 *
0x1400193fc  mov     r13d, 0CEEh
0x140019402  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140019409  mov     r9, r14; unsigned __int16 *
0x14001940c  mov     r8, rsi; unsigned __int16 *
0x14001940f  mov     edx, r13d; unsigned int
0x140019412  mov     rcx, rdi; unsigned __int16 *
0x140019415  mov     ebx, r15d
0x140019418  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001941d  call    cs:__imp_IsDebuggerPresent
0x140019423  test    eax, eax
0x140019425  lea     rax, aPprgwmssession_0; "pprgWmsSessionInfo"
0x14001942c  jmp     loc_140019377
0x140019431  mov     [r13+0], r12d
0x140019435  mov     [r15], r12
0x140019438  call    cs:__imp_WTSGetActiveConsoleSessionId
0x14001943e  mov     [rbp+var_1C], eax
0x140019441  lea     rdx, [rbp+var_24]
0x140019445  mov     rax, [rdi]
0x140019448  mov     rcx, rdi
0x14001944b  mov     rax, [rax+68h]
0x14001944f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019454  mov     ebx, eax
0x140019456  test    eax, eax
0x140019458  js      loc_1400197BC
0x14001945e  lea     rax, [rbp+arg_18]
0x140019462  xor     r8d, r8d; Filter
0x140019465  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x140019469  mov     [rsp+70h+pCount], rax; pCount
0x14001946e  lea     rdx, [rbp+pLevel]; pLevel
0x140019472  xor     ecx, ecx; hServer
0x140019474  call    cs:__imp_WTSEnumerateSessionsExW
0x14001947a  test    eax, eax
0x14001947c  jnz     loc_140019503
0x140019482  call    cs:__imp_GetLastError
0x140019488  mov     ebx, eax
0x14001948a  test    eax, eax
0x14001948c  jle     short loc_140019497
0x14001948e  movzx   ebx, ax
0x140019491  or      ebx, 80070000h
0x140019497  mov     r13d, 0CFBh
0x14001949d  mov     eax, 80004005h
0x1400194a2  lea     rsi, aCeventnotifica_135; "CEventNotificationService::GetAllSessio"...
0x1400194a9  test    ebx, ebx
0x1400194ab  lea     r14, aCbraex; "CBRAEx"
0x1400194b2  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400194b9  mov     r8, rsi; unsigned __int16 *
0x1400194bc  cmovns  ebx, eax
0x1400194bf  lea     r15, aFsuccess; "fSuccess"
0x1400194c6  mov     [rsp+70h+var_48], ebx; int
0x1400194ca  mov     r9, r14; unsigned __int16 *
0x1400194cd  mov     edx, r13d; unsigned int
0x1400194d0  mov     [rsp+70h+pCount], r15; unsigned __int16 *
0x1400194d5  mov     rcx, rdi; unsigned __int16 *
0x1400194d8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400194dd  call    cs:__imp_IsDebuggerPresent
0x1400194e3  test    eax, eax
0x1400194e5  jz      short loc_1400194F5
0x1400194e7  mov     [rsp+70h+var_38], ebx
0x1400194eb  mov     [rsp+70h+var_40], r15
0x1400194f0  jmp     loc_140019383
0x1400194f5  mov     dword ptr [rsp+70h+var_40], ebx
0x1400194f9  mov     qword ptr [rsp+70h+var_48], r15
0x1400194fe  jmp     loc_1400193B3
0x140019503  cmp     [rbp+arg_18], r12d
0x140019507  jnz     short loc_140019510
0x140019509  xor     ebx, ebx
0x14001950b  jmp     loc_1400197BC
0x140019510  lea     rcx, [rbp+var_28]; this
0x140019514  mov     [rbp+var_28], r12d
0x140019518  call    ?IsRole@PlatformSkuUtils@@YAJPEAH@Z; PlatformSkuUtils::IsRole(int *)
0x14001951d  mov     eax, [rbp+arg_18]
0x140019520  lea     rcx, [rax+rax*4]
0x140019524  shl     rcx, 3; cb
0x140019528  call    cs:__imp_CoTaskMemAlloc
0x14001952e  mov     r12, rax
0x140019531  test    rax, rax
0x140019534  jnz     short loc_1400195AD
0x140019536  mov     ebx, 8007000Eh
0x14001953b  lea     r13, aCpr; "CPR"
0x140019542  lea     rsi, aCeventnotifica_135; "CEventNotificationService::GetAllSessio"...
0x140019549  mov     [rsp+70h+var_48], ebx; int
0x14001954d  mov     r14d, 0D02h
0x140019553  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001955a  lea     r15, aPrgwmssessioni_0; "prgWmsSessionInfo"
0x140019561  mov     r9, r13; unsigned __int16 *
0x140019564  mov     r8, rsi; unsigned __int16 *
0x140019567  mov     [rsp+70h+pCount], r15; unsigned __int16 *
0x14001956c  mov     edx, r14d; unsigned int
0x14001956f  mov     rcx, rdi; unsigned __int16 *
0x140019572  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140019577  call    cs:__imp_IsDebuggerPresent
0x14001957d  test    eax, eax
0x14001957f  jz      short loc_140019597
0x140019581  mov     [rsp+70h+var_38], ebx
0x140019585  mov     r9d, r14d
0x140019588  mov     [rsp+70h+var_40], r15
0x14001958d  mov     qword ptr [rsp+70h+var_48], r13
0x140019592  jmp     loc_14001938B
0x140019597  mov     dword ptr [rsp+70h+var_40], ebx
0x14001959b  mov     r8d, r14d
0x14001959e  mov     qword ptr [rsp+70h+var_48], r15
0x1400195a3  mov     [rsp+70h+pCount], r13
0x1400195a8  jmp     loc_1400193BB
0x1400195ad  xor     r14d, r14d
0x1400195b0  mov     rdi, r12
0x1400195b3  cmp     [rbp+arg_18], r14d
0x1400195b7  jbe     loc_14001979D
0x1400195bd  mov     rax, [rbp+ppSessionInfo]
0x1400195c1  imul    rsi, r14, 38h ; '8'
0x1400195c5  mov     ecx, [rsi+rax+8]; SessionId
0x1400195c9  test    ecx, ecx
0x1400195cb  jz      loc_14001978E
0x1400195d1  cmp     dword ptr [rsi+rax+4], 6
0x1400195d6  jz      loc_14001978E
0x1400195dc  cmp     dword ptr [rsi+rax+4], 1
0x1400195e1  jz      loc_14001978E
0x1400195e7  cmp     [rbp+var_28], 0
0x1400195eb  jz      short loc_140019619
0x1400195ed  cmp     ecx, [rbp+var_1C]
0x1400195f0  jnz     short loc_140019619
0x1400195f2  cmp     [rbp+var_24], 1
0x1400195f6  jz      loc_14001978E
0x1400195fc  lea     rdx, [rbp+var_20]; int *
0x140019600  call    ?s_IsWmsShellSession@CEventNotificationService@@SAJKPEAH@Z; CEventNotificationService::s_IsWmsShellSession(ulong,int *)
0x140019605  mov     ebx, eax
0x140019607  test    eax, eax
0x140019609  js      loc_1400197BC
0x14001960f  cmp     [rbp+var_20], 0
0x140019613  jnz     loc_14001978E
0x140019619  mov     rcx, [rbp+ppSessionInfo]
0x14001961d  cmp     qword ptr [rsi+rcx+18h], 0
0x140019623  jnz     loc_14001978E
0x140019629  cmp     qword ptr [rsi+rcx+20h], 0
0x14001962f  jz      loc_14001978E
0x140019635  mov     ecx, [rsi+rcx+8]
0x140019639  call    ?GetSessionType@@YA?AW4ESessionType@@K@Z; GetSessionType(ulong)
0x14001963e  cmp     eax, 6
0x140019641  jz      loc_14001978E
0x140019647  mov     rcx, [rbp+pMemory]; pMemory
0x14001964b  test    rcx, rcx
0x14001964e  jz      short loc_14001965E
0x140019650  call    cs:__imp_WTSFreeMemory
0x140019656  mov     [rbp+pMemory], 0
0x14001965e  mov     rdx, [rbp+ppSessionInfo]
0x140019662  lea     rax, [rbp+pBytesReturned]
0x140019666  mov     qword ptr [rsp+70h+var_48], rax
0x14001966b  lea     r9, [rbp+var_14]
0x14001966f  mov     r8d, 27h ; '''
0x140019675  mov     dword ptr [rsp+70h+pCount], 4
0x14001967d  xor     ecx, ecx
0x14001967f  mov     edx, [rsi+rdx+8]
0x140019683  call    cs:__imp_WinStationQueryInformationW
0x140019689  test    al, al
0x14001968b  jnz     short loc_1400196BC
0x14001968d  call    cs:__imp_GetLastError
0x140019693  cmp     eax, 2
0x140019696  jz      loc_14001978E
0x14001969c  call    cs:__imp_GetLastError
0x1400196a2  mov     ebx, eax
0x1400196a4  test    eax, eax
0x1400196a6  jle     short loc_1400196B1
0x1400196a8  movzx   ebx, ax
0x1400196ab  or      ebx, 80070000h
0x1400196b1  mov     r13d, 0D5Ch
0x1400196b7  jmp     loc_14001949D
0x1400196bc  mov     rax, [rbp+ppSessionInfo]
0x1400196c0  mov     edx, [rsi+rax+8]; SessionId
0x1400196c4  cmp     edx, [rbp+var_1C]
0x1400196c7  jz      short loc_14001971B
0x1400196c9  xor     ecx, ecx; hServer
0x1400196cb  lea     rax, [rbp+pBytesReturned]
0x1400196cf  lea     r9, [rbp+pMemory]; ppBuffer
0x1400196d3  mov     [rsp+70h+pCount], rax; pBytesReturned
0x1400196d8  lea     r8d, [rcx+0Ah]; WTSInfoClass
0x1400196dc  call    cs:__imp_WTSQuerySessionInformationW
0x1400196e2  test    eax, eax
0x1400196e4  jnz     short loc_140019715
0x1400196e6  call    cs:__imp_GetLastError
0x1400196ec  cmp     eax, 2
0x1400196ef  jz      loc_14001978E
0x1400196f5  call    cs:__imp_GetLastError
0x1400196fb  mov     ebx, eax
0x1400196fd  test    eax, eax
0x1400196ff  jle     short loc_14001970A
0x140019701  movzx   ebx, ax
0x140019704  or      ebx, 80070000h
0x14001970a  mov     r13d, 0D6Ah
0x140019710  jmp     loc_14001949D
0x140019715  mov     rcx, [rbp+pMemory]
0x140019719  jmp     short loc_140019726
0x14001971b  mov     rcx, [rbp+arg_0]
0x14001971f  add     rcx, 370h; unsigned __int16 *
0x140019726  lea     rdx, [rdi+18h]; unsigned __int16 **
0x14001972a  call    ?SafeSysAllocString@@YAJPEBGPEAPEAG@Z; SafeSysAllocString(ushort const *,ushort * *)
0x14001972f  mov     ebx, eax
0x140019731  test    eax, eax
0x140019733  js      loc_1400197BC
0x140019739  mov     rax, [rbp+ppSessionInfo]
0x14001973d  lea     rdx, [rdi+8]; unsigned __int16 **
0x140019741  mov     ecx, [rsi+rax+8]
0x140019745  mov     [rdi], ecx
0x140019747  mov     rax, [rbp+ppSessionInfo]
0x14001974b  mov     ecx, [rsi+rax+4]
0x14001974f  xor     eax, eax
0x140019751  mov     [rdi+4], ecx
0x140019754  cmp     [rbp+var_14], 5
0x140019758  setz    al
0x14001975b  mov     [rdi+20h], eax
0x14001975e  mov     rcx, [rbp+ppSessionInfo]
0x140019762  mov     rcx, [rsi+rcx+20h]; unsigned __int16 *
0x140019767  call    ?SafeSysAllocString@@YAJPEBGPEAPEAG@Z; SafeSysAllocString(ushort const *,ushort * *)
0x14001976c  mov     ebx, eax
0x14001976e  test    eax, eax
0x140019770  js      short loc_1400197BC
0x140019772  mov     rcx, [rbp+ppSessionInfo]
0x140019776  lea     rdx, [rdi+10h]; unsigned __int16 **
0x14001977a  mov     rcx, [rsi+rcx+28h]; unsigned __int16 *
0x14001977f  call    ?SafeSysAllocString@@YAJPEBGPEAPEAG@Z; SafeSysAllocString(ushort const *,ushort * *)
0x140019784  mov     ebx, eax
0x140019786  test    eax, eax
0x140019788  js      short loc_1400197BC
0x14001978a  add     rdi, 28h ; '('
0x14001978e  mov     eax, [rbp+arg_18]
0x140019791  inc     r14
  ... truncated ...
```
