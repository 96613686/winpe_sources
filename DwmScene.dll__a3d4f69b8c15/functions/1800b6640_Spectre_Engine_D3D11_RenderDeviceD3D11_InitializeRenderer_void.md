# Spectre::Engine::D3D11::RenderDeviceD3D11::InitializeRenderer(void)

- ea: `0x1800b6640`
- end: `0x1800b7199`
- name: `?InitializeRenderer@RenderDeviceD3D11@D3D11@Engine@Spectre@@MEAAXXZ`
- size: `2905`
- prototype: `void __fastcall(Spectre::Engine::D3D11::RenderDeviceD3D11 *__hidden this)`
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000fe40`
- `0x18001128c`
- `0x180011f64`
- `0x1800121f4`
- `0x1800125e8`
- `0x180012ba8`
- `0x180012df8`
- `0x1800142d0`
- `0x180014a3c`
- `0x1800182e8`
- `0x180018318`
- `0x18001daf4`
- `0x18001e1b0`
- `0x18001f250`
- `0x180020130`
- `0x180023e98`
- `0x180026100`
- `0x180027ea4`
- `0x18002866c`
- `0x18002c374`
- `0x18002c8dc`
- `0x18002f730`
- `0x180030ca0`
- `0x180040b80`
- `0x180054cc8`
- `0x180055140`
- `0x18007eca0`
- `0x1800b3834`
- `0x1800b3870`
- `0x1800b3954`
- `0x1800b39a4`
- `0x1800b4888`
- `0x1800b617c`
- `0x1800b6640`
- `0x1800b792c`
- `0x1800b8e60`
- `0x1800c9814`
- `0x1800c9854`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b6866`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b6b82`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b6866`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b6b82`
- `d3d11!D3D11CreateDevice` at `0x1800b6d44`
- `d3d11!D3D11CreateDevice` at `0x1800b6da9`
- `d3d11!D3D11CreateDevice` at `0x1800b6d44`
- `d3d11!D3D11CreateDevice` at `0x1800b6da9`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall Spectre::Engine::D3D11::RenderDeviceD3D11::InitializeRenderer(
        Spectre::Engine::D3D11::RenderDeviceD3D11 *this)
{
  struct ID3D11DeviceChild *v2; // rbx
  struct ID3D11DeviceChild **v3; // rdi
  struct ID3D11DeviceChild *v4; // rsi
  ULONG (__stdcall *AddRef)(ID3D11DeviceChild *); // rbx
  struct ID3D11DeviceChild **v6; // r15
  struct ID3D11DeviceChild *v7; // rsi
  HRESULT (__stdcall *QueryInterface)(ID3D11DeviceChild *, const IID *const, void **); // rbx
  struct ID3D11DeviceChild *v9; // rsi
  HRESULT (__stdcall *v10)(ID3D11DeviceChild *, const IID *const, void **); // rbx
  __int64 v11; // rsi
  void (__fastcall *v12)(__int64, GUID *, char *); // rbx
  _QWORD *v13; // r12
  int DeviceResources; // eax
  ULONG_PTR v15; // rbx
  struct ID3D11DeviceChild *v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rsi
  struct ID3D11DeviceChild *v24; // rbx
  std::_Ref_count_base *v25; // rdi
  std::_Ref_count_base *v26; // rcx
  _QWORD *Adapter; // rax
  ULONG_PTR v28; // rbx
  __int64 v29; // rax
  __int64 v30; // r13
  int v31; // esi
  int v32; // r15d
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rdx
  IDXGIAdapter **v39; // rax
  _DWORD *v40; // r12
  HRESULT Device; // ebx
  IDXGIAdapter **v42; // rax
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rax
  const char *v50; // rax
  __int64 v51; // r15
  __int64 v52; // rsi
  __int64 v53; // rbx
  __int64 v54; // rax
  int v55; // edx
  int v56; // r9d
  __int64 v57; // rbx
  int v58; // edx
  int v59; // r9d
  __int64 v60; // rbx
  int v61; // edx
  int v62; // r9d
  __int64 v63; // rbx
  int v64; // edx
  int v65; // r9d
  __int64 v66; // rbx
  __int64 v67; // rax
  int v68; // edx
  int v69; // r9d
  __int64 v70; // rax
  int ppDevice; // [rsp+38h] [rbp-C8h]
  int pFeatureLevel; // [rsp+40h] [rbp-C0h]
  struct ID3D11DeviceChild *v73; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+60h] [rbp-A0h]
  int v76; // [rsp+68h] [rbp-98h] BYREF
  __int64 v77; // [rsp+6Ch] [rbp-94h]
  __int64 v78; // [rsp+74h] [rbp-8Ch]
  int v79; // [rsp+7Ch] [rbp-84h]
  char v80; // [rsp+80h] [rbp-80h]
  __int16 v81; // [rsp+81h] [rbp-7Fh]
  char v82; // [rsp+83h] [rbp-7Dh]
  __int128 v83; // [rsp+84h] [rbp-7Ch]
  __int128 v84; // [rsp+94h] [rbp-6Ch]
  int v85; // [rsp+A4h] [rbp-5Ch]
  char v86; // [rsp+A8h] [rbp-58h]
  __int16 v87; // [rsp+A9h] [rbp-57h]
  char v88; // [rsp+ABh] [rbp-55h]
  int v89; // [rsp+ACh] [rbp-54h]
  char v90[8]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v91; // [rsp+B8h] [rbp-48h]
  __int64 v92; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v93; // [rsp+C8h] [rbp-38h]
  char v94[8]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v95; // [rsp+D8h] [rbp-28h]
  EXCEPTION_RECORD pExceptionRecord; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v97[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v98[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v99[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v100[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v101[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v102[32]; // [rsp+220h] [rbp+120h] BYREF
  _OWORD v103[20]; // [rsp+240h] [rbp+140h] BYREF
  __int128 v104; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v105[720]; // [rsp+390h] [rbp+290h] BYREF
  Spectre::Engine::RenderState *v106; // [rsp+660h] [rbp+560h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+8C0h] [rbp+7C0h] BYREF
  __m128i si128; // [rsp+8D0h] [rbp+7D0h]
  int v109; // [rsp+8E0h] [rbp+7E0h]
  void *retaddr; // [rsp+938h] [rbp+838h]

  v2 = (struct ID3D11DeviceChild *)*((_QWORD *)this + 37);
  v73 = v2;
  if ( v2 )
    ((void (__fastcall *)(struct ID3D11DeviceChild *))v2->lpVtbl->AddRef)(v2);
  v3 = (struct ID3D11DeviceChild **)((char *)this + 4256);
  if ( v2 )
    Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device1>(&v73, (char *)this + 4256);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  v4 = *v3;
  if ( *v3 )
  {
    v73 = 0;
    v74 = 0;
    AddRef = v4->lpVtbl[6].AddRef;
    v6 = (struct ID3D11DeviceChild **)((char *)this + 4264);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 4264);
    ((void (__fastcall *)(struct ID3D11DeviceChild *, char *))AddRef)(v4, (char *)this + 4264);
    v7 = *v3;
    QueryInterface = (*v3)->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    ((void (__fastcall *)(struct ID3D11DeviceChild *, GUID *, struct ID3D11DeviceChild **))QueryInterface)(
      v7,
      &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
      &v73);
    v9 = v73;
    v10 = v73->lpVtbl[1].QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
    ((void (__fastcall *)(struct ID3D11DeviceChild *, __int64 *))v10)(v9, &v74);
    Microsoft::WRL::ComPtr<IDXGIAdapter>::As<IDXGIAdapter1>(&v74, (char *)this + 4272);
    v11 = *((_QWORD *)this + 534);
    v12 = *(void (__fastcall **)(__int64, GUID *, char *))(*(_QWORD *)v11 + 48LL);
    v13 = (_QWORD *)((char *)this + 4280);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 4280);
    v12(v11, &GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0, (char *)this + 4280);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  }
  else
  {
    v103[0] = 0;
    v104 = 0;
    DeviceResources = CDXDeviceFactory::CreateDeviceResources(
                        (unsigned int)v103,
                        (unsigned int)v103,
                        (unsigned int)&v104,
                        (unsigned int)&v104 + 8,
                        (unsigned int)(*((_DWORD *)this + 72) - 3) <= 1,
                        *((_DWORD *)this + 81),
                        *((_DWORD *)this + 82),
                        *((_DWORD *)this + 79),
                        *((_DWORD *)this + 80),
                        *((_DWORD *)this + 83));
    v15 = DeviceResources;
    if ( DeviceResources < 0 )
    {
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = -532265403;
      pExceptionRecord.ExceptionAddress = retaddr;
      pExceptionRecord.NumberParameters = 1;
      pExceptionRecord.ExceptionInformation[0] = v15;
      RaiseFailFastException(&pExceptionRecord, 0, 0);
    }
    v16 = (struct ID3D11DeviceChild *)v104;
    if ( (_QWORD)v104 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v104 + 8LL))(v104);
    v74 = 0;
    v73 = *v3;
    *v3 = v16;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
    v17 = *((_QWORD *)&v104 + 1);
    if ( *((_QWORD *)&v104 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v104 + 1) + 8LL))(*((_QWORD *)&v104 + 1));
    v6 = (struct ID3D11DeviceChild **)((char *)this + 4264);
    v74 = 0;
    v73 = (struct ID3D11DeviceChild *)*((_QWORD *)this + 533);
    *((_QWORD *)this + 533) = v17;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
    v18 = *(_QWORD *)&v103[0];
    if ( *(_QWORD *)&v103[0] )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v103[0] + 8LL))(*(_QWORD *)&v103[0]);
    v74 = 0;
    v73 = (struct ID3D11DeviceChild *)*((_QWORD *)this + 534);
    *((_QWORD *)this + 534) = v18;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
    v19 = *((_QWORD *)&v103[0] + 1);
    if ( *((_QWORD *)&v103[0] + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v103[0] + 1) + 8LL))(*((_QWORD *)&v103[0] + 1));
    v13 = (_QWORD *)((char *)this + 4280);
    v74 = 0;
    v73 = (struct ID3D11DeviceChild *)*((_QWORD *)this + 535);
    *((_QWORD *)this + 535) = v19;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v103);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v104);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)&v104 + 8);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v103 + 8);
    (*(void (__fastcall **)(Spectre::Engine::D3D11::RenderDeviceD3D11 *, _QWORD))(*(_QWORD *)this + 224LL))(
      this,
      *((unsigned int *)this + 94));
    CDXDeviceFactory::~CDXDeviceFactory((CDXDeviceFactory *)v103);
  }
  if ( *v3 )
    *((_DWORD *)this + 1062) = 0;
  if ( (*((_DWORD *)this + 96) & 0xFFFFFFFD) == 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v13 + 64LL))(*v13, *((_QWORD *)this + 49), 0);
  v20 = ((__int64 (__fastcall *)(struct ID3D11DeviceChild *))(*v3)->lpVtbl[5].Release)(*v3);
  *((_DWORD *)this + 1072) = v20;
  *((_DWORD *)this + 60) = v20;
  D3D11_SetDebugName(*v6, "DefaultImmediateContext");
  Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::CommandList>(this, v94);
  v21 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          v90,
          v94);
  Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(
    &v92,
    v21);
  v22 = std::string::string(v97, "Default");
  v23 = v92;
  Spectre::Engine::RendererResource::SetName(v92, v22);
  v24 = *v6;
  v73 = v24;
  if ( v24 )
    ((void (__fastcall *)(struct ID3D11DeviceChild *))v24->lpVtbl->AddRef)(v24);
  if ( *(struct ID3D11DeviceChild **)(v23 + 144) != v24 )
  {
    if ( v24 )
      ((void (__fastcall *)(struct ID3D11DeviceChild *))v24->lpVtbl->AddRef)(v24);
    v74 = *(_QWORD *)(v23 + 144);
    *(_QWORD *)(v23 + 144) = v24;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  v25 = v93;
  if ( v93 )
    _InterlockedIncrement((volatile signed __int32 *)v93 + 2);
  *((_QWORD *)this + 34) = v23;
  v26 = (std::_Ref_count_base *)*((_QWORD *)this + 35);
  *((_QWORD *)this + 35) = v25;
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  Adapter = (_QWORD *)Spectre::Engine::D3D11::RenderDeviceD3D11::GetAdapter(this, &v73);
  v28 = (*(int (__fastcall **)(_QWORD, char *))(*(_QWORD *)*Adapter + 64LL))(*Adapter, (char *)this + 4296);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  if ( (v28 & 0x80000000) != 0LL )
  {
    memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
    pExceptionRecord.ExceptionCode = -532265403;
    pExceptionRecord.ExceptionAddress = retaddr;
    pExceptionRecord.NumberParameters = 1;
    pExceptionRecord.ExceptionInformation[0] = v28;
    RaiseFailFastException(&pExceptionRecord, 0, 0);
  }
  std::wstring::wstring(v97, (char *)this + 4296);
  std::wstring::operator=((char *)this + 4600, v29);
  std::wstring::_Tidy_deallocate(v97);
  std::wstring::operator=((char *)this + 80, (char *)this + 4600);
  v30 = *((_QWORD *)this + 571) >> 20;
  v75 = *((_QWORD *)this + 572) >> 20;
  v74 = *((_QWORD *)this + 573) >> 20;
  Spectre::Engine::D3D11::RenderDeviceD3D11::SelectAdapterProfileLevel(this);
  v31 = *((_DWORD *)this + 1072) / 4096;
  v32 = *((_DWORD *)this + 1072) / 256 % 16;
  v33 = std::to_wstring(v98);
  v34 = std::to_wstring(v102);
  v36 = std::operator+<wchar_t>(v101, v35, v34);
  v37 = std::operator+<wchar_t>(v100, v36, L"_");
  std::wstring::wstring(v97, v38, v37, v33);
  std::wstring::operator=((char *)this + 144, v97);
  std::wstring::_Tidy_deallocate(v97);
  std::wstring::_Tidy_deallocate(v100);
  std::wstring::_Tidy_deallocate(v101);
  std::wstring::_Tidy_deallocate(v102);
  std::wstring::_Tidy_deallocate(v98);
  *(__m128i *)pFeatureLevels = _mm_load_si128((const __m128i *)&_xmm);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v109 = 37120;
  v39 = (IDXGIAdapter **)Spectre::Engine::D3D11::RenderDeviceD3D11::GetAdapter(this, &v73);
  v40 = (_DWORD *)((char *)this + 4292);
  Device = D3D11CreateDevice(
             *v39,
             D3D_DRIVER_TYPE_UNKNOWN,
             0,
             0,
             pFeatureLevels,
             9u,
             7u,
             0,
             (D3D_FEATURE_LEVEL *)this + 1073,
             0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  if ( Device == -2147024809 )
  {
    v42 = (IDXGIAdapter **)Spectre::Engine::D3D11::RenderDeviceD3D11::GetAdapter(this, &v73);
    Device = D3D11CreateDevice(
               *v42,
               D3D_DRIVER_TYPE_UNKNOWN,
               0,
               0,
               &pFeatureLevels[3],
               6u,
               7u,
               0,
               (D3D_FEATURE_LEVEL *)this + 1073,
               0);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  }
  if ( Device >= 0 )
  {
    v31 = *v40 / 4096;
    v32 = *v40 / 256 % 16;
    v43 = std::to_wstring(v100);
    v44 = std::to_wstring(v101);
    v46 = std::operator+<wchar_t>(v102, v45, v44);
    v47 = std::operator+<wchar_t>(v98, v46, L"_");
    std::wstring::wstring(v97, v48, v47, v43);
    std::wstring::operator=((char *)this + 176, v97);
    std::wstring::_Tidy_deallocate(v97);
    std::wstring::_Tidy_deallocate(v98);
    std::wstring::_Tidy_deallocate(v102);
    std::wstring::_Tidy_deallocate(v101);
    std::wstring::_Tidy_deallocate(v100);
  }
  v49 = std::to_wstring(v98);
  std::wstring::operator=((char *)this + 208, v49);
  std::wstring::_Tidy_deallocate(v98);
  Spectre::Utils::LexicalCast<std::string,std::wstring>(v99, (char *)this + 4600);
  v50 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v99);
  pFeatureLevel = v32;
  ppDevice = v31;
  v51 = v74;
  v52 = v75;
  Trace::LevelSettingsWrapper::Output(
    &gTraceLevelsNativeRenderer_RendererD3D11,
    3,
    "Adapter used %s -- memory %IuMB / %IuMB / %IuMB -- feature level %d_%d -- profile level %d",
    v50,
    v30,
    v75,
    v74,
    ppDevice,
    pFeatureLevel,
    *((_DWORD *)this + 1158));
  if ( Spectre::Utils::PerformanceLogger::HasSubscriber(*((Spectre::Utils::PerformanceLogger **)this + 74)) )
  {
    v53 = *((_QWORD *)this + 74);
    v54 = std::string::string(v98, v99);
    Spectre::Utils::PerformanceLogger::AddMeasurement<std::string>(
      v53,
      v55,
      491,
      v56,
      (__int64)"MachineSpecs_AdapterName",
      v54);
    v57 = *((_QWORD *)this + 74);
    std::_Integral_to_string<char,unsigned __int64>(v97, v30);
    Spectre::Utils::PerformanceLogger::AddMeasurement<std::string>(
      v57,
      v58,
      492,
      v59,
      (__int64)"MachineSpecs_AdapterVideoMemory",
      (__int64)v97);
    v60 = *((_QWORD *)this + 74);
    std::_Integral_to_string<char,unsigned __int64>(v97, v52);
    Spectre::Utils::PerformanceLogger::AddMeasurement<std::string>(
      v60,
      v61,
      493,
      v62,
      (__int64)"MachineSpecs_AdapterSystemMemory",
      (__int64)v97);
    v63 = *((_QWORD *)this + 74);
    std::_Integral_to_string<char,unsigned __int64>(v97, v51);
    Spectre::Utils::PerformanceLogger::AddMeasurement<std::string>(
      v63,
      v64,
      494,
      v65,
      (__int64)"MachineSpecs_AdapterSharedMemory",
      (__int64)v97);
    v66 = *((_QWORD *)this + 74);
    v67 = std::to_string(v98, *((unsigned int *)this + 1158));
    Spectre::Utils::PerformanceLogger::AddMeasurement<std::string>(
      v66,
      v68,
      495,
      v69,
      (__int64)"MachineSpecs_AdapterProfileLevel",
      v67);
  }
  Spectre::Engine::State::State((Spectre::Engine::State *)v105);
  v70 = Spectre::Engine::Engine::CreateResource<Spectre::Engine::RenderState,>(*((_QWORD *)this + 498), v90);
  std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(&v106, v70);
  if ( v91 )
    std::_Ref_count_base::_Decref(v91);
  v81 = 0;
  v82 = 0;
  v87 = 0;
  v88 = 0;
  v76 = 0;
  v77 = 2;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 65793;
  v86 = 1;
  v89 = 3;
  Spectre::Engine::RenderState::Create(v106, (const struct Spectre::Engine::RenderStateDesc *)&v76, this);
  (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 34) + 40LL))(*((_QWORD *)this + 34), v105);
  if ( *((int *)this + 1072) < 40960 )
    *((_DWORD *)this + 970) = 4;
  Spectre::Engine::RenderDevice::InitializeRenderer(this);
  Spectre::Engine::State::~State((Spectre::Engine::State *)v105);
  std::string::_Tidy_deallocate(v99);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  if ( v95 )
    std::_Ref_count_base::_Decref(v95);
}

```

## disassembly

```asm
0x1800b6640  push    rbp
0x1800b6642  push    rbx
0x1800b6643  push    rsi
0x1800b6644  push    rdi
0x1800b6645  push    r12
0x1800b6647  push    r13
0x1800b6649  push    r14
0x1800b664b  push    r15
0x1800b664d  lea     rbp, [rsp-7F8h]
0x1800b6655  sub     rsp, 8F8h
0x1800b665c  mov     rax, cs:__security_cookie
0x1800b6663  xor     rax, rsp
0x1800b6666  mov     [rbp+830h+var_48], rax
0x1800b666d  mov     r14, rcx
0x1800b6670  xor     r13d, r13d
0x1800b6673  mov     rbx, [rcx+128h]
0x1800b667a  mov     [rsp+930h+var_8E0], rbx
0x1800b667f  test    rbx, rbx
0x1800b6682  jz      short loc_1800B6694
0x1800b6684  mov     rax, [rbx]
0x1800b6687  mov     rcx, rbx
0x1800b668a  mov     rax, [rax+8]
0x1800b668e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6693  nop
0x1800b6694  lea     rdi, [r14+10A0h]
0x1800b669b  test    rbx, rbx
0x1800b669e  jz      short loc_1800B66AD
0x1800b66a0  mov     rdx, rdi
0x1800b66a3  lea     rcx, [rsp+930h+var_8E0]
0x1800b66a8  call    ??$As@UID3D11Device1@@@?$ComPtr@UID3D11Device@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device1>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D11Device1>>)
0x1800b66ad  lea     rcx, [rsp+930h+var_8E0]
0x1800b66b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b66b7  mov     rsi, [rdi]
0x1800b66ba  test    rsi, rsi
0x1800b66bd  jz      loc_1800B67A3
0x1800b66c3  mov     [rsp+930h+var_8E0], r13
0x1800b66c8  mov     [rsp+930h+var_8D8], r13
0x1800b66cd  mov     rax, [rsi]
0x1800b66d0  mov     rbx, [rax+158h]
0x1800b66d7  lea     r15, [r14+10A8h]
0x1800b66de  mov     rcx, r15
0x1800b66e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b66e6  mov     rdx, r15
0x1800b66e9  mov     rcx, rsi
0x1800b66ec  mov     rax, rbx
0x1800b66ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b66f4  nop
0x1800b66f5  mov     rsi, [rdi]
0x1800b66f8  mov     rax, [rsi]
0x1800b66fb  mov     rbx, [rax]
0x1800b66fe  lea     rcx, [rsp+930h+var_8E0]
0x1800b6703  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6708  lea     r8, [rsp+930h+var_8E0]
0x1800b670d  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x1800b6714  mov     rcx, rsi
0x1800b6717  mov     rax, rbx
0x1800b671a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b671f  nop
0x1800b6720  mov     rsi, [rsp+930h+var_8E0]
0x1800b6725  mov     rax, [rsi]
0x1800b6728  mov     rbx, [rax+38h]
0x1800b672c  lea     rcx, [rsp+930h+var_8D8]
0x1800b6731  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6736  lea     rdx, [rsp+930h+var_8D8]
0x1800b673b  mov     rcx, rsi
0x1800b673e  mov     rax, rbx
0x1800b6741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6746  lea     rbx, [r14+10B0h]
0x1800b674d  mov     rdx, rbx
0x1800b6750  lea     rcx, [rsp+930h+var_8D8]
0x1800b6755  call    ??$As@UIDXGIAdapter1@@@?$ComPtr@UIDXGIAdapter@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IDXGIAdapter>::As<IDXGIAdapter1>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGIAdapter1>>)
0x1800b675a  mov     rsi, [rbx]
0x1800b675d  mov     rax, [rsi]
0x1800b6760  mov     rbx, [rax+30h]
0x1800b6764  lea     r12, [r14+10B8h]
0x1800b676b  mov     rcx, r12
0x1800b676e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6773  mov     r8, r12
0x1800b6776  lea     rdx, _GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0
0x1800b677d  mov     rcx, rsi
0x1800b6780  mov     rax, rbx
0x1800b6783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6788  nop
0x1800b6789  lea     rcx, [rsp+930h+var_8D8]
0x1800b678e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6793  nop
0x1800b6794  lea     rcx, [rsp+930h+var_8E0]
0x1800b6799  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b679e  jmp     loc_1800B69DA
0x1800b67a3  xorps   xmm0, xmm0
0x1800b67a6  movdqa  [rbp+830h+var_6F0], xmm0
0x1800b67ae  xorps   xmm1, xmm1
0x1800b67b1  movdqa  [rbp+830h+var_5B0], xmm1
0x1800b67b9  mov     eax, [r14+120h]
0x1800b67c0  sub     eax, 3
0x1800b67c3  mov     ecx, r13d
0x1800b67c6  cmp     eax, 1
0x1800b67c9  setbe   cl
0x1800b67cc  mov     eax, [r14+14Ch]
0x1800b67d3  mov     dword ptr [rsp+930h+ppImmediateContext], eax
0x1800b67d7  mov     eax, [r14+140h]
0x1800b67de  mov     dword ptr [rsp+930h+pFeatureLevel], eax
0x1800b67e2  mov     eax, [r14+13Ch]
0x1800b67e9  mov     dword ptr [rsp+930h+ppDevice], eax
0x1800b67ed  mov     eax, [r14+148h]
0x1800b67f4  mov     [rsp+930h+SDKVersion], eax
0x1800b67f8  mov     eax, [r14+144h]
0x1800b67ff  mov     [rsp+930h+FeatureLevels], eax
0x1800b6803  mov     dword ptr [rsp+930h+pFeatureLevels], ecx
0x1800b6807  lea     r9, [rbp+830h+var_5B0+8]
0x1800b680e  lea     r8, [rbp+830h+var_5B0]
0x1800b6815  lea     rdx, [rbp+830h+var_6F0]
0x1800b681c  lea     rcx, [rbp+830h+var_6F0]
0x1800b6823  call    ?CreateDeviceResources@CDXDeviceFactory@@AEAAJAEAV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@AEAV?$ComPtr@UID3D11Device1@@@34@AEAV?$ComPtr@UID3D11DeviceContext1@@@34@W4GraphicsDeviceType@@W4AdditionalDeviceFlags@@W4AdditionalDevicePerformanceFlags@@W4D3D_FEATURE_LEVEL@@6W4DeviceFeatureFlags@@@Z; CDXDeviceFactory::CreateDeviceResources(Microsoft::WRL::ComPtr<IDXGIAdapter1> &,Microsoft::WRL::ComPtr<ID3D11Device1> &,Microsoft::WRL::ComPtr<ID3D11DeviceContext1> &,GraphicsDeviceType,AdditionalDeviceFlags,AdditionalDevicePerformanceFlags,D3D_FEATURE_LEVEL,D3D_FEATURE_LEVEL,DeviceFeatureFlags)
0x1800b6828  movsxd  rbx, eax
0x1800b682b  test    eax, eax
0x1800b682d  jns     short loc_1800B686C
0x1800b682f  xor     edx, edx; Val
0x1800b6831  mov     r8d, 98h; Size
0x1800b6837  lea     rcx, [rbp+830h+pExceptionRecord]; void *
0x1800b683b  call    memset_0
0x1800b6840  mov     [rbp+830h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800b6847  mov     rcx, [rbp+838h]
0x1800b684e  mov     [rbp+830h+pExceptionRecord.ExceptionAddress], rcx
0x1800b6852  mov     [rbp+830h+pExceptionRecord.NumberParameters], 1
0x1800b6859  mov     [rbp+830h+pExceptionRecord.ExceptionInformation], rbx
0x1800b685d  xor     r8d, r8d; dwFlags
0x1800b6860  xor     edx, edx; pContextRecord
0x1800b6862  lea     rcx, [rbp+830h+pExceptionRecord]; pExceptionRecord
0x1800b6866  call    cs:__imp_RaiseFailFastException
0x1800b686c  mov     rbx, qword ptr [rbp+830h+var_5B0]
0x1800b6873  test    rbx, rbx
0x1800b6876  jz      short loc_1800B6888
0x1800b6878  mov     rax, [rbx]
0x1800b687b  mov     rcx, rbx
0x1800b687e  mov     rax, [rax+8]
0x1800b6882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6887  nop
0x1800b6888  mov     [rsp+930h+var_8D8], r13
0x1800b688d  mov     rax, [rdi]
0x1800b6890  mov     [rsp+930h+var_8E0], rax
0x1800b6895  mov     [rdi], rbx
0x1800b6898  lea     rcx, [rsp+930h+var_8E0]
0x1800b689d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b68a2  lea     rcx, [rsp+930h+var_8D8]
0x1800b68a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b68ac  mov     rbx, qword ptr [rbp+830h+var_5B0+8]
0x1800b68b3  test    rbx, rbx
0x1800b68b6  jz      short loc_1800B68C8
0x1800b68b8  mov     rax, [rbx]
0x1800b68bb  mov     rcx, rbx
0x1800b68be  mov     rax, [rax+8]
0x1800b68c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b68c7  nop
0x1800b68c8  lea     r15, [r14+10A8h]
0x1800b68cf  mov     [rsp+930h+var_8D8], r13
0x1800b68d4  mov     rax, [r15]
0x1800b68d7  mov     [rsp+930h+var_8E0], rax
0x1800b68dc  mov     [r15], rbx
0x1800b68df  lea     rcx, [rsp+930h+var_8E0]
0x1800b68e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b68e9  lea     rcx, [rsp+930h+var_8D8]
0x1800b68ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b68f3  mov     rbx, qword ptr [rbp+830h+var_6F0]
0x1800b68fa  test    rbx, rbx
0x1800b68fd  jz      short loc_1800B690F
0x1800b68ff  mov     rax, [rbx]
0x1800b6902  mov     rcx, rbx
0x1800b6905  mov     rax, [rax+8]
0x1800b6909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b690e  nop
0x1800b690f  mov     [rsp+930h+var_8D8], r13
0x1800b6914  mov     rax, [r14+10B0h]
0x1800b691b  mov     [rsp+930h+var_8E0], rax
0x1800b6920  mov     [r14+10B0h], rbx
0x1800b6927  lea     rcx, [rsp+930h+var_8E0]
0x1800b692c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6931  lea     rcx, [rsp+930h+var_8D8]
0x1800b6936  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b693b  mov     rbx, qword ptr [rbp+830h+var_6F0+8]
0x1800b6942  test    rbx, rbx
0x1800b6945  jz      short loc_1800B6957
0x1800b6947  mov     rax, [rbx]
0x1800b694a  mov     rcx, rbx
0x1800b694d  mov     rax, [rax+8]
0x1800b6951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6956  nop
0x1800b6957  lea     r12, [r14+10B8h]
0x1800b695e  mov     [rsp+930h+var_8D8], r13
0x1800b6963  mov     rax, [r12]
0x1800b6967  mov     [rsp+930h+var_8E0], rax
0x1800b696c  mov     [r12], rbx
0x1800b6970  lea     rcx, [rsp+930h+var_8E0]
0x1800b6975  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b697a  lea     rcx, [rsp+930h+var_8D8]
0x1800b697f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6984  lea     rcx, [rbp+830h+var_6F0]
0x1800b698b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6990  lea     rcx, [rbp+830h+var_5B0]
0x1800b6997  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b699c  lea     rcx, [rbp+830h+var_5B0+8]
0x1800b69a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b69a8  lea     rcx, [rbp+830h+var_6F0+8]
0x1800b69af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b69b4  mov     rax, [r14]
0x1800b69b7  mov     edx, [r14+178h]
0x1800b69be  mov     rcx, r14
0x1800b69c1  mov     rax, [rax+0E0h]
0x1800b69c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69cd  nop
0x1800b69ce  lea     rcx, [rbp+830h+var_6F0]; this
0x1800b69d5  call    ??1CDXDeviceFactory@@QEAA@XZ; CDXDeviceFactory::~CDXDeviceFactory(void)
0x1800b69da  cmp     [rdi], r13
0x1800b69dd  jz      short loc_1800B69E6
0x1800b69df  mov     [r14+1098h], r13d
0x1800b69e6  test    dword ptr [r14+180h], 0FFFFFFFDh
0x1800b69f1  jnz     short loc_1800B6A0D
0x1800b69f3  mov     rcx, [r12]
0x1800b69f7  mov     rax, [rcx]
0x1800b69fa  xor     r8d, r8d
0x1800b69fd  mov     rdx, [r14+188h]
0x1800b6a04  mov     rax, [rax+40h]
0x1800b6a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a0d  mov     rcx, [rdi]
0x1800b6a10  mov     rax, [rcx]
0x1800b6a13  mov     rax, [rax+128h]
0x1800b6a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a1f  mov     [r14+10C0h], eax
0x1800b6a26  mov     [r14+0F0h], eax
0x1800b6a2d  lea     rdx, aDefaultimmedia; "DefaultImmediateContext"
0x1800b6a34  mov     rcx, [r15]; struct ID3D11DeviceChild *
0x1800b6a37  call    ?D3D11_SetDebugName@@YAXPEAUID3D11DeviceChild@@PEBD@Z; D3D11_SetDebugName(ID3D11DeviceChild *,char const *)
0x1800b6a3c  lea     rdx, [rbp+830h+var_860]
0x1800b6a40  mov     rcx, r14
0x1800b6a43  call    ??$CreateResource@VCommandList@Engine@Spectre@@@RenderDevice@Engine@Spectre@@QEAA?AV?$shared_ptr@VCommandList@Engine@Spectre@@@std@@XZ; Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::CommandList>(void)
0x1800b6a48  nop
0x1800b6a49  lea     rdx, [rbp+830h+var_860]
0x1800b6a4d  lea     rcx, [rbp+830h+var_880]
0x1800b6a51  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800b6a56  mov     rdx, rax
0x1800b6a59  lea     rcx, [rbp+830h+var_870]
0x1800b6a5d  call    ??$spectre_safe_pointer_cast@VCommandListD3D11@D3D11@Engine@Spectre@@VCommandList@34@@Utils@Spectre@@YA?AV?$shared_ptr@VCommandListD3D11@D3D11@Engine@Spectre@@@std@@V?$shared_ptr@VCommandList@Engine@Spectre@@@3@@Z; Spectre::Utils::spectre_safe_pointer_cast<Spectre::Engine::D3D11::CommandListD3D11,Spectre::Engine::CommandList>(std::shared_ptr<Spectre::Engine::CommandList>)
0x1800b6a62  nop
0x1800b6a63  lea     rdx, aDefault; "Default"
0x1800b6a6a  lea     rcx, [rbp+830h+var_7B0]
0x1800b6a71  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800b6a76  mov     rdx, rax
0x1800b6a79  mov     rsi, [rbp+830h+var_870]
0x1800b6a7d  mov     rcx, rsi
0x1800b6a80  call    ?SetName@RendererResource@Engine@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::RendererResource::SetName(std::string)
0x1800b6a85  mov     rbx, [r15]
0x1800b6a88  mov     [rsp+930h+var_8E0], rbx
0x1800b6a8d  test    rbx, rbx
0x1800b6a90  jz      short loc_1800B6AA2
0x1800b6a92  mov     rax, [rbx]
0x1800b6a95  mov     rcx, rbx
0x1800b6a98  mov     rax, [rax+8]
0x1800b6a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6aa1  nop
0x1800b6aa2  cmp     [rsi+90h], rbx
0x1800b6aa9  jz      short loc_1800B6ADD
0x1800b6aab  test    rbx, rbx
0x1800b6aae  jz      short loc_1800B6AC0
0x1800b6ab0  mov     rax, [rbx]
0x1800b6ab3  mov     rcx, rbx
0x1800b6ab6  mov     rax, [rax+8]
0x1800b6aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6abf  nop
0x1800b6ac0  mov     rax, [rsi+90h]
0x1800b6ac7  mov     [rsp+930h+var_8D8], rax
0x1800b6acc  mov     [rsi+90h], rbx
0x1800b6ad3  lea     rcx, [rsp+930h+var_8D8]
0x1800b6ad8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6add  lea     rcx, [rsp+930h+var_8E0]
0x1800b6ae2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6ae7  mov     rdi, [rbp+830h+var_868]
0x1800b6aeb  test    rdi, rdi
0x1800b6aee  jz      short loc_1800B6AF4
0x1800b6af0  lock inc dword ptr [rdi+8]
0x1800b6af4  mov     [r14+110h], rsi
0x1800b6afb  mov     rcx, [r14+118h]; this
0x1800b6b02  mov     [r14+118h], rdi
0x1800b6b09  test    rcx, rcx
0x1800b6b0c  jz      short loc_1800B6B13
0x1800b6b0e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b6b13  lea     rdx, [rsp+930h+var_8E0]
0x1800b6b18  mov     rcx, r14
0x1800b6b1b  call    ?GetAdapter@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetAdapter(void)
0x1800b6b20  nop
0x1800b6b21  mov     rcx, [rax]
0x1800b6b24  lea     rsi, [r14+10C8h]
0x1800b6b2b  mov     rax, [rcx]
0x1800b6b2e  mov     rdx, rsi
0x1800b6b31  mov     rax, [rax+40h]
0x1800b6b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6b3a  movsxd  rbx, eax
0x1800b6b3d  lea     rcx, [rsp+930h+var_8E0]
0x1800b6b42  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b6b47  test    ebx, ebx
0x1800b6b49  jns     short loc_1800B6B88
  ... truncated ...
```
