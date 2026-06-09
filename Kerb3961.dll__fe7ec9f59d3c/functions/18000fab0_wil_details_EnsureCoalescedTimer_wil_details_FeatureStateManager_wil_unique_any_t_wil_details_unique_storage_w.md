# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000fab0`
- end: `0x18000fb2f`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `127`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18000fab0`
- `0x1800134d0`
- `0x180014b74`
- `0x180015750`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fac9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fac9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fadb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fadb`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rdi

  if ( *Context )
  {
    v4 = (RTL_SRWLOCK *)(Context + 32);
    AcquireSRWLockExclusive((PSRWLOCK)Context + 4);
    Context[65] = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)Context) )
    {
      wil::details_abi::SubscriptionList::OnSignaled(
        (LPCRITICAL_SECTION)(*((_QWORD *)Context + 3) + 200LL),
        *((PSRWLOCK *)Context + 3));
      wil::details_abi::FeatureStateData::RecordUsage(*((PSRWLOCK *)Context + 3));
    }
  }
}

```

## disassembly

```asm
0x18000fab0  mov     [rsp+arg_0], rbx
0x18000fab5  push    rdi
0x18000fab6  sub     rsp, 20h
0x18000faba  cmp     byte ptr [rdx], 0
0x18000fabd  mov     rbx, rdx
0x18000fac0  jz      short loc_18000FB24
0x18000fac2  lea     rdi, [rdx+20h]
0x18000fac6  mov     rcx, rdi; SRWLock
0x18000fac9  call    cs:__imp_AcquireSRWLockExclusive
0x18000facf  mov     byte ptr [rbx+41h], 0
0x18000fad3  test    rdi, rdi
0x18000fad6  jz      short loc_18000FAE1
0x18000fad8  mov     rcx, rdi; SRWLock
0x18000fadb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fae1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fae8  jnz     short loc_18000FB24
0x18000faea  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000faf1  test    rax, rax
0x18000faf4  jz      short loc_18000FAFF
0x18000faf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fafb  test    al, al
0x18000fafd  jnz     short loc_18000FB24
0x18000faff  mov     rcx, rbx; this
0x18000fb02  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000fb07  test    al, al
0x18000fb09  jz      short loc_18000FB24
0x18000fb0b  mov     rdx, [rbx+18h]; SRWLock
0x18000fb0f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000fb16  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000fb1b  mov     rcx, [rbx+18h]; SRWLock
0x18000fb1f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000fb24  mov     rbx, [rsp+28h+arg_0]
0x18000fb29  add     rsp, 20h
0x18000fb2d  pop     rdi
0x18000fb2e  retn
```
