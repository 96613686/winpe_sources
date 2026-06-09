# `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800024b0`
- end: `0x18000251c`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `108`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800024b0`
- `0x18000d808`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002506`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002506`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800024ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800024ce`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rdi

  if ( LOBYTE(Context->Ptr) )
  {
    v4 = Context + 5;
    AcquireSRWLockExclusive(Context + 5);
    if ( (PVOID)((char *)Context[30].Ptr - (char *)Context[29].Ptr) >= (PVOID)0xC )
    {
      wil_details_WriteSRUMWnfUsageBuffer(&Context[29]);
      Context[30].Ptr = Context[29].Ptr;
    }
    LOBYTE(Context[8].Ptr) = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
}

```

## disassembly

```asm
0x1800024b0  mov     [rsp+arg_0], rbx
0x1800024b5  mov     [rsp+arg_8], rsi
0x1800024ba  push    rdi
0x1800024bb  sub     rsp, 20h
0x1800024bf  cmp     byte ptr [rdx], 0
0x1800024c2  mov     rbx, rdx
0x1800024c5  jz      short loc_18000250C
0x1800024c7  lea     rdi, [rdx+28h]
0x1800024cb  mov     rcx, rdi; SRWLock
0x1800024ce  call    cs:__imp_AcquireSRWLockExclusive
0x1800024d4  lea     rsi, [rbx+0E8h]
0x1800024db  mov     rax, [rsi+8]
0x1800024df  sub     rax, [rsi]
0x1800024e2  cmp     rax, 0Ch
0x1800024e6  jb      short loc_1800024FA
0x1800024e8  mov     rcx, rsi
0x1800024eb  call    ?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z; wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)
0x1800024f0  mov     rax, [rsi]
0x1800024f3  mov     [rbx+0F0h], rax
0x1800024fa  mov     byte ptr [rbx+40h], 0
0x1800024fe  test    rdi, rdi
0x180002501  jz      short loc_18000250C
0x180002503  mov     rcx, rdi; SRWLock
0x180002506  call    cs:__imp_ReleaseSRWLockExclusive
0x18000250c  mov     rbx, [rsp+28h+arg_0]
0x180002511  mov     rsi, [rsp+28h+arg_8]
0x180002516  add     rsp, 20h
0x18000251a  pop     rdi
0x18000251b  retn
```
