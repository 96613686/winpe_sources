# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140006f2c`
- end: `0x140006fc0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003e88`
- `0x1400a7b50`

## callees

- `0x140006f2c`
- `0x140007538`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006f57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140006f57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006f6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140006f6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006faa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f78`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006f99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006f99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006fa2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006fa2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f8b`

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
0x140006f2c  mov     [rsp+arg_0], rbx
0x140006f31  mov     [rsp+arg_8], rsi
0x140006f36  push    rdi
0x140006f37  sub     rsp, 20h
0x140006f3b  mov     dword ptr [rcx], 0
0x140006f41  lea     rdi, [rcx+8]
0x140006f45  mov     rsi, [rcx+10h]
0x140006f49  mov     rbx, rcx
0x140006f4c  mov     qword ptr [rcx+10h], 0
0x140006f54  mov     rcx, rdi; SRWLock
0x140006f57  call    cs:__imp_AcquireSRWLockExclusive
0x140006f5d  mov     rcx, rbx
0x140006f60  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140006f65  test    rdi, rdi
0x140006f68  jz      short loc_140006F73
0x140006f6a  mov     rcx, rdi; SRWLock
0x140006f6d  call    cs:__imp_ReleaseSRWLockExclusive
0x140006f73  test    rsi, rsi
0x140006f76  jz      short loc_140006FB0
0x140006f78  call    cs:__imp_GetLastError
0x140006f7e  xor     r9d, r9d; msWindowLength
0x140006f81  xor     r8d, r8d; msPeriod
0x140006f84  xor     edx, edx; pftDueTime
0x140006f86  mov     rcx, rsi; pti
0x140006f89  mov     ebx, eax
0x140006f8b  call    cs:__imp_SetThreadpoolTimer
0x140006f91  mov     edx, 1; fCancelPendingCallbacks
0x140006f96  mov     rcx, rsi; pti
0x140006f99  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006f9f  mov     rcx, rsi; pti
0x140006fa2  call    cs:__imp_CloseThreadpoolTimer
0x140006fa8  mov     ecx, ebx; dwErrCode
0x140006faa  call    cs:__imp_SetLastError
0x140006fb0  mov     rbx, [rsp+28h+arg_0]
0x140006fb5  mov     rsi, [rsp+28h+arg_8]
0x140006fba  add     rsp, 20h
0x140006fbe  pop     rdi
0x140006fbf  retn
```
