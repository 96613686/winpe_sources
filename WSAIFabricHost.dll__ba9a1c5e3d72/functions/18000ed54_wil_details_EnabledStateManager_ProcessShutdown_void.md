# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000ed54`
- end: `0x18000ede8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc88`
- `0x180088450`

## callees

- `0x18000ed54`
- `0x18000f360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eda0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edd2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000edc1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000edc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000edca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000edca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000edb3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000edb3`

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
0x18000ed54  mov     [rsp+arg_0], rbx
0x18000ed59  mov     [rsp+arg_8], rsi
0x18000ed5e  push    rdi
0x18000ed5f  sub     rsp, 20h
0x18000ed63  mov     dword ptr [rcx], 0
0x18000ed69  lea     rdi, [rcx+8]
0x18000ed6d  mov     rsi, [rcx+10h]
0x18000ed71  mov     rbx, rcx
0x18000ed74  mov     qword ptr [rcx+10h], 0
0x18000ed7c  mov     rcx, rdi; SRWLock
0x18000ed7f  call    cs:__imp_AcquireSRWLockExclusive
0x18000ed85  mov     rcx, rbx
0x18000ed88  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000ed8d  test    rdi, rdi
0x18000ed90  jz      short loc_18000ED9B
0x18000ed92  mov     rcx, rdi; SRWLock
0x18000ed95  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ed9b  test    rsi, rsi
0x18000ed9e  jz      short loc_18000EDD8
0x18000eda0  call    cs:__imp_GetLastError
0x18000eda6  xor     r9d, r9d; msWindowLength
0x18000eda9  xor     r8d, r8d; msPeriod
0x18000edac  xor     edx, edx; pftDueTime
0x18000edae  mov     rcx, rsi; pti
0x18000edb1  mov     ebx, eax
0x18000edb3  call    cs:__imp_SetThreadpoolTimer
0x18000edb9  mov     edx, 1; fCancelPendingCallbacks
0x18000edbe  mov     rcx, rsi; pti
0x18000edc1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000edc7  mov     rcx, rsi; pti
0x18000edca  call    cs:__imp_CloseThreadpoolTimer
0x18000edd0  mov     ecx, ebx; dwErrCode
0x18000edd2  call    cs:__imp_SetLastError
0x18000edd8  mov     rbx, [rsp+28h+arg_0]
0x18000eddd  mov     rsi, [rsp+28h+arg_8]
0x18000ede2  add     rsp, 20h
0x18000ede6  pop     rdi
0x18000ede7  retn
```
