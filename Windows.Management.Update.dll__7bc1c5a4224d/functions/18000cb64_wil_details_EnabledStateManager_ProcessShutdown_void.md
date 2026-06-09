# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000cb64`
- end: `0x18000cbf8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009934`
- `0x180029120`

## callees

- `0x18000cb64`
- `0x18000cfb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cb8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cb8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cba5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbe2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cbc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cbc3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cbda`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cbda`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cbd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cbd1`

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
0x18000cb64  mov     [rsp+arg_0], rbx
0x18000cb69  mov     [rsp+arg_8], rsi
0x18000cb6e  push    rdi
0x18000cb6f  sub     rsp, 20h
0x18000cb73  mov     dword ptr [rcx], 0
0x18000cb79  lea     rdi, [rcx+8]
0x18000cb7d  mov     rsi, [rcx+10h]
0x18000cb81  mov     rbx, rcx
0x18000cb84  mov     qword ptr [rcx+10h], 0
0x18000cb8c  mov     rcx, rdi; SRWLock
0x18000cb8f  call    cs:__imp_AcquireSRWLockExclusive
0x18000cb95  mov     rcx, rbx
0x18000cb98  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000cb9d  test    rdi, rdi
0x18000cba0  jz      short loc_18000CBAB
0x18000cba2  mov     rcx, rdi; SRWLock
0x18000cba5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cbab  test    rsi, rsi
0x18000cbae  jz      short loc_18000CBE8
0x18000cbb0  call    cs:__imp_GetLastError
0x18000cbb6  xor     r9d, r9d; msWindowLength
0x18000cbb9  xor     r8d, r8d; msPeriod
0x18000cbbc  xor     edx, edx; pftDueTime
0x18000cbbe  mov     rcx, rsi; pti
0x18000cbc1  mov     ebx, eax
0x18000cbc3  call    cs:__imp_SetThreadpoolTimer
0x18000cbc9  mov     edx, 1; fCancelPendingCallbacks
0x18000cbce  mov     rcx, rsi; pti
0x18000cbd1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cbd7  mov     rcx, rsi; pti
0x18000cbda  call    cs:__imp_CloseThreadpoolTimer
0x18000cbe0  mov     ecx, ebx; dwErrCode
0x18000cbe2  call    cs:__imp_SetLastError
0x18000cbe8  mov     rbx, [rsp+28h+arg_0]
0x18000cbed  mov     rsi, [rsp+28h+arg_8]
0x18000cbf2  add     rsp, 20h
0x18000cbf6  pop     rdi
0x18000cbf7  retn
```
