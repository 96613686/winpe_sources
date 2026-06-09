# CTimerThread::Thread(CTimerThread *)

- ea: `0x18005f130`
- end: `0x18005f4b4`
- name: `?Thread@CTimerThread@@SAJPEAV1@@Z`
- size: `900`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000c7b4`
- `0x18005e88c`
- `0x18005f130`
- `0x18006028c`
- `0x1800aaa58`
- `0x1800b3ac0`
- `0x1800c12b4`
- `0x1800d6a54`
- `0x18010b1d0`
- `0x1801691d0`
- `0x180183ad0`
- `0x18019d2e0`
- `0x1801abeb0`
- `0x1801abf7c`
- `0x1801ac0bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f153`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f153`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f1bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f43e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f46c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f1bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f43e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f46c`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18005f163`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18005f163`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005f147`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005f147`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005f49b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005f49b`

## string_xrefs

- `0x18005f15c`: `Gathering Service Timer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTimerThread::Thread(CThread *Parameter)
{
  HRESULT v2; // ebx
  HANDLE CurrentThread; // rax
  const wchar_t *v4; // r9
  CEventThrottleManager *v5; // rcx
  signed int v6; // r14d
  DWORD TickCount; // eax
  CRegistry *v8; // r9
  char v9; // si
  CRegistry *v10; // rax
  volatile signed __int32 *v11; // rcx
  unsigned int *v12; // rax
  unsigned int v13; // ecx
  unsigned int *v14; // rax
  unsigned int v15; // r8d
  unsigned int *v16; // r8
  unsigned int v17; // r10d
  unsigned int v18; // r11d
  unsigned int v19; // r10d
  unsigned int *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned int *v23; // rax
  CEventThrottleManager *v24; // rcx
  char v25; // al
  _DWORD *v26; // rax
  _DWORD *v27; // rax
  unsigned int v28; // eax
  int v29; // r8d
  unsigned int v30; // edx
  DWORD v31; // ebp
  char v33; // [rsp+50h] [rbp+8h] BYREF
  HRESULT v34; // [rsp+58h] [rbp+10h]

  v2 = CoInitializeEx(0, 0);
  v34 = v2;
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, L"Gathering Service Timer");
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\timerthrd.cxx\"",
    (const wchar_t *)0x80,
    (unsigned int)L"[SrchGatherSvc] Started Timer\n",
    v4);
  CEventThrottleManager::InitializeIfNeeded(v5);
  v6 = (unsigned int)(g_lEventThrottleFlushPeriodMs / 1000) / *((_DWORD *)g_pGatheringService + 324);
  if ( v6 < 1 )
    v6 = 1;
  TickCount = GetTickCount();
  v9 = 0;
  while ( 1 )
  {
    v31 = TickCount;
    if ( *((_DWORD *)Parameter + 10) )
      break;
    CActiveQueue::ProvideRobotThread(*((CActiveQueue **)g_pGatheringService + 489));
    v10 = g_pGatheringService;
    v11 = (volatile signed __int32 *)*((_QWORD *)g_pGatheringService + 927);
    if ( v11 )
    {
      _InterlockedAdd(v11, 1u);
      v10 = g_pGatheringService;
    }
    if ( !*((_DWORD *)v10 + 316) )
      CGatheringService::CheckProcesses((CGatheringService *)v11);
    if ( *((_DWORD *)Parameter + 10) )
      break;
    HandlePingPlugins();
    if ( *((_DWORD *)Parameter + 10) )
      break;
    v8 = g_pGatheringService;
    v12 = (unsigned int *)*((_QWORD *)g_pGatheringService + 927);
    if ( v12 )
      v13 = *v12;
    else
      v13 = 0;
    if ( !(v13 % (0x78u / *((_DWORD *)g_pGatheringService + 324))) )
    {
      CRobotThreadPool::StopThreadsIdleTooLong(*((CRobotThreadPool **)g_pGatheringService + 488));
      v8 = g_pGatheringService;
    }
    v14 = (unsigned int *)*((_QWORD *)v8 + 927);
    if ( v14 )
      v15 = *v14;
    else
      v15 = 0;
    if ( !(v15 % (0x12Cu / *((_DWORD *)v8 + 324))) )
    {
      CLanguageResourcePools::RemoveObsoleteResources(*((CLanguageResourcePools **)v8 + 499));
      v8 = g_pGatheringService;
    }
    v16 = (unsigned int *)*((_QWORD *)v8 + 927);
    if ( v16 )
      v17 = *v16;
    else
      v17 = 0;
    v18 = *((_DWORD *)v8 + 324);
    if ( !(v17 % (0x3C / v18)) )
    {
      if ( v16 )
        v19 = *v16;
      else
        v19 = 0;
      CGatherApplicationCollection::CheckCrawlInterval(
        *((CGatherApplicationCollection **)v8 + 47),
        v19 % (0x384 / v18) == 0);
      v8 = g_pGatheringService;
    }
    v20 = (unsigned int *)*((_QWORD *)v8 + 927);
    if ( v20 )
      v21 = *v20;
    else
      v21 = 0;
    v22 = (unsigned int)v21 % (0xA8C0u / *((_DWORD *)v8 + 324));
    if ( !(_DWORD)v22 )
    {
      CGatheringService::FlushSQMData(v8);
      v8 = g_pGatheringService;
    }
    if ( *((_DWORD *)Parameter + 10) )
      break;
    if ( !v9 )
    {
      v23 = (unsigned int *)*((_QWORD *)v8 + 927);
      if ( v23 )
        v21 = *v23;
      else
        v21 = 0;
      v24 = (CEventThrottleManager *)(0xE10u / *((_DWORD *)v8 + 324));
      v22 = (unsigned int)v21 % (unsigned int)v24;
      if ( (unsigned int)v21 % (unsigned int)v24 )
        goto LABEL_46;
      v9 = 1;
    }
    v33 = 1;
    if ( (int)ForEachGatherer__lambda_c5dfdb0b802aebc14c3d6037d41ece7b_(&v33, v22, v21, v8) >= 0 )
    {
      v25 = v33;
    }
    else
    {
      v25 = 0;
      v33 = 0;
    }
    if ( v25 )
    {
      v9 = 0;
      CUserSettings::StartMonitoringCertStores((CRegistry *)((char *)g_pGatheringService + 6688));
    }
    v8 = g_pGatheringService;
LABEL_46:
    v26 = (_DWORD *)*((_QWORD *)v8 + 927);
    if ( v26 )
      LODWORD(v26) = *v26;
    if ( !((unsigned int)v26 % v6) )
    {
      CEventThrottleManager::Flush(v24);
      v8 = g_pGatheringService;
    }
    v27 = (_DWORD *)*((_QWORD *)v8 + 927);
    if ( v27 )
      LODWORD(v27) = *v27;
    if ( !((unsigned int)v27 % *((_DWORD *)v8 + 322)) )
    {
      v33 = 0;
      ForEachGatherer__lambda_d24c8be6bd95d952914f1bb4154e40b6_(&v33);
    }
    if ( *((_DWORD *)Parameter + 11) )
    {
      if ( *((_DWORD *)Parameter + 10) )
        break;
      CThread::WaitForEvent(Parameter, 0xFFFFFFFF, v21);
    }
    if ( *((_DWORD *)Parameter + 10) )
      break;
    do
    {
      v28 = GetTickCount() - v31;
      v30 = 1000 * *((_DWORD *)g_pGatheringService + 324);
    }
    while ( v28 < v30 && CThread::WaitForEvent(Parameter, v30 - v28, v29) == 192 );
    TickCount = GetTickCount();
  }
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\timerthrd.cxx\"",
    (const wchar_t *)0x118,
    (unsigned int)L"[SrchGatherSvc] Terminated Timer\n",
    (const wchar_t *)v8);
  if ( v2 >= 0 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18005f130  mov     [rsp+arg_10], rbx
0x18005f135  push    rbp
0x18005f136  push    rsi
0x18005f137  push    rdi
0x18005f138  push    r12
0x18005f13a  push    r14
0x18005f13c  sub     rsp, 20h
0x18005f140  mov     rdi, rcx
0x18005f143  xor     edx, edx; dwCoInit
0x18005f145  xor     ecx, ecx; pvReserved
0x18005f147  call    cs:__imp_CoInitializeEx
0x18005f14d  mov     ebx, eax
0x18005f14f  mov     [rsp+48h+arg_8], eax
0x18005f153  call    cs:__imp_GetCurrentThread
0x18005f159  mov     rcx, rax; hThread
0x18005f15c  lea     rdx, ThreadDescription; "Gathering Service Timer"
0x18005f163  call    cs:__imp_SetThreadDescription
0x18005f169  lea     r8, aSrchgathersvcS_0; "[SrchGatherSvc] Started Timer\n"
0x18005f170  mov     edx, 80h; wchar_t *
0x18005f175  lea     rcx, aOnecoreuapBase_138; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18005f17c  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18005f181  call    ?InitializeIfNeeded@CEventThrottleManager@@QEAAXXZ; CEventThrottleManager::InitializeIfNeeded(void)
0x18005f186  mov     eax, 10624DD3h
0x18005f18b  imul    cs:?g_lEventThrottleFlushPeriodMs@@3JA; long g_lEventThrottleFlushPeriodMs
0x18005f191  mov     eax, edx
0x18005f193  sar     eax, 6
0x18005f196  mov     ecx, eax
0x18005f198  shr     ecx, 1Fh
0x18005f19b  add     eax, ecx
0x18005f19d  xor     edx, edx
0x18005f19f  mov     rcx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f1a6  div     dword ptr [rcx+510h]
0x18005f1ac  mov     r14d, eax
0x18005f1af  mov     r12d, 1
0x18005f1b5  cmp     eax, r12d
0x18005f1b8  cmovl   r14d, r12d
0x18005f1bc  call    cs:__imp_GetTickCount
0x18005f1c2  xor     sil, sil
0x18005f1c5  jmp     loc_18005F472
0x18005f1ca  mov     rcx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f1d1  mov     rcx, [rcx+0F48h]; this
0x18005f1d8  call    ?ProvideRobotThread@CActiveQueue@@QEAAXXZ; CActiveQueue::ProvideRobotThread(void)
0x18005f1dd  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f1e4  mov     rcx, [rax+1CF8h]; this
0x18005f1eb  test    rcx, rcx
0x18005f1ee  jz      short loc_18005F1FB
0x18005f1f0  lock add [rcx], r12d
0x18005f1f4  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f1fb  cmp     dword ptr [rax+4F0h], 0
0x18005f202  jnz     short loc_18005F209
0x18005f204  call    ?CheckProcesses@CGatheringService@@QEAAXXZ; CGatheringService::CheckProcesses(void)
0x18005f209  cmp     dword ptr [rdi+28h], 0
0x18005f20d  jnz     loc_18005F47E
0x18005f213  call    ?HandlePingPlugins@@YAXXZ; HandlePingPlugins(void)
0x18005f218  cmp     dword ptr [rdi+28h], 0
0x18005f21c  jnz     loc_18005F47E
0x18005f222  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f229  mov     rax, [r9+1CF8h]
0x18005f230  test    rax, rax
0x18005f233  jz      short loc_18005F239
0x18005f235  mov     ecx, [rax]
0x18005f237  jmp     short loc_18005F23B
0x18005f239  xor     ecx, ecx
0x18005f23b  xor     edx, edx
0x18005f23d  lea     eax, [rdx+78h]
0x18005f240  div     dword ptr [r9+510h]
0x18005f247  mov     r8d, eax
0x18005f24a  xor     edx, edx
0x18005f24c  mov     eax, ecx
0x18005f24e  div     r8d
0x18005f251  test    edx, edx
0x18005f253  jnz     short loc_18005F268
0x18005f255  mov     rcx, [r9+0F40h]; this
0x18005f25c  call    ?StopThreadsIdleTooLong@CRobotThreadPool@@QEAAXXZ; CRobotThreadPool::StopThreadsIdleTooLong(void)
0x18005f261  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f268  mov     rax, [r9+1CF8h]
0x18005f26f  test    rax, rax
0x18005f272  jz      short loc_18005F279
0x18005f274  mov     r8d, [rax]
0x18005f277  jmp     short loc_18005F27C
0x18005f279  xor     r8d, r8d
0x18005f27c  xor     edx, edx
0x18005f27e  mov     eax, 12Ch
0x18005f283  div     dword ptr [r9+510h]
0x18005f28a  mov     ecx, eax
0x18005f28c  xor     edx, edx
0x18005f28e  mov     eax, r8d
0x18005f291  div     ecx
0x18005f293  test    edx, edx
0x18005f295  jnz     short loc_18005F2AA
0x18005f297  mov     rcx, [r9+0F98h]; this
0x18005f29e  call    ?RemoveObsoleteResources@CLanguageResourcePools@@QEAAXXZ; CLanguageResourcePools::RemoveObsoleteResources(void)
0x18005f2a3  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f2aa  mov     r8, [r9+1CF8h]
0x18005f2b1  test    r8, r8
0x18005f2b4  jz      short loc_18005F2BB
0x18005f2b6  mov     r10d, [r8]
0x18005f2b9  jmp     short loc_18005F2BE
0x18005f2bb  xor     r10d, r10d
0x18005f2be  mov     r11d, [r9+510h]
0x18005f2c5  xor     edx, edx
0x18005f2c7  lea     eax, [rdx+3Ch]
0x18005f2ca  div     r11d
0x18005f2cd  mov     ecx, eax
0x18005f2cf  xor     edx, edx
0x18005f2d1  mov     eax, r10d
0x18005f2d4  div     ecx
0x18005f2d6  test    edx, edx
0x18005f2d8  jnz     short loc_18005F316
0x18005f2da  test    r8, r8
0x18005f2dd  jz      short loc_18005F2E4
0x18005f2df  mov     r10d, [r8]
0x18005f2e2  jmp     short loc_18005F2E7
0x18005f2e4  xor     r10d, r10d
0x18005f2e7  xor     edx, edx
0x18005f2e9  mov     eax, 384h
0x18005f2ee  div     r11d
0x18005f2f1  mov     ecx, eax
0x18005f2f3  xor     edx, edx
0x18005f2f5  mov     eax, r10d
0x18005f2f8  div     ecx
0x18005f2fa  xor     eax, eax
0x18005f2fc  test    edx, edx
0x18005f2fe  setz    al
0x18005f301  mov     edx, eax; int
0x18005f303  mov     rcx, [r9+178h]; this
0x18005f30a  call    ?CheckCrawlInterval@CGatherApplicationCollection@@QEAAXH@Z; CGatherApplicationCollection::CheckCrawlInterval(int)
0x18005f30f  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f316  mov     rax, [r9+1CF8h]
0x18005f31d  test    rax, rax
0x18005f320  jz      short loc_18005F327
0x18005f322  mov     r8d, [rax]
0x18005f325  jmp     short loc_18005F32A
0x18005f327  xor     r8d, r8d
0x18005f32a  xor     edx, edx
0x18005f32c  mov     eax, 0A8C0h
0x18005f331  div     dword ptr [r9+510h]
0x18005f338  mov     ecx, eax
0x18005f33a  xor     edx, edx
0x18005f33c  mov     eax, r8d
0x18005f33f  div     ecx
0x18005f341  test    edx, edx
0x18005f343  jnz     short loc_18005F354
0x18005f345  mov     rcx, r9; this
0x18005f348  call    ?FlushSQMData@CGatheringService@@QEAAXXZ; CGatheringService::FlushSQMData(void)
0x18005f34d  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f354  cmp     dword ptr [rdi+28h], 0
0x18005f358  jnz     loc_18005F47E
0x18005f35e  test    sil, sil
0x18005f361  jnz     short loc_18005F395
0x18005f363  mov     rax, [r9+1CF8h]
0x18005f36a  test    rax, rax
0x18005f36d  jz      short loc_18005F374
0x18005f36f  mov     r8d, [rax]
0x18005f372  jmp     short loc_18005F377
0x18005f374  xor     r8d, r8d
0x18005f377  xor     edx, edx
0x18005f379  mov     eax, 0E10h
0x18005f37e  div     dword ptr [r9+510h]
0x18005f385  mov     ecx, eax
0x18005f387  xor     edx, edx
0x18005f389  mov     eax, r8d
0x18005f38c  div     ecx
0x18005f38e  test    edx, edx
0x18005f390  jnz     short loc_18005F3D5
0x18005f392  mov     sil, r12b
0x18005f395  mov     [rsp+48h+arg_0], r12b
0x18005f39a  lea     rcx, [rsp+48h+arg_0]
0x18005f39f  call    _ForEachGatherer__lambda_c5dfdb0b802aebc14c3d6037d41ece7b___; ForEachGatherer__lambda_c5dfdb0b802aebc14c3d6037d41ece7b_
0x18005f3a4  test    eax, eax
0x18005f3a6  jns     short loc_18005F3B0
0x18005f3a8  xor     al, al
0x18005f3aa  mov     [rsp+48h+arg_0], al
0x18005f3ae  jmp     short loc_18005F3B4
0x18005f3b0  mov     al, [rsp+48h+arg_0]
0x18005f3b4  test    al, al
0x18005f3b6  jz      short loc_18005F3CE
0x18005f3b8  xor     sil, sil
0x18005f3bb  mov     rcx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f3c2  add     rcx, 1A20h; this
0x18005f3c9  call    ?StartMonitoringCertStores@CUserSettings@@QEAAJXZ; CUserSettings::StartMonitoringCertStores(void)
0x18005f3ce  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f3d5  mov     rax, [r9+1CF8h]
0x18005f3dc  test    rax, rax
0x18005f3df  jz      short loc_18005F3E3
0x18005f3e1  mov     eax, [rax]
0x18005f3e3  xor     edx, edx
0x18005f3e5  div     r14d
0x18005f3e8  test    edx, edx
0x18005f3ea  jnz     short loc_18005F3F8
0x18005f3ec  call    ?Flush@CEventThrottleManager@@QEAAXXZ; CEventThrottleManager::Flush(void)
0x18005f3f1  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f3f8  mov     rax, [r9+1CF8h]
0x18005f3ff  test    rax, rax
0x18005f402  jz      short loc_18005F406
0x18005f404  mov     eax, [rax]
0x18005f406  xor     edx, edx
0x18005f408  div     dword ptr [r9+508h]
0x18005f40f  test    edx, edx
0x18005f411  jnz     short loc_18005F421
0x18005f413  mov     [rsp+48h+arg_0], dl
0x18005f417  lea     rcx, [rsp+48h+arg_0]
0x18005f41c  call    _ForEachGatherer__lambda_d24c8be6bd95d952914f1bb4154e40b6___; ForEachGatherer__lambda_d24c8be6bd95d952914f1bb4154e40b6_
0x18005f421  cmp     dword ptr [rdi+2Ch], 0
0x18005f425  jz      short loc_18005F438
0x18005f427  cmp     dword ptr [rdi+28h], 0
0x18005f42b  jnz     short loc_18005F47E
0x18005f42d  or      edx, 0FFFFFFFFh; unsigned int
0x18005f430  mov     rcx, rdi; this
0x18005f433  call    ?WaitForEvent@CThread@@QEAAKKH@Z; CThread::WaitForEvent(ulong,int)
0x18005f438  cmp     dword ptr [rdi+28h], 0
0x18005f43c  jnz     short loc_18005F47E
0x18005f43e  call    cs:__imp_GetTickCount
0x18005f444  sub     eax, ebp
0x18005f446  mov     rcx, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x18005f44d  imul    edx, [rcx+510h], 3E8h
0x18005f457  cmp     eax, edx
0x18005f459  jnb     short loc_18005F46C
0x18005f45b  sub     edx, eax; unsigned int
0x18005f45d  mov     rcx, rdi; this
0x18005f460  call    ?WaitForEvent@CThread@@QEAAKKH@Z; CThread::WaitForEvent(ulong,int)
0x18005f465  cmp     eax, 0C0h
0x18005f46a  jz      short loc_18005F43E
0x18005f46c  call    cs:__imp_GetTickCount
0x18005f472  cmp     dword ptr [rdi+28h], 0
0x18005f476  mov     ebp, eax
0x18005f478  jz      loc_18005F1CA
0x18005f47e  lea     r8, aSrchgathersvcT_0; "[SrchGatherSvc] Terminated Timer\n"
0x18005f485  mov     edx, 118h; wchar_t *
0x18005f48a  lea     rcx, aOnecoreuapBase_138; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18005f491  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18005f496  nop
0x18005f497  test    ebx, ebx
0x18005f499  js      short loc_18005F4A1
0x18005f49b  call    cs:__imp_CoUninitialize
0x18005f4a1  xor     eax, eax
0x18005f4a3  mov     rbx, [rsp+48h+arg_10]
0x18005f4a8  add     rsp, 20h
0x18005f4ac  pop     r14
0x18005f4ae  pop     r12
0x18005f4b0  pop     rdi
0x18005f4b1  pop     rsi
0x18005f4b2  pop     rbp
0x18005f4b3  retn
```
