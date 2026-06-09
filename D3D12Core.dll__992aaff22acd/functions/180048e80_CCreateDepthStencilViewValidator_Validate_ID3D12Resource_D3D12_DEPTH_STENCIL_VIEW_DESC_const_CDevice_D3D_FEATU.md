# CCreateDepthStencilViewValidator::Validate(ID3D12Resource *,D3D12_DEPTH_STENCIL_VIEW_DESC const *,CDevice *,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures)

- ea: `0x180048e80`
- end: `0x180049b24`
- name: `?Validate@CCreateDepthStencilViewValidator@@QEAA_NPEAUID3D12Resource@@PEBUD3D12_DEPTH_STENCIL_VIEW_DESC@@PEAVCDevice@@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@CD3D11FormatHelper@@@Z`
- size: `3236`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800ec17c`

## callees

- `0x1800264c0`
- `0x1800268f0`
- `0x18002ef50`
- `0x180031ec0`
- `0x180033a70`
- `0x180048934`
- `0x180048e80`
- `0x180049bb0`
- `0x18005e09c`
- `0x18009fd4c`
- `0x1800aa248`
- `0x1800abc10`
- `0x1800bb480`
- `0x180262020`

## string_xrefs

- `0x180049106`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x1800495b5`: `The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created with an explicit format cast list`
- `0x180049917`: `A DepthStencilView cannot be created of a Buffer nor Texture3D Resource.`
- `0x18004938f`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180049457`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x18004983b`: `When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.`
- `0x180049075`: `A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default Desc parameters cannot be used, as a fully qualified Format must be supplied.`
- `0x180049287`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x180049736`: `The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualified Format, which is not castable (%#x, %s).`
- `0x180049233`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x1800496e2`: `The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - this type of format casting is not supported.`
- `0x180049006`: `The ViewDimension in the View Desc incompatible with the type of the Resource.`
- `0x180049ae3`: `A DepthStencilView cannot be created from a NULL Resource and NULL Desc.`
- `0x180049533`: `The base resource was created as a multisample resource.  You must specify D3D11_DSV_DIMENSION_TEXTURE2DMSARRAYinstead of D3D11_DSV_DIMENSION_TEXTURE2DARRAY.`
- `0x180049518`: `The base resource was created as a multisample resource.  You must specify D3D11_DSV_DIMENSION_TEXTURE2DMS instead of D3D11_DSV_DIMENSION_TEXTURE2D.`
- `0x1800499c9`: `A DepthStencilView cannot be created of a Resource that did not specify D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL.`
- `0x180049ac1`: `The D3D12_DSV_FLAG_READ_ONLY_STENCIL flag was set in the Flags field. This is not valid, because the format (%#x, %s) does not have a S component.`
- `0x180049a9a`: `The D3D12_DSV_FLAG_READ_ONLY_DEPTH flag was set in the Flags field. This is not valid, because the format (%#x, %s) does not have a D component.`

## pseudocode

```c
bool __fastcall CCreateDepthStencilViewValidator::Validate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6)
{
  int v6; // ebx
  __int64 v8; // r13
  int v9; // r11d
  __int64 v10; // r15
  __int64 v11; // r8
  __int64 v12; // rax
  enum DXGI_FORMAT v13; // edi
  int v14; // ecx
  int v15; // esi
  enum DXGI_FORMAT v16; // ebp
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  _DWORD *v20; // rax
  char v21; // r12
  int v22; // esi
  int v23; // esi
  __int64 v24; // rsi
  unsigned __int64 v25; // r8
  __int64 v26; // r9
  _DWORD *v27; // rcx
  _DWORD *v28; // rdx
  bool v29; // dl
  const char *Name; // rax
  const char *v31; // r8
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  bool v35; // dl
  bool v36; // dl
  const char *v37; // rax
  const char *v38; // r8
  bool v39; // dl
  const char *v40; // rax
  __int64 v41; // r8
  const char *v42; // r8
  bool v43; // dl
  __int64 v44; // r8
  bool v45; // dl
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rax
  bool v49; // dl
  __int64 v50; // r8
  const char *v51; // rax
  _DWORD *v52; // r15
  int v53; // r9d
  unsigned int v54; // eax
  unsigned int v55; // r10d
  int v56; // ecx
  int v57; // r9d
  unsigned int v58; // eax
  const char *v59; // r8
  __int64 v60; // rdx
  _DWORD *v61; // rcx
  _DWORD *v62; // rdx
  bool v63; // dl
  const char *v64; // rax
  const char *v65; // r8
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  bool v69; // dl
  bool v70; // dl
  const char *v71; // rax
  const char *v72; // r8
  bool v73; // dl
  const char *v74; // rax
  __int64 v75; // r8
  const char *v76; // r8
  bool v77; // dl
  __int64 v78; // r8
  bool v79; // dl
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // rax
  bool v83; // dl
  __int64 v84; // r8
  const char *v85; // rax
  int v86; // r9d
  unsigned int v87; // eax
  unsigned int v88; // r8d
  int v89; // ecx
  __int16 v90; // r11
  __int16 v91; // si
  __int64 i; // r10
  __int64 v93; // rcx
  unsigned int v94; // eax
  __int64 v95; // r10
  __int16 v96; // r11
  __int16 v97; // ax
  __int16 v98; // cx
  const char *v99; // rax
  __int64 v100; // r9
  char v101; // bp
  char v102; // r15
  unsigned int j; // esi
  int ComponentName; // eax
  bool v105; // dl
  const char *v106; // rax
  __int64 v108; // [rsp+20h] [rbp-C8h]
  const char *v109; // [rsp+20h] [rbp-C8h]
  __int64 v110; // [rsp+30h] [rbp-B8h]
  __int64 v111; // [rsp+30h] [rbp-B8h]
  unsigned int v112; // [rsp+50h] [rbp-98h]
  unsigned __int16 v113; // [rsp+54h] [rbp-94h]
  _DWORD v114[2]; // [rsp+58h] [rbp-90h]
  int v115; // [rsp+60h] [rbp-88h]
  _BYTE v116[56]; // [rsp+68h] [rbp-80h] BYREF

  v6 = 0;
  v8 = a2;
  v9 = 1;
  v10 = a2 & -(__int64)(a2 != 0);
  if ( *(int *)(a4 + 304) < 37120 )
  {
    v6 = 1;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      1157,
      "This operation is not supported on a core or generic device.");
    v9 = 1;
  }
  if ( a3 && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(*(enum DXGI_FORMAT *)a3) )
  {
    v6 += v9;
    TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 45, "The Format (%#x) is unrecognized.");
    return v6 == 0;
  }
  v11 = 2;
  if ( v8 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v8 + 80LL))(v8, v116, 2);
    v13 = DXGI_FORMAT_UNKNOWN;
    v11 = *(unsigned __int16 *)(v12 + 30);
    v9 = 1;
    LODWORD(a2) = *(_DWORD *)(v12 + 36);
    v14 = *(_DWORD *)(v12 + 48);
    v15 = *(_DWORD *)v12;
    v16 = *(_DWORD *)(v12 + 32);
    v112 = *(unsigned __int16 *)(v12 + 28);
    v113 = *(_WORD *)(v12 + 30);
    v114[0] = a2;
    v115 = v14;
    if ( !a3 )
      goto LABEL_30;
    v11 = 2;
LABEL_17:
    v13 = *(_DWORD *)a3;
    v20 = (_DWORD *)(a3 + 4);
    if ( (*(_DWORD *)(a3 + 4) != v9 || v15 != 2)
      && (*v20 != 3 || v15 != 3)
      && (*v20 != 4 || v15 != 3)
      && (*v20 != 5 || v15 != 3)
      && (*v20 != 6 || v15 != 3)
      && (*v20 != 2 || v15 != 2) )
    {
      v6 += v9;
      TDebugOutputFunctor::operator()(
        &g_coreRuntimeTallyErrorOutputFunctor,
        49,
        "The ViewDimension in the View Desc incompatible with the type of the Resource.");
      v9 = 1;
    }
LABEL_30:
    v21 = 0;
    v22 = v15 - 1;
    if ( !v22 )
      goto LABEL_169;
    v23 = v22 - 1;
    if ( v23 )
    {
      if ( v23 == 1 )
      {
        v24 = 0xFFFFFFFFLL;
        if ( !a3 )
        {
LABEL_34:
          v25 = (unsigned __int64)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail;
          v26 = 3072;
          if ( (unsigned int)v16 < 0xC0 )
            v24 = (unsigned int)v16;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v24 + 6) & 0xC00) == 0x800 )
          {
            v6 += v9;
            TDebugOutputFunctor::operator()(
              &g_coreRuntimeTallyErrorOutputFunctor,
              46,
              "A View cannot be created using a NULL Desc, when the Resource was created with a typeless Format. Default "
              "Desc parameters cannot be used, as a fully qualified Format must be supplied.",
              3072);
          }
          v13 = v16;
          goto LABEL_171;
        }
        if ( v13 != v16 )
        {
          if ( v10 )
          {
            v27 = *(_DWORD **)(v10 + 328);
            if ( v27 )
            {
              v28 = &v27[*(unsigned __int16 *)(v10 + 412)];
              while ( 1 )
              {
                if ( v27 == v28 )
                {
                  ++v6;
                  GetDebugObjectIdentifierString(v116, v28, v11);
                  Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v29);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    28,
                    "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was cre"
                    "ated with an explicit format cast list",
                    v13,
                    Name,
                    v31);
                  std::string::_Tidy_deallocate(v116);
                  goto LABEL_77;
                }
                if ( *v27 == v13 )
                  break;
                ++v27;
              }
              if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v16)
                && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v13) )
              {
                v21 = 1;
              }
              goto LABEL_77;
            }
          }
        }
        v32 = 0xFFFFFFFFLL;
        if ( (unsigned int)v16 < 0xC0 )
          v32 = (unsigned int)v16;
        if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v32 + 6) & 0xC00) == 0xC00 )
        {
          if ( v13 == DXGI_FORMAT_UNKNOWN )
          {
            v13 = v16;
LABEL_77:
            if ( (unsigned int)CD3D11FormatHelper::Texture2DSupport((unsigned int)v13, a5, (unsigned int)a6) == -1 )
            {
              ++v6;
              v51 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, a2);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                47,
                "The Format (%#x, %s) cannot be used, when creating a View of a Texture2D.",
                v13,
                v51);
            }
            v52 = (_DWORD *)(a3 + 4);
            if ( v8 )
            {
              switch ( *v52 )
              {
                case 4:
                  if ( v21 )
                  {
                    v53 = *(_DWORD *)(a3 + 20);
                    if ( v53 != 1 )
                    {
                      ++v6;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        48,
                        "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                        v53);
                    }
                  }
                  v26 = *(unsigned int *)(a3 + 12);
                  v25 = v112;
                  if ( (unsigned int)v26 >= v113
                    || (LODWORD(a2) = *(_DWORD *)(a3 + 16), (unsigned int)a2 >= (unsigned __int16)v112)
                    || (v54 = *(_DWORD *)(a3 + 20)) == 0
                    || v54 != -1 && (v54 > (unsigned __int16)v112 || (unsigned int)a2 + v54 > (unsigned __int16)v112) )
                  {
                    v55 = *(_DWORD *)(a3 + 16);
                    ++v6;
                    v56 = (unsigned __int16)v112;
                    if ( (unsigned __int16)v112 >= v55 )
                      v56 = *(_DWORD *)(a3 + 16);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      48,
                      "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice ("
                      "value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. FirstArra"
                      "ySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. W"
                      "ith the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or "
                      "-1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.",
                      v26,
                      v113 - 1,
                      v55,
                      (unsigned __int16)v112 - 1,
                      *(_DWORD *)(a3 + 20),
                      (unsigned __int16)v112 - v56);
                  }
                  break;
                case 6:
                  if ( v21 )
                  {
                    v57 = *(_DWORD *)(a3 + 16);
                    if ( v57 != 1 )
                    {
                      ++v6;
                      TDebugOutputFunctor::operator()(
                        &g_coreRuntimeTallyErrorOutputFunctor,
                        48,
                        "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                        v57);
                    }
                  }
                  v25 = v112;
                  v26 = *(unsigned int *)(a3 + 12);
                  LOBYTE(a2) = v112;
                  if ( (unsigned int)v26 >= (unsigned __int16)v112
                    || (v58 = *(_DWORD *)(a3 + 16)) == 0
                    || v58 != -1 && (v58 > (unsigned __int16)v112 || (unsigned int)v26 + v58 > (unsigned __int16)v112) )
                  {
                    ++v6;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      48,
                      "The Dimensions of the View are invalid due to at least one of the following conditions.  FirstArra"
                      "ySlice (value = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. W"
                      "ith the current FirstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or "
                      "-1 to default to all slices from FirstArraySlice, in order that the View fit on the Texture.");
                  }
                  break;
                case 3:
                  v26 = *(unsigned int *)(a3 + 12);
                  if ( (unsigned int)v26 >= v113 )
                  {
                    ++v6;
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      48,
                      "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice ("
                      "value = %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. ",
                      v26,
                      v113 - 1);
                  }
                  break;
              }
            }
            if ( v114[0] <= 1u )
              goto LABEL_171;
            if ( *v52 == 3 )
            {
              v59 = "The base resource was created as a multisample resource.  You must specify D3D11_DSV_DIMENSION_TEXTU"
                    "RE2DMS instead of D3D11_DSV_DIMENSION_TEXTURE2D.";
            }
            else
            {
              if ( *v52 != 4 )
                goto LABEL_171;
              v59 = "The base resource was created as a multisample resource.  You must specify D3D11_DSV_DIMENSION_TEXTU"
                    "RE2DMSARRAYinstead of D3D11_DSV_DIMENSION_TEXTURE2DARRAY.";
            }
            v60 = 46;
LABEL_170:
            ++v6;
            TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, v60, v59);
LABEL_171:
            v90 = 0;
            v114[0] = v13;
            v91 = 0;
            v114[1] = 0;
            for ( i = 0; i != -1; i = v95 + 1 )
            {
              v93 = (unsigned int)v114[i];
              if ( !(_DWORD)v93 )
                break;
              v94 = CD3D11FormatHelper::DepthStencilTargetSupport(v93, a5, (unsigned int)a6, v26);
              v25 = v94;
              if ( v94 == -2 )
              {
                v97 = 0;
                v98 = 1;
              }
              else
              {
                v97 = v94 == 1;
                v98 = 0;
              }
              v90 = v97 + v96;
              v91 += v98;
            }
            if ( !v90 && !v91 )
            {
              ++v6;
              v99 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, a2);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                47,
                "The format (%#x, %s) cannot be used with a DepthStencil view.",
                v13,
                v99);
            }
            if ( (v115 & 2) == 0 )
            {
              ++v6;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                49,
                "A DepthStencilView cannot be created of a Resource that did not specify D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL.",
                v26);
            }
            if ( a3 )
            {
              v100 = *(unsigned int *)(a3 + 8);
              if ( (v100 & 0xFFFFFFFC) != 0 )
              {
                ++v6;
                LODWORD(v108) = 3;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  276,
                  "There were unrecognized flags specified in the DepthStencilView Flags field. The flags value was %#x, "
                  "while the valid flags are limited to %#x.",
                  v100,
                  v108);
              }
              else if ( (v100 & 3) != 0 )
              {
                if ( (int)a5 >= 45056 )
                {
                  v101 = 0;
                  v102 = 0;
                  for ( j = 0; j < 4; ++j )
                  {
                    ComponentName = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetComponentName((unsigned int)v13, j, v25);
                    if ( ComponentName )
                    {
                      if ( ComponentName == 1 )
                        v102 = 1;
                    }
                    else
                    {
                      v101 = 1;
                    }
                  }
                  if ( (*(_BYTE *)(a3 + 8) & 1) != 0 && !v101 )
                  {
                    ++v6;
                    v106 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v105);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      276,
                      "The D3D12_DSV_FLAG_READ_ONLY_DEPTH flag was set in the Flags field. This is not valid, because the"
                      " format (%#x, %s) does not have a D component.",
                      v13,
                      v106);
                  }
                  if ( (*(_BYTE *)(a3 + 8) & 2) != 0 && !v102 )
                  {
                    ++v6;
                    v109 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v105);
                    TDebugOutputFunctor::operator()(
                      &g_coreRuntimeTallyErrorOutputFunctor,
                      276,
                      "The D3D12_DSV_FLAG_READ_ONLY_STENCIL flag was set in the Flags field. This is not valid, because t"
                      "he format (%#x, %s) does not have a S component.",
                      (unsigned int)v13,
                      v109);
                  }
                }
                else
                {
                  ++v6;
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    276,
                    "A non-zero Flags field (%#x) is not valid, unless the GetFeatureLevel returns D3D_FEATURE_LEVEL_11_0 or greater.");
                }
              }
            }
            return v6 == 0;
          }
          if ( v16 == v13 )
            goto LABEL_77;
          if ( a6 < 6 )
          {
            v6 += v9;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, a2);
            v40 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v43);
            v110 = v44;
            v42 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qu"
                  "alified Format, which is not castable (%#x, %s).";
          }
          else
          {
            if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v16 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v13 + 1) )
            {
              v33 = 0xFFFFFFFFLL;
              if ( (unsigned int)v13 < 0xC0 )
                v33 = (unsigned int)v13;
              if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v33 + 6) & 0xC00) != 0x800 )
              {
                v34 = 0xFFFFFFFFLL;
                if ( (unsigned int)v13 < 0xC0 )
                  v34 = (unsigned int)v13;
                if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v34 + 6) & 0xC00) == 0xC00
                  && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v13, v16) )
                {
                  ++v6;
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v35);
                  v37 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v36);
                  TDebugOutputFunctor::operator()(
                    &g_coreRuntimeTallyErrorOutputFunctor,
                    47,
                    "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation "
                    "- this type of format casting is not supported.",
                    v37,
                    v38);
                }
                goto LABEL_77;
              }
            }
            v6 += v9;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, 5 * v13);
            v40 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v39);
            v110 = v41;
            v42 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the sa"
                  "me family as the Format of the Resource (%#x, %s).";
          }
        }
        else
        {
          if ( v13 == DXGI_FORMAT_UNKNOWN )
          {
            v6 += v9;
            D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, a2);
            v40 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v45);
            v110 = v46;
            v47 = 0;
            v42 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the format"
                  " of the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_76:
            TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 47, v42, v47, v40, v16, v110);
            goto LABEL_77;
          }
          if ( v16 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v13 + 1) )
          {
            v48 = 0xFFFFFFFFLL;
            if ( (unsigned int)v13 < 0xC0 )
              v48 = (unsigned int)v13;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v48 + 6) & 0xC00) != 0x800 )
              goto LABEL_77;
          }
          v6 += v9;
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, a2);
          v40 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v49);
          v110 = v50;
          v42 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable from "
                "the Format of the Resource (%#x, %s).";
        }
        v47 = (unsigned int)v13;
        goto LABEL_76;
      }
LABEL_169:
      v59 = "A DepthStencilView cannot be created of a Buffer nor Texture3D Resource.";
      v60 = 49;
      goto LABEL_170;
    }
    v24 = 0xFFFFFFFFLL;
    if ( !a3 )
      goto LABEL_34;
    if ( v13 != v16 )
    {
      if ( v10 )
      {
        v61 = *(_DWORD **)(v10 + 328);
        if ( v61 )
        {
          v62 = &v61[*(unsigned __int16 *)(v10 + 412)];
          while ( 1 )
          {
            if ( v61 == v62 )
            {
              ++v6;
              GetDebugObjectIdentifierString(v116, v62, v11);
              v64 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v63);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                28,
                "The view format (%#x, %s) was not specified in the list of castable formats. The resource %s was created"
                " with an explicit format cast list",
                v13,
                v64,
                v65);
              std::string::_Tidy_deallocate(v116);
              goto LABEL_151;
            }
            if ( *v61 == v13 )
              break;
            ++v61;
          }
          if ( D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v16)
            && !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(v13) )
          {
            v21 = 1;
          }
          goto LABEL_151;
        }
      }
    }
    v66 = 0xFFFFFFFFLL;
    if ( (unsigned int)v16 < 0xC0 )
      v66 = (unsigned int)v16;
    if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v66 + 6) & 0xC00) == 0xC00 )
    {
      if ( v13 == DXGI_FORMAT_UNKNOWN )
      {
        v13 = v16;
LABEL_151:
        if ( (unsigned int)CD3D11FormatHelper::Texture1DSupport((unsigned int)v13, a5, (unsigned int)a6) == -1 )
        {
          ++v6;
          v85 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, a2);
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            47,
            "The Format (%#x, %s) cannot be used, when creating a View of a Texture1D.",
            v13,
            v85);
        }
        if ( v8 )
        {
          if ( *(_DWORD *)(a3 + 4) == 2 )
          {
            if ( v21 )
            {
              v86 = *(_DWORD *)(a3 + 20);
              if ( v86 != 1 )
              {
                ++v6;
                TDebugOutputFunctor::operator()(
                  &g_coreRuntimeTallyErrorOutputFunctor,
                  48,
                  "When casting from a compressed format to an uncompressed format, the ArraySize (value = %u) must be 1.",
                  v86);
              }
            }
            v26 = *(unsigned int *)(a3 + 12);
            v25 = v112;
            if ( (unsigned int)v26 >= v113
              || (LODWORD(a2) = *(_DWORD *)(a3 + 16), (unsigned int)a2 >= (unsigned __int16)v112)
              || (v87 = *(_DWORD *)(a3 + 20)) == 0
              || v87 != -1 && (v87 > (unsigned __int16)v112 || (unsigned int)a2 + v87 > (unsigned __int16)v112) )
            {
              ++v6;
              v88 = *(_DWORD *)(a3 + 16);
              v89 = (unsigned __int16)v112;
              if ( (unsigned __int16)v112 >= v88 )
                v89 = *(_DWORD *)(a3 + 16);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                48,
                "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice (value "
                "= %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. FirstArraySlice (valu"
                "e = %u) must be between 0 and ArraySize-1 of the Texture Resource, %hu, inclusively. With the current Fi"
                "rstArraySlice, ArraySize (value = %u) must be between 1 and %u, inclusively, or -1 to default to all sli"
                "ces from FirstArraySlice, in order that the View fit on the Texture.",
                v26,
                v113 - 1,
                v88,
                (unsigned __int16)v112 - 1,
                *(_DWORD *)(a3 + 20),
                (unsigned __int16)v112 - v89);
            }
          }
          else
          {
            v26 = *(unsigned int *)(a3 + 12);
            if ( (unsigned int)v26 >= v113 )
            {
              ++v6;
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                48,
                "The Dimensions of the View are invalid due to at least one of the following conditions. MipSlice (value "
                "= %u) must be between 0 and MipLevels-1 of the Texture Resource, %hu, inclusively. ",
                v26,
                v113 - 1);
            }
          }
        }
        goto LABEL_171;
      }
      if ( v16 == v13 )
        goto LABEL_151;
      if ( a6 < 6 )
      {
        v6 += v9;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, a2);
        v74 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v77);
        v111 = v78;
        v76 = "The Format (%#x, %s) is invalid when creating a View; the Resource was already created with a fully qualif"
              "ied Format, which is not castable (%#x, %s).";
      }
      else
      {
        if ( *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v16 + 1) == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
                                                                                                + 10 * v13
                                                                                                + 1) )
        {
          v67 = 0xFFFFFFFFLL;
          if ( (unsigned int)v13 < 0xC0 )
            v67 = (unsigned int)v13;
          if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v67 + 6) & 0xC00) != 0x800 )
          {
            v68 = 0xFFFFFFFFLL;
            if ( (unsigned int)v13 < 0xC0 )
              v68 = (unsigned int)v13;
            if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v68 + 6) & 0xC00) == 0xC00
              && D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(v13, v16) )
            {
              ++v6;
              D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v69);
              v71 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, v70);
              TDebugOutputFunctor::operator()(
                &g_coreRuntimeTallyErrorOutputFunctor,
                47,
                "The resource format (%s) and view format (%s) differ in float vs non-float component interpretation - th"
                "is type of format casting is not supported.",
                v71,
                v72);
            }
            goto LABEL_151;
          }
        }
        v6 += v9;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, 5 * v13);
        v74 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v73);
        v111 = v75;
        v76 = "The Format (%#x, %s) is invalid when creating a View; it is not a fully qualified format within the same f"
              "amily as the Format of the Resource (%#x, %s).";
      }
    }
    else
    {
      if ( v13 == DXGI_FORMAT_UNKNOWN )
      {
        v6 += v9;
        D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, a2);
        v74 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT_UNKNOWN, v79);
        v111 = v80;
        v81 = 0;
        v76 = "The Format (%#x, %s) is invalid when creating this View; using this format indicates to use the format of "
              "the Resource, however the Resource does not have a fully typed format: (%#x, %s).";
LABEL_150:
        TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 47, v76, v81, v74, v16, v111);
        goto LABEL_151;
      }
      if ( v16 == *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v13 + 1) )
      {
        v82 = 0xFFFFFFFFLL;
        if ( (unsigned int)v13 < 0xC0 )
          v82 = (unsigned int)v13;
        if ( (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v82 + 6) & 0xC00) != 0x800 )
          goto LABEL_151;
      }
      v6 += v9;
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v16, a2);
      v74 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v13, v83);
      v111 = v84;
      v76 = "The Format (%#x, %s) is invalid, when creating a View; it is not a fully qualified Format castable from the "
            "Format of the Resource (%#x, %s).";
    }
    v81 = (unsigned int)v13;
    goto LABEL_150;
  }
  if ( a3 )
  {
    v17 = *(_DWORD *)(a3 + 4);
    v112 = v9;
    v113 = v9;
    v114[0] = v9;
    v115 = 2;
    v18 = v17 - 1;
    if ( v18 && (v19 = v18 - 1) != 0 )
    {
      if ( (unsigned int)(v19 - 1) >= 2 )
        v114[0] = 2;
      v15 = 3;
    }
    else
    {
      v15 = 2;
    }
    v16 = *(_DWORD *)a3;
    goto LABEL_17;
  }
  TDebugOutputFunctor::operator()(
    &g_coreRuntimeTallyErrorOutputFunctor,
    49,
    "A DepthStencilView cannot be created from a NULL Resource and NULL Desc.");
  return 0;
}

```

## disassembly

```asm
0x180048e80  mov     [rsp+arg_0], rbx
0x180048e85  push    rbp
0x180048e86  push    rsi
0x180048e87  push    rdi
0x180048e88  push    r12
0x180048e8a  push    r13
0x180048e8c  push    r14
0x180048e8e  push    r15
0x180048e90  sub     rsp, 0B0h
0x180048e97  mov     rax, cs:__security_cookie
0x180048e9e  xor     rax, rsp
0x180048ea1  mov     [rsp+0E8h+var_48], rax
0x180048ea9  xor     ebx, ebx
0x180048eab  lea     r12, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180048eb2  mov     rax, rdx
0x180048eb5  mov     r14, r8
0x180048eb8  neg     rax
0x180048ebb  mov     r13, rdx
0x180048ebe  sbb     r15, r15
0x180048ec1  lea     r11d, [rbx+1]
0x180048ec5  and     r15, rdx
0x180048ec8  cmp     dword ptr [r9+130h], 9100h
0x180048ed3  jge     short loc_180048EF2
0x180048ed5  lea     r8, aThisOperationI; "This operation is not supported on a co"...
0x180048edc  mov     edx, 485h
0x180048ee1  mov     rcx, r12
0x180048ee4  mov     ebx, r11d
0x180048ee7  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180048eec  mov     r11d, 1
0x180048ef2  test    r14, r14
0x180048ef5  jz      short loc_180048F1D
0x180048ef7  mov     r9d, [r14]
0x180048efa  mov     ecx, r9d; enum DXGI_FORMAT
0x180048efd  call    ?FormatExists@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(DXGI_FORMAT)
0x180048f02  test    al, al
0x180048f04  jnz     short loc_180048F1D
0x180048f06  add     ebx, r11d
0x180048f09  lea     r8, aTheFormatXIsUn; "The Format (%#x) is unrecognized."
0x180048f10  mov     edx, 2Dh ; '-'
0x180048f15  mov     rcx, r12
0x180048f18  jmp     loc_180049A39
0x180048f1d  mov     r8d, 2
0x180048f23  test    r13, r13
0x180048f26  jz      short loc_180048F79
0x180048f28  mov     rax, [r13+0]
0x180048f2c  lea     rdx, [rsp+0E8h+var_80]
0x180048f31  mov     rcx, r13
0x180048f34  mov     rax, [rax+50h]
0x180048f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f3d  xor     edi, edi
0x180048f3f  movzx   r9d, word ptr [rax+1Ch]
0x180048f44  movzx   r8d, word ptr [rax+1Eh]
0x180048f49  lea     r11d, [rdi+1]
0x180048f4d  mov     edx, [rax+24h]
0x180048f50  mov     ecx, [rax+30h]
0x180048f53  mov     esi, [rax]
0x180048f55  mov     ebp, [rax+20h]
0x180048f58  mov     [rsp+0E8h+var_98], r9d
0x180048f5d  mov     [rsp+0E8h+var_94], r8d
0x180048f62  mov     [rsp+0E8h+var_90], edx
0x180048f66  mov     [rsp+0E8h+var_88], ecx
0x180048f6a  test    r14, r14
0x180048f6d  jz      loc_180049020
0x180048f73  lea     r8d, [rdi+2]
0x180048f77  jmp     short loc_180048FC0
0x180048f79  test    r14, r14
0x180048f7c  jz      loc_180049AE3
0x180048f82  mov     ecx, [r14+4]
0x180048f86  mov     [rsp+0E8h+var_98], r11d
0x180048f8b  mov     [rsp+0E8h+var_94], r11d
0x180048f90  mov     [rsp+0E8h+var_90], r11d
0x180048f95  mov     [rsp+0E8h+var_88], r8d
0x180048f9a  sub     ecx, 1
0x180048f9d  jz      short loc_180048FBA
0x180048f9f  sub     ecx, 1
0x180048fa2  jz      short loc_180048FBA
0x180048fa4  sub     ecx, 1
0x180048fa7  jz      short loc_180048FB3
0x180048fa9  sub     ecx, 1
0x180048fac  jz      short loc_180048FB3
0x180048fae  mov     [rsp+0E8h+var_90], r8d
0x180048fb3  mov     esi, 3
0x180048fb8  jmp     short loc_180048FBD
0x180048fba  mov     esi, r8d
0x180048fbd  mov     ebp, [r14]
0x180048fc0  mov     edi, [r14]
0x180048fc3  lea     rax, [r14+4]
0x180048fc7  cmp     [rax], r11d
0x180048fca  jnz     short loc_180048FD1
0x180048fcc  cmp     esi, r8d
0x180048fcf  jz      short loc_180049020
0x180048fd1  cmp     dword ptr [rax], 3
0x180048fd4  jnz     short loc_180048FDB
0x180048fd6  cmp     esi, 3
0x180048fd9  jz      short loc_180049020
0x180048fdb  cmp     dword ptr [rax], 4
0x180048fde  jnz     short loc_180048FE5
0x180048fe0  cmp     esi, 3
0x180048fe3  jz      short loc_180049020
0x180048fe5  cmp     dword ptr [rax], 5
0x180048fe8  jnz     short loc_180048FEF
0x180048fea  cmp     esi, 3
0x180048fed  jz      short loc_180049020
0x180048fef  cmp     dword ptr [rax], 6
0x180048ff2  jnz     short loc_180048FF9
0x180048ff4  cmp     esi, 3
0x180048ff7  jz      short loc_180049020
0x180048ff9  cmp     [rax], r8d
0x180048ffc  jnz     short loc_180049003
0x180048ffe  cmp     esi, r8d
0x180049001  jz      short loc_180049020
0x180049003  add     ebx, r11d
0x180049006  lea     r8, aTheViewdimensi_1; "The ViewDimension in the View Desc inco"...
0x18004900d  mov     edx, 31h ; '1'
0x180049012  mov     rcx, r12
0x180049015  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18004901a  mov     r11d, 1
0x180049020  xor     r12b, r12b
0x180049023  sub     esi, 1
0x180049026  jz      loc_180049912
0x18004902c  sub     esi, 1
0x18004902f  jz      loc_18004953C
0x180049035  cmp     esi, 1
0x180049038  jnz     loc_180049912
0x18004903e  or      esi, 0FFFFFFFFh
0x180049041  test    r14, r14
0x180049044  jnz     short loc_180049099
0x180049046  mov     r10d, 0C0h
0x18004904c  lea     r8, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180049053  cmp     ebp, r10d
0x180049056  mov     r9d, 0C00h
0x18004905c  cmovb   esi, ebp
0x18004905f  lea     rcx, [rsi+rsi*4]
0x180049063  mov     eax, [r8+rcx*8+18h]
0x180049068  and     eax, r9d
0x18004906b  cmp     eax, 800h
0x180049070  jnz     short loc_18004908D
0x180049072  add     ebx, r11d
0x180049075  lea     r8, aAViewCannotBeC; "A View cannot be created using a NULL D"...
0x18004907c  mov     edx, 2Eh ; '.'
0x180049081  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180049088  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18004908d  mov     edi, ebp
0x18004908f  mov     ebp, 1
0x180049094  jmp     loc_18004992F
0x180049099  cmp     edi, ebp
0x18004909b  jz      loc_180049159
0x1800490a1  test    r15, r15
0x1800490a4  jz      loc_180049159
0x1800490aa  mov     rcx, [r15+148h]
0x1800490b1  test    rcx, rcx
0x1800490b4  jz      loc_180049159
0x1800490ba  movzx   eax, word ptr [r15+19Ch]
0x1800490c2  lea     rdx, [rcx+rax*4]
0x1800490c6  jmp     short loc_1800490D0
0x1800490c8  cmp     [rcx], edi
0x1800490ca  jz      short loc_18004912E
0x1800490cc  add     rcx, 4
0x1800490d0  cmp     rcx, rdx
0x1800490d3  jnz     short loc_1800490C8
0x1800490d5  mov     ebp, 1
0x1800490da  lea     rcx, [rsp+0E8h+var_80]
0x1800490df  add     ebx, ebp
0x1800490e1  call    ?GetDebugObjectIdentifierString@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUID3D12DeviceChild@@@Z; GetDebugObjectIdentifierString(ID3D12DeviceChild *)
0x1800490e6  mov     r8, rax
0x1800490e9  cmp     qword ptr [rax+18h], 0Fh
0x1800490ee  jbe     short loc_1800490F3
0x1800490f0  mov     r8, [rax]
0x1800490f3  mov     ecx, edi; enum DXGI_FORMAT
0x1800490f5  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1800490fa  mov     [rsp+0E8h+var_C0], r8
0x1800490ff  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180049106  lea     r8, aTheViewFormatX; "The view format (%#x, %s) was not speci"...
0x18004910d  mov     [rsp+0E8h+var_C8], rax
0x180049112  mov     edx, 1Ch
0x180049117  mov     r9d, edi
0x18004911a  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18004911f  lea     rcx, [rsp+0E8h+var_80]
0x180049124  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180049129  jmp     loc_180049324
0x18004912e  mov     ecx, ebp; enum DXGI_FORMAT
0x180049130  call    ?IsBlockCompressFormat@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(DXGI_FORMAT)
0x180049135  test    al, al
0x180049137  jz      loc_18004931F
0x18004913d  mov     ecx, edi; enum DXGI_FORMAT
0x18004913f  call    ?IsBlockCompressFormat@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::IsBlockCompressFormat(DXGI_FORMAT)
0x180049144  mov     ebp, 1
0x180049149  test    al, al
0x18004914b  jnz     loc_180049324
0x180049151  mov     r12b, bpl
0x180049154  jmp     loc_180049324
0x180049159  mov     eax, esi
0x18004915b  lea     r8, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180049162  mov     r9d, 0C00h
0x180049168  mov     r10d, 0C0h
0x18004916e  cmp     ebp, r10d
0x180049171  cmovb   eax, ebp
0x180049174  lea     rax, [rax+rax*4]
0x180049178  mov     eax, [r8+rax*8+18h]
0x18004917d  and     eax, r9d
0x180049180  cmp     eax, r9d
0x180049183  jnz     loc_180049290
0x180049189  test    edi, edi
0x18004918b  jnz     short loc_180049194
0x18004918d  mov     edi, ebp
0x18004918f  jmp     loc_18004931F
0x180049194  cmp     ebp, edi
0x180049196  jz      loc_18004931F
0x18004919c  cmp     [rsp+0E8h+arg_28], 6
0x1800491a4  jl      loc_18004926E
0x1800491aa  movsxd  rax, edi
0x1800491ad  lea     rdx, [rax+rax*4]; bool
0x1800491b1  movsxd  rax, ebp
0x1800491b4  lea     rcx, [rax+rax*4]
0x1800491b8  mov     eax, [r8+rdx*8+4]
0x1800491bd  cmp     [r8+rcx*8+4], eax
0x1800491c2  jnz     loc_180049249
0x1800491c8  cmp     edi, r10d
0x1800491cb  mov     eax, esi
0x1800491cd  cmovb   eax, edi
0x1800491d0  lea     rcx, [rax+rax*4]
0x1800491d4  mov     eax, [r8+rcx*8+18h]
0x1800491d9  and     eax, r9d
0x1800491dc  cmp     eax, 800h
0x1800491e1  jz      short loc_180049249
0x1800491e3  cmp     edi, r10d
0x1800491e6  mov     eax, esi
0x1800491e8  cmovb   eax, edi
0x1800491eb  lea     rax, [rax+rax*4]
0x1800491ef  mov     eax, [r8+rax*8+18h]
0x1800491f4  and     eax, r9d
0x1800491f7  cmp     eax, r9d
0x1800491fa  jnz     loc_18004931F
0x180049200  mov     edx, ebp; enum DXGI_FORMAT
0x180049202  mov     ecx, edi; enum DXGI_FORMAT
0x180049204  call    ?FloatAndNotFloatFormats@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SA_NW4DXGI_FORMAT@@0@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FloatAndNotFloatFormats(DXGI_FORMAT,DXGI_FORMAT)
0x180049209  test    al, al
0x18004920b  jz      loc_18004931F
0x180049211  mov     ecx, edi; enum DXGI_FORMAT
0x180049213  inc     ebx
0x180049215  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18004921a  mov     ecx, ebp; enum DXGI_FORMAT
0x18004921c  mov     r8, rax
0x18004921f  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180049224  mov     [rsp+0E8h+var_C8], r8
0x180049229  lea     rcx, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x180049230  mov     r9, rax
0x180049233  lea     r8, aTheResourceFor; "The resource format (%s) and view forma"...
0x18004923a  mov     edx, 2Fh ; '/'
0x18004923f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180049244  jmp     loc_18004931F
0x180049249  mov     ecx, ebp; enum DXGI_FORMAT
0x18004924b  add     ebx, r11d
0x18004924e  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180049253  mov     ecx, edi; enum DXGI_FORMAT
0x180049255  mov     r8, rax
0x180049258  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18004925d  mov     [rsp+0E8h+var_B8], r8
0x180049262  lea     r8, aTheFormatXSIsI_0; "The Format (%#x, %s) is invalid when cr"...
0x180049269  jmp     loc_180049302
0x18004926e  mov     ecx, ebp; enum DXGI_FORMAT
0x180049270  add     ebx, r11d
0x180049273  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180049278  mov     ecx, edi; enum DXGI_FORMAT
0x18004927a  mov     r8, rax
0x18004927d  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180049282  mov     [rsp+0E8h+var_B8], r8
0x180049287  lea     r8, aTheFormatXSIsI_8; "The Format (%#x, %s) is invalid when cr"...
0x18004928e  jmp     short loc_180049302
0x180049290  test    edi, edi
0x180049292  jnz     short loc_1800492B9
0x180049294  mov     ecx, ebp; enum DXGI_FORMAT
0x180049296  add     ebx, r11d
0x180049299  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18004929e  xor     ecx, ecx; enum DXGI_FORMAT
0x1800492a0  mov     r8, rax
0x1800492a3  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1800492a8  mov     [rsp+0E8h+var_B8], r8
0x1800492ad  xor     r9d, r9d
0x1800492b0  lea     r8, aTheFormatXSIsI_3; "The Format (%#x, %s) is invalid when cr"...
0x1800492b7  jmp     short loc_180049305
0x1800492b9  movsxd  rax, edi
0x1800492bc  lea     rcx, [rax+rax*4]
0x1800492c0  cmp     ebp, [r8+rcx*8+4]
0x1800492c5  jnz     short loc_1800492E2
0x1800492c7  cmp     edi, r10d
0x1800492ca  mov     eax, esi
0x1800492cc  cmovb   eax, edi
0x1800492cf  lea     rcx, [rax+rax*4]
0x1800492d3  mov     eax, [r8+rcx*8+18h]
0x1800492d8  and     eax, r9d
0x1800492db  cmp     eax, 800h
0x1800492e0  jnz     short loc_18004931F
0x1800492e2  mov     ecx, ebp; enum DXGI_FORMAT
0x1800492e4  add     ebx, r11d
0x1800492e7  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1800492ec  mov     ecx, edi; enum DXGI_FORMAT
0x1800492ee  mov     r8, rax
0x1800492f1  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1800492f6  mov     [rsp+0E8h+var_B8], r8
  ... truncated ...
```
