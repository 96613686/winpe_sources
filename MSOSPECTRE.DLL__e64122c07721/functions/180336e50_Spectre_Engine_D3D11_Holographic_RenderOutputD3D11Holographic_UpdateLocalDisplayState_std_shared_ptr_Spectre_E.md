# Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::UpdateLocalDisplayState(std::shared_ptr<Spectre::Engine::D3D11::Holographic::IHolographicDisplayProvider> const &,std::shared_ptr<Spectre::Engine::D3D11::Holographic::HolographicDisplayState> const &)

- ea: `0x180336e50`
- end: `0x180338788`
- name: `?UpdateLocalDisplayState@RenderOutputD3D11Holographic@Holographic@D3D11@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VIHolographicDisplayProvider@Holographic@D3D11@Engine@Spectre@@@std@@AEBV?$shared_ptr@UHolographicDisplayState@Holographic@D3D11@Engine@Spectre@@@7@@Z`
- size: `6456`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180336ac0`

## callees

- `0x180014b80`
- `0x180015730`
- `0x180015740`
- `0x180015770`
- `0x18002a0ac`
- `0x18002a178`
- `0x18002a2d8`
- `0x18002a3d8`
- `0x1801872c0`
- `0x18022e4e0`
- `0x180261810`
- `0x18026e970`
- `0x18026f280`
- `0x180273150`
- `0x1802743c0`
- `0x180275910`
- `0x180277e30`
- `0x180320740`
- `0x180324640`
- `0x1803265e0`
- `0x18032d170`
- `0x180336e50`
- `0x18039e5b0`
- `0x18039f8e0`
- `0x18039f970`
- `0x1804f99e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1803371e1`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18033725e`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1803371e1`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18033725e`

## string_xrefs

- `0x180337ff2`: `"CreateRenderTargetView failure"`
- `0x1803380f1`: `"CreateRenderTargetView stereo failure"`
- `0x1803382ef`: `"dxgiBackBuffer->CreateSubresourceSurface(isStereo ? 1 : 0, &dxgiSurface) failure"`
- `0x1803383ee`: `"m_d2dContext->CreateBitmapFromDxgiSurface failure"`
- `0x1803384ed`: `"d3dDevice->CreateTexture2D failure"`
- `0x1803385ec`: `"d3dDevice->CreateTexture2D failure"`
- `0x180337df4`: `"d3dDevice->CreateDepthStencilView failure"`
- `0x1803386eb`: `"d3dDevice->CreateDepthStencilView failure"`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Spectre::Engine::D3D11::Holographic::RenderOutputD3D11Holographic::UpdateLocalDisplayState(
        _QWORD *a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v5; // r8
  __int64 v6; // rbx
  volatile signed __int32 *v7; // r9
  __int64 v8; // rdx
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  __int64 v11; // rcx
  double v12; // xmm0_8
  float v13; // xmm6_4
  __int64 v14; // r15
  int v15; // r14d
  char v16; // r12
  __int64 v17; // r14
  struct ID3D11DeviceChild *v18; // rcx
  struct ID3D11DeviceChild *v19; // rbx
  unsigned int v20; // r12d
  __int64 v21; // r14
  __int64 v22; // rdx
  __int64 *v23; // rbx
  __int64 v24; // rcx
  int v25; // r14d
  __int64 v26; // rbx
  __int64 *v27; // r14
  __int64 v28; // r15
  __int64 v29; // rcx
  int v30; // r14d
  __m128 v31; // xmm0
  __m128 v32; // xmm0
  int v33; // r14d
  __int64 v34; // rbx
  unsigned int v35; // eax
  int v36; // r14d
  __int64 v37; // rbx
  unsigned int v38; // eax
  __int64 v39; // r14
  __int64 v40; // rbx
  __int64 v41; // rcx
  int v42; // r14d
  __int64 v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // r14
  __int64 v46; // rcx
  int v47; // r14d
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rbx
  __int64 v55; // rdx
  int v56; // ecx
  __int64 v57; // r14
  _QWORD *v58; // rbx
  __int64 v59; // rcx
  int v60; // r14d
  BOOL v61; // ecx
  int v62; // ecx
  int v63; // ecx
  int v64; // ecx
  int v65; // ecx
  __int64 v66; // r14
  __int64 v67; // rdx
  __int64 *v68; // rbx
  __int64 v69; // rcx
  int v70; // r14d
  __int64 v71; // rbx
  __int64 *v72; // r14
  __int64 v73; // r15
  __int64 v74; // rcx
  int v75; // r14d
  __int64 v76; // rcx
  __int64 v77; // rbx
  __int64 v78; // r8
  __int64 v79; // rdx
  signed __int32 v80; // eax
  signed __int32 v81; // ett
  __int64 v82; // rcx
  __int64 result; // rax
  __int64 v84; // r13
  bool v85; // zf
  __int64 v86; // r12
  __int64 v87; // r14
  glslang::TIntermTyped *v88; // rbx
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // rcx
  volatile signed __int32 *v95; // rbx
  volatile signed __int32 *v96; // rbx
  volatile signed __int32 *v97; // rbx
  _QWORD *v98; // r15
  __int64 v99; // rdx
  __int64 v100; // r14
  glslang::TIntermTyped *v101; // rbx
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rdx
  __int64 v106; // rcx
  volatile signed __int32 *v107; // rbx
  volatile signed __int32 *v108; // rbx
  volatile signed __int32 *v109; // rbx
  Spectre::Engine::RenderDevice *v110; // rbx
  struct ID3D11DeviceChild *v111; // rcx
  __int64 (__fastcall ***v112)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rbx
  __int64 v118; // rax
  const char *v119; // rax
  int v120; // eax
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rbx
  __int64 v125; // rax
  const char *v126; // rax
  int v127; // eax
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rbx
  __int64 v132; // rax
  const char *v133; // rax
  int v134; // eax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  __int64 v138; // rbx
  __int64 v139; // rax
  const char *v140; // rax
  int v141; // eax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rbx
  __int64 v146; // rax
  const char *v147; // rax
  int v148; // eax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rbx
  __int64 v153; // rax
  const char *v154; // rax
  int v155; // eax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rbx
  __int64 v160; // rax
  const char *v161; // rax
  int v162; // eax
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 v166; // rbx
  __int64 v167; // rax
  const char *v168; // rax
  int v169; // eax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rbx
  __int64 v174; // rax
  const char *v175; // rax
  int v176; // eax
  __int64 v177; // rax
  __int64 v178; // rax
  __int64 v179; // rax
  __int64 v180; // rbx
  __int64 v181; // rax
  const char *v182; // rax
  int v183; // eax
  char v184; // [rsp+30h] [rbp-D0h]
  char v185; // [rsp+31h] [rbp-CFh]
  volatile signed __int32 *v186; // [rsp+40h] [rbp-C0h]
  char v188[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v189[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v190[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v191[32]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v192; // [rsp+B8h] [rbp-48h]
  __int64 v193; // [rsp+C0h] [rbp-40h]
  __int64 v194; // [rsp+C8h] [rbp-38h]
  __int64 v195; // [rsp+D0h] [rbp-30h]
  _BYTE pExceptionObject[64]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v197; // [rsp+120h] [rbp+20h] BYREF
  __int128 v198; // [rsp+130h] [rbp+30h] BYREF
  __int128 v199; // [rsp+140h] [rbp+40h]
  char v200[8]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v201; // [rsp+158h] [rbp+58h]
  char v202[8]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v203; // [rsp+168h] [rbp+68h]
  _BYTE v204[32]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v205; // [rsp+190h] [rbp+90h] BYREF
  __int64 v206; // [rsp+198h] [rbp+98h] BYREF
  __int64 v207; // [rsp+1A0h] [rbp+A0h] BYREF
  struct ID3D11DeviceChild *v208; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 (__fastcall ***v209)(_QWORD, GUID *, struct ID3D11DeviceChild **); // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v210; // [rsp+1C0h] [rbp+C0h] BYREF
  Spectre::Engine::RenderDevice *v211[2]; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 v212; // [rsp+1E0h] [rbp+E0h]
  __int64 v213; // [rsp+1E8h] [rbp+E8h]
  _DWORD v214[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v215; // [rsp+1FCh] [rbp+FCh]
  int v216; // [rsp+204h] [rbp+104h]
  __int128 v217; // [rsp+208h] [rbp+108h] BYREF
  _DWORD v218[2]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v219; // [rsp+220h] [rbp+120h]
  int v220; // [rsp+228h] [rbp+128h]
  __int128 v221; // [rsp+230h] [rbp+130h] BYREF
  __int128 v222; // [rsp+240h] [rbp+140h] BYREF
  _DWORD v223[5]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v224; // [rsp+264h] [rbp+164h]
  int v225; // [rsp+26Ch] [rbp+16Ch]
  __int64 v226; // [rsp+270h] [rbp+170h]
  int v227; // [rsp+278h] [rbp+178h]
  __int128 v228; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v229[20]; // [rsp+290h] [rbp+190h]
  __int64 v230; // [rsp+2A4h] [rbp+1A4h]
  __int128 v231; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v232; // [rsp+2C0h] [rbp+1C0h]
  _OWORD v233[2]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v199 = 0;
  v5 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD *, char *))(*a1 + 376LL))(a1, v200);
  v6 = 0;
  v7 = 0;
  v186 = 0;
  v8 = v5[1];
  if ( v8 )
  {
    v9 = *(_DWORD *)(v8 + 8);
    if ( v9 )
    {
      while ( 1 )
      {
        v10 = v9;
        v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
        if ( v10 == v9 )
          break;
        if ( !v9 )
          goto LABEL_7;
      }
      v6 = *v5;
      v7 = (volatile signed __int32 *)v5[1];
      v186 = v7;
    }
  }
LABEL_7:
  *(_QWORD *)&v199 = v6;
  *((_QWORD *)&v199 + 1) = v7;
  v11 = v201;
  if ( v201 && _InterlockedExchangeAdd((volatile signed __int32 *)(v201 + 12), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 8LL))(v11, v8, v5);
  v205 = 0;
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(v6, &v205, v5);
  v209 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct ID3D11DeviceChild **)))(*(_QWORD *)*a2 + 32LL))(
    *a2,
    &v209);
  v12 = (*(double (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 8LL))(*a2);
  v13 = *(float *)&v12;
  v184 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  LODWORD(v14) = (v184 != 0) + 1;
  *(_BYTE *)(*a3 + 1) = v184;
  v208 = 0;
  v15 = (**v209)(v209, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v208);
  if ( v15 < 0 )
  {
    std::string::string(v204, "THROW_IF_FAILED. ");
    v121 = std::string::append(v204, " File=");
    std::string::append(v121, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
    v122 = std::string::append(v204, " Line=");
    std::string::append(v122, "269");
    v123 = std::string::append(v204, " Message=");
    std::string::append(v123, "\"Get a Direct3D interface for the holographic camera's back buffer.\"");
    v124 = std::to_string(v191);
    v125 = std::string::append(v204, " HRESULT=");
    std::string::append(v125, v124);
    std::string::~string(v191);
    v126 = (const char *)std::string::c_str(v204);
    std::string::string(v189, v126);
    v127 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v127, 269, v15, (__int64)v189, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  D3D11_SetDebugName(v208, "CameraBackBuffer");
  v16 = 0;
  v185 = 0;
  v17 = *a3;
  v18 = *(struct ID3D11DeviceChild **)(*a3 + 8);
  v19 = v208;
  if ( v18 != v208 )
  {
    if ( v208 )
    {
      ((void (__fastcall *)(struct ID3D11DeviceChild *))v208->lpVtbl->AddRef)(v208);
      v18 = *(struct ID3D11DeviceChild **)(v17 + 8);
    }
    *(_QWORD *)(v17 + 8) = v19;
    if ( v18 )
      ((void (__fastcall *)(struct ID3D11DeviceChild *))v18->lpVtbl->Release)(v18);
    (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(*a3 + 8) + 80LL))(*(_QWORD *)(*a3 + 8), &v231);
    v20 = v232;
    v218[1] = (v184 != 0) + 4;
    v219 = 0;
    v220 = 1;
    v218[0] = v232;
    v21 = v205;
    v22 = *a3;
    v23 = (__int64 *)(*a3 + 48);
    v24 = *v23;
    if ( *v23 )
    {
      *v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v22 = *a3;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64 *))(*(_QWORD *)v21 + 72LL))(
            v21,
            *(_QWORD *)(v22 + 8),
            v218,
            v23);
    if ( v25 < 0 )
    {
      std::string::string(v204, "THROW_IF_FAILED. ");
      v128 = std::string::append(v204, " File=");
      std::string::append(v128, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      v129 = std::string::append(v204, " Line=");
      std::string::append(v129, "295");
      v130 = std::string::append(v204, " Message=");
      std::string::append(v130, "\"CreateRenderTargetView failure\"");
      v131 = std::to_string(v189);
      v132 = std::string::append(v204, " HRESULT=");
      std::string::append(v132, v131);
      std::string::~string(v189);
      v133 = (const char *)std::string::c_str(v204);
      std::string::string(v191, v133);
      v134 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      Spectre::Engine::EngineException::EngineException(
        (unsigned int)pExceptionObject,
        v134,
        295,
        v25,
        (__int64)v191,
        0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    v26 = *a3;
    v27 = (__int64 *)(*a3 + 96);
    if ( v184 )
    {
      HIDWORD(v219) = 1;
      v28 = v205;
      v29 = *v27;
      if ( *v27 )
      {
        *v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v26 = *a3;
      }
      v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64 *))(*(_QWORD *)v28 + 72LL))(
              v28,
              *(_QWORD *)(v26 + 8),
              v218,
              v27);
      if ( v30 < 0 )
      {
        std::string::string(v204, "THROW_IF_FAILED. ");
        v135 = std::string::append(v204, " File=");
        std::string::append(v135, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
        v136 = std::string::append(v204, " Line=");
        std::string::append(v136, "304");
        v137 = std::string::append(v204, " Message=");
        std::string::append(v137, "\"CreateRenderTargetView stereo failure\"");
        v138 = std::to_string(v189);
        v139 = std::string::append(v204, " HRESULT=");
        std::string::append(v139, v138);
        std::string::~string(v189);
        v140 = (const char *)std::string::c_str(v204);
        std::string::string(v191, v140);
        v141 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
        Spectre::Engine::EngineException::EngineException(
          (unsigned int)pExceptionObject,
          v141,
          304,
          v30,
          (__int64)v191,
          0);
        throw (Spectre::Engine::EngineException *)pExceptionObject;
      }
      LODWORD(v14) = (v184 != 0) + 1;
    }
    else
    {
      v53 = *v27;
      v54 = *(_QWORD *)(v26 + 48);
      if ( *v27 != v54 )
      {
        if ( v54 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
          v53 = *v27;
        }
        *v27 = v54;
        if ( v53 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
    }
    v211[0] = (Spectre::Engine::RenderDevice *)(v20 | 0x100000000LL);
    LODWORD(v212) = 3;
    v213 = 0;
    v31 = _mm_shuffle_ps(*(__m128 *)v211, *(__m128 *)v211, 210);
    v31.m128_f32[0] = v13;
    v32 = _mm_shuffle_ps(v31, v31, 39);
    v32.m128_f32[0] = v13;
    *(__m128 *)v211 = _mm_shuffle_ps(v32, v32, 57);
    v233[0] = *(_OWORD *)v211;
    v233[1] = v212;
    v207 = 0;
    v33 = (**v209)(v209, &GUID_30961379_4609_4a41_998e_54fe567ee0c1, (struct ID3D11DeviceChild **)&v207);
    if ( v33 < 0 )
    {
      std::string::string(v204, "THROW_IF_FAILED. ");
      v142 = std::string::append(v204, " File=");
      std::string::append(v142, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      v143 = std::string::append(v204, " Line=");
      std::string::append(v143, "325");
      v144 = std::string::append(v204, " Message=");
      std::string::append(v144, "\"backBufferResource.As(&dxgiBackBuffer) failure\"");
      v145 = std::to_string(v189);
      v146 = std::string::append(v204, " HRESULT=");
      std::string::append(v146, v145);
      std::string::~string(v189);
      v147 = (const char *)std::string::c_str(v204);
      std::string::string(v191, v147);
      v148 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      Spectre::Engine::EngineException::EngineException(
        (unsigned int)pExceptionObject,
        v148,
        325,
        v33,
        (__int64)v191,
        0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    v34 = v207;
    if ( v207 )
    {
      v35 = strnlen("DxgiBackBuffer", 0xFFu);
      (*(void (__fastcall **)(__int64, const GUID *, _QWORD, const char *))(*(_QWORD *)v34 + 24LL))(
        v34,
        &WKPDID_D3DDebugObjectName,
        v35,
        "DxgiBackBuffer");
      v34 = v207;
    }
    v206 = 0;
    v36 = (*(__int64 (__fastcall **)(__int64, bool, __int64 *))(*(_QWORD *)v34 + 96LL))(v34, v184 != 0, &v206);
    if ( v36 < 0 )
    {
      std::string::string(v204, "THROW_IF_FAILED. ");
      v149 = std::string::append(v204, " File=");
      std::string::append(v149, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      v150 = std::string::append(v204, " Line=");
      std::string::append(v150, "332");
      v151 = std::string::append(v204, " Message=");
      std::string::append(v151, "\"dxgiBackBuffer->CreateSubresourceSurface(isStereo ? 1 : 0, &dxgiSurface) failure\"");
      v152 = std::to_string(v189);
      v153 = std::string::append(v204, " HRESULT=");
      std::string::append(v153, v152);
      std::string::~string(v189);
      v154 = (const char *)std::string::c_str(v204);
      std::string::string(v191, v154);
      v155 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      Spectre::Engine::EngineException::EngineException(
        (unsigned int)pExceptionObject,
        v155,
        332,
        v36,
        (__int64)v191,
        0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    v37 = v206;
    if ( v206 )
    {
      v38 = strnlen("DxgiSurface", 0xFFu);
      (*(void (__fastcall **)(__int64, const GUID *, _QWORD, const char *))(*(_QWORD *)v37 + 24LL))(
        v37,
        &WKPDID_D3DDebugObjectName,
        v38,
        "DxgiSurface");
    }
    v39 = a1[66];
    v40 = *a3;
    v41 = *(_QWORD *)(*a3 + 32);
    if ( v41 )
    {
      *(_QWORD *)(v40 + 32) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = (*(__int64 (__fastcall **)(__int64, __int64, _OWORD *, __int64))(*(_QWORD *)v39 + 496LL))(
            v39,
            v206,
            v233,
            v40 + 32);
    if ( v42 < 0 )
    {
      std::string::string(v204, "THROW_IF_FAILED. ");
      v156 = std::string::append(v204, " File=");
      std::string::append(v156, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      v157 = std::string::append(v204, " Line=");
      std::string::append(v157, "338");
      v158 = std::string::append(v204, " Message=");
      std::string::append(v158, "\"m_d2dContext->CreateBitmapFromDxgiSurface failure\"");
      v159 = std::to_string(v189);
      v160 = std::string::append(v204, " HRESULT=");
      std::string::append(v160, v159);
      std::string::~string(v189);
      v161 = (const char *)std::string::c_str(v204);
      std::string::string(v191, v161);
      v162 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      Spectre::Engine::EngineException::EngineException(
        (unsigned int)pExceptionObject,
        v162,
        338,
        v42,
        (__int64)v191,
        0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)a1[66] + 592LL))(a1[66], *(_QWORD *)(*a3 + 32));
    *(_QWORD *)(*a3 + 40) = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*a2 + 24LL))(*a2, v188);
    v228 = v231;
    *(_OWORD *)v229 = v232;
    *(_QWORD *)&v229[12] = 3;
    v230 = 0x20000;
    HIDWORD(v228) = 1;
    v43 = *a3;
    v44 = *(_QWORD *)(*a3 + 16);
    if ( v44 )
    {
      *(_QWORD *)(v43 + 16) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v43 = *a3;
    }
    v45 = v205;
    v46 = *(_QWORD *)(v43 + 16);
    if ( v46 )
    {
      *(_QWORD *)(v43 + 16) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int64))(*(_QWORD *)v45 + 40LL))(
            v45,
            &v228,
            0,
            v43 + 16);
    if ( v47 < 0 )
    {
      std::string::string(v204, "THROW_IF_FAILED. ");
      v163 = std::string::append(v204, " File=");
      std::string::append(v163, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      v164 = std::string::append(v204, " Line=");
      std::string::append(v164, "356");
      v165 = std::string::append(v204, " Message=");
      std::string::append(v165, "\"d3dDevice->CreateTexture2D failure\"");
      v166 = std::to_string(v189);
      v167 = std::string::append(v204, " HRESULT=");
      std::string::append(v167, v166);
      std::string::~string(v189);
      v168 = (const char *)std::string::c_str(v204);
      std::string::string(v191, v168);
      v169 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      Spectre::Engine::EngineException::EngineException(
        (unsigned int)pExceptionObject,
        v169,
        356,
        v47,
        (__int64)v191,
        0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 16), "BackBufferStaging");
    v48 = *a3;
    v49 = *(_QWORD *)(*a3 + 56);
    if ( v49 )
    {
      *(_QWORD *)(v48 + 56) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      v48 = *a3;
    }
    v50 = *(_QWORD *)(v48 + 104);
    if ( v50 )
    {
      *(_QWORD *)(v48 + 104) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v16 = 1;
    v51 = v206;
    if ( v206 )
    {
      v206 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v207;
    if ( v207 )
    {
      v207 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
  }
  v55 = *a3;
  if ( !*(_QWORD *)(*a3 + 56) || !*(_QWORD *)(v55 + 104) )
  {
    v56 = *(_DWORD *)(v55 + 44);
    v223[0] = *(_DWORD *)(v55 + 40);
    v223[1] = v56;
    v223[2] = 1;
    v223[3] = v14;
    v223[4] = 55;
    v224 = 1;
    v225 = 0;
    v226 = 64;
    v227 = 0;
    v57 = v205;
    v58 = (_QWORD *)(v55 + 24);
    v59 = *(_QWORD *)(v55 + 24);
    if ( v59 )
    {
      *v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    v60 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, _QWORD *))(*(_QWORD *)v57 + 40LL))(v57, v223, 0, v58);
    if ( v60 < 0 )
    {
      std::string::string(v204, "THROW_IF_FAILED. ");
      v170 = std::string::append(v204, " File=");
      std::string::append(v170, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      v171 = std::string::append(v204, " Line=");
      std::string::append(v171, "381");
      v172 = std::string::append(v204, " Message=");
      std::string::append(v172, "\"d3dDevice->CreateTexture2D failure\"");
      v173 = std::to_string(v189);
      v174 = std::string::append(v204, " HRESULT=");
      std::string::append(v174, v173);
      std::string::~string(v189);
      v175 = (const char *)std::string::c_str(v204);
      std::string::string(v191, v175);
      v176 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
      Spectre::Engine::EngineException::EngineException(
        (unsigned int)pExceptionObject,
        v176,
        381,
        v60,
        (__int64)v191,
        0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 24), "BackBuffer_DepthStencilTexture");
    v61 = v184 != 0;
    v214[0] = 0;
    v214[1] = v61 + 3;
    v214[2] = 0;
    v62 = v61 + 2;
    if ( !v62 )
      goto LABEL_62;
    v63 = v62 - 1;
    if ( v63 )
    {
      v64 = v63 - 1;
      if ( !v64 )
        goto LABEL_62;
      v65 = v64 - 1;
      if ( v65 )
      {
        if ( v65 != 2 )
        {
LABEL_63:
          v216 = 1;
          v66 = v205;
          v67 = *a3;
          v68 = (__int64 *)(*a3 + 56);
          v69 = *v68;
          if ( *v68 )
          {
            *v68 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
            v67 = *a3;
          }
          v70 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64 *))(*(_QWORD *)v66 + 80LL))(
                  v66,
                  *(_QWORD *)(v67 + 24),
                  v214,
                  v68);
          if ( v70 < 0 )
          {
            std::string::string(v204, "THROW_IF_FAILED. ");
            v177 = std::string::append(v204, " File=");
            std::string::append(v177, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
            v178 = std::string::append(v204, " Line=");
            std::string::append(v178, "391");
            v179 = std::string::append(v204, " Message=");
            std::string::append(v179, "\"d3dDevice->CreateDepthStencilView failure\"");
            v180 = std::to_string(v189);
            v181 = std::string::append(v204, " HRESULT=");
            std::string::append(v181, v180);
            std::string::~string(v189);
            v182 = (const char *)std::string::c_str(v204);
            std::string::string(v191, v182);
            v183 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
            Spectre::Engine::EngineException::EngineException(
              (unsigned int)pExceptionObject,
              v183,
              391,
              v70,
              (__int64)v191,
              0);
            throw (Spectre::Engine::EngineException *)pExceptionObject;
          }
          D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 56), "BackBuffer_DepthStencilView_LeftEye");
          v71 = *a3;
          v72 = (__int64 *)(*a3 + 104);
          if ( v184 )
          {
            HIDWORD(v215) = 1;
            v73 = v205;
            v74 = *v72;
            if ( *v72 )
            {
              *v72 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
              v71 = *a3;
            }
            v75 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *, __int64 *))(*(_QWORD *)v73 + 80LL))(
                    v73,
                    *(_QWORD *)(v71 + 24),
                    v214,
                    v72);
            if ( v75 < 0 )
            {
              std::string::string(v204, "THROW_IF_FAILED. ");
              v114 = std::string::append(v204, " File=");
              std::string::append(v114, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
              v115 = std::string::append(v204, " Line=");
              std::string::append(v115, "401");
              v116 = std::string::append(v204, " Message=");
              std::string::append(v116, "\"d3dDevice->CreateDepthStencilView failure\"");
              v117 = std::to_string(v189);
              v118 = std::string::append(v204, " HRESULT=");
              std::string::append(v118, v117);
              std::string::~string(v189);
              v119 = (const char *)std::string::c_str(v204);
              std::string::string(v191, v119);
              v120 = std::string::string(v190, "..\\Source\\Holographic\\RenderOutputD3D11Holographic.cpp");
              Spectre::Engine::EngineException::EngineException(
                (unsigned int)pExceptionObject,
                v120,
                401,
                v75,
                (__int64)v191,
                0);
              throw (Spectre::Engine::EngineException *)pExceptionObject;
            }
            D3D11_SetDebugName(*(struct ID3D11DeviceChild **)(*a3 + 104), "BackBuffer_DepthStencilView_RightEye");
            LODWORD(v14) = (v184 != 0) + 1;
          }
          else
          {
            v76 = *v72;
            v77 = *(_QWORD *)(v71 + 56);
            if ( *v72 != v77 )
            {
              if ( v77 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 8LL))(v77);
                v76 = *v72;
              }
              *v72 = v77;
              if ( v76 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
            }
          }
          v185 = 1;
          goto LABEL_78;
        }
        HIDWORD(v215) = -1;
LABEL_62:
        LODWORD(v215) = 0;
        goto LABEL_63;
      }
    }
    v215 = 0;
    goto LABEL_63;
  }
LABEL_78:
  v78 = (*(__int64 (__fastcall **)(_QWORD *, char *))(*a1 + 376LL))(a1, v202);
  *(_OWORD *)v211 = 0;
  v79 = *(_QWORD *)(v78 + 8);
  if ( v79 )
  {
    v80 = *(_DWORD *)(v79 + 8);
    if ( v80 )
    {
      while ( 1 )
      {
        v81 = v80;
        v80 = _InterlockedCompareExchange((volatile signed __int32 *)(v79 + 8), v80 + 1, v80);
        if ( v81 == v80 )
          break;
        if ( !v80 )
          goto LABEL_84;
      }
      v211[0] = *(Spectre::Engine::RenderDevice **)v78;
      v211[1] = *(Spectre::Engine::RenderDevice **)(v78 + 8);
    }
  }
LABEL_84:
  v82 = v203;
  if ( v203 && _InterlockedExchangeAdd((volatile signed __int32 *)(v203 + 12), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v82 + 8LL))(v82, v79, v78);
  result = (__int64)Spectre::Engine::RenderDevice::GetEngine(v211[0]);
  v84 = (unsigned int)v14;
  v85 = v16 == 0;
  v86 = result;
  if ( v85 )
  {
    v98 = a1;
  }
  else
  {
    v87 = 0;
    v14 = (unsigned int)v14;
    do
    {
      v222 = 0;
      Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::DeviceFrameBuffer>(v211[0], &v222);
      v88 = (glslang::TIntermTyped *)_RTDynamicCast_0(
                                       v222,
                                       0,
                                       &Spectre::Engine::DeviceFrameBuffer `RTTI Type Descriptor',
                                       &Spectre::Engine::D3D11::RenderTargetD3D11 `RTTI Type Descriptor',
                                       1);
      v89 = *a3;
      v90 = *(_QWORD *)(*a3 + 16);
      v192 = v90;
      if ( v90 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 8LL))(v90);
        v89 = *a3;
      }
      v91 = *(_QWORD *)(v89 + 8);
      v193 = v91;
      if ( v91 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 8LL))(v91);
        v89 = *a3;
      }
      v92 = *(_QWORD *)(v87 + v89 + 48);
      v194 = v92;
      if ( v92 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 8LL))(v92);
        v89 = *a3;
      }
      Spectre::Engine::D3D11::RenderTargetD3D11::Create(v88, *(_DWORD *)(v89 + 40), *(_DWORD *)(v89 + 44));
      v217 = 0;
      Spectre::Engine::Engine::CreateResource<Spectre::Engine::FrameBuffer,>(v86, &v217, 0);
      Spectre::Engine::FrameBuffer::Create(v217, &v222);
      v93 = *a3;
      v94 = *((_QWORD *)&v217 + 1);
      if ( *((_QWORD *)&v217 + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v217 + 1) + 8LL));
        v94 = *((_QWORD *)&v217 + 1);
      }
      *(_QWORD *)(v87 + v93 + 64) = v217;
      v95 = *(volatile signed __int32 **)(v87 + v93 + 72);
      *(_QWORD *)(v87 + v93 + 72) = v94;
      if ( v95 )
      {
        if ( _InterlockedExchangeAdd(v95 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
          if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
        }
      }
      v96 = (volatile signed __int32 *)*((_QWORD *)&v217 + 1);
      if ( *((_QWORD *)&v217 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v217 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
          if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
        }
      }
      v97 = (volatile signed __int32 *)*((_QWORD *)&v222 + 1);
      if ( *((_QWORD *)&v222 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v222 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
          if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
        }
      }
      v87 += 48;
      --v14;
    }
    while ( v14 );
    if ( !v184 )
      std::shared_ptr<Spectre::Engine::FrameBuffer>::operator=(*a3 + 64, *a3 + 112);
    v98 = a1;
    (*(void (__fastcall **)(_QWORD *))(*a1 + 56LL))(a1);
    LOBYTE(v99) = 1;
    result = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v98 + 360LL))(v98, v99);
  }
  if ( v185 )
  {
    v100 = 0;
    do
    {
      v221 = 0;
      Spectre::Engine::RenderDevice::CreateResource<Spectre::Engine::DeviceDepthBuffer>(v211[0], &v221);
      v101 = (glslang::TIntermTyped *)_RTDynamicCast_0(
                                        v221,
                                        0,
                                        &Spectre::Engine::DeviceDepthBuffer `RTTI Type Descriptor',
                                        &Spectre::Engine::D3D11::DepthBufferD3D11 `RTTI Type Descriptor',
                                        1);
      v102 = *a3;
      v103 = *(_QWORD *)(*a3 + 24);
      if ( v103 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 8LL))(v103);
        v102 = *a3;
      }
      v104 = *(_QWORD *)(v100 + v102 + 56);
      v195 = v104;
      if ( v104 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 8LL))(v104);
      Spectre::Engine::D3D11::DepthBufferD3D11::Create(v101);
      v210 = 0;
      Spectre::Engine::Engine::CreateResource<Spectre::Engine::DepthBuffer,>(v86, &v210, 0);
      v197 = 0;
      if ( *((_QWORD *)&v221 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v221 + 1) + 8LL));
      v197 = v221;
      Spectre::Engine::DepthBuffer::Create(v210, &v197, 5);
      v198 = 0;
      if ( *((_QWORD *)&v210 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v210 + 1) + 8LL));
      v198 = v210;
      Spectre::Engine::RenderOutput::SetDepthBuffer(v98, &v198);
      v105 = *a3;
      v106 = *((_QWORD *)&v210 + 1);
      if ( *((_QWORD *)&v210 + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v210 + 1) + 8LL));
        v106 = *((_QWORD *)&v210 + 1);
      }
      result = v210;
      *(_QWORD *)(v100 + v105 + 80) = v210;
      v107 = *(volatile signed __int32 **)(v100 + v105 + 88);
      *(_QWORD *)(v100 + v105 + 88) = v106;
      if ( v107 )
      {
        result = (unsigned int)_InterlockedExchangeAdd(v107 + 2, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v107)(v107);
          result = (unsigned int)_InterlockedExchangeAdd(v107 + 3, 0xFFFFFFFF);
          if ( (_DWORD)result == 1 )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v107 + 8LL))(v107);
        }
      }
      v108 = (volatile signed __int32 *)*((_QWORD *)&v210 + 1);
      if ( *((_QWORD *)&v210 + 1) )
      {
        result = (unsigned int)_InterlockedExchangeAdd(
                                 (volatile signed __int32 *)(*((_QWORD *)&v210 + 1) + 8LL),
                                 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v108)(v108);
          result = (unsigned int)_InterlockedExchangeAdd(v108 + 3, 0xFFFFFFFF);
          if ( (_DWORD)result == 1 )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v108 + 8LL))(v108);
        }
      }
      v109 = (volatile signed __int32 *)*((_QWORD *)&v221 + 1);
      if ( *((_QWORD *)&v221 + 1) )
      {
        result = (unsigned int)_InterlockedExchangeAdd(
                                 (volatile signed __int32 *)(*((_QWORD *)&v221 + 1) + 8LL),
                                 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v109)(v109);
          result = (unsigned int)_InterlockedExchangeAdd(v109 + 3, 0xFFFFFFFF);
          if ( (_DWORD)result == 1 )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v109 + 8LL))(v109);
        }
      }
      v100 += 48;
      --v84;
    }
    while ( v84 );
    if ( !v184 )
      result = std::shared_ptr<Spectre::Engine::Texture>::operator=(*a3 + 80, *a3 + 128);
  }
  if ( v211[1] )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)v211[1] + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      v110 = v211[1];
      (**(void (__fastcall ***)(Spectre::Engine::RenderDevice *))v211[1])(v211[1]);
      result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)v110 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        result = (*(__int64 (__fastcall **)(Spectre::Engine::RenderDevice *))(*(_QWORD *)v211[1] + 8LL))(v211[1]);
    }
  }
  v111 = v208;
  if ( v208 )
  {
    v208 = 0;
    result = ((__int64 (__fastcall *)(struct ID3D11DeviceChild *))v111->lpVtbl->Release)(v111);
  }
  v112 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v209;
  if ( v209 )
  {
    v209 = 0;
    result = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v112)[2])(v112);
  }
  v113 = v205;
  if ( v205 )
  {
    v205 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  }
  if ( v186 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v186 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      result = (**(__int64 (__fastcall ***)(volatile signed __int32 *))v186)(v186);
      if ( _InterlockedExchangeAdd(v186 + 3, 0xFFFFFFFF) == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v186 + 8LL))(v186);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180336e50  mov     [rsp-8+arg_18], rbx
0x180336e55  push    rbp
0x180336e56  push    rsi
0x180336e57  push    rdi
0x180336e58  push    r12
0x180336e5a  push    r13
0x180336e5c  push    r14
0x180336e5e  push    r15
0x180336e60  lea     rbp, [rsp-220h]
0x180336e68  sub     rsp, 320h
0x180336e6f  movaps  [rsp+350h+var_40], xmm6
0x180336e77  mov     rax, cs:__security_cookie
0x180336e7e  xor     rax, rsp
0x180336e81  mov     [rbp+250h+var_50], rax
0x180336e88  mov     rsi, r8
0x180336e8b  mov     r13, rdx
0x180336e8e  mov     [rsp+350h+var_308], rcx
0x180336e93  xorps   xmm0, xmm0
0x180336e96  movups  [rbp+250h+var_210], xmm0
0x180336e9a  mov     rax, [rcx]
0x180336e9d  lea     rdx, [rbp+250h+var_200]
0x180336ea1  mov     rax, [rax+178h]
0x180336ea8  call    cs:__guard_dispatch_icall_fptr
0x180336eae  mov     r8, rax
0x180336eb1  xor     r14d, r14d
0x180336eb4  mov     ebx, r14d
0x180336eb7  mov     r9d, r14d
0x180336eba  mov     [rsp+350h+var_310], r14
0x180336ebf  mov     rdx, [rax+8]
0x180336ec3  test    rdx, rdx
0x180336ec6  jz      short loc_180336EEC
0x180336ec8  mov     eax, [rdx+8]
0x180336ecb  test    eax, eax
0x180336ecd  jz      short loc_180336EEC
0x180336ecf  nop
0x180336ed0  lea     ecx, [rax+1]
0x180336ed3  lock cmpxchg [rdx+8], ecx
0x180336ed8  jz      short loc_180336EE0
0x180336eda  test    eax, eax
0x180336edc  jnz     short loc_180336ED0
0x180336ede  jmp     short loc_180336EEC
0x180336ee0  mov     rbx, [r8]
0x180336ee3  mov     r9, [r8+8]
0x180336ee7  mov     [rsp+350h+var_310], r9
0x180336eec  mov     qword ptr [rbp+250h+var_210], rbx
0x180336ef0  mov     qword ptr [rbp+250h+var_210+8], r9
0x180336ef4  mov     edi, 0FFFFFFFFh
0x180336ef9  mov     rcx, [rbp+250h+var_1F8]
0x180336efd  test    rcx, rcx
0x180336f00  jz      short loc_180336F1C
0x180336f02  mov     eax, edi
0x180336f04  lock xadd [rcx+0Ch], eax
0x180336f09  cmp     eax, 1
0x180336f0c  jnz     short loc_180336F1C
0x180336f0e  mov     rax, [rcx]
0x180336f11  mov     rax, [rax+8]
0x180336f15  call    cs:__guard_dispatch_icall_fptr
0x180336f1b  nop
0x180336f1c  mov     [rbp+250h+var_1C0], r14
0x180336f23  lea     rdx, [rbp+250h+var_1C0]
0x180336f2a  mov     rcx, rbx
0x180336f2d  call    ?GetDevice@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(void)
0x180336f32  nop
0x180336f33  mov     [rbp+250h+var_1A0], r14
0x180336f3a  mov     rcx, [r13+0]
0x180336f3e  mov     rax, [rcx]
0x180336f41  lea     rdx, [rbp+250h+var_1A0]
0x180336f48  mov     rax, [rax+20h]
0x180336f4c  call    cs:__guard_dispatch_icall_fptr
0x180336f52  nop
0x180336f53  mov     rcx, [r13+0]
0x180336f57  mov     rax, [rcx]
0x180336f5a  mov     rax, [rax+8]
0x180336f5e  call    cs:__guard_dispatch_icall_fptr
0x180336f64  movaps  xmm6, xmm0
0x180336f67  mov     rcx, [r13+0]
0x180336f6b  mov     rax, [rcx]
0x180336f6e  mov     rax, [rax+10h]
0x180336f72  call    cs:__guard_dispatch_icall_fptr
0x180336f78  mov     [rsp+350h+var_320], al
0x180336f7c  mov     r15d, r14d
0x180336f7f  test    al, al
0x180336f81  setnz   r15b
0x180336f85  inc     r15d
0x180336f88  mov     [rsp+350h+var_318], r15d
0x180336f8d  mov     rcx, [rsi]
0x180336f90  mov     [rcx+1], al
0x180336f93  mov     [rbp+250h+var_1A8], r14
0x180336f9a  mov     rcx, [rbp+250h+var_1A0]
0x180336fa1  mov     rdx, [rcx]
0x180336fa4  mov     rax, [rdx]
0x180336fa7  lea     r8, [rbp+250h+var_1A8]
0x180336fae  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x180336fb5  call    cs:__guard_dispatch_icall_fptr
0x180336fbb  mov     r14d, eax
0x180336fbe  test    eax, eax
0x180336fc0  js      loc_180337E91
0x180336fc6  lea     rdx, aCamerabackbuff; "CameraBackBuffer"
0x180336fcd  mov     rcx, [rbp+250h+var_1A8]; struct ID3D11DeviceChild *
0x180336fd4  call    ?D3D11_SetDebugName@@YAXPEAUID3D11DeviceChild@@PEBD@Z; D3D11_SetDebugName(ID3D11DeviceChild *,char const *)
0x180336fd9  xor     r12b, r12b
0x180336fdc  mov     [rsp+350h+var_31F], r12b
0x180336fe1  mov     r14, [rsi]
0x180336fe4  mov     rcx, [r14+8]
0x180336fe8  mov     rbx, [rbp+250h+var_1A8]
0x180336fef  cmp     rcx, rbx
0x180336ff2  jz      loc_1803374B7
0x180336ff8  test    rbx, rbx
0x180336ffb  jz      short loc_180337011
0x180336ffd  mov     rax, [rbx]
0x180337000  mov     rcx, rbx
0x180337003  mov     rax, [rax+8]
0x180337007  call    cs:__guard_dispatch_icall_fptr
0x18033700d  mov     rcx, [r14+8]
0x180337011  mov     [r14+8], rbx
0x180337015  test    rcx, rcx
0x180337018  jz      short loc_180337027
0x18033701a  mov     rax, [rcx]
0x18033701d  mov     rax, [rax+10h]
0x180337021  call    cs:__guard_dispatch_icall_fptr
0x180337027  mov     rax, [rsi]
0x18033702a  mov     rcx, [rax+8]
0x18033702e  mov     rax, [rcx]
0x180337031  lea     rdx, [rbp+250h+var_A0]
0x180337038  mov     rax, [rax+50h]
0x18033703c  call    cs:__guard_dispatch_icall_fptr
0x180337042  mov     r12d, dword ptr [rbp+250h+var_90]
0x180337049  xor     r8d, r8d
0x18033704c  mov     eax, r8d
0x18033704f  cmp     [rsp+350h+var_320], r8b
0x180337054  setnz   al
0x180337057  add     eax, 4
0x18033705a  mov     [rbp+250h+var_134], eax
0x180337060  mov     [rbp+250h+var_130], r8
0x180337067  mov     [rbp+250h+var_128], 1
0x180337071  mov     [rbp+250h+var_138], r12d
0x180337078  mov     r14, [rbp+250h+var_1C0]
0x18033707f  mov     rdx, [rsi]
0x180337082  lea     rbx, [rdx+30h]
0x180337086  mov     rcx, [rbx]
0x180337089  test    rcx, rcx
0x18033708c  jz      short loc_1803370A1
0x18033708e  mov     [rbx], r8
0x180337091  mov     rax, [rcx]
0x180337094  mov     rax, [rax+10h]
0x180337098  call    cs:__guard_dispatch_icall_fptr
0x18033709e  mov     rdx, [rsi]
0x1803370a1  mov     rax, [r14]
0x1803370a4  mov     r9, rbx
0x1803370a7  lea     r8, [rbp+250h+var_138]
0x1803370ae  mov     rdx, [rdx+8]
0x1803370b2  mov     rcx, r14
0x1803370b5  mov     rax, [rax+48h]
0x1803370b9  call    cs:__guard_dispatch_icall_fptr
0x1803370bf  mov     r14d, eax
0x1803370c2  test    eax, eax
0x1803370c4  js      loc_180337F90
0x1803370ca  mov     rbx, [rsi]
0x1803370cd  lea     r14, [rbx+60h]
0x1803370d1  cmp     [rsp+350h+var_320], 0
0x1803370d6  jz      loc_180337471
0x1803370dc  mov     dword ptr [rbp+250h+var_130+4], 1
0x1803370e6  mov     r15, [rbp+250h+var_1C0]
0x1803370ed  mov     rcx, [r14]
0x1803370f0  test    rcx, rcx
0x1803370f3  jz      short loc_18033710C
0x1803370f5  mov     qword ptr [r14], 0
0x1803370fc  mov     rax, [rcx]
0x1803370ff  mov     rax, [rax+10h]
0x180337103  call    cs:__guard_dispatch_icall_fptr
0x180337109  mov     rbx, [rsi]
0x18033710c  mov     rax, [r15]
0x18033710f  mov     r9, r14
0x180337112  lea     r8, [rbp+250h+var_138]
0x180337119  mov     rdx, [rbx+8]
0x18033711d  mov     rcx, r15
0x180337120  mov     rax, [rax+48h]
0x180337124  call    cs:__guard_dispatch_icall_fptr
0x18033712a  mov     r14d, eax
0x18033712d  test    eax, eax
0x18033712f  js      loc_18033808F
0x180337135  mov     r15d, [rsp+350h+var_318]
0x18033713a  mov     dword ptr [rbp+250h+var_180], r12d
0x180337141  mov     dword ptr [rbp+250h+var_180+4], 1
0x18033714b  mov     dword ptr [rbp+250h+var_170], 3
0x180337155  xor     r12d, r12d
0x180337158  mov     qword ptr [rbp+250h+var_170+8], r12
0x18033715f  movups  xmm0, xmmword ptr [rbp+250h+var_180]
0x180337166  shufps  xmm0, xmm0, 0D2h
0x18033716a  movss   xmm0, xmm6
0x18033716e  shufps  xmm0, xmm0, 27h ; '''
0x180337172  movss   xmm0, xmm6
0x180337176  shufps  xmm0, xmm0, 39h ; '9'
0x18033717a  movups  xmmword ptr [rbp+250h+var_180], xmm0
0x180337181  movups  [rbp+250h+var_70], xmm0
0x180337188  movups  xmm0, [rbp+250h+var_170]
0x18033718f  movups  [rbp+250h+var_60], xmm0
0x180337196  mov     [rbp+250h+var_1B0], r12
0x18033719d  mov     rcx, [rbp+250h+var_1A0]
0x1803371a4  mov     rax, [rcx]
0x1803371a7  lea     r8, [rbp+250h+var_1B0]
0x1803371ae  lea     rdx, _GUID_30961379_4609_4a41_998e_54fe567ee0c1
0x1803371b5  mov     rax, [rax]
0x1803371b8  call    cs:__guard_dispatch_icall_fptr
0x1803371be  mov     r14d, eax
0x1803371c1  test    eax, eax
0x1803371c3  js      loc_18033818E
0x1803371c9  mov     rbx, [rbp+250h+var_1B0]
0x1803371d0  test    rbx, rbx
0x1803371d3  jz      short loc_180337212
0x1803371d5  mov     edx, 0FFh; MaxCount
0x1803371da  lea     rcx, aDxgibackbuffer_0; "DxgiBackBuffer"
0x1803371e1  call    cs:__imp_strnlen
0x1803371e7  mov     rdx, [rbx]
0x1803371ea  mov     r10, [rdx+18h]
0x1803371ee  lea     r9, aDxgibackbuffer_0; "DxgiBackBuffer"
0x1803371f5  mov     r8d, eax
0x1803371f8  lea     rdx, WKPDID_D3DDebugObjectName
0x1803371ff  mov     rcx, rbx
0x180337202  mov     rax, r10
0x180337205  call    cs:__guard_dispatch_icall_fptr
0x18033720b  mov     rbx, [rbp+250h+var_1B0]
0x180337212  mov     [rbp+250h+var_1B8], r12
0x180337219  mov     rax, [rbx]
0x18033721c  mov     edx, r12d
0x18033721f  cmp     [rsp+350h+var_320], r12b
0x180337224  setnz   dl
0x180337227  lea     r8, [rbp+250h+var_1B8]
0x18033722e  mov     rcx, rbx
0x180337231  mov     rax, [rax+60h]
0x180337235  call    cs:__guard_dispatch_icall_fptr
0x18033723b  mov     r14d, eax
0x18033723e  test    eax, eax
0x180337240  js      loc_18033828D
0x180337246  mov     rbx, [rbp+250h+var_1B8]
0x18033724d  test    rbx, rbx
0x180337250  jz      short loc_180337288
0x180337252  mov     edx, 0FFh; MaxCount
0x180337257  lea     rcx, aDxgisurface; "DxgiSurface"
0x18033725e  call    cs:__imp_strnlen
0x180337264  mov     r8, [rbx]
0x180337267  mov     r10, [r8+18h]
0x18033726b  lea     r9, aDxgisurface; "DxgiSurface"
0x180337272  mov     r8d, eax
0x180337275  lea     rdx, WKPDID_D3DDebugObjectName
0x18033727c  mov     rcx, rbx
0x18033727f  mov     rax, r10
0x180337282  call    cs:__guard_dispatch_icall_fptr
0x180337288  mov     r12, [rsp+350h+var_308]
0x18033728d  mov     r14, [r12+210h]
0x180337295  mov     rbx, [rsi]
0x180337298  mov     rcx, [rbx+20h]
0x18033729c  test    rcx, rcx
0x18033729f  jz      short loc_1803372B6
0x1803372a1  mov     qword ptr [rbx+20h], 0
0x1803372a9  mov     rax, [rcx]
0x1803372ac  mov     rax, [rax+10h]
0x1803372b0  call    cs:__guard_dispatch_icall_fptr
0x1803372b6  mov     rax, [r14]
0x1803372b9  lea     r9, [rbx+20h]
0x1803372bd  lea     r8, [rbp+250h+var_70]
0x1803372c4  mov     rdx, [rbp+250h+var_1B8]
0x1803372cb  mov     rcx, r14
0x1803372ce  mov     rax, [rax+1F0h]
0x1803372d5  call    cs:__guard_dispatch_icall_fptr
0x1803372db  mov     r14d, eax
0x1803372de  test    eax, eax
0x1803372e0  js      loc_18033838C
0x1803372e6  mov     rcx, [r12+210h]
0x1803372ee  mov     rax, [rcx]
0x1803372f1  mov     rdx, [rsi]
0x1803372f4  mov     rdx, [rdx+20h]
0x1803372f8  mov     rax, [rax+250h]
0x1803372ff  call    cs:__guard_dispatch_icall_fptr
0x180337305  mov     rcx, [r13+0]
0x180337309  mov     rax, [rcx]
0x18033730c  lea     rdx, [rsp+350h+var_300]
0x180337311  mov     rax, [rax+18h]
0x180337315  call    cs:__guard_dispatch_icall_fptr
0x18033731b  mov     rcx, [rsi]
0x18033731e  mov     rax, [rax]
0x180337321  mov     [rcx+28h], rax
0x180337325  movups  xmm0, [rbp+250h+var_A0]
0x18033732c  movups  [rbp+250h+var_D0], xmm0
0x180337333  movups  xmm1, [rbp+250h+var_90]
0x18033733a  movups  [rbp+250h+var_C0], xmm1
0x180337341  movsd   xmm0, [rbp+250h+var_80]
0x180337349  movsd   qword ptr [rbp+250h+var_B0], xmm0
0x180337351  mov     qword ptr [rbp+250h+var_C0+0Ch], 3
0x18033735c  mov     qword ptr [rbp+250h+var_B0+4], 20000h
0x180337367  xor     r13d, r13d
0x18033736a  mov     dword ptr [rbp+250h+var_D0+0Ch], 1
0x180337374  mov     rbx, [rsi]
0x180337377  mov     rcx, [rbx+10h]
0x18033737b  test    rcx, rcx
0x18033737e  jz      short loc_180337394
0x180337380  mov     [rbx+10h], r13
0x180337384  mov     rax, [rcx]
0x180337387  mov     rax, [rax+10h]
0x18033738b  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
