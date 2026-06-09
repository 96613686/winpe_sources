# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000629c`
- end: `0x180006330`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003778`
- `0x180029b20`

## callees

- `0x18000629c`
- `0x1800066e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800062dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800062dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800062c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800062c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000631a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000631a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006312`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006312`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006309`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006309`

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
0x18000629c  mov     [rsp+arg_0], rbx
0x1800062a1  mov     [rsp+arg_8], rsi
0x1800062a6  push    rdi
0x1800062a7  sub     rsp, 20h
0x1800062ab  mov     dword ptr [rcx], 0
0x1800062b1  lea     rdi, [rcx+8]
0x1800062b5  mov     rsi, [rcx+10h]
0x1800062b9  mov     rbx, rcx
0x1800062bc  mov     qword ptr [rcx+10h], 0
0x1800062c4  mov     rcx, rdi; SRWLock
0x1800062c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800062cd  mov     rcx, rbx
0x1800062d0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800062d5  test    rdi, rdi
0x1800062d8  jz      short loc_1800062E3
0x1800062da  mov     rcx, rdi; SRWLock
0x1800062dd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800062e3  test    rsi, rsi
0x1800062e6  jz      short loc_180006320
0x1800062e8  call    cs:__imp_GetLastError
0x1800062ee  xor     r9d, r9d; msWindowLength
0x1800062f1  xor     r8d, r8d; msPeriod
0x1800062f4  xor     edx, edx; pftDueTime
0x1800062f6  mov     rcx, rsi; pti
0x1800062f9  mov     ebx, eax
0x1800062fb  call    cs:__imp_SetThreadpoolTimer
0x180006301  mov     edx, 1; fCancelPendingCallbacks
0x180006306  mov     rcx, rsi; pti
0x180006309  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000630f  mov     rcx, rsi; pti
0x180006312  call    cs:__imp_CloseThreadpoolTimer
0x180006318  mov     ecx, ebx; dwErrCode
0x18000631a  call    cs:__imp_SetLastError
0x180006320  mov     rbx, [rsp+28h+arg_0]
0x180006325  mov     rsi, [rsp+28h+arg_8]
0x18000632a  add     rsp, 20h
0x18000632e  pop     rdi
0x18000632f  retn
```
