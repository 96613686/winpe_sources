# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180007190`
- end: `0x180007224`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003738`
- `0x180010f40`

## callees

- `0x180007190`
- `0x1800075d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800071d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800071d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800071bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000720e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000720e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800071ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800071ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007206`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007206`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800071fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800071fd`

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
0x180007190  mov     [rsp+arg_8], rbx
0x180007195  mov     [rsp+arg_10], rsi
0x18000719a  push    rdi
0x18000719b  sub     rsp, 20h
0x18000719f  mov     dword ptr [rcx], 0
0x1800071a5  lea     rsi, [rcx+8]
0x1800071a9  mov     rdi, [rcx+10h]
0x1800071ad  mov     rbx, rcx
0x1800071b0  mov     qword ptr [rcx+10h], 0
0x1800071b8  mov     rcx, rsi; SRWLock
0x1800071bb  call    cs:__imp_AcquireSRWLockExclusive
0x1800071c1  mov     rcx, rbx
0x1800071c4  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800071c9  test    rsi, rsi
0x1800071cc  jz      short loc_1800071D7
0x1800071ce  mov     rcx, rsi; SRWLock
0x1800071d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800071d7  test    rdi, rdi
0x1800071da  jz      short loc_180007214
0x1800071dc  call    cs:__imp_GetLastError
0x1800071e2  xor     r9d, r9d; msWindowLength
0x1800071e5  xor     r8d, r8d; msPeriod
0x1800071e8  xor     edx, edx; pftDueTime
0x1800071ea  mov     rcx, rdi; pti
0x1800071ed  mov     ebx, eax
0x1800071ef  call    cs:__imp_SetThreadpoolTimer
0x1800071f5  mov     edx, 1; fCancelPendingCallbacks
0x1800071fa  mov     rcx, rdi; pti
0x1800071fd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007203  mov     rcx, rdi; pti
0x180007206  call    cs:__imp_CloseThreadpoolTimer
0x18000720c  mov     ecx, ebx; dwErrCode
0x18000720e  call    cs:__imp_SetLastError
0x180007214  mov     rbx, [rsp+28h+arg_8]
0x180007219  mov     rsi, [rsp+28h+arg_10]
0x18000721e  add     rsp, 20h
0x180007222  pop     rdi
0x180007223  retn
```
