# VideoFrameImpl::CopyDXToDX(Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *,Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)

- ea: `0x180036d60`
- end: `0x180036fcc`
- name: `?CopyDXToDX@VideoFrameImpl@@AEAAXPEAUIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@0@Z`
- size: `620`
- prototype: `void(VideoFrameImpl *__hidden this, struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *, struct Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180037088`

## callees

- `0x180001938`
- `0x1800019c0`
- `0x180005cd0`
- `0x180006e40`
- `0x180021e2c`
- `0x180036d60`
- `0x180036fd4`
- `0x180037df4`
- `0x180037fa0`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036ee3`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036f13`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036ee3`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036f13`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall VideoFrameImpl::CopyDXToDX(struct ID3D11Device *this, struct IInspectable *a2, struct IInspectable *a3)
{
  const struct _GUID *v5; // rdx
  unsigned int DXGIInterfaceFromDirect3D11Object; // eax
  int v7; // edx
  const struct _GUID *v8; // rdx
  unsigned int v9; // eax
  int v10; // edx
  IUnknown *v11; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  IUnknown *v13; // rdi
  HRESULT (__stdcall *v14)(IUnknown *, const IID *const, void **); // rbx
  char v15; // bl
  VideoFrameImpl *v16; // rcx
  unsigned int v17; // eax
  int v18; // edx
  unsigned int v19; // eax
  int v20; // edx
  _QWORD *v21; // rax
  unsigned int v22; // eax
  int v23; // edx
  IUnknown *punkSurface; // [rsp+30h] [rbp-40h] BYREF
  IMFMediaBuffer *v25; // [rsp+38h] [rbp-38h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+40h] [rbp-30h] BYREF
  struct ID3D11Device *v27; // [rsp+48h] [rbp-28h] BYREF
  void *v28; // [rsp+50h] [rbp-20h] BYREF
  void *v29; // [rsp+58h] [rbp-18h] BYREF
  __int64 v30; // [rsp+60h] [rbp-10h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-8h] BYREF
  struct ID3D11Device *v32; // [rsp+80h] [rbp+10h] BYREF
  IUnknown *v33; // [rsp+98h] [rbp+28h] BYREF

  v32 = this;
  v29 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v29);
  DXGIInterfaceFromDirect3D11Object = GetDXGIInterfaceFromDirect3D11Object(a2, v5, &v29);
  MF::ThrowIfFailed((MF *)DXGIInterfaceFromDirect3D11Object, v7);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v28);
  v9 = GetDXGIInterfaceFromDirect3D11Object(a3, v8, &v28);
  MF::ThrowIfFailed((MF *)v9, v10);
  MF::As<ID3D11Texture2D,IDXGISurface>(&punkSurface, &v29);
  MF::As<ID3D11Texture2D,IDXGISurface>(&v33, &v28);
  v27 = 0;
  v32 = 0;
  v11 = punkSurface;
  QueryInterface = punkSurface->lpVtbl[1].QueryInterface;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v27);
  ((void (__fastcall *)(IUnknown *, struct ID3D11Device **))QueryInterface)(v11, &v27);
  v13 = v33;
  v14 = v33->lpVtbl[1].QueryInterface;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
  ((void (__fastcall *)(IUnknown *, struct ID3D11Device **))v14)(v13, &v32);
  if ( v27 == v32 )
  {
    VideoFrameImpl::CopyDXToDXOnSameDevice(
      (VideoFrameImpl *)v27,
      (struct ID3D11Texture2D *)punkSurface,
      (struct ID3D11Texture2D *)v33);
  }
  else
  {
    if ( !VideoFrameImpl::IsSameAdapter(v27, v32) )
      goto LABEL_7;
    v15 = 1;
    ppBuffer = 0;
    if ( (int)VideoFrameImpl::GetShareableTexture(
                (struct ID3D11Texture2D *)punkSurface,
                v32,
                (struct ID3D11Texture2D **)&ppBuffer) >= 0 )
    {
      v30 = 0;
      VideoFrameImpl::CopyDXToDXOnSameDevice(v16, (struct ID3D11Texture2D *)ppBuffer, (struct ID3D11Texture2D *)v33);
      v15 = 0;
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v30);
    }
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppBuffer);
    if ( v15 )
    {
LABEL_7:
      ppBuffer = 0;
      v25 = 0;
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppBuffer);
      v17 = MFCreateDXGISurfaceBuffer(&GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, punkSurface, 0, 0, &ppBuffer);
      MF::ThrowIfFailed((MF *)v17, v18);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v25);
      v19 = MFCreateDXGISurfaceBuffer(&GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, v33, 0, 0, &v25);
      MF::ThrowIfFailed((MF *)v19, v20);
      MF::As<IMF2DBuffer2,IMFMediaBuffer>(&v30, &v25);
      v21 = (_QWORD *)MF::As<IMF2DBuffer2,IMFMediaBuffer>(v31, &ppBuffer);
      v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v21 + 88LL))(*v21, v30);
      MF::ThrowIfFailed((MF *)v22, v23);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(v31);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppBuffer);
    }
  }
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&punkSurface);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v29);
}

```

## disassembly

```asm
0x180036d60  mov     [rsp-8+arg_8], rbx
0x180036d65  mov     [rsp-8+arg_10], rdi
0x180036d6a  mov     [rsp-8+arg_0], rcx
0x180036d6f  push    rbp
0x180036d70  mov     rbp, rsp
0x180036d73  sub     rsp, 70h
0x180036d77  mov     rdi, r8
0x180036d7a  mov     rbx, rdx
0x180036d7d  mov     [rbp+var_18], 0
0x180036d85  mov     [rbp+var_20], 0
0x180036d8d  lea     rcx, [rbp+var_18]
0x180036d91  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036d96  lea     r8, [rbp+var_18]; void **
0x180036d9a  mov     rcx, rbx; struct IInspectable *
0x180036d9d  call    ?GetDXGIInterfaceFromDirect3D11Object@@YAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; GetDXGIInterfaceFromDirect3D11Object(IInspectable *,_GUID const &,void * *)
0x180036da2  mov     ecx, eax; this
0x180036da4  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036da9  lea     rcx, [rbp+var_20]
0x180036dad  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036db2  lea     r8, [rbp+var_20]; void **
0x180036db6  mov     rcx, rdi; struct IInspectable *
0x180036db9  call    ?GetDXGIInterfaceFromDirect3D11Object@@YAJPEAUIInspectable@@AEBU_GUID@@PEAPEAX@Z; GetDXGIInterfaceFromDirect3D11Object(IInspectable *,_GUID const &,void * *)
0x180036dbe  mov     ecx, eax; this
0x180036dc0  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036dc5  lea     rdx, [rbp+var_18]
0x180036dc9  lea     rcx, [rbp+punkSurface]
0x180036dcd  call    ??$As@UID3D11Texture2D@@UIDXGISurface@@@MF@@YA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@AEBV?$ComPtr@UIDXGISurface@@@23@@Z; MF::As<ID3D11Texture2D,IDXGISurface>(Microsoft::WRL::ComPtr<IDXGISurface> const &)
0x180036dd2  nop
0x180036dd3  lea     rdx, [rbp+var_20]
0x180036dd7  lea     rcx, [rbp+arg_18]
0x180036ddb  call    ??$As@UID3D11Texture2D@@UIDXGISurface@@@MF@@YA?AV?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@AEBV?$ComPtr@UIDXGISurface@@@23@@Z; MF::As<ID3D11Texture2D,IDXGISurface>(Microsoft::WRL::ComPtr<IDXGISurface> const &)
0x180036de0  nop
0x180036de1  mov     [rbp+var_28], 0
0x180036de9  mov     [rbp+arg_0], 0
0x180036df1  mov     rdi, [rbp+punkSurface]
0x180036df5  mov     rax, [rdi]
0x180036df8  mov     rbx, [rax+18h]
0x180036dfc  lea     rcx, [rbp+var_28]
0x180036e00  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036e05  lea     rdx, [rbp+var_28]
0x180036e09  mov     rcx, rdi
0x180036e0c  mov     rax, rbx
0x180036e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e14  mov     rdi, [rbp+arg_18]
0x180036e18  mov     rax, [rdi]
0x180036e1b  mov     rbx, [rax+18h]
0x180036e1f  lea     rcx, [rbp+arg_0]
0x180036e23  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036e28  lea     rdx, [rbp+arg_0]
0x180036e2c  mov     rcx, rdi
0x180036e2f  mov     rax, rbx
0x180036e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e37  mov     rcx, [rbp+var_28]; struct ID3D11Device *
0x180036e3b  mov     rdx, [rbp+arg_0]; struct ID3D11Device *
0x180036e3f  cmp     rcx, rdx
0x180036e42  jnz     short loc_180036E56
0x180036e44  mov     r8, [rbp+arg_18]; struct ID3D11Texture2D *
0x180036e48  mov     rdx, [rbp+punkSurface]; struct ID3D11Texture2D *
0x180036e4c  call    ?CopyDXToDXOnSameDevice@VideoFrameImpl@@AEAAXPEAUID3D11Texture2D@@0@Z; VideoFrameImpl::CopyDXToDXOnSameDevice(ID3D11Texture2D *,ID3D11Texture2D *)
0x180036e51  jmp     loc_180036F7F
0x180036e56  call    ?IsSameAdapter@VideoFrameImpl@@CA_NPEAUID3D11Device@@0@Z; VideoFrameImpl::IsSameAdapter(ID3D11Device *,ID3D11Device *)
0x180036e5b  test    al, al
0x180036e5d  jz      short loc_180036EB0
0x180036e5f  mov     bl, 1
0x180036e61  mov     [rbp+var_30], 0
0x180036e69  lea     r8, [rbp+var_30]; struct ID3D11Texture2D **
0x180036e6d  mov     rdx, [rbp+arg_0]; struct ID3D11Device *
0x180036e71  mov     rcx, [rbp+punkSurface]; struct ID3D11Texture2D *
0x180036e75  call    ?GetShareableTexture@VideoFrameImpl@@CAJPEAUID3D11Texture2D@@PEAUID3D11Device@@PEAPEAU2@@Z; VideoFrameImpl::GetShareableTexture(ID3D11Texture2D *,ID3D11Device *,ID3D11Texture2D * *)
0x180036e7a  test    eax, eax
0x180036e7c  js      short loc_180036E9F
0x180036e7e  mov     [rbp+var_10], 0
0x180036e86  mov     r8, [rbp+arg_18]; struct ID3D11Texture2D *
0x180036e8a  mov     rdx, [rbp+var_30]; struct ID3D11Texture2D *
0x180036e8e  call    ?CopyDXToDXOnSameDevice@VideoFrameImpl@@AEAAXPEAUID3D11Texture2D@@0@Z; VideoFrameImpl::CopyDXToDXOnSameDevice(ID3D11Texture2D *,ID3D11Texture2D *)
0x180036e93  xor     bl, bl
0x180036e95  lea     rcx, [rbp+var_10]
0x180036e99  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036e9e  nop
0x180036e9f  lea     rcx, [rbp+var_30]
0x180036ea3  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036ea8  test    bl, bl
0x180036eaa  jz      loc_180036F7F
0x180036eb0  mov     [rbp+var_30], 0
0x180036eb8  mov     [rbp+var_38], 0
0x180036ec0  lea     rcx, [rbp+var_30]
0x180036ec4  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036ec9  lea     rax, [rbp+var_30]
0x180036ecd  mov     [rsp+70h+ppBuffer], rax; ppBuffer
0x180036ed2  xor     r9d, r9d; fBottomUpWhenLinear
0x180036ed5  xor     r8d, r8d; uSubresourceIndex
0x180036ed8  mov     rdx, [rbp+punkSurface]; punkSurface
0x180036edc  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x180036ee3  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x180036ee9  mov     ecx, eax; this
0x180036eeb  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036ef0  lea     rcx, [rbp+var_38]
0x180036ef4  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036ef9  lea     rax, [rbp+var_38]
0x180036efd  mov     [rsp+70h+ppBuffer], rax; ppBuffer
0x180036f02  xor     r9d, r9d; fBottomUpWhenLinear
0x180036f05  xor     r8d, r8d; uSubresourceIndex
0x180036f08  mov     rdx, [rbp+arg_18]; punkSurface
0x180036f0c  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x180036f13  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x180036f19  mov     ecx, eax; this
0x180036f1b  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036f20  lea     rdx, [rbp+var_38]
0x180036f24  lea     rcx, [rbp+var_10]
0x180036f28  call    ??$As@UIMF2DBuffer2@@UIMFMediaBuffer@@@MF@@YA?AV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaBuffer@@@23@@Z; MF::As<IMF2DBuffer2,IMFMediaBuffer>(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x180036f2d  nop
0x180036f2e  lea     rdx, [rbp+var_30]
0x180036f32  lea     rcx, [rbp+var_8]
0x180036f36  call    ??$As@UIMF2DBuffer2@@UIMFMediaBuffer@@@MF@@YA?AV?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFMediaBuffer@@@23@@Z; MF::As<IMF2DBuffer2,IMFMediaBuffer>(Microsoft::WRL::ComPtr<IMFMediaBuffer> const &)
0x180036f3b  nop
0x180036f3c  mov     rcx, [rax]
0x180036f3f  mov     rax, [rcx]
0x180036f42  mov     rdx, [rbp+var_10]
0x180036f46  mov     rax, [rax+58h]
0x180036f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f4f  mov     ecx, eax; this
0x180036f51  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180036f56  nop
0x180036f57  lea     rcx, [rbp+var_8]
0x180036f5b  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036f60  nop
0x180036f61  lea     rcx, [rbp+var_10]
0x180036f65  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036f6a  nop
0x180036f6b  lea     rcx, [rbp+var_38]
0x180036f6f  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036f74  nop
0x180036f75  lea     rcx, [rbp+var_30]
0x180036f79  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036f7e  nop
0x180036f7f  lea     rcx, [rbp+arg_0]
0x180036f83  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036f88  nop
0x180036f89  lea     rcx, [rbp+var_28]
0x180036f8d  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036f92  nop
0x180036f93  lea     rcx, [rbp+arg_18]
0x180036f97  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036f9c  nop
0x180036f9d  lea     rcx, [rbp+punkSurface]
0x180036fa1  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036fa6  nop
0x180036fa7  lea     rcx, [rbp+var_20]
0x180036fab  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036fb0  nop
0x180036fb1  lea     rcx, [rbp+var_18]
0x180036fb5  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180036fba  lea     r11, [rsp+70h+var_s0]
0x180036fbf  mov     rbx, [r11+18h]
0x180036fc3  mov     rdi, [r11+20h]
0x180036fc7  mov     rsp, r11
0x180036fca  pop     rbp
0x180036fcb  retn
```
