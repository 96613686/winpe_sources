# ValidateResourceDescription(TDebugOutputFunctor &,DeviceValidationInfo const &,CD3DX12_RESOURCE_DESC2 const &,D3D12_CLEAR_VALUE const *,uint,DXGI_FORMAT const *,unsigned __int64,CD3DX12_RESOURCE_DESC2 *,bool)

- ea: `0x1800fe198`
- end: `0x18010003f`
- name: `?ValidateResourceDescription@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUCD3DX12_RESOURCE_DESC2@@PEBUD3D12_CLEAR_VALUE@@IPEBW4DXGI_FORMAT@@_KPEAU3@_N@Z`
- size: `7847`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, const struct DeviceValidationInfo *@<rdx>, const struct CD3DX12_RESOURCE_DESC2 *@<r8>, const struct D3D12_CLEAR_VALUE *@<r9>, unsigned int, const enum DXGI_FORMAT *, unsigned __int64, struct CD3DX12_RESOURCE_DESC2 *, bool)`
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046100`
- `0x18006a598`
- `0x18006e450`
- `0x1800a73c8`
- `0x1800e6c44`
- `0x1800f57a0`
- `0x1800fdb10`
- `0x1800fdbd8`

## callees

- `0x180003c84`
- `0x180024c70`
- `0x180025dc0`
- `0x18002621c`
- `0x180026300`
- `0x1800266a8`
- `0x1800268f0`
- `0x18002a0c0`
- `0x18002a170`
- `0x18002ef50`
- `0x180034fb0`
- `0x18003e900`
- `0x180049b2c`
- `0x18004bdb0`
- `0x18004bdd0`
- `0x18004cc90`
- `0x180067b6c`
- `0x18006e748`
- `0x180074dd4`
- `0x18009332c`
- `0x18009fd4c`
- `0x1800a15c8`
- `0x1800a87c4`
- `0x1800abc10`
- `0x1800ae508`
- `0x1800bb480`
- `0x1800f6d7c`
- `0x1800fcf04`
- `0x1800fe198`
- `0x180100458`
- `0x180262020`

## string_xrefs

- `0x1800ffd85`: `D3D12_RESOURCE_DESC::MiscFlag cannot have D3D12_RESOURCE_FLAG_ALLOW_SIMULTANEOUS_ACCESS set when D3D12_RESOURCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_BUFFER.`
- `0x1800ffc6c`: `Textures created with certain Formats must align the resource dimensions properly. D3D12_RESOURCE_DESC::Format is %s. D3D12_RESOURCE_DESC::Width is %I64u, and must be a multiple of %u. D3D12_RESOURCE_DESC::Height is %u, and must be a multiple of %u.`
- `0x1800fe95a`: `A multisampled resource cannot set D3D12_RESOURCE_FLAG_ALLOW_SIMULTANEOUS_ACCESS in D3D12_RESOURCE_DESC::Flags.DXGI_SAMPLE_DESC::Count is %u, DXGI_SAMPLE_DESC::Quality is %u.`
- `0x1800fe944`: `A multisampled resource cannot set D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS in D3D12_RESOURCE_DESC::Flags since the device does not expose WriteableMSAATexturesSupported.DXGI_SAMPLE_DESC::Count is %u, DXGI_SAMPLE_DESC::Quality is %u.`
- `0x1800fee3f`: `D3D12_RESOURCE_DESC::Flags is invalid.  The value is 0x%x.  The D3D12 device being used only supports copies to/from row major textures.  Neither D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET nor D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS may be set.`
- `0x1800ff1ce`: `Textures with layout D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE and most resource flags cannot be created when the tiled resource capabilities do not support full orthogonality for %s. D3D12_FEATURE_DATA_D3D12_OPTIONS::TiledResourcesTier is %s. D3D12_FEATURE_DATA_D3D12_OPTIONS5::SRVOnlyTiledResourceTier3 is %s. The following flags are not supported, unless TiledResourcesTier is D3D12_TILED_RESOURCES_TIER_3 or greater: D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET = %u. D3D12_RESOURCE_FLAG_ALLOW_DEPTH`
- `0x1800ff253`: `Textures with layout D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE cannot be created when the D3D12_RESOURCE_DESC::Format does not support tiled resources. Format is %s. D3D12_FORMAT_SUPPORT2_TILED is not set for D3D12_FEATURE_FORMAT_SUPPORT.`
- `0x1800ff20b`: `Textures with layout D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE cannot be created when the tiled resource capabilities do not support D3D12_RESOURCE_DESC::Dimension of %s. D3D12_FEATURE_DATA_D3D12_OPTIONS::TiledResourcesTier is %s. D3D12_FEATURE_DATA_D3D12_OPTIONS5::SRVOnlyTiledResourceTier3 is %s.`
- `0x1800ff490`: `On a device with Tier 2 & 3 Tiled Resources support, Tiled Resources cannot be created with both more than one array slice and any mipmap that has a dimension less than a tile in extent. For the Tiled Resource being created, Mip [%u] has (width=%u, height=%u) while the tile dimension for the given format is (width=%u, height=%u). Hardware support in this area was not able to be standardized in time to be included in D3D.`
- `0x1800ff400`: `On a device with Tier 1 Tiled Resources support, Tiled Resources cannot be created with both more than one array slice and any mipmap that has a dimension not a multiple of a tile in extent. For the Tiled Resource being created, Mip [%u] has (width=%u, height=%u) while the tile dimension for the given format is (width=%u, height=%u). `
- `0x1800ff6d7`: `A texture that has D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET set in D3D12_RESOURCE_DESC::Flags must be created with a format that either can be used as a render target, or cast to a format that could be used as a render target. FeatureLevel is %s. D3D12_RESOURCE_DESC::Format is %s.%s`
- `0x1800ff61f`: `A texture that has D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS set in D3D12_RESOURCE_DESC::Flags must be created with a format that either can be used as unordered access, or cast to a format that could be used as unordered access. FeatureLevel is %s. D3D12_RESOURCE_DESC::Format is %s.%s`
- `0x1800ff789`: `A texture that has D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set in D3D12_RESOURCE_DESC::Flags must be created with a format that either can be used as a depth stencil, or cast to a format that could be used as a depth stencil. FeatureLevel is %s. D3D12_RESOURCE_DESC::Format is %s.%s`
- `0x1800ff6ff`: `D3D12_RESOURCE_DESC::Flags cannot have D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set with D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET, D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS, nor D3D12_RESOURCE_FLAG_ALLOW_SIMULTANEOUS_ACCESS.`
- `0x1800ff55d`: `Textures cannot be used as unordered access resources when the feature level is less than D3D_FEATURE_LEVEL_11_0. D3D12_RESOURCE_DESC::Dimension is %s. D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS set. FeatureLevel is %s.`
- `0x1800ff83e`: `D3D12_RESOURCE_DESC::Flags can only combine D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY with these flags: 0x%x.  Unsupported flags specified: 0x%x.`
- `0x1800ff917`: `D3D12_RESOURCE_DESC::Flags can only combine D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY with these flags: 0x%x.  Unsupported flags specified: 0x%x.`
- `0x1800ffba0`: `D3D12_CLEAR_VALUE::DepthStencil::Depth is outside the valid range of 0.0f to 1.0f. Depth = %f.`
- `0x1800fff29`: `Castable format list: Cannot cast from non-compressed format %s to compressed format %s.`
- `0x1800fffbb`: `This device does not support at least D3D12_RECREATEAT_TIER_1 and cannot specify heap and resource virtual addresses.`
- `0x1800ffeee`: `Only heaps and buffer resources are compatible with SetNextAllocationAddress. Dimension was %s (0x%X)`

## pseudocode

```c
__int64 __fastcall ValidateResourceDescription(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        const struct CD3DX12_RESOURCE_DESC2 *a3,
        const struct D3D12_CLEAR_VALUE *a4,
        unsigned int a5,
        const enum DXGI_FORMAT *a6,
        unsigned __int64 a7,
        struct CD3DX12_RESOURCE_DESC2 *a8,
        bool a9)
{
  int v12; // r12d
  unsigned int v13; // esi
  int v14; // r9d
  const char *v15; // r8
  __int64 v16; // rdx
  unsigned __int64 *v17; // r13
  const char *v18; // r9
  int v19; // eax
  bool v20; // dl
  __int64 result; // rax
  char v22; // r12
  unsigned int v23; // r9d
  unsigned int v24; // r11d
  unsigned int v25; // r10d
  char v26; // al
  unsigned int v27; // eax
  unsigned __int64 v28; // r10
  unsigned __int64 v29; // r8
  unsigned __int64 *v30; // rcx
  unsigned __int64 v31; // rax
  int v32; // r11d
  unsigned __int16 v33; // dx
  unsigned __int16 v34; // r12
  const char *v35; // rax
  bool v36; // dl
  enum DXGI_FORMAT v37; // r9d
  const char *Name; // rax
  enum DXGI_FORMAT *v39; // r8
  const char *v40; // r8
  __int64 v41; // rdx
  bool v42; // dl
  enum DXGI_FORMAT v43; // r9d
  const char *v44; // rax
  const char *v45; // r8
  enum DXGI_FORMAT *v46; // r10
  const char *v47; // r8
  __int64 v48; // rdx
  unsigned __int64 v49; // rdx
  __int64 v50; // r8
  unsigned int v51; // r9d
  __int16 v52; // r10
  __int64 v53; // r11
  unsigned int v54; // r8d
  bool v55; // dl
  enum DXGI_FORMAT v56; // r9d
  const char *v57; // rbx
  const char *v58; // rax
  unsigned int *v59; // r8
  int v60; // r10d
  const char *v61; // r8
  __int64 v62; // rdx
  unsigned int v63; // r8d
  unsigned int v64; // eax
  unsigned int v65; // r10d
  const char *v66; // rax
  unsigned int *v67; // r9
  int v68; // r8d
  int v69; // r10d
  __int64 v70; // r9
  const char *v71; // r8
  __int64 v72; // rdx
  unsigned int v73; // r12d
  const char *v74; // rax
  const char *v75; // r8
  const char *v76; // r9
  const char *v77; // rcx
  int v78; // r10d
  const char *v79; // rax
  int v80; // r8d
  const char *v81; // rbx
  int v82; // ecx
  int v83; // ecx
  int v84; // ecx
  __int64 v85; // rax
  bool v86; // cl
  __int64 v87; // rax
  __int64 v88; // r9
  const char *v89; // r8
  unsigned int v90; // eax
  const char *v91; // r8
  __int64 v92; // rdx
  __int64 v93; // r9
  enum DXGI_FORMAT v94; // r12d
  unsigned __int8 PlaneCount; // al
  __int64 v96; // r8
  unsigned __int8 v97; // r10
  UINT v98; // r11d
  char v99; // r9
  unsigned int v100; // r13d
  enum DXGI_FORMAT v101; // ecx
  unsigned int v102; // r8d
  __int64 v103; // rax
  unsigned __int64 v104; // r10
  const char *v105; // rax
  __int64 v106; // r8
  const char *v107; // r9
  int v108; // r11d
  __int64 v109; // rax
  const char *v110; // r9
  int v111; // r8d
  __int64 v112; // r11
  __int64 v113; // r9
  enum DXGI_FORMAT v114; // ecx
  __int64 v115; // rax
  const char *v116; // r8
  unsigned __int16 v117; // cx
  bool v118; // dl
  const char *v119; // r8
  enum DXGI_FORMAT v120; // r12d
  __int64 v121; // rax
  unsigned __int16 v122; // cx
  bool v123; // dl
  const char *v124; // rax
  const char *v125; // r8
  int v126; // r9d
  int v127; // r10d
  int v128; // r11d
  const char *v129; // r9
  enum DXGI_FORMAT *v130; // r8
  unsigned __int16 v131; // ax
  unsigned int v132; // r12d
  unsigned __int16 v133; // ax
  int v134; // eax
  unsigned __int16 v135; // cx
  __int64 v136; // rcx
  __int64 v137; // r9
  __int64 v138; // rax
  const bool *v139; // r10
  _DWORD *v140; // r12
  unsigned __int64 v141; // r13
  int v142; // r8d
  enum D3D_FEATURE_LEVEL v143; // r8d
  __int64 v144; // r9
  _DWORD *v145; // rcx
  const char *v146; // rax
  enum DXGI_FORMAT *v147; // r8
  __int64 v148; // r9
  _DWORD *v149; // rcx
  enum DXGI_FORMAT *v150; // r8
  int v151; // r13d
  __int64 v152; // r8
  enum D3D_FEATURE_LEVEL v153; // r12d
  __int64 v154; // rcx
  enum DXGI_FORMAT *v155; // r8
  bool v156; // dl
  int v157; // ecx
  float *v158; // r13
  int v159; // ecx
  unsigned int v160; // r8d
  __int64 v161; // r10
  enum D3D_FEATURE_LEVEL v162; // r11d
  bool v163; // dl
  enum DXGI_FORMAT v164; // r10d
  enum DXGI_FORMAT *v165; // r8
  __int64 v166; // rax
  enum DXGI_FORMAT v167; // ecx
  bool v168; // dl
  enum DXGI_FORMAT v169; // r10d
  enum DXGI_FORMAT *v170; // r8
  bool v171; // dl
  enum DXGI_FORMAT v172; // r10d
  enum DXGI_FORMAT *v173; // r8
  bool v174; // dl
  enum DXGI_FORMAT *v175; // r8
  enum D3D_FEATURE_LEVEL v176; // r12d
  bool v177; // dl
  enum DXGI_FORMAT *v178; // r8
  _OWORD *v179; // rcx
  const enum DXGI_FORMAT *v180; // r13
  const char *v181; // rax
  const char *v182; // r8
  int v183; // r9d
  int v184; // r10d
  int v185; // r11d
  enum DXGI_FORMAT v186; // ecx
  int v187; // eax
  enum DXGI_FORMAT v188; // r9d
  __int64 v189; // rax
  unsigned int v190; // r9d
  unsigned int v191; // r10d
  bool IsBlockCompressFormat; // r11
  __int64 v193; // r8
  enum DXGI_FORMAT v194; // edx
  __int64 v195; // rax
  bool v196; // dl
  enum DXGI_FORMAT v197; // r8d
  __int64 v198; // rax
  __int64 v199; // rcx
  __int64 v200; // rax
  enum DXGI_FORMAT v201; // edi
  __int64 v202; // rax
  int v203; // eax
  bool v204; // dl
  enum DXGI_FORMAT *v205; // r8
  int v206; // ebx
  bool v207; // dl
  const char *v208; // r11
  int v209; // r10d
  enum DXGI_FORMAT *v210; // [rsp+20h] [rbp-E0h]
  enum DXGI_FORMAT *v211; // [rsp+20h] [rbp-E0h]
  enum DXGI_FORMAT *v212; // [rsp+20h] [rbp-E0h]
  enum DXGI_FORMAT *v213; // [rsp+20h] [rbp-E0h]
  const char *v214; // [rsp+28h] [rbp-D8h]
  enum DXGI_FORMAT v215[2]; // [rsp+28h] [rbp-D8h]
  unsigned int *v216; // [rsp+30h] [rbp-D0h]
  unsigned int *v217; // [rsp+38h] [rbp-C8h]
  char v218; // [rsp+80h] [rbp-80h]
  char v219; // [rsp+80h] [rbp-80h]
  char v220; // [rsp+81h] [rbp-7Fh]
  struct D3D12_TILE_SHAPE v221; // [rsp+88h] [rbp-78h] BYREF
  int v222; // [rsp+98h] [rbp-68h]
  unsigned int v223; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v224; // [rsp+A0h] [rbp-60h] BYREF
  float v225; // [rsp+A4h] [rbp-5Ch]
  enum DXGI_FORMAT v226; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v227; // [rsp+ACh] [rbp-54h] BYREF
  const enum DXGI_FORMAT *v228; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v229; // [rsp+B8h] [rbp-48h]
  _DWORD v230[2]; // [rsp+C0h] [rbp-40h] BYREF
  const struct D3D12_CLEAR_VALUE *v231; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v232; // [rsp+D0h] [rbp-30h] BYREF
  struct CD3DX12_RESOURCE_DESC2 *v233; // [rsp+D8h] [rbp-28h]
  int v234; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v235; // [rsp+E4h] [rbp-1Ch]
  unsigned int v236[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v237; // [rsp+100h] [rbp+0h]
  _OWORD v238[2]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v239[96]; // [rsp+130h] [rbp+30h] BYREF
  _DWORD v240[48]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v231 = a4;
  v228 = a6;
  v233 = a8;
  v12 = 0;
  v222 = 0;
  v13 = -2147024809;
  if ( *(int *)a3 >= 5 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      718,
      "D3D12_RESOURCE_DESC::Dimension is unrecognized. The value is %u.",
      *(_DWORD *)a3);
    v12 = -2147024809;
    v222 = -2147024809;
  }
  if ( !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExistsInHeader(*((enum DXGI_FORMAT *)a3 + 8), (bool)a2) )
  {
    TDebugOutputFunctor::operator()(a1, 737, "D3D12_RESOURCE_DESC::Format is unrecognized. The value is %u.", v14);
    v12 = -2147024809;
    v222 = -2147024809;
  }
  if ( *((int *)a3 + 11) >= 5 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      719,
      "D3D12_RESOURCE_DESC::Layout is unrecognized. The value is %u.",
      *(_DWORD *)a3);
    v12 = -2147024809;
    v222 = -2147024809;
  }
  if ( (*((_DWORD *)a3 + 12) & 0xFFFFF000) != 0 )
  {
    v15 = "D3D12_RESOURCE_DESC::Flags has unrecognized bits. The value is 0x%x, and the unrecognized bits are 0x%x.";
    v16 = 719;
LABEL_27:
    TDebugOutputFunctor::operator()(a1, v16, v15);
    return v13;
  }
  if ( v12 < 0 )
    return (unsigned int)v12;
  v17 = (unsigned __int64 *)((char *)a3 + 16);
  v18 = (const char *)*((_QWORD *)a3 + 2);
  if ( !v18 || !*((_DWORD *)a3 + 6) || !*((_WORD *)a3 + 14) )
  {
    LODWORD(v214) = *((unsigned __int16 *)a3 + 14);
    LODWORD(v210) = *((_DWORD *)a3 + 6);
    v47 = "D3D12_RESOURCE_DESC::Width, D3D12_RESOURCE_DESC::Height, and D3D12_RESOURCE_DESC::DepthOrArraySize cannot be 0"
          ". The minimum value is 1. Width = %I64u, Height = %u, and DepthOrArraySize = %u.";
    v48 = 597;
    goto LABEL_449;
  }
  v19 = *((_DWORD *)a2 + 164);
  *(_QWORD *)&v221.WidthInTexels = 4096;
  if ( (v19 == 4096 || v19 == 256) && ((*(_DWORD *)a3 - 1) & 0xFFFFFFFD) != 0 )
  {
    v15 = "The only resource dimension supported by D3D_FEATURE_LEVEL_1_0_CORE/GENERIC devices is BUFFER or TEXTURE2D.";
    v16 = 597;
    goto LABEL_27;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12TightAlignment>::GetImpl'::`2'::impl)
    && (*((_DWORD *)a3 + 12) & 0x400) != 0 )
  {
    if ( !*((_DWORD *)a2 + 259) )
    {
      v15 = "D3D12_RESOURCE_DESC::Flag D3D12_RESOURCE_FLAG_USE_TIGHT_ALIGNMENT is not valid when D3D12_TIGHT_ALIGNMENT_TI"
            "ER.SupportTier is D3D12_TIGHT_ALIGNMENT_TIER_NOT_SUPPORTED.";
LABEL_22:
      v16 = 599;
      goto LABEL_27;
    }
    if ( *((_DWORD *)a3 + 11) == 3 || *((_DWORD *)a3 + 11) == 2 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        599,
        "D3D12_RESOURCE_DESC::Flag D3D12_RESOURCE_FLAG_USE_TIGHT_ALIGNMENT is not valid when the layout is either D3D12_T"
        "EXTURE_LAYOUT_64KB_STANDARD_SWIZZLE or D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE (current layout is %s).");
      return v13;
    }
    if ( *((_QWORD *)a3 + 1) )
    {
      v15 = "D3D12_RESOURCE_DESC::Alignment is invalid. The value is %I64u. When D3D12_RESOURCE_DESC::Flag bit for D3D12_"
            "RESOURCE_FLAG_USE_TIGHT_ALIGNMENT is set, Alignment must be 0.";
      v16 = 721;
      goto LABEL_27;
    }
  }
  if ( *((_DWORD *)a3 + 11) != 4
    || (result = ValidateTextureLayoutGuid(a1, a2, a3, a9), v222 = result, (int)result >= 0) )
  {
    if ( (*((_DWORD *)a3 + 12) & 0x200) != 0 )
    {
      if ( *(_DWORD *)a3 != 4 )
      {
        v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_PROCESS_3DLUT_ONLY set when D3D12_RESOU"
              "RCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_TEXTURE3D.";
        goto LABEL_22;
      }
      if ( !IsValid3DLUTTextureSize(a3, a1) )
        return v13;
    }
    if ( (*((_DWORD *)a3 + 12) & 0x800) != 0 && *(_DWORD *)a3 != 2 )
    {
      v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_PROCESS_1DLUT_ONLY set when D3D12_RESOURC"
            "E_DESC::Dimension is D3D12_RESOURCE_DIMENSION_TEXTURE1D.";
      goto LABEL_22;
    }
    if ( *(_DWORD *)a3 == 1 )
    {
      v88 = *((_QWORD *)a3 + 1);
      if ( (v88 & 0xFFFFFFFFFFFEFFFFuLL) != 0 )
      {
        v89 = "D3D12_RESOURCE_DESC::Alignment is invalid. The value is %I64u. Buffers must have this field set to %I64u (aka. %s) or 0.";
        goto LABEL_140;
      }
      if ( *((_DWORD *)a3 + 6) != 1 || *((_WORD *)a3 + 14) != 1 )
      {
        v15 = "D3D12_RESOURCE_DESC::Height and D3D12_RESOURCE_DESC::DepthOrArraySize must be 1 when D3D12_RESOURCE_DESC::"
              "Dimension is D3D12_RESOURCE_DIMENSION_BUFFER. Height = %u and DepthOrArraySize = %u.";
        v16 = 597;
        goto LABEL_27;
      }
      v90 = *((unsigned __int16 *)a3 + 15);
      if ( (_WORD)v90 != 1 )
      {
        v91 = "D3D12_RESOURCE_DESC::MipLevels must be 1 when D3D12_RESOURCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_B"
              "UFFER. MipLevels = %u.";
        v92 = 722;
        goto LABEL_146;
      }
      v186 = *((_DWORD *)a3 + 8);
      if ( v186 )
      {
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v186, v20);
        v15 = "D3D12_RESOURCE_DESC::Format must be DXGI_FORMAT_UNKNOWN when D3D12_RESOURCE_DESC::Dimension is D3D12_RESOU"
              "RCE_DIMENSION_BUFFER. Format = %s.";
        goto LABEL_205;
      }
      if ( *(_QWORD *)((char *)a3 + 36) == 1 )
      {
        if ( *((_DWORD *)a3 + 11) != 1 )
        {
          D3D12ToStr((const enum D3D12_TEXTURE_LAYOUT *)a3 + 11);
          v15 = "D3D12_RESOURCE_DESC::Layout must be D3D12_TEXTURE_LAYOUT_ROW_MAJOR when D3D12_RESOURCE_DESC::Dimension i"
                "s D3D12_RESOURCE_DIMENSION_BUFFER. Layout = %s.";
          goto LABEL_172;
        }
        v187 = *((_DWORD *)a3 + 12);
        if ( (v187 & 2) != 0 )
        {
          v15 = "D3D12_RESOURCE_DESC::MiscFlag cannot have D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set when D3D12_RESOURC"
                "E_DESC::Dimension is D3D12_RESOURCE_DIMENSION_BUFFER.";
          goto LABEL_22;
        }
        if ( (v187 & 0x20) != 0 )
        {
          v15 = "D3D12_RESOURCE_DESC::MiscFlag cannot have D3D12_RESOURCE_FLAG_ALLOW_SIMULTANEOUS_ACCESS set when D3D12_R"
                "ESOURCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_BUFFER.";
          goto LABEL_22;
        }
        if ( (v187 & 0x40) != 0 )
        {
          v15 = "D3D12_RESOURCE_DESC::Flags cannot have D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY set when D3D12_RE"
                "SOURCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_BUFFER.";
          goto LABEL_22;
        }
        if ( (v187 & 0x80u) != 0 )
        {
          v15 = "D3D12_RESOURCE_DESC::Flags cannot have D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set when D3D12_RE"
                "SOURCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_BUFFER.";
          goto LABEL_22;
        }
        if ( !v231 )
        {
LABEL_384:
          if ( v233 && D3DX12ConditionallyExpandAPIDesc(v233, a3, *((_DWORD *)a2 + 259) >= 1, 0) == a3 )
          {
            *v179 = *(_OWORD *)a3;
            v179[1] = *((_OWORD *)a3 + 1);
            v179[2] = *((_OWORD *)a3 + 2);
            v179[3] = *((_OWORD *)a3 + 3);
            v179[4] = *((_OWORD *)a3 + 4);
          }
          v180 = v228;
          if ( !v228 )
            goto LABEL_431;
          if ( !*((_DWORD *)a2 + 222) )
          {
            TDebugOutputFunctor::operator()(a1, 1342, "pCastableFormats must be NULL");
            return v13;
          }
          v188 = *((_DWORD *)a3 + 8);
          v189 = 0xFFFFFFFFLL;
          if ( (unsigned int)v188 < 0xC0 )
            v189 = (unsigned int)v188;
          if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v189 + 32) & 8) != 0 )
          {
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v188, 5 * v189);
            v15 = "Castable format list: Cannot cast from planar format %s.";
LABEL_417:
            v16 = 1371;
            goto LABEL_27;
          }
          if ( !a5 )
          {
LABEL_431:
            if ( a7 )
            {
              v201 = *(_DWORD *)a3;
              if ( v201 == DXGI_FORMAT_R32G32B32A32_TYPELESS )
              {
                v203 = v222;
              }
              else
              {
                v202 = CD3D12Strings::ToString(v236, (unsigned int)v201, 0);
                if ( *(_QWORD *)(v202 + 24) > 0xFu )
                  v202 = *(_QWORD *)v202;
                TDebugOutputFunctor::operator()(
                  a1,
                  1385,
                  "Only heaps and buffer resources are compatible with SetNextAllocationAddress. Dimension was %s (0x%X)",
                  (const char *)v202,
                  v201);
                std::string::_Tidy_deallocate(v236);
                v203 = -2147024809;
              }
              if ( *((int *)a2 + 250) < 1 )
              {
                TDebugOutputFunctor::operator()(
                  a1,
                  1386,
                  "This device does not support at least D3D12_RECREATEAT_TIER_1 and cannot specify heap and resource virtual addresses.");
                return v13;
              }
              v13 = v203;
              if ( v203 < 0 )
                return v13;
            }
            return 0;
          }
          IsBlockCompressFormat = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v188);
          while ( 1 )
          {
            v193 = v191;
            if ( !IsBlockCompressFormat && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v180[v191]) )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v194, v194);
              Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((_DWORD *)a3 + 8), v204);
              v211 = v205;
              v40 = "Castable format list: Cannot cast from non-compressed format %s to compressed format %s.";
              v41 = 1371;
              goto LABEL_83;
            }
            v195 = 0xFFFFFFFFLL;
            if ( v190 < 0xC0 )
              v195 = v190;
            v196 = *(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v195 + 20);
            v197 = v180[v193];
            v198 = 0xFFFFFFFFLL;
            if ( (unsigned int)v197 < 0xC0 )
              v198 = (unsigned int)v197;
            v199 = 5 * v198;
            v200 = 0xFFFFFFFFLL;
            if ( v196 != *(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 8 * v199 + 20) )
              break;
            if ( (unsigned int)v197 < 0xC0 )
              v200 = (unsigned int)v197;
            if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v200 + 32) & 8) != 0 )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v197, v196);
              v15 = "Castable format list: Cannot cast to planar format %s.";
              goto LABEL_417;
            }
            if ( ++v191 >= a5 )
              goto LABEL_431;
          }
          if ( (unsigned int)v197 < 0xC0 )
            v200 = (unsigned int)v197;
          v206 = *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v200 + 20);
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v197, v196);
          v58 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((_DWORD *)a3 + 8), v207);
          LODWORD(v216) = v206;
          v214 = v208;
          LODWORD(v210) = v209;
          v61 = "Castable format list: Cannot cast from %s with unit size %u to %s with unit size %u.";
          v62 = 1371;
LABEL_97:
          TDebugOutputFunctor::operator()(a1, v62, v61, v58, v210, v214, v216);
          return v13;
        }
        v15 = "pOptimizedClearValue must be NULL when D3D12_RESOURCE_DESC::Dimension is D3D12_RESOURCE_DIMENSION_BUFFER.";
LABEL_359:
        v16 = 815;
        goto LABEL_27;
      }
      v15 = "D3D12_RESOURCE_DESC::SampleDesc must be { Count: 1, Quality: 0 } when D3D12_RESOURCE_DESC::Dimension is D3D1"
            "2_RESOURCE_DIMENSION_BUFFER. SampleDesc = { %u, %u }.";
      goto LABEL_178;
    }
    if ( *(_DWORD *)a3 != 2 && (unsigned int)(*(_DWORD *)a3 - 3) >= 2 )
    {
      D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
      v15 = "D3D12_RESOURCE_DESC::Dimension is invalid. The value is %s.";
LABEL_42:
      v16 = 720;
      goto LABEL_27;
    }
    v220 = 0;
    v22 = 1;
    v218 = 1;
    v234 = *((_DWORD *)a3 + 8);
    v235 = 0;
    v222 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)a2 + 83) + 104LL))(
             *((_QWORD *)a2 + 83),
             3,
             &v234);
    if ( *((int *)a2 + 164) < 45056 )
    {
      v23 = 0x2000;
      v24 = 512;
    }
    else
    {
      v23 = 0x4000;
      v24 = 2048;
    }
    if ( *(_DWORD *)a3 == 2 )
    {
      v25 = 1;
      v223 = 16;
    }
    else if ( *(_DWORD *)a3 == 3 )
    {
      if ( (*((_BYTE *)a2 + 688) & 1) != 0 && (*v17 > v23 || *((_DWORD *)a3 + 6) > v23) )
      {
        v23 = 0x800000;
        v24 = 1;
        v26 = 0;
      }
      else
      {
        v26 = 1;
        v220 = 1;
      }
      v223 = 32;
      v22 = v26;
      v218 = v26;
      v25 = v23;
    }
    else
    {
      v23 = 2048;
      v25 = 2048;
      v24 = 2048;
      v223 = 64;
    }
    if ( *v17 > v23 || *((_DWORD *)a3 + 6) > v25 || (v27 = *((unsigned __int16 *)a3 + 14), v27 > v24) )
    {
      D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
      v181 = FeatureLevelToString((enum D3D_FEATURE_LEVEL)*((_DWORD *)a2 + 164));
      TDebugOutputFunctor::operator()(
        a1,
        597,
        "D3D12_RESOURCE_DESC::Width, D3D12_RESOURCE_DESC::Height, and/ or D3D12_RESOURCE_DESC::DepthOrArraySize are too l"
        "arge for the D3D12_RESOURCE_DESC::Dimension and FeatureLevel. Width = %I64u and must be <= %u, Height = %u and m"
        "ust be <= %u, DepthOrArraySize = %u and must be <= %u, Dimension = %s, and FeatureLevel = %s.",
        *v17,
        v183,
        *((_DWORD *)a3 + 6),
        v184,
        *((unsigned __int16 *)a3 + 14),
        v185,
        v182,
        v181);
      return v13;
    }
    if ( *(_DWORD *)a3 != 4 )
      LOWORD(v27) = 1;
    v28 = (unsigned __int16)v27;
    v229 = (unsigned __int16)v27;
    v29 = *((unsigned int *)a3 + 6);
    v232 = v29;
    if ( *v17 >= v29 )
    {
      v30 = (unsigned __int64 *)((char *)a3 + 16);
      v31 = *v17;
    }
    else
    {
      v30 = &v232;
      v31 = (unsigned int)v29;
    }
    if ( v31 >= v28 )
    {
      v28 = *v30;
      v229 = *v30;
    }
    v32 = 0;
    if ( v22 )
      v33 = MaxMipLevels(v28);
    else
      v33 = 1;
    v34 = *((_WORD *)a3 + 15);
    if ( v34 )
    {
      if ( v34 > v33 )
      {
        if ( v28 == *((_QWORD *)a3 + 2) )
        {
          v35 = "Width";
        }
        else
        {
          v35 = "Height";
          if ( v28 != v29 )
            v35 = "DepthOrArraySize";
        }
        TDebugOutputFunctor::operator()(
          a1,
          722,
          "D3D12_RESOURCE_DESC::MipLevels must be 0 or <= %u when the largest texture dimension, D3D12_RESOURCE_DESC::%s,"
          " is %I64u. MipLevels is %u.",
          v33,
          v35,
          v28,
          *((unsigned __int16 *)a3 + 15));
        v32 = 0;
        if ( !v218 )
          return v13;
      }
    }
    else
    {
      v34 = v33;
    }
    if ( (*((_DWORD *)a3 + 8) == 189 || *((_DWORD *)a3 + 8) == 190) && *((_DWORD *)a2 + 209) == v32 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1255,
        "A sampler feedback DXGI_FORMAT was specified, but the device reports D3D12_SAMPLER_FEEDBACK_TIER_NONE.");
      return v13;
    }
    if ( v222 < 0 )
    {
      FeatureLevelToString(*((enum D3D_FEATURE_LEVEL *)a2 + 164));
      Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v37, v36);
      v211 = v39;
      v40 = "D3D12_RESOURCE_DESC::Format is not supported at the current feature level. Format = %s and FeatureLevel is %s.";
      v41 = 738;
LABEL_83:
      TDebugOutputFunctor::operator()(a1, v41, v40, Name, v211);
      return v13;
    }
    if ( ((unsigned int)v235 & v223) == 0 )
    {
      D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
      FeatureLevelToString(*((enum D3D_FEATURE_LEVEL *)a2 + 164));
      v44 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v43, v42);
      v214 = v45;
      v210 = v46;
      v47 = "D3D12_RESOURCE_DESC::Format is not supported with D3D12_RESOURCE_DESC::Dimension at the current feature leve"
            "l. Format = %s, Dimension = %s, FeatureLevel is %s.";
LABEL_86:
      v18 = v44;
      v48 = 720;
LABEL_449:
      TDebugOutputFunctor::operator()(a1, v48, v47, v18, v210, v214);
      return v13;
    }
    if ( !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(*((enum DXGI_FORMAT *)a3 + 8))
      || *((_DWORD *)a2 + 210) == (_DWORD)v53 )
    {
      v54 = (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v50 + 6) >> 4) & 0xF;
      v49 = *((_QWORD *)a3 + 2)
          % (unsigned __int64)(*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v49 + 6) & 0xF);
      if ( v49 || (LODWORD(v49) = *((_DWORD *)a3 + 6) % v54, (_DWORD)v49) )
      {
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v49);
        TDebugOutputFunctor::operator()(
          a1,
          597,
          "Textures created with certain Formats must align the resource dimensions properly. D3D12_RESOURCE_DESC::Format"
          " is %s. D3D12_RESOURCE_DESC::Width is %I64u, and must be a multiple of %u. D3D12_RESOURCE_DESC::Height is %u, "
          "and must be a multiple of %u.");
        return v13;
      }
      v52 = v235;
      v53 = 0;
    }
    if ( v34 > 1u && (v52 & 0x1000) == 0 )
    {
      FeatureLevelToString(*((enum D3D_FEATURE_LEVEL *)a2 + 164));
      v57 = "auto calculated from resource dimensions to be ";
      if ( *((_WORD *)a3 + 15) )
        v57 = Src;
      v58 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v56, v55);
      v216 = v59;
      LODWORD(v214) = v60;
      v210 = (enum DXGI_FORMAT *)v57;
      v61 = "D3D12_RESOURCE_DESC::MipLevels must be 1 when D3D12_RESOURCE_DESC::Format is %s, at the current feature leve"
            "l. MipLevels is %s%u. FeatureLevel is %s.D3D12_FEATURE_DATA_FORMAT_SUPPORT::Support1 does not include D3D12_"
            "FORMAT_SUPPORT1_MIP when calling CheckFeatureSupport with D3D12_FEATURE_FORMAT_SUPPORT.";
      v62 = 722;
      goto LABEL_97;
    }
    v63 = *((_DWORD *)a3 + 9);
    if ( !v63 )
    {
      TDebugOutputFunctor::operator()(a1, 723, "D3D12_RESOURCE_DESC::SampleDesc::Count cannot be 0.");
      return v13;
    }
    if ( v63 != 1 )
    {
      if ( v34 != 1 || v220 == (_BYTE)v53 )
      {
        v79 = D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
        v81 = "auto calculated from resource dimensions to be ";
        if ( *((_WORD *)a3 + 15) )
          v81 = Src;
        TDebugOutputFunctor::operator()(
          a1,
          723,
          "D3D12_RESOURCE_DESC::SampleDesc::Count must be 1 when number of mip levels is not 1, or Dimension is not D3D12"
          "_RESOURCE_DIMENSION_TEXTURE2D. SampleDesc::Count is %u, MipLevels is %s%u, and Dimension is %s.",
          v80,
          v81,
          v34,
          v79);
        return v13;
      }
      v236[0] = v51;
      v236[1] = v63;
      v64 = v53;
      LOBYTE(v64) = *((_DWORD *)a3 + 11) == 2;
      v236[2] = v64;
      v236[3] = v53;
      v222 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *))(**((_QWORD **)a2 + 83) + 104LL))(
               *((_QWORD *)a2 + 83),
               4,
               v236);
      v65 = *((_DWORD *)a3 + 10);
      if ( v65 > 0xFFFFFFFD )
      {
        v73 = v236[3];
        v53 = 0;
        if ( *((_DWORD *)a3 + 9) != 1
          && *((_DWORD *)a3 + 9) != 2
          && *((_DWORD *)a3 + 9) != 4
          && *((_DWORD *)a3 + 9) != 8
          && *((_DWORD *)a3 + 9) != 16
          || !v236[3] )
        {
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v49);
          v74 = FeatureLevelToString((enum D3D_FEATURE_LEVEL)*((_DWORD *)a2 + 164));
          v77 = "DXGI_STANDARD_MULTISAMPLE_QUALITY_PATTERN";
          if ( v78 != -1 )
            v77 = "DXGI_CENTER_MULTISAMPLE_QUALITY_PATTERN";
          TDebugOutputFunctor::operator()(
            a1,
            723,
            "The well-known multisample quality patterns are not supported. The device must support D3D_FEATURE_LEVEL_10_"
            "1 or greater, and multisampling for the particular format and sample count. Well-known multisample quality p"
            "atterns can only be used with D3D12_RESOURCE_DESC::SampleDesc::Count equal to 1, 2, 4, 8, or 16. But, suppor"
            "t for each sample count value and format must still be verified. DXGI_SAMPLE_DESC::Count is %u, DXGI_SAMPLE_"
            "DESC::Quality is %s, FeatureLevel is %s, D3D12_RESOURCE_DESC::Format is %s. D3D12_FEATURE_DATA_MULTISAMPLE_Q"
            "UALITY_LEVELS::NumQualityLevels is %u when calling CheckFeatureSupport with D3D12_FEATURE_MULTISAMPLE_QUALITY_LEVELS%s.",
            *((_DWORD *)a3 + 9),
            v77,
            v74,
            v75,
            v73,
            v76);
          return v13;
        }
      }
      else
      {
        if ( v65 >= v236[3] )
        {
          v66 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((_DWORD *)a3 + 8), v49);
          v217 = v67;
          LODWORD(v216) = v68;
          *(_QWORD *)v215 = v66;
          LODWORD(v210) = v69;
          v70 = *((unsigned int *)a3 + 9);
          v71 = "The multisample quality value is not supported. Support for each sample count value and format must be v"
                "erified. DXGI_SAMPLE_DESC::Count is %u, DXGI_SAMPLE_DESC::Quality is %u, D3D12_RESOURCE_DESC::Format is "
                "%s. D3D12_FEATURE_DATA_MULTISAMPLE_QUALITY_LEVELS::NumQualityLevels is %u when calling CheckFeatureSuppo"
                "rt with D3D12_FEATURE_MULTISAMPLE_QUALITY_LEVELS%s.";
          v72 = 723;
LABEL_106:
          TDebugOutputFunctor::operator()(a1, v72, v71, v70, v210, *(_QWORD *)v215, v216, v217);
          return v13;
        }
        v53 = 0;
      }
      if ( (*((_BYTE *)a3 + 48) & 3) == 0 )
      {
        v15 = "A multisampled resource must have either D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_AL"
              "LOW_DEPTH_STENCIL set in D3D12_RESOURCE_DESC::Flags. DXGI_SAMPLE_DESC::Count is %u, DXGI_SAMPLE_DESC::Quality is %u.";
LABEL_119:
        v16 = 599;
        goto LABEL_27;
      }
      if ( (*((_BYTE *)a3 + 48) & 4) != 0 && !*((_DWORD *)a2 + 230) )
      {
        v15 = "A multisampled resource cannot set D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS in D3D12_RESOURCE_DESC::Flag"
              "s since the device does not expose WriteableMSAATexturesSupported.DXGI_SAMPLE_DESC::Count is %u, DXGI_SAMP"
              "LE_DESC::Quality is %u.";
        goto LABEL_119;
      }
      if ( (*((_BYTE *)a3 + 48) & 0x20) != 0 )
      {
        v15 = "A multisampled resource cannot set D3D12_RESOURCE_FLAG_ALLOW_SIMULTANEOUS_ACCESS in D3D12_RESOURCE_DESC::F"
              "lags.DXGI_SAMPLE_DESC::Count is %u, DXGI_SAMPLE_DESC::Quality is %u.";
        goto LABEL_119;
      }
    }
    v82 = *((_DWORD *)a3 + 11);
    if ( v82 )
    {
      v83 = v82 - 1;
      if ( v83 )
      {
        v84 = v83 - 1;
        if ( v84 )
        {
          if ( v84 != 1 )
          {
            v85 = *((_QWORD *)a3 + 8) - D3D12_GUID_TEXTURE_LAYOUT_ROW_MAJOR_WITH_RENDER_AND_VPBLT_CAPABILITY;
            if ( !v85 )
              v85 = *((_QWORD *)a3 + 9) + 0x4734638E35F29846LL;
            v86 = v85 == 0;
            v87 = *((_QWORD *)a3 + 8)
                - D3D12_GUID_TEXTURE_LAYOUT_ROW_MAJOR_WITH_RENDER_AND_VPBLT_CAPABILITY_8_ROW_ALIGNMENT;
            if ( !v87 )
              v87 = *((_QWORD *)a3 + 9) - 0x59A2C6E1B7F4D83LL;
            if ( !v86 && v87 )
              goto LABEL_169;
            v88 = *((_QWORD *)a3 + 1);
            if ( (v88 & 0xFFFFFFFFFFFEFFFFuLL) != 0 )
            {
              v89 = "D3D12_RESOURCE_DESC::Alignment is invalid. The value is %I64u. When LayoutGuid is D3D12_GUID_TEXTURE"
                    "_LAYOUT_ROW_MAJOR_WITH_RENDER_AND_VPBLT_CAPABILITY, the Alignment field must be either %I64u (aka. %s) or 0.";
LABEL_140:
              TDebugOutputFunctor::operator()(a1, 721, v89, v88, 0x10000, "D3D12_DEFAULT_RESOURCE_PLACEMENT_ALIGNMENT");
              return v13;
            }
            if ( *(_DWORD *)a3 != 3 )
            {
              D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
              v15 = "D3D12_RESOURCE_DESC::Dimension is invalid.  The value is %s. D3D12_GUID_TEXTURE_LAYOUT_ROW_MAJOR_WIT"
                    "H_RENDER_AND_VPBLT_CAPABILITY is only supported with D3D12_RESOURCE_DIMENSION_TEXTURE2D.";
              goto LABEL_42;
            }
            v90 = *((unsigned __int16 *)a3 + 15);
            if ( (_WORD)v90 != 1 )
            {
              v91 = "D3D12_RESOURCE_DESC::MipLevels is invalid.  The value is %u.  When LayoutGuid is D3D12_GUID_TEXTURE_"
                    "LAYOUT_ROW_MAJOR_WITH_RENDER_AND_VPBLT_CAPABILITY, MipLevels must be 1.";
LABEL_145:
              v92 = 722;
LABEL_146:
              v93 = v90;
LABEL_147:
              TDebugOutputFunctor::operator()(a1, v92, v91, v93);
              return v13;
            }
            v90 = *((unsigned __int16 *)a3 + 14);
            if ( (_WORD)v90 != 1 )
            {
              v91 = "D3D12_RESOURCE_DESC::DepthOrArraySize is invalid.  The value is %u.  When LayoutGuid is D3D12_GUID_T"
                    "EXTURE_LAYOUT_ROW_MAJOR_WITH_RENDER_AND_VPBLT_CAPABILITY, DepthOrArraySize must be 1.";
LABEL_150:
              v92 = 597;
              goto LABEL_146;
            }
            if ( *(_QWORD *)((char *)a3 + 36) == __PAIR64__(v53, 1) )
            {
              v93 = *((unsigned int *)a3 + 12);
              if ( (v93 & 2) != 0 )
              {
                v91 = "D3D12_RESOURCE_DESC::Flags is invalid.  The value is 0x%x.  When LayoutGuid is D3D12_GUID_TEXTURE_"
                      "LAYOUT_ROW_MAJOR_WITH_RENDER_AND_VPBLT_CAPABILITY, the D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL fla"
                      "g cannot be set.";
LABEL_154:
                v92 = 599;
                goto LABEL_147;
              }
              v94 = *((_DWORD *)a3 + 8);
              PlaneCount = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetPlaneCount(v94);
              v224 = PlaneCount;
              if ( PlaneCount )
              {
                v98 = 4 * v97 + 4;
                v225 = *(float *)&v98;
                v99 = *(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v96 + 32) & 8;
                v219 = v99;
                v100 = 0;
                while ( 1 )
                {
                  v101 = v94;
                  v226 = v94;
                  v102 = *((_DWORD *)a3 + 6);
                  v227 = v102;
                  if ( v99 )
                  {
                    v223 = 0;
                    v236[0] = 0;
                    D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetPlaneSubsampledSizeAndFormatForCopyableLayout(
                      v100,
                      v94,
                      *((_DWORD *)a3 + 4),
                      *((_DWORD *)a3 + 6),
                      &v226,
                      &v223,
                      v236,
                      &v227);
                    LODWORD(v49) = v223;
                    v101 = v226;
                    v102 = v227;
                    v98 = LODWORD(v225);
                    v99 = v219;
                  }
                  else
                  {
                    LODWORD(v49) = *((_DWORD *)a3 + 4);
                  }
                  v103 = 0xFFFFFFFFLL;
                  if ( (unsigned int)v101 < 0xC0 )
                    v103 = (unsigned int)v101;
                  v104 = (unsigned int)v49
                       * ((unsigned __int64)*((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
                                            + 40 * v103
                                            + 20) >> 3);
                  LOBYTE(v49) = 0;
                  if ( (_BYTE)v104 )
                    break;
                  LODWORD(v49) = v102 % v98;
                  if ( v102 % v98 )
                  {
                    v221.WidthInTexels = v98;
                    goto LABEL_176;
                  }
                  if ( v99 && v100 + 1 < v224 && (((_WORD)v104 * (_WORD)v102) & 0xFFF) != 0 )
                    goto LABEL_176;
                  if ( ++v100 >= v224 )
                    goto LABEL_168;
                }
                v221.WidthInTexels = 256;
LABEL_176:
                v105 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((_DWORD *)a3 + 8), v49);
                TDebugOutputFunctor::operator()(
                  a1,
                  597,
                  "D3D12_RESOURCE_DESC dimensions are not naturally aligned for the row-major GUID texture layout. Plane "
                  "%u %s = %I64u must be a multiple of %u. Format = %s, Width = %I64u, Height = %u, GUID height alignment = %u.",
                  v100,
                  v107,
                  v106,
                  v221.WidthInTexels,
                  v105,
                  *((_QWORD *)a3 + 2),
                  *((_DWORD *)a3 + 6),
                  v108);
                return v13;
              }
              goto LABEL_169;
            }
            v15 = "D3D12_RESOURCE_DESC::SampleDesc is invalid.  Count is %u, quality is %u.  When LayoutGuid is D3D12_GUI"
                  "D_TEXTURE_LAYOUT_ROW_MAJOR_WITH_RENDER_AND_VPBLT_CAPABILITY, the sample count must be 1, and the sampl"
                  "e quality must be 0.";
            goto LABEL_178;
          }
          if ( *((_DWORD *)a3 + 9) > 1u || (*((_BYTE *)a3 + 48) & 2) != 0 )
            goto LABEL_185;
          v109 = 0xFFFFFFFFLL;
          if ( *((_DWORD *)a3 + 8) < 0xC0u )
            v109 = *((unsigned int *)a3 + 8);
          if ( *(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v109 + 20) == 96 || *(_DWORD *)a3 == 2 )
          {
LABEL_185:
            v110 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((_DWORD *)a3 + 8), v49);
            LODWORD(v214) = v111;
            TDebugOutputFunctor::operator()(
              a1,
              724,
              "D3D12_RESOURCE_DESC::Layout is invalid due to interactions with other resource properties. When it is D3D1"
              "2_TEXTURE_LAYOUT_64KB_STANDARD_SWIZZLE, D3D12_RESOURCE_DESC::Format can not be one of the DXGI_FORMAT_R32G"
              "32B32_TYPELESS group, D3D12_RESOURCE_DESC:Flags cannot have D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set, a"
              "nd D3D12_RESOURCE_DESC::SampleDesc::Count must be 1. Format is %s, D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL"
              " is %s set, and Count is %u.",
              v110,
              v112,
              v214);
            return v13;
          }
        }
        if ( (*((_QWORD *)a3 + 1) & 0xFFFFFFFFFFFEFFFFuLL) == 0 )
          goto LABEL_169;
      }
      else if ( (*((_QWORD *)a3 + 1) & 0xFFFFFFFFFFFEFFFFuLL) == 0 )
      {
        if ( *(_DWORD *)a3 != 3 )
        {
          D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
          v15 = "D3D12_RESOURCE_DESC::Dimension is invalid.  The value is %s.  D3D12_TEXTURE_LAYOUT_ROW_MAJOR is only sup"
                "ported with D3D12_RESOURCE_DIMENSION_BUFFER or D3D12_RESOURCE_DIMENSION_TEXTURE2D.";
          goto LABEL_42;
        }
        v90 = *((unsigned __int16 *)a3 + 15);
        if ( (_WORD)v90 != 1 )
        {
          v91 = "D3D12_RESOURCE_DESC::MipLevels is invalid.  The value is %u.  When D3D12_RESOURCE_DESC::Layout is D3D12_"
                "TEXTURE_LAYOUT_ROW_MAJOR, MipLevels must be 1.";
          goto LABEL_145;
        }
        v90 = *((unsigned __int16 *)a3 + 14);
        if ( (_WORD)v90 != 1 )
        {
          v91 = "D3D12_RESOURCE_DESC::DepthOrArraySize is invalid.  The value is %u.  When D3D12_RESOURCE_DESC::Layout is"
                " D3D12_TEXTURE_LAYOUT_ROW_MAJOR, DepthOrArraySize must be 1.";
          goto LABEL_150;
        }
        if ( *(_QWORD *)((char *)a3 + 36) == __PAIR64__(v53, 1) )
        {
          v93 = *((unsigned int *)a3 + 12);
          if ( (v93 & 2) != 0 )
          {
            v91 = "D3D12_RESOURCE_DESC::Flags is invalid.  The value is 0x%x.  When D3D12_RESOURCE_DESC::Layout is D3D12_"
                  "TEXTURE_LAYOUT_ROW_MAJOR, the D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL flag cannot be set.";
            goto LABEL_154;
          }
          *(_OWORD *)v236 = 0;
          v237 = 0;
          memset(v238, 0, 28);
          v222 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, __int64))(**((_QWORD **)a2 + 83) + 104LL))(
                   *((_QWORD *)a2 + 83),
                   0,
                   v236,
                   60);
          v53 = 0;
          if ( !LODWORD(v238[1]) )
          {
            v93 = *((unsigned int *)a3 + 12);
            if ( (v93 & 5) != 0 )
            {
              v91 = "D3D12_RESOURCE_DESC::Flags is invalid.  The value is 0x%x.  The D3D12 device being used only support"
                    "s copies to/from row major textures.  Neither D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET nor D3D12_RESO"
                    "URCE_FLAG_ALLOW_UNORDERED_ACCESS may be set.";
              goto LABEL_154;
            }
          }
          v114 = *((_DWORD *)a3 + 8);
          v115 = 0xFFFFFFFFLL;
          if ( (unsigned int)v114 < 0xC0 )
            v115 = (unsigned int)v114;
          LOBYTE(v49) = 5 * v115;
          if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v115 + 32) & 0x10) != 0 )
          {
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v114, v49);
            v15 = "D3D12_RESOURCE_DESC::Format is invalid.  The value is %s.  When D3D12_RESOURCE_DESC::Layout is D3D12_T"
                  "EXTURE_LAYOUT_ROW_MAJOR, the format cannot be YUV.";
LABEL_205:
            v16 = 738;
            goto LABEL_27;
          }
LABEL_169:
          if ( *((_DWORD *)a3 + 11) == 2 )
          {
            v49 = (unsigned __int64)a2 + 640;
            if ( *((_DWORD *)a2 + 160) == (_DWORD)v53 )
            {
              D3D12ToStr((const enum D3D12_TILED_RESOURCES_TIER *)a2 + 160);
              v15 = "The D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE layout cannot be used on a device that does not supp"
                    "ort tiled resources. CheckFeatureLevel with D3D12_FEATURE_D3D12_OPTIONS indicates D3D12_FEATURE_DATA"
                    "_D3D12_OPTIONS::TiledResourcesTier is %s.";
LABEL_172:
              v16 = 724;
              goto LABEL_27;
            }
            if ( *(_DWORD *)a3 == 2 )
            {
              TDebugOutputFunctor::operator()(
                a1,
                724,
                "The D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE layout cannot be used on a Texture1D resource (these can't be tiled). ");
              return v13;
            }
            if ( *(_DWORD *)a3 != 3 )
            {
              if ( *(_DWORD *)a3 != 4 )
                goto LABEL_281;
              if ( *(int *)v49 <= 2 )
              {
                if ( *((_DWORD *)a2 + 200) == (_DWORD)v53 )
                {
                  D3D12ToStr((const enum D3D12_TILED_RESOURCES_TIER *)a2 + 160);
                  v44 = D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
                  v214 = v129;
                  v210 = v130;
                  v47 = "Textures with layout D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE cannot be created when the tile"
                        "d resource capabilities do not support D3D12_RESOURCE_DESC::Dimension of %s. D3D12_FEATURE_DATA_"
                        "D3D12_OPTIONS::TiledResourcesTier is %s. D3D12_FEATURE_DATA_D3D12_OPTIONS5::SRVOnlyTiledResourceTier3 is %s.";
                  goto LABEL_86;
                }
                if ( (*((_DWORD *)a3 + 12) & 7) != 0 )
                {
                  D3D12ToStr((const enum D3D12_TILED_RESOURCES_TIER *)a2 + 160);
                  v124 = D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
                  TDebugOutputFunctor::operator()(
                    a1,
                    720,
                    "Textures with layout D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE and most resource flags cannot be c"
                    "reated when the tiled resource capabilities do not support full orthogonality for %s. D3D12_FEATURE_"
                    "DATA_D3D12_OPTIONS::TiledResourcesTier is %s. D3D12_FEATURE_DATA_D3D12_OPTIONS5::SRVOnlyTiledResourc"
                    "eTier3 is %s. The following flags are not supported, unless TiledResourcesTier is D3D12_TILED_RESOUR"
                    "CES_TIER_3 or greater: D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET = %u. D3D12_RESOURCE_FLAG_ALLOW_DEPTH"
                    "_STENCIL = %u. D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS = %u. ",
                    v124,
                    v125,
                    "TRUE",
                    v126,
                    v127,
                    v128);
                  return v13;
                }
              }
            }
            *(_QWORD *)&v236[1] = v53;
            v236[0] = *((_DWORD *)a3 + 8);
            (*(void (__fastcall **)(_QWORD, __int64, unsigned int *))(**((_QWORD **)a2 + 83) + 104LL))(
              *((_QWORD *)a2 + 83),
              3,
              v236);
            if ( (v236[2] & 0x200) == 0 )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v49);
              v15 = "Textures with layout D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWIZZLE cannot be created when the D3D12_RE"
                    "SOURCE_DESC::Format does not support tiled resources. Format is %s. D3D12_FORMAT_SUPPORT2_TILED is n"
                    "ot set for D3D12_FEATURE_FORMAT_SUPPORT.";
              goto LABEL_205;
            }
            if ( *(_DWORD *)a3 != 4 && *((_WORD *)a3 + 14) > 1u )
            {
              LODWORD(v49) = *((_DWORD *)a3 + 9);
              if ( (_DWORD)v49 == 1
                || *((_DWORD *)a3 + 9) == 2
                || *((_DWORD *)a3 + 9) == 4
                || *((_DWORD *)a3 + 9) == 8
                || *((_DWORD *)a3 + 9) == 16 )
              {
                *(_QWORD *)&v221.WidthInTexels = 0;
                v221.DepthInTexels = 0;
                v224 = 0;
                v131 = *((_WORD *)a3 + 15);
                if ( !v131 )
                  v131 = MaxMipLevels(v229);
                v132 = v131;
                LOBYTE(v216) = 0;
                LOBYTE(v214) = v131;
                GenerateMipTiling(
                  *((unsigned int *)a3 + 4),
                  *((unsigned int *)a3 + 6),
                  1,
                  *((unsigned __int16 *)a3 + 14),
                  v49,
                  (_DWORD)v214,
                  (_DWORD)v216,
                  0,
                  3,
                  *((_DWORD *)a3 + 8),
                  *((_DWORD *)a2 + 164),
                  *((_DWORD *)a2 + 165),
                  v240,
                  &v221,
                  &v224);
                if ( *(_DWORD *)a3 == 4 )
                  v133 = *((_WORD *)a3 + 14);
                else
                  v133 = 1;
                GenerateMipInfo(
                  (struct D3D_MIPINFO *)v239,
                  v132,
                  *((_DWORD *)a3 + 4),
                  *((_DWORD *)a3 + 6),
                  v133,
                  *((enum DXGI_FORMAT *)a3 + 8));
                v134 = *((_DWORD *)a2 + 160);
                if ( v134 == 1 )
                {
                  if ( *(_DWORD *)a3 == 4 )
                    v135 = 1;
                  else
                    v135 = *((_WORD *)a3 + 14);
                  v49 = ((unsigned __int64)v224 << 16) % v135;
                  if ( ((unsigned __int64)v224 << 16) / v135 > 0x3FFFFFFFCLL )
                  {
                    TDebugOutputFunctor::operator()(
                      a1,
                      597,
                      "The Dimensions are too large for a Tiled Resource with multiple array slices on device with Tier 1"
                      " level of support. At this Tier, resources with multiple array slices cannot have individual array"
                      " slices larger than 2^24 - 1 (%I64u) bytes in virtual address space. The requested surface dimensi"
                      "ons padded to tile size require roughly %I64u bytes.",
                      0x3FFFFFFFCLL,
                      ((unsigned __int64)v224 << 16) / v135);
                    return v13;
                  }
                  v70 = 0;
                  if ( v132 )
                  {
                    while ( !(v239[6 * (unsigned int)v70] % v221.WidthInTexels) )
                    {
                      LODWORD(v49) = v239[6 * (unsigned int)v70 + 1] % v221.HeightInTexels;
                      if ( (_DWORD)v49 )
                        break;
                      v70 = (unsigned int)(v70 + 1);
                      if ( (unsigned int)v70 >= v132 )
                        goto LABEL_281;
                    }
                    LODWORD(v217) = v221.HeightInTexels;
                    LODWORD(v216) = v221.WidthInTexels;
                    v215[0] = (enum DXGI_FORMAT)v239[6 * (unsigned int)v70 + 1];
                    LODWORD(v210) = v239[6 * (unsigned int)v70];
                    v71 = "On a device with Tier 1 Tiled Resources support, Tiled Resources cannot be created with both m"
                          "ore than one array slice and any mipmap that has a dimension not a multiple of a tile in exten"
                          "t. For the Tiled Resource being created, Mip [%u] has (width=%u, height=%u) while the tile dim"
                          "ension for the given format is (width=%u, height=%u). ";
LABEL_268:
                    v72 = 597;
                    goto LABEL_106;
                  }
                }
                else if ( v134 >= 2 && v134 < 4 )
                {
                  v70 = 0;
                  if ( v132 )
                  {
                    LOBYTE(v49) = v221.HeightInTexels;
                    while ( 1 )
                    {
                      if ( v240[3 * (unsigned int)v70] == 1 )
                      {
                        v136 = 6LL * (unsigned int)v70;
                        if ( v221.WidthInTexels > v239[v136] )
                          break;
                      }
                      if ( LOWORD(v240[3 * (unsigned int)v70 + 1]) == 1 )
                      {
                        v136 = 6LL * (unsigned int)v70;
                        if ( v221.HeightInTexels > v239[v136 + 1] )
                          break;
                      }
                      v70 = (unsigned int)(v70 + 1);
                      if ( (unsigned int)v70 >= v132 )
                        goto LABEL_281;
                    }
                    LODWORD(v217) = v221.HeightInTexels;
                    LODWORD(v216) = v221.WidthInTexels;
                    v215[0] = (enum DXGI_FORMAT)v239[v136 + 1];
                    LODWORD(v210) = v239[v136];
                    v71 = "On a device with Tier 2 & 3 Tiled Resources support, Tiled Resources cannot be created with bo"
                          "th more than one array slice and any mipmap that has a dimension less than a tile in extent. F"
                          "or the Tiled Resource being created, Mip [%u] has (width=%u, height=%u) while the tile dimensi"
                          "on for the given format is (width=%u, height=%u). Hardware support in this area was not able t"
                          "o be standardized in time to be included in D3D.";
                    goto LABEL_268;
                  }
                }
              }
            }
          }
LABEL_281:
          v137 = *((int *)a3 + 8);
          v230[0] = v137;
          v230[1] = 0;
          v138 = 0xFFFFFFFFLL;
          if ( (unsigned int)v137 < 0xC0 )
            v138 = (unsigned int)v137;
          v139 = &D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v138 + 6) & 0xC00) == 0x800
            || (v140 = v230, *(_QWORD *)v236 = v230, *(_DWORD *)a3 == 3)
            && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::CanBeCastEvenFullyTyped(
                 (enum DXGI_FORMAT)v137,
                 *((enum D3D_FEATURE_LEVEL *)a2 + 164)) )
          {
            v140 = *(_DWORD **)&v139[40 * v137 + 8];
            *(_QWORD *)v236 = v140;
          }
          v225 = *(float *)&v139[40 * v137 + 4];
          v141 = *(_QWORD *)&v139[40 * SLODWORD(v225) + 8];
          v229 = v141;
          if ( (*((_BYTE *)a3 + 48) & 4) != 0 )
          {
            v142 = *((_DWORD *)a2 + 164);
            if ( v142 < 45056 )
            {
              D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
              v213 = (enum DXGI_FORMAT *)FeatureLevelToString(v143);
              TDebugOutputFunctor::operator()(
                a1,
                599,
                "Textures cannot be used as unordered access resources when the feature level is less than D3D_FEATURE_LE"
                "VEL_11_0. D3D12_RESOURCE_DESC::Dimension is %s. D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLAG_ALLOW"
                "_UNORDERED_ACCESS set. FeatureLevel is %s.",
                v144,
                v213);
              return v13;
            }
            if ( (unsigned int)(v137 - 189) >= 2 )
            {
              if ( !*((_DWORD *)a2 + 222)
                || !v228
                || (LODWORD(v210) = *((_DWORD *)a2 + 165),
                    (int)ValidateTypedUnorderedAccessViewFormats(
                           v228,
                           *((_QWORD *)a2 + 83),
                           *((unsigned int *)a3 + 8),
                           (unsigned int)v142,
                           v210,
                           a5) < 0) )
              {
                LODWORD(v210) = *((_DWORD *)a2 + 165);
                v145 = (int)v210 < 6 ? v140 : (_DWORD *)v141;
                if ( (int)ValidateTypedUnorderedAccessViewFormats(
                            v145,
                            *((_QWORD *)a2 + 83),
                            *((unsigned int *)a3 + 8),
                            *((unsigned int *)a2 + 164),
                            v210,
                            -1) < 0 )
                {
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v49);
                  v146 = FeatureLevelToString((enum D3D_FEATURE_LEVEL)*((_DWORD *)a2 + 164));
                  v214 = Src;
                  v210 = v147;
                  v47 = "A texture that has D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS set in D3D12_RESOURCE_DESC::Flags "
                        "must be created with a format that either can be used as unordered access, or cast to a format t"
                        "hat could be used as unordered access. FeatureLevel is %s. D3D12_RESOURCE_DESC::Format is %s.%s";
LABEL_298:
                  v18 = v146;
                  v48 = 599;
                  goto LABEL_449;
                }
              }
            }
          }
          if ( (*((_BYTE *)a3 + 48) & 1) != 0
            && (!*((_DWORD *)a2 + 222)
             || !v228
             || (int)ValidateRenderTargetViewFormats(
                       v228,
                       *((_QWORD *)a2 + 83),
                       *((unsigned int *)a2 + 164),
                       *((unsigned int *)a2 + 165),
                       a5) < 0) )
          {
            v148 = *((unsigned int *)a2 + 165);
            v149 = (int)v148 < 6 ? v140 : (_DWORD *)v141;
            if ( (int)ValidateRenderTargetViewFormats(v149, *((_QWORD *)a2 + 83), *((unsigned int *)a2 + 164), v148, -1) < 0 )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v49);
              v146 = FeatureLevelToString((enum D3D_FEATURE_LEVEL)*((_DWORD *)a2 + 164));
              v214 = Src;
              v210 = v150;
              v47 = "A texture that has D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET set in D3D12_RESOURCE_DESC::Flags must be"
                    " created with a format that either can be used as a render target, or cast to a format that could be"
                    " used as a render target. FeatureLevel is %s. D3D12_RESOURCE_DESC::Format is %s.%s";
              goto LABEL_298;
            }
          }
          v151 = *((_DWORD *)a3 + 12);
          if ( (v151 & 2) != 0 )
          {
            if ( (v151 & 0x25) != 0 )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags cannot have D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set with D3D12_RESOUR"
                    "CE_FLAG_ALLOW_RENDER_TARGET, D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS, nor D3D12_RESOURCE_FLAG_ALL"
                    "OW_SIMULTANEOUS_ACCESS.";
              goto LABEL_22;
            }
            if ( !*((_DWORD *)a2 + 222)
              || !v228
              || (int)ValidateDepthStencilViewFormats(
                        v228,
                        *((unsigned int *)a2 + 164),
                        *((unsigned int *)a2 + 165),
                        a5) < 0 )
            {
              v152 = *((unsigned int *)a2 + 165);
              v153 = *((_DWORD *)a2 + 164);
              v154 = (int)v152 < 6 ? *(_QWORD *)v236 : v229;
              if ( (int)ValidateDepthStencilViewFormats(v154, *((unsigned int *)a2 + 164), v152, -1) < 0 )
              {
                D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v49);
                v146 = FeatureLevelToString(v153);
                v214 = Src;
                v210 = v155;
                v47 = "A texture that has D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL set in D3D12_RESOURCE_DESC::Flags must "
                      "be created with a format that either can be used as a depth stencil, or cast to a format that coul"
                      "d be used as a depth stencil. FeatureLevel is %s. D3D12_RESOURCE_DESC::Format is %s.%s";
                goto LABEL_298;
              }
            }
          }
          else if ( (v151 & 0xC8) == 8 )
          {
            v15 = "D3D12_RESOURCE_DESC::Flags cannot have D3D12_RESOURCE_FLAG_DENY_SHADER_RESOURCE set without D3D12_RESO"
                  "URCE_FLAG_ALLOW_DEPTH_STENCIL, D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY or D3D12_RESOURCE_FLAG_"
                  "VIDEO_ENCODE_REFERENCE_ONLY.";
            goto LABEL_22;
          }
          if ( (v151 & 0x40) != 0 )
          {
            *(_QWORD *)&v221.WidthInTexels = 0;
            if ( (***((int (__fastcall ****)(_QWORD, GUID *, struct D3D12_TILE_SHAPE *))a2 + 83))(
                   *((_QWORD *)a2 + 83),
                   &GUID_1f052807_0b46_4acc_8a89_364f793718a4,
                   &v221) < 0 )
            {
              TDebugOutputFunctor::operator()(
                a1,
                599,
                "D3D12_RESOURCE_DESC::Flags cannot have D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY set if the device"
                " does not support video.");
LABEL_325:
              ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v221);
              return v13;
            }
            ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v221);
            if ( (v235 & 0x8000000) == 0 )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v156);
              v15 = "D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY set, but the D3D12_RE"
                    "SOURCE_DESC::Format specified does not support D3D12_FORMAT_SUPPORT1_DECODER_OUTPUT Format = %s.";
              goto LABEL_205;
            }
            v157 = *((_DWORD *)a3 + 12);
            if ( (v157 & 0xFFFFFFB7) != 0 )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only combine D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY with the"
                    "se flags: 0x%x.  Unsupported flags specified: 0x%x.";
              goto LABEL_119;
            }
            LOBYTE(v49) = 72;
            if ( (v157 & 0x48) != 0x48 )
            {
              v15 = "When D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY set, you must al"
                    "so set the following flags: 0x%x. Missing flags: 0x%x.";
              goto LABEL_119;
            }
            if ( *(_DWORD *)a3 != 3 )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY for D3D12_R"
                    "ESOURCE_DIMENSION_TEXTURE2D.";
              goto LABEL_22;
            }
            if ( *((_DWORD *)a3 + 11) )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY for D3D12_R"
                    "ESOURCE_DESC::Layout == D3D12_TEXTURE_LAYOUT_UNKNOWN.";
              goto LABEL_22;
            }
            if ( *((_WORD *)a3 + 15) != 1 )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY for D3D12_R"
                    "ESOURCE_DESC::MipLevels == 1.";
              goto LABEL_22;
            }
            v158 = (float *)v231;
            if ( v231 )
            {
              v15 = "It is invalid to specify pOptimizedClearValue when D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLA"
                    "G_VIDEO_DECODE_REFERENCE_ONLY.";
              goto LABEL_22;
            }
          }
          else
          {
            v158 = (float *)v231;
          }
          if ( *((char *)a3 + 48) < 0 )
          {
            *(_QWORD *)&v221.WidthInTexels = 0;
            if ( (***((int (__fastcall ****)(_QWORD, GUID *, struct D3D12_TILE_SHAPE *))a2 + 83))(
                   *((_QWORD *)a2 + 83),
                   &GUID_1f052807_0b46_4acc_8a89_364f793718a4,
                   &v221) < 0 )
            {
              TDebugOutputFunctor::operator()(
                a1,
                599,
                "D3D12_RESOURCE_DESC::Flags cannot have D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set if the device"
                " does not support video.");
              goto LABEL_325;
            }
            ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v221);
            v159 = *((_DWORD *)a3 + 12);
            if ( (v159 & 0xFFFFFF77) != 0 )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only combine D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY with the"
                    "se flags: 0x%x.  Unsupported flags specified: 0x%x.";
              goto LABEL_119;
            }
            if ( (v159 & 0x88) != 0x88 )
            {
              v15 = "When D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set, you must al"
                    "so set the following flags: 0x%x. Missing flags: 0x%x.";
              goto LABEL_119;
            }
            if ( *(_DWORD *)a3 != 3 )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY for D3D12_R"
                    "ESOURCE_DIMENSION_TEXTURE2D.";
              goto LABEL_22;
            }
            if ( *((_DWORD *)a3 + 11) )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY for D3D12_R"
                    "ESOURCE_DESC::Layout == D3D12_TEXTURE_LAYOUT_UNKNOWN.";
              goto LABEL_22;
            }
            if ( *((_WORD *)a3 + 15) != 1 )
            {
              v15 = "D3D12_RESOURCE_DESC::Flags can only have D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY for D3D12_R"
                    "ESOURCE_DESC::MipLevels == 1.";
              goto LABEL_22;
            }
            if ( v158 )
            {
              v15 = "It is invalid to specify pOptimizedClearValue when D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLA"
                    "G_VIDEO_ENCODE_REFERENCE_ONLY.";
              goto LABEL_22;
            }
            goto LABEL_383;
          }
          if ( v158 )
          {
            if ( (*((_BYTE *)a3 + 48) & 3) == 0 )
            {
              v15 = "pOptimizedClearValue must be NULL when D3D12_RESOURCE_DESC::Dimension is not D3D12_RESOURCE_DIMENSIO"
                    "N_BUFFER and neither D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET nor D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STE"
                    "NCIL are set in D3D12_RESOURCE_DESC::Flags.";
              goto LABEL_359;
            }
            if ( !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExistsInHeader(*(enum DXGI_FORMAT *)v158, v49) )
            {
              TDebugOutputFunctor::operator()(
                a1,
                816,
                "D3D12_CLEAR_VALUE::Format is unrecognized. The value is %u.",
                *(_DWORD *)v158);
              v222 = -2147024809;
            }
            if ( !(unsigned __int8)CD3D11FormatHelper::APIFormatExists(
                                     *(unsigned int *)v158,
                                     *((unsigned int *)a2 + 164),
                                     *((unsigned int *)a2 + 165)) )
            {
              FeatureLevelToString(v162);
              Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v164, v163);
              v211 = v165;
              v40 = "D3D12_CLEAR_VALUE::Format is not supported at the current feature level. Format = %s and FeatureLevel is %s.";
LABEL_364:
              v41 = 817;
              goto LABEL_83;
            }
            v166 = 0xFFFFFFFFLL;
            if ( (unsigned int)v161 < 0xC0 )
              v166 = (unsigned int)v161;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v166 + 6) & 0xC00) == 0x800 )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(
                (enum DXGI_FORMAT)v161,
                (bool)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail);
              TDebugOutputFunctor::operator()(
                a1,
                817,
                "D3D12_CLEAR_VALUE::Format cannot be a typeless format. A fully qualified format must be supplied. Format = %s.");
              return v13;
            }
            if ( *(_DWORD **)v236 == v230 )
            {
              v167 = *((_DWORD *)a3 + 8);
              if ( v167 != (_DWORD)v161 )
              {
                D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(
                  v167,
                  (bool)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail);
                Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v169, v168);
                v211 = v170;
                v40 = "D3D12_CLEAR_VALUE::Format must be equal to D3D12_RESOURCE_DESC::Format, when the resource format i"
                      "s not a typeless format. D3D12_CLEAR_VALUE::Format = %s, D3D12_RESOURCE_DESC::Format = %s.";
                goto LABEL_364;
              }
            }
            else if ( LODWORD(v225) != *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v161 + 1) )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(
                *((enum DXGI_FORMAT *)a3 + 8),
                (bool)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail);
              Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v172, v171);
              v211 = v173;
              v40 = "D3D12_CLEAR_VALUE::Format must belong to the same format cast group as D3D12_RESOURCE_DESC::Format. "
                    "D3D12_CLEAR_VALUE::Format = %s, D3D12_RESOURCE_DESC::Format = %s.";
              goto LABEL_364;
            }
            v221.WidthInTexels = v161;
            v221.HeightInTexels = 0;
            if ( (*((_BYTE *)a3 + 48) & 1) != 0
              && (int)ValidateRenderTargetViewFormats(&v221, *((_QWORD *)a2 + 83), (unsigned int)v162, v160, -1) < 0 )
            {
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v174);
              Name = FeatureLevelToString((enum D3D_FEATURE_LEVEL)*((_DWORD *)a2 + 164));
              v211 = v175;
              v40 = "When D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET is set in D3D12_RESOURCE_DESC::Flags, D3D12_CLEAR_VALUE"
                    "::Format must be valid to be used as a render target. FeatureLevel is %s. D3D12_CLEAR_VALUE::Format is %s.";
              goto LABEL_364;
            }
            if ( (*((_BYTE *)a3 + 48) & 2) != 0 )
            {
              v176 = *((_DWORD *)a2 + 164);
              if ( (int)ValidateDepthStencilViewFormats(&v221, (unsigned int)v176, *((unsigned int *)a2 + 165), -1) < 0 )
              {
                D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v177);
                Name = FeatureLevelToString(v176);
                v211 = v178;
                v40 = "When D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL is set in D3D12_RESOURCE_DESC::Flags, D3D12_CLEAR_VAL"
                      "UE::Format must be valid to be used as a depth stencil. FeatureLevel is %s. D3D12_CLEAR_VALUE::Format is %s.";
                goto LABEL_364;
              }
              v225 = v158[1];
              if ( v225 < 0.0 || v225 > 1.0 )
              {
                TDebugOutputFunctor::operator()(
                  a1,
                  815,
                  "D3D12_CLEAR_VALUE::DepthStencil::Depth is outside the valid range of 0.0f to 1.0f. Depth = %f.",
                  v225);
                return v13;
              }
            }
          }
LABEL_383:
          if ( !ValidateSamplerFeedbackAndOutputDebugMessages(a1, a3) )
            return v13;
          goto LABEL_384;
        }
        v15 = "D3D12_RESOURCE_DESC::SampleDesc is invalid.  Count is %u, quality is %u.  When D3D12_RESOURCE_DESC::Layout"
              " is D3D12_TEXTURE_LAYOUT_ROW_MAJOR, the sample count must be 1, and the sample quality must be 0.";
LABEL_178:
        v16 = 723;
        goto LABEL_27;
      }
      v212 = (enum DXGI_FORMAT *)D3D12ToStr((const enum D3D12_TEXTURE_LAYOUT *)a3 + 11);
      TDebugOutputFunctor::operator()(
        a1,
        721,
        "D3D12_RESOURCE_DESC::Alignment is invalid. The value is %I64u. When D3D12_RESOURCE_DESC::Layout is %s, the Align"
        "ment field must be either %I64u (aka. %s) or 0.",
        v113,
        v212,
        0x10000,
        "D3D12_DEFAULT_RESOURCE_PLACEMENT_ALIGNMENT");
      return v13;
    }
    v88 = *((_QWORD *)a3 + 1);
    if ( !v88 )
      goto LABEL_169;
    if ( *((_DWORD *)a3 + 9) <= 1u )
    {
      if ( v88 == 0x10000 )
        goto LABEL_169;
      if ( (*((_BYTE *)a3 + 48) & 0xC3) != 0 )
      {
        v89 = "D3D12_RESOURCE_DESC::Alignment is invalid. The value is %I64u. Resources with D3D12_RESOURCE_DESC::Flags w"
              "ith either D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET or D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL must set Ali"
              "gnment equal to %I64u (aka. %s), or 0.";
        goto LABEL_140;
      }
      if ( v88 != 4096 )
      {
        v116 = "D3D12_RESOURCE_DESC::Alignment is invalid. The value is %I64u. Non-MSAA resources must have this field se"
               "t to %I64u (aka. %s), %u (aka. %s), or 0.";
        goto LABEL_212;
      }
      v120 = *((_DWORD *)a3 + 8);
      v121 = 0xFFFFFFFFLL;
      if ( (unsigned int)v120 < 0xC0 )
        v121 = (unsigned int)v120;
      if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v121 + 32) & 8) != 0 )
      {
        TDebugOutputFunctor::operator()(a1, 721, "D3D12_RESOURCE_DESC::Alignment cannot be 4096 for planar formats.");
        return v13;
      }
      *(_QWORD *)&v221.WidthInTexels = 0;
      v221.DepthInTexels = 0;
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::Get4KTileShape(
        &v221,
        v120,
        *(enum D3D12_RESOURCE_DIMENSION *)a3,
        *((_DWORD *)a3 + 9));
      if ( *(_DWORD *)a3 == 4 )
        v122 = *((_WORD *)a3 + 14);
      else
        v122 = 1;
      LODWORD(v49) = (*((_DWORD *)a3 + 6) + v221.HeightInTexels - 1) % v221.HeightInTexels;
      if ( (*((_DWORD *)a3 + 6) + v221.HeightInTexels - 1)
         / v221.HeightInTexels
         * (v221.DepthInTexels + v122 - 1)
         / v221.DepthInTexels
         * (unsigned __int64)((v221.WidthInTexels + *((_DWORD *)a3 + 4) - 1) / v221.WidthInTexels) > 0x10 )
      {
        D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v120, v123);
        v119 = "D3D12_RESOURCE_DESC::Alignment cannot be 4KB, since D3D12_RESOURCE_DESC::Width, D3D12_RESOURCE_DESC::Heig"
               "ht, and/ or D3D12_RESOURCE_DESC::DepthOrArraySize are too large. 4KB alignment requires the most detailed"
               " mip level be theoretically 64KB or smaller. A 4KB tile shape for %s and %s is %u texels wide, %u texels "
               "high, and %u texels deep. When Width = %I64u, Height = %u, and Depth = %u, the number of tiles needed is "
               "%I64u, while 16 tiles is the maximum. D3D12_RESOURCE_DESC::Alignment must be 0 or 4MB (aka D3D12_DEFAULT_"
               "MSAA_RESOURCE_PLACEMENT_ALIGNMENT).";
        goto LABEL_219;
      }
    }
    else
    {
      LOBYTE(v49) = 0;
      if ( v88 == 0x400000 )
        goto LABEL_169;
      if ( v88 != 0x10000 )
      {
        v116 = "D3D12_RESOURCE_DESC::Alignment is invalid. The value is %I64u. MSAA resources must have this field set to"
               " %I64u (aka. %s), %I64u (aka. %s), or 0.";
LABEL_212:
        TDebugOutputFunctor::operator()(a1, 721, v116);
        return v13;
      }
      if ( *((_DWORD *)a2 + 197) != (_DWORD)v53 )
        goto LABEL_169;
      *(_QWORD *)&v221.WidthInTexels = 0;
      v221.DepthInTexels = 0;
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetTileShape(
        &v221,
        *((enum DXGI_FORMAT *)a3 + 8),
        *(enum D3D12_RESOURCE_DIMENSION *)a3,
        *((_DWORD *)a3 + 9));
      if ( *(_DWORD *)a3 == 4 )
        v117 = *((_WORD *)a3 + 14);
      else
        v117 = 1;
      LODWORD(v49) = (*((_DWORD *)a3 + 6) + v221.HeightInTexels - 1) % v221.HeightInTexels;
      if ( (*((_DWORD *)a3 + 6) + v221.HeightInTexels - 1)
         / v221.HeightInTexels
         * (v221.DepthInTexels + v117 - 1)
         / v221.DepthInTexels
         * (unsigned __int64)((v221.WidthInTexels + *((_DWORD *)a3 + 4) - 1) / v221.WidthInTexels) > 0x40 )
      {
        D3D12ToStr((const enum D3D12_RESOURCE_DIMENSION *)a3);
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(*((enum DXGI_FORMAT *)a3 + 8), v118);
        v119 = "D3D12_RESOURCE_DESC::Alignment cannot be 64KB, since D3D12_RESOURCE_DESC::Width, D3D12_RESOURCE_DESC::Hei"
               "ght, and/ or D3D12_RESOURCE_DESC::DepthOrArraySize are too large. 64KB alignment requires the most detail"
               "ed mip level be theoretically 4MB or smaller. A 64KB tile shape for %s and %s is %u texels wide, %u texel"
               "s high, and %u texels deep. When Width = %I64u, Height = %u, and Depth = %u, the number of tiles needed i"
               "s %I64u, while 16 tiles is the maximum. D3D12_RESOURCE_DESC::Alignment must be 0 or 4MB (aka D3D12_DEFAUL"
               "T_MSAA_RESOURCE_PLACEMENT_ALIGNMENT).";
LABEL_219:
        TDebugOutputFunctor::operator()(a1, 1380, v119);
        return v13;
      }
    }
LABEL_168:
    v53 = 0;
    goto LABEL_169;
  }
  return result;
}

```

## disassembly

```asm
0x1800fe198  push    rbp
0x1800fe19a  push    rbx
0x1800fe19b  push    rsi
0x1800fe19c  push    rdi
0x1800fe19d  push    r12
0x1800fe19f  push    r13
0x1800fe1a1  push    r14
0x1800fe1a3  push    r15
0x1800fe1a5  lea     rbp, [rsp-288h]
0x1800fe1ad  sub     rsp, 388h
0x1800fe1b4  mov     rax, cs:__security_cookie
0x1800fe1bb  xor     rax, rsp
0x1800fe1be  mov     [rbp+2C0h+var_50], rax
0x1800fe1c5  mov     [rbp+2C0h+var_2F8], r9
0x1800fe1c9  mov     rdi, r8
0x1800fe1cc  mov     rbx, rdx
0x1800fe1cf  mov     r14, rcx
0x1800fe1d2  mov     rax, [rbp+2C0h+arg_28]
0x1800fe1d9  mov     [rbp+2C0h+var_310], rax
0x1800fe1dd  mov     rcx, [rbp+2C0h+arg_38]
0x1800fe1e4  mov     [rbp+2C0h+var_2E8], rcx
0x1800fe1e8  xor     r15d, r15d
0x1800fe1eb  mov     r12d, r15d
0x1800fe1ee  mov     [rbp+2C0h+var_328], r15d
0x1800fe1f2  mov     esi, 80070057h
0x1800fe1f7  cmp     dword ptr [r8], 5
0x1800fe1fb  jl      short loc_1800FE21A
0x1800fe1fd  mov     r9d, [r8]
0x1800fe200  lea     r8, aD3d12ResourceD_51; "D3D12_RESOURCE_DESC::Dimension is unrec"...
0x1800fe207  mov     edx, 2CEh
0x1800fe20c  mov     rcx, r14
0x1800fe20f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe214  mov     r12d, esi
0x1800fe217  mov     [rbp+2C0h+var_328], esi
0x1800fe21a  mov     r9d, [rdi+20h]
0x1800fe21e  mov     ecx, r9d; enum DXGI_FORMAT
0x1800fe221  call    ?FormatExistsInHeader@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExistsInHeader(DXGI_FORMAT,bool)
0x1800fe226  test    al, al
0x1800fe228  jnz     short loc_1800FE244
0x1800fe22a  lea     r8, aD3d12ResourceD_45; "D3D12_RESOURCE_DESC::Format is unrecogn"...
0x1800fe231  mov     edx, 2E1h
0x1800fe236  mov     rcx, r14
0x1800fe239  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe23e  mov     r12d, esi
0x1800fe241  mov     [rbp+2C0h+var_328], esi
0x1800fe244  mov     r13d, 2CFh
0x1800fe24a  cmp     dword ptr [rdi+2Ch], 5
0x1800fe24e  jl      short loc_1800FE26B
0x1800fe250  mov     r9d, [rdi]
0x1800fe253  lea     r8, aD3d12ResourceD_78; "D3D12_RESOURCE_DESC::Layout is unrecogn"...
0x1800fe25a  mov     edx, r13d
0x1800fe25d  mov     rcx, r14
0x1800fe260  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe265  mov     r12d, esi
0x1800fe268  mov     [rbp+2C0h+var_328], esi
0x1800fe26b  mov     r9d, [rdi+30h]
0x1800fe26f  mov     eax, r9d
0x1800fe272  and     eax, 0FFFFF000h
0x1800fe277  jz      short loc_1800FE294
0x1800fe279  lea     r8, aD3d12ResourceD_52; "D3D12_RESOURCE_DESC::Flags has unrecogn"...
0x1800fe280  mov     edx, r13d
0x1800fe283  mov     dword ptr [rsp+3C0h+var_3A0], eax
0x1800fe287  mov     rcx, r14
0x1800fe28a  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe28f  jmp     loc_18010001A
0x1800fe294  test    r12d, r12d
0x1800fe297  jns     short loc_1800FE2A1
0x1800fe299  mov     esi, r12d
0x1800fe29c  jmp     loc_18010001A
0x1800fe2a1  lea     r13, [rdi+10h]
0x1800fe2a5  mov     r9, [r13+0]
0x1800fe2a9  test    r9, r9
0x1800fe2ac  jz      loc_1800FFFF7
0x1800fe2b2  cmp     [rdi+18h], r15d
0x1800fe2b6  jz      loc_1800FFFF7
0x1800fe2bc  cmp     [rdi+1Ch], r15w
0x1800fe2c1  jz      loc_1800FFFF7
0x1800fe2c7  mov     eax, [rbx+290h]
0x1800fe2cd  mov     ecx, 1000h
0x1800fe2d2  mov     r15d, 1
0x1800fe2d8  mov     qword ptr [rbp+2C0h+var_338.WidthInTexels], rcx
0x1800fe2dc  cmp     eax, ecx
0x1800fe2de  jz      short loc_1800FE2E7
0x1800fe2e0  cmp     eax, 100h
0x1800fe2e5  jnz     short loc_1800FE30C
0x1800fe2e7  mov     eax, [rdi]
0x1800fe2e9  sub     eax, r15d
0x1800fe2ec  test    eax, 0FFFFFFFDh
0x1800fe2f1  jz      short loc_1800FE30C
0x1800fe2f3  lea     r8, aTheOnlyResourc; "The only resource dimension supported b"...
0x1800fe2fa  mov     edx, 255h
0x1800fe2ff  mov     rcx, r14
0x1800fe302  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe307  jmp     loc_18010001A
0x1800fe30c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment> `wil::Feature<__WilFeatureTraits_Feature_D3D12TightAlignment>::GetImpl(void)'::`2'::impl
0x1800fe313  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment>::__private_IsEnabled(void)
0x1800fe318  xor     r8d, r8d
0x1800fe31b  test    al, al
0x1800fe31d  jz      short loc_1800FE38B
0x1800fe31f  test    dword ptr [rdi+30h], 400h
0x1800fe326  jz      short loc_1800FE38B
0x1800fe328  cmp     [rbx+40Ch], r8d
0x1800fe32f  jnz     short loc_1800FE33F
0x1800fe331  lea     r8, aD3d12ResourceD_26; "D3D12_RESOURCE_DESC::Flag D3D12_RESOURC"...
0x1800fe338  mov     edx, 257h
0x1800fe33d  jmp     short loc_1800FE2FF
0x1800fe33f  cmp     dword ptr [rdi+2Ch], 3
0x1800fe343  jz      short loc_1800FE376
0x1800fe345  cmp     dword ptr [rdi+2Ch], 2
0x1800fe349  jz      short loc_1800FE36D
0x1800fe34b  mov     r9, [rdi+8]
0x1800fe34f  test    r9, r9
0x1800fe352  jz      short loc_1800FE38B
0x1800fe354  lea     r8, aD3d12ResourceD_48; "D3D12_RESOURCE_DESC::Alignment is inval"...
0x1800fe35b  mov     edx, 2D1h
0x1800fe360  mov     rcx, r14
0x1800fe363  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe368  jmp     loc_18010001A
0x1800fe36d  lea     r9, aD3d12TextureLa_3; "D3D12_TEXTURE_LAYOUT_64KB_UNDEFINED_SWI"...
0x1800fe374  jmp     short loc_1800FE37D
0x1800fe376  lea     r9, aD3d12TextureLa_2; "D3D12_TEXTURE_LAYOUT_64KB_STANDARD_SWIZ"...
0x1800fe37d  lea     r8, aD3d12ResourceD_67; "D3D12_RESOURCE_DESC::Flag D3D12_RESOURC"...
0x1800fe384  mov     edx, 257h
0x1800fe389  jmp     short loc_1800FE360
0x1800fe38b  cmp     dword ptr [rdi+2Ch], 4
0x1800fe38f  jnz     short loc_1800FE3B4
0x1800fe391  mov     r9b, [rbp+2C0h+arg_40]; bool
0x1800fe398  mov     r8, rdi; struct D3D12_RESOURCE_DESC2 *
0x1800fe39b  mov     rdx, rbx; struct DeviceValidationInfo *
0x1800fe39e  mov     rcx, r14; struct TDebugOutputFunctor *
0x1800fe3a1  call    ?ValidateTextureLayoutGuid@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUD3D12_RESOURCE_DESC2@@_N@Z; ValidateTextureLayoutGuid(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_RESOURCE_DESC2 const &,bool)
0x1800fe3a6  mov     [rbp+2C0h+var_328], eax
0x1800fe3a9  xor     r8d, r8d
0x1800fe3ac  test    eax, eax
0x1800fe3ae  js      loc_18010001C
0x1800fe3b4  test    dword ptr [rdi+30h], 200h
0x1800fe3bb  jz      short loc_1800FE3E4
0x1800fe3bd  cmp     dword ptr [rdi], 4
0x1800fe3c0  jz      short loc_1800FE3CE
0x1800fe3c2  lea     r8, aD3d12ResourceD_3; "D3D12_RESOURCE_DESC::Flags can only hav"...
0x1800fe3c9  jmp     loc_1800FE338
0x1800fe3ce  mov     rdx, r14; struct TDebugOutputFunctor *
0x1800fe3d1  mov     rcx, rdi; struct CD3DX12_RESOURCE_DESC2 *
0x1800fe3d4  call    ?IsValid3DLUTTextureSize@@YA_NAEBUCD3DX12_RESOURCE_DESC2@@AEAUTDebugOutputFunctor@@@Z; IsValid3DLUTTextureSize(CD3DX12_RESOURCE_DESC2 const &,TDebugOutputFunctor &)
0x1800fe3d9  xor     r8d, r8d
0x1800fe3dc  test    al, al
0x1800fe3de  jz      loc_18010001A
0x1800fe3e4  test    dword ptr [rdi+30h], 800h
0x1800fe3eb  jz      short loc_1800FE3FE
0x1800fe3ed  cmp     dword ptr [rdi], 2
0x1800fe3f0  jz      short loc_1800FE3FE
0x1800fe3f2  lea     r8, aD3d12ResourceD_54; "D3D12_RESOURCE_DESC::Flags can only hav"...
0x1800fe3f9  jmp     loc_1800FE338
0x1800fe3fe  mov     ecx, [rdi]
0x1800fe400  or      r12d, 0FFFFFFFFh
0x1800fe404  sub     ecx, r15d
0x1800fe407  jz      loc_1800FFCD8
0x1800fe40d  sub     ecx, r15d
0x1800fe410  jz      short loc_1800FE438
0x1800fe412  sub     ecx, r15d
0x1800fe415  jz      short loc_1800FE438
0x1800fe417  cmp     ecx, r15d
0x1800fe41a  jz      short loc_1800FE438
0x1800fe41c  mov     rcx, rdi; enum D3D12_RESOURCE_DIMENSION *
0x1800fe41f  call    ?D3D12ToStr@@YAPEBDAEBW4D3D12_RESOURCE_DIMENSION@@@Z; D3D12ToStr(D3D12_RESOURCE_DIMENSION const &)
0x1800fe424  lea     r8, aD3d12ResourceD_41; "D3D12_RESOURCE_DESC::Dimension is inval"...
0x1800fe42b  mov     r9, rax
0x1800fe42e  mov     edx, 2D0h
0x1800fe433  jmp     loc_1800FE360
0x1800fe438  mov     [rbp+2C0h+var_33F], r8b
0x1800fe43c  mov     r12b, r15b
0x1800fe43f  mov     [rbp+2C0h+var_340], r15b
0x1800fe443  mov     eax, [rdi+20h]
0x1800fe446  mov     [rbp+2C0h+var_2E0], eax
0x1800fe449  mov     [rbp+2C0h+var_2DC], 0
0x1800fe451  mov     rcx, [rbx+298h]
0x1800fe458  mov     rax, [rcx]
0x1800fe45b  mov     r9d, 0Ch
0x1800fe461  lea     r8, [rbp+2C0h+var_2E0]
0x1800fe465  lea     edx, [r9-9]
0x1800fe469  mov     rax, [rax+68h]
0x1800fe46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe472  mov     [rbp+2C0h+var_328], eax
0x1800fe475  mov     edx, 800h
0x1800fe47a  cmp     dword ptr [rbx+290h], 0B000h
0x1800fe484  jl      short loc_1800FE491
0x1800fe486  mov     r9d, 4000h
0x1800fe48c  mov     r11d, edx
0x1800fe48f  jmp     short loc_1800FE49D
0x1800fe491  mov     r9d, 2000h
0x1800fe497  mov     r11d, 200h
0x1800fe49d  mov     ecx, [rdi]
0x1800fe49f  sub     ecx, 2
0x1800fe4a2  jz      short loc_1800FE4F9
0x1800fe4a4  cmp     ecx, r15d
0x1800fe4a7  jz      short loc_1800FE4BB
0x1800fe4a9  mov     r9d, edx
0x1800fe4ac  mov     r10d, edx
0x1800fe4af  mov     r11d, edx
0x1800fe4b2  mov     [rbp+2C0h+var_324], 40h ; '@'
0x1800fe4b9  jmp     short loc_1800FE503
0x1800fe4bb  test    [rbx+2B0h], r15b
0x1800fe4c2  jz      short loc_1800FE4E1
0x1800fe4c4  mov     eax, r9d
0x1800fe4c7  cmp     [r13+0], rax
0x1800fe4cb  ja      short loc_1800FE4D3
0x1800fe4cd  cmp     [rdi+18h], r9d
0x1800fe4d1  jbe     short loc_1800FE4E1
0x1800fe4d3  mov     r9d, 800000h
0x1800fe4d9  mov     r11d, r15d
0x1800fe4dc  mov     al, [rbp+2C0h+var_33F]
0x1800fe4df  jmp     short loc_1800FE4E7
0x1800fe4e1  mov     al, r15b
0x1800fe4e4  mov     [rbp+2C0h+var_33F], al
0x1800fe4e7  mov     [rbp+2C0h+var_324], 20h ; ' '
0x1800fe4ee  mov     r12b, al
0x1800fe4f1  mov     [rbp+2C0h+var_340], al
0x1800fe4f4  mov     r10d, r9d
0x1800fe4f7  jmp     short loc_1800FE503
0x1800fe4f9  mov     r10d, r15d
0x1800fe4fc  mov     [rbp+2C0h+var_324], 10h
0x1800fe503  mov     eax, r9d
0x1800fe506  cmp     [r13+0], rax
0x1800fe50a  ja      loc_1800FFC7D
0x1800fe510  cmp     [rdi+18h], r10d
0x1800fe514  ja      loc_1800FFC7D
0x1800fe51a  movzx   eax, word ptr [rdi+1Ch]
0x1800fe51e  cmp     eax, r11d
0x1800fe521  ja      loc_1800FFC7D
0x1800fe527  cmp     dword ptr [rdi], 4
0x1800fe52a  jz      short loc_1800FE530
0x1800fe52c  movzx   eax, r15w
0x1800fe530  movzx   r10d, ax
0x1800fe534  mov     [rbp+2C0h+var_308], r10
0x1800fe538  mov     r8d, [rdi+18h]
0x1800fe53c  mov     [rbp+2C0h+var_2F0], r8
0x1800fe540  cmp     [r13+0], r8
0x1800fe544  jnb     short loc_1800FE54F
0x1800fe546  lea     rcx, [rbp+2C0h+var_2F0]
0x1800fe54a  mov     eax, r8d
0x1800fe54d  jmp     short loc_1800FE556
0x1800fe54f  mov     rcx, r13
0x1800fe552  mov     rax, [r13+0]
0x1800fe556  cmp     rax, r10
0x1800fe559  jb      short loc_1800FE562
0x1800fe55b  mov     r10, [rcx]
0x1800fe55e  mov     [rbp+2C0h+var_308], r10
0x1800fe562  xor     r11d, r11d
0x1800fe565  test    r12b, r12b
0x1800fe568  jz      short loc_1800FE577
0x1800fe56a  mov     rcx, r10; unsigned __int64
0x1800fe56d  call    ?MaxMipLevels@@YAG_K@Z; MaxMipLevels(unsigned __int64)
0x1800fe572  movzx   edx, ax
0x1800fe575  jmp     short loc_1800FE57A
0x1800fe577  mov     edx, r15d
0x1800fe57a  movzx   r12d, word ptr [rdi+1Eh]
0x1800fe57f  mov     r13d, 2D2h
0x1800fe585  test    r12w, r12w
0x1800fe589  jnz     short loc_1800FE591
0x1800fe58b  movzx   r12d, dx
0x1800fe58f  jmp     short loc_1800FE5ED
0x1800fe591  cmp     r12w, dx
0x1800fe595  jbe     short loc_1800FE5ED
0x1800fe597  cmp     r10, [rdi+10h]
0x1800fe59b  jnz     short loc_1800FE5A6
0x1800fe59d  lea     rax, aWidth; "Width"
0x1800fe5a4  jmp     short loc_1800FE5BB
0x1800fe5a6  lea     rax, aHeight_0; "Height"
0x1800fe5ad  lea     r9, aDepthorarraysi; "DepthOrArraySize"
0x1800fe5b4  cmp     r10, r8
0x1800fe5b7  cmovnz  rax, r9
0x1800fe5bb  movzx   r9d, dx
0x1800fe5bf  mov     dword ptr [rsp+3C0h+var_390], r12d
0x1800fe5c4  mov     qword ptr [rsp+3C0h+var_398], r10
0x1800fe5c9  mov     [rsp+3C0h+var_3A0], rax
0x1800fe5ce  lea     r8, aD3d12ResourceD_31; "D3D12_RESOURCE_DESC::MipLevels must be "...
0x1800fe5d5  mov     edx, r13d
0x1800fe5d8  mov     rcx, r14
0x1800fe5db  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800fe5e0  xor     r11d, r11d
0x1800fe5e3  cmp     [rbp+2C0h+var_340], r11b
0x1800fe5e7  jz      loc_18010001A
0x1800fe5ed  mov     r9d, [rdi+20h]
0x1800fe5f1  mov     ecx, r9d
0x1800fe5f4  sub     ecx, 0BDh
0x1800fe5fa  jz      short loc_1800FE601
0x1800fe5fc  cmp     ecx, r15d
0x1800fe5ff  jnz     short loc_1800FE61B
0x1800fe601  cmp     [rbx+344h], r11d
0x1800fe608  jnz     short loc_1800FE61B
0x1800fe60a  lea     r8, aASamplerFeedba; "A sampler feedback DXGI_FORMAT was spec"...
0x1800fe611  mov     edx, 4E7h
0x1800fe616  jmp     loc_1800FE2FF
0x1800fe61b  mov     eax, [rbp+2C0h+var_328]
0x1800fe61e  shr     eax, 1Fh
0x1800fe621  xor     al, r15b
0x1800fe624  jnz     short loc_1800FE65D
0x1800fe626  mov     ecx, [rbx+290h]; enum D3D_FEATURE_LEVEL
0x1800fe62c  call    ?FeatureLevelToString@@YAPEBDW4D3D_FEATURE_LEVEL@@@Z; FeatureLevelToString(D3D_FEATURE_LEVEL)
0x1800fe631  mov     r8, rax
  ... truncated ...
```
