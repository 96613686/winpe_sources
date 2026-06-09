# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180008990`
- end: `0x180008a24`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800058e4`
- `0x180032e10`

## callees

- `0x180008990`
- `0x180008e4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800089bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800089bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800089d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800089d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a06`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a06`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089fd`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rsi
  struct _TP_TIMER *Ptr; // rdi
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
0x180008990  mov     [rsp+arg_8], rbx
0x180008995  mov     [rsp+arg_10], rsi
0x18000899a  push    rdi
0x18000899b  sub     rsp, 20h
0x18000899f  mov     dword ptr [rcx], 0
0x1800089a5  lea     rsi, [rcx+8]
0x1800089a9  mov     rdi, [rcx+10h]
0x1800089ad  mov     rbx, rcx
0x1800089b0  mov     qword ptr [rcx+10h], 0
0x1800089b8  mov     rcx, rsi; SRWLock
0x1800089bb  call    cs:__imp_AcquireSRWLockExclusive
0x1800089c1  mov     rcx, rbx
0x1800089c4  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800089c9  test    rsi, rsi
0x1800089cc  jz      short loc_1800089D7
0x1800089ce  mov     rcx, rsi; SRWLock
0x1800089d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800089d7  test    rdi, rdi
0x1800089da  jz      short loc_180008A14
0x1800089dc  call    cs:__imp_GetLastError
0x1800089e2  xor     r9d, r9d; msWindowLength
0x1800089e5  xor     r8d, r8d; msPeriod
0x1800089e8  xor     edx, edx; pftDueTime
0x1800089ea  mov     rcx, rdi; pti
0x1800089ed  mov     ebx, eax
0x1800089ef  call    cs:__imp_SetThreadpoolTimer
0x1800089f5  mov     edx, 1; fCancelPendingCallbacks
0x1800089fa  mov     rcx, rdi; pti
0x1800089fd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008a03  mov     rcx, rdi; pti
0x180008a06  call    cs:__imp_CloseThreadpoolTimer
0x180008a0c  mov     ecx, ebx; dwErrCode
0x180008a0e  call    cs:__imp_SetLastError
0x180008a14  mov     rbx, [rsp+28h+arg_8]
0x180008a19  mov     rsi, [rsp+28h+arg_10]
0x180008a1e  add     rsp, 20h
0x180008a22  pop     rdi
0x180008a23  retn
```
