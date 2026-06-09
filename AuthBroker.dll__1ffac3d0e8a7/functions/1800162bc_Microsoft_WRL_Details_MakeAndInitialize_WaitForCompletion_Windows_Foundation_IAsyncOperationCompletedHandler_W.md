# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800162bc`
- end: `0x1800163f2`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `310`
- prototype: `__int64 __fastcall(WaitForCompletion::__l2::FTMEventDelegate **result)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006a58`

## callees

- `0x180006060`
- `0x180006f58`
- `0x180008068`
- `0x1800162bc`
- `0x180016dec`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016384`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016393`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        WaitForCompletion::__l2::FTMEventDelegate **result)
{
  WaitForCompletion::__l2::FTMEventDelegate *buffer; // rdi
  signed int v3; // ebx
  _QWORD *v4; // rbx
  Microsoft::WRL::Details::ModuleBase *v5; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> >'::`2'::FTMEventDelegate> object; // [rsp+30h] [rbp+8h] BYREF
  Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> >'::`2'::FTMEventDelegate> allocator; // [rsp+38h] [rbp+10h] BYREF

  *result = 0;
  allocator.buffer_ = operator new(0x40u, &std::nothrow);
  buffer = (WaitForCompletion::__l2::FTMEventDelegate *)allocator.buffer_;
  if ( allocator.buffer_ )
  {
    v4 = (char *)allocator.buffer_ + 8;
    *(_QWORD *)allocator.buffer_ = Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase(&buffer->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >);
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    buffer->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>::Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider *> >::IUnknown::lpVtbl = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'};
    buffer->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::lpVtbl = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >_vtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    buffer->refcount_ = 1;
    if ( v5 )
      v5->IncrementObjectCount(v5);
    buffer->_status = Started;
    buffer->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>::Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider *> >::IUnknown::lpVtbl = (WaitForCompletion::__l2::FTMEventDelegate_vtbl *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>'::`2'::FTMEventDelegate::`vftable';
    buffer->_hEventCompleted = 0;
    *v4 = Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    object.ptr_ = buffer;
    allocator.buffer_ = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    buffer->_hEventCompleted = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      buffer->AddRef(buffer);
      *result = buffer;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&object);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&object);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>::~MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>((Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&allocator);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800162bc  mov     [rsp+arg_10], rbx
0x1800162c1  mov     [rsp+arg_18], rsi
0x1800162c6  push    rdi
0x1800162c7  sub     rsp, 20h
0x1800162cb  mov     rsi, result
0x1800162ce  mov     qword ptr [result], 0
0x1800162d5  mov     ecx, 40h ; '@'; count
0x1800162da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x1800162e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800162e6  mov     [rsp+28h+allocator.buffer_], rax
0x1800162eb  mov     rdi, rax
0x1800162ee  test    rax, rax
0x1800162f1  jnz     short loc_1800162FD
0x1800162f3  mov     ebx, 8007000Eh
0x1800162f8  jmp     loc_1800163D6
0x1800162fd  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x180016304  lea     rbx, [rdi+8]
0x180016308  mov     [rdi], rax
0x18001630b  mov     result, rbx; this
0x18001630e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180016313  mov     result, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001631a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x180016321  mov     [rdi], rax
0x180016324  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001632b  mov     [rbx], rax
0x18001632e  mov     dword ptr [rdi+2Ch], 1
0x180016335  test    result, result
0x180016338  jz      short loc_180016346
0x18001633a  mov     rax, [result]
0x18001633d  mov     rax, [rax+8]
0x180016341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016346  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x18001634d  mov     dword ptr [rdi+30h], 0
0x180016354  mov     [rdi], rax
0x180016357  mov     r9d, 1F0003h; dwDesiredAccess
0x18001635d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180016364  mov     qword ptr [rdi+38h], 0
0x18001636c  xor     r8d, r8d; dwFlags
0x18001636f  mov     [rbx], rax
0x180016372  xor     edx, edx; lpName
0x180016374  mov     [rsp+28h+object.ptr_], rdi
0x180016379  xor     ecx, ecx; lpEventAttributes
0x18001637b  mov     [rsp+28h+allocator.buffer_], 0
0x180016384  call    cs:__imp_CreateEventExW
0x18001638a  mov     [rdi+38h], rax
0x18001638e  test    rax, rax
0x180016391  jnz     short loc_1800163B8
0x180016393  call    cs:__imp_GetLastError
0x180016399  mov     ebx, eax
0x18001639b  test    eax, eax
0x18001639d  jle     short loc_1800163A8
0x18001639f  movzx   ebx, ax
0x1800163a2  or      ebx, 80070000h
0x1800163a8  test    ebx, ebx
0x1800163aa  jns     short loc_1800163B8
0x1800163ac  lea     result, [rsp+28h+object]; this
0x1800163b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800163b6  jmp     short loc_1800163D6
0x1800163b8  mov     rax, [rdi]
0x1800163bb  mov     result, rdi
0x1800163be  mov     rax, [rax+8]
0x1800163c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163c7  lea     result, [rsp+28h+object]; this
0x1800163cc  mov     [rsi], rdi
0x1800163cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800163d4  xor     ebx, ebx
0x1800163d6  lea     result, [rsp+28h+allocator]; this
0x1800163db  call    ??1?$MakeAllocator@VCWebAuthOperation@Web@Authentication@Security@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>::~MakeAllocator<Windows::Security::Authentication::Web::CWebAuthOperation>(void)
0x1800163e0  mov     rsi, [rsp+28h+arg_18]
0x1800163e5  mov     eax, ebx
0x1800163e7  mov     rbx, [rsp+28h+arg_10]
0x1800163ec  add     rsp, 20h
0x1800163f0  pop     rdi
0x1800163f1  retn
```
