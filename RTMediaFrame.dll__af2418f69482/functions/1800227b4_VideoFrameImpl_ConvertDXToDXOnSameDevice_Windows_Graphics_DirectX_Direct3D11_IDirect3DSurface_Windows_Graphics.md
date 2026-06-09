# VideoFrameImpl::ConvertDXToDXOnSameDevice(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,tagRECT const &,tagRECT const &,IMFDXGIDeviceManager *)

- ea: `0x1800227b4`
- end: `0x180022c16`
- name: `?ConvertDXToDXOnSameDevice@VideoFrameImpl@@AEAAXPEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@0AEBUtagRECT@@1PEAUIMFDXGIDeviceManager@@@Z`
- size: `1122`
- prototype: `void __fastcall(VideoFrameImpl *__hidden this, struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *, struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *, const struct tagRECT *, const struct tagRECT *, struct IMFDXGIDeviceManager *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800368e4`

## callees

- `0x18000168c`
- `0x180001938`
- `0x1800019c0`
- `0x180001cd8`
- `0x180001ddc`
- `0x180001ec0`
- `0x1800022e4`
- `0x18000266c`
- `0x1800026c0`
- `0x180005cd0`
- `0x18000f77c`
- `0x18000f9cc`
- `0x18002007c`
- `0x180021e2c`
- `0x1800227b4`
- `0x180022c1c`
- `0x1800230d0`
- `0x1800231cc`
- `0x180026920`
- `0x180034a60`
- `0x180034c04`
- `0x180038970`
- `0x180038a5c`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180022972`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x1800229a2`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180022972`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x1800229a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall VideoFrameImpl::ConvertDXToDXOnSameDevice(
        VideoFrameImpl *this,
        struct IInspectable *a2,
        struct IInspectable *a3,
        const struct tagRECT *a4,
        const struct tagRECT *a5,
        struct IMFDXGIDeviceManager *a6)
{
  char IsFormatSupportedByXVP; // r15
  char v11; // al
  unsigned int v12; // r14d
  unsigned int v13; // eax
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // r8
  const struct _GUID *v17; // rdx
  unsigned int DXGIInterfaceFromDirect3D11Object; // eax
  int v19; // edx
  const struct _GUID *v20; // rdx
  unsigned int v21; // eax
  int v22; // edx
  unsigned int v23; // eax
  int v24; // edx
  unsigned int v25; // eax
  int v26; // edx
  __int64 v27; // r8
  __int64 v28; // rcx
  struct IMFTransform *v29; // rcx
  struct IMFTransform *v30; // [rsp+30h] [rbp-79h] BYREF
  void *v31; // [rsp+38h] [rbp-71h] BYREF
  void *v32; // [rsp+40h] [rbp-69h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+48h] [rbp-61h] BYREF
  IMFMediaBuffer *v34; // [rsp+50h] [rbp-59h] BYREF
  IUnknown *punkSurface; // [rsp+58h] [rbp-51h] BYREF
  IUnknown *v36; // [rsp+60h] [rbp-49h] BYREF
  struct IMFMediaType *v37; // [rsp+68h] [rbp-41h] BYREF
  struct IMFMediaType *ppMFType; // [rsp+70h] [rbp-39h] BYREF
  __int128 v39; // [rsp+78h] [rbp-31h] BYREF
  int v40; // [rsp+88h] [rbp-21h]
  __int128 v41; // [rsp+90h] [rbp-19h] BYREF
  int v42; // [rsp+A0h] [rbp-9h]

  punkSurface = (IUnknown *)a6;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  ((void (__fastcall *)(struct IInspectable *, __int128 *))a2->lpVtbl[1].QueryInterface)(a2, &v39);
  ((void (__fastcall *)(struct IInspectable *, __int128 *))a3->lpVtbl[1].QueryInterface)(a3, &v41);
  IsFormatSupportedByXVP = MediaFrameHelpers::IsFormatSupportedByXVP(DWORD2(v39));
  v11 = MediaFrameHelpers::IsFormatSupportedByXVP(DWORD2(v41));
  if ( !IsFormatSupportedByXVP || !v11 )
    goto LABEL_8;
  LOBYTE(v12) = 1;
  MediaFrameHelpers::CreateMFMediaType(&ppMFType);
  MediaFrameHelpers::CreateMFMediaType(&v37);
  v30 = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v30);
  v13 = VideoFrameImpl::CreateXVP(this, &v30);
  MF::ThrowIfFailed((MF *)v13, v14);
  if ( (int)VideoFrameImpl::XVPConfigure(this, v30, ppMFType, v37, (struct IMFDXGIDeviceManager *)punkSurface) >= 0 )
  {
    if ( g_wppLevels >= 8u )
      WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, a2, a3, *((_QWORD *)this + 26));
    v32 = 0;
    v31 = 0;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
    DXGIInterfaceFromDirect3D11Object = GetDXGIInterfaceFromDirect3D11Object(a2, v17, &v32);
    MF::ThrowIfFailed((MF *)DXGIInterfaceFromDirect3D11Object, v19);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v31);
    v21 = GetDXGIInterfaceFromDirect3D11Object(a3, v20, &v31);
    MF::ThrowIfFailed((MF *)v21, v22);
    MF::As<ID3D11Texture2D,IDXGISurface>(&punkSurface, &v32);
    MF::As<ID3D11Texture2D,IDXGISurface>(&v36, &v31);
    ppBuffer = 0;
    v34 = 0;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppBuffer);
    v23 = MFCreateDXGISurfaceBuffer(&GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, punkSurface, 0, 0, &ppBuffer);
    MF::ThrowIfFailed((MF *)v23, v24);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v34);
    v25 = MFCreateDXGISurfaceBuffer(&GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, v36, 0, 0, &v34);
    MF::ThrowIfFailed((MF *)v25, v26);
    v12 = (unsigned int)VideoFrameImpl::XVPConvertMFMediaBuffer(v30, ppBuffer, a4, v34, a5) >> 31;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppBuffer);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&punkSurface);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
  }
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppMFType);
  if ( (_BYTE)v12 )
  {
LABEL_8:
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease((char *)this + 200);
    if ( g_wppLevels >= 8u )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v27, a2, a3);
    if ( IsFormatSupportedByXVP )
    {
      LODWORD(ppBuffer) = MediaFrameHelpers::GetFormat(DWORD2(v41));
      LODWORD(v34) = MediaFrameHelpers::GetAlpha(DWORD2(v41));
      Microsoft::WRL::Details::Make<SoftwareBitmapImpl,enum Windows::Graphics::Imaging::BitmapPixelFormat const &,int const &,int const &,enum Windows::Graphics::Imaging::BitmapAlphaMode const &>(
        (unsigned int)&v30,
        (unsigned int)&ppBuffer,
        (unsigned int)&v41,
        (unsigned int)&v41 + 4,
        (__int64)&v34);
      MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>(&v30);
      v31 = v30;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v31);
      v32 = a3;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v32);
      MediaFrameHelpers::CopyToBitmapFromSurface();
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v31);
      VideoFrameImpl::CopyTo(
        this,
        (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)a2,
        (struct Windows::Graphics::Imaging::ISoftwareBitmap *)v30,
        a4,
        a5);
      v31 = a3;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v31);
      v32 = v30;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v32);
      MediaFrameHelpers::CopyToSurfaceFromBitmap(v28, &v32, &v31);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v31);
    }
    else
    {
      LODWORD(v34) = MediaFrameHelpers::GetFormat(DWORD2(v39));
      LODWORD(ppBuffer) = MediaFrameHelpers::GetAlpha(DWORD2(v39));
      Microsoft::WRL::Details::Make<SoftwareBitmapImpl,enum Windows::Graphics::Imaging::BitmapPixelFormat const &,int const &,int const &,enum Windows::Graphics::Imaging::BitmapAlphaMode const &>(
        (unsigned int)&v30,
        (unsigned int)&v34,
        (unsigned int)&v39,
        (unsigned int)&v39 + 4,
        (__int64)&ppBuffer);
      MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>(&v30);
      v31 = v30;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v31);
      v32 = a2;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v32);
      MediaFrameHelpers::CopyToBitmapFromSurface();
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v31);
      VideoFrameImpl::CopyTo(
        this,
        (struct Windows::Graphics::Imaging::ISoftwareBitmap *)v30,
        (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)a3,
        a4,
        a5);
    }
    v29 = v30;
    if ( v30 )
    {
      v30 = 0;
      SoftwareBitmapImpl::Release((SoftwareBitmapImpl *)v29);
    }
  }
}

```

## disassembly

```asm
0x1800227b4  push    rbp
0x1800227b6  push    rbx
0x1800227b7  push    rsi
0x1800227b8  push    rdi
0x1800227b9  push    r12
0x1800227bb  push    r13
0x1800227bd  push    r14
0x1800227bf  push    r15
0x1800227c1  lea     rbp, [rsp-0Fh]
0x1800227c6  sub     rsp, 0B8h
0x1800227cd  mov     rax, cs:__security_cookie
0x1800227d4  xor     rax, rsp
0x1800227d7  mov     [rbp+47h+var_48], rax
0x1800227db  mov     r12, r9
0x1800227de  mov     rbx, r8
0x1800227e1  mov     rsi, rdx
0x1800227e4  mov     rdi, rcx
0x1800227e7  mov     r13, [rbp+47h+arg_20]
0x1800227eb  mov     rax, [rbp+47h+arg_28]
0x1800227ef  mov     [rbp+47h+punkSurface], rax
0x1800227f3  xorps   xmm0, xmm0
0x1800227f6  xor     eax, eax
0x1800227f8  movups  [rbp+47h+var_78], xmm0
0x1800227fc  mov     [rbp+47h+var_68], eax
0x1800227ff  xorps   xmm1, xmm1
0x180022802  movups  [rbp+47h+var_60], xmm1
0x180022806  mov     [rbp+47h+var_50], eax
0x180022809  mov     rax, [rdx]
0x18002280c  lea     rdx, [rbp+47h+var_78]
0x180022810  mov     rcx, rsi
0x180022813  mov     rax, [rax+30h]
0x180022817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002281c  mov     rax, [rbx]
0x18002281f  lea     rdx, [rbp+47h+var_60]
0x180022823  mov     rcx, rbx
0x180022826  mov     rax, [rax+30h]
0x18002282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002282f  mov     ecx, dword ptr [rbp+47h+var_78+8]
0x180022832  call    ?IsFormatSupportedByXVP@MediaFrameHelpers@@SA_NW4DirectXPixelFormat@DirectX@Graphics@Windows@@@Z; MediaFrameHelpers::IsFormatSupportedByXVP(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180022837  mov     r15b, al
0x18002283a  mov     ecx, dword ptr [rbp+47h+var_60+8]
0x18002283d  call    ?IsFormatSupportedByXVP@MediaFrameHelpers@@SA_NW4DirectXPixelFormat@DirectX@Graphics@Windows@@@Z; MediaFrameHelpers::IsFormatSupportedByXVP(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180022842  test    r15b, r15b
0x180022845  jz      loc_180022A31
0x18002284b  test    al, al
0x18002284d  jz      loc_180022A31
0x180022853  mov     r14b, 1
0x180022856  lea     rdx, [rbp+47h+var_78]
0x18002285a  lea     rcx, [rbp+47h+ppMFType]; ppMFType
0x18002285e  call    ?CreateMFMediaType@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@AEBUDirect3DSurfaceDescription@Direct3D11@DirectX@Graphics@Windows@@@Z; MediaFrameHelpers::CreateMFMediaType(Windows::Graphics::DirectX::Direct3D11::Direct3DSurfaceDescription const &)
0x180022863  nop
0x180022864  lea     rdx, [rbp+47h+var_60]
0x180022868  lea     rcx, [rbp+47h+var_88]; ppMFType
0x18002286c  call    ?CreateMFMediaType@MediaFrameHelpers@@SA?AV?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@AEBUDirect3DSurfaceDescription@Direct3D11@DirectX@Graphics@Windows@@@Z; MediaFrameHelpers::CreateMFMediaType(Windows::Graphics::DirectX::Direct3D11::Direct3DSurfaceDescription const &)
0x180022871  nop
0x180022872  mov     [rbp+47h+var_C0], 0
0x18002287a  lea     rcx, [rbp+47h+var_C0]
0x18002287e  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022883  lea     rdx, [rbp+47h+var_C0]; struct IMFTransform **
0x180022887  mov     rcx, rdi; this
0x18002288a  call    ?CreateXVP@VideoFrameImpl@@AEAAJPEAPEAUIMFTransform@@@Z; VideoFrameImpl::CreateXVP(IMFTransform * *)
0x18002288f  mov     ecx, eax; this
0x180022891  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180022896  mov     rax, [rbp+47h+punkSurface]
0x18002289a  mov     [rsp+0F0h+ppBuffer], rax; struct IMFDXGIDeviceManager *
0x18002289f  mov     r9, [rbp+47h+var_88]; struct IMFMediaType *
0x1800228a3  mov     r8, [rbp+47h+ppMFType]; struct IMFMediaType *
0x1800228a7  mov     rdx, [rbp+47h+var_C0]; struct IMFTransform *
0x1800228ab  mov     rcx, rdi; this
0x1800228ae  call    ?XVPConfigure@VideoFrameImpl@@AEAAJPEAUIMFTransform@@PEAUIMFMediaType@@1PEAUIMFDXGIDeviceManager@@@Z; VideoFrameImpl::XVPConfigure(IMFTransform *,IMFMediaType *,IMFMediaType *,IMFDXGIDeviceManager *)
0x1800228b3  test    eax, eax
0x1800228b5  js      loc_180022A0B
0x1800228bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800228c2  jb      short loc_1800228E8
0x1800228c4  mov     rax, [rdi+0D0h]
0x1800228cb  mov     [rsp+0F0h+var_C8], rax
0x1800228d0  mov     [rsp+0F0h+ppBuffer], rbx
0x1800228d5  mov     r9, rsi
0x1800228d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228df  mov     rcx, [rcx+10h]
0x1800228e3  call    WPP_SF_qqq
0x1800228e8  xor     r14d, r14d
0x1800228eb  mov     [rbp+47h+var_B0], r14
0x1800228ef  mov     [rbp+47h+var_B8], r14
0x1800228f3  lea     rcx, [rbp+47h+var_B0]
0x1800228f7  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800228fc  lea     r8, [rbp+47h+var_B0]; void **
0x180022900  mov     rcx, rsi; struct IInspectable *
0x180022903  call    ?GetDXGIInterfaceFromDirect3D11Object@@YAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; GetDXGIInterfaceFromDirect3D11Object(IInspectable *,_GUID const &,void * *)
0x180022908  mov     ecx, eax; this
0x18002290a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18002290f  lea     rcx, [rbp+47h+var_B8]
0x180022913  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022918  lea     r8, [rbp+47h+var_B8]; void **
0x18002291c  mov     rcx, rbx; struct IInspectable *
0x18002291f  call    ?GetDXGIInterfaceFromDirect3D11Object@@YAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; GetDXGIInterfaceFromDirect3D11Object(IInspectable *,_GUID const &,void * *)
0x180022924  mov     ecx, eax; this
0x180022926  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18002292b  lea     rdx, [rbp+47h+var_B0]
0x18002292f  lea     rcx, [rbp+47h+punkSurface]
0x180022933  call    ??$As@UID3D11Texture2D@@UIDXGISurface@@@MF@@YA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@AEBV?$ComPtr@UIDXGISurface@@@23@@Z; MF::As<ID3D11Texture2D,IDXGISurface>(Microsoft::WRL::ComPtr<IDXGISurface> const &)
0x180022938  nop
0x180022939  lea     rdx, [rbp+47h+var_B8]
0x18002293d  lea     rcx, [rbp+47h+var_90]
0x180022941  call    ??$As@UID3D11Texture2D@@UIDXGISurface@@@MF@@YA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@AEBV?$ComPtr@UIDXGISurface@@@23@@Z; MF::As<ID3D11Texture2D,IDXGISurface>(Microsoft::WRL::ComPtr<IDXGISurface> const &)
0x180022946  nop
0x180022947  mov     [rbp+47h+var_A8], r14
0x18002294b  mov     [rbp+47h+var_A0], r14
0x18002294f  lea     rcx, [rbp+47h+var_A8]
0x180022953  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022958  lea     rax, [rbp+47h+var_A8]
0x18002295c  mov     [rsp+0F0h+ppBuffer], rax; ppBuffer
0x180022961  xor     r9d, r9d; fBottomUpWhenLinear
0x180022964  xor     r8d, r8d; uSubresourceIndex
0x180022967  mov     rdx, [rbp+47h+punkSurface]; punkSurface
0x18002296b  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x180022972  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x180022978  mov     ecx, eax; this
0x18002297a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18002297f  lea     rcx, [rbp+47h+var_A0]
0x180022983  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022988  lea     rax, [rbp+47h+var_A0]
0x18002298c  mov     [rsp+0F0h+ppBuffer], rax; ppBuffer
0x180022991  xor     r9d, r9d; fBottomUpWhenLinear
0x180022994  xor     r8d, r8d; uSubresourceIndex
0x180022997  mov     rdx, [rbp+47h+var_90]; punkSurface
0x18002299b  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x1800229a2  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x1800229a8  mov     ecx, eax; this
0x1800229aa  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800229af  mov     [rsp+0F0h+ppBuffer], r13; struct tagRECT *
0x1800229b4  mov     r9, [rbp+47h+var_A0]; struct IMFMediaBuffer *
0x1800229b8  mov     r8, r12; struct tagRECT *
0x1800229bb  mov     rdx, [rbp+47h+var_A8]; struct IMFMediaBuffer *
0x1800229bf  mov     rcx, [rbp+47h+var_C0]; struct IMFTransform *
0x1800229c3  call    ?XVPConvertMFMediaBuffer@VideoFrameImpl@@CAJPEAUIMFTransform@@PEAUIMFMediaBuffer@@AEBUtagRECT@@12@Z; VideoFrameImpl::XVPConvertMFMediaBuffer(IMFTransform *,IMFMediaBuffer *,tagRECT const &,IMFMediaBuffer *,tagRECT const &)
0x1800229c8  mov     r14d, eax
0x1800229cb  shr     r14d, 1Fh
0x1800229cf  lea     rcx, [rbp+47h+var_A0]
0x1800229d3  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800229d8  nop
0x1800229d9  lea     rcx, [rbp+47h+var_A8]
0x1800229dd  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800229e2  nop
0x1800229e3  lea     rcx, [rbp+47h+var_90]
0x1800229e7  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800229ec  nop
0x1800229ed  lea     rcx, [rbp+47h+punkSurface]
0x1800229f1  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800229f6  nop
0x1800229f7  lea     rcx, [rbp+47h+var_B8]
0x1800229fb  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022a00  nop
0x180022a01  lea     rcx, [rbp+47h+var_B0]
0x180022a05  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022a0a  nop
0x180022a0b  lea     rcx, [rbp+47h+var_C0]
0x180022a0f  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022a14  nop
0x180022a15  lea     rcx, [rbp+47h+var_88]
0x180022a19  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022a1e  nop
0x180022a1f  lea     rcx, [rbp+47h+ppMFType]
0x180022a23  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022a28  test    r14b, r14b
0x180022a2b  jz      loc_180022BF6
0x180022a31  lea     rcx, [rdi+0C8h]
0x180022a38  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022a3d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180022a44  jb      short loc_180022A63
0x180022a46  mov     edx, 13h
0x180022a4b  mov     [rsp+0F0h+ppBuffer], rbx
0x180022a50  mov     r9, rsi
0x180022a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a5a  mov     rcx, [rcx+10h]
0x180022a5e  call    WPP_SF_qq
0x180022a63  test    r15b, r15b
0x180022a66  jnz     loc_180022B08
0x180022a6c  mov     ecx, dword ptr [rbp+47h+var_78+8]
0x180022a6f  call    ?GetFormat@MediaFrameHelpers@@SA?AW4BitmapPixelFormat@Imaging@Graphics@Windows@@W4DirectXPixelFormat@DirectX@45@@Z; MediaFrameHelpers::GetFormat(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180022a74  mov     dword ptr [rbp+47h+var_A0], eax
0x180022a77  mov     ecx, dword ptr [rbp+47h+var_78+8]
0x180022a7a  call    ?GetAlpha@MediaFrameHelpers@@SA?AW4BitmapAlphaMode@Imaging@Graphics@Windows@@W4DirectXPixelFormat@DirectX@45@@Z; MediaFrameHelpers::GetAlpha(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180022a7f  mov     dword ptr [rbp+47h+var_A8], eax
0x180022a82  lea     rax, [rbp+47h+var_A8]
0x180022a86  mov     [rsp+0F0h+ppBuffer], rax
0x180022a8b  lea     r9, [rbp+47h+var_78+4]
0x180022a8f  lea     r8, [rbp+47h+var_78]
0x180022a93  lea     rdx, [rbp+47h+var_A0]
0x180022a97  lea     rcx, [rbp+47h+var_C0]
0x180022a9b  call    ??$Make@VSoftwareBitmapImpl@@AEBW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBHAEBHAEBW4BitmapAlphaMode@345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSoftwareBitmapImpl@@@12@AEBW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBH1AEBW4BitmapAlphaMode@567@@Z; Microsoft::WRL::Details::Make<SoftwareBitmapImpl,Windows::Graphics::Imaging::BitmapPixelFormat const &,int const &,int const &,Windows::Graphics::Imaging::BitmapAlphaMode const &>(Windows::Graphics::Imaging::BitmapPixelFormat const &,int const &,int const &,Windows::Graphics::Imaging::BitmapAlphaMode const &)
0x180022aa0  nop
0x180022aa1  lea     rcx, [rbp+47h+var_C0]
0x180022aa5  call    ??$ThrowIfBadAlloc@V?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@MF@@YAXAEBV?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@Z; MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>(Microsoft::WRL::ComPtr<AudioFrameState> const &)
0x180022aaa  mov     rax, [rbp+47h+var_C0]
0x180022aae  mov     [rbp+47h+var_B8], rax
0x180022ab2  lea     rcx, [rbp+47h+var_B8]
0x180022ab6  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180022abb  nop
0x180022abc  mov     [rbp+47h+var_B0], rsi
0x180022ac0  lea     rcx, [rbp+47h+var_B0]
0x180022ac4  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180022ac9  nop
0x180022aca  lea     r8, [rbp+47h+var_B8]
0x180022ace  lea     rdx, [rbp+47h+var_B0]
0x180022ad2  call    ?CopyToBitmapFromSurface@MediaFrameHelpers@@SAXW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBV?$ComPtr@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@78@@Z; MediaFrameHelpers::CopyToBitmapFromSurface(Windows::Graphics::Imaging::BitmapPixelFormat,Microsoft::WRL::ComPtr<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface> const &,Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)
0x180022ad7  nop
0x180022ad8  lea     rcx, [rbp+47h+var_B0]
0x180022adc  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022ae1  nop
0x180022ae2  lea     rcx, [rbp+47h+var_B8]
0x180022ae6  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022aeb  mov     [rsp+0F0h+ppBuffer], r13; struct tagRECT *
0x180022af0  mov     r9, r12; struct tagRECT *
0x180022af3  mov     r8, rbx; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180022af6  mov     rdx, [rbp+47h+var_C0]; struct Windows::Graphics::Imaging::ISoftwareBitmap *
0x180022afa  mov     rcx, rdi; this
0x180022afd  call    ?CopyTo@VideoFrameImpl@@AEAAXPEAUISoftwareBitmap@Imaging@Graphics@Windows@@PEAUIDirect3DSurface@Direct3D11@DirectX@45@AEBUtagRECT@@2@Z; VideoFrameImpl::CopyTo(Windows::Graphics::Imaging::ISoftwareBitmap *,Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,tagRECT const &,tagRECT const &)
0x180022b02  nop
0x180022b03  jmp     loc_180022BE0
0x180022b08  mov     ecx, dword ptr [rbp+47h+var_60+8]
0x180022b0b  call    ?GetFormat@MediaFrameHelpers@@SA?AW4BitmapPixelFormat@Imaging@Graphics@Windows@@W4DirectXPixelFormat@DirectX@45@@Z; MediaFrameHelpers::GetFormat(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180022b10  mov     dword ptr [rbp+47h+var_A8], eax
0x180022b13  mov     ecx, dword ptr [rbp+47h+var_60+8]
0x180022b16  call    ?GetAlpha@MediaFrameHelpers@@SA?AW4BitmapAlphaMode@Imaging@Graphics@Windows@@W4DirectXPixelFormat@DirectX@45@@Z; MediaFrameHelpers::GetAlpha(Windows::Graphics::DirectX::DirectXPixelFormat)
0x180022b1b  mov     dword ptr [rbp+47h+var_A0], eax
0x180022b1e  lea     rax, [rbp+47h+var_A0]
0x180022b22  mov     [rsp+0F0h+ppBuffer], rax
0x180022b27  lea     r9, [rbp+47h+var_60+4]
0x180022b2b  lea     r8, [rbp+47h+var_60]
0x180022b2f  lea     rdx, [rbp+47h+var_A8]
0x180022b33  lea     rcx, [rbp+47h+var_C0]
0x180022b37  call    ??$Make@VSoftwareBitmapImpl@@AEBW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBHAEBHAEBW4BitmapAlphaMode@345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSoftwareBitmapImpl@@@12@AEBW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBH1AEBW4BitmapAlphaMode@567@@Z; Microsoft::WRL::Details::Make<SoftwareBitmapImpl,Windows::Graphics::Imaging::BitmapPixelFormat const &,int const &,int const &,Windows::Graphics::Imaging::BitmapAlphaMode const &>(Windows::Graphics::Imaging::BitmapPixelFormat const &,int const &,int const &,Windows::Graphics::Imaging::BitmapAlphaMode const &)
0x180022b3c  nop
0x180022b3d  lea     rcx, [rbp+47h+var_C0]
0x180022b41  call    ??$ThrowIfBadAlloc@V?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@MF@@YAXAEBV?$ComPtr@VAudioFrameState@@@WRL@Microsoft@@@Z; MF::ThrowIfBadAlloc<Microsoft::WRL::ComPtr<AudioFrameState>>(Microsoft::WRL::ComPtr<AudioFrameState> const &)
0x180022b46  mov     rax, [rbp+47h+var_C0]
0x180022b4a  mov     [rbp+47h+var_B8], rax
0x180022b4e  lea     rcx, [rbp+47h+var_B8]
0x180022b52  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180022b57  nop
0x180022b58  mov     [rbp+47h+var_B0], rbx
0x180022b5c  lea     rcx, [rbp+47h+var_B0]
0x180022b60  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180022b65  nop
0x180022b66  lea     r8, [rbp+47h+var_B8]
0x180022b6a  lea     rdx, [rbp+47h+var_B0]
0x180022b6e  call    ?CopyToBitmapFromSurface@MediaFrameHelpers@@SAXW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBV?$ComPtr@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@78@@Z; MediaFrameHelpers::CopyToBitmapFromSurface(Windows::Graphics::Imaging::BitmapPixelFormat,Microsoft::WRL::ComPtr<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface> const &,Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &)
0x180022b73  nop
0x180022b74  lea     rcx, [rbp+47h+var_B0]
0x180022b78  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022b7d  nop
0x180022b7e  lea     rcx, [rbp+47h+var_B8]
0x180022b82  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022b87  mov     [rsp+0F0h+ppBuffer], r13; struct tagRECT *
0x180022b8c  mov     r9, r12; struct tagRECT *
0x180022b8f  mov     r8, [rbp+47h+var_C0]; struct Windows::Graphics::Imaging::ISoftwareBitmap *
0x180022b93  mov     rdx, rsi; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180022b96  mov     rcx, rdi; this
0x180022b99  call    ?CopyTo@VideoFrameImpl@@AEAAXPEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@PEAUISoftwareBitmap@Imaging@56@AEBUtagRECT@@2@Z; VideoFrameImpl::CopyTo(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,Windows::Graphics::Imaging::ISoftwareBitmap *,tagRECT const &,tagRECT const &)
0x180022b9e  mov     [rbp+47h+var_B8], rbx
0x180022ba2  lea     rcx, [rbp+47h+var_B8]
0x180022ba6  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180022bab  nop
0x180022bac  mov     rax, [rbp+47h+var_C0]
0x180022bb0  mov     [rbp+47h+var_B0], rax
0x180022bb4  lea     rcx, [rbp+47h+var_B0]
0x180022bb8  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180022bbd  nop
0x180022bbe  lea     r8, [rbp+47h+var_B8]
0x180022bc2  lea     rdx, [rbp+47h+var_B0]
0x180022bc6  call    ?CopyToSurfaceFromBitmap@MediaFrameHelpers@@SAXW4BitmapPixelFormat@Imaging@Graphics@Windows@@AEBV?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@78@@Z; MediaFrameHelpers::CopyToSurfaceFromBitmap(Windows::Graphics::Imaging::BitmapPixelFormat,Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap> const &,Microsoft::WRL::ComPtr<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface> const &)
0x180022bcb  nop
0x180022bcc  lea     rcx, [rbp+47h+var_B0]
0x180022bd0  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022bd5  nop
0x180022bd6  lea     rcx, [rbp+47h+var_B8]
0x180022bda  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180022bdf  nop
0x180022be0  mov     rcx, [rbp+47h+var_C0]; this
0x180022be4  test    rcx, rcx
0x180022be7  jz      short loc_180022BF6
0x180022be9  mov     [rbp+47h+var_C0], 0
0x180022bf1  call    ?Release@SoftwareBitmapImpl@@UEAAKXZ; SoftwareBitmapImpl::Release(void)
0x180022bf6  mov     rcx, [rbp+47h+var_48]
0x180022bfa  xor     rcx, rsp; StackCookie
0x180022bfd  call    __security_check_cookie
0x180022c02  add     rsp, 0B8h
0x180022c09  pop     r15
0x180022c0b  pop     r14
0x180022c0d  pop     r13
0x180022c0f  pop     r12
0x180022c11  pop     rdi
0x180022c12  pop     rsi
0x180022c13  pop     rbx
0x180022c14  pop     rbp
0x180022c15  retn
```
