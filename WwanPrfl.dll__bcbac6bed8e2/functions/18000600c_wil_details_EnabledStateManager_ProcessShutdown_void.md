# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000600c`
- end: `0x1800060a0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003324`
- `0x1800139b0`

## callees

- `0x18000600c`
- `0x180006614`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000608a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000608a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000604d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000604d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006037`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006037`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006082`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006082`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006079`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006079`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000606b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000606b`

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
0x18000600c  mov     [rsp+arg_0], rbx
0x180006011  mov     [rsp+arg_8], rsi
0x180006016  push    rdi
0x180006017  sub     rsp, 20h
0x18000601b  mov     dword ptr [rcx], 0
0x180006021  lea     rdi, [rcx+8]
0x180006025  mov     rsi, [rcx+10h]
0x180006029  mov     rbx, rcx
0x18000602c  mov     qword ptr [rcx+10h], 0
0x180006034  mov     rcx, rdi; SRWLock
0x180006037  call    cs:__imp_AcquireSRWLockExclusive
0x18000603d  mov     rcx, rbx
0x180006040  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180006045  test    rdi, rdi
0x180006048  jz      short loc_180006053
0x18000604a  mov     rcx, rdi; SRWLock
0x18000604d  call    cs:__imp_ReleaseSRWLockExclusive
0x180006053  test    rsi, rsi
0x180006056  jz      short loc_180006090
0x180006058  call    cs:__imp_GetLastError
0x18000605e  xor     r9d, r9d; msWindowLength
0x180006061  xor     r8d, r8d; msPeriod
0x180006064  xor     edx, edx; pftDueTime
0x180006066  mov     rcx, rsi; pti
0x180006069  mov     ebx, eax
0x18000606b  call    cs:__imp_SetThreadpoolTimer
0x180006071  mov     edx, 1; fCancelPendingCallbacks
0x180006076  mov     rcx, rsi; pti
0x180006079  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000607f  mov     rcx, rsi; pti
0x180006082  call    cs:__imp_CloseThreadpoolTimer
0x180006088  mov     ecx, ebx; dwErrCode
0x18000608a  call    cs:__imp_SetLastError
0x180006090  mov     rbx, [rsp+28h+arg_0]
0x180006095  mov     rsi, [rsp+28h+arg_8]
0x18000609a  add     rsp, 20h
0x18000609e  pop     rdi
0x18000609f  retn
```
