# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18002ad40`
- end: `0x18002ae85`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002af70`

## callees

- `0x1800042b4`
- `0x1800076ac`
- `0x18000faf0`
- `0x180010090`
- `0x18002ad40`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002ae09`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002ae09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae1e`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppListEntry_Core_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>'::`2'::FTMEventDelegate::`vftable';
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
0x18002ad40  mov     [rsp+arg_10], rbx
0x18002ad45  mov     [rsp+arg_18], rsi
0x18002ad4a  push    rdi
0x18002ad4b  sub     rsp, 20h
0x18002ad4f  mov     rsi, rcx
0x18002ad52  mov     qword ptr [rcx], 0
0x18002ad59  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ad60  mov     ecx, 40h ; '@'; unsigned __int64
0x18002ad65  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ad6a  mov     rbx, rax
0x18002ad6d  mov     [rsp+28h+arg_8], rax
0x18002ad72  test    rax, rax
0x18002ad75  jnz     short loc_18002AD81
0x18002ad77  mov     edi, 8007000Eh
0x18002ad7c  jmp     loc_18002AE68
0x18002ad81  lea     rax, ??_7?$IEventHandler@PEAVUserDeletedEventArgs@Internal@System@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>::`vftable'
0x18002ad88  mov     [rbx], rax
0x18002ad8b  lea     rdi, [rbx+8]
0x18002ad8f  mov     rcx, rdi; this
0x18002ad92  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18002ad97  mov     dword ptr [rbx+2Ch], 1
0x18002ad9e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>'}
0x18002ada5  mov     [rbx], rax
0x18002ada8  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002adaf  mov     [rdi], rax
0x18002adb2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002adb9  test    rcx, rcx
0x18002adbc  jz      short loc_18002ADCB
0x18002adbe  mov     rax, [rcx]
0x18002adc1  mov     rax, [rax+8]
0x18002adc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adca  nop
0x18002adcb  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>'}
0x18002add2  mov     [rbx], rax
0x18002add5  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppListEntry@Core@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Core::AppListEntry *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002addc  mov     [rdi], rax
0x18002addf  mov     dword ptr [rbx+30h], 0
0x18002ade6  mov     qword ptr [rbx+38h], 0
0x18002adee  mov     [rsp+28h+arg_0], rbx
0x18002adf3  mov     [rsp+28h+arg_8], 0
0x18002adfc  mov     r9d, 1F0003h; dwDesiredAccess
0x18002ae02  xor     r8d, r8d; dwFlags
0x18002ae05  xor     edx, edx; lpName
0x18002ae07  xor     ecx, ecx; lpEventAttributes
0x18002ae09  call    cs:__imp_CreateEventExW
0x18002ae10  nop     dword ptr [rax+rax+00h]
0x18002ae15  mov     [rbx+38h], rax
0x18002ae19  test    rax, rax
0x18002ae1c  jnz     short loc_18002AE49
0x18002ae1e  call    cs:__imp_GetLastError
0x18002ae25  nop     dword ptr [rax+rax+00h]
0x18002ae2a  mov     edi, eax
0x18002ae2c  test    eax, eax
0x18002ae2e  jle     short loc_18002AE39
0x18002ae30  movzx   edi, ax
0x18002ae33  or      edi, 80070000h
0x18002ae39  test    edi, edi
0x18002ae3b  jns     short loc_18002AE49
0x18002ae3d  lea     rcx, [rsp+28h+arg_0]
0x18002ae42  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae47  jmp     short loc_18002AE68
0x18002ae49  mov     rax, [rbx]
0x18002ae4c  mov     rcx, rbx
0x18002ae4f  mov     rax, [rax+8]
0x18002ae53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae58  nop
0x18002ae59  mov     [rsi], rbx
0x18002ae5c  lea     rcx, [rsp+28h+arg_0]
0x18002ae61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae66  xor     edi, edi
0x18002ae68  lea     rcx, [rsp+28h+arg_8]
0x18002ae6d  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@Windows@@V_lambda_b69842130674797083d794350c9637e7_@@$0?0PEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@67893@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAUITokenBrokerListenerInternal@23456@@Internal@Foundation@Windows@@U?$AggregateType@PEAVWebAccountDeletePendingEventArgs@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletePendingEventArgs@23456@@234@@Foundation@Windows@@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@3@PEAUIWebAccountDeletePendingEventArgs@56783@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *>,Windows::Foundation::Internal::AggregateType<Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>::*)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_,-1,Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *>>(void)
0x18002ae72  mov     eax, edi
0x18002ae74  mov     rbx, [rsp+28h+arg_10]
0x18002ae79  mov     rsi, [rsp+28h+arg_18]
0x18002ae7e  add     rsp, 20h
0x18002ae82  pop     rdi
0x18002ae83  retn
```
