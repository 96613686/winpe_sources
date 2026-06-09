# ValidateResolveSubresourceRegion(TDebugOutputFunctor &,DeviceValidationInfo const &,ResourceValidationInfo const &,uint,uint,uint,ResourceValidationInfo const &,uint,tagRECT const *,DXGI_FORMAT,D3D12_RESOLVE_MODE)

- ea: `0x180236008`
- end: `0x18023671d`
- name: `?ValidateResolveSubresourceRegion@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUResourceValidationInfo@@III2IPEBUtagRECT@@W4DXGI_FORMAT@@W4D3D12_RESOLVE_MODE@@@Z`
- size: `1813`
- prototype: `int(struct TDebugOutputFunctor *, const struct DeviceValidationInfo *, const struct ResourceValidationInfo *, unsigned int, unsigned int, unsigned int, const struct ResourceValidationInfo *, unsigned int, const struct tagRECT *, enum DXGI_FORMAT, enum D3D12_RESOLVE_MODE)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180250440`
- `0x180250690`
- `0x18025da88`
- `0x18025e44c`

## callees

- `0x18002ef50`
- `0x180031ec0`
- `0x18003f5d0`
- `0x180049bb0`
- `0x18004a0c0`
- `0x1800abc10`
- `0x180236008`
- `0x18025ce10`
- `0x180262020`

## string_xrefs

- `0x180236042`: `The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.`
- `0x1802360ac`: `When encoding sampler feedback, the source resource needs to be a compatible format- e.g., R8_UINT or DXGI_FORMAT_UNKNOWN. The passed-in format was %s.`
- `0x1802363f9`: `Destination resource sample count : %u, and Source resource sample count : %u, but when mode is set to D3D12_RESOLVE_MODE_DECOMPRESS, sample count of destination resource must be equal to sample count of source resource. `
- `0x18023641d`: `When mode is set to D3D12_RESOLVE_MODE_DECOMPRESS, sample quality of destination resource must be match sample quality of source resource.`
- `0x1802361be`: `When decoding sampler feedback, the destination resource needs to be a compatible format- e.g., R8_UINT or UNKNOWN. The passed-in format was %s.`
- `0x1802365fc`: `The specified format is not compatible with the source resource. Format:%s, Source Resource Format:%s`
- `0x180236632`: `The specified format is not compatible with the destination resource. Format:%s, Destination Resource Format:%s`
- `0x18023658d`: `The specified format %s does not support MSAA resolve. Only render target and depth stencil fully typed formats are allowed, except for formats DXGI_FORMAT_R24_UNORM_X8_TYPELESS, DXGI_FORMAT_R32_FLOAT_X8X24_TYPELESS, DXGI_FORMAT_X24_TYPELESS_G8_UINT and DXGI_FORMAT_X32_TYPELESS_G8X24_UINT, which are allowed since these have a fully typed component.`

## pseudocode

```c
__int64 __fastcall ValidateResolveSubresourceRegion(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        const struct ResourceValidationInfo *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        const struct ResourceValidationInfo *a7,
        unsigned int a8,
        const struct tagRECT *a9,
        enum DXGI_FORMAT a10,
        enum D3D12_RESOLVE_MODE a11)
{
  const struct DeviceValidationInfo *v13; // r13
  const struct ResourceValidationInfo *v15; // rbp
  char v17; // di
  _DWORD *v18; // r14
  enum DXGI_FORMAT v19; // ecx
  const char *Name; // rax
  _DWORD *v21; // rsi
  const char *v22; // rax
  int v23; // eax
  int v24; // ecx
  __int16 v25; // dx
  const char *v26; // rax
  enum DXGI_FORMAT v27; // ecx
  const char *v28; // rax
  unsigned __int16 v29; // ax
  __int16 v30; // dx
  int v31; // ecx
  char v32; // r12
  const struct tagRECT *v33; // rsi
  int v34; // ecx
  int v35; // r14d
  int top; // r9d
  unsigned int v37; // edx
  unsigned int v38; // ecx
  int v39; // r9d
  const char *v40; // r8
  unsigned int v41; // r9d
  __int64 v42; // rsi
  int v43; // eax
  bool v44; // dl
  const char *v45; // rax
  unsigned int v46; // r10d
  __int64 v47; // r8
  __int64 v48; // r9
  int v49; // eax
  bool v50; // dl
  int v51; // r11d
  const char *v52; // rax
  int v53; // r12d
  int v54; // r13d
  char v55; // dl
  bool v56; // dl
  const char *v57; // rax
  const char *v58; // r8
  bool v59; // dl
  const char *v60; // rax
  const char *v61; // r8

  v13 = a2;
  v15 = a7;
  if ( (*((_DWORD *)a7 + 3) & 0xF000000) == 0x3000000 )
  {
    TDebugOutputFunctor::operator()(a1, 950, "The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.");
    return 2147942487LL;
  }
  if ( (*((_DWORD *)a3 + 3) & 0xF000000) == 0x2000000 )
  {
    TDebugOutputFunctor::operator()(a1, 948, "The destination resource cannot be on a D3D12_HEAP_TYPE_UPLOAD heap.");
    return 2147942487LL;
  }
  v17 = 0;
  if ( a11 == 4 )
  {
    v18 = (_DWORD *)((char *)a7 + 16);
    v19 = *((__int16 *)a7 + 9);
    if ( v19 != DXGI_FORMAT_R8_UINT && *((_WORD *)a7 + 9) )
    {
      Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v19, (bool)a2);
      TDebugOutputFunctor::operator()(
        a1,
        1268,
        "When encoding sampler feedback, the source resource needs to be a compatible format- e.g., R8_UINT or DXGI_FORMA"
        "T_UNKNOWN. The passed-in format was %s.",
        Name);
      v17 = 1;
    }
    v21 = (_DWORD *)((char *)a3 + 16);
    if ( *((_WORD *)a3 + 9) != 189 && *((_WORD *)a3 + 9) != 190 )
    {
      v22 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((__int16 *)a3 + 9), (bool)a2);
      TDebugOutputFunctor::operator()(
        a1,
        1268,
        "When encoding sampler feedback, the destination resource needs to be a sampler feedback format. The passed-in format was %s.",
        v22);
      v17 = 1;
    }
    v23 = *((__int16 *)a3 + 9);
    if ( v23 == 189 )
    {
      if ( *((_BYTE *)v15 + 23) == 1 )
      {
LABEL_30:
        ResourceValidationInfo::ArraySize(a3);
        v29 = ResourceValidationInfo::ArraySize(v15);
        if ( v29 != v30 )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1270,
            "When transcoding sampler feedback, the source and destination array sizes must match.");
          v17 = 1;
        }
        if ( ((*v18 & 0xFFFF0000) == 0xBE0000 || (*v21 & 0xFFFF0000) == 0xBE0000)
          && (v31 = *((unsigned __int8 *)v15 + 23), (_BYTE)v31 != *((_BYTE *)a3 + 23)) )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1269,
            "When transcoding MipRegionUsed sampler feedback, the source resource must have the same mip level count as t"
            "he destination. The source resource mip level count is %u, and the destination mip level count is %u.",
            v31,
            *((unsigned __int8 *)a3 + 23));
          v17 = 1;
          v32 = 1;
        }
        else
        {
          v32 = 1;
        }
        v13 = a2;
        goto LABEL_54;
      }
      TDebugOutputFunctor::operator()(
        a1,
        1269,
        "When encoding MinMip sampler feedback, the source resource must have 1 mip level. Source resource mip level count : %u.",
        *((unsigned __int8 *)v15 + 23));
    }
    else
    {
      if ( v23 != 190 )
        goto LABEL_30;
      v24 = *((unsigned __int8 *)v15 + 23);
      if ( (_BYTE)v24 == *((_BYTE *)a3 + 23) )
        goto LABEL_30;
      TDebugOutputFunctor::operator()(
        a1,
        1269,
        "When encoding MipRegionUsed sampler feedback, the source resource must have the same mip level count as the dest"
        "ination. The source resource mip level count is %u, and the destination mip level count is %u.",
        v24,
        *((unsigned __int8 *)a3 + 23));
    }
LABEL_29:
    v17 = 1;
    goto LABEL_30;
  }
  if ( a11 == 5 )
  {
    v18 = (_DWORD *)((char *)a7 + 16);
    v25 = *((_WORD *)a7 + 9) - 189;
    if ( *((_WORD *)a7 + 9) != 189 && *((_WORD *)a7 + 9) != 190 )
    {
      v26 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(
              (enum DXGI_FORMAT)*((__int16 *)a7 + 9),
              *((_BYTE *)a7 + 18) + 67);
      TDebugOutputFunctor::operator()(
        a1,
        1268,
        "When decoding sampler feedback, the source resource needs to be a sampler feedback format. The passed-in format was %s.",
        v26);
      v17 = 1;
    }
    v21 = (_DWORD *)((char *)a3 + 16);
    v27 = *((__int16 *)a3 + 9);
    if ( v27 != DXGI_FORMAT_R8_UINT && *((_WORD *)a3 + 9) )
    {
      v28 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v27, v25);
      TDebugOutputFunctor::operator()(
        a1,
        1268,
        "When decoding sampler feedback, the destination resource needs to be a compatible format- e.g., R8_UINT or UNKNO"
        "WN. The passed-in format was %s.",
        v28);
      v17 = 1;
    }
    if ( (*v18 & 0xFFFF0000) != 0xBD0000 || *((_BYTE *)a3 + 23) == 1 )
      goto LABEL_30;
    TDebugOutputFunctor::operator()(
      a1,
      1269,
      "When decoding MinMip sampler feedback, the destination resource must have 1 mip level. Destination resource mip level count : %u.",
      *((unsigned __int8 *)a3 + 23));
    goto LABEL_29;
  }
  v32 = 0;
  if ( ((*((_DWORD *)a3 + 2) ^ *((_DWORD *)a7 + 2)) & 0xF000000) != 0 )
  {
    TDebugOutputFunctor::operator()(a1, 879, "The dimensions of the source and destination resources do not match.");
    v17 = 1;
  }
  if ( a4 >= (*((_DWORD *)a3 + 5) & 0xFFFFFFu) || a8 >= (*((_DWORD *)v15 + 5) & 0xFFFFFFu) )
  {
    TDebugOutputFunctor::operator()(a1, 877, "Source or destination subresource index is out of bounds.");
    v17 = 1;
  }
  v33 = a9;
  if ( a9 )
  {
    if ( a9->left >= a9->right )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1050,
        "pSrcRect.left = %u and pSrcRect.right = %u, and left must be less than right",
        a9->left,
        a9->right);
      v17 = 1;
    }
    top = v33->top;
    if ( top >= v33->bottom )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1050,
        "pSrcRect.top = %u and pSrcRect.bottom = %u, and top must be less than bottom.",
        top,
        v33->bottom);
      v17 = 1;
    }
    v34 = v33->right - v33->left;
    v35 = v33->bottom - v33->top;
  }
  else
  {
    v34 = *((_DWORD *)v15 + 2) & 0xFFFFFF;
    v35 = *((_DWORD *)v15 + 3) & 0xFFFFFF;
  }
  v37 = *((_DWORD *)a3 + 2) & 0xFFFFFF;
  if ( v34 + a5 > v37 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1050,
      "The destination region extends past the end of the destination resource. With DstX = %u, pSrcRect's width = %u wil"
      "l exceed width of destination resource = %u.",
      a5,
      v34,
      v37);
    v17 = 1;
  }
  v38 = *((_DWORD *)a3 + 3) & 0xFFFFFF;
  if ( v35 + a6 > v38 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1050,
      "The destination region extends past the end of the destination resource. With DstY = %u, pSrcRect's height = %u wi"
      "ll exceed height of destination resource = %u.",
      a6,
      v35,
      v38);
    v17 = 1;
  }
LABEL_54:
  if ( a11 )
  {
    if ( a11 == 4 )
    {
      if ( *((_DWORD *)v15 + 6) <= 1u && !*((_DWORD *)v15 + 7) )
        goto LABEL_72;
      v40 = "When encoding sampler feedback, the source subresource must have sample count 1, quality 0. Source resource "
            "sample count : %u, quality %u.";
    }
    else
    {
      v41 = *((_DWORD *)a3 + 6);
      if ( a11 == 5 )
      {
        if ( v41 <= 1 && !*((_DWORD *)a3 + 7) )
          goto LABEL_72;
        v40 = "When decoding sampler feedback, the destination subresource must have sample count 1, quality 0. Destinati"
              "on resource sample count : %u, quality %u.";
      }
      else
      {
        if ( v41 == 1 && *((_DWORD *)v15 + 6) >= 2u )
          goto LABEL_72;
        v40 = "Destination resource sample count: %u, and Source resource sample count: %u. The destination resource samp"
              "le count must be 1, and the source resource sample count must be >= 2.";
      }
    }
    TDebugOutputFunctor::operator()(a1, 880, v40);
    goto LABEL_71;
  }
  v39 = *((_DWORD *)a3 + 6);
  if ( v39 != *((_DWORD *)v15 + 6) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      880,
      "Destination resource sample count : %u, and Source resource sample count : %u, but when mode is set to D3D12_RESOL"
      "VE_MODE_DECOMPRESS, sample count of destination resource must be equal to sample count of source resource. ",
      v39,
      *((_DWORD *)v15 + 6));
    v17 = 1;
  }
  if ( *((_DWORD *)a3 + 7) != *((_DWORD *)v15 + 7) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      880,
      "When mode is set to D3D12_RESOLVE_MODE_DECOMPRESS, sample quality of destination resource must be match sample qua"
      "lity of source resource.");
LABEL_71:
    v17 = 1;
  }
LABEL_72:
  v42 = a10;
  if ( !D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::FormatExists(a10) )
  {
    TDebugOutputFunctor::operator()(a1, 878, "The specified format is unrecognized. The value is %u.", v42);
    return 2147942487LL;
  }
  if ( (unsigned int)a11 <= D3D12_RESOLVE_MODE_MAX )
  {
    CD3D11FormatHelper::RenderTargetSupport(
      (unsigned int)v42,
      *((unsigned int *)v13 + 164),
      *((unsigned int *)v13 + 165));
    v49 = CD3D11FormatHelper::DepthStencilTargetSupport((unsigned int)v42, v46, v47, v48);
    if ( v51 != 1 && v51 != -2 && v49 != 1 && v49 != -2 && (unsigned int)(v42 - 21) > 1 && (unsigned int)(v42 - 46) > 1 )
    {
      v52 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v42, v50);
      TDebugOutputFunctor::operator()(
        a1,
        878,
        "The specified format %s does not support MSAA resolve. Only render target and depth stencil fully typed formats "
        "are allowed, except for formats DXGI_FORMAT_R24_UNORM_X8_TYPELESS, DXGI_FORMAT_R32_FLOAT_X8X24_TYPELESS, DXGI_FO"
        "RMAT_X24_TYPELESS_G8_UINT and DXGI_FORMAT_X32_TYPELESS_G8X24_UINT, which are allowed since these have a fully typed component.",
        v52);
      goto LABEL_88;
    }
  }
  else if ( a11 == D3D12_RESOLVE_MODE_AVERAGE )
  {
    v43 = CD3D11FormatHelper::MultisampleResolveSupport(
            (unsigned int)v42,
            *((unsigned int *)v13 + 164),
            *((unsigned int *)v13 + 165));
    if ( v43 != 1 && v43 != -2 && (_DWORD)v42 != 46 && (_DWORD)v42 != 21 )
    {
      v45 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v42, v44);
      TDebugOutputFunctor::operator()(
        a1,
        878,
        "The specified format %s does not support MSAA resolve. Only fully typed non integer and non stencil formats are "
        "allowed, except for formats DXGI_FORMAT_R24_UNORM_X8_TYPELESS and DXGI_FORMAT_R32_FLOAT_X8X24_TYPELESS which are"
        " allowed since these have R fully typed and are non integer.",
        v45);
LABEL_88:
      v17 = 1;
    }
  }
  if ( !v32 )
  {
    v53 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * v42 + 1);
    v54 = *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail + 10 * *((__int16 *)a3 + 9) + 1);
    v55 = 5 * HIWORD(*((_DWORD *)v15 + 4));
    if ( v53 != *((_DWORD *)&D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::s_FormatDetail
                + 10 * ((__int64)*((int *)v15 + 4) >> 16)
                + 1) )
    {
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)(*((int *)v15 + 4) >> 16), v55);
      v57 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v42, v56);
      TDebugOutputFunctor::operator()(
        a1,
        878,
        "The specified format is not compatible with the source resource. Format:%s, Source Resource Format:%s",
        v57,
        v58);
      v17 = 1;
    }
    if ( v53 != v54 )
    {
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)*((__int16 *)a3 + 9), v55);
      v60 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName((enum DXGI_FORMAT)v42, v59);
      TDebugOutputFunctor::operator()(
        a1,
        878,
        "The specified format is not compatible with the destination resource. Format:%s, Destination Resource Format:%s",
        v60,
        v61);
      v17 = 1;
    }
  }
  a7 = 0;
  (*(void (__fastcall **)(_QWORD, __int64, const struct ResourceValidationInfo **))(**((_QWORD **)a2 + 83) + 104LL))(
    *((_QWORD *)a2 + 83),
    18,
    &a7);
  if ( HIDWORD(a7) )
    return v17 != 0 ? 0x80070057 : 0;
  if ( (*((_BYTE *)v15 + 32) & 2) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      934,
      "The source resource is not allowed to have the D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL flag.");
  }
  else if ( (*((_BYTE *)v15 + 32) & 0x40) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      934,
      "The source resource is not allowed to have the D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY flag.");
  }
  else
  {
    if ( *((char *)v15 + 32) >= 0 )
      goto LABEL_102;
    TDebugOutputFunctor::operator()(
      a1,
      934,
      "The source resource is not allowed to have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY flag.");
  }
  v17 = 1;
LABEL_102:
  if ( (*((_BYTE *)a3 + 32) & 2) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      934,
      "The destination resource is not allowed to have the D3D12_RESOURCE_FLAG_ALLOW_DEPTH_STENCIL flag.");
LABEL_108:
    v17 = 1;
    return v17 != 0 ? 0x80070057 : 0;
  }
  if ( (*((_BYTE *)a3 + 32) & 0x40) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      934,
      "The destination resource is not allowed to have the D3D12_RESOURCE_FLAG_VIDEO_DECODE_REFERENCE_ONLY flag.");
    goto LABEL_108;
  }
  if ( *((char *)a3 + 32) < 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      934,
      "The destination resource is not allowed to have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY flag.");
    goto LABEL_108;
  }
  return v17 != 0 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x180236008  mov     [rsp+arg_8], rdx
0x18023600d  push    rbx
0x18023600e  push    rbp
0x18023600f  push    rsi
0x180236010  push    rdi
0x180236011  push    r12
0x180236013  push    r13
0x180236015  push    r14
0x180236017  push    r15
0x180236019  sub     rsp, 38h
0x18023601d  mov     esi, r9d
0x180236020  mov     r15, r8
0x180236023  mov     r13, rdx
0x180236026  mov     rbx, rcx
0x180236029  mov     rbp, [rsp+78h+arg_30]
0x180236031  mov     eax, [rbp+0Ch]
0x180236034  mov     ecx, 0F000000h
0x180236039  and     eax, ecx
0x18023603b  cmp     eax, 3000000h
0x180236040  jnz     short loc_180236060
0x180236042  lea     r8, aTheSourceResou_0; "The source resource cannot be on a D3D1"...
0x180236049  mov     edx, 3B6h
0x18023604e  mov     rcx, rbx
0x180236051  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236056  mov     eax, 80070057h
0x18023605b  jmp     loc_18023670C
0x180236060  mov     eax, [r8+0Ch]
0x180236064  and     eax, ecx
0x180236066  cmp     eax, 2000000h
0x18023606b  jnz     short loc_18023607B
0x18023606d  lea     r8, aTheDestination_4; "The destination resource cannot be on a"...
0x180236074  mov     edx, 3B4h; bool
0x180236079  jmp     short loc_18023604E
0x18023607b  xor     dil, dil
0x18023607e  cmp     [rsp+78h+arg_50], 4
0x180236086  jnz     loc_18023615C
0x18023608c  lea     r14, [rbp+10h]
0x180236090  movsx   ecx, word ptr [r14+2]; enum DXGI_FORMAT
0x180236095  mov     r13d, 4F4h
0x18023609b  cmp     ecx, 3Eh ; '>'
0x18023609e  jz      short loc_1802360C1
0x1802360a0  test    ecx, ecx
0x1802360a2  jz      short loc_1802360C1
0x1802360a4  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1802360a9  mov     r9, rax
0x1802360ac  lea     r8, aWhenEncodingSa_0; "When encoding sampler feedback, the sou"...
0x1802360b3  mov     edx, r13d
0x1802360b6  mov     rcx, rbx
0x1802360b9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802360be  mov     dil, 1
0x1802360c1  lea     rsi, [r15+10h]
0x1802360c5  movsx   ecx, word ptr [rsi+2]; enum DXGI_FORMAT
0x1802360c9  mov     r8d, ecx
0x1802360cc  mov     r12d, 0BDh
0x1802360d2  sub     r8d, r12d
0x1802360d5  jz      short loc_1802360FA
0x1802360d7  cmp     r8d, 1
0x1802360db  jz      short loc_1802360FA
0x1802360dd  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1802360e2  mov     r9, rax
0x1802360e5  lea     r8, aWhenEncodingSa_1; "When encoding sampler feedback, the des"...
0x1802360ec  mov     edx, r13d
0x1802360ef  mov     rcx, rbx
0x1802360f2  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802360f7  mov     dil, 1
0x1802360fa  movsx   eax, word ptr [rsi+2]
0x1802360fe  cmp     eax, r12d
0x180236101  jnz     short loc_18023611E
0x180236103  cmp     byte ptr [rbp+17h], 1
0x180236107  jz      loc_180236205
0x18023610d  movzx   r9d, byte ptr [rbp+17h]
0x180236112  lea     r8, aWhenEncodingMi_0; "When encoding MinMip sampler feedback, "...
0x180236119  jmp     loc_1802361F5
0x18023611e  cmp     eax, 0BEh
0x180236123  jnz     loc_180236205
0x180236129  movzx   ecx, byte ptr [rbp+17h]
0x18023612d  cmp     cl, [r15+17h]
0x180236131  jz      loc_180236205
0x180236137  movzx   eax, byte ptr [r15+17h]
0x18023613c  mov     r9d, ecx
0x18023613f  mov     dword ptr [rsp+78h+var_58], eax
0x180236143  lea     r8, aWhenEncodingMi; "When encoding MipRegionUsed sampler fee"...
0x18023614a  mov     edx, 4F5h
0x18023614f  mov     rcx, rbx
0x180236152  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236157  jmp     loc_180236202
0x18023615c  cmp     [rsp+78h+arg_50], 5
0x180236164  jnz     loc_18023628D
0x18023616a  lea     r14, [rbp+10h]
0x18023616e  movsx   ecx, word ptr [r14+2]; enum DXGI_FORMAT
0x180236173  mov     edx, ecx
0x180236175  mov     r13d, 4F4h
0x18023617b  sub     edx, 0BDh; bool
0x180236181  jz      short loc_1802361A5
0x180236183  cmp     edx, 1
0x180236186  jz      short loc_1802361A5
0x180236188  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x18023618d  mov     r9, rax
0x180236190  lea     r8, aWhenDecodingSa; "When decoding sampler feedback, the sou"...
0x180236197  mov     edx, r13d
0x18023619a  mov     rcx, rbx
0x18023619d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802361a2  mov     dil, 1
0x1802361a5  lea     rsi, [r15+10h]
0x1802361a9  movsx   ecx, word ptr [rsi+2]; enum DXGI_FORMAT
0x1802361ad  cmp     ecx, 3Eh ; '>'
0x1802361b0  jz      short loc_1802361D3
0x1802361b2  test    ecx, ecx
0x1802361b4  jz      short loc_1802361D3
0x1802361b6  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1802361bb  mov     r9, rax
0x1802361be  lea     r8, aWhenDecodingSa_1; "When decoding sampler feedback, the des"...
0x1802361c5  mov     edx, r13d
0x1802361c8  mov     rcx, rbx
0x1802361cb  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802361d0  mov     dil, 1
0x1802361d3  mov     eax, [r14]
0x1802361d6  and     eax, 0FFFF0000h
0x1802361db  cmp     eax, 0BD0000h
0x1802361e0  jnz     short loc_180236205
0x1802361e2  cmp     byte ptr [r15+17h], 1
0x1802361e7  jz      short loc_180236205
0x1802361e9  movzx   r9d, byte ptr [r15+17h]
0x1802361ee  lea     r8, aWhenDecodingMi; "When decoding MinMip sampler feedback, "...
0x1802361f5  mov     edx, 4F5h
0x1802361fa  mov     rcx, rbx
0x1802361fd  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236202  mov     dil, 1
0x180236205  mov     rcx, r15; this
0x180236208  call    ?ArraySize@ResourceValidationInfo@@QEBAGXZ; ResourceValidationInfo::ArraySize(void)
0x18023620d  movzx   edx, ax
0x180236210  mov     rcx, rbp; this
0x180236213  call    ?ArraySize@ResourceValidationInfo@@QEBAGXZ; ResourceValidationInfo::ArraySize(void)
0x180236218  cmp     ax, dx
0x18023621b  jz      short loc_180236234
0x18023621d  lea     r8, aWhenTranscodin; "When transcoding sampler feedback, the "...
0x180236224  mov     edx, 4F6h
0x180236229  mov     rcx, rbx
0x18023622c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236231  mov     dil, 1
0x180236234  mov     eax, [r14]
0x180236237  and     eax, 0FFFF0000h
0x18023623c  mov     ecx, 0BE0000h
0x180236241  cmp     eax, ecx
0x180236243  jz      short loc_180236254
0x180236245  mov     eax, [rsi]
0x180236247  and     eax, 0FFFF0000h
0x18023624c  cmp     eax, ecx
0x18023624e  jnz     loc_1802363D1
0x180236254  movzx   ecx, byte ptr [rbp+17h]
0x180236258  cmp     cl, [r15+17h]
0x18023625c  jz      loc_1802363D1
0x180236262  movzx   eax, byte ptr [r15+17h]
0x180236267  mov     r9d, ecx
0x18023626a  mov     dword ptr [rsp+78h+var_58], eax
0x18023626e  lea     r8, aWhenTranscodin_0; "When transcoding MipRegionUsed sampler "...
0x180236275  mov     edx, 4F5h
0x18023627a  mov     rcx, rbx
0x18023627d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236282  mov     dil, 1
0x180236285  mov     r12b, dil
0x180236288  jmp     loc_1802363D4
0x18023628d  xor     r12b, r12b
0x180236290  mov     eax, [rbp+8]
0x180236293  xor     eax, [r8+8]
0x180236297  test    ecx, eax
0x180236299  jz      short loc_1802362B2
0x18023629b  lea     r8, aTheDimensionsO_9; "The dimensions of the source and destin"...
0x1802362a2  mov     edx, 36Fh
0x1802362a7  mov     rcx, rbx
0x1802362aa  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802362af  mov     dil, 1
0x1802362b2  mov     eax, [r15+14h]
0x1802362b6  mov     edx, 0FFFFFFh
0x1802362bb  and     eax, edx
0x1802362bd  cmp     esi, eax
0x1802362bf  jnb     short loc_1802362CF
0x1802362c1  mov     eax, [rbp+14h]
0x1802362c4  and     eax, edx
0x1802362c6  cmp     [rsp+78h+arg_38], eax
0x1802362cd  jb      short loc_1802362EB
0x1802362cf  lea     r8, aSourceOrDestin; "Source or destination subresource index"...
0x1802362d6  mov     edx, 36Dh
0x1802362db  mov     rcx, rbx
0x1802362de  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802362e3  mov     dil, 1
0x1802362e6  mov     edx, 0FFFFFFh
0x1802362eb  mov     rsi, [rsp+78h+arg_40]
0x1802362f3  test    rsi, rsi
0x1802362f6  jnz     short loc_180236306
0x1802362f8  mov     ecx, [rbp+8]
0x1802362fb  and     ecx, edx
0x1802362fd  mov     r14d, [rbp+0Ch]
0x180236301  and     r14d, edx
0x180236304  jmp     short loc_18023635F
0x180236306  mov     eax, [rsi+8]
0x180236309  cmp     [rsi], eax
0x18023630b  jl      short loc_18023632B
0x18023630d  mov     dword ptr [rsp+78h+var_58], eax
0x180236311  mov     r9d, [rsi]
0x180236314  lea     r8, aPsrcrectLeftUA; "pSrcRect.left = %u and pSrcRect.right ="...
0x18023631b  mov     edx, 41Ah
0x180236320  mov     rcx, rbx
0x180236323  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236328  mov     dil, 1
0x18023632b  mov     eax, [rsi+0Ch]
0x18023632e  mov     r9d, [rsi+4]
0x180236332  cmp     r9d, eax
0x180236335  jl      short loc_180236352
0x180236337  mov     dword ptr [rsp+78h+var_58], eax
0x18023633b  lea     r8, aPsrcrectTopUAn; "pSrcRect.top = %u and pSrcRect.bottom ="...
0x180236342  mov     edx, 41Ah
0x180236347  mov     rcx, rbx
0x18023634a  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18023634f  mov     dil, 1
0x180236352  mov     ecx, [rsi+8]
0x180236355  sub     ecx, [rsi]
0x180236357  mov     r14d, [rsi+0Ch]
0x18023635b  sub     r14d, [rsi+4]
0x18023635f  mov     edx, [r15+8]
0x180236363  mov     esi, 0FFFFFFh
0x180236368  and     edx, esi
0x18023636a  mov     r9d, [rsp+78h+arg_20]
0x180236372  lea     eax, [rcx+r9]
0x180236376  cmp     eax, edx
0x180236378  jbe     short loc_180236399
0x18023637a  mov     [rsp+78h+var_50], edx
0x18023637e  mov     dword ptr [rsp+78h+var_58], ecx
0x180236382  lea     r8, aTheDestination_7; "The destination region extends past the"...
0x180236389  mov     edx, 41Ah
0x18023638e  mov     rcx, rbx
0x180236391  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236396  mov     dil, 1
0x180236399  mov     ecx, [r15+0Ch]
0x18023639d  and     ecx, esi
0x18023639f  mov     r9d, [rsp+78h+arg_28]
0x1802363a7  lea     eax, [r14+r9]
0x1802363ab  cmp     eax, ecx
0x1802363ad  jbe     short loc_1802363DC
0x1802363af  mov     [rsp+78h+var_50], ecx
0x1802363b3  mov     dword ptr [rsp+78h+var_58], r14d
0x1802363b8  lea     r8, aTheDestination_3; "The destination region extends past the"...
0x1802363bf  mov     edx, 41Ah
0x1802363c4  mov     rcx, rbx
0x1802363c7  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802363cc  mov     dil, 1
0x1802363cf  jmp     short loc_1802363DC
0x1802363d1  mov     r12b, 1
0x1802363d4  mov     r13, [rsp+78h+arg_8]
0x1802363dc  xor     r14d, r14d
0x1802363df  cmp     [rsp+78h+arg_50], r14d
0x1802363e7  jnz     short loc_180236433
0x1802363e9  mov     eax, [rbp+18h]
0x1802363ec  mov     r9d, [r15+18h]
0x1802363f0  cmp     r9d, eax
0x1802363f3  jz      short loc_180236410
0x1802363f5  mov     dword ptr [rsp+78h+var_58], eax
0x1802363f9  lea     r8, aDestinationRes_1; "Destination resource sample count : %u,"...
0x180236400  mov     edx, 370h
0x180236405  mov     rcx, rbx
0x180236408  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18023640d  mov     dil, 1
0x180236410  mov     eax, [rbp+1Ch]
0x180236413  cmp     [r15+1Ch], eax
0x180236417  jz      loc_1802364AD
0x18023641d  lea     r8, aWhenModeIsSetT; "When mode is set to D3D12_RESOLVE_MODE_"...
0x180236424  mov     edx, 370h
0x180236429  mov     rcx, rbx
0x18023642c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180236431  jmp     short loc_1802364AA
0x180236433  cmp     [rsp+78h+arg_50], 4
0x18023643b  jnz     short loc_18023645B
0x18023643d  mov     r9d, [rbp+18h]
0x180236441  lea     rax, [rbp+1Ch]
0x180236445  cmp     r9d, 1
0x180236449  ja      short loc_180236450
0x18023644b  cmp     [rax], r14d
0x18023644e  jz      short loc_1802364AD
0x180236450  mov     eax, [rax]
0x180236452  lea     r8, aWhenEncodingSa; "When encoding sampler feedback, the sou"...
0x180236459  jmp     short loc_180236499
0x18023645b  mov     r9d, [r15+18h]
0x18023645f  cmp     [rsp+78h+arg_50], 5
0x180236467  jnz     short loc_180236483
0x180236469  lea     rax, [r15+1Ch]
0x18023646d  cmp     r9d, 1
0x180236471  ja      short loc_180236478
0x180236473  cmp     [rax], r14d
0x180236476  jz      short loc_1802364AD
0x180236478  mov     eax, [rax]
0x18023647a  lea     r8, aWhenDecodingSa_0; "When decoding sampler feedback, the des"...
0x180236481  jmp     short loc_180236499
0x180236483  cmp     r9d, 1
0x180236487  jnz     short loc_18023648F
0x180236489  cmp     dword ptr [rbp+18h], 2
0x18023648d  jnb     short loc_1802364AD
0x18023648f  mov     eax, [rbp+18h]
0x180236492  lea     r8, aDestinationRes; "Destination resource sample count: %u, "...
0x180236499  mov     dword ptr [rsp+78h+var_58], eax
0x18023649d  mov     edx, 370h
  ... truncated ...
```
