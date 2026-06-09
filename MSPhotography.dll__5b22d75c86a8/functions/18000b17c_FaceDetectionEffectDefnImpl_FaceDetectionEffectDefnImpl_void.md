# FaceDetectionEffectDefnImpl::~FaceDetectionEffectDefnImpl(void)

- ea: `0x18000b17c`
- end: `0x18000b222`
- name: `??1FaceDetectionEffectDefnImpl@@EEAA@XZ`
- size: `166`
- prototype: `void __fastcall(FaceDetectionEffectDefnImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b270`

## callees

- `0x180005660`
- `0x18000b14c`
- `0x18000b17c`
- `0x18000b480`
- `0x18000c0b8`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b207`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b207`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FaceDetectionEffectDefnImpl::~FaceDetectionEffectDefnImpl(FaceDetectionEffectDefnImpl *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &FaceDetectionEffectDefnImpl::`vftable'{for `Windows::Media::Core::IFaceDetectionEffectDefinition'};
  *((_QWORD *)this + 1) = &FaceDetectionEffectDefnImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Media::Effects::IVideoEffectDefinition,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &FaceDetectionEffectDefnImpl::`vftable'{for `Windows::Media::Effects::IVideoEffectDefinition'};
  *((_QWORD *)this + 3) = &FaceDetectionEffectDefnImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, WPP_309d84805ff9309032e4a9a4f72506c8_Traceguids, v2);
  v3 = *((_QWORD *)this + 13);
  if ( v3 )
  {
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 96);
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::IIterable<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::IIterable<enum Windows::Graphics::Imaging::BitmapPixelFormat>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18000b17c  push    rbx
0x18000b17e  sub     rsp, 20h
0x18000b182  mov     rbx, rcx
0x18000b185  lea     rax, ??_7FaceDetectionEffectDefnImpl@@6BIFaceDetectionEffectDefinition@Core@Media@Windows@@@; const FaceDetectionEffectDefnImpl::`vftable'{for `Windows::Media::Core::IFaceDetectionEffectDefinition'}
0x18000b18c  mov     [rcx], rax
0x18000b18f  lea     rax, ??_7FaceDetectionEffectDefnImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIVideoEffectDefinition@Effects@Media@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const FaceDetectionEffectDefnImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Media::Effects::IVideoEffectDefinition,Microsoft::WRL::FtmBase>'}
0x18000b196  mov     [rcx+8], rax
0x18000b19a  lea     rax, ??_7FaceDetectionEffectDefnImpl@@6BIVideoEffectDefinition@Effects@Media@Windows@@@; const FaceDetectionEffectDefnImpl::`vftable'{for `Windows::Media::Effects::IVideoEffectDefinition'}
0x18000b1a1  mov     [rcx+10h], rax
0x18000b1a5  lea     rax, ??_7FaceDetectionEffectDefnImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const FaceDetectionEffectDefnImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000b1ac  mov     [rcx+18h], rax
0x18000b1b0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000b1b5  cmp     al, 20h ; ' '
0x18000b1b7  jb      short loc_18000B1DC
0x18000b1b9  mov     edx, 0Bh
0x18000b1be  mov     r9, rcx
0x18000b1c1  lea     r8, WPP_309d84805ff9309032e4a9a4f72506c8_Traceguids
0x18000b1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1cf  mov     rcx, [rcx+0D8h]
0x18000b1d6  call    WPP_SF_q
0x18000b1db  nop
0x18000b1dc  mov     rcx, [rbx+68h]
0x18000b1e0  test    rcx, rcx
0x18000b1e3  jz      short loc_18000B1FA
0x18000b1e5  mov     qword ptr [rbx+68h], 0
0x18000b1ed  mov     rax, [rcx]
0x18000b1f0  mov     rax, [rax+10h]
0x18000b1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1f9  nop
0x18000b1fa  lea     rcx, [rbx+60h]
0x18000b1fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b203  mov     rcx, [rbx+50h]; string
0x18000b207  call    cs:__imp_WindowsDeleteString
0x18000b20d  mov     qword ptr [rbx+50h], 0
0x18000b215  mov     rcx, rbx
0x18000b218  add     rsp, 20h
0x18000b21c  pop     rbx
0x18000b21d  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@Collections@Foundation@Windows@@U?$IIterable@W4BitmapPixelFormat@Imaging@Graphics@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::IIterable<Windows::Graphics::Imaging::BitmapPixelFormat>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<Windows::Graphics::Imaging::BitmapPixelFormat>,Windows::Foundation::Collections::IIterable<Windows::Graphics::Imaging::BitmapPixelFormat>,Microsoft::WRL::FtmBase>(void)
```
