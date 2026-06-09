# Microsoft::WRL::Details::Make<SoftwareBitmapImpl,IWICBitmap *,bool,tagRECT>(IWICBitmap * &&,bool &&,tagRECT &&)

- ea: `0x1800039d0`
- end: `0x180003bec`
- name: `??$Make@VSoftwareBitmapImpl@@PEAUIWICBitmap@@_NUtagRECT@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSoftwareBitmapImpl@@@12@$$QEAPEAUIWICBitmap@@$$QEA_N$$QEAUtagRECT@@@Z`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002940`

## callees

- `0x1800026c0`
- `0x1800039d0`
- `0x180003c00`
- `0x180026e0c`
- `0x180026e30`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003b76`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003b76`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003a57`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180003a57`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
SoftwareBitmapImpl **__fastcall Microsoft::WRL::Details::Make<SoftwareBitmapImpl,IWICBitmap *,bool,tagRECT>(
        SoftwareBitmapImpl **a1,
        _QWORD *a2,
        char *a3,
        __int64 a4)
{
  RTL_SRWLOCK *v8; // rax
  RTL_SRWLOCK *v9; // rbx
  char v10; // r12
  LPUNKNOWN v11; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r15
  PVOID Ptr; // rcx
  LPUNKNOWN v14; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+28h] [rbp-90h] BYREF
  _QWORD v17[4]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD pExceptionObject[13]; // [rsp+50h] [rbp-68h] BYREF

  *a1 = 0;
  v8 = (RTL_SRWLOCK *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v17[1] = v8;
  v17[2] = v8;
  if ( v8 )
  {
    v17[3] = v8;
    v10 = *a3;
    v17[0] = *a2;
    v8[5].Ptr = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
    v8[8].Ptr = 0;
    ppunkMarshal = 0;
    if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
    {
      v11 = ppunkMarshal;
      QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
      Ptr = v9[8].Ptr;
      if ( Ptr )
      {
        v9[8].Ptr = 0;
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      }
      ((void (__fastcall *)(LPUNKNOWN, GUID *, RTL_SRWLOCK *))QueryInterface)(
        v11,
        &GUID_00000003_0000_0000_c000_000000000046,
        &v9[8]);
    }
    v14 = ppunkMarshal;
    if ( ppunkMarshal )
    {
      ppunkMarshal = 0;
      ((void (__fastcall *)(LPUNKNOWN))v14->lpVtbl->Release)(v14);
    }
    v9[10].Ptr = (PVOID)1;
    v9->Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'};
    v9[1].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v9[2].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IClosable'};
    v9[3].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v9[4].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'};
    v9[5].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v9->Ptr = &SoftwareBitmapImpl::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'};
    v9[1].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v9[2].Ptr = &SoftwareBitmapImpl::`vftable'{for `Windows::Foundation::IClosable'};
    v9[3].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v9[4].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'};
    v9[5].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    LOBYTE(v9[11].Ptr) = v10;
    Microsoft::WRL::Details::Make<SoftwareBitmapState,IWICBitmap * &,tagRECT const &>(&v9[12], v17, a4);
    InitializeSRWLock(v9 + 13);
    if ( !v9[12].Ptr )
    {
      pExceptionObject[2] = 0;
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    if ( *a1 )
      SoftwareBitmapImpl::Release(*a1);
    *a1 = (SoftwareBitmapImpl *)v9;
    v9 = 0;
  }
  if ( v9 )
    operator delete(v9);
  return a1;
}

```

## disassembly

```asm
0x1800039d0  mov     [rsp+arg_0], rcx
0x1800039d5  push    rbx
0x1800039d6  push    rbp
0x1800039d7  push    rsi
0x1800039d8  push    rdi
0x1800039d9  push    r12
0x1800039db  push    r13
0x1800039dd  push    r14
0x1800039df  push    r15
0x1800039e1  sub     rsp, 78h
0x1800039e5  mov     rbp, r9
0x1800039e8  mov     rdi, r8
0x1800039eb  mov     r14, rdx
0x1800039ee  mov     rsi, rcx
0x1800039f1  xor     r13d, r13d
0x1800039f4  mov     [rsp+0B8h+var_98], r13d
0x1800039f9  mov     [rcx], r13
0x1800039fc  mov     [rsp+0B8h+var_98], 1
0x180003a04  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003a0b  mov     ecx, 70h ; 'p'; unsigned __int64
0x180003a10  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003a15  mov     rbx, rax
0x180003a18  mov     [rsp+0B8h+var_80], rax
0x180003a1d  mov     [rsp+0B8h+var_78], rax
0x180003a22  test    rax, rax
0x180003a25  jz      loc_180003B91
0x180003a2b  mov     [rsp+0B8h+var_70], rax
0x180003a30  movzx   r12d, byte ptr [rdi]
0x180003a34  mov     rax, [r14]
0x180003a37  mov     [rsp+0B8h+var_88], rax
0x180003a3c  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x180003a43  mov     [rbx+28h], rax
0x180003a47  mov     [rbx+40h], r13
0x180003a4b  mov     [rsp+0B8h+ppunkMarshal], r13
0x180003a50  lea     rdx, [rsp+0B8h+ppunkMarshal]; ppunkMarshal
0x180003a55  xor     ecx, ecx; punkOuter
0x180003a57  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180003a5d  test    eax, eax
0x180003a5f  js      short loc_180003A9D
0x180003a61  mov     rdi, [rsp+0B8h+ppunkMarshal]
0x180003a66  mov     rax, [rdi]
0x180003a69  mov     r15, [rax]
0x180003a6c  mov     rcx, [rbx+40h]
0x180003a70  test    rcx, rcx
0x180003a73  jz      short loc_180003A86
0x180003a75  mov     [rbx+40h], r13
0x180003a79  mov     rdx, [rcx]
0x180003a7c  mov     rax, [rdx+10h]
0x180003a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a85  nop
0x180003a86  lea     r8, [rbx+40h]
0x180003a8a  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180003a91  mov     rcx, rdi
0x180003a94  mov     rax, r15
0x180003a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a9c  nop
0x180003a9d  mov     rcx, [rsp+0B8h+ppunkMarshal]
0x180003aa2  test    rcx, rcx
0x180003aa5  jz      short loc_180003AB9
0x180003aa7  mov     [rsp+0B8h+ppunkMarshal], r13
0x180003aac  mov     rax, [rcx]
0x180003aaf  mov     rax, [rax+10h]
0x180003ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab8  nop
0x180003ab9  mov     qword ptr [rbx+50h], 1
0x180003ac1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6BISoftwareBitmap@Imaging@Graphics@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'}
0x180003ac8  mov     [rbx], rax
0x180003acb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x180003ad2  mov     [rbx+8], rax
0x180003ad6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6BIClosable@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IClosable'}
0x180003add  mov     [rbx+10h], rax
0x180003ae1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x180003ae8  mov     [rbx+18h], rax
0x180003aec  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISoftwareBitmapInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'}
0x180003af3  mov     [rbx+20h], rax
0x180003af7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180003afe  mov     [rbx+28h], rax
0x180003b02  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003b09  test    rcx, rcx
0x180003b0c  jz      short loc_180003B1B
0x180003b0e  mov     rax, [rcx]
0x180003b11  mov     rax, [rax+8]
0x180003b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1a  nop
0x180003b1b  lea     rax, ??_7SoftwareBitmapImpl@@6BISoftwareBitmap@Imaging@Graphics@Windows@@@; const SoftwareBitmapImpl::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'}
0x180003b22  mov     [rbx], rax
0x180003b25  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x180003b2c  mov     [rbx+8], rax
0x180003b30  lea     rax, ??_7SoftwareBitmapImpl@@6BIClosable@Foundation@Windows@@@; const SoftwareBitmapImpl::`vftable'{for `Windows::Foundation::IClosable'}
0x180003b37  mov     [rbx+10h], rax
0x180003b3b  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x180003b42  mov     [rbx+18h], rax
0x180003b46  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISoftwareBitmapInternal@@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'}
0x180003b4d  mov     [rbx+20h], rax
0x180003b51  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180003b58  mov     [rbx+28h], rax
0x180003b5c  mov     [rbx+58h], r12b
0x180003b60  mov     r8, rbp
0x180003b63  lea     rdx, [rsp+0B8h+var_88]
0x180003b68  lea     rcx, [rbx+60h]
0x180003b6c  call    ??$Make@VSoftwareBitmapState@@AEAPEAUIWICBitmap@@AEBUtagRECT@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSoftwareBitmapState@@@12@AEAPEAUIWICBitmap@@AEBUtagRECT@@@Z; Microsoft::WRL::Details::Make<SoftwareBitmapState,IWICBitmap * &,tagRECT const &>(IWICBitmap * &,tagRECT const &)
0x180003b71  nop
0x180003b72  lea     rcx, [rbx+68h]; SRWLock
0x180003b76  call    cs:__imp_InitializeSRWLock
0x180003b7c  cmp     qword ptr [rbx+60h], 0
0x180003b81  jz      short loc_180003BB2
0x180003b83  mov     rcx, [rsi]; this
0x180003b86  test    rcx, rcx
0x180003b89  jnz     short loc_180003BE4
0x180003b8b  mov     [rsi], rbx
0x180003b8e  mov     rbx, r13
0x180003b91  test    rbx, rbx
0x180003b94  jz      short loc_180003B9E
0x180003b96  mov     rcx, rbx; Block
0x180003b99  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b9e  mov     rax, rsi
0x180003ba1  add     rsp, 78h
0x180003ba5  pop     r15
0x180003ba7  pop     r14
0x180003ba9  pop     r13
0x180003bab  pop     r12
0x180003bad  pop     rdi
0x180003bae  pop     rsi
0x180003baf  pop     rbp
0x180003bb0  pop     rbx
0x180003bb1  retn
0x180003bb2  xorps   xmm0, xmm0
0x180003bb5  movups  [rsp+0B8h+var_60], xmm0
0x180003bba  lea     rax, aBadAllocation; "bad allocation"
0x180003bc1  mov     qword ptr [rsp+0B8h+var_60], rax
0x180003bc6  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180003bcd  mov     [rsp+0B8h+pExceptionObject], rax
0x180003bd2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180003bd9  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180003bde  call    _CxxThrowException_0
0x180003be4  call    ?Release@SoftwareBitmapImpl@@UEAAKXZ; SoftwareBitmapImpl::Release(void)
0x180003be9  jmp     short loc_180003B8B
```
