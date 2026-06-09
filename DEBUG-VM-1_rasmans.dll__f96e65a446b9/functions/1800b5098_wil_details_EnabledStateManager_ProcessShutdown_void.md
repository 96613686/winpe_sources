# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x1800b5098`
- end: `0x1800b512c`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ae7a0`
- `0x1800e8330`

## callees

- `0x1800b5098`
- `0x1800b592c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b5116`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b5116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b50e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b50e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b50d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b50d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b50c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b50c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b5105`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b5105`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b510e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b510e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b50f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b50f7`

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
0x1800b5098  mov     [rsp+arg_0], rbx
0x1800b509d  mov     [rsp+arg_8], rsi
0x1800b50a2  push    rdi
0x1800b50a3  sub     rsp, 20h
0x1800b50a7  mov     dword ptr [rcx], 0
0x1800b50ad  lea     rdi, [rcx+8]
0x1800b50b1  mov     rsi, [rcx+10h]
0x1800b50b5  mov     rbx, rcx
0x1800b50b8  mov     qword ptr [rcx+10h], 0
0x1800b50c0  mov     rcx, rdi; SRWLock
0x1800b50c3  call    cs:__imp_AcquireSRWLockExclusive
0x1800b50c9  mov     rcx, rbx
0x1800b50cc  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800b50d1  test    rdi, rdi
0x1800b50d4  jz      short loc_1800B50DF
0x1800b50d6  mov     rcx, rdi; SRWLock
0x1800b50d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b50df  test    rsi, rsi
0x1800b50e2  jz      short loc_1800B511C
0x1800b50e4  call    cs:__imp_GetLastError
0x1800b50ea  xor     r9d, r9d; msWindowLength
0x1800b50ed  xor     r8d, r8d; msPeriod
0x1800b50f0  xor     edx, edx; pftDueTime
0x1800b50f2  mov     rcx, rsi; pti
0x1800b50f5  mov     ebx, eax
0x1800b50f7  call    cs:__imp_SetThreadpoolTimer
0x1800b50fd  mov     edx, 1; fCancelPendingCallbacks
0x1800b5102  mov     rcx, rsi; pti
0x1800b5105  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b510b  mov     rcx, rsi; pti
0x1800b510e  call    cs:__imp_CloseThreadpoolTimer
0x1800b5114  mov     ecx, ebx; dwErrCode
0x1800b5116  call    cs:__imp_SetLastError
0x1800b511c  mov     rbx, [rsp+28h+arg_0]
0x1800b5121  mov     rsi, [rsp+28h+arg_8]
0x1800b5126  add     rsp, 20h
0x1800b512a  pop     rdi
0x1800b512b  retn
```
