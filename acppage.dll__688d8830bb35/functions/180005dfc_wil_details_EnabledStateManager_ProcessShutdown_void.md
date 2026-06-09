# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180005dfc`
- end: `0x180005e90`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003254`
- `0x1800167f0`

## callees

- `0x180005dfc`
- `0x180006224`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180005e7a`
- `KERNEL32!SetLastError` at `0x180005e7a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005e69`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180005e69`
- `KERNEL32!GetLastError` at `0x180005e48`
- `KERNEL32!GetLastError` at `0x180005e48`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005e3d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005e3d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005e72`
- `KERNEL32!CloseThreadpoolTimer` at `0x180005e72`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005e27`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005e27`
- `KERNEL32!SetThreadpoolTimer` at `0x180005e5b`
- `KERNEL32!SetThreadpoolTimer` at `0x180005e5b`

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
0x180005dfc  mov     [rsp+arg_0], rbx
0x180005e01  mov     [rsp+arg_8], rsi
0x180005e06  push    rdi
0x180005e07  sub     rsp, 20h
0x180005e0b  mov     dword ptr [rcx], 0
0x180005e11  lea     rdi, [rcx+8]
0x180005e15  mov     rsi, [rcx+10h]
0x180005e19  mov     rbx, rcx
0x180005e1c  mov     qword ptr [rcx+10h], 0
0x180005e24  mov     rcx, rdi; SRWLock
0x180005e27  call    cs:__imp_AcquireSRWLockExclusive
0x180005e2d  mov     rcx, rbx
0x180005e30  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180005e35  test    rdi, rdi
0x180005e38  jz      short loc_180005E43
0x180005e3a  mov     rcx, rdi; SRWLock
0x180005e3d  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e43  test    rsi, rsi
0x180005e46  jz      short loc_180005E80
0x180005e48  call    cs:__imp_GetLastError
0x180005e4e  xor     r9d, r9d; msWindowLength
0x180005e51  xor     r8d, r8d; msPeriod
0x180005e54  xor     edx, edx; pftDueTime
0x180005e56  mov     rcx, rsi; pti
0x180005e59  mov     ebx, eax
0x180005e5b  call    cs:__imp_SetThreadpoolTimer
0x180005e61  mov     edx, 1; fCancelPendingCallbacks
0x180005e66  mov     rcx, rsi; pti
0x180005e69  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005e6f  mov     rcx, rsi; pti
0x180005e72  call    cs:__imp_CloseThreadpoolTimer
0x180005e78  mov     ecx, ebx; dwErrCode
0x180005e7a  call    cs:__imp_SetLastError
0x180005e80  mov     rbx, [rsp+28h+arg_0]
0x180005e85  mov     rsi, [rsp+28h+arg_8]
0x180005e8a  add     rsp, 20h
0x180005e8e  pop     rdi
0x180005e8f  retn
```
