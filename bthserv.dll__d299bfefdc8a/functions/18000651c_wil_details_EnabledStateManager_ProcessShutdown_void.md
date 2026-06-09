# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000651c`
- end: `0x1800065b0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003958`
- `0x180033b40`

## callees

- `0x18000651c`
- `0x1800069b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000655d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000655d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006547`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006568`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000659a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000659a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000657b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000657b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006592`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006592`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006589`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006589`

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
0x18000651c  mov     [rsp+arg_0], rbx
0x180006521  mov     [rsp+arg_8], rsi
0x180006526  push    rdi
0x180006527  sub     rsp, 20h
0x18000652b  mov     dword ptr [rcx], 0
0x180006531  lea     rdi, [rcx+8]
0x180006535  mov     rsi, [rcx+10h]
0x180006539  mov     rbx, rcx
0x18000653c  mov     qword ptr [rcx+10h], 0
0x180006544  mov     rcx, rdi; SRWLock
0x180006547  call    cs:__imp_AcquireSRWLockExclusive
0x18000654d  mov     rcx, rbx
0x180006550  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180006555  test    rdi, rdi
0x180006558  jz      short loc_180006563
0x18000655a  mov     rcx, rdi; SRWLock
0x18000655d  call    cs:__imp_ReleaseSRWLockExclusive
0x180006563  test    rsi, rsi
0x180006566  jz      short loc_1800065A0
0x180006568  call    cs:__imp_GetLastError
0x18000656e  xor     r9d, r9d; msWindowLength
0x180006571  xor     r8d, r8d; msPeriod
0x180006574  xor     edx, edx; pftDueTime
0x180006576  mov     rcx, rsi; pti
0x180006579  mov     ebx, eax
0x18000657b  call    cs:__imp_SetThreadpoolTimer
0x180006581  mov     edx, 1; fCancelPendingCallbacks
0x180006586  mov     rcx, rsi; pti
0x180006589  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000658f  mov     rcx, rsi; pti
0x180006592  call    cs:__imp_CloseThreadpoolTimer
0x180006598  mov     ecx, ebx; dwErrCode
0x18000659a  call    cs:__imp_SetLastError
0x1800065a0  mov     rbx, [rsp+28h+arg_0]
0x1800065a5  mov     rsi, [rsp+28h+arg_8]
0x1800065aa  add     rsp, 20h
0x1800065ae  pop     rdi
0x1800065af  retn
```
