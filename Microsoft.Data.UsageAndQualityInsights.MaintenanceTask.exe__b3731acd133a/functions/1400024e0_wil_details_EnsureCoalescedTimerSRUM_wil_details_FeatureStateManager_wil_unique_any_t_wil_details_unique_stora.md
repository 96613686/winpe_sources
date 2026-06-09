# `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1400024e0`
- end: `0x14000254c`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `108`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400024e0`
- `0x140008e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400024fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400024fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002536`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002536`

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
0x1400024e0  mov     [rsp+arg_0], rbx
0x1400024e5  mov     [rsp+arg_8], rsi
0x1400024ea  push    rdi
0x1400024eb  sub     rsp, 20h
0x1400024ef  cmp     byte ptr [rdx], 0
0x1400024f2  mov     rbx, rdx
0x1400024f5  jz      short loc_14000253C
0x1400024f7  lea     rdi, [rdx+28h]
0x1400024fb  mov     rcx, rdi; SRWLock
0x1400024fe  call    cs:__imp_AcquireSRWLockExclusive
0x140002504  lea     rsi, [rbx+0E8h]
0x14000250b  mov     rax, [rsi+8]
0x14000250f  sub     rax, [rsi]
0x140002512  cmp     rax, 0Ch
0x140002516  jb      short loc_14000252A
0x140002518  mov     rcx, rsi
0x14000251b  call    ?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z; wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)
0x140002520  mov     rax, [rsi]
0x140002523  mov     [rbx+0F0h], rax
0x14000252a  mov     byte ptr [rbx+40h], 0
0x14000252e  test    rdi, rdi
0x140002531  jz      short loc_14000253C
0x140002533  mov     rcx, rdi; SRWLock
0x140002536  call    cs:__imp_ReleaseSRWLockExclusive
0x14000253c  mov     rbx, [rsp+28h+arg_0]
0x140002541  mov     rsi, [rsp+28h+arg_8]
0x140002546  add     rsp, 20h
0x14000254a  pop     rdi
0x14000254b  retn
```
