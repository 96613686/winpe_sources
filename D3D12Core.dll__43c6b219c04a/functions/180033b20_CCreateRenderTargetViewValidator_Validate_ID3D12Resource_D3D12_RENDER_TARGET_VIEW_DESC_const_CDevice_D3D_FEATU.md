# CCreateRenderTargetViewValidator::Validate(ID3D12Resource *,D3D12_RENDER_TARGET_VIEW_DESC const *,CDevice *,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures,bool *)

- ea: `0x180033b20`
- end: `0x180034fa4`
- name: `?Validate@CCreateRenderTargetViewValidator@@QEAAJPEAUID3D12Resource@@PEBUD3D12_RENDER_TARGET_VIEW_DESC@@PEAVCDevice@@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@CD3D11FormatHelper@@PEA_N@Z`
- size: `5252`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x18007f308`

## callees

- `0x180025f90`
- `0x180026410`
- `0x1800264c0`
- `0x1800268f0`
- `0x1800269d0`
- `0x18002ef50`
- `0x180031e4c`
- `0x180031ec0`
- `0x180033a70`
- `0x180033b20`
- `0x180034fb0`
- `0x18003f5d0`
- `0x180048934`
- `0x180074dd4`
- `0x180078b10`
- `0x18007b6e8`
- `0x18009fd4c`
- `0x1800aa248`
- `0x1800abc10`
- `0x1800bb480`
- `0x180262020`

## string_xrefs

- `0x180034c84`: `A View of a Buffer cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a Format must be supplied.`
- `0x180033e14`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x180034238`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x180034935`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x180033d16`: `The ViewDimension in the View Desc is incompatible with the type of the Resource.`
- `0x180034f64`: `A RenderTargetView cannot be created from a NULL Resource and NULL Desc.`
- `0x1800342ca`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x1800347cb`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180034bb4`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180034153`: `Views of video formats cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a View format must be supplied, not the same as the underlying video format.The View format is needed to indicate how the video surface (or part of it) will appear to shaders - see documentation.`
- `0x1800347a0`: `The video format %s does not support RenderTargetViews. For this format, specifying D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET when the surface created actually only allows the surface to be used for video processor decode output.  For some other video formats (depending on device Feature Level as well), D3D12_RESOURCE_FLAG_ALLOW_RENDER_TARGET does allow both video processor decode output and RenderTargetView output, but not in this case.`
- `0x180033d8d`: `A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default Desc parameters cannot be used, as a fully qualified Format must be supplied.`
- `0x180034124`: `A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default Desc parameters cannot be used, as a fully qualified Format must be supplied.`
- `0x180033f68`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x180034546`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x180034aaf`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x180033f14`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x1800344ce`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x180034a5b`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x180034f18`: `A RenderTargetView cannot be created of a Resource that did not specify the RENDER_TARGET MiscFlag.`
- `0x180034576`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s), unless the resource is a DXGI swap chain back buffer.`
- `0x18003488f`: `The base resource was created as a multisample resource.  You must specify D3D12_RTV_DIMENSION_TEXTURE2DMS instead of D3D12_RTV_DIMENSION_TEXTURE2D.`
- `0x1800348a1`: `The base resource was created as a multisample resource.  You must specify D3D12_RTV_DIMENSION_TEXTURE2DMSARRAYinstead of D3D12_RTV_DIMENSION_TEXTURE2DARRAY.`

## pseudocode

```c
__int64 __fastcall CCreateRenderTargetViewValidator::Validate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int *a4,
        enum D3D_FEATURE_LEVEL a5,
        unsigned int a6,
        __int64 a7)
{
  int v7; // edi
  __int64 v9; // r8
  __int64 v10; // r10
  __int64 v11; // r15
  int v12; // r9d
  __int64 v13; // rax
  enum DXGI_FORMAT v14; // ebx
  unsigned int v15; // r8d
  unsigned __int16 v16; // r9
  int v17; // r14d
  enum DXGI_FORMAT v18; // esi
  _DWORD *v19; // rdx
  bool v20; // zf
  char v21; // r12
  int v22; // r14d
  int v23; // r14d
  __int64 v24; // rax
  _DWORD *v25; // rcx
  _DWORD *v26; // rdx
  bool v27; // dl
  const char *Name; // rax
  const char *v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  bool v33; // dl
  bool v34; // dl
  const char *v35; // rax
  const char *v36; // r8
  bool v37; // dl
  const char *v38; // rax
  __int64 v39; // r8
  const char *v40; // r8
  bool v41; // dl
  __int64 v42; // r8
  bool v43; // dl
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rax
  bool v47; // dl
  __int64 v48; // r8
  enum D3D_FEATURE_LEVEL v49; // r14d
  bool v50; // dl
  const char *v51; // rax
  unsigned int v52; // edx
  unsigned int v53; // ecx
  unsigned int v54; // eax
  const char *v55; // r8
  __int64 v56; // rbx
  __int64 v57; // rax
  int PlaneSliceFromViewFormat; // r9d
  char v59; // dl
  __int64 v60; // rax
  __int64 v61; // rax
  _DWORD *v62; // rcx
  _DWORD *v63; // rdx
  bool v64; // dl
  const char *v65; // rax
  const char *v66; // r8
  __int64 v67; // r12
  char v68; // si
  bool v69; // dl
  const char *v70; // rax
  _DWORD *v71; // rax
  int v72; // r9d
  unsigned int v73; // r9d
  unsigned int v74; // edx
  unsigned int v75; // eax
  unsigned int v76; // r8d
  int v77; // ecx
  char v78; // r10
  __int64 v79; // rax
  bool v80; // dl
  const char *v81; // rax
  const char *v82; // r8
  int v83; // r9d
  bool v84; // dl
  __int64 v85; // rax
  __int64 v86; // rax
  bool v87; // dl
  const char *v88; // rax
  const char *v89; // r8
  bool v90; // dl
  const char *v91; // rax
  __int64 v92; // r8
  const char *v93; // r8
  bool v94; // dl
  __int64 v95; // r8
  bool v96; // dl
  const char *v97; // rax
  __int64 v98; // r8
  const char *v99; // r8
  bool v100; // dl
  __int64 v101; // r8
  bool v102; // dl
  const char *v103; // rax
  __int64 v104; // r8
  __int64 v105; // r9
  const char *v106; // r8
  __int64 v107; // rax
  bool v108; // dl
  const char *v109; // rax
  const char *v110; // r8
  int v111; // r9d
  bool v112; // dl
  __int64 v113; // r8
  int v114; // eax
  bool v115; // dl
  bool v116; // dl
  const char *v117; // rax
  const char *v118; // r8
  bool v119; // dl
  const char *v120; // rax
  const char *v121; // r8
  bool v122; // dl
  const char *v123; // rax
  int v124; // r9d
  unsigned int v125; // r9d
  unsigned int v126; // eax
  unsigned int v127; // r9d
  const char *v128; // r8
  _DWORD *v129; // rcx
  _DWORD *v130; // rdx
  bool v131; // dl
  const char *v132; // rax
  const char *v133; // r8
  char v134; // r10
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  bool v138; // dl
  bool v139; // dl
  const char *v140; // rax
  const char *v141; // r8
  bool v142; // dl
  const char *v143; // rax
  __int64 v144; // r8
  const char *v145; // r8
  bool v146; // dl
  __int64 v147; // r8
  bool v148; // dl
  __int64 v149; // r8
  __int64 v150; // r9
  __int64 v151; // rax
  bool v152; // dl
  __int64 v153; // r8
  bool v154; // dl
  const char *v155; // rax
  int v156; // r9d
  unsigned int v157; // edx
  unsigned int v158; // eax
  unsigned int v159; // r9d
  bool v160; // dl
  int v161; // esi
  char v162; // al
  __int64 v163; // rax
  const char *v164; // rax
  enum D3D_FEATURE_LEVEL v165; // ecx
  __int64 v166; // rax
  unsigned int v167; // r15d
  unsigned __int64 v168; // r11
  unsigned int v169; // r8d
  unsigned __int64 v170; // r10
  unsigned __int64 v171; // rdx
  unsigned __int64 v172; // rcx
  unsigned int v173; // r8d
  const char *v174; // rax
  __int64 v175; // r8
  __int64 v176; // r9
  const char *v177; // r10
  __int64 v178; // r11
  bool v179; // dl
  const char *v180; // rax
  int v181; // eax
  bool v182; // dl
  const char *v183; // rax
  const char *v184; // rax
  const char *v186; // rax
  __int64 v187; // [rsp+30h] [rbp-B1h]
  __int64 v188; // [rsp+30h] [rbp-B1h]
  __int64 v189; // [rsp+30h] [rbp-B1h]
  __int64 v190; // [rsp+30h] [rbp-B1h]
  __int64 v191; // [rsp+30h] [rbp-B1h]
  unsigned __int16 v193; // [rsp+70h] [rbp-71h]
  int v194; // [rsp+74h] [rbp-6Dh]
  int v195; // [rsp+74h] [rbp-6Dh]
  unsigned __int16 v196; // [rsp+78h] [rbp-69h]
  _DWORD *v197; // [rsp+80h] [rbp-61h]
  unsigned int v198; // [rsp+88h] [rbp-59h]
  int v199; // [rsp+8Ch] [rbp-55h]
  unsigned __int64 v200; // [rsp+90h] [rbp-51h] BYREF
  CDevice *v201; // [rsp+98h] [rbp-49h]
  _BYTE v202[12]; // [rsp+A0h] [rbp-41h] BYREF
  _BYTE v203[56]; // [rsp+B0h] [rbp-31h] BYREF

  v7 = 0;
  *(_QWORD *)v202 = a7;
  v9 = a2;
  v201 = (CDevice *)a4;
  v10 = 1;
  v11 = a2 & -(__int64)(a2 != 0);
  if ( a4[76] < 37120 )
  {
    v7 = 1;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      1157,
      "This operation is not supported on a core or generic device.");
    v9 = a2;
    v10 = 1;
  }
  if ( a3 && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(*(enum DXGI_FORMAT *)a3) )
  {
    v7 += v10;
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 35, "The Format (%#x) is unrecognized.", v12);
    return v7 != 0 ? 0x80070057 : 0;
  }
  if ( !v9 )
  {
    if ( !a3 )
    {
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        42,
        "A RenderTargetView cannot be created from a NULL Resource and NULL Desc.");
      return 2147942487LL;
    }
    v19 = (_DWORD *)(a3 + 4);
    v200 = v10;
    v193 = v10;
    v196 = v10;
    v198 = v10;
    v194 = 0;
    LOBYTE(v199) = v10;
    v197 = (_DWORD *)(a3 + 4);
    if ( *(_DWORD *)(a3 + 4) == 1 )
    {
      v17 = v10;
      goto LABEL_21;
    }
    if ( *(_DWORD *)(a3 + 4) == 2 || *(_DWORD *)(a3 + 4) == 3 )
    {
      v17 = 2;
      goto LABEL_21;
    }
    if ( *(_DWORD *)(a3 + 4) != 4 && *(_DWORD *)(a3 + 4) != 5 )
    {
      if ( (unsigned int)(*(_DWORD *)(a3 + 4) - 6) >= 2 )
      {
        v17 = 4;
LABEL_21:
        v18 = *(_DWORD *)a3;
        goto LABEL_22;
      }
      v198 = 2;
    }
    v17 = 3;
    goto LABEL_21;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 80LL))(v9, v203);
  v14 = DXGI_FORMAT_UNKNOWN;
  LOWORD(v10) = *(_WORD *)(v13 + 28);
  v15 = *(_DWORD *)(v13 + 36);
  v16 = *(_WORD *)(v13 + 30);
  v17 = *(_DWORD *)v13;
  v18 = *(_DWORD *)(v13 + 32);
  v200 = *(_QWORD *)(v13 + 16);
  v194 = *(_DWORD *)(v13 + 44);
  v19 = (_DWORD *)(a3 + 4);
  v198 = v15;
  v9 = *(unsigned int *)(v13 + 48);
  v193 = v10;
  LODWORD(v10) = 1;
  v197 = (_DWORD *)(a3 + 4);
  v196 = v16;
  v199 = *(_DWORD *)(v13 + 48);
  if ( !a3 )
    goto LABEL_39;
LABEL_22:
  v14 = *(_DWORD *)a3;
  if ( *v19 == (_DWORD)v10 )
  {
    v20 = v17 == (_DWORD)v10;
    goto LABEL_37;
  }
  if ( *v19 == 2 )
    goto LABEL_36;
  if ( *v19 == 4 )
  {
    v20 = v17 == 3;
    goto LABEL_37;
  }
  if ( (*v19 != 8 || v17 != 4) && (*v19 != 5 || v17 != 3) && (*v19 != 6 || v17 != 3) && (*v19 != 7 || v17 != 3) )
  {
    if ( *v19 != 3 )
    {
LABEL_38:
      v7 += v10;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        42,
        "The ViewDimension in the View Desc is incompatible with the type of the Resource.");
      LODWORD(v10) = 1;
      goto LABEL_39;
    }
LABEL_36:
    v20 = v17 == 2;
LABEL_37:
    if ( v20 )
      goto LABEL_39;
    goto LABEL_38;
  }
LABEL_39:
  v21 = 0;
  v22 = v17 - 1;
  if ( v22 )
  {
    v23 = v22 - 1;
    if ( v23 )
    {
      if ( v23 != 1 )
      {
        if ( !a3 )
        {
LABEL_43:
          v24 = 0xFFFFFFFFLL;
          if ( (unsigned int)v18 < 0xC0 )
            v24 = (unsigned int)v18;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v24 + 6) & 0xC00) == 0x800 )
          {
            v7 += v10;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              37,
              "A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default "
              "Desc parameters cannot be used, as a fully qualified Format must be supplied.");
          }
LABEL_47:
          v14 = v18;
LABEL_297:
          v49 = a5;
          goto LABEL_298;
        }
        if ( v14 != v18 )
        {
          if ( v11 )
          {
            v25 = *(_DWORD **)(v11 + 328);
            if ( v25 )
            {
              v26 = &v25[*(unsigned __int16 *)(v11 + 412)];
              while ( v25 != v26 )
              {
                if ( *v25 == v14 )
                  goto LABEL_83;
                ++v25;
              }
              v7 += v10;
              GetDebugObjectIdentifierString(v203, v26, 0xFFFFFFFFLL);
              Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v27);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                38,
                "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created"
                " with an explicit format cast list",
                v14,
                Name,
                v29);
              std::string::_Tidy_deallocate(v203);
              goto LABEL_83;
            }
          }
        }
        v30 = 0xFFFFFFFFLL;
        if ( (unsigned int)v18 < 0xC0 )
          v30 = (unsigned int)v18;
        if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v30 + 6) & 0xC00) == 0xC00 )
        {
          if ( v14 == DXGI_FORMAT_UNKNOWN )
          {
            v14 = v18;
LABEL_83:
            v49 = a5;
            if ( (unsigned int)CD3D11FormatHelper::Texture3DSupport((unsigned int)v14, (unsigned int)a5, a6) == -1 )
            {
              ++v7;
              v51 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v50);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                38,
                "The Format (%#x, %s) cannot be used, when creating a View of a Texture3D.",
                v14,
                v51);
            }
            if ( !a2 )
              goto LABEL_298;
            v52 = 1;
            if ( v193 >> *(_BYTE *)(a3 + 8) > 1u )
              v52 = v193 >> *(_BYTE *)(a3 + 8);
            if ( *(_DWORD *)(a3 + 8) < (unsigned int)v196 )
            {
              v53 = *(_DWORD *)(a3 + 12);
              if ( v53 < v52 )
              {
                v54 = *(_DWORD *)(a3 + 16);
                if ( v54 )
                {
                  if ( v54 == -1 || v54 <= v52 && v53 + v54 <= v52 )
                    goto LABEL_298;
                }
              }
            }
            ++v7;
            v55 = "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice (valu"
                  "e = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. FirstWSlice (valu"
                  "e = %u) must be between 0 and the Depth size of the Mip Level, %u, inclusively. With the current First"
                  "WSlice, WSize (value = %u) must be between 1 and %u, inclusively, or -1 to default to all slices from "
                  "FirstWSlice, in order that the View fit on the Texture.";
            goto LABEL_95;
          }
          if ( v18 == v14 )
            goto LABEL_83;
          if ( (int)a6 < 6 )
          {
            v7 += v10;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, (bool)v19);
            v38 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v41);
            v187 = v42;
            v40 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qu"
                  "alified Format, which is not castable (%#x, %s).";
          }
          else
          {
            if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v18 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v14 + 1) )
            {
              v31 = 0xFFFFFFFFLL;
              if ( (unsigned int)v14 < 0xC0 )
                v31 = (unsigned int)v14;
              if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v31 + 6) & 0xC00) != 0x800 )
              {
                v32 = 0xFFFFFFFFLL;
                if ( (unsigned int)v14 < 0xC0 )
                  v32 = (unsigned int)v14;
                if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v32 + 6) & 0xC00) == 0xC00
                  && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v14, v18) )
                {
                  ++v7;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v33);
                  v35 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v34);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    38,
                    "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation "
                    "- this type of format casting is not supported.",
                    v35,
                    v36);
                }
                goto LABEL_83;
              }
            }
            v7 += v10;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, 5 * v14);
            v38 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v37);
            v187 = v39;
            v40 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the sa"
                  "me family as the Format of the Resource (%#x, %s).";
          }
        }
        else
        {
          if ( v14 == DXGI_FORMAT_UNKNOWN )
          {
            v7 += v10;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, (bool)v19);
            v38 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v43);
            v187 = v44;
            v45 = 0;
            v40 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the format"
                  " of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_82:
            TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 38, v40, v45, v38, v18, v187);
            goto LABEL_83;
          }
          if ( v18 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v14 + 1) )
          {
            v46 = 0xFFFFFFFFLL;
            if ( (unsigned int)v14 < 0xC0 )
              v46 = (unsigned int)v14;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v46 + 6) & 0xC00) != 0x800 )
              goto LABEL_83;
          }
          v7 += v10;
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, (bool)v19);
          v38 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v47);
          v187 = v48;
          v40 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable from "
                "the Format of the Resource (%#x, %s).";
        }
        v45 = (unsigned int)v14;
        goto LABEL_82;
      }
      if ( !a3 )
      {
        v56 = 0xFFFFFFFFLL;
        v57 = 0xFFFFFFFFLL;
        if ( (unsigned int)v18 < 0xC0 )
          v57 = (unsigned int)v18;
        if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v57 + 6) & 0xC00) == 0x800 )
        {
          v7 += v10;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            37,
            "A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default De"
            "sc parameters cannot be used, as a fully qualified Format must be supplied.");
        }
        if ( (unsigned int)v18 < 0xC0 )
          v56 = (unsigned int)v18;
        if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v56 + 32) & 0x10) != 0 )
        {
          ++v7;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            37,
            "Views of video formats cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a Vie"
            "w format must be supplied, not the same as the underlying video format.The View format is needed to indicate"
            " how the video surface (or part of it) will appear to shaders - see documentation.");
        }
        goto LABEL_47;
      }
      if ( *(_DWORD *)(a3 + 4) == 4 )
      {
        PlaneSliceFromViewFormat = *(_DWORD *)(a3 + 12);
      }
      else if ( *(_DWORD *)(a3 + 4) == 5 )
      {
        PlaneSliceFromViewFormat = *(_DWORD *)(a3 + 20);
      }
      else
      {
        PlaneSliceFromViewFormat = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetPlaneSliceFromViewFormat(
                                     v18,
                                     *(enum DXGI_FORMAT *)a3);
      }
      v59 = -1;
      v195 = PlaneSliceFromViewFormat;
      v60 = 0xFFFFFFFFLL;
      if ( (unsigned int)v18 < 0xC0 )
        v60 = (unsigned int)v18;
      if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v60 + 32) & 0x10) != 0 )
        goto LABEL_185;
      v61 = 0xFFFFFFFFLL;
      if ( (unsigned int)v18 < 0xC0 )
        v61 = (unsigned int)v18;
      if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v61 + 32) & 8) != 0 )
      {
LABEL_185:
        v49 = a5;
        v114 = ValidateD3DPlanarAndYUVResourceViewFormat(
                 (unsigned int)v18,
                 (unsigned int)v14,
                 (unsigned int)a5,
                 a6,
                 32,
                 PlaneSliceFromViewFormat);
        if ( v114 )
        {
          ++v7;
          if ( v114 == 3 )
          {
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v115);
            v117 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v116);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              39,
              "The Plane Slice %d cannot be used when the resource format is %s and the view format is %s.  See documenta"
              "tion for the set of valid view format names for this resource format, determining which how the resource ("
              "or part of it) will appear to shader.",
              v195,
              v117,
              v118);
          }
          else
          {
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v115);
            v120 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v119);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              38,
              "For the resource format %s, when making a D3D view, the format name for the view can't be %s.  See documen"
              "tation for the set of valid view format names for this resource format, determining which how the resource"
              " (or part of it) will appear to shader.",
              v120,
              v121);
          }
        }
        else if ( (v199 & 1) != 0
               && (unsigned int)CD3D11FormatHelper::RenderTargetSupport((unsigned int)v18, (unsigned int)a5, a6) == -1 )
        {
          ++v7;
          v123 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v122);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            38,
            "The video format %s does not support RenderTargetViews. For this format, specifying D3D12_RESOURCE_FLAG_ALLO"
            "W_RENDER_TARGET when the surface created actually only allows the surface to be used for video processor dec"
            "ode output.  For some other video formats (depending on device Feature Level as well), D3D12_RESOURCE_FLAG_A"
            "LLOW_RENDER_TARGET does allow both video processor decode output and RenderTargetView output, but not in this case.",
            v123);
        }
        goto LABEL_125;
      }
      if ( v14 != v18 )
      {
        if ( v11 )
        {
          v62 = *(_DWORD **)(v11 + 328);
          if ( v62 )
          {
            v63 = &v62[*(unsigned __int16 *)(v11 + 412)];
            while ( 1 )
            {
              if ( v62 == v63 )
              {
                v7 += v10;
                GetDebugObjectIdentifierString(v203, v63, v9);
                v65 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v64);
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  38,
                  "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was creat"
                  "ed with an explicit format cast list",
                  v14,
                  v65,
                  v66);
                std::string::_Tidy_deallocate(v203);
                goto LABEL_124;
              }
              if ( *v62 == v14 )
                break;
              ++v62;
            }
            if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v18) )
            {
              v67 = a2;
              v49 = a5;
              if ( !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v14) )
              {
                v68 = v78;
LABEL_127:
                if ( (unsigned int)CD3D11FormatHelper::Texture2DSupport((unsigned int)v14, (unsigned int)v49, a6) == -1 )
                {
                  ++v7;
                  v70 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v69);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    38,
                    "The Format (%#x, %s) cannot be used, when creating a View of a Texture2D.",
                    v14,
                    v70);
                }
                if ( v67 )
                {
                  v71 = (_DWORD *)(a3 + 4);
                  if ( *(_DWORD *)(a3 + 4) == 5 )
                  {
                    if ( v68 )
                    {
                      v72 = *(_DWORD *)(a3 + 16);
                      if ( v72 != 1 )
                      {
                        ++v7;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          41,
                          "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                          v72);
                      }
                    }
                    v73 = *(_DWORD *)(a3 + 8);
                    if ( v73 >= v196
                      || (v74 = *(_DWORD *)(a3 + 12), v74 >= v193)
                      || (v75 = *(_DWORD *)(a3 + 16)) == 0
                      || v75 != -1 && (v75 > v193 || v74 + v75 > v193) )
                    {
                      ++v7;
                      v76 = *(_DWORD *)(a3 + 12);
                      v77 = v193;
                      if ( v193 >= v76 )
                        v77 = *(_DWORD *)(a3 + 12);
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        41,
                        "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice"
                        " (value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. First"
                        "ArraySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusiv"
                        "ely. With the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusiv"
                        "ely, or -1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.",
                        v73,
                        v196 - 1,
                        v76,
                        v193 - 1,
                        *(_DWORD *)(a3 + 16),
                        v193 - v77);
                    }
                  }
                  else if ( *v71 == 7 )
                  {
                    if ( v68 )
                    {
                      v124 = *(_DWORD *)(a3 + 12);
                      if ( v124 != 1 )
                      {
                        ++v7;
                        TDebugOutputFunctor::operator()(
                          &g_coreRuntimeTallyErrorOutputFunctor,
                          41,
                          "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                          v124);
                      }
                    }
                    v125 = *(_DWORD *)(a3 + 8);
                    if ( v125 >= v193
                      || (v126 = *(_DWORD *)(a3 + 12)) == 0
                      || v126 != -1 && (v126 > v193 || v125 + v126 > v193) )
                    {
                      ++v7;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        41,
                        "The Dimensions of the View are invalid due to at least one of the following conditions. FirstArr"
                        "aySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively"
                        ". With the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively"
                        ", or -1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.");
                    }
                  }
                  else
                  {
                    if ( *v71 != 4 )
                      goto LABEL_206;
                    v127 = *(_DWORD *)(a3 + 8);
                    if ( v127 >= v196 )
                    {
                      ++v7;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        41,
                        "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice"
                        " (value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. ",
                        v127,
                        v196 - 1);
                    }
                  }
                }
                v71 = v197;
LABEL_206:
                if ( v198 > 1 )
                {
                  if ( *v71 == 4 )
                  {
                    v128 = "The base resource was created as a multisample resource.  You must specify D3D12_RTV_DIMENSIO"
                           "N_TEXTURE2DMS instead of D3D12_RTV_DIMENSION_TEXTURE2D.";
                  }
                  else
                  {
                    if ( *v71 != 5 )
                      goto LABEL_298;
                    v128 = "The base resource was created as a multisample resource.  You must specify D3D12_RTV_DIMENSIO"
                           "N_TEXTURE2DMSARRAYinstead of D3D12_RTV_DIMENSION_TEXTURE2DARRAY.";
                  }
                  ++v7;
                  TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 37, v128);
                  goto LABEL_298;
                }
                goto LABEL_298;
              }
LABEL_126:
              v68 = 0;
              goto LABEL_127;
            }
            goto LABEL_124;
          }
        }
      }
      v79 = 0xFFFFFFFFLL;
      if ( (unsigned int)v18 < 0xC0 )
        v79 = (unsigned int)v18;
      if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v79 + 6) & 0xC00) == 0xC00 )
      {
        if ( v14 )
        {
          if ( v18 != v14 )
          {
            *(_DWORD *)v202 = v18;
            *(_QWORD *)&v202[4] = 0;
            CDevice::CheckFeatureSupport(v201, D3D12_FEATURE_FORMAT_SUPPORT, v202, 0xCu);
            if ( (int)a6 < 6 )
            {
              if ( (*(_DWORD *)&v202[4] & 0x1000000) != 0 )
              {
                v67 = a2;
                if ( *(_BYTE *)(a2 + 312) )
                {
                  v59 = 5 * v14;
                  if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v18 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v14 + 1) )
                    goto LABEL_152;
                  ++v7;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v59);
                  v97 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v100);
                  v189 = v101;
                  v99 = "The view format (%#x, %s) is invalid. The view format and resource format (%#x, %s) must be from"
                        " the same format family.";
                }
                else
                {
                  ++v7;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v84);
                  v97 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v96);
                  v189 = v98;
                  v99 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fu"
                        "lly qualified Format, which is not castable (%#x, %s), unless the resource is a DXGI swap chain back buffer.";
                }
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  38,
                  v99,
                  (unsigned int)v14,
                  v97,
                  v18,
                  v189);
LABEL_152:
                if ( v195 )
                {
                  ++v7;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v59);
                  v81 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v80);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    40,
                    "The PlaneSlice %d is invalid when the resource format is %s and the view format is %s.  Only Plane S"
                    "lice 0 is valid when creating a view on a non-planar format.",
                    v83,
                    v81,
                    v82);
                }
                v49 = a5;
                goto LABEL_126;
              }
              ++v7;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v84);
              v91 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v94);
              v188 = v95;
              v93 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully "
                    "qualified Format, which is not castable (%#x, %s).";
            }
            else
            {
              v59 = 5 * v14;
              if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v18 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v14 + 1) )
              {
                v59 = -1;
                v85 = 0xFFFFFFFFLL;
                if ( (unsigned int)v14 < 0xC0 )
                  v85 = (unsigned int)v14;
                if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v85 + 6) & 0xC00) != 0x800 )
                {
                  v86 = 0xFFFFFFFFLL;
                  if ( (unsigned int)v14 < 0xC0 )
                    v86 = (unsigned int)v14;
                  if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v86 + 6) & 0xC00) == 0xC00
                    && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v14, v18) )
                  {
                    ++v7;
                    D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v59);
                    v88 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v87);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      38,
                      "The resource format (%s) and view format (%s) differ in float vs non-float component interpretatio"
                      "n - this type of format casting is not supported.",
                      v88,
                      v89);
                  }
                  goto LABEL_151;
                }
              }
              ++v7;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v59);
              v91 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v90);
              v188 = v92;
              v93 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the "
                    "same family as the Format of the Resource (%#x, %s).";
            }
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              38,
              v93,
              (unsigned int)v14,
              v91,
              v18,
              v188);
          }
        }
        else
        {
          v14 = v18;
        }
LABEL_151:
        v67 = a2;
        goto LABEL_152;
      }
      if ( v14 )
      {
        if ( v18 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v14 + 1) )
        {
          v107 = 0xFFFFFFFFLL;
          if ( (unsigned int)v14 < 0xC0 )
            v107 = (unsigned int)v14;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v107 + 6) & 0xC00) != 0x800 )
          {
            if ( PlaneSliceFromViewFormat )
            {
              v7 += v10;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, -1);
              v109 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v108);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                40,
                "The PlaneSlice %d is invalid when the resource format is %s and the view format is %s.  Only Plane Slice"
                " 0 is valid when creating a view on a non-planar format.",
                v111,
                v109,
                v110);
            }
            goto LABEL_124;
          }
        }
        v7 += v10;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, -1);
        v103 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v112);
        v190 = v113;
        v105 = (unsigned int)v14;
        v106 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable from t"
               "he Format of the Resource (%#x, %s).";
      }
      else
      {
        v7 += v10;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, -1);
        v103 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v102);
        v190 = v104;
        v105 = 0;
        v106 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the format of"
               " the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
      }
      TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 38, v106, v105, v103, v18, v190);
LABEL_124:
      v49 = a5;
LABEL_125:
      v67 = a2;
      goto LABEL_126;
    }
    if ( !a3 )
      goto LABEL_43;
    if ( v14 != v18 )
    {
      if ( v11 )
      {
        v129 = *(_DWORD **)(v11 + 328);
        if ( v129 )
        {
          v130 = &v129[*(unsigned __int16 *)(v11 + 412)];
          while ( 1 )
          {
            if ( v129 == v130 )
            {
              v7 += v10;
              GetDebugObjectIdentifierString(v203, v130, 0xFFFFFFFFLL);
              v132 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v131);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                38,
                "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created"
                " with an explicit format cast list",
                v14,
                v132,
                v133);
              std::string::_Tidy_deallocate(v203);
              goto LABEL_252;
            }
            if ( *v129 == v14 )
              break;
            ++v129;
          }
          if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v18)
            && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v14) )
          {
            v21 = v134;
          }
LABEL_252:
          v49 = a5;
          if ( (unsigned int)CD3D11FormatHelper::Texture1DSupport((unsigned int)v14, (unsigned int)a5, a6) == -1 )
          {
            ++v7;
            v155 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v154);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              38,
              "The Format (%#x, %s) cannot be used, when creating a View of a Texture1D.",
              v14,
              v155);
          }
          if ( !a2 )
            goto LABEL_298;
          if ( *(_DWORD *)(a3 + 4) != 3 )
          {
            v159 = *(_DWORD *)(a3 + 8);
            if ( v159 >= v196 )
            {
              ++v7;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                41,
                "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice (value "
                "= %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. ",
                v159,
                v196 - 1);
            }
            goto LABEL_298;
          }
          if ( v21 )
          {
            v156 = *(_DWORD *)(a3 + 16);
            if ( v156 != 1 )
            {
              ++v7;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                41,
                "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                v156);
            }
          }
          if ( *(_DWORD *)(a3 + 8) >= (unsigned int)v196
            || (v157 = *(_DWORD *)(a3 + 12), v157 >= v193)
            || (v158 = *(_DWORD *)(a3 + 16)) == 0
            || v158 != -1 && (v158 > v193 || v157 + v158 > v193) )
          {
            ++v7;
            v55 = "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice (valu"
                  "e = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. FirstArraySlice ("
                  "value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. With the curr"
                  "ent FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or -1 to default to"
                  " all slices from FirstArraySlice, in order that the View fit on the Texture.";
LABEL_95:
            TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 41, v55);
          }
LABEL_298:
          v200 = (unsigned int)v14;
          v181 = ValidateRenderTargetViewFormats(&v200, v201, (unsigned int)v49, a6, -1);
          if ( v181 == -2147467263 )
          {
            ++v7;
            v184 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v182);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              36,
              "The format (%#x, %s) cannot be used with a RenderTarget view because this particular graphics implementati"
              "on doesn't support this format. ",
              (unsigned int)v14,
              v184);
          }
          else if ( v181 == -2147024809 )
          {
            ++v7;
            v183 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v182);
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              38,
              "The format (%#x, %s) cannot be used with a RenderTarget view. ",
              (unsigned int)v14,
              v183);
          }
          if ( (v199 & 1) == 0 )
          {
            ++v7;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              42,
              "A RenderTargetView cannot be created of a Resource that did not specify the RENDER_TARGET MiscFlag.");
          }
          return v7 != 0 ? 0x80070057 : 0;
        }
      }
    }
    v135 = 0xFFFFFFFFLL;
    if ( (unsigned int)v18 < 0xC0 )
      v135 = (unsigned int)v18;
    if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v135 + 6) & 0xC00) == 0xC00 )
    {
      if ( v14 == DXGI_FORMAT_UNKNOWN )
      {
        v14 = v18;
LABEL_251:
        v21 = 0;
        goto LABEL_252;
      }
      if ( v18 == v14 )
        goto LABEL_251;
      if ( (int)a6 < 6 )
      {
        v7 += v10;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, (bool)v19);
        v143 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v146);
        v191 = v147;
        v145 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully quali"
               "fied Format, which is not castable (%#x, %s).";
      }
      else
      {
        if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v18 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
                                                                                                + 10 * v14
                                                                                                + 1) )
        {
          v136 = 0xFFFFFFFFLL;
          if ( (unsigned int)v14 < 0xC0 )
            v136 = (unsigned int)v14;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v136 + 6) & 0xC00) != 0x800 )
          {
            v137 = 0xFFFFFFFFLL;
            if ( (unsigned int)v14 < 0xC0 )
              v137 = (unsigned int)v14;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v137 + 6) & 0xC00) == 0xC00
              && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v14, v18) )
            {
              ++v7;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v138);
              v140 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, v139);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                38,
                "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - th"
                "is type of format casting is not supported.",
                v140,
                v141);
            }
            goto LABEL_251;
          }
        }
        v7 += v10;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, 5 * v14);
        v143 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v142);
        v191 = v144;
        v145 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the same "
               "family as the Format of the Resource (%#x, %s).";
      }
    }
    else
    {
      if ( v14 == DXGI_FORMAT_UNKNOWN )
      {
        v7 += v10;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, (bool)v19);
        v143 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v148);
        v191 = v149;
        v150 = 0;
        v145 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the format of"
               " the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_250:
        TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 38, v145, v150, v143, v18, v191);
        goto LABEL_251;
      }
      if ( v18 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v14 + 1) )
      {
        v151 = 0xFFFFFFFFLL;
        if ( (unsigned int)v14 < 0xC0 )
          v151 = (unsigned int)v14;
        if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v151 + 6) & 0xC00) != 0x800 )
          goto LABEL_251;
      }
      v7 += v10;
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v18, (bool)v19);
      v143 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v152);
      v191 = v153;
      v145 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable from the"
             " Format of the Resource (%#x, %s).";
    }
    v150 = (unsigned int)v14;
    goto LABEL_250;
  }
  if ( !a3 )
  {
    v7 += v10;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      37,
      "A View of a Buffer cannot be created using a NULL Desc. Default Desc parameters cannot be used, as a Format must be supplied.");
    goto LABEL_297;
  }
  v161 = CD3D11FormatHelper::BufferSupport((unsigned int)v14, (unsigned int)a5, a6);
  *(_DWORD *)v202 = v14;
  v162 = 0;
  *(_QWORD *)&v202[4] = 0;
  if ( v161 == -2 )
  {
    CDevice::CheckFeatureSupport(v201, D3D12_FEATURE_FORMAT_SUPPORT, v202, 0xCu);
    v162 = v202[4];
LABEL_273:
    if ( v14 && (v161 != -2 || (v162 & 1) != 0) )
    {
      v163 = 0xFFFFFFFFLL;
      if ( (unsigned int)v14 < 0xC0 )
        v163 = (unsigned int)v14;
      if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v163 + 6) & 0xC00) == 0x800 )
      {
        ++v7;
        v164 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v160);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          38,
          "The Format (%#x, %s) is invalid, when creating a View; because it is a typeless format",
          v14,
          v164);
      }
      v165 = a5;
      v166 = 0xFFFFFFFFLL;
      if ( (unsigned int)v14 < 0xC0 )
        v166 = (unsigned int)v14;
      v167 = 0x4000;
      if ( a5 < D3D_FEATURE_LEVEL_11_0 )
        v167 = 0x2000;
      if ( a2 )
      {
        v168 = *(_QWORD *)(a3 + 8);
        v169 = *((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v166 + 20) >> 3;
        v170 = 0xFFFFFFFF / v169;
        if ( v168 > v170
          || v168 * v169 >= v200
          || (v171 = *(unsigned int *)(a3 + 16), !(_DWORD)v171)
          || (v172 = v171 + v168, v171 + v168 < v171)
          || v172 > v170
          || v169 * v172 > v200
          || (unsigned int)v171 > v167 )
        {
          ++v7;
          FeatureLevelToString(a5);
          v174 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v200 % v173);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            41,
            "The Dimensions of the View are invalid due to at least one of the following conditions. Assuming this Format"
            " (%#x, %s), FirstElement (value = %I64u) must be between 0 and the maximum offset of the Buffer, %I64u, incl"
            "usively. With the current FirstElement, NumElements (value = %u) must be between 1 and %I64u, inclusively, i"
            "n order that the View fit on the Buffer. In addition, the NumElements may not be larger than %u for feature level %s.",
            v14,
            v174,
            v178,
            v176,
            *(_DWORD *)(a3 + 16),
            v175,
            v167,
            v177);
        }
        v165 = a5;
      }
      if ( v194 == 2
        && (unsigned int)CD3D11FormatHelper::TiledResourceSupport((unsigned int)v14, 1, 1, (unsigned int)v165, a6) == -1 )
      {
        ++v7;
        v180 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v179);
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          38,
          "The Format (%#x, %s) cannot be used with a Tiled Resource.",
          v14,
          v180);
      }
      goto LABEL_297;
    }
    goto LABEL_305;
  }
  if ( v161 != -1 )
    goto LABEL_273;
LABEL_305:
  v186 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v14, v160);
  TDebugOutputFunctor::operator()(
    &g_coreRuntimeTallyErrorOutputFunctor,
    38,
    "The Format (%#x, %s) cannot be used, when creating a View of a Buffer.",
    v14,
    v186);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180033b20  mov     [rsp-8+arg_0], rbx
0x180033b25  push    rbp
0x180033b26  push    rsi
0x180033b27  push    rdi
0x180033b28  push    r12
0x180033b2a  push    r13
0x180033b2c  push    r14
0x180033b2e  push    r15
0x180033b30  lea     rbp, [rsp-0Fh]
0x180033b35  sub     rsp, 0F0h
0x180033b3c  mov     rax, cs:__security_cookie
0x180033b43  xor     rax, rsp
0x180033b46  mov     [rbp+3Fh+var_38], rax
0x180033b4a  mov     eax, [rbp+3Fh+arg_20]
0x180033b4d  lea     r12, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180033b54  mov     [rbp+3Fh+var_BC], eax
0x180033b57  xor     edi, edi
0x180033b59  mov     rax, [rbp+3Fh+arg_30]
0x180033b5d  mov     r13, r8
0x180033b60  mov     [rbp+3Fh+var_80], rax
0x180033b64  mov     r8, rdx
0x180033b67  mov     rax, rdx
0x180033b6a  mov     [rbp+3Fh+var_88], r9
0x180033b6e  neg     rax
0x180033b71  mov     [rbp+3Fh+var_B8], rdx
0x180033b75  lea     r10d, [rdi+1]
0x180033b79  sbb     r15, r15
0x180033b7c  and     r15, rdx
0x180033b7f  cmp     dword ptr [r9+130h], 9100h
0x180033b8a  jge     short loc_180033BAD
0x180033b8c  lea     r8, aThisOperationI; "This operation is not supported on a co"...
0x180033b93  mov     edx, 485h
0x180033b98  mov     rcx, r12
0x180033b9b  mov     edi, r10d
0x180033b9e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180033ba3  mov     r8, [rbp+3Fh+var_B8]
0x180033ba7  mov     r10d, 1
0x180033bad  test    r13, r13
0x180033bb0  jz      short loc_180033BDE
0x180033bb2  mov     r9d, [r13+0]
0x180033bb6  mov     ecx, r9d; enum DXGI_FORMAT
0x180033bb9  call    ?FormatExists@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(DXGI_FORMAT)
0x180033bbe  test    al, al
0x180033bc0  jnz     short loc_180033BDE
0x180033bc2  add     edi, r10d
0x180033bc5  lea     r8, aTheFormatXIsUn; "The Format (%#x) is unrecognized."
0x180033bcc  mov     edx, 23h ; '#'
0x180033bd1  mov     rcx, r12
0x180033bd4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180033bd9  jmp     loc_180034F30
0x180033bde  test    r8, r8
0x180033be1  jz      short loc_180033C44
0x180033be3  mov     rax, [r8]
0x180033be6  lea     rdx, [rbp+3Fh+var_70]
0x180033bea  mov     rcx, r8
0x180033bed  mov     rax, [rax+50h]
0x180033bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bf6  xor     ebx, ebx
0x180033bf8  mov     rdx, [rax+10h]
0x180033bfc  movzx   r10d, word ptr [rax+1Ch]
0x180033c01  mov     r8d, [rax+24h]
0x180033c05  movzx   r9d, word ptr [rax+1Eh]
0x180033c0a  mov     r14d, [rax]
0x180033c0d  mov     esi, [rax+20h]
0x180033c10  mov     [rbp+3Fh+var_90], rdx
0x180033c14  mov     edx, [rax+2Ch]
0x180033c17  mov     [rbp+3Fh+var_AC], edx
0x180033c1a  lea     rdx, [r13+4]
0x180033c1e  mov     [rbp+3Fh+var_98], r8d
0x180033c22  mov     r8d, [rax+30h]
0x180033c26  mov     [rbp+3Fh+var_B0], r10d
0x180033c2a  lea     r10d, [rbx+1]
0x180033c2e  mov     [rbp+3Fh+var_A0], rdx
0x180033c32  mov     dword ptr [rbp+3Fh+var_A8], r9d
0x180033c36  mov     [rbp+3Fh+var_94], r8d
0x180033c3a  test    r13, r13
0x180033c3d  jnz     short loc_180033CBB
0x180033c3f  jmp     loc_180033D30
0x180033c44  test    r13, r13
0x180033c47  jz      loc_180034F64
0x180033c4d  lea     rdx, [r13+4]
0x180033c51  mov     [rbp+3Fh+var_90], r10
0x180033c55  mov     ecx, [rdx]
0x180033c57  mov     [rbp+3Fh+var_B0], r10d
0x180033c5b  mov     dword ptr [rbp+3Fh+var_A8], r10d
0x180033c5f  mov     [rbp+3Fh+var_98], r10d
0x180033c63  mov     [rbp+3Fh+var_AC], 0
0x180033c6a  mov     [rbp+3Fh+var_94], r10d
0x180033c6e  mov     [rbp+3Fh+var_A0], rdx
0x180033c72  sub     ecx, 1
0x180033c75  jz      short loc_180033CB4
0x180033c77  sub     ecx, 1
0x180033c7a  jz      short loc_180033CAC
0x180033c7c  sub     ecx, 1
0x180033c7f  jz      short loc_180033CAC
0x180033c81  sub     ecx, 1
0x180033c84  jz      short loc_180033CA4
0x180033c86  sub     ecx, 1
0x180033c89  jz      short loc_180033CA4
0x180033c8b  sub     ecx, 1
0x180033c8e  jz      short loc_180033C9D
0x180033c90  cmp     ecx, 1
0x180033c93  jz      short loc_180033C9D
0x180033c95  mov     r14d, 4
0x180033c9b  jmp     short loc_180033CB7
0x180033c9d  mov     [rbp+3Fh+var_98], 2
0x180033ca4  mov     r14d, 3
0x180033caa  jmp     short loc_180033CB7
0x180033cac  mov     r14d, 2
0x180033cb2  jmp     short loc_180033CB7
0x180033cb4  mov     r14d, r10d
0x180033cb7  mov     esi, [r13+0]
0x180033cbb  mov     ebx, [r13+0]
0x180033cbf  mov     rax, rdx
0x180033cc2  cmp     [rax], r10d
0x180033cc5  jnz     short loc_180033CCC
0x180033cc7  cmp     r14d, r10d
0x180033cca  jmp     short loc_180033D11
0x180033ccc  cmp     dword ptr [rax], 2
0x180033ccf  jz      short loc_180033D0D
0x180033cd1  cmp     dword ptr [rax], 4
0x180033cd4  jnz     short loc_180033CDC
0x180033cd6  cmp     r14d, 3
0x180033cda  jmp     short loc_180033D11
0x180033cdc  cmp     dword ptr [rax], 8
0x180033cdf  jnz     short loc_180033CE7
0x180033ce1  cmp     r14d, 4
0x180033ce5  jz      short loc_180033D30
0x180033ce7  cmp     dword ptr [rax], 5
0x180033cea  jnz     short loc_180033CF2
0x180033cec  cmp     r14d, 3
0x180033cf0  jz      short loc_180033D30
0x180033cf2  cmp     dword ptr [rax], 6
0x180033cf5  jnz     short loc_180033CFD
0x180033cf7  cmp     r14d, 3
0x180033cfb  jz      short loc_180033D30
0x180033cfd  cmp     dword ptr [rax], 7
0x180033d00  jnz     short loc_180033D08
0x180033d02  cmp     r14d, 3
0x180033d06  jz      short loc_180033D30
0x180033d08  cmp     dword ptr [rax], 3
0x180033d0b  jnz     short loc_180033D13
0x180033d0d  cmp     r14d, 2
0x180033d11  jz      short loc_180033D30
0x180033d13  add     edi, r10d
0x180033d16  lea     r8, aTheViewdimensi; "The ViewDimension in the View Desc is i"...
0x180033d1d  mov     edx, 2Ah ; '*'
0x180033d22  mov     rcx, r12
0x180033d25  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180033d2a  mov     r10d, 1
0x180033d30  xor     r12b, r12b
0x180033d33  mov     [rsp+120h+var_C0], r12b
0x180033d38  sub     r14d, 1
0x180033d3c  jz      loc_180034C7C
0x180033d42  sub     r14d, 1
0x180033d46  jz      loc_1800348C0
0x180033d4c  cmp     r14d, 1
0x180033d50  jz      loc_1800340EB
0x180033d56  test    r13, r13
0x180033d59  jnz     short loc_180033DAC
0x180033d5b  or      eax, 0FFFFFFFFh
0x180033d5e  lea     r14, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180033d65  mov     r12d, 0C0h
0x180033d6b  mov     r15d, 0C00h
0x180033d71  cmp     esi, r12d
0x180033d74  cmovb   eax, esi
0x180033d77  lea     rcx, [rax+rax*4]
0x180033d7b  mov     eax, [r14+rcx*8+18h]
0x180033d80  and     eax, r15d
0x180033d83  cmp     eax, 800h
0x180033d88  jnz     short loc_180033DA5
0x180033d8a  add     edi, r10d
0x180033d8d  lea     r8, aAViewCannotBeC; "A View cannot be created using a NULL D"...
0x180033d94  mov     edx, 25h ; '%'
0x180033d99  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180033da0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180033da5  mov     ebx, esi
0x180033da7  jmp     loc_180034E96
0x180033dac  or      r8d, 0FFFFFFFFh
0x180033db0  cmp     ebx, esi
0x180033db2  jz      loc_180033E3B
0x180033db8  test    r15, r15
0x180033dbb  jz      short loc_180033E3B
0x180033dbd  mov     rcx, [r15+148h]
0x180033dc4  test    rcx, rcx
0x180033dc7  jz      short loc_180033E3B
0x180033dc9  movzx   eax, word ptr [r15+19Ch]
0x180033dd1  lea     rdx, [rcx+rax*4]
0x180033dd5  jmp     short loc_180033DE3
0x180033dd7  cmp     [rcx], ebx
0x180033dd9  jz      loc_180034001
0x180033ddf  add     rcx, 4
0x180033de3  cmp     rcx, rdx
0x180033de6  jnz     short loc_180033DD7
0x180033de8  lea     rcx, [rbp+3Fh+var_70]
0x180033dec  add     edi, r10d
0x180033def  call    ?GetDebugObjectIdentifierString@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUID3D12DeviceChild@@@Z; GetDebugObjectIdentifierString(ID3D12DeviceChild *)
0x180033df4  mov     r8, rax
0x180033df7  cmp     qword ptr [rax+18h], 0Fh
0x180033dfc  jbe     short loc_180033E01
0x180033dfe  mov     r8, [rax]
0x180033e01  mov     ecx, ebx; enum DXGI_FORMAT
0x180033e03  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033e08  mov     [rsp+120h+var_F8], r8
0x180033e0d  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180033e14  lea     r8, aTheViewFormatX; "The view format (%#x, %s) was not speci"...
0x180033e1b  mov     [rsp+120h+var_100], rax
0x180033e20  mov     edx, 26h ; '&'
0x180033e25  mov     r9d, ebx
0x180033e28  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180033e2d  lea     rcx, [rbp+3Fh+var_70]
0x180033e31  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180033e36  jmp     loc_180034001
0x180033e3b  mov     eax, r8d
0x180033e3e  lea     r14, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180033e45  mov     r15d, 0C00h
0x180033e4b  mov     r12d, 0C0h
0x180033e51  cmp     esi, r12d
0x180033e54  cmovb   eax, esi
0x180033e57  lea     rax, [rax+rax*4]
0x180033e5b  mov     eax, [r14+rax*8+18h]
0x180033e60  and     eax, r15d
0x180033e63  cmp     eax, r15d
0x180033e66  jnz     loc_180033F71
0x180033e6c  test    ebx, ebx
0x180033e6e  jnz     short loc_180033E77
0x180033e70  mov     ebx, esi
0x180033e72  jmp     loc_180034001
0x180033e77  cmp     esi, ebx
0x180033e79  jz      loc_180034001
0x180033e7f  cmp     [rbp+3Fh+arg_28], 6
0x180033e83  jl      loc_180033F4F
0x180033e89  movsxd  rax, ebx
0x180033e8c  lea     rdx, [rax+rax*4]; bool
0x180033e90  movsxd  rax, esi
0x180033e93  lea     rcx, [rax+rax*4]
0x180033e97  mov     eax, [r14+rdx*8+4]
0x180033e9c  cmp     [r14+rcx*8+4], eax
0x180033ea1  jnz     loc_180033F2A
0x180033ea7  cmp     ebx, r12d
0x180033eaa  mov     eax, r8d
0x180033ead  cmovb   eax, ebx
0x180033eb0  lea     rcx, [rax+rax*4]
0x180033eb4  mov     eax, [r14+rcx*8+18h]
0x180033eb9  and     eax, r15d
0x180033ebc  cmp     eax, 800h
0x180033ec1  jz      short loc_180033F2A
0x180033ec3  cmp     ebx, r12d
0x180033ec6  mov     eax, r8d
0x180033ec9  cmovb   eax, ebx
0x180033ecc  lea     rax, [rax+rax*4]
0x180033ed0  mov     eax, [r14+rax*8+18h]
0x180033ed5  and     eax, r15d
0x180033ed8  cmp     eax, r15d
0x180033edb  jnz     loc_180034001
0x180033ee1  mov     edx, esi; enum DXGI_FORMAT
0x180033ee3  mov     ecx, ebx; enum DXGI_FORMAT
0x180033ee5  call    ?FloatAndNotFloatFormats@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@0@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(DXGI_FORMAT,DXGI_FORMAT)
0x180033eea  test    al, al
0x180033eec  jz      loc_180034001
0x180033ef2  mov     ecx, ebx; enum DXGI_FORMAT
0x180033ef4  inc     edi
0x180033ef6  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033efb  mov     ecx, esi; enum DXGI_FORMAT
0x180033efd  mov     r8, rax
0x180033f00  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033f05  mov     [rsp+120h+var_100], r8
0x180033f0a  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180033f11  mov     r9, rax
0x180033f14  lea     r8, aTheResourceFor; "The resource format (%s) and view forma"...
0x180033f1b  mov     edx, 26h ; '&'
0x180033f20  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180033f25  jmp     loc_180034001
0x180033f2a  mov     ecx, esi; enum DXGI_FORMAT
0x180033f2c  add     edi, r10d
0x180033f2f  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033f34  mov     ecx, ebx; enum DXGI_FORMAT
0x180033f36  mov     r8, rax
0x180033f39  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033f3e  mov     [rsp+120h+var_F0], r8
0x180033f43  lea     r8, aTheFormatXSIsI_0; "The Format (%#x, %s) is invalid when cr"...
0x180033f4a  jmp     loc_180033FE4
0x180033f4f  mov     ecx, esi; enum DXGI_FORMAT
0x180033f51  add     edi, r10d
0x180033f54  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033f59  mov     ecx, ebx; enum DXGI_FORMAT
0x180033f5b  mov     r8, rax
0x180033f5e  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033f63  mov     [rsp+120h+var_F0], r8
0x180033f68  lea     r8, aTheFormatXSIsI_8; "The Format (%#x, %s) is invalid when cr"...
0x180033f6f  jmp     short loc_180033FE4
0x180033f71  test    ebx, ebx
0x180033f73  jnz     short loc_180033F9A
0x180033f75  mov     ecx, esi; enum DXGI_FORMAT
0x180033f77  add     edi, r10d
0x180033f7a  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033f7f  xor     ecx, ecx; enum DXGI_FORMAT
0x180033f81  mov     r8, rax
0x180033f84  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180033f89  mov     [rsp+120h+var_F0], r8
  ... truncated ...
```
