# CDsmCore::_Startup(void)

- ea: `0x180024374`
- end: `0x1800247d0`
- name: `?_Startup@CDsmCore@@AEAAJXZ`
- size: `1116`
- prototype: `__int64 __fastcall(CDsmCore *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800238e8`

## callees

- `0x18000ba0c`
- `0x18000e974`
- `0x18000f990`
- `0x1800112a4`
- `0x180011a00`
- `0x18001370c`
- `0x180013864`
- `0x180013af8`
- `0x180014bb4`
- `0x180018308`
- `0x180018368`
- `0x180018f58`
- `0x1800190bc`
- `0x180019148`
- `0x18001baa8`
- `0x180021790`
- `0x180022070`
- `0x18002216c`
- `0x180024374`
- `0x1800298b4`
- `0x18002b2f8`
- `0x18002c124`
- `0x18002d464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800243bf`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800243d3`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800243bf`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800243d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024759`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002476a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024759`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002476a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024650`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002461d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002461d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800245b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800245b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002460b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002460b`

## string_xrefs

- `0x18002473d`: `onecoreuap\base\devices\setup\dsm\service\core.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDsmCore::_Startup(CDsmCore *this)
{
  __int64 v1; // rax
  JobScheduler *v2; // rcx
  JobScheduler *v3; // rdx
  std::_Ref_count_base *v4; // rcx
  _DWORD *v5; // rbx
  std::_Ref_count_base *v6; // rcx
  __int64 v7; // rax
  std::_Ref_count_base *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r9
  EventScan *v11; // rax
  EventScan *v12; // rdx
  const char *v13; // r9
  struct _TP_POOL *Threadpool; // rax
  signed int LastError; // eax
  signed int v16; // ebx
  signed int v17; // eax
  CNetworkEvents *v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  JobScheduler *v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  int v24; // eax
  int v26; // [rsp+20h] [rbp-88h]
  _BYTE v27[8]; // [rsp+30h] [rbp-78h] BYREF
  std::_Ref_count_base *v28; // [rsp+38h] [rbp-70h]
  __int64 *v29; // [rsp+40h] [rbp-68h] BYREF
  char v30; // [rsp+48h] [rbp-60h]
  _BYTE v31[88]; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  CDsmCore *v33; // [rsp+B0h] [rbp+8h] BYREF

  v33 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
  InitializeSRWLock(&CDsmMetadataTask::s_srwLock);
  CDevNotify::_bInShutdown = 0;
  InitializeSRWLock(&CDevNotify::_srwObjectListLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
  try
  {
    v1 = std::make_shared<JobScheduler,>();
    v2 = *(JobScheduler **)v1;
    v3 = *(JobScheduler **)(v1 + 8);
    *(_QWORD *)v1 = 0;
    *(_QWORD *)(v1 + 8) = 0;
    xmmword_180059EC0 = v2;
    v4 = *(&xmmword_180059EC0 + 1);
    *(&xmmword_180059EC0 + 1) = v3;
    if ( v4 )
      std::_Ref_count_base::_Decref(v4);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    v5 = operator new(0xC0u);
    v33 = (CDsmCore *)v5;
    v5[2] = 1;
    v5[3] = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<ContainerManager>::`vftable';
    ContainerManager::ContainerManager((ContainerManager *)(v5 + 4));
    xmmword_180059F10 = (ContainerManager *)(v5 + 4);
    v6 = *(&xmmword_180059F10 + 1);
    *(&xmmword_180059F10 + 1) = (ContainerManager *)v5;
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
    v33 = (CDsmCore *)operator new(0xE0u);
    v7 = std::_Ref_count_obj2<DriverRecoveryManager>::_Ref_count_obj2<DriverRecoveryManager>(v33);
    *(&xmmword_180059F20 + 1) = (EventScan *)(v7 + 16);
    v8 = qword_180059F30;
    qword_180059F30 = (std::_Ref_count_base *)v7;
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    operator new(0x40u);
    std::shared_ptr<Container>::shared_ptr<Container>(v27, &xmmword_180059F20 + 1);
    v9 = std::shared_ptr<Container>::shared_ptr<Container>(&v29, &xmmword_180059F10);
    v11 = (EventScan *)EventScan::EventScan(v10, v9);
    v33 = 0;
    v12 = xmmword_180059F20;
    xmmword_180059F20 = v11;
    if ( v12 )
      std::default_delete<EventScan>::operator()();
    std::unique_ptr<EventScan>::~unique_ptr<EventScan>(&v33);
  }
  catch ( ... )
  {
    LODWORD(v33) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xA9,
                     (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
                     v13);
    return (unsigned int)v33;
  }
  pcbe.Version = 3;
  *(_OWORD *)&pcbe.Pool = 0;
  pcbe.CleanupGroupCancelCallback = 0;
  pcbe.RaceDll = 0;
  pcbe.ActivationContext = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  Threadpool = CreateThreadpool(0);
  ptpp = Threadpool;
  if ( !Threadpool )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( v16 < 0 )
      goto LABEL_44;
    Threadpool = ptpp;
  }
  pcbe.Pool = Threadpool;
  pti = CreateThreadpoolTimer(CDsmCore::_TimerCallback, &g_DsmCore, &pcbe);
  if ( pti )
    goto LABEL_27;
  v17 = GetLastError();
  v16 = v17;
  if ( v17 > 0 )
    v16 = (unsigned __int16)v17 | 0x80070000;
  if ( v16 >= 0 )
  {
LABEL_27:
    if ( (unsigned int)CDsmCore::get_CoreServiceMode() != 4 )
      CNetworkEvents::Initialize(v18);
    AcquireSRWLockExclusive(&stru_180059EA8);
    v29 = &g_DsmCore;
    v30 = 1;
    ContainerManager::SetContainerManagerMode(xmmword_180059F10, dword_180059E30 != 3);
    v19 = DriverRecoveryManager::Initialize(*(&xmmword_180059F20 + 1));
    v16 = v19;
    if ( v19 < 0 )
    {
      v20 = 202;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\core.cpp",
        (const char *)(unsigned int)v19,
        v26);
      ReleaseSRWLockExclusive(&stru_180059EA8);
      return (unsigned int)v16;
    }
    v21 = xmmword_180059EC0;
    v33 = (CDsmCore *)v27;
    v22 = std::shared_ptr<Container>::shared_ptr<Container>(v27, &xmmword_180059F10);
    v23 = std::function<void (enum SchedulerEvent)>::function<void (enum SchedulerEvent)>(v31, &unk_180059ED0);
    v19 = JobScheduler::Initialize((__int64)v21, v23, v22);
    v16 = v19;
    if ( v19 < 0 )
    {
      v20 = 206;
      goto LABEL_40;
    }
    v24 = dword_180059E30;
    if ( dword_180059E30 != 3 )
    {
      v19 = EventScan::Initialize(xmmword_180059F20, &qword_18005A018);
      v16 = v19;
      if ( v19 < 0 )
      {
        v20 = 213;
        goto LABEL_40;
      }
      v24 = dword_180059E30;
    }
    if ( ((v24 - 1) & 0xFFFFFFFD) != 0 )
    {
      v19 = JobScheduler::Start(xmmword_180059EC0);
      v16 = v19;
      if ( v19 < 0 )
      {
        v20 = 219;
        goto LABEL_40;
      }
    }
    ReleaseSRWLockExclusive(&stru_180059EA8);
    v16 = DsmRpcStartup();
    if ( v16 >= 0 )
      CDsmCore::_SetCoreEvent(&g_DsmCore, 1);
  }
LABEL_44:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids,
      (unsigned int)v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180024374  mov     [rsp+arg_10], rbx
0x180024379  mov     [rsp+arg_0], rcx
0x18002437e  push    rdi
0x18002437f  push    r12
0x180024381  push    r13
0x180024383  sub     rsp, 90h
0x18002438a  lea     r13, WPP_GLOBAL_Control
0x180024391  mov     rcx, cs:WPP_GLOBAL_Control
0x180024398  cmp     rcx, r13
0x18002439b  jz      short loc_1800243B8
0x18002439d  test    byte ptr [rcx+1Ch], 1
0x1800243a1  jz      short loc_1800243B8
0x1800243a3  mov     edx, 0Dh
0x1800243a8  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x1800243af  mov     rcx, [rcx+10h]
0x1800243b3  call    WPP_SF_
0x1800243b8  lea     rcx, ?s_srwLock@CDsmMetadataTask@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800243bf  call    cs:__imp_InitializeSRWLock
0x1800243c5  mov     cs:?_bInShutdown@CDevNotify@@0_NA, 0; bool CDevNotify::_bInShutdown
0x1800243cc  lea     rcx, ?_srwObjectListLock@CDevNotify@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800243d3  call    cs:__imp_InitializeSRWLock
0x1800243d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243e0  cmp     rcx, r13
0x1800243e3  jz      short loc_180024401
0x1800243e5  test    byte ptr [rcx+1Ch], 1
0x1800243e9  jz      short loc_180024401
0x1800243eb  mov     edx, 0Eh
0x1800243f0  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x1800243f7  mov     rcx, [rcx+10h]
0x1800243fb  call    WPP_SF_
0x180024400  nop
0x180024401  lea     rcx, [rsp+0A8h+var_78]
0x180024406  call    ??$make_shared@VJobScheduler@@$$V@std@@YA?AV?$shared_ptr@VJobScheduler@@@0@XZ; std::make_shared<JobScheduler,>(void)
0x18002440b  mov     rcx, [rax]
0x18002440e  mov     rdx, [rax+8]
0x180024412  mov     qword ptr [rax], 0
0x180024419  mov     qword ptr [rax+8], 0
0x180024421  mov     qword ptr cs:xmmword_180059EC0, rcx
0x180024428  mov     rcx, qword ptr cs:xmmword_180059EC0+8; this
0x18002442f  mov     qword ptr cs:xmmword_180059EC0+8, rdx
0x180024436  test    rcx, rcx
0x180024439  jz      short loc_180024440
0x18002443b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180024440  mov     rcx, [rsp+0A8h+var_70]; this
0x180024445  test    rcx, rcx
0x180024448  jz      short loc_18002444F
0x18002444a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002444f  mov     ecx, 0C0h; Size
0x180024454  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024459  mov     rbx, rax
0x18002445c  mov     [rsp+0A8h+arg_0], rax
0x180024464  mov     dword ptr [rax+8], 1
0x18002446b  mov     dword ptr [rax+0Ch], 1
0x180024472  lea     rax, ??_7?$_Ref_count_obj2@VContainerManager@@@std@@6B@; const std::_Ref_count_obj2<ContainerManager>::`vftable'
0x180024479  mov     [rbx], rax
0x18002447c  lea     rdi, [rbx+10h]
0x180024480  mov     rcx, rdi; this
0x180024483  call    ??0ContainerManager@@QEAA@XZ; ContainerManager::ContainerManager(void)
0x180024488  nop
0x180024489  mov     qword ptr cs:xmmword_180059F10, rdi
0x180024490  mov     rcx, qword ptr cs:xmmword_180059F10+8; this
0x180024497  mov     qword ptr cs:xmmword_180059F10+8, rbx
0x18002449e  test    rcx, rcx
0x1800244a1  jz      short loc_1800244A8
0x1800244a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800244a8  mov     ecx, 0E0h; Size
0x1800244ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800244b2  mov     [rsp+0A8h+arg_0], rax
0x1800244ba  mov     rcx, rax
0x1800244bd  call    ??$?0$$V@?$_Ref_count_obj2@VDriverRecoveryManager@@@std@@QEAA@XZ; std::_Ref_count_obj2<DriverRecoveryManager>::_Ref_count_obj2<DriverRecoveryManager>(void)
0x1800244c2  nop
0x1800244c3  lea     rcx, [rax+10h]
0x1800244c7  mov     qword ptr cs:xmmword_180059F20+8, rcx
0x1800244ce  mov     rcx, cs:qword_180059F30; this
0x1800244d5  mov     cs:qword_180059F30, rax
0x1800244dc  test    rcx, rcx
0x1800244df  jz      short loc_1800244E6
0x1800244e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800244e6  mov     ecx, 40h ; '@'; Size
0x1800244eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800244f0  mov     r9, rax
0x1800244f3  lea     rdx, xmmword_180059F20+8
0x1800244fa  lea     rcx, [rsp+0A8h+var_78]
0x1800244ff  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x180024504  mov     r8, rax
0x180024507  lea     rdx, xmmword_180059F10
0x18002450e  lea     rcx, [rsp+0A8h+var_68]
0x180024513  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x180024518  mov     rdx, rax
0x18002451b  mov     rcx, r9
0x18002451e  call    ??0EventScan@@QEAA@V?$shared_ptr@VContainerManager@@@std@@V?$shared_ptr@VDriverRecoveryManager@@@2@@Z; EventScan::EventScan(std::shared_ptr<ContainerManager>,std::shared_ptr<DriverRecoveryManager>)
0x180024523  mov     [rsp+0A8h+arg_0], 0
0x18002452f  mov     rdx, qword ptr cs:xmmword_180059F20
0x180024536  mov     qword ptr cs:xmmword_180059F20, rax
0x18002453d  test    rdx, rdx
0x180024540  jz      short loc_180024547
0x180024542  call    ??R?$default_delete@VEventScan@@@std@@QEBAXPEAVEventScan@@@Z; std::default_delete<EventScan>::operator()(EventScan *)
0x180024547  lea     rcx, [rsp+0A8h+arg_0]
0x18002454f  call    ??1?$unique_ptr@VEventScan@@U?$default_delete@VEventScan@@@std@@@std@@QEAA@XZ; std::unique_ptr<EventScan>::~unique_ptr<EventScan>(void)
0x180024554  nop
0x180024555  mov     cs:pcbe.Version, 3
0x18002455f  xorps   xmm0, xmm0
0x180024562  movdqa  xmmword ptr cs:pcbe.Pool, xmm0
0x18002456a  mov     cs:pcbe.CleanupGroupCancelCallback, 0
0x180024575  mov     cs:pcbe.RaceDll, 0
0x180024580  mov     cs:pcbe.ActivationContext, 0
0x18002458b  mov     cs:pcbe.FinalizationCallback, 0
0x180024596  mov     dword ptr cs:pcbe.u, 0
0x1800245a0  mov     cs:pcbe.CallbackPriority, 1
0x1800245aa  mov     cs:pcbe.Size, 48h ; 'H'
0x1800245b4  xor     ecx, ecx; reserved
0x1800245b6  call    cs:__imp_CreateThreadpool
0x1800245bc  mov     cs:ptpp, rax
0x1800245c3  test    rax, rax
0x1800245c6  jnz     short loc_1800245EC
0x1800245c8  call    cs:__imp_GetLastError
0x1800245ce  mov     ebx, eax
0x1800245d0  test    eax, eax
0x1800245d2  jle     short loc_1800245DD
0x1800245d4  movzx   ebx, ax
0x1800245d7  or      ebx, 80070000h
0x1800245dd  test    ebx, ebx
0x1800245df  js      loc_180024788
0x1800245e5  mov     rax, cs:ptpp
0x1800245ec  mov     cs:pcbe.Pool, rax
0x1800245f3  lea     r8, pcbe; pcbe
0x1800245fa  lea     r12, ?g_DsmCore@@3VCDsmCore@@A; CDsmCore g_DsmCore
0x180024601  mov     rdx, r12; pv
0x180024604  lea     rcx, ?_TimerCallback@CDsmCore@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002460b  call    cs:__imp_CreateThreadpoolTimer
0x180024611  mov     cs:pti, rax
0x180024618  test    rax, rax
0x18002461b  jnz     short loc_18002463A
0x18002461d  call    cs:__imp_GetLastError
0x180024623  mov     ebx, eax
0x180024625  test    eax, eax
0x180024627  jle     short loc_180024632
0x180024629  movzx   ebx, ax
0x18002462c  or      ebx, 80070000h
0x180024632  test    ebx, ebx
0x180024634  js      loc_180024788
0x18002463a  call    ?get_CoreServiceMode@CDsmCore@@QEAA?AW4DSM_SERVICE_MODE@@XZ; CDsmCore::get_CoreServiceMode(void)
0x18002463f  cmp     eax, 4
0x180024642  jz      short loc_180024649
0x180024644  call    ?Initialize@CNetworkEvents@@QEAAJXZ; CNetworkEvents::Initialize(void)
0x180024649  lea     rcx, stru_180059EA8; SRWLock
0x180024650  call    cs:__imp_AcquireSRWLockExclusive
0x180024656  mov     [rsp+0A8h+var_68], r12
0x18002465b  mov     [rsp+0A8h+var_60], 1
0x180024660  xor     edx, edx
0x180024662  cmp     cs:dword_180059E30, 3
0x180024669  setnz   dl
0x18002466c  mov     rcx, qword ptr cs:xmmword_180059F10
0x180024673  call    ?SetContainerManagerMode@ContainerManager@@QEAAXW4ContainerManagerMode@@@Z; ContainerManager::SetContainerManagerMode(ContainerManagerMode)
0x180024678  mov     rcx, qword ptr cs:xmmword_180059F20+8; this
0x18002467f  call    ?Initialize@DriverRecoveryManager@@QEAAJXZ; DriverRecoveryManager::Initialize(void)
0x180024684  mov     ebx, eax
0x180024686  test    eax, eax
0x180024688  jns     short loc_180024694
0x18002468a  mov     edx, 0CAh
0x18002468f  jmp     loc_18002473A
0x180024694  mov     rdi, qword ptr cs:xmmword_180059EC0
0x18002469b  lea     rax, [rsp+0A8h+var_78]
0x1800246a0  mov     [rsp+0A8h+arg_0], rax
0x1800246a8  lea     rdx, xmmword_180059F10
0x1800246af  lea     rcx, [rsp+0A8h+var_78]
0x1800246b4  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x1800246b9  mov     rbx, rax
0x1800246bc  lea     rdx, unk_180059ED0
0x1800246c3  lea     rcx, [rsp+0A8h+var_58]
0x1800246c8  call    ??0?$function@$$A6AXW4SchedulerEvent@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (SchedulerEvent)>::function<void (SchedulerEvent)>(std::function<void (SchedulerEvent)> const &)
0x1800246cd  nop
0x1800246ce  mov     r8, rbx
0x1800246d1  mov     rdx, rax
0x1800246d4  mov     rcx, rdi
0x1800246d7  call    ?Initialize@JobScheduler@@QEAAJV?$function@$$A6AXW4SchedulerEvent@@@Z@std@@V?$shared_ptr@VContainerManager@@@3@KK@Z; JobScheduler::Initialize(std::function<void (SchedulerEvent)>,std::shared_ptr<ContainerManager>,ulong,ulong)
0x1800246dc  mov     ebx, eax
0x1800246de  test    eax, eax
0x1800246e0  jns     short loc_1800246E9
0x1800246e2  mov     edx, 0CEh
0x1800246e7  jmp     short loc_18002473A
0x1800246e9  mov     eax, cs:dword_180059E30
0x1800246ef  cmp     eax, 3
0x1800246f2  jz      short loc_18002471A
0x1800246f4  lea     rdx, qword_18005A018; unsigned __int64 *
0x1800246fb  mov     rcx, qword ptr cs:xmmword_180059F20; this
0x180024702  call    ?Initialize@EventScan@@QEAAJPEA_K@Z; EventScan::Initialize(unsigned __int64 *)
0x180024707  mov     ebx, eax
0x180024709  test    eax, eax
0x18002470b  jns     short loc_180024714
0x18002470d  mov     edx, 0D5h
0x180024712  jmp     short loc_18002473A
0x180024714  mov     eax, cs:dword_180059E30
0x18002471a  dec     eax
0x18002471c  test    eax, 0FFFFFFFDh
0x180024721  jz      short loc_180024763
0x180024723  mov     rcx, qword ptr cs:xmmword_180059EC0; this
0x18002472a  call    ?Start@JobScheduler@@QEAAJXZ; JobScheduler::Start(void)
0x18002472f  mov     ebx, eax
0x180024731  test    eax, eax
0x180024733  jns     short loc_180024763
0x180024735  mov     edx, 0DBh; void *
0x18002473a  mov     r9d, eax; char *
0x18002473d  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180024744  mov     rcx, [rsp+0A8h]; this
0x18002474c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024751  nop
0x180024752  lea     rcx, stru_180059EA8; SRWLock
0x180024759  call    cs:__imp_ReleaseSRWLockExclusive
0x18002475f  mov     eax, ebx
0x180024761  jmp     short loc_1800247BB
0x180024763  lea     rcx, stru_180059EA8; SRWLock
0x18002476a  call    cs:__imp_ReleaseSRWLockExclusive
0x180024770  call    ?DsmRpcStartup@@YAJXZ; DsmRpcStartup(void)
0x180024775  mov     ebx, eax
0x180024777  test    eax, eax
0x180024779  js      short loc_180024788
0x18002477b  mov     edx, 1
0x180024780  mov     rcx, r12
0x180024783  call    ?_SetCoreEvent@CDsmCore@@AEAAXW4CORE_EVENT@1@@Z; CDsmCore::_SetCoreEvent(CDsmCore::CORE_EVENT)
0x180024788  mov     rcx, cs:WPP_GLOBAL_Control
0x18002478f  cmp     rcx, r13
0x180024792  jz      short loc_18002475F
0x180024794  test    byte ptr [rcx+1Ch], 1
0x180024798  jz      short loc_18002475F
0x18002479a  mov     edx, 0Fh
0x18002479f  mov     r9d, ebx
0x1800247a2  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x1800247a9  mov     rcx, [rcx+10h]
0x1800247ad  call    WPP_SF_d
0x1800247b2  jmp     short loc_18002475F
0x1800247b4  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x1800247bb  mov     rbx, [rsp+0A8h+arg_10]
0x1800247c3  add     rsp, 90h
0x1800247ca  pop     r13
0x1800247cc  pop     r12
0x1800247ce  pop     rdi
0x1800247cf  retn
```
