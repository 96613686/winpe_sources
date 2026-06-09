# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18002d778`
- end: `0x18002d80c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f830`
- `0x18008df70`

## callees

- `0x18002d778`
- `0x18002e284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d7a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d7a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d7b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d7b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d7f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d7f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d7d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d7d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d7ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d7ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d7e5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d7e5`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rsi
  struct _TP_TIMER *Ptr; // rdi
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
0x18002d778  mov     [rsp+arg_8], rbx
0x18002d77d  mov     [rsp+arg_10], rsi
0x18002d782  push    rdi
0x18002d783  sub     rsp, 20h
0x18002d787  mov     dword ptr [rcx], 0
0x18002d78d  lea     rsi, [rcx+8]
0x18002d791  mov     rdi, [rcx+10h]
0x18002d795  mov     rbx, rcx
0x18002d798  mov     qword ptr [rcx+10h], 0
0x18002d7a0  mov     rcx, rsi; SRWLock
0x18002d7a3  call    cs:__imp_AcquireSRWLockExclusive
0x18002d7a9  mov     rcx, rbx
0x18002d7ac  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18002d7b1  test    rsi, rsi
0x18002d7b4  jz      short loc_18002D7BF
0x18002d7b6  mov     rcx, rsi; SRWLock
0x18002d7b9  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d7bf  test    rdi, rdi
0x18002d7c2  jz      short loc_18002D7FC
0x18002d7c4  call    cs:__imp_GetLastError
0x18002d7ca  xor     r9d, r9d; msWindowLength
0x18002d7cd  xor     r8d, r8d; msPeriod
0x18002d7d0  xor     edx, edx; pftDueTime
0x18002d7d2  mov     rcx, rdi; pti
0x18002d7d5  mov     ebx, eax
0x18002d7d7  call    cs:__imp_SetThreadpoolTimer
0x18002d7dd  mov     edx, 1; fCancelPendingCallbacks
0x18002d7e2  mov     rcx, rdi; pti
0x18002d7e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002d7eb  mov     rcx, rdi; pti
0x18002d7ee  call    cs:__imp_CloseThreadpoolTimer
0x18002d7f4  mov     ecx, ebx; dwErrCode
0x18002d7f6  call    cs:__imp_SetLastError
0x18002d7fc  mov     rbx, [rsp+28h+arg_8]
0x18002d801  mov     rsi, [rsp+28h+arg_10]
0x18002d806  add     rsp, 20h
0x18002d80a  pop     rdi
0x18002d80b  retn
```
