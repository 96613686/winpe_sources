# ShutDown(void)

- ea: `0x18003f760`
- end: `0x18003fbb8`
- name: `?ShutDown@@YAJXZ`
- size: `1112`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18003db14`

## callees

- `0x180030f10`
- `0x180031358`
- `0x18003206c`
- `0x1800327a8`
- `0x180032830`
- `0x180032870`
- `0x180035134`
- `0x18003518c`
- `0x18003ccd8`
- `0x18003f760`
- `0x180054cb0`
- `0x1800588bc`
- `0x180059384`

## import_xrefs

- `ole32!CoFreeUnusedLibraries` at `0x18003fb36`
- `ole32!CoFreeUnusedLibraries` at `0x18003fb36`
- `KERNEL32!SetThreadPriority` at `0x18003f95a`
- `KERNEL32!SetThreadPriority` at `0x18003fb86`
- `KERNEL32!SetThreadPriority` at `0x18003f95a`
- `KERNEL32!SetThreadPriority` at `0x18003fb86`
- `KERNEL32!GetThreadPriority` at `0x18003f775`
- `KERNEL32!GetThreadPriority` at `0x18003f775`
- `KERNEL32!LeaveCriticalSection` at `0x18003f8f2`
- `KERNEL32!LeaveCriticalSection` at `0x18003f918`
- `KERNEL32!LeaveCriticalSection` at `0x18003f8f2`
- `KERNEL32!LeaveCriticalSection` at `0x18003f918`
- `KERNEL32!Sleep` at `0x18003f843`
- `KERNEL32!Sleep` at `0x18003f872`
- `KERNEL32!Sleep` at `0x18003f8fd`
- `KERNEL32!Sleep` at `0x18003f9c6`
- `KERNEL32!Sleep` at `0x18003fa25`
- `KERNEL32!Sleep` at `0x18003fac8`
- `KERNEL32!Sleep` at `0x18003fb26`
- `KERNEL32!Sleep` at `0x18003f843`
- `KERNEL32!Sleep` at `0x18003f872`
- `KERNEL32!Sleep` at `0x18003f8fd`
- `KERNEL32!Sleep` at `0x18003f9c6`
- `KERNEL32!Sleep` at `0x18003fa25`
- `KERNEL32!Sleep` at `0x18003fac8`
- `KERNEL32!Sleep` at `0x18003fb26`
- `KERNEL32!EnterCriticalSection` at `0x18003f906`
- `KERNEL32!EnterCriticalSection` at `0x18003f906`
- `KERNEL32!GetCurrentThread` at `0x18003f76c`
- `KERNEL32!GetCurrentThread` at `0x18003f94c`
- `KERNEL32!GetCurrentThread` at `0x18003fb7b`
- `KERNEL32!GetCurrentThread` at `0x18003f76c`
- `KERNEL32!GetCurrentThread` at `0x18003f94c`
- `KERNEL32!GetCurrentThread` at `0x18003fb7b`
- `iisutil!PuDbgPrint` at `0x18003f7d9`
- `iisutil!PuDbgPrint` at `0x18003f827`
- `iisutil!PuDbgPrint` at `0x18003f8b0`
- `iisutil!PuDbgPrint` at `0x18003f8e3`
- `iisutil!PuDbgPrint` at `0x18003f946`
- `iisutil!PuDbgPrint` at `0x18003fa10`
- `iisutil!PuDbgPrint` at `0x18003fa76`
- `iisutil!PuDbgPrint` at `0x18003fab3`
- `iisutil!PuDbgPrint` at `0x18003fb19`
- `iisutil!PuDbgPrint` at `0x18003fb75`
- `iisutil!PuDbgPrint` at `0x18003f7d9`
- `iisutil!PuDbgPrint` at `0x18003f827`
- `iisutil!PuDbgPrint` at `0x18003f8b0`
- `iisutil!PuDbgPrint` at `0x18003f8e3`
- `iisutil!PuDbgPrint` at `0x18003f946`
- `iisutil!PuDbgPrint` at `0x18003fa10`
- `iisutil!PuDbgPrint` at `0x18003fa76`
- `iisutil!PuDbgPrint` at `0x18003fab3`
- `iisutil!PuDbgPrint` at `0x18003fb19`
- `iisutil!PuDbgPrint` at `0x18003fb75`

## pseudocode

```c
__int64 ShutDown(void)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  CApplnMgr *v2; // rcx
  int v3; // esi
  CTemplateCacheManager *v4; // rcx
  CTemplateCacheManager *v5; // rcx
  unsigned int v6; // eax
  signed int v7; // ebx
  signed int i; // ebx
  HANDLE v9; // rax
  struct CApplnMgr *v10; // rdx
  struct CAppln *v11; // rax
  struct CAppln *v12; // rbx
  int j; // edi
  CScriptManager *v14; // rcx
  int k; // ebx
  unsigned int v16; // eax
  CScriptManager *v17; // rcx
  int m; // ebx
  unsigned int v19; // eax
  unsigned int v20; // edx
  HANDLE v21; // rax
  void **v23; // [rsp+40h] [rbp-48h] BYREF
  __int128 v24; // [rsp+48h] [rbp-40h]
  int v25; // [rsp+58h] [rbp-30h]

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v3 = 0;
  if ( ThreadPriority != 0x7FFFFFFF )
    v3 = ThreadPriority;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1311,
      "ShutDown",
      "ASP Shutdown: %d apps (%d restarting), %d sessions\n",
      g_nApplications,
      g_nApplicationsRestarting,
      g_nSessions);
  CApplnMgr::ShutdownApplications(v2);
  CTemplateCacheManager::ShutdownCacheChangeNotification(v4);
  if ( g_pPDM )
  {
    CTemplateCacheManager::RemoveApplicationFromDebuggerUI(v5, 0);
    UnInitDebugging();
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 1330, "ShutDown", "ASP Shutdown: PDM Closed\n");
  }
  v6 = g_nBrowserRequests;
  if ( g_nBrowserRequests )
  {
    v7 = 2 * g_nBrowserRequests;
    do
    {
      if ( v7 <= 0 )
        break;
      Sleep(0x64u);
      v6 = g_nBrowserRequests;
      --v7;
    }
    while ( g_nBrowserRequests );
    if ( v6 )
    {
      CScriptManager::EmptyRunningScriptList(v5);
      v6 = g_nBrowserRequests;
      for ( i = 2 * g_nBrowserRequests; v6 && i > 0; --i )
      {
        Sleep(0x64u);
        v6 = g_nBrowserRequests;
      }
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1353,
      "ShutDown",
      "ASP Shutdown: Requests drained: %d remaining\n",
      v6);
  CScriptManager::EmptyRunningScriptList(v5);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 1360, "ShutDown", "ASP Shutdown: Scripts killed\n");
  while ( 1 )
  {
    EnterCriticalSection(&stru_180079B28);
    if ( !g_nApplicationsRestarting )
      break;
    LeaveCriticalSection(&stru_180079B28);
    Sleep(0x64u);
  }
  LeaveCriticalSection(&stru_180079B28);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1374,
      "ShutDown",
      "ASP Shutdown: 0 applications restarting\n");
  v9 = GetCurrentThread();
  SetThreadPriority(v9, 1);
  v25 = 0;
  v23 = &CApplnIterator::`vftable';
  v24 = 0;
  CApplnIterator::Start((CApplnIterator *)&v23, v10);
  while ( 1 )
  {
    v11 = CApplnIterator::Next((CApplnIterator *)&v23);
    v12 = v11;
    if ( !v11 )
      break;
    CSessionMgr::UnScheduleSessionKiller(*((CSessionMgr **)v11 + 18));
    for ( j = *((_DWORD *)v12 + 21); j > 0; --j )
    {
      CSessionMgr::DeleteAllSessions(*((CSessionMgr **)v12 + 18), 1);
      if ( !*((_DWORD *)v12 + 21) )
        break;
      Sleep(0x64u);
    }
  }
  CApplnIterator::Stop((CApplnIterator *)&v23);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1405,
      "ShutDown",
      "ASP Shutdown: All sessions queued up for deletion. nSessions=%d\n",
      g_nSessions);
  while ( 1 )
  {
    v16 = g_nSessions;
    if ( !g_nSessions )
      break;
    for ( k = g_nSessions; v16 && k > 0; --k )
    {
      Sleep(0x64u);
      v16 = g_nSessions;
    }
    if ( !v16 )
      break;
    CScriptManager::EmptyRunningScriptList(v14);
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1421,
      "ShutDown",
      "ASP Shutdown: Finished waiting for sessions to go away. nSessions=%d\n",
      v16);
  CApplnMgr::DeleteAllApplications(v14);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1428,
      "ShutDown",
      "ASP Shutdown: All applications queued up for deletion. nApplications=%d\n",
      g_nApplications);
  while ( 1 )
  {
    v19 = g_nApplications;
    if ( !g_nApplications )
      break;
    for ( m = g_nApplications; v19 && m > 0; --m )
    {
      Sleep(0x3E8u);
      v19 = g_nApplications;
    }
    if ( !v19 )
      break;
    CScriptManager::EmptyRunningScriptList(v17);
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1444,
      "ShutDown",
      "ASP Shutdown: Finished waiting for applications to go away. nApplications=%d\n",
      v19);
  while ( g_nViperRequests > 0 )
    Sleep(0x64u);
  CoFreeUnusedLibraries();
  if ( g_pDebugActivity )
    CViperActivity::`scalar deleting destructor'(g_pDebugActivity, v20);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      1470,
      "ShutDown",
      "ASP Shutdown: Debug Activity destroyed\n");
  v21 = GetCurrentThread();
  SetThreadPriority(v21, v3);
  v23 = &CApplnIterator::`vftable';
  if ( (_QWORD)v24 )
    CApplnIterator::Stop((CApplnIterator *)&v23);
  return 0;
}

```

## disassembly

```asm
0x18003f760  push    rbx
0x18003f762  push    rsi
0x18003f763  push    rdi
0x18003f764  push    r12
0x18003f766  push    r13
0x18003f768  sub     rsp, 60h
0x18003f76c  call    cs:__imp_GetCurrentThread
0x18003f772  mov     rcx, rax; hThread
0x18003f775  call    cs:__imp_GetThreadPriority
0x18003f77b  xor     esi, esi
0x18003f77d  lea     r12, aShutdown; "ShutDown"
0x18003f784  cmp     eax, 7FFFFFFFh
0x18003f789  lea     r13, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x18003f790  cmovnz  esi, eax
0x18003f793  test    byte ptr cs:g_dwDebugFlags, 3
0x18003f79a  jz      short loc_18003F7DF
0x18003f79c  mov     eax, cs:?g_nSessions@@3KA; ulong g_nSessions
0x18003f7a2  mov     r9, r12
0x18003f7a5  mov     rcx, cs:g_pDebug
0x18003f7ac  mov     r8d, 51Fh
0x18003f7b2  mov     [rsp+88h+var_50], eax
0x18003f7b6  mov     rdx, r13
0x18003f7b9  mov     eax, cs:?g_nApplicationsRestarting@@3KA; ulong g_nApplicationsRestarting
0x18003f7bf  mov     [rsp+88h+var_58], eax
0x18003f7c3  mov     eax, cs:?g_nApplications@@3KA; ulong g_nApplications
0x18003f7c9  mov     [rsp+88h+var_60], eax
0x18003f7cd  lea     rax, aAspShutdownDAp; "ASP Shutdown: %d apps (%d restarting), "...
0x18003f7d4  mov     [rsp+88h+var_68], rax
0x18003f7d9  call    cs:__imp_PuDbgPrint
0x18003f7df  call    ?ShutdownApplications@CApplnMgr@@QEAAJXZ; CApplnMgr::ShutdownApplications(void)
0x18003f7e4  call    ?ShutdownCacheChangeNotification@CTemplateCacheManager@@QEAAHXZ; CTemplateCacheManager::ShutdownCacheChangeNotification(void)
0x18003f7e9  cmp     cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA, 0; IProcessDebugManager64 * g_pPDM
0x18003f7f1  jz      short loc_18003F82D
0x18003f7f3  xor     edx, edx; struct CAppln *
0x18003f7f5  call    ?RemoveApplicationFromDebuggerUI@CTemplateCacheManager@@QEAAXPEAVCAppln@@@Z; CTemplateCacheManager::RemoveApplicationFromDebuggerUI(CAppln *)
0x18003f7fa  call    ?UnInitDebugging@@YAJXZ; UnInitDebugging(void)
0x18003f7ff  test    byte ptr cs:g_dwDebugFlags, 3
0x18003f806  jz      short loc_18003F82D
0x18003f808  mov     rcx, cs:g_pDebug
0x18003f80f  lea     rax, aAspShutdownPdm; "ASP Shutdown: PDM Closed\n"
0x18003f816  mov     r9, r12
0x18003f819  mov     [rsp+88h+var_68], rax
0x18003f81e  mov     r8d, 532h
0x18003f824  mov     rdx, r13
0x18003f827  call    cs:__imp_PuDbgPrint
0x18003f82d  mov     eax, cs:?g_nBrowserRequests@@3KA; ulong g_nBrowserRequests
0x18003f833  test    eax, eax
0x18003f835  jz      short loc_18003F884
0x18003f837  lea     ebx, [rax+rax]
0x18003f83a  test    ebx, ebx
0x18003f83c  jle     short loc_18003F855
0x18003f83e  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003f843  call    cs:__imp_Sleep
0x18003f849  mov     eax, cs:?g_nBrowserRequests@@3KA; ulong g_nBrowserRequests
0x18003f84f  dec     ebx
0x18003f851  test    eax, eax
0x18003f853  jnz     short loc_18003F83A
0x18003f855  test    eax, eax
0x18003f857  jz      short loc_18003F884
0x18003f859  call    ?EmptyRunningScriptList@CScriptManager@@QEAAJXZ; CScriptManager::EmptyRunningScriptList(void)
0x18003f85e  mov     eax, cs:?g_nBrowserRequests@@3KA; ulong g_nBrowserRequests
0x18003f864  lea     ebx, [rax+rax]
0x18003f867  jmp     short loc_18003F880
0x18003f869  test    ebx, ebx
0x18003f86b  jle     short loc_18003F884
0x18003f86d  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003f872  call    cs:__imp_Sleep
0x18003f878  mov     eax, cs:?g_nBrowserRequests@@3KA; ulong g_nBrowserRequests
0x18003f87e  dec     ebx
0x18003f880  test    eax, eax
0x18003f882  jnz     short loc_18003F869
0x18003f884  test    byte ptr cs:g_dwDebugFlags, 3
0x18003f88b  jz      short loc_18003F8B6
0x18003f88d  mov     rcx, cs:g_pDebug
0x18003f894  mov     r9, r12
0x18003f897  mov     [rsp+88h+var_60], eax
0x18003f89b  mov     r8d, 549h
0x18003f8a1  lea     rax, aAspShutdownReq; "ASP Shutdown: Requests drained: %d rema"...
0x18003f8a8  mov     rdx, r13
0x18003f8ab  mov     [rsp+88h+var_68], rax
0x18003f8b0  call    cs:__imp_PuDbgPrint
0x18003f8b6  call    ?EmptyRunningScriptList@CScriptManager@@QEAAJXZ; CScriptManager::EmptyRunningScriptList(void)
0x18003f8bb  test    byte ptr cs:g_dwDebugFlags, 3
0x18003f8c2  jz      short loc_18003F8E9
0x18003f8c4  mov     rcx, cs:g_pDebug
0x18003f8cb  lea     rax, aAspShutdownScr; "ASP Shutdown: Scripts killed\n"
0x18003f8d2  mov     r9, r12
0x18003f8d5  mov     [rsp+88h+var_68], rax
0x18003f8da  mov     r8d, 550h
0x18003f8e0  mov     rdx, r13
0x18003f8e3  call    cs:__imp_PuDbgPrint
0x18003f8e9  lea     rbx, stru_180079B28
0x18003f8f0  jmp     short loc_18003F903
0x18003f8f2  call    cs:__imp_LeaveCriticalSection
0x18003f8f8  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003f8fd  call    cs:__imp_Sleep
0x18003f903  mov     rcx, rbx; lpCriticalSection
0x18003f906  call    cs:__imp_EnterCriticalSection
0x18003f90c  cmp     cs:?g_nApplicationsRestarting@@3KA, 0; ulong g_nApplicationsRestarting
0x18003f913  mov     rcx, rbx; lpCriticalSection
0x18003f916  ja      short loc_18003F8F2
0x18003f918  call    cs:__imp_LeaveCriticalSection
0x18003f91e  test    byte ptr cs:g_dwDebugFlags, 3
0x18003f925  jz      short loc_18003F94C
0x18003f927  mov     rcx, cs:g_pDebug
0x18003f92e  lea     rax, aAspShutdown0Ap; "ASP Shutdown: 0 applications restarting"...
0x18003f935  mov     r9, r12
0x18003f938  mov     [rsp+88h+var_68], rax
0x18003f93d  mov     r8d, 55Eh
0x18003f943  mov     rdx, r13
0x18003f946  call    cs:__imp_PuDbgPrint
0x18003f94c  call    cs:__imp_GetCurrentThread
0x18003f952  mov     rcx, rax; hThread
0x18003f955  mov     edx, 1; nPriority
0x18003f95a  call    cs:__imp_SetThreadPriority
0x18003f960  lea     rax, ??_7CApplnIterator@@6B@; const CApplnIterator::`vftable'
0x18003f967  mov     [rsp+88h+var_30], 0
0x18003f96f  xorps   xmm0, xmm0
0x18003f972  mov     [rsp+88h+var_48], rax
0x18003f977  lea     rcx, [rsp+88h+var_48]; this
0x18003f97c  movdqu  [rsp+88h+var_40], xmm0
0x18003f982  call    ?Start@CApplnIterator@@QEAAJPEAVCApplnMgr@@@Z; CApplnIterator::Start(CApplnMgr *)
0x18003f987  lea     rcx, [rsp+88h+var_48]; this
0x18003f98c  call    ?Next@CApplnIterator@@QEAAPEAVCAppln@@XZ; CApplnIterator::Next(void)
0x18003f991  mov     rbx, rax
0x18003f994  test    rax, rax
0x18003f997  jz      short loc_18003F9D4
0x18003f999  mov     rcx, [rax+90h]; this
0x18003f9a0  call    ?UnScheduleSessionKiller@CSessionMgr@@QEAAJXZ; CSessionMgr::UnScheduleSessionKiller(void)
0x18003f9a5  mov     edi, [rbx+54h]
0x18003f9a8  jmp     short loc_18003F9CE
0x18003f9aa  mov     rcx, [rbx+90h]; this
0x18003f9b1  mov     edx, 1; int
0x18003f9b6  call    ?DeleteAllSessions@CSessionMgr@@QEAAJH@Z; CSessionMgr::DeleteAllSessions(int)
0x18003f9bb  cmp     dword ptr [rbx+54h], 0
0x18003f9bf  jz      short loc_18003F987
0x18003f9c1  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003f9c6  call    cs:__imp_Sleep
0x18003f9cc  dec     edi
0x18003f9ce  test    edi, edi
0x18003f9d0  jg      short loc_18003F9AA
0x18003f9d2  jmp     short loc_18003F987
0x18003f9d4  lea     rcx, [rsp+88h+var_48]; this
0x18003f9d9  call    ?Stop@CApplnIterator@@QEAAJXZ; CApplnIterator::Stop(void)
0x18003f9de  test    byte ptr cs:g_dwDebugFlags, 3
0x18003f9e5  jz      short loc_18003FA40
0x18003f9e7  mov     eax, cs:?g_nSessions@@3KA; ulong g_nSessions
0x18003f9ed  mov     r9, r12
0x18003f9f0  mov     rcx, cs:g_pDebug
0x18003f9f7  mov     r8d, 57Dh
0x18003f9fd  mov     [rsp+88h+var_60], eax
0x18003fa01  mov     rdx, r13
0x18003fa04  lea     rax, aAspShutdownAll; "ASP Shutdown: All sessions queued up fo"...
0x18003fa0b  mov     [rsp+88h+var_68], rax
0x18003fa10  call    cs:__imp_PuDbgPrint
0x18003fa16  jmp     short loc_18003FA40
0x18003fa18  mov     ebx, eax
0x18003fa1a  jmp     short loc_18003FA33
0x18003fa1c  test    ebx, ebx
0x18003fa1e  jle     short loc_18003FA37
0x18003fa20  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003fa25  call    cs:__imp_Sleep
0x18003fa2b  mov     eax, cs:?g_nSessions@@3KA; ulong g_nSessions
0x18003fa31  dec     ebx
0x18003fa33  test    eax, eax
0x18003fa35  jnz     short loc_18003FA1C
0x18003fa37  test    eax, eax
0x18003fa39  jz      short loc_18003FA4A
0x18003fa3b  call    ?EmptyRunningScriptList@CScriptManager@@QEAAJXZ; CScriptManager::EmptyRunningScriptList(void)
0x18003fa40  mov     eax, cs:?g_nSessions@@3KA; ulong g_nSessions
0x18003fa46  test    eax, eax
0x18003fa48  jnz     short loc_18003FA18
0x18003fa4a  test    byte ptr cs:g_dwDebugFlags, 3
0x18003fa51  jz      short loc_18003FA7C
0x18003fa53  mov     rcx, cs:g_pDebug
0x18003fa5a  mov     r9, r12
0x18003fa5d  mov     [rsp+88h+var_60], eax
0x18003fa61  mov     r8d, 58Dh
0x18003fa67  lea     rax, aAspShutdownFin; "ASP Shutdown: Finished waiting for sess"...
0x18003fa6e  mov     rdx, r13
0x18003fa71  mov     [rsp+88h+var_68], rax
0x18003fa76  call    cs:__imp_PuDbgPrint
0x18003fa7c  call    ?DeleteAllApplications@CApplnMgr@@QEAAXXZ; CApplnMgr::DeleteAllApplications(void)
0x18003fa81  test    byte ptr cs:g_dwDebugFlags, 3
0x18003fa88  jz      short loc_18003FAE3
0x18003fa8a  mov     eax, cs:?g_nApplications@@3KA; ulong g_nApplications
0x18003fa90  mov     r9, r12
0x18003fa93  mov     rcx, cs:g_pDebug
0x18003fa9a  mov     r8d, 594h
0x18003faa0  mov     [rsp+88h+var_60], eax
0x18003faa4  mov     rdx, r13
0x18003faa7  lea     rax, aAspShutdownAll_0; "ASP Shutdown: All applications queued u"...
0x18003faae  mov     [rsp+88h+var_68], rax
0x18003fab3  call    cs:__imp_PuDbgPrint
0x18003fab9  jmp     short loc_18003FAE3
0x18003fabb  mov     ebx, eax
0x18003fabd  jmp     short loc_18003FAD6
0x18003fabf  test    ebx, ebx
0x18003fac1  jle     short loc_18003FADA
0x18003fac3  mov     ecx, 3E8h; dwMilliseconds
0x18003fac8  call    cs:__imp_Sleep
0x18003face  mov     eax, cs:?g_nApplications@@3KA; ulong g_nApplications
0x18003fad4  dec     ebx
0x18003fad6  test    eax, eax
0x18003fad8  jnz     short loc_18003FABF
0x18003fada  test    eax, eax
0x18003fadc  jz      short loc_18003FAED
0x18003fade  call    ?EmptyRunningScriptList@CScriptManager@@QEAAJXZ; CScriptManager::EmptyRunningScriptList(void)
0x18003fae3  mov     eax, cs:?g_nApplications@@3KA; ulong g_nApplications
0x18003fae9  test    eax, eax
0x18003faeb  jnz     short loc_18003FABB
0x18003faed  test    byte ptr cs:g_dwDebugFlags, 3
0x18003faf4  jz      short loc_18003FB2C
0x18003faf6  mov     rcx, cs:g_pDebug
0x18003fafd  mov     r9, r12
0x18003fb00  mov     [rsp+88h+var_60], eax
0x18003fb04  mov     r8d, 5A4h
0x18003fb0a  lea     rax, aAspShutdownFin_0; "ASP Shutdown: Finished waiting for appl"...
0x18003fb11  mov     rdx, r13
0x18003fb14  mov     [rsp+88h+var_68], rax
0x18003fb19  call    cs:__imp_PuDbgPrint
0x18003fb1f  jmp     short loc_18003FB2C
0x18003fb21  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18003fb26  call    cs:__imp_Sleep
0x18003fb2c  mov     eax, cs:?g_nViperRequests@@3JC; long volatile g_nViperRequests
0x18003fb32  test    eax, eax
0x18003fb34  jg      short loc_18003FB21
0x18003fb36  call    cs:__imp_CoFreeUnusedLibraries
0x18003fb3c  mov     rcx, cs:?g_pDebugActivity@@3PEAVCViperActivity@@EA; this
0x18003fb43  test    rcx, rcx
0x18003fb46  jz      short loc_18003FB4D
0x18003fb48  call    ??_GCViperActivity@@QEAAPEAXI@Z; CViperActivity::`scalar deleting destructor'(uint)
0x18003fb4d  test    byte ptr cs:g_dwDebugFlags, 3
0x18003fb54  jz      short loc_18003FB7B
0x18003fb56  mov     rcx, cs:g_pDebug
0x18003fb5d  lea     rax, aAspShutdownDeb; "ASP Shutdown: Debug Activity destroyed"...
0x18003fb64  mov     r9, r12
0x18003fb67  mov     [rsp+88h+var_68], rax
0x18003fb6c  mov     r8d, 5BEh
0x18003fb72  mov     rdx, r13
0x18003fb75  call    cs:__imp_PuDbgPrint
0x18003fb7b  call    cs:__imp_GetCurrentThread
0x18003fb81  mov     rcx, rax; hThread
0x18003fb84  mov     edx, esi; nPriority
0x18003fb86  call    cs:__imp_SetThreadPriority
0x18003fb8c  cmp     qword ptr [rsp+88h+var_40], 0
0x18003fb92  lea     rax, ??_7CApplnIterator@@6B@; const CApplnIterator::`vftable'
0x18003fb99  mov     [rsp+88h+var_48], rax
0x18003fb9e  jz      short loc_18003FBAA
0x18003fba0  lea     rcx, [rsp+88h+var_48]; this
0x18003fba5  call    ?Stop@CApplnIterator@@QEAAJXZ; CApplnIterator::Stop(void)
0x18003fbaa  xor     eax, eax
0x18003fbac  add     rsp, 60h
0x18003fbb0  pop     r13
0x18003fbb2  pop     r12
0x18003fbb4  pop     rdi
0x18003fbb5  pop     rsi
0x18003fbb6  pop     rbx
0x18003fbb7  retn
```
