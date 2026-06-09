# ValidateVideoProcessFramesLUTCompound(TDebugOutputFunctor &,D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE const &,D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1 const &,D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2 const &,D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT1 const &,uint)

- ea: `0x180248c18`
- end: `0x180249188`
- name: `?ValidateVideoProcessFramesLUTCompound@@YAJAEAUTDebugOutputFunctor@@AEBUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@AEBUD3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1@@AEBUD3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2@@AEBUD3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT1@@I@Z`
- size: `1392`
- prototype: `__int64 __fastcall(struct TDebugOutputFunctor *, const struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *, const struct D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1 *, const struct D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2 *, const struct D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT1 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180247794`

## callees

- `0x180025550`
- `0x18002ef50`
- `0x18005f00c`
- `0x1800f4320`
- `0x180248c18`
- `0x18025cda8`

## string_xrefs

- `0x180248cb9`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode::Configuration::UpsampledChromaInput must match with the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.`
- `0x180248c92`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode - Must enable D3D12_VIDEO_PROCESS_LUT_TRANSFORM_CONFIGURATION_FLAG_ENABLE in the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.`
- `0x180248c6a`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC[%d]::ColorSpace Must be DXGI_COLOR_SPACE_CUSTOM when enabling D3D12_VIDEO_PROCESS_LUT_TRANSFORM_CONFIGURATION_FLAG_ENABLE.`
- `0x180248fc3`: `When D3D12_FEATURE_VIDEO_ARCHITECTURE::IOCoherent is false, D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2::LUTMode.p1DLUTtransform must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM.  For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180249028`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode::Configuration::Dimension3DLUT must match with the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.`
- `0x180248f29`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTtransform must have a format that matches with D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format1DLUT.`
- `0x180248efd`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.ColorSpace3DLUTOutput must match with the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.`
- `0x180248ed1`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format3DLUT must match with the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.`
- `0x180248ea8`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format1DLUT must match with the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.`
- `0x180248dd2`: `When D3D12_FEATURE_VIDEO_ARCHITECTURE::IOCoherent is false, D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2::LUTMode.p1DLUTInputSpacing must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM.  For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180249156`: `When D3D12_FEATURE_VIDEO_ARCHITECTURE::IOCoherent is false, D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2::LUTMode.p3DLUTTransform must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM.  For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180249058`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode::Configuration::Interpolation3DLUT must match with the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.`
- `0x1802490db`: `D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p3DLUTTransform must have a format that matches with flag D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format3DLUT.`

## pseudocode

```c
__int64 __fastcall ValidateVideoProcessFramesLUTCompound(
        struct TDebugOutputFunctor *a1,
        struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *a2,
        const struct D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1 *a3,
        const struct D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2 *a4,
        const struct D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT1 *a5,
        unsigned int a6)
{
  unsigned int v6; // ebx
  bool v7; // zf
  __int64 v11; // rcx
  __int64 v12; // r15
  unsigned int v13; // r12d
  __int64 v14; // rcx
  __int64 v15; // r15
  unsigned int v16; // r12d
  __int64 v17; // rcx
  CResource *v18; // r15
  __int64 v19; // rcx
  const struct D3D12_FEATURE_DATA_VIDEO_PROCESS_SUPPORT1 *v21; // [rsp+30h] [rbp-50h] BYREF
  struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *v22; // [rsp+38h] [rbp-48h]
  struct D3D12_RESOURCE_DESC v23; // [rsp+40h] [rbp-40h] BYREF

  v6 = 0;
  v7 = (*((_BYTE *)a4 + 320) & 1) == 0;
  v22 = a2;
  v21 = a5;
  if ( v7 )
    return v6;
  if ( *((_DWORD *)a3 + 1) != -1 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC[%d]::ColorSpace Must be DXGI_COLOR_SPACE_CUSTOM when enabling D3D12_VIDEO_PR"
      "OCESS_LUT_TRANSFORM_CONFIGURATION_FLAG_ENABLE.",
      a6);
    v6 = -2147024809;
  }
  if ( (*((_BYTE *)a4 + 320) & 1) != 0 && (*((_BYTE *)a3 + 112) & 1) == 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode - Must enable D3D12_VIDEO_PROCESS_LUT_TRANSFORM_CONFIGURA"
      "TION_FLAG_ENABLE in the associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.",
      a6);
    v6 = -2147024809;
  }
  if ( *((_DWORD *)a4 + 81) != *((_DWORD *)a3 + 29) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode::Configuration::UpsampledChromaInput must match with the "
      "associated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.",
      a6);
    v6 = -2147024809;
  }
  v11 = *((_QWORD *)a4 + 52);
  if ( !v11 )
    goto LABEL_26;
  if ( (*((_BYTE *)a5 + 620) & 2) == 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTInputSpacing must have a null resource when D3D12_V"
      "IDEO_PROCESS_LUT_SUPPORT_FLAG_1DLUT_SPACING_CURVE not supported.",
      a6);
LABEL_12:
    v6 = -2147024809;
    goto LABEL_26;
  }
  v12 = QIFrom<CResource>(v11);
  CResource::GetDesc((CResource *)v12, &v23);
  v13 = *((_DWORD *)a4 + 102);
  if ( v23.Format != DXGI_FORMAT_R16_FLOAT )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTInputSpacing must have a resource Format DXGI_FORMAT_R16_FLOAT.",
      a6);
    v6 = -2147024809;
  }
  if ( v23.Width != *((_DWORD *)v21 + 156) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTInputSpacing must have a resource Width (%d) matchi"
      "ng Native1DLUTSize (%d).",
      a6,
      LODWORD(v23.Width),
      *((_DWORD *)v21 + 156));
    v6 = -2147024809;
  }
  if ( v23.Dimension != D3D12_RESOURCE_DIMENSION_TEXTURE1D )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTInputSpacing must have a resource dimension of D3D1"
      "2_RESOURCE_DIMENSION_TEXTURE1D.",
      a6);
    v6 = -2147024809;
  }
  if ( *(_BYTE *)(v12 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTInputSpacing must not be a reserved resource.",
      a6);
  }
  else
  {
    if ( IsVideoHeapTypeSupported(v22, (struct CResource *)v12) )
      goto LABEL_24;
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "When D3D12_FEATURE_VIDEO_ARCHITECTURE::IOCoherent is false, D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2::LUTMode.p"
      "1DLUTInputSpacing must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD,"
      " or D3D12_HEAP_TYPE_CUSTOM.  For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPE"
      "RTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
  }
  v6 = -2147024809;
LABEL_24:
  if ( v13 >= (*(_DWORD *)(v12 + 244) & 0xFFFFFFu) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Subresource (%d) exceeds the number of subresources (%d) "
      "for the associated resource.",
      a6,
      v13,
      *(_DWORD *)(v12 + 244) & 0xFFFFFF);
    goto LABEL_12;
  }
LABEL_26:
  v14 = *((_QWORD *)a4 + 50);
  if ( !v14 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTtransform must have a non-null resource.",
      a6);
LABEL_28:
    v6 = -2147024809;
    goto LABEL_50;
  }
  v15 = QIFrom<CResource>(v14);
  CResource::GetDesc((CResource *)v15, &v23);
  v16 = *((_DWORD *)a4 + 102);
  if ( (v23.Flags & 0x800) == 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTTransform must have a resource with flag D3D12_RESO"
      "URCE_FLAG_VIDEO_PROCESS_1DLUT_ONLY.",
      a6);
    v6 = -2147024809;
  }
  if ( *((_DWORD *)a3 + 30) != *((_DWORD *)a4 + 82) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format1DLUT must match with the associated "
      "video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.",
      a6);
    v6 = -2147024809;
  }
  if ( *((_DWORD *)a3 + 31) != *((_DWORD *)a4 + 83) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format3DLUT must match with the associated "
      "video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.",
      a6);
    v6 = -2147024809;
  }
  if ( *((_DWORD *)a3 + 32) != *((_DWORD *)a4 + 84) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.ColorSpace3DLUTOutput must match with the a"
      "ssociated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.",
      a6);
    v6 = -2147024809;
  }
  if ( v23.Format != *((_DWORD *)a4 + 82) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTtransform must have a format that matches with D3D1"
      "2_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format1DLUT.",
      a6,
      a6);
    v6 = -2147024809;
  }
  if ( v23.Width != *((_DWORD *)v21 + 156) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTtransform must have a resource Width matching Native1DLUTSize.",
      a6);
    v6 = -2147024809;
  }
  if ( v23.Dimension != D3D12_RESOURCE_DIMENSION_TEXTURE1D )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTtransform must have a resource dimension of D3D12_R"
      "ESOURCE_DIMENSION_TEXTURE1D.",
      a6);
    v6 = -2147024809;
  }
  if ( *(_BYTE *)(v15 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p1DLUTtransform must not be a reserved resource.",
      a6);
  }
  else
  {
    if ( IsVideoHeapTypeSupported(v22, (struct CResource *)v15) )
      goto LABEL_48;
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "When D3D12_FEATURE_VIDEO_ARCHITECTURE::IOCoherent is false, D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2::LUTMode.p"
      "1DLUTtransform must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or"
      " D3D12_HEAP_TYPE_CUSTOM.  For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY"
      "_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
  }
  v6 = -2147024809;
LABEL_48:
  if ( v16 >= (*(_DWORD *)(v15 + 244) & 0xFFFFFFu) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Subresource exceeds the number of subresources for the as"
      "sociated resource.",
      a6);
    goto LABEL_28;
  }
LABEL_50:
  if ( *((_DWORD *)a4 + 86) != *((_DWORD *)a3 + 34) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode::Configuration::Dimension3DLUT must match with the associ"
      "ated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.",
      a6);
    v6 = -2147024809;
  }
  if ( *((_DWORD *)a4 + 85) != *((_DWORD *)a3 + 33) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode::Configuration::Interpolation3DLUT must match with the as"
      "sociated video processor D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC1.",
      a6);
    v6 = -2147024809;
  }
  v17 = *((_QWORD *)a4 + 54);
  if ( !v17 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p3DLUTTransform must have a non-null resource.",
      a6);
    return (unsigned int)-2147024809;
  }
  v18 = (CResource *)QIFrom<CResource>(v17);
  CResource::GetDesc(v18, &v23);
  if ( (v23.Flags & 0x200) == 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p3DLUTTransform must have a resource with flag D3D12_RESO"
      "URCE_FLAG_VIDEO_PROCESS_3DLUT_ONLY.",
      a6);
    v6 = -2147024809;
  }
  if ( v23.Format != *((_DWORD *)a4 + 83) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p3DLUTTransform must have a format that matches with flag"
      " D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.Configuration.Format3DLUT.",
      a6,
      a6);
    v6 = -2147024809;
  }
  v19 = *((unsigned int *)a4 + 86);
  LODWORD(v21) = 0;
  if ( (int)GetExpected3DLUTSize(v19, &v21) < 0 )
    return 2147942487LL;
  if ( v23.Height != (_DWORD)v21 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p3DLUTTransform must have a resource Width=Height=Depth m"
      "atching D3D12_VIDEO_PROCESS_3DLUT_TABLE_DIMENSION.",
      a6);
    v6 = -2147024809;
  }
  if ( *((_BYTE *)v18 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2[%d]::LUTMode.p3DLUTTransform must not be a reserved resource.",
      a6);
    return (unsigned int)-2147024809;
  }
  if ( !IsVideoHeapTypeSupported(v22, v18) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1113,
      "When D3D12_FEATURE_VIDEO_ARCHITECTURE::IOCoherent is false, D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS2::LUTMode.p"
      "3DLUTTransform must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or"
      " D3D12_HEAP_TYPE_CUSTOM.  For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY"
      "_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180248c18  mov     [rsp-38h+arg_8], rbx
0x180248c1d  push    rbp
0x180248c1e  push    rsi
0x180248c1f  push    rdi
0x180248c20  push    r12
0x180248c22  push    r13
0x180248c24  push    r14
0x180248c26  push    r15
0x180248c28  mov     rbp, rsp
0x180248c2b  sub     rsp, 80h
0x180248c32  mov     r15, [rbp+arg_20]
0x180248c36  xor     ebx, ebx
0x180248c38  test    byte ptr [r9+140h], 1
0x180248c40  mov     r14, r9
0x180248c43  mov     r13, r8
0x180248c46  mov     [rbp+var_48], rdx
0x180248c4a  mov     rdi, rcx
0x180248c4d  mov     [rbp+var_50], r15
0x180248c51  jz      loc_18024916B
0x180248c57  cmp     dword ptr [r8+4], 0FFFFFFFFh
0x180248c5c  mov     r12d, 80070057h
0x180248c62  mov     esi, [rbp+arg_28]
0x180248c65  jz      short loc_180248C7E
0x180248c67  mov     r9d, esi
0x180248c6a  lea     r8, aD3d12VideoProc; "D3D12_VIDEO_PROCESS_INPUT_STREAM_DESC[%"...
0x180248c71  mov     edx, 459h
0x180248c76  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248c7b  mov     ebx, r12d
0x180248c7e  test    byte ptr [r14+140h], 1
0x180248c86  jz      short loc_180248CA9
0x180248c88  test    byte ptr [r13+70h], 1
0x180248c8d  jnz     short loc_180248CA9
0x180248c8f  mov     r9d, esi
0x180248c92  lea     r8, aD3d12VideoProc_48; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248c99  mov     edx, 459h
0x180248c9e  mov     rcx, rdi
0x180248ca1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248ca6  mov     ebx, r12d
0x180248ca9  mov     eax, [r13+74h]
0x180248cad  cmp     [r14+144h], eax
0x180248cb4  jz      short loc_180248CD0
0x180248cb6  mov     r9d, esi
0x180248cb9  lea     r8, aD3d12VideoProc_25; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248cc0  mov     edx, 459h
0x180248cc5  mov     rcx, rdi
0x180248cc8  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248ccd  mov     ebx, r12d
0x180248cd0  mov     rcx, [r14+1A0h]
0x180248cd7  test    rcx, rcx
0x180248cda  jz      loc_180248E2D
0x180248ce0  test    byte ptr [r15+26Ch], 2
0x180248ce8  jnz     short loc_180248D09
0x180248cea  mov     r9d, esi
0x180248ced  lea     r8, aD3d12VideoProc_33; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248cf4  mov     edx, 459h
0x180248cf9  mov     rcx, rdi
0x180248cfc  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248d01  mov     ebx, r12d
0x180248d04  jmp     loc_180248E2D
0x180248d09  call    ??$QIFrom@VCResource@@@@YAPEAVCResource@@PEAUIUnknown@@AEBU_GUID@@W4ERefType@@@Z; QIFrom<CResource>(IUnknown *,_GUID const &,ERefType)
0x180248d0e  lea     rdx, [rbp+var_40]; retstr
0x180248d12  mov     rcx, rax; this
0x180248d15  mov     r15, rax
0x180248d18  call    ?GetDesc@CResource@@UEAA?AUD3D12_RESOURCE_DESC@@XZ; CResource::GetDesc(void)
0x180248d1d  cmp     [rbp+var_40.Format], 36h ; '6'
0x180248d21  mov     r12d, [r14+198h]
0x180248d28  jz      short loc_180248D46
0x180248d2a  mov     r9d, esi
0x180248d2d  lea     r8, aD3d12VideoProc_24; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248d34  mov     edx, 459h
0x180248d39  mov     rcx, rdi
0x180248d3c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248d41  mov     ebx, 80070057h
0x180248d46  mov     rax, [rbp+var_50]
0x180248d4a  mov     rcx, [rbp+var_40.Width]
0x180248d4e  mov     eax, [rax+270h]
0x180248d54  cmp     rcx, rax
0x180248d57  jz      short loc_180248D7D
0x180248d59  mov     [rsp+80h+var_58], eax
0x180248d5d  lea     r8, aD3d12VideoProc_26; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248d64  mov     [rsp+80h+var_60], ecx
0x180248d68  mov     r9d, esi
0x180248d6b  mov     rcx, rdi
0x180248d6e  mov     edx, 459h
0x180248d73  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248d78  mov     ebx, 80070057h
0x180248d7d  cmp     [rbp+var_40.Dimension], 2
0x180248d81  jz      short loc_180248D9F
0x180248d83  mov     r9d, esi
0x180248d86  lea     r8, aD3d12VideoProc_7; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248d8d  mov     edx, 459h
0x180248d92  mov     rcx, rdi
0x180248d95  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248d9a  mov     ebx, 80070057h
0x180248d9f  cmp     byte ptr [r15+188h], 3
0x180248da7  jnz     short loc_180248DC2
0x180248da9  mov     r9d, esi
0x180248dac  lea     r8, aD3d12VideoProc_12; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248db3  mov     edx, 459h
0x180248db8  mov     rcx, rdi
0x180248dbb  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248dc0  jmp     short loc_180248DE6
0x180248dc2  mov     rcx, [rbp+var_48]; struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *
0x180248dc6  mov     rdx, r15; struct CResource *
0x180248dc9  call    ?IsVideoHeapTypeSupported@@YA_NAEBUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEAVCResource@@@Z; IsVideoHeapTypeSupported(D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE const &,CResource *)
0x180248dce  test    al, al
0x180248dd0  jnz     short loc_180248DEB
0x180248dd2  lea     r8, aWhenD3d12Featu_2; "When D3D12_FEATURE_VIDEO_ARCHITECTURE::"...
0x180248dd9  mov     edx, 459h
0x180248dde  mov     rcx, rdi
0x180248de1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248de6  mov     ebx, 80070057h
0x180248deb  mov     eax, [r15+0F4h]
0x180248df2  and     eax, 0FFFFFFh
0x180248df7  cmp     r12d, eax
0x180248dfa  jb      short loc_180248E27
0x180248dfc  mov     [rsp+80h+var_58], eax
0x180248e00  lea     r8, aD3d12VideoProc_0; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248e07  mov     r9d, esi
0x180248e0a  mov     [rsp+80h+var_60], r12d
0x180248e0f  mov     edx, 459h
0x180248e14  mov     rcx, rdi
0x180248e17  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248e1c  mov     r12d, 80070057h
0x180248e22  jmp     loc_180248D01
0x180248e27  mov     r12d, 80070057h
0x180248e2d  mov     rcx, [r14+190h]
0x180248e34  test    rcx, rcx
0x180248e37  jnz     short loc_180248E58
0x180248e39  mov     r9d, esi
0x180248e3c  lea     r8, aD3d12VideoProc_15; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248e43  mov     edx, 459h
0x180248e48  mov     rcx, rdi
0x180248e4b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248e50  mov     ebx, r12d
0x180248e53  jmp     loc_180249015
0x180248e58  call    ??$QIFrom@VCResource@@@@YAPEAVCResource@@PEAUIUnknown@@AEBU_GUID@@W4ERefType@@@Z; QIFrom<CResource>(IUnknown *,_GUID const &,ERefType)
0x180248e5d  lea     rdx, [rbp+var_40]; retstr
0x180248e61  mov     rcx, rax; this
0x180248e64  mov     r15, rax
0x180248e67  call    ?GetDesc@CResource@@UEAA?AUD3D12_RESOURCE_DESC@@XZ; CResource::GetDesc(void)
0x180248e6c  test    [rbp+var_40.Flags], 800h
0x180248e73  mov     r12d, [r14+198h]
0x180248e7a  jnz     short loc_180248E98
0x180248e7c  mov     r9d, esi
0x180248e7f  lea     r8, aD3d12VideoProc_30; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248e86  mov     edx, 459h
0x180248e8b  mov     rcx, rdi
0x180248e8e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248e93  mov     ebx, 80070057h
0x180248e98  mov     eax, [r14+148h]
0x180248e9f  cmp     [r13+78h], eax
0x180248ea3  jz      short loc_180248EC1
0x180248ea5  mov     r9d, esi
0x180248ea8  lea     r8, aD3d12VideoProc_16; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248eaf  mov     edx, 459h
0x180248eb4  mov     rcx, rdi
0x180248eb7  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248ebc  mov     ebx, 80070057h
0x180248ec1  mov     eax, [r14+14Ch]
0x180248ec8  cmp     [r13+7Ch], eax
0x180248ecc  jz      short loc_180248EEA
0x180248ece  mov     r9d, esi
0x180248ed1  lea     r8, aD3d12VideoProc_10; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248ed8  mov     edx, 459h
0x180248edd  mov     rcx, rdi
0x180248ee0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248ee5  mov     ebx, 80070057h
0x180248eea  mov     eax, [r14+150h]
0x180248ef1  cmp     [r13+80h], eax
0x180248ef8  jz      short loc_180248F16
0x180248efa  mov     r9d, esi
0x180248efd  lea     r8, aD3d12VideoProc_23; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248f04  mov     edx, 459h
0x180248f09  mov     rcx, rdi
0x180248f0c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248f11  mov     ebx, 80070057h
0x180248f16  mov     eax, [r14+148h]
0x180248f1d  cmp     [rbp+var_40.Format], eax
0x180248f20  jz      short loc_180248F42
0x180248f22  mov     r9d, esi
0x180248f25  mov     [rsp+80h+var_60], esi
0x180248f29  lea     r8, aD3d12VideoProc_43; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248f30  mov     edx, 459h
0x180248f35  mov     rcx, rdi
0x180248f38  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248f3d  mov     ebx, 80070057h
0x180248f42  mov     rax, [rbp+var_50]
0x180248f46  mov     eax, [rax+270h]
0x180248f4c  cmp     [rbp+var_40.Width], rax
0x180248f50  jz      short loc_180248F6E
0x180248f52  mov     r9d, esi
0x180248f55  lea     r8, aD3d12VideoProc_4; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248f5c  mov     edx, 459h
0x180248f61  mov     rcx, rdi
0x180248f64  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248f69  mov     ebx, 80070057h
0x180248f6e  cmp     [rbp+var_40.Dimension], 2
0x180248f72  jz      short loc_180248F90
0x180248f74  mov     r9d, esi
0x180248f77  lea     r8, aD3d12VideoProc_29; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248f7e  mov     edx, 459h
0x180248f83  mov     rcx, rdi
0x180248f86  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248f8b  mov     ebx, 80070057h
0x180248f90  cmp     byte ptr [r15+188h], 3
0x180248f98  jnz     short loc_180248FB3
0x180248f9a  mov     r9d, esi
0x180248f9d  lea     r8, aD3d12VideoProc_9; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248fa4  mov     edx, 459h
0x180248fa9  mov     rcx, rdi
0x180248fac  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248fb1  jmp     short loc_180248FD7
0x180248fb3  mov     rcx, [rbp+var_48]; struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *
0x180248fb7  mov     rdx, r15; struct CResource *
0x180248fba  call    ?IsVideoHeapTypeSupported@@YA_NAEBUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEAVCResource@@@Z; IsVideoHeapTypeSupported(D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE const &,CResource *)
0x180248fbf  test    al, al
0x180248fc1  jnz     short loc_180248FDC
0x180248fc3  lea     r8, aWhenD3d12Featu_3; "When D3D12_FEATURE_VIDEO_ARCHITECTURE::"...
0x180248fca  mov     edx, 459h
0x180248fcf  mov     rcx, rdi
0x180248fd2  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180248fd7  mov     ebx, 80070057h
0x180248fdc  mov     eax, [r15+0F4h]
0x180248fe3  and     eax, 0FFFFFFh
0x180248fe8  cmp     r12d, eax
0x180248feb  jb      short loc_18024900F
0x180248fed  mov     r9d, esi
0x180248ff0  lea     r8, aD3d12VideoProc_5; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180248ff7  mov     edx, 459h
0x180248ffc  mov     rcx, rdi
0x180248fff  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180249004  mov     r12d, 80070057h
0x18024900a  jmp     loc_180248E50
0x18024900f  mov     r12d, 80070057h
0x180249015  mov     eax, [r13+88h]
0x18024901c  cmp     [r14+158h], eax
0x180249023  jz      short loc_18024903F
0x180249025  mov     r9d, esi
0x180249028  lea     r8, aD3d12VideoProc_37; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x18024902f  mov     edx, 459h
0x180249034  mov     rcx, rdi
0x180249037  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024903c  mov     ebx, r12d
0x18024903f  mov     eax, [r13+84h]
0x180249046  mov     r13d, 459h
0x18024904c  cmp     [r14+154h], eax
0x180249053  jz      short loc_18024906D
0x180249055  mov     r9d, esi
0x180249058  lea     r8, aD3d12VideoProc_13; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x18024905f  mov     edx, r13d
0x180249062  mov     rcx, rdi
0x180249065  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024906a  mov     ebx, r12d
0x18024906d  mov     rcx, [r14+1B0h]
0x180249074  test    rcx, rcx
0x180249077  jnz     short loc_180249093
0x180249079  lea     r8, aD3d12VideoProc_3; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180249080  mov     r9d, esi
0x180249083  mov     edx, r13d
0x180249086  mov     rcx, rdi
0x180249089  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024908e  jmp     loc_180249168
0x180249093  call    ??$QIFrom@VCResource@@@@YAPEAVCResource@@PEAUIUnknown@@AEBU_GUID@@W4ERefType@@@Z; QIFrom<CResource>(IUnknown *,_GUID const &,ERefType)
0x180249098  lea     rdx, [rbp+var_40]; retstr
0x18024909c  mov     rcx, rax; this
0x18024909f  mov     r15, rax
0x1802490a2  call    ?GetDesc@CResource@@UEAA?AUD3D12_RESOURCE_DESC@@XZ; CResource::GetDesc(void)
0x1802490a7  test    [rbp+var_40.Flags], 200h
0x1802490ae  jnz     short loc_1802490C8
0x1802490b0  mov     r9d, esi
0x1802490b3  lea     r8, aD3d12VideoProc_1; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x1802490ba  mov     edx, r13d
0x1802490bd  mov     rcx, rdi
0x1802490c0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802490c5  mov     ebx, r12d
0x1802490c8  mov     eax, [r14+14Ch]
0x1802490cf  cmp     [rbp+var_40.Format], eax
0x1802490d2  jz      short loc_1802490F0
0x1802490d4  mov     r9d, esi
0x1802490d7  mov     [rsp+80h+var_60], esi
0x1802490db  lea     r8, aD3d12VideoProc_11; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x1802490e2  mov     edx, r13d
0x1802490e5  mov     rcx, rdi
0x1802490e8  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802490ed  mov     ebx, r12d
0x1802490f0  mov     ecx, [r14+158h]
0x1802490f7  lea     rdx, [rbp+var_50]
0x1802490fb  mov     dword ptr [rbp+var_50], 0
0x180249102  call    ?GetExpected3DLUTSize@@YAIW4D3D12_VIDEO_PROCESS_3DLUT_TABLE_DIMENSION@@AEAI@Z; GetExpected3DLUTSize(D3D12_VIDEO_PROCESS_3DLUT_TABLE_DIMENSION,uint &)
0x180249107  test    eax, eax
0x180249109  jns     short loc_180249110
0x18024910b  mov     eax, r12d
0x18024910e  jmp     short loc_18024916D
0x180249110  mov     eax, dword ptr [rbp+var_50]
0x180249113  cmp     [rbp+var_40.Height], eax
0x180249116  jz      short loc_180249130
0x180249118  mov     r9d, esi
0x18024911b  lea     r8, aD3d12VideoProc_27; "D3D12_VIDEO_PROCESS_INPUT_STREAM_ARGUME"...
0x180249122  mov     edx, r13d
  ... truncated ...
```
