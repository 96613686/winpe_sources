# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800088d0`
- end: `0x180008964`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fe4`
- `0x180032030`

## callees

- `0x1800088d0`
- `0x1800090c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000894e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000894e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000891c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000891c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008911`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008911`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000893d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000893d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008946`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008946`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000892f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000892f`

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
0x1800088d0  mov     [rsp+arg_0], rbx
0x1800088d5  mov     [rsp+arg_8], rsi
0x1800088da  push    rdi
0x1800088db  sub     rsp, 20h
0x1800088df  mov     dword ptr [rcx], 0
0x1800088e5  lea     rdi, [rcx+8]
0x1800088e9  mov     rsi, [rcx+10h]
0x1800088ed  mov     rbx, rcx
0x1800088f0  mov     qword ptr [rcx+10h], 0
0x1800088f8  mov     rcx, rdi; SRWLock
0x1800088fb  call    cs:__imp_AcquireSRWLockExclusive
0x180008901  mov     rcx, rbx
0x180008904  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180008909  test    rdi, rdi
0x18000890c  jz      short loc_180008917
0x18000890e  mov     rcx, rdi; SRWLock
0x180008911  call    cs:__imp_ReleaseSRWLockExclusive
0x180008917  test    rsi, rsi
0x18000891a  jz      short loc_180008954
0x18000891c  call    cs:__imp_GetLastError
0x180008922  xor     r9d, r9d; msWindowLength
0x180008925  xor     r8d, r8d; msPeriod
0x180008928  xor     edx, edx; pftDueTime
0x18000892a  mov     rcx, rsi; pti
0x18000892d  mov     ebx, eax
0x18000892f  call    cs:__imp_SetThreadpoolTimer
0x180008935  mov     edx, 1; fCancelPendingCallbacks
0x18000893a  mov     rcx, rsi; pti
0x18000893d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008943  mov     rcx, rsi; pti
0x180008946  call    cs:__imp_CloseThreadpoolTimer
0x18000894c  mov     ecx, ebx; dwErrCode
0x18000894e  call    cs:__imp_SetLastError
0x180008954  mov     rbx, [rsp+28h+arg_0]
0x180008959  mov     rsi, [rsp+28h+arg_8]
0x18000895e  add     rsp, 20h
0x180008962  pop     rdi
0x180008963  retn
```
