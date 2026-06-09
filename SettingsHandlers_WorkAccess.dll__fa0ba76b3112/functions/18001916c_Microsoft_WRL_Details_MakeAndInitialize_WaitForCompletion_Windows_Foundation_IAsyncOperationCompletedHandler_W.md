# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18001916c`
- end: `0x1800192b1`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019970`

## callees

- `0x1800042b4`
- `0x1800076ac`
- `0x18000faf0`
- `0x180010090`
- `0x18001916c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180019235`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180019235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001924a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001924a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v7 = v2;
    v8 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v2 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001916c  mov     [rsp+arg_10], rbx
0x180019171  mov     [rsp+arg_18], rsi
0x180019176  push    rdi
0x180019177  sub     rsp, 20h
0x18001917b  mov     rsi, rcx
0x18001917e  mov     qword ptr [rcx], 0
0x180019185  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001918c  mov     ecx, 40h ; '@'; unsigned __int64
0x180019191  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019196  mov     rbx, rax
0x180019199  mov     [rsp+28h+arg_8], rax
0x18001919e  test    rax, rax
0x1800191a1  jnz     short loc_1800191AD
0x1800191a3  mov     edi, 8007000Eh
0x1800191a8  jmp     loc_180019294
0x1800191ad  lea     rax, ??_7?$IEventHandler@PEAVUserDeletedEventArgs@Internal@System@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>::`vftable'
0x1800191b4  mov     [rbx], rax
0x1800191b7  lea     rdi, [rbx+8]
0x1800191bb  mov     rcx, rdi; this
0x1800191be  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800191c3  mov     dword ptr [rbx+2Ch], 1
0x1800191ca  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'}
0x1800191d1  mov     [rbx], rax
0x1800191d4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800191db  mov     [rdi], rax
0x1800191de  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800191e5  test    rcx, rcx
0x1800191e8  jz      short loc_1800191F7
0x1800191ea  mov     rax, [rcx]
0x1800191ed  mov     rax, [rax+8]
0x1800191f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191f6  nop
0x1800191f7  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'}
0x1800191fe  mov     [rbx], rax
0x180019201  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180019208  mov     [rdi], rax
0x18001920b  mov     dword ptr [rbx+30h], 0
0x180019212  mov     qword ptr [rbx+38h], 0
0x18001921a  mov     [rsp+28h+arg_0], rbx
0x18001921f  mov     [rsp+28h+arg_8], 0
0x180019228  mov     r9d, 1F0003h; dwDesiredAccess
0x18001922e  xor     r8d, r8d; dwFlags
0x180019231  xor     edx, edx; lpName
0x180019233  xor     ecx, ecx; lpEventAttributes
0x180019235  call    cs:__imp_CreateEventExW
0x18001923c  nop     dword ptr [rax+rax+00h]
0x180019241  mov     [rbx+38h], rax
0x180019245  test    rax, rax
0x180019248  jnz     short loc_180019275
0x18001924a  call    cs:__imp_GetLastError
0x180019251  nop     dword ptr [rax+rax+00h]
0x180019256  mov     edi, eax
0x180019258  test    eax, eax
0x18001925a  jle     short loc_180019265
0x18001925c  movzx   edi, ax
0x18001925f  or      edi, 80070000h
0x180019265  test    edi, edi
0x180019267  jns     short loc_180019275
0x180019269  lea     rcx, [rsp+28h+arg_0]
0x18001926e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019273  jmp     short loc_180019294
0x180019275  mov     rax, [rbx]
0x180019278  mov     rcx, rbx
0x18001927b  mov     rax, [rax+8]
0x18001927f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019284  nop
0x180019285  mov     [rsi], rbx
0x180019288  lea     rcx, [rsp+28h+arg_0]
0x18001928d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019292  xor     edi, edi
0x180019294  lea     rcx, [rsp+28h+arg_8]
0x180019299  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@Windows@@V_lambda_b69842130674797083d794350c9637e7_@@$0?0PEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAUITokenBrokerListenerInternal@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVWebAccountDeletePendingEventArgs@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletePendingEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@56783@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>(void)
0x18001929e  mov     eax, edi
0x1800192a0  mov     rbx, [rsp+28h+arg_10]
0x1800192a5  mov     rsi, [rsp+28h+arg_18]
0x1800192aa  add     rsp, 20h
0x1800192ae  pop     rdi
0x1800192af  retn
```
