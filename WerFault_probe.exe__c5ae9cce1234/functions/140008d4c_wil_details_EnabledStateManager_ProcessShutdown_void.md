# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140008d4c`
- end: `0x140008de0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ab4`
- `0x14005c7c0`

## callees

- `0x140008d4c`
- `0x140009358`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008d77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008d77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008d8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008d8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008dca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008dca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008dc2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008dc2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008db9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008db9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008dab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008dab`

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
0x140008d4c  mov     [rsp+arg_0], rbx
0x140008d51  mov     [rsp+arg_8], rsi
0x140008d56  push    rdi
0x140008d57  sub     rsp, 20h
0x140008d5b  mov     dword ptr [rcx], 0
0x140008d61  lea     rdi, [rcx+8]
0x140008d65  mov     rsi, [rcx+10h]
0x140008d69  mov     rbx, rcx
0x140008d6c  mov     qword ptr [rcx+10h], 0
0x140008d74  mov     rcx, rdi; SRWLock
0x140008d77  call    cs:__imp_AcquireSRWLockExclusive
0x140008d7d  mov     rcx, rbx
0x140008d80  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140008d85  test    rdi, rdi
0x140008d88  jz      short loc_140008D93
0x140008d8a  mov     rcx, rdi; SRWLock
0x140008d8d  call    cs:__imp_ReleaseSRWLockExclusive
0x140008d93  test    rsi, rsi
0x140008d96  jz      short loc_140008DD0
0x140008d98  call    cs:__imp_GetLastError
0x140008d9e  xor     r9d, r9d; msWindowLength
0x140008da1  xor     r8d, r8d; msPeriod
0x140008da4  xor     edx, edx; pftDueTime
0x140008da6  mov     rcx, rsi; pti
0x140008da9  mov     ebx, eax
0x140008dab  call    cs:__imp_SetThreadpoolTimer
0x140008db1  mov     edx, 1; fCancelPendingCallbacks
0x140008db6  mov     rcx, rsi; pti
0x140008db9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008dbf  mov     rcx, rsi; pti
0x140008dc2  call    cs:__imp_CloseThreadpoolTimer
0x140008dc8  mov     ecx, ebx; dwErrCode
0x140008dca  call    cs:__imp_SetLastError
0x140008dd0  mov     rbx, [rsp+28h+arg_0]
0x140008dd5  mov     rsi, [rsp+28h+arg_8]
0x140008dda  add     rsp, 20h
0x140008dde  pop     rdi
0x140008ddf  retn
```
