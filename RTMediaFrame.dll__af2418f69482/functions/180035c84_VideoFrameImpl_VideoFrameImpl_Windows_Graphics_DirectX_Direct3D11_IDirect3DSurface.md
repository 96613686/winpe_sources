# VideoFrameImpl::VideoFrameImpl(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)

- ea: `0x180035c84`
- end: `0x180035e38`
- name: `??0VideoFrameImpl@@QEAA@PEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@Z`
- size: `436`
- prototype: `VideoFrameImpl *__fastcall(VideoFrameImpl *__hidden this, struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024fe4`

## callees

- `0x1800019c0`
- `0x18000266c`
- `0x180005cd0`
- `0x180006c94`
- `0x1800093d4`
- `0x18001eca4`
- `0x180026920`
- `0x180035c84`
- `0x1800368b0`
- `0x180038970`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035dbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035dbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035da2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035da2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
VideoFrameImpl *__fastcall VideoFrameImpl::VideoFrameImpl(
        VideoFrameImpl *this,
        struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *a2)
{
  unsigned int v4; // eax
  int v5; // edx
  __int64 v6; // rcx
  unsigned int String; // eax
  int v8; // edx
  __int64 v9; // r8
  _QWORD v11[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF
  int v13; // [rsp+50h] [rbp-18h]

  v11[1] = this;
  v11[0] = a2;
  Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>();
  *(_QWORD *)this = &VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'};
  *((_QWORD *)this + 1) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 14) = &VideoFrameImpl::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 15) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *((_QWORD *)this + 16) = &VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'};
  *((_QWORD *)this + 17) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *((_QWORD *)this + 18) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'};
  *((_QWORD *)this + 19) = &VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'};
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef((char *)this + 184);
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_WORD *)this + 108) = 0;
  v12 = 0;
  v13 = 0;
  MF::ThrowIfNull<Windows::Media::IVideoFrame *>(v11);
  v4 = (*(__int64 (__fastcall **)(struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *, __int128 *))(*(_QWORD *)a2 + 48LL))(
         a2,
         &v12);
  MF::ThrowIfFailed((MF *)v4, v5);
  VideoFrameImpl::CheckDXFormatSupport(v6, DWORD2(v12));
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  String = WindowsCreateString(L"VideoFrame", 0xAu, (HSTRING *)this + 12);
  MF::ThrowIfFailed((MF *)String, v8);
  v11[0] = 0;
  MediaFrameImpl::Initialize(this);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(v11);
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v9, this, a2);
  return this;
}

```

## disassembly

```asm
0x180035c84  mov     r11, rsp
0x180035c87  mov     [r11+18h], rbx
0x180035c8b  mov     [r11+20h], rsi
0x180035c8f  push    rdi
0x180035c90  sub     rsp, 60h
0x180035c94  mov     rax, cs:__security_cookie
0x180035c9b  xor     rax, rsp
0x180035c9e  mov     [rsp+68h+var_10], rax
0x180035ca3  mov     rsi, rdx
0x180035ca6  mov     rdi, rcx
0x180035ca9  mov     [r11-30h], rcx
0x180035cad  mov     [r11-38h], rdx
0x180035cb1  call    ??0?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIVideoFrame@Media@4@UIVideoFrame2@64@U?$CloakedIid@UIVideoFrameNative@@@WRL@Microsoft@@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@9Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>(void)
0x180035cb6  nop
0x180035cb7  lea     rax, ??_7VideoFrameImpl@@6BIMediaFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x180035cbe  mov     [rdi], rax
0x180035cc1  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180035cc8  mov     [rdi+8], rax
0x180035ccc  lea     rax, ??_7VideoFrameImpl@@6BIWeakReferenceSource@@@; const VideoFrameImpl::`vftable'{for `IWeakReferenceSource'}
0x180035cd3  mov     [rdi+70h], rax
0x180035cd7  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIVideoFrame@Media@6@UIVideoFrame2@86@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180035cde  mov     [rdi+78h], rax
0x180035ce2  lea     rax, ??_7VideoFrameImpl@@6BIVideoFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'}
0x180035ce9  mov     [rdi+80h], rax
0x180035cf0  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrame2@Media@Windows@@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180035cf7  mov     [rdi+88h], rax
0x180035cfe  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrameNative@@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'}
0x180035d05  mov     [rdi+90h], rax
0x180035d0c  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180035d13  mov     [rdi+98h], rax
0x180035d1a  mov     qword ptr [rdi+0B0h], 0
0x180035d25  lea     rcx, [rdi+0B8h]
0x180035d2c  mov     [rcx], rsi
0x180035d2f  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180035d34  nop
0x180035d35  mov     qword ptr [rdi+0C0h], 0
0x180035d40  mov     qword ptr [rdi+0C8h], 0
0x180035d4b  mov     qword ptr [rdi+0D0h], 0
0x180035d56  mov     word ptr [rdi+0D8h], 0
0x180035d5f  xorps   xmm0, xmm0
0x180035d62  xor     eax, eax
0x180035d64  movups  [rsp+68h+var_28], xmm0
0x180035d69  mov     [rsp+68h+var_18], eax
0x180035d6d  lea     rcx, [rsp+68h+var_38]
0x180035d72  call    ??$ThrowIfNull@PEAUIVideoFrame@Media@Windows@@@MF@@YAXAEBQEAUIVideoFrame@Media@Windows@@@Z; MF::ThrowIfNull<Windows::Media::IVideoFrame *>(Windows::Media::IVideoFrame * const &)
0x180035d77  mov     rax, [rsi]
0x180035d7a  lea     rdx, [rsp+68h+var_28]
0x180035d7f  mov     rcx, rsi
0x180035d82  mov     rax, [rax+30h]
0x180035d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d8b  mov     ecx, eax; this
0x180035d8d  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180035d92  mov     edx, dword ptr [rsp+68h+var_28+8]
0x180035d96  call    ?CheckDXFormatSupport@VideoFrameImpl@@AEAAXW4DirectXPixelFormat@DirectX@Graphics@Windows@@@Z; VideoFrameImpl::CheckDXFormatSupport(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180035d9b  lea     rbx, [rdi+60h]
0x180035d9f  mov     rcx, [rbx]; string
0x180035da2  call    cs:__imp_WindowsDeleteString
0x180035da8  mov     qword ptr [rbx], 0
0x180035daf  mov     r8, rbx; string
0x180035db2  mov     edx, 0Ah; length
0x180035db7  lea     rcx, sourceString; "VideoFrame"
0x180035dbe  call    cs:__imp_WindowsCreateString
0x180035dc4  mov     ecx, eax; this
0x180035dc6  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180035dcb  mov     [rsp+68h+var_38], 0
0x180035dd4  xor     r8d, r8d
0x180035dd7  lea     rdx, [rsp+68h+var_38]
0x180035ddc  mov     rcx, rdi; this
0x180035ddf  call    ?Initialize@MediaFrameImpl@@IEAAXAEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@_N@Z; MediaFrameImpl::Initialize(Microsoft::WRL::ComPtr<IMFSample> const &,bool)
0x180035de4  nop
0x180035de5  lea     rcx, [rsp+68h+var_38]
0x180035dea  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180035def  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180035df6  jb      short loc_180035E16
0x180035df8  mov     edx, 0Eh
0x180035dfd  mov     [rsp+68h+var_48], rsi
0x180035e02  mov     r9, rdi
0x180035e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e0c  mov     rcx, [rcx+10h]
0x180035e10  call    WPP_SF_qq
0x180035e15  nop
0x180035e16  mov     rax, rdi
0x180035e19  mov     rcx, [rsp+68h+var_10]
0x180035e1e  xor     rcx, rsp; StackCookie
0x180035e21  call    __security_check_cookie
0x180035e26  lea     r11, [rsp+68h+var_8]
0x180035e2b  mov     rbx, [r11+20h]
0x180035e2f  mov     rsi, [r11+28h]
0x180035e33  mov     rsp, r11
0x180035e36  pop     rdi
0x180035e37  retn
```
