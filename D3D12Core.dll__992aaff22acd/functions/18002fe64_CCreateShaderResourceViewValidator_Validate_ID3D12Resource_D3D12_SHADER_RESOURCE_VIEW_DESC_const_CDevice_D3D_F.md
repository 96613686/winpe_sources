# CCreateShaderResourceViewValidator::Validate(ID3D12Resource *,D3D12_SHADER_RESOURCE_VIEW_DESC const *,CDevice *,D3D_FEATURE_LEVEL,DeviceValidationInfo const &,bool *)

- ea: `0x18002fe64`
- end: `0x180031c4c`
- name: `?Validate@CCreateShaderResourceViewValidator@@QEAAJPEAUID3D12Resource@@PEBUD3D12_SHADER_RESOURCE_VIEW_DESC@@PEAVCDevice@@W4D3D_FEATURE_LEVEL@@AEBUDeviceValidationInfo@@PEA_N@Z`
- size: `7656`
- prototype: `__int64 __fastcall(CCreateShaderResourceViewValidator *__hidden this, struct ID3D12Resource *, const struct D3D12_SHADER_RESOURCE_VIEW_DESC *, struct CDevice *, enum D3D_FEATURE_LEVEL, const struct DeviceValidationInfo *, bool *)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180090160`

## callees

- `0x180025f90`
- `0x180026410`
- `0x1800264c0`
- `0x1800268f0`
- `0x1800269d0`
- `0x18002ef50`
- `0x18002fe64`
- `0x180031e10`
- `0x180031ec0`
- `0x180033a70`
- `0x180035140`
- `0x180048934`
- `0x18004a470`
- `0x18004b950`
- `0x180078b10`
- `0x18007b6e8`
- `0x18009fd4c`
- `0x1800aa248`
- `0x1800abc10`
- `0x1800ae14c`
- `0x1800bb480`
- `0x1800bc010`
- `0x1800fa540`
- `0x180262020`

## string_xrefs

- `0x180031bfa`: `A View of a Buffer cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a Format must be supplied.`
- `0x180031a0b`: `Invalid Buffer SRV Flags combination: (%#x)`
- `0x180030230`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x180030642`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x180030ed8`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x1800300ab`: `The ViewDimension in the View Desc is incompatible with the type of the Resource.`
- `0x180030988`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180030ad6`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180031151`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180030571`: `Views of video formats cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a View format must be supplied, not the same as the underlying video format.The View format is needed to indicate how the video surface (or part of it) will appear to shaders - see documentation.`
- `0x1800301aa`: `A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default Desc parameters cannot be used, as a fully qualified Format must be supplied.`
- `0x180030548`: `A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default Desc parameters cannot be used, as a fully qualified Format must be supplied.`
- `0x1800303a5`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x18003079f`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x18003104d`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x18003034e`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x18003074e`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x180030ff6`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x18003135c`: `For D3D12_SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE, Shader4ComponentMapping must be D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING (%#x) (the field is actually unused).`
- `0x180030132`: `Shader4ComponentMapping is set to an invalid value.  To create a valid value use the D3D12_ENCODE_SHADER_4_COMPONENT_MAPPING(Src0,Src1,Src2,Src3) macro with a value from the D3D12_SHADER_COMPONENT_MAPPING enum in each entry.  Or, for a default 1:1 component mapping, simply use D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING (%#x).`
- `0x180031c0b`: `A ShaderResourceView cannot be created from a NULL Resource and NULL Desc.`
- `0x1800312e1`: `When ViewDimension is D3D12_SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE, pResource must be NULL, since the resource location comes from a GPUVA in pDesc.`
- `0x18003190d`: `Shader4ComponentMapping must be D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING (%#x) for raw buffers.`
- `0x1800315f5`: `Resources created with the D3D12_RESOURCE_FLAG_RAYTRACING_ACCELERATION_STRUCTURE flag can only be used to create SRVs with SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE.`
- `0x18003164a`: `Devices with feature level D3D_FEATURE_LEVEL_CORE_1_0 only support creating shader resource views on resources created from default heaps.`
- `0x180030c03`: `When casting from a compressed format to an uncompressed format, the NumCubes (value = %u) must be 1.`
- `0x1800316ee`: `Shader4ComponentMapping must be D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING (%#x) for structured buffers.`
- `0x18003049b`: `When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.`
- `0x1800309a6`: `When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.`
- `0x180030b58`: `When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.`
- `0x180030c21`: `When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.`
- `0x18003116f`: `When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.`
- `0x180031263`: `When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.`
- `0x180030e1d`: `The base resource was created as a multisample resource. You must specify D3D12_SRV_DIMENSION_TEXTURE2DMSARRAY or D3D12_SRV_DIMENSION_TEXTURE2DMS.`
- `0x180030d9d`: `Texture cube arrays cannot be created when GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less.`
- `0x180030e4c`: `When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, a ShaderResourceView cannot be created for a multisample resource when it is has the D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL flag.`
- `0x180031bd7`: `A ShaderResourceView cannot be created of a Resource that did specify the D3D12_RESOURCE_FLAG_DENY_SHADER_RESOURCE MiscFlag.`

## pseudocode

```c
__int64 __fastcall CCreateShaderResourceViewValidator::Validate(
        CCreateShaderResourceViewValidator *this,
        unsigned __int64 a2,
        const struct D3D12_SHADER_RESOURCE_VIEW_DESC *a3,
        struct CDevice *a4,
        enum D3D_FEATURE_LEVEL a5,
        const struct DeviceValidationInfo *a6,
        bool *a7)
{
  struct ID3D12Resource *v8; // r8
  unsigned int v9; // edi
  unsigned __int64 v10; // r13
  int v11; // r9d
  __int64 v12; // rax
  enum DXGI_FORMAT Format; // edi
  unsigned __int16 v14; // r9
  int v15; // r12d
  enum DXGI_FORMAT v16; // r14d
  D3D12_SRV_DIMENSION *v17; // rdx
  D3D12_SRV_DIMENSION ViewDimension; // ecx
  __int32 v19; // ecx
  __int32 v20; // ecx
  __int32 v21; // ecx
  __int32 v22; // ecx
  D3D12_SRV_DIMENSION v23; // ecx
  const char *v24; // r8
  __int64 v25; // rdx
  int v27; // ebx
  unsigned __int64 v28; // rdx
  UINT Shader4ComponentMapping; // ecx
  int v30; // r12d
  int v31; // r12d
  __int64 v32; // rax
  const char *v33; // r8
  _DWORD *v34; // rcx
  _DWORD *v35; // rdx
  bool v36; // dl
  const char *Name; // rax
  const char *v38; // r8
  char v39; // r12
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  bool v43; // dl
  bool v44; // dl
  const char *v45; // rax
  const char *v46; // r8
  bool v47; // dl
  const char *v48; // rax
  __int64 v49; // r8
  const char *v50; // r8
  bool v51; // dl
  __int64 v52; // r8
  bool v53; // dl
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rax
  bool v57; // dl
  __int64 v58; // r8
  bool v59; // dl
  const char *v60; // rax
  UINT MipLevels; // r9d
  UINT MostDetailedMip; // r9d
  UINT v63; // eax
  const char *v64; // r8
  __int64 v65; // rdi
  __int64 v66; // rax
  int v67; // r10d
  __int64 v68; // rcx
  int v69; // r9d
  char v70; // dl
  __int64 v71; // rax
  _DWORD *v72; // rcx
  _DWORD *v73; // rdx
  bool v74; // dl
  const char *v75; // rax
  const char *v76; // r8
  char v77; // al
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  bool v81; // dl
  const char *v82; // rax
  const char *v83; // r8
  bool v84; // dl
  const char *v85; // rax
  __int64 v86; // r8
  const char *v87; // r8
  bool v88; // dl
  __int64 v89; // r8
  bool v90; // dl
  const char *v91; // rax
  __int64 v92; // r8
  __int64 v93; // rdx
  const char *v94; // r8
  bool v95; // dl
  const char *v96; // rax
  __int64 v97; // r8
  __int64 v98; // r9
  const char *v99; // r8
  __int64 v100; // rax
  bool v101; // dl
  bool v102; // dl
  __int64 v103; // r8
  int v104; // eax
  bool v105; // dl
  bool v106; // dl
  __int64 v107; // r8
  bool v108; // dl
  const char *v109; // rax
  const char *v110; // r8
  _DWORD *v111; // r12
  UINT StructureByteStride; // r9d
  UINT v113; // r9d
  UINT v114; // r12d
  UINT v115; // eax
  unsigned __int16 v116; // r9
  UINT NumElements; // edx
  UINT v118; // eax
  __int64 v119; // r8
  bool v120; // zf
  bool v121; // dl
  UINT v122; // ecx
  UINT v123; // eax
  UINT v124; // r9d
  UINT v125; // r9d
  UINT v126; // eax
  const char *v127; // r8
  UINT v128; // r9d
  UINT v129; // r9d
  UINT v130; // eax
  UINT v131; // r9d
  UINT v132; // r9d
  UINT v133; // edx
  UINT v134; // r12d
  double v135; // xmm0_8
  UINT v136; // edx
  __int64 v137; // r9
  const char *v138; // r8
  bool v139; // dl
  const char *v140; // rax
  const char *v141; // rax
  char v142; // r14
  _DWORD *v143; // rcx
  _DWORD *v144; // rdx
  bool v145; // dl
  const char *v146; // rax
  const char *v147; // r8
  char v148; // r12
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  bool v152; // dl
  bool v153; // dl
  const char *v154; // rax
  const char *v155; // r8
  bool v156; // dl
  const char *v157; // rax
  __int64 v158; // r8
  const char *v159; // r8
  bool v160; // dl
  __int64 v161; // r8
  bool v162; // dl
  __int64 v163; // r8
  __int64 v164; // r9
  __int64 v165; // rax
  bool v166; // dl
  __int64 v167; // r8
  bool v168; // dl
  const char *v169; // rax
  UINT v170; // r9d
  UINT v171; // r9d
  UINT v172; // r12d
  UINT v173; // eax
  unsigned __int16 v174; // r9
  UINT v175; // r8d
  UINT v176; // eax
  UINT v177; // ecx
  UINT v178; // eax
  UINT v179; // r9d
  UINT v180; // r9d
  UINT v181; // eax
  UINT64 FirstElement; // r9
  unsigned __int64 v183; // r9
  UINT64 v184; // r9
  unsigned __int64 v185; // rdx
  UINT64 v186; // rcx
  unsigned int PlaneSlice; // r8d
  unsigned int v188; // ecx
  __int64 v189; // rax
  unsigned int v190; // ecx
  int v191; // r8d
  __int64 v192; // r9
  const char *v193; // r11
  const char *v194; // rcx
  char v195; // r10
  int v196; // r8d
  __int64 v197; // r9
  const char *v198; // rcx
  D3D12_BUFFER_SRV_FLAGS Flags; // r9d
  UINT64 v200; // r9
  ID3D12Resource_vtbl *v201; // rax
  unsigned __int32 v202; // ecx
  FLOAT ResourceMinLODClamp; // eax
  const char *v204; // rax
  UINT v205; // r9d
  UINT v206; // edx
  UINT64 v207; // r9
  UINT v208; // r11d
  UINT64 v209; // r8
  unsigned int v210; // r9d
  UINT64 v211; // r10
  UINT64 v212; // rax
  UINT64 v213; // rdx
  unsigned __int64 v214; // rax
  UINT64 v215; // rdx
  char v216; // r13
  unsigned __int64 ImmutableHeapOffset; // rax
  UINT64 v218; // rax
  const char *v219; // r8
  int v220; // eax
  bool v221; // dl
  char v222; // cl
  __int64 v223; // rax
  const char *v224; // rax
  const char *v225; // rax
  __int64 v226; // rax
  UINT64 v227; // r10
  unsigned __int64 v228; // r8
  UINT64 v229; // r9
  UINT64 v230; // rax
  UINT64 v231; // rcx
  const char *v232; // rax
  int v233; // r8d
  __int64 v234; // r9
  __int64 v235; // r10
  bool v236; // dl
  const char *v237; // rax
  bool v238; // dl
  const char *v239; // rax
  __int64 v240; // [rsp+20h] [rbp-E0h]
  __int64 v241; // [rsp+28h] [rbp-D8h]
  __int64 v242; // [rsp+30h] [rbp-D0h]
  __int64 v243; // [rsp+30h] [rbp-D0h]
  __int64 v244; // [rsp+30h] [rbp-D0h]
  __int64 v245; // [rsp+30h] [rbp-D0h]
  __int64 v246; // [rsp+30h] [rbp-D0h]
  __int64 v247; // [rsp+38h] [rbp-C8h]
  const char *v248; // [rsp+38h] [rbp-C8h]
  const char *v249; // [rsp+38h] [rbp-C8h]
  char v250; // [rsp+60h] [rbp-A0h]
  int v251; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v252; // [rsp+68h] [rbp-98h]
  unsigned int v253; // [rsp+6Ch] [rbp-94h]
  __int64 p_ViewDimension; // [rsp+70h] [rbp-90h]
  int Plane; // [rsp+78h] [rbp-88h]
  unsigned int v256; // [rsp+78h] [rbp-88h]
  unsigned int v257; // [rsp+7Ch] [rbp-84h]
  FLOAT v258; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 v259; // [rsp+80h] [rbp-80h]
  int v260; // [rsp+84h] [rbp-7Ch]
  struct ID3D12Resource *v261; // [rsp+88h] [rbp-78h]
  unsigned __int64 v262; // [rsp+90h] [rbp-70h]
  unsigned __int64 v263; // [rsp+98h] [rbp-68h] BYREF
  int v264; // [rsp+A0h] [rbp-60h]
  CDevice *v265; // [rsp+A8h] [rbp-58h]
  __int128 v266; // [rsp+B0h] [rbp-50h] BYREF
  int v267; // [rsp+C0h] [rbp-40h]
  D3D12_RESOURCE_DESC v268; // [rsp+D0h] [rbp-30h] BYREF

  *(_QWORD *)&v266 = a7;
  v8 = (struct ID3D12Resource *)a2;
  v9 = -2147024809;
  v265 = a4;
  v261 = (struct ID3D12Resource *)a2;
  p_ViewDimension = (__int64)&a3->ViewDimension;
  v253 = *((_DWORD *)a6 + 165);
  v10 = a2 & -(__int64)(a2 != 0);
  v263 = v10;
  if ( !a3 )
  {
    p_ViewDimension = 4;
    goto LABEL_7;
  }
  if ( a3->ViewDimension == (D3D12_SRV_DIMENSION_TEXTURE3D|D3D12_SRV_DIMENSION_TEXTURE2D) )
  {
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::GetImpl'::`2'::impl,
      a2,
      v8);
  }
  if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(a3->Format) )
  {
LABEL_7:
    if ( v8 )
    {
      v12 = (__int64)v8->GetDesc(v8, &v268);
      Format = DXGI_FORMAT_UNKNOWN;
      v14 = *(_WORD *)(v12 + 30);
      v15 = *(_DWORD *)v12;
      v16 = *(_DWORD *)(v12 + 32);
      v262 = *(_QWORD *)(v12 + 16);
      v252 = *(_WORD *)(v12 + 28);
      v264 = *(_DWORD *)(v12 + 44);
      v259 = v14;
      v251 = *(_DWORD *)(v12 + 48);
      v257 = *(_DWORD *)(v12 + 36);
      if ( !a3 )
        goto LABEL_49;
      v17 = &a3->ViewDimension;
LABEL_25:
      v23 = *v17;
      Format = a3->Format;
      if ( (*v17 != D3D12_SRV_DIMENSION_BUFFER && (unsigned int)(v23 - 11) > 1 || v15 != 1)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURE1D || v15 != 2)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURE2D || v15 != 3)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURE3D || v15 != 4)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURECUBE || v15 != 3)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURECUBEARRAY || v15 != 3)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURE2DARRAY || v15 != 3)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURE2DMS || v15 != 3)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURE2DMSARRAY || v15 != 3)
        && (v23 != D3D12_SRV_DIMENSION_TEXTURE1DARRAY || v15 != 2) )
      {
        v24 = "The ViewDimension in the View Desc is incompatible with the type of the Resource.";
        v25 = 32;
LABEL_47:
        TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, v25, v24);
        return 2147942487LL;
      }
LABEL_49:
      v27 = 0;
      LOBYTE(v28) = -120;
      if ( a3 )
      {
        Shader4ComponentMapping = a3->Shader4ComponentMapping;
        v260 = Shader4ComponentMapping;
        if ( (Shader4ComponentMapping & 0xFFFFF000) != 0x1000
          || (Shader4ComponentMapping & 7) >= 6
          || (Shader4ComponentMapping & 0x38) >= 0x30
          || (Shader4ComponentMapping & 0x1C0) >= 0x180
          || (Shader4ComponentMapping & 0xE00) >= 0xC00 )
        {
          v27 = 1;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            27,
            "Shader4ComponentMapping is set to an invalid value.  To create a valid value use the D3D12_ENCODE_SHADER_4_C"
            "OMPONENT_MAPPING(Src0,Src1,Src2,Src3) macro with a value from the D3D12_SHADER_COMPONENT_MAPPING enum in eac"
            "h entry.  Or, for a default 1:1 component mapping, simply use D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING (%#x).",
            5768);
        }
      }
      else
      {
        v260 = 5768;
      }
      v30 = v15 - 1;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          if ( v31 != 1 )
          {
            if ( !a3 )
            {
LABEL_61:
              v32 = 0xFFFFFFFFLL;
              if ( (unsigned int)v16 < 0xC0 )
                v32 = (unsigned int)v16;
              if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v32 + 6) & 0xC00) != 0x800 )
                goto LABEL_66;
              v33 = "A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. De"
                    "fault Desc parameters cannot be used, as a fully qualified Format must be supplied.";
LABEL_65:
              ++v27;
              TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 27, v33);
LABEL_66:
              Format = v16;
              goto LABEL_482;
            }
            if ( Format != v16 )
            {
              if ( v10 )
              {
                v34 = *(_DWORD **)(v10 + 328);
                if ( v34 )
                {
                  v35 = &v34[*(unsigned __int16 *)(v10 + 412)];
                  while ( 1 )
                  {
                    if ( v34 == v35 )
                    {
                      ++v27;
                      GetDebugObjectIdentifierString(&v266, v35, 0xFFFFFFFFLL);
                      Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v36);
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        28,
                        "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was"
                        " created with an explicit format cast list",
                        Format,
                        Name,
                        v38);
                      std::string::_Tidy_deallocate(&v266);
                      goto LABEL_105;
                    }
                    if ( *v34 == Format )
                      break;
                    ++v34;
                  }
                  if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v16)
                    && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(Format) )
                  {
                    v39 = 1;
LABEL_106:
                    if ( (unsigned int)CD3D11FormatHelper::Texture3DSupport(
                                         (unsigned int)Format,
                                         (unsigned int)a5,
                                         v253) == -1 )
                    {
                      ++v27;
                      v60 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v59);
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        28,
                        "The Format (%#x, %s) cannot be used, when creating a View of a Texture3D.",
                        Format,
                        v60);
                    }
                    if ( !v261 )
                      goto LABEL_482;
                    if ( v39 )
                    {
                      MipLevels = a3->Texture1D.MipLevels;
                      if ( MipLevels != 1 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          31,
                          "When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.",
                          MipLevels);
                      }
                    }
                    MostDetailedMip = a3->Texture1D.MostDetailedMip;
                    if ( MostDetailedMip < v259 )
                    {
                      v63 = a3->Texture1D.MipLevels;
                      if ( v63 )
                      {
                        if ( v63 == -1 || v63 <= v259 && MostDetailedMip + v63 <= v259 )
                          goto LABEL_482;
                      }
                    }
                    v64 = "The Dimensions of the View are invalid. MostDetailedMip (value = %u) must be between 0 and Mip"
                          "Levels-1 of the Texture Resource, %hu, inclusively. With the current MostDetailedMip, MipLevel"
                          "s (value = %u) must be between 1 and %u, or -1 to default to all mips from MostDetailedMip, in"
                          "clusively, in order that the View fit on the Texture.";
LABEL_118:
                    ++v27;
                    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 31, v64);
                    goto LABEL_482;
                  }
LABEL_105:
                  v39 = 0;
                  goto LABEL_106;
                }
              }
            }
            v40 = 0xFFFFFFFFLL;
            if ( (unsigned int)v16 < 0xC0 )
              v40 = (unsigned int)v16;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v40 + 6) & 0xC00) == 0xC00 )
            {
              if ( Format == DXGI_FORMAT_UNKNOWN )
              {
                Format = v16;
                goto LABEL_105;
              }
              if ( v16 == Format )
                goto LABEL_105;
              if ( (int)v253 < 6 )
              {
                ++v27;
                D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v28);
                v48 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v51);
                v243 = v52;
                v50 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a full"
                      "y qualified Format, which is not castable (%#x, %s).";
              }
              else
              {
                if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v16 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1) )
                {
                  v41 = 0xFFFFFFFFLL;
                  if ( (unsigned int)Format < 0xC0 )
                    v41 = (unsigned int)Format;
                  if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v41 + 6) & 0xC00) != 0x800 )
                  {
                    v42 = 0xFFFFFFFFLL;
                    if ( (unsigned int)Format < 0xC0 )
                      v42 = (unsigned int)Format;
                    if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v42 + 6) & 0xC00) == 0xC00
                      && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(Format, v16) )
                    {
                      ++v27;
                      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v43);
                      v45 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v44);
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        28,
                        "The resource format (%s) and view format (%s) differ in float vs non-float component interpretat"
                        "ion - this type of format casting is not supported.",
                        v45,
                        v46);
                    }
                    goto LABEL_105;
                  }
                }
                ++v27;
                D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, 5 * Format);
                v48 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v47);
                v243 = v49;
                v50 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within th"
                      "e same family as the Format of the Resource (%#x, %s).";
              }
            }
            else
            {
              if ( Format == DXGI_FORMAT_UNKNOWN )
              {
                ++v27;
                D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v28);
                v48 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v53);
                v243 = v54;
                v55 = 0;
                v50 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the fo"
                      "rmat of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_104:
                TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 28, v50, v55, v48, v16, v243);
                goto LABEL_105;
              }
              if ( v16 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1) )
              {
                v56 = 0xFFFFFFFFLL;
                if ( (unsigned int)Format < 0xC0 )
                  v56 = (unsigned int)Format;
                if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v56 + 6) & 0xC00) != 0x800 )
                  goto LABEL_105;
              }
              ++v27;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v28);
              v48 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v57);
              v243 = v58;
              v50 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable f"
                    "rom the Format of the Resource (%#x, %s).";
            }
            v55 = (unsigned int)Format;
            goto LABEL_104;
          }
          if ( !a3 )
          {
            v65 = 0xFFFFFFFFLL;
            v66 = 0xFFFFFFFFLL;
            if ( (unsigned int)v16 < 0xC0 )
              v66 = (unsigned int)v16;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v66 + 6) & 0xC00) == 0x800 )
            {
              ++v27;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                27,
                "A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Defaul"
                "t Desc parameters cannot be used, as a fully qualified Format must be supplied.");
            }
            if ( (unsigned int)v16 < 0xC0 )
              v65 = (unsigned int)v16;
            if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v65 + 32) & 0x10) == 0 )
              goto LABEL_66;
            v33 = "Views of video formats cannot be created using a NULL Desc. Default Desc parameters cannot be used, as"
                  " a View format must be supplied, not the same as the underlying video format.The View format is needed"
                  " to indicate how the video surface (or part of it) will appear to shaders - see documentation.";
            goto LABEL_65;
          }
          Plane = GetPlaneSlice<D3D12_SHADER_RESOURCE_VIEW_DESC>(a3, (unsigned int)v16);
          v68 = 0xFFFFFFFFLL;
          v69 = Plane;
          if ( (unsigned int)v16 < 0xC0 )
            v68 = (unsigned int)v16;
          v70 = 5 * v68;
          if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v68 + 32) & 0x10) != 0 )
            goto LABEL_179;
          v71 = 0xFFFFFFFFLL;
          if ( (unsigned int)v16 < 0xC0 )
            v71 = (unsigned int)v16;
          if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v71 + 32) & 8) != 0 )
          {
LABEL_179:
            HIDWORD(v247) = DWORD1(v266);
            v104 = ValidateD3DPlanarAndYUVResourceViewFormat(
                     (unsigned int)v16,
                     (unsigned int)Format,
                     (unsigned int)a5,
                     v253,
                     8,
                     Plane);
            if ( !v104 )
              goto LABEL_183;
            ++v27;
            if ( v104 != 3 )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v105);
              v109 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v108);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                28,
                "For the resource format %s, when making a D3D view, the format name for the view can't be %s.  See docum"
                "entation for the set of valid view format names for this resource format, determining which how the reso"
                "urce (or part of it) will appear to shader.",
                v109,
                v110);
              goto LABEL_183;
            }
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v105);
            v91 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v106);
            v93 = 29;
            v241 = v107;
            v94 = "The Plane Slice %u cannot be used when the resource format is %s and the view format is %s.  See docum"
                  "entation for the set of valid view format names for this resource format, determining which how the re"
                  "source (or part of it) will appear to shader.";
            goto LABEL_168;
          }
          if ( Format != v16 )
          {
            if ( v263 )
            {
              v72 = *(_DWORD **)(v263 + 328);
              if ( v72 )
              {
                v73 = &v72[*(unsigned __int16 *)(v263 + 412)];
                while ( 1 )
                {
                  if ( v72 == v73 )
                  {
                    ++v27;
                    GetDebugObjectIdentifierString(&v266, v73, 0xFFFFFFFFLL);
                    v75 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v74);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      28,
                      "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was c"
                      "reated with an explicit format cast list",
                      Format,
                      v75,
                      v76);
                    std::string::_Tidy_deallocate(&v266);
                    goto LABEL_183;
                  }
                  if ( *v72 == Format )
                    break;
                  ++v72;
                }
                if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v16)
                  && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(Format) )
                {
                  v77 = 1;
                  goto LABEL_184;
                }
LABEL_183:
                v77 = 0;
LABEL_184:
                v111 = (_DWORD *)p_ViewDimension;
                if ( !v261 )
                  goto LABEL_202;
                switch ( *(_DWORD *)p_ViewDimension )
                {
                  case 5:
                    if ( v77 )
                    {
                      StructureByteStride = a3->Buffer.StructureByteStride;
                      if ( StructureByteStride != 1 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          31,
                          "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                          StructureByteStride);
                      }
                      v113 = a3->Texture1D.MipLevels;
                      if ( v113 != 1 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          31,
                          "When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.",
                          v113);
                      }
                    }
                    v114 = a3->Texture1D.MostDetailedMip;
                    if ( v114 < v259
                      && (v115 = a3->Texture1D.MipLevels) != 0
                      && (v115 == -1 || v115 <= v259 && v114 + v115 <= v259) )
                    {
                      v116 = v252;
                      NumElements = a3->Buffer.NumElements;
                      if ( NumElements < v252 )
                      {
                        v118 = a3->Buffer.StructureByteStride;
                        if ( v118 )
                        {
                          if ( v118 == -1 || v118 <= v252 && NumElements + v118 <= v252 )
                          {
LABEL_201:
                            v111 = (_DWORD *)p_ViewDimension;
                            goto LABEL_202;
                          }
                        }
                      }
                    }
                    else
                    {
                      v116 = v252;
                    }
                    ++v27;
                    v122 = a3->Texture1D.MostDetailedMip;
                    v123 = v116;
                    if ( v116 >= a3->Buffer.NumElements )
                      v123 = a3->Buffer.NumElements;
                    if ( v259 < v114 )
                      v122 = v259;
                    LODWORD(v247) = a3->Buffer.NumElements;
                    LODWORD(v242) = v259 - v122;
                    LODWORD(v241) = a3->Texture1D.MipLevels;
                    LODWORD(v240) = v259 - 1;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      31,
                      "The Dimensions of the View are invalid due to at least one of the following conditions. MostDetail"
                      "edMip (value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. Wi"
                      "th the current MostDetailedMip, MipLevels (value = %u) must be between 1 and %u, inclusively, or -"
                      "1 to default to all mips from MostDetailedMip, in order that the View fit on the Texture. FirstArr"
                      "aySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %u, inclusively. W"
                      "ith the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or "
                      "-1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.",
                      v114,
                      v240,
                      v241,
                      v242,
                      v247,
                      v116 - 1,
                      a3->Buffer.StructureByteStride,
                      v116 - v123);
                    goto LABEL_201;
                  case 7:
                    if ( v77 )
                    {
                      v124 = a3->Texture1D.MipLevels;
                      if ( v124 != 1 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          31,
                          "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                          v124);
                      }
                    }
                    v125 = a3->Texture1D.MostDetailedMip;
                    if ( v125 >= v252
                      || (v126 = a3->Texture1D.MipLevels) == 0
                      || v126 != -1 && (v126 > v252 || v125 + v126 > v252) )
                    {
                      v127 = "The Dimensions of the View are invalid due to at least one of the following conditions. Fir"
                             "stArraySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, i"
                             "nclusively. With the current FirstArraySlice, ArraySize (value = %u) must be between 1 and "
                             "%u, inclusively, or -1 to default to all slices from FirstArraySlice, in order that the Vie"
                             "w fit on the Texture.";
LABEL_234:
                      ++v27;
                      TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 31, v127);
                      goto LABEL_202;
                    }
                    goto LABEL_202;
                  case 4:
                    goto LABEL_499;
                  case 6:
                    goto LABEL_202;
                  case 9:
LABEL_499:
                    if ( v77 )
                    {
                      v128 = a3->Texture1D.MipLevels;
                      if ( v128 != 1 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          31,
                          "When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.",
                          v128);
                      }
                    }
                    v129 = a3->Texture1D.MostDetailedMip;
                    if ( v129 >= v259
                      || (v130 = a3->Texture1D.MipLevels) == 0
                      || v130 != -1 && (v130 > v259 || v129 + v130 > v259) )
                    {
                      v127 = "The Dimensions of the View are invalid due to at least one of the following conditions. Mos"
                             "tDetailedMip (value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, i"
                             "nclusively. With the current MostDetailedMip, MipLevels (value = %u) must be between 1 and "
                             "%u, inclusively, or -1 to default to all mips from MostDetailedMip, in order that the View "
                             "fit on the Texture.";
                      goto LABEL_234;
                    }
LABEL_202:
                    if ( a5 >= D3D_FEATURE_LEVEL_10_1 )
                      goto LABEL_203;
LABEL_263:
                    if ( (unsigned int)CD3D11FormatHelper::Texture2DSupport(
                                         (unsigned int)Format,
                                         (unsigned int)a5,
                                         v253) != -1 )
                      goto LABEL_270;
                    if ( a5 >= D3D_FEATURE_LEVEL_10_0
                      || Format != DXGI_FORMAT_R16_UNORM && Format != DXGI_FORMAT_R24_UNORM_X8_TYPELESS )
                    {
LABEL_269:
                      ++v27;
                      v141 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v121);
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        28,
                        "The Format (%#x, %s) cannot be used, when creating a View of a Texture2D.",
                        Format,
                        v141);
LABEL_270:
                      if ( v257 > 1 )
                      {
                        if ( (unsigned int)(*v111 - 6) > 1 )
                        {
                          ++v27;
                          TDebugOutputFunctor::operator()(
                            &g_coreRuntimeTallyErrorOutputFunctor,
                            27,
                            "The base resource was created as a multisample resource. You must specify D3D12_SRV_DIMENSIO"
                            "N_TEXTURE2DMSARRAY or D3D12_SRV_DIMENSION_TEXTURE2DMS.");
                        }
                        v142 = v251;
                        if ( a5 < D3D_FEATURE_LEVEL_10_1 && (v251 & 2) != 0 )
                        {
                          ++v27;
                          TDebugOutputFunctor::operator()(
                            &g_coreRuntimeTallyErrorOutputFunctor,
                            27,
                            "When GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less, a ShaderResourceView cannot be "
                            "created for a multisample resource when it is has the D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL flag.");
                        }
                        goto LABEL_483;
                      }
LABEL_482:
                      v142 = v251;
LABEL_483:
                      v263 = (unsigned int)Format;
                      if ( (unsigned int)ValidateShaderResourceViewFormats(&v263, v265, (unsigned int)a5, v253) == -2147024809
                        && (a5 >= D3D_FEATURE_LEVEL_10_0
                         || Format != DXGI_FORMAT_R16_UNORM && Format != DXGI_FORMAT_R24_UNORM_X8_TYPELESS
                         || (v142 & 2) == 0) )
                      {
                        ++v27;
                        v239 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v238);
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          28,
                          "The format (%#x, %s) cannot be used with a ShaderResource view.",
                          Format,
                          v239);
                      }
LABEL_489:
                      if ( (v251 & 8) != 0 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          32,
                          "A ShaderResourceView cannot be created of a Resource that did specify the D3D12_RESOURCE_FLAG_"
                          "DENY_SHADER_RESOURCE MiscFlag.");
                      }
                      if ( v27 )
                        return (unsigned int)-2147024809;
                      else
                        return 0;
                    }
                    v120 = (v251 & 2) == 0;
LABEL_268:
                    if ( !v120 )
                      goto LABEL_270;
                    goto LABEL_269;
                }
                if ( *(_DWORD *)p_ViewDimension != 10 )
                  goto LABEL_202;
                if ( a5 < D3D_FEATURE_LEVEL_10_1 )
                {
                  ++v27;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    27,
                    "Texture cube arrays cannot be created when GetFeatureLevel returns D3D_FEATURE_LEVEL_10_0 or less.");
                  goto LABEL_263;
                }
                if ( v77 )
                {
                  v131 = a3->Buffer.StructureByteStride;
                  if ( v131 != 1 )
                  {
                    ++v27;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      31,
                      "When casting from a compressed format to an uncompressed format, the NumCubes (value = %u) must be 1.",
                      v131);
                  }
                  v132 = a3->Texture1D.MipLevels;
                  if ( v132 != 1 )
                  {
                    ++v27;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      31,
                      "When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.",
                      v132);
                  }
                }
                if ( v252 >= 6u )
                {
                  v133 = a3->Buffer.NumElements;
                  if ( v133 <= (unsigned int)v252 - 6 )
                  {
                    v134 = a3->Buffer.StructureByteStride;
                    if ( !v134 || v134 != -1 && (6 * v134 > v252 || v133 + 6 * v134 > v252) )
                    {
                      ++v27;
                      v135 = o_ceil_0();
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        31,
                        "The Dimensions of the View are invalid because NumCubes (value = %u) must not be 0 and must be n"
                        "o greater than %u.",
                        v134,
                        LODWORD(v135));
                    }
                    v111 = (_DWORD *)p_ViewDimension;
                  }
                  else
                  {
                    ++v27;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      31,
                      "The Dimensions of the View are invalid because First2DArrayFace (value = %u) must be between 0 and"
                      " ArraySize-6 of the Texture Resource, %hu, inclusively.",
                      v133,
                      v252 - 6);
                  }
                  v136 = a3->Texture1D.MostDetailedMip;
                  if ( v136 < v259 )
                  {
                    v137 = a3->Texture1D.MipLevels;
                    if ( (_DWORD)v137
                      && ((_DWORD)v137 == -1 || (unsigned int)v137 <= v259 && v136 + (unsigned int)v137 <= v259) )
                    {
                      goto LABEL_260;
                    }
                    v138 = "The Dimensions of the View are invalid, MipLevels(value = %u) must be between 1 and %u, inclu"
                           "sively, or -1 to default to all mips from MostDetailedMip, in order that the View fit on the Texture.";
                    LODWORD(v240) = v259 - v136;
                  }
                  else
                  {
                    v137 = v136;
                    LODWORD(v240) = v259 - 1;
                    v138 = "The Dimensions of the View are invalid because MostDetailedMip (value = %u) must be between 0"
                           " and MipLevels-1 of the Texture Resource, %hu, inclusively.";
                  }
                  ++v27;
                  TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 31, v138, v137, v240, v241);
                }
                else
                {
                  ++v27;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    31,
                    "The Dimensions of the View are invalid because DepthOrArraySize (value = %hu) is less than 6. DepthO"
                    "rArraySize has to be at least 6.",
                    v252);
                }
LABEL_260:
                if ( (unsigned int)CD3D11FormatHelper::TextureCubeSupport((unsigned int)Format, (unsigned int)a5, v253) != -1 )
                  goto LABEL_204;
                ++v27;
                v140 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v139);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  28,
                  "The Format (%#x, %s) cannot be used, when creating a View of a TextureCube.",
                  Format,
                  v140);
LABEL_203:
                v119 = v253;
LABEL_204:
                if ( (unsigned int)(*v111 - 9) <= 1 )
                  goto LABEL_270;
                v120 = (unsigned int)CD3D11FormatHelper::Texture2DSupport((unsigned int)Format, (unsigned int)a5, v119) == -1;
                goto LABEL_268;
              }
            }
          }
          v78 = 0xFFFFFFFFLL;
          if ( (unsigned int)v16 < 0xC0 )
            v78 = (unsigned int)v16;
          if ( (v67 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v78 + 6)) != v67 )
          {
            if ( Format )
            {
              if ( v16 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1) )
              {
                v100 = 0xFFFFFFFFLL;
                if ( (unsigned int)Format < 0xC0 )
                  v100 = (unsigned int)Format;
                if ( (v67 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v100 + 6)) != 0x800 )
                {
                  if ( !Plane )
                    goto LABEL_183;
                  ++v27;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v70);
                  v91 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v101);
                  v93 = 30;
LABEL_167:
                  v241 = v92;
                  v94 = "The PlaneSlice %u is invalid when the resource format is %s and the view format is %s.  Only Pla"
                        "ne Slice 0 is valid when creating a view on a non-planar format.";
LABEL_168:
                  HIDWORD(v240) = HIDWORD(v91);
                  TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, v93, v94);
                  goto LABEL_183;
                }
              }
              ++v27;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v70);
              v96 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v102);
              v245 = v103;
              v98 = (unsigned int)Format;
              v99 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable f"
                    "rom the Format of the Resource (%#x, %s).";
            }
            else
            {
              ++v27;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v70);
              v96 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v95);
              v245 = v97;
              v98 = 0;
              v99 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the form"
                    "at of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
            }
            TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 28, v99, v98, v96, v16, v245);
            goto LABEL_183;
          }
          if ( Format == DXGI_FORMAT_UNKNOWN )
          {
            Format = v16;
LABEL_165:
            if ( !v69 )
              goto LABEL_183;
            ++v27;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v70);
            v91 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v90);
            v93 = 344;
            goto LABEL_167;
          }
          if ( v16 == Format )
            goto LABEL_165;
          if ( (int)v253 < 6 )
          {
            ++v27;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v70);
            v85 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v88);
            v244 = v89;
            v87 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qu"
                  "alified Format, which is not castable (%#x, %s).";
          }
          else
          {
            v70 = 5 * Format;
            if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v16 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1) )
            {
              v79 = 0xFFFFFFFFLL;
              if ( (unsigned int)Format < 0xC0 )
                v79 = (unsigned int)Format;
              if ( (v67 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v79 + 6)) != 0x800 )
              {
                v80 = 0xFFFFFFFFLL;
                if ( (unsigned int)Format < 0xC0 )
                  v80 = (unsigned int)Format;
                if ( (v67 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v80 + 6)) != v67 )
                  goto LABEL_165;
                if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(Format, v16) )
                {
                  ++v27;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v70);
                  v82 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v81);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    28,
                    "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation "
                    "- this type of format casting is not supported.",
                    v82,
                    v83);
                }
                goto LABEL_164;
              }
            }
            ++v27;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v70);
            v85 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v84);
            v244 = v86;
            v87 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the sa"
                  "me family as the Format of the Resource (%#x, %s).";
          }
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            28,
            v87,
            (unsigned int)Format,
            v85,
            v16,
            v244);
LABEL_164:
          v69 = Plane;
          goto LABEL_165;
        }
        if ( !a3 )
          goto LABEL_61;
        if ( Format != v16 )
        {
          if ( v10 )
          {
            v143 = *(_DWORD **)(v10 + 328);
            if ( v143 )
            {
              v144 = &v143[*(unsigned __int16 *)(v10 + 412)];
              while ( 1 )
              {
                if ( v143 == v144 )
                {
                  ++v27;
                  GetDebugObjectIdentifierString(&v266, v144, 0xFFFFFFFFLL);
                  v146 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v145);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    28,
                    "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was cre"
                    "ated with an explicit format cast list",
                    Format,
                    v146,
                    v147);
                  std::string::_Tidy_deallocate(&v266);
                  goto LABEL_315;
                }
                if ( *v143 == Format )
                  break;
                ++v143;
              }
              if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v16)
                && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(Format) )
              {
                v148 = 1;
LABEL_316:
                if ( (unsigned int)CD3D11FormatHelper::Texture1DSupport((unsigned int)Format, (unsigned int)a5, v253) == -1 )
                {
                  ++v27;
                  v169 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v168);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    28,
                    "The Format (%#x, %s) cannot be used, when creating a View of a Texture1D.",
                    Format,
                    v169);
                }
                if ( !v261 )
                  goto LABEL_482;
                if ( *(_DWORD *)p_ViewDimension == 3 )
                {
                  if ( v148 )
                  {
                    v170 = a3->Buffer.StructureByteStride;
                    if ( v170 != 1 )
                    {
                      ++v27;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        31,
                        "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                        v170);
                    }
                    v171 = a3->Texture1D.MipLevels;
                    if ( v171 != 1 )
                    {
                      ++v27;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        31,
                        "When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.",
                        v171);
                    }
                  }
                  v172 = a3->Texture1D.MostDetailedMip;
                  if ( v172 < v259
                    && (v173 = a3->Texture1D.MipLevels) != 0
                    && (v173 == -1 || v173 <= v259 && v172 + v173 <= v259) )
                  {
                    v174 = v252;
                    v175 = a3->Buffer.NumElements;
                    if ( v175 < v252 )
                    {
                      v176 = a3->Buffer.StructureByteStride;
                      if ( v176 )
                      {
                        if ( v176 == -1 || v176 <= v252 && v175 + v176 <= v252 )
                          goto LABEL_482;
                      }
                    }
                  }
                  else
                  {
                    v174 = v252;
                  }
                  ++v27;
                  v177 = a3->Texture1D.MostDetailedMip;
                  v178 = v174;
                  if ( v174 >= a3->Buffer.NumElements )
                    v178 = a3->Buffer.NumElements;
                  if ( v259 < v172 )
                    v177 = v259;
                  LODWORD(v242) = v259 - v177;
                  LODWORD(v241) = a3->Texture1D.MipLevels;
                  LODWORD(v240) = v259 - 1;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    31,
                    "The Dimensions of the View are invalid due to at least one of the following conditions. MostDetailed"
                    "Mip (value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. With t"
                    "he current MostDetailedMip, MipLevels (value = %u) must be between 1 and %u, inclusively, or -1 to d"
                    "efault to all mips from MostDetailedMip, in order that the View fit on the Texture. FirstArraySlice "
                    "(value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. With the c"
                    "urrent FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or -1 to defau"
                    "lt to all slices from FirstArraySlice, in order that the View fit on the Texture.",
                    v172,
                    v240,
                    v241,
                    v242,
                    a3->Buffer.NumElements,
                    v174 - 1,
                    a3->Buffer.StructureByteStride,
                    v174 - v178);
                  goto LABEL_482;
                }
                if ( v148 )
                {
                  v179 = a3->Texture1D.MipLevels;
                  if ( v179 != 1 )
                  {
                    ++v27;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      31,
                      "When casting from a compressed format to an uncompressed format, the MipLevels (value = %u) must be 1.",
                      v179);
                  }
                }
                v180 = a3->Texture1D.MostDetailedMip;
                if ( v180 < v259 )
                {
                  v181 = a3->Texture1D.MipLevels;
                  if ( v181 )
                  {
                    if ( v181 == -1 || v181 <= v259 && v180 + v181 <= v259 )
                      goto LABEL_482;
                  }
                }
                v64 = "The Dimensions of the View are invalid due to at least one of the following conditions. MostDetail"
                      "edMip (value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. Wi"
                      "th the current MostDetailedMip, MipLevels (value = %u) must be between 1 and %u, inclusively, or -"
                      "1 to default to all mips from MostDetailedMip, in order that the View fit on the Texture.";
                goto LABEL_118;
              }
LABEL_315:
              v148 = 0;
              goto LABEL_316;
            }
          }
        }
        v149 = 0xFFFFFFFFLL;
        if ( (unsigned int)v16 < 0xC0 )
          v149 = (unsigned int)v16;
        if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v149 + 6) & 0xC00) == 0xC00 )
        {
          if ( Format == DXGI_FORMAT_UNKNOWN )
          {
            Format = v16;
            goto LABEL_315;
          }
          if ( v16 == Format )
            goto LABEL_315;
          if ( (int)v253 < 6 )
          {
            ++v27;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v28);
            v157 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v160);
            v246 = v161;
            v159 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully q"
                   "ualified Format, which is not castable (%#x, %s).";
          }
          else
          {
            if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v16 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1) )
            {
              v150 = 0xFFFFFFFFLL;
              if ( (unsigned int)Format < 0xC0 )
                v150 = (unsigned int)Format;
              if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v150 + 6) & 0xC00) != 0x800 )
              {
                v151 = 0xFFFFFFFFLL;
                if ( (unsigned int)Format < 0xC0 )
                  v151 = (unsigned int)Format;
                if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v151 + 6) & 0xC00) == 0xC00
                  && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(Format, v16) )
                {
                  ++v27;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v152);
                  v154 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v153);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    28,
                    "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation "
                    "- this type of format casting is not supported.",
                    v154,
                    v155);
                }
                goto LABEL_315;
              }
            }
            ++v27;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, 5 * Format);
            v157 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v156);
            v246 = v158;
            v159 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the s"
                   "ame family as the Format of the Resource (%#x, %s).";
          }
        }
        else
        {
          if ( Format == DXGI_FORMAT_UNKNOWN )
          {
            ++v27;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v28);
            v157 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v162);
            v246 = v163;
            v164 = 0;
            v159 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the forma"
                   "t of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_314:
            TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 28, v159, v164, v157, v16, v246);
            goto LABEL_315;
          }
          if ( v16 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1) )
          {
            v165 = 0xFFFFFFFFLL;
            if ( (unsigned int)Format < 0xC0 )
              v165 = (unsigned int)Format;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v165 + 6) & 0xC00) != 0x800 )
              goto LABEL_315;
          }
          ++v27;
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v28);
          v157 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v166);
          v246 = v167;
          v159 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable from"
                 " the Format of the Resource (%#x, %s).";
        }
        v164 = (unsigned int)Format;
        goto LABEL_314;
      }
      if ( a3 )
      {
        if ( *(_DWORD *)p_ViewDimension == 11 )
        {
          if ( v261 )
          {
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              32,
              "When ViewDimension is D3D12_SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE, pResource must be NULL, since"
              " the resource location comes from a GPUVA in pDesc.");
            return 2147942487LL;
          }
          if ( !*((_DWORD *)a6 + 202) )
          {
            ++v27;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              27,
              "D3D12_SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE invalid on a device that does not support raytracing.");
          }
          if ( Format == DXGI_FORMAT_UNKNOWN )
          {
            FirstElement = a3->Buffer.FirstElement;
            if ( (_BYTE)FirstElement )
            {
              ++v27;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                31,
                "For D3D12_SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE, the address (%I64u) must be aligned to %d bytes.",
                FirstElement,
                256);
            }
            if ( v260 != 5768 )
            {
              ++v27;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                27,
                "For D3D12_SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE, Shader4ComponentMapping must be D3D12_DEFAULT"
                "_SHADER_4_COMPONENT_MAPPING (%#x) (the field is actually unused).",
                5768);
            }
            goto LABEL_489;
          }
          v24 = "For D3D12_SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE, the format must be DXGI_FORMAT_UNKNOWN.";
LABEL_359:
          v25 = 28;
          goto LABEL_47;
        }
        if ( *(_DWORD *)p_ViewDimension == 12 )
        {
          if ( !CDevice::IsViewCreationByteOffsetSupportedAndImplemented(v265) )
          {
            ++v27;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              31,
              "A shader resource view of D3D12_SRV_DIMENSION_BUFFER_BYTE_OFFSET dimension is not supported by the driver.");
          }
          if ( (*((_BYTE *)&a3->RaytracingAccelerationStructure + 20) & 1) == 0 )
          {
            v183 = *(_QWORD *)&a3->Texture3D.ResourceMinLODClamp;
            if ( !v183 )
            {
              ++v27;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                31,
                "BufferByteOffset.Size cannot be 0.");
              v183 = *(_QWORD *)&a3->Texture3D.ResourceMinLODClamp;
            }
            if ( v261 )
            {
              v184 = a3->Buffer.FirstElement;
              v185 = v262;
              if ( v184 >= v262 )
              {
                ++v27;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  31,
                  "BufferByteOffset.Offset (%I64u) must be less than the buffer size (%I64u).",
                  v184,
                  v262);
                v185 = v262;
              }
              v183 = *(_QWORD *)&a3->Texture3D.ResourceMinLODClamp;
              v186 = a3->Buffer.FirstElement;
              if ( v186 + v183 > v185 )
              {
                ++v27;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  31,
                  "BufferByteOffset.Offset (%I64u) + Size (%I64u) exceeds the buffer size (%I64u).",
                  v186,
                  v183,
                  v185);
                v183 = *(_QWORD *)&a3->Texture3D.ResourceMinLODClamp;
              }
            }
            PlaneSlice = a3->Texture2DArray.PlaneSlice;
            if ( PlaneSlice )
            {
              _BitScanForward(&v188, PlaneSlice);
              v256 = 1 << v188;
              v250 = 1;
              if ( (unsigned int)(1 << v188) > 0x10 )
                v256 = 16;
            }
            else
            {
              v189 = 0xFFFFFFFFLL;
              if ( (unsigned int)Format < 0xC0 )
                v189 = (unsigned int)Format;
              PlaneSlice = *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v189 + 20) >> 3;
              if ( PlaneSlice )
              {
                _BitScanForward(&v190, PlaneSlice);
                v256 = 1 << v190;
              }
              else
              {
                v256 = 1;
              }
              v250 = 0;
            }
            v28 = v183 % PlaneSlice;
            if ( v28 )
            {
              ++v27;
              v248 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v28);
              v194 = "structured";
              if ( !v195 )
                v194 = v193;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                31,
                "BufferByteOffset.Size (%I64u) must be a multiple of (%u) for %s buffers with Format (%#x) %s.",
                v192,
                v191,
                v194,
                Format,
                v248);
            }
            if ( v263 )
            {
              v28 = (a3->Buffer.FirstElement + CResource::PrivateGetImmutableHeapOffset((CResource *)(v263 + 200)))
                  % v256;
              if ( v28 )
              {
                ++v27;
                v249 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v28);
                v198 = "structured";
                if ( !v250 )
                  v198 = "typed";
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  31,
                  "BufferByteOffset.Offset (%I64u) must be %u-byte aligned for %s buffers with Format (%#x) %s.",
                  v197,
                  v196,
                  v198,
                  Format,
                  v249);
              }
              if ( a5 != 4096 )
              {
LABEL_406:
                if ( !a3 )
                {
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    27,
                    "A View of a Buffer cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a"
                    " Format must be supplied.");
                  return 2147942487LL;
                }
                if ( *(_DWORD *)p_ViewDimension == 1 )
                {
                  v202 = a3->Buffer.StructureByteStride;
                  ResourceMinLODClamp = a3->Texture1DArray.ResourceMinLODClamp;
                }
                else
                {
                  ResourceMinLODClamp = 0.0;
                  if ( *(_DWORD *)p_ViewDimension != 12 )
                    goto LABEL_435;
                  v202 = a3->Texture2DArray.PlaneSlice;
                  ResourceMinLODClamp = a3->Texture2DArray.ResourceMinLODClamp;
                }
                v258 = ResourceMinLODClamp;
                if ( v202 )
                {
                  if ( Format )
                  {
                    ++v27;
                    v204 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v28);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      28,
                      "The Format (%#x, %s) is invalid, when creating a View of a Structured Buffer; it must be DXGI_FORMAT_UNKNOWN.",
                      Format,
                      v204);
                  }
                  if ( v258 != 0.0 )
                  {
                    ++v27;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      28,
                      "When the StructuredByteStride is nonzero, no SRV Flags are allowed.");
                  }
                  if ( v260 != 5768 )
                  {
                    ++v27;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      27,
                      "Shader4ComponentMapping must be D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING (%#x) for structured buffers.",
                      5768);
                  }
                  if ( v261 && *(_DWORD *)p_ViewDimension == 1 )
                  {
                    if ( a5 == 4096 )
                    {
                      v205 = a3->Buffer.StructureByteStride;
                      if ( v205 == 2 )
                      {
                        v206 = a3->Buffer.NumElements;
                        v207 = a3->Buffer.FirstElement;
                        if ( (v206 & 1) != 0 || (v207 & 1) != 0 )
                        {
                          ++v27;
                          TDebugOutputFunctor::operator()(
                            &g_coreRuntimeTallyErrorOutputFunctor,
                            31,
                            "Devices with feature level D3D_FEATURE_LEVEL_CORE_1_0 require structured buffer FirstElement"
                            " and NumElements to be a multiple of 2 (0 is allowed) when StructureByteStride is 2, to keep"
                            " the base address 4 byte aligned. FirstElement=%I64u and NumElements=%u specified",
                            v207,
                            v206);
                        }
                      }
                      else if ( (v205 & 3) != 0 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          31,
                          "Devices with feature level D3D_FEATURE_LEVEL_CORE_1_0 require structured buffer StructuredByte"
                          "Stride to be 2 or a multiple of 4 (%u specified)",
                          v205);
                      }
                    }
                    v208 = a3->Buffer.StructureByteStride;
                    v209 = a3->Buffer.FirstElement;
                    v210 = 8 * v208;
                    v211 = 8 * (0xFFFFFFFF / (8 * v208));
                    if ( v209 > v211
                      || (v209 * v210) >> 3 >= v262
                      || !a3->Buffer.NumElements
                      || (v212 = a3->Buffer.NumElements, v213 = v209 + v212, v209 + v212 < v212)
                      || v213 > v211
                      || v213 * v210 > 8 * v262 )
                    {
                      ++v27;
                      v214 = 8 * v262 / v210;
                      v215 = a3->Buffer.FirstElement;
                      if ( v214 < v209 )
                        v215 = 8 * v262 / v210;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        31,
                        "The Dimensions of the View are invalid due to at least one of the following conditions. Assuming"
                        " StructureByteStride %u, FirstElement (value = %I64u) must be between 0 and the maximum offset o"
                        "f the Buffer, %I64u, inclusively. With the current FirstElement, NumElements (value = %u) must b"
                        "e between 1 and %I64u, inclusively, in order that the View fit on the Buffer.",
                        v208,
                        v209,
                        v214 - 1,
                        a3->Buffer.NumElements,
                        v214 - v215);
                    }
                  }
                  goto LABEL_489;
                }
LABEL_435:
                if ( (LOBYTE(ResourceMinLODClamp) & 1) != 0 )
                {
                  if ( Format != DXGI_FORMAT_R32_TYPELESS )
                  {
                    v24 = "When creating a RAW Shader Resource View, the format must be DXGI_FORMAT_R32_TYPELESS.";
                    goto LABEL_359;
                  }
                  v216 = 0;
                  if ( (*((_BYTE *)a6 + 688) & 0x14) != 0 )
                    goto LABEL_449;
                  if ( v263 )
                  {
                    ImmutableHeapOffset = CResource::PrivateGetImmutableHeapOffset((CResource *)(v263 + 200));
                    if ( (ImmutableHeapOffset & 0xF) != 0 )
                    {
                      ++v27;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        32,
                        "When creating a RAW Shader Resource View, the underlying resource must be aligned to %u bytes.Th"
                        "e heap offset of the resource was actually %I64u, which does not meet this requirement.",
                        16,
                        ImmutableHeapOffset);
                    }
                  }
                  if ( *(_DWORD *)p_ViewDimension == 1 )
                  {
                    v218 = a3->Buffer.FirstElement;
                    if ( (v218 & 3) == 0 )
                      goto LABEL_449;
                    LODWORD(v241) = 4;
                    v219 = "When creating a RAW Shader Resource View, the offset of the first element from the start of t"
                           "he buffer must be a multiple of %u bytes.  Thus, FirstElement (%I64u) must be a multiple of %"
                           "u since each element is 4 bytes.";
                  }
                  else
                  {
                    if ( *(_DWORD *)p_ViewDimension != 12 || (v218 = a3->Buffer.FirstElement, (v218 & 0xF) == 0) )
                    {
LABEL_449:
                      if ( v260 != 5768 )
                      {
                        ++v27;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          27,
                          "Shader4ComponentMapping must be D3D12_DEFAULT_SHADER_4_COMPONENT_MAPPING (%#x) for raw buffers.",
                          5768);
                      }
                      goto LABEL_467;
                    }
                    v219 = "When creating a RAW Shader Resource View, the offset of the view from the start of the buffer"
                           " must be a multiple of %u bytes.  Thus, Offset (%I64u) must be a multiple of %u.";
                    LODWORD(v241) = 16;
                  }
                  ++v27;
                  TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 31, v219, 16, v218, v241);
                  goto LABEL_449;
                }
                if ( ResourceMinLODClamp != 0.0 )
                {
                  ++v27;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    27,
                    "Invalid Buffer SRV Flags combination: (%#x)",
                    ResourceMinLODClamp);
                  goto LABEL_466;
                }
                if ( a5 == 4096 )
                {
                  ++v27;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    27,
                    "Devices with feature level D3D_FEATURE_LEVEL_CORE_1_0 do not support typed buffer views.  Only raw a"
                    "nd structured buffer views are supported.");
                }
                v220 = CD3D11FormatHelper::BufferSupport((unsigned int)Format, (unsigned int)a5, v253);
                v222 = 0;
                LODWORD(v266) = Format;
                *(_QWORD *)((char *)&v266 + 4) = 0;
                if ( v220 == -2 )
                {
                  CDevice::CheckFeatureSupport(v265, D3D12_FEATURE_FORMAT_SUPPORT, &v266, 0xCu);
                  v222 = BYTE4(v266);
                  v220 = -2;
                }
                else if ( v220 == -1 )
                {
                  goto LABEL_464;
                }
                if ( Format && (v220 != -2 || (v222 & 1) != 0) )
                {
                  v223 = 0xFFFFFFFFLL;
                  if ( (unsigned int)Format < 0xC0 )
                    v223 = (unsigned int)Format;
                  if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v223 + 6) & 0xC00) == 0x800 )
                  {
                    ++v27;
                    v224 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v221);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      28,
                      "The Format (%#x, %s) is invalid, when creating a View; it is a typeless format",
                      Format,
                      v224);
                  }
LABEL_466:
                  v216 = 1;
                  if ( (unsigned int)Format >= 0xC0 )
                  {
                    v226 = 0xFFFFFFFFLL;
                    goto LABEL_469;
                  }
LABEL_467:
                  v226 = (unsigned int)Format;
LABEL_469:
                  if ( v261 )
                  {
                    if ( *(_DWORD *)p_ViewDimension == 1 )
                    {
                      v227 = a3->Buffer.FirstElement;
                      v228 = *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v226 + 20);
                      v229 = 8 * (0xFFFFFFFF / (unsigned int)v228);
                      if ( v227 > v229
                        || (v227
                          * *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v226 + 20)) >> 3 >= v262
                        || !a3->Buffer.NumElements
                        || (v230 = a3->Buffer.NumElements, v231 = v230 + v227, v230 + v227 < v230)
                        || v231 > v229
                        || (unsigned int)v228 * v231 > 8 * v262 )
                      {
                        ++v27;
                        v232 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, 8 * v262 % v228);
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          31,
                          "The Dimensions of the View are invalid due to at least one of the following conditions. Assumi"
                          "ng this Format (%#x, %s), FirstElement (value = %I64u) must be between 0 and the maximum offse"
                          "t of the Buffer, %I64u, inclusively. With the current FirstElement, NumElements (value = %u) m"
                          "ust be between 1 and %u, inclusively, in order that the View fit on the Buffer.",
                          Format,
                          v232,
                          v235,
                          v234,
                          a3->Buffer.NumElements,
                          v233);
                      }
                    }
                  }
                  if ( v264 == 2
                    && (unsigned int)CD3D11FormatHelper::TiledResourceSupport(
                                       (unsigned int)Format,
                                       1,
                                       1,
                                       (unsigned int)a5,
                                       v253) == -1 )
                  {
                    ++v27;
                    v237 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v236);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      28,
                      "The Format (%#x, %s) cannot be used with a Tiled Resource.",
                      Format,
                      v237);
                  }
                  if ( !v216 )
                    goto LABEL_489;
                  goto LABEL_482;
                }
LABEL_464:
                v225 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v221);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  28,
                  "The Format (%#x, %s) cannot be used, when creating a View of a Buffer.",
                  Format,
                  v225);
                return 2147942487LL;
              }
              Flags = a3->Buffer.Flags;
              if ( Flags == 2 )
              {
                v200 = a3->Buffer.FirstElement;
                if ( (((unsigned __int8)v200 | LOBYTE(a3->Texture3D.ResourceMinLODClamp)) & 1) != 0 )
                {
                  ++v27;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    31,
                    "Devices with feature level D3D_FEATURE_LEVEL_CORE_1_0 require structured buffer Offset and Size to b"
                    "e a multiple of 2 (0 is allowed) when StructureByteStride is 2, to keep the base address 4 byte alig"
                    "ned. FirstElement=%I64u and NumElements=%u specified",
                    v200,
                    *(_QWORD *)&a3->Texture3D.ResourceMinLODClamp);
                }
              }
              else if ( (Flags & 3) != 0 )
              {
                ++v27;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  31,
                  "Devices with feature level D3D_FEATURE_LEVEL_CORE_1_0 require structured buffer StructuredByteStride t"
                  "o be 2 or a multiple of 4 (%u specified)",
                  Flags);
                goto LABEL_401;
              }
LABEL_402:
              if ( v261 )
              {
                if ( !*((_DWORD *)v265 + 446) )
                {
                  v267 = 0;
                  v201 = v261->__vftable;
                  v266 = 0;
                  v201->GetHeapProperties(v261, (D3D12_HEAP_PROPERTIES *)&v266, 0);
                  if ( (_DWORD)v266 != 1 )
                  {
                    ++v27;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      32,
                      "Devices with feature level D3D_FEATURE_LEVEL_CORE_1_0 only support creating shader resource views "
                      "on resources created from default heaps.");
                  }
                }
              }
              goto LABEL_406;
            }
          }
        }
        else if ( (v251 & 0x100) != 0 )
        {
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            32,
            "Resources created with the D3D12_RESOURCE_FLAG_RAYTRACING_ACCELERATION_STRUCTURE flag can only be used to cr"
            "eate SRVs with SRV_DIMENSION_RAYTRACING_ACCELERATION_STRUCTURE.");
        }
      }
LABEL_401:
      if ( a5 != 4096 )
        goto LABEL_406;
      goto LABEL_402;
    }
    if ( !a3 )
    {
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        32,
        "A ShaderResourceView cannot be created from a NULL Resource and NULL Desc.",
        6);
      return v9;
    }
    v17 = &a3->ViewDimension;
    v262 = 1;
    ViewDimension = a3->ViewDimension;
    v252 = 1;
    v259 = 1;
    v257 = 1;
    v264 = 0;
    LOWORD(v251) = 0;
    if ( ViewDimension > D3D12_SRV_DIMENSION_TEXTURE2DMSARRAY )
    {
      v22 = ViewDimension - 8;
      if ( !v22 )
      {
        v15 = 4;
        goto LABEL_24;
      }
      if ( (unsigned int)(v22 - 1) < 2 )
        goto LABEL_17;
    }
    else
    {
      if ( ViewDimension == D3D12_SRV_DIMENSION_TEXTURE2DMSARRAY )
        goto LABEL_19;
      v19 = ViewDimension - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( !v20 || (v21 = v20 - 1) == 0 )
        {
          v15 = 2;
          goto LABEL_24;
        }
        if ( (unsigned int)(v21 - 1) <= 1 )
        {
LABEL_17:
          v15 = 3;
LABEL_24:
          v16 = a3->Format;
          p_ViewDimension = (__int64)&a3->ViewDimension;
          goto LABEL_25;
        }
LABEL_19:
        v257 = 2;
        goto LABEL_17;
      }
    }
    v15 = 1;
    goto LABEL_24;
  }
  TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 26, "The Format (%#x) is unrecognized.", v11);
  return v9;
}

```

## disassembly

```asm
0x18002fe64  mov     [rsp-8+arg_0], rbx
0x18002fe69  push    rbp
0x18002fe6a  push    rsi
0x18002fe6b  push    rdi
0x18002fe6c  push    r12
0x18002fe6e  push    r13
0x18002fe70  push    r14
0x18002fe72  push    r15
0x18002fe74  lea     rbp, [rsp-10h]
0x18002fe79  sub     rsp, 110h
0x18002fe80  mov     rax, cs:__security_cookie
0x18002fe87  xor     rax, rsp
0x18002fe8a  mov     [rbp+40h+var_38], rax
0x18002fe8e  mov     rax, [rbp+40h+arg_30]
0x18002fe95  mov     r15, r8
0x18002fe98  mov     qword ptr [rbp+40h+var_90], rax
0x18002fe9c  mov     r8, rdx
0x18002fe9f  mov     rax, [rbp+40h+arg_28]
0x18002fea3  mov     edi, 80070057h
0x18002fea8  mov     [rbp+40h+var_98], r9
0x18002feac  lea     rbx, [r15+4]
0x18002feb0  mov     [rbp+40h+var_B8], rdx
0x18002feb4  mov     [rsp+140h+var_D0], rbx
0x18002feb9  mov     eax, [rax+294h]
0x18002febf  mov     [rsp+140h+var_D4], eax
0x18002fec3  mov     rax, rdx
0x18002fec6  neg     rax
0x18002fec9  sbb     r13, r13
0x18002fecc  and     r13, rdx
0x18002fecf  mov     [rbp+40h+var_A8], r13
0x18002fed3  test    r15, r15
0x18002fed6  jz      short loc_18002FF1B
0x18002fed8  cmp     dword ptr [rbx], 0Ch
0x18002fedb  jnz     short loc_18002FEEF
0x18002fedd  mov     dl, 1
0x18002fedf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12RevisedViewCreation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12RevisedViewCreation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12RevisedViewCreation> `wil::Feature<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::GetImpl(void)'::`2'::impl
0x18002fee6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12RevisedViewCreation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002feeb  mov     r8, [rbp+40h+var_B8]
0x18002feef  mov     r9d, [r15]
0x18002fef2  mov     ecx, r9d; enum DXGI_FORMAT
0x18002fef5  call    ?FormatExists@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(DXGI_FORMAT)
0x18002fefa  test    al, al
0x18002fefc  jnz     short loc_18002FF20
0x18002fefe  lea     r8, aTheFormatXIsUn; "The Format (%#x) is unrecognized."
0x18002ff05  mov     edx, 1Ah
0x18002ff0a  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18002ff11  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18002ff16  jmp     loc_180031C23
0x18002ff1b  mov     [rsp+140h+var_D0], rbx
0x18002ff20  mov     r9d, 6
0x18002ff26  test    r8, r8
0x18002ff29  jz      short loc_18002FF91
0x18002ff2b  mov     rax, [r8]
0x18002ff2e  lea     rdx, [rbp+40h+var_70]
0x18002ff32  mov     rcx, r8
0x18002ff35  mov     rax, [rax+50h]
0x18002ff39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff3e  xor     edi, edi
0x18002ff40  mov     r8, [rax+10h]
0x18002ff44  movzx   r9d, word ptr [rax+1Eh]
0x18002ff49  mov     r12d, [rax]
0x18002ff4c  mov     r14d, [rax+20h]
0x18002ff50  mov     [rbp+40h+var_B0], r8
0x18002ff54  movzx   r8d, word ptr [rax+1Ch]
0x18002ff59  mov     [rsp+140h+var_D8], r8d
0x18002ff5e  mov     r8d, [rax+2Ch]
0x18002ff62  mov     [rbp+40h+var_A0], r8d
0x18002ff66  mov     r8d, [rax+30h]
0x18002ff6a  mov     [rbp+40h+var_C0], r9d
0x18002ff6e  mov     r9d, [rax+24h]
0x18002ff72  mov     [rsp+140h+var_DC], r8d
0x18002ff77  mov     [rsp+140h+var_C4], r9d
0x18002ff7c  test    r15, r15
0x18002ff7f  jz      loc_1800300CD
0x18002ff85  mov     rdx, rbx
0x18002ff88  lea     r9d, [rdi+6]
0x18002ff8c  jmp     loc_18003002D
0x18002ff91  test    r15, r15
0x18002ff94  jz      loc_180031C0B
0x18002ff9a  lea     rdx, [r15+4]
0x18002ff9e  mov     [rbp+40h+var_B0], 1
0x18002ffa6  mov     ecx, [rdx]
0x18002ffa8  mov     [rsp+140h+var_D8], 1
0x18002ffb0  mov     [rbp+40h+var_C0], 1
0x18002ffb7  mov     [rsp+140h+var_C4], 1
0x18002ffbf  mov     [rbp+40h+var_A0], 0
0x18002ffc6  mov     [rsp+140h+var_DC], 0
0x18002ffce  cmp     ecx, 7
0x18002ffd1  jg      short loc_180030008
0x18002ffd3  jz      short loc_18002FFFE
0x18002ffd5  sub     ecx, 1
0x18002ffd8  jz      short loc_180030017
0x18002ffda  sub     ecx, 1
0x18002ffdd  jz      short loc_18002FFF6
0x18002ffdf  sub     ecx, 1
0x18002ffe2  jz      short loc_18002FFF6
0x18002ffe4  sub     ecx, 1
0x18002ffe7  jz      short loc_18002FFEE
0x18002ffe9  cmp     ecx, 1
0x18002ffec  jnz     short loc_18002FFFE
0x18002ffee  mov     r12d, 3
0x18002fff4  jmp     short loc_180030025
0x18002fff6  mov     r12d, 2
0x18002fffc  jmp     short loc_180030025
0x18002fffe  mov     [rsp+140h+var_C4], 2
0x180030006  jmp     short loc_18002FFEE
0x180030008  sub     ecx, 8
0x18003000b  jz      short loc_18003001F
0x18003000d  sub     ecx, 1
0x180030010  jz      short loc_18002FFEE
0x180030012  sub     ecx, 1
0x180030015  jz      short loc_18002FFEE
0x180030017  mov     r12d, 1
0x18003001d  jmp     short loc_180030025
0x18003001f  mov     r12d, 4
0x180030025  mov     r14d, [r15]
0x180030028  mov     [rsp+140h+var_D0], rdx
0x18003002d  mov     ecx, [rdx]
0x18003002f  mov     edi, [r15]
0x180030032  cmp     ecx, 1
0x180030035  jz      short loc_18003003F
0x180030037  lea     eax, [rcx-0Bh]
0x18003003a  cmp     eax, 1
0x18003003d  ja      short loc_180030049
0x18003003f  cmp     r12d, 1
0x180030043  jz      loc_1800300CD
0x180030049  cmp     ecx, 2
0x18003004c  jnz     short loc_180030053
0x18003004e  cmp     r12d, ecx
0x180030051  jz      short loc_1800300CD
0x180030053  cmp     ecx, 4
0x180030056  jnz     short loc_18003005E
0x180030058  cmp     r12d, 3
0x18003005c  jz      short loc_1800300CD
0x18003005e  cmp     ecx, 8
0x180030061  jnz     short loc_180030069
0x180030063  cmp     r12d, 4
0x180030067  jz      short loc_1800300CD
0x180030069  cmp     ecx, 9
0x18003006c  jnz     short loc_180030074
0x18003006e  cmp     r12d, 3
0x180030072  jz      short loc_1800300CD
0x180030074  cmp     ecx, 0Ah
0x180030077  jnz     short loc_18003007F
0x180030079  cmp     r12d, 3
0x18003007d  jz      short loc_1800300CD
0x18003007f  cmp     ecx, 5
0x180030082  jnz     short loc_18003008A
0x180030084  cmp     r12d, 3
0x180030088  jz      short loc_1800300CD
0x18003008a  cmp     ecx, r9d
0x18003008d  jnz     short loc_180030095
0x18003008f  cmp     r12d, 3
0x180030093  jz      short loc_1800300CD
0x180030095  cmp     ecx, 7
0x180030098  jnz     short loc_1800300A0
0x18003009a  cmp     r12d, 3
0x18003009e  jz      short loc_1800300CD
0x1800300a0  cmp     ecx, 3
0x1800300a3  jnz     short loc_1800300AB
0x1800300a5  cmp     r12d, 2
0x1800300a9  jz      short loc_1800300CD
0x1800300ab  lea     r8, aTheViewdimensi; "The ViewDimension in the View Desc is i"...
0x1800300b2  mov     edx, 20h ; ' '
0x1800300b7  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800300be  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800300c3  mov     eax, 80070057h
0x1800300c8  jmp     loc_180031C25
0x1800300cd  xor     ebx, ebx
0x1800300cf  lea     rsi, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x1800300d6  mov     [rsp+140h+var_E0], bl
0x1800300da  mov     edx, 1688h; bool
0x1800300df  mov     r10d, 0C00h
0x1800300e5  lea     r11d, [rbx+1Bh]
0x1800300e9  test    r15, r15
0x1800300ec  jz      short loc_180030155
0x1800300ee  mov     ecx, [r15+8]
0x1800300f2  mov     eax, ecx
0x1800300f4  and     eax, 0FFFFF000h
0x1800300f9  mov     [rbp+40h+var_BC], ecx
0x1800300fc  cmp     eax, 1000h
0x180030101  jnz     short loc_18003012F
0x180030103  mov     eax, ecx
0x180030105  and     eax, 7
0x180030108  cmp     al, 6
0x18003010a  jnb     short loc_18003012F
0x18003010c  mov     eax, ecx
0x18003010e  and     eax, 38h
0x180030111  cmp     al, 30h ; '0'
0x180030113  jnb     short loc_18003012F
0x180030115  mov     eax, ecx
0x180030117  and     eax, 1C0h
0x18003011c  cmp     eax, 180h
0x180030121  jnb     short loc_18003012F
0x180030123  mov     eax, ecx
0x180030125  and     eax, 0E00h
0x18003012a  cmp     eax, r10d
0x18003012d  jb      short loc_180030158
0x18003012f  mov     r9d, edx
0x180030132  lea     r8, aShader4compone_0; "Shader4ComponentMapping is set to an in"...
0x180030139  mov     edx, r11d
0x18003013c  mov     rcx, rsi
0x18003013f  mov     ebx, 1
0x180030144  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180030149  mov     r10d, 0C00h
0x18003014f  lea     r11d, [rbx+1Ah]
0x180030153  jmp     short loc_180030158
0x180030155  mov     [rbp+40h+var_BC], edx
0x180030158  mov     ecx, 20h ; ' '
0x18003015d  sub     r12d, 1
0x180030161  jz      loc_1800312B0
0x180030167  sub     r12d, 1
0x18003016b  jz      loc_180030E65
0x180030171  cmp     r12d, 1
0x180030175  jz      loc_180030515
0x18003017b  test    r15, r15
0x18003017e  jnz     short loc_1800301C6
0x180030180  or      eax, 0FFFFFFFFh
0x180030183  lea     r12, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x18003018a  mov     r13d, 0C0h
0x180030190  cmp     r14d, r13d
0x180030193  cmovb   eax, r14d
0x180030197  lea     rax, [rax+rax*4]
0x18003019b  mov     eax, [r12+rax*8+18h]
0x1800301a0  and     eax, r10d
0x1800301a3  cmp     eax, 800h
0x1800301a8  jnz     short loc_1800301BE
0x1800301aa  lea     r8, aAViewCannotBeC; "A View cannot be created using a NULL D"...
0x1800301b1  mov     edx, r11d
0x1800301b4  inc     ebx
0x1800301b6  mov     rcx, rsi
0x1800301b9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800301be  mov     edi, r14d
0x1800301c1  jmp     loc_180031B61
0x1800301c6  or      r8d, 0FFFFFFFFh
0x1800301ca  cmp     edi, r14d
0x1800301cd  jz      loc_18003027C
0x1800301d3  test    r13, r13
0x1800301d6  jz      loc_18003027C
0x1800301dc  mov     rcx, [r13+148h]
0x1800301e3  test    rcx, rcx
0x1800301e6  jz      loc_18003027C
0x1800301ec  movzx   eax, word ptr [r13+19Ch]
0x1800301f4  lea     rdx, [rcx+rax*4]
0x1800301f8  jmp     short loc_180030202
0x1800301fa  cmp     [rcx], edi
0x1800301fc  jz      short loc_180030255
0x1800301fe  add     rcx, 4
0x180030202  cmp     rcx, rdx
0x180030205  jnz     short loc_1800301FA
0x180030207  lea     rcx, [rbp+40h+var_90]
0x18003020b  inc     ebx
0x18003020d  call    ?GetDebugObjectIdentifierString@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUID3D12DeviceChild@@@Z; GetDebugObjectIdentifierString(ID3D12DeviceChild *)
0x180030212  mov     r8, rax
0x180030215  cmp     qword ptr [rax+18h], 0Fh
0x18003021a  jbe     short loc_18003021F
0x18003021c  mov     r8, [rax]
0x18003021f  mov     ecx, edi; enum DXGI_FORMAT
0x180030221  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180030226  mov     [rsp+140h+var_118], r8
0x18003022b  mov     edx, 1Ch
0x180030230  lea     r8, aTheViewFormatX; "The view format (%#x, %s) was not speci"...
0x180030237  mov     [rsp+140h+var_120], rax
0x18003023c  mov     rcx, rsi
0x18003023f  mov     r9d, edi
0x180030242  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180030247  lea     rcx, [rbp+40h+var_90]
0x18003024b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180030250  jmp     loc_18003043B
0x180030255  mov     ecx, r14d; enum DXGI_FORMAT
0x180030258  call    ?IsBlockCompressFormat@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(DXGI_FORMAT)
0x18003025d  test    al, al
0x18003025f  jz      loc_18003043B
0x180030265  mov     ecx, edi; enum DXGI_FORMAT
0x180030267  call    ?IsBlockCompressFormat@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(DXGI_FORMAT)
0x18003026c  test    al, al
0x18003026e  jnz     loc_18003043B
0x180030274  mov     r12b, 1
0x180030277  jmp     loc_180030440
0x18003027c  mov     eax, r8d
0x18003027f  lea     r12, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180030286  mov     r13d, 0C0h
0x18003028c  cmp     r14d, r13d
0x18003028f  cmovb   eax, r14d
0x180030293  lea     rax, [rax+rax*4]
0x180030297  mov     eax, [r12+rax*8+18h]
0x18003029c  and     eax, r10d
0x18003029f  cmp     eax, r10d
0x1800302a2  jnz     loc_1800303AE
0x1800302a8  test    edi, edi
0x1800302aa  jnz     short loc_1800302B4
0x1800302ac  mov     edi, r14d
0x1800302af  jmp     loc_18003043B
0x1800302b4  cmp     r14d, edi
0x1800302b7  jz      loc_18003043B
0x1800302bd  cmp     [rsp+140h+var_D4], 6
0x1800302c2  jl      loc_18003038C
0x1800302c8  movsxd  rax, edi
0x1800302cb  lea     rdx, [rax+rax*4]; bool
0x1800302cf  movsxd  rax, r14d
  ... truncated ...
```
