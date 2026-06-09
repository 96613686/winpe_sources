# AgentManager::DeallocateAgentUser_DropsLock(AgentUser *,Windows::AI::IsolationEnvironment::IsolationProvisionLostReason,bool)

- ea: `0x180037470`
- end: `0x180037833`
- name: `?DeallocateAgentUser_DropsLock@AgentManager@@SAXPEAVAgentUser@@W4IsolationProvisionLostReason@IsolationEnvironment@AI@Windows@@_N@Z`
- size: `963`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023fb0`
- `0x180037924`
- `0x18003cd20`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18000e4bc`
- `0x18001045c`
- `0x18001f998`
- `0x180036f34`
- `0x180037470`
- `0x18003c324`
- `0x18003c4a4`
- `0x18003c79c`
- `0x18003cc34`
- `0x18003d158`
- `0x18004bd10`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800376a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800376a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003768a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800376d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003768a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800376d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800376a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800376a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037698`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037698`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180037662`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180037662`

## string_xrefs

- `0x1800375c9`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentmanager.cpp`
- `0x18003772b`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentmanager.cpp`
- `0x180037763`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentmanager.cpp`
- `0x1800377fd`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentmanager.cpp`
- `0x18003780f`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentmanager.cpp`
- `0x180037821`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AgentManager::DeallocateAgentUser_DropsLock(__int64 a1, unsigned int a2, char a3, const char *a4)
{
  _QWORD *i; // rbx
  const char *v8; // r9
  AgentUser *v9; // r14
  volatile signed __int32 *v10; // rsi
  __int64 v11; // r15
  __int64 *j; // rdi
  volatile signed __int32 *v13; // rbx
  int AppConnection; // eax
  AgentUser *v15; // r15
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  struct Windows::AI::IsolationEnvironment::IsolationEnvironment *v18; // rdx
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  struct _TP_TIMER *v20; // r12
  DWORD LastError; // edi
  AgentUser *v22; // rax
  volatile signed __int32 *v23; // rax
  int v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  __int64 v28; // [rsp+20h] [rbp-49h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-41h] BYREF
  AgentUser *v30; // [rsp+30h] [rbp-39h]
  volatile signed __int32 *v31; // [rsp+38h] [rbp-31h]
  char *v32[4]; // [rsp+40h] [rbp-29h] BYREF
  char *v33[4]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( !a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x6E,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentmanager.cpp",
      a4);
  for ( i = (_QWORD *)AgentManager::s_agentUsersInUse; i != (_QWORD *)qword_1800B9348 && *i != a1; i += 2 )
    ;
  if ( i == (_QWORD *)qword_1800B9348 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x76,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentmanager.cpp",
      a4);
  std::wstring::wstring((__int64)v33, *(_QWORD *)(a1 + 48) + 80LL);
  std::wstring::wstring((__int64)v32, a1 + 248);
  v9 = (AgentUser *)*i;
  v30 = (AgentUser *)*i;
  v10 = (volatile signed __int32 *)i[1];
  v31 = v10;
  *i = 0;
  i[1] = 0;
  v11 = qword_1800B9348;
  for ( j = i + 2; j != (__int64 *)v11; j += 2 )
  {
    std::shared_ptr<AppIdentity>::operator=(i, j);
    i += 2;
  }
  v13 = *(volatile signed __int32 **)(qword_1800B9348 - 8);
  if ( v13 )
  {
    if ( !_InterlockedDecrement(v13 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( !_InterlockedDecrement(v13 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  qword_1800B9348 -= 16;
  if ( AgentManager::s_cachedAgentNotInUse == v9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x82,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentmanager.cpp",
      v8);
  v28 = 0;
  AppConnection = AgentUser::GetAppConnection(v9, &v28);
  if ( AppConnection < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentmanager.cpp",
      (const char *)(unsigned int)AppConnection,
      v28);
  if ( !a3 && *((_DWORD *)v9 + 60) == 1 )
  {
    v15 = v9;
    AgentUser::CleanupProxyAndClientConnections(v9);
    v16 = *((_QWORD *)v9 + 9);
    *((_QWORD *)v9 + 9) = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v17 = (_QWORD *)((char *)v9 + 248);
    *((_QWORD *)v9 + 33) = 0;
    if ( *((_QWORD *)v9 + 34) > 7u )
      v17 = (_QWORD *)*v17;
    *(_WORD *)v17 = 0;
    v18 = (struct Windows::AI::IsolationEnvironment::IsolationEnvironment *)*((_QWORD *)v9 + 8);
    if ( v18 )
      AgentUser::UnbindEnvironment_DropsLock(v9, v18);
    ThreadpoolTimer = AgentManager::s_cleanupTimer;
    if ( AgentManager::s_cleanupTimer )
      goto LABEL_29;
    ThreadpoolTimer = CreateThreadpoolTimer(AgentManager::CleanupTimerCallback_NoLock, 0, 0);
    v20 = AgentManager::s_cleanupTimer;
    if ( AgentManager::s_cleanupTimer )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v20, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v20, 1);
      CloseThreadpoolTimer(v20);
      SetLastError(LastError);
    }
    AgentManager::s_cleanupTimer = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
LABEL_29:
      pftDueTime = (struct _FILETIME)-9000000000LL;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      v22 = AgentManager::s_cachedAgentNotInUse;
      AgentManager::s_cachedAgentNotInUse = v9;
      v9 = v22;
      v30 = v22;
      v23 = (volatile signed __int32 *)*(&AgentManager::s_cachedAgentNotInUse + 1);
      *(&AgentManager::s_cachedAgentNotInUse + 1) = (AgentUser *)v10;
      v10 = v23;
      v31 = v23;
      AgentUser::MarkCached(v15, 1);
    }
  }
  if ( v9 )
  {
    v24 = AgentUser::Destroy_DropsLock(v9);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentmanager.cpp",
        (const char *)(unsigned int)v24,
        v28);
  }
  v25 = v28;
  if ( v28 )
  {
    v26 = Windows::AI::IsolationEnvironment::AppConnection::FireProvisionLostEvent_DropsLock(v28, v33, v32, a2);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentmanager.cpp",
        (const char *)(unsigned int)v26,
        v28);
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  std::wstring::~wstring(v32);
  return std::wstring::~wstring(v33);
}

```

## disassembly

```asm
0x180037470  mov     [rsp-8+arg_10], rbx
0x180037475  push    rbp
0x180037476  push    rsi
0x180037477  push    rdi
0x180037478  push    r12
0x18003747a  push    r13
0x18003747c  push    r14
0x18003747e  push    r15
0x180037480  lea     rbp, [rsp-27h]
0x180037485  sub     rsp, 90h
0x18003748c  mov     rax, cs:__security_cookie
0x180037493  xor     rax, rsp
0x180037496  mov     [rbp+57h+var_40], rax
0x18003749a  mov     r12b, r8b
0x18003749d  mov     r13d, edx
0x1800374a0  mov     rdi, rcx
0x1800374a3  mov     rcx, [rbp+5Fh]; this
0x1800374a7  test    rdi, rdi
0x1800374aa  jz      loc_18003780F
0x1800374b0  mov     rbx, cs:?s_agentUsersInUse@AgentManager@@0V?$vector@V?$shared_ptr@VAgentUser@@@std@@V?$allocator@V?$shared_ptr@VAgentUser@@@std@@@2@@std@@A; std::vector<std::shared_ptr<AgentUser>> AgentManager::s_agentUsersInUse
0x1800374b7  mov     rax, cs:qword_1800B9348
0x1800374be  jmp     short loc_1800374C9
0x1800374c0  cmp     [rbx], rdi
0x1800374c3  jz      short loc_1800374CE
0x1800374c5  add     rbx, 10h
0x1800374c9  cmp     rbx, rax
0x1800374cc  jnz     short loc_1800374C0
0x1800374ce  cmp     rbx, rax
0x1800374d1  setz    al
0x1800374d4  mov     rcx, [rbp+5Fh]; this
0x1800374d8  test    al, al
0x1800374da  jnz     loc_180037821
0x1800374e0  mov     rdx, [rdi+30h]
0x1800374e4  add     rdx, 50h ; 'P'
0x1800374e8  lea     rcx, [rbp+57h+var_60]
0x1800374ec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800374f1  nop
0x1800374f2  lea     rdx, [rdi+0F8h]
0x1800374f9  lea     rcx, [rbp+57h+var_80]
0x1800374fd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180037502  nop
0x180037503  mov     r14, [rbx]
0x180037506  mov     [rbp+57h+var_90], r14
0x18003750a  mov     rsi, [rbx+8]
0x18003750e  mov     [rbp+57h+var_88], rsi
0x180037512  mov     qword ptr [rbx], 0
0x180037519  mov     qword ptr [rbx+8], 0
0x180037521  mov     r15, cs:qword_1800B9348
0x180037528  lea     rdi, [rbx+10h]
0x18003752c  jmp     short loc_180037541
0x18003752e  mov     rdx, rdi
0x180037531  mov     rcx, rbx
0x180037534  call    ??4?$shared_ptr@VAppIdentity@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<AppIdentity>::operator=(std::shared_ptr<AppIdentity> &&)
0x180037539  add     rbx, 10h
0x18003753d  add     rdi, 10h
0x180037541  cmp     rdi, r15
0x180037544  jnz     short loc_18003752E
0x180037546  mov     rax, cs:qword_1800B9348
0x18003754d  mov     rbx, [rax-8]
0x180037551  or      edi, 0FFFFFFFFh
0x180037554  test    rbx, rbx
0x180037557  jz      short loc_18003758C
0x180037559  mov     eax, edi
0x18003755b  lock xadd [rbx+8], eax
0x180037560  add     eax, edi
0x180037562  jnz     short loc_18003758C
0x180037564  mov     rax, [rbx]
0x180037567  mov     rcx, rbx
0x18003756a  mov     rax, [rax]
0x18003756d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037572  mov     eax, edi
0x180037574  lock xadd [rbx+0Ch], eax
0x180037579  add     eax, edi
0x18003757b  jnz     short loc_18003758C
0x18003757d  mov     rax, [rbx]
0x180037580  mov     rcx, rbx
0x180037583  mov     rax, [rax+8]
0x180037587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003758c  sub     cs:qword_1800B9348, 10h
0x180037594  cmp     qword ptr cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A, r14; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x18003759b  setz    al
0x18003759e  mov     rcx, [rbp+5Fh]; this
0x1800375a2  test    al, al
0x1800375a4  jnz     loc_1800377FD
0x1800375aa  mov     [rbp+57h+var_A0], 0
0x1800375b2  lea     rdx, [rbp+57h+var_A0]
0x1800375b6  mov     rcx, r14
0x1800375b9  call    ?GetAppConnection@AgentUser@@QEAAJAEAV?$com_ptr_t@VAppConnection@IsolationEnvironment@AI@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; AgentUser::GetAppConnection(wil::com_ptr_t<Windows::AI::IsolationEnvironment::AppConnection,wil::err_returncode_policy> &)
0x1800375be  mov     rcx, [rbp+5Fh]; this
0x1800375c2  test    eax, eax
0x1800375c4  jns     short loc_1800375DA
0x1800375c6  mov     r9d, eax; char *
0x1800375c9  lea     r8, aOnecoreuapWind_11; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800375d0  mov     edx, 87h; void *
0x1800375d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800375da  test    r12b, r12b
0x1800375dd  jnz     loc_180037713
0x1800375e3  cmp     dword ptr [r14+0F0h], 1
0x1800375eb  jnz     loc_180037713
0x1800375f1  mov     r15, r14
0x1800375f4  mov     rcx, r14; this
0x1800375f7  call    ?CleanupProxyAndClientConnections@AgentUser@@AEAAXXZ; AgentUser::CleanupProxyAndClientConnections(void)
0x1800375fc  nop
0x1800375fd  mov     rcx, [r14+48h]
0x180037601  mov     qword ptr [r14+48h], 0
0x180037609  test    rcx, rcx
0x18003760c  jz      short loc_18003761B
0x18003760e  mov     rax, [rcx]
0x180037611  mov     rax, [rax+10h]
0x180037615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003761a  nop
0x18003761b  lea     rcx, [r14+0F8h]
0x180037622  mov     qword ptr [rcx+10h], 0
0x18003762a  cmp     qword ptr [rcx+18h], 7
0x18003762f  jbe     short loc_180037634
0x180037631  mov     rcx, [rcx]
0x180037634  xor     eax, eax
0x180037636  mov     [rcx], ax
0x180037639  mov     rdx, [r14+40h]; struct Windows::AI::IsolationEnvironment::IsolationEnvironment *
0x18003763d  test    rdx, rdx
0x180037640  jz      short loc_18003764A
0x180037642  mov     rcx, r15; this
0x180037645  call    ?UnbindEnvironment_DropsLock@AgentUser@@QEAAXPEAVIsolationEnvironment@2AI@Windows@@@Z; AgentUser::UnbindEnvironment_DropsLock(Windows::AI::IsolationEnvironment::IsolationEnvironment *)
0x18003764a  mov     rbx, cs:?s_cleanupTimer@AgentManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager::s_cleanupTimer
0x180037651  test    rbx, rbx
0x180037654  jnz     short loc_1800376BE
0x180037656  xor     r8d, r8d; pcbe
0x180037659  xor     edx, edx; pv
0x18003765b  lea     rcx, ?CleanupTimerCallback_NoLock@AgentManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180037662  call    cs:__imp_CreateThreadpoolTimer
0x180037668  mov     rbx, rax
0x18003766b  mov     r12, cs:?s_cleanupTimer@AgentManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager::s_cleanupTimer
0x180037672  test    r12, r12
0x180037675  jz      short loc_1800376B2
0x180037677  call    cs:__imp_GetLastError
0x18003767d  mov     edi, eax
0x18003767f  xor     r9d, r9d; msWindowLength
0x180037682  xor     r8d, r8d; msPeriod
0x180037685  xor     edx, edx; pftDueTime
0x180037687  mov     rcx, r12; pti
0x18003768a  call    cs:__imp_SetThreadpoolTimer
0x180037690  mov     edx, 1; fCancelPendingCallbacks
0x180037695  mov     rcx, r12; pti
0x180037698  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003769e  mov     rcx, r12; pti
0x1800376a1  call    cs:__imp_CloseThreadpoolTimer
0x1800376a7  mov     ecx, edi; dwErrCode
0x1800376a9  call    cs:__imp_SetLastError
0x1800376af  or      edi, 0FFFFFFFFh
0x1800376b2  mov     cs:?s_cleanupTimer@AgentManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rbx; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager::s_cleanupTimer
0x1800376b9  test    rbx, rbx
0x1800376bc  jz      short loc_180037713
0x1800376be  mov     rax, 0FFFFFFFDE78EE600h
0x1800376c8  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x1800376cc  xor     r9d, r9d; msWindowLength
0x1800376cf  xor     r8d, r8d; msPeriod
0x1800376d2  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x1800376d6  mov     rcx, rbx; pti
0x1800376d9  call    cs:__imp_SetThreadpoolTimer
0x1800376df  mov     rax, qword ptr cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x1800376e6  mov     qword ptr cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A, r14; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x1800376ed  mov     r14, rax
0x1800376f0  mov     [rbp+57h+var_90], rax
0x1800376f4  mov     rax, qword ptr cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A+8; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x1800376fb  mov     qword ptr cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A+8, rsi; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x180037702  mov     rsi, rax
0x180037705  mov     [rbp+57h+var_88], rax
0x180037709  mov     dl, 1; bool
0x18003770b  mov     rcx, r15; this
0x18003770e  call    ?MarkCached@AgentUser@@QEAAX_N@Z; AgentUser::MarkCached(bool)
0x180037713  test    r14, r14
0x180037716  jz      short loc_18003773C
0x180037718  mov     rcx, r14; this
0x18003771b  call    ?Destroy_DropsLock@AgentUser@@QEAAJXZ; AgentUser::Destroy_DropsLock(void)
0x180037720  mov     rcx, [rbp+5Fh]; this
0x180037724  test    eax, eax
0x180037726  jns     short loc_18003773C
0x180037728  mov     r9d, eax; char *
0x18003772b  lea     r8, aOnecoreuapWind_11; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180037732  mov     edx, 0C5h; void *
0x180037737  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003773c  mov     rbx, [rbp+57h+var_A0]
0x180037740  test    rbx, rbx
0x180037743  jz      short loc_180037775
0x180037745  mov     r9d, r13d
0x180037748  lea     r8, [rbp+57h+var_80]
0x18003774c  lea     rdx, [rbp+57h+var_60]
0x180037750  mov     rcx, rbx
0x180037753  call    ?FireProvisionLostEvent_DropsLock@AppConnection@IsolationEnvironment@AI@Windows@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0W4IsolationProvisionLostReason@234@@Z; Windows::AI::IsolationEnvironment::AppConnection::FireProvisionLostEvent_DropsLock(std::wstring const &,std::wstring const &,Windows::AI::IsolationEnvironment::IsolationProvisionLostReason)
0x180037758  mov     rcx, [rbp+5Fh]; this
0x18003775c  test    eax, eax
0x18003775e  jns     short loc_180037775
0x180037760  mov     r9d, eax; char *
0x180037763  lea     r8, aOnecoreuapWind_11; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003776a  mov     edx, 0D1h; void *
0x18003776f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037774  nop
0x180037775  test    rbx, rbx
0x180037778  jz      short loc_18003778A
0x18003777a  mov     rax, [rbx]
0x18003777d  mov     rcx, rbx
0x180037780  mov     rax, [rax+10h]
0x180037784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037789  nop
0x18003778a  test    rsi, rsi
0x18003778d  jz      short loc_1800377C3
0x18003778f  mov     eax, edi
0x180037791  lock xadd [rsi+8], eax
0x180037796  add     eax, edi
0x180037798  jnz     short loc_1800377C3
0x18003779a  mov     rax, [rsi]
0x18003779d  mov     rcx, rsi
0x1800377a0  mov     rax, [rax]
0x1800377a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377a8  mov     eax, edi
0x1800377aa  lock xadd [rsi+0Ch], eax
0x1800377af  add     eax, edi
0x1800377b1  jnz     short loc_1800377C3
0x1800377b3  mov     rax, [rsi]
0x1800377b6  mov     rcx, rsi
0x1800377b9  mov     rax, [rax+8]
0x1800377bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377c2  nop
0x1800377c3  lea     rcx, [rbp+57h+var_80]
0x1800377c7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800377cc  nop
0x1800377cd  lea     rcx, [rbp+57h+var_60]
0x1800377d1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800377d6  mov     rcx, [rbp+57h+var_40]
0x1800377da  xor     rcx, rsp; StackCookie
0x1800377dd  call    __security_check_cookie
0x1800377e2  mov     rbx, [rsp+0C0h+arg_10]
0x1800377ea  add     rsp, 90h
0x1800377f1  pop     r15
0x1800377f3  pop     r14
0x1800377f5  pop     r13
0x1800377f7  pop     r12
0x1800377f9  pop     rdi
0x1800377fa  pop     rsi
0x1800377fb  pop     rbp
0x1800377fc  retn
0x1800377fd  lea     r8, aOnecoreuapWind_11; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180037804  mov     edx, 82h; void *
0x180037809  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003780f  lea     r8, aOnecoreuapWind_11; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180037816  mov     edx, 6Eh ; 'n'; void *
0x18003781b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180037821  lea     r8, aOnecoreuapWind_11; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180037828  mov     edx, 76h ; 'v'; void *
0x18003782d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
