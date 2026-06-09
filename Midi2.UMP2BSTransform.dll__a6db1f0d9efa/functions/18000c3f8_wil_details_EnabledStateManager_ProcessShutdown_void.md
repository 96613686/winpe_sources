# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000c3f8`
- end: `0x18000c48c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a958`
- `0x18000ecc0`

## callees

- `0x18000c3f8`
- `0x18000c604`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c423`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c423`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c439`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c476`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c444`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c46e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c46e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c457`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c457`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c465`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c465`

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
0x18000c3f8  mov     [rsp+arg_0], rbx
0x18000c3fd  mov     [rsp+arg_8], rsi
0x18000c402  push    rdi
0x18000c403  sub     rsp, 20h
0x18000c407  mov     dword ptr [rcx], 0
0x18000c40d  lea     rdi, [rcx+8]
0x18000c411  mov     rsi, [rcx+10h]
0x18000c415  mov     rbx, rcx
0x18000c418  mov     qword ptr [rcx+10h], 0
0x18000c420  mov     rcx, rdi; SRWLock
0x18000c423  call    cs:__imp_AcquireSRWLockExclusive
0x18000c429  mov     rcx, rbx
0x18000c42c  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000c431  test    rdi, rdi
0x18000c434  jz      short loc_18000C43F
0x18000c436  mov     rcx, rdi; SRWLock
0x18000c439  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c43f  test    rsi, rsi
0x18000c442  jz      short loc_18000C47C
0x18000c444  call    cs:__imp_GetLastError
0x18000c44a  xor     r9d, r9d; msWindowLength
0x18000c44d  xor     r8d, r8d; msPeriod
0x18000c450  xor     edx, edx; pftDueTime
0x18000c452  mov     rcx, rsi; pti
0x18000c455  mov     ebx, eax
0x18000c457  call    cs:__imp_SetThreadpoolTimer
0x18000c45d  mov     edx, 1; fCancelPendingCallbacks
0x18000c462  mov     rcx, rsi; pti
0x18000c465  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c46b  mov     rcx, rsi; pti
0x18000c46e  call    cs:__imp_CloseThreadpoolTimer
0x18000c474  mov     ecx, ebx; dwErrCode
0x18000c476  call    cs:__imp_SetLastError
0x18000c47c  mov     rbx, [rsp+28h+arg_0]
0x18000c481  mov     rsi, [rsp+28h+arg_8]
0x18000c486  add     rsp, 20h
0x18000c48a  pop     rdi
0x18000c48b  retn
```
