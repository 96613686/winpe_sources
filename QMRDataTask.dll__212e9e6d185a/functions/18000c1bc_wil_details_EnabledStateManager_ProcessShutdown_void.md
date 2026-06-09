# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000c1bc`
- end: `0x18000c250`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059cc`
- `0x180014990`

## callees

- `0x18000c1bc`
- `0x18000cbe4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c208`
- `KERNEL32!GetLastError` at `0x18000c208`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c21b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000c21b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c1e7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c1e7`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c232`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000c232`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c1fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c1fd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c229`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000c229`
- `KERNEL32!SetLastError` at `0x18000c23a`
- `KERNEL32!SetLastError` at `0x18000c23a`

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
0x18000c1bc  mov     [rsp+arg_0], rbx
0x18000c1c1  mov     [rsp+arg_8], rsi
0x18000c1c6  push    rdi
0x18000c1c7  sub     rsp, 20h
0x18000c1cb  mov     dword ptr [rcx], 0
0x18000c1d1  lea     rdi, [rcx+8]
0x18000c1d5  mov     rsi, [rcx+10h]
0x18000c1d9  mov     rbx, rcx
0x18000c1dc  mov     qword ptr [rcx+10h], 0
0x18000c1e4  mov     rcx, rdi; SRWLock
0x18000c1e7  call    cs:__imp_AcquireSRWLockExclusive
0x18000c1ed  mov     rcx, rbx
0x18000c1f0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000c1f5  test    rdi, rdi
0x18000c1f8  jz      short loc_18000C203
0x18000c1fa  mov     rcx, rdi; SRWLock
0x18000c1fd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c203  test    rsi, rsi
0x18000c206  jz      short loc_18000C240
0x18000c208  call    cs:__imp_GetLastError
0x18000c20e  xor     r9d, r9d; msWindowLength
0x18000c211  xor     r8d, r8d; msPeriod
0x18000c214  xor     edx, edx; pftDueTime
0x18000c216  mov     rcx, rsi; pti
0x18000c219  mov     ebx, eax
0x18000c21b  call    cs:__imp_SetThreadpoolTimer
0x18000c221  mov     edx, 1; fCancelPendingCallbacks
0x18000c226  mov     rcx, rsi; pti
0x18000c229  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c22f  mov     rcx, rsi; pti
0x18000c232  call    cs:__imp_CloseThreadpoolTimer
0x18000c238  mov     ecx, ebx; dwErrCode
0x18000c23a  call    cs:__imp_SetLastError
0x18000c240  mov     rbx, [rsp+28h+arg_0]
0x18000c245  mov     rsi, [rsp+28h+arg_8]
0x18000c24a  add     rsp, 20h
0x18000c24e  pop     rdi
0x18000c24f  retn
```
