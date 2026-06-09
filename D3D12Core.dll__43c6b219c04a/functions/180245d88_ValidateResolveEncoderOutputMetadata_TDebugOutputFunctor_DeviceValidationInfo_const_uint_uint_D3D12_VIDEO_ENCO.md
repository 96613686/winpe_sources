# ValidateResolveEncoderOutputMetadata(TDebugOutputFunctor &,DeviceValidationInfo const &,uint,uint,D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1 const *,D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1 const *)

- ea: `0x180245d88`
- end: `0x18024654d`
- name: `?ValidateResolveEncoderOutputMetadata@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@IIPEBUD3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1@@PEBUD3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1@@@Z`
- size: `1989`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, const struct DeviceValidationInfo *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1 *, const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18023ea08`

## callees

- `0x180025550`
- `0x18002ef50`
- `0x18005f00c`
- `0x1800bb480`
- `0x1800bc094`
- `0x180124e00`
- `0x180125b4c`
- `0x180125eec`
- `0x18023ad00`
- `0x180245d88`
- `0x18025cda8`
- `0x180262020`

## string_xrefs

- `0x180245df3`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments cannot be null.`
- `0x180245ddd`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pInputArguments cannot be null.`
- `0x180245e34`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->ResolvedLayoutMetadata.pBuffer cannot be null.`
- `0x180245e12`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pInputArguments->HWLayoutMetadata.pBuffer cannot be null.`
- `0x180246038`: `The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS.HWLayoutMetadata.pBuffer must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x1802461a0`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_PROFILE_LEVEL,...) for the given input returned failure or profile not supported.`
- `0x1802460f4`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_CODEC,...) for the given input returned failure or not supported.`
- `0x180245fa4`: `The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS.ResolvedLayoutMetadata.pBuffer must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180245f13`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata Failure on call to CheckFeatureSupport(D3D12_FEATURE_VIDEO_ARCHITECTURE,...).`
- `0x180245ed4`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->ResolvedSubregionsPSNRData.pBuffer cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_SUBREGIONS_PSNR enabled.`
- `0x180245e74`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->pOutputSATDMap cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_SATD_MAP enabled.`
- `0x180245e54`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->pOutputQPMap cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_QP_MAP enabled.`
- `0x180245eb4`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->ResolvedFramePSNRData.pBuffer cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_FRAME_PSNR enabled.`
- `0x180245e94`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->pOutputBitAllocationMap cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_RC_BIT_ALLOCATION_MAP enabled.`
- `0x1802464b6`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments warning - Buffer offset alignment for HWLayoutMetadata.pBuffer specified in InputArguments.HWLayoutMetadata.Offset is different than advised in encoder caps. Current buffer offset: %d Required alignment reported: %d`
- `0x180246259`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - EncodedPictureEffectiveResolution does not satisfy the constraints specified in CheckFeatureSupport - D3D12_FEATURE_VIDEO_ENCODER_OUTPUT_RESOLUTION.`
- `0x180246220`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_INPUT_FORMAT,...) for the given input returned failure or not supported.`
- `0x18024650c`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_RESOURCE_REQUIREMENTS1,...) for the given input returned failure or not supported.`
- `0x1802464ec`: `ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments warning - Buffer offset alignment for ResolvedLayoutMetadata.pBuffer specified in OutputArguments.ResolvedLayoutMetadata.Offset is different than advised in encoder caps. Current buffer offset: %d Required alignment reported: %d`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall ValidateResolveEncoderOutputMetadata(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        __int64 a3,
        int a4,
        const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1 *a5,
        const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1 *a6)
{
  char v8; // r15
  char v9; // r12
  int *v10; // r13
  CResource *v11; // r15
  CResource *v12; // r15
  unsigned int v14; // eax
  char v15; // di
  __int64 *v16; // rax
  __int64 v17; // rcx
  int v18; // edx
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  unsigned int v21; // r8d
  unsigned __int64 v22; // r9
  struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE v23; // [rsp+50h] [rbp-168h] BYREF
  unsigned int v24; // [rsp+54h] [rbp-164h]
  int v25; // [rsp+58h] [rbp-160h] BYREF
  int v26; // [rsp+5Ch] [rbp-15Ch] BYREF
  struct DeviceValidationInfo *v27; // [rsp+60h] [rbp-158h]
  __int128 v28; // [rsp+68h] [rbp-150h] BYREF
  __int64 v29; // [rsp+78h] [rbp-140h] BYREF
  __int64 v30; // [rsp+80h] [rbp-138h] BYREF
  _DWORD v31[2]; // [rsp+88h] [rbp-130h] BYREF
  __int128 v32; // [rsp+90h] [rbp-128h]
  int v33; // [rsp+A0h] [rbp-118h]
  int v34; // [rsp+A4h] [rbp-114h]
  _DWORD v35[2]; // [rsp+B0h] [rbp-108h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-100h]
  int v37; // [rsp+C8h] [rbp-F0h]
  __int64 v38; // [rsp+CCh] [rbp-ECh]
  int v39; // [rsp+D4h] [rbp-E4h]
  unsigned int v40; // [rsp+DCh] [rbp-DCh]
  int v41; // [rsp+E4h] [rbp-D4h]
  __int128 v42; // [rsp+E8h] [rbp-D0h]
  int v43; // [rsp+F8h] [rbp-C0h]
  int v44; // [rsp+FCh] [rbp-BCh]
  int v45; // [rsp+100h] [rbp-B8h]
  int v46; // [rsp+104h] [rbp-B4h]
  int v47; // [rsp+108h] [rbp-B0h]
  int v48; // [rsp+10Ch] [rbp-ACh]
  int v49; // [rsp+118h] [rbp-A0h]
  struct D3D12_RESOURCE_DESC v50; // [rsp+128h] [rbp-90h] BYREF
  _DWORD v51[2]; // [rsp+160h] [rbp-58h] BYREF
  int v52; // [rsp+168h] [rbp-50h]

  v25 = a4;
  v27 = a2;
  v8 = 1;
  v9 = 0;
  if ( !a5 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pInputArguments cannot be null.");
    v8 = 0;
  }
  if ( !a6 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments cannot be null.");
    v8 = 0;
  }
  if ( a5 && !*((_QWORD *)a5 + 5) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pInputArguments->HWLayoutMe"
      "tadata.pBuffer cannot be null.");
    v8 = 0;
  }
  if ( a6 )
  {
    if ( !*(_QWORD *)a6 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1307,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->Resolve"
        "dLayoutMetadata.pBuffer cannot be null.");
      v8 = 0;
    }
    if ( !*((_QWORD *)a6 + 2) && (*((_BYTE *)a5 + 56) & 1) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1307,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->pOutput"
        "QPMap cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_QP_MAP enabled.");
      v8 = 0;
    }
    if ( !*((_QWORD *)a6 + 3) && (*((_BYTE *)a5 + 56) & 2) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1307,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->pOutput"
        "SATDMap cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_SATD_MAP enabled.");
      v8 = 0;
    }
    if ( !*((_QWORD *)a6 + 4) && (*((_BYTE *)a5 + 56) & 4) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1307,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->pOutput"
        "BitAllocationMap cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_RC_BIT_ALLOCATION_MAP enabled.");
      v8 = 0;
    }
    if ( !*((_QWORD *)a6 + 5) && (*((_BYTE *)a5 + 56) & 8) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1307,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->Resolve"
        "dFramePSNRData.pBuffer cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_FRAME_PSNR enabled.");
      v8 = 0;
    }
    if ( !*((_QWORD *)a6 + 7) && (*((_BYTE *)a5 + 56) & 0x10) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1307,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not correct - pOutputArguments->Resolve"
        "dSubregionsPSNRData.pBuffer cannot be null with D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_SUBREGIONS_PSNR enabled.");
      v8 = 0;
    }
  }
  v23.IOCoherent = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *))(**((_QWORD **)a2 + 85)
                                                                                              + 24LL))(
         *((_QWORD *)a2 + 85),
         17,
         &v23) < 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata Failure on call to CheckFeatureSupport(D3D12_FEATURE_VI"
      "DEO_ARCHITECTURE,...).");
    v8 = 0;
  }
  v10 = (int *)((char *)a5 + 56);
  if ( ValidateOptionalMetadataInputs(
         (const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1 *)((char *)a5 + 56),
         a5,
         (const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1 *)((char *)a5 + 64),
         a1) >= 0 )
    v9 = v8;
  v11 = (CResource *)QIFrom<CResource>(*(_QWORD *)a6);
  CResource::GetDesc(v11, &v50);
  if ( v50.Dimension != D3D12_RESOURCE_DIMENSION_BUFFER )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS.ResolvedLayoutMetadata.pBuffer must be a buffer.");
    v9 = 0;
  }
  if ( *((_BYTE *)v11 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS.ResolvedLayoutMetadata.pBuffer must not be a"
      " reserved resource.");
  }
  else
  {
    if ( IsVideoHeapTypeSupported(&v23, v11) )
      goto LABEL_37;
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS.ResolvedLayoutMetadata.pBuffer must have hea"
      "p type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For"
      " D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE"
      "_VIDEO_ARCHITECTURE.");
  }
  v9 = 0;
LABEL_37:
  if ( *((_QWORD *)a6 + 1) >= v50.Width )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS::ResolvedLayoutMetadata.Offset exceeds the size of the b"
      "uffer specified D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS.ResolvedLayoutMetadata.pBuffer.");
    v9 = 0;
  }
  v12 = (CResource *)QIFrom<CResource>(*((_QWORD *)a5 + 5));
  CResource::GetDesc(v12, &v50);
  if ( v50.Dimension != D3D12_RESOURCE_DIMENSION_BUFFER )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS.HWLayoutMetadata.pBuffer must be a buffer.");
    v9 = 0;
  }
  if ( *((_BYTE *)v12 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS.HWLayoutMetadata.pBuffer must not be a reserved resource.");
  }
  else
  {
    if ( IsVideoHeapTypeSupported(&v23, v12) )
      goto LABEL_46;
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The resource in D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS.HWLayoutMetadata.pBuffer must have heap type "
      "D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_"
      "HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
  }
  v9 = 0;
LABEL_46:
  if ( *((_QWORD *)a5 + 6) >= v50.Width )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1307,
      "The D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS::HWLayoutMetadata.Offset exceeds the size of the buffer "
      "specified D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS.HWLayoutMetadata.pBuffer.");
    return 2147942487LL;
  }
  if ( !v9 )
    return 2147942487LL;
  v24 = 0;
  v14 = 1;
  if ( v25 )
    v14 = v25;
  _BitScanForward(&v14, v14);
  v24 = v14;
  v51[0] = v14;
  v51[1] = *(_DWORD *)a5;
  v52 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))(**((_QWORD **)v27 + 85) + 24LL))(
         *((_QWORD *)v27 + 85),
         33,
         v51,
         12) < 0
    || (v15 = 1, !v52) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1308,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12"
      "_FEATURE_VIDEO_ENCODER_CODEC,...) for the given input returned failure or not supported.");
    v15 = 0;
  }
  v26 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  if ( *(_DWORD *)a5 )
  {
    if ( *(_DWORD *)a5 == 1 )
    {
      v16 = &v30;
    }
    else
    {
      if ( *(_DWORD *)a5 != 2 )
        goto LABEL_63;
      v16 = &v29;
    }
    LODWORD(v28) = 8;
  }
  else
  {
    v16 = (__int64 *)&v26;
    LODWORD(v28) = 4;
  }
  *((_QWORD *)&v28 + 1) = v16;
LABEL_63:
  v25 = 2;
  if ( (int)ValidateVideoEncodeProfileLevelSupport(
              v24,
              a5,
              (const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1 *)((char *)a5 + 8),
              (const struct D3D12_VIDEO_ENCODER_LEVEL_SETTING *)&v28,
              (enum D3D12_VIDEO_ENCODER_PROFILE_LEVEL_VALIDATION_RESULT *)&v25,
              v27) < 0
    || v25 == 2 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1308,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12"
      "_FEATURE_VIDEO_ENCODER_PROFILE_LEVEL,...) for the given input returned failure or profile not supported.");
    v15 = 0;
  }
  v31[0] = v24;
  v31[1] = *(_DWORD *)a5;
  v32 = *(_OWORD *)((char *)a5 + 8);
  v33 = *((_DWORD *)a5 + 6);
  v34 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)v27 + 85) + 24LL))(
         *((_QWORD *)v27 + 85),
         37,
         v31) < 0
    || !v34 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1308,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12"
      "_FEATURE_VIDEO_ENCODER_INPUT_FORMAT,...) for the given input returned failure or not supported.");
    v15 = 0;
  }
  if ( (int)ValidateVideoEncodeResolutionsListSupported(
              v24,
              a5,
              1u,
              (const struct D3D12_VIDEO_ENCODER_RESOLVE_METADATA_INPUT_ARGUMENTS1 *)((char *)a5 + 28),
              v27) < 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1308,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - EncodedPictureEffectiveRe"
      "solution does not satisfy the constraints specified in CheckFeatureSupport - D3D12_FEATURE_VIDEO_ENCODER_OUTPUT_RESOLUTION.");
    v15 = 0;
  }
  memset_0(v35, 0, 0x70u);
  v35[0] = v24;
  v35[1] = *(_DWORD *)a5;
  v36 = *(_OWORD *)((char *)a5 + 8);
  v37 = *((_DWORD *)a5 + 6);
  v38 = *(_QWORD *)((char *)a5 + 28);
  v41 = *v10;
  v42 = *((_OWORD *)a5 + 4);
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)v27 + 85) + 24LL))(
         *((_QWORD *)v27 + 85),
         48,
         v35) >= 0
    && v39 )
  {
    if ( (*(_BYTE *)v10 & 1) != 0 )
    {
      v18 = 0;
      v19 = *(unsigned int *)a5;
      if ( (_DWORD)v19 && (v19 = (unsigned int)(v19 - 1), (_DWORD)v19) )
      {
        if ( (_DWORD)v19 == 1 )
          v18 = 62;
      }
      else
      {
        v18 = 64;
      }
      v15 &= _lambda_677435261ab462159bab436ab1c5f70f_::operator()(
               v19,
               a1,
               *((_QWORD *)a6 + 2),
               &v23,
               "D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1::pOutputQPMap",
               v18,
               v43,
               v44,
               3);
    }
    if ( (*(_BYTE *)v10 & 2) != 0 )
      v15 &= _lambda_677435261ab462159bab436ab1c5f70f_::operator()(
               v17,
               a1,
               *((_QWORD *)a6 + 3),
               &v23,
               "D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1::pOutputSATDMap",
               42,
               v45,
               v46,
               3);
    if ( (*(_BYTE *)v10 & 4) != 0 )
      v15 &= _lambda_677435261ab462159bab436ab1c5f70f_::operator()(
               v17,
               a1,
               *((_QWORD *)a6 + 4),
               &v23,
               "D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1::pOutputBitAllocationMap",
               42,
               v47,
               v48,
               3);
    if ( (*(_BYTE *)v10 & 8) != 0 )
      v15 &= _lambda_677435261ab462159bab436ab1c5f70f_::operator()(
               v17,
               a1,
               *((_QWORD *)a6 + 5),
               &v23,
               "D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1::ResolvedFramePSNRData.pBuffer",
               0,
               12,
               1,
               1);
    if ( (*(_BYTE *)v10 & 0x10) != 0 )
      v15 &= _lambda_677435261ab462159bab436ab1c5f70f_::operator()(
               v17,
               a1,
               *((_QWORD *)a6 + 7),
               &v23,
               "D3D12_VIDEO_ENCODER_RESOLVE_METADATA_OUTPUT_ARGUMENTS1::ResolvedSubregionsPSNRData.pBuffer",
               0,
               v49,
               1,
               1);
    v20 = *((_QWORD *)a5 + 6);
    v21 = v40;
    if ( v20 % v40 )
    {
      v15 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1308,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments warning - Buffer offset alignment for HWLay"
        "outMetadata.pBuffer specified in InputArguments.HWLayoutMetadata.Offset is different than advised in encoder cap"
        "s. Current buffer offset: %d Required alignment reported: %d",
        v20,
        v40);
      v21 = v40;
    }
    v22 = *((_QWORD *)a6 + 1);
    if ( v22 % v21 )
    {
      v15 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1308,
        "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments warning - Buffer offset alignment for Resol"
        "vedLayoutMetadata.pBuffer specified in OutputArguments.ResolvedLayoutMetadata.Offset is different than advised i"
        "n encoder caps. Current buffer offset: %d Required alignment reported: %d",
        v22,
        v21);
    }
    return v15 == 0 ? 0x80070057 : 0;
  }
  else
  {
    TDebugOutputFunctor::operator()(
      a1,
      1308,
      "ID3D12VideoEncodeCommandList::ResolveEncoderOutputMetadata arguments are not supported - CheckFeatureSupport(D3D12"
      "_FEATURE_VIDEO_ENCODER_RESOURCE_REQUIREMENTS1,...) for the given input returned failure or not supported.");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180245d88  push    rbx
0x180245d8a  push    rsi
0x180245d8b  push    rdi
0x180245d8c  push    r12
0x180245d8e  push    r13
0x180245d90  push    r14
0x180245d92  push    r15
0x180245d94  sub     rsp, 180h
0x180245d9b  mov     rax, cs:__security_cookie
0x180245da2  xor     rax, rsp
0x180245da5  mov     [rsp+1B8h+var_48], rax
0x180245dad  mov     [rsp+1B8h+var_160], r9d
0x180245db2  mov     r13, rdx
0x180245db5  mov     [rsp+1B8h+var_158], rdx
0x180245dba  mov     rbx, rcx
0x180245dbd  mov     rsi, [rsp+1B8h+arg_20]
0x180245dc5  mov     r14, [rsp+1B8h+arg_28]
0x180245dcd  mov     r15b, 1
0x180245dd0  xor     r12d, r12d
0x180245dd3  mov     edi, 51Bh
0x180245dd8  test    rsi, rsi
0x180245ddb  jnz     short loc_180245DEE
0x180245ddd  lea     r8, aId3d12videoenc_148; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245de4  mov     edx, edi
0x180245de6  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245deb  mov     r15b, r12b
0x180245dee  test    r14, r14
0x180245df1  jnz     short loc_180245E07
0x180245df3  lea     r8, aId3d12videoenc_99; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245dfa  mov     edx, edi
0x180245dfc  mov     rcx, rbx
0x180245dff  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245e04  mov     r15b, r12b
0x180245e07  test    rsi, rsi
0x180245e0a  jz      short loc_180245E26
0x180245e0c  cmp     [rsi+28h], r12
0x180245e10  jnz     short loc_180245E26
0x180245e12  lea     r8, aId3d12videoenc_95; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245e19  mov     edx, edi
0x180245e1b  mov     rcx, rbx
0x180245e1e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245e23  mov     r15b, r12b
0x180245e26  test    r14, r14
0x180245e29  jz      loc_180245EE8
0x180245e2f  cmp     [r14], r12
0x180245e32  jnz     short loc_180245E48
0x180245e34  lea     r8, aId3d12videoenc_152; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245e3b  mov     edx, edi
0x180245e3d  mov     rcx, rbx
0x180245e40  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245e45  mov     r15b, r12b
0x180245e48  cmp     [r14+10h], r12
0x180245e4c  jnz     short loc_180245E68
0x180245e4e  test    byte ptr [rsi+38h], 1
0x180245e52  jz      short loc_180245E68
0x180245e54  lea     r8, aId3d12videoenc_69; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245e5b  mov     edx, edi
0x180245e5d  mov     rcx, rbx
0x180245e60  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245e65  mov     r15b, r12b
0x180245e68  cmp     [r14+18h], r12
0x180245e6c  jnz     short loc_180245E88
0x180245e6e  test    byte ptr [rsi+38h], 2
0x180245e72  jz      short loc_180245E88
0x180245e74  lea     r8, aId3d12videoenc_87; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245e7b  mov     edx, edi
0x180245e7d  mov     rcx, rbx
0x180245e80  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245e85  mov     r15b, r12b
0x180245e88  cmp     [r14+20h], r12
0x180245e8c  jnz     short loc_180245EA8
0x180245e8e  test    byte ptr [rsi+38h], 4
0x180245e92  jz      short loc_180245EA8
0x180245e94  lea     r8, aId3d12videoenc_122; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245e9b  mov     edx, edi
0x180245e9d  mov     rcx, rbx
0x180245ea0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245ea5  mov     r15b, r12b
0x180245ea8  cmp     [r14+28h], r12
0x180245eac  jnz     short loc_180245EC8
0x180245eae  test    byte ptr [rsi+38h], 8
0x180245eb2  jz      short loc_180245EC8
0x180245eb4  lea     r8, aId3d12videoenc_155; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245ebb  mov     edx, edi
0x180245ebd  mov     rcx, rbx
0x180245ec0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245ec5  mov     r15b, r12b
0x180245ec8  cmp     [r14+38h], r12
0x180245ecc  jnz     short loc_180245EE8
0x180245ece  test    byte ptr [rsi+38h], 10h
0x180245ed2  jz      short loc_180245EE8
0x180245ed4  lea     r8, aId3d12videoenc_102; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245edb  mov     edx, edi
0x180245edd  mov     rcx, rbx
0x180245ee0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245ee5  mov     r15b, r12b
0x180245ee8  mov     [rsp+1B8h+var_168.IOCoherent], r12d
0x180245eed  mov     rcx, [r13+2A8h]
0x180245ef4  mov     rax, [rcx]
0x180245ef7  mov     r9d, 4
0x180245efd  lea     r8, [rsp+1B8h+var_168]
0x180245f02  lea     edx, [r9+0Dh]
0x180245f06  mov     rax, [rax+18h]
0x180245f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180245f0f  test    eax, eax
0x180245f11  jns     short loc_180245F27
0x180245f13  lea     r8, aId3d12videoenc_15; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180245f1a  mov     edx, edi
0x180245f1c  mov     rcx, rbx
0x180245f1f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245f24  mov     r15b, r12b
0x180245f27  lea     r8, [rsi+40h]; struct D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION *
0x180245f2b  lea     r13, [rsi+38h]
0x180245f2f  mov     r9, rbx; struct TDebugOutputFunctor *
0x180245f32  mov     rdx, rsi; enum D3D12_VIDEO_ENCODER_CODEC *
0x180245f35  mov     rcx, r13; enum D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAGS *
0x180245f38  call    ?ValidateOptionalMetadataInputs@@YAJAEBW4D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAGS@@AEBW4D3D12_VIDEO_ENCODER_CODEC@@AEBUD3D12_VIDEO_ENCODER_CODEC_CONFIGURATION@@AEAUTDebugOutputFunctor@@@Z; ValidateOptionalMetadataInputs(D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAGS const &,D3D12_VIDEO_ENCODER_CODEC const &,D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION const &,TDebugOutputFunctor &)
0x180245f3d  movzx   ecx, r15b
0x180245f41  test    eax, eax
0x180245f43  cmovns  r12d, ecx
0x180245f47  mov     rcx, [r14]
0x180245f4a  call    ??$QIFrom@VCResource@@@@YAPEAVCResource@@PEAUIUnknown@@AEBU_GUID@@W4ERefType@@@Z; QIFrom<CResource>(IUnknown *,_GUID const &,ERefType)
0x180245f4f  mov     r15, rax
0x180245f52  lea     rdx, [rsp+1B8h+var_90]; retstr
0x180245f5a  mov     rcx, rax; this
0x180245f5d  call    ?GetDesc@CResource@@UEAA?AUD3D12_RESOURCE_DESC@@XZ; CResource::GetDesc(void)
0x180245f62  cmp     [rsp+1B8h+var_90.Dimension], 1
0x180245f6a  jz      short loc_180245F80
0x180245f6c  lea     r8, aTheResourceInD_13; "The resource in D3D12_VIDEO_ENCODER_RES"...
0x180245f73  mov     edx, edi
0x180245f75  mov     rcx, rbx
0x180245f78  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245f7d  xor     r12b, r12b
0x180245f80  cmp     byte ptr [r15+188h], 3
0x180245f88  jnz     short loc_180245F93
0x180245f8a  lea     r8, aTheResourceInD_2; "The resource in D3D12_VIDEO_ENCODER_RES"...
0x180245f91  jmp     short loc_180245FAB
0x180245f93  mov     rdx, r15; struct CResource *
0x180245f96  lea     rcx, [rsp+1B8h+var_168]; struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *
0x180245f9b  call    ?IsVideoHeapTypeSupported@@YA_NAEBUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEAVCResource@@@Z; IsVideoHeapTypeSupported(D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE const &,CResource *)
0x180245fa0  test    al, al
0x180245fa2  jnz     short loc_180245FB8
0x180245fa4  lea     r8, aTheResourceInD_6; "The resource in D3D12_VIDEO_ENCODER_RES"...
0x180245fab  mov     edx, edi
0x180245fad  mov     rcx, rbx
0x180245fb0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245fb5  xor     r12b, r12b
0x180245fb8  mov     rax, [rsp+1B8h+var_90.Width]
0x180245fc0  cmp     [r14+8], rax
0x180245fc4  jb      short loc_180245FDA
0x180245fc6  lea     r8, aTheD3d12VideoE_7; "The D3D12_VIDEO_ENCODER_RESOLVE_METADAT"...
0x180245fcd  mov     edx, edi
0x180245fcf  mov     rcx, rbx
0x180245fd2  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245fd7  xor     r12b, r12b
0x180245fda  mov     rcx, [rsi+28h]
0x180245fde  call    ??$QIFrom@VCResource@@@@YAPEAVCResource@@PEAUIUnknown@@AEBU_GUID@@W4ERefType@@@Z; QIFrom<CResource>(IUnknown *,_GUID const &,ERefType)
0x180245fe3  mov     r15, rax
0x180245fe6  lea     rdx, [rsp+1B8h+var_90]; retstr
0x180245fee  mov     rcx, rax; this
0x180245ff1  call    ?GetDesc@CResource@@UEAA?AUD3D12_RESOURCE_DESC@@XZ; CResource::GetDesc(void)
0x180245ff6  cmp     [rsp+1B8h+var_90.Dimension], 1
0x180245ffe  jz      short loc_180246014
0x180246000  lea     r8, aTheResourceInD_3; "The resource in D3D12_VIDEO_ENCODER_RES"...
0x180246007  mov     edx, edi
0x180246009  mov     rcx, rbx
0x18024600c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246011  xor     r12b, r12b
0x180246014  cmp     byte ptr [r15+188h], 3
0x18024601c  jnz     short loc_180246027
0x18024601e  lea     r8, aTheResourceInD_1; "The resource in D3D12_VIDEO_ENCODER_RES"...
0x180246025  jmp     short loc_18024603F
0x180246027  mov     rdx, r15; struct CResource *
0x18024602a  lea     rcx, [rsp+1B8h+var_168]; struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *
0x18024602f  call    ?IsVideoHeapTypeSupported@@YA_NAEBUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEAVCResource@@@Z; IsVideoHeapTypeSupported(D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE const &,CResource *)
0x180246034  test    al, al
0x180246036  jnz     short loc_18024604C
0x180246038  lea     r8, aTheResourceInD_12; "The resource in D3D12_VIDEO_ENCODER_RES"...
0x18024603f  mov     edx, edi
0x180246041  mov     rcx, rbx
0x180246044  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246049  xor     r12b, r12b
0x18024604c  mov     rax, [rsp+1B8h+var_90.Width]
0x180246054  cmp     [rsi+30h], rax
0x180246058  jb      short loc_18024606D
0x18024605a  lea     r8, aTheD3d12VideoE_6; "The D3D12_VIDEO_ENCODER_RESOLVE_METADAT"...
0x180246061  mov     edx, edi
0x180246063  mov     rcx, rbx
0x180246066  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024606b  jmp     short loc_180246072
0x18024606d  test    r12b, r12b
0x180246070  jnz     short loc_18024607C
0x180246072  mov     eax, 80070057h
0x180246077  jmp     loc_180246529
0x18024607c  xor     r12d, r12d
0x18024607f  mov     [rsp+1B8h+var_164], r12d
0x180246084  lea     eax, [r12+1]
0x180246089  mov     ecx, [rsp+1B8h+var_160]
0x18024608d  test    ecx, ecx
0x18024608f  cmovnz  eax, ecx
0x180246092  bsf     eax, eax
0x180246095  mov     [rsp+1B8h+var_164], eax
0x180246099  mov     [rsp+1B8h+var_58], eax
0x1802460a0  mov     eax, [rsi]
0x1802460a2  mov     [rsp+1B8h+var_54], eax
0x1802460a9  mov     [rsp+1B8h+var_50], r12d
0x1802460b1  mov     rcx, [rsp+1B8h+var_158]
0x1802460b6  mov     rcx, [rcx+2A8h]
0x1802460bd  mov     rax, [rcx]
0x1802460c0  lea     r9d, [r12+0Ch]
0x1802460c5  lea     r8, [rsp+1B8h+var_58]
0x1802460cd  lea     edx, [r12+21h]
0x1802460d2  mov     rax, [rax+18h]
0x1802460d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802460db  test    eax, eax
0x1802460dd  js      short loc_1802460F4
0x1802460df  mov     dil, 1
0x1802460e2  cmp     [rsp+1B8h+var_50], r12d
0x1802460ea  jz      short loc_1802460F4
0x1802460ec  mov     r15d, 51Ch
0x1802460f2  jmp     short loc_18024610F
0x1802460f4  lea     r8, aId3d12videoenc_64; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x1802460fb  mov     r15d, 51Ch
0x180246101  mov     edx, r15d
0x180246104  mov     rcx, rbx
0x180246107  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024610c  mov     dil, r12b
0x18024610f  mov     [rsp+1B8h+var_15C], r12d
0x180246114  mov     [rsp+1B8h+var_138], r12
0x18024611c  mov     [rsp+1B8h+var_140], r12
0x180246121  xorps   xmm0, xmm0
0x180246124  movups  [rsp+1B8h+var_150], xmm0
0x180246129  mov     ecx, [rsi]
0x18024612b  test    ecx, ecx
0x18024612d  jz      short loc_180246152
0x18024612f  sub     ecx, 1
0x180246132  jz      short loc_180246148
0x180246134  cmp     ecx, 1
0x180246137  jnz     short loc_180246164
0x180246139  lea     rax, [rsp+1B8h+var_140]
0x18024613e  mov     dword ptr [rsp+1B8h+var_150], 8
0x180246146  jmp     short loc_18024615F
0x180246148  lea     rax, [rsp+1B8h+var_138]
0x180246150  jmp     short loc_18024613E
0x180246152  lea     rax, [rsp+1B8h+var_15C]
0x180246157  mov     dword ptr [rsp+1B8h+var_150], 4
0x18024615f  mov     qword ptr [rsp+1B8h+var_150+8], rax
0x180246164  mov     [rsp+1B8h+var_160], 2
0x18024616c  mov     rax, [rsp+1B8h+var_158]
0x180246171  mov     [rsp+1B8h+var_190], rax; struct DeviceValidationInfo *
0x180246176  lea     rax, [rsp+1B8h+var_160]
0x18024617b  mov     [rsp+1B8h+var_198], rax; enum D3D12_VIDEO_ENCODER_PROFILE_LEVEL_VALIDATION_RESULT *
0x180246180  lea     r9, [rsp+1B8h+var_150]; struct D3D12_VIDEO_ENCODER_LEVEL_SETTING *
0x180246185  lea     r8, [rsi+8]; struct D3D12_VIDEO_ENCODER_PROFILE_DESC *
0x180246189  mov     rdx, rsi; enum D3D12_VIDEO_ENCODER_CODEC *
0x18024618c  mov     ecx, [rsp+1B8h+var_164]; unsigned int
0x180246190  call    ?ValidateVideoEncodeProfileLevelSupport@@YAJIAEBW4D3D12_VIDEO_ENCODER_CODEC@@AEBUD3D12_VIDEO_ENCODER_PROFILE_DESC@@AEBUD3D12_VIDEO_ENCODER_LEVEL_SETTING@@AEAW4D3D12_VIDEO_ENCODER_PROFILE_LEVEL_VALIDATION_RESULT@@AEBUDeviceValidationInfo@@@Z; ValidateVideoEncodeProfileLevelSupport(uint,D3D12_VIDEO_ENCODER_CODEC const &,D3D12_VIDEO_ENCODER_PROFILE_DESC const &,D3D12_VIDEO_ENCODER_LEVEL_SETTING const &,D3D12_VIDEO_ENCODER_PROFILE_LEVEL_VALIDATION_RESULT &,DeviceValidationInfo const &)
0x180246195  test    eax, eax
0x180246197  js      short loc_1802461A0
0x180246199  cmp     [rsp+1B8h+var_160], 2
0x18024619e  jnz     short loc_1802461B5
0x1802461a0  lea     r8, aId3d12videoenc_153; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x1802461a7  mov     edx, r15d
0x1802461aa  mov     rcx, rbx
0x1802461ad  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802461b2  xor     dil, dil
0x1802461b5  mov     eax, [rsp+1B8h+var_164]
0x1802461b9  mov     [rsp+1B8h+var_130], eax
0x1802461c0  mov     eax, [rsi]
0x1802461c2  mov     [rsp+1B8h+var_12C], eax
0x1802461c9  movups  xmm0, xmmword ptr [rsi+8]
0x1802461cd  movdqu  [rsp+1B8h+var_128], xmm0
0x1802461d6  mov     eax, [rsi+18h]
0x1802461d9  mov     [rsp+1B8h+var_118], eax
0x1802461e0  mov     [rsp+1B8h+var_114], r12d
0x1802461e8  mov     rax, [rsp+1B8h+var_158]
0x1802461ed  mov     rcx, [rax+2A8h]
0x1802461f4  mov     rax, [rcx]
0x1802461f7  mov     r9d, 20h ; ' '
0x1802461fd  lea     r8, [rsp+1B8h+var_130]
0x180246205  lea     edx, [r9+5]
0x180246209  mov     rax, [rax+18h]
0x18024620d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246212  test    eax, eax
0x180246214  js      short loc_180246220
0x180246216  cmp     [rsp+1B8h+var_114], r12d
0x18024621e  jnz     short loc_180246235
0x180246220  lea     r8, aId3d12videoenc_149; "ID3D12VideoEncodeCommandList::ResolveEn"...
0x180246227  mov     edx, r15d
0x18024622a  mov     rcx, rbx
0x18024622d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246232  xor     dil, dil
0x180246235  mov     rax, [rsp+1B8h+var_158]
0x18024623a  mov     [rsp+1B8h+var_198], rax; struct DeviceValidationInfo *
0x18024623f  lea     r9, [rsi+1Ch]; struct D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC *
0x180246243  mov     r8d, 1; unsigned int
0x180246249  mov     rdx, rsi; enum D3D12_VIDEO_ENCODER_CODEC *
0x18024624c  mov     ecx, [rsp+1B8h+var_164]; unsigned int
0x180246250  call    ?ValidateVideoEncodeResolutionsListSupported@@YAJIAEBW4D3D12_VIDEO_ENCODER_CODEC@@IPEBUD3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC@@AEBUDeviceValidationInfo@@@Z; ValidateVideoEncodeResolutionsListSupported(uint,D3D12_VIDEO_ENCODER_CODEC const &,uint,D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC const *,DeviceValidationInfo const &)
0x180246255  test    eax, eax
  ... truncated ...
```
