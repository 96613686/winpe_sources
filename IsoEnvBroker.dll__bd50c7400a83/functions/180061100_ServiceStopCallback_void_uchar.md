# ServiceStopCallback(void *,uchar)

- ea: `0x180061100`
- end: `0x1800615a0`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `1184`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18000e4bc`
- `0x180011e18`
- `0x1800134e8`
- `0x180023170`
- `0x180036118`
- `0x180037ab8`
- `0x18004f730`
- `0x180056060`
- `0x1800589c8`
- `0x18005b8fc`
- `0x18005c1c8`
- `0x18005f8cc`
- `0x18005fa0c`
- `0x18005facc`
- `0x18005fdf4`
- `0x180061020`
- `0x180061100`
- `0x180061aa0`
- `0x180061bfc`
- `0x180061d58`
- `0x180062914`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061513`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061446`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061410`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800614e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800614e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061408`
- `AUTHZ!AuthzUnregisterSecurityEventSource` at `0x180061433`
- `AUTHZ!AuthzUnregisterSecurityEventSource` at `0x180061433`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180061499`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180061499`

## string_xrefs

- `0x18006158a`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\clientidentity.cpp`
- `0x180061575`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientidentity.cpp`
- `0x180061120`: `ServiceStopActivity`
- `0x180061196`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x1800614cb`: `Service stopped; closing log.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ServiceStopCallback(void *a1)
{
  int v1; // eax
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  ClientConnection2 **v5; // rax
  OwningUser2 **i; // rax
  __int64 v7; // rax
  volatile signed __int32 *v8; // rbx
  OwningUser **j; // rax
  __int64 v10; // rax
  volatile signed __int32 *v11; // rbx
  _QWORD *k; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  volatile signed __int32 *v15; // rbx
  _QWORD *m; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  HKEY v23; // rdi
  DWORD LastError; // ebx
  unsigned int v25; // r8d
  const char *v26; // r9
  RTL_SRWLOCK *v27; // rcx
  const char *v28; // r9
  DWORD v29; // [rsp+20h] [rbp-2E8h] BYREF
  PSRWLOCK SRWLock; // [rsp+28h] [rbp-2E0h] BYREF
  _QWORD v31[42]; // [rsp+30h] [rbp-2D8h] BYREF
  _QWORD v32[42]; // [rsp+180h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v32,
    (__int64)"ServiceStopActivity");
  v32[0] = &IsoEnvBrokerTelemetry::ServiceStopActivity::`vftable';
  IsoEnvBrokerTelemetry::ServiceStopActivity::StartActivity((IsoEnvBrokerTelemetry::ServiceStopActivity *)v32);
  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v31,
    (__int64)"UnregisterObjectsActivity");
  v31[0] = &IsoEnvBrokerTelemetry::UnregisterObjectsActivity::`vftable';
  IsoEnvBrokerTelemetry::UnregisterObjectsActivity::StartActivity((IsoEnvBrokerTelemetry::UnregisterObjectsActivity *)v31);
  try
  {
    v1 = qword_1800B91E8(0);
    if ( v1 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
        (const char *)(unsigned int)v1,
        v29);
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
    checked_srwlock::lock_exclusive(v2, &SRWLock);
    AgentManager2::Shutdown_DropsLock();
    AgentManager::Shutdown_DropsLock();
    v5 = (ClientConnection2 **)qword_1800B93F8;
    while ( ClientConnection2::s_instancesNoRef != v5 )
    {
      ClientConnection2::Destroy(*(v5 - 1));
      v5 = (ClientConnection2 **)(qword_1800B93F8 - 8);
      qword_1800B93F8 -= 8;
    }
    for ( i = (OwningUser2 **)qword_1800B9438; OwningUser2::s_instances != i; qword_1800B9438 = (__int64)i )
    {
      OwningUser2::Destroy(*(i - 2));
      v7 = qword_1800B9438;
      v8 = *(volatile signed __int32 **)(qword_1800B9438 - 8);
      if ( v8 )
      {
        if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
        v7 = qword_1800B9438;
      }
      i = (OwningUser2 **)(v7 - 16);
    }
    for ( j = (OwningUser **)qword_1800B9330; OwningUser::s_instances != j; qword_1800B9330 = (__int64)j )
    {
      OwningUser::Destroy(*(j - 2));
      v10 = qword_1800B9330;
      v11 = *(volatile signed __int32 **)(qword_1800B9330 - 8);
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
        v10 = qword_1800B9330;
      }
      j = (OwningUser **)(v10 - 16);
    }
    for ( k = (_QWORD *)qword_1800B9450; ClientIdentity2::s_instances != k; qword_1800B9450 = (__int64)k )
    {
      v13 = *(k - 2);
      if ( *(_QWORD *)(v13 + 152) != *(_QWORD *)(v13 + 160) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x3A,
          (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientidentity.cpp",
          (const char *)retaddr);
      *(_BYTE *)v13 = 1;
      v14 = qword_1800B9450;
      v15 = *(volatile signed __int32 **)(qword_1800B9450 - 8);
      if ( v15 )
      {
        if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64, wil::details::in1diag3 *))v15)(
            v15,
            v3,
            v4,
            retaddr);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
        v14 = qword_1800B9450;
      }
      k = (_QWORD *)(v14 - 16);
    }
    for ( m = (_QWORD *)qword_1800B9370; ClientIdentity::s_instances != m; qword_1800B9370 = (__int64)m )
    {
      v17 = *(m - 2);
      if ( *(_QWORD *)(v17 + 56) != *(_QWORD *)(v17 + 64) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x38,
          (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\clientidentity.cpp",
          (const char *)retaddr);
      *(_BYTE *)v17 = 1;
      v18 = qword_1800B9370;
      v19 = *(volatile signed __int32 **)(qword_1800B9370 - 8);
      if ( v19 )
      {
        if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64, wil::details::in1diag3 *))v19)(
            v19,
            v3,
            v4,
            retaddr);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
        v18 = qword_1800B9370;
      }
      m = (_QWORD *)(v18 - 16);
    }
    Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock();
    Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock(
      v21,
      v20,
      v22);
    v23 = g_rootKey;
    if ( g_rootKey )
    {
      LastError = GetLastError();
      RegCloseKey(v23);
      SetLastError(LastError);
    }
    g_rootKey = 0;
    if ( byte_1800B9248 )
    {
      if ( AuthzUnregisterSecurityEventSource(0, &g_securityLog) )
      {
        byte_1800B9248 = 0;
      }
      else
      {
        v29 = GetLastError();
        IsoEnvBrokerTelemetry::SecurityLogShutdownFailure<unsigned long>((int *)&v29);
      }
    }
    if ( g_eventLog )
    {
      McGenEventUnregister_EventUnregister();
      g_eventLog = 0;
      Log(4u, L"Uninitialized EventLog");
    }
    *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
    if ( !SetServiceStatus(g_serviceState, &ServiceStatus) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x10B, v25, v26);
    ServiceState::Reset((ServiceState *)&g_serviceState);
    if ( g_hLogFile )
    {
      Log(4u, L"Service stopped; closing log.");
      CloseHandle(g_hLogFile);
      g_hLogFile = 0;
    }
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
    v27 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v27);
    }
    v31[0] = &IsoEnvBrokerTelemetry::UnregisterObjectsActivity::`vftable';
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v31);
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v31);
    v32[0] = &IsoEnvBrokerTelemetry::ServiceStopActivity::`vftable';
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v32);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
      v28);
  }
}

```

## disassembly

```asm
0x180061100  push    rbx
0x180061102  push    rdi
0x180061103  push    r14
0x180061105  push    r15
0x180061107  sub     rsp, 2E8h
0x18006110e  mov     rax, cs:__security_cookie
0x180061115  xor     rax, rsp
0x180061118  mov     [rsp+308h+var_38], rax
0x180061120  lea     rdx, aServicestopact; "ServiceStopActivity"
0x180061127  lea     rcx, [rsp+308h+var_188]
0x18006112f  call    ??0?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180061134  lea     r14, ??_7ServiceStopActivity@IsoEnvBrokerTelemetry@@6B@; const IsoEnvBrokerTelemetry::ServiceStopActivity::`vftable'
0x18006113b  mov     [rsp+308h+var_188], r14
0x180061143  lea     rcx, [rsp+308h+var_188]; this
0x18006114b  call    ?StartActivity@ServiceStopActivity@IsoEnvBrokerTelemetry@@QEAAXXZ; IsoEnvBrokerTelemetry::ServiceStopActivity::StartActivity(void)
0x180061150  nop
0x180061151  lea     rdx, aUnregisterobje; "UnregisterObjectsActivity"
0x180061158  lea     rcx, [rsp+308h+var_2D8]
0x18006115d  call    ??0?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180061162  lea     r15, ??_7UnregisterObjectsActivity@IsoEnvBrokerTelemetry@@6B@; const IsoEnvBrokerTelemetry::UnregisterObjectsActivity::`vftable'
0x180061169  mov     [rsp+308h+var_2D8], r15
0x18006116e  lea     rcx, [rsp+308h+var_2D8]; this
0x180061173  call    ?StartActivity@UnregisterObjectsActivity@IsoEnvBrokerTelemetry@@QEAAXXZ; IsoEnvBrokerTelemetry::UnregisterObjectsActivity::StartActivity(void)
0x180061178  nop
0x180061179  xor     ecx, ecx
0x18006117b  mov     rax, cs:qword_1800B91E8
0x180061182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061187  mov     rcx, [rsp+308h]; this
0x18006118f  test    eax, eax
0x180061191  jns     short loc_1800611A7
0x180061193  mov     r9d, eax; char *
0x180061196  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18006119d  mov     edx, 0E5h; void *
0x1800611a2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800611a7  lea     rcx, [rsp+308h+var_2D8]
0x1800611ac  call    ?Stop@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800611b1  lea     rdx, [rsp+308h+SRWLock]
0x1800611b6  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x1800611bb  nop
0x1800611bc  call    ?Shutdown_DropsLock@AgentManager2@@SAXXZ; AgentManager2::Shutdown_DropsLock(void)
0x1800611c1  call    ?Shutdown_DropsLock@AgentManager@@SAXXZ; AgentManager::Shutdown_DropsLock(void)
0x1800611c6  mov     rax, cs:qword_1800B93F8
0x1800611cd  cmp     cs:?s_instancesNoRef@ClientConnection2@@0V?$vector@PEAVClientConnection2@@V?$allocator@PEAVClientConnection2@@@std@@@std@@A, rax; std::vector<ClientConnection2 *> ClientConnection2::s_instancesNoRef
0x1800611d4  jz      short loc_1800611F3
0x1800611d6  mov     rcx, [rax-8]; this
0x1800611da  call    ?Destroy@ClientConnection2@@QEAAXXZ; ClientConnection2::Destroy(void)
0x1800611df  mov     rax, cs:qword_1800B93F8
0x1800611e6  sub     rax, 8
0x1800611ea  mov     cs:qword_1800B93F8, rax
0x1800611f1  jmp     short loc_1800611CD
0x1800611f3  or      edi, 0FFFFFFFFh
0x1800611f6  mov     rax, cs:qword_1800B9438
0x1800611fd  cmp     cs:?s_instances@OwningUser2@@0V?$vector@V?$shared_ptr@VOwningUser2@@@std@@V?$allocator@V?$shared_ptr@VOwningUser2@@@std@@@2@@std@@A, rax; std::vector<std::shared_ptr<OwningUser2>> OwningUser2::s_instances
0x180061204  jz      short loc_180061266
0x180061206  mov     rcx, [rax-10h]; this
0x18006120a  call    ?Destroy@OwningUser2@@QEAAXXZ; OwningUser2::Destroy(void)
0x18006120f  mov     rax, cs:qword_1800B9438
0x180061216  mov     rbx, [rax-8]
0x18006121a  test    rbx, rbx
0x18006121d  jz      short loc_180061259
0x18006121f  mov     eax, edi
0x180061221  lock xadd [rbx+8], eax
0x180061226  add     eax, edi
0x180061228  jnz     short loc_180061252
0x18006122a  mov     rax, [rbx]
0x18006122d  mov     rcx, rbx
0x180061230  mov     rax, [rax]
0x180061233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061238  mov     eax, edi
0x18006123a  lock xadd [rbx+0Ch], eax
0x18006123f  add     eax, edi
0x180061241  jnz     short loc_180061252
0x180061243  mov     rax, [rbx]
0x180061246  mov     rcx, rbx
0x180061249  mov     rax, [rax+8]
0x18006124d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061252  mov     rax, cs:qword_1800B9438
0x180061259  sub     rax, 10h
0x18006125d  mov     cs:qword_1800B9438, rax
0x180061264  jmp     short loc_1800611FD
0x180061266  mov     rax, cs:qword_1800B9330
0x18006126d  cmp     cs:?s_instances@OwningUser@@0V?$vector@V?$shared_ptr@VOwningUser@@@std@@V?$allocator@V?$shared_ptr@VOwningUser@@@std@@@2@@std@@A, rax; std::vector<std::shared_ptr<OwningUser>> OwningUser::s_instances
0x180061274  jz      short loc_1800612D6
0x180061276  mov     rcx, [rax-10h]; this
0x18006127a  call    ?Destroy@OwningUser@@QEAAXXZ; OwningUser::Destroy(void)
0x18006127f  mov     rax, cs:qword_1800B9330
0x180061286  mov     rbx, [rax-8]
0x18006128a  test    rbx, rbx
0x18006128d  jz      short loc_1800612C9
0x18006128f  mov     eax, edi
0x180061291  lock xadd [rbx+8], eax
0x180061296  add     eax, edi
0x180061298  jnz     short loc_1800612C2
0x18006129a  mov     rax, [rbx]
0x18006129d  mov     rcx, rbx
0x1800612a0  mov     rax, [rax]
0x1800612a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612a8  mov     eax, edi
0x1800612aa  lock xadd [rbx+0Ch], eax
0x1800612af  add     eax, edi
0x1800612b1  jnz     short loc_1800612C2
0x1800612b3  mov     rax, [rbx]
0x1800612b6  mov     rcx, rbx
0x1800612b9  mov     rax, [rax+8]
0x1800612bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612c2  mov     rax, cs:qword_1800B9330
0x1800612c9  sub     rax, 10h
0x1800612cd  mov     cs:qword_1800B9330, rax
0x1800612d4  jmp     short loc_18006126D
0x1800612d6  mov     rax, cs:qword_1800B9450
0x1800612dd  cmp     cs:?s_instances@ClientIdentity2@@0V?$vector@V?$shared_ptr@VClientIdentity2@@@std@@V?$allocator@V?$shared_ptr@VClientIdentity2@@@std@@@2@@std@@A, rax; std::vector<std::shared_ptr<ClientIdentity2>> ClientIdentity2::s_instances
0x1800612e4  jz      short loc_180061363
0x1800612e6  mov     rcx, [rax-10h]
0x1800612ea  mov     r9, [rsp+308h]; char *
0x1800612f2  mov     rax, [rcx+0A0h]
0x1800612f9  cmp     [rcx+98h], rax
0x180061300  jnz     loc_180061575
0x180061306  mov     byte ptr [rcx], 1
0x180061309  mov     rax, cs:qword_1800B9450
0x180061310  mov     rbx, [rax-8]
0x180061314  test    rbx, rbx
0x180061317  jz      short loc_180061353
0x180061319  mov     eax, edi
0x18006131b  lock xadd [rbx+8], eax
0x180061320  add     eax, edi
0x180061322  jnz     short loc_18006134C
0x180061324  mov     rax, [rbx]
0x180061327  mov     rcx, rbx
0x18006132a  mov     rax, [rax]
0x18006132d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061332  mov     eax, edi
0x180061334  lock xadd [rbx+0Ch], eax
0x180061339  add     eax, edi
0x18006133b  jnz     short loc_18006134C
0x18006133d  mov     rax, [rbx]
0x180061340  mov     rcx, rbx
0x180061343  mov     rax, [rax+8]
0x180061347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006134c  mov     rax, cs:qword_1800B9450
0x180061353  sub     rax, 10h
0x180061357  mov     cs:qword_1800B9450, rax
0x18006135e  jmp     loc_1800612DD
0x180061363  mov     rax, cs:qword_1800B9370
0x18006136a  cmp     cs:?s_instances@ClientIdentity@@0V?$vector@V?$shared_ptr@VClientIdentity@@@std@@V?$allocator@V?$shared_ptr@VClientIdentity@@@std@@@2@@std@@A, rax; std::vector<std::shared_ptr<ClientIdentity>> ClientIdentity::s_instances
0x180061371  jz      short loc_1800613E7
0x180061373  mov     rcx, [rax-10h]
0x180061377  mov     r9, [rsp+308h]; char *
0x18006137f  mov     rax, [rcx+40h]
0x180061383  cmp     [rcx+38h], rax
0x180061387  jnz     loc_18006158A
0x18006138d  mov     byte ptr [rcx], 1
0x180061390  mov     rax, cs:qword_1800B9370
0x180061397  mov     rbx, [rax-8]
0x18006139b  test    rbx, rbx
0x18006139e  jz      short loc_1800613DA
0x1800613a0  mov     eax, edi
0x1800613a2  lock xadd [rbx+8], eax
0x1800613a7  add     eax, edi
0x1800613a9  jnz     short loc_1800613D3
0x1800613ab  mov     rax, [rbx]
0x1800613ae  mov     rcx, rbx
0x1800613b1  mov     rax, [rax]
0x1800613b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613b9  mov     eax, edi
0x1800613bb  lock xadd [rbx+0Ch], eax
0x1800613c0  add     eax, edi
0x1800613c2  jnz     short loc_1800613D3
0x1800613c4  mov     rax, [rbx]
0x1800613c7  mov     rcx, rbx
0x1800613ca  mov     rax, [rax+8]
0x1800613ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613d3  mov     rax, cs:qword_1800B9370
0x1800613da  sub     rax, 10h
0x1800613de  mov     cs:qword_1800B9370, rax
0x1800613e5  jmp     short loc_18006136A
0x1800613e7  call    ?CleanupAllOutstandingAgentUsers_DropsLock@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@SAXXZ; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock(void)
0x1800613ec  call    ?CleanupAllOutstandingAgentUsers_DropsLock@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@SAXXZ; Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock(void)
0x1800613f1  mov     rdi, cs:?g_rootKey@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> g_rootKey
0x1800613f8  test    rdi, rdi
0x1800613fb  jz      short loc_180061416
0x1800613fd  call    cs:__imp_GetLastError
0x180061403  mov     ebx, eax
0x180061405  mov     rcx, rdi; hKey
0x180061408  call    cs:__imp_RegCloseKey
0x18006140e  mov     ecx, ebx; dwErrCode
0x180061410  call    cs:__imp_SetLastError
0x180061416  mov     cs:?g_rootKey@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> g_rootKey
0x180061421  cmp     cs:byte_1800B9248, 0
0x180061428  jz      short loc_18006145A
0x18006142a  lea     rdx, ?g_securityLog@@3VSecurityLog@@A; phEventProvider
0x180061431  xor     ecx, ecx; dwFlags
0x180061433  call    cs:__imp_AuthzUnregisterSecurityEventSource
0x180061439  test    eax, eax
0x18006143b  jz      short loc_180061446
0x18006143d  mov     cs:byte_1800B9248, 0
0x180061444  jmp     short loc_18006145A
0x180061446  call    cs:__imp_GetLastError
0x18006144c  mov     [rsp+308h+var_2E8], eax
0x180061450  lea     rcx, [rsp+308h+var_2E8]
0x180061455  call    ??$SecurityLogShutdownFailure@K@IsoEnvBrokerTelemetry@@SAX$$QEAK@Z; IsoEnvBrokerTelemetry::SecurityLogShutdownFailure<ulong>(ulong &&)
0x18006145a  cmp     cs:?g_eventLog@@3VEventLog@@A, 0; EventLog g_eventLog
0x180061461  jz      short loc_180061480
0x180061463  call    McGenEventUnregister_EventUnregister
0x180061468  mov     cs:?g_eventLog@@3VEventLog@@A, 0; EventLog g_eventLog
0x18006146f  lea     rdx, aUninitializedE; "Uninitialized EventLog"
0x180061476  mov     ecx, 4; unsigned __int8
0x18006147b  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180061480  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x18006148b  lea     rdx, ServiceStatus; lpServiceStatus
0x180061492  mov     rcx, cs:?g_serviceState@@3UServiceState@@A; hServiceStatus
0x180061499  call    cs:__imp_SetServiceStatus
0x18006149f  mov     rcx, [rsp+308h]; this
0x1800614a7  test    eax, eax
0x1800614a9  jnz     short loc_1800614B5
0x1800614ab  mov     edx, 10Bh; void *
0x1800614b0  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800614b5  lea     rcx, ?g_serviceState@@3UServiceState@@A; this
0x1800614bc  call    ?Reset@ServiceState@@QEAAXXZ; ServiceState::Reset(void)
0x1800614c1  cmp     cs:?g_hLogFile@@3PEAXEA, 0; void * g_hLogFile
0x1800614c9  jz      short loc_1800614F4
0x1800614cb  lea     rdx, aServiceStopped; "Service stopped; closing log."
0x1800614d2  mov     ecx, 4; unsigned __int8
0x1800614d7  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800614dc  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x1800614e3  call    cs:__imp_CloseHandle
0x1800614e9  mov     cs:?g_hLogFile@@3PEAXEA, 0; void * g_hLogFile
0x1800614f4  lea     rcx, [rsp+308h+var_188]
0x1800614fc  call    ?Stop@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180061501  nop
0x180061502  mov     rcx, [rsp+308h+SRWLock]; SRWLock
0x180061507  test    rcx, rcx
0x18006150a  jz      short loc_18006151A
0x18006150c  mov     dword ptr [rcx+8], 0
0x180061513  call    cs:__imp_ReleaseSRWLockExclusive
0x180061519  nop
0x18006151a  mov     [rsp+308h+var_2D8], r15
0x18006151f  lea     rcx, [rsp+308h+var_2D8]
0x180061524  call    ?Destroy@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180061529  lea     rcx, [rsp+308h+var_2D8]
0x18006152e  call    ??1?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180061533  nop
0x180061534  mov     [rsp+308h+var_188], r14
0x18006153c  lea     rcx, [rsp+308h+var_188]
0x180061544  call    ?Destroy@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180061549  lea     rcx, [rsp+308h+var_188]
0x180061551  call    ??1?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180061556  nop
0x180061557  mov     rcx, [rsp+308h+var_38]
0x18006155f  xor     rcx, rsp; StackCookie
0x180061562  call    __security_check_cookie
0x180061567  add     rsp, 2E8h
0x18006156e  pop     r15
0x180061570  pop     r14
0x180061572  pop     rdi
0x180061573  pop     rbx
0x180061574  retn
0x180061575  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18006157c  mov     edx, 3Ah ; ':'; void *
0x180061581  mov     rcx, r9; this
0x180061584  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006158a  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180061591  mov     edx, 38h ; '8'; void *
0x180061596  mov     rcx, r9; this
0x180061599  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
