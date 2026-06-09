# `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1400123a0`
- end: `0x14001240c`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `108`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400123a0`
- `0x14001638c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400123be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400123be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400123f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400123f6`

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
0x1400123a0  mov     [rsp+arg_0], rbx
0x1400123a5  mov     [rsp+arg_8], rsi
0x1400123aa  push    rdi
0x1400123ab  sub     rsp, 20h
0x1400123af  cmp     byte ptr [rdx], 0
0x1400123b2  mov     rbx, rdx
0x1400123b5  jz      short loc_1400123FC
0x1400123b7  lea     rdi, [rdx+28h]
0x1400123bb  mov     rcx, rdi; SRWLock
0x1400123be  call    cs:__imp_AcquireSRWLockExclusive
0x1400123c4  lea     rsi, [rbx+0E8h]
0x1400123cb  mov     rax, [rsi+8]
0x1400123cf  sub     rax, [rsi]
0x1400123d2  cmp     rax, 0Ch
0x1400123d6  jb      short loc_1400123EA
0x1400123d8  mov     rcx, rsi
0x1400123db  call    ?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z; wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)
0x1400123e0  mov     rax, [rsi]
0x1400123e3  mov     [rbx+0F0h], rax
0x1400123ea  mov     byte ptr [rbx+40h], 0
0x1400123ee  test    rdi, rdi
0x1400123f1  jz      short loc_1400123FC
0x1400123f3  mov     rcx, rdi; SRWLock
0x1400123f6  call    cs:__imp_ReleaseSRWLockExclusive
0x1400123fc  mov     rbx, [rsp+28h+arg_0]
0x140012401  mov     rsi, [rsp+28h+arg_8]
0x140012406  add     rsp, 20h
0x14001240a  pop     rdi
0x14001240b  retn
```
