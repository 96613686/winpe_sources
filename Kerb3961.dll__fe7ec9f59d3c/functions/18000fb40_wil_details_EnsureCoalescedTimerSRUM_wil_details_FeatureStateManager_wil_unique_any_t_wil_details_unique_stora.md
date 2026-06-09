# `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000fb40`
- end: `0x18000fbac`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `108`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000fb40`
- `0x18001836c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fb5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fb5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb96`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rdi

  if ( *Context )
  {
    v4 = (RTL_SRWLOCK *)(Context + 40);
    AcquireSRWLockExclusive((PSRWLOCK)Context + 5);
    if ( *((_QWORD *)Context + 30) - *((_QWORD *)Context + 29) >= 0xCu )
    {
      wil_details_WriteSRUMWnfUsageBuffer((__int64 *)Context + 29);
      *((_QWORD *)Context + 30) = *((_QWORD *)Context + 29);
    }
    Context[64] = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
}

```

## disassembly

```asm
0x18000fb40  mov     [rsp+arg_0], rbx
0x18000fb45  mov     [rsp+arg_8], rsi
0x18000fb4a  push    rdi
0x18000fb4b  sub     rsp, 20h
0x18000fb4f  cmp     byte ptr [rdx], 0
0x18000fb52  mov     rbx, rdx
0x18000fb55  jz      short loc_18000FB9C
0x18000fb57  lea     rdi, [rdx+28h]
0x18000fb5b  mov     rcx, rdi; SRWLock
0x18000fb5e  call    cs:__imp_AcquireSRWLockExclusive
0x18000fb64  lea     rsi, [rbx+0E8h]
0x18000fb6b  mov     rax, [rsi+8]
0x18000fb6f  sub     rax, [rsi]
0x18000fb72  cmp     rax, 0Ch
0x18000fb76  jb      short loc_18000FB8A
0x18000fb78  mov     rcx, rsi
0x18000fb7b  call    ?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z; wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)
0x18000fb80  mov     rax, [rsi]
0x18000fb83  mov     [rbx+0F0h], rax
0x18000fb8a  mov     byte ptr [rbx+40h], 0
0x18000fb8e  test    rdi, rdi
0x18000fb91  jz      short loc_18000FB9C
0x18000fb93  mov     rcx, rdi; SRWLock
0x18000fb96  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fb9c  mov     rbx, [rsp+28h+arg_0]
0x18000fba1  mov     rsi, [rsp+28h+arg_8]
0x18000fba6  add     rsp, 20h
0x18000fbaa  pop     rdi
0x18000fbab  retn
```
