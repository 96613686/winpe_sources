# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800090fc`
- end: `0x180009190`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006390`
- `0x1801076d0`

## callees

- `0x1800090fc`
- `0x180009590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000913d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000913d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009148`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000917a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000917a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009172`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009172`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000915b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000915b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009169`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009169`

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
0x1800090fc  mov     [rsp+arg_0], rbx
0x180009101  mov     [rsp+arg_8], rsi
0x180009106  push    rdi
0x180009107  sub     rsp, 20h
0x18000910b  mov     dword ptr [rcx], 0
0x180009111  lea     rdi, [rcx+8]
0x180009115  mov     rsi, [rcx+10h]
0x180009119  mov     rbx, rcx
0x18000911c  mov     qword ptr [rcx+10h], 0
0x180009124  mov     rcx, rdi; SRWLock
0x180009127  call    cs:__imp_AcquireSRWLockExclusive
0x18000912d  mov     rcx, rbx
0x180009130  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180009135  test    rdi, rdi
0x180009138  jz      short loc_180009143
0x18000913a  mov     rcx, rdi; SRWLock
0x18000913d  call    cs:__imp_ReleaseSRWLockExclusive
0x180009143  test    rsi, rsi
0x180009146  jz      short loc_180009180
0x180009148  call    cs:__imp_GetLastError
0x18000914e  xor     r9d, r9d; msWindowLength
0x180009151  xor     r8d, r8d; msPeriod
0x180009154  xor     edx, edx; pftDueTime
0x180009156  mov     rcx, rsi; pti
0x180009159  mov     ebx, eax
0x18000915b  call    cs:__imp_SetThreadpoolTimer
0x180009161  mov     edx, 1; fCancelPendingCallbacks
0x180009166  mov     rcx, rsi; pti
0x180009169  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000916f  mov     rcx, rsi; pti
0x180009172  call    cs:__imp_CloseThreadpoolTimer
0x180009178  mov     ecx, ebx; dwErrCode
0x18000917a  call    cs:__imp_SetLastError
0x180009180  mov     rbx, [rsp+28h+arg_0]
0x180009185  mov     rsi, [rsp+28h+arg_8]
0x18000918a  add     rsp, 20h
0x18000918e  pop     rdi
0x18000918f  retn
```
