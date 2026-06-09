# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_>(_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_ &&)

- ea: `0x14000a250`
- end: `0x14000a309`
- name: `??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006580`

## callees

- `0x140008ca4`
- `0x14000a250`
- `0x14000aa7c`
- `0x14000ab38`
- `0x14000c4d0`
- `0x140010010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_>(
        _QWORD *a1,
        void *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = a2;
  *a1 = 0;
  v3 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v3;
  v4 = v3;
  if ( v3 )
  {
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>(v3);
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>'};
    v4[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_DWORD *)v4 + 15) = 1;
    if ( v5 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
    *v4 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>'};
    v4[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::Release();
    *a1 = v4;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(&v7);
  return a1;
}

```

## disassembly

```asm
0x14000a250  mov     [rsp+arg_0], rbx
0x14000a255  mov     [rsp+arg_8], rdx
0x14000a25a  push    rdi
0x14000a25b  sub     rsp, 20h
0x14000a25f  mov     rdi, rcx
0x14000a262  mov     qword ptr [rcx], 0
0x14000a269  mov     ecx, 48h ; 'H'; unsigned __int64
0x14000a26e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000a275  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000a27a  mov     [rsp+28h+arg_8], rax
0x14000a27f  mov     rbx, rax
0x14000a282  test    rax, rax
0x14000a285  jz      short loc_14000A2F1
0x14000a287  mov     rcx, rax
0x14000a28a  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>(void)
0x14000a28f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000a296  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@23@@WRL@Microsoft@@6B?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>'}
0x14000a29d  mov     [rbx], rax
0x14000a2a0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000a2a7  mov     [rbx+8], rax
0x14000a2ab  mov     dword ptr [rbx+3Ch], 1
0x14000a2b2  test    rcx, rcx
0x14000a2b5  jz      short loc_14000A2C3
0x14000a2b7  mov     rax, [rcx]
0x14000a2ba  mov     rax, [rax+8]
0x14000a2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2c3  lea     rax, ??_7?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@6B?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>::`vftable'{for `Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>'}
0x14000a2ca  mov     [rbx], rax
0x14000a2cd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000a2d4  mov     [rbx+8], rax
0x14000a2d8  mov     rcx, [rdi]
0x14000a2db  test    rcx, rcx
0x14000a2de  jz      short loc_14000A2E5
0x14000a2e0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::Release(void)
0x14000a2e5  mov     [rdi], rbx
0x14000a2e8  mov     [rsp+28h+arg_8], 0
0x14000a2f1  lea     rcx, [rsp+28h+arg_8]
0x14000a2f6  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(void)
0x14000a2fb  mov     rbx, [rsp+28h+arg_0]
0x14000a300  mov     rax, rdi
0x14000a303  add     rsp, 20h
0x14000a307  pop     rdi
0x14000a308  retn
```
