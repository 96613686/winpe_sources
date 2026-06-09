# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180008d3c`
- end: `0x180008dd0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006058`
- `0x180067080`

## callees

- `0x180008d3c`
- `0x1800091d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d9b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008db2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008db2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008da9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008da9`

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
0x180008d3c  mov     [rsp+arg_0], rbx
0x180008d41  mov     [rsp+arg_8], rsi
0x180008d46  push    rdi
0x180008d47  sub     rsp, 20h
0x180008d4b  mov     dword ptr [rcx], 0
0x180008d51  lea     rdi, [rcx+8]
0x180008d55  mov     rsi, [rcx+10h]
0x180008d59  mov     rbx, rcx
0x180008d5c  mov     qword ptr [rcx+10h], 0
0x180008d64  mov     rcx, rdi; SRWLock
0x180008d67  call    cs:__imp_AcquireSRWLockExclusive
0x180008d6d  mov     rcx, rbx
0x180008d70  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180008d75  test    rdi, rdi
0x180008d78  jz      short loc_180008D83
0x180008d7a  mov     rcx, rdi; SRWLock
0x180008d7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180008d83  test    rsi, rsi
0x180008d86  jz      short loc_180008DC0
0x180008d88  call    cs:__imp_GetLastError
0x180008d8e  xor     r9d, r9d; msWindowLength
0x180008d91  xor     r8d, r8d; msPeriod
0x180008d94  xor     edx, edx; pftDueTime
0x180008d96  mov     rcx, rsi; pti
0x180008d99  mov     ebx, eax
0x180008d9b  call    cs:__imp_SetThreadpoolTimer
0x180008da1  mov     edx, 1; fCancelPendingCallbacks
0x180008da6  mov     rcx, rsi; pti
0x180008da9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008daf  mov     rcx, rsi; pti
0x180008db2  call    cs:__imp_CloseThreadpoolTimer
0x180008db8  mov     ecx, ebx; dwErrCode
0x180008dba  call    cs:__imp_SetLastError
0x180008dc0  mov     rbx, [rsp+28h+arg_0]
0x180008dc5  mov     rsi, [rsp+28h+arg_8]
0x180008dca  add     rsp, 20h
0x180008dce  pop     rdi
0x180008dcf  retn
```
