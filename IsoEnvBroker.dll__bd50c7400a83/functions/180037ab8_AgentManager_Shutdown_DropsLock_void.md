# AgentManager::Shutdown_DropsLock(void)

- ea: `0x180037ab8`
- end: `0x180037c5f`
- name: `?Shutdown_DropsLock@AgentManager@@SAXXZ`
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
- `0x180037ab8`
- `0x18003c4a4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ace`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037b00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037b00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180037ae1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180037ae1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180037af8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180037af8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037aef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037aef`

## string_xrefs

- `0x180037b5f`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void AgentManager::Shutdown_DropsLock(void)
{
  struct _TP_TIMER *v0; // rdi
  DWORD LastError; // ebx
  volatile signed __int32 *v2; // rbx
  int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rsi
  volatile signed __int32 *v7; // rbx
  int v8[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v0 = AgentManager::s_cleanupTimer;
  if ( AgentManager::s_cleanupTimer )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v0, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v0, 1);
    CloseThreadpoolTimer(v0);
    SetLastError(LastError);
  }
  AgentManager::s_cleanupTimer = 0;
  if ( AgentManager::s_cachedAgentNotInUse )
  {
    *(__m128i *)v8 = _mm_loadu_si128((const __m128i *)&AgentManager::s_cachedAgentNotInUse);
    v2 = (volatile signed __int32 *)_mm_srli_si128(*(__m128i *)v8, 8).m128i_u64[0];
    *(_OWORD *)&AgentManager::s_cachedAgentNotInUse = 0;
    v3 = AgentUser::Destroy_DropsLock(*(AgentUser **)v8);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentmanager.cpp",
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
  v4 = qword_1800B9350;
  qword_1800B9350 = 0;
  v5 = qword_1800B9348;
  qword_1800B9348 = 0;
  v6 = AgentManager::s_agentUsersInUse;
  AgentManager::s_agentUsersInUse = 0;
  *(_QWORD *)v8 = v6;
  *(_QWORD *)&v8[2] = v5;
  v9 = v4;
  while ( v6 != v5 )
  {
    AgentUser::Destroy_DropsLock(*(AgentUser **)(v5 - 16));
    v5 -= 16;
    v7 = *(volatile signed __int32 **)(v5 + 8);
    if ( v7 && _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    *(_QWORD *)&v8[2] = v5;
  }
  std::vector<std::shared_ptr<OwningUser2>>::~vector<std::shared_ptr<OwningUser2>>(v8);
}

```

## disassembly

```asm
0x180037ab8  push    rbx
0x180037aba  push    rsi
0x180037abb  push    rdi
0x180037abc  push    r14
0x180037abe  sub     rsp, 48h
0x180037ac2  mov     rdi, cs:?s_cleanupTimer@AgentManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager::s_cleanupTimer
0x180037ac9  test    rdi, rdi
0x180037acc  jz      short loc_180037B06
0x180037ace  call    cs:__imp_GetLastError
0x180037ad4  mov     ebx, eax
0x180037ad6  xor     r9d, r9d; msWindowLength
0x180037ad9  xor     r8d, r8d; msPeriod
0x180037adc  xor     edx, edx; pftDueTime
0x180037ade  mov     rcx, rdi; pti
0x180037ae1  call    cs:__imp_SetThreadpoolTimer
0x180037ae7  mov     edx, 1; fCancelPendingCallbacks
0x180037aec  mov     rcx, rdi; pti
0x180037aef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180037af5  mov     rcx, rdi; pti
0x180037af8  call    cs:__imp_CloseThreadpoolTimer
0x180037afe  mov     ecx, ebx; dwErrCode
0x180037b00  call    cs:__imp_SetLastError
0x180037b06  mov     cs:?s_cleanupTimer@AgentManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> AgentManager::s_cleanupTimer
0x180037b11  or      r14d, 0FFFFFFFFh
0x180037b15  cmp     qword ptr cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A, 0; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x180037b1d  jz      loc_180037BAD
0x180037b23  movdqu  xmm2, cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x180037b2b  movups  xmmword ptr [rsp+68h+var_48], xmm2; int
0x180037b30  movdqa  xmm0, xmm2
0x180037b34  psrldq  xmm0, 8
0x180037b39  movq    rbx, xmm0
0x180037b3e  xorps   xmm1, xmm1
0x180037b41  movdqu  cs:?s_cachedAgentNotInUse@AgentManager@@0V?$shared_ptr@VAgentUser@@@std@@A, xmm1; std::shared_ptr<AgentUser> AgentManager::s_cachedAgentNotInUse
0x180037b49  movq    rcx, xmm2; this
0x180037b4e  call    ?Destroy_DropsLock@AgentUser@@QEAAJXZ; AgentUser::Destroy_DropsLock(void)
0x180037b53  mov     rcx, [rsp+68h]; this
0x180037b58  test    eax, eax
0x180037b5a  jns     short loc_180037B71
0x180037b5c  mov     r9d, eax; char *
0x180037b5f  lea     r8, aOnecoreuapWind_11; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180037b66  mov     edx, 108h; void *
0x180037b6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037b70  nop
0x180037b71  test    rbx, rbx
0x180037b74  jz      short loc_180037BAD
0x180037b76  mov     eax, r14d
0x180037b79  lock xadd [rbx+8], eax
0x180037b7e  add     eax, r14d
0x180037b81  jnz     short loc_180037BAD
0x180037b83  mov     rax, [rbx]
0x180037b86  mov     rcx, rbx
0x180037b89  mov     rax, [rax]
0x180037b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b91  mov     eax, r14d
0x180037b94  lock xadd [rbx+0Ch], eax
0x180037b99  add     eax, r14d
0x180037b9c  jnz     short loc_180037BAD
0x180037b9e  mov     rax, [rbx]
0x180037ba1  mov     rcx, rbx
0x180037ba4  mov     rax, [rax+8]
0x180037ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bad  mov     rax, cs:qword_1800B9350
0x180037bb4  mov     cs:qword_1800B9350, 0
0x180037bbf  mov     rdi, cs:qword_1800B9348
0x180037bc6  mov     cs:qword_1800B9348, 0
0x180037bd1  mov     rsi, cs:?s_agentUsersInUse@AgentManager@@0V?$vector@V?$shared_ptr@VAgentUser@@@std@@V?$allocator@V?$shared_ptr@VAgentUser@@@std@@@2@@std@@A; std::vector<std::shared_ptr<AgentUser>> AgentManager::s_agentUsersInUse
0x180037bd8  mov     cs:?s_agentUsersInUse@AgentManager@@0V?$vector@V?$shared_ptr@VAgentUser@@@std@@V?$allocator@V?$shared_ptr@VAgentUser@@@std@@@2@@std@@A, 0; std::vector<std::shared_ptr<AgentUser>> AgentManager::s_agentUsersInUse
0x180037be3  mov     qword ptr [rsp+68h+var_48], rsi
0x180037be8  mov     qword ptr [rsp+68h+var_48+8], rdi
0x180037bed  mov     [rsp+68h+var_38], rax
0x180037bf2  cmp     rsi, rdi
0x180037bf5  jz      short loc_180037C4B
0x180037bf7  mov     rcx, [rdi-10h]; this
0x180037bfb  call    ?Destroy_DropsLock@AgentUser@@QEAAJXZ; AgentUser::Destroy_DropsLock(void)
0x180037c00  add     rdi, 0FFFFFFFFFFFFFFF0h
0x180037c04  mov     rbx, [rdi+8]
0x180037c08  test    rbx, rbx
0x180037c0b  jz      short loc_180037C44
0x180037c0d  mov     eax, r14d
0x180037c10  lock xadd [rbx+8], eax
0x180037c15  add     eax, r14d
0x180037c18  jnz     short loc_180037C44
0x180037c1a  mov     rax, [rbx]
0x180037c1d  mov     rcx, rbx
0x180037c20  mov     rax, [rax]
0x180037c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c28  mov     eax, r14d
0x180037c2b  lock xadd [rbx+0Ch], eax
0x180037c30  add     eax, r14d
0x180037c33  jnz     short loc_180037C44
0x180037c35  mov     rax, [rbx]
0x180037c38  mov     rcx, rbx
0x180037c3b  mov     rax, [rax+8]
0x180037c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c44  mov     qword ptr [rsp+68h+var_48+8], rdi
0x180037c49  jmp     short loc_180037BF2
0x180037c4b  lea     rcx, [rsp+68h+var_48]
0x180037c50  call    ??1?$vector@V?$shared_ptr@VOwningUser2@@@std@@V?$allocator@V?$shared_ptr@VOwningUser2@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<OwningUser2>>::~vector<std::shared_ptr<OwningUser2>>(void)
0x180037c55  add     rsp, 48h
0x180037c59  pop     r14
0x180037c5b  pop     rdi
0x180037c5c  pop     rsi
0x180037c5d  pop     rbx
0x180037c5e  retn
```
