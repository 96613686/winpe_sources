# Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_>(_lambda_6412db1a0a1618af10ca0c7de7541180_ &&)

- ea: `0x140006d74`
- end: `0x140006ddb`
- name: `??$Callback@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowActivatedEventArgs@234@@Foundation@Windows@@V_lambda_6412db1a0a1618af10ca0c7de7541180_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowActivatedEventArgs@234@@Foundation@Windows@@@01@$$QEAV_lambda_6412db1a0a1618af10ca0c7de7541180_@@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140007080`

## callees

- `0x14000289c`
- `0x1400047c4`
- `0x140006d74`
- `0x140006f58`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_>(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // rbx
  void *v5; // rax
  __int64 *result; // rax
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v5 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v5;
  if ( v5 )
  {
    v4 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreWindow *,Windows::UI::Core::ICoreWindow *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::WindowActivatedEventArgs *,Windows::UI::Core::IWindowActivatedEventArgs *>>::*)(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowActivatedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_,-1,Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowActivatedEventArgs *>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_,-1,Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowActivatedEventArgs *>(
           v5,
           a2);
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(&v7);
  result = a1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x140006d74  mov     [rsp+arg_8], rbx
0x140006d79  mov     [rsp+arg_10], rsi
0x140006d7e  push    rdi
0x140006d7f  sub     rsp, 20h
0x140006d83  mov     rsi, rdx
0x140006d86  mov     rdi, rcx
0x140006d89  xor     ebx, ebx
0x140006d8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006d92  lea     ecx, [rbx+28h]; unsigned __int64
0x140006d95  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140006d9a  mov     [rsp+28h+arg_0], rax
0x140006d9f  test    rax, rax
0x140006da2  jz      short loc_140006DBB
0x140006da4  mov     rdx, rsi
0x140006da7  mov     rcx, rax
0x140006daa  call    ??0?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowActivatedEventArgs@234@@Foundation@Windows@@V_lambda_6412db1a0a1618af10ca0c7de7541180_@@$0?0PEAUICoreWindow@Core@UI@3@PEAUIWindowActivatedEventArgs@673@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreWindow@Core@UI@Windows@@PEAUICoreWindow@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVWindowActivatedEventArgs@Core@UI@Windows@@PEAUIWindowActivatedEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUICoreWindow@Core@UI@3@PEAUIWindowActivatedEventArgs@563@@Z@Details@WRL@Microsoft@@QEAA@$$QEAV_lambda_6412db1a0a1618af10ca0c7de7541180_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreWindow *,Windows::UI::Core::ICoreWindow *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::WindowActivatedEventArgs *,Windows::UI::Core::IWindowActivatedEventArgs *>>::*)(Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowActivatedEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_,-1,Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowActivatedEventArgs *>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>,_lambda_6412db1a0a1618af10ca0c7de7541180_,-1,Windows::UI::Core::ICoreWindow *,Windows::UI::Core::IWindowActivatedEventArgs *>(_lambda_6412db1a0a1618af10ca0c7de7541180_ &&)
0x140006daf  mov     rbx, rax
0x140006db2  mov     [rsp+28h+arg_0], 0
0x140006dbb  lea     rcx, [rsp+28h+arg_0]
0x140006dc0  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@V_lambda_766ca67daaea39a1a461b0c067384f4a_@@$0?0PEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@673@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreDispatcher@Core@UI@Windows@@PEAUICoreDispatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVAcceleratorKeyEventArgs@Core@UI@Windows@@PEAUIAcceleratorKeyEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@563@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(void)
0x140006dc5  mov     rsi, [rsp+28h+arg_10]
0x140006dca  mov     rax, rdi
0x140006dcd  mov     [rdi], rbx
0x140006dd0  mov     rbx, [rsp+28h+arg_8]
0x140006dd5  add     rsp, 20h
0x140006dd9  pop     rdi
0x140006dda  retn
```
