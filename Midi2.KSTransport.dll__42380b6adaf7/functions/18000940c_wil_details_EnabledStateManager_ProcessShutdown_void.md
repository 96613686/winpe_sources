# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000940c`
- end: `0x1800094a0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006234`
- `0x180040760`

## callees

- `0x18000940c`
- `0x180009598`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000944d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000944d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009437`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000948a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000948a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009458`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000946b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000946b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009482`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009482`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009479`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009479`

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
0x18000940c  mov     [rsp+arg_0], rbx
0x180009411  mov     [rsp+arg_8], rsi
0x180009416  push    rdi
0x180009417  sub     rsp, 20h
0x18000941b  mov     dword ptr [rcx], 0
0x180009421  lea     rdi, [rcx+8]
0x180009425  mov     rsi, [rcx+10h]
0x180009429  mov     rbx, rcx
0x18000942c  mov     qword ptr [rcx+10h], 0
0x180009434  mov     rcx, rdi; SRWLock
0x180009437  call    cs:__imp_AcquireSRWLockExclusive
0x18000943d  mov     rcx, rbx
0x180009440  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180009445  test    rdi, rdi
0x180009448  jz      short loc_180009453
0x18000944a  mov     rcx, rdi; SRWLock
0x18000944d  call    cs:__imp_ReleaseSRWLockExclusive
0x180009453  test    rsi, rsi
0x180009456  jz      short loc_180009490
0x180009458  call    cs:__imp_GetLastError
0x18000945e  xor     r9d, r9d; msWindowLength
0x180009461  xor     r8d, r8d; msPeriod
0x180009464  xor     edx, edx; pftDueTime
0x180009466  mov     rcx, rsi; pti
0x180009469  mov     ebx, eax
0x18000946b  call    cs:__imp_SetThreadpoolTimer
0x180009471  mov     edx, 1; fCancelPendingCallbacks
0x180009476  mov     rcx, rsi; pti
0x180009479  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000947f  mov     rcx, rsi; pti
0x180009482  call    cs:__imp_CloseThreadpoolTimer
0x180009488  mov     ecx, ebx; dwErrCode
0x18000948a  call    cs:__imp_SetLastError
0x180009490  mov     rbx, [rsp+28h+arg_0]
0x180009495  mov     rsi, [rsp+28h+arg_8]
0x18000949a  add     rsp, 20h
0x18000949e  pop     rdi
0x18000949f  retn
```
