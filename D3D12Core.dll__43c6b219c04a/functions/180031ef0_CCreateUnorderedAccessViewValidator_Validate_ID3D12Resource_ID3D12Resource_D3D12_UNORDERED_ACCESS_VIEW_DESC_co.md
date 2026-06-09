# CCreateUnorderedAccessViewValidator::Validate(ID3D12Resource *,ID3D12Resource *,D3D12_UNORDERED_ACCESS_VIEW_DESC const *,CDevice *,D3D_FEATURE_LEVEL,DeviceValidationInfo const &,bool *)

- ea: `0x180031ef0`
- end: `0x180033a62`
- name: `?Validate@CCreateUnorderedAccessViewValidator@@QEAA_NPEAUID3D12Resource@@0PEBUD3D12_UNORDERED_ACCESS_VIEW_DESC@@PEAVCDevice@@W4D3D_FEATURE_LEVEL@@AEBUDeviceValidationInfo@@PEA_N@Z`
- size: `7026`
- prototype: `bool __fastcall(CCreateUnorderedAccessViewValidator *__hidden this, struct ID3D12Resource *, struct ID3D12Resource *, const struct D3D12_UNORDERED_ACCESS_VIEW_DESC *, struct CDevice *, enum D3D_FEATURE_LEVEL, const struct DeviceValidationInfo *, bool *)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800ec358`

## callees

- `0x180025f90`
- `0x180026410`
- `0x1800264c0`
- `0x1800268f0`
- `0x1800269d0`
- `0x18002ef50`
- `0x180031e4c`
- `0x180031ec0`
- `0x180031ef0`
- `0x180033a70`
- `0x18003e900`
- `0x18003eb58`
- `0x180048934`
- `0x18004b950`
- `0x180078b10`
- `0x18007b6e8`
- `0x18009fd4c`
- `0x1800aa248`
- `0x1800abc10`
- `0x1800bb480`
- `0x1800fa540`
- `0x180262020`

## string_xrefs

- `0x1800322e3`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x18003272e`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x180032cf3`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x1800331c5`: `An unordered access view of D3D12_UAV_DIMENSION_BUFFER_BYTE_OFFSET dimension is not supported by the driver.`
- `0x180032ad4`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180032b9d`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180032f99`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180032641`: `Views of video formats cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a View format must be supplied, not the same as the underlying video format.The View format is needed to indicate how the video surface (or part of it) will appear to shaders - see documentation.`
- `0x18003225b`: `A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default Desc parameters cannot be used, as a fully qualified Format must be supplied.`
- `0x180032611`: `A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default Desc parameters cannot be used, as a fully qualified Format must be supplied.`
- `0x180032e87`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x180032406`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x180032867`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x180032e3d`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x1800321a0`: `Counter UAVs require a non-NULL D3D12_UNORDERED_ACCESS_VIEW_DESC.`
- `0x1800330be`: `Devices with feature level D3D_FEATURE_LEVEL_1_0_CORE/GENERIC only support creating unordered access views on resources created from default heaps.`
- `0x1800320fe`: `The ViewDimension in the View Desc is incompatible with the type of the Resource or View.`
- `0x180033a20`: `An UnorderedAccessView cannot be created from a NULL Resource and NULL Desc.`
- `0x180033517`: `When creating a RAW Unordered Access View with byte offset, the offset of the resource + BufferByteOffset.Offsetmust be a multiple of %u bytes.`
- `0x1800334e4`: `When creating a RAW Unordered Access View, the underlying resource must be aligned to %u bytes.The heap offset of the resource was actually %I64u, which does not meet this requirement.`
- `0x180033560`: `When creating a RAW Unordered Access View, the offset of the first element from the start of the buffer must be a multiple of %u bytes.  Thus, FirstElement (%I64u) must be a multiple of %u since each element is 4 bytes.`
- `0x180033175`: `Resources created with the D3D12_RESOURCE_FLAG_RAYTRACING_ACCELERATION_STRUCTURE flag set cannot be used as a UAV resource.`
- `0x180033458`: `A View of a non-Structured Buffer cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a Format must be supplied.`
- `0x180033491`: `When creating a RAW Unordered Access View, the format must be DXGI_FORMAT_R32_TYPELESS.`
- `0x180033470`: `When creating a Counter Unordered Access View, the StructureByteStride on the view must be non-zero.`
- `0x1800339dc`: `A UnorderedAccessView cannot be created of a Resource that did not specify the D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS Flag.`
- `0x180033818`: `The format (%#x, %s) cannot be used with a Typed Unordered Access View.  This is because the current graphics implementation does not even support this Format.  Therefore this format does not support Unordered Access Views. Use CheckFormatSupport to check Format support.`
- `0x180033a00`: `A UnorderedAccessView cannot be created with a counter Resource that did not specify the D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS Flag.`
- `0x180032450`: `The Format (%#x, %s) is invalid, when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x1800328a6`: `The Format (%#x, %s) is invalid, when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x180032c63`: `The base resource was created as a multisample resource. You must specify D3D12_UAV_DIMENSION_TEXTURE2DMSARRAY or D3D12_UAV_DIMENSION_TEXTURE2DMS.`
- `0x1800337eb`: `The format (%#x, %s) cannot be used with a Typed Unordered Access View.`

## pseudocode

```c
char __fastcall CCreateUnorderedAccessViewValidator::Validate(
        CCreateUnorderedAccessViewValidator *this,
        unsigned __int64 a2,
        struct ID3D12Resource *a3,
        const struct D3D12_UNORDERED_ACCESS_VIEW_DESC *a4,
        struct CDevice *a5,
        enum D3D_FEATURE_LEVEL a6,
        const struct DeviceValidationInfo *a7,
        bool *a8)
{
  D3D12_UAV_DIMENSION *p_ViewDimension; // rdi
  char v10; // si
  struct ID3D12Resource *v11; // r8
  int v12; // r9d
  int v13; // ebx
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  unsigned __int16 v16; // r10
  unsigned __int16 v17; // r9
  int v18; // r13d
  enum DXGI_FORMAT Format; // r14d
  enum DXGI_FORMAT v20; // edi
  D3D12_UAV_DIMENSION ViewDimension; // ecx
  __int32 v22; // ecx
  __int32 v23; // ecx
  __int32 v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  bool v29; // zf
  struct ID3D12Resource *v30; // rcx
  __int64 v31; // rax
  __int128 v32; // xmm6
  UINT64 CounterOffsetInBytes; // rax
  int v34; // r13d
  int v35; // r13d
  __int64 v36; // rax
  const char *v37; // r8
  _DWORD *v38; // rcx
  _DWORD *v39; // rdx
  bool v40; // dl
  const char *v41; // rax
  const char *v42; // r8
  __int64 v43; // rax
  bool v44; // dl
  int v45; // r8d
  unsigned int v46; // r9d
  unsigned int v47; // r10d
  int v48; // r11d
  __int64 v49; // rax
  bool v50; // dl
  const char *v51; // rax
  __int64 v52; // r8
  const char *v53; // r8
  __int64 v54; // rax
  bool v55; // dl
  bool v56; // dl
  const char *v57; // rax
  const char *v58; // r8
  bool v59; // dl
  enum DXGI_FORMAT v60; // ecx
  bool v61; // dl
  __int64 v62; // r8
  bool v63; // dl
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // rax
  bool v67; // dl
  enum DXGI_FORMAT v68; // ecx
  bool v69; // dl
  __int64 v70; // r8
  bool v71; // dl
  const char *v72; // rax
  unsigned int v73; // edx
  UINT FirstArraySlice; // r8d
  UINT NumElements; // ecx
  __int64 v76; // rdx
  __int64 v77; // rax
  UINT StructureByteStride; // r11d
  __int64 v79; // rax
  __int64 v80; // rax
  _DWORD *v81; // rcx
  _DWORD *v82; // rdx
  bool v83; // dl
  const char *v84; // rax
  const char *v85; // r8
  char v86; // r13
  __int64 v87; // rax
  int v88; // r8d
  unsigned int v89; // r9d
  unsigned int v90; // r10d
  int v91; // r11d
  __int64 v92; // rax
  bool v93; // dl
  const char *v94; // rax
  __int64 v95; // r8
  const char *v96; // r8
  __int64 v97; // rax
  bool v98; // dl
  const char *v99; // rax
  const char *v100; // r8
  enum DXGI_FORMAT v101; // ecx
  bool v102; // dl
  __int64 v103; // r8
  bool v104; // dl
  const char *v105; // rax
  __int64 v106; // rdx
  const char *v107; // r8
  bool v108; // dl
  const char *v109; // rax
  __int64 v110; // r8
  __int64 v111; // r9
  const char *v112; // r8
  __int64 v113; // rax
  enum DXGI_FORMAT v114; // ecx
  bool v115; // dl
  __int64 v116; // r8
  int v117; // eax
  bool v118; // dl
  bool v119; // dl
  bool v120; // dl
  const char *v121; // rax
  const char *v122; // r8
  bool v123; // dl
  const char *v124; // rax
  _DWORD *v125; // rax
  UINT v126; // r9d
  UINT MipSlice; // r9d
  UINT v128; // r8d
  UINT v129; // ecx
  UINT v130; // r8d
  UINT v131; // ecx
  UINT v132; // r9d
  UINT v133; // r9d
  UINT v134; // ecx
  UINT v135; // r9d
  _DWORD *v136; // rcx
  _DWORD *v137; // rdx
  bool v138; // dl
  const char *v139; // rax
  const char *v140; // r8
  char v141; // r13
  __int64 v142; // rax
  bool v143; // dl
  int v144; // r8d
  unsigned int v145; // r9d
  unsigned int v146; // r10d
  int v147; // r11d
  __int64 v148; // rax
  bool v149; // dl
  const char *v150; // rax
  __int64 v151; // r8
  const char *v152; // r8
  __int64 v153; // rax
  bool v154; // dl
  bool v155; // dl
  const char *v156; // rax
  const char *v157; // r8
  bool v158; // dl
  enum DXGI_FORMAT v159; // ecx
  bool v160; // dl
  __int64 v161; // r8
  bool v162; // dl
  __int64 v163; // r8
  __int64 v164; // r9
  __int64 v165; // rax
  bool v166; // dl
  enum DXGI_FORMAT v167; // ecx
  bool v168; // dl
  __int64 v169; // r8
  bool v170; // dl
  const char *v171; // rax
  UINT v172; // r9d
  UINT v173; // r8d
  UINT v174; // ecx
  UINT v175; // r9d
  ID3D12Resource_vtbl *v176; // rax
  __int32 Flags; // r14d
  UINT64 v178; // rax
  unsigned __int64 v180; // r10
  UINT64 FirstElement; // r9
  unsigned __int64 v182; // rcx
  UINT64 v183; // r9
  unsigned int v184; // r9d
  unsigned int v185; // ecx
  __int64 v186; // rax
  unsigned int v187; // ecx
  int v188; // r9d
  __int64 v189; // r10
  const char *v190; // rax
  char v191; // r11
  unsigned __int64 v192; // rax
  int v193; // r8d
  __int64 v194; // r9
  const char *v195; // rcx
  int v196; // r9d
  UINT64 v197; // r9
  unsigned __int64 ImmutableHeapOffset; // rax
  char v199; // cl
  UINT64 v200; // rax
  int v201; // eax
  bool v202; // dl
  char v203; // cl
  __int64 v204; // rax
  const char *v205; // rax
  __int64 v206; // rax
  UINT64 v207; // r11
  unsigned __int64 v208; // r8
  unsigned __int64 v209; // rcx
  UINT64 v210; // rax
  unsigned __int64 v211; // rdx
  const char *v212; // rax
  int v213; // r8d
  __int64 v214; // r10
  __int64 v215; // r11
  bool v216; // dl
  const char *v217; // rax
  int v218; // eax
  bool v219; // dl
  const char *v220; // rax
  const char *Name; // rax
  const char *v222; // rax
  const char *v223; // rax
  UINT v224; // r9d
  UINT64 v225; // r9
  UINT v226; // r11d
  UINT64 v227; // r8
  unsigned __int64 v228; // r9
  unsigned __int64 v229; // r10
  UINT64 v230; // rax
  unsigned __int64 v231; // rcx
  unsigned __int64 v232; // rax
  UINT v233; // edx
  UINT64 v234; // [rsp+20h] [rbp-E0h]
  __int64 v235; // [rsp+30h] [rbp-D0h]
  __int64 v236; // [rsp+30h] [rbp-D0h]
  __int64 v237; // [rsp+30h] [rbp-D0h]
  __int64 v238; // [rsp+30h] [rbp-D0h]
  const char *v239; // [rsp+38h] [rbp-C8h]
  const char *v240; // [rsp+38h] [rbp-C8h]
  char v241; // [rsp+50h] [rbp-B0h]
  char v242; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v243; // [rsp+54h] [rbp-ACh]
  char v244; // [rsp+54h] [rbp-ACh]
  unsigned __int16 v245; // [rsp+58h] [rbp-A8h]
  UINT v246; // [rsp+58h] [rbp-A8h]
  __int64 v247; // [rsp+60h] [rbp-A0h]
  int v248; // [rsp+68h] [rbp-98h]
  UINT v249; // [rsp+6Ch] [rbp-94h]
  unsigned int v250; // [rsp+6Ch] [rbp-94h]
  unsigned int v251; // [rsp+70h] [rbp-90h]
  unsigned __int64 v252; // [rsp+78h] [rbp-88h]
  unsigned __int64 v253; // [rsp+80h] [rbp-80h] BYREF
  struct ID3D12Resource *v254; // [rsp+88h] [rbp-78h]
  int v255; // [rsp+90h] [rbp-70h]
  int v256; // [rsp+94h] [rbp-6Ch]
  struct ID3D12Resource *v257; // [rsp+98h] [rbp-68h]
  CDevice *v258; // [rsp+A0h] [rbp-60h]
  __int128 v259; // [rsp+A8h] [rbp-58h] BYREF
  int v260; // [rsp+B8h] [rbp-48h]
  char v261; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v262; // [rsp+F8h] [rbp-8h]
  D3D12_RESOURCE_DESC v263; // [rsp+100h] [rbp+0h] BYREF

  p_ViewDimension = &a4->ViewDimension;
  v258 = a5;
  v10 = 1;
  *(_QWORD *)&v259 = a8;
  v257 = a3;
  v11 = (struct ID3D12Resource *)a2;
  v254 = (struct ID3D12Resource *)a2;
  v247 = (__int64)&a4->ViewDimension;
  v248 = *((_DWORD *)a7 + 165);
  v252 = a2 & -(__int64)(a2 != 0);
  if ( a4 )
  {
    if ( *p_ViewDimension == (D3D12_UAV_DIMENSION_TEXTURE3D|D3D12_UAV_DIMENSION_BUFFER) )
    {
      LOBYTE(a2) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::GetImpl'::`2'::impl,
        a2,
        v11);
    }
    if ( !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(a4->Format) )
    {
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        346,
        "The Format (%#x) is unrecognized.",
        v12);
      return 0;
    }
  }
  else
  {
    v247 = 4;
  }
  v13 = 0;
  if ( !v11 )
  {
    if ( !a4 )
    {
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        340,
        "An UnorderedAccessView cannot be created from a NULL Resource and NULL Desc.");
      return 0;
    }
    v15 = (unsigned __int64)&a4->ViewDimension;
    v253 = 1;
    ViewDimension = a4->ViewDimension;
    v243 = 1;
    v245 = 1;
    v251 = 1;
    v256 = 0;
    v255 = 4;
    v22 = ViewDimension - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 || (v24 = v23 - 1) == 0 )
      {
        v18 = 2;
        goto LABEL_24;
      }
      v25 = v24 - 1;
      if ( !v25 || (v26 = v25 - 1) == 0 || (v27 = v26 - 1) == 0 || (v28 = v27 - 1) == 0 )
      {
        v18 = 3;
        goto LABEL_24;
      }
      if ( v28 == 1 )
      {
        v18 = 4;
LABEL_24:
        Format = a4->Format;
        v247 = (__int64)&a4->ViewDimension;
        goto LABEL_25;
      }
    }
    v18 = 1;
    goto LABEL_24;
  }
  v14 = (__int64)v11->GetDesc(v11, (D3D12_RESOURCE_DESC *)&v261);
  v16 = *(_WORD *)(v14 + 28);
  v17 = *(_WORD *)(v14 + 30);
  v18 = *(_DWORD *)v14;
  Format = *(_DWORD *)(v14 + 32);
  v253 = *(_QWORD *)(v14 + 16);
  v251 = *(_DWORD *)(v14 + 36);
  v256 = *(_DWORD *)(v14 + 44);
  v11 = (struct ID3D12Resource *)*(unsigned int *)(v14 + 48);
  v255 = *(_DWORD *)(v14 + 48);
  v243 = v16;
  v245 = v17;
  if ( !a4 )
  {
    v20 = DXGI_FORMAT_UNKNOWN;
    goto LABEL_44;
  }
  v15 = (unsigned __int64)p_ViewDimension;
LABEL_25:
  v20 = a4->Format;
  if ( *(_DWORD *)v15 == 9 || *(_DWORD *)v15 == 1 )
  {
    v29 = v18 == 1;
    goto LABEL_42;
  }
  if ( (*(_DWORD *)v15 != 2 || v18 != 2)
    && (*(_DWORD *)v15 != 4 || v18 != 3)
    && (*(_DWORD *)v15 != 6 || v18 != 3)
    && (*(_DWORD *)v15 != 8 || v18 != 4)
    && (*(_DWORD *)v15 != 5 || v18 != 3)
    && (*(_DWORD *)v15 != 7 || v18 != 3) )
  {
    if ( *(_DWORD *)v15 != 3 )
    {
LABEL_43:
      v13 = 1;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        340,
        "The ViewDimension in the View Desc is incompatible with the type of the Resource or View.");
      goto LABEL_44;
    }
    v29 = v18 == 2;
LABEL_42:
    if ( v29 )
      goto LABEL_44;
    goto LABEL_43;
  }
LABEL_44:
  v30 = v257;
  v262 = 0;
  if ( !v257 )
    goto LABEL_58;
  if ( v18 != 1 )
  {
    ++v13;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      652,
      "Counter UAVs are only supported on buffers.");
    v30 = v257;
  }
  v31 = (__int64)v30->GetDesc(v30, &v263);
  v32 = *(_OWORD *)(v31 + 16);
  v262 = *(_QWORD *)(v31 + 48);
  if ( *(_DWORD *)v31 != 1 )
  {
    ++v13;
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 652, "Counter resources must be buffers.");
  }
  if ( !v254 )
  {
    ++v13;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      652,
      "Counter UAVs require a non-NULL pResource.");
  }
  if ( a4 )
  {
    if ( (*((_DWORD *)&a4->Texture3D + 4) & 0xFFFLL) != 0 )
    {
      ++v13;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        652,
        "CounterOffsetInBytes must be a multiple of D3D12_UAV_COUNTER_PLACEMENT_ALIGNMENT (%u).",
        4096);
    }
    CounterOffsetInBytes = a4->Buffer.CounterOffsetInBytes;
    if ( CounterOffsetInBytes + 4 < CounterOffsetInBytes || CounterOffsetInBytes + 4 > (unsigned __int64)v32 )
    {
      ++v13;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        652,
        "CounterOffsetInBytes must not exceed the counter resource size.");
    }
LABEL_58:
    v34 = v18 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( v35 )
      {
        if ( v35 != 1 )
        {
          if ( !a4 )
          {
LABEL_62:
            v36 = 0xFFFFFFFFLL;
            if ( (unsigned int)Format < 0xC0 )
              v36 = (unsigned int)Format;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v36 + 6) & 0xC00) != 0x800 )
              goto LABEL_67;
            v37 = "A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Defa"
                  "ult Desc parameters cannot be used, as a fully qualified Format must be supplied.";
LABEL_66:
            ++v13;
            TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 341, v37);
LABEL_67:
            v20 = Format;
LABEL_386:
            LODWORD(v234) = v248;
            v253 = (unsigned int)v20;
            v218 = ValidateTypedUnorderedAccessViewFormats(&v253, v258, (unsigned int)v20, (unsigned int)a6, v234, -1);
            if ( v218 == -2147467263 )
            {
              ++v13;
              Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(a4->Format, v219);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                342,
                "The format (%#x, %s) cannot be used with a Typed Unordered Access View.  This is because the current gra"
                "phics implementation does not even support this Format.  Therefore this format does not support Unordere"
                "d Access Views. Use CheckFormatSupport to check Format support.",
                (unsigned int)a4->Format,
                Name);
            }
            else if ( v218 == -2147024809 )
            {
              ++v13;
              v220 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v219);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                342,
                "The format (%#x, %s) cannot be used with a Typed Unordered Access View.",
                (unsigned int)v20,
                v220);
            }
            goto LABEL_415;
          }
          if ( v20 != Format )
          {
            if ( v252 )
            {
              v38 = *(_DWORD **)(v252 + 328);
              if ( v38 )
              {
                v39 = &v38[*(unsigned __int16 *)(v252 + 412)];
                while ( v38 != v39 )
                {
                  if ( *v38 == v20 )
                    goto LABEL_106;
                  ++v38;
                }
                ++v13;
                GetDebugObjectIdentifierString(&v259, v39, v11);
                v41 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v40);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  342,
                  "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was creat"
                  "ed with an explicit format cast list",
                  v20,
                  v41,
                  v42);
                std::string::_Tidy_deallocate(&v259);
                goto LABEL_106;
              }
            }
          }
          v43 = 0xFFFFFFFFLL;
          if ( (unsigned int)Format < 0xC0 )
            v43 = (unsigned int)Format;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v43 + 6) & 0xC00) == 0xC00 )
          {
            if ( v20 == DXGI_FORMAT_UNKNOWN )
            {
              v20 = Format;
LABEL_106:
              if ( (unsigned int)CD3D11FormatHelper::Texture3DSupport(
                                   (unsigned int)v20,
                                   (unsigned int)a6,
                                   (unsigned int)v248) == -1 )
              {
                ++v13;
                v72 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v71);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  342,
                  "The Format (%#x, %s) cannot be used, when creating a View of a Texture3D.",
                  v20,
                  v72);
              }
              if ( v254 )
              {
                v73 = 1;
                if ( v243 >> LOBYTE(a4->Buffer.FirstElement) > 1u )
                  v73 = v243 >> LOBYTE(a4->Buffer.FirstElement);
                if ( a4->Texture1D.MipSlice >= v245
                  || (FirstArraySlice = a4->Texture1DArray.FirstArraySlice, FirstArraySlice >= v73)
                  || (NumElements = a4->Buffer.NumElements) == 0
                  || NumElements != -1 && (NumElements > v73 || NumElements + FirstArraySlice > v73) )
                {
                  ++v13;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    345,
                    "The Dimensions of the View are invalid. MipSlice (value = %u) must be between 0 and MipLevels-1 of t"
                    "he Texture Resource, %hu, inclusively. FirstWSlice (value = %u) must be between 0 and the Depth size"
                    " of the Mip Level, %u, inclusively. With the current FirstWSlice, WSize (value = %u) must be between"
                    " 1 and %u, or -1 to default to all slices from MipSlice, inclusively, in order that the View fit on the Texture.");
                }
              }
              goto LABEL_386;
            }
            if ( v248 < 6 )
            {
              if ( Format == v20 || D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(Format, v20) )
                goto LABEL_106;
              ++v13;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v60, v59);
              v51 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v61);
              v235 = v62;
              v53 = "The Format (%#x, %s) is invalid, when creating a View; the Resource was already created with a fully"
                    " qualified Format, which is not castable (%#x, %s).";
            }
            else
            {
              if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(
                     *((enum DXGI_FORMAT *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1),
                     v20) )
              {
                goto LABEL_88;
              }
              if ( v48 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v20 + 1) )
              {
                v49 = v47;
                if ( v20 < v46 )
                  v49 = (unsigned int)v20;
                if ( (v45 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v49 + 6)) != 0x800 )
                {
LABEL_88:
                  v54 = v47;
                  if ( v20 < v46 )
                    v54 = (unsigned int)v20;
                  if ( (v45 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v54 + 6)) == v45
                    && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v20, Format) )
                  {
                    ++v13;
                    D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v55);
                    v57 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v56);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      342,
                      "The resource format (%s) and view format (%s) differ in float vs non-float component interpretatio"
                      "n - this type of format casting is not supported.",
                      v57,
                      v58);
                  }
                  goto LABEL_106;
                }
              }
              ++v13;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v44);
              v51 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v50);
              v235 = v52;
              v53 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the "
                    "same family as the Format of the Resource (%#x, %s).";
            }
          }
          else
          {
            if ( v20 == DXGI_FORMAT_UNKNOWN )
            {
              ++v13;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v15);
              v51 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v63);
              v235 = v64;
              v65 = 0;
              v53 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the form"
                    "at of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_105:
              TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 342, v53, v65, v51, Format, v235);
              goto LABEL_106;
            }
            if ( Format == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v20 + 1) )
            {
              v66 = 0xFFFFFFFFLL;
              if ( (unsigned int)v20 < 0xC0 )
                v66 = (unsigned int)v20;
              if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v66 + 6) & 0xC00) != 0x800 )
                goto LABEL_106;
            }
            if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(Format, v20) )
              goto LABEL_106;
            ++v13;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v68, v67);
            v51 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v69);
            v235 = v70;
            v53 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable fro"
                  "m the Format of the Resource (%#x, %s).";
          }
          v65 = (unsigned int)v20;
          goto LABEL_105;
        }
        if ( !a4 )
        {
          v76 = 0xFFFFFFFFLL;
          v77 = 0xFFFFFFFFLL;
          if ( (unsigned int)Format < 0xC0 )
            v77 = (unsigned int)Format;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v77 + 6) & 0xC00) == 0x800 )
          {
            ++v13;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              341,
              "A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default "
              "Desc parameters cannot be used, as a fully qualified Format must be supplied.");
            v76 = 0xFFFFFFFFLL;
          }
          if ( (unsigned int)Format < 0xC0 )
            v76 = (unsigned int)Format;
          if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v76 + 32) & 0x10) == 0 )
            goto LABEL_67;
          v37 = "Views of video formats cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a"
                " View format must be supplied, not the same as the underlying video format.The View format is needed to "
                "indicate how the video surface (or part of it) will appear to shaders - see documentation.";
          goto LABEL_66;
        }
        if ( *(_DWORD *)v247 == 4 )
        {
          StructureByteStride = a4->Texture1DArray.FirstArraySlice;
        }
        else if ( *(_DWORD *)v247 == 5 )
        {
          StructureByteStride = a4->Buffer.StructureByteStride;
        }
        else
        {
          StructureByteStride = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetPlaneSliceFromViewFormat(Format, a4->Format);
        }
        v249 = StructureByteStride;
        v79 = 0xFFFFFFFFLL;
        if ( (unsigned int)Format < 0xC0 )
          v79 = (unsigned int)Format;
        if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v79 + 32) & 0x10) != 0 )
          goto LABEL_184;
        v80 = 0xFFFFFFFFLL;
        if ( (unsigned int)Format < 0xC0 )
          v80 = (unsigned int)Format;
        if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v80 + 32) & 8) != 0 )
        {
LABEL_184:
          v117 = ValidateD3DPlanarAndYUVResourceViewFormat(
                   (unsigned int)Format,
                   (unsigned int)v20,
                   (unsigned int)a6,
                   (unsigned int)v248,
                   128,
                   StructureByteStride);
          if ( !v117 )
            goto LABEL_188;
          ++v13;
          if ( v117 != 3 )
          {
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v118);
            v121 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v120);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              342,
              "For the resource format %s, when making a D3D view, the format name for the view can't be %s.  See documen"
              "tation for the set of valid view format names for this resource format, determining which how the resource"
              " (or part of it) will appear to shader.",
              v121,
              v122);
            goto LABEL_188;
          }
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v118);
          v105 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v119);
          v106 = 343;
          v107 = "The Plane Slice %u cannot be used when the resource format is %s and the view format is %s.  See docume"
                 "ntation for the set of valid view format names for this resource format, determining which how the reso"
                 "urce (or part of it) will appear to shader.";
          goto LABEL_172;
        }
        if ( v20 != Format )
        {
          if ( v252 )
          {
            v81 = *(_DWORD **)(v252 + 328);
            if ( v81 )
            {
              v82 = &v81[*(unsigned __int16 *)(v252 + 412)];
              while ( 1 )
              {
                if ( v81 == v82 )
                {
                  ++v13;
                  GetDebugObjectIdentifierString(&v259, v82, v11);
                  v84 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v83);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    342,
                    "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was cre"
                    "ated with an explicit format cast list",
                    v20,
                    v84,
                    v85);
                  std::string::_Tidy_deallocate(&v259);
                  goto LABEL_188;
                }
                if ( *v81 == v20 )
                  break;
                ++v81;
              }
              if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(Format)
                && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v20) )
              {
                v86 = 1;
                goto LABEL_189;
              }
LABEL_188:
              v86 = 0;
LABEL_189:
              if ( (unsigned int)CD3D11FormatHelper::Texture2DSupport(
                                   (unsigned int)v20,
                                   (unsigned int)a6,
                                   (unsigned int)v248) == -1 )
              {
                ++v13;
                v124 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v123);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  342,
                  "The Format (%#x, %s) cannot be used, when creating a View of a Texture2D.",
                  v20,
                  v124);
              }
              if ( !v254 )
                goto LABEL_386;
              v125 = (_DWORD *)v247;
              switch ( *(_DWORD *)v247 )
              {
                case 5:
                  if ( v86 )
                  {
                    v126 = a4->Buffer.NumElements;
                    if ( v126 != 1 )
                    {
                      ++v13;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        345,
                        "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                        v126);
                    }
                  }
                  MipSlice = a4->Texture1D.MipSlice;
                  if ( MipSlice >= v245
                    || (v128 = a4->Texture1DArray.FirstArraySlice, v128 >= v243)
                    || (v129 = a4->Buffer.NumElements) == 0
                    || v129 != -1 && (v129 > v243 || v128 + v129 > v243) )
                  {
                    v130 = a4->Texture1DArray.FirstArraySlice;
                    ++v13;
                    v131 = v243;
                    if ( v243 >= v130 )
                      v131 = a4->Texture1DArray.FirstArraySlice;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      345,
                      "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice ("
                      "value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively.  FirstArr"
                      "aySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. "
                      "With the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or"
                      " -1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.",
                      MipSlice,
                      v245 - 1,
                      v130,
                      v243 - 1,
                      a4->Buffer.NumElements,
                      v243 - v131);
                  }
                  break;
                case 7:
                  if ( v86 )
                  {
                    v132 = a4->Texture1DArray.FirstArraySlice;
                    if ( v132 != 1 )
                    {
                      ++v13;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        345,
                        "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                        v132);
                    }
                  }
                  v133 = a4->Texture1D.MipSlice;
                  if ( v133 >= v243
                    || (v134 = a4->Texture1DArray.FirstArraySlice) == 0
                    || v134 != -1 && (v134 > v243 || v133 + v134 > v243) )
                  {
                    ++v13;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      345,
                      "The Dimensions of the View are invalid due to at least one of the following conditions. FirstArray"
                      "Slice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. Wi"
                      "th the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or -"
                      "1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.");
                  }
                  break;
                case 4:
                  v135 = a4->Texture1D.MipSlice;
                  if ( v135 >= v245 )
                  {
                    ++v13;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      345,
                      "The Dimensions of the View are invalid.  MipSlice (value = %u) must be between 0 and MipLevels-1 o"
                      "f the Texture Resource, %hu, inclusively.",
                      v135,
                      v245 - 1);
                  }
                  break;
                default:
LABEL_219:
                  if ( v251 > 1 && (unsigned int)(*v125 - 6) > 1 )
                  {
                    ++v13;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      341,
                      "The base resource was created as a multisample resource. You must specify D3D12_UAV_DIMENSION_TEXT"
                      "URE2DMSARRAY or D3D12_UAV_DIMENSION_TEXTURE2DMS.");
                  }
                  goto LABEL_386;
              }
              v125 = (_DWORD *)v247;
              goto LABEL_219;
            }
          }
        }
        v87 = 0xFFFFFFFFLL;
        if ( (unsigned int)Format < 0xC0 )
          v87 = (unsigned int)Format;
        if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v87 + 6) & 0xC00) != 0xC00 )
        {
          if ( v20 )
          {
            if ( Format == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v20 + 1) )
            {
              v113 = 0xFFFFFFFFLL;
              if ( (unsigned int)v20 < 0xC0 )
                v113 = (unsigned int)v20;
              if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v113 + 6) & 0xC00) != 0x800 )
                goto LABEL_182;
            }
            if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(Format, v20) )
            {
LABEL_182:
              if ( !StructureByteStride )
                goto LABEL_188;
LABEL_171:
              ++v13;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v15);
              v105 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v104);
              v106 = 344;
              v107 = "The PlaneSlice %u is invalid when the resource format is %s and the view format is %s.  Only Plane "
                     "Slice 0 is valid when creating a view on a non-planar format.";
LABEL_172:
              HIDWORD(v234) = HIDWORD(v105);
              TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, v106, v107);
              goto LABEL_188;
            }
            ++v13;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v114, v15);
            v109 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v115);
            v237 = v116;
            v111 = (unsigned int)v20;
            v112 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable fr"
                   "om the Format of the Resource (%#x, %s).";
          }
          else
          {
            ++v13;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v15);
            v109 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v108);
            v237 = v110;
            v111 = 0;
            v112 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the forma"
                   "t of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
          }
          TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 342, v112, v111, v109, Format, v237);
          goto LABEL_188;
        }
        if ( v20 == DXGI_FORMAT_UNKNOWN )
        {
          v20 = Format;
          goto LABEL_170;
        }
        if ( v248 < 6 )
        {
          if ( Format != v20 && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(Format, v20) )
          {
            ++v13;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v101, v15);
            v94 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v102);
            v236 = v103;
            v96 = "The Format (%#x, %s) is invalid, when creating a View; the Resource was already created with a fully q"
                  "ualified Format, which is not castable (%#x, %s).";
            goto LABEL_169;
          }
        }
        else
        {
          if ( !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(
                  *((enum DXGI_FORMAT *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1),
                  v20) )
          {
            if ( v91 != *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v20 + 1) )
              goto LABEL_160;
            v92 = v90;
            if ( v20 < v89 )
              v92 = (unsigned int)v20;
            if ( (v88 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v92 + 6)) == 0x800 )
            {
LABEL_160:
              ++v13;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v15);
              v94 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v93);
              v236 = v95;
              v96 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the "
                    "same family as the Format of the Resource (%#x, %s).";
LABEL_169:
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                342,
                v96,
                (unsigned int)v20,
                v94,
                Format,
                v236);
              goto LABEL_170;
            }
          }
          v97 = v90;
          if ( v20 < v89 )
            v97 = (unsigned int)v20;
          if ( (v88 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v97 + 6)) == v88
            && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v20, Format) )
          {
            ++v13;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v15);
            v99 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v98);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              342,
              "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this"
              " type of format casting is not supported.",
              v99,
              v100);
          }
        }
LABEL_170:
        if ( !v249 )
          goto LABEL_188;
        goto LABEL_171;
      }
      if ( !a4 )
        goto LABEL_62;
      if ( v20 != Format )
      {
        if ( v252 )
        {
          v136 = *(_DWORD **)(v252 + 328);
          if ( v136 )
          {
            v137 = &v136[*(unsigned __int16 *)(v252 + 412)];
            while ( 1 )
            {
              if ( v136 == v137 )
              {
                ++v13;
                GetDebugObjectIdentifierString(&v259, v137, v11);
                v139 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v138);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  342,
                  "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was creat"
                  "ed with an explicit format cast list",
                  v20,
                  v139,
                  v140);
                std::string::_Tidy_deallocate(&v259);
                goto LABEL_264;
              }
              if ( *v136 == v20 )
                break;
              ++v136;
            }
            if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(Format)
              && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v20) )
            {
              v141 = 1;
LABEL_265:
              if ( (unsigned int)CD3D11FormatHelper::Texture1DSupport(
                                   (unsigned int)v20,
                                   (unsigned int)a6,
                                   (unsigned int)v248) == -1 )
              {
                ++v13;
                v171 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v170);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  342,
                  "The Format (%#x, %s) cannot be used, when creating a View of a Texture1D.",
                  v20,
                  v171);
              }
              if ( v254 )
              {
                if ( *(_DWORD *)v247 == 3 )
                {
                  if ( v141 )
                  {
                    v172 = a4->Buffer.NumElements;
                    if ( v172 != 1 )
                    {
                      ++v13;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        345,
                        "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                        v172);
                    }
                  }
                  if ( a4->Texture1D.MipSlice >= v245
                    || (v173 = a4->Texture1DArray.FirstArraySlice, v173 >= v243)
                    || (v174 = a4->Buffer.NumElements) == 0
                    || v174 != -1 && (v174 > v243 || v173 + v174 > v243) )
                  {
                    ++v13;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      345,
                      "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice ("
                      "value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively.  FirstArr"
                      "aySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. "
                      "With the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or"
                      " -1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.");
                  }
                }
                else
                {
                  v175 = a4->Texture1D.MipSlice;
                  if ( v175 >= v245 )
                  {
                    ++v13;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      345,
                      "The Dimensions of the View are invalid. MipSlice (value = %u) must be between 0 and MipLevels-1 of"
                      " the Texture Resource, %hu, inclusively.",
                      v175,
                      v245 - 1);
                  }
                }
              }
              goto LABEL_386;
            }
LABEL_264:
            v141 = 0;
            goto LABEL_265;
          }
        }
      }
      v142 = 0xFFFFFFFFLL;
      if ( (unsigned int)Format < 0xC0 )
        v142 = (unsigned int)Format;
      if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v142 + 6) & 0xC00) == 0xC00 )
      {
        if ( v20 == DXGI_FORMAT_UNKNOWN )
        {
          v20 = Format;
          goto LABEL_264;
        }
        if ( v248 < 6 )
        {
          if ( Format == v20 || D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(Format, v20) )
            goto LABEL_264;
          ++v13;
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v159, v158);
          v150 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v160);
          v238 = v161;
          v152 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qua"
                 "lified Format, which is not castable (%#x, %s).";
        }
        else
        {
          if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(
                 *((enum DXGI_FORMAT *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * Format + 1),
                 v20) )
          {
            goto LABEL_246;
          }
          if ( v147 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v20 + 1) )
          {
            v148 = v146;
            if ( v20 < v145 )
              v148 = (unsigned int)v20;
            if ( (v144 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v148 + 6)) != 0x800 )
            {
LABEL_246:
              v153 = v146;
              if ( v20 < v145 )
                v153 = (unsigned int)v20;
              if ( (v144 & *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v153 + 6)) == v144
                && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v20, Format) )
              {
                ++v13;
                D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v154);
                v156 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v155);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  342,
                  "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - "
                  "this type of format casting is not supported.",
                  v156,
                  v157);
              }
              goto LABEL_264;
            }
          }
          ++v13;
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v143);
          v150 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v149);
          v238 = v151;
          v152 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the sam"
                 "e family as the Format of the Resource (%#x, %s).";
        }
      }
      else
      {
        if ( v20 == DXGI_FORMAT_UNKNOWN )
        {
          ++v13;
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(Format, v15);
          v150 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v162);
          v238 = v163;
          v164 = 0;
          v152 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the format "
                 "of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_263:
          TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 342, v152, v164, v150, Format, v238);
          goto LABEL_264;
        }
        if ( Format == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v20 + 1) )
        {
          v165 = 0xFFFFFFFFLL;
          if ( (unsigned int)v20 < 0xC0 )
            v165 = (unsigned int)v20;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v165 + 6) & 0xC00) != 0x800 )
            goto LABEL_264;
        }
        if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::ValidCastToR32UAV(Format, v20) )
          goto LABEL_264;
        ++v13;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v167, v166);
        v150 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v168);
        v238 = v169;
        v152 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable from t"
               "he Format of the Resource (%#x, %s).";
      }
      v164 = (unsigned int)v20;
      goto LABEL_263;
    }
    if ( a6 == 4096 || a6 == 256 )
    {
      if ( v254 )
      {
        if ( !*((_DWORD *)v258 + 446) )
        {
          v260 = 0;
          v176 = v254->__vftable;
          v259 = 0;
          v176->GetHeapProperties(v254, (D3D12_HEAP_PROPERTIES *)&v259, 0);
          if ( (_DWORD)v259 != 1 )
          {
            ++v13;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              340,
              "Devices with feature level D3D_FEATURE_LEVEL_1_0_CORE/GENERIC only support creating unordered access views"
              " on resources created from default heaps.");
          }
        }
      }
    }
    v244 = 0;
    v246 = 0;
    if ( a4 )
    {
      if ( *(_DWORD *)v247 == 1 )
      {
        Flags = a4->Buffer.Flags;
        v178 = a4->Buffer.CounterOffsetInBytes;
        v246 = a4->Buffer.StructureByteStride;
      }
      else
      {
        if ( *(_DWORD *)v247 != 9 )
          goto LABEL_298;
        Flags = a4[1].Format;
        v246 = *((_DWORD *)&a4->Texture3D + 4);
        v178 = *((_QWORD *)&a4->Texture3D + 3);
      }
      v244 = Flags;
      if ( v178 && !v257 )
      {
        ++v13;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          652,
          "When pCounterResource is NULL, D3D12_BUFFER_UAV::CounterOffsetInBytes must be 0");
      }
      if ( (Flags & 0xFFFFFFFE) != 0 )
      {
        TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 354, "Invalid Buffer.Flags. ");
        return v13 == -1;
      }
    }
LABEL_298:
    if ( (v255 & 0x100) != 0 )
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        340,
        "Resources created with the D3D12_RESOURCE_FLAG_RAYTRACING_ACCELERATION_STRUCTURE flag set cannot be used as a UAV resource.");
    if ( a4 && *(_DWORD *)v247 == 9 )
    {
      if ( *((_BYTE *)v258 + 296) < 0x51u || !*((_DWORD *)v258 + 139) )
      {
        ++v13;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          345,
          "An unordered access view of D3D12_UAV_DIMENSION_BUFFER_BYTE_OFFSET dimension is not supported by the driver.");
      }
      if ( (a4[1].Format & 1) == 0 )
      {
        v180 = *(_QWORD *)&a4->Texture3D.WSize;
        if ( !v180 )
        {
          ++v13;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            345,
            "BufferByteOffset.Size cannot be 0.");
          v180 = *(_QWORD *)&a4->Texture3D.WSize;
        }
        if ( v254 )
        {
          FirstElement = a4->Buffer.FirstElement;
          v182 = v253;
          if ( FirstElement >= v253 )
          {
            ++v13;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              345,
              "BufferByteOffset.Offset (%I64u) must be less than the buffer size (%I64u).",
              FirstElement,
              v253);
            v182 = v253;
          }
          v180 = *(_QWORD *)&a4->Texture3D.WSize;
          v183 = a4->Buffer.FirstElement;
          if ( v183 + v180 > v182 )
          {
            ++v13;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              345,
              "BufferByteOffset.Offset (%I64u) + Size (%I64u) exceeds the buffer size (%I64u).",
              v183,
              v180,
              v182);
            v180 = *(_QWORD *)&a4->Texture3D.WSize;
          }
        }
        v184 = *((_DWORD *)&a4->Texture3D + 4);
        if ( v184 )
        {
          _BitScanForward(&v185, v184);
          v250 = 1 << v185;
          v241 = 1;
          if ( (unsigned int)(1 << v185) > 0x10 )
            v250 = 16;
        }
        else
        {
          v186 = 0xFFFFFFFFLL;
          if ( (unsigned int)v20 < 0xC0 )
            v186 = (unsigned int)v20;
          v184 = *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v186 + 20) >> 3;
          if ( v184 )
          {
            _BitScanForward(&v187, v184);
            v250 = 1 << v187;
          }
          else
          {
            v250 = 1;
          }
          v241 = 0;
        }
        v15 = v180 % v184;
        if ( v15 )
        {
          ++v13;
          v239 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v15);
          v190 = "structured";
          if ( !v191 )
            v190 = "typed";
          LODWORD(v234) = v188;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            345,
            "BufferByteOffset.Size (%I64u) must be a multiple of (%u) for %s buffers with Format (%#x) %s.",
            v189,
            v234,
            v190,
            v20,
            v239);
        }
        v192 = v252;
        if ( !v252 )
        {
LABEL_339:
          if ( v246 )
          {
            if ( v20 )
            {
              ++v13;
              v223 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v15);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                342,
                "The Format (%#x, %s) is invalid, when creating a View of a Structured Buffer; it must be DXGI_FORMAT_UNKNOWN.",
                v20,
                v223);
            }
            if ( a4 )
            {
              if ( (*(_BYTE *)(&a4->Texture3D + 2) & 1) != 0 )
              {
                ++v13;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  342,
                  "When StructureByteStride is not 0, the UAV Flag D3D12_BUFFER_UAV_FLAG_RAW cannot be specified.");
              }
              if ( v254 && *(_DWORD *)v247 == 1 )
              {
                if ( a6 == 4096 || a6 == 256 )
                {
                  v224 = a4->Buffer.StructureByteStride;
                  if ( v224 == 2 )
                  {
                    v225 = a4->Buffer.FirstElement;
                    if ( (v225 & 1) != 0 || (a4->Texture3D.WSize & 1) != 0 )
                    {
                      ++v13;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        345,
                        "Devices with feature level D3D_FEATURE_LEVEL_1_0_CORE/GENERIC require structured buffer FirstEle"
                        "ment and NumElements to be a multiple of 2 (0 is allowed) when StructureByteStride is 2, to keep"
                        " the base address 4 byte aligned. FirstElement=%I64u and NumElements=%u specified",
                        v225,
                        a4->Buffer.NumElements);
                    }
                  }
                  else if ( (v224 & 3) != 0 )
                  {
                    ++v13;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      345,
                      "Devices with feature level D3D_FEATURE_LEVEL_1_0_CORE/GENERIC require structured buffer Structured"
                      "ByteStride to be 2 or a multiple of 4 (%u specified)",
                      v224);
                  }
                }
                v226 = a4->Buffer.StructureByteStride;
                v227 = a4->Buffer.FirstElement;
                v228 = 8 * v226;
                v229 = 8 * (0xFFFFFFFFFFFFFFFFuLL / v228);
                if ( v227 > v229
                  || (v227 * (unsigned int)v228) >> 3 >= v253
                  || !a4->Buffer.NumElements
                  || (v230 = a4->Buffer.NumElements, v231 = v230 + v227, v230 + v227 < v230)
                  || v231 > v229
                  || v228 * v231 > 8 * v253 )
                {
                  v232 = 8 * v253 / v228;
                  ++v13;
                  v233 = v232;
                  if ( v232 >= v227 )
                    v233 = a4->Texture1D.MipSlice;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    345,
                    "The Dimensions of the View are invalid due to at least one of the following conditions. Assuming Str"
                    "uctureByteStride %u, FirstElement (value = %I64u) must be between 0 and the maximum offset of the Bu"
                    "ffer, %I64u, inclusively. With the current FirstElement, NumElements (value = %u) must be between 1 "
                    "and %u, inclusively, in order that the View fit on the Buffer.",
                    v226,
                    v227,
                    v232 - 1,
                    a4->Buffer.NumElements,
                    v232 - v233);
                }
              }
            }
            goto LABEL_415;
          }
          if ( !a4 )
          {
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              341,
              "A View of a non-Structured Buffer cannot be created using a NULL Desc. Default Desc parameters cannot be u"
              "sed, as a Format must be supplied.");
            return v13 == -1;
          }
          if ( v257 )
          {
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              652,
              "When creating a Counter Unordered Access View, the StructureByteStride on the view must be non-zero.");
            return v13 == -1;
          }
          if ( (v244 & 1) != 0 )
          {
            if ( v20 != DXGI_FORMAT_R32_TYPELESS )
            {
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                342,
                "When creating a RAW Unordered Access View, the format must be DXGI_FORMAT_R32_TYPELESS.");
              return v13 == -1;
            }
            v242 = 0;
            if ( (*((_BYTE *)a7 + 688) & 0x14) == 0 )
            {
              if ( v192 )
              {
                ImmutableHeapOffset = CResource::PrivateGetImmutableHeapOffset((CResource *)(v192 + 200));
                *(_QWORD *)&v259 = ImmutableHeapOffset;
                v199 = ImmutableHeapOffset;
                if ( (ImmutableHeapOffset & 0xF) != 0 )
                {
                  ++v13;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    340,
                    "When creating a RAW Unordered Access View, the underlying resource must be aligned to %u bytes.The h"
                    "eap offset of the resource was actually %I64u, which does not meet this requirement.",
                    16,
                    ImmutableHeapOffset);
                  v199 = v259;
                }
                if ( *(_DWORD *)v247 == 9 && ((v199 + (unsigned __int8)a4->Buffer.FirstElement) & 0xF) != 0 )
                {
                  v234 = a4->Buffer.FirstElement;
                  ++v13;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    345,
                    "When creating a RAW Unordered Access View with byte offset, the offset of the resource + BufferByteO"
                    "ffset.Offsetmust be a multiple of %u bytes.",
                    16);
                }
              }
              if ( *(_DWORD *)v247 == 1 )
              {
                v200 = a4->Buffer.FirstElement;
                if ( (v200 & 3) != 0 )
                {
                  ++v13;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    345,
                    "When creating a RAW Unordered Access View, the offset of the first element from the start of the buf"
                    "fer must be a multiple of %u bytes.  Thus, FirstElement (%I64u) must be a multiple of %u since each "
                    "element is 4 bytes.",
                    16,
                    v200,
                    4);
                }
              }
            }
            goto LABEL_371;
          }
          if ( a6 == 4096 || a6 == 256 )
          {
            ++v13;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              341,
              "Devices with feature level D3D_FEATURE_LEVEL_1_0_CORE/GENERIC do not support typed buffer views.  Only raw"
              " and structured buffer views are supported.");
          }
          v201 = CD3D11FormatHelper::BufferSupport((unsigned int)v20, (unsigned int)a6, (unsigned int)v248);
          v203 = 0;
          LODWORD(v259) = v20;
          *(_QWORD *)((char *)&v259 + 4) = 0;
          if ( v201 == -2 )
          {
            CDevice::CheckFeatureSupport(v258, D3D12_FEATURE_FORMAT_SUPPORT, &v259, 0xCu);
            v203 = BYTE4(v259);
            v201 = -2;
          }
          else if ( v201 == -1 )
          {
            goto LABEL_390;
          }
          if ( v20 && (v201 != -2 || (v203 & 1) != 0) )
          {
            v204 = 0xFFFFFFFFLL;
            v242 = 1;
            if ( (unsigned int)v20 < 0xC0 )
              v204 = (unsigned int)v20;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v204 + 6) & 0xC00) == 0x800 )
            {
              ++v13;
              v205 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v202);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                342,
                "The Format (%#x, %s) is invalid when creating a typed View; it is a typeless format",
                v20,
                v205);
            }
            if ( (unsigned int)v20 >= 0xC0 )
            {
              v206 = 0xFFFFFFFFLL;
              goto LABEL_373;
            }
LABEL_371:
            v206 = (unsigned int)v20;
LABEL_373:
            if ( v254 )
            {
              if ( *(_DWORD *)v247 == 1 )
              {
                v207 = a4->Buffer.FirstElement;
                v208 = *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v206 + 20);
                v209 = 8 * (0xFFFFFFFFFFFFFFFFuLL / v208);
                if ( v207 > v209
                  || (v207 * *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v206 + 20)) >> 3 >= v253
                  || !a4->Buffer.NumElements
                  || (v210 = a4->Buffer.NumElements, v211 = v210 + v207, v210 + v207 < v210)
                  || v211 > v209
                  || v211 * (unsigned int)v208 > 8 * v253 )
                {
                  ++v13;
                  v212 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, 8 * v253 % v208);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    345,
                    "The Dimensions of the View are invalid due to at least one of the following conditions. Assuming thi"
                    "s Format (%#x, %s), FirstElement (value = %I64u) must be between 0 and the maximum offset of the Buf"
                    "fer, %I64u, inclusively. With the current FirstElement, NumElements (value = %u) must be between 1 a"
                    "nd %u, inclusively, in order that the View fit on the Buffer.",
                    v20,
                    v212,
                    v215,
                    v214,
                    a4->Buffer.NumElements,
                    v213);
                }
              }
            }
            if ( v256 == 2
              && (unsigned int)CD3D11FormatHelper::TiledResourceSupport((unsigned int)v20, 1, 1, (unsigned int)a6, v248) == -1 )
            {
              ++v13;
              v217 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v216);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                342,
                "The Format (%#x, %s) cannot be used with a Tiled Resource.",
                v20,
                v217);
            }
            if ( v242 )
              goto LABEL_386;
LABEL_415:
            if ( (v255 & 4) == 0 )
            {
              ++v13;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                340,
                "A UnorderedAccessView cannot be created of a Resource that did not specify the D3D12_RESOURCE_FLAG_ALLOW"
                "_UNORDERED_ACCESS Flag.");
            }
            if ( v257 )
            {
              if ( (v262 & 4) == 0 )
              {
                ++v13;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  340,
                  "A UnorderedAccessView cannot be created with a counter Resource that did not specify the D3D12_RESOURC"
                  "E_FLAG_ALLOW_UNORDERED_ACCESS Flag.");
              }
            }
            if ( !v13 )
              return v10;
            return 0;
          }
LABEL_390:
          v222 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v202);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            342,
            "The Format (%#x, %s) cannot be used when creating a typed View of a Buffer.",
            v20,
            v222);
          return v13 == -1;
        }
        v15 = (a4->Buffer.FirstElement + CResource::PrivateGetImmutableHeapOffset((CResource *)(v252 + 200))) % v250;
        if ( v15 )
        {
          ++v13;
          v240 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v20, v15);
          v195 = "structured";
          if ( !v241 )
            v195 = "typed";
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            345,
            "BufferByteOffset.Offset (%I64u) must be %u-byte aligned for %s buffers with Format (%#x) %s.",
            v194,
            v193,
            v195,
            v20,
            v240);
        }
        if ( a6 == 4096 || a6 == 256 )
        {
          v196 = *((_DWORD *)&a4->Texture3D + 4);
          if ( v196 == 2 )
          {
            v197 = a4->Buffer.FirstElement;
            if ( (((unsigned __int8)v197 | LOBYTE(a4->Texture3D.WSize)) & 1) != 0 )
            {
              ++v13;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                345,
                "Devices with feature level D3D_FEATURE_LEVEL_1_0_CORE/GENERIC require structured buffer FirstElement and"
                " NumElements to be a multiple of 2 (0 is allowed) when StructureByteStride is 2, to keep the base addres"
                "s 4 byte aligned. Offset=%I64u and Size=%u specified",
                v197,
                *(_QWORD *)&a4->Texture3D.WSize);
            }
          }
          else if ( (v196 & 3) != 0 )
          {
            ++v13;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              345,
              "Devices with feature level D3D_FEATURE_LEVEL_1_0_CORE/GENERIC require structured buffer StructuredByteStri"
              "de to be 2 or a multiple of 4 (%u specified)",
              v196);
          }
        }
      }
    }
    v192 = v252;
    goto LABEL_339;
  }
  TDebugOutputFunctor::operator()(
    &g_coreRuntimeTallyErrorOutputFunctor,
    652,
    "Counter UAVs require a non-NULL D3D12_UNORDERED_ACCESS_VIEW_DESC.");
  return 0;
}

```

## disassembly

```asm
0x180031ef0  mov     rax, rsp
0x180031ef3  mov     [rax+8], rbx
0x180031ef7  push    rbp
0x180031ef8  push    rsi
0x180031ef9  push    rdi
0x180031efa  push    r12
0x180031efc  push    r13
0x180031efe  push    r14
0x180031f00  push    r15
0x180031f02  lea     rbp, [rsp-50h]
0x180031f07  sub     rsp, 150h
0x180031f0e  movaps  xmmword ptr [rax-48h], xmm6
0x180031f12  mov     rax, cs:__security_cookie
0x180031f19  xor     rax, rsp
0x180031f1c  mov     [rbp+80h+var_48], rax
0x180031f20  mov     rax, [rbp+80h+arg_20]
0x180031f27  lea     rdi, [r9+4]
0x180031f2b  mov     [rbp+80h+var_E0], rax
0x180031f2f  mov     r12, r9
0x180031f32  mov     rax, [rbp+80h+arg_38]
0x180031f39  mov     esi, 1
0x180031f3e  mov     qword ptr [rbp+80h+var_D8], rax
0x180031f42  mov     rax, [rbp+80h+arg_30]
0x180031f49  mov     [rbp+80h+var_E8], r8
0x180031f4d  mov     r8, rdx
0x180031f50  mov     [rbp+80h+var_F8], rdx
0x180031f54  mov     [rsp+180h+var_120], rdi
0x180031f59  mov     eax, [rax+294h]
0x180031f5f  mov     [rsp+180h+var_118], eax
0x180031f63  mov     rax, rdx
0x180031f66  neg     rax
0x180031f69  sbb     rax, rax
0x180031f6c  and     rax, rdx
0x180031f6f  mov     [rsp+180h+var_108], rax
0x180031f74  test    r9, r9
0x180031f77  jz      short loc_180031FBE
0x180031f79  cmp     dword ptr [rdi], 9
0x180031f7c  jnz     short loc_180031F91
0x180031f7e  mov     dl, sil
0x180031f81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12RevisedViewCreation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12RevisedViewCreation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12RevisedViewCreation> `wil::Feature<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::GetImpl(void)'::`2'::impl
0x180031f88  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12RevisedViewCreation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12RevisedViewCreation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180031f8d  mov     r8, [rbp+80h+var_F8]
0x180031f91  mov     r9d, [r12]
0x180031f95  mov     ecx, r9d; enum DXGI_FORMAT
0x180031f98  call    ?FormatExists@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(DXGI_FORMAT)
0x180031f9d  test    al, al
0x180031f9f  jnz     short loc_180031FC3
0x180031fa1  lea     r8, aTheFormatXIsUn; "The Format (%#x) is unrecognized."
0x180031fa8  mov     edx, 15Ah
0x180031fad  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180031fb4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180031fb9  jmp     loc_180033A18
0x180031fbe  mov     [rsp+180h+var_120], rdi
0x180031fc3  xor     ebx, ebx
0x180031fc5  lea     r15, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180031fcc  test    r8, r8
0x180031fcf  jz      short loc_180032031
0x180031fd1  mov     rax, [r8]
0x180031fd4  lea     rdx, [rbp+80h+var_B8]
0x180031fd8  mov     rcx, r8
0x180031fdb  mov     rax, [rax+50h]
0x180031fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fe4  mov     r8, [rax+10h]
0x180031fe8  movzx   r10d, word ptr [rax+1Ch]
0x180031fed  movzx   r9d, word ptr [rax+1Eh]
0x180031ff2  mov     r13d, [rax]
0x180031ff5  mov     r14d, [rax+20h]
0x180031ff9  mov     [rbp+80h+var_100], r8
0x180031ffd  mov     r8d, [rax+24h]
0x180032001  mov     [rsp+180h+var_110], r8d
0x180032006  mov     r8d, [rax+2Ch]
0x18003200a  mov     [rbp+80h+var_EC], r8d
0x18003200e  mov     r8d, [rax+30h]
0x180032012  mov     [rbp+80h+var_F0], r8d
0x180032016  mov     [rsp+180h+var_12C], r10d
0x18003201b  mov     [rsp+180h+var_128], r9d
0x180032020  test    r12, r12
0x180032023  jz      short loc_18003202A
0x180032025  mov     rdx, rdi
0x180032028  jmp     short loc_18003209F
0x18003202a  xor     edi, edi
0x18003202c  jmp     loc_180032114
0x180032031  test    r12, r12
0x180032034  jz      loc_180033A20
0x18003203a  lea     rdx, [r12+4]
0x18003203f  mov     [rbp+80h+var_100], rsi
0x180032043  mov     ecx, [rdx]
0x180032045  mov     [rsp+180h+var_12C], esi
0x180032049  mov     [rsp+180h+var_128], esi
0x18003204d  mov     [rsp+180h+var_110], esi
0x180032051  mov     [rbp+80h+var_EC], ebx
0x180032054  mov     [rbp+80h+var_F0], 4
0x18003205b  sub     ecx, esi
0x18003205d  jz      short loc_180032093
0x18003205f  sub     ecx, esi
0x180032061  jz      short loc_18003208B
0x180032063  sub     ecx, esi
0x180032065  jz      short loc_18003208B
0x180032067  sub     ecx, esi
0x180032069  jz      short loc_180032083
0x18003206b  sub     ecx, esi
0x18003206d  jz      short loc_180032083
0x18003206f  sub     ecx, esi
0x180032071  jz      short loc_180032083
0x180032073  sub     ecx, esi
0x180032075  jz      short loc_180032083
0x180032077  cmp     ecx, esi
0x180032079  jnz     short loc_180032093
0x18003207b  mov     r13d, 4
0x180032081  jmp     short loc_180032096
0x180032083  mov     r13d, 3
0x180032089  jmp     short loc_180032096
0x18003208b  mov     r13d, 2
0x180032091  jmp     short loc_180032096
0x180032093  mov     r13d, esi
0x180032096  mov     r14d, [r12]
0x18003209a  mov     [rsp+180h+var_120], rdx
0x18003209f  cmp     dword ptr [rdx], 9
0x1800320a2  mov     edi, [r12]
0x1800320a6  jnz     short loc_1800320AD
0x1800320a8  cmp     r13d, esi
0x1800320ab  jmp     short loc_1800320FC
0x1800320ad  cmp     [rdx], esi
0x1800320af  jz      short loc_1800320A8
0x1800320b1  cmp     dword ptr [rdx], 2
0x1800320b4  jnz     short loc_1800320BC
0x1800320b6  cmp     r13d, 2
0x1800320ba  jz      short loc_180032114
0x1800320bc  cmp     dword ptr [rdx], 4
0x1800320bf  jnz     short loc_1800320C7
0x1800320c1  cmp     r13d, 3
0x1800320c5  jz      short loc_180032114
0x1800320c7  cmp     dword ptr [rdx], 6
0x1800320ca  jnz     short loc_1800320D2
0x1800320cc  cmp     r13d, 3
0x1800320d0  jz      short loc_180032114
0x1800320d2  cmp     dword ptr [rdx], 8
0x1800320d5  jnz     short loc_1800320DD
0x1800320d7  cmp     r13d, 4
0x1800320db  jz      short loc_180032114
0x1800320dd  cmp     dword ptr [rdx], 5
0x1800320e0  jnz     short loc_1800320E8
0x1800320e2  cmp     r13d, 3
0x1800320e6  jz      short loc_180032114
0x1800320e8  cmp     dword ptr [rdx], 7
0x1800320eb  jnz     short loc_1800320F3
0x1800320ed  cmp     r13d, 3
0x1800320f1  jz      short loc_180032114
0x1800320f3  cmp     dword ptr [rdx], 3
0x1800320f6  jnz     short loc_1800320FE
0x1800320f8  cmp     r13d, 2
0x1800320fc  jz      short loc_180032114
0x1800320fe  lea     r8, aTheViewdimensi_0; "The ViewDimension in the View Desc is i"...
0x180032105  mov     edx, 154h
0x18003210a  mov     rcx, r15
0x18003210d  mov     ebx, esi
0x18003210f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180032114  mov     rcx, [rbp+80h+var_E8]
0x180032118  xor     eax, eax
0x18003211a  mov     [rbp+80h+var_88], rax
0x18003211e  test    rcx, rcx
0x180032121  jz      loc_180032208
0x180032127  cmp     r13d, esi
0x18003212a  jz      short loc_180032146
0x18003212c  add     ebx, esi
0x18003212e  lea     r8, aCounterUavsAre; "Counter UAVs are only supported on buff"...
0x180032135  mov     edx, 28Ch
0x18003213a  mov     rcx, r15
0x18003213d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180032142  mov     rcx, [rbp+80h+var_E8]
0x180032146  mov     rax, [rcx]
0x180032149  lea     rdx, [rbp+80h+var_80]
0x18003214d  mov     rax, [rax+50h]
0x180032151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032156  movsd   xmm1, qword ptr [rax+30h]
0x18003215b  movups  xmm6, xmmword ptr [rax+10h]
0x18003215f  movsd   [rbp+80h+var_88], xmm1
0x180032164  cmp     [rax], esi
0x180032166  jz      short loc_18003217E
0x180032168  add     ebx, esi
0x18003216a  lea     r8, aCounterResourc; "Counter resources must be buffers."
0x180032171  mov     edx, 28Ch
0x180032176  mov     rcx, r15
0x180032179  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18003217e  cmp     [rbp+80h+var_F8], 0
0x180032183  jnz     short loc_18003219B
0x180032185  add     ebx, esi
0x180032187  lea     r8, aCounterUavsReq_0; "Counter UAVs require a non-NULL pResour"...
0x18003218e  mov     edx, 28Ch
0x180032193  mov     rcx, r15
0x180032196  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18003219b  test    r12, r12
0x18003219e  jnz     short loc_1800321B1
0x1800321a0  lea     r8, aCounterUavsReq; "Counter UAVs require a non-NULL D3D12_U"...
0x1800321a7  mov     edx, 28Ch
0x1800321ac  jmp     loc_180033A2C
0x1800321b1  mov     eax, [r12+18h]
0x1800321b6  test    rax, 0FFFh
0x1800321bc  jz      short loc_1800321DA
0x1800321be  add     ebx, esi
0x1800321c0  lea     r8, aCounteroffseti_0; "CounterOffsetInBytes must be a multiple"...
0x1800321c7  mov     r9d, 1000h
0x1800321cd  mov     edx, 28Ch
0x1800321d2  mov     rcx, r15
0x1800321d5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800321da  mov     rax, [r12+18h]
0x1800321df  lea     rcx, [rax+4]
0x1800321e3  cmp     rcx, rax
0x1800321e6  jb      short loc_1800321F2
0x1800321e8  movq    rax, xmm6
0x1800321ed  cmp     rcx, rax
0x1800321f0  jbe     short loc_180032208
0x1800321f2  add     ebx, esi
0x1800321f4  lea     r8, aCounteroffseti; "CounterOffsetInBytes must not exceed th"...
0x1800321fb  mov     edx, 28Ch
0x180032200  mov     rcx, r15
0x180032203  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180032208  mov     [rsp+180h+var_130], 0
0x18003220d  sub     r13d, esi
0x180032210  jz      loc_180033067
0x180032216  sub     r13d, esi
0x180032219  jz      loc_180032C7C
0x18003221f  cmp     r13d, esi
0x180032222  jz      loc_1800325DB
0x180032228  test    r12, r12
0x18003222b  jnz     short loc_180032279
0x18003222d  or      eax, 0FFFFFFFFh
0x180032230  lea     r13, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180032237  cmp     r14d, 0C0h
0x18003223e  mov     r8d, 0C00h
0x180032244  cmovb   eax, r14d
0x180032248  lea     rcx, [rax+rax*4]
0x18003224c  mov     eax, [r13+rcx*8+18h]
0x180032251  and     eax, r8d
0x180032254  cmp     eax, 800h
0x180032259  jnz     short loc_180032271
0x18003225b  lea     r8, aAViewCannotBeC; "A View cannot be created using a NULL D"...
0x180032262  add     ebx, esi
0x180032264  mov     edx, 155h
0x180032269  mov     rcx, r15
0x18003226c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180032271  mov     edi, r14d
0x180032274  jmp     loc_18003379B
0x180032279  or      r10d, 0FFFFFFFFh
0x18003227d  cmp     edi, r14d
0x180032280  jz      loc_180032308
0x180032286  mov     rax, [rsp+180h+var_108]
0x18003228b  test    rax, rax
0x18003228e  jz      short loc_180032308
0x180032290  mov     rcx, [rax+148h]
0x180032297  test    rcx, rcx
0x18003229a  jz      short loc_180032308
0x18003229c  movzx   eax, word ptr [rax+19Ch]
0x1800322a3  lea     rdx, [rcx+rax*4]
0x1800322a7  jmp     short loc_1800322B5
0x1800322a9  cmp     [rcx], edi
0x1800322ab  jz      loc_1800324F1
0x1800322b1  add     rcx, 4
0x1800322b5  cmp     rcx, rdx
0x1800322b8  jnz     short loc_1800322A9
0x1800322ba  lea     rcx, [rbp+80h+var_D8]
0x1800322be  add     ebx, esi
0x1800322c0  call    ?GetDebugObjectIdentifierString@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUID3D12DeviceChild@@@Z; GetDebugObjectIdentifierString(ID3D12DeviceChild *)
0x1800322c5  mov     r8, rax
0x1800322c8  cmp     qword ptr [rax+18h], 0Fh
0x1800322cd  jbe     short loc_1800322D2
0x1800322cf  mov     r8, [rax]
0x1800322d2  mov     ecx, edi; enum DXGI_FORMAT
0x1800322d4  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1800322d9  mov     [rsp+180h+var_158], r8
0x1800322de  mov     edx, 156h
0x1800322e3  lea     r8, aTheViewFormatX; "The view format (%#x, %s) was not speci"...
0x1800322ea  mov     [rsp+180h+var_160], rax
0x1800322ef  mov     rcx, r15
0x1800322f2  mov     r9d, edi
0x1800322f5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800322fa  lea     rcx, [rbp+80h+var_D8]
0x1800322fe  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180032303  jmp     loc_1800324F1
0x180032308  mov     eax, r10d
0x18003230b  lea     r13, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180032312  mov     r8d, 0C00h
0x180032318  mov     r9d, 0C0h
0x18003231e  cmp     r14d, r9d
0x180032321  cmovb   eax, r14d
0x180032325  lea     rax, [rax+rax*4]
0x180032329  mov     eax, [r13+rax*8+18h]
0x18003232e  and     eax, r8d
0x180032331  cmp     eax, r8d
0x180032334  jnz     loc_180032459
0x18003233a  test    edi, edi
0x18003233c  jnz     short loc_180032346
0x18003233e  mov     edi, r14d
0x180032341  jmp     loc_1800324F1
0x180032346  cmp     [rsp+180h+var_118], 6
0x18003234b  jl      loc_18003241F
0x180032351  movsxd  rax, r14d
0x180032354  mov     edx, edi; enum DXGI_FORMAT
0x180032356  lea     rcx, [rax+rax*4]
0x18003235a  mov     r11d, [r13+rcx*8+4]
  ... truncated ...
```
