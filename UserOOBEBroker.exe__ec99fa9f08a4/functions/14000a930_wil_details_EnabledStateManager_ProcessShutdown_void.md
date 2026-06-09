# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x14000a930`
- end: `0x14000a9c4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007ddc`
- `0x14000e9a0`

## callees

- `0x14000a930`
- `0x14000b0c8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000a9ae`
- `KERNEL32!SetLastError` at `0x14000a9ae`
- `KERNEL32!GetLastError` at `0x14000a97c`
- `KERNEL32!GetLastError` at `0x14000a97c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a95b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a95b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a971`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a971`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a98f`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a98f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a99d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a99d`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a9a6`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000a9a6`

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
0x14000a930  mov     [rsp+arg_0], rbx
0x14000a935  mov     [rsp+arg_8], rsi
0x14000a93a  push    rdi
0x14000a93b  sub     rsp, 20h
0x14000a93f  mov     dword ptr [rcx], 0
0x14000a945  lea     rdi, [rcx+8]
0x14000a949  mov     rsi, [rcx+10h]
0x14000a94d  mov     rbx, rcx
0x14000a950  mov     qword ptr [rcx+10h], 0
0x14000a958  mov     rcx, rdi; SRWLock
0x14000a95b  call    cs:__imp_AcquireSRWLockExclusive
0x14000a961  mov     rcx, rbx
0x14000a964  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x14000a969  test    rdi, rdi
0x14000a96c  jz      short loc_14000A977
0x14000a96e  mov     rcx, rdi; SRWLock
0x14000a971  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a977  test    rsi, rsi
0x14000a97a  jz      short loc_14000A9B4
0x14000a97c  call    cs:__imp_GetLastError
0x14000a982  xor     r9d, r9d; msWindowLength
0x14000a985  xor     r8d, r8d; msPeriod
0x14000a988  xor     edx, edx; pftDueTime
0x14000a98a  mov     rcx, rsi; pti
0x14000a98d  mov     ebx, eax
0x14000a98f  call    cs:__imp_SetThreadpoolTimer
0x14000a995  mov     edx, 1; fCancelPendingCallbacks
0x14000a99a  mov     rcx, rsi; pti
0x14000a99d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a9a3  mov     rcx, rsi; pti
0x14000a9a6  call    cs:__imp_CloseThreadpoolTimer
0x14000a9ac  mov     ecx, ebx; dwErrCode
0x14000a9ae  call    cs:__imp_SetLastError
0x14000a9b4  mov     rbx, [rsp+28h+arg_0]
0x14000a9b9  mov     rsi, [rsp+28h+arg_8]
0x14000a9be  add     rsp, 20h
0x14000a9c2  pop     rdi
0x14000a9c3  retn
```
