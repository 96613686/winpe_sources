# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800236c0`
- end: `0x180023741`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `129`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800236c0`
- `0x1800241dc`
- `0x180024640`
- `0x180024c38`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800236d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800236d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800236eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800236eb`

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
0x1800236c0  mov     [rsp+arg_0], rbx
0x1800236c5  push    rdi
0x1800236c6  sub     rsp, 20h
0x1800236ca  mov     rbx, rdx
0x1800236cd  cmp     byte ptr [rdx], 0
0x1800236d0  jz      short loc_180023736
0x1800236d2  lea     rdi, [rdx+20h]
0x1800236d6  mov     rcx, rdi; SRWLock
0x1800236d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800236df  mov     byte ptr [rbx+41h], 0
0x1800236e3  test    rdi, rdi
0x1800236e6  jz      short loc_1800236F2
0x1800236e8  mov     rcx, rdi; SRWLock
0x1800236eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800236f1  nop
0x1800236f2  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800236f9  jnz     short loc_180023736
0x1800236fb  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180023702  test    rax, rax
0x180023705  jz      short loc_180023710
0x180023707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002370c  test    al, al
0x18002370e  jnz     short loc_180023736
0x180023710  mov     rcx, rbx; this
0x180023713  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180023718  test    al, al
0x18002371a  jz      short loc_180023736
0x18002371c  mov     rdx, [rbx+18h]; SRWLock
0x180023720  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180023727  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18002372c  mov     rcx, [rbx+18h]; SRWLock
0x180023730  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180023735  nop
0x180023736  mov     rbx, [rsp+28h+arg_0]
0x18002373b  add     rsp, 20h
0x18002373f  pop     rdi
0x180023740  retn
```
