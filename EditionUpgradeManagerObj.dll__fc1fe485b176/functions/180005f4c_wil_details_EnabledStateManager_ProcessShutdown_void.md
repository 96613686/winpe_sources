# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180005f4c`
- end: `0x180005fe0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800035a8`
- `0x180022b20`

## callees

- `0x180005f4c`
- `0x180006394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005f77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f98`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005fb9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005fb9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005fc2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005fc2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005fab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005fab`

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
0x180005f4c  mov     [rsp+arg_0], rbx
0x180005f51  mov     [rsp+arg_8], rsi
0x180005f56  push    rdi
0x180005f57  sub     rsp, 20h
0x180005f5b  mov     dword ptr [rcx], 0
0x180005f61  lea     rdi, [rcx+8]
0x180005f65  mov     rsi, [rcx+10h]
0x180005f69  mov     rbx, rcx
0x180005f6c  mov     qword ptr [rcx+10h], 0
0x180005f74  mov     rcx, rdi; SRWLock
0x180005f77  call    cs:__imp_AcquireSRWLockExclusive
0x180005f7d  mov     rcx, rbx
0x180005f80  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180005f85  test    rdi, rdi
0x180005f88  jz      short loc_180005F93
0x180005f8a  mov     rcx, rdi; SRWLock
0x180005f8d  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f93  test    rsi, rsi
0x180005f96  jz      short loc_180005FD0
0x180005f98  call    cs:__imp_GetLastError
0x180005f9e  xor     r9d, r9d; msWindowLength
0x180005fa1  xor     r8d, r8d; msPeriod
0x180005fa4  xor     edx, edx; pftDueTime
0x180005fa6  mov     rcx, rsi; pti
0x180005fa9  mov     ebx, eax
0x180005fab  call    cs:__imp_SetThreadpoolTimer
0x180005fb1  mov     edx, 1; fCancelPendingCallbacks
0x180005fb6  mov     rcx, rsi; pti
0x180005fb9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005fbf  mov     rcx, rsi; pti
0x180005fc2  call    cs:__imp_CloseThreadpoolTimer
0x180005fc8  mov     ecx, ebx; dwErrCode
0x180005fca  call    cs:__imp_SetLastError
0x180005fd0  mov     rbx, [rsp+28h+arg_0]
0x180005fd5  mov     rsi, [rsp+28h+arg_8]
0x180005fda  add     rsp, 20h
0x180005fde  pop     rdi
0x180005fdf  retn
```
