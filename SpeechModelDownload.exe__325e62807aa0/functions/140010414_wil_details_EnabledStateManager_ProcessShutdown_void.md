# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140010414`
- end: `0x1400104a8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b2f8`
- `0x14001c5a0`

## callees

- `0x140010414`
- `0x140010f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010455`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010455`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001043f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001043f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010460`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010492`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010492`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010473`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010473`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001048a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001048a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010481`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010481`

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
0x140010414  mov     [rsp+arg_0], rbx
0x140010419  mov     [rsp+arg_8], rsi
0x14001041e  push    rdi
0x14001041f  sub     rsp, 20h
0x140010423  mov     dword ptr [rcx], 0
0x140010429  lea     rdi, [rcx+8]
0x14001042d  mov     rsi, [rcx+10h]
0x140010431  mov     rbx, rcx
0x140010434  mov     qword ptr [rcx+10h], 0
0x14001043c  mov     rcx, rdi; SRWLock
0x14001043f  call    cs:__imp_AcquireSRWLockExclusive
0x140010445  mov     rcx, rbx
0x140010448  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x14001044d  test    rdi, rdi
0x140010450  jz      short loc_14001045B
0x140010452  mov     rcx, rdi; SRWLock
0x140010455  call    cs:__imp_ReleaseSRWLockExclusive
0x14001045b  test    rsi, rsi
0x14001045e  jz      short loc_140010498
0x140010460  call    cs:__imp_GetLastError
0x140010466  xor     r9d, r9d; msWindowLength
0x140010469  xor     r8d, r8d; msPeriod
0x14001046c  xor     edx, edx; pftDueTime
0x14001046e  mov     rcx, rsi; pti
0x140010471  mov     ebx, eax
0x140010473  call    cs:__imp_SetThreadpoolTimer
0x140010479  mov     edx, 1; fCancelPendingCallbacks
0x14001047e  mov     rcx, rsi; pti
0x140010481  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010487  mov     rcx, rsi; pti
0x14001048a  call    cs:__imp_CloseThreadpoolTimer
0x140010490  mov     ecx, ebx; dwErrCode
0x140010492  call    cs:__imp_SetLastError
0x140010498  mov     rbx, [rsp+28h+arg_0]
0x14001049d  mov     rsi, [rsp+28h+arg_8]
0x1400104a2  add     rsp, 20h
0x1400104a6  pop     rdi
0x1400104a7  retn
```
