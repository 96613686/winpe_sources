# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180009994`
- end: `0x180009a28`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006530`
- `0x1801c1df0`

## callees

- `0x180009994`
- `0x18000a090`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180009a0a`
- `KERNEL32!CloseThreadpoolTimer` at `0x180009a0a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009a01`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009a01`
- `KERNEL32!SetThreadpoolTimer` at `0x1800099f3`
- `KERNEL32!SetThreadpoolTimer` at `0x1800099f3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800099bf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800099bf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800099d5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800099d5`
- `KERNEL32!SetLastError` at `0x180009a12`
- `KERNEL32!SetLastError` at `0x180009a12`
- `KERNEL32!GetLastError` at `0x1800099e0`
- `KERNEL32!GetLastError` at `0x1800099e0`

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
0x180009994  mov     [rsp+arg_0], rbx
0x180009999  mov     [rsp+arg_8], rsi
0x18000999e  push    rdi
0x18000999f  sub     rsp, 20h
0x1800099a3  mov     dword ptr [rcx], 0
0x1800099a9  lea     rdi, [rcx+8]
0x1800099ad  mov     rsi, [rcx+10h]
0x1800099b1  mov     rbx, rcx
0x1800099b4  mov     qword ptr [rcx+10h], 0
0x1800099bc  mov     rcx, rdi; SRWLock
0x1800099bf  call    cs:__imp_AcquireSRWLockExclusive
0x1800099c5  mov     rcx, rbx
0x1800099c8  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800099cd  test    rdi, rdi
0x1800099d0  jz      short loc_1800099DB
0x1800099d2  mov     rcx, rdi; SRWLock
0x1800099d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800099db  test    rsi, rsi
0x1800099de  jz      short loc_180009A18
0x1800099e0  call    cs:__imp_GetLastError
0x1800099e6  xor     r9d, r9d; msWindowLength
0x1800099e9  xor     r8d, r8d; msPeriod
0x1800099ec  xor     edx, edx; pftDueTime
0x1800099ee  mov     rcx, rsi; pti
0x1800099f1  mov     ebx, eax
0x1800099f3  call    cs:__imp_SetThreadpoolTimer
0x1800099f9  mov     edx, 1; fCancelPendingCallbacks
0x1800099fe  mov     rcx, rsi; pti
0x180009a01  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009a07  mov     rcx, rsi; pti
0x180009a0a  call    cs:__imp_CloseThreadpoolTimer
0x180009a10  mov     ecx, ebx; dwErrCode
0x180009a12  call    cs:__imp_SetLastError
0x180009a18  mov     rbx, [rsp+28h+arg_0]
0x180009a1d  mov     rsi, [rsp+28h+arg_8]
0x180009a22  add     rsp, 20h
0x180009a26  pop     rdi
0x180009a27  retn
```
