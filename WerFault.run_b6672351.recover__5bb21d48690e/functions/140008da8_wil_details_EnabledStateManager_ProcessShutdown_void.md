# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x140008da8`
- end: `0x140008e57`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005a44`
- `0x140060550`

## callees

- `0x140008da8`
- `0x140009370`
- `0x14000cec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008dd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008def`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008def`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008e3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008e3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008e30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008e30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008e1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008e1c`

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
0x140008da8  mov     [rsp+arg_8], rbx
0x140008dad  push    rdi
0x140008dae  sub     rsp, 20h
0x140008db2  mov     dword ptr [rcx], 0
0x140008db8  lea     rdi, [rcx+8]
0x140008dbc  mov     rax, [rcx+10h]
0x140008dc0  mov     rbx, rcx
0x140008dc3  mov     qword ptr [rcx+10h], 0
0x140008dcb  mov     rcx, rdi; SRWLock
0x140008dce  mov     [rsp+28h+pti], rax
0x140008dd3  call    cs:__imp_AcquireSRWLockExclusive
0x140008dda  nop     dword ptr [rax+rax+00h]
0x140008ddf  mov     rcx, rbx
0x140008de2  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x140008de7  test    rdi, rdi
0x140008dea  jz      short loc_140008DFB
0x140008dec  mov     rcx, rdi; SRWLock
0x140008def  call    cs:__imp_ReleaseSRWLockExclusive
0x140008df6  nop     dword ptr [rax+rax+00h]
0x140008dfb  xor     edx, edx
0x140008dfd  lea     rcx, [rsp+28h+pti]
0x140008e02  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140008e07  mov     rbx, [rsp+28h+pti]
0x140008e0c  test    rbx, rbx
0x140008e0f  jz      short loc_140008E4B
0x140008e11  xor     r9d, r9d; msWindowLength
0x140008e14  xor     r8d, r8d; msPeriod
0x140008e17  xor     edx, edx; pftDueTime
0x140008e19  mov     rcx, rbx; pti
0x140008e1c  call    cs:__imp_SetThreadpoolTimer
0x140008e23  nop     dword ptr [rax+rax+00h]
0x140008e28  mov     edx, 1; fCancelPendingCallbacks
0x140008e2d  mov     rcx, rbx; pti
0x140008e30  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008e37  nop     dword ptr [rax+rax+00h]
0x140008e3c  mov     rcx, rbx; pti
0x140008e3f  call    cs:__imp_CloseThreadpoolTimer
0x140008e46  nop     dword ptr [rax+rax+00h]
0x140008e4b  mov     rbx, [rsp+28h+arg_8]
0x140008e50  add     rsp, 20h
0x140008e54  pop     rdi
0x140008e55  retn
```
