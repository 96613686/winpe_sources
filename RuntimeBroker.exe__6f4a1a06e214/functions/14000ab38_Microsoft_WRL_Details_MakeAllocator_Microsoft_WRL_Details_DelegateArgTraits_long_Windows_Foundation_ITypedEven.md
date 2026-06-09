# Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(void)

- ea: `0x14000ab38`
- end: `0x14000ab4f`
- name: `??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a250`

## callees

- `0x14000ab38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ab44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ab44`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x14000ab38  sub     rsp, 28h
0x14000ab3c  mov     rcx, [rcx]; pv
0x14000ab3f  test    rcx, rcx
0x14000ab42  jz      short loc_14000AB4A
0x14000ab44  call    cs:__imp_CoTaskMemFree
0x14000ab4a  add     rsp, 28h
0x14000ab4e  retn
```
