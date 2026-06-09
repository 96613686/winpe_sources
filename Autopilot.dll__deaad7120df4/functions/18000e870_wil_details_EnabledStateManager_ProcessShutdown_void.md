# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18000e870`
- end: `0x18000e91f`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ae14`
- `0x18002e140`

## callees

- `0x18000e870`
- `0x18000efd0`
- `0x1800125b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e8b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e8b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e89b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e89b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e8f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e8f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e907`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e907`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e8e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e8e4`

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
0x18000e870  mov     [rsp+arg_8], rbx
0x18000e875  push    rdi
0x18000e876  sub     rsp, 20h
0x18000e87a  mov     dword ptr [rcx], 0
0x18000e880  lea     rdi, [rcx+8]
0x18000e884  mov     rax, [rcx+10h]
0x18000e888  mov     rbx, rcx
0x18000e88b  mov     qword ptr [rcx+10h], 0
0x18000e893  mov     rcx, rdi; SRWLock
0x18000e896  mov     [rsp+28h+pti], rax
0x18000e89b  call    cs:__imp_AcquireSRWLockExclusive
0x18000e8a2  nop     dword ptr [rax+rax+00h]
0x18000e8a7  mov     rcx, rbx
0x18000e8aa  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000e8af  test    rdi, rdi
0x18000e8b2  jz      short loc_18000E8C3
0x18000e8b4  mov     rcx, rdi; SRWLock
0x18000e8b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e8be  nop     dword ptr [rax+rax+00h]
0x18000e8c3  xor     edx, edx
0x18000e8c5  lea     rcx, [rsp+28h+pti]
0x18000e8ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000e8cf  mov     rbx, [rsp+28h+pti]
0x18000e8d4  test    rbx, rbx
0x18000e8d7  jz      short loc_18000E913
0x18000e8d9  xor     r9d, r9d; msWindowLength
0x18000e8dc  xor     r8d, r8d; msPeriod
0x18000e8df  xor     edx, edx; pftDueTime
0x18000e8e1  mov     rcx, rbx; pti
0x18000e8e4  call    cs:__imp_SetThreadpoolTimer
0x18000e8eb  nop     dword ptr [rax+rax+00h]
0x18000e8f0  mov     edx, 1; fCancelPendingCallbacks
0x18000e8f5  mov     rcx, rbx; pti
0x18000e8f8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e8ff  nop     dword ptr [rax+rax+00h]
0x18000e904  mov     rcx, rbx; pti
0x18000e907  call    cs:__imp_CloseThreadpoolTimer
0x18000e90e  nop     dword ptr [rax+rax+00h]
0x18000e913  mov     rbx, [rsp+28h+arg_8]
0x18000e918  add     rsp, 20h
0x18000e91c  pop     rdi
0x18000e91d  retn
```
