# Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(void)

- ea: `0x1400047c4`
- end: `0x1400047db`
- name: `??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@V_lambda_766ca67daaea39a1a461b0c067384f4a_@@$0?0PEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@673@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreDispatcher@Core@UI@Windows@@PEAUICoreDispatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVAcceleratorKeyEventArgs@Core@UI@Windows@@PEAUIAcceleratorKeyEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@563@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400044c0`
- `0x140006c94`
- `0x140006d04`
- `0x140006d74`
- `0x140006de4`
- `0x140008624`
- `0x1400086f8`
- `0x14001312d`

## callees

- `0x1400047c4`
- `0x140012d4c`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    Common::GlobalHeap::Free(v1);
}

```

## disassembly

```asm
0x1400047c4  sub     rsp, 28h
0x1400047c8  mov     rcx, [rcx]; P
0x1400047cb  test    rcx, rcx
0x1400047ce  jz      short loc_1400047D6
0x1400047d0  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1400047d5  nop
0x1400047d6  add     rsp, 28h
0x1400047da  retn
```
