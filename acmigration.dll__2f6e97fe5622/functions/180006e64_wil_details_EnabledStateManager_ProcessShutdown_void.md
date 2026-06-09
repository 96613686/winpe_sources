# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180006e64`
- end: `0x180006ef8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000421c`
- `0x180068fb0`

## callees

- `0x180006e64`
- `0x18000739c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180006ec3`
- `KERNEL32!SetThreadpoolTimer` at `0x180006ec3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006e8f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006e8f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180006eda`
- `KERNEL32!CloseThreadpoolTimer` at `0x180006eda`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006ea5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006ea5`
- `KERNEL32!GetLastError` at `0x180006eb0`
- `KERNEL32!GetLastError` at `0x180006eb0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006ed1`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180006ed1`
- `KERNEL32!SetLastError` at `0x180006ee2`
- `KERNEL32!SetLastError` at `0x180006ee2`

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
0x180006e64  mov     [rsp+arg_0], rbx
0x180006e69  mov     [rsp+arg_8], rsi
0x180006e6e  push    rdi
0x180006e6f  sub     rsp, 20h
0x180006e73  mov     dword ptr [rcx], 0
0x180006e79  lea     rdi, [rcx+8]
0x180006e7d  mov     rsi, [rcx+10h]
0x180006e81  mov     rbx, rcx
0x180006e84  mov     qword ptr [rcx+10h], 0
0x180006e8c  mov     rcx, rdi; SRWLock
0x180006e8f  call    cs:__imp_AcquireSRWLockExclusive
0x180006e95  mov     rcx, rbx
0x180006e98  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180006e9d  test    rdi, rdi
0x180006ea0  jz      short loc_180006EAB
0x180006ea2  mov     rcx, rdi; SRWLock
0x180006ea5  call    cs:__imp_ReleaseSRWLockExclusive
0x180006eab  test    rsi, rsi
0x180006eae  jz      short loc_180006EE8
0x180006eb0  call    cs:__imp_GetLastError
0x180006eb6  xor     r9d, r9d; msWindowLength
0x180006eb9  xor     r8d, r8d; msPeriod
0x180006ebc  xor     edx, edx; pftDueTime
0x180006ebe  mov     rcx, rsi; pti
0x180006ec1  mov     ebx, eax
0x180006ec3  call    cs:__imp_SetThreadpoolTimer
0x180006ec9  mov     edx, 1; fCancelPendingCallbacks
0x180006ece  mov     rcx, rsi; pti
0x180006ed1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006ed7  mov     rcx, rsi; pti
0x180006eda  call    cs:__imp_CloseThreadpoolTimer
0x180006ee0  mov     ecx, ebx; dwErrCode
0x180006ee2  call    cs:__imp_SetLastError
0x180006ee8  mov     rbx, [rsp+28h+arg_0]
0x180006eed  mov     rsi, [rsp+28h+arg_8]
0x180006ef2  add     rsp, 20h
0x180006ef6  pop     rdi
0x180006ef7  retn
```
