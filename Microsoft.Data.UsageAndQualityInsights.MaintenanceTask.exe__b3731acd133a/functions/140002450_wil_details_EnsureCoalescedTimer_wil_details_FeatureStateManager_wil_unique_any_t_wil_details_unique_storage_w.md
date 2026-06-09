# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x140002450`
- end: `0x1400024d1`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `129`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x140002450`
- `0x1400044b4`
- `0x140005c54`
- `0x140006600`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002469`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002469`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000247b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000247b`

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
0x140002450  mov     [rsp+arg_0], rbx
0x140002455  push    rdi
0x140002456  sub     rsp, 20h
0x14000245a  mov     rbx, rdx
0x14000245d  cmp     byte ptr [rdx], 0
0x140002460  jz      short loc_1400024C6
0x140002462  lea     rdi, [rdx+20h]
0x140002466  mov     rcx, rdi; SRWLock
0x140002469  call    cs:__imp_AcquireSRWLockExclusive
0x14000246f  mov     byte ptr [rbx+41h], 0
0x140002473  test    rdi, rdi
0x140002476  jz      short loc_140002482
0x140002478  mov     rcx, rdi; SRWLock
0x14000247b  call    cs:__imp_ReleaseSRWLockExclusive
0x140002481  nop
0x140002482  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140002489  jnz     short loc_1400024C6
0x14000248b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140002492  test    rax, rax
0x140002495  jz      short loc_1400024A0
0x140002497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000249c  test    al, al
0x14000249e  jnz     short loc_1400024C6
0x1400024a0  mov     rcx, rbx; this
0x1400024a3  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400024a8  test    al, al
0x1400024aa  jz      short loc_1400024C6
0x1400024ac  mov     rdx, [rbx+18h]; SRWLock
0x1400024b0  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400024b7  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1400024bc  mov     rcx, [rbx+18h]; SRWLock
0x1400024c0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400024c5  nop
0x1400024c6  mov     rbx, [rsp+28h+arg_0]
0x1400024cb  add     rsp, 20h
0x1400024cf  pop     rdi
0x1400024d0  retn
```
