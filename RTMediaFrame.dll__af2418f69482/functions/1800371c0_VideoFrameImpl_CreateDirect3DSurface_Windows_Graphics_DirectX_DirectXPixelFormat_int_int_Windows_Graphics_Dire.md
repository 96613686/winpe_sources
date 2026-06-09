# VideoFrameImpl::CreateDirect3DSurface(Windows::Graphics::DirectX::DirectXPixelFormat,int,int,Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice *)

- ea: `0x1800371c0`
- end: `0x180037461`
- name: `?CreateDirect3DSurface@VideoFrameImpl@@AEAAXW4DirectXPixelFormat@DirectX@Graphics@Windows@@HHPEAUIDirect3DDevice@Direct3D11@345@@Z`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035e40`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x18000df20`
- `0x180035804`
- `0x180036074`
- `0x1800371c0`
- `0x180037468`
- `0x1800376f4`
- `0x180052010`

## import_xrefs

- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x1800373bb`
- `d3d11!CreateDirect3D11SurfaceFromDXGISurface` at `0x1800373bb`
- `MFPlat!MFCreateDXGIDeviceManager` at `0x1800372c9`
- `MFPlat!MFCreateDXGIDeviceManager` at `0x1800372c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall VideoFrameImpl::CreateDirect3DSurface(
        VideoFrameImpl *a1,
        enum DXGI_FORMAT a2,
        int a3,
        int a4,
        __int64 (__fastcall ***resetToken)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // eax
  int v14; // edx
  struct ID3D11Device *v15; // rdi
  HRESULT (__stdcall *QueryInterface)(ID3D11Device *, const IID *const, void **); // rbx
  unsigned int v17; // eax
  int v18; // edx
  unsigned int v19; // eax
  int v20; // edx
  unsigned int v21; // eax
  int v22; // edx
  unsigned int v23; // eax
  int v24; // edx
  unsigned int v25; // eax
  int v26; // edx
  unsigned int v27; // eax
  int v28; // edx
  unsigned int v29; // eax
  int v30; // edx
  unsigned int v31; // eax
  int v32; // edx
  IMFDXGIDeviceManager *v33; // rbx
  __int64 v34; // rcx
  __int64 result; // rax
  struct ID3D11Device *v36; // [rsp+30h] [rbp-41h] BYREF
  __int64 v37; // [rsp+38h] [rbp-39h] BYREF
  __int64 v38; // [rsp+40h] [rbp-31h] BYREF
  IInspectable *graphicsSurface; // [rsp+48h] [rbp-29h] BYREF
  IDXGISurface *dgxiSurface; // [rsp+50h] [rbp-21h] BYREF
  struct ID3D11Texture2D *v41; // [rsp+58h] [rbp-19h] BYREF
  char v42[8]; // [rsp+60h] [rbp-11h] BYREF
  _QWORD *p_resetToken; // [rsp+68h] [rbp-9h]
  IMFDXGIDeviceManager **p_ppDeviceManager; // [rsp+70h] [rbp-1h]
  __int64 (__fastcall ***v45)(_QWORD, _QWORD, _QWORD); // [rsp+78h] [rbp+7h]
  IMFDXGIDeviceManager *ppDeviceManager; // [rsp+D0h] [rbp+5Fh] BYREF

  v9 = resetToken;
  v45 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))resetToken;
  if ( resetToken )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*resetToken)[1])(resetToken);
  v36 = 0;
  ppDeviceManager = 0;
  v41 = 0;
  if ( v9 )
  {
    v38 = 0;
    v37 = 0;
    LODWORD(resetToken) = 0;
    v10 = **v9;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v38);
    v11 = v10(v9, &GUID_a9b3d012_3df2_4ee3_b8d1_8695f457d3c1, &v38);
    MF::ThrowIfFailed((MF *)v11, v12);
    v13 = (*(__int64 (__fastcall **)(__int64, GUID *, struct ID3D11Device **))(*(_QWORD *)v38 + 24LL))(
            v38,
            &GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140,
            &v36);
    MF::ThrowIfFailed((MF *)v13, v14);
    v15 = v36;
    QueryInterface = v36->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v37);
    v17 = ((__int64 (__fastcall *)(struct ID3D11Device *, GUID *, __int64 *))QueryInterface)(
            v15,
            &GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0,
            &v37);
    MF::ThrowIfFailed((MF *)v17, v18);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 40LL))(v37, 1);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppDeviceManager);
    v19 = MFCreateDXGIDeviceManager((UINT *)&resetToken, &ppDeviceManager);
    MF::ThrowIfFailed((MF *)v19, v20);
    v21 = ((__int64 (__fastcall *)(IMFDXGIDeviceManager *, struct ID3D11Device *, _QWORD))ppDeviceManager->lpVtbl->ResetDevice)(
            ppDeviceManager,
            v36,
            (unsigned int)resetToken);
    MF::ThrowIfFailed((MF *)v21, v22);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v38);
  }
  else
  {
    resetToken = 0;
    v42[0] = 0;
    p_resetToken = &resetToken;
    p_ppDeviceManager = &ppDeviceManager;
    VideoFrameImpl::GetDXGIDeviceManager(a1, &ppDeviceManager);
    v23 = ((__int64 (__fastcall *)(IMFDXGIDeviceManager *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))ppDeviceManager->lpVtbl->OpenDeviceHandle)(
            ppDeviceManager,
            &resetToken);
    MF::ThrowIfFailed((MF *)v23, v24);
    v25 = ((__int64 (__fastcall *)(IMFDXGIDeviceManager *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), GUID *, struct ID3D11Device **))ppDeviceManager->lpVtbl->GetVideoService)(
            ppDeviceManager,
            resetToken,
            &GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140,
            &v36);
    MF::ThrowIfFailed((MF *)v25, v26);
    ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14___::_ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14___(v42);
  }
  VideoFrameImpl::CreateTexture(a2, a3, a4, v36, &v41);
  dgxiSurface = 0;
  graphicsSurface = 0;
  v27 = Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface>(&v41, &dgxiSurface);
  MF::ThrowIfFailed((MF *)v27, v28);
  v29 = CreateDirect3D11SurfaceFromDXGISurface(dgxiSurface, &graphicsSurface);
  MF::ThrowIfFailed((MF *)v29, v30);
  v31 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>(
          &graphicsSurface,
          (char *)a1 + 184);
  MF::ThrowIfFailed((MF *)v31, v32);
  v33 = ppDeviceManager;
  ppDeviceManager = 0;
  v34 = *((_QWORD *)a1 + 24);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  *((_QWORD *)a1 + 24) = v33;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&graphicsSurface);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&dgxiSurface);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppDeviceManager);
  result = Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v36);
  if ( v9 )
    return ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v9)[2])(v9);
  return result;
}

```

## disassembly

```asm
0x1800371c0  push    rbp
0x1800371c2  push    rbx
0x1800371c3  push    rsi
0x1800371c4  push    rdi
0x1800371c5  push    r12
0x1800371c7  push    r13
0x1800371c9  push    r14
0x1800371cb  push    r15
0x1800371cd  lea     rbp, [rsp-17h]
0x1800371d2  sub     rsp, 88h
0x1800371d9  mov     r15d, r9d
0x1800371dc  mov     r12d, r8d
0x1800371df  mov     r13d, edx
0x1800371e2  mov     r14, rcx
0x1800371e5  mov     rsi, [rbp+4Fh+resetToken]
0x1800371e9  mov     [rbp+4Fh+var_48], rsi
0x1800371ed  xor     edi, edi
0x1800371ef  test    rsi, rsi
0x1800371f2  jz      short loc_180037204
0x1800371f4  mov     rax, [rsi]
0x1800371f7  mov     rcx, rsi
0x1800371fa  mov     rax, [rax+8]
0x1800371fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037203  nop
0x180037204  mov     [rbp+4Fh+var_90], rdi
0x180037208  mov     [rbp+4Fh+ppDeviceManager], rdi
0x18003720c  mov     [rbp+4Fh+var_68], rdi
0x180037210  test    rsi, rsi
0x180037213  jz      loc_18003730D
0x180037219  mov     [rbp+4Fh+var_80], rdi
0x18003721d  mov     [rbp+4Fh+var_88], rdi
0x180037221  mov     dword ptr [rbp+4Fh+resetToken], edi
0x180037224  mov     rax, [rsi]
0x180037227  mov     rbx, [rax]
0x18003722a  lea     rcx, [rbp+4Fh+var_80]
0x18003722e  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037233  lea     r8, [rbp+4Fh+var_80]
0x180037237  lea     rdx, _GUID_a9b3d012_3df2_4ee3_b8d1_8695f457d3c1
0x18003723e  mov     rcx, rsi
0x180037241  mov     rax, rbx
0x180037244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037249  nop
0x18003724a  mov     ecx, eax; this
0x18003724c  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180037251  mov     rcx, [rbp+4Fh+var_80]
0x180037255  mov     rax, [rcx]
0x180037258  lea     r8, [rbp+4Fh+var_90]
0x18003725c  lea     rdx, _GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140
0x180037263  mov     rax, [rax+18h]
0x180037267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003726c  mov     ecx, eax; this
0x18003726e  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180037273  mov     rdi, [rbp+4Fh+var_90]
0x180037277  mov     rax, [rdi]
0x18003727a  mov     rbx, [rax]
0x18003727d  lea     rcx, [rbp+4Fh+var_88]
0x180037281  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037286  lea     r8, [rbp+4Fh+var_88]
0x18003728a  lea     rdx, _GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0
0x180037291  mov     rcx, rdi
0x180037294  mov     rax, rbx
0x180037297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003729c  mov     ecx, eax; this
0x18003729e  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800372a3  mov     rcx, [rbp+4Fh+var_88]
0x1800372a7  mov     rax, [rcx]
0x1800372aa  mov     edx, 1
0x1800372af  mov     rax, [rax+28h]
0x1800372b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372b8  lea     rcx, [rbp+4Fh+ppDeviceManager]
0x1800372bc  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800372c1  lea     rdx, [rbp+4Fh+ppDeviceManager]; ppDeviceManager
0x1800372c5  lea     rcx, [rbp+4Fh+resetToken]; resetToken
0x1800372c9  call    cs:__imp_MFCreateDXGIDeviceManager
0x1800372cf  mov     ecx, eax; this
0x1800372d1  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800372d6  mov     rcx, [rbp+4Fh+ppDeviceManager]
0x1800372da  mov     rax, [rcx]
0x1800372dd  mov     r8d, dword ptr [rbp+4Fh+resetToken]
0x1800372e1  mov     rdx, [rbp+4Fh+var_90]
0x1800372e5  mov     rax, [rax+38h]
0x1800372e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372ee  mov     ecx, eax; this
0x1800372f0  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800372f5  nop
0x1800372f6  lea     rcx, [rbp+4Fh+var_88]
0x1800372fa  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800372ff  nop
0x180037300  lea     rcx, [rbp+4Fh+var_80]
0x180037304  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037309  xor     edi, edi
0x18003730b  jmp     short loc_18003737C
0x18003730d  mov     [rbp+4Fh+resetToken], rdi
0x180037311  mov     [rbp+4Fh+var_60], dil
0x180037315  lea     rax, [rbp+4Fh+resetToken]
0x180037319  mov     [rbp+4Fh+var_58], rax
0x18003731d  lea     rax, [rbp+4Fh+ppDeviceManager]
0x180037321  mov     [rbp+4Fh+var_50], rax
0x180037325  lea     rdx, [rbp+4Fh+ppDeviceManager]; struct IMFDXGIDeviceManager **
0x180037329  mov     rcx, r14; this
0x18003732c  call    ?GetDXGIDeviceManager@VideoFrameImpl@@AEAAXPEAPEAUIMFDXGIDeviceManager@@@Z; VideoFrameImpl::GetDXGIDeviceManager(IMFDXGIDeviceManager * *)
0x180037331  mov     rcx, [rbp+4Fh+ppDeviceManager]
0x180037335  mov     rax, [rcx]
0x180037338  lea     rdx, [rbp+4Fh+resetToken]
0x18003733c  mov     rax, [rax+30h]
0x180037340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037345  mov     ecx, eax; this
0x180037347  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18003734c  mov     rcx, [rbp+4Fh+ppDeviceManager]
0x180037350  mov     rax, [rcx]
0x180037353  lea     r9, [rbp+4Fh+var_90]
0x180037357  lea     r8, _GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140
0x18003735e  mov     rdx, [rbp+4Fh+resetToken]
0x180037362  mov     rax, [rax+20h]
0x180037366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003736b  mov     ecx, eax; this
0x18003736d  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180037372  nop
0x180037373  lea     rcx, [rbp+4Fh+var_60]
0x180037377  call    ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14______ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14___
0x18003737c  lea     rax, [rbp+4Fh+var_68]
0x180037380  mov     [rsp+0C0h+var_A0], rax; struct ID3D11Texture2D **
0x180037385  mov     r9, [rbp+4Fh+var_90]; struct ID3D11Device *
0x180037389  mov     r8d, r15d; int
0x18003738c  mov     edx, r12d; int
0x18003738f  mov     ecx, r13d; enum DXGI_FORMAT
0x180037392  call    ?CreateTexture@VideoFrameImpl@@CAXW4DXGI_FORMAT@@HHPEAUID3D11Device@@PEAPEAUID3D11Texture2D@@@Z; VideoFrameImpl::CreateTexture(DXGI_FORMAT,int,int,ID3D11Device *,ID3D11Texture2D * *)
0x180037397  mov     [rbp+4Fh+dgxiSurface], rdi
0x18003739b  mov     [rbp+4Fh+graphicsSurface], rdi
0x18003739f  lea     rdx, [rbp+4Fh+dgxiSurface]
0x1800373a3  lea     rcx, [rbp+4Fh+var_68]
0x1800373a7  call    ??$As@UIDXGISurface@@@?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGISurface@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Texture2D>::As<IDXGISurface>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGISurface>>)
0x1800373ac  mov     ecx, eax; this
0x1800373ae  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800373b3  lea     rdx, [rbp+4Fh+graphicsSurface]; graphicsSurface
0x1800373b7  mov     rcx, [rbp+4Fh+dgxiSurface]; dgxiSurface
0x1800373bb  call    cs:__imp_CreateDirect3D11SurfaceFromDXGISurface
0x1800373c1  mov     ecx, eax; this
0x1800373c3  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800373c8  lea     rdx, [r14+0B8h]
0x1800373cf  lea     rcx, [rbp+4Fh+graphicsSurface]
0x1800373d3  call    ??$As@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDirect3DSurface@Direct3D11@DirectX@Graphics@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Graphics::DirectX::Direct3D11::IDirect3DSurface>>)
0x1800373d8  mov     ecx, eax; this
0x1800373da  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800373df  mov     rbx, [rbp+4Fh+ppDeviceManager]
0x1800373e3  mov     [rbp+4Fh+ppDeviceManager], rdi
0x1800373e7  mov     rcx, [r14+0C0h]
0x1800373ee  test    rcx, rcx
0x1800373f1  jz      short loc_1800373FF
0x1800373f3  mov     rax, [rcx]
0x1800373f6  mov     rax, [rax+10h]
0x1800373fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373ff  mov     [r14+0C0h], rbx
0x180037406  lea     rcx, [rbp+4Fh+graphicsSurface]
0x18003740a  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18003740f  nop
0x180037410  lea     rcx, [rbp+4Fh+dgxiSurface]
0x180037414  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037419  nop
0x18003741a  lea     rcx, [rbp+4Fh+var_68]
0x18003741e  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037423  nop
0x180037424  lea     rcx, [rbp+4Fh+ppDeviceManager]
0x180037428  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18003742d  nop
0x18003742e  lea     rcx, [rbp+4Fh+var_90]
0x180037432  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037437  nop
0x180037438  test    rsi, rsi
0x18003743b  jz      short loc_18003744D
0x18003743d  mov     rax, [rsi]
0x180037440  mov     rcx, rsi
0x180037443  mov     rax, [rax+10h]
0x180037447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003744c  nop
0x18003744d  add     rsp, 88h
0x180037454  pop     r15
0x180037456  pop     r14
0x180037458  pop     r13
0x18003745a  pop     r12
0x18003745c  pop     rdi
0x18003745d  pop     rsi
0x18003745e  pop     rbx
0x18003745f  pop     rbp
0x180037460  retn
```
