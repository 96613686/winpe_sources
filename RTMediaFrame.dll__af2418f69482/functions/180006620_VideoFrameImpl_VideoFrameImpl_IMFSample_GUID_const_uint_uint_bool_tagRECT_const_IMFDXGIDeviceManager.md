# VideoFrameImpl::VideoFrameImpl(IMFSample *,_GUID const &,uint,uint,bool,tagRECT const &,IMFDXGIDeviceManager *)

- ea: `0x180006620`
- end: `0x180006c8e`
- name: `??0VideoFrameImpl@@QEAA@PEAUIMFSample@@AEBU_GUID@@II_NAEBUtagRECT@@PEAUIMFDXGIDeviceManager@@@Z`
- size: `1646`
- prototype: `VideoFrameImpl *__usercall@<rax>(VideoFrameImpl *__hidden this@<rcx>, struct IMFSample *@<rdx>, const struct _GUID *@<r8>, unsigned int@<r9d>, unsigned int, bool, const struct tagRECT *, struct IMFDXGIDeviceManager *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180006080`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x180006620`
- `0x180006c94`
- `0x180006d38`
- `0x180006e40`
- `0x1800095c0`
- `0x180009760`
- `0x18000a220`
- `0x180026e0c`
- `0x180026e30`
- `0x18002749c`
- `0x180035ac4`
- `0x1800389c4`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800069e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800069e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800069ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800069ce`
- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x180006902`
- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x180006902`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
VideoFrameImpl *__fastcall VideoFrameImpl::VideoFrameImpl(
        VideoFrameImpl *this,
        struct IMFSample *a2,
        struct _GUID *a3,
        unsigned int a4,
        unsigned int a5,
        BOOL a6,
        const struct tagRECT *a7,
        IDXGISurface *dgxiSurface)
{
  __int64 v12; // rdx
  __int64 v13; // r8
  IDXGISurface *v14; // rbx
  bool v15; // r15
  unsigned int v16; // r12d
  struct IMFSample *v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  struct IMF2DBuffer2 *v20; // rsi
  SoftwareBitmapImpl *v21; // rax
  SoftwareBitmapImpl *v22; // rbx
  __int64 v23; // rcx
  IDXGISurface *v24; // rcx
  __int64 v25; // rsi
  int (__fastcall *v26)(__int64, GUID *, IDXGISurface **); // rbx
  unsigned int v27; // eax
  int v28; // edx
  IInspectable *v29; // rbx
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rsi
  unsigned int v31; // eax
  int v32; // edx
  void *v33; // rax
  void *v34; // rcx
  __int64 v35; // rdx
  IInspectable *v36; // rcx
  IDXGISurface *v37; // rcx
  HRESULT String; // eax
  __int64 v39; // rcx
  IInspectable *v40; // rax
  __int64 v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rcx
  int (__fastcall ***v44)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v46; // rsi
  __int64 (__fastcall *v47)(__int64, GUID *, __int64 *); // rbx
  unsigned int v48; // eax
  int v49; // edx
  unsigned int v50; // eax
  int v51; // edx
  __int64 v52; // rsi
  __int64 (__fastcall *v53)(__int64, BOOL, IDXGISurface **); // rbx
  unsigned int v54; // eax
  int v55; // edx
  void *v56; // [rsp+50h] [rbp-59h] BYREF
  IInspectable *graphicsSurface; // [rsp+58h] [rbp-51h] BYREF
  __int64 v58; // [rsp+60h] [rbp-49h] BYREF
  int (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-41h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v61[3]; // [rsp+78h] [rbp-31h]
  SoftwareBitmapImpl *v62; // [rsp+90h] [rbp-19h]
  VideoFrameImpl *v63; // [rsp+98h] [rbp-11h]
  IInspectable *v64; // [rsp+A0h] [rbp-9h]
  __int64 v65; // [rsp+F8h] [rbp+4Fh] BYREF
  struct _GUID *v66; // [rsp+100h] [rbp+57h]

  v66 = a3;
  LODWORD(v65) = 0;
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
  *((_QWORD *)this + 23) = 0;
  v14 = dgxiSurface;
  *((_QWORD *)this + 24) = dgxiSurface;
  if ( v14 )
    ((void (__fastcall *)(IDXGISurface *))v14->lpVtbl->AddRef)(v14);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_WORD *)this + 108) = 0;
  v15 = a6;
  v16 = a5;
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qqddddq(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, this, a2, a3->Data1, a4, a5, a6, v14);
  v17 = (struct IMFSample *)*((_QWORD *)this + 11);
  if ( v17 != a2 )
  {
    if ( a2 )
      ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
    v18 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = a2;
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v17 = (struct IMFSample *)*((_QWORD *)this + 11);
    }
    else
    {
      v17 = a2;
    }
  }
  *((_BYTE *)this + 48) = v15;
  v59 = 0;
  v19 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD, _QWORD))v17->lpVtbl->GetBufferByIndex)(v17, 0, &v59);
  if ( v19 < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    LODWORD(v61[0]) = v19;
    *(_OWORD *)&v61[1] = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v58 = 0;
  if ( (**v59)(v59, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v58) >= 0 )
  {
    if ( !v14 )
      MF::ThrowOriginateError<14>();
    dgxiSurface = 0;
    graphicsSurface = 0;
    v25 = v58;
    v26 = *(int (__fastcall **)(__int64, GUID *, IDXGISurface **))(*(_QWORD *)v58 + 24LL);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&dgxiSurface);
    if ( v26(v25, &GUID_aba496dd_b617_4cb8_a866_bc44d7eb1fa2, &dgxiSurface) < 0 )
    {
      v65 = 0;
      v46 = v58;
      v47 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v58 + 24LL);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v65);
      v48 = v47(v46, &GUID_30961379_4609_4a41_998e_54fe567ee0c1, &v65);
      MF::ThrowIfFailed((MF *)v48, v49);
      a6 = 0;
      v50 = (*(__int64 (__fastcall **)(__int64, BOOL *))(*(_QWORD *)v58 + 32LL))(v58, &a6);
      MF::ThrowIfFailed((MF *)v50, v51);
      v52 = v65;
      v53 = *(__int64 (__fastcall **)(__int64, BOOL, IDXGISurface **))(*(_QWORD *)v65 + 96LL);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&dgxiSurface);
      v54 = v53(v52, a6, &dgxiSurface);
      MF::ThrowIfFailed((MF *)v54, v55);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v65);
    }
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&graphicsSurface);
    v27 = CreateDirect3D11SurfaceFromDXGISurface(dgxiSurface, &graphicsSurface);
    MF::ThrowIfFailed((MF *)v27, v28);
    v56 = 0;
    LODWORD(v65) = 1;
    v29 = graphicsSurface;
    QueryInterface = graphicsSurface->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v56);
    v31 = ((__int64 (__fastcall *)(IInspectable *, GUID *, void **))QueryInterface)(
            v29,
            &GUID_0bf4a146_13c1_4694_bee3_7abf15eaf586,
            &v56);
    MF::ThrowIfFailed((MF *)v31, v32);
    v33 = v56;
    v34 = 0;
    v56 = 0;
    v35 = *((_QWORD *)this + 23);
    *((_QWORD *)this + 23) = v33;
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v34 = v56;
    }
    if ( v34 )
    {
      v56 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v36 = graphicsSurface;
    if ( graphicsSurface )
    {
      graphicsSurface = 0;
      ((void (__fastcall *)(IInspectable *))v36->lpVtbl->Release)(v36);
    }
    v37 = dgxiSurface;
    if ( dgxiSurface )
    {
      dgxiSurface = 0;
      ((void (__fastcall *)(IDXGISurface *))v37->lpVtbl->Release)(v37);
    }
  }
  else
  {
    v20 = *(struct IMF2DBuffer2 **)MF::As<IMF2DBuffer2,IMFMediaBuffer>(&dgxiSurface, &v59);
    graphicsSurface = 0;
    LODWORD(v65) = 4;
    v21 = (SoftwareBitmapImpl *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
    v56 = v21;
    v62 = v21;
    v22 = 0;
    if ( v21 )
    {
      v63 = v21;
      v22 = SoftwareBitmapImpl::SoftwareBitmapImpl(v21, v20, v66, a4, v16, v15, a7);
    }
    graphicsSurface = 0;
    v23 = *((_QWORD *)this + 22);
    *((_QWORD *)this + 22) = v22;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = dgxiSurface;
    if ( dgxiSurface )
    {
      dgxiSurface = 0;
      ((void (__fastcall *)(IDXGISurface *))v24->lpVtbl->Release)(v24);
    }
    if ( !*((_QWORD *)this + 22) )
    {
      v61[1] = 0;
      v61[0] = "bad allocation";
      pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
  }
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  String = WindowsCreateString(L"VideoFrame", 0xAu, (HSTRING *)this + 12);
  if ( String < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    LODWORD(v61[0]) = String;
    *(_OWORD *)&v61[1] = 0;
    throw (_com_error *)&pExceptionObject;
  }
  dgxiSurface = (IDXGISurface *)a2;
  if ( a2 )
    ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
  v63 = this;
  if ( *((struct IMFSample **)this + 11) != a2 )
  {
    if ( a2 )
      ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->AddRef)(a2);
    v39 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = a2;
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  *((_BYTE *)this + 48) = v15;
  MediaFrameImpl::ReadMfSample(this);
  v62 = 0;
  LODWORD(v65) = 8;
  v40 = (IInspectable *)operator new(0x98u, (const struct std::nothrow_t *)&std::nothrow);
  graphicsSurface = v40;
  v56 = v40;
  if ( v40 )
  {
    v64 = v40;
    v41 = MediaFramePropertySetImpl::MediaFramePropertySetImpl((MediaFramePropertySetImpl *)v40);
  }
  else
  {
    v41 = 0;
  }
  v42 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = v41;
  if ( v42 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release();
  if ( !*((_QWORD *)this + 10) )
  {
    v61[1] = 0;
    v61[0] = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  if ( a2 )
    ((void (__fastcall *)(struct IMFSample *))a2->lpVtbl->Release)(a2);
  v43 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v59;
  if ( v59 )
  {
    v59 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v44)[2])(v44);
  }
  return this;
}

```

## disassembly

```asm
0x180006620  mov     [rsp-8+arg_18], rbx
0x180006625  mov     [rsp-8+arg_10], r8
0x18000662a  mov     [rsp-8+arg_0], rcx
0x18000662f  push    rbp
0x180006630  push    rsi
0x180006631  push    rdi
0x180006632  push    r12
0x180006634  push    r13
0x180006636  push    r14
0x180006638  push    r15
0x18000663a  lea     rbp, [rsp-7]
0x18000663f  sub     rsp, 0B0h
0x180006646  mov     r13d, r9d
0x180006649  mov     rsi, r8
0x18000664c  mov     rdi, rdx
0x18000664f  mov     r14, rcx
0x180006652  xor     r15d, r15d
0x180006655  mov     dword ptr [rbp+37h+arg_8], r15d
0x180006659  call    ??0?$RuntimeClass@VMediaFrameImpl@@UIClosable@Foundation@Windows@@UIVideoFrame@Media@4@UIVideoFrame2@64@U?$CloakedIid@UIVideoFrameNative@@@WRL@Microsoft@@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@9Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>::RuntimeClass<MediaFrameImpl,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>(void)
0x18000665e  nop
0x18000665f  lea     rax, ??_7VideoFrameImpl@@6BIMediaFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IMediaFrame'}
0x180006666  mov     [r14], rax
0x180006669  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180006670  mov     [r14+8], rax
0x180006674  lea     rax, ??_7VideoFrameImpl@@6BIWeakReferenceSource@@@; const VideoFrameImpl::`vftable'{for `IWeakReferenceSource'}
0x18000667b  mov     [r14+70h], rax
0x18000667f  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@UIVideoFrame@Media@6@UIVideoFrame2@86@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IClosable,Windows::Media::IVideoFrame,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x180006686  mov     [r14+78h], rax
0x18000668a  lea     rax, ??_7VideoFrameImpl@@6BIVideoFrame@Media@Windows@@@; const VideoFrameImpl::`vftable'{for `Windows::Media::IVideoFrame'}
0x180006691  mov     [r14+80h], rax
0x180006698  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrame2@Media@Windows@@U?$CloakedIid@UIVideoFrameNative@@@23@U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Media::IVideoFrame2,Microsoft::WRL::CloakedIid<IVideoFrameNative>,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x18000669f  mov     [r14+88h], rax
0x1800066a6  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIVideoFrameNative@@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IVideoFrameNative>'}
0x1800066ad  mov     [r14+90h], rax
0x1800066b4  lea     rax, ??_7VideoFrameImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIVideoFrameInternal@Internal@Media@Windows@@@23@@Details@WRL@Microsoft@@@; const VideoFrameImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IVideoFrameInternal>>'}
0x1800066bb  mov     [r14+98h], rax
0x1800066c2  mov     [r14+0B0h], r15
0x1800066c9  mov     [r14+0B8h], r15
0x1800066d0  mov     rbx, [rbp+37h+dgxiSurface]
0x1800066d4  mov     [r14+0C0h], rbx
0x1800066db  test    rbx, rbx
0x1800066de  jz      short loc_1800066F0
0x1800066e0  mov     rax, [rbx]
0x1800066e3  mov     rcx, rbx
0x1800066e6  mov     rax, [rax+8]
0x1800066ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ef  nop
0x1800066f0  mov     [r14+0C8h], r15
0x1800066f7  mov     [r14+0D0h], r15
0x1800066fe  mov     word ptr [r14+0D8h], 0
0x180006708  movzx   r15d, byte ptr [rbp+37h+arg_28]
0x18000670d  mov     r12d, [rbp+37h+arg_20]
0x180006711  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180006718  jnb     loc_180006B83
0x18000671e  mov     rcx, [r14+58h]
0x180006722  cmp     rcx, rdi
0x180006725  jz      short loc_18000675D
0x180006727  test    rdi, rdi
0x18000672a  jz      short loc_18000673C
0x18000672c  mov     rax, [rdi]
0x18000672f  mov     rcx, rdi
0x180006732  mov     rax, [rax+8]
0x180006736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673b  nop
0x18000673c  mov     rcx, [r14+58h]
0x180006740  mov     [r14+58h], rdi
0x180006744  test    rcx, rcx
0x180006747  jz      loc_180006BBA
0x18000674d  mov     rax, [rcx]
0x180006750  mov     rax, [rax+10h]
0x180006754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006759  mov     rcx, [r14+58h]
0x18000675d  mov     [r14+30h], r15b
0x180006761  xor     esi, esi
0x180006763  mov     [rbp+37h+var_78], rsi
0x180006767  mov     rax, [rcx]
0x18000676a  lea     r8, [rbp+37h+var_78]
0x18000676e  xor     edx, edx
0x180006770  mov     rax, [rax+140h]
0x180006777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677c  test    eax, eax
0x18000677e  js      loc_180006B35
0x180006784  mov     [rbp+37h+var_80], rsi
0x180006788  mov     rcx, [rbp+37h+var_78]
0x18000678c  mov     rax, [rcx]
0x18000678f  lea     r8, [rbp+37h+var_80]
0x180006793  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x18000679a  mov     rax, [rax]
0x18000679d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a2  nop
0x1800067a3  test    eax, eax
0x1800067a5  jns     loc_1800068AB
0x1800067ab  lea     rdx, [rbp+37h+var_78]
0x1800067af  lea     rcx, [rbp+37h+dgxiSurface]
0x1800067b3  call    ??$As@UIMF2DBuffer2@@UIMFMediaBuffer@@@MF@@YA?AV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaBuffer@@@23@@Z; MF::As<IMF2DBuffer2,IMFMediaBuffer>(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x1800067b8  nop
0x1800067b9  mov     rsi, [rax]
0x1800067bc  mov     [rbp+37h+graphicsSurface], 0
0x1800067c4  mov     dword ptr [rbp+37h+arg_8], 4
0x1800067cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800067d2  mov     ecx, 70h ; 'p'; unsigned __int64
0x1800067d7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800067dc  mov     [rbp+37h+var_90], rax
0x1800067e0  mov     [rbp+37h+var_50], rax
0x1800067e4  xor     ebx, ebx
0x1800067e6  test    rax, rax
0x1800067e9  jz      loc_180006C58
0x1800067ef  mov     [rbp+37h+var_48], rax
0x1800067f3  mov     rcx, [rbp+37h+arg_30]
0x1800067f7  mov     [rsp+0E0h+var_B0], rcx; struct tagRECT *
0x1800067fc  mov     [rsp+0E0h+var_B8], r15b; bool
0x180006801  mov     [rsp+0E0h+var_C0], r12d; unsigned int
0x180006806  mov     r9d, r13d; unsigned int
0x180006809  mov     r8, [rbp+37h+arg_10]; struct _GUID *
0x18000680d  mov     rdx, rsi; struct IMF2DBuffer2 *
0x180006810  mov     rcx, rax; this
0x180006813  call    ??0SoftwareBitmapImpl@@QEAA@PEAUIMF2DBuffer2@@AEBU_GUID@@II_NAEBUtagRECT@@@Z; SoftwareBitmapImpl::SoftwareBitmapImpl(IMF2DBuffer2 *,_GUID const &,uint,uint,bool,tagRECT const &)
0x180006818  mov     rbx, rax
0x18000681b  xor     r12d, r12d
0x18000681e  mov     eax, r12d
0x180006821  test    rax, rax
0x180006824  jz      short loc_18000682E
0x180006826  mov     rcx, rax; Block
0x180006829  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000682e  mov     [rbp+37h+graphicsSurface], r12
0x180006832  mov     rcx, [r14+0B0h]
0x180006839  mov     [r14+0B0h], rbx
0x180006840  test    rcx, rcx
0x180006843  jz      short loc_180006852
0x180006845  mov     rax, [rcx]
0x180006848  mov     rax, [rax+10h]
0x18000684c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006851  nop
0x180006852  mov     esi, r12d
0x180006855  mov     rcx, [rbp+37h+dgxiSurface]
0x180006859  test    rcx, rcx
0x18000685c  jz      short loc_18000686F
0x18000685e  mov     [rbp+37h+dgxiSurface], r12
0x180006862  mov     rax, [rcx]
0x180006865  mov     rax, [rax+10h]
0x180006869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000686e  nop
0x18000686f  cmp     qword ptr [r14+0B0h], 0
0x180006877  jnz     loc_1800069CA
0x18000687d  xorps   xmm0, xmm0
0x180006880  movups  xmmword ptr [rbp+37h+var_68], xmm0
0x180006884  lea     rax, aBadAllocation; "bad allocation"
0x18000688b  mov     qword ptr [rbp+37h+var_68], rax
0x18000688f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180006896  mov     [rbp+37h+pExceptionObject], rax
0x18000689a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800068a1  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800068a5  call    _CxxThrowException_0
0x1800068ab  test    rbx, rbx
0x1800068ae  jz      loc_180006BC2
0x1800068b4  xor     r12d, r12d
0x1800068b7  mov     [rbp+37h+dgxiSurface], r12
0x1800068bb  mov     [rbp+37h+graphicsSurface], r12
0x1800068bf  mov     rsi, [rbp+37h+var_80]
0x1800068c3  mov     rax, [rsi]
0x1800068c6  mov     rbx, [rax+18h]
0x1800068ca  lea     rcx, [rbp+37h+dgxiSurface]
0x1800068ce  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800068d3  lea     r8, [rbp+37h+dgxiSurface]
0x1800068d7  lea     rdx, _GUID_aba496dd_b617_4cb8_a866_bc44d7eb1fa2
0x1800068de  mov     rcx, rsi
0x1800068e1  mov     rax, rbx
0x1800068e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e9  test    eax, eax
0x1800068eb  js      loc_180006BC8
0x1800068f1  lea     rcx, [rbp+37h+graphicsSurface]
0x1800068f5  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800068fa  lea     rdx, [rbp+37h+graphicsSurface]; graphicsSurface
0x1800068fe  mov     rcx, [rbp+37h+dgxiSurface]; dgxiSurface
0x180006902  call    cs:__imp_CreateDirect3D11SurfaceFromDXGISurface
0x180006908  mov     ecx, eax; this
0x18000690a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000690f  nop
0x180006910  mov     [rbp+37h+var_90], r12
0x180006914  mov     dword ptr [rbp+37h+arg_8], 1
0x18000691b  mov     rbx, [rbp+37h+graphicsSurface]
0x18000691f  mov     rax, [rbx]
0x180006922  mov     rsi, [rax]
0x180006925  lea     rcx, [rbp+37h+var_90]
0x180006929  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000692e  lea     r8, [rbp+37h+var_90]
0x180006932  lea     rdx, _GUID_0bf4a146_13c1_4694_bee3_7abf15eaf586
0x180006939  mov     rcx, rbx
0x18000693c  mov     rax, rsi
0x18000693f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006944  nop
0x180006945  mov     ecx, eax; this
0x180006947  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000694c  mov     rax, [rbp+37h+var_90]
0x180006950  mov     rcx, r12
0x180006953  mov     [rbp+37h+var_90], rcx
0x180006957  mov     rdx, [r14+0B8h]
0x18000695e  mov     [r14+0B8h], rax
0x180006965  test    rdx, rdx
0x180006968  jz      short loc_18000697D
0x18000696a  mov     rax, [rdx]
0x18000696d  mov     rcx, rdx
0x180006970  mov     rax, [rax+10h]
0x180006974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006979  mov     rcx, [rbp+37h+var_90]
0x18000697d  mov     esi, r12d
0x180006980  test    rcx, rcx
0x180006983  jz      short loc_180006996
0x180006985  mov     [rbp+37h+var_90], r12
0x180006989  mov     rax, [rcx]
0x18000698c  mov     rax, [rax+10h]
0x180006990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006995  nop
0x180006996  mov     rcx, [rbp+37h+graphicsSurface]
0x18000699a  test    rcx, rcx
0x18000699d  jz      short loc_1800069B0
0x18000699f  mov     [rbp+37h+graphicsSurface], r12
0x1800069a3  mov     rax, [rcx]
0x1800069a6  mov     rax, [rax+10h]
0x1800069aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069af  nop
0x1800069b0  mov     rcx, [rbp+37h+dgxiSurface]
0x1800069b4  test    rcx, rcx
0x1800069b7  jz      short loc_1800069CA
0x1800069b9  mov     [rbp+37h+dgxiSurface], r12
0x1800069bd  mov     rax, [rcx]
0x1800069c0  mov     rax, [rax+10h]
0x1800069c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c9  nop
0x1800069ca  mov     rcx, [r14+60h]; string
0x1800069ce  call    cs:__imp_WindowsDeleteString
0x1800069d4  mov     [r14+60h], r12
0x1800069d8  lea     r8, [r14+60h]; string
0x1800069dc  mov     edx, 0Ah; length
0x1800069e1  lea     rcx, sourceString; "VideoFrame"
0x1800069e8  call    cs:__imp_WindowsCreateString
0x1800069ee  test    eax, eax
0x1800069f0  js      loc_180006B5C
0x1800069f6  mov     [rbp+37h+dgxiSurface], rdi
0x1800069fa  test    rdi, rdi
0x1800069fd  jz      short loc_180006A0F
0x1800069ff  mov     rax, [rdi]
0x180006a02  mov     rcx, rdi
0x180006a05  mov     rax, [rax+8]
0x180006a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a0e  nop
0x180006a0f  mov     [rbp+37h+var_48], r14
0x180006a13  cmp     [r14+58h], rdi
0x180006a17  jz      short loc_180006A48
0x180006a19  test    rdi, rdi
0x180006a1c  jz      short loc_180006A2E
0x180006a1e  mov     rax, [rdi]
0x180006a21  mov     rcx, rdi
0x180006a24  mov     rax, [rax+8]
0x180006a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a2d  nop
0x180006a2e  mov     rcx, [r14+58h]
0x180006a32  mov     [r14+58h], rdi
0x180006a36  test    rcx, rcx
0x180006a39  jz      short loc_180006A48
0x180006a3b  mov     rax, [rcx]
0x180006a3e  mov     rax, [rax+10h]
0x180006a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a47  nop
0x180006a48  mov     [r14+30h], r15b
0x180006a4c  mov     rcx, r14; this
0x180006a4f  call    ?ReadMfSample@MediaFrameImpl@@AEAAXXZ; MediaFrameImpl::ReadMfSample(void)
0x180006a54  nop
0x180006a55  mov     [rbp+37h+var_50], r12
0x180006a59  or      esi, 8
0x180006a5c  mov     dword ptr [rbp+37h+arg_8], esi
0x180006a5f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006a66  mov     ecx, 98h; unsigned __int64
0x180006a6b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006a70  mov     [rbp+37h+graphicsSurface], rax
0x180006a74  mov     [rbp+37h+var_90], rax
0x180006a78  test    rax, rax
0x180006a7b  jz      loc_180006B2D
0x180006a81  mov     [rbp+37h+var_40], rax
0x180006a85  movzx   r8d, r15b
0x180006a89  lea     rdx, [rbp+37h+dgxiSurface]
0x180006a8d  mov     rcx, rax; this
0x180006a90  call    ??0MediaFramePropertySetImpl@@QEAA@AEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@_N@Z; MediaFramePropertySetImpl::MediaFramePropertySetImpl(Microsoft::WRL::ComPtr<IMFSample> const &,bool)
0x180006a95  mov     rbx, rax
0x180006a98  mov     rax, r12
0x180006a9b  test    rax, rax
0x180006a9e  jz      short loc_180006AA8
0x180006aa0  mov     rcx, rax; Block
0x180006aa3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006aa8  mov     rcx, [r14+50h]
0x180006aac  mov     [r14+50h], rbx
0x180006ab0  test    rcx, rcx
0x180006ab3  jz      short loc_180006ABB
0x180006ab5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@567@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(void)
0x180006aba  nop
0x180006abb  cmp     qword ptr [r14+50h], 0
0x180006ac0  jz      loc_180006C60
0x180006ac6  test    rdi, rdi
0x180006ac9  jz      short loc_180006ADB
0x180006acb  mov     rax, [rdi]
  ... truncated ...
```
