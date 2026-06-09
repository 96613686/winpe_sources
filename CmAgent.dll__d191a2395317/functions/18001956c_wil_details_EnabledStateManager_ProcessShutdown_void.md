# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x18001956c`
- end: `0x18001961b`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `175`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015258`
- `0x180037010`

## callees

- `0x18001956c`
- `0x180019ba0`
- `0x180021b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019597`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019597`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800195f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800195f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019603`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019603`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800195e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800195e0`

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
0x18001956c  mov     [rsp+arg_8], rbx
0x180019571  push    rdi
0x180019572  sub     rsp, 20h
0x180019576  mov     dword ptr [rcx], 0
0x18001957c  lea     rdi, [rcx+8]
0x180019580  mov     rax, [rcx+10h]
0x180019584  mov     rbx, rcx
0x180019587  mov     qword ptr [rcx+10h], 0
0x18001958f  mov     rcx, rdi; SRWLock
0x180019592  mov     [rsp+28h+pti], rax
0x180019597  call    cs:__imp_AcquireSRWLockExclusive
0x18001959e  nop     dword ptr [rax+rax+00h]
0x1800195a3  mov     rcx, rbx
0x1800195a6  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1800195ab  test    rdi, rdi
0x1800195ae  jz      short loc_1800195BF
0x1800195b0  mov     rcx, rdi; SRWLock
0x1800195b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800195ba  nop     dword ptr [rax+rax+00h]
0x1800195bf  xor     edx, edx
0x1800195c1  lea     rcx, [rsp+28h+pti]
0x1800195c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800195cb  mov     rbx, [rsp+28h+pti]
0x1800195d0  test    rbx, rbx
0x1800195d3  jz      short loc_18001960F
0x1800195d5  xor     r9d, r9d; msWindowLength
0x1800195d8  xor     r8d, r8d; msPeriod
0x1800195db  xor     edx, edx; pftDueTime
0x1800195dd  mov     rcx, rbx; pti
0x1800195e0  call    cs:__imp_SetThreadpoolTimer
0x1800195e7  nop     dword ptr [rax+rax+00h]
0x1800195ec  mov     edx, 1; fCancelPendingCallbacks
0x1800195f1  mov     rcx, rbx; pti
0x1800195f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800195fb  nop     dword ptr [rax+rax+00h]
0x180019600  mov     rcx, rbx; pti
0x180019603  call    cs:__imp_CloseThreadpoolTimer
0x18001960a  nop     dword ptr [rax+rax+00h]
0x18001960f  mov     rbx, [rsp+28h+arg_8]
0x180019614  add     rsp, 20h
0x180019618  pop     rdi
0x180019619  retn
```
