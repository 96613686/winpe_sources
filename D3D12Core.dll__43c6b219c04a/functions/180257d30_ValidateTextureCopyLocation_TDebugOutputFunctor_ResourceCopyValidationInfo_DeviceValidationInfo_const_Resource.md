# ValidateTextureCopyLocation(TDebugOutputFunctor &,ResourceCopyValidationInfo &,DeviceValidationInfo const &,ResourceValidationInfo const &,D3D12_TEXTURE_COPY_LOCATION const &,TextureCopyLocationValidationIDs const &)

- ea: `0x180257d30`
- end: `0x180258568`
- name: `?ValidateTextureCopyLocation@@YAJAEAUTDebugOutputFunctor@@AEAUResourceCopyValidationInfo@@AEBUDeviceValidationInfo@@AEBUResourceValidationInfo@@AEBUD3D12_TEXTURE_COPY_LOCATION@@AEBUTextureCopyLocationValidationIDs@@@Z`
- size: `2104`
- prototype: `__int64 __fastcall(struct TDebugOutputFunctor *, struct ResourceCopyValidationInfo *, const struct DeviceValidationInfo *, const struct ResourceValidationInfo *, const struct D3D12_TEXTURE_COPY_LOCATION *, const struct TextureCopyLocationValidationIDs *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180257320`

## callees

- `0x180026180`
- `0x18002ef50`
- `0x180067b6c`
- `0x180074dd4`
- `0x1800a8844`
- `0x1800abc10`
- `0x1800bb480`
- `0x180257d30`
- `0x180258570`
- `0x180262020`

## string_xrefs

- `0x18025819f`: `The region specified by D3D12_TEXTURE_COPY_LOCATION:PlacedFootprint extends past the end of the buffer it is placed on. The size required by PlacedFootprint is %I64u, as the fields of PlacedFootprint::Placement are as follows: RowPitch is %u, Height is %u, and Format is %s. PlacedFootprint::Offset is %I64u, which requires the buffer to have %I64u bytes; but the buffer only has %I64u bytes.`
- `0x1802580bd`: `D3D12_TEXTURE_COPY_LOCATION::Type is unrecognized. The value is %d.`
- `0x1802582e7`: `D3D12_TEXTURE_COPY_LOCATION::Type can not be D3D12_TEXTURE_COPY_TYPE_SUBRESOURCE_INDEX and used with a resource that is D3D12_RESOURCE_DIMENSION_BUFFER. D3D12_TEXTURE_COPY_TYPE_SUBRESOURCE_INDEX can only be used with textures.`
- `0x1802583b4`: `D3D12_TEXTURE_COPY_LOCATION::Type can not be D3D12_TEXTURE_COPY_TYPE_PLACED_FOOTPRINT and used with a resource that is a texture. The resource must be D3D12_RESOURCE_DIMENSION_BUFFER.`
- `0x180258409`: `Textures created with certain Formats must align the resource dimensions properly. D3D12_SUBRESOURCE_FOOTPRINT::Format is %s. D3D12_SUBRESOURCE_FOOTPRINT::Width is %u, and must be a multiple of %u. D3D12_SUBRESOURCE_FOOTPRINT::Height is %u, and must be a multiple of %u.`
- `0x1802582a4`: `D3D12_SUBRESOURCE_FOOTPRINT::RowPitch must be a multiple of %u (aka. D3D12_TEXTURE_DATA_PITCH_ALIGNMENT) when UnrestrictedBufferTextureCopyPitchSupported is false.`
- `0x18025825a`: `D3D12_PLACED_SUBRESOURCE_FOOTPRINT::Offset must be a multiple of %u (aka. D3D12_TEXTURE_DATA_PLACEMENT_ALIGNMENT) when UnrestrictedBufferTextureCopyPitchSupported is false. Offset is %I64u.`
- `0x18025854f`: `D3D12_TEXTURE_COPY_LOCATION::Subresource is too large for the associated resource. The value is %u, when the resource only has %u subresources.`
- `0x180258522`: `D3D12_SUBRESOURCE_FOOTPRINT::Format may not be a DXGI_FORMAT_R32G8X24_TYPELESS or DXGI_FORMAT_R24G8_TYPELESS family format. These formats are planar.  Use DXGI_FORMAT_R32_TYPELESS for plane 0 (Depth) and DXGI_FORMAT_R8_TYPELESS for plane 1 (stencil).  See GetCopyableFootprints.Format = %s`

## pseudocode

```c
__int64 __fastcall ValidateTextureCopyLocation(
        struct TDebugOutputFunctor *a1,
        struct ResourceCopyValidationInfo *a2,
        const struct DeviceValidationInfo *a3,
        const struct ResourceValidationInfo *a4,
        const struct D3D12_TEXTURE_COPY_LOCATION *a5,
        const struct TextureCopyLocationValidationIDs *a6)
{
  D3D12_TEXTURE_COPY_TYPE Type; // r9d
  __int64 Format; // r9
  enum D3D_FEATURE_LEVEL v12; // edx
  unsigned int v13; // r9d
  unsigned int Depth; // r13d
  unsigned int *p_Height; // r11
  int v16; // ecx
  __int64 v17; // rdi
  DXGI_FORMAT v18; // eax
  int v19; // r14d
  unsigned int v20; // r14d
  unsigned int v21; // r8d
  unsigned int v22; // edx
  unsigned int Width; // r15d
  unsigned int v24; // r14d
  unsigned int ByteAlignment; // eax
  unsigned int RowPitch; // r10d
  __int64 v27; // rax
  unsigned int v28; // r9d
  unsigned int v29; // ebp
  __int64 v30; // rax
  unsigned int v31; // r8d
  unsigned int v32; // eax
  unsigned int v33; // edx
  unsigned int SubresourceIndex; // r8d
  _OWORD *TexSubresourceInfo; // rax
  bool v37; // dl
  const char *Name; // rax
  const char *v39; // r8
  unsigned int v40; // eax
  __int64 v41; // rax
  unsigned __int64 v42; // rbp
  int v43; // r11d
  unsigned __int128 v44; // rax
  unsigned __int64 v45; // r9
  const char *v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  int v49; // r10d
  unsigned __int64 Offset; // rax
  int v51; // eax
  bool v52; // dl
  const char *v53; // rax
  _DWORD *v54; // r11
  const char *v55; // r8
  const char *v56; // r10
  const char *v57; // rax
  const char *v58; // r8
  int v59; // r9d
  int v60; // r10d
  int v61; // r11d
  const char *v62; // rax
  _DWORD *v63; // r11
  int v64; // r8d
  int v65; // r10d
  const char *v66; // rax
  int v67; // r8d
  int v68; // r10d
  const char *v69; // rax
  unsigned int v70; // [rsp+60h] [rbp-B8h] BYREF
  unsigned int v71; // [rsp+64h] [rbp-B4h]
  unsigned int v72; // [rsp+68h] [rbp-B0h]
  enum D3D12_RESOURCE_DIMENSION v73; // [rsp+6Ch] [rbp-ACh] BYREF
  enum D3D_FEATURE_LEVEL v74; // [rsp+70h] [rbp-A8h]
  unsigned int *v75; // [rsp+78h] [rbp-A0h]
  struct TDebugOutputFunctor *v76; // [rsp+80h] [rbp-98h]
  unsigned int v77; // [rsp+88h] [rbp-90h]
  _BYTE v78[20]; // [rsp+90h] [rbp-88h] BYREF
  __int64 v79; // [rsp+A4h] [rbp-74h]
  DXGI_FORMAT v80; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v81; // [rsp+B4h] [rbp-64h]

  v76 = a1;
  v75 = (unsigned int *)a6;
  Type = a5->Type;
  if ( Type )
  {
    if ( Type != D3D12_TEXTURE_COPY_TYPE_PLACED_FOOTPRINT )
    {
      TDebugOutputFunctor::operator()(
        a1,
        *(unsigned int *)a6,
        "D3D12_TEXTURE_COPY_LOCATION::Type is unrecognized. The value is %d.",
        Type);
      return 2147942487LL;
    }
    if ( (*((_DWORD *)a4 + 2) & 0xF000000) != 0x1000000 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a6 + 1),
        "D3D12_TEXTURE_COPY_LOCATION::Type can not be D3D12_TEXTURE_COPY_TYPE_PLACED_FOOTPRINT and used with a resource t"
        "hat is a texture. The resource must be D3D12_RESOURCE_DIMENSION_BUFFER.");
      return 2147942487LL;
    }
    if ( !*((_DWORD *)a3 + 223) && (a5->PlacedFootprint.Offset & 0x1FF) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a6 + 4),
        "D3D12_PLACED_SUBRESOURCE_FOOTPRINT::Offset must be a multiple of %u (aka. D3D12_TEXTURE_DATA_PLACEMENT_ALIGNMENT"
        ") when UnrestrictedBufferTextureCopyPitchSupported is false. Offset is %I64u.",
        512,
        a5->PlacedFootprint.Offset);
      return 2147942487LL;
    }
    Format = (unsigned int)a5->PlacedFootprint.Footprint.Format;
    if ( (unsigned int)Format >= 0xC0
      || (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * Format + 32) & 0x40) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a6 + 5),
        "D3D12_SUBRESOURCE_FOOTPRINT::Format is unrecognized. The value is %u.",
        Format);
      return 2147942487LL;
    }
    v80 = a5->PlacedFootprint.Footprint.Format;
    v81 = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64, DXGI_FORMAT *, __int64))(**((_QWORD **)a3 + 83) + 104LL))(
           *((_QWORD *)a3 + 83),
           3,
           &v80,
           12) < 0 )
    {
      FeatureLevelToString(*((enum D3D_FEATURE_LEVEL *)a3 + 164));
      Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(a5->PlacedFootprint.Footprint.Format, v37);
      TDebugOutputFunctor::operator()(
        a1,
        *((unsigned int *)a6 + 6),
        "D3D12_SUBRESOURCE_FOOTPRINT::Format is not supported at the current feature level. Format = %s and FeatureLevel is %s.",
        Name,
        v39);
      return 2147942487LL;
    }
    v12 = *((_DWORD *)a3 + 164);
    v74 = v12;
    v73 = D3D12_RESOURCE_DIMENSION_TEXTURE1D;
    v13 = 0x4000;
    if ( v12 < D3D_FEATURE_LEVEL_11_0 )
      v13 = 0x2000;
    Depth = a5->PlacedFootprint.Footprint.Depth;
    p_Height = &a5->PlacedFootprint.Footprint.Height;
    if ( Depth > 1 )
    {
      v13 = 2048;
      v16 = 64;
      v73 = D3D12_RESOURCE_DIMENSION_TEXTURE3D;
      v72 = 2048;
    }
    else
    {
      v72 = 1;
      if ( *p_Height == 1 && (v81 & 0x10) != 0 )
      {
        v16 = 16;
        v71 = 1;
LABEL_15:
        if ( (v16 & (unsigned int)v81) == 0 )
        {
          FeatureLevelToString(v12);
          D3D12ToStr(&v73);
          v53 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(a5->PlacedFootprint.Footprint.Format, v52);
          TDebugOutputFunctor::operator()(
            a1,
            *((unsigned int *)a6 + 7),
            "D3D12_SUBRESOURCE_FOOTPRINT::Format is not supported at the current feature level with the dimensionality im"
            "plied by the D3D12_SUBRESOURCE_FOOTPRINT::Height and D3D12_SUBRESOURCE_FOOTPRINT::Depth. Format = %s, Dimens"
            "ion = %s, Height = %u, Depth = %u, and FeatureLevel is %s.",
            v53,
            v56,
            *v54,
            Depth,
            v55);
          return 2147942487LL;
        }
        v17 = a5->PlacedFootprint.Footprint.Format;
        v18 = DXGI_FORMAT_FORCE_UINT;
        if ( (unsigned int)v17 >= 0xC0 )
        {
          v19 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 0x9FFFFFFFCLL);
          v74 = v12;
        }
        else
        {
          v19 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * (unsigned int)v17 + 6);
          v18 = a5->PlacedFootprint.Footprint.Format;
        }
        v20 = v19 & 0xF;
        v70 = v20;
        v21 = (*((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * (unsigned int)v18 + 6) >> 4) & 0xF;
        v77 = v21;
        if ( (unsigned int)(v17 - 70) > 0xE && (unsigned int)(v17 - 94) > 5 || !*((_DWORD *)a3 + 210) )
        {
          v22 = a5->PlacedFootprint.Footprint.Width % v20;
          if ( v22 || (v22 = *p_Height % v21) != 0 )
          {
            v62 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v17, v22);
            TDebugOutputFunctor::operator()(
              a1,
              v75[7],
              "Textures created with certain Formats must align the resource dimensions properly. D3D12_SUBRESOURCE_FOOTP"
              "RINT::Format is %s. D3D12_SUBRESOURCE_FOOTPRINT::Width is %u, and must be a multiple of %u. D3D12_SUBRESOU"
              "RCE_FOOTPRINT::Height is %u, and must be a multiple of %u.",
              v62,
              v65,
              v20,
              *v63,
              v64);
            return 2147942487LL;
          }
          v12 = v74;
        }
        Width = a5->PlacedFootprint.Footprint.Width;
        if ( !Width || (v24 = *p_Height) == 0 || !Depth )
        {
          TDebugOutputFunctor::operator()(
            v76,
            v75[7],
            "D3D12_SUBRESOURCE_FOOTPRINT::Width, D3D12_SUBRESOURCE_FOOTPRINT::Height, and D3D12_SUBRESOURCE_FOOTPRINT::De"
            "pth cannot be 0. The minimum value is 1. Width = %u, Height = %u, and Depth = %u.",
            Width,
            *p_Height,
            Depth);
          return 2147942487LL;
        }
        if ( Depth > v72 || Width > v13 || v24 > v71 )
        {
          FeatureLevelToString(v12);
          v57 = D3D12ToStr(&v73);
          TDebugOutputFunctor::operator()(
            v76,
            v75[7],
            "D3D12_SUBRESOURCE_FOOTPRINT::Width, D3D12_SUBRESOURCE_FOOTPRINT::Height, and/ or D3D12_SUBRESOURCE_FOOTPRINT"
            "::Depth are too large for the implied dimensionality and FeatureLevel. Width = %u and must be <= %u, Height "
            "= %u and must be <= %u, Depth = %u and must be <= %u, Dimension = %s, and FeatureLevel = %s.",
            Width,
            v59,
            v24,
            v60,
            Depth,
            v61,
            v57,
            v58);
          return 2147942487LL;
        }
        ByteAlignment = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetByteAlignment((enum DXGI_FORMAT)v17);
        RowPitch = a5->PlacedFootprint.Footprint.RowPitch;
        if ( RowPitch < Width / v70 * ByteAlignment )
        {
          v66 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v17, Width % v70);
          TDebugOutputFunctor::operator()(
            v76,
            v75[8],
            "D3D12_SUBRESOURCE_FOOTPRINT::RowPitch must be greater or equal to the pitch implied by the width. RowPitch i"
            "s %u, and must be greater or equal to %u when D3D12_SUBRESOURCE_FOOTPRINT::Width is %u and D3D12_SUBRESOURCE"
            "_FOOTPRINT::Format is %s.",
            v68,
            v67,
            Width,
            v66);
          return 2147942487LL;
        }
        if ( !*((_DWORD *)a3 + 223) && (_BYTE)RowPitch )
        {
          TDebugOutputFunctor::operator()(
            v76,
            v75[8],
            "D3D12_SUBRESOURCE_FOOTPRINT::RowPitch must be a multiple of %u (aka. D3D12_TEXTURE_DATA_PITCH_ALIGNMENT) whe"
            "n UnrestrictedBufferTextureCopyPitchSupported is false.",
            256);
          return 2147942487LL;
        }
        v27 = 0xFFFFFFFFLL;
        if ( (unsigned int)v17 < 0xC0 )
          v27 = (unsigned int)v17;
        v74 = (int)v27;
        v28 = 0;
        v70 = 0;
        if ( !(_DWORD)v17 )
        {
          v29 = Width;
LABEL_52:
          v43 = 0;
          if ( (*(&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v27 + 32) & 8) != 0 )
          {
            v43 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::CalculateExtraPlanarRows((enum DXGI_FORMAT)v17, v24, &v70);
            v28 = v70;
            RowPitch = a5->PlacedFootprint.Footprint.RowPitch;
          }
          else
          {
            v28 = (v24 + v77 - 1) / v77;
          }
          goto LABEL_54;
        }
        v29 = 0;
        v30 = 0xFFFFFFFFLL;
        if ( (unsigned int)v17 < 0xC0 )
          v30 = (unsigned int)v17;
        v31 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v30 + 6) & 0xF;
        if ( (unsigned int)(v17 - 70) <= 0xE || (unsigned int)(v17 - 94) <= 5 )
        {
          v40 = v31 + Width - 1;
          if ( v40 < Width )
            goto LABEL_89;
          v33 = v40 / v31;
        }
        else
        {
          v32 = v31 - 1 + Width;
          if ( v32 < Width )
            goto LABEL_89;
          v33 = v32 & ~(v31 - 1);
        }
        if ( (unsigned int)v17 >= 0xC0 )
          v41 = 0xFFFFFFFFLL;
        else
          v41 = (unsigned int)v17;
        v42 = v33
            * (unsigned __int64)*((unsigned __int8 *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 40 * v41 + 20);
        if ( v42 <= 0xFFFFFFFF )
        {
          v29 = (unsigned int)v42 >> 3;
          v27 = (unsigned int)v74;
          goto LABEL_52;
        }
        v29 = -1;
LABEL_89:
        v43 = -2147024362;
LABEL_54:
        v44 = RowPitch * (unsigned __int128)(v28 * Depth - 1);
        if ( !is_mul_ok(RowPitch, v28 * Depth - 1)
          || (v45 = v44 + v29, v45 < (unsigned __int64)v44)
          || (Offset = a5->PlacedFootprint.Offset, v45 + Offset < Offset)
          || v45 + Offset > *(_QWORD *)a4
          || v43 < 0 )
        {
          v46 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v17, SBYTE8(v44));
          TDebugOutputFunctor::operator()(
            v76,
            v75[9],
            "The region specified by D3D12_TEXTURE_COPY_LOCATION:PlacedFootprint extends past the end of the buffer it is"
            " placed on. The size required by PlacedFootprint is %I64u, as the fields of PlacedFootprint::Placement are a"
            "s follows: RowPitch is %u, Height is %u, and Format is %s. PlacedFootprint::Offset is %I64u, which requires "
            "the buffer to have %I64u bytes; but the buffer only has %I64u bytes.",
            v48,
            v49,
            v24,
            v46,
            a5->PlacedFootprint.Offset,
            v47,
            *(_QWORD *)a4);
          return 2147942487LL;
        }
        v51 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v17 + 1);
        if ( v51 != 19 && v51 != 44 )
        {
          v79 = 1;
          *(_DWORD *)a2 = Width;
          *((_DWORD *)a2 + 1) = v24;
          *((_DWORD *)a2 + 2) = Depth;
          *((_DWORD *)a2 + 3) = v17;
          *((_DWORD *)a2 + 4) = v51;
          *(_QWORD *)((char *)a2 + 20) = v79;
          return 0;
        }
        v69 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v17, SBYTE8(v44));
        TDebugOutputFunctor::operator()(
          v76,
          v75[10],
          "D3D12_SUBRESOURCE_FOOTPRINT::Format may not be a DXGI_FORMAT_R32G8X24_TYPELESS or DXGI_FORMAT_R24G8_TYPELESS f"
          "amily format. These formats are planar.  Use DXGI_FORMAT_R32_TYPELESS for plane 0 (Depth) and DXGI_FORMAT_R8_T"
          "YPELESS for plane 1 (stencil).  See GetCopyableFootprints.Format = %s",
          v69);
        return 2147942487LL;
      }
      if ( (*((_BYTE *)a3 + 688) & 1) != 0 && (a5->PlacedFootprint.Footprint.Width > v13 || *p_Height > v13) )
        v13 = 0x800000;
      v16 = 32;
      v73 = D3D12_RESOURCE_DIMENSION_TEXTURE2D;
    }
    v71 = v13;
    goto LABEL_15;
  }
  if ( (*((_DWORD *)a4 + 2) & 0xF000000) == 0x1000000 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a6 + 1),
      "D3D12_TEXTURE_COPY_LOCATION::Type can not be D3D12_TEXTURE_COPY_TYPE_SUBRESOURCE_INDEX and used with a resource th"
      "at is D3D12_RESOURCE_DIMENSION_BUFFER. D3D12_TEXTURE_COPY_TYPE_SUBRESOURCE_INDEX can only be used with textures.");
    return 2147942487LL;
  }
  else
  {
    SubresourceIndex = a5->SubresourceIndex;
    if ( SubresourceIndex < (*((_DWORD *)a4 + 5) & 0xFFFFFFu) )
    {
      TexSubresourceInfo = (_OWORD *)ResourceValidationInfo::GetTexSubresourceInfo(a4, v78);
      *(_OWORD *)a2 = *TexSubresourceInfo;
      *(_OWORD *)((char *)a2 + 12) = *(_OWORD *)((char *)TexSubresourceInfo + 12);
      return 0;
    }
    TDebugOutputFunctor::operator()(
      a1,
      *((unsigned int *)a6 + 3),
      "D3D12_TEXTURE_COPY_LOCATION::Subresource is too large for the associated resource. The value is %u, when the resou"
      "rce only has %u subresources.",
      SubresourceIndex,
      *((_DWORD *)a4 + 5) & 0xFFFFFF);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180257d30  push    rbx
0x180257d32  push    rbp
0x180257d33  push    rsi
0x180257d34  push    rdi
0x180257d35  push    r12
0x180257d37  push    r13
0x180257d39  push    r14
0x180257d3b  push    r15
0x180257d3d  sub     rsp, 0D8h
0x180257d44  mov     rax, cs:__security_cookie
0x180257d4b  xor     rax, rsp
0x180257d4e  mov     [rsp+118h+var_58], rax
0x180257d56  mov     rsi, r9
0x180257d59  mov     rbp, r8
0x180257d5c  mov     r12, rdx
0x180257d5f  mov     r15, rcx
0x180257d62  mov     [rsp+118h+var_98], rcx
0x180257d6a  mov     rdi, [rsp+118h+arg_28]
0x180257d72  mov     [rsp+118h+var_A0], rdi
0x180257d77  mov     rbx, [rsp+118h+arg_20]
0x180257d7f  mov     r9d, [rbx+8]
0x180257d83  test    r9d, r9d
0x180257d86  jz      loc_180258016
0x180257d8c  cmp     r9d, 1
0x180257d90  jnz     loc_1802580BD
0x180257d96  mov     eax, [rsi+8]
0x180257d99  and     eax, 0F000000h
0x180257d9e  cmp     eax, 1000000h
0x180257da3  jnz     loc_1802583B4
0x180257da9  cmp     dword ptr [r8+37Ch], 0
0x180257db1  jz      loc_18025823F
0x180257db7  mov     r9d, [rbx+18h]
0x180257dbb  cmp     r9d, 0C0h
0x180257dc2  jnb     loc_1802583CD
0x180257dc8  lea     rcx, [r9+r9*4]
0x180257dcc  lea     r14, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180257dd3  test    byte ptr [r14+rcx*8+20h], 40h
0x180257dd9  jnz     loc_1802583CD
0x180257ddf  mov     [rsp+118h+var_68], r9d
0x180257de7  xor     eax, eax
0x180257de9  mov     [rsp+118h+var_64], rax
0x180257df1  mov     rcx, [r8+298h]
0x180257df8  mov     rax, [rcx]
0x180257dfb  mov     r9d, 0Ch
0x180257e01  lea     r8, [rsp+118h+var_68]
0x180257e09  mov     edx, 3
0x180257e0e  mov     rax, [rax+68h]
0x180257e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180257e17  test    eax, eax
0x180257e19  js      loc_180258086
0x180257e1f  mov     edx, [rbp+290h]
0x180257e25  mov     [rsp+118h+var_A8], edx
0x180257e29  mov     [rsp+118h+var_AC], 2
0x180257e31  mov     eax, 2000h
0x180257e36  mov     r9d, 4000h
0x180257e3c  cmp     edx, 0B000h
0x180257e42  cmovl   r9d, eax
0x180257e46  mov     r13d, [rbx+24h]
0x180257e4a  mov     eax, dword ptr [rsp+118h+var_64]
0x180257e51  lea     r11, [rbx+20h]
0x180257e55  cmp     r13d, 1
0x180257e59  ja      loc_1802582CA
0x180257e5f  mov     [rsp+118h+var_B0], 1
0x180257e67  mov     ecx, [r11]
0x180257e6a  cmp     ecx, 1
0x180257e6d  jz      loc_180258273
0x180257e73  test    byte ptr [rbp+2B0h], 1
0x180257e7a  jnz     loc_18025842A
0x180257e80  mov     ecx, 20h ; ' '
0x180257e85  mov     [rsp+118h+var_AC], 3
0x180257e8d  mov     [rsp+118h+var_B4], r9d
0x180257e92  test    eax, ecx
0x180257e94  jz      loc_180258300
0x180257e9a  movsxd  rdi, dword ptr [rbx+18h]
0x180257e9e  mov     eax, 0FFFFFFFFh
0x180257ea3  lea     r8, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180257eaa  cmp     edi, 0C0h
0x180257eb0  jnb     loc_1802584EA
0x180257eb6  mov     eax, edi
0x180257eb8  lea     rcx, [rax+rax*4]
0x180257ebc  mov     r14d, [r14+rcx*8+18h]
0x180257ec1  mov     eax, edi
0x180257ec3  and     r14d, 0Fh
0x180257ec7  mov     [rsp+118h+var_B8], r14d
0x180257ecc  mov     eax, eax
0x180257ece  lea     rcx, [rax+rax*4]
0x180257ed2  mov     r8d, [r8+rcx*8+18h]
0x180257ed7  shr     r8d, 4
0x180257edb  and     r8d, 0Fh
0x180257edf  mov     [rsp+118h+var_90], r8d
0x180257ee7  lea     eax, [rdi-46h]
0x180257eea  cmp     eax, 0Eh
0x180257eed  jbe     loc_1802584D8
0x180257ef3  lea     eax, [rdi-5Eh]
0x180257ef6  cmp     eax, 5
0x180257ef9  jbe     loc_1802584D8
0x180257eff  mov     r10d, [rbx+1Ch]
0x180257f03  xor     edx, edx; bool
0x180257f05  mov     eax, r10d
0x180257f08  div     r14d
0x180257f0b  test    edx, edx
0x180257f0d  jnz     loc_1802583E9
0x180257f13  xor     edx, edx
0x180257f15  mov     eax, [r11]
0x180257f18  div     r8d
0x180257f1b  test    edx, edx
0x180257f1d  jnz     loc_1802583E9
0x180257f23  mov     edx, [rsp+118h+var_A8]
0x180257f27  mov     r15d, [rbx+1Ch]
0x180257f2b  test    r15d, r15d
0x180257f2e  jz      loc_180258444
0x180257f34  mov     r14d, [r11]
0x180257f37  test    r14d, r14d
0x180257f3a  jz      loc_180258444
0x180257f40  test    r13d, r13d
0x180257f43  jz      loc_180258444
0x180257f49  mov     r10d, [rsp+118h+var_B4]
0x180257f4e  mov     r11d, [rsp+118h+var_B0]
0x180257f53  cmp     r13d, r11d
0x180257f56  ja      loc_180258354
0x180257f5c  cmp     r15d, r9d
0x180257f5f  ja      loc_180258354
0x180257f65  cmp     r14d, r10d
0x180257f68  ja      loc_180258354
0x180257f6e  mov     ecx, edi; enum DXGI_FORMAT
0x180257f70  call    ?GetByteAlignment@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAIW4DXGI_FORMAT@@@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetByteAlignment(DXGI_FORMAT)
0x180257f75  mov     r8d, eax
0x180257f78  xor     edx, edx; bool
0x180257f7a  mov     eax, r15d
0x180257f7d  div     [rsp+118h+var_B8]
0x180257f81  imul    r8d, eax
0x180257f85  mov     r10d, [rbx+28h]
0x180257f89  cmp     r10d, r8d
0x180257f8c  jb      loc_180258479
0x180257f92  cmp     dword ptr [rbp+37Ch], 0
0x180257f99  jz      loc_180258295
0x180257f9f  mov     ecx, 0FFFFFFFFh
0x180257fa4  mov     eax, ecx
0x180257fa6  cmp     edi, 0C0h
0x180257fac  cmovb   eax, edi
0x180257faf  mov     [rsp+118h+var_A8], eax
0x180257fb3  xor     r9d, r9d
0x180257fb6  mov     [rsp+118h+var_B8], r9d
0x180257fbb  test    edi, edi
0x180257fbd  jz      loc_18025828D
0x180257fc3  xor     ebp, ebp
0x180257fc5  mov     eax, ecx
0x180257fc7  cmp     edi, 0C0h
0x180257fcd  cmovb   eax, edi
0x180257fd0  lea     rcx, [rax+rax*4]
0x180257fd4  lea     r11, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x180257fdb  mov     r8d, [r11+rcx*8+18h]
0x180257fe0  and     r8d, 0Fh
0x180257fe4  lea     eax, [rdi-46h]
0x180257fe7  cmp     eax, 0Eh
0x180257fea  jbe     loc_1802580D2
0x180257ff0  lea     eax, [rdi-5Eh]
0x180257ff3  cmp     eax, 5
0x180257ff6  jbe     loc_1802580D2
0x180257ffc  lea     edx, [r8-1]
0x180258000  lea     eax, [rdx+r15]
0x180258004  cmp     eax, r15d
0x180258007  jb      loc_18025850D
0x18025800d  not     edx
0x18025800f  and     edx, eax
0x180258011  jmp     loc_1802580E9
0x180258016  mov     eax, [rsi+8]
0x180258019  and     eax, 0F000000h
0x18025801e  cmp     eax, 1000000h
0x180258023  jz      loc_1802582E7
0x180258029  mov     eax, [rsi+14h]
0x18025802c  and     eax, 0FFFFFFh
0x180258031  mov     r8d, [rbx+10h]
0x180258035  cmp     r8d, eax
0x180258038  jnb     loc_180258548
0x18025803e  lea     rdx, [rsp+118h+var_88]
0x180258046  mov     rcx, rsi
0x180258049  call    ?GetTexSubresourceInfo@ResourceValidationInfo@@QEBA?AUResourceCopyValidationInfo@@I@Z; ResourceValidationInfo::GetTexSubresourceInfo(uint)
0x18025804e  movups  xmm0, xmmword ptr [rax]
0x180258051  movups  xmmword ptr [r12], xmm0
0x180258056  movups  xmm1, xmmword ptr [rax+0Ch]
0x18025805a  movups  xmmword ptr [r12+0Ch], xmm1
0x180258060  xor     eax, eax
0x180258062  mov     rcx, [rsp+118h+var_58]
0x18025806a  xor     rcx, rsp; StackCookie
0x18025806d  call    __security_check_cookie
0x180258072  add     rsp, 0D8h
0x180258079  pop     r15
0x18025807b  pop     r14
0x18025807d  pop     r13
0x18025807f  pop     r12
0x180258081  pop     rdi
0x180258082  pop     rsi
0x180258083  pop     rbp
0x180258084  pop     rbx
0x180258085  retn
0x180258086  mov     ecx, [rbp+290h]; enum D3D_FEATURE_LEVEL
0x18025808c  call    ?FeatureLevelToString@@YAPEBDW4D3D_FEATURE_LEVEL@@@Z; FeatureLevelToString(D3D_FEATURE_LEVEL)
0x180258091  mov     r8, rax
0x180258094  mov     ecx, [rbx+18h]; enum DXGI_FORMAT
0x180258097  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18025809c  mov     r9, rax
0x18025809f  mov     [rsp+118h+var_F8], r8
0x1802580a4  lea     r8, aD3d12Subresour_5; "D3D12_SUBRESOURCE_FOOTPRINT::Format is "...
0x1802580ab  mov     edx, [rdi+18h]
0x1802580ae  mov     rcx, r15
0x1802580b1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802580b6  mov     eax, 80070057h
0x1802580bb  jmp     short loc_180258062
0x1802580bd  lea     r8, aD3d12TextureCo_0; "D3D12_TEXTURE_COPY_LOCATION::Type is un"...
0x1802580c4  mov     edx, [rdi]
0x1802580c6  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802580cb  mov     eax, 80070057h
0x1802580d0  jmp     short loc_180258062
0x1802580d2  lea     eax, [r15-1]
0x1802580d6  add     eax, r8d
0x1802580d9  cmp     eax, r15d
0x1802580dc  jb      loc_18025850D
0x1802580e2  xor     edx, edx
0x1802580e4  div     r8d
0x1802580e7  mov     edx, eax
0x1802580e9  mov     r8d, 0FFFFFFFFh
0x1802580ef  cmp     edi, 0C0h
0x1802580f5  jnb     loc_180258502
0x1802580fb  mov     eax, edi
0x1802580fd  lea     rcx, [rax+rax*4]
0x180258101  movzx   ebp, byte ptr [r11+rcx*8+14h]
0x180258107  mov     eax, edx
0x180258109  imul    rbp, rax
0x18025810d  cmp     rbp, r8
0x180258110  ja      loc_18025850A
0x180258116  shr     ebp, 3
0x180258119  mov     eax, [rsp+118h+var_A8]
0x18025811d  xor     r11d, r11d
0x180258120  lea     rcx, [rax+rax*4]
0x180258124  lea     rax, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x18025812b  test    byte ptr [rax+rcx*8+20h], 8
0x180258130  jnz     loc_1802584B8
0x180258136  mov     ecx, [rsp+118h+var_90]
0x18025813d  lea     eax, [rcx-1]
0x180258140  add     eax, r14d
0x180258143  xor     edx, edx; bool
0x180258145  div     ecx
0x180258147  mov     r9d, eax
0x18025814a  xor     r8d, r8d
0x18025814d  mov     eax, r13d
0x180258150  imul    eax, r9d
0x180258154  dec     eax
0x180258156  mov     ecx, r10d
0x180258159  mul     rcx
0x18025815c  test    rdx, rdx
0x18025815f  jnz     short loc_18025816C
0x180258161  mov     r9d, ebp
0x180258164  add     r9, rax
0x180258167  cmp     r9, rax
0x18025816a  jnb     short loc_1802581C5
0x18025816c  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180258173  mov     ecx, edi; enum DXGI_FORMAT
0x180258175  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18025817a  mov     rcx, [rsi]
0x18025817d  mov     [rsp+118h+var_D0], rcx
0x180258182  mov     [rsp+118h+var_D8], r8
0x180258187  mov     rcx, [rbx+10h]
0x18025818b  mov     [rsp+118h+var_E0], rcx
0x180258190  mov     [rsp+118h+var_E8], rax
0x180258195  mov     [rsp+118h+var_F0], r14d
0x18025819a  mov     dword ptr [rsp+118h+var_F8], r10d
0x18025819f  lea     r8, aTheRegionSpeci; "The region specified by D3D12_TEXTURE_C"...
0x1802581a6  mov     rdx, [rsp+118h+var_A0]
0x1802581ab  mov     edx, [rdx+24h]
0x1802581ae  mov     rcx, [rsp+118h+var_98]
0x1802581b6  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802581bb  mov     eax, 80070057h
0x1802581c0  jmp     loc_180258062
0x1802581c5  mov     rax, [rbx+10h]
0x1802581c9  lea     r8, [r9+rax]
0x1802581cd  cmp     r8, rax
0x1802581d0  jb      short loc_180258233
0x1802581d2  cmp     r8, [rsi]
0x1802581d5  ja      short loc_180258173
0x1802581d7  test    r11d, r11d
0x1802581da  js      short loc_180258173
0x1802581dc  lea     rcx, [rdi+rdi*4]
0x1802581e0  lea     rax, ?s_FormatDetail@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@0QBUFORMAT_DETAIL@1@B; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FORMAT_DETAIL const near * const D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
0x1802581e7  mov     eax, [rax+rcx*8+4]
0x1802581eb  cmp     eax, 13h
0x1802581ee  jz      loc_180258518
0x1802581f4  cmp     eax, 2Ch ; ','
0x1802581f7  jz      loc_180258518
0x1802581fd  mov     [rsp+118h+var_74], 1
0x180258209  mov     [r12], r15d
0x18025820d  mov     [r12+4], r14d
0x180258212  mov     [r12+8], r13d
0x180258217  mov     [r12+0Ch], edi
0x18025821c  mov     [r12+10h], eax
0x180258221  mov     rax, [rsp+118h+var_74]
0x180258229  mov     [r12+14h], rax
0x18025822e  jmp     loc_180258060
0x180258233  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18025823a  jmp     loc_180258173
  ... truncated ...
```
