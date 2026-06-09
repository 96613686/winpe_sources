# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180013dd4`
- end: `0x180013e68`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010edc`
- `0x18001a0f0`

## callees

- `0x180013dd4`
- `0x180014398`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013e15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013e15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013dff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013dff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013e52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e20`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013e41`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013e41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013e4a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013e4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013e33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013e33`

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
0x180013dd4  mov     [rsp+arg_0], rbx
0x180013dd9  mov     [rsp+arg_8], rsi
0x180013dde  push    rdi
0x180013ddf  sub     rsp, 20h
0x180013de3  mov     dword ptr [rcx], 0
0x180013de9  lea     rdi, [rcx+8]
0x180013ded  mov     rsi, [rcx+10h]
0x180013df1  mov     rbx, rcx
0x180013df4  mov     qword ptr [rcx+10h], 0
0x180013dfc  mov     rcx, rdi; SRWLock
0x180013dff  call    cs:__imp_AcquireSRWLockExclusive
0x180013e05  mov     rcx, rbx
0x180013e08  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180013e0d  test    rdi, rdi
0x180013e10  jz      short loc_180013E1B
0x180013e12  mov     rcx, rdi; SRWLock
0x180013e15  call    cs:__imp_ReleaseSRWLockExclusive
0x180013e1b  test    rsi, rsi
0x180013e1e  jz      short loc_180013E58
0x180013e20  call    cs:__imp_GetLastError
0x180013e26  xor     r9d, r9d; msWindowLength
0x180013e29  xor     r8d, r8d; msPeriod
0x180013e2c  xor     edx, edx; pftDueTime
0x180013e2e  mov     rcx, rsi; pti
0x180013e31  mov     ebx, eax
0x180013e33  call    cs:__imp_SetThreadpoolTimer
0x180013e39  mov     edx, 1; fCancelPendingCallbacks
0x180013e3e  mov     rcx, rsi; pti
0x180013e41  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013e47  mov     rcx, rsi; pti
0x180013e4a  call    cs:__imp_CloseThreadpoolTimer
0x180013e50  mov     ecx, ebx; dwErrCode
0x180013e52  call    cs:__imp_SetLastError
0x180013e58  mov     rbx, [rsp+28h+arg_0]
0x180013e5d  mov     rsi, [rsp+28h+arg_8]
0x180013e62  add     rsp, 20h
0x180013e66  pop     rdi
0x180013e67  retn
```
