# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180009d70`
- end: `0x180009e04`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e64`
- `0x180011160`

## callees

- `0x180009d70`
- `0x18000a5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009db1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009dee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dbc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009de6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009de6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dcf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dcf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009ddd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009ddd`

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
0x180009d70  mov     [rsp+arg_0], rbx
0x180009d75  mov     [rsp+arg_8], rsi
0x180009d7a  push    rdi
0x180009d7b  sub     rsp, 20h
0x180009d7f  mov     dword ptr [rcx], 0
0x180009d85  lea     rdi, [rcx+8]
0x180009d89  mov     rsi, [rcx+10h]
0x180009d8d  mov     rbx, rcx
0x180009d90  mov     qword ptr [rcx+10h], 0
0x180009d98  mov     rcx, rdi; SRWLock
0x180009d9b  call    cs:__imp_AcquireSRWLockExclusive
0x180009da1  mov     rcx, rbx
0x180009da4  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180009da9  test    rdi, rdi
0x180009dac  jz      short loc_180009DB7
0x180009dae  mov     rcx, rdi; SRWLock
0x180009db1  call    cs:__imp_ReleaseSRWLockExclusive
0x180009db7  test    rsi, rsi
0x180009dba  jz      short loc_180009DF4
0x180009dbc  call    cs:__imp_GetLastError
0x180009dc2  xor     r9d, r9d; msWindowLength
0x180009dc5  xor     r8d, r8d; msPeriod
0x180009dc8  xor     edx, edx; pftDueTime
0x180009dca  mov     rcx, rsi; pti
0x180009dcd  mov     ebx, eax
0x180009dcf  call    cs:__imp_SetThreadpoolTimer
0x180009dd5  mov     edx, 1; fCancelPendingCallbacks
0x180009dda  mov     rcx, rsi; pti
0x180009ddd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009de3  mov     rcx, rsi; pti
0x180009de6  call    cs:__imp_CloseThreadpoolTimer
0x180009dec  mov     ecx, ebx; dwErrCode
0x180009dee  call    cs:__imp_SetLastError
0x180009df4  mov     rbx, [rsp+28h+arg_0]
0x180009df9  mov     rsi, [rsp+28h+arg_8]
0x180009dfe  add     rsp, 20h
0x180009e02  pop     rdi
0x180009e03  retn
```
