# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800136e4`
- end: `0x180013778`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012234`
- `0x18004eb70`

## callees

- `0x1800136e4`
- `0x180013cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013725`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013725`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001370f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001370f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013730`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013762`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013762`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001375a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001375a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013751`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013751`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013743`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013743`

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
0x1800136e4  mov     [rsp+arg_0], rbx
0x1800136e9  mov     [rsp+arg_8], rsi
0x1800136ee  push    rdi
0x1800136ef  sub     rsp, 20h
0x1800136f3  mov     dword ptr [rcx], 0
0x1800136f9  lea     rdi, [rcx+8]
0x1800136fd  mov     rsi, [rcx+10h]
0x180013701  mov     rbx, rcx
0x180013704  mov     qword ptr [rcx+10h], 0
0x18001370c  mov     rcx, rdi; SRWLock
0x18001370f  call    cs:__imp_AcquireSRWLockExclusive
0x180013715  mov     rcx, rbx
0x180013718  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18001371d  test    rdi, rdi
0x180013720  jz      short loc_18001372B
0x180013722  mov     rcx, rdi; SRWLock
0x180013725  call    cs:__imp_ReleaseSRWLockExclusive
0x18001372b  test    rsi, rsi
0x18001372e  jz      short loc_180013768
0x180013730  call    cs:__imp_GetLastError
0x180013736  xor     r9d, r9d; msWindowLength
0x180013739  xor     r8d, r8d; msPeriod
0x18001373c  xor     edx, edx; pftDueTime
0x18001373e  mov     rcx, rsi; pti
0x180013741  mov     ebx, eax
0x180013743  call    cs:__imp_SetThreadpoolTimer
0x180013749  mov     edx, 1; fCancelPendingCallbacks
0x18001374e  mov     rcx, rsi; pti
0x180013751  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013757  mov     rcx, rsi; pti
0x18001375a  call    cs:__imp_CloseThreadpoolTimer
0x180013760  mov     ecx, ebx; dwErrCode
0x180013762  call    cs:__imp_SetLastError
0x180013768  mov     rbx, [rsp+28h+arg_0]
0x18001376d  mov     rsi, [rsp+28h+arg_8]
0x180013772  add     rsp, 20h
0x180013776  pop     rdi
0x180013777  retn
```
