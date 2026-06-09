# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180014cf0`
- end: `0x180014d84`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010458`
- `0x18001d600`

## callees

- `0x180014cf0`
- `0x1800153dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014d1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014d1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014d31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014d31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d3c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014d66`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014d66`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014d5d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014d5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014d4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014d4f`

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
0x180014cf0  mov     [rsp+arg_0], rbx
0x180014cf5  mov     [rsp+arg_8], rsi
0x180014cfa  push    rdi
0x180014cfb  sub     rsp, 20h
0x180014cff  mov     dword ptr [rcx], 0
0x180014d05  lea     rdi, [rcx+8]
0x180014d09  mov     rsi, [rcx+10h]
0x180014d0d  mov     rbx, rcx
0x180014d10  mov     qword ptr [rcx+10h], 0
0x180014d18  mov     rcx, rdi; SRWLock
0x180014d1b  call    cs:__imp_AcquireSRWLockExclusive
0x180014d21  mov     rcx, rbx
0x180014d24  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180014d29  test    rdi, rdi
0x180014d2c  jz      short loc_180014D37
0x180014d2e  mov     rcx, rdi; SRWLock
0x180014d31  call    cs:__imp_ReleaseSRWLockExclusive
0x180014d37  test    rsi, rsi
0x180014d3a  jz      short loc_180014D74
0x180014d3c  call    cs:__imp_GetLastError
0x180014d42  xor     r9d, r9d; msWindowLength
0x180014d45  xor     r8d, r8d; msPeriod
0x180014d48  xor     edx, edx; pftDueTime
0x180014d4a  mov     rcx, rsi; pti
0x180014d4d  mov     ebx, eax
0x180014d4f  call    cs:__imp_SetThreadpoolTimer
0x180014d55  mov     edx, 1; fCancelPendingCallbacks
0x180014d5a  mov     rcx, rsi; pti
0x180014d5d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014d63  mov     rcx, rsi; pti
0x180014d66  call    cs:__imp_CloseThreadpoolTimer
0x180014d6c  mov     ecx, ebx; dwErrCode
0x180014d6e  call    cs:__imp_SetLastError
0x180014d74  mov     rbx, [rsp+28h+arg_0]
0x180014d79  mov     rsi, [rsp+28h+arg_8]
0x180014d7e  add     rsp, 20h
0x180014d82  pop     rdi
0x180014d83  retn
```
