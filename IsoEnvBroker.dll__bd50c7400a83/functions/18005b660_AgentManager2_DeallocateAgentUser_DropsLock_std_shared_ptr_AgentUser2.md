# AgentManager2::DeallocateAgentUser_DropsLock(std::shared_ptr<AgentUser2> &)

- ea: `0x18005b660`
- end: `0x18005b8f5`
- name: `?DeallocateAgentUser_DropsLock@AgentManager2@@SAJAEAV?$shared_ptr@VAgentUser2@@@std@@@Z`
- size: `661`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005efe0`

## callees

- `0x1800075e4`
- `0x18000e4bc`
- `0x180036f34`
- `0x180058d38`
- `0x18005b660`
- `0x18005f33c`
- `0x18005f578`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b7db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b7db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b7bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b80a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b7bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b80a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005b7d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005b7d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b7ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b7ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005b794`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005b794`

## string_xrefs

- `0x18005b85f`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentmanager.cpp`
- `0x18005b8bc`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentmanager.cpp`
- `0x18005b8ce`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentmanager.cpp`
- `0x18005b8e3`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AgentManager2::DeallocateAgentUser_DropsLock(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  AgentUser2 *v4; // r14
  volatile signed __int32 *v5; // rsi
  __int64 v6; // rbx
  _QWORD *i; // rdi
  __int64 *v8; // rbp
  volatile signed __int32 *v9; // rdi
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  struct _TP_TIMER *v11; // rbp
  DWORD LastError; // edi
  AgentUser2 *v13; // rax
  AgentUser2 *v14; // rcx
  volatile signed __int32 *v15; // rax
  int v16; // eax
  int v18[2]; // [rsp+20h] [rbp-48h] BYREF
  volatile signed __int32 *v19; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  v4 = *(AgentUser2 **)a1;
  if ( !*(_QWORD *)a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x80,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentmanager.cpp",
      a4);
  *(_QWORD *)v18 = *(_QWORD *)a1;
  v5 = *(volatile signed __int32 **)(a1 + 8);
  v19 = v5;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v6 = qword_1800B9410;
  for ( i = AgentManager2::s_agentUsersInUse; i != (_QWORD *)qword_1800B9410 && (AgentUser2 *)*i != v4; i += 2 )
    ;
  if ( i == (_QWORD *)qword_1800B9410 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x87,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentmanager.cpp",
      a4);
  v8 = i + 2;
  if ( i + 2 != (_QWORD *)qword_1800B9410 )
  {
    do
    {
      std::shared_ptr<AppIdentity>::operator=(i, v8);
      i += 2;
      v8 += 2;
    }
    while ( v8 != (__int64 *)v6 );
    v6 = qword_1800B9410;
  }
  v9 = *(volatile signed __int32 **)(v6 - 8);
  if ( v9 )
  {
    if ( !_InterlockedDecrement(v9 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( !_InterlockedDecrement(v9 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    v6 = qword_1800B9410;
  }
  qword_1800B9410 = v6 - 16;
  if ( *(_QWORD *)v4 )
    ClientConnection2::NotifyAgentUserUnassigned(*(_QWORD *)v4, v18);
  if ( AgentManager2::s_cachedAgentNotInUse == v4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x95,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentmanager.cpp",
      a4);
  if ( *((_DWORD *)v4 + 58) == 1 )
  {
    ThreadpoolTimer = AgentManager2::s_cleanupTimer;
    if ( AgentManager2::s_cleanupTimer )
      goto LABEL_23;
    ThreadpoolTimer = CreateThreadpoolTimer(AgentManager2::CleanupTimerCallback_NoLock, 0, 0);
    v11 = AgentManager2::s_cleanupTimer;
    if ( AgentManager2::s_cleanupTimer )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v11, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v11, 1);
      CloseThreadpoolTimer(v11);
      SetLastError(LastError);
    }
    AgentManager2::s_cleanupTimer = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
LABEL_23:
      pftDueTime = (struct _FILETIME)-9000000000LL;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      v13 = AgentManager2::s_cachedAgentNotInUse;
      v14 = v4;
      AgentManager2::s_cachedAgentNotInUse = v4;
      v4 = v13;
      *(_QWORD *)v18 = v13;
      v15 = (volatile signed __int32 *)*(&AgentManager2::s_cachedAgentNotInUse + 1);
      *(&AgentManager2::s_cachedAgentNotInUse + 1) = (AgentUser2 *)v5;
      v5 = v15;
      v19 = v15;
      AgentUser2::MarkCached(v14, 1);
    }
  }
  if ( v4 )
  {
    v16 = AgentUser2::Destroy_DropsLock(v4);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentmanager.cpp",
        (const char *)(unsigned int)v16,
        v18[0]);
  }
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005b660  push    rbx
0x18005b662  push    rbp
0x18005b663  push    rsi
0x18005b664  push    rdi
0x18005b665  push    r14
0x18005b667  push    r15
0x18005b669  sub     rsp, 38h
0x18005b66d  mov     r14, [rcx]
0x18005b670  mov     rax, [rsp+68h]
0x18005b675  test    r14, r14
0x18005b678  jz      loc_18005B8CE
0x18005b67e  mov     qword ptr [rsp+68h+var_48], r14
0x18005b683  mov     rsi, [rcx+8]
0x18005b687  mov     [rsp+68h+var_40], rsi
0x18005b68c  mov     qword ptr [rcx], 0
0x18005b693  mov     qword ptr [rcx+8], 0
0x18005b69b  mov     rbx, cs:qword_1800B9410
0x18005b6a2  mov     rdi, cs:?s_agentUsersInUse@AgentManager2@@0V?$vector@V?$shared_ptr@VAgentUser2@@@std@@V?$allocator@V?$shared_ptr@VAgentUser2@@@std@@@2@@std@@A; std::vector<std::shared_ptr<AgentUser2>> AgentManager2::s_agentUsersInUse
0x18005b6a9  jmp     short loc_18005B6B4
0x18005b6ab  cmp     [rdi], r14
0x18005b6ae  jz      short loc_18005B6B9
0x18005b6b0  add     rdi, 10h
0x18005b6b4  cmp     rdi, rbx
0x18005b6b7  jnz     short loc_18005B6AB
0x18005b6b9  mov     rcx, [rsp+68h]; this
0x18005b6be  cmp     rdi, rbx
0x18005b6c1  jz      loc_18005B8E3
0x18005b6c7  lea     rbp, [rdi+10h]
0x18005b6cb  cmp     rbp, rbx
0x18005b6ce  jz      short loc_18005B6EF
0x18005b6d0  mov     rdx, rbp
0x18005b6d3  mov     rcx, rdi
0x18005b6d6  call    ??4?$shared_ptr@VAppIdentity@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<AppIdentity>::operator=(std::shared_ptr<AppIdentity> &&)
0x18005b6db  add     rdi, 10h
0x18005b6df  add     rbp, 10h
0x18005b6e3  cmp     rbp, rbx
0x18005b6e6  jnz     short loc_18005B6D0
0x18005b6e8  mov     rbx, cs:qword_1800B9410
0x18005b6ef  mov     rdi, [rbx-8]
0x18005b6f3  or      r15d, 0FFFFFFFFh
0x18005b6f7  test    rdi, rdi
0x18005b6fa  jz      short loc_18005B73A
0x18005b6fc  mov     eax, r15d
0x18005b6ff  lock xadd [rdi+8], eax
0x18005b704  add     eax, r15d
0x18005b707  jnz     short loc_18005B733
0x18005b709  mov     rax, [rdi]
0x18005b70c  mov     rcx, rdi
0x18005b70f  mov     rax, [rax]
0x18005b712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b717  mov     eax, r15d
0x18005b71a  lock xadd [rdi+0Ch], eax
0x18005b71f  add     eax, r15d
0x18005b722  jnz     short loc_18005B733
0x18005b724  mov     rax, [rdi]
0x18005b727  mov     rcx, rdi
0x18005b72a  mov     rax, [rax+8]
0x18005b72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b733  mov     rbx, cs:qword_1800B9410
0x18005b73a  sub     rbx, 10h
0x18005b73e  mov     cs:qword_1800B9410, rbx
0x18005b745  mov     rcx, [r14]
0x18005b748  test    rcx, rcx
0x18005b74b  jz      short loc_18005B757
0x18005b74d  lea     rdx, [rsp+68h+var_48]
0x18005b752  call    ?NotifyAgentUserUnassigned@ClientConnection2@@QEAAXAEAV?$shared_ptr@VAgentUser2@@@std@@@Z; ClientConnection2::NotifyAgentUserUnassigned(std::shared_ptr<AgentUser2> &)
0x18005b757  cmp     qword ptr cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A, r14; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b75e  setz    al
0x18005b761  mov     rcx, [rsp+68h]; this
0x18005b766  test    al, al
0x18005b768  jnz     loc_18005B8BC
0x18005b76e  cmp     dword ptr [r14+0E8h], 1
0x18005b776  jnz     loc_18005B846
0x18005b77c  mov     rbx, cs:?s_cleanupTimer@AgentManager2@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager2::s_cleanupTimer
0x18005b783  test    rbx, rbx
0x18005b786  jnz     short loc_18005B7ED
0x18005b788  xor     r8d, r8d; pcbe
0x18005b78b  xor     edx, edx; pv
0x18005b78d  lea     rcx, ?CleanupTimerCallback_NoLock@AgentManager2@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005b794  call    cs:__imp_CreateThreadpoolTimer
0x18005b79a  mov     rbx, rax
0x18005b79d  mov     rbp, cs:?s_cleanupTimer@AgentManager2@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager2::s_cleanupTimer
0x18005b7a4  test    rbp, rbp
0x18005b7a7  jz      short loc_18005B7E1
0x18005b7a9  call    cs:__imp_GetLastError
0x18005b7af  mov     edi, eax
0x18005b7b1  xor     r9d, r9d; msWindowLength
0x18005b7b4  xor     r8d, r8d; msPeriod
0x18005b7b7  xor     edx, edx; pftDueTime
0x18005b7b9  mov     rcx, rbp; pti
0x18005b7bc  call    cs:__imp_SetThreadpoolTimer
0x18005b7c2  mov     edx, 1; fCancelPendingCallbacks
0x18005b7c7  mov     rcx, rbp; pti
0x18005b7ca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005b7d0  mov     rcx, rbp; pti
0x18005b7d3  call    cs:__imp_CloseThreadpoolTimer
0x18005b7d9  mov     ecx, edi; dwErrCode
0x18005b7db  call    cs:__imp_SetLastError
0x18005b7e1  mov     cs:?s_cleanupTimer@AgentManager2@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rbx; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager2::s_cleanupTimer
0x18005b7e8  test    rbx, rbx
0x18005b7eb  jz      short loc_18005B846
0x18005b7ed  mov     rax, 0FFFFFFFDE78EE600h
0x18005b7f7  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18005b7fc  xor     r9d, r9d; msWindowLength
0x18005b7ff  xor     r8d, r8d; msPeriod
0x18005b802  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18005b807  mov     rcx, rbx; pti
0x18005b80a  call    cs:__imp_SetThreadpoolTimer
0x18005b810  mov     rax, qword ptr cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b817  mov     rcx, r14; this
0x18005b81a  mov     qword ptr cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A, rcx; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b821  mov     r14, rax
0x18005b824  mov     qword ptr [rsp+68h+var_48], rax; int
0x18005b829  mov     rax, qword ptr cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A+8; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b830  mov     qword ptr cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A+8, rsi; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b837  mov     rsi, rax
0x18005b83a  mov     [rsp+68h+var_40], rax
0x18005b83f  mov     dl, 1; bool
0x18005b841  call    ?MarkCached@AgentUser2@@QEAAX_N@Z; AgentUser2::MarkCached(bool)
0x18005b846  test    r14, r14
0x18005b849  jz      short loc_18005B871
0x18005b84b  mov     rcx, r14; this
0x18005b84e  call    ?Destroy_DropsLock@AgentUser2@@QEAAJXZ; AgentUser2::Destroy_DropsLock(void)
0x18005b853  mov     rcx, [rsp+68h]; this
0x18005b858  test    eax, eax
0x18005b85a  jns     short loc_18005B871
0x18005b85c  mov     r9d, eax; char *
0x18005b85f  lea     r8, aOnecoreuapWind_10; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005b866  mov     edx, 0CFh; void *
0x18005b86b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b870  nop
0x18005b871  test    rsi, rsi
0x18005b874  jz      short loc_18005B8AD
0x18005b876  mov     eax, r15d
0x18005b879  lock xadd [rsi+8], eax
0x18005b87e  add     eax, r15d
0x18005b881  jnz     short loc_18005B8AD
0x18005b883  mov     rax, [rsi]
0x18005b886  mov     rcx, rsi
0x18005b889  mov     rax, [rax]
0x18005b88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b891  mov     eax, r15d
0x18005b894  lock xadd [rsi+0Ch], eax
0x18005b899  add     eax, r15d
0x18005b89c  jnz     short loc_18005B8AD
0x18005b89e  mov     rax, [rsi]
0x18005b8a1  mov     rcx, rsi
0x18005b8a4  mov     rax, [rax+8]
0x18005b8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8ad  xor     eax, eax
0x18005b8af  add     rsp, 38h
0x18005b8b3  pop     r15
0x18005b8b5  pop     r14
0x18005b8b7  pop     rdi
0x18005b8b8  pop     rsi
0x18005b8b9  pop     rbp
0x18005b8ba  pop     rbx
0x18005b8bb  retn
0x18005b8bc  lea     r8, aOnecoreuapWind_10; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005b8c3  mov     edx, 95h; void *
0x18005b8c8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005b8ce  lea     r8, aOnecoreuapWind_10; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005b8d5  mov     edx, 80h; void *
0x18005b8da  mov     rcx, rax; this
0x18005b8dd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005b8e3  lea     r8, aOnecoreuapWind_10; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005b8ea  mov     edx, 87h; void *
0x18005b8ef  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
