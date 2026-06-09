# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180073168`
- end: `0x1800731fc`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18006cf20`
- `0x1802a8620`

## callees

- `0x180073168`
- `0x1800735b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800731a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800731a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073193`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180073193`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800731e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800731e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800731de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800731de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800731d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800731d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800731c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800731c7`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rsi
  DWORD LastError; // ebx

  LODWORD(this->Ptr) = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  if ( Ptr )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(Ptr, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Ptr, 1);
    CloseThreadpoolTimer(Ptr);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x180073168  mov     [rsp+arg_0], rbx
0x18007316d  mov     [rsp+arg_8], rsi
0x180073172  push    rdi
0x180073173  sub     rsp, 20h
0x180073177  mov     dword ptr [rcx], 0
0x18007317d  lea     rdi, [rcx+8]
0x180073181  mov     rsi, [rcx+10h]
0x180073185  mov     rbx, rcx
0x180073188  mov     qword ptr [rcx+10h], 0
0x180073190  mov     rcx, rdi; SRWLock
0x180073193  call    cs:__imp_AcquireSRWLockExclusive
0x180073199  mov     rcx, rbx
0x18007319c  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800731a1  test    rdi, rdi
0x1800731a4  jz      short loc_1800731AF
0x1800731a6  mov     rcx, rdi; SRWLock
0x1800731a9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800731af  test    rsi, rsi
0x1800731b2  jz      short loc_1800731EC
0x1800731b4  call    cs:__imp_GetLastError
0x1800731ba  xor     r9d, r9d; msWindowLength
0x1800731bd  xor     r8d, r8d; msPeriod
0x1800731c0  xor     edx, edx; pftDueTime
0x1800731c2  mov     rcx, rsi; pti
0x1800731c5  mov     ebx, eax
0x1800731c7  call    cs:__imp_SetThreadpoolTimer
0x1800731cd  mov     edx, 1; fCancelPendingCallbacks
0x1800731d2  mov     rcx, rsi; pti
0x1800731d5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800731db  mov     rcx, rsi; pti
0x1800731de  call    cs:__imp_CloseThreadpoolTimer
0x1800731e4  mov     ecx, ebx; dwErrCode
0x1800731e6  call    cs:__imp_SetLastError
0x1800731ec  mov     rbx, [rsp+28h+arg_0]
0x1800731f1  mov     rsi, [rsp+28h+arg_8]
0x1800731f6  add     rsp, 20h
0x1800731fa  pop     rdi
0x1800731fb  retn
```
