# `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)'::`8'::_lambda_1_::_lambda_invoker_cdecl_(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800029a0`
- end: `0x1800029e5`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, RTL_SRWLOCK *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800029a0`
- `0x180003698`
- `0x180004b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800029b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800029b9`

## pseudocode

```c
void __fastcall `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_TIMER Timer)
{
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v5; // [rsp+38h] [rbp+10h] BYREF

  if ( LOBYTE(Context->Ptr) )
  {
    v4 = Context + 4;
    AcquireSRWLockExclusive(Context + 4);
    v5 = v4;
    BYTE1(Context[8].Ptr) = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
    wil::details::FeatureStateManager::FlushUsage((wil::details::FeatureStateManager *)Context);
  }
}

```

## disassembly

```asm
0x1800029a0  mov     [rsp+arg_0], rbx
0x1800029a5  push    rdi
0x1800029a6  sub     rsp, 20h
0x1800029aa  cmp     byte ptr [rdx], 0
0x1800029ad  mov     rdi, rdx
0x1800029b0  jz      short loc_1800029DA
0x1800029b2  lea     rbx, [rdx+20h]
0x1800029b6  mov     rcx, rbx; SRWLock
0x1800029b9  call    cs:__imp_AcquireSRWLockExclusive
0x1800029bf  lea     rcx, [rsp+28h+arg_8]
0x1800029c4  mov     [rsp+28h+arg_8], rbx
0x1800029c9  mov     byte ptr [rdi+41h], 0
0x1800029cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800029d2  mov     rcx, rdi; this
0x1800029d5  call    ?FlushUsage@FeatureStateManager@details@wil@@QEAAXXZ; wil::details::FeatureStateManager::FlushUsage(void)
0x1800029da  mov     rbx, [rsp+28h+arg_0]
0x1800029df  add     rsp, 20h
0x1800029e3  pop     rdi
0x1800029e4  retn
```
