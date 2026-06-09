# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18001947c`
- end: `0x180019510`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012eb0`
- `0x180029950`

## callees

- `0x18001947c`
- `0x180019ba8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800194bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800194bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800194a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800194a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800194fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800194fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800194f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800194f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800194db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800194db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800194e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800194e9`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rsi
  struct _TP_TIMER *Ptr; // rdi
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
0x18001947c  mov     [rsp+arg_8], rbx
0x180019481  mov     [rsp+arg_10], rsi
0x180019486  push    rdi
0x180019487  sub     rsp, 20h
0x18001948b  mov     dword ptr [rcx], 0
0x180019491  lea     rsi, [rcx+8]
0x180019495  mov     rdi, [rcx+10h]
0x180019499  mov     rbx, rcx
0x18001949c  mov     qword ptr [rcx+10h], 0
0x1800194a4  mov     rcx, rsi; SRWLock
0x1800194a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800194ad  mov     rcx, rbx
0x1800194b0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800194b5  test    rsi, rsi
0x1800194b8  jz      short loc_1800194C3
0x1800194ba  mov     rcx, rsi; SRWLock
0x1800194bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800194c3  test    rdi, rdi
0x1800194c6  jz      short loc_180019500
0x1800194c8  call    cs:__imp_GetLastError
0x1800194ce  xor     r9d, r9d; msWindowLength
0x1800194d1  xor     r8d, r8d; msPeriod
0x1800194d4  xor     edx, edx; pftDueTime
0x1800194d6  mov     rcx, rdi; pti
0x1800194d9  mov     ebx, eax
0x1800194db  call    cs:__imp_SetThreadpoolTimer
0x1800194e1  mov     edx, 1; fCancelPendingCallbacks
0x1800194e6  mov     rcx, rdi; pti
0x1800194e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800194ef  mov     rcx, rdi; pti
0x1800194f2  call    cs:__imp_CloseThreadpoolTimer
0x1800194f8  mov     ecx, ebx; dwErrCode
0x1800194fa  call    cs:__imp_SetLastError
0x180019500  mov     rbx, [rsp+28h+arg_8]
0x180019505  mov     rsi, [rsp+28h+arg_10]
0x18001950a  add     rsp, 20h
0x18001950e  pop     rdi
0x18001950f  retn
```
