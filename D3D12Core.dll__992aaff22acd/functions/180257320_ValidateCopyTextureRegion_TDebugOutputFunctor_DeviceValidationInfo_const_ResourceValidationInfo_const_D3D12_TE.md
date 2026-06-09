# ValidateCopyTextureRegion(TDebugOutputFunctor &,DeviceValidationInfo const &,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,uint,uint,uint,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,D3D12_BOX const * &,bool *)

- ea: `0x180257320`
- end: `0x180257d26`
- name: `?ValidateCopyTextureRegion@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUResourceValidationInfo@@AEBUD3D12_TEXTURE_COPY_LOCATION@@III23AEAPEBUD3D12_BOX@@PEA_N@Z`
- size: `2566`
- prototype: `__int64 __fastcall(struct TDebugOutputFunctor *, const struct DeviceValidationInfo *, const struct ResourceValidationInfo *, const struct D3D12_TEXTURE_COPY_LOCATION *, unsigned int, unsigned int, unsigned int, const struct ResourceValidationInfo *, const struct D3D12_TEXTURE_COPY_LOCATION *, const struct D3D12_BOX **, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18024bae0`

## callees

- `0x18002ef50`
- `0x1800abc10`
- `0x180257320`
- `0x180257d30`
- `0x180262020`

## string_xrefs

- `0x1802575d3`: `The source and destination resource formats are incompatible. The source format is %s and the destination format is %s. Some non-obvious formats are considered equivalent: BC[1|4] ~= R16G16B16A16|R32G32, BC[2|3|5|6|7] ~= R32G32B32A32, and R9G9B9E5_SHAREDEXP ~= R32.`
- `0x180257659`: `pSrcBox was empty, but probably was not intended. The resulting behavior is well-defined to result in no copy. The left, top, and front coordinates must be less then the corresponding right, bottom, and back coordinates to avoid specifying an empty box. left is %u, right is %u, top is %u, bottom is %u, front is %u, and back is %u.`
- `0x1802578cb`: `Resources with either DXGI_SAMPLE_DESC::Count greater than 1 or that use D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL can only copy the entire subresource at a time, where the subresource dimensions must match. The source subresource has %u height, %u width, %u depth, and %u samples. The destination subresource has %u height, %u width, %u depth, and %u samples.`
- `0x180257a66`: `Resources with either DXGI_SAMPLE_DESC::Count greater than 1 or that use D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL can only copy the entire subresource at a time, where the subresource dimensions must match. pSrcBox must be NULL, or specify the entire subresource. The source subresource %u samples. The destination subresource has %u samples. pSrcBox left is %u, top is %u, front is %u, and all must be 0; right is %u, bottom is %u, and back is %u. But, the source subresource has %u width, %u height,`
- `0x180260b7e`: `Hardware copy not supported. See D3D12_FEATURE_DATA_HARDWARE_COPY`
- `0x180257b2c`: `The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.`
- `0x180257c93`: `Resources with either DXGI_SAMPLE_DESC::Count greater than 1 or that use D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL can only copy the entire subresource at a time, where the subresource dimensions must match. DstX, DstY, and DstZ must be 0. The source subresource %u samples. The destination subresource has %u samples. DstX is %u, DstY is %u, and DstZ is %u.`
- `0x180257cdb`: `Source and Destination subresources cannot be the same when doing a copy operation. Copies with the same resource are allowed as long as the subresource indices are different Src and Dst subresources are both: %d`

## pseudocode

```c
__int64 __fastcall ValidateCopyTextureRegion(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        const struct ResourceValidationInfo *a3,
        const struct D3D12_TEXTURE_COPY_LOCATION *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        const struct ResourceValidationInfo *a8,
        const struct D3D12_TEXTURE_COPY_LOCATION *a9,
        const struct D3D12_BOX **a10,
        bool *a11)
{
  bool *v15; // r13
  __int64 result; // rax
  const struct ResourceValidationInfo *v17; // r14
  unsigned int v18; // r10d
  unsigned int v19; // r12d
  int v20; // r15d
  enum DXGI_FORMAT v21; // r9d
  __int64 v22; // rax
  unsigned int v23; // r11d
  __int64 v24; // rax
  unsigned int v25; // r8d
  unsigned int v26; // edx
  const struct D3D12_BOX **v27; // r11
  const struct D3D12_BOX *v28; // rcx
  enum DXGI_FORMAT v29; // r13d
  unsigned int v30; // edx
  __int64 v31; // rax
  __int64 v32; // rax
  const struct D3D12_BOX *v33; // rax
  unsigned int *p_bottom; // rcx
  unsigned int *p_top; // rax
  BOOL v36; // eax
  BOOL v37; // ecx
  int v38; // ecx
  BOOL v39; // eax
  int v40; // eax
  BOOL v41; // ecx
  int v42; // ecx
  int v43; // r14d
  BOOL v44; // eax
  int v45; // eax
  BOOL v46; // ecx
  bool v47; // dl
  const char *v48; // rax
  const char *v49; // r8
  int v50; // edx
  int v51; // edx
  unsigned int v52; // eax
  int v53; // ecx
  int v54; // r14d
  unsigned int *v55; // rax
  unsigned int v56; // ecx
  int v57; // ecx
  int v58; // eax
  int v59; // ecx
  unsigned int v60; // eax
  unsigned int v61; // eax
  const struct D3D12_BOX *v62; // rax
  const char *Name; // rax
  int v64; // r8d
  int v65; // r10d
  int v66; // r11d
  int v67; // ecx
  int v68; // eax
  int v69; // ecx
  unsigned int SubresourceIndex; // r9d
  const char *v71; // rax
  bool v72; // dl
  enum DXGI_FORMAT v73; // r9d
  const char *v74; // rax
  const char *v75; // r8
  int v76; // r10d
  int v77; // r11d
  unsigned int v78; // [rsp+90h] [rbp-80h]
  unsigned int v79; // [rsp+90h] [rbp-80h]
  unsigned int v80; // [rsp+90h] [rbp-80h]
  int v81; // [rsp+90h] [rbp-80h]
  unsigned int v82; // [rsp+94h] [rbp-7Ch]
  unsigned int v83; // [rsp+94h] [rbp-7Ch]
  unsigned int v84; // [rsp+94h] [rbp-7Ch]
  int v85; // [rsp+98h] [rbp-78h]
  int v86; // [rsp+9Ch] [rbp-74h]
  int v87; // [rsp+A0h] [rbp-70h]
  unsigned int v88; // [rsp+A4h] [rbp-6Ch]
  unsigned int v89; // [rsp+A4h] [rbp-6Ch]
  unsigned int left; // [rsp+A8h] [rbp-68h]
  unsigned int v91; // [rsp+A8h] [rbp-68h]
  unsigned int *v92; // [rsp+B0h] [rbp-60h]
  unsigned int v93; // [rsp+B0h] [rbp-60h]
  unsigned int v94; // [rsp+B8h] [rbp-58h]
  unsigned int *v95; // [rsp+C0h] [rbp-50h]
  unsigned int v96; // [rsp+C8h] [rbp-48h] BYREF
  __int64 v97; // [rsp+CCh] [rbp-44h]
  int v98; // [rsp+D4h] [rbp-3Ch]
  enum DXGI_FORMAT v99; // [rsp+D8h] [rbp-38h]
  int v100; // [rsp+DCh] [rbp-34h]
  int v101; // [rsp+E0h] [rbp-30h]
  unsigned int v102; // [rsp+E8h] [rbp-28h] BYREF
  unsigned int v103; // [rsp+ECh] [rbp-24h]
  unsigned int v104; // [rsp+F0h] [rbp-20h]
  int v105; // [rsp+F4h] [rbp-1Ch]
  enum DXGI_FORMAT v106; // [rsp+F8h] [rbp-18h]
  int v107; // [rsp+FCh] [rbp-14h]
  int v108; // [rsp+100h] [rbp-10h]
  unsigned int v109; // [rsp+108h] [rbp-8h]
  int *v110; // [rsp+110h] [rbp+0h]
  unsigned int v111; // [rsp+120h] [rbp+10h]
  int v112; // [rsp+124h] [rbp+14h] BYREF
  int v113; // [rsp+128h] [rbp+18h] BYREF
  unsigned int *p_right; // [rsp+130h] [rbp+20h]
  _DWORD *v115; // [rsp+138h] [rbp+28h]
  unsigned int v116; // [rsp+140h] [rbp+30h]
  unsigned int v117; // [rsp+144h] [rbp+34h] BYREF
  int v118; // [rsp+148h] [rbp+38h] BYREF
  __int64 v119; // [rsp+198h] [rbp+88h] BYREF
  const struct D3D12_TEXTURE_COPY_LOCATION *v120; // [rsp+1A8h] [rbp+98h]

  v120 = a4;
  if ( *((_DWORD *)a2 + 164) == 256 )
  {
    LODWORD(v119) = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(**((_QWORD **)a2 + 83) + 104LL))(
           *((_QWORD *)a2 + 83),
           52,
           &v119,
           4) < 0
      || !(_DWORD)v119 )
    {
      TDebugOutputFunctor::operator()(a1, 1381, "Hardware copy not supported. See D3D12_FEATURE_DATA_HARDWARE_COPY");
      return 2147942487LL;
    }
  }
  v15 = a11;
  *a11 = 0;
  result = ValidateTextureCopyLocation(
             a1,
             (struct ResourceCopyValidationInfo *)&v96,
             a2,
             a3,
             a4,
             (const struct TextureCopyLocationValidationIDs *)`ValidateCopyTextureRegion'::`2'::DstValidationIDs);
  if ( (int)result >= 0 )
  {
    v17 = a8;
    result = ValidateTextureCopyLocation(
               a1,
               (struct ResourceCopyValidationInfo *)&v102,
               a2,
               a8,
               a9,
               (const struct TextureCopyLocationValidationIDs *)`ValidateCopyTextureRegion'::`2'::SrcValidationIDs);
    if ( (int)result >= 0 )
    {
      if ( (*((_DWORD *)v17 + 3) & 0xF000000) == 0x3000000 )
      {
        TDebugOutputFunctor::operator()(a1, 862, "The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.");
        return 2147942487LL;
      }
      if ( (*((_DWORD *)a3 + 3) & 0xF000000) == 0x2000000 )
      {
        TDebugOutputFunctor::operator()(a1, 849, "The destination resource cannot be on a D3D12_HEAP_TYPE_UPLOAD heap.");
        return 2147942487LL;
      }
      v18 = a5;
      v110 = (int *)__PAIR64__(a6, a5);
      v19 = a6;
      v20 = v107;
      if ( v107 == v100 )
      {
        if ( v107 == 1 || (v68 = v108, v67 = v101, v108 == v101) )
        {
          v21 = v99;
          v22 = 0xFFFFFFFFLL;
          if ( (unsigned int)v99 < 0xC0 )
            v22 = (unsigned int)v99;
          v23 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v22 + 6) & 0xF;
          v94 = v23;
          v24 = 0xFFFFFFFFLL;
          if ( (unsigned int)v99 < 0xC0 )
            v24 = (unsigned int)v99;
          v25 = (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v24 + 6) >> 4) & 0xF;
          v26 = a5 % v23;
          if ( a5 % v23 || (v26 = a6 % v25) != 0 )
          {
            Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v99, v26);
            TDebugOutputFunctor::operator()(
              a1,
              872,
              "The destination coordinates are not aligned properly for the format used with the destination. When the fo"
              "rmat is %s, DstX must be a multiple of %u and DstY must be a multiple of %u. DstX is %u and DstY is %u.",
              Name,
              v66,
              v64,
              v65,
              v19);
            return 2147942487LL;
          }
          v27 = a10;
          v28 = *a10;
          if ( *a10 && (v28->right <= v28->left || v28->bottom <= v28->top || v28->back <= v28->front) )
          {
            *v15 = 1;
            TDebugOutputFunctor::operator()(
              a1,
              875,
              "pSrcBox was empty, but probably was not intended. The resulting behavior is well-defined to result in no c"
              "opy. The left, top, and front coordinates must be less then the corresponding right, bottom, and back coor"
              "dinates to avoid specifying an empty box. left is %u, right is %u, top is %u, bottom is %u, front is %u, and back is %u.",
              (*v27)->left,
              (*v27)->right,
              (*v27)->top,
              (*v27)->bottom,
              (*v27)->front,
              (*v27)->back);
            goto LABEL_47;
          }
          *v15 = 0;
          v29 = v106;
          v30 = -1;
          v31 = 0xFFFFFFFFLL;
          if ( (unsigned int)v106 < 0xC0 )
            v31 = (unsigned int)v106;
          v78 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v31 + 6) & 0xF;
          v32 = 0xFFFFFFFFLL;
          if ( (unsigned int)v106 < 0xC0 )
            v32 = (unsigned int)v106;
          v82 = (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v32 + 6) >> 4) & 0xF;
          v33 = *v27;
          p_right = &(*v27)->right;
          p_bottom = &v33->bottom;
          v95 = &v33->bottom;
          p_top = &v33->top;
          v92 = p_top;
          if ( !*v27 )
          {
            v95 = p_bottom;
            v18 = a5;
            goto LABEL_21;
          }
          left = (*v27)->left;
          LODWORD(v119) = *p_right;
          v51 = (left | (unsigned __int64)(unsigned int)v119) % v78;
          if ( v51 )
          {
            v95 = p_bottom;
          }
          else
          {
            v51 = (*p_bottom | (unsigned __int64)*p_top) % v82;
            if ( !v51 )
            {
              v30 = -1;
LABEL_21:
              if ( v21 != v106 )
              {
                v36 = v106 == DXGI_FORMAT_R32_TYPELESS && v98 == 67;
                v37 = v21 == DXGI_FORMAT_R32_TYPELESS && v105 == 67;
                v38 = v36 || v37;
                v39 = (v106 == DXGI_FORMAT_R16G16B16A16_TYPELESS || v106 == DXGI_FORMAT_R32G32_TYPELESS)
                   && (v21 == DXGI_FORMAT_BC1_TYPELESS || v21 == DXGI_FORMAT_BC4_TYPELESS);
                v40 = v38 | v39;
                v41 = (v21 == DXGI_FORMAT_R16G16B16A16_TYPELESS || v21 == DXGI_FORMAT_R32G32_TYPELESS)
                   && (v106 == DXGI_FORMAT_BC1_TYPELESS || v106 == DXGI_FORMAT_BC4_TYPELESS);
                v42 = v40 | v41;
                v44 = 0;
                if ( v106 == DXGI_FORMAT_R32G32B32A32_TYPELESS && (unsigned int)(v21 - 73) <= 0x18 )
                {
                  v43 = 18874889;
                  if ( _bittest(&v43, v21 - 73) )
                    v44 = 1;
                }
                v45 = v42 | v44;
                v46 = 0;
                if ( v21 == DXGI_FORMAT_R32G32B32A32_TYPELESS && (unsigned int)(v106 - 73) <= 0x18 )
                {
                  v69 = 18874889;
                  v19 = a6;
                  if ( _bittest(&v69, v106 - 73) )
                    v46 = 1;
                }
                if ( !(v45 | v46) )
                {
                  D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v21, -1);
                  v48 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v29, v47);
                  TDebugOutputFunctor::operator()(
                    a1,
                    874,
                    "The source and destination resource formats are incompatible. The source format is %s and the destin"
                    "ation format is %s. Some non-obvious formats are considered equivalent: BC[1|4] ~= R16G16B16A16|R32G"
                    "32, BC[2|3|5|6|7] ~= R32G32B32A32, and R9G9B9E5_SHAREDEXP ~= R32.",
                    v48,
                    v49);
                  return 2147942487LL;
                }
                p_bottom = &(*v27)->bottom;
                v95 = p_bottom;
                p_top = &(*v27)->top;
              }
              if ( *v27 )
              {
                v87 = (*v27)->right - (*v27)->left;
                v53 = *p_bottom - *p_top;
                v54 = (*v27)->back - (*v27)->front;
                v20 = v107;
                v52 = v87;
              }
              else
              {
                v52 = v102;
                v87 = v102;
                v53 = v103;
                v54 = v104;
              }
              v85 = v54;
              v17 = a8;
              v86 = v53;
              v111 = v52;
              v112 = v53;
              v113 = v85;
              if ( v21 == v106 )
              {
                v79 = v52;
                v110 = &v113;
                v55 = (unsigned int *)&v112;
              }
              else
              {
                if ( v78 < v94 )
                {
                  v83 = (v18 + v94 - 1) / v94;
                  v88 = (v25 + HIDWORD(v110) - 1) / v25;
                  v109 = (v94 + v96 - 1) / v94;
                  v93 = (v25 + (_DWORD)v97 - 1) / v25;
                  v110 = &v113;
                  v115 = &v112;
                  LOBYTE(v119) = 1;
                  v56 = HIDWORD(v97);
                  v79 = v87;
                  v30 = -1;
LABEL_61:
                  v91 = v56;
                  v57 = -1;
                  if ( v79 + v83 >= v83 )
                    v57 = v79 + v83;
                  v84 = v57;
                  v58 = -1;
                  if ( *v115 + v88 >= v88 )
                    v58 = *v115 + v88;
                  v80 = v58;
                  if ( *v110 + a7 >= a7 )
                    v30 = *v110 + a7;
                  v89 = v30;
                  v59 = v58;
                  if ( v84 > v109 )
                    goto LABEL_133;
                  v60 = v93;
                  if ( !(_BYTE)v119 )
                    v60 = v97;
                  if ( v80 > v60 )
                    goto LABEL_133;
                  v61 = v91;
                  if ( !(_BYTE)v119 )
                    v61 = HIDWORD(v97);
                  if ( v30 > v61 )
                  {
LABEL_133:
                    if ( (_BYTE)v119 )
                      v59 = v25 * v80;
                    v81 = v59;
                    D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v106, v30);
                    v74 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v73, v72);
                    TDebugOutputFunctor::operator()(
                      a1,
                      858,
                      "The destination region extends past, at least, one of the edges of the destination subresource. Wh"
                      "en the destination format is %s, the source format is %s, DstX is %u, DstY is %u, DstZ is %u and t"
                      "he effective SrcBox width is %u, height is %u, and depth is %u, the operation requires the destina"
                      "tion subresource to have %u width, %u height, and %u depth. But the destination subresource only h"
                      "as %u width, %u height, and %u depth.",
                      v74,
                      v75,
                      v76,
                      v19,
                      a7,
                      v87,
                      v86,
                      v85,
                      v77,
                      v81,
                      v89,
                      v96,
                      v97,
                      HIDWORD(v97));
                    return 2147942487LL;
                  }
                  v62 = *v27;
                  if ( *v27 && (*p_right > v102 || *v95 > v103 || v62->back > v104) )
                  {
                    TDebugOutputFunctor::operator()(
                      a1,
                      871,
                      "The source box extends past, at least, one the edges of the source subresource. pSrcBox right is %"
                      "u, bottom is %u, and back is %u. But, the source subresource only has %u width, %u height, and %u depth.",
                      *p_right,
                      *v95,
                      v62->back,
                      v102,
                      v103,
                      v104);
                  }
                  else
                  {
                    if ( v102 == v87 && v103 == v86 && v104 == v85 )
                      *v27 = 0;
                    v119 = 0;
                    (*(void (__fastcall **)(_QWORD, __int64, __int64 *, __int64))(**((_QWORD **)a2 + 83) + 104LL))(
                      *((_QWORD *)a2 + 83),
                      18,
                      &v119,
                      8);
                    if ( HIDWORD(v119)
                      || (*((_BYTE *)a3 + 32) & 2) == 0 && v100 == 1 && (*((_BYTE *)v17 + 32) & 2) == 0 && v20 == 1 )
                    {
LABEL_47:
                      if ( a9->pResource == v120->pResource
                        && a9->Type == D3D12_TEXTURE_COPY_TYPE_SUBRESOURCE_INDEX
                        && v120->Type == D3D12_TEXTURE_COPY_TYPE_SUBRESOURCE_INDEX )
                      {
                        SubresourceIndex = a9->SubresourceIndex;
                        if ( SubresourceIndex == v120->SubresourceIndex && !*((_DWORD *)a2 + 221) )
                          TDebugOutputFunctor::operator()(
                            a1,
                            998,
                            "Source and Destination subresources cannot be the same when doing a copy operation. Copies w"
                            "ith the same resource are allowed as long as the subresource indices are different Src and D"
                            "st subresources are both: %d",
                            SubresourceIndex);
                      }
                      v50 = *((_DWORD *)a3 + 8);
                      if ( (((unsigned __int8)v50 ^ *((_BYTE *)v17 + 32)) & 0x40) != 0 )
                      {
                        TDebugOutputFunctor::operator()(
                          a1,
                          1097,
                          "If the source resource D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFEREN"
                          "CE_ONLY set, the destination resource D3D12_RESOURCE_DESC::Flags must also have D3D12_RESOURCE"
                          "_FLAG_VIDEO_DECODE_REFERENCE_ONLY set, and vice versa.");
                      }
                      else
                      {
                        if ( ((v50 ^ *((_DWORD *)v17 + 8)) & 0x80u) == 0 )
                          return 0;
                        TDebugOutputFunctor::operator()(
                          a1,
                          1303,
                          "If the source resource D3D12_RESOURCE_DESC::Flags has D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFEREN"
                          "CE_ONLY set, the destination resource D3D12_RESOURCE_DESC::Flags must also have D3D12_RESOURCE"
                          "_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set, and vice versa.");
                      }
                      return 2147942487LL;
                    }
                    if ( v87 == v96 && __PAIR64__(v85, v86) == v97 )
                    {
                      if ( a5 || v19 || a7 )
                      {
                        TDebugOutputFunctor::operator()(
                          a1,
                          872,
                          "Resources with either DXGI_SAMPLE_DESC::Count greater than 1 or that use D3D12_RESOURCE_FLAG_A"
                          "LLOW_DEPTH_STENCIL can only copy the entire subresource at a time, where the subresource dimen"
                          "sions must match. DstX, DstY, and DstZ must be 0. The source subresource %u samples. The desti"
                          "nation subresource has %u samples. DstX is %u, DstY is %u, and DstZ is %u.",
                          v20,
                          v100,
                          a5,
                          v19,
                          a7);
                      }
                      else
                      {
                        if ( !*a10 )
                          goto LABEL_47;
                        TDebugOutputFunctor::operator()(
                          a1,
                          873,
                          "Resources with either DXGI_SAMPLE_DESC::Count greater than 1 or that use D3D12_RESOURCE_FLAG_A"
                          "LLOW_DEPTH_STENCIL can only copy the entire subresource at a time, where the subresource dimen"
                          "sions must match. pSrcBox must be NULL, or specify the entire subresource. The source subresou"
                          "rce %u samples. The destination subresource has %u samples. pSrcBox left is %u, top is %u, fro"
                          "nt is %u, and all must be 0; right is %u, bottom is %u, and back is %u. But, the source subres"
                          "ource has %u width, %u height, and %u depth.",
                          v20,
                          v100,
                          (*a10)->left,
                          (*a10)->top,
                          (*a10)->front,
                          (*a10)->right,
                          (*a10)->bottom,
                          (*a10)->back,
                          v102,
                          v103,
                          v104);
                      }
                    }
                    else
                    {
                      TDebugOutputFunctor::operator()(
                        a1,
                        862,
                        "Resources with either DXGI_SAMPLE_DESC::Count greater than 1 or that use D3D12_RESOURCE_FLAG_ALL"
                        "OW_DEPTH_STENCIL can only copy the entire subresource at a time, where the subresource dimension"
                        "s must match. The source subresource has %u height, %u width, %u depth, and %u samples. The dest"
                        "ination subresource has %u height, %u width, %u depth, and %u samples.",
                        v87,
                        v86,
                        v85,
                        v20,
                        v96,
                        v97,
                        HIDWORD(v97),
                        v100);
                    }
                  }
                  return 2147942487LL;
                }
                v118 = v85;
                v79 = (v78 + v52 - 1) / v78;
                v116 = v79;
                v117 = (v53 + v82 - 1) / v82;
                v110 = &v118;
                v55 = &v117;
                v30 = -1;
              }
              LOBYTE(v119) = 0;
              v115 = v55;
              v83 = v18;
              v109 = v96;
              v88 = v19;
              v93 = v119;
              v56 = v119;
              goto LABEL_61;
            }
          }
          v71 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v106, v51);
          TDebugOutputFunctor::operator()(
            a1,
            873,
            "The coordinates in pSrcBox are not aligned properly for the format used with the source. When the format is "
            "%s, left & right must be a multiple of %u and top & bottom must be a multiple of %u. left is %u, right is %u"
            ", top is %u, and bottom is %u.",
            v71,
            v78,
            v82,
            left,
            v119,
            *v92,
            *v95);
          return 2147942487LL;
        }
      }
      else
      {
        v67 = v101;
        v68 = v108;
      }
      TDebugOutputFunctor::operator()(
        a1,
        849,
        "The destination resource multisampling properties must equal the source resource. The destination resource has %"
        "u samples and %u quality. The source resource has %u samples and %u quality. ",
        v100,
        v67,
        v107,
        v68);
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180257320  mov     [rsp-8+arg_0], rbx
0x180257325  mov     [rsp-8+arg_18], r9
0x18025732a  push    rbp
0x18025732b  push    rsi
0x18025732c  push    rdi
0x18025732d  push    r12
0x18025732f  push    r13
0x180257331  push    r14
0x180257333  push    r15
0x180257335  lea     rbp, [rsp-40h]
0x18025733a  sub     rsp, 150h
0x180257341  mov     r14, r9
0x180257344  mov     rdi, r8
0x180257347  mov     rbx, rdx
0x18025734a  mov     rsi, rcx
0x18025734d  cmp     dword ptr [rdx+290h], 100h
0x180257357  jz      loc_180257AE3
0x18025735d  mov     r13, [rbp+70h+arg_50]
0x180257364  mov     byte ptr [r13+0], 0
0x180257369  lea     rax, ?DstValidationIDs@?1??ValidateCopyTextureRegion@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUResourceValidationInfo@@AEBUD3D12_TEXTURE_COPY_LOCATION@@III23AEAPEBUD3D12_BOX@@PEA_N@Z@4UTextureCopyLocationValidationIDs@@B; TextureCopyLocationValidationIDs const `ValidateCopyTextureRegion(TDebugOutputFunctor &,DeviceValidationInfo const &,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,uint,uint,uint,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,D3D12_BOX const * &,bool *)'::`2'::DstValidationIDs
0x180257370  mov     [rsp+180h+var_158], rax; struct TextureCopyLocationValidationIDs *
0x180257375  mov     [rsp+180h+var_160], r14; const struct D3D12_TEXTURE_COPY_LOCATION *
0x18025737a  mov     r9, rdi; struct ResourceValidationInfo *
0x18025737d  mov     r8, rbx; struct DeviceValidationInfo *
0x180257380  lea     rdx, [rbp+70h+var_B8]; struct ResourceCopyValidationInfo *
0x180257384  mov     rcx, rsi; struct TDebugOutputFunctor *
0x180257387  call    ?ValidateTextureCopyLocation@@YAJAEAUTDebugOutputFunctor@@AEAUResourceCopyValidationInfo@@AEBUDeviceValidationInfo@@AEBUResourceValidationInfo@@AEBUD3D12_TEXTURE_COPY_LOCATION@@AEBUTextureCopyLocationValidationIDs@@@Z; ValidateTextureCopyLocation(TDebugOutputFunctor &,ResourceCopyValidationInfo &,DeviceValidationInfo const &,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,TextureCopyLocationValidationIDs const &)
0x18025738c  test    eax, eax
0x18025738e  js      loc_1802575EC
0x180257394  lea     rax, ?SrcValidationIDs@?1??ValidateCopyTextureRegion@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUResourceValidationInfo@@AEBUD3D12_TEXTURE_COPY_LOCATION@@III23AEAPEBUD3D12_BOX@@PEA_N@Z@4UTextureCopyLocationValidationIDs@@B; TextureCopyLocationValidationIDs const `ValidateCopyTextureRegion(TDebugOutputFunctor &,DeviceValidationInfo const &,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,uint,uint,uint,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,D3D12_BOX const * &,bool *)'::`2'::SrcValidationIDs
0x18025739b  mov     [rsp+180h+var_158], rax; struct TextureCopyLocationValidationIDs *
0x1802573a0  mov     rax, [rbp+70h+arg_40]
0x1802573a7  mov     [rsp+180h+var_160], rax; const struct D3D12_TEXTURE_COPY_LOCATION *
0x1802573ac  mov     r14, [rbp+70h+arg_38]
0x1802573b3  mov     r9, r14; struct ResourceValidationInfo *
0x1802573b6  mov     r8, rbx; struct DeviceValidationInfo *
0x1802573b9  lea     rdx, [rbp+70h+var_98]; struct ResourceCopyValidationInfo *
0x1802573bd  mov     rcx, rsi; struct TDebugOutputFunctor *
0x1802573c0  call    ?ValidateTextureCopyLocation@@YAJAEAUTDebugOutputFunctor@@AEAUResourceCopyValidationInfo@@AEBUDeviceValidationInfo@@AEBUResourceValidationInfo@@AEBUD3D12_TEXTURE_COPY_LOCATION@@AEBUTextureCopyLocationValidationIDs@@@Z; ValidateTextureCopyLocation(TDebugOutputFunctor &,ResourceCopyValidationInfo &,DeviceValidationInfo const &,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,TextureCopyLocationValidationIDs const &)
0x1802573c5  test    eax, eax
0x1802573c7  js      loc_1802575EC
0x1802573cd  mov     eax, [r14+0Ch]
0x1802573d1  and     eax, 0F000000h
0x1802573d6  cmp     eax, 3000000h
0x1802573db  jz      loc_180257B2C
0x1802573e1  mov     eax, [rdi+0Ch]
0x1802573e4  and     eax, 0F000000h
0x1802573e9  cmp     eax, 2000000h
0x1802573ee  jz      loc_180257B45
0x1802573f4  mov     r10d, [rbp+70h+arg_20]
0x1802573fb  mov     dword ptr [rbp+70h+var_70], r10d
0x1802573ff  mov     r12d, [rbp+70h+arg_28]
0x180257406  mov     dword ptr [rbp+70h+var_70+4], r12d
0x18025740a  mov     r15d, [rbp+70h+var_84]
0x18025740e  mov     r9d, [rbp+70h+var_A4]
0x180257412  cmp     r15d, r9d
0x180257415  jnz     loc_180257AB7
0x18025741b  cmp     r15d, 1
0x18025741f  jnz     loc_180257B5E
0x180257425  mov     r9d, [rbp+70h+var_A8]
0x180257429  mov     edx, 0FFFFFFFFh
0x18025742e  mov     eax, edx
0x180257430  cmp     r9d, 0C0h
0x180257437  cmovb   eax, r9d
0x18025743b  lea     rcx, [rax+rax*4]
0x18025743f  lea     r8, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180257446  mov     r11d, [r8+rcx*8+18h]
0x18025744b  and     r11d, 0Fh
0x18025744f  mov     [rbp+70h+var_C8], r11d
0x180257453  mov     eax, edx
0x180257455  cmp     r9d, 0C0h
0x18025745c  cmovb   eax, r9d
0x180257460  lea     rcx, [rax+rax*4]
0x180257464  mov     r8d, [r8+rcx*8+18h]
0x180257469  shr     r8d, 4
0x18025746d  and     r8d, 0Fh
0x180257471  xor     edx, edx; bool
0x180257473  mov     eax, r10d
0x180257476  div     r11d
0x180257479  test    edx, edx
0x18025747b  jnz     loc_180257A7F
0x180257481  xor     edx, edx
0x180257483  mov     eax, r12d
0x180257486  div     r8d
0x180257489  test    edx, edx
0x18025748b  jnz     loc_180257A7F
0x180257491  mov     r11, [rbp+70h+arg_48]
0x180257498  mov     rcx, [r11]
0x18025749b  test    rcx, rcx
0x18025749e  jnz     loc_18025760B
0x1802574a4  mov     byte ptr [r13+0], 0
0x1802574a9  mov     r13d, [rbp+70h+var_88]
0x1802574ad  mov     edx, 0FFFFFFFFh; bool
0x1802574b2  mov     eax, edx
0x1802574b4  cmp     r13d, 0C0h
0x1802574bb  cmovb   eax, r13d
0x1802574bf  lea     rcx, [rax+rax*4]
0x1802574c3  lea     rax, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x1802574ca  mov     eax, [rax+rcx*8+18h]
0x1802574ce  and     eax, 0Fh
0x1802574d1  mov     [rbp+70h+var_F0], eax
0x1802574d4  mov     eax, edx
0x1802574d6  cmp     r13d, 0C0h
0x1802574dd  cmovb   eax, r13d
0x1802574e1  lea     rcx, [rax+rax*4]
0x1802574e5  lea     rax, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x1802574ec  mov     eax, [rax+rcx*8+18h]
0x1802574f0  shr     eax, 4
0x1802574f3  and     eax, 0Fh
0x1802574f6  mov     [rbp+70h+var_EC], eax
0x1802574f9  mov     rax, [r11]
0x1802574fc  lea     rcx, [rax+0Ch]
0x180257500  mov     [rbp+70h+var_50], rcx
0x180257504  lea     rcx, [rax+10h]
0x180257508  mov     [rbp+70h+var_C0], rcx
0x18025750c  add     rax, 4
0x180257510  mov     [rbp+70h+var_D0], rax
0x180257514  cmp     qword ptr [r11], 0
0x180257518  jnz     loc_1802576BF
0x18025751e  mov     r10, [rbp+70h+var_50]
0x180257522  mov     [rbp+70h+var_50], r10
0x180257526  mov     [rbp+70h+var_C0], rcx
0x18025752a  mov     r10d, [rbp+70h+arg_20]
0x180257531  cmp     r9d, r13d
0x180257534  jz      loc_180257705
0x18025753a  cmp     r13d, 27h ; '''
0x18025753e  jz      loc_180257B7E
0x180257544  xor     eax, eax
0x180257546  cmp     r9d, 27h ; '''
0x18025754a  jz      loc_180257B92
0x180257550  xor     ecx, ecx
0x180257552  or      ecx, eax
0x180257554  cmp     r13d, 9
0x180257558  jz      loc_1802576AB
0x18025755e  cmp     r13d, 0Fh
0x180257562  jz      loc_1802576AB
0x180257568  xor     eax, eax
0x18025756a  or      eax, ecx
0x18025756c  cmp     r9d, 9
0x180257570  jz      loc_180257BA6
0x180257576  cmp     r9d, 0Fh
0x18025757a  jz      loc_180257BA6
0x180257580  xor     ecx, ecx
0x180257582  or      ecx, eax
0x180257584  cmp     r13d, 1
0x180257588  jnz     short loc_180257607
0x18025758a  lea     eax, [r9-49h]
0x18025758e  cmp     eax, 18h
0x180257591  ja      short loc_180257607
0x180257593  mov     r14d, 1200209h
0x180257599  bt      r14d, eax
0x18025759d  jnb     short loc_180257607
0x18025759f  mov     eax, r13d
0x1802575a2  or      eax, ecx
0x1802575a4  cmp     r9d, 1
0x1802575a8  jz      loc_180257BBF
0x1802575ae  xor     ecx, ecx
0x1802575b0  or      ecx, eax
0x1802575b2  jnz     loc_180257BF0
0x1802575b8  mov     ecx, r9d; enum DXGI_FORMAT
0x1802575bb  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1802575c0  mov     r8, rax
0x1802575c3  mov     ecx, r13d; enum DXGI_FORMAT
0x1802575c6  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1802575cb  mov     r9, rax
0x1802575ce  mov     [rsp+180h+var_160], r8
0x1802575d3  lea     r8, aTheSourceAndDe; "The source and destination resource for"...
0x1802575da  mov     edx, 36Ah
0x1802575df  mov     rcx, rsi
0x1802575e2  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802575e7  mov     eax, 80070057h
0x1802575ec  mov     rbx, [rsp+180h+arg_0]
0x1802575f4  add     rsp, 150h
0x1802575fb  pop     r15
0x1802575fd  pop     r14
0x1802575ff  pop     r13
0x180257601  pop     r12
0x180257603  pop     rdi
0x180257604  pop     rsi
0x180257605  pop     rbp
0x180257606  retn
0x180257607  xor     eax, eax
0x180257609  jmp     short loc_1802575A2
0x18025760b  mov     eax, [rcx]
0x18025760d  cmp     [rcx+0Ch], eax
0x180257610  jbe     short loc_180257626
0x180257612  mov     eax, [rcx+4]
0x180257615  cmp     [rcx+10h], eax
0x180257618  jbe     short loc_180257626
0x18025761a  mov     eax, [rcx+8]
0x18025761d  cmp     [rcx+14h], eax
0x180257620  ja      loc_1802574A4
0x180257626  mov     byte ptr [r13+0], 1
0x18025762b  mov     r9, [r11]
0x18025762e  mov     eax, [r9+14h]
0x180257632  mov     [rsp+180h+var_140], eax
0x180257636  mov     eax, [r9+8]
0x18025763a  mov     [rsp+180h+var_148], eax
0x18025763e  mov     eax, [r9+10h]
0x180257642  mov     [rsp+180h+var_150], eax
0x180257646  mov     eax, [r9+4]
0x18025764a  mov     dword ptr [rsp+180h+var_158], eax
0x18025764e  mov     eax, [r9+0Ch]
0x180257652  mov     dword ptr [rsp+180h+var_160], eax
0x180257656  mov     r9d, [r9]
0x180257659  lea     r8, aPsrcboxWasEmpt; "pSrcBox was empty, but probably was not"...
0x180257660  mov     edx, 36Bh
0x180257665  mov     rcx, rsi
0x180257668  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18025766d  mov     rcx, [rbp+70h+arg_18]
0x180257674  mov     rax, [rcx]
0x180257677  mov     rdx, [rbp+70h+arg_40]
0x18025767e  cmp     [rdx], rax
0x180257681  jz      loc_180257CAC
0x180257687  mov     edx, [rdi+20h]
0x18025768a  mov     ecx, [r14+20h]
0x18025768e  mov     eax, ecx
0x180257690  xor     eax, edx
0x180257692  test    al, 40h
0x180257694  jnz     loc_180257998
0x18025769a  xor     ecx, edx
0x18025769c  test    cl, cl
0x18025769e  js      loc_180257CF4
0x1802576a4  xor     eax, eax
0x1802576a6  jmp     loc_1802575EC
0x1802576ab  cmp     r9d, 46h ; 'F'
0x1802576af  jnz     loc_180257989
0x1802576b5  mov     eax, 1
0x1802576ba  jmp     loc_18025756A
0x1802576bf  mov     rax, [r11]
0x1802576c2  mov     edx, [rax]
0x1802576c4  mov     [rbp+70h+var_D8], edx
0x1802576c7  mov     rax, [rbp+70h+var_50]
0x1802576cb  mov     eax, [rax]
0x1802576cd  mov     dword ptr [rbp+70h+arg_8], eax
0x1802576d3  or      eax, edx
0x1802576d5  xor     edx, edx
0x1802576d7  div     [rbp+70h+var_F0]
0x1802576da  mov     rax, [rbp+70h+var_D0]
0x1802576de  test    edx, edx
0x1802576e0  jnz     loc_180257B71
0x1802576e6  mov     eax, [rax]
0x1802576e8  or      eax, [rcx]
0x1802576ea  xor     edx, edx; bool
0x1802576ec  div     [rbp+70h+var_EC]
0x1802576ef  test    edx, edx
0x1802576f1  jnz     loc_180260B98
0x1802576f7  mov     edx, 0FFFFFFFFh
0x1802576fc  mov     rax, [rbp+70h+var_D0]
0x180257700  jmp     loc_180257531
0x180257705  cmp     qword ptr [r11], 0
0x180257709  jnz     loc_1802578E4
0x18025770f  mov     eax, [rbp+70h+var_98]
0x180257712  mov     [rbp+70h+var_E0], eax
0x180257715  mov     ecx, [rbp+70h+var_94]
0x180257718  mov     r14d, [rbp+70h+var_90]
0x18025771c  mov     [rbp+70h+var_E8], r14d
0x180257720  mov     r14, [rbp+70h+arg_38]
0x180257727  mov     [rbp+70h+var_E4], ecx
0x18025772a  mov     dword ptr [rbp+70h+var_60], eax
0x18025772d  mov     dword ptr [rbp+70h+var_60+4], ecx
0x180257730  mov     ecx, [rbp+70h+var_E8]
0x180257733  mov     [rbp+70h+var_58], ecx
0x180257736  cmp     r9d, r13d
0x180257739  jnz     loc_18025790D
0x18025773f  mov     [rbp+70h+var_F0], eax
0x180257742  lea     rax, [rbp+70h+var_58]
0x180257746  mov     [rbp+70h+var_70], rax
0x18025774a  lea     rax, [rbp+70h+var_60+4]
0x18025774e  mov     byte ptr [rbp+70h+arg_8], 0
0x180257755  mov     [rbp+70h+var_48], rax
0x180257759  mov     [rbp+70h+var_EC], r10d
0x18025775d  mov     eax, [rbp+70h+var_B8]
0x180257760  mov     [rbp+70h+var_78], eax
0x180257763  mov     [rbp+70h+var_DC], r12d
0x180257767  mov     eax, dword ptr [rbp+70h+arg_8]
0x18025776d  mov     dword ptr [rbp+70h+var_D0], eax
0x180257770  mov     ecx, dword ptr [rbp+70h+arg_8]
0x180257776  mov     [rbp+70h+var_D8], ecx
0x180257779  mov     eax, [rbp+70h+var_EC]
0x18025777c  add     eax, [rbp+70h+var_F0]
0x18025777f  mov     ecx, edx
0x180257781  cmp     eax, [rbp+70h+var_EC]
0x180257784  cmovnb  ecx, eax
0x180257787  mov     [rbp+70h+var_EC], ecx
0x18025778a  mov     rax, [rbp+70h+var_48]
0x18025778e  mov     ecx, [rbp+70h+var_DC]
0x180257791  add     ecx, [rax]
0x180257793  mov     eax, edx
0x180257795  cmp     ecx, [rbp+70h+var_DC]
0x180257798  cmovnb  eax, ecx
0x18025779b  mov     [rbp+70h+var_F0], eax
0x18025779e  mov     rax, [rbp+70h+var_70]
0x1802577a2  mov     ecx, [rbp+70h+arg_30]
0x1802577a8  add     ecx, [rax]
0x1802577aa  cmp     ecx, [rbp+70h+arg_30]
0x1802577b0  cmovnb  edx, ecx; bool
0x1802577b3  mov     [rbp+70h+var_DC], edx
0x1802577b6  mov     eax, [rbp+70h+var_78]
0x1802577b9  mov     ecx, [rbp+70h+var_F0]
  ... truncated ...
```
