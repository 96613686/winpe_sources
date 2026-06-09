# Microsoft::WRL::Details::Make<SoftwareBitmapImpl,IWICBitmap * const &,bool>(IWICBitmap * const &,bool &&)

- ea: `0x180012340`
- end: `0x180012573`
- name: `??$Make@VSoftwareBitmapImpl@@AEBQEAUIWICBitmap@@_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSoftwareBitmapImpl@@@12@AEBQEAUIWICBitmap@@$$QEA_N@Z`
- size: `563`
- prototype: `SoftwareBitmapImpl **__fastcall(SoftwareBitmapImpl **, _QWORD *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011f10`

## callees

- `0x1800026c0`
- `0x180012340`
- `0x180012580`
- `0x180026e0c`
- `0x180026e30`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800124f5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800124f5`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800123d0`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800123d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
SoftwareBitmapImpl **__fastcall Microsoft::WRL::Details::Make<SoftwareBitmapImpl,IWICBitmap * const &,bool>(
        SoftwareBitmapImpl **a1,
        _QWORD *a2,
        char *a3)
{
  RTL_SRWLOCK *v6; // rax
  RTL_SRWLOCK *v7; // rbx
  char v8; // r15
  LPUNKNOWN v9; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  PVOID Ptr; // rcx
  LPUNKNOWN v12; // rcx
  _QWORD v14[4]; // [rsp+28h] [rbp-60h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-40h] BYREF
  LPUNKNOWN ppunkMarshal; // [rsp+A8h] [rbp+20h] BYREF

  *a1 = 0;
  v6 = (RTL_SRWLOCK *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v14[1] = v6;
  v14[2] = v6;
  if ( v6 )
  {
    v14[3] = v6;
    v8 = *a3;
    v14[0] = *a2;
    v6[5].Ptr = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
    v6[8].Ptr = 0;
    ppunkMarshal = 0;
    if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
    {
      v9 = ppunkMarshal;
      QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
      Ptr = v7[8].Ptr;
      if ( Ptr )
      {
        v7[8].Ptr = 0;
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      }
      ((void (__fastcall *)(LPUNKNOWN, GUID *, RTL_SRWLOCK *))QueryInterface)(
        v9,
        &GUID_00000003_0000_0000_c000_000000000046,
        &v7[8]);
    }
    v12 = ppunkMarshal;
    if ( ppunkMarshal )
    {
      ppunkMarshal = 0;
      ((void (__fastcall *)(LPUNKNOWN))v12->lpVtbl->Release)(v12);
    }
    v7[10].Ptr = (PVOID)1;
    v7->Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'};
    v7[1].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v7[2].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IClosable'};
    v7[3].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v7[4].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'};
    v7[5].Ptr = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v7->Ptr = &SoftwareBitmapImpl::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'};
    v7[1].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v7[2].Ptr = &SoftwareBitmapImpl::`vftable'{for `Windows::Foundation::IClosable'};
    v7[3].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
    v7[4].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'};
    v7[5].Ptr = &SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    LOBYTE(v7[11].Ptr) = v8;
    Microsoft::WRL::Details::Make<SoftwareBitmapState,IWICBitmap * &>(&v7[12], v14);
    InitializeSRWLock(v7 + 13);
    if ( !v7[12].Ptr )
    {
      pExceptionObject[2] = 0;
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    if ( *a1 )
      SoftwareBitmapImpl::Release(*a1);
    *a1 = (SoftwareBitmapImpl *)v7;
    v7 = 0;
  }
  if ( v7 )
    operator delete(v7);
  return a1;
}

```

## disassembly

```asm
0x180012340  mov     [rsp+arg_8], rbx
0x180012345  mov     [rsp+arg_10], rbp
0x18001234a  mov     [rsp+arg_0], rcx
0x18001234f  push    rsi
0x180012350  push    rdi
0x180012351  push    r12
0x180012353  push    r14
0x180012355  push    r15
0x180012357  sub     rsp, 60h
0x18001235b  mov     rdi, r8
0x18001235e  mov     rsi, rdx
0x180012361  mov     r14, rcx
0x180012364  xor     r12d, r12d
0x180012367  mov     [rsp+88h+var_68], r12d
0x18001236c  mov     [rcx], r12
0x18001236f  mov     [rsp+88h+var_68], 1
0x180012377  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001237e  mov     ecx, 70h ; 'p'; unsigned __int64
0x180012383  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012388  mov     rbx, rax
0x18001238b  mov     [rsp+88h+var_58], rax
0x180012390  mov     [rsp+88h+var_50], rax
0x180012395  test    rax, rax
0x180012398  jz      loc_180012510
0x18001239e  mov     [rsp+88h+var_48], rax
0x1800123a3  movzx   r15d, byte ptr [rdi]
0x1800123a7  mov     rax, [rsi]
0x1800123aa  mov     [rsp+88h+var_60], rax
0x1800123af  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800123b6  mov     [rbx+28h], rax
0x1800123ba  mov     [rbx+40h], r12
0x1800123be  mov     [rsp+88h+ppunkMarshal], r12
0x1800123c6  lea     rdx, [rsp+88h+ppunkMarshal]; ppunkMarshal
0x1800123ce  xor     ecx, ecx; punkOuter
0x1800123d0  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800123d6  test    eax, eax
0x1800123d8  js      short loc_180012419
0x1800123da  mov     rdi, [rsp+88h+ppunkMarshal]
0x1800123e2  mov     rax, [rdi]
0x1800123e5  mov     rbp, [rax]
0x1800123e8  mov     rcx, [rbx+40h]
0x1800123ec  test    rcx, rcx
0x1800123ef  jz      short loc_180012402
0x1800123f1  mov     [rbx+40h], r12
0x1800123f5  mov     rdx, [rcx]
0x1800123f8  mov     rax, [rdx+10h]
0x1800123fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012401  nop
0x180012402  lea     r8, [rbx+40h]
0x180012406  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001240d  mov     rcx, rdi
0x180012410  mov     rax, rbp
0x180012413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012418  nop
0x180012419  mov     rcx, [rsp+88h+ppunkMarshal]
0x180012421  test    rcx, rcx
0x180012424  jz      short loc_18001243B
0x180012426  mov     [rsp+88h+ppunkMarshal], r12
0x18001242e  mov     rax, [rcx]
0x180012431  mov     rax, [rax+10h]
0x180012435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001243a  nop
0x18001243b  mov     qword ptr [rbx+50h], 1
0x180012443  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6BISoftwareBitmap@Imaging@Graphics@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'}
0x18001244a  mov     [rbx], rax
0x18001244d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x180012454  mov     [rbx+8], rax
0x180012458  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6BIClosable@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IClosable'}
0x18001245f  mov     [rbx+10h], rax
0x180012463  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x18001246a  mov     [rbx+18h], rax
0x18001246e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISoftwareBitmapInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'}
0x180012475  mov     [rbx+20h], rax
0x180012479  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180012480  mov     [rbx+28h], rax
0x180012484  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001248b  test    rcx, rcx
0x18001248e  jz      short loc_18001249D
0x180012490  mov     rax, [rcx]
0x180012493  mov     rax, [rax+8]
0x180012497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001249c  nop
0x18001249d  lea     rax, ??_7SoftwareBitmapImpl@@6BISoftwareBitmap@Imaging@Graphics@Windows@@@; const SoftwareBitmapImpl::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'}
0x1800124a4  mov     [rbx], rax
0x1800124a7  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x1800124ae  mov     [rbx+8], rax
0x1800124b2  lea     rax, ??_7SoftwareBitmapImpl@@6BIClosable@Foundation@Windows@@@; const SoftwareBitmapImpl::`vftable'{for `Windows::Foundation::IClosable'}
0x1800124b9  mov     [rbx+10h], rax
0x1800124bd  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x1800124c4  mov     [rbx+18h], rax
0x1800124c8  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISoftwareBitmapInternal@@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'}
0x1800124cf  mov     [rbx+20h], rax
0x1800124d3  lea     rax, ??_7SoftwareBitmapImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const SoftwareBitmapImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800124da  mov     [rbx+28h], rax
0x1800124de  mov     [rbx+58h], r15b
0x1800124e2  lea     rdx, [rsp+88h+var_60]
0x1800124e7  lea     rcx, [rbx+60h]
0x1800124eb  call    ??$Make@VSoftwareBitmapState@@AEAPEAUIWICBitmap@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSoftwareBitmapState@@@12@AEAPEAUIWICBitmap@@@Z; Microsoft::WRL::Details::Make<SoftwareBitmapState,IWICBitmap * &>(IWICBitmap * &)
0x1800124f0  nop
0x1800124f1  lea     rcx, [rbx+68h]; SRWLock
0x1800124f5  call    cs:__imp_InitializeSRWLock
0x1800124fb  cmp     qword ptr [rbx+60h], 0
0x180012500  jz      short loc_180012539
0x180012502  mov     rcx, [r14]; this
0x180012505  test    rcx, rcx
0x180012508  jnz     short loc_18001256B
0x18001250a  mov     [r14], rbx
0x18001250d  mov     rbx, r12
0x180012510  test    rbx, rbx
0x180012513  jz      short loc_18001251D
0x180012515  mov     rcx, rbx; Block
0x180012518  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001251d  mov     rax, r14
0x180012520  lea     r11, [rsp+88h+var_28]
0x180012525  mov     rbx, [r11+38h]
0x180012529  mov     rbp, [r11+40h]
0x18001252d  mov     rsp, r11
0x180012530  pop     r15
0x180012532  pop     r14
0x180012534  pop     r12
0x180012536  pop     rdi
0x180012537  pop     rsi
0x180012538  retn
0x180012539  xorps   xmm0, xmm0
0x18001253c  movups  [rsp+88h+var_38], xmm0
0x180012541  lea     rax, aBadAllocation; "bad allocation"
0x180012548  mov     qword ptr [rsp+88h+var_38], rax
0x18001254d  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180012554  mov     [rsp+88h+pExceptionObject], rax
0x180012559  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180012560  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180012565  call    _CxxThrowException_0
0x18001256b  call    ?Release@SoftwareBitmapImpl@@UEAAKXZ; SoftwareBitmapImpl::Release(void)
0x180012570  jmp     short loc_18001250A
```
