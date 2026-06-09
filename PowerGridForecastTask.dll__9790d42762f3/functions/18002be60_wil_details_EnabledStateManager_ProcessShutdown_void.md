# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18002be60`
- end: `0x18002bef4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002803c`
- `0x1800364f0`

## callees

- `0x18002be60`
- `0x18002c5c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002beac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002beac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bede`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bede`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bea1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bea1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002be8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002be8b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002becd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002becd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002bed6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002bed6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002bebf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002bebf`

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
0x18002be60  mov     [rsp+arg_0], rbx
0x18002be65  mov     [rsp+arg_8], rsi
0x18002be6a  push    rdi
0x18002be6b  sub     rsp, 20h
0x18002be6f  mov     dword ptr [rcx], 0
0x18002be75  lea     rdi, [rcx+8]
0x18002be79  mov     rsi, [rcx+10h]
0x18002be7d  mov     rbx, rcx
0x18002be80  mov     qword ptr [rcx+10h], 0
0x18002be88  mov     rcx, rdi; SRWLock
0x18002be8b  call    cs:__imp_AcquireSRWLockExclusive
0x18002be91  mov     rcx, rbx
0x18002be94  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18002be99  test    rdi, rdi
0x18002be9c  jz      short loc_18002BEA7
0x18002be9e  mov     rcx, rdi; SRWLock
0x18002bea1  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bea7  test    rsi, rsi
0x18002beaa  jz      short loc_18002BEE4
0x18002beac  call    cs:__imp_GetLastError
0x18002beb2  xor     r9d, r9d; msWindowLength
0x18002beb5  xor     r8d, r8d; msPeriod
0x18002beb8  xor     edx, edx; pftDueTime
0x18002beba  mov     rcx, rsi; pti
0x18002bebd  mov     ebx, eax
0x18002bebf  call    cs:__imp_SetThreadpoolTimer
0x18002bec5  mov     edx, 1; fCancelPendingCallbacks
0x18002beca  mov     rcx, rsi; pti
0x18002becd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002bed3  mov     rcx, rsi; pti
0x18002bed6  call    cs:__imp_CloseThreadpoolTimer
0x18002bedc  mov     ecx, ebx; dwErrCode
0x18002bede  call    cs:__imp_SetLastError
0x18002bee4  mov     rbx, [rsp+28h+arg_0]
0x18002bee9  mov     rsi, [rsp+28h+arg_8]
0x18002beee  add     rsp, 20h
0x18002bef2  pop     rdi
0x18002bef3  retn
```
