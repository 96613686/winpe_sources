# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000b900`
- end: `0x18000b994`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009da4`
- `0x180069bf0`

## callees

- `0x18000b900`
- `0x18000bf20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b94c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b94c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b97e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b97e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b941`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b941`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b92b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b92b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b976`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b976`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b95f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b95f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b96d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b96d`

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
0x18000b900  mov     [rsp+arg_0], rbx
0x18000b905  mov     [rsp+arg_8], rsi
0x18000b90a  push    rdi
0x18000b90b  sub     rsp, 20h
0x18000b90f  mov     dword ptr [rcx], 0
0x18000b915  lea     rdi, [rcx+8]
0x18000b919  mov     rsi, [rcx+10h]
0x18000b91d  mov     rbx, rcx
0x18000b920  mov     qword ptr [rcx+10h], 0
0x18000b928  mov     rcx, rdi; SRWLock
0x18000b92b  call    cs:__imp_AcquireSRWLockExclusive
0x18000b931  mov     rcx, rbx
0x18000b934  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000b939  test    rdi, rdi
0x18000b93c  jz      short loc_18000B947
0x18000b93e  mov     rcx, rdi; SRWLock
0x18000b941  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b947  test    rsi, rsi
0x18000b94a  jz      short loc_18000B984
0x18000b94c  call    cs:__imp_GetLastError
0x18000b952  xor     r9d, r9d; msWindowLength
0x18000b955  xor     r8d, r8d; msPeriod
0x18000b958  xor     edx, edx; pftDueTime
0x18000b95a  mov     rcx, rsi; pti
0x18000b95d  mov     ebx, eax
0x18000b95f  call    cs:__imp_SetThreadpoolTimer
0x18000b965  mov     edx, 1; fCancelPendingCallbacks
0x18000b96a  mov     rcx, rsi; pti
0x18000b96d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b973  mov     rcx, rsi; pti
0x18000b976  call    cs:__imp_CloseThreadpoolTimer
0x18000b97c  mov     ecx, ebx; dwErrCode
0x18000b97e  call    cs:__imp_SetLastError
0x18000b984  mov     rbx, [rsp+28h+arg_0]
0x18000b989  mov     rsi, [rsp+28h+arg_8]
0x18000b98e  add     rsp, 20h
0x18000b992  pop     rdi
0x18000b993  retn
```
