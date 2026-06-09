# DqbServiceStop(void)

- ea: `0x180002c20`
- end: `0x180002e0f`
- name: `?DqbServiceStop@@YAXXZ`
- size: `495`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180002af0`
- `0x180002ba0`
- `0x180002eb0`
- `0x180002ec0`

## callees

- `0x180001214`
- `0x1800029ac`
- `0x180002c20`
- `0x180002e18`
- `0x18000314c`

## import_xrefs

- `BrokerLib!BrDeleteBrokerInstance` at `0x180002d16`
- `BrokerLib!BrDeleteBrokerInstance` at `0x180002d16`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180002cd8`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180002cd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d45`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002dca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002dca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002dd7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002dd7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002db8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002db8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002c7f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002c7f`

## pseudocode

```c
void DqbServiceStop(void)
{
  signed __int64 i; // rax
  struct SERVICE_STATUS_HANDLE__ *v1; // rcx
  struct SERVICE_STATUS_HANDLE__ *v2; // rcx
  unsigned int v3; // eax
  struct SERVICE_STATUS_HANDLE__ *v4; // rcx
  void *v5; // rbx
  struct SERVICE_STATUS_HANDLE__ *v6; // rcx
  struct SERVICE_STATUS_HANDLE__ *v7; // rcx
  struct SERVICE_STATUS_HANDLE__ *v8; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids);
  _m_prefetchw((const void *)&g_dqbSeviceControlFlags);
  for ( i = _InterlockedOr64((volatile signed __int64 *)&g_dqbSeviceControlFlags, 1u);
        (i & 0xFFFFFFFFFFFFFFFEuLL) != 0;
        i = _InterlockedOr64((volatile signed __int64 *)&g_dqbSeviceControlFlags, 1u) )
  {
    Sleep(0x32u);
    _m_prefetchw((const void *)&g_dqbSeviceControlFlags);
  }
  DqbStatusUpdate(v1, 3u, 0, 0);
  v3 = g_dqbServiceState;
  if ( (g_dqbServiceState & 2) != 0 )
  {
    if ( (g_dqbRpcState & 1) != 0 )
    {
      RpcServerInterfaceGroupClose(g_dqbRpcInterfaceGroup);
      g_dqbRpcState &= 0xFFFFFFFC;
      v3 = g_dqbServiceState;
    }
    g_dqbServiceState = v3 & 0xFFFFFFFD;
  }
  DqbStatusUpdate(v2, 3u, 1u, 0);
  v5 = g_pDqbInstance;
  if ( g_pDqbInstance )
  {
    if ( *(_QWORD *)g_pDqbInstance )
      BrDeleteBrokerInstance();
    operator delete(v5);
  }
  DqbStatusUpdate(v4, 3u, 2u, 0);
  if ( (g_dqbServiceState & 1) != 0 )
  {
    EnterCriticalSection(&g_csActiveQueriesList);
    while ( g_activeQueriesList.Flink != &g_activeQueriesList )
      CActiveQueries::RemoveBrokeredQueryContext((struct _BrokeredQueryContext *)&g_activeQueriesList.Flink[-1]);
    LeaveCriticalSection(&g_csActiveQueriesList);
    DeleteCriticalSection(&g_csActiveQueriesList);
    g_dqbServiceState &= ~1u;
    *(_OWORD *)&g_csActiveQueriesList.DebugInfo = 0;
    g_csActiveQueriesList.SpinCount = 0;
    *(_OWORD *)&g_csActiveQueriesList.OwningThread = 0;
  }
  DqbStatusUpdate(v6, 3u, 3u, 0);
  SetThreadpoolTimer(g_dqbIdleStopTimer, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(g_dqbIdleStopTimer, 1);
  CloseThreadpoolTimer(g_dqbIdleStopTimer);
  g_dqbIdleStopTimer = 0;
  DqbStatusUpdate(v7, 3u, 4u, 0);
  DqbStatusUpdate(v8, 1u, 0, 0);
}

```

## disassembly

```asm
0x180002c20  mov     [rsp+arg_0], rbx
0x180002c25  push    rsi
0x180002c26  sub     rsp, 20h
0x180002c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c31  lea     rax, WPP_GLOBAL_Control
0x180002c38  cmp     rcx, rax
0x180002c3b  jz      short loc_180002C58
0x180002c3d  cmp     byte ptr [rcx+19h], 4
0x180002c41  jb      short loc_180002C58
0x180002c43  mov     rcx, [rcx+10h]
0x180002c47  lea     r8, WPP_dfb895cd27423fa336520d05ee2dcb21_Traceguids
0x180002c4e  mov     edx, 0Ah
0x180002c53  call    WPP_SF_
0x180002c58  prefetchw byte ptr cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002c5f  mov     rax, cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002c66  mov     rcx, rax
0x180002c69  or      rcx, 1
0x180002c6d  lock cmpxchg cs:?g_dqbSeviceControlFlags@@3_KC, rcx; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002c76  jnz     short loc_180002C66
0x180002c78  jmp     short loc_180002CA5
0x180002c7a  mov     ecx, 32h ; '2'; dwMilliseconds
0x180002c7f  call    cs:__imp_Sleep
0x180002c85  prefetchw byte ptr cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002c8c  mov     rax, cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002c93  mov     rcx, rax
0x180002c96  or      rcx, 1; struct SERVICE_STATUS_HANDLE__ *
0x180002c9a  lock cmpxchg cs:?g_dqbSeviceControlFlags@@3_KC, rcx; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002ca3  jnz     short loc_180002C93
0x180002ca5  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002cab  jnz     short loc_180002C7A
0x180002cad  xor     r9d, r9d; unsigned int
0x180002cb0  xor     r8d, r8d; unsigned int
0x180002cb3  lea     esi, [r9+3]
0x180002cb7  mov     edx, esi; unsigned int
0x180002cb9  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180002cbe  mov     eax, cs:?g_dqbServiceState@@3KA; ulong g_dqbServiceState
0x180002cc4  test    al, 2
0x180002cc6  jz      short loc_180002CF4
0x180002cc8  test    byte ptr cs:?g_dqbRpcState@@3KA, 1; ulong g_dqbRpcState
0x180002ccf  jz      short loc_180002CEB
0x180002cd1  mov     rcx, cs:?g_dqbRpcInterfaceGroup@@3PEAXEA; void * g_dqbRpcInterfaceGroup
0x180002cd8  call    cs:__imp_RpcServerInterfaceGroupClose
0x180002cde  and     cs:?g_dqbRpcState@@3KA, 0FFFFFFFCh; ulong g_dqbRpcState
0x180002ce5  mov     eax, cs:?g_dqbServiceState@@3KA; ulong g_dqbServiceState
0x180002ceb  and     eax, 0FFFFFFFDh
0x180002cee  mov     cs:?g_dqbServiceState@@3KA, eax; ulong g_dqbServiceState
0x180002cf4  xor     r9d, r9d; unsigned int
0x180002cf7  mov     edx, esi; unsigned int
0x180002cf9  lea     r8d, [r9+1]; unsigned int
0x180002cfd  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180002d02  mov     rbx, cs:?g_pDqbInstance@@3PEAVCBrokerInstance@@EA; CBrokerInstance * g_pDqbInstance
0x180002d09  test    rbx, rbx
0x180002d0c  jz      short loc_180002D24
0x180002d0e  mov     rcx, [rbx]
0x180002d11  test    rcx, rcx
0x180002d14  jz      short loc_180002D1C
0x180002d16  call    cs:__imp_BrDeleteBrokerInstance
0x180002d1c  mov     rcx, rbx; Block
0x180002d1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d24  xor     r9d, r9d; unsigned int
0x180002d27  mov     edx, esi; unsigned int
0x180002d29  lea     r8d, [r9+2]; unsigned int
0x180002d2d  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180002d32  test    byte ptr cs:?g_dqbServiceState@@3KA, 1; ulong g_dqbServiceState
0x180002d39  jz      short loc_180002D9C
0x180002d3b  lea     rbx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csActiveQueriesList
0x180002d42  mov     rcx, rbx; lpCriticalSection
0x180002d45  call    cs:__imp_EnterCriticalSection
0x180002d4b  mov     rcx, cs:?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x180002d52  lea     rax, ?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x180002d59  cmp     rcx, rax
0x180002d5c  jz      short loc_180002D69
0x180002d5e  add     rcx, 0FFFFFFFFFFFFFFF0h; struct _BrokeredQueryContext *
0x180002d62  call    ?RemoveBrokeredQueryContext@CActiveQueries@@SAXPEAU_BrokeredQueryContext@@@Z; CActiveQueries::RemoveBrokeredQueryContext(_BrokeredQueryContext *)
0x180002d67  jmp     short loc_180002D4B
0x180002d69  mov     rcx, rbx; lpCriticalSection
0x180002d6c  call    cs:__imp_LeaveCriticalSection
0x180002d72  mov     rcx, rbx; lpCriticalSection
0x180002d75  call    cs:__imp_DeleteCriticalSection
0x180002d7b  xorps   xmm0, xmm0
0x180002d7e  xor     eax, eax
0x180002d80  and     cs:?g_dqbServiceState@@3KA, 0FFFFFFFEh; ulong g_dqbServiceState
0x180002d87  movups  xmmword ptr cs:?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A.DebugInfo, xmm0; _RTL_CRITICAL_SECTION g_csActiveQueriesList ...
0x180002d8e  mov     cs:?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A.SpinCount, rax; _RTL_CRITICAL_SECTION g_csActiveQueriesList ...
0x180002d95  movups  xmmword ptr cs:?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, xmm0; _RTL_CRITICAL_SECTION g_csActiveQueriesList ...
0x180002d9c  xor     r9d, r9d; unsigned int
0x180002d9f  mov     r8d, esi; unsigned int
0x180002da2  mov     edx, esi; unsigned int
0x180002da4  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180002da9  mov     rcx, cs:?g_dqbIdleStopTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002db0  xor     r9d, r9d; msWindowLength
0x180002db3  xor     r8d, r8d; msPeriod
0x180002db6  xor     edx, edx; pftDueTime
0x180002db8  call    cs:__imp_SetThreadpoolTimer
0x180002dbe  mov     rcx, cs:?g_dqbIdleStopTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002dc5  mov     edx, 1; fCancelPendingCallbacks
0x180002dca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002dd0  mov     rcx, cs:?g_dqbIdleStopTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002dd7  call    cs:__imp_CloseThreadpoolTimer
0x180002ddd  xor     r9d, r9d; unsigned int
0x180002de0  mov     cs:?g_dqbIdleStopTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_dqbIdleStopTimer
0x180002deb  mov     edx, esi; unsigned int
0x180002ded  lea     r8d, [r9+4]; unsigned int
0x180002df1  call    ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180002df6  xor     r9d, r9d; unsigned int
0x180002df9  xor     r8d, r8d; unsigned int
0x180002dfc  lea     edx, [r9+1]; unsigned int
0x180002e00  mov     rbx, [rsp+28h+arg_0]
0x180002e05  add     rsp, 20h
0x180002e09  pop     rsi
0x180002e0a  jmp     ?DqbStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DqbStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
```
