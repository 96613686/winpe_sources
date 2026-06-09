# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180002420`
- end: `0x1800024a1`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `129`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180002420`
- `0x180004544`
- `0x180005ea4`
- `0x180006a00`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000244b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000244b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002439`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002439`

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
0x180002420  mov     [rsp+arg_0], rbx
0x180002425  push    rdi
0x180002426  sub     rsp, 20h
0x18000242a  mov     rbx, rdx
0x18000242d  cmp     byte ptr [rdx], 0
0x180002430  jz      short loc_180002496
0x180002432  lea     rdi, [rdx+20h]
0x180002436  mov     rcx, rdi; SRWLock
0x180002439  call    cs:__imp_AcquireSRWLockExclusive
0x18000243f  mov     byte ptr [rbx+41h], 0
0x180002443  test    rdi, rdi
0x180002446  jz      short loc_180002452
0x180002448  mov     rcx, rdi; SRWLock
0x18000244b  call    cs:__imp_ReleaseSRWLockExclusive
0x180002451  nop
0x180002452  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180002459  jnz     short loc_180002496
0x18000245b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180002462  test    rax, rax
0x180002465  jz      short loc_180002470
0x180002467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000246c  test    al, al
0x18000246e  jnz     short loc_180002496
0x180002470  mov     rcx, rbx; this
0x180002473  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180002478  test    al, al
0x18000247a  jz      short loc_180002496
0x18000247c  mov     rdx, [rbx+18h]; SRWLock
0x180002480  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180002487  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000248c  mov     rcx, [rbx+18h]; SRWLock
0x180002490  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180002495  nop
0x180002496  mov     rbx, [rsp+28h+arg_0]
0x18000249b  add     rsp, 20h
0x18000249f  pop     rdi
0x1800024a0  retn
```
