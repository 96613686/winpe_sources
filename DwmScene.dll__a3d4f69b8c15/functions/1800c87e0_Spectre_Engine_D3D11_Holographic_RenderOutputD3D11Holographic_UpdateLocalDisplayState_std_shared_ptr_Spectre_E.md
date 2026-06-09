# Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::UpdateLocalDisplayState(std::shared_ptr<Spectre::Engine::D3D11::Holographic::IHolographicDisplayProvider> const &,std::shared_ptr<Spectre::Engine::D3D11::Holographic::HolographicDisplayState> const &)

- ea: `0x1800c87e0`
- end: `0x1800c9312`
- name: `?UpdateLocalDisplayState@RenderOutputD3D11Holographic@Holographic@D3D11@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VIHolographicDisplayProvider@Holographic@D3D11@Engine@Spectre@@@std@@AEBV?$shared_ptr@UHolographicDisplayState@Holographic@D3D11@Engine@Spectre@@@7@@Z`
- size: `2866`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c8670`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000fe40`
- `0x18001128c`
- `0x1800112c4`
- `0x180011840`
- `0x1800119a0`
- `0x1800125e8`
- `0x180012680`
- `0x180012c58`
- `0x180012df8`
- `0x180013664`
- `0x1800240c4`
- `0x180027150`
- `0x18002b5f4`
- `0x180068288`
- `0x180068c8c`
- `0x1800b62f0`
- `0x1800ba38c`
- `0x1800bbb2c`
- `0x1800bcb18`
- `0x1800c49bc`
- `0x1800c4c20`
- `0x1800c4dfc`
- `0x1800c7944`
- `0x1800c7994`
- `0x1800c84ec`
- `0x1800c87e0`
- `0x1800d1594`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c88e5`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c89e2`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8a5f`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8b03`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8b8c`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8c19`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8d20`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8e3b`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8ed5`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8f63`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c88e5`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c89e2`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8a5f`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8b03`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8b8c`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8c19`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8d20`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8e3b`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8ed5`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800c8f63`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::UpdateLocalDisplayState(
        _QWORD *a1,
        _QWORD *a2,
        __int64 *a3)
{
  _QWORD *v5; // r13
  char v6; // si
  double v7; // xmm0_8
  char v8; // r12
  int v9; // r14d
  int v10; // eax
  ULONG_PTR v11; // rbx
  struct ID3D11DeviceChild **v12; // rcx
  __int64 v13; // rbx
  unsigned int v14; // r14d
  __int64 (__fastcall *v15)(__int64, _QWORD, _DWORD *, __int64); // rsi
  __int64 v16; // rdi
  int v17; // eax
  ULONG_PTR v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, _DWORD *, __int64); // rsi
  __int64 v20; // rdi
  int v21; // eax
  ULONG_PTR v22; // rdi
  int v23; // eax
  ULONG_PTR v24; // rdi
  struct IDXGIObject *v25; // rsi
  HRESULT (__stdcall *GetPrivateData)(IDXGIObject *, const GUID *const, UINT *, void *); // rdi
  int v27; // eax
  ULONG_PTR v28; // rdi
  __int64 v29; // r14
  __int64 (__fastcall *v30)(__int64, struct IDXGIObject *, __int64 *, __int64); // rsi
  __int64 v31; // rdi
  int v32; // eax
  ULONG_PTR v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int128 *, _QWORD, __int64); // rsi
  __int64 v35; // rdi
  int v36; // eax
  ULONG_PTR v37; // rdi
  __int64 v38; // rdi
  int v39; // ecx
  __int64 (__fastcall *v40)(__int64, __int64 *, _QWORD, __int64); // rsi
  int v41; // eax
  ULONG_PTR v42; // rdi
  enum DXGI_FORMAT v43; // r8d
  unsigned int v44; // r9d
  __int64 (__fastcall *v45)(__int64, _QWORD, _DWORD *, __int64); // rsi
  __int64 v46; // rdi
  int v47; // eax
  ULONG_PTR v48; // rdi
  __int64 (__fastcall *v49)(__int64, _QWORD, _DWORD *, __int64); // rsi
  __int64 v50; // rdi
  int v51; // eax
  ULONG_PTR v52; // rbx
  __int64 v53; // rax
  __int64 v54; // r14
  _QWORD *v55; // rax
  __int64 v56; // rbx
  _QWORD *v57; // r12
  int v58; // r13d
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // rbx
  _QWORD *v63; // r12
  __int64 v64; // rsi
  _QWORD *v65; // rcx
  __int64 v66; // rax
  __int64 v67; // r9
  __int64 v68; // rax
  __int64 v69; // rcx
  unsigned int v70; // [rsp+28h] [rbp-E0h]
  unsigned int v71; // [rsp+30h] [rbp-D8h]
  unsigned int v72; // [rsp+38h] [rbp-D0h]
  char v73; // [rsp+48h] [rbp-C0h]
  char v74; // [rsp+49h] [rbp-BFh]
  struct IDXGIObject *v75; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v76; // [rsp+58h] [rbp-B0h]
  __int64 v77; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v78; // [rsp+68h] [rbp-A0h] BYREF
  struct IDXGIObject *v79[2]; // [rsp+70h] [rbp-98h] BYREF
  struct ID3D11DeviceChild *v80; // [rsp+80h] [rbp-88h] BYREF
  __int64 v81; // [rsp+88h] [rbp-80h] BYREF
  _DWORD v82[2]; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v83; // [rsp+98h] [rbp-70h]
  int v84; // [rsp+A0h] [rbp-68h]
  int v85; // [rsp+A4h] [rbp-64h]
  __int64 v86; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD *v87; // [rsp+B0h] [rbp-58h] BYREF
  std::_Ref_count_base *v88; // [rsp+B8h] [rbp-50h]
  __int64 v89; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v90; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v91; // [rsp+D0h] [rbp-38h] BYREF
  std::_Ref_count_base *v92; // [rsp+D8h] [rbp-30h]
  __int64 v93; // [rsp+E0h] [rbp-28h] BYREF
  std::_Ref_count_base *v94; // [rsp+E8h] [rbp-20h]
  _QWORD v95[2]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v96; // [rsp+110h] [rbp+8h] BYREF
  std::_Ref_count_base *v97; // [rsp+118h] [rbp+10h]
  EXCEPTION_RECORD pExceptionRecord; // [rsp+128h] [rbp+20h] BYREF
  __int64 v99; // [rsp+1C8h] [rbp+C0h] BYREF
  std::_Ref_count_base *v100; // [rsp+1D0h] [rbp+C8h]
  __int128 v101; // [rsp+1D8h] [rbp+D0h]
  __int64 v102; // [rsp+1E8h] [rbp+E0h]
  int v103; // [rsp+1F0h] [rbp+E8h]
  __int128 v104; // [rsp+1F8h] [rbp+F0h] BYREF
  _BYTE v105[20]; // [rsp+208h] [rbp+100h]
  __int64 v106; // [rsp+21Ch] [rbp+114h]
  _OWORD v107[3]; // [rsp+228h] [rbp+120h] BYREF
  void *retaddr; // [rsp+2B0h] [rbp+1A8h]

  v78 = a2;
  v5 = a1;
  v87 = a1;
  v6 = 0;
  Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::GetRendererD3D11(a1, &v96);
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(v96, &v90);
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 32LL))(*a2, &v81);
  v7 = (*(double (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 8LL))(*a2);
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  v74 = v8;
  v9 = (v8 != 0) + 1;
  LODWORD(v76) = v9;
  *(_BYTE *)(*a3 + 1) = v8;
  v80 = 0;
  v10 = Microsoft::WRL::ComPtr<ID3D11Resource>::As<ID3D11Texture2D>(&v81, &v80);
  v11 = v10;
  if ( v10 < 0 )
  {
    memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
    pExceptionRecord.ExceptionCode = -532265403;
    pExceptionRecord.ExceptionAddress = retaddr;
    pExceptionRecord.NumberParameters = 1;
    pExceptionRecord.ExceptionInformation[0] = v11;
    RaiseFailFastException(&pExceptionRecord, 0, 0);
  }
  D3D11_SetDebugName(v80, "CameraBackBuffer");
  v73 = 0;
  v12 = (struct ID3D11DeviceChild **)(*a3 + 8);
  v13 = v90;
  if ( *v12 != v80 )
  {
    Microsoft::WRL::ComPtr<ID3D11Texture2D>::operator=(v12, &v80);
    memset(v107, 0, 44);
    (*(void (__fastcall **)(_QWORD, _OWORD *))(**(_QWORD **)(*a3 + 8) + 80LL))(*(_QWORD *)(*a3 + 8), v107);
    v14 = v107[1];
    v82[1] = (v8 != 0) + 4;
    v83 = 0;
    v84 = 1;
    v82[0] = v107[1];
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64))(*(_QWORD *)v13 + 72LL);
    v16 = *a3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 48);
    v17 = v15(v13, *(_QWORD *)(*a3 + 8), v82, v16 + 48);
    v18 = v17;
    if ( v17 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v18;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    if ( v8 )
    {
      HIDWORD(v83) = 1;
      v19 = *(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64))(*(_QWORD *)v13 + 72LL);
      v20 = *a3;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 96);
      v21 = v19(v13, *(_QWORD *)(*a3 + 8), v82, v20 + 96);
      v22 = v21;
      if ( v21 < 0 )
      {
        memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
        pExceptionRecord.ExceptionCode = -532265403;
        pExceptionRecord.ExceptionAddress = retaddr;
        pExceptionRecord.NumberParameters = 1;
        pExceptionRecord.ExceptionInformation[0] = v22;
        RaiseFailFastException(&pExceptionRecord, 0, 0);
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<ID3D11DepthStencilView>::operator=(*a3 + 96, *a3 + 48);
    }
    v93 = v14 | 0x100000000LL;
    v99 = v93;
    LODWORD(v100) = LODWORD(v7);
    HIDWORD(v100) = LODWORD(v7);
    v101 = 3u;
    v79[0] = 0;
    v23 = Microsoft::WRL::ComPtr<ID3D11Resource>::As<IDXGIResource1>(&v81, v79);
    v24 = v23;
    if ( v23 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v24;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    D3D11_SetDebugName(v79[0], "DxgiBackBuffer");
    v75 = 0;
    v25 = v79[0];
    GetPrivateData = v79[0]->lpVtbl[1].GetPrivateData;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    v27 = ((__int64 (__fastcall *)(struct IDXGIObject *, bool, struct IDXGIObject **))GetPrivateData)(
            v25,
            v8 != 0,
            &v75);
    v28 = v27;
    if ( v27 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v28;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    D3D11_SetDebugName(v75, "DxgiSurface");
    v29 = v5[66];
    v30 = *(__int64 (__fastcall **)(__int64, struct IDXGIObject *, __int64 *, __int64))(*(_QWORD *)v29 + 496LL);
    v31 = *a3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 32);
    v32 = v30(v29, v75, &v99, v31 + 32);
    v33 = v32;
    if ( v32 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v33;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v5[66] + 592LL))(v5[66], *(_QWORD *)(*a3 + 32));
    *(_QWORD *)(*a3 + 40) = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v78 + 24LL))(*v78, v95);
    v104 = v107[0];
    *(_OWORD *)v105 = v107[1];
    *(_QWORD *)&v105[12] = 3;
    v106 = 0x20000;
    HIDWORD(v104) = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 16);
    v34 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int64))(*(_QWORD *)v13 + 40LL);
    v35 = *a3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 16);
    v36 = v34(v13, &v104, 0, v35 + 16);
    v37 = v36;
    v6 = 0;
    if ( v36 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v37;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 16), "BackBufferStaging");
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 56);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 104);
    v73 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v79);
    v9 = v76;
  }
  v38 = *a3;
  if ( !*(_QWORD *)(*a3 + 56) || !*(_QWORD *)(v38 + 104) )
  {
    v39 = *(_DWORD *)(v38 + 44);
    LODWORD(v99) = *(_DWORD *)(v38 + 40);
    HIDWORD(v99) = v39;
    LODWORD(v100) = 1;
    HIDWORD(v100) = v9;
    LODWORD(v101) = 55;
    *(_QWORD *)((char *)&v101 + 4) = 1;
    HIDWORD(v101) = 0;
    v102 = 64;
    v103 = 0;
    v40 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, __int64))(*(_QWORD *)v13 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v38 + 24);
    v41 = v40(v13, &v99, 0, v38 + 24);
    v42 = v41;
    if ( v41 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v42;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 24), "BackBuffer_DepthStencilTexture");
    CD3D11_DEPTH_STENCIL_VIEW_DESC::CD3D11_DEPTH_STENCIL_VIEW_DESC(
      (CD3D11_DEPTH_STENCIL_VIEW_DESC *)v82,
      (enum D3D11_DSV_DIMENSION)((v8 != 0) + 3),
      v43,
      v44,
      v70,
      v71,
      v72);
    v85 = 1;
    v45 = *(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64))(*(_QWORD *)v13 + 80LL);
    v46 = *a3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 56);
    v47 = v45(v13, *(_QWORD *)(*a3 + 24), v82, v46 + 56);
    v48 = v47;
    if ( v47 < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v48;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 56), "BackBuffer_DepthStencilView_LeftEye");
    if ( v8 )
    {
      v84 = 1;
      v49 = *(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64))(*(_QWORD *)v13 + 80LL);
      v50 = *a3;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*a3 + 104);
      v51 = v49(v13, *(_QWORD *)(*a3 + 24), v82, v50 + 104);
      v52 = v51;
      if ( v51 < 0 )
      {
        memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
        pExceptionRecord.ExceptionCode = -532265403;
        pExceptionRecord.ExceptionAddress = retaddr;
        pExceptionRecord.NumberParameters = 1;
        pExceptionRecord.ExceptionInformation[0] = v52;
        RaiseFailFastException(&pExceptionRecord, 0, 0);
      }
      D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 104), "BackBuffer_DepthStencilView_RightEye");
    }
    else
    {
      Microsoft::WRL::ComPtr<ID3D11DepthStencilView>::operator=(*a3 + 104, *a3 + 56);
    }
    v6 = 1;
  }
  v53 = (*(__int64 (__fastcall **)(_QWORD *, _DWORD *))(*v5 + 376LL))(v5, v82);
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v53, &v99);
  if ( v83 )
    std::_Ref_count_base::_Decwref(v83);
  v54 = v99;
  v55 = *(_QWORD **)(v99 + 3984);
  v78 = v55;
  if ( v73 )
  {
    v56 = 0;
    v57 = v55;
    v58 = v76;
    do
    {
      Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::DeviceFrameBuffer>(v54, &v93);
      v95[0] = _RTDynamicCast_0(
                 v93,
                 0,
                 &Spectre::Engine::DeviceFrameBuffer `RTTI Type Descriptor',
                 &Spectre::Engine::D3D11::RenderTargetD3D11 `RTTI Type Descriptor',
                 1);
      v59 = *a3;
      LODWORD(v79[0]) = *(_DWORD *)(*a3 + 44);
      LODWORD(v75) = *(_DWORD *)(v59 + 40);
      v86 = *(_QWORD *)(v59 + 16);
      Microsoft::WRL::ComPtr<ID3D11ShaderResourceView>::InternalAddRef(&v86);
      v77 = *(_QWORD *)(*a3 + 8);
      Microsoft::WRL::ComPtr<ID3D11ShaderResourceView>::InternalAddRef(&v77);
      v60 = *(_QWORD *)(*a3 + 48 * v56 + 48);
      v89 = v60;
      if ( v60 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 8LL))(v60);
      Spectre::Engine::D3D11::RenderTargetD3D11::Create(
        v95[0],
        (unsigned int)&v89,
        (unsigned int)&v77,
        (unsigned int)&v86,
        (_DWORD)v75,
        v79[0]);
      Spectre::Engine::Engine::CreateResource<Spectre::Engine::FrameBuffer,>(v57, &v91);
      Spectre::Engine::FrameBuffer::Create(v91, &v93);
      std::shared_ptr<Spectre::Engine::Light>::operator=(48 * v56 + *a3 + 64, &v91);
      if ( v92 )
        std::_Ref_count_base::_Decref(v92);
      if ( v94 )
        std::_Ref_count_base::_Decref(v94);
      v56 = (unsigned int)(v56 + 1);
    }
    while ( (int)v56 < v58 );
    v5 = v87;
    if ( !v74 )
      std::shared_ptr<Spectre::Engine::Light>::operator=(*a3 + 64, *a3 + 112);
    (*(void (__fastcall **)(_QWORD *))(*v5 + 56LL))(v5);
    LOBYTE(v61) = 1;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v5 + 360LL))(v5, v61);
  }
  if ( v6 )
  {
    v62 = 0;
    v63 = v78;
    do
    {
      Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::DeviceDepthBuffer>(v54, &v93);
      v64 = _RTDynamicCast_0(
              v93,
              0,
              &Spectre::Engine::DeviceDepthBuffer `RTTI Type Descriptor',
              &Spectre::Engine::D3D11::DepthBufferD3D11 `RTTI Type Descriptor',
              1);
      v77 = *(_QWORD *)(*a3 + 24);
      Microsoft::WRL::ComPtr<ID3D11ShaderResourceView>::InternalAddRef(&v77);
      v65 = *(_QWORD **)(*a3 + 48 * v62 + 56);
      v78 = v65;
      if ( v65 )
        (*(void (__fastcall **)(_QWORD *))(*v65 + 8LL))(v65);
      Spectre::Engine::D3D11::DepthBufferD3D11::Create(v64, &v78, &v77);
      Spectre::Engine::Engine::CreateResource<Spectre::Engine::DepthBuffer,>(v63, &v87);
      v66 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
              &v91,
              &v93);
      Spectre::Engine::DepthBuffer::Create(v67, v66, 5);
      v68 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
              v95,
              &v87);
      Spectre::Engine::RenderOutput::SetDepthBuffer(v5, v68);
      std::shared_ptr<Spectre::Engine::Light>::operator=(48 * v62 + *a3 + 80, &v87);
      if ( v88 )
        std::_Ref_count_base::_Decref(v88);
      if ( v94 )
        std::_Ref_count_base::_Decref(v94);
      v62 = (unsigned int)(v62 + 1);
    }
    while ( (int)v62 < (int)v76 );
    if ( !v74 )
      std::shared_ptr<Spectre::Engine::Light>::operator=(*a3 + 80, *a3 + 128);
  }
  if ( v100 )
    std::_Ref_count_base::_Decref(v100);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
  v69 = v81;
  if ( v81 )
  {
    v81 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
  if ( v97 )
    std::_Ref_count_base::_Decref(v97);
}

```

## disassembly

```asm
0x1800c87e0  mov     rax, rsp
0x1800c87e3  mov     [rax+20h], rbx
0x1800c87e7  push    rbp
0x1800c87e8  push    rsi
0x1800c87e9  push    rdi
0x1800c87ea  push    r12
0x1800c87ec  push    r13
0x1800c87ee  push    r14
0x1800c87f0  push    r15
0x1800c87f2  lea     rbp, [rax-1A8h]
0x1800c87f9  sub     rsp, 270h
0x1800c8800  movaps  xmmword ptr [rax-48h], xmm6
0x1800c8804  mov     rax, cs:__security_cookie
0x1800c880b  xor     rax, rsp
0x1800c880e  mov     [rbp+1A0h+var_50], rax
0x1800c8815  mov     r15, r8
0x1800c8818  mov     rbx, rdx
0x1800c881b  mov     [rsp+2A0h+var_240], rdx
0x1800c8820  mov     r13, rcx
0x1800c8823  mov     [rbp+1A0h+var_1F8], rcx
0x1800c8827  xor     esi, esi
0x1800c8829  lea     rdx, [rbp+1A0h+var_198]
0x1800c882d  call    ?GetRendererD3D11@RenderOutputD3D11Holographic@Holographic@D3D11@Engine@Spectre@@AEBA?AV?$shared_ptr@VRenderDeviceD3D11@D3D11@Engine@Spectre@@@std@@XZ; Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::GetRendererD3D11(void)
0x1800c8832  nop
0x1800c8833  lea     rdx, [rbp+1A0h+var_1E0]
0x1800c8837  mov     rcx, [rbp+1A0h+var_198]
0x1800c883b  call    ?GetDevice@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(void)
0x1800c8840  nop
0x1800c8841  mov     rcx, [rbx]
0x1800c8844  mov     rax, [rcx]
0x1800c8847  lea     rdx, [rbp+1A0h+var_220]
0x1800c884b  mov     rax, [rax+20h]
0x1800c884f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8854  nop
0x1800c8855  mov     rcx, [rbx]
0x1800c8858  mov     rax, [rcx]
0x1800c885b  mov     rax, [rax+8]
0x1800c885f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8864  movaps  xmm6, xmm0
0x1800c8867  mov     rcx, [rbx]
0x1800c886a  mov     rax, [rcx]
0x1800c886d  mov     rax, [rax+10h]
0x1800c8871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8876  mov     r12b, al
0x1800c8879  mov     byte ptr [rsp+2A0h+var_260+1], al
0x1800c887d  mov     cl, al
0x1800c887f  neg     cl
0x1800c8881  sbb     r14d, r14d
0x1800c8884  neg     r14d
0x1800c8887  lea     edi, [rsi+1]
0x1800c888a  add     r14d, edi
0x1800c888d  mov     dword ptr [rsp+2A0h+var_250], r14d
0x1800c8892  mov     rcx, [r15]
0x1800c8895  mov     [rcx+1], al
0x1800c8898  mov     [rsp+2A0h+var_228], rsi
0x1800c889d  lea     rdx, [rsp+2A0h+var_228]
0x1800c88a2  lea     rcx, [rbp+1A0h+var_220]
0x1800c88a6  call    ??$As@UID3D11Texture2D@@@?$ComPtr@UID3D11Resource@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Resource>::As<ID3D11Texture2D>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D11Texture2D>>)
0x1800c88ab  movsxd  rbx, eax
0x1800c88ae  test    eax, eax
0x1800c88b0  jns     short loc_1800C88EB
0x1800c88b2  xor     edx, edx; Val
0x1800c88b4  mov     r8d, 98h; Size
0x1800c88ba  lea     rcx, [rbp+1A0h+pExceptionRecord]; void *
0x1800c88be  call    memset_0
0x1800c88c3  mov     [rbp+1A0h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800c88ca  mov     rcx, [rbp+1A8h]
0x1800c88d1  mov     [rbp+1A0h+pExceptionRecord.ExceptionAddress], rcx
0x1800c88d5  mov     [rbp+1A0h+pExceptionRecord.NumberParameters], edi
0x1800c88d8  mov     [rbp+1A0h+pExceptionRecord.ExceptionInformation], rbx
0x1800c88dc  xor     r8d, r8d; dwFlags
0x1800c88df  xor     edx, edx; pContextRecord
0x1800c88e1  lea     rcx, [rbp+1A0h+pExceptionRecord]; pExceptionRecord
0x1800c88e5  call    cs:__imp_RaiseFailFastException
0x1800c88eb  lea     rdx, aCamerabackbuff; "CameraBackBuffer"
0x1800c88f2  mov     rcx, [rsp+2A0h+var_228]; struct ID3D11DeviceChild *
0x1800c88f7  call    ?D3D11_SetDebugName@@YAXPEAUID3D11DeviceChild@@PEBD@Z; D3D11_SetDebugName(ID3D11DeviceChild *,char const *)
0x1800c88fc  mov     byte ptr [rsp+2A0h+var_260], sil
0x1800c8901  mov     rcx, [r15]
0x1800c8904  add     rcx, 8
0x1800c8908  mov     rbx, [rbp+1A0h+var_1E0]
0x1800c890c  mov     rax, [rsp+2A0h+var_228]
0x1800c8911  cmp     [rcx], rax
0x1800c8914  jz      loc_1800C8D70
0x1800c891a  lea     rdx, [rsp+2A0h+var_228]
0x1800c891f  call    ??4?$ComPtr@UID3D11Texture2D@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D11Texture2D>::operator=(Microsoft::WRL::ComPtr<ID3D11Texture2D> const &)
0x1800c8924  xorps   xmm0, xmm0
0x1800c8927  movups  [rbp+1A0h+var_80], xmm0
0x1800c892e  movups  xmmword ptr [rbp+1A0h+var_70], xmm0
0x1800c8935  movups  xmmword ptr [rbp+1A0h+var_70+0Ch], xmm0
0x1800c893c  mov     rax, [r15]
0x1800c893f  mov     rcx, [rax+8]
0x1800c8943  mov     rax, [rcx]
0x1800c8946  lea     rdx, [rbp+1A0h+var_80]
0x1800c894d  mov     rax, [rax+50h]
0x1800c8951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8956  mov     r14d, dword ptr [rbp+1A0h+var_70]
0x1800c895d  mov     al, r12b
0x1800c8960  neg     al
0x1800c8962  sbb     ecx, ecx
0x1800c8964  neg     ecx
0x1800c8966  add     ecx, 4
0x1800c8969  mov     [rbp+1A0h+var_214], ecx
0x1800c896c  mov     [rbp+1A0h+var_210], rsi
0x1800c8970  mov     [rbp+1A0h+var_208], edi
0x1800c8973  mov     [rbp+1A0h+var_218], r14d
0x1800c8977  mov     rax, [rbx]
0x1800c897a  mov     rsi, [rax+48h]
0x1800c897e  mov     rdi, [r15]
0x1800c8981  lea     rcx, [rdi+30h]
0x1800c8985  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c898a  mov     rdx, [r15]
0x1800c898d  lea     r9, [rdi+30h]
0x1800c8991  lea     r8, [rbp+1A0h+var_218]
0x1800c8995  mov     rdx, [rdx+8]
0x1800c8999  mov     rcx, rbx
0x1800c899c  mov     rax, rsi
0x1800c899f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c89a4  movsxd  rdi, eax
0x1800c89a7  test    eax, eax
0x1800c89a9  jns     short loc_1800C89E8
0x1800c89ab  xor     edx, edx; Val
0x1800c89ad  mov     r8d, 98h; Size
0x1800c89b3  lea     rcx, [rbp+1A0h+pExceptionRecord]; void *
0x1800c89b7  call    memset_0
0x1800c89bc  mov     [rbp+1A0h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800c89c3  mov     rcx, [rbp+1A8h]
0x1800c89ca  mov     [rbp+1A0h+pExceptionRecord.ExceptionAddress], rcx
0x1800c89ce  mov     [rbp+1A0h+pExceptionRecord.NumberParameters], 1
0x1800c89d5  mov     [rbp+1A0h+pExceptionRecord.ExceptionInformation], rdi
0x1800c89d9  xor     r8d, r8d; dwFlags
0x1800c89dc  xor     edx, edx; pContextRecord
0x1800c89de  lea     rcx, [rbp+1A0h+pExceptionRecord]; pExceptionRecord
0x1800c89e2  call    cs:__imp_RaiseFailFastException
0x1800c89e8  test    r12b, r12b
0x1800c89eb  jz      short loc_1800C8A67
0x1800c89ed  mov     dword ptr [rbp+1A0h+var_210+4], 1
0x1800c89f4  mov     rax, [rbx]
0x1800c89f7  mov     rsi, [rax+48h]
0x1800c89fb  mov     rdi, [r15]
0x1800c89fe  lea     rcx, [rdi+60h]
0x1800c8a02  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8a07  mov     rdx, [r15]
0x1800c8a0a  lea     r9, [rdi+60h]
0x1800c8a0e  lea     r8, [rbp+1A0h+var_218]
0x1800c8a12  mov     rdx, [rdx+8]
0x1800c8a16  mov     rcx, rbx
0x1800c8a19  mov     rax, rsi
0x1800c8a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8a21  movsxd  rdi, eax
0x1800c8a24  test    eax, eax
0x1800c8a26  jns     short loc_1800C8A77
0x1800c8a28  xor     edx, edx; Val
0x1800c8a2a  mov     r8d, 98h; Size
0x1800c8a30  lea     rcx, [rbp+1A0h+pExceptionRecord]; void *
0x1800c8a34  call    memset_0
0x1800c8a39  mov     [rbp+1A0h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800c8a40  mov     rcx, [rbp+1A8h]
0x1800c8a47  mov     [rbp+1A0h+pExceptionRecord.ExceptionAddress], rcx
0x1800c8a4b  mov     [rbp+1A0h+pExceptionRecord.NumberParameters], 1
0x1800c8a52  mov     [rbp+1A0h+pExceptionRecord.ExceptionInformation], rdi
0x1800c8a56  xor     r8d, r8d; dwFlags
0x1800c8a59  xor     edx, edx; pContextRecord
0x1800c8a5b  lea     rcx, [rbp+1A0h+pExceptionRecord]; pExceptionRecord
0x1800c8a5f  call    cs:__imp_RaiseFailFastException
0x1800c8a65  jmp     short loc_1800C8A77
0x1800c8a67  mov     rdx, [r15]
0x1800c8a6a  add     rdx, 30h ; '0'
0x1800c8a6e  lea     rcx, [rdx+30h]
0x1800c8a72  call    ??4?$ComPtr@UID3D11DepthStencilView@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D11DepthStencilView>::operator=(Microsoft::WRL::ComPtr<ID3D11DepthStencilView> const &)
0x1800c8a77  mov     dword ptr [rbp+1A0h+var_1C8], r14d
0x1800c8a7b  mov     dword ptr [rbp+1A0h+var_1C8+4], 1
0x1800c8a82  mov     rax, [rbp+1A0h+var_1C8]
0x1800c8a86  mov     [rbp+1A0h+var_E0], rax
0x1800c8a8d  movss   dword ptr [rbp+1A0h+var_D8], xmm6
0x1800c8a95  movss   dword ptr [rbp+1A0h+var_D8+4], xmm6
0x1800c8a9d  mov     [rbp+1A0h+var_D0], 3
0x1800c8aa8  xor     r14d, r14d
0x1800c8aab  mov     [rbp+1A0h+var_C8], r14
0x1800c8ab2  mov     [rsp+2A0h+var_238], r14
0x1800c8ab7  lea     rdx, [rsp+2A0h+var_238]
0x1800c8abc  lea     rcx, [rbp+1A0h+var_220]
0x1800c8ac0  call    ??$As@UIDXGIResource1@@@?$ComPtr@UID3D11Resource@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGIResource1@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Resource>::As<IDXGIResource1>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGIResource1>>)
0x1800c8ac5  movsxd  rdi, eax
0x1800c8ac8  test    eax, eax
0x1800c8aca  jns     short loc_1800C8B09
0x1800c8acc  xor     edx, edx; Val
0x1800c8ace  mov     r8d, 98h; Size
0x1800c8ad4  lea     rcx, [rbp+1A0h+pExceptionRecord]; void *
0x1800c8ad8  call    memset_0
0x1800c8add  mov     [rbp+1A0h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800c8ae4  mov     rcx, [rbp+1A8h]
0x1800c8aeb  mov     [rbp+1A0h+pExceptionRecord.ExceptionAddress], rcx
0x1800c8aef  mov     [rbp+1A0h+pExceptionRecord.NumberParameters], 1
0x1800c8af6  mov     [rbp+1A0h+pExceptionRecord.ExceptionInformation], rdi
0x1800c8afa  xor     r8d, r8d; dwFlags
0x1800c8afd  xor     edx, edx; pContextRecord
0x1800c8aff  lea     rcx, [rbp+1A0h+pExceptionRecord]; pExceptionRecord
0x1800c8b03  call    cs:__imp_RaiseFailFastException
0x1800c8b09  lea     rdx, aDxgibackbuffer; "DxgiBackBuffer"
0x1800c8b10  mov     rcx, [rsp+2A0h+var_238]; struct IDXGIObject *
0x1800c8b15  call    ?D3D11_SetDebugName@@YAXPEAUIDXGIObject@@PEBD@Z; D3D11_SetDebugName(IDXGIObject *,char const *)
0x1800c8b1a  mov     [rsp+2A0h+var_258], r14
0x1800c8b1f  mov     rsi, [rsp+2A0h+var_238]
0x1800c8b24  mov     rax, [rsi]
0x1800c8b27  mov     rdi, [rax+60h]
0x1800c8b2b  lea     rcx, [rsp+2A0h+var_258]
0x1800c8b30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8b35  mov     edx, r14d
0x1800c8b38  test    r12b, r12b
0x1800c8b3b  setnz   dl
0x1800c8b3e  lea     r8, [rsp+2A0h+var_258]
0x1800c8b43  mov     rcx, rsi
0x1800c8b46  mov     rax, rdi
0x1800c8b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8b4e  movsxd  rdi, eax
0x1800c8b51  test    eax, eax
0x1800c8b53  jns     short loc_1800C8B92
0x1800c8b55  xor     edx, edx; Val
0x1800c8b57  mov     r8d, 98h; Size
0x1800c8b5d  lea     rcx, [rbp+1A0h+pExceptionRecord]; void *
0x1800c8b61  call    memset_0
0x1800c8b66  mov     [rbp+1A0h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800c8b6d  mov     rcx, [rbp+1A8h]
0x1800c8b74  mov     [rbp+1A0h+pExceptionRecord.ExceptionAddress], rcx
0x1800c8b78  mov     [rbp+1A0h+pExceptionRecord.NumberParameters], 1
0x1800c8b7f  mov     [rbp+1A0h+pExceptionRecord.ExceptionInformation], rdi
0x1800c8b83  xor     r8d, r8d; dwFlags
0x1800c8b86  xor     edx, edx; pContextRecord
0x1800c8b88  lea     rcx, [rbp+1A0h+pExceptionRecord]; pExceptionRecord
0x1800c8b8c  call    cs:__imp_RaiseFailFastException
0x1800c8b92  lea     rdx, aDxgisurface; "DxgiSurface"
0x1800c8b99  mov     rcx, [rsp+2A0h+var_258]; struct IDXGIObject *
0x1800c8b9e  call    ?D3D11_SetDebugName@@YAXPEAUIDXGIObject@@PEBD@Z; D3D11_SetDebugName(IDXGIObject *,char const *)
0x1800c8ba3  mov     r14, [r13+210h]
0x1800c8baa  mov     rax, [r14]
0x1800c8bad  mov     rsi, [rax+1F0h]
0x1800c8bb4  mov     rdi, [r15]
0x1800c8bb7  lea     rcx, [rdi+20h]
0x1800c8bbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8bc0  lea     r9, [rdi+20h]
0x1800c8bc4  lea     r8, [rbp+1A0h+var_E0]
0x1800c8bcb  mov     rdx, [rsp+2A0h+var_258]
0x1800c8bd0  mov     rcx, r14
0x1800c8bd3  mov     rax, rsi
0x1800c8bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8bdb  movsxd  rdi, eax
0x1800c8bde  test    eax, eax
0x1800c8be0  jns     short loc_1800C8C1F
0x1800c8be2  xor     edx, edx; Val
0x1800c8be4  mov     r8d, 98h; Size
0x1800c8bea  lea     rcx, [rbp+1A0h+pExceptionRecord]; void *
0x1800c8bee  call    memset_0
0x1800c8bf3  mov     [rbp+1A0h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800c8bfa  mov     rcx, [rbp+1A8h]
0x1800c8c01  mov     [rbp+1A0h+pExceptionRecord.ExceptionAddress], rcx
0x1800c8c05  mov     [rbp+1A0h+pExceptionRecord.NumberParameters], 1
0x1800c8c0c  mov     [rbp+1A0h+pExceptionRecord.ExceptionInformation], rdi
0x1800c8c10  xor     r8d, r8d; dwFlags
0x1800c8c13  xor     edx, edx; pContextRecord
0x1800c8c15  lea     rcx, [rbp+1A0h+pExceptionRecord]; pExceptionRecord
0x1800c8c19  call    cs:__imp_RaiseFailFastException
0x1800c8c1f  mov     rcx, [r13+210h]
0x1800c8c26  mov     rax, [rcx]
0x1800c8c29  mov     rdx, [r15]
0x1800c8c2c  mov     rdx, [rdx+20h]
0x1800c8c30  mov     rax, [rax+250h]
0x1800c8c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8c3c  mov     rax, [rsp+2A0h+var_240]
0x1800c8c41  mov     rcx, [rax]
0x1800c8c44  mov     rax, [rcx]
0x1800c8c47  lea     rdx, [rbp+1A0h+var_1A8]
0x1800c8c4b  mov     rax, [rax+18h]
0x1800c8c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8c54  mov     rcx, [r15]
0x1800c8c57  mov     rax, [rax]
0x1800c8c5a  mov     [rcx+28h], rax
0x1800c8c5e  movups  xmm0, [rbp+1A0h+var_80]
0x1800c8c65  movups  [rbp+1A0h+var_B0], xmm0
0x1800c8c6c  movups  xmm1, xmmword ptr [rbp+1A0h+var_70]
0x1800c8c73  movups  xmmword ptr [rbp+1A0h+var_A0], xmm1
0x1800c8c7a  movups  xmm0, xmmword ptr [rbp+1A0h+var_70+0Ch]
0x1800c8c81  movups  xmmword ptr [rbp+1A0h+var_A0+0Ch], xmm0
0x1800c8c88  mov     qword ptr [rbp+1A0h+var_A0+0Ch], 3
0x1800c8c93  mov     [rbp+1A0h+var_8C], 20000h
0x1800c8c9e  mov     dword ptr [rbp+1A0h+var_B0+0Ch], 1
0x1800c8ca8  mov     rcx, [r15]
0x1800c8cab  add     rcx, 10h
0x1800c8caf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8cb4  mov     rax, [rbx]
0x1800c8cb7  mov     rsi, [rax+28h]
0x1800c8cbb  mov     rdi, [r15]
0x1800c8cbe  lea     rcx, [rdi+10h]
0x1800c8cc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8cc7  lea     r9, [rdi+10h]
0x1800c8ccb  xor     r8d, r8d
0x1800c8cce  lea     rdx, [rbp+1A0h+var_B0]
0x1800c8cd5  mov     rcx, rbx
0x1800c8cd8  mov     rax, rsi
0x1800c8cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
