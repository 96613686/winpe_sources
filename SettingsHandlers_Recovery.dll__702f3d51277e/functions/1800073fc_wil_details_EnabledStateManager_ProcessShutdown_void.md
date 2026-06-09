# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800073fc`
- end: `0x180007490`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800045d0`
- `0x18002aac0`

## callees

- `0x1800073fc`
- `0x180007910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007427`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007427`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000743d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000743d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000747a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000747a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007448`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007472`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007472`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000745b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000745b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007469`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007469`

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
0x1800073fc  mov     [rsp+arg_0], rbx
0x180007401  mov     [rsp+arg_8], rsi
0x180007406  push    rdi
0x180007407  sub     rsp, 20h
0x18000740b  mov     dword ptr [rcx], 0
0x180007411  lea     rdi, [rcx+8]
0x180007415  mov     rsi, [rcx+10h]
0x180007419  mov     rbx, rcx
0x18000741c  mov     qword ptr [rcx+10h], 0
0x180007424  mov     rcx, rdi; SRWLock
0x180007427  call    cs:__imp_AcquireSRWLockExclusive
0x18000742d  mov     rcx, rbx
0x180007430  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180007435  test    rdi, rdi
0x180007438  jz      short loc_180007443
0x18000743a  mov     rcx, rdi; SRWLock
0x18000743d  call    cs:__imp_ReleaseSRWLockExclusive
0x180007443  test    rsi, rsi
0x180007446  jz      short loc_180007480
0x180007448  call    cs:__imp_GetLastError
0x18000744e  xor     r9d, r9d; msWindowLength
0x180007451  xor     r8d, r8d; msPeriod
0x180007454  xor     edx, edx; pftDueTime
0x180007456  mov     rcx, rsi; pti
0x180007459  mov     ebx, eax
0x18000745b  call    cs:__imp_SetThreadpoolTimer
0x180007461  mov     edx, 1; fCancelPendingCallbacks
0x180007466  mov     rcx, rsi; pti
0x180007469  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000746f  mov     rcx, rsi; pti
0x180007472  call    cs:__imp_CloseThreadpoolTimer
0x180007478  mov     ecx, ebx; dwErrCode
0x18000747a  call    cs:__imp_SetLastError
0x180007480  mov     rbx, [rsp+28h+arg_0]
0x180007485  mov     rsi, [rsp+28h+arg_8]
0x18000748a  add     rsp, 20h
0x18000748e  pop     rdi
0x18000748f  retn
```
