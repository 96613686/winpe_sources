# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000e840`
- end: `0x18000e8d4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009314`
- `0x180057db0`

## callees

- `0x18000e840`
- `0x18000f134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e881`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e881`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e86b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e88c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e88c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e8be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e8be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e89f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e89f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e8b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e8b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e8ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e8ad`

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
0x18000e840  mov     [rsp+arg_0], rbx
0x18000e845  mov     [rsp+arg_8], rsi
0x18000e84a  push    rdi
0x18000e84b  sub     rsp, 20h
0x18000e84f  mov     dword ptr [rcx], 0
0x18000e855  lea     rdi, [rcx+8]
0x18000e859  mov     rsi, [rcx+10h]
0x18000e85d  mov     rbx, rcx
0x18000e860  mov     qword ptr [rcx+10h], 0
0x18000e868  mov     rcx, rdi; SRWLock
0x18000e86b  call    cs:__imp_AcquireSRWLockExclusive
0x18000e871  mov     rcx, rbx
0x18000e874  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000e879  test    rdi, rdi
0x18000e87c  jz      short loc_18000E887
0x18000e87e  mov     rcx, rdi; SRWLock
0x18000e881  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e887  test    rsi, rsi
0x18000e88a  jz      short loc_18000E8C4
0x18000e88c  call    cs:__imp_GetLastError
0x18000e892  xor     r9d, r9d; msWindowLength
0x18000e895  xor     r8d, r8d; msPeriod
0x18000e898  xor     edx, edx; pftDueTime
0x18000e89a  mov     rcx, rsi; pti
0x18000e89d  mov     ebx, eax
0x18000e89f  call    cs:__imp_SetThreadpoolTimer
0x18000e8a5  mov     edx, 1; fCancelPendingCallbacks
0x18000e8aa  mov     rcx, rsi; pti
0x18000e8ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e8b3  mov     rcx, rsi; pti
0x18000e8b6  call    cs:__imp_CloseThreadpoolTimer
0x18000e8bc  mov     ecx, ebx; dwErrCode
0x18000e8be  call    cs:__imp_SetLastError
0x18000e8c4  mov     rbx, [rsp+28h+arg_0]
0x18000e8c9  mov     rsi, [rsp+28h+arg_8]
0x18000e8ce  add     rsp, 20h
0x18000e8d2  pop     rdi
0x18000e8d3  retn
```
