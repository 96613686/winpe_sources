# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180010e04`
- end: `0x180010e98`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d5e8`
- `0x180020db0`

## callees

- `0x180010e04`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010e45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010e82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010e82`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010e71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010e71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010e63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010e63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010e7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010e7a`

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
0x180010e04  mov     [rsp+arg_0], rbx
0x180010e09  mov     [rsp+arg_8], rsi
0x180010e0e  push    rdi
0x180010e0f  sub     rsp, 20h
0x180010e13  mov     dword ptr [rcx], 0
0x180010e19  lea     rdi, [rcx+8]
0x180010e1d  mov     rsi, [rcx+10h]
0x180010e21  mov     rbx, rcx
0x180010e24  mov     qword ptr [rcx+10h], 0
0x180010e2c  mov     rcx, rdi; SRWLock
0x180010e2f  call    cs:__imp_AcquireSRWLockExclusive
0x180010e35  mov     rcx, rbx
0x180010e38  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180010e3d  test    rdi, rdi
0x180010e40  jz      short loc_180010E4B
0x180010e42  mov     rcx, rdi; SRWLock
0x180010e45  call    cs:__imp_ReleaseSRWLockExclusive
0x180010e4b  test    rsi, rsi
0x180010e4e  jz      short loc_180010E88
0x180010e50  call    cs:__imp_GetLastError
0x180010e56  xor     r9d, r9d; msWindowLength
0x180010e59  xor     r8d, r8d; msPeriod
0x180010e5c  xor     edx, edx; pftDueTime
0x180010e5e  mov     rcx, rsi; pti
0x180010e61  mov     ebx, eax
0x180010e63  call    cs:__imp_SetThreadpoolTimer
0x180010e69  mov     edx, 1; fCancelPendingCallbacks
0x180010e6e  mov     rcx, rsi; pti
0x180010e71  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010e77  mov     rcx, rsi; pti
0x180010e7a  call    cs:__imp_CloseThreadpoolTimer
0x180010e80  mov     ecx, ebx; dwErrCode
0x180010e82  call    cs:__imp_SetLastError
0x180010e88  mov     rbx, [rsp+28h+arg_0]
0x180010e8d  mov     rsi, [rsp+28h+arg_8]
0x180010e92  add     rsp, 20h
0x180010e96  pop     rdi
0x180010e97  retn
```
