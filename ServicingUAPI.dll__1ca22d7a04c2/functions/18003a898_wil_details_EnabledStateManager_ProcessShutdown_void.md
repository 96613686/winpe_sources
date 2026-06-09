# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18003a898`
- end: `0x18003a947`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800397b8`
- `0x1801b82b0`

## callees

- `0x18003a898`
- `0x18003ada8`
- `0x18003c954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a8c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a8c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a8df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a8df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a90c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003a90c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003a920`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003a920`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a92f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003a92f`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rax
  struct _TP_TIMER *v4; // rbx
  PTP_TIMER pti; // [rsp+20h] [rbp-18h] BYREF

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
0x18003a898  mov     [rsp+arg_8], rbx
0x18003a89d  push    rdi
0x18003a89e  sub     rsp, 30h
0x18003a8a2  mov     dword ptr [rcx], 0
0x18003a8a8  lea     rdi, [rcx+8]
0x18003a8ac  mov     rax, [rcx+10h]
0x18003a8b0  mov     rbx, rcx
0x18003a8b3  mov     qword ptr [rcx+10h], 0
0x18003a8bb  mov     rcx, rdi; SRWLock
0x18003a8be  mov     [rsp+38h+pti], rax
0x18003a8c3  call    cs:__imp_AcquireSRWLockExclusive
0x18003a8ca  nop     dword ptr [rax+rax+00h]
0x18003a8cf  mov     rcx, rbx
0x18003a8d2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18003a8d7  test    rdi, rdi
0x18003a8da  jz      short loc_18003A8EB
0x18003a8dc  mov     rcx, rdi; SRWLock
0x18003a8df  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a8e6  nop     dword ptr [rax+rax+00h]
0x18003a8eb  xor     edx, edx
0x18003a8ed  lea     rcx, [rsp+38h+pti]
0x18003a8f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003a8f7  mov     rbx, [rsp+38h+pti]
0x18003a8fc  test    rbx, rbx
0x18003a8ff  jz      short loc_18003A93B
0x18003a901  xor     r9d, r9d; msWindowLength
0x18003a904  xor     r8d, r8d; msPeriod
0x18003a907  xor     edx, edx; pftDueTime
0x18003a909  mov     rcx, rbx; pti
0x18003a90c  call    cs:__imp_SetThreadpoolTimer
0x18003a913  nop     dword ptr [rax+rax+00h]
0x18003a918  mov     edx, 1; fCancelPendingCallbacks
0x18003a91d  mov     rcx, rbx; pti
0x18003a920  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003a927  nop     dword ptr [rax+rax+00h]
0x18003a92c  mov     rcx, rbx; pti
0x18003a92f  call    cs:__imp_CloseThreadpoolTimer
0x18003a936  nop     dword ptr [rax+rax+00h]
0x18003a93b  mov     rbx, [rsp+38h+arg_8]
0x18003a940  add     rsp, 30h
0x18003a944  pop     rdi
0x18003a945  retn
```
