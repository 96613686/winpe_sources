# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18003a274`
- end: `0x18003a308`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180038bb4`
- `0x18006eca0`

## callees

- `0x18003a274`
- `0x18003a6c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a29f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a29f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a2b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a2b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a2c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a2c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a2f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a2f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a2d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a2d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003a2e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003a2e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a2ea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a2ea`

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
0x18003a274  mov     [rsp+arg_0], rbx
0x18003a279  mov     [rsp+arg_8], rsi
0x18003a27e  push    rdi
0x18003a27f  sub     rsp, 20h
0x18003a283  mov     dword ptr [rcx], 0
0x18003a289  lea     rdi, [rcx+8]
0x18003a28d  mov     rsi, [rcx+10h]
0x18003a291  mov     rbx, rcx
0x18003a294  mov     qword ptr [rcx+10h], 0
0x18003a29c  mov     rcx, rdi; SRWLock
0x18003a29f  call    cs:__imp_AcquireSRWLockExclusive
0x18003a2a5  mov     rcx, rbx
0x18003a2a8  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18003a2ad  test    rdi, rdi
0x18003a2b0  jz      short loc_18003A2BB
0x18003a2b2  mov     rcx, rdi; SRWLock
0x18003a2b5  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a2bb  test    rsi, rsi
0x18003a2be  jz      short loc_18003A2F8
0x18003a2c0  call    cs:__imp_GetLastError
0x18003a2c6  xor     r9d, r9d; msWindowLength
0x18003a2c9  xor     r8d, r8d; msPeriod
0x18003a2cc  xor     edx, edx; pftDueTime
0x18003a2ce  mov     rcx, rsi; pti
0x18003a2d1  mov     ebx, eax
0x18003a2d3  call    cs:__imp_SetThreadpoolTimer
0x18003a2d9  mov     edx, 1; fCancelPendingCallbacks
0x18003a2de  mov     rcx, rsi; pti
0x18003a2e1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003a2e7  mov     rcx, rsi; pti
0x18003a2ea  call    cs:__imp_CloseThreadpoolTimer
0x18003a2f0  mov     ecx, ebx; dwErrCode
0x18003a2f2  call    cs:__imp_SetLastError
0x18003a2f8  mov     rbx, [rsp+28h+arg_0]
0x18003a2fd  mov     rsi, [rsp+28h+arg_8]
0x18003a302  add     rsp, 20h
0x18003a306  pop     rdi
0x18003a307  retn
```
