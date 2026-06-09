# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000e760`
- end: `0x18000e7f4`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000adac`
- `0x18002d280`

## callees

- `0x18000e760`
- `0x18000eeac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e7a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e7a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e78b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e78b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e7cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e7cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e7d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e7d6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e7bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e7bf`

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
0x18000e760  mov     [rsp+arg_0], rbx
0x18000e765  mov     [rsp+arg_8], rsi
0x18000e76a  push    rdi
0x18000e76b  sub     rsp, 20h
0x18000e76f  mov     dword ptr [rcx], 0
0x18000e775  lea     rdi, [rcx+8]
0x18000e779  mov     rsi, [rcx+10h]
0x18000e77d  mov     rbx, rcx
0x18000e780  mov     qword ptr [rcx+10h], 0
0x18000e788  mov     rcx, rdi; SRWLock
0x18000e78b  call    cs:__imp_AcquireSRWLockExclusive
0x18000e791  mov     rcx, rbx
0x18000e794  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000e799  test    rdi, rdi
0x18000e79c  jz      short loc_18000E7A7
0x18000e79e  mov     rcx, rdi; SRWLock
0x18000e7a1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e7a7  test    rsi, rsi
0x18000e7aa  jz      short loc_18000E7E4
0x18000e7ac  call    cs:__imp_GetLastError
0x18000e7b2  xor     r9d, r9d; msWindowLength
0x18000e7b5  xor     r8d, r8d; msPeriod
0x18000e7b8  xor     edx, edx; pftDueTime
0x18000e7ba  mov     rcx, rsi; pti
0x18000e7bd  mov     ebx, eax
0x18000e7bf  call    cs:__imp_SetThreadpoolTimer
0x18000e7c5  mov     edx, 1; fCancelPendingCallbacks
0x18000e7ca  mov     rcx, rsi; pti
0x18000e7cd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e7d3  mov     rcx, rsi; pti
0x18000e7d6  call    cs:__imp_CloseThreadpoolTimer
0x18000e7dc  mov     ecx, ebx; dwErrCode
0x18000e7de  call    cs:__imp_SetLastError
0x18000e7e4  mov     rbx, [rsp+28h+arg_0]
0x18000e7e9  mov     rsi, [rsp+28h+arg_8]
0x18000e7ee  add     rsp, 20h
0x18000e7f2  pop     rdi
0x18000e7f3  retn
```
