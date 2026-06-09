# PimIMService::_AggregateCacheBackupTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000b480`
- end: `0x18000b580`
- name: `?_AggregateCacheBackupTimerCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `256`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x18000b480`
- `0x18000b654`
- `0x18000d63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b521`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b546`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b4ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b521`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b4f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b539`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b4f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b511`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b539`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b579`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b564`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b564`
- `PIMSTORE!GetAggregateCache` at `0x18000b4c8`
- `PIMSTORE!GetAggregateCache` at `0x18000b4c8`

## string_xrefs

- `0x18000b4da`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000b4fc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
void __fastcall PimIMService::_AggregateCacheBackupTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  _QWORD *v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  int AggregateCache; // eax
  unsigned int v7; // ebp

  v4 = Context + 368;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)Context + 114, 0, 1) )
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)(Context + 376);
    EnterCriticalSection((LPCRITICAL_SECTION)(Context + 376));
    if ( *v4
      && (AggregateCache = GetAggregateCache(2, *((_QWORD *)Context + 27)), v7 = AggregateCache, AggregateCache < 0) )
    {
      Log_HREvent(
        (unsigned int)AggregateCache,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        3535);
      LeaveCriticalSection(v5);
      Log_HREvent(
        v7,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        3477);
    }
    else
    {
      LeaveCriticalSection(v5);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 416));
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v4);
  *v4 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 416));
  EnterCriticalSection(&g_shutdownLock);
  if ( (int)FailOnServiceShutdown() >= 0 )
    SetThreadpoolTimer(*((PTP_TIMER *)Context + 61), 0, 0, 0);
  LeaveCriticalSection(&g_shutdownLock);
}

```

## disassembly

```asm
0x18000b480  push    rbx
0x18000b482  push    rbp
0x18000b483  push    rsi
0x18000b484  push    rdi
0x18000b485  sub     rsp, 38h
0x18000b489  xor     ecx, ecx
0x18000b48b  mov     rdi, rdx
0x18000b48e  lea     eax, [rcx+1]
0x18000b491  lock cmpxchg [rdx+1C8h], ecx
0x18000b499  lea     rsi, [rdx+170h]
0x18000b4a0  test    eax, eax
0x18000b4a2  jz      short loc_18000B517
0x18000b4a4  lea     rbx, [rdx+178h]
0x18000b4ab  mov     rcx, rbx; lpCriticalSection
0x18000b4ae  call    cs:__imp_EnterCriticalSection
0x18000b4b4  cmp     qword ptr [rsi], 0
0x18000b4b8  jz      short loc_18000B50E
0x18000b4ba  mov     rdx, [rdi+0D8h]
0x18000b4c1  xor     r8d, r8d
0x18000b4c4  lea     ecx, [r8+2]
0x18000b4c8  call    cs:__imp_GetAggregateCache
0x18000b4ce  mov     ebp, eax
0x18000b4d0  test    eax, eax
0x18000b4d2  jns     short loc_18000B50E
0x18000b4d4  mov     r9d, 0DCFh
0x18000b4da  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b4e1  mov     edx, 1
0x18000b4e6  mov     ecx, eax
0x18000b4e8  call    Log_HREvent
0x18000b4ed  mov     rcx, rbx; lpCriticalSection
0x18000b4f0  call    cs:__imp_LeaveCriticalSection
0x18000b4f6  mov     r9d, 0D95h
0x18000b4fc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b503  xor     edx, edx
0x18000b505  mov     ecx, ebp
0x18000b507  call    Log_HREvent
0x18000b50c  jmp     short loc_18000B517
0x18000b50e  mov     rcx, rbx; lpCriticalSection
0x18000b511  call    cs:__imp_LeaveCriticalSection
0x18000b517  lea     rbx, [rdi+1A0h]
0x18000b51e  mov     rcx, rbx; lpCriticalSection
0x18000b521  call    cs:__imp_EnterCriticalSection
0x18000b527  mov     rcx, rsi
0x18000b52a  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000b52f  mov     rcx, rbx; lpCriticalSection
0x18000b532  mov     qword ptr [rsi], 0
0x18000b539  call    cs:__imp_LeaveCriticalSection
0x18000b53f  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000b546  call    cs:__imp_EnterCriticalSection
0x18000b54c  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x18000b551  test    eax, eax
0x18000b553  js      short loc_18000B56A
0x18000b555  mov     rcx, [rdi+1E8h]; pti
0x18000b55c  xor     r9d, r9d; msWindowLength
0x18000b55f  xor     r8d, r8d; msPeriod
0x18000b562  xor     edx, edx; pftDueTime
0x18000b564  call    cs:__imp_SetThreadpoolTimer
0x18000b56a  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_shutdownLock
0x18000b571  add     rsp, 38h
0x18000b575  pop     rdi
0x18000b576  pop     rsi
0x18000b577  pop     rbp
0x18000b578  pop     rbx
0x18000b579  jmp     cs:__imp_LeaveCriticalSection
```
