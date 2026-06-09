# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800449d8`
- end: `0x180044b1d`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044f08`

## callees

- `0x1800042b4`
- `0x1800076ac`
- `0x18000faf0`
- `0x180010090`
- `0x1800449d8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180044aa1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180044aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ab6`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVSessionResult_Provision_Management_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVSessionResult_Provision_Management_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVSessionResult_Provision_Management_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVSessionResult_Provision_Management_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVSessionResult_Provision_Management_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVSessionResult_Provision_Management_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVSessionResult_Provision_Management_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVSessionResult_Provision_Management_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>'::`2'::FTMEventDelegate::`vftable';
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
0x1800449d8  mov     [rsp+arg_10], rbx
0x1800449dd  mov     [rsp+arg_18], rsi
0x1800449e2  push    rdi
0x1800449e3  sub     rsp, 20h
0x1800449e7  mov     rsi, rcx
0x1800449ea  mov     qword ptr [rcx], 0
0x1800449f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800449f8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800449fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044a02  mov     rbx, rax
0x180044a05  mov     [rsp+28h+arg_8], rax
0x180044a0a  test    rax, rax
0x180044a0d  jnz     short loc_180044A19
0x180044a0f  mov     edi, 8007000Eh
0x180044a14  jmp     loc_180044B00
0x180044a19  lea     rax, ??_7?$IEventHandler@PEAVUserDeletedEventArgs@Internal@System@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>::`vftable'
0x180044a20  mov     [rbx], rax
0x180044a23  lea     rdi, [rbx+8]
0x180044a27  mov     rcx, rdi; this
0x180044a2a  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180044a2f  mov     dword ptr [rbx+2Ch], 1
0x180044a36  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>'}
0x180044a3d  mov     [rbx], rax
0x180044a40  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180044a47  mov     [rdi], rax
0x180044a4a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180044a51  test    rcx, rcx
0x180044a54  jz      short loc_180044A63
0x180044a56  mov     rax, [rcx]
0x180044a59  mov     rax, [rax+8]
0x180044a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a62  nop
0x180044a63  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>'}
0x180044a6a  mov     [rbx], rax
0x180044a6d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::SessionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180044a74  mov     [rdi], rax
0x180044a77  mov     dword ptr [rbx+30h], 0
0x180044a7e  mov     qword ptr [rbx+38h], 0
0x180044a86  mov     [rsp+28h+arg_0], rbx
0x180044a8b  mov     [rsp+28h+arg_8], 0
0x180044a94  mov     r9d, 1F0003h; dwDesiredAccess
0x180044a9a  xor     r8d, r8d; dwFlags
0x180044a9d  xor     edx, edx; lpName
0x180044a9f  xor     ecx, ecx; lpEventAttributes
0x180044aa1  call    cs:__imp_CreateEventExW
0x180044aa8  nop     dword ptr [rax+rax+00h]
0x180044aad  mov     [rbx+38h], rax
0x180044ab1  test    rax, rax
0x180044ab4  jnz     short loc_180044AE1
0x180044ab6  call    cs:__imp_GetLastError
0x180044abd  nop     dword ptr [rax+rax+00h]
0x180044ac2  mov     edi, eax
0x180044ac4  test    eax, eax
0x180044ac6  jle     short loc_180044AD1
0x180044ac8  movzx   edi, ax
0x180044acb  or      edi, 80070000h
0x180044ad1  test    edi, edi
0x180044ad3  jns     short loc_180044AE1
0x180044ad5  lea     rcx, [rsp+28h+arg_0]
0x180044ada  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044adf  jmp     short loc_180044B00
0x180044ae1  mov     rax, [rbx]
0x180044ae4  mov     rcx, rbx
0x180044ae7  mov     rax, [rax+8]
0x180044aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044af0  nop
0x180044af1  mov     [rsi], rbx
0x180044af4  lea     rcx, [rsp+28h+arg_0]
0x180044af9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044afe  xor     edi, edi
0x180044b00  lea     rcx, [rsp+28h+arg_8]
0x180044b05  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@Windows@@V_lambda_b69842130674797083d794350c9637e7_@@$0?0PEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAUITokenBrokerListenerInternal@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVWebAccountDeletePendingEventArgs@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletePendingEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@56783@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>(void)
0x180044b0a  mov     eax, edi
0x180044b0c  mov     rbx, [rsp+28h+arg_10]
0x180044b11  mov     rsi, [rsp+28h+arg_18]
0x180044b16  add     rsp, 20h
0x180044b1a  pop     rdi
0x180044b1b  retn
```
