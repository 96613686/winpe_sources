# VideoFrameImpl::VideoFrameImpl(Windows::Graphics::Imaging::BitmapPixelFormat,int,int,Windows::Graphics::Imaging::BitmapAlphaMode)

- ea: `0x1800020d4`
- end: `0x1800022dd`
- name: `??0VideoFrameImpl@@QEAA@W4BitmapPixelFormat@Imaging@Graphics@Windows@@HHW4BitmapAlphaMode@234@@Z`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180001af8`

## callees

- `0x180001ec0`
- `0x1800020d4`
- `0x1800023c4`
- `0x180002474`
- `0x1800026c0`
- `0x180005cd0`
- `0x180006c94`
- `0x1800093d4`
- `0x180026e0c`
- `0x180026e30`
- `0x180038870`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002286`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002286`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000226a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000226a`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall VideoFrameImpl::VideoFrameImpl(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  SoftwareBitmapImpl *v11; // rax
  unsigned int String; // eax
  int v13; // edx
  SoftwareBitmapImpl *v15[5]; // [rsp+48h] [rbp-28h] BYREF

  Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>();
  *(_QWORD *)a1 = &VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'};
  *(_QWORD *)(a1 + 8) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 112) = &VideoFrameImpl::`vftable'{for `IWeakReferenceSource'};
  *(_QWORD *)(a1 + 120) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *(_QWORD *)(a1 + 128) = &VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'};
  *(_QWORD *)(a1 + 136) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *(_QWORD *)(a1 + 144) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'};
  *(_QWORD *)(a1 + 152) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_WORD *)(a1 + 216) = 0;
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qdddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a1, a2, a3, a4, a5);
  v15[0] = 0;
  v11 = (SoftwareBitmapImpl *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v15[1] = v11;
  v15[2] = v11;
  if ( v11 )
  {
    v15[3] = v11;
    v15[0] = (SoftwareBitmapImpl *)SoftwareBitmapImpl::SoftwareBitmapImpl(v11, a2, a3, a4, a5);
  }
  Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=<SoftwareBitmapImpl>(a1 + 176, v15);
  if ( v15[0] )
    SoftwareBitmapImpl::Release(v15[0]);
  MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>(a1 + 176);
  WindowsDeleteString(*(HSTRING *)(a1 + 96));
  *(_QWORD *)(a1 + 96) = 0;
  String = WindowsCreateString(L"VideoFrame", 0xAu, (HSTRING *)(a1 + 96));
  MF::ThrowIfFailed((MF *)String, v13);
  v15[0] = 0;
  MediaFrameImpl::Initialize((MediaFrameImpl *)a1);
  if ( v15[0] )
    (*(void (__fastcall **)(SoftwareBitmapImpl *))(*(_QWORD *)v15[0] + 16LL))(v15[0]);
  return a1;
}

```

## disassembly

```asm
0x1800020d4  mov     [rsp-28h+arg_8], rbx
0x1800020d9  mov     [rsp-28h+arg_10], rsi
0x1800020de  mov     [rsp-28h+arg_0], rcx
0x1800020e3  push    rbp
0x1800020e4  push    rdi
0x1800020e5  push    r12
0x1800020e7  push    r14
0x1800020e9  push    r15
0x1800020eb  mov     rbp, rsp
0x1800020ee  sub     rsp, 70h
0x1800020f2  mov     esi, r9d
0x1800020f5  mov     r14d, r8d
0x1800020f8  mov     r15d, edx
0x1800020fb  mov     rdi, rcx
0x1800020fe  mov     [rbp+var_30], 0
0x180002105  call    ??0?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIVideoFrame@Media@4@UIVideoFrame2@64@U?$CloakedIid@UIVideoFrameNative@@@WRL@Microsoft@@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@9Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>(void)
0x18000210a  nop
0x18000210b  lea     rax, ??_7VideoFrameImpl@@6BIMediaFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x180002112  mov     [rdi], rax
0x180002115  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000211c  mov     [rdi+8], rax
0x180002120  lea     rax, ??_7VideoFrameImpl@@6BIWeakReferenceSource@@@; const VideoFrameImpl::`vftable'{for `IWeakReferenceSource'}
0x180002127  mov     [rdi+70h], rax
0x18000212b  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIVideoFrame@Media@6@UIVideoFrame2@86@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180002132  mov     [rdi+78h], rax
0x180002136  lea     rax, ??_7VideoFrameImpl@@6BIVideoFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'}
0x18000213d  mov     [rdi+80h], rax
0x180002144  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrame2@Media@Windows@@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x18000214b  mov     [rdi+88h], rax
0x180002152  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrameNative@@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'}
0x180002159  mov     [rdi+90h], rax
0x180002160  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180002167  mov     [rdi+98h], rax
0x18000216e  lea     rbx, [rdi+0B0h]
0x180002175  mov     qword ptr [rbx], 0
0x18000217c  mov     qword ptr [rdi+0B8h], 0
0x180002187  mov     qword ptr [rdi+0C0h], 0
0x180002192  mov     qword ptr [rdi+0C8h], 0
0x18000219d  mov     qword ptr [rdi+0D0h], 0
0x1800021a8  mov     word ptr [rdi+0D8h], 0
0x1800021b1  mov     r12d, [rbp+arg_20]
0x1800021b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800021bc  jb      short loc_1800021E5
0x1800021be  mov     [rsp+70h+var_38], r12d
0x1800021c3  mov     [rsp+70h+var_40], esi
0x1800021c7  mov     [rsp+70h+var_48], r14d
0x1800021cc  mov     [rsp+70h+var_50], r15d
0x1800021d1  mov     r9, rdi
0x1800021d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021db  mov     rcx, [rcx+10h]
0x1800021df  call    WPP_SF_qdddd
0x1800021e4  nop
0x1800021e5  mov     [rbp+var_28], 0
0x1800021ed  mov     [rbp+var_30], 1
0x1800021f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800021fb  mov     ecx, 70h ; 'p'; unsigned __int64
0x180002200  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002205  mov     [rbp+var_20], rax
0x180002209  mov     [rbp+var_18], rax
0x18000220d  test    rax, rax
0x180002210  jz      short loc_180002233
0x180002212  mov     [rbp+var_10], rax
0x180002216  mov     [rsp+70h+var_50], r12d
0x18000221b  mov     r9d, esi
0x18000221e  mov     r8d, r14d
0x180002221  mov     edx, r15d
0x180002224  mov     rcx, rax
0x180002227  call    ??0SoftwareBitmapImpl@@QEAA@W4BitmapPixelFormat@Imaging@Graphics@Windows@@HHW4BitmapAlphaMode@234@@Z; SoftwareBitmapImpl::SoftwareBitmapImpl(Windows::Graphics::Imaging::BitmapPixelFormat,int,int,Windows::Graphics::Imaging::BitmapAlphaMode)
0x18000222c  nop
0x18000222d  mov     [rbp+var_28], rax
0x180002231  xor     eax, eax
0x180002233  test    rax, rax
0x180002236  jz      short loc_180002240
0x180002238  mov     rcx, rax; Block
0x18000223b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002240  lea     rdx, [rbp+var_28]
0x180002244  mov     rcx, rbx
0x180002247  call    ??$?4VSoftwareBitmapImpl@@@?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV?$ComPtr@VSoftwareBitmapImpl@@@12@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::operator=<SoftwareBitmapImpl>(Microsoft::WRL::ComPtr<SoftwareBitmapImpl> &&)
0x18000224c  nop
0x18000224d  mov     rcx, [rbp+var_28]; this
0x180002251  test    rcx, rcx
0x180002254  jz      short loc_18000225B
0x180002256  call    ?Release@SoftwareBitmapImpl@@UEAAKXZ; SoftwareBitmapImpl::Release(void)
0x18000225b  mov     rcx, rbx
0x18000225e  call    ??$ThrowIfBadAlloc@V?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@MF@@YAXAEBV?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@Z; MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>(Microsoft::WRL::ComPtr<AudioFrameState> const &)
0x180002263  lea     rbx, [rdi+60h]
0x180002267  mov     rcx, [rbx]; string
0x18000226a  call    cs:__imp_WindowsDeleteString
0x180002270  mov     qword ptr [rbx], 0
0x180002277  mov     r8, rbx; string
0x18000227a  mov     edx, 0Ah; length
0x18000227f  lea     rcx, sourceString; "VideoFrame"
0x180002286  call    cs:__imp_WindowsCreateString
0x18000228c  mov     ecx, eax; this
0x18000228e  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180002293  mov     [rbp+var_28], 0
0x18000229b  xor     r8d, r8d
0x18000229e  lea     rdx, [rbp+var_28]
0x1800022a2  mov     rcx, rdi; this
0x1800022a5  call    ?Initialize@MediaFrameImpl@@IEAAXAEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@_N@Z; MediaFrameImpl::Initialize(Microsoft::WRL::ComPtr<IMFSample> const &,bool)
0x1800022aa  nop
0x1800022ab  mov     rcx, [rbp+var_28]
0x1800022af  test    rcx, rcx
0x1800022b2  jz      short loc_1800022C1
0x1800022b4  mov     rax, [rcx]
0x1800022b7  mov     rax, [rax+10h]
0x1800022bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c0  nop
0x1800022c1  mov     rax, rdi
0x1800022c4  lea     r11, [rsp+70h+var_s0]
0x1800022c9  mov     rbx, [r11+38h]
0x1800022cd  mov     rsi, [r11+40h]
0x1800022d1  mov     rsp, r11
0x1800022d4  pop     r15
0x1800022d6  pop     r14
0x1800022d8  pop     r12
0x1800022da  pop     rdi
0x1800022db  pop     rbp
0x1800022dc  retn
```
