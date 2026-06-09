# ValidateVideoEncodeCodecConfig(uint,D3D12_VIDEO_ENCODER_CODEC const &,D3D12_VIDEO_ENCODER_PROFILE_DESC const &,D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION const &,DeviceValidationInfo const &,TDebugOutputFunctor &)

- ea: `0x180125274`
- end: `0x180125afe`
- name: `?ValidateVideoEncodeCodecConfig@@YAJIAEBW4D3D12_VIDEO_ENCODER_CODEC@@AEBUD3D12_VIDEO_ENCODER_PROFILE_DESC@@AEBUD3D12_VIDEO_ENCODER_CODEC_CONFIGURATION@@AEBUDeviceValidationInfo@@AEAUTDebugOutputFunctor@@@Z`
- size: `2186`
- prototype: `int(unsigned int, const enum D3D12_VIDEO_ENCODER_CODEC *, const struct D3D12_VIDEO_ENCODER_PROFILE_DESC *, const struct D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION *, const struct DeviceValidationInfo *, struct TDebugOutputFunctor *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1801262ec`
- `0x180246e70`

## callees

- `0x18002ef50`
- `0x1800bb480`
- `0x1800bc094`
- `0x1801241b8`
- `0x180125274`
- `0x180126168`
- `0x180262020`

## string_xrefs

- `0x180125a9e`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - CABAC encoding not supported.`
- `0x1801254b1`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Call to CheckFeatureCaps (D3D12_FEATURE_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported for Codec HEVC -  MinLumaSize %d - MaxLumaSize %d -  MinTransformSize %d - MaxTransformSize %d - Depth_inter %d - Depth intra %d`
- `0x180125a52`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Constrained intraprediction not supported.`
- `0x180125a78`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Adaptive 8x8 transform not supported.`
- `0x1801259ff`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Direct mode spatial not supported.`
- `0x180125a26`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Direct mode temporal not supported.`
- `0x1801259b2`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - DisableDeblockingFilterConfig (value: %d) has to be within defined range.`
- `0x1801259da`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - DisableDeblockingFilterConfig (value %d) not allowed by DisableDeblockingFilterSupportedModes 0x%x cap reporting.`
- `0x1801255be`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Constrained intra-prediction use is not supported.`
- `0x1801255e7`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_TRANSFORM_SKIP_ROTATION not supported.`
- `0x180125572`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Asymetric motion partition is required to be set.`
- `0x180125598`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Transform skipping is not supported.`
- `0x180125526`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - SAO Filter mode not supported.`
- `0x18012554c`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Asymetric motion partition not supported.`
- `0x1801254da`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Disable deblocking across slice boundary mode not supported.`
- `0x180125500`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Intra slice constrained mode not supported.`
- `0x180125acc`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Intra slice constrained mode not supported.`
- `0x180125718`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_EXPLICIT_RDPCM is required to be set.`
- `0x180125747`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_EXTENDED_PRECISION_PROCESSING not supported.`
- `0x1801256c0`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_IMPLICIT_RDPCM is required to be set.`
- `0x1801256ec`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_EXPLICIT_RDPCM not supported.`
- `0x180125668`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_TRANSFORM_SKIP_CONTEXT is required to be set.`
- `0x180125697`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_IMPLICIT_RDPCM not supported.`
- `0x180125610`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_TRANSFORM_SKIP_ROTATION is required to be set.`
- `0x18012563f`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_TRANSFORM_SKIP_CONTEXT not supported.`
- `0x180125878`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_PERSISTENT_RICE_ADAPTATION is required to be set.`
- `0x1801258a7`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_CABAC_BYPASS_ALIGNMENT not supported.`
- `0x180125820`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_HIGH_PRECISION_OFFSETS is required to be set.`
- `0x18012584f`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_PERSISTENT_RICE_ADAPTATION not supported.`
- `0x1801257c8`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_INTRA_SMOOTHING_DISABLED is required to be set.`
- `0x1801257f7`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_HIGH_PRECISION_OFFSETS not supported.`
- `0x180125770`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_EXTENDED_PRECISION_PROCESSING is required to be set.`
- `0x18012579f`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_INTRA_SMOOTHING_DISABLED not supported.`
- `0x18012537d`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION.FeatureFlags (value %x) not allowed by D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_AV1.SupportedFeatureFlags 0x%x reported caps.`
- `0x1801253a7`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION.FeatureFlags (value %x) does not have all the D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_AV1.RequiredFeatureFlags 0x%x reported caps set.`
- `0x18012592c`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_SEPARATE_COLOUR_PLANE is required to be set.`
- `0x180125350`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Call to CheckFeatureCaps (D3D12_FEATURE_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported.`
- `0x18012598f`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Call to CheckFeatureCaps (D3D12_FEATURE_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported.`
- `0x1801258d0`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_CABAC_BYPASS_ALIGNMENT is required to be set.`
- `0x1801258fd`: `D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_SEPARATE_COLOUR_PLANE not supported.`

## pseudocode

```c
__int64 __fastcall ValidateVideoEncodeCodecConfig(
        int a1,
        const enum D3D12_VIDEO_ENCODER_CODEC *a2,
        const struct D3D12_VIDEO_ENCODER_PROFILE_DESC *a3,
        const struct D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION *a4,
        const struct DeviceValidationInfo *a5,
        struct TDebugOutputFunctor *a6)
{
  char v8; // bl
  int v9; // r9d
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // r9d
  unsigned int v15; // r9d
  int v16; // eax
  _DWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h]
  int *v19; // [rsp+60h] [rbp-A0h]
  __int128 v20; // [rsp+68h] [rbp-98h]
  int *v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+90h] [rbp-70h] BYREF
  int v24; // [rsp+94h] [rbp-6Ch]
  int v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+9Ch] [rbp-64h]
  int v27; // [rsp+A0h] [rbp-60h]
  char v28; // [rsp+A4h] [rbp-5Ch]
  char v29; // [rsp+A5h] [rbp-5Bh]
  __int16 v30; // [rsp+A6h] [rbp-5Ah]
  _BYTE v31[72]; // [rsp+A8h] [rbp-58h] BYREF

  v20 = 0;
  v21 = 0;
  v17[0] = a1;
  v17[1] = *(_DWORD *)a2;
  v18 = *(_QWORD *)a3;
  v19 = (int *)*((_QWORD *)a3 + 1);
  if ( (int)ValidateVideoEncoderCodecConfig(a4, a2, a6) >= 0 )
  {
    v8 = 1;
    if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 == 1 )
      {
        v23 = 0;
        v11 = *((_QWORD *)a4 + 1);
        v24 = *(_DWORD *)(v11 + 4);
        v25 = *(_DWORD *)(v11 + 8);
        v26 = *(_DWORD *)(v11 + 12);
        v27 = *(_DWORD *)(v11 + 16);
        v28 = *(_BYTE *)(v11 + 20);
        v29 = *(_BYTE *)(v11 + 21);
        v30 = 0;
        memset_0(v31, 0, sizeof(v31));
        LOBYTE(v12) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444>::GetImpl'::`2'::impl,
          v12);
        if ( *v19 > 1 )
        {
          if ( *v19 <= 8 )
          {
            v21 = &v23;
            DWORD2(v20) = 96;
          }
        }
        else
        {
          v21 = &v23;
          DWORD2(v20) = 24;
        }
        if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a5 + 85) + 24LL))(
               *((_QWORD *)a5 + 85),
               42,
               v17) < 0
          || !(_DWORD)v20 )
        {
          v13 = *((_QWORD *)a4 + 1);
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Call to CheckFeatureCaps (D3D12_FEATUR"
            "E_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported for Codec HEVC -  MinLum"
            "aSize %d - MaxLumaSize %d -  MinTransformSize %d - MaxTransformSize %d - Depth_inter %d - Depth intra %d",
            *(_DWORD *)(v13 + 4),
            *(_DWORD *)(v13 + 8),
            *(_DWORD *)(v13 + 12),
            *(_DWORD *)(v13 + 16),
            *(unsigned __int8 *)(v13 + 20),
            *(unsigned __int8 *)(v13 + 21));
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 1) != 0 && (*(_BYTE *)v21 & 0x80) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Disable deblocking across slice bounda"
            "ry mode not supported.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 2) != 0 && (*(_BYTE *)v21 & 2) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Intra slice constrained mode not supported.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 4) != 0 && (*(_BYTE *)v21 & 8) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - SAO Filter mode not supported.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 0x10) != 0 && (*(_BYTE *)v21 & 0x10) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Asymetric motion partition not supported.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 0x10) == 0 && (*(_BYTE *)v21 & 0x20) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Asymetric motion partition is required to be set.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 0x20) != 0 && (*(_BYTE *)v21 & 0x40) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Transform skipping is not supported.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 0x40) != 0 && (*(_BYTE *)v21 & 4) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Constrained intra-prediction use is not supported.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 0x80) != 0 && (*v21 & 0x400) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_TRANSFORM_SKIP_ROTATION not supported.");
          v8 = 0;
        }
        if ( (**((_BYTE **)a4 + 1) & 0x80) == 0 && (*v21 & 0x800) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_TRANSFORM_SKIP_ROTATION is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x100) != 0 && (*v21 & 0x1000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_TRANSFORM_SKIP_CONTEXT not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x100) == 0 && (*v21 & 0x2000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_TRANSFORM_SKIP_CONTEXT is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x200) != 0 && (*v21 & 0x4000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_IMPLICIT_RDPCM not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x200) == 0 && (*v21 & 0x8000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_IMPLICIT_RDPCM is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x400) != 0 && (*v21 & 0x10000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_EXPLICIT_RDPCM not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x400) == 0 && (*v21 & 0x20000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_EXPLICIT_RDPCM is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x800) != 0 && (*v21 & 0x40000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_EXTENDED_PRECISION_PROCESSING not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x800) == 0 && (*v21 & 0x80000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_EXTENDED_PRECISION_PROCESSING is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x1000) != 0 && (*v21 & 0x100000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_INTRA_SMOOTHING_DISABLED not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x1000) == 0 && (*v21 & 0x200000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_INTRA_SMOOTHING_DISABLED is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x2000) != 0 && (*v21 & 0x400000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_HIGH_PRECISION_OFFSETS not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x2000) == 0 && (*v21 & 0x800000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_HIGH_PRECISION_OFFSETS is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x4000) != 0 && (*v21 & 0x1000000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_PERSISTENT_RICE_ADAPTATION not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x4000) == 0 && (*v21 & 0x2000000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_PERSISTENT_RICE_ADAPTATION is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x8000) != 0 && (*v21 & 0x4000000) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_CABAC_BYPASS_ALIGNMENT not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x8000) == 0 && (*v21 & 0x8000000) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_CABAC_BYPASS_ALIGNMENT is required to be set.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x10000) != 0 && (v21[23] & 1) == 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_SEPARATE_COLOUR_PLANE not supported.");
          v8 = 0;
        }
        if ( (**((_DWORD **)a4 + 1) & 0x10000) == 0 && (v21[23] & 2) != 0 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - D3D12_VIDEO_ENCODER_CODEC_CONFIGURATIO"
            "N_HEVC_FLAG_SEPARATE_COLOUR_PLANE is required to be set.");
          v8 = 0;
        }
        return v8 == 0 ? 0x80070057 : 0;
      }
      if ( *(_DWORD *)a2 == 2 )
      {
        memset_0(&v23, 0, 0x54u);
        v21 = &v23;
        DWORD2(v20) = 84;
        if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))(**((_QWORD **)a5 + 85) + 24LL))(
               *((_QWORD *)a5 + 85),
               42,
               v17,
               48) < 0
          || !(_DWORD)v20 )
        {
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Call to CheckFeatureCaps (D3D12_FEATUR"
            "E_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported.");
          v8 = 0;
        }
        v9 = **((_DWORD **)a4 + 1);
        if ( (v23 & v9) != v9 )
        {
          v8 = 0;
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATIO"
            "N.FeatureFlags (value %x) not allowed by D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_AV1.SupportedFeatur"
            "eFlags 0x%x reported caps.",
            v9,
            v23);
        }
        if ( (v24 & **((_DWORD **)a4 + 1)) != v24 )
        {
          v8 = 0;
          TDebugOutputFunctor::operator()(
            a6,
            1310,
            "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATIO"
            "N.FeatureFlags (value %x) does not have all the D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_AV1.Required"
            "FeatureFlags 0x%x reported caps set.",
            **((_DWORD **)a4 + 1),
            v24);
        }
        return v8 == 0 ? 0x80070057 : 0;
      }
    }
    else
    {
      v22 = 0;
      v21 = (int *)&v22;
      DWORD2(v20) = 8;
      if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a5 + 85) + 24LL))(
             *((_QWORD *)a5 + 85),
             42,
             v17) < 0
        || !(_DWORD)v20 )
      {
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Call to CheckFeatureCaps (D3D12_FEATURE_"
          "VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported.");
        v8 = 0;
      }
      v14 = *(_DWORD *)(*((_QWORD *)a4 + 1) + 8LL);
      if ( v14 >= 7 )
      {
        v8 = 0;
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - DisableDeblockingFilterConfig (value: %d) ha"
          "s to be within defined range.",
          v14);
      }
      v15 = *(_DWORD *)(*((_QWORD *)a4 + 1) + 8LL);
      v16 = HIDWORD(v22);
      if ( !_bittest(&v16, v15) )
      {
        v8 = 0;
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments not supported - DisableDeblockingFilterConfig (value %d) not"
          " allowed by DisableDeblockingFilterSupportedModes 0x%x cap reporting.",
          v15,
          HIDWORD(v22));
      }
      if ( *(_DWORD *)(*((_QWORD *)a4 + 1) + 4LL) == 2 && (*(_BYTE *)v21 & 0x10) == 0 )
      {
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Direct mode spatial not supported.");
        v8 = 0;
      }
      if ( *(_DWORD *)(*((_QWORD *)a4 + 1) + 4LL) == 1 && (*(_BYTE *)v21 & 0x20) == 0 )
      {
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Direct mode temporal not supported.");
        v8 = 0;
      }
      if ( (**((_BYTE **)a4 + 1) & 1) != 0 && (*(_BYTE *)v21 & 0x40) == 0 )
      {
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Constrained intraprediction not supported.");
        v8 = 0;
      }
      if ( (**((_BYTE **)a4 + 1) & 2) != 0 && (*(_BYTE *)v21 & 8) == 0 )
      {
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Adaptive 8x8 transform not supported.");
        v8 = 0;
      }
      if ( (**((_BYTE **)a4 + 1) & 4) != 0 && (*(_BYTE *)v21 & 1) == 0 )
      {
        TDebugOutputFunctor::operator()(
          a6,
          1310,
          "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - CABAC encoding not supported.");
        v8 = 0;
      }
      if ( (**((_BYTE **)a4 + 1) & 8) == 0 || (*(_BYTE *)v21 & 2) != 0 )
        return v8 == 0 ? 0x80070057 : 0;
      TDebugOutputFunctor::operator()(
        a6,
        1310,
        "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION arguments are not supported - Intra slice constrained mode not supported.");
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180125274  push    rbp
0x180125276  push    rbx
0x180125277  push    rsi
0x180125278  push    rdi
0x180125279  push    r14
0x18012527b  push    r15
0x18012527d  lea     rbp, [rsp-8]
0x180125282  sub     rsp, 108h
0x180125289  mov     rax, cs:__security_cookie
0x180125290  xor     rax, rsp
0x180125293  mov     [rbp+30h+var_40], rax
0x180125297  mov     r14, r9
0x18012529a  mov     rdi, rdx
0x18012529d  mov     r15, [rbp+30h+arg_20]
0x1801252a1  mov     rsi, [rbp+30h+arg_28]
0x1801252a5  xorps   xmm0, xmm0
0x1801252a8  movdqu  [rsp+130h+var_C8], xmm0
0x1801252ae  mov     [rsp+130h+var_B8], 0
0x1801252b7  mov     [rsp+130h+var_E0], ecx
0x1801252bb  mov     eax, [rdx]
0x1801252bd  mov     [rsp+130h+var_DC], eax
0x1801252c1  mov     rax, [r8]
0x1801252c4  mov     [rsp+130h+var_D8], rax
0x1801252c9  mov     rax, [r8+8]
0x1801252cd  mov     [rsp+130h+var_D0], rax
0x1801252d2  mov     r8, rsi; struct TDebugOutputFunctor *
0x1801252d5  mov     rcx, r9; struct D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION *
0x1801252d8  call    ?ValidateVideoEncoderCodecConfig@@YAJAEBUD3D12_VIDEO_ENCODER_CODEC_CONFIGURATION@@AEBW4D3D12_VIDEO_ENCODER_CODEC@@AEAUTDebugOutputFunctor@@@Z; ValidateVideoEncoderCodecConfig(D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION const &,D3D12_VIDEO_ENCODER_CODEC const &,TDebugOutputFunctor &)
0x1801252dd  test    eax, eax
0x1801252df  js      loc_180125ADD
0x1801252e5  mov     bl, 1
0x1801252e7  mov     ecx, [rdi]
0x1801252e9  test    ecx, ecx
0x1801252eb  jz      loc_180125944
0x1801252f1  sub     ecx, 1
0x1801252f4  jz      loc_1801253C8
0x1801252fa  cmp     ecx, 1
0x1801252fd  jnz     loc_180125ADD
0x180125303  lea     edi, [rcx+53h]
0x180125306  mov     r8d, edi; Size
0x180125309  xor     edx, edx; Val
0x18012530b  lea     rcx, [rbp+30h+var_A0]; void *
0x18012530f  call    memset_0
0x180125314  lea     rax, [rbp+30h+var_A0]
0x180125318  mov     [rsp+130h+var_B8], rax
0x18012531d  mov     dword ptr [rsp+130h+var_C8+8], edi
0x180125321  mov     rcx, [r15+2A8h]
0x180125328  mov     rax, [rcx]
0x18012532b  lea     r9d, [rdi-24h]
0x18012532f  lea     r8, [rsp+130h+var_E0]
0x180125334  lea     edx, [rdi-2Ah]
0x180125337  mov     rax, [rax+18h]
0x18012533b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125340  mov     edi, 51Eh
0x180125345  test    eax, eax
0x180125347  js      short loc_180125350
0x180125349  cmp     dword ptr [rsp+130h+var_C8], 0
0x18012534e  jnz     short loc_180125363
0x180125350  lea     r8, aD3d12VideoEnco_32; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180125357  mov     edx, edi
0x180125359  mov     rcx, rsi
0x18012535c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125361  xor     bl, bl
0x180125363  mov     rax, [r14+8]
0x180125367  mov     r9d, [rax]
0x18012536a  mov     eax, r9d
0x18012536d  mov     ecx, [rbp+30h+var_A0]
0x180125370  and     eax, ecx
0x180125372  cmp     eax, r9d
0x180125375  jz      short loc_18012538E
0x180125377  xor     bl, bl
0x180125379  mov     [rsp+130h+var_110], ecx
0x18012537d  lea     r8, aD3d12VideoEnco_89; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180125384  mov     edx, edi
0x180125386  mov     rcx, rsi
0x180125389  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18012538e  mov     rax, [r14+8]
0x180125392  mov     r9d, [rax]
0x180125395  mov     eax, r9d
0x180125398  mov     ecx, [rbp+30h+var_9C]
0x18012539b  and     eax, ecx
0x18012539d  cmp     eax, ecx
0x18012539f  jz      short loc_1801253B8
0x1801253a1  xor     bl, bl
0x1801253a3  mov     [rsp+130h+var_110], ecx
0x1801253a7  lea     r8, aD3d12VideoEnco_65; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x1801253ae  mov     edx, edi
0x1801253b0  mov     rcx, rsi
0x1801253b3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801253b8  neg     bl
0x1801253ba  sbb     eax, eax
0x1801253bc  not     eax
0x1801253be  and     eax, 80070057h
0x1801253c3  jmp     loc_180125AE2
0x1801253c8  mov     [rbp+30h+var_A0], 0
0x1801253cf  mov     rcx, [r14+8]
0x1801253d3  mov     eax, [rcx+4]
0x1801253d6  mov     [rbp+30h+var_9C], eax
0x1801253d9  mov     eax, [rcx+8]
0x1801253dc  mov     [rbp+30h+var_98], eax
0x1801253df  mov     eax, [rcx+0Ch]
0x1801253e2  mov     [rbp+30h+var_94], eax
0x1801253e5  mov     eax, [rcx+10h]
0x1801253e8  mov     [rbp+30h+var_90], eax
0x1801253eb  mov     al, [rcx+14h]
0x1801253ee  mov     [rbp+30h+var_8C], al
0x1801253f1  mov     al, [rcx+15h]
0x1801253f4  mov     [rbp+30h+var_8B], al
0x1801253f7  xor     eax, eax
0x1801253f9  mov     [rbp+30h+var_8A], ax
0x1801253fd  xor     edx, edx; Val
0x1801253ff  lea     r8d, [rax+48h]; Size
0x180125403  lea     rcx, [rbp+30h+var_88]; void *
0x180125407  call    memset_0
0x18012540c  mov     dl, bl
0x18012540e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444> `wil::Feature<__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444>::GetImpl(void)'::`2'::impl
0x180125415  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12VideoEncode_HEVC422444>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18012541a  mov     rax, [rsp+130h+var_D0]
0x18012541f  cmp     dword ptr [rax], 1
0x180125422  jg      short loc_180125437
0x180125424  lea     rcx, [rbp+30h+var_A0]
0x180125428  mov     [rsp+130h+var_B8], rcx
0x18012542d  mov     dword ptr [rsp+130h+var_C8+8], 18h
0x180125435  jmp     short loc_18012544D
0x180125437  cmp     dword ptr [rax], 8
0x18012543a  jg      short loc_18012544D
0x18012543c  lea     rax, [rbp+30h+var_A0]
0x180125440  mov     [rsp+130h+var_B8], rax
0x180125445  mov     dword ptr [rsp+130h+var_C8+8], 60h ; '`'
0x18012544d  mov     rcx, [r15+2A8h]
0x180125454  mov     rax, [rcx]
0x180125457  mov     r9d, 30h ; '0'
0x18012545d  lea     r8, [rsp+130h+var_E0]
0x180125462  lea     edx, [r9-6]
0x180125466  mov     rax, [rax+18h]
0x18012546a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012546f  mov     edi, 51Eh
0x180125474  test    eax, eax
0x180125476  js      short loc_18012547F
0x180125478  cmp     dword ptr [rsp+130h+var_C8], 0
0x18012547d  jnz     short loc_1801254C4
0x18012547f  mov     r9, [r14+8]
0x180125483  movzx   eax, byte ptr [r9+15h]
0x180125488  movzx   ecx, byte ptr [r9+14h]
0x18012548d  mov     [rsp+130h+var_F0], eax
0x180125491  mov     [rsp+130h+var_F8], ecx
0x180125495  mov     eax, [r9+10h]
0x180125499  mov     [rsp+130h+var_100], eax
0x18012549d  mov     eax, [r9+0Ch]
0x1801254a1  mov     [rsp+130h+var_108], eax
0x1801254a5  mov     eax, [r9+8]
0x1801254a9  mov     [rsp+130h+var_110], eax
0x1801254ad  mov     r9d, [r9+4]
0x1801254b1  lea     r8, aD3d12VideoEnco_77; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x1801254b8  mov     edx, edi
0x1801254ba  mov     rcx, rsi
0x1801254bd  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801254c2  xor     bl, bl
0x1801254c4  mov     rax, [r14+8]
0x1801254c8  mov     r15b, 80h
0x1801254cb  test    byte ptr [rax], 1
0x1801254ce  jz      short loc_1801254ED
0x1801254d0  mov     rax, [rsp+130h+var_B8]
0x1801254d5  test    [rax], r15b
0x1801254d8  jnz     short loc_1801254ED
0x1801254da  lea     r8, aD3d12VideoEnco_56; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x1801254e1  mov     edx, edi
0x1801254e3  mov     rcx, rsi
0x1801254e6  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801254eb  xor     bl, bl
0x1801254ed  mov     rax, [r14+8]
0x1801254f1  test    byte ptr [rax], 2
0x1801254f4  jz      short loc_180125513
0x1801254f6  mov     rax, [rsp+130h+var_B8]
0x1801254fb  test    byte ptr [rax], 2
0x1801254fe  jnz     short loc_180125513
0x180125500  lea     r8, aD3d12VideoEnco_70; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180125507  mov     edx, edi
0x180125509  mov     rcx, rsi
0x18012550c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125511  xor     bl, bl
0x180125513  mov     rax, [r14+8]
0x180125517  test    byte ptr [rax], 4
0x18012551a  jz      short loc_180125539
0x18012551c  mov     rax, [rsp+130h+var_B8]
0x180125521  test    byte ptr [rax], 8
0x180125524  jnz     short loc_180125539
0x180125526  lea     r8, aD3d12VideoEnco_76; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x18012552d  mov     edx, edi
0x18012552f  mov     rcx, rsi
0x180125532  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125537  xor     bl, bl
0x180125539  mov     rax, [r14+8]
0x18012553d  test    byte ptr [rax], 10h
0x180125540  jz      short loc_18012555F
0x180125542  mov     rax, [rsp+130h+var_B8]
0x180125547  test    byte ptr [rax], 10h
0x18012554a  jnz     short loc_18012555F
0x18012554c  lea     r8, aD3d12VideoEnco_99; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180125553  mov     edx, edi
0x180125555  mov     rcx, rsi
0x180125558  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18012555d  xor     bl, bl
0x18012555f  mov     rax, [r14+8]
0x180125563  test    byte ptr [rax], 10h
0x180125566  jnz     short loc_180125585
0x180125568  mov     rax, [rsp+130h+var_B8]
0x18012556d  test    byte ptr [rax], 20h
0x180125570  jz      short loc_180125585
0x180125572  lea     r8, aD3d12VideoEnco_103; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180125579  mov     edx, edi
0x18012557b  mov     rcx, rsi
0x18012557e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125583  xor     bl, bl
0x180125585  mov     rax, [r14+8]
0x180125589  test    byte ptr [rax], 20h
0x18012558c  jz      short loc_1801255AB
0x18012558e  mov     rax, [rsp+130h+var_B8]
0x180125593  test    byte ptr [rax], 40h
0x180125596  jnz     short loc_1801255AB
0x180125598  lea     r8, aD3d12VideoEnco_35; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x18012559f  mov     edx, edi
0x1801255a1  mov     rcx, rsi
0x1801255a4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801255a9  xor     bl, bl
0x1801255ab  mov     rax, [r14+8]
0x1801255af  test    byte ptr [rax], 40h
0x1801255b2  jz      short loc_1801255D1
0x1801255b4  mov     rax, [rsp+130h+var_B8]
0x1801255b9  test    byte ptr [rax], 4
0x1801255bc  jnz     short loc_1801255D1
0x1801255be  lea     r8, aD3d12VideoEnco_80; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x1801255c5  mov     edx, edi
0x1801255c7  mov     rcx, rsi
0x1801255ca  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801255cf  xor     bl, bl
0x1801255d1  mov     rax, [r14+8]
0x1801255d5  test    [rax], r15b
0x1801255d8  jz      short loc_1801255FA
0x1801255da  mov     rax, [rsp+130h+var_B8]
0x1801255df  test    dword ptr [rax], 400h
0x1801255e5  jnz     short loc_1801255FA
0x1801255e7  lea     r8, aD3d12VideoEnco_81; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x1801255ee  mov     edx, edi
0x1801255f0  mov     rcx, rsi
0x1801255f3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801255f8  xor     bl, bl
0x1801255fa  mov     rax, [r14+8]
0x1801255fe  test    [rax], r15b
0x180125601  jnz     short loc_180125623
0x180125603  mov     rax, [rsp+130h+var_B8]
0x180125608  test    dword ptr [rax], 800h
0x18012560e  jz      short loc_180125623
0x180125610  lea     r8, aD3d12VideoEnco_92; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180125617  mov     edx, edi
0x180125619  mov     rcx, rsi
0x18012561c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125621  xor     bl, bl
0x180125623  mov     rax, [r14+8]
0x180125627  mov     r15d, 100h
0x18012562d  test    [rax], r15d
0x180125630  jz      short loc_180125652
0x180125632  mov     rax, [rsp+130h+var_B8]
0x180125637  test    dword ptr [rax], 1000h
0x18012563d  jnz     short loc_180125652
0x18012563f  lea     r8, aD3d12VideoEnco_43; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x180125646  mov     edx, edi
0x180125648  mov     rcx, rsi
0x18012564b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125650  xor     bl, bl
0x180125652  mov     rax, [r14+8]
0x180125656  test    [rax], r15d
0x180125659  jnz     short loc_18012567B
0x18012565b  mov     rax, [rsp+130h+var_B8]
0x180125660  test    dword ptr [rax], 2000h
0x180125666  jz      short loc_18012567B
0x180125668  lea     r8, aD3d12VideoEnco_82; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x18012566f  mov     edx, edi
0x180125671  mov     rcx, rsi
0x180125674  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125679  xor     bl, bl
0x18012567b  mov     rax, [r14+8]
0x18012567f  mov     r15d, 200h
0x180125685  test    [rax], r15d
0x180125688  jz      short loc_1801256AA
0x18012568a  mov     rax, [rsp+130h+var_B8]
0x18012568f  test    dword ptr [rax], 4000h
0x180125695  jnz     short loc_1801256AA
0x180125697  lea     r8, aD3d12VideoEnco_112; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
0x18012569e  mov     edx, edi
0x1801256a0  mov     rcx, rsi
0x1801256a3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1801256a8  xor     bl, bl
0x1801256aa  mov     rax, [r14+8]
0x1801256ae  test    [rax], r15d
0x1801256b1  jnz     short loc_1801256D3
0x1801256b3  mov     rax, [rsp+130h+var_B8]
0x1801256b8  test    dword ptr [rax], 8000h
0x1801256be  jz      short loc_1801256D3
0x1801256c0  lea     r8, aD3d12VideoEnco_8; "D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION"...
  ... truncated ...
```
