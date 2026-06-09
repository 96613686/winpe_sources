# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180044dbc`
- end: `0x180044f01`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180045360`

## callees

- `0x1800042b4`
- `0x1800076ac`
- `0x18000faf0`
- `0x180010090`
- `0x180044dbc`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180044e85`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180044e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044e9a`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
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
0x180044dbc  mov     [rsp+arg_10], rbx
0x180044dc1  mov     [rsp+arg_18], rsi
0x180044dc6  push    rdi
0x180044dc7  sub     rsp, 20h
0x180044dcb  mov     rsi, rcx
0x180044dce  mov     qword ptr [rcx], 0
0x180044dd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044ddc  mov     ecx, 40h ; '@'; unsigned __int64
0x180044de1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044de6  mov     rbx, rax
0x180044de9  mov     [rsp+28h+arg_8], rax
0x180044dee  test    rax, rax
0x180044df1  jnz     short loc_180044DFD
0x180044df3  mov     edi, 8007000Eh
0x180044df8  jmp     loc_180044EE4
0x180044dfd  lea     rax, ??_7?$IEventHandler@PEAVUserDeletedEventArgs@Internal@System@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>::`vftable'
0x180044e04  mov     [rbx], rax
0x180044e07  lea     rdi, [rbx+8]
0x180044e0b  mov     rcx, rdi; this
0x180044e0e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180044e13  mov     dword ptr [rbx+2Ch], 1
0x180044e1a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x180044e21  mov     [rbx], rax
0x180044e24  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180044e2b  mov     [rdi], rax
0x180044e2e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180044e35  test    rcx, rcx
0x180044e38  jz      short loc_180044E47
0x180044e3a  mov     rax, [rcx]
0x180044e3d  mov     rax, [rax+8]
0x180044e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e46  nop
0x180044e47  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x180044e4e  mov     [rbx], rax
0x180044e51  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180044e58  mov     [rdi], rax
0x180044e5b  mov     dword ptr [rbx+30h], 0
0x180044e62  mov     qword ptr [rbx+38h], 0
0x180044e6a  mov     [rsp+28h+arg_0], rbx
0x180044e6f  mov     [rsp+28h+arg_8], 0
0x180044e78  mov     r9d, 1F0003h; dwDesiredAccess
0x180044e7e  xor     r8d, r8d; dwFlags
0x180044e81  xor     edx, edx; lpName
0x180044e83  xor     ecx, ecx; lpEventAttributes
0x180044e85  call    cs:__imp_CreateEventExW
0x180044e8c  nop     dword ptr [rax+rax+00h]
0x180044e91  mov     [rbx+38h], rax
0x180044e95  test    rax, rax
0x180044e98  jnz     short loc_180044EC5
0x180044e9a  call    cs:__imp_GetLastError
0x180044ea1  nop     dword ptr [rax+rax+00h]
0x180044ea6  mov     edi, eax
0x180044ea8  test    eax, eax
0x180044eaa  jle     short loc_180044EB5
0x180044eac  movzx   edi, ax
0x180044eaf  or      edi, 80070000h
0x180044eb5  test    edi, edi
0x180044eb7  jns     short loc_180044EC5
0x180044eb9  lea     rcx, [rsp+28h+arg_0]
0x180044ebe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044ec3  jmp     short loc_180044EE4
0x180044ec5  mov     rax, [rbx]
0x180044ec8  mov     rcx, rbx
0x180044ecb  mov     rax, [rax+8]
0x180044ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ed4  nop
0x180044ed5  mov     [rsi], rbx
0x180044ed8  lea     rcx, [rsp+28h+arg_0]
0x180044edd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044ee2  xor     edi, edi
0x180044ee4  lea     rcx, [rsp+28h+arg_8]
0x180044ee9  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@Windows@@V_lambda_b69842130674797083d794350c9637e7_@@$0?0PEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAUITokenBrokerListenerInternal@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVWebAccountDeletePendingEventArgs@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletePendingEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@56783@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>(void)
0x180044eee  mov     eax, edi
0x180044ef0  mov     rbx, [rsp+28h+arg_10]
0x180044ef5  mov     rsi, [rsp+28h+arg_18]
0x180044efa  add     rsp, 20h
0x180044efe  pop     rdi
0x180044eff  retn
```
