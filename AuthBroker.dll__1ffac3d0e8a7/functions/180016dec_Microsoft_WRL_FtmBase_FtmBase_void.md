# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180016dec`
- end: `0x180016e71`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800162bc`
- `0x1800163f8`
- `0x180016abc`
- `0x180016bb8`
- `0x18001e5ac`
- `0x18001e6e8`

## callees

- `0x180006060`
- `0x180016dec`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180016e28`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180016e28`

## pseudocode

```c
void __fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  Microsoft::WRL::ComPtr<IMarshal> *p_marshaller; // r14
  IUnknown *ptr; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  Microsoft::WRL::ComPtr<IUnknown> unknown; // [rsp+50h] [rbp+8h] BYREF

  p_marshaller = &this->marshaller_;
  unknown.ptr_ = 0;
  this->lpVtbl = (Microsoft::WRL::FtmBase_vtbl *)Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  this->marshaller_.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&unknown);
  if ( CoCreateFreeThreadedMarshaler(0, &unknown.ptr_) >= 0 )
  {
    ptr = unknown.ptr_;
    QueryInterface = unknown.ptr_->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)p_marshaller);
    QueryInterface(ptr, &GUID_00000003_0000_0000_c000_000000000046, (void **)&p_marshaller->ptr_);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&unknown);
}

```

## disassembly

```asm
0x180016dec  push    rbx
0x180016dee  push    rsi
0x180016def  push    rdi
0x180016df0  push    r14
0x180016df2  sub     rsp, 28h
0x180016df6  lea     r14, [this+18h]
0x180016dfa  mov     [rsp+48h+unknown.ptr_], 0
0x180016e03  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x180016e0a  mov     rsi, this
0x180016e0d  mov     [this], rax
0x180016e10  lea     this, [rsp+48h+unknown]; this
0x180016e15  mov     qword ptr [r14], 0
0x180016e1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016e21  lea     rdx, [rsp+48h+unknown]; ppunkMarshal
0x180016e26  xor     ecx, ecx; punkOuter
0x180016e28  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180016e2e  test    eax, eax
0x180016e30  js      short loc_180016E5A
0x180016e32  mov     rbx, [rsp+48h+unknown.ptr_]
0x180016e37  mov     this, r14; this
0x180016e3a  mov     rax, [rbx]
0x180016e3d  mov     rdi, [rax]
0x180016e40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016e45  mov     r8, r14
0x180016e48  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180016e4f  mov     this, rbx
0x180016e52  mov     rax, rdi
0x180016e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e5a  lea     this, [rsp+48h+unknown]; this
0x180016e5f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016e64  mov     rax, rsi
0x180016e67  add     rsp, 28h
0x180016e6b  pop     r14
0x180016e6d  pop     rdi
0x180016e6e  pop     rsi
0x180016e6f  pop     rbx
0x180016e70  retn
```
