# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x14000bd34`
- end: `0x14000bdc8`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400088d4`
- `0x1400126d0`

## callees

- `0x14000bd34`
- `0x14000c174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bdb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bdb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bd5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bd5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bd75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000bd75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bd93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000bd93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bda1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000bda1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bdaa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000bdaa`

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
0x14000bd34  mov     [rsp+arg_0], rbx
0x14000bd39  mov     [rsp+arg_8], rsi
0x14000bd3e  push    rdi
0x14000bd3f  sub     rsp, 20h
0x14000bd43  mov     dword ptr [rcx], 0
0x14000bd49  lea     rdi, [rcx+8]
0x14000bd4d  mov     rsi, [rcx+10h]
0x14000bd51  mov     rbx, rcx
0x14000bd54  mov     qword ptr [rcx+10h], 0
0x14000bd5c  mov     rcx, rdi; SRWLock
0x14000bd5f  call    cs:__imp_AcquireSRWLockExclusive
0x14000bd65  mov     rcx, rbx
0x14000bd68  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x14000bd6d  test    rdi, rdi
0x14000bd70  jz      short loc_14000BD7B
0x14000bd72  mov     rcx, rdi; SRWLock
0x14000bd75  call    cs:__imp_ReleaseSRWLockExclusive
0x14000bd7b  test    rsi, rsi
0x14000bd7e  jz      short loc_14000BDB8
0x14000bd80  call    cs:__imp_GetLastError
0x14000bd86  xor     r9d, r9d; msWindowLength
0x14000bd89  xor     r8d, r8d; msPeriod
0x14000bd8c  xor     edx, edx; pftDueTime
0x14000bd8e  mov     rcx, rsi; pti
0x14000bd91  mov     ebx, eax
0x14000bd93  call    cs:__imp_SetThreadpoolTimer
0x14000bd99  mov     edx, 1; fCancelPendingCallbacks
0x14000bd9e  mov     rcx, rsi; pti
0x14000bda1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000bda7  mov     rcx, rsi; pti
0x14000bdaa  call    cs:__imp_CloseThreadpoolTimer
0x14000bdb0  mov     ecx, ebx; dwErrCode
0x14000bdb2  call    cs:__imp_SetLastError
0x14000bdb8  mov     rbx, [rsp+28h+arg_0]
0x14000bdbd  mov     rsi, [rsp+28h+arg_8]
0x14000bdc2  add     rsp, 20h
0x14000bdc6  pop     rdi
0x14000bdc7  retn
```
