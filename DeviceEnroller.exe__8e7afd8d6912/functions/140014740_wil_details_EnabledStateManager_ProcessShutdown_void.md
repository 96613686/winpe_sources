# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140014740`
- end: `0x1400147d4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c780`
- `0x14005c0e0`

## callees

- `0x140014740`
- `0x140015468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014781`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014781`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001476b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001476b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001478c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001478c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400147be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400147be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400147b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400147b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001479f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001479f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400147ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400147ad`

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
0x140014740  mov     [rsp+arg_0], rbx
0x140014745  mov     [rsp+arg_8], rsi
0x14001474a  push    rdi
0x14001474b  sub     rsp, 20h
0x14001474f  mov     dword ptr [rcx], 0
0x140014755  lea     rdi, [rcx+8]
0x140014759  mov     rsi, [rcx+10h]
0x14001475d  mov     rbx, rcx
0x140014760  mov     qword ptr [rcx+10h], 0
0x140014768  mov     rcx, rdi; SRWLock
0x14001476b  call    cs:__imp_AcquireSRWLockExclusive
0x140014771  mov     rcx, rbx
0x140014774  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140014779  test    rdi, rdi
0x14001477c  jz      short loc_140014787
0x14001477e  mov     rcx, rdi; SRWLock
0x140014781  call    cs:__imp_ReleaseSRWLockExclusive
0x140014787  test    rsi, rsi
0x14001478a  jz      short loc_1400147C4
0x14001478c  call    cs:__imp_GetLastError
0x140014792  xor     r9d, r9d; msWindowLength
0x140014795  xor     r8d, r8d; msPeriod
0x140014798  xor     edx, edx; pftDueTime
0x14001479a  mov     rcx, rsi; pti
0x14001479d  mov     ebx, eax
0x14001479f  call    cs:__imp_SetThreadpoolTimer
0x1400147a5  mov     edx, 1; fCancelPendingCallbacks
0x1400147aa  mov     rcx, rsi; pti
0x1400147ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400147b3  mov     rcx, rsi; pti
0x1400147b6  call    cs:__imp_CloseThreadpoolTimer
0x1400147bc  mov     ecx, ebx; dwErrCode
0x1400147be  call    cs:__imp_SetLastError
0x1400147c4  mov     rbx, [rsp+28h+arg_0]
0x1400147c9  mov     rsi, [rsp+28h+arg_8]
0x1400147ce  add     rsp, 20h
0x1400147d2  pop     rdi
0x1400147d3  retn
```
