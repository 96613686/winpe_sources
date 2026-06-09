# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180011bfc`
- end: `0x180011c90`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800105e0`
- `0x1800abde0`

## callees

- `0x180011bfc`
- `0x180012048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011c27`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011c27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011c3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011c3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011c72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011c72`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011c69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011c69`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011c5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011c5b`

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
0x180011bfc  mov     [rsp+arg_0], rbx
0x180011c01  mov     [rsp+arg_8], rsi
0x180011c06  push    rdi
0x180011c07  sub     rsp, 20h
0x180011c0b  mov     dword ptr [rcx], 0
0x180011c11  lea     rdi, [rcx+8]
0x180011c15  mov     rsi, [rcx+10h]
0x180011c19  mov     rbx, rcx
0x180011c1c  mov     qword ptr [rcx+10h], 0
0x180011c24  mov     rcx, rdi; SRWLock
0x180011c27  call    cs:__imp_AcquireSRWLockExclusive
0x180011c2d  mov     rcx, rbx
0x180011c30  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180011c35  test    rdi, rdi
0x180011c38  jz      short loc_180011C43
0x180011c3a  mov     rcx, rdi; SRWLock
0x180011c3d  call    cs:__imp_ReleaseSRWLockExclusive
0x180011c43  test    rsi, rsi
0x180011c46  jz      short loc_180011C80
0x180011c48  call    cs:__imp_GetLastError
0x180011c4e  xor     r9d, r9d; msWindowLength
0x180011c51  xor     r8d, r8d; msPeriod
0x180011c54  xor     edx, edx; pftDueTime
0x180011c56  mov     rcx, rsi; pti
0x180011c59  mov     ebx, eax
0x180011c5b  call    cs:__imp_SetThreadpoolTimer
0x180011c61  mov     edx, 1; fCancelPendingCallbacks
0x180011c66  mov     rcx, rsi; pti
0x180011c69  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011c6f  mov     rcx, rsi; pti
0x180011c72  call    cs:__imp_CloseThreadpoolTimer
0x180011c78  mov     ecx, ebx; dwErrCode
0x180011c7a  call    cs:__imp_SetLastError
0x180011c80  mov     rbx, [rsp+28h+arg_0]
0x180011c85  mov     rsi, [rsp+28h+arg_8]
0x180011c8a  add     rsp, 20h
0x180011c8e  pop     rdi
0x180011c8f  retn
```
