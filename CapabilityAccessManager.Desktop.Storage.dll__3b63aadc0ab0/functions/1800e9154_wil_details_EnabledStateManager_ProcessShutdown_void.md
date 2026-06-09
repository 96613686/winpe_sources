# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800e9154`
- end: `0x1800e91e8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800e6310`
- `0x18010c450`

## callees

- `0x1800e9154`
- `0x1800e95e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e917f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e917f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e9195`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e9195`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e91d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e91d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e91a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e91a0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e91c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e91c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e91ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e91ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e91b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e91b3`

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
0x1800e9154  mov     [rsp+arg_0], rbx
0x1800e9159  mov     [rsp+arg_8], rsi
0x1800e915e  push    rdi
0x1800e915f  sub     rsp, 20h
0x1800e9163  mov     dword ptr [rcx], 0
0x1800e9169  lea     rdi, [rcx+8]
0x1800e916d  mov     rsi, [rcx+10h]
0x1800e9171  mov     rbx, rcx
0x1800e9174  mov     qword ptr [rcx+10h], 0
0x1800e917c  mov     rcx, rdi; SRWLock
0x1800e917f  call    cs:__imp_AcquireSRWLockExclusive
0x1800e9185  mov     rcx, rbx
0x1800e9188  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800e918d  test    rdi, rdi
0x1800e9190  jz      short loc_1800E919B
0x1800e9192  mov     rcx, rdi; SRWLock
0x1800e9195  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e919b  test    rsi, rsi
0x1800e919e  jz      short loc_1800E91D8
0x1800e91a0  call    cs:__imp_GetLastError
0x1800e91a6  xor     r9d, r9d; msWindowLength
0x1800e91a9  xor     r8d, r8d; msPeriod
0x1800e91ac  xor     edx, edx; pftDueTime
0x1800e91ae  mov     rcx, rsi; pti
0x1800e91b1  mov     ebx, eax
0x1800e91b3  call    cs:__imp_SetThreadpoolTimer
0x1800e91b9  mov     edx, 1; fCancelPendingCallbacks
0x1800e91be  mov     rcx, rsi; pti
0x1800e91c1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e91c7  mov     rcx, rsi; pti
0x1800e91ca  call    cs:__imp_CloseThreadpoolTimer
0x1800e91d0  mov     ecx, ebx; dwErrCode
0x1800e91d2  call    cs:__imp_SetLastError
0x1800e91d8  mov     rbx, [rsp+28h+arg_0]
0x1800e91dd  mov     rsi, [rsp+28h+arg_8]
0x1800e91e2  add     rsp, 20h
0x1800e91e6  pop     rdi
0x1800e91e7  retn
```
