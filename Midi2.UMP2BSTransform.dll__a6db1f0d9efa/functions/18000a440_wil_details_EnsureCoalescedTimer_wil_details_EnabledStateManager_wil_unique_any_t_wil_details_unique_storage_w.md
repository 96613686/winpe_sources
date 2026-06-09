# `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000a440`
- end: `0x18000a48b`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `75`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000a440`
- `0x18000c604`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a45a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a47a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a47a`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rbx

  if ( LODWORD(Context->Ptr) )
  {
    v4 = Context + 1;
    AcquireSRWLockExclusive(Context + 1);
    if ( LODWORD(Context->Ptr) )
    {
      wil::details::EnabledStateManager::RecordCachedUsageUnderLock((__int64)Context);
      LOBYTE(Context[3].Ptr) = 0;
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
}

```

## disassembly

```asm
0x18000a440  mov     [rsp+arg_0], rbx
0x18000a445  push    rdi
0x18000a446  sub     rsp, 20h
0x18000a44a  mov     eax, [rdx]
0x18000a44c  mov     rdi, rdx
0x18000a44f  test    eax, eax
0x18000a451  jz      short loc_18000A480
0x18000a453  lea     rbx, [rdx+8]
0x18000a457  mov     rcx, rbx; SRWLock
0x18000a45a  call    cs:__imp_AcquireSRWLockExclusive
0x18000a460  mov     eax, [rdi]
0x18000a462  test    eax, eax
0x18000a464  jz      short loc_18000A472
0x18000a466  mov     rcx, rdi
0x18000a469  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18000a46e  mov     byte ptr [rdi+18h], 0
0x18000a472  test    rbx, rbx
0x18000a475  jz      short loc_18000A480
0x18000a477  mov     rcx, rbx; SRWLock
0x18000a47a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a480  mov     rbx, [rsp+28h+arg_0]
0x18000a485  add     rsp, 20h
0x18000a489  pop     rdi
0x18000a48a  retn
```
