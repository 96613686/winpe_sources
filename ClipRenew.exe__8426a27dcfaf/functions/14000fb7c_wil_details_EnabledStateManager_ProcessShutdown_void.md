# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x14000fb7c`
- end: `0x14000fc10`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005dc0`
- `0x140013770`

## callees

- `0x14000fb7c`
- `0x140010158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000fbbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000fbbd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fba7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fbfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fbfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fbc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fbc8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fbe9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fbe9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fbf2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fbf2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fbdb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fbdb`

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
0x14000fb7c  mov     [rsp+arg_0], rbx
0x14000fb81  mov     [rsp+arg_8], rsi
0x14000fb86  push    rdi
0x14000fb87  sub     rsp, 20h
0x14000fb8b  mov     dword ptr [rcx], 0
0x14000fb91  lea     rdi, [rcx+8]
0x14000fb95  mov     rsi, [rcx+10h]
0x14000fb99  mov     rbx, rcx
0x14000fb9c  mov     qword ptr [rcx+10h], 0
0x14000fba4  mov     rcx, rdi; SRWLock
0x14000fba7  call    cs:__imp_AcquireSRWLockExclusive
0x14000fbad  mov     rcx, rbx
0x14000fbb0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x14000fbb5  test    rdi, rdi
0x14000fbb8  jz      short loc_14000FBC3
0x14000fbba  mov     rcx, rdi; SRWLock
0x14000fbbd  call    cs:__imp_ReleaseSRWLockExclusive
0x14000fbc3  test    rsi, rsi
0x14000fbc6  jz      short loc_14000FC00
0x14000fbc8  call    cs:__imp_GetLastError
0x14000fbce  xor     r9d, r9d; msWindowLength
0x14000fbd1  xor     r8d, r8d; msPeriod
0x14000fbd4  xor     edx, edx; pftDueTime
0x14000fbd6  mov     rcx, rsi; pti
0x14000fbd9  mov     ebx, eax
0x14000fbdb  call    cs:__imp_SetThreadpoolTimer
0x14000fbe1  mov     edx, 1; fCancelPendingCallbacks
0x14000fbe6  mov     rcx, rsi; pti
0x14000fbe9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000fbef  mov     rcx, rsi; pti
0x14000fbf2  call    cs:__imp_CloseThreadpoolTimer
0x14000fbf8  mov     ecx, ebx; dwErrCode
0x14000fbfa  call    cs:__imp_SetLastError
0x14000fc00  mov     rbx, [rsp+28h+arg_0]
0x14000fc05  mov     rsi, [rsp+28h+arg_8]
0x14000fc0a  add     rsp, 20h
0x14000fc0e  pop     rdi
0x14000fc0f  retn
```
