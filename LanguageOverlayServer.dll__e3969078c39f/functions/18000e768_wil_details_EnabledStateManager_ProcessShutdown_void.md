# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000e768`
- end: `0x18000e7fc`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c1bc`
- `0x1800697c0`

## callees

- `0x18000e768`
- `0x18000ef1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e7a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e7a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e793`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e7c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e7c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e7de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e7de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e7d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e7d5`

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
0x18000e768  mov     [rsp+arg_0], rbx
0x18000e76d  mov     [rsp+arg_8], rsi
0x18000e772  push    rdi
0x18000e773  sub     rsp, 20h
0x18000e777  mov     dword ptr [rcx], 0
0x18000e77d  lea     rdi, [rcx+8]
0x18000e781  mov     rsi, [rcx+10h]
0x18000e785  mov     rbx, rcx
0x18000e788  mov     qword ptr [rcx+10h], 0
0x18000e790  mov     rcx, rdi; SRWLock
0x18000e793  call    cs:__imp_AcquireSRWLockExclusive
0x18000e799  mov     rcx, rbx
0x18000e79c  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000e7a1  test    rdi, rdi
0x18000e7a4  jz      short loc_18000E7AF
0x18000e7a6  mov     rcx, rdi; SRWLock
0x18000e7a9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e7af  test    rsi, rsi
0x18000e7b2  jz      short loc_18000E7EC
0x18000e7b4  call    cs:__imp_GetLastError
0x18000e7ba  xor     r9d, r9d; msWindowLength
0x18000e7bd  xor     r8d, r8d; msPeriod
0x18000e7c0  xor     edx, edx; pftDueTime
0x18000e7c2  mov     rcx, rsi; pti
0x18000e7c5  mov     ebx, eax
0x18000e7c7  call    cs:__imp_SetThreadpoolTimer
0x18000e7cd  mov     edx, 1; fCancelPendingCallbacks
0x18000e7d2  mov     rcx, rsi; pti
0x18000e7d5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e7db  mov     rcx, rsi; pti
0x18000e7de  call    cs:__imp_CloseThreadpoolTimer
0x18000e7e4  mov     ecx, ebx; dwErrCode
0x18000e7e6  call    cs:__imp_SetLastError
0x18000e7ec  mov     rbx, [rsp+28h+arg_0]
0x18000e7f1  mov     rsi, [rsp+28h+arg_8]
0x18000e7f6  add     rsp, 20h
0x18000e7fa  pop     rdi
0x18000e7fb  retn
```
