# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18001624c`
- end: `0x1800162e0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010704`
- `0x18006e850`

## callees

- `0x18001624c`
- `0x180016858`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001628d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001628d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016277`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016298`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800162ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800162c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800162c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800162ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800162ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800162b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800162b9`

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
0x18001624c  mov     [rsp+arg_0], rbx
0x180016251  mov     [rsp+arg_8], rsi
0x180016256  push    rdi
0x180016257  sub     rsp, 20h
0x18001625b  mov     dword ptr [rcx], 0
0x180016261  lea     rdi, [rcx+8]
0x180016265  mov     rsi, [rcx+10h]
0x180016269  mov     rbx, rcx
0x18001626c  mov     qword ptr [rcx+10h], 0
0x180016274  mov     rcx, rdi; SRWLock
0x180016277  call    cs:__imp_AcquireSRWLockExclusive
0x18001627d  mov     rcx, rbx
0x180016280  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180016285  test    rdi, rdi
0x180016288  jz      short loc_180016293
0x18001628a  mov     rcx, rdi; SRWLock
0x18001628d  call    cs:__imp_ReleaseSRWLockExclusive
0x180016293  test    rsi, rsi
0x180016296  jz      short loc_1800162D0
0x180016298  call    cs:__imp_GetLastError
0x18001629e  xor     r9d, r9d; msWindowLength
0x1800162a1  xor     r8d, r8d; msPeriod
0x1800162a4  xor     edx, edx; pftDueTime
0x1800162a6  mov     rcx, rsi; pti
0x1800162a9  mov     ebx, eax
0x1800162ab  call    cs:__imp_SetThreadpoolTimer
0x1800162b1  mov     edx, 1; fCancelPendingCallbacks
0x1800162b6  mov     rcx, rsi; pti
0x1800162b9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800162bf  mov     rcx, rsi; pti
0x1800162c2  call    cs:__imp_CloseThreadpoolTimer
0x1800162c8  mov     ecx, ebx; dwErrCode
0x1800162ca  call    cs:__imp_SetLastError
0x1800162d0  mov     rbx, [rsp+28h+arg_0]
0x1800162d5  mov     rsi, [rsp+28h+arg_8]
0x1800162da  add     rsp, 20h
0x1800162de  pop     rdi
0x1800162df  retn
```
