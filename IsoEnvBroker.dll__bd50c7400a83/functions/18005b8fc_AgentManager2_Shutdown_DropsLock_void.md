# AgentManager2::Shutdown_DropsLock(void)

- ea: `0x18005b8fc`
- end: `0x18005baa3`
- name: `?Shutdown_DropsLock@AgentManager2@@SAXXZ`
- size: `423`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180061100`

## callees

- `0x18000e4bc`
- `0x180035bfc`
- `0x18005b8fc`
- `0x18005f33c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b912`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b944`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b944`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b925`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b925`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005b93c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005b93c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b933`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b933`

## string_xrefs

- `0x18005b9a3`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentmanager.cpp`

## pseudocode

```c
void AgentManager2::Shutdown_DropsLock(void)
{
  struct _TP_TIMER *v0; // rdi
  DWORD LastError; // ebx
  volatile signed __int32 *v2; // rbx
  int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rdi
  void *v6; // rsi
  volatile signed __int32 *v7; // rbx
  int v8[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v0 = AgentManager2::s_cleanupTimer;
  if ( AgentManager2::s_cleanupTimer )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v0, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v0, 1);
    CloseThreadpoolTimer(v0);
    SetLastError(LastError);
  }
  AgentManager2::s_cleanupTimer = 0;
  if ( AgentManager2::s_cachedAgentNotInUse )
  {
    *(__m128i *)v8 = _mm_loadu_si128((const __m128i *)&AgentManager2::s_cachedAgentNotInUse);
    v2 = (volatile signed __int32 *)_mm_srli_si128(*(__m128i *)v8, 8).m128i_u64[0];
    *(_OWORD *)&AgentManager2::s_cachedAgentNotInUse = 0;
    v3 = AgentUser2::Destroy_DropsLock(*(AgentUser2 **)v8);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentmanager.cpp",
        (const char *)(unsigned int)v3,
        v8[0]);
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
        if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      }
    }
  }
  v4 = qword_1800B9418;
  qword_1800B9418 = 0;
  v5 = qword_1800B9410;
  qword_1800B9410 = 0;
  v6 = AgentManager2::s_agentUsersInUse;
  AgentManager2::s_agentUsersInUse = 0;
  *(_QWORD *)v8 = v6;
  *(_QWORD *)&v8[2] = v5;
  v9 = v4;
  while ( v6 != (void *)v5 )
  {
    AgentUser2::Destroy_DropsLock(*(AgentUser2 **)(v5 - 16));
    v5 -= 16;
    v7 = *(volatile signed __int32 **)(v5 + 8);
    if ( v7 && !_InterlockedDecrement(v7 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( !_InterlockedDecrement(v7 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    *(_QWORD *)&v8[2] = v5;
  }
  std::vector<std::shared_ptr<OwningUser2>>::~vector<std::shared_ptr<OwningUser2>>(v8);
}

```

## disassembly

```asm
0x18005b8fc  push    rbx
0x18005b8fe  push    rsi
0x18005b8ff  push    rdi
0x18005b900  push    r14
0x18005b902  sub     rsp, 48h
0x18005b906  mov     rdi, cs:?s_cleanupTimer@AgentManager2@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager2::s_cleanupTimer
0x18005b90d  test    rdi, rdi
0x18005b910  jz      short loc_18005B94A
0x18005b912  call    cs:__imp_GetLastError
0x18005b918  mov     ebx, eax
0x18005b91a  xor     r9d, r9d; msWindowLength
0x18005b91d  xor     r8d, r8d; msPeriod
0x18005b920  xor     edx, edx; pftDueTime
0x18005b922  mov     rcx, rdi; pti
0x18005b925  call    cs:__imp_SetThreadpoolTimer
0x18005b92b  mov     edx, 1; fCancelPendingCallbacks
0x18005b930  mov     rcx, rdi; pti
0x18005b933  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005b939  mov     rcx, rdi; pti
0x18005b93c  call    cs:__imp_CloseThreadpoolTimer
0x18005b942  mov     ecx, ebx; dwErrCode
0x18005b944  call    cs:__imp_SetLastError
0x18005b94a  mov     cs:?s_cleanupTimer@AgentManager2@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager2::s_cleanupTimer
0x18005b955  or      r14d, 0FFFFFFFFh
0x18005b959  cmp     qword ptr cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A, 0; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b961  jz      loc_18005B9F1
0x18005b967  movdqu  xmm2, cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b96f  movups  xmmword ptr [rsp+68h+var_48], xmm2; int
0x18005b974  movdqa  xmm0, xmm2
0x18005b978  psrldq  xmm0, 8
0x18005b97d  movq    rbx, xmm0
0x18005b982  xorps   xmm1, xmm1
0x18005b985  movdqu  cs:?s_cachedAgentNotInUse@AgentManager2@@0V?$shared_ptr@VAgentUser2@@@std@@A, xmm1; std::shared_ptr<AgentUser2> AgentManager2::s_cachedAgentNotInUse
0x18005b98d  movq    rcx, xmm2; this
0x18005b992  call    ?Destroy_DropsLock@AgentUser2@@QEAAJXZ; AgentUser2::Destroy_DropsLock(void)
0x18005b997  mov     rcx, [rsp+68h]; this
0x18005b99c  test    eax, eax
0x18005b99e  jns     short loc_18005B9B5
0x18005b9a0  mov     r9d, eax; char *
0x18005b9a3  lea     r8, aOnecoreuapWind_10; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005b9aa  mov     edx, 10Ah; void *
0x18005b9af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b9b4  nop
0x18005b9b5  test    rbx, rbx
0x18005b9b8  jz      short loc_18005B9F1
0x18005b9ba  mov     eax, r14d
0x18005b9bd  lock xadd [rbx+8], eax
0x18005b9c2  add     eax, r14d
0x18005b9c5  jnz     short loc_18005B9F1
0x18005b9c7  mov     rax, [rbx]
0x18005b9ca  mov     rcx, rbx
0x18005b9cd  mov     rax, [rax]
0x18005b9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9d5  mov     eax, r14d
0x18005b9d8  lock xadd [rbx+0Ch], eax
0x18005b9dd  add     eax, r14d
0x18005b9e0  jnz     short loc_18005B9F1
0x18005b9e2  mov     rax, [rbx]
0x18005b9e5  mov     rcx, rbx
0x18005b9e8  mov     rax, [rax+8]
0x18005b9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9f1  mov     rax, cs:qword_1800B9418
0x18005b9f8  mov     cs:qword_1800B9418, 0
0x18005ba03  mov     rdi, cs:qword_1800B9410
0x18005ba0a  mov     cs:qword_1800B9410, 0
0x18005ba15  mov     rsi, cs:?s_agentUsersInUse@AgentManager2@@0V?$vector@V?$shared_ptr@VAgentUser2@@@std@@V?$allocator@V?$shared_ptr@VAgentUser2@@@std@@@2@@std@@A; std::vector<std::shared_ptr<AgentUser2>> AgentManager2::s_agentUsersInUse
0x18005ba1c  mov     cs:?s_agentUsersInUse@AgentManager2@@0V?$vector@V?$shared_ptr@VAgentUser2@@@std@@V?$allocator@V?$shared_ptr@VAgentUser2@@@std@@@2@@std@@A, 0; std::vector<std::shared_ptr<AgentUser2>> AgentManager2::s_agentUsersInUse
0x18005ba27  mov     qword ptr [rsp+68h+var_48], rsi
0x18005ba2c  mov     qword ptr [rsp+68h+var_48+8], rdi
0x18005ba31  mov     [rsp+68h+var_38], rax
0x18005ba36  cmp     rsi, rdi
0x18005ba39  jz      short loc_18005BA8F
0x18005ba3b  mov     rcx, [rdi-10h]; this
0x18005ba3f  call    ?Destroy_DropsLock@AgentUser2@@QEAAJXZ; AgentUser2::Destroy_DropsLock(void)
0x18005ba44  add     rdi, 0FFFFFFFFFFFFFFF0h
0x18005ba48  mov     rbx, [rdi+8]
0x18005ba4c  test    rbx, rbx
0x18005ba4f  jz      short loc_18005BA88
0x18005ba51  mov     eax, r14d
0x18005ba54  lock xadd [rbx+8], eax
0x18005ba59  add     eax, r14d
0x18005ba5c  jnz     short loc_18005BA88
0x18005ba5e  mov     rax, [rbx]
0x18005ba61  mov     rcx, rbx
0x18005ba64  mov     rax, [rax]
0x18005ba67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba6c  mov     eax, r14d
0x18005ba6f  lock xadd [rbx+0Ch], eax
0x18005ba74  add     eax, r14d
0x18005ba77  jnz     short loc_18005BA88
0x18005ba79  mov     rax, [rbx]
0x18005ba7c  mov     rcx, rbx
0x18005ba7f  mov     rax, [rax+8]
0x18005ba83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba88  mov     qword ptr [rsp+68h+var_48+8], rdi
0x18005ba8d  jmp     short loc_18005BA36
0x18005ba8f  lea     rcx, [rsp+68h+var_48]
0x18005ba94  call    ??1?$vector@V?$shared_ptr@VOwningUser2@@@std@@V?$allocator@V?$shared_ptr@VOwningUser2@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<OwningUser2>>::~vector<std::shared_ptr<OwningUser2>>(void)
0x18005ba99  add     rsp, 48h
0x18005ba9d  pop     r14
0x18005ba9f  pop     rdi
0x18005baa0  pop     rsi
0x18005baa1  pop     rbx
0x18005baa2  retn
```
