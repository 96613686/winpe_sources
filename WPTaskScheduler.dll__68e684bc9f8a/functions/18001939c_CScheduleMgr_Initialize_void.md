# CScheduleMgr::Initialize(void)

- ea: `0x18001939c`
- end: `0x18001953e`
- name: `?Initialize@CScheduleMgr@@QEAAJXZ`
- size: `418`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180015544`

## callees

- `0x180005b10`
- `0x18000c450`
- `0x18000e970`
- `0x18000ea40`
- `0x18000eeb0`
- `0x180010094`
- `0x18001939c`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800194bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800194bc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800194a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800194a2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800194b3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800194b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800193bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800193bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001951e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001951e`
- `ntdll!RtlQueryWnfStateData` at `0x180019455`
- `ntdll!RtlQueryWnfStateData` at `0x180019455`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180019487`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180019487`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::Initialize(CScheduleMgr *this)
{
  TaskStore *v1; // rax
  __int64 v2; // rcx
  __int64 v3; // r8
  unsigned int v4; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v6; // rdi
  unsigned int v8; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v9[16]; // [rsp+48h] [rbp-20h] BYREF

  EnterCriticalSection(&CriticalSection);
  qword_180030EE8 = (__int64)&CScheduleMgr::ExpiredScheduleList;
  CScheduleMgr::ExpiredScheduleList = (struct CSchedule *)&CScheduleMgr::ExpiredScheduleList;
  qword_180030A98 = (__int64)&g_ScheduleMgr;
  g_ScheduleMgr = &g_ScheduleMgr;
  std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(&xmmword_180030BE0);
  v1 = (TaskStore *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = 0;
  if ( v1 )
  {
    *(_QWORD *)v1 = &g_ScheduleMgr;
    qword_180030AC8 = v1;
    TimeInfo::SetTimeNow(&TimeZoneInformation);
    TimeInfo::LogTimeETW((TimeInfo *)&TimeZoneInformation);
    v8 = 0;
    RtlQueryWnfStateData(&v8, WNF_TB_SYSTEM_TIME_CHANGED, CScheduleMgr::wnfQueryCallback, 0, 0);
    if ( (int)RtlSubscribeWnfStateChangeNotification(
                &qword_180030BF0,
                WNF_TB_SYSTEM_TIME_CHANGED,
                v8,
                CScheduleMgr::BaseTimeChangeEventCallback,
                0,
                0,
                0,
                0) >= 0
      && (ThreadpoolWork = CreateThreadpoolWork(
                             (PTP_WORK_CALLBACK)CompleteInitializationWorker,
                             &g_ScheduleMgr,
                             &ThreadpoolCallBackEnvironment),
          (v6 = ThreadpoolWork) != 0) )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v6);
    }
    else
    {
      v4 = -2147467259;
    }
  }
  else
  {
    qword_180030AC8 = 0;
    if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 2) != 0 )
      McTemplateU0q_EventWriteTransfer(v2, ObjectCreationError, 1);
    v4 = -2100363005;
  }
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, ServiceInitializePhase1Completed, v3, 1, v9);
  LeaveCriticalSection(&CriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18001939c  mov     [rsp+arg_0], rbx
0x1800193a1  push    rdi
0x1800193a2  sub     rsp, 60h
0x1800193a6  mov     rax, cs:__security_cookie
0x1800193ad  xor     rax, rsp
0x1800193b0  mov     [rsp+68h+var_10], rax
0x1800193b5  lea     rcx, CriticalSection; lpCriticalSection
0x1800193bc  call    cs:__imp_EnterCriticalSection
0x1800193c2  lea     rax, ?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x1800193c9  lea     rdi, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x1800193d0  mov     cs:qword_180030EE8, rax
0x1800193d7  lea     rcx, xmmword_180030BE0
0x1800193de  mov     cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x1800193e5  mov     cs:qword_180030A98, rdi
0x1800193ec  mov     cs:?g_ScheduleMgr@@3VCScheduleMgr@@A, rdi; CScheduleMgr g_ScheduleMgr
0x1800193f3  call    ?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(void)
0x1800193f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800193ff  mov     ecx, 8; unsigned __int64
0x180019404  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019409  xor     ebx, ebx
0x18001940b  test    rax, rax
0x18001940e  jz      loc_1800194CB
0x180019414  mov     [rax], rdi
0x180019417  lea     rcx, TimeZoneInformation; lpTimeZoneInformation
0x18001941e  mov     cs:qword_180030AC8, rax
0x180019425  call    ?SetTimeNow@TimeInfo@@QEAAHXZ; TimeInfo::SetTimeNow(void)
0x18001942a  lea     rcx, TimeZoneInformation; this
0x180019431  call    ?LogTimeETW@TimeInfo@@QEBAXXZ; TimeInfo::LogTimeETW(void)
0x180019436  mov     rdx, cs:WNF_TB_SYSTEM_TIME_CHANGED
0x18001943d  lea     r8, ?wnfQueryCallback@CScheduleMgr@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CScheduleMgr::wnfQueryCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180019444  xor     r9d, r9d
0x180019447  mov     [rsp+68h+var_28], ebx
0x18001944b  lea     rcx, [rsp+68h+var_28]
0x180019450  mov     [rsp+68h+var_48], rbx
0x180019455  call    cs:__imp_RtlQueryWnfStateData
0x18001945b  mov     r8d, [rsp+68h+var_28]
0x180019460  lea     r9, ?BaseTimeChangeEventCallback@CScheduleMgr@@CAXU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CScheduleMgr::BaseTimeChangeEventCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180019467  mov     rdx, cs:WNF_TB_SYSTEM_TIME_CHANGED
0x18001946e  lea     rcx, qword_180030BF0
0x180019475  mov     [rsp+68h+var_30], ebx
0x180019479  mov     [rsp+68h+var_38], ebx
0x18001947d  mov     [rsp+68h+var_40], rbx
0x180019482  mov     [rsp+68h+var_48], rbx
0x180019487  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001948d  test    eax, eax
0x18001948f  js      short loc_1800194C4
0x180019491  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180019498  mov     rdx, rdi; pv
0x18001949b  lea     rcx, ?CompleteInitializationWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800194a2  call    cs:__imp_CreateThreadpoolWork
0x1800194a8  mov     rdi, rax
0x1800194ab  test    rax, rax
0x1800194ae  jz      short loc_1800194C4
0x1800194b0  mov     rcx, rax; pwk
0x1800194b3  call    cs:__imp_SubmitThreadpoolWork
0x1800194b9  mov     rcx, rdi; pwk
0x1800194bc  call    cs:__imp_CloseThreadpoolWork
0x1800194c2  jmp     short loc_1800194F2
0x1800194c4  mov     ebx, 80004005h
0x1800194c9  jmp     short loc_1800194F2
0x1800194cb  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x1800194d2  mov     cs:qword_180030AC8, rbx
0x1800194d9  jz      short loc_1800194ED
0x1800194db  mov     r8d, 1
0x1800194e1  lea     rdx, ObjectCreationError
0x1800194e8  call    McTemplateU0q_EventWriteTransfer
0x1800194ed  mov     ebx, 82CF0103h
0x1800194f2  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 8
0x1800194f9  jz      short loc_180019517
0x1800194fb  lea     rax, [rsp+68h+var_20]
0x180019500  mov     r9d, 1
0x180019506  lea     rdx, ServiceInitializePhase1Completed
0x18001950d  mov     [rsp+68h+var_48], rax
0x180019512  call    McGenEventWrite_EventWriteTransfer
0x180019517  lea     rcx, CriticalSection; lpCriticalSection
0x18001951e  call    cs:__imp_LeaveCriticalSection
0x180019524  mov     eax, ebx
0x180019526  mov     rcx, [rsp+68h+var_10]
0x18001952b  xor     rcx, rsp; StackCookie
0x18001952e  call    __security_check_cookie
0x180019533  mov     rbx, [rsp+68h+arg_0]
0x180019538  add     rsp, 60h
0x18001953c  pop     rdi
0x18001953d  retn
```
