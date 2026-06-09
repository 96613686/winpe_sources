# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180016c00`
- end: `0x180016c94`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba88`
- `0x180063630`

## callees

- `0x180016c00`
- `0x180016f98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c7e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016c76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016c76`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016c5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016c5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016c6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016c6d`

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
0x180016c00  mov     [rsp+arg_0], rbx
0x180016c05  mov     [rsp+arg_8], rsi
0x180016c0a  push    rdi
0x180016c0b  sub     rsp, 20h
0x180016c0f  mov     dword ptr [rcx], 0
0x180016c15  lea     rdi, [rcx+8]
0x180016c19  mov     rsi, [rcx+10h]
0x180016c1d  mov     rbx, rcx
0x180016c20  mov     qword ptr [rcx+10h], 0
0x180016c28  mov     rcx, rdi; SRWLock
0x180016c2b  call    cs:__imp_AcquireSRWLockExclusive
0x180016c31  mov     rcx, rbx
0x180016c34  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180016c39  test    rdi, rdi
0x180016c3c  jz      short loc_180016C47
0x180016c3e  mov     rcx, rdi; SRWLock
0x180016c41  call    cs:__imp_ReleaseSRWLockExclusive
0x180016c47  test    rsi, rsi
0x180016c4a  jz      short loc_180016C84
0x180016c4c  call    cs:__imp_GetLastError
0x180016c52  xor     r9d, r9d; msWindowLength
0x180016c55  xor     r8d, r8d; msPeriod
0x180016c58  xor     edx, edx; pftDueTime
0x180016c5a  mov     rcx, rsi; pti
0x180016c5d  mov     ebx, eax
0x180016c5f  call    cs:__imp_SetThreadpoolTimer
0x180016c65  mov     edx, 1; fCancelPendingCallbacks
0x180016c6a  mov     rcx, rsi; pti
0x180016c6d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016c73  mov     rcx, rsi; pti
0x180016c76  call    cs:__imp_CloseThreadpoolTimer
0x180016c7c  mov     ecx, ebx; dwErrCode
0x180016c7e  call    cs:__imp_SetLastError
0x180016c84  mov     rbx, [rsp+28h+arg_0]
0x180016c89  mov     rsi, [rsp+28h+arg_8]
0x180016c8e  add     rsp, 20h
0x180016c92  pop     rdi
0x180016c93  retn
```
