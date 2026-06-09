# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>(void)

- ea: `0x180006ff0`
- end: `0x1800070fc`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `268`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800023c4`
- `0x180006d38`
- `0x1800078bc`
- `0x180034c94`

## callees

- `0x180006ff0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180007023`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180007023`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  a1[5] = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  a1[8] = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v4 = a1[8];
    if ( v4 )
    {
      a1[8] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      a1 + 8);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  a1[10] = 1;
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'};
  a1[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
  a1[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IClosable'};
  a1[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'};
  a1[4] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'};
  a1[5] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x180006ff0  mov     [rsp+arg_8], rbx
0x180006ff5  mov     [rsp+arg_10], rbp
0x180006ffa  push    rsi
0x180006ffb  push    rdi
0x180006ffc  push    r14
0x180006ffe  sub     rsp, 20h
0x180007002  mov     rdi, rcx
0x180007005  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18000700c  mov     [rcx+28h], rax
0x180007010  xor     r14d, r14d
0x180007013  mov     [rcx+40h], r14
0x180007017  mov     [rsp+38h+ppunkMarshal], r14
0x18000701c  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x180007021  xor     ecx, ecx; punkOuter
0x180007023  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180007029  test    eax, eax
0x18000702b  js      short loc_180007069
0x18000702d  mov     rbx, [rsp+38h+ppunkMarshal]
0x180007032  mov     rax, [rbx]
0x180007035  mov     rbp, [rax]
0x180007038  mov     rcx, [rdi+40h]
0x18000703c  test    rcx, rcx
0x18000703f  jz      short loc_180007052
0x180007041  mov     [rdi+40h], r14
0x180007045  mov     rdx, [rcx]
0x180007048  mov     rax, [rdx+10h]
0x18000704c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007051  nop
0x180007052  lea     r8, [rdi+40h]
0x180007056  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000705d  mov     rcx, rbx
0x180007060  mov     rax, rbp
0x180007063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007068  nop
0x180007069  mov     rcx, [rsp+38h+ppunkMarshal]
0x18000706e  test    rcx, rcx
0x180007071  jz      short loc_180007085
0x180007073  mov     [rsp+38h+ppunkMarshal], r14
0x180007078  mov     rax, [rcx]
0x18000707b  mov     rax, [rax+10h]
0x18000707f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007084  nop
0x180007085  mov     qword ptr [rdi+50h], 1
0x18000708d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6BISoftwareBitmap@Imaging@Graphics@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Graphics::Imaging::ISoftwareBitmap'}
0x180007094  mov     [rdi], rax
0x180007097  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x18000709e  mov     [rdi+8], rax
0x1800070a2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6BIClosable@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IClosable'}
0x1800070a9  mov     [rdi+10h], rax
0x1800070ad  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>'}
0x1800070b4  mov     [rdi+18h], rax
0x1800070b8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UISoftwareBitmapInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ISoftwareBitmapInternal>'}
0x1800070bf  mov     [rdi+20h], rax
0x1800070c3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800070ca  mov     [rdi+28h], rax
0x1800070ce  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800070d5  test    rcx, rcx
0x1800070d8  jz      short loc_1800070E6
0x1800070da  mov     rax, [rcx]
0x1800070dd  mov     rax, [rax+8]
0x1800070e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070e6  mov     rax, rdi
0x1800070e9  mov     rbx, [rsp+38h+arg_8]
0x1800070ee  mov     rbp, [rsp+38h+arg_10]
0x1800070f3  add     rsp, 20h
0x1800070f7  pop     r14
0x1800070f9  pop     rdi
0x1800070fa  pop     rsi
0x1800070fb  retn
```
