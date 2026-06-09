# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800124c8`
- end: `0x18001255c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006738`
- `0x180052770`

## callees

- `0x1800124c8`
- `0x180013880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012509`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012546`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012514`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012535`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012535`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001253e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001253e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012527`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012527`

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
0x1800124c8  mov     [rsp+arg_8], rbx
0x1800124cd  mov     [rsp+arg_10], rsi
0x1800124d2  push    rdi
0x1800124d3  sub     rsp, 20h
0x1800124d7  mov     dword ptr [rcx], 0
0x1800124dd  lea     rsi, [rcx+8]
0x1800124e1  mov     rdi, [rcx+10h]
0x1800124e5  mov     rbx, rcx
0x1800124e8  mov     qword ptr [rcx+10h], 0
0x1800124f0  mov     rcx, rsi; SRWLock
0x1800124f3  call    cs:__imp_AcquireSRWLockExclusive
0x1800124f9  mov     rcx, rbx
0x1800124fc  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180012501  test    rsi, rsi
0x180012504  jz      short loc_18001250F
0x180012506  mov     rcx, rsi; SRWLock
0x180012509  call    cs:__imp_ReleaseSRWLockExclusive
0x18001250f  test    rdi, rdi
0x180012512  jz      short loc_18001254C
0x180012514  call    cs:__imp_GetLastError
0x18001251a  xor     r9d, r9d; msWindowLength
0x18001251d  xor     r8d, r8d; msPeriod
0x180012520  xor     edx, edx; pftDueTime
0x180012522  mov     rcx, rdi; pti
0x180012525  mov     ebx, eax
0x180012527  call    cs:__imp_SetThreadpoolTimer
0x18001252d  mov     edx, 1; fCancelPendingCallbacks
0x180012532  mov     rcx, rdi; pti
0x180012535  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001253b  mov     rcx, rdi; pti
0x18001253e  call    cs:__imp_CloseThreadpoolTimer
0x180012544  mov     ecx, ebx; dwErrCode
0x180012546  call    cs:__imp_SetLastError
0x18001254c  mov     rbx, [rsp+28h+arg_8]
0x180012551  mov     rsi, [rsp+28h+arg_10]
0x180012556  add     rsp, 20h
0x18001255a  pop     rdi
0x18001255b  retn
```
