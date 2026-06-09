# CEventNotificationService::RegisterCore(ulong,IWmsCore *)

- ea: `0x1400221e0`
- end: `0x1400227a3`
- name: `?RegisterCore@CEventNotificationService@@UEAAJKPEAUIWmsCore@@@Z`
- size: `1475`
- prototype: `int(CEventNotificationService *__hidden this, unsigned int, struct IWmsCore *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x140004730`
- `0x140004a04`
- `0x140017c48`
- `0x1400221e0`
- `0x1400229c0`
- `0x14002d3c0`
- `0x14002d554`
- `0x14002e2bc`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x140068ebc`
- `0x14006c590`
- `0x14006eb38`
- `0x140073c08`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140022381`
- `KERNEL32!GetCurrentProcessId` at `0x140022381`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x14002260c`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x140022688`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x14002260c`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x140022688`
- `KERNEL32!OpenProcess` at `0x1400224ce`
- `KERNEL32!OpenProcess` at `0x1400224ce`
- `KERNEL32!CreateThread` at `0x1400225ac`
- `KERNEL32!CreateThread` at `0x1400225ac`
- `KERNEL32!GetLastError` at `0x1400224dd`
- `KERNEL32!GetLastError` at `0x1400225bb`
- `KERNEL32!GetLastError` at `0x1400226b8`
- `KERNEL32!GetLastError` at `0x1400224dd`
- `KERNEL32!GetLastError` at `0x1400225bb`
- `KERNEL32!GetLastError` at `0x1400226b8`
- `KERNEL32!IsDebuggerPresent` at `0x1400222d2`
- `KERNEL32!IsDebuggerPresent` at `0x1400223cc`
- `KERNEL32!IsDebuggerPresent` at `0x140022463`
- `KERNEL32!IsDebuggerPresent` at `0x140022535`
- `KERNEL32!IsDebuggerPresent` at `0x140022737`
- `KERNEL32!IsDebuggerPresent` at `0x1400222d2`
- `KERNEL32!IsDebuggerPresent` at `0x1400223cc`
- `KERNEL32!IsDebuggerPresent` at `0x140022463`
- `KERNEL32!IsDebuggerPresent` at `0x140022535`
- `KERNEL32!IsDebuggerPresent` at `0x140022737`
- `WTSAPI32!WTSFreeMemory` at `0x140022782`
- `WTSAPI32!WTSFreeMemory` at `0x140022782`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400226ae`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400226ae`

## string_xrefs

- `0x14002223b`: `CEventNotificationService::RegisterCore`
- `0x1400222a3`: `CEventNotificationService::RegisterCore`
- `0x140022395`: `CEventNotificationService::RegisterCore`
- `0x140022436`: `CEventNotificationService::RegisterCore`
- `0x14002270a`: `CEventNotificationService::RegisterCore`
- `0x140022229`: ` - Not registering core; service shutdown in progress.`
- `0x14002227c`: `CEventNotificationService::RegisterCore - m_modeCore = %s\n`
- `0x14002251c`: `m_hCoreProcessWatcherThread == NULL`
- `0x1400225d2`: `m_hCoreProcessWatcherThread != 0`
- `0x14002274f`: `CEventNotificationService::RegisterCore - *peConnectState=%d\n`
- `0x140022633`: `CEventNotificationService::TerminateConsoleSessionAgent Removing console session agent (session %lu)\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::RegisterCore(
        CEventNotificationService *this,
        DWORD a2,
        struct IWmsCore *a3)
{
  int v6; // ebx
  _QWORD *v7; // r15
  __int64 v8; // rax
  __int64 v9; // r8
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r12
  unsigned int v12; // r15d
  __int64 v13; // rdx
  __int64 v14; // r8
  const unsigned __int16 *v15; // r9
  const unsigned __int16 *v16; // r9
  unsigned int v17; // r12d
  bool v18; // zf
  const unsigned __int16 *v19; // rax
  HANDLE v20; // rax
  const unsigned __int16 *v21; // r9
  signed int v22; // eax
  HANDLE Thread; // rax
  signed int v24; // eax
  DWORD v25; // esi
  const unsigned __int16 *v26; // r9
  int SessionAgent; // eax
  struct ISessionAgent *v28; // rdi
  DWORD active; // edi
  signed int LastError; // eax
  __int64 v32; // [rsp+30h] [rbp-20h]
  LPWSTR ppBuffer; // [rsp+40h] [rbp-10h] BYREF
  struct ISessionAgent *pBytesReturned; // [rsp+98h] [rbp+48h] BYREF

  ppBuffer = 0;
  v6 = CUserManagement::s_VerifyAccessLevelEx(2u, 0);
  if ( v6 < 0 )
    goto LABEL_52;
  if ( CEventNotificationService::m_sShutdownInProgress )
  {
    v6 = -2147023781;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      4468,
      L"CEventNotificationService::RegisterCore",
      L" - Not registering core; service shutdown in progress.");
    goto LABEL_52;
  }
  v7 = (_QWORD *)((char *)this - 8);
  v8 = Utils::WmsModeToString(*((unsigned int *)this + 112));
  DEBUGMSG(L"CEventNotificationService::RegisterCore - m_modeCore = %s\n", v8);
  if ( !a3 )
  {
    v6 = -2147024809;
    v11 = L"pCore";
    v12 = 4473;
LABEL_6:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v12,
      L"CEventNotificationService::RegisterCore",
      L"CBRAEx",
      v11,
      v6);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v12,
        L"CEventNotificationService::RegisterCore",
        L"CBRAEx",
        v11,
        v6);
    }
    else
    {
      LODWORD(v32) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v12,
        L"CEventNotificationService::RegisterCore",
        L"CBRAEx",
        v11,
        v32);
    }
    goto LABEL_52;
  }
  if ( *((_DWORD *)this + 112) == 2 )
  {
    v6 = CEventNotificationService::ReleaseCore((CEventNotificationService *)((char *)this - 8));
    if ( v6 < 0 )
      goto LABEL_52;
  }
  else if ( v7[56] )
  {
    v17 = 4491;
    v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x118Bu,
      L"CEventNotificationService::RegisterCore",
      L"CBRA",
      L"m_pCore == 0",
      -2147467259);
    v18 = !IsDebuggerPresent();
    v19 = L"m_pCore == 0";
    goto LABEL_17;
  }
  CAutoWriteLock::CAutoWriteLock(
    (CAutoWriteLock *)&pBytesReturned,
    (CEventNotificationService *)((char *)this + 2304),
    v9,
    v10);
  *((_QWORD *)this + 55) = a3;
  (*(void (__fastcall **)(struct IWmsCore *))(*(_QWORD *)a3 + 8LL))(a3);
  CAutoWriteLock::~CAutoWriteLock((PSRWLOCK *)&pBytesReturned, v13, v14, v15);
  if ( a2 == GetCurrentProcessId() )
  {
    LODWORD(pBytesReturned) = 0;
    SetSuppressDeviceInstallUI(0);
    v6 = 0;
    *((_DWORD *)this + 112) = 2;
    active = WTSGetActiveConsoleSessionId();
    if ( active == -1 )
      goto LABEL_52;
    if ( !WTSQuerySessionInformationW(0, active, WTSConnectState, &ppBuffer, (DWORD *)&pBytesReturned) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v11 = L"fSuccess";
      v12 = 4545;
      if ( v6 >= 0 )
        v6 = -2147467259;
      goto LABEL_6;
    }
    if ( (_DWORD)pBytesReturned == 4 )
    {
      DEBUGMSG(L"CEventNotificationService::RegisterCore - *peConnectState=%d\n", *(unsigned int *)ppBuffer);
      if ( (*(_DWORD *)ppBuffer & 0xFFFFFFFB) == 0 )
        v6 = CSessionAgentList::InjectSessionAgent((CEventNotificationService *)((char *)this + 520), active);
      goto LABEL_52;
    }
    v17 = 4547;
    v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x11C3u,
      L"CEventNotificationService::RegisterCore",
      L"CBRA",
      L"cbReturned == sizeof (*peConnectState)",
      -2147467259);
    v18 = !IsDebuggerPresent();
    v19 = L"cbReturned == sizeof (*peConnectState)";
LABEL_17:
    if ( v18 )
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v17,
        L"CEventNotificationService::RegisterCore",
        L"CBRA",
        v19,
        -2147467259);
    else
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v17,
        L"CEventNotificationService::RegisterCore",
        L"CBRA",
        v19,
        -2147467259);
    goto LABEL_52;
  }
  if ( *((_QWORD *)this + 9) )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x119Au,
      L"CEventNotificationService::RegisterCore",
      v16,
      L"m_hCoreProcess == NULL");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        4506,
        L"CEventNotificationService::RegisterCore",
        L"ASSERT",
        L"m_hCoreProcess == NULL");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        4506,
        L"CEventNotificationService::RegisterCore",
        L"ASSERT",
        L"m_hCoreProcess == NULL");
  }
  v20 = OpenProcess(0x100000u, 0, a2);
  *((_QWORD *)this + 9) = v20;
  if ( !v20 )
  {
    v22 = GetLastError();
    v6 = v22;
    if ( v22 > 0 )
      v6 = (unsigned __int16)v22 | 0x80070000;
    v11 = L"m_hCoreProcess != 0";
    v12 = 4508;
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_6;
  }
  if ( *((_QWORD *)this + 10) )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x119Fu,
      L"CEventNotificationService::RegisterCore",
      v21,
      L"m_hCoreProcessWatcherThread == NULL");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        4511,
        L"CEventNotificationService::RegisterCore",
        L"ASSERT",
        L"m_hCoreProcessWatcherThread == NULL");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        4511,
        L"CEventNotificationService::RegisterCore",
        L"ASSERT",
        L"m_hCoreProcessWatcherThread == NULL");
  }
  Thread = CreateThread(0, 0, CEventNotificationService::s_CoreProcessWatcherThreadProc, (char *)this - 8, 0, 0);
  *((_QWORD *)this + 10) = Thread;
  if ( !Thread )
  {
    v24 = GetLastError();
    v6 = v24;
    if ( v24 > 0 )
      v6 = (unsigned __int16)v24 | 0x80070000;
    v11 = L"m_hCoreProcessWatcherThread != 0";
    v12 = 4513;
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_6;
  }
  SetSuppressDeviceInstallUI(1);
  CDeviceUtils::s_DisableSystemAudioDevices();
  v6 = 0;
  *((_DWORD *)this + 112) = 1;
  pBytesReturned = 0;
  v25 = WTSGetActiveConsoleSessionId();
  SessionAgent = CSessionAgentList::FindSessionAgent((CSessionAgentList *)(v7 + 66), v25, &pBytesReturned, v26);
  v28 = pBytesReturned;
  if ( SessionAgent >= 0 )
  {
    DEBUGMSG(
      L"CEventNotificationService::TerminateConsoleSessionAgent Removing console session agent (session %lu)\n",
      v25);
    CSessionAgentList::RemoveSessionAgentByInterface((CSessionAgentList *)(v7 + 66), v28);
    CEventNotificationService::ClearChatForSession((CEventNotificationService *)v7, v25);
  }
  if ( v28 )
    (*(void (__fastcall **)(struct ISessionAgent *))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_52:
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400221e0  mov     [rsp-28h+arg_0], rbx
0x1400221e5  mov     [rsp-28h+arg_8], rsi
0x1400221ea  push    rbp
0x1400221eb  push    rdi
0x1400221ec  push    r12
0x1400221ee  push    r14
0x1400221f0  push    r15
0x1400221f2  mov     rbp, rsp
0x1400221f5  sub     rsp, 50h
0x1400221f9  mov     r12d, edx
0x1400221fc  mov     [rbp+ppBuffer], 0
0x140022204  xor     edx, edx
0x140022206  mov     r14, rcx
0x140022209  mov     rdi, r8
0x14002220c  lea     esi, [rdx+2]
0x14002220f  mov     ecx, esi
0x140022211  call    ?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z; CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)
0x140022216  mov     ebx, eax
0x140022218  test    eax, eax
0x14002221a  js      loc_140022779
0x140022220  cmp     cs:?m_sShutdownInProgress@CEventNotificationService@@2HA, 0; int CEventNotificationService::m_sShutdownInProgress
0x140022227  jz      short loc_140022269
0x140022229  lea     rax, aNotRegistering; " - Not registering core; service shutdo"...
0x140022230  mov     r9d, 1174h
0x140022236  mov     [rsp+50h+lpThreadId], rax
0x14002223b  lea     rsi, aCeventnotifica_22; "CEventNotificationService::RegisterCore"
0x140022242  lea     r8, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x140022249  mov     qword ptr [rsp+50h+dwCreationFlags], rsi
0x14002224e  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140022255  mov     ecx, 4; unsigned __int8
0x14002225a  mov     ebx, 8007045Bh
0x14002225f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022264  jmp     loc_140022779
0x140022269  lea     r15, [r14-8]
0x14002226d  mov     ecx, [r15+1C8h]
0x140022274  call    ?WmsModeToString@Utils@@YAPEBGW4__MIDL___MIDL_itf_wmssvc_0000_0000_0001@@@Z; Utils::WmsModeToString(__MIDL___MIDL_itf_wmssvc_0000_0000_0001)
0x140022279  mov     rdx, rax
0x14002227c  lea     rcx, aCeventnotifica_182; "CEventNotificationService::RegisterCore"...
0x140022283  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140022288  test    rdi, rdi
0x14002228b  jnz     loc_140022333
0x140022291  mov     ebx, 80070057h
0x140022296  lea     r12, aPcore; "pCore"
0x14002229d  mov     r15d, 1179h
0x1400222a3  lea     rsi, aCeventnotifica_22; "CEventNotificationService::RegisterCore"
0x1400222aa  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400222b1  lea     r14, aCbraex; "CBRAEx"
0x1400222b8  mov     dword ptr [rsp+50h+lpThreadId], ebx; int
0x1400222bc  mov     r9, r14; unsigned __int16 *
0x1400222bf  mov     qword ptr [rsp+50h+dwCreationFlags], r12; unsigned __int16 *
0x1400222c4  mov     r8, rsi; unsigned __int16 *
0x1400222c7  mov     edx, r15d; unsigned int
0x1400222ca  mov     rcx, rdi; unsigned __int16 *
0x1400222cd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400222d2  call    cs:__imp_IsDebuggerPresent
0x1400222d8  test    eax, eax
0x1400222da  jz      short loc_14002230B
0x1400222dc  mov     [rsp+50h+var_18], ebx
0x1400222e0  mov     r9d, r15d
0x1400222e3  mov     [rsp+50h+var_20], r12
0x1400222e8  mov     [rsp+50h+lpThreadId], r14
0x1400222ed  mov     r8, rdi
0x1400222f0  mov     qword ptr [rsp+50h+dwCreationFlags], rsi
0x1400222f5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400222fc  mov     ecx, 2; unsigned __int8
0x140022301  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140022306  jmp     loc_140022779
0x14002230b  mov     dword ptr [rsp+50h+var_20], ebx
0x14002230f  mov     r8d, r15d
0x140022312  mov     [rsp+50h+lpThreadId], r12
0x140022317  mov     qword ptr [rsp+50h+dwCreationFlags], r14
0x14002231c  mov     r9, rsi
0x14002231f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140022326  mov     rdx, rdi
0x140022329  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002232e  jmp     loc_140022779
0x140022333  cmp     [r14+1C0h], esi
0x14002233a  jnz     loc_14002240F
0x140022340  mov     rcx, r15; this
0x140022343  call    ?ReleaseCore@CEventNotificationService@@IEAAJXZ; CEventNotificationService::ReleaseCore(void)
0x140022348  mov     ebx, eax
0x14002234a  test    eax, eax
0x14002234c  js      loc_140022779
0x140022352  lea     rdx, [r14+900h]; struct CSharedReaderWriterLock *
0x140022359  lea     rcx, [rbp+pBytesReturned]; this
0x14002235d  call    ??0CAutoWriteLock@@QEAA@PEAVCSharedReaderWriterLock@@@Z; CAutoWriteLock::CAutoWriteLock(CSharedReaderWriterLock *)
0x140022362  mov     [r14+1B8h], rdi
0x140022369  mov     rcx, rdi
0x14002236c  mov     rax, [rdi]
0x14002236f  mov     rax, [rax+8]
0x140022373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022378  lea     rcx, [rbp+pBytesReturned]; this
0x14002237c  call    ??1CAutoWriteLock@@QEAA@XZ; CAutoWriteLock::~CAutoWriteLock(void)
0x140022381  call    cs:__imp_GetCurrentProcessId
0x140022387  cmp     r12d, eax
0x14002238a  jz      loc_140022671
0x140022390  cmp     qword ptr [r14+48h], 0
0x140022395  lea     rsi, aCeventnotifica_22; "CEventNotificationService::RegisterCore"
0x14002239c  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x1400223a3  lea     rbx, aAssert; "ASSERT"
0x1400223aa  jz      loc_1400224C4
0x1400223b0  lea     rax, aMHcoreprocessN; "m_hCoreProcess == NULL"
0x1400223b7  mov     r8, rsi; unsigned __int16 *
0x1400223ba  mov     edx, 119Ah; unsigned int
0x1400223bf  mov     qword ptr [rsp+50h+dwCreationFlags], rax; unsigned __int16 *
0x1400223c4  mov     rcx, rdi; unsigned __int16 *
0x1400223c7  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x1400223cc  call    cs:__imp_IsDebuggerPresent
0x1400223d2  test    eax, eax
0x1400223d4  lea     rax, aMHcoreprocessN; "m_hCoreProcess == NULL"
0x1400223db  jz      loc_1400224A2
0x1400223e1  mov     [rsp+50h+var_20], rax
0x1400223e6  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400223ed  mov     [rsp+50h+lpThreadId], rbx
0x1400223f2  mov     r9d, 119Ah
0x1400223f8  mov     r8, rdi
0x1400223fb  mov     qword ptr [rsp+50h+dwCreationFlags], rsi
0x140022400  mov     ecx, 2; unsigned __int8
0x140022405  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002240a  jmp     loc_1400224C4
0x14002240f  cmp     qword ptr [r15+1C0h], 0
0x140022417  jz      loc_140022352
0x14002241d  mov     r14d, 80004005h
0x140022423  lea     rax, aMPcore0; "m_pCore == 0"
0x14002242a  lea     r15, aCbra; "CBRA"
0x140022431  mov     dword ptr [rsp+50h+lpThreadId], r14d; int
0x140022436  lea     rsi, aCeventnotifica_22; "CEventNotificationService::RegisterCore"
0x14002243d  mov     qword ptr [rsp+50h+dwCreationFlags], rax; unsigned __int16 *
0x140022442  mov     r12d, 118Bh
0x140022448  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14002244f  mov     r9, r15; unsigned __int16 *
0x140022452  mov     r8, rsi; unsigned __int16 *
0x140022455  mov     edx, r12d; unsigned int
0x140022458  mov     rcx, rdi; unsigned __int16 *
0x14002245b  mov     ebx, r14d
0x14002245e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140022463  call    cs:__imp_IsDebuggerPresent
0x140022469  test    eax, eax
0x14002246b  lea     rax, aMPcore0; "m_pCore == 0"
0x140022472  jz      short loc_14002248B
0x140022474  mov     [rsp+50h+var_18], r14d
0x140022479  mov     r9d, r12d
0x14002247c  mov     [rsp+50h+var_20], rax
0x140022481  mov     [rsp+50h+lpThreadId], r15
0x140022486  jmp     loc_1400222ED
0x14002248b  mov     dword ptr [rsp+50h+var_20], r14d
0x140022490  mov     r8d, r12d
0x140022493  mov     [rsp+50h+lpThreadId], rax
0x140022498  mov     qword ptr [rsp+50h+dwCreationFlags], r15
0x14002249d  jmp     loc_14002231C
0x1400224a2  mov     [rsp+50h+lpThreadId], rax
0x1400224a7  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400224ae  mov     r9, rsi
0x1400224b1  mov     qword ptr [rsp+50h+dwCreationFlags], rbx
0x1400224b6  mov     r8d, 119Ah
0x1400224bc  mov     rdx, rdi
0x1400224bf  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400224c4  mov     r8d, r12d; dwProcessId
0x1400224c7  xor     edx, edx; bInheritHandle
0x1400224c9  mov     ecx, 100000h; dwDesiredAccess
0x1400224ce  call    cs:__imp_OpenProcess
0x1400224d4  mov     [r14+48h], rax
0x1400224d8  test    rax, rax
0x1400224db  jnz     short loc_140022510
0x1400224dd  call    cs:__imp_GetLastError
0x1400224e3  mov     ebx, eax
0x1400224e5  test    eax, eax
0x1400224e7  jle     short loc_1400224F2
0x1400224e9  movzx   ebx, ax
0x1400224ec  or      ebx, 80070000h
0x1400224f2  test    ebx, ebx
0x1400224f4  lea     r12, aMHcoreprocess0; "m_hCoreProcess != 0"
0x1400224fb  mov     r14d, 80004005h
0x140022501  mov     r15d, 119Ch
0x140022507  cmovns  ebx, r14d
0x14002250b  jmp     loc_1400222B1
0x140022510  cmp     qword ptr [r14+50h], 0
0x140022515  jz      short loc_14002258D
0x140022517  mov     ebx, 119Fh
0x14002251c  lea     r12, aMHcoreprocessw_0; "m_hCoreProcessWatcherThread == NULL"
0x140022523  mov     edx, ebx; unsigned int
0x140022525  mov     qword ptr [rsp+50h+dwCreationFlags], r12; unsigned __int16 *
0x14002252a  mov     r8, rsi; unsigned __int16 *
0x14002252d  mov     rcx, rdi; unsigned __int16 *
0x140022530  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140022535  call    cs:__imp_IsDebuggerPresent
0x14002253b  test    eax, eax
0x14002253d  lea     rax, aAssert; "ASSERT"
0x140022544  jz      short loc_14002256E
0x140022546  mov     [rsp+50h+var_20], r12
0x14002254b  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140022552  mov     [rsp+50h+lpThreadId], rax
0x140022557  mov     r9d, ebx
0x14002255a  mov     r8, rdi
0x14002255d  mov     qword ptr [rsp+50h+dwCreationFlags], rsi
0x140022562  mov     ecx, 2; unsigned __int8
0x140022567  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002256c  jmp     short loc_14002258D
0x14002256e  mov     [rsp+50h+lpThreadId], r12
0x140022573  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002257a  mov     r9, rsi
0x14002257d  mov     qword ptr [rsp+50h+dwCreationFlags], rax
0x140022582  mov     r8d, ebx
0x140022585  mov     rdx, rdi
0x140022588  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002258d  mov     [rsp+50h+lpThreadId], 0; lpThreadId
0x140022596  lea     r8, ?s_CoreProcessWatcherThreadProc@CEventNotificationService@@KAKPEAX@Z; lpStartAddress
0x14002259d  mov     r9, r15; lpParameter
0x1400225a0  mov     [rsp+50h+dwCreationFlags], 0; dwCreationFlags
0x1400225a8  xor     edx, edx; dwStackSize
0x1400225aa  xor     ecx, ecx; lpThreadAttributes
0x1400225ac  call    cs:__imp_CreateThread
0x1400225b2  mov     [r14+50h], rax
0x1400225b6  test    rax, rax
0x1400225b9  jnz     short loc_1400225EE
0x1400225bb  call    cs:__imp_GetLastError
0x1400225c1  mov     ebx, eax
0x1400225c3  test    eax, eax
0x1400225c5  jle     short loc_1400225D0
0x1400225c7  movzx   ebx, ax
0x1400225ca  or      ebx, 80070000h
0x1400225d0  test    ebx, ebx
0x1400225d2  lea     r12, aMHcoreprocessw; "m_hCoreProcessWatcherThread != 0"
0x1400225d9  mov     r14d, 80004005h
0x1400225df  mov     r15d, 11A1h
0x1400225e5  cmovns  ebx, r14d
0x1400225e9  jmp     loc_1400222B1
0x1400225ee  mov     edi, 1
0x1400225f3  mov     ecx, edi
0x1400225f5  call    ?SetSuppressDeviceInstallUI@@YAJW4ESuppressDeviceInstall@@@Z; SetSuppressDeviceInstallUI(ESuppressDeviceInstall)
0x1400225fa  call    ?s_DisableSystemAudioDevices@CDeviceUtils@@SAJXZ; CDeviceUtils::s_DisableSystemAudioDevices(void)
0x1400225ff  xor     ebx, ebx
0x140022601  mov     [r14+1C0h], edi
0x140022608  mov     [rbp+pBytesReturned], rbx
0x14002260c  call    cs:__imp_WTSGetActiveConsoleSessionId
0x140022612  lea     r14, [r15+210h]
0x140022619  mov     edx, eax; unsigned int
0x14002261b  mov     rcx, r14; this
0x14002261e  lea     r8, [rbp+pBytesReturned]; struct ISessionAgent **
0x140022622  mov     esi, eax
0x140022624  call    ?FindSessionAgent@CSessionAgentList@@QEAAJKPEAPEAUISessionAgent@@@Z; CSessionAgentList::FindSessionAgent(ulong,ISessionAgent * *)
0x140022629  mov     rdi, [rbp+pBytesReturned]
0x14002262d  test    eax, eax
0x14002262f  js      short loc_140022654
0x140022631  mov     edx, esi
0x140022633  lea     rcx, aCeventnotifica_96; "CEventNotificationService::TerminateCon"...
0x14002263a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002263f  mov     rdx, rdi; struct ISessionAgent *
0x140022642  mov     rcx, r14; this
0x140022645  call    ?RemoveSessionAgentByInterface@CSessionAgentList@@QEAAJPEAUISessionAgent@@@Z; CSessionAgentList::RemoveSessionAgentByInterface(ISessionAgent *)
0x14002264a  mov     edx, esi; unsigned int
0x14002264c  mov     rcx, r15; this
0x14002264f  call    ?ClearChatForSession@CEventNotificationService@@IEAAJK@Z; CEventNotificationService::ClearChatForSession(ulong)
0x140022654  test    rdi, rdi
0x140022657  jz      loc_140022779
0x14002265d  mov     rax, [rdi]
0x140022660  mov     rcx, rdi
0x140022663  mov     rax, [rax+10h]
0x140022667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002266c  jmp     loc_140022779
0x140022671  xor     ecx, ecx
0x140022673  mov     dword ptr [rbp+pBytesReturned], 0
0x14002267a  call    ?SetSuppressDeviceInstallUI@@YAJW4ESuppressDeviceInstall@@@Z; SetSuppressDeviceInstallUI(ESuppressDeviceInstall)
0x14002267f  xor     ebx, ebx
0x140022681  mov     [r14+1C0h], esi
0x140022688  call    cs:__imp_WTSGetActiveConsoleSessionId
0x14002268e  mov     edi, eax
0x140022690  cmp     eax, 0FFFFFFFFh
0x140022693  jz      loc_140022779
0x140022699  lea     rax, [rbp+pBytesReturned]
0x14002269d  mov     edx, edi; SessionId
0x14002269f  lea     r9, [rbp+ppBuffer]; ppBuffer
0x1400226a3  mov     qword ptr [rsp+50h+dwCreationFlags], rax; pBytesReturned
0x1400226a8  lea     r8d, [rbx+8]; WTSInfoClass
0x1400226ac  xor     ecx, ecx; hServer
0x1400226ae  call    cs:__imp_WTSQuerySessionInformationW
0x1400226b4  test    eax, eax
0x1400226b6  jnz     short loc_1400226EB
0x1400226b8  call    cs:__imp_GetLastError
0x1400226be  mov     ebx, eax
0x1400226c0  test    eax, eax
0x1400226c2  jle     short loc_1400226CD
0x1400226c4  movzx   ebx, ax
0x1400226c7  or      ebx, 80070000h
0x1400226cd  test    ebx, ebx
0x1400226cf  lea     r12, aFsuccess; "fSuccess"
0x1400226d6  mov     r14d, 80004005h
0x1400226dc  mov     r15d, 11C1h
0x1400226e2  cmovns  ebx, r14d
0x1400226e6  jmp     loc_1400222A3
0x1400226eb  cmp     dword ptr [rbp+pBytesReturned], 4
0x1400226ef  jz      short loc_14002274B
0x1400226f1  mov     r14d, 80004005h
0x1400226f7  lea     rax, aCbreturnedSize; "cbReturned == sizeof (*peConnectState)"
0x1400226fe  lea     r15, aCbra; "CBRA"
0x140022705  mov     dword ptr [rsp+50h+lpThreadId], r14d; int
0x14002270a  lea     rsi, aCeventnotifica_22; "CEventNotificationService::RegisterCore"
0x140022711  mov     qword ptr [rsp+50h+dwCreationFlags], rax; unsigned __int16 *
0x140022716  mov     r12d, 11C3h
0x14002271c  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
  ... truncated ...
```
