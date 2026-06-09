# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800071a4`
- end: `0x180007238`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004660`
- `0x180017c10`

## callees

- `0x1800071a4`
- `0x180007688`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800071e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800071e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007222`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007203`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007203`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000721a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000721a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007211`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007211`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800071a4  mov     [rsp+arg_0], rbx
0x1800071a9  mov     [rsp+arg_8], rsi
0x1800071ae  push    rdi
0x1800071af  sub     rsp, 20h
0x1800071b3  mov     dword ptr [rcx], 0
0x1800071b9  lea     rdi, [rcx+8]
0x1800071bd  mov     rsi, [rcx+10h]
0x1800071c1  mov     rbx, rcx
0x1800071c4  mov     qword ptr [rcx+10h], 0
0x1800071cc  mov     rcx, rdi; SRWLock
0x1800071cf  call    cs:__imp_AcquireSRWLockExclusive
0x1800071d5  mov     rcx, rbx
0x1800071d8  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800071dd  test    rdi, rdi
0x1800071e0  jz      short loc_1800071EB
0x1800071e2  mov     rcx, rdi; SRWLock
0x1800071e5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800071eb  test    rsi, rsi
0x1800071ee  jz      short loc_180007228
0x1800071f0  call    cs:__imp_GetLastError
0x1800071f6  xor     r9d, r9d; msWindowLength
0x1800071f9  xor     r8d, r8d; msPeriod
0x1800071fc  xor     edx, edx; pftDueTime
0x1800071fe  mov     rcx, rsi; pti
0x180007201  mov     ebx, eax
0x180007203  call    cs:__imp_SetThreadpoolTimer
0x180007209  mov     edx, 1; fCancelPendingCallbacks
0x18000720e  mov     rcx, rsi; pti
0x180007211  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007217  mov     rcx, rsi; pti
0x18000721a  call    cs:__imp_CloseThreadpoolTimer
0x180007220  mov     ecx, ebx; dwErrCode
0x180007222  call    cs:__imp_SetLastError
0x180007228  mov     rbx, [rsp+28h+arg_0]
0x18000722d  mov     rsi, [rsp+28h+arg_8]
0x180007232  add     rsp, 20h
0x180007236  pop     rdi
0x180007237  retn
```
