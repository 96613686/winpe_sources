# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000f7d4`
- end: `0x18000f868`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c9d0`
- `0x1800125b0`

## callees

- `0x18000f7d4`
- `0x18000f9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f7ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f7ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f815`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f815`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f852`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f820`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f84a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f84a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f841`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f841`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f833`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f833`

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
0x18000f7d4  mov     [rsp+arg_0], rbx
0x18000f7d9  mov     [rsp+arg_8], rsi
0x18000f7de  push    rdi
0x18000f7df  sub     rsp, 20h
0x18000f7e3  mov     dword ptr [rcx], 0
0x18000f7e9  lea     rdi, [rcx+8]
0x18000f7ed  mov     rsi, [rcx+10h]
0x18000f7f1  mov     rbx, rcx
0x18000f7f4  mov     qword ptr [rcx+10h], 0
0x18000f7fc  mov     rcx, rdi; SRWLock
0x18000f7ff  call    cs:__imp_AcquireSRWLockExclusive
0x18000f805  mov     rcx, rbx
0x18000f808  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000f80d  test    rdi, rdi
0x18000f810  jz      short loc_18000F81B
0x18000f812  mov     rcx, rdi; SRWLock
0x18000f815  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f81b  test    rsi, rsi
0x18000f81e  jz      short loc_18000F858
0x18000f820  call    cs:__imp_GetLastError
0x18000f826  xor     r9d, r9d; msWindowLength
0x18000f829  xor     r8d, r8d; msPeriod
0x18000f82c  xor     edx, edx; pftDueTime
0x18000f82e  mov     rcx, rsi; pti
0x18000f831  mov     ebx, eax
0x18000f833  call    cs:__imp_SetThreadpoolTimer
0x18000f839  mov     edx, 1; fCancelPendingCallbacks
0x18000f83e  mov     rcx, rsi; pti
0x18000f841  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f847  mov     rcx, rsi; pti
0x18000f84a  call    cs:__imp_CloseThreadpoolTimer
0x18000f850  mov     ecx, ebx; dwErrCode
0x18000f852  call    cs:__imp_SetLastError
0x18000f858  mov     rbx, [rsp+28h+arg_0]
0x18000f85d  mov     rsi, [rsp+28h+arg_8]
0x18000f862  add     rsp, 20h
0x18000f866  pop     rdi
0x18000f867  retn
```
