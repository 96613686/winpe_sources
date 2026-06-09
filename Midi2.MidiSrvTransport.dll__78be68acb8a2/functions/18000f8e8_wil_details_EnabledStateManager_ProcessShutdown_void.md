# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000f8e8`
- end: `0x18000f97c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d284`
- `0x1800145a0`

## callees

- `0x18000f8e8`
- `0x18000fbb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f913`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f913`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f929`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f929`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f966`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f934`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f955`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f955`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f95e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f95e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f947`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f947`

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
0x18000f8e8  mov     [rsp+arg_0], rbx
0x18000f8ed  mov     [rsp+arg_8], rsi
0x18000f8f2  push    rdi
0x18000f8f3  sub     rsp, 20h
0x18000f8f7  mov     dword ptr [rcx], 0
0x18000f8fd  lea     rdi, [rcx+8]
0x18000f901  mov     rsi, [rcx+10h]
0x18000f905  mov     rbx, rcx
0x18000f908  mov     qword ptr [rcx+10h], 0
0x18000f910  mov     rcx, rdi; SRWLock
0x18000f913  call    cs:__imp_AcquireSRWLockExclusive
0x18000f919  mov     rcx, rbx
0x18000f91c  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000f921  test    rdi, rdi
0x18000f924  jz      short loc_18000F92F
0x18000f926  mov     rcx, rdi; SRWLock
0x18000f929  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f92f  test    rsi, rsi
0x18000f932  jz      short loc_18000F96C
0x18000f934  call    cs:__imp_GetLastError
0x18000f93a  xor     r9d, r9d; msWindowLength
0x18000f93d  xor     r8d, r8d; msPeriod
0x18000f940  xor     edx, edx; pftDueTime
0x18000f942  mov     rcx, rsi; pti
0x18000f945  mov     ebx, eax
0x18000f947  call    cs:__imp_SetThreadpoolTimer
0x18000f94d  mov     edx, 1; fCancelPendingCallbacks
0x18000f952  mov     rcx, rsi; pti
0x18000f955  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f95b  mov     rcx, rsi; pti
0x18000f95e  call    cs:__imp_CloseThreadpoolTimer
0x18000f964  mov     ecx, ebx; dwErrCode
0x18000f966  call    cs:__imp_SetLastError
0x18000f96c  mov     rbx, [rsp+28h+arg_0]
0x18000f971  mov     rsi, [rsp+28h+arg_8]
0x18000f976  add     rsp, 20h
0x18000f97a  pop     rdi
0x18000f97b  retn
```
