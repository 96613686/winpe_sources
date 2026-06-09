# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000b09c`
- end: `0x18000b130`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008024`
- `0x18009c0a0`

## callees

- `0x18000b09c`
- `0x18000b530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b11a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b11a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b109`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b109`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b112`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b112`

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
0x18000b09c  mov     [rsp+arg_0], rbx
0x18000b0a1  mov     [rsp+arg_8], rsi
0x18000b0a6  push    rdi
0x18000b0a7  sub     rsp, 20h
0x18000b0ab  mov     dword ptr [rcx], 0
0x18000b0b1  lea     rdi, [rcx+8]
0x18000b0b5  mov     rsi, [rcx+10h]
0x18000b0b9  mov     rbx, rcx
0x18000b0bc  mov     qword ptr [rcx+10h], 0
0x18000b0c4  mov     rcx, rdi; SRWLock
0x18000b0c7  call    cs:__imp_AcquireSRWLockExclusive
0x18000b0cd  mov     rcx, rbx
0x18000b0d0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000b0d5  test    rdi, rdi
0x18000b0d8  jz      short loc_18000B0E3
0x18000b0da  mov     rcx, rdi; SRWLock
0x18000b0dd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b0e3  test    rsi, rsi
0x18000b0e6  jz      short loc_18000B120
0x18000b0e8  call    cs:__imp_GetLastError
0x18000b0ee  xor     r9d, r9d; msWindowLength
0x18000b0f1  xor     r8d, r8d; msPeriod
0x18000b0f4  xor     edx, edx; pftDueTime
0x18000b0f6  mov     rcx, rsi; pti
0x18000b0f9  mov     ebx, eax
0x18000b0fb  call    cs:__imp_SetThreadpoolTimer
0x18000b101  mov     edx, 1; fCancelPendingCallbacks
0x18000b106  mov     rcx, rsi; pti
0x18000b109  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b10f  mov     rcx, rsi; pti
0x18000b112  call    cs:__imp_CloseThreadpoolTimer
0x18000b118  mov     ecx, ebx; dwErrCode
0x18000b11a  call    cs:__imp_SetLastError
0x18000b120  mov     rbx, [rsp+28h+arg_0]
0x18000b125  mov     rsi, [rsp+28h+arg_8]
0x18000b12a  add     rsp, 20h
0x18000b12e  pop     rdi
0x18000b12f  retn
```
