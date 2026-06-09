# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000bcc8`
- end: `0x18000bd77`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009fc0`
- `0x18006f710`

## callees

- `0x18000bcc8`
- `0x18000c30c`
- `0x18000e9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bd0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bd0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bcf3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bcf3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bd5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bd5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bd3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bd3c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bd50`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bd50`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rax
  struct _TP_TIMER *v4; // rbx
  PTP_TIMER pti; // [rsp+30h] [rbp+8h] BYREF

  LODWORD(this->Ptr) = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  pti = Ptr;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  v4 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
  }
}

```

## disassembly

```asm
0x18000bcc8  mov     [rsp+arg_8], rbx
0x18000bccd  push    rdi
0x18000bcce  sub     rsp, 20h
0x18000bcd2  mov     dword ptr [rcx], 0
0x18000bcd8  lea     rdi, [rcx+8]
0x18000bcdc  mov     rax, [rcx+10h]
0x18000bce0  mov     rbx, rcx
0x18000bce3  mov     qword ptr [rcx+10h], 0
0x18000bceb  mov     rcx, rdi; SRWLock
0x18000bcee  mov     [rsp+28h+pti], rax
0x18000bcf3  call    cs:__imp_AcquireSRWLockExclusive
0x18000bcfa  nop     dword ptr [rax+rax+00h]
0x18000bcff  mov     rcx, rbx
0x18000bd02  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000bd07  test    rdi, rdi
0x18000bd0a  jz      short loc_18000BD1B
0x18000bd0c  mov     rcx, rdi; SRWLock
0x18000bd0f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bd16  nop     dword ptr [rax+rax+00h]
0x18000bd1b  xor     edx, edx
0x18000bd1d  lea     rcx, [rsp+28h+pti]
0x18000bd22  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000bd27  mov     rbx, [rsp+28h+pti]
0x18000bd2c  test    rbx, rbx
0x18000bd2f  jz      short loc_18000BD6B
0x18000bd31  xor     r9d, r9d; msWindowLength
0x18000bd34  xor     r8d, r8d; msPeriod
0x18000bd37  xor     edx, edx; pftDueTime
0x18000bd39  mov     rcx, rbx; pti
0x18000bd3c  call    cs:__imp_SetThreadpoolTimer
0x18000bd43  nop     dword ptr [rax+rax+00h]
0x18000bd48  mov     edx, 1; fCancelPendingCallbacks
0x18000bd4d  mov     rcx, rbx; pti
0x18000bd50  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bd57  nop     dword ptr [rax+rax+00h]
0x18000bd5c  mov     rcx, rbx; pti
0x18000bd5f  call    cs:__imp_CloseThreadpoolTimer
0x18000bd66  nop     dword ptr [rax+rax+00h]
0x18000bd6b  mov     rbx, [rsp+28h+arg_8]
0x18000bd70  add     rsp, 20h
0x18000bd74  pop     rdi
0x18000bd75  retn
```
