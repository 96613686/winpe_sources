# MediaFrameImpl::~MediaFrameImpl(void)

- ea: `0x1800094e0`
- end: `0x1800095b2`
- name: `??1MediaFrameImpl@@MEAA@XZ`
- size: `210`
- prototype: `void __fastcall(MediaFrameImpl *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000842c`
- `0x180008494`
- `0x18000861c`
- `0x180008f80`
- `0x180039280`

## callees

- `0x1800094e0`
- `0x1800095c0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009506`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MediaFrameImpl::~MediaFrameImpl(MediaFrameImpl *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)this = &MediaFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'};
  *((_QWORD *)this + 1) = &Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  v2 = *((_QWORD *)this + 11);
  if ( v2 )
  {
    *((_QWORD *)this + 11) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
  {
    *((_QWORD *)this + 10) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(v3);
  }
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = *((_QWORD *)this + 8);
  if ( v5 )
  {
    *((_QWORD *)this + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 7);
  if ( v6 )
  {
    *((_QWORD *)this + 7) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = *((_QWORD *)this + 4);
  if ( v7 )
  {
    *((_QWORD *)this + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
}

```

## disassembly

```asm
0x1800094e0  mov     [rsp+arg_0], rbx
0x1800094e5  push    rdi
0x1800094e6  sub     rsp, 20h
0x1800094ea  mov     rbx, rcx
0x1800094ed  lea     rax, ??_7MediaFrameImpl@@6BIMediaFrame@Media@Windows@@@; const MediaFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x1800094f4  mov     [rcx], rax
0x1800094f7  lea     rax, ??_7?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geopoint *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800094fe  mov     [rcx+8], rax
0x180009502  mov     rcx, [rcx+60h]; string
0x180009506  call    cs:__imp_WindowsDeleteString
0x18000950c  xor     edi, edi
0x18000950e  mov     [rbx+60h], rdi
0x180009512  mov     rcx, [rbx+58h]
0x180009516  test    rcx, rcx
0x180009519  jz      short loc_18000952C
0x18000951b  mov     [rbx+58h], rdi
0x18000951f  mov     rax, [rcx]
0x180009522  mov     rax, [rax+10h]
0x180009526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952b  nop
0x18000952c  mov     rcx, [rbx+50h]
0x180009530  test    rcx, rcx
0x180009533  jz      short loc_18000953F
0x180009535  mov     [rbx+50h], rdi
0x180009539  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@567@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(void)
0x18000953e  nop
0x18000953f  mov     rcx, [rbx+48h]
0x180009543  test    rcx, rcx
0x180009546  jz      short loc_180009559
0x180009548  mov     [rbx+48h], rdi
0x18000954c  mov     rax, [rcx]
0x18000954f  mov     rax, [rax+10h]
0x180009553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009558  nop
0x180009559  mov     rcx, [rbx+40h]
0x18000955d  test    rcx, rcx
0x180009560  jz      short loc_180009573
0x180009562  mov     [rbx+40h], rdi
0x180009566  mov     rax, [rcx]
0x180009569  mov     rax, [rax+10h]
0x18000956d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009572  nop
0x180009573  mov     rcx, [rbx+38h]
0x180009577  test    rcx, rcx
0x18000957a  jz      short loc_18000958D
0x18000957c  mov     [rbx+38h], rdi
0x180009580  mov     rax, [rcx]
0x180009583  mov     rax, [rax+10h]
0x180009587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958c  nop
0x18000958d  mov     rcx, [rbx+20h]
0x180009591  test    rcx, rcx
0x180009594  jz      short loc_1800095A7
0x180009596  mov     [rbx+20h], rdi
0x18000959a  mov     rax, [rcx]
0x18000959d  mov     rax, [rax+10h]
0x1800095a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a6  nop
0x1800095a7  mov     rbx, [rsp+28h+arg_0]
0x1800095ac  add     rsp, 20h
0x1800095b0  pop     rdi
0x1800095b1  retn
```
