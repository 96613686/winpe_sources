# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800096c8`
- end: `0x18000975c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085ac`
- `0x1800c95e0`

## callees

- `0x1800096c8`
- `0x180009b14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009709`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009709`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800096f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800096f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009746`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009714`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009727`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009727`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009735`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009735`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000973e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000973e`

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
0x1800096c8  mov     [rsp+arg_0], rbx
0x1800096cd  mov     [rsp+arg_8], rsi
0x1800096d2  push    rdi
0x1800096d3  sub     rsp, 20h
0x1800096d7  mov     dword ptr [rcx], 0
0x1800096dd  lea     rdi, [rcx+8]
0x1800096e1  mov     rsi, [rcx+10h]
0x1800096e5  mov     rbx, rcx
0x1800096e8  mov     qword ptr [rcx+10h], 0
0x1800096f0  mov     rcx, rdi; SRWLock
0x1800096f3  call    cs:__imp_AcquireSRWLockExclusive
0x1800096f9  mov     rcx, rbx
0x1800096fc  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180009701  test    rdi, rdi
0x180009704  jz      short loc_18000970F
0x180009706  mov     rcx, rdi; SRWLock
0x180009709  call    cs:__imp_ReleaseSRWLockExclusive
0x18000970f  test    rsi, rsi
0x180009712  jz      short loc_18000974C
0x180009714  call    cs:__imp_GetLastError
0x18000971a  xor     r9d, r9d; msWindowLength
0x18000971d  xor     r8d, r8d; msPeriod
0x180009720  xor     edx, edx; pftDueTime
0x180009722  mov     rcx, rsi; pti
0x180009725  mov     ebx, eax
0x180009727  call    cs:__imp_SetThreadpoolTimer
0x18000972d  mov     edx, 1; fCancelPendingCallbacks
0x180009732  mov     rcx, rsi; pti
0x180009735  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000973b  mov     rcx, rsi; pti
0x18000973e  call    cs:__imp_CloseThreadpoolTimer
0x180009744  mov     ecx, ebx; dwErrCode
0x180009746  call    cs:__imp_SetLastError
0x18000974c  mov     rbx, [rsp+28h+arg_0]
0x180009751  mov     rsi, [rsp+28h+arg_8]
0x180009756  add     rsp, 20h
0x18000975a  pop     rdi
0x18000975b  retn
```
