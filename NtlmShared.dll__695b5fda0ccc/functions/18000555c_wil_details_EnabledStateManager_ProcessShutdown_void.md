# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000555c`
- end: `0x1800055f0`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c48`
- `0x18000c6e0`

## callees

- `0x18000555c`
- `0x180005984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000559d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000559d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005587`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800055d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800055d2`

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
0x18000555c  mov     [rsp+arg_0], rbx
0x180005561  mov     [rsp+arg_8], rsi
0x180005566  push    rdi
0x180005567  sub     rsp, 20h
0x18000556b  mov     dword ptr [rcx], 0
0x180005571  lea     rdi, [rcx+8]
0x180005575  mov     rsi, [rcx+10h]
0x180005579  mov     rbx, rcx
0x18000557c  mov     qword ptr [rcx+10h], 0
0x180005584  mov     rcx, rdi; SRWLock
0x180005587  call    cs:__imp_AcquireSRWLockExclusive
0x18000558d  mov     rcx, rbx
0x180005590  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180005595  test    rdi, rdi
0x180005598  jz      short loc_1800055A3
0x18000559a  mov     rcx, rdi; SRWLock
0x18000559d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800055a3  test    rsi, rsi
0x1800055a6  jz      short loc_1800055E0
0x1800055a8  call    cs:__imp_GetLastError
0x1800055ae  xor     r9d, r9d; msWindowLength
0x1800055b1  xor     r8d, r8d; msPeriod
0x1800055b4  xor     edx, edx; pftDueTime
0x1800055b6  mov     rcx, rsi; pti
0x1800055b9  mov     ebx, eax
0x1800055bb  call    cs:__imp_SetThreadpoolTimer
0x1800055c1  mov     edx, 1; fCancelPendingCallbacks
0x1800055c6  mov     rcx, rsi; pti
0x1800055c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800055cf  mov     rcx, rsi; pti
0x1800055d2  call    cs:__imp_CloseThreadpoolTimer
0x1800055d8  mov     ecx, ebx; dwErrCode
0x1800055da  call    cs:__imp_SetLastError
0x1800055e0  mov     rbx, [rsp+28h+arg_0]
0x1800055e5  mov     rsi, [rsp+28h+arg_8]
0x1800055ea  add     rsp, 20h
0x1800055ee  pop     rdi
0x1800055ef  retn
```
