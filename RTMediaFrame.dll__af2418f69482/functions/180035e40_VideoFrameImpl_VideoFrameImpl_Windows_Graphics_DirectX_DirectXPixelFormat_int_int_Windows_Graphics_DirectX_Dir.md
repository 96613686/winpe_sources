# VideoFrameImpl::VideoFrameImpl(Windows::Graphics::DirectX::DirectXPixelFormat,int,int,Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *)

- ea: `0x180035e40`
- end: `0x180035fe1`
- name: `??0VideoFrameImpl@@QEAA@W4DirectXPixelFormat@DirectX@Graphics@Windows@@HHPEAUIDirect3DDevice@Direct3D11@234@@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800251b4`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x180006c94`
- `0x1800093d4`
- `0x180035e40`
- `0x1800368b0`
- `0x1800371c0`
- `0x1800384d4`
- `0x1800388f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180035f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall VideoFrameImpl::VideoFrameImpl(
        __int64 a1,
        enum DXGI_FORMAT a2,
        int a3,
        int a4,
        __int64 (__fastcall ***a5)(_QWORD, GUID *, __int64 *))
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  MF *v12; // rcx
  int v13; // r8d
  unsigned int String; // eax
  int v15; // edx
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF

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
    WPP_SF_qdddq(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v11, a1, a2, a3, a4, a5);
  VideoFrameImpl::CheckDXFormatSupport(v10, (unsigned int)a2);
  if ( a3 < 0 || a4 < 0 )
    LOBYTE(v12) = 1;
  else
    v12 = 0;
  MF::ThrowOriginateErrorIfTrue(v12, 87, v13);
  VideoFrameImpl::CreateDirect3DSurface((VideoFrameImpl *)a1, a2, a3, a4, a5);
  WindowsDeleteString(*(HSTRING *)(a1 + 96));
  *(_QWORD *)(a1 + 96) = 0;
  String = WindowsCreateString(L"VideoFrame", 0xAu, (HSTRING *)(a1 + 96));
  MF::ThrowIfFailed((MF *)String, v15);
  v17 = 0;
  MediaFrameImpl::Initialize((MediaFrameImpl *)a1);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v17);
  return a1;
}

```

## disassembly

```asm
0x180035e40  mov     [rsp+arg_8], rbx
0x180035e45  mov     [rsp+arg_10], rbp
0x180035e4a  mov     [rsp+arg_0], rcx
0x180035e4f  push    rsi
0x180035e50  push    rdi
0x180035e51  push    r14
0x180035e53  sub     rsp, 50h
0x180035e57  mov     ebx, r9d
0x180035e5a  mov     esi, r8d
0x180035e5d  mov     ebp, edx
0x180035e5f  mov     rdi, rcx
0x180035e62  call    ??0?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIVideoFrame@Media@4@UIVideoFrame2@64@U?$CloakedIid@UIVideoFrameNative@@@WRL@Microsoft@@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@9Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>(void)
0x180035e67  nop
0x180035e68  lea     rax, ??_7VideoFrameImpl@@6BIMediaFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x180035e6f  mov     [rdi], rax
0x180035e72  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180035e79  mov     [rdi+8], rax
0x180035e7d  lea     rax, ??_7VideoFrameImpl@@6BIWeakReferenceSource@@@; const VideoFrameImpl::`vftable'{for `IWeakReferenceSource'}
0x180035e84  mov     [rdi+70h], rax
0x180035e88  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIVideoFrame@Media@6@UIVideoFrame2@86@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180035e8f  mov     [rdi+78h], rax
0x180035e93  lea     rax, ??_7VideoFrameImpl@@6BIVideoFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'}
0x180035e9a  mov     [rdi+80h], rax
0x180035ea1  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrame2@Media@Windows@@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180035ea8  mov     [rdi+88h], rax
0x180035eaf  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrameNative@@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'}
0x180035eb6  mov     [rdi+90h], rax
0x180035ebd  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180035ec4  mov     [rdi+98h], rax
0x180035ecb  mov     qword ptr [rdi+0B0h], 0
0x180035ed6  mov     qword ptr [rdi+0B8h], 0
0x180035ee1  mov     qword ptr [rdi+0C0h], 0
0x180035eec  mov     qword ptr [rdi+0C8h], 0
0x180035ef7  mov     qword ptr [rdi+0D0h], 0
0x180035f02  mov     word ptr [rdi+0D8h], 0
0x180035f0b  mov     r14, [rsp+68h+arg_20]
0x180035f13  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180035f1a  jb      short loc_180035F40
0x180035f1c  mov     [rsp+68h+var_30], r14
0x180035f21  mov     [rsp+68h+var_38], ebx
0x180035f25  mov     [rsp+68h+var_40], esi
0x180035f29  mov     dword ptr [rsp+68h+var_48], ebp
0x180035f2d  mov     r9, rdi
0x180035f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f37  mov     rcx, [rcx+10h]
0x180035f3b  call    WPP_SF_qdddq
0x180035f40  mov     edx, ebp
0x180035f42  call    ?CheckDXFormatSupport@VideoFrameImpl@@AEAAXW4DirectXPixelFormat@DirectX@Graphics@Windows@@@Z; VideoFrameImpl::CheckDXFormatSupport(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180035f47  test    esi, esi
0x180035f49  js      short loc_180035F53
0x180035f4b  test    ebx, ebx
0x180035f4d  js      short loc_180035F53
0x180035f4f  xor     ecx, ecx
0x180035f51  jmp     short loc_180035F55
0x180035f53  mov     cl, 1; this
0x180035f55  mov     edx, 80070057h; bool
0x180035f5a  call    ?ThrowOriginateErrorIfTrue@MF@@YAX_NJ@Z; MF::ThrowOriginateErrorIfTrue(bool,long)
0x180035f5f  mov     [rsp+68h+var_48], r14
0x180035f64  mov     r9d, ebx
0x180035f67  mov     r8d, esi
0x180035f6a  mov     edx, ebp
0x180035f6c  mov     rcx, rdi
0x180035f6f  call    ?CreateDirect3DSurface@VideoFrameImpl@@AEAAXW4DirectXPixelFormat@DirectX@Graphics@Windows@@HHPEAUIDirect3DDevice@Direct3D11@345@@Z; VideoFrameImpl::CreateDirect3DSurface(Windows::Graphics::DirectX::DirectXPixelFormat,int,int,Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *)
0x180035f74  lea     rbx, [rdi+60h]
0x180035f78  mov     rcx, [rbx]; string
0x180035f7b  call    cs:__imp_WindowsDeleteString
0x180035f81  mov     qword ptr [rbx], 0
0x180035f88  mov     r8, rbx; string
0x180035f8b  mov     edx, 0Ah; length
0x180035f90  lea     rcx, sourceString; "VideoFrame"
0x180035f97  call    cs:__imp_WindowsCreateString
0x180035f9d  mov     ecx, eax; this
0x180035f9f  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180035fa4  mov     [rsp+68h+var_28], 0
0x180035fad  xor     r8d, r8d
0x180035fb0  lea     rdx, [rsp+68h+var_28]
0x180035fb5  mov     rcx, rdi; this
0x180035fb8  call    ?Initialize@MediaFrameImpl@@IEAAXAEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@_N@Z; MediaFrameImpl::Initialize(Microsoft::WRL::ComPtr<IMFSample> const &,bool)
0x180035fbd  nop
0x180035fbe  lea     rcx, [rsp+68h+var_28]
0x180035fc3  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180035fc8  nop
0x180035fc9  mov     rax, rdi
0x180035fcc  lea     r11, [rsp+68h+var_18]
0x180035fd1  mov     rbx, [r11+28h]
0x180035fd5  mov     rbp, [r11+30h]
0x180035fd9  mov     rsp, r11
0x180035fdc  pop     r14
0x180035fde  pop     rdi
0x180035fdf  pop     rsi
0x180035fe0  retn
```
