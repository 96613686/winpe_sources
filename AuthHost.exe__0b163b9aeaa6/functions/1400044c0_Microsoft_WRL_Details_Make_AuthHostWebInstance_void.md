# Microsoft::WRL::Details::Make<AuthHostWebInstance,>(void)

- ea: `0x1400044c0`
- end: `0x14000454a`
- name: `??$Make@VAuthHostWebInstance@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAuthHostWebInstance@@@12@XZ`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140006418`

## callees

- `0x14000289c`
- `0x1400044c0`
- `0x1400045f8`
- `0x1400047c4`
- `0x140014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
AuthHostWebInstance **__fastcall Microsoft::WRL::Details::Make<AuthHostWebInstance,>(AuthHostWebInstance **a1)
{
  AuthHostWebInstance *v2; // rax
  AuthHostWebInstance *v3; // rdi
  AuthHostWebInstance *v5; // [rsp+58h] [rbp+10h] BYREF
  AuthHostWebInstance *v6; // [rsp+60h] [rbp+18h]
  AuthHostWebInstance *v7; // [rsp+68h] [rbp+20h]

  *a1 = 0;
  v2 = (AuthHostWebInstance *)operator new(0x2C8u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v2;
  v6 = v2;
  if ( v2 )
  {
    v7 = v2;
    v3 = AuthHostWebInstance::AuthHostWebInstance(v2);
    if ( *a1 )
      (*(void (__fastcall **)(AuthHostWebInstance *))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v3;
    v5 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(&v5);
  return a1;
}

```

## disassembly

```asm
0x1400044c0  mov     [rsp+arg_0], rcx
0x1400044c5  push    rbx
0x1400044c6  push    rdi
0x1400044c7  sub     rsp, 38h
0x1400044cb  mov     rbx, rcx
0x1400044ce  mov     [rsp+48h+var_28], 0
0x1400044d6  mov     qword ptr [rcx], 0
0x1400044dd  mov     [rsp+48h+var_28], 1
0x1400044e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400044ec  mov     ecx, 2C8h; unsigned __int64
0x1400044f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400044f6  mov     [rsp+48h+arg_8], rax
0x1400044fb  mov     [rsp+48h+arg_10], rax
0x140004500  test    rax, rax
0x140004503  jz      short loc_140004535
0x140004505  mov     [rsp+48h+arg_18], rax
0x14000450a  mov     rcx, rax; this
0x14000450d  call    ??0AuthHostWebInstance@@QEAA@XZ; AuthHostWebInstance::AuthHostWebInstance(void)
0x140004512  mov     rdi, rax
0x140004515  mov     rcx, [rbx]
0x140004518  test    rcx, rcx
0x14000451b  jz      short loc_140004529
0x14000451d  mov     rdx, [rcx]
0x140004520  mov     rax, [rdx+10h]
0x140004524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004529  mov     [rbx], rdi
0x14000452c  mov     [rsp+48h+arg_8], 0
0x140004535  lea     rcx, [rsp+48h+arg_8]
0x14000453a  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@V_lambda_766ca67daaea39a1a461b0c067384f4a_@@$0?0PEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@673@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreDispatcher@Core@UI@Windows@@PEAUICoreDispatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVAcceleratorKeyEventArgs@Core@UI@Windows@@PEAUIAcceleratorKeyEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@563@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(void)
0x14000453f  mov     rax, rbx
0x140004542  add     rsp, 38h
0x140004546  pop     rdi
0x140004547  pop     rbx
0x140004548  retn
```
