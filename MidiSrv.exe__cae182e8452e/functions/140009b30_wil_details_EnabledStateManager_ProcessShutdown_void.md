# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140009b30`
- end: `0x140009bc4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007f7c`
- `0x140059270`

## callees

- `0x140009b30`
- `0x140009c14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009b5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009b5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009b71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009bae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009ba6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009ba6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009b8f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009b8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009b9d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009b9d`

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
0x140009b30  mov     [rsp+arg_0], rbx
0x140009b35  mov     [rsp+arg_8], rsi
0x140009b3a  push    rdi
0x140009b3b  sub     rsp, 20h
0x140009b3f  mov     dword ptr [rcx], 0
0x140009b45  lea     rdi, [rcx+8]
0x140009b49  mov     rsi, [rcx+10h]
0x140009b4d  mov     rbx, rcx
0x140009b50  mov     qword ptr [rcx+10h], 0
0x140009b58  mov     rcx, rdi; SRWLock
0x140009b5b  call    cs:__imp_AcquireSRWLockExclusive
0x140009b61  mov     rcx, rbx
0x140009b64  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140009b69  test    rdi, rdi
0x140009b6c  jz      short loc_140009B77
0x140009b6e  mov     rcx, rdi; SRWLock
0x140009b71  call    cs:__imp_ReleaseSRWLockExclusive
0x140009b77  test    rsi, rsi
0x140009b7a  jz      short loc_140009BB4
0x140009b7c  call    cs:__imp_GetLastError
0x140009b82  xor     r9d, r9d; msWindowLength
0x140009b85  xor     r8d, r8d; msPeriod
0x140009b88  xor     edx, edx; pftDueTime
0x140009b8a  mov     rcx, rsi; pti
0x140009b8d  mov     ebx, eax
0x140009b8f  call    cs:__imp_SetThreadpoolTimer
0x140009b95  mov     edx, 1; fCancelPendingCallbacks
0x140009b9a  mov     rcx, rsi; pti
0x140009b9d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009ba3  mov     rcx, rsi; pti
0x140009ba6  call    cs:__imp_CloseThreadpoolTimer
0x140009bac  mov     ecx, ebx; dwErrCode
0x140009bae  call    cs:__imp_SetLastError
0x140009bb4  mov     rbx, [rsp+28h+arg_0]
0x140009bb9  mov     rsi, [rsp+28h+arg_8]
0x140009bbe  add     rsp, 20h
0x140009bc2  pop     rdi
0x140009bc3  retn
```
