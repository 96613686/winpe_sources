# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140005dbc`
- end: `0x140005e50`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003290`
- `0x14000b9a0`

## callees

- `0x140005dbc`
- `0x140006208`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005de7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005de7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005dfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e3a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e32`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005e32`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005e1b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005e29`

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
0x140005dbc  mov     [rsp+arg_0], rbx
0x140005dc1  mov     [rsp+arg_8], rsi
0x140005dc6  push    rdi
0x140005dc7  sub     rsp, 20h
0x140005dcb  mov     dword ptr [rcx], 0
0x140005dd1  lea     rdi, [rcx+8]
0x140005dd5  mov     rsi, [rcx+10h]
0x140005dd9  mov     rbx, rcx
0x140005ddc  mov     qword ptr [rcx+10h], 0
0x140005de4  mov     rcx, rdi; SRWLock
0x140005de7  call    cs:__imp_AcquireSRWLockExclusive
0x140005ded  mov     rcx, rbx
0x140005df0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140005df5  test    rdi, rdi
0x140005df8  jz      short loc_140005E03
0x140005dfa  mov     rcx, rdi; SRWLock
0x140005dfd  call    cs:__imp_ReleaseSRWLockExclusive
0x140005e03  test    rsi, rsi
0x140005e06  jz      short loc_140005E40
0x140005e08  call    cs:__imp_GetLastError
0x140005e0e  xor     r9d, r9d; msWindowLength
0x140005e11  xor     r8d, r8d; msPeriod
0x140005e14  xor     edx, edx; pftDueTime
0x140005e16  mov     rcx, rsi; pti
0x140005e19  mov     ebx, eax
0x140005e1b  call    cs:__imp_SetThreadpoolTimer
0x140005e21  mov     edx, 1; fCancelPendingCallbacks
0x140005e26  mov     rcx, rsi; pti
0x140005e29  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005e2f  mov     rcx, rsi; pti
0x140005e32  call    cs:__imp_CloseThreadpoolTimer
0x140005e38  mov     ecx, ebx; dwErrCode
0x140005e3a  call    cs:__imp_SetLastError
0x140005e40  mov     rbx, [rsp+28h+arg_0]
0x140005e45  mov     rsi, [rsp+28h+arg_8]
0x140005e4a  add     rsp, 20h
0x140005e4e  pop     rdi
0x140005e4f  retn
```
