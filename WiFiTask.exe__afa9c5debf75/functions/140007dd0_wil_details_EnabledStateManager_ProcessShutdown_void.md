# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140007dd0`
- end: `0x140007e64`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003670`
- `0x140011380`

## callees

- `0x140007dd0`
- `0x140008440`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007e3d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007e3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007e2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007e2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007e46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007e46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007dfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007dfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007e11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007e11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007e4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007e1c`

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
0x140007dd0  mov     [rsp+arg_0], rbx
0x140007dd5  mov     [rsp+arg_8], rsi
0x140007dda  push    rdi
0x140007ddb  sub     rsp, 20h
0x140007ddf  mov     dword ptr [rcx], 0
0x140007de5  lea     rdi, [rcx+8]
0x140007de9  mov     rsi, [rcx+10h]
0x140007ded  mov     rbx, rcx
0x140007df0  mov     qword ptr [rcx+10h], 0
0x140007df8  mov     rcx, rdi; SRWLock
0x140007dfb  call    cs:__imp_AcquireSRWLockExclusive
0x140007e01  mov     rcx, rbx
0x140007e04  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140007e09  test    rdi, rdi
0x140007e0c  jz      short loc_140007E17
0x140007e0e  mov     rcx, rdi; SRWLock
0x140007e11  call    cs:__imp_ReleaseSRWLockExclusive
0x140007e17  test    rsi, rsi
0x140007e1a  jz      short loc_140007E54
0x140007e1c  call    cs:__imp_GetLastError
0x140007e22  xor     r9d, r9d; msWindowLength
0x140007e25  xor     r8d, r8d; msPeriod
0x140007e28  xor     edx, edx; pftDueTime
0x140007e2a  mov     rcx, rsi; pti
0x140007e2d  mov     ebx, eax
0x140007e2f  call    cs:__imp_SetThreadpoolTimer
0x140007e35  mov     edx, 1; fCancelPendingCallbacks
0x140007e3a  mov     rcx, rsi; pti
0x140007e3d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007e43  mov     rcx, rsi; pti
0x140007e46  call    cs:__imp_CloseThreadpoolTimer
0x140007e4c  mov     ecx, ebx; dwErrCode
0x140007e4e  call    cs:__imp_SetLastError
0x140007e54  mov     rbx, [rsp+28h+arg_0]
0x140007e59  mov     rsi, [rsp+28h+arg_8]
0x140007e5e  add     rsp, 20h
0x140007e62  pop     rdi
0x140007e63  retn
```
