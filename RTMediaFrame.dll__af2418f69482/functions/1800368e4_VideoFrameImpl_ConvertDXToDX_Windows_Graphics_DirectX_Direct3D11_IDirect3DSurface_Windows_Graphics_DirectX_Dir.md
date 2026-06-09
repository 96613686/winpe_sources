# VideoFrameImpl::ConvertDXToDX(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,tagRECT const &,tagRECT const &,IMFDXGIDeviceManager *)

- ea: `0x1800368e4`
- end: `0x180036d57`
- name: `?ConvertDXToDX@VideoFrameImpl@@AEAAXPEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@0AEBUtagRECT@@1PEAUIMFDXGIDeviceManager@@@Z`
- size: `1139`
- prototype: `void __fastcall(VideoFrameImpl *__hidden this, struct IInspectable *, struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *, const struct tagRECT *, const struct tagRECT *, struct IMFDXGIDeviceManager *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180037088`

## callees

- `0x180001938`
- `0x1800019c0`
- `0x180005cd0`
- `0x180006e40`
- `0x18000df20`
- `0x180021e2c`
- `0x1800227b4`
- `0x180026920`
- `0x180035804`
- `0x1800368e4`
- `0x180037df4`
- `0x180037fa0`
- `0x180052010`

## import_xrefs

- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x180036aaf`
- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x180036c70`
- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x180036aaf`
- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x180036c70`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036bc4`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036bf7`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036bc4`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036bf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall VideoFrameImpl::ConvertDXToDX(
        VideoFrameImpl *this,
        struct IInspectable *a2,
        struct IInspectable *a3,
        const struct tagRECT *a4,
        const struct tagRECT *a5,
        struct IMFDXGIDeviceManager *a6)
{
  const struct _GUID *v10; // rdx
  unsigned int DXGIInterfaceFromDirect3D11Object; // eax
  int v12; // edx
  const struct _GUID *v13; // rdx
  unsigned int v14; // eax
  int v15; // edx
  IUnknown *v16; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v18; // rdi
  void (__fastcall *v19)(__int64, struct ID3D11Device **); // rbx
  IUnknown *v20; // rdi
  HRESULT (__stdcall *v21)(IUnknown *, const IID *const, void **); // rbx
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, struct ID3D11Device **); // rbx
  char v24; // bl
  unsigned int v25; // eax
  int v26; // edx
  unsigned int v27; // eax
  int v28; // edx
  unsigned int v29; // eax
  int v30; // edx
  unsigned int v31; // eax
  int v32; // edx
  unsigned int v33; // eax
  int v34; // edx
  unsigned int v35; // eax
  int v36; // edx
  _QWORD *v37; // rax
  unsigned int v38; // eax
  int v39; // edx
  unsigned int v40; // eax
  int v41; // edx
  unsigned int v42; // eax
  int v43; // edx
  unsigned int v44; // eax
  int v45; // edx
  struct ID3D11Device *v46; // [rsp+30h] [rbp-A9h] BYREF
  IDXGISurface *dgxiSurface; // [rsp+38h] [rbp-A1h] BYREF
  IInspectable *graphicsSurface; // [rsp+40h] [rbp-99h] BYREF
  IUnknown *v49; // [rsp+48h] [rbp-91h] BYREF
  struct ID3D11Texture2D *v50; // [rsp+50h] [rbp-89h] BYREF
  struct ID3D11Device *v51; // [rsp+58h] [rbp-81h] BYREF
  IUnknown *punkSurface; // [rsp+60h] [rbp-79h] BYREF
  void *v53; // [rsp+68h] [rbp-71h] BYREF
  void *v54; // [rsp+70h] [rbp-69h] BYREF
  struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *v55; // [rsp+78h] [rbp-61h] BYREF
  IInspectable *v56; // [rsp+80h] [rbp-59h] BYREF
  IDXGISurface *v57; // [rsp+88h] [rbp-51h] BYREF
  __int64 v58; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v59[8]; // [rsp+98h] [rbp-41h] BYREF
  _OWORD v60[3]; // [rsp+A0h] [rbp-39h] BYREF

  v55 = (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)a2;
  v54 = 0;
  v53 = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v54);
  DXGIInterfaceFromDirect3D11Object = GetDXGIInterfaceFromDirect3D11Object(a2, v10, &v54);
  MF::ThrowIfFailed((MF *)DXGIInterfaceFromDirect3D11Object, v12);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v53);
  v14 = GetDXGIInterfaceFromDirect3D11Object(a3, v13, &v53);
  MF::ThrowIfFailed((MF *)v14, v15);
  MF::As<ID3D11Texture2D,IDXGISurface>(&punkSurface, &v54);
  MF::As<ID3D11Texture2D,IDXGISurface>(&v58, &v53);
  v51 = 0;
  v46 = 0;
  v16 = punkSurface;
  QueryInterface = punkSurface->lpVtbl[1].QueryInterface;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v51);
  ((void (__fastcall *)(IUnknown *, struct ID3D11Device **))QueryInterface)(v16, &v51);
  v18 = v58;
  v19 = *(void (__fastcall **)(__int64, struct ID3D11Device **))(*(_QWORD *)v58 + 24LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v46);
  v19(v18, &v46);
  v20 = punkSurface;
  v21 = punkSurface->lpVtbl[1].QueryInterface;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v51);
  ((void (__fastcall *)(IUnknown *, struct ID3D11Device **))v21)(v20, &v51);
  v22 = v58;
  v23 = *(void (__fastcall **)(__int64, struct ID3D11Device **))(*(_QWORD *)v58 + 24LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v46);
  v23(v22, &v46);
  if ( v51 == v46 )
  {
    VideoFrameImpl::ConvertDXToDXOnSameDevice(
      this,
      v55,
      (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)a3,
      a4,
      a5,
      a6);
  }
  else
  {
    if ( !VideoFrameImpl::IsSameAdapter(v51, v46) )
      goto LABEL_7;
    v24 = 1;
    v50 = 0;
    if ( (int)VideoFrameImpl::GetShareableTexture((struct ID3D11Texture2D *)punkSurface, v46, &v50) >= 0 )
    {
      dgxiSurface = 0;
      graphicsSurface = 0;
      v49 = 0;
      v25 = Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface>(&v50, &dgxiSurface);
      MF::ThrowIfFailed((MF *)v25, v26);
      v27 = CreateDirect3D11SurfaceFromDXGISurface(dgxiSurface, &graphicsSurface);
      MF::ThrowIfFailed((MF *)v27, v28);
      v29 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>(
              &graphicsSurface,
              &v49);
      MF::ThrowIfFailed((MF *)v29, v30);
      VideoFrameImpl::ConvertDXToDXOnSameDevice(
        this,
        (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)v49,
        (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)a3,
        a4,
        a5,
        a6);
      v24 = 0;
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&graphicsSurface);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&dgxiSurface);
    }
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v50);
    if ( v24 )
    {
LABEL_7:
      memset(v60, 0, 44);
      v49 = 0;
      ((void (__fastcall *)(IUnknown *, _OWORD *))punkSurface->lpVtbl[3].AddRef)(punkSurface, v60);
      *((_QWORD *)&v60[0] + 1) = 0x100000001LL;
      *(_QWORD *)((char *)&v60[1] + 4) = 1;
      HIDWORD(v60[1]) = 0;
      *(_QWORD *)&v60[2] = 40;
      DWORD2(v60[2]) = 0;
      v31 = ((__int64 (__fastcall *)(struct ID3D11Device *, _OWORD *, _QWORD, IUnknown **))v46->lpVtbl->CreateTexture2D)(
              v46,
              v60,
              0,
              &v49);
      MF::ThrowIfFailed((MF *)v31, v32);
      graphicsSurface = 0;
      dgxiSurface = 0;
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&graphicsSurface);
      v33 = MFCreateDXGISurfaceBuffer(
              &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
              punkSurface,
              0,
              0,
              (IMFMediaBuffer **)&graphicsSurface);
      MF::ThrowIfFailed((MF *)v33, v34);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&dgxiSurface);
      v35 = MFCreateDXGISurfaceBuffer(
              &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
              v49,
              0,
              0,
              (IMFMediaBuffer **)&dgxiSurface);
      MF::ThrowIfFailed((MF *)v35, v36);
      MF::As<IMF2DBuffer2,IMFMediaBuffer>(&v55, &dgxiSurface);
      v37 = (_QWORD *)MF::As<IMF2DBuffer2,IMFMediaBuffer>(v59, &graphicsSurface);
      v38 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *))(*(_QWORD *)*v37 + 88LL))(
              *v37,
              v55);
      MF::ThrowIfFailed((MF *)v38, v39);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(v59);
      v57 = 0;
      v56 = 0;
      v50 = 0;
      v40 = Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface>(&v49, &v57);
      MF::ThrowIfFailed((MF *)v40, v41);
      v42 = CreateDirect3D11SurfaceFromDXGISurface(v57, &v56);
      MF::ThrowIfFailed((MF *)v42, v43);
      v44 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>(
              &v56,
              &v50);
      MF::ThrowIfFailed((MF *)v44, v45);
      VideoFrameImpl::ConvertDXToDXOnSameDevice(
        this,
        (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)v50,
        (struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)a3,
        a4,
        a5,
        a6);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&dgxiSurface);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&graphicsSurface);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v49);
    }
  }
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v51);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&punkSurface);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v54);
}

```

## disassembly

```asm
0x1800368e4  push    rbp
0x1800368e6  push    rbx
0x1800368e7  push    rsi
0x1800368e8  push    rdi
0x1800368e9  push    r12
0x1800368eb  push    r13
0x1800368ed  push    r14
0x1800368ef  push    r15
0x1800368f1  lea     rbp, [rsp-0Fh]
0x1800368f6  sub     rsp, 0E8h
0x1800368fd  mov     rax, cs:__security_cookie
0x180036904  xor     rax, rsp
0x180036907  mov     [rbp+47h+var_50], rax
0x18003690b  mov     r15, r9
0x18003690e  mov     rsi, r8
0x180036911  mov     rbx, rdx
0x180036914  mov     [rbp+47h+var_A8], rdx
0x180036918  mov     r14, rcx
0x18003691b  mov     r12, [rbp+47h+arg_20]
0x18003691f  mov     r13, [rbp+47h+arg_28]
0x180036923  xor     edi, edi
0x180036925  mov     [rbp+47h+var_B0], rdi
0x180036929  mov     [rbp+47h+var_B8], rdi
0x18003692d  lea     rcx, [rbp+47h+var_B0]
0x180036931  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036936  lea     r8, [rbp+47h+var_B0]; void **
0x18003693a  mov     rcx, rbx; struct IInspectable *
0x18003693d  call    ?GetDXGIInterfaceFromDirect3D11Object@@YAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; GetDXGIInterfaceFromDirect3D11Object(IInspectable *,_GUID const &,void * *)
0x180036942  mov     ecx, eax; this
0x180036944  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036949  lea     rcx, [rbp+47h+var_B8]
0x18003694d  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036952  lea     r8, [rbp+47h+var_B8]; void **
0x180036956  mov     rcx, rsi; struct IInspectable *
0x180036959  call    ?GetDXGIInterfaceFromDirect3D11Object@@YAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; GetDXGIInterfaceFromDirect3D11Object(IInspectable *,_GUID const &,void * *)
0x18003695e  mov     ecx, eax; this
0x180036960  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036965  lea     rdx, [rbp+47h+var_B0]
0x180036969  lea     rcx, [rbp+47h+punkSurface]
0x18003696d  call    ??$As@UID3D11Texture2D@@UIDXGISurface@@@MF@@YA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@AEBV?$ComPtr@UIDXGISurface@@@23@@Z; MF::As<ID3D11Texture2D,IDXGISurface>(Microsoft::WRL::ComPtr<IDXGISurface> const &)
0x180036972  nop
0x180036973  lea     rdx, [rbp+47h+var_B8]
0x180036977  lea     rcx, [rbp+47h+var_90]
0x18003697b  call    ??$As@UID3D11Texture2D@@UIDXGISurface@@@MF@@YA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@AEBV?$ComPtr@UIDXGISurface@@@23@@Z; MF::As<ID3D11Texture2D,IDXGISurface>(Microsoft::WRL::ComPtr<IDXGISurface> const &)
0x180036980  nop
0x180036981  mov     [rsp+120h+var_C8], rdi
0x180036986  mov     [rsp+120h+var_F0], rdi
0x18003698b  mov     rdi, [rbp+47h+punkSurface]
0x18003698f  mov     rax, [rdi]
0x180036992  mov     rbx, [rax+18h]
0x180036996  lea     rcx, [rsp+120h+var_C8]
0x18003699b  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800369a0  lea     rdx, [rsp+120h+var_C8]
0x1800369a5  mov     rcx, rdi
0x1800369a8  mov     rax, rbx
0x1800369ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369b0  mov     rdi, [rbp+47h+var_90]
0x1800369b4  mov     rax, [rdi]
0x1800369b7  mov     rbx, [rax+18h]
0x1800369bb  lea     rcx, [rsp+120h+var_F0]
0x1800369c0  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800369c5  lea     rdx, [rsp+120h+var_F0]
0x1800369ca  mov     rcx, rdi
0x1800369cd  mov     rax, rbx
0x1800369d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369d5  mov     rdi, [rbp+47h+punkSurface]
0x1800369d9  mov     rax, [rdi]
0x1800369dc  mov     rbx, [rax+18h]
0x1800369e0  lea     rcx, [rsp+120h+var_C8]
0x1800369e5  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800369ea  lea     rdx, [rsp+120h+var_C8]
0x1800369ef  mov     rcx, rdi
0x1800369f2  mov     rax, rbx
0x1800369f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369fa  mov     rdi, [rbp+47h+var_90]
0x1800369fe  mov     rax, [rdi]
0x180036a01  mov     rbx, [rax+18h]
0x180036a05  lea     rcx, [rsp+120h+var_F0]
0x180036a0a  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036a0f  lea     rdx, [rsp+120h+var_F0]
0x180036a14  mov     rcx, rdi
0x180036a17  mov     rax, rbx
0x180036a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a1f  mov     rcx, [rsp+120h+var_C8]; struct ID3D11Device *
0x180036a24  mov     rdx, [rsp+120h+var_F0]; struct ID3D11Device *
0x180036a29  cmp     rcx, rdx
0x180036a2c  jnz     short loc_180036A4F
0x180036a2e  mov     [rsp+120h+var_F8], r13; struct IMFDXGIDeviceManager *
0x180036a33  mov     [rsp+120h+ppBuffer], r12; struct tagRECT *
0x180036a38  mov     r9, r15; struct tagRECT *
0x180036a3b  mov     r8, rsi; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180036a3e  mov     rdx, [rbp+47h+var_A8]; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180036a42  mov     rcx, r14; this
0x180036a45  call    ?ConvertDXToDXOnSameDevice@VideoFrameImpl@@AEAAXPEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@0AEBUtagRECT@@1PEAUIMFDXGIDeviceManager@@@Z; VideoFrameImpl::ConvertDXToDXOnSameDevice(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,tagRECT const &,tagRECT const &,IMFDXGIDeviceManager *)
0x180036a4a  jmp     loc_180036CFA
0x180036a4f  call    ?IsSameAdapter@VideoFrameImpl@@CA_NPEAUID3D11Device@@0@Z; VideoFrameImpl::IsSameAdapter(ID3D11Device *,ID3D11Device *)
0x180036a54  xor     edi, edi
0x180036a56  test    al, al
0x180036a58  jz      loc_180036B25
0x180036a5e  mov     bl, 1
0x180036a60  mov     [rsp+120h+var_D0], rdi
0x180036a65  lea     r8, [rsp+120h+var_D0]; struct ID3D11Texture2D **
0x180036a6a  mov     rdx, [rsp+120h+var_F0]; struct ID3D11Device *
0x180036a6f  mov     rcx, [rbp+47h+punkSurface]; struct ID3D11Texture2D *
0x180036a73  call    ?GetShareableTexture@VideoFrameImpl@@CAJPEAUID3D11Texture2D@@PEAUID3D11Device@@PEAPEAU2@@Z; VideoFrameImpl::GetShareableTexture(ID3D11Texture2D *,ID3D11Device *,ID3D11Texture2D * *)
0x180036a78  test    eax, eax
0x180036a7a  js      loc_180036B13
0x180036a80  mov     [rsp+120h+dgxiSurface], rdi
0x180036a85  mov     [rsp+120h+graphicsSurface], rdi
0x180036a8a  mov     [rsp+120h+var_D8], rdi
0x180036a8f  lea     rdx, [rsp+120h+dgxiSurface]
0x180036a94  lea     rcx, [rsp+120h+var_D0]
0x180036a99  call    ??$As@UIDXGISurface@@@?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGISurface@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGISurface>>)
0x180036a9e  mov     ecx, eax; this
0x180036aa0  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036aa5  lea     rdx, [rsp+120h+graphicsSurface]; graphicsSurface
0x180036aaa  mov     rcx, [rsp+120h+dgxiSurface]; dgxiSurface
0x180036aaf  call    cs:__imp_CreateDirect3D11SurfaceFromDXGISurface
0x180036ab5  mov     ecx, eax; this
0x180036ab7  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036abc  lea     rdx, [rsp+120h+var_D8]
0x180036ac1  lea     rcx, [rsp+120h+graphicsSurface]
0x180036ac6  call    ??$As@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>>)
0x180036acb  mov     ecx, eax; this
0x180036acd  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036ad2  mov     [rsp+120h+var_F8], r13; struct IMFDXGIDeviceManager *
0x180036ad7  mov     [rsp+120h+ppBuffer], r12; struct tagRECT *
0x180036adc  mov     r9, r15; struct tagRECT *
0x180036adf  mov     r8, rsi; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180036ae2  mov     rdx, [rsp+120h+var_D8]; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180036ae7  mov     rcx, r14; this
0x180036aea  call    ?ConvertDXToDXOnSameDevice@VideoFrameImpl@@AEAAXPEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@0AEBUtagRECT@@1PEAUIMFDXGIDeviceManager@@@Z; VideoFrameImpl::ConvertDXToDXOnSameDevice(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,tagRECT const &,tagRECT const &,IMFDXGIDeviceManager *)
0x180036aef  mov     bl, dil
0x180036af2  lea     rcx, [rsp+120h+var_D8]
0x180036af7  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036afc  nop
0x180036afd  lea     rcx, [rsp+120h+graphicsSurface]
0x180036b02  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036b07  nop
0x180036b08  lea     rcx, [rsp+120h+dgxiSurface]
0x180036b0d  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036b12  nop
0x180036b13  lea     rcx, [rsp+120h+var_D0]
0x180036b18  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036b1d  test    bl, bl
0x180036b1f  jz      loc_180036CFA
0x180036b25  xorps   xmm0, xmm0
0x180036b28  movups  [rbp+47h+var_80], xmm0
0x180036b2c  movups  [rbp+47h+var_70], xmm0
0x180036b30  movups  [rbp+47h+var_70+0Ch], xmm0
0x180036b34  mov     [rsp+120h+var_D8], rdi
0x180036b39  mov     rcx, [rbp+47h+punkSurface]
0x180036b3d  mov     rax, [rcx]
0x180036b40  lea     rdx, [rbp+47h+var_80]
0x180036b44  mov     rax, [rax+50h]
0x180036b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b4d  mov     dword ptr [rbp+47h+var_80+8], 1
0x180036b54  mov     dword ptr [rbp+47h+var_80+0Ch], 1
0x180036b5b  mov     qword ptr [rbp+47h+var_70+4], 1
0x180036b63  mov     dword ptr [rbp+47h+var_70+0Ch], edi
0x180036b66  mov     [rbp+47h+var_60], 28h ; '('
0x180036b6e  mov     [rbp+47h+var_58], edi
0x180036b71  mov     rcx, [rsp+120h+var_F0]
0x180036b76  mov     rax, [rcx]
0x180036b79  lea     r9, [rsp+120h+var_D8]
0x180036b7e  xor     r8d, r8d
0x180036b81  lea     rdx, [rbp+47h+var_80]
0x180036b85  mov     rax, [rax+28h]
0x180036b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b8e  mov     ecx, eax; this
0x180036b90  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036b95  mov     [rsp+120h+graphicsSurface], rdi
0x180036b9a  mov     [rsp+120h+dgxiSurface], rdi
0x180036b9f  lea     rcx, [rsp+120h+graphicsSurface]
0x180036ba4  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036ba9  lea     rax, [rsp+120h+graphicsSurface]
0x180036bae  mov     [rsp+120h+ppBuffer], rax; ppBuffer
0x180036bb3  xor     r9d, r9d; fBottomUpWhenLinear
0x180036bb6  xor     r8d, r8d; uSubresourceIndex
0x180036bb9  mov     rdx, [rbp+47h+punkSurface]; punkSurface
0x180036bbd  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x180036bc4  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x180036bca  mov     ecx, eax; this
0x180036bcc  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036bd1  lea     rcx, [rsp+120h+dgxiSurface]
0x180036bd6  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036bdb  lea     rax, [rsp+120h+dgxiSurface]
0x180036be0  mov     [rsp+120h+ppBuffer], rax; ppBuffer
0x180036be5  xor     r9d, r9d; fBottomUpWhenLinear
0x180036be8  xor     r8d, r8d; uSubresourceIndex
0x180036beb  mov     rdx, [rsp+120h+var_D8]; punkSurface
0x180036bf0  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x180036bf7  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x180036bfd  mov     ecx, eax; this
0x180036bff  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036c04  lea     rdx, [rsp+120h+dgxiSurface]
0x180036c09  lea     rcx, [rbp+47h+var_A8]
0x180036c0d  call    ??$As@UIMF2DBuffer2@@UIMFMediaBuffer@@@MF@@YA?AV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaBuffer@@@23@@Z; MF::As<IMF2DBuffer2,IMFMediaBuffer>(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x180036c12  nop
0x180036c13  lea     rdx, [rsp+120h+graphicsSurface]
0x180036c18  lea     rcx, [rbp+47h+var_88]
0x180036c1c  call    ??$As@UIMF2DBuffer2@@UIMFMediaBuffer@@@MF@@YA?AV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaBuffer@@@23@@Z; MF::As<IMF2DBuffer2,IMFMediaBuffer>(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x180036c21  nop
0x180036c22  mov     rcx, [rax]
0x180036c25  mov     rax, [rcx]
0x180036c28  mov     rdx, [rbp+47h+var_A8]
0x180036c2c  mov     rax, [rax+58h]
0x180036c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c35  mov     ecx, eax; this
0x180036c37  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036c3c  nop
0x180036c3d  lea     rcx, [rbp+47h+var_88]
0x180036c41  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036c46  mov     [rbp+47h+var_98], rdi
0x180036c4a  mov     [rbp+47h+var_A0], rdi
0x180036c4e  mov     [rsp+120h+var_D0], rdi
0x180036c53  lea     rdx, [rbp+47h+var_98]
0x180036c57  lea     rcx, [rsp+120h+var_D8]
0x180036c5c  call    ??$As@UIDXGISurface@@@?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGISurface@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGISurface>>)
0x180036c61  mov     ecx, eax; this
0x180036c63  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036c68  lea     rdx, [rbp+47h+var_A0]; graphicsSurface
0x180036c6c  mov     rcx, [rbp+47h+var_98]; dgxiSurface
0x180036c70  call    cs:__imp_CreateDirect3D11SurfaceFromDXGISurface
0x180036c76  mov     ecx, eax; this
0x180036c78  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036c7d  lea     rdx, [rsp+120h+var_D0]
0x180036c82  lea     rcx, [rbp+47h+var_A0]
0x180036c86  call    ??$As@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>>)
0x180036c8b  mov     ecx, eax; this
0x180036c8d  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036c92  mov     [rsp+120h+var_F8], r13; struct IMFDXGIDeviceManager *
0x180036c97  mov     [rsp+120h+ppBuffer], r12; struct tagRECT *
0x180036c9c  mov     r9, r15; struct tagRECT *
0x180036c9f  mov     r8, rsi; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180036ca2  mov     rdx, [rsp+120h+var_D0]; struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *
0x180036ca7  mov     rcx, r14; this
0x180036caa  call    ?ConvertDXToDXOnSameDevice@VideoFrameImpl@@AEAAXPEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@0AEBUtagRECT@@1PEAUIMFDXGIDeviceManager@@@Z; VideoFrameImpl::ConvertDXToDXOnSameDevice(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,tagRECT const &,tagRECT const &,IMFDXGIDeviceManager *)
0x180036caf  nop
0x180036cb0  lea     rcx, [rsp+120h+var_D0]
0x180036cb5  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036cba  nop
0x180036cbb  lea     rcx, [rbp+47h+var_A0]
0x180036cbf  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036cc4  nop
0x180036cc5  lea     rcx, [rbp+47h+var_98]
0x180036cc9  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036cce  nop
0x180036ccf  lea     rcx, [rbp+47h+var_A8]
0x180036cd3  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036cd8  nop
0x180036cd9  lea     rcx, [rsp+120h+dgxiSurface]
0x180036cde  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036ce3  nop
0x180036ce4  lea     rcx, [rsp+120h+graphicsSurface]
0x180036ce9  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036cee  nop
0x180036cef  lea     rcx, [rsp+120h+var_D8]
0x180036cf4  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036cf9  nop
0x180036cfa  lea     rcx, [rsp+120h+var_F0]
0x180036cff  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036d04  nop
0x180036d05  lea     rcx, [rsp+120h+var_C8]
0x180036d0a  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036d0f  nop
0x180036d10  lea     rcx, [rbp+47h+var_90]
0x180036d14  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036d19  nop
0x180036d1a  lea     rcx, [rbp+47h+punkSurface]
0x180036d1e  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036d23  nop
0x180036d24  lea     rcx, [rbp+47h+var_B8]
0x180036d28  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036d2d  nop
0x180036d2e  lea     rcx, [rbp+47h+var_B0]
0x180036d32  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036d37  mov     rcx, [rbp+47h+var_50]
0x180036d3b  xor     rcx, rsp; StackCookie
0x180036d3e  call    __security_check_cookie
0x180036d43  add     rsp, 0E8h
0x180036d4a  pop     r15
0x180036d4c  pop     r14
0x180036d4e  pop     r13
0x180036d50  pop     r12
0x180036d52  pop     rdi
0x180036d53  pop     rsi
0x180036d54  pop     rbx
0x180036d55  pop     rbp
0x180036d56  retn
```
