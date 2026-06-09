# VideoFrameImpl::VideoFrameImpl(Windows::Graphics::Imaging::ISoftwareBitmap *,bool)

- ea: `0x180007e60`
- end: `0x180007fc5`
- name: `??0VideoFrameImpl@@QEAA@PEAUISoftwareBitmap@Imaging@Graphics@Windows@@_N@Z`
- size: `357`
- prototype: `VideoFrameImpl *__fastcall(VideoFrameImpl *__hidden this, struct Windows::Graphics::Imaging::ISoftwareBitmap *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cc38`

## callees

- `0x18000266c`
- `0x180005cd0`
- `0x180006c94`
- `0x180007e60`
- `0x1800093d4`
- `0x180038970`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007f74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007f74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007f58`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
VideoFrameImpl *__fastcall VideoFrameImpl::VideoFrameImpl(
        VideoFrameImpl *this,
        struct Windows::Graphics::Imaging::ISoftwareBitmap *a2)
{
  __int64 v4; // r8
  unsigned int String; // eax
  int v6; // edx

  Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>();
  *(_QWORD *)this = &VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'};
  *((_QWORD *)this + 1) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 14) = &VideoFrameImpl::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 15) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *((_QWORD *)this + 16) = &VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'};
  *((_QWORD *)this + 17) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *((_QWORD *)this + 18) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'};
  *((_QWORD *)this + 19) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *((_QWORD *)this + 22) = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef((char *)this + 176);
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_WORD *)this + 108) = 0;
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v4, this, a2);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  String = WindowsCreateString(L"VideoFrame", 0xAu, (HSTRING *)this + 12);
  MF::ThrowIfFailed((MF *)String, v6);
  MediaFrameImpl::Initialize(this);
  return this;
}

```

## disassembly

```asm
0x180007e60  mov     [rsp+arg_10], rbx
0x180007e65  mov     [rsp+arg_18], rsi
0x180007e6a  mov     [rsp+arg_0], rcx
0x180007e6f  push    rdi
0x180007e70  sub     rsp, 30h
0x180007e74  mov     sil, r8b
0x180007e77  mov     rbx, rdx
0x180007e7a  mov     rdi, rcx
0x180007e7d  call    ??0?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIVideoFrame@Media@4@UIVideoFrame2@64@U?$CloakedIid@UIVideoFrameNative@@@WRL@Microsoft@@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@9Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>(void)
0x180007e82  nop
0x180007e83  lea     rax, ??_7VideoFrameImpl@@6BIMediaFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x180007e8a  mov     [rdi], rax
0x180007e8d  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180007e94  mov     [rdi+8], rax
0x180007e98  lea     rax, ??_7VideoFrameImpl@@6BIWeakReferenceSource@@@; const VideoFrameImpl::`vftable'{for `IWeakReferenceSource'}
0x180007e9f  mov     [rdi+70h], rax
0x180007ea3  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIVideoFrame@Media@6@UIVideoFrame2@86@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180007eaa  mov     [rdi+78h], rax
0x180007eae  lea     rax, ??_7VideoFrameImpl@@6BIVideoFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'}
0x180007eb5  mov     [rdi+80h], rax
0x180007ebc  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrame2@Media@Windows@@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180007ec3  mov     [rdi+88h], rax
0x180007eca  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrameNative@@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'}
0x180007ed1  mov     [rdi+90h], rax
0x180007ed8  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180007edf  mov     [rdi+98h], rax
0x180007ee6  lea     rcx, [rdi+0B0h]
0x180007eed  mov     [rcx], rbx
0x180007ef0  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180007ef5  nop
0x180007ef6  mov     qword ptr [rdi+0B8h], 0
0x180007f01  mov     qword ptr [rdi+0C0h], 0
0x180007f0c  mov     qword ptr [rdi+0C8h], 0
0x180007f17  mov     qword ptr [rdi+0D0h], 0
0x180007f22  mov     word ptr [rdi+0D8h], 0
0x180007f2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180007f32  jb      short loc_180007F51
0x180007f34  mov     edx, 0Bh
0x180007f39  mov     [rsp+38h+var_18], rbx
0x180007f3e  mov     r9, rdi
0x180007f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f48  mov     rcx, [rcx+10h]
0x180007f4c  call    WPP_SF_qq
0x180007f51  lea     rbx, [rdi+60h]
0x180007f55  mov     rcx, [rbx]; string
0x180007f58  call    cs:__imp_WindowsDeleteString
0x180007f5e  mov     qword ptr [rbx], 0
0x180007f65  mov     r8, rbx; string
0x180007f68  mov     edx, 0Ah; length
0x180007f6d  lea     rcx, sourceString; "VideoFrame"
0x180007f74  call    cs:__imp_WindowsCreateString
0x180007f7a  mov     ecx, eax; this
0x180007f7c  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180007f81  mov     [rsp+38h+arg_8], 0
0x180007f8a  mov     r8b, sil
0x180007f8d  lea     rdx, [rsp+38h+arg_8]
0x180007f92  mov     rcx, rdi; this
0x180007f95  call    ?Initialize@MediaFrameImpl@@IEAAXAEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@_N@Z; MediaFrameImpl::Initialize(Microsoft::WRL::ComPtr<IMFSample> const &,bool)
0x180007f9a  nop
0x180007f9b  mov     rcx, [rsp+38h+arg_8]
0x180007fa0  test    rcx, rcx
0x180007fa3  jz      short loc_180007FB2
0x180007fa5  mov     rax, [rcx]
0x180007fa8  mov     rax, [rax+10h]
0x180007fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb1  nop
0x180007fb2  mov     rax, rdi
0x180007fb5  mov     rbx, [rsp+38h+arg_10]
0x180007fba  mov     rsi, [rsp+38h+arg_18]
0x180007fbf  add     rsp, 30h
0x180007fc3  pop     rdi
0x180007fc4  retn
```
