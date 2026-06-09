# ValidateVideoEncoderSupportSimultaneousHazards(D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 const *,D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO const &,DeviceValidationInfo const &,TDebugOutputFunctor &)

- ea: `0x180246e70`
- end: `0x18024778e`
- name: `?ValidateVideoEncoderSupportSimultaneousHazards@@YAXPEBUD3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2@@AEBUD3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO@@AEBUDeviceValidationInfo@@AEAUTDebugOutputFunctor@@@Z`
- size: `2334`
- prototype: `void(const struct D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 *, const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *, const struct DeviceValidationInfo *, struct TDebugOutputFunctor *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802404b4`

## callees

- `0x18002ef50`
- `0x1800bb480`
- `0x1800bc010`
- `0x1800bc034`
- `0x180125274`
- `0x180125cb4`
- `0x180125eec`
- `0x180246e70`
- `0x180262020`

## string_xrefs

- `0x180246faa`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support for resolution when querying feature checks: D3D12_FEATURE_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT.`
- `0x180247740`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_QPMAP_NOT_SUPPORTED.`
- `0x180247728`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_MOTION_SEARCH_NOT_SUPPORTED.`
- `0x1802476e0`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_RESOLUTION_NOT_SUPPORTED_IN_LIST.`
- `0x1802476c8`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_SUBREGION_LAYOUT_MODE_NOT_SUPPORTED.`
- `0x180247710`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_DIRTY_REGIONS_NOT_SUPPORTED.`
- `0x1802476f8`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_GOP_STRUCTURE_NOT_SUPPORTED.`
- `0x180247681`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_RATE_CONTROL_MODE_NOT_SUPPORTED.`
- `0x180247669`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_CODEC_CONFIGURATION_NOT_SUPPORTED.`
- `0x1802476b0`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_INTRA_REFRESH_MODE_NOT_SUPPORTED.`
- `0x180247699`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_RATE_CONTROL_CONFIGURATION_NOT_SUPPORTED.`
- `0x180247621`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Individual feature query calls for input arguments for D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 are (0x%x) but combined support check returned (0x%x). This might be due to mutually exclusive features that are supported individually but not together. Please check the following configuration areas for such restrictions.`
- `0x180247651`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_INPUT_FORMAT_NOT_SUPPORTED.`
- `0x180247639`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_CODEC_NOT_SUPPORTED.`
- `0x180247758`: `D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for configuration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_FRAME_ANALYSIS_NOT_SUPPORTED.`

## pseudocode

```c
void __fastcall ValidateVideoEncoderSupportSimultaneousHazards(
        const struct D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 *a1,
        const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *a2,
        const struct DeviceValidationInfo *a3,
        struct TDebugOutputFunctor *a4)
{
  const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *v6; // r15
  const enum D3D12_VIDEO_ENCODER_CODEC *v8; // r12
  int v9; // edi
  __int64 v10; // rax
  unsigned int v11; // r14d
  char v12; // r15
  double v13; // xmm0_8
  const char *v15; // r8
  int v16; // r14d
  int v17; // edx
  int v18; // ecx
  int v19; // r14d
  int v20; // edi
  unsigned __int8 v21; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v22; // [rsp+31h] [rbp-CFh]
  unsigned int v24; // [rsp+40h] [rbp-C0h]
  _DWORD v25[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  _DWORD v29[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  int v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+8Ch] [rbp-74h]
  __int128 *v34; // [rsp+90h] [rbp-70h]
  _DWORD v35[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int128 v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+C0h] [rbp-40h]
  int v39; // [rsp+C4h] [rbp-3Ch]
  _DWORD v40[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v41; // [rsp+D0h] [rbp-30h]
  __int128 v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F4h] [rbp-Ch]
  _DWORD v45[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v46; // [rsp+108h] [rbp+8h]
  __int128 v47; // [rsp+118h] [rbp+18h]
  __int128 v48; // [rsp+128h] [rbp+28h]
  __int128 v49; // [rsp+138h] [rbp+38h]
  __int128 v50; // [rsp+148h] [rbp+48h]
  __int128 v51; // [rsp+158h] [rbp+58h]
  int v52; // [rsp+168h] [rbp+68h]
  int v53; // [rsp+16Ch] [rbp+6Ch]
  int v54; // [rsp+170h] [rbp+70h]
  __int64 v55; // [rsp+174h] [rbp+74h]
  __int64 v56; // [rsp+17Ch] [rbp+7Ch]
  __int64 v57; // [rsp+184h] [rbp+84h]
  int v58; // [rsp+18Ch] [rbp+8Ch]
  __int128 v59; // [rsp+190h] [rbp+90h]
  _DWORD v60[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v61; // [rsp+1A8h] [rbp+A8h]
  __int128 v62; // [rsp+1B8h] [rbp+B8h]
  __int128 v63; // [rsp+1C8h] [rbp+C8h]
  __int128 v64; // [rsp+1D8h] [rbp+D8h]
  __int128 v65; // [rsp+1E8h] [rbp+E8h]
  __int128 v66; // [rsp+1F8h] [rbp+F8h]
  int v67; // [rsp+208h] [rbp+108h]
  __int64 v68; // [rsp+20Ch] [rbp+10Ch]
  int v69; // [rsp+214h] [rbp+114h]
  _DWORD v70[2]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v71; // [rsp+228h] [rbp+128h]
  __int128 v72; // [rsp+238h] [rbp+138h]
  __int128 v73; // [rsp+248h] [rbp+148h]
  __int128 v74; // [rsp+258h] [rbp+158h]
  __int128 v75; // [rsp+268h] [rbp+168h]
  __int128 v76; // [rsp+278h] [rbp+178h]
  int v77; // [rsp+288h] [rbp+188h]
  int v78; // [rsp+28Ch] [rbp+18Ch]
  __int64 v79; // [rsp+290h] [rbp+190h]
  _DWORD v80[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v81; // [rsp+2A8h] [rbp+1A8h]
  _DWORD v82[3]; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v83; // [rsp+2BCh] [rbp+1BCh]
  __int128 v84; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v85; // [rsp+2D0h] [rbp+1D0h]
  _DWORD v86[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v87; // [rsp+2E8h] [rbp+1E8h]
  __int128 v88; // [rsp+2F8h] [rbp+1F8h]
  int v89; // [rsp+308h] [rbp+208h]
  __int64 v90; // [rsp+30Ch] [rbp+20Ch]
  int v91; // [rsp+314h] [rbp+214h]
  __int128 v92; // [rsp+318h] [rbp+218h]
  int v93; // [rsp+328h] [rbp+228h]
  int v94; // [rsp+32Ch] [rbp+22Ch]
  __int128 v95; // [rsp+330h] [rbp+230h]
  __int64 v96; // [rsp+340h] [rbp+240h]
  __int64 v97; // [rsp+348h] [rbp+248h]
  int v98; // [rsp+350h] [rbp+250h]
  __int128 v99; // [rsp+354h] [rbp+254h]
  int v100; // [rsp+364h] [rbp+264h]
  __int64 v101; // [rsp+368h] [rbp+268h]

  v6 = a2;
  v80[0] = *(_DWORD *)a1;
  v8 = (const struct D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 *)((char *)a1 + 4);
  v80[1] = *((_DWORD *)a1 + 1);
  v81 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(*((_QWORD *)a3 + 85), 33, v80) < 0
    || (v9 = 0, !v81) )
  {
    v9 = 1;
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support when querying feature check: D3D12_FEATURE_VIDEO_ENCODER_CODEC.");
  }
  v25[0] = *(_DWORD *)a1;
  v25[1] = *(_DWORD *)v8;
  v26 = *(_OWORD *)((char *)a1 + 120);
  v27 = *((_DWORD *)a1 + 2);
  v28 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(*((_QWORD *)a3 + 85), 37, v25) < 0
    || !v28 )
  {
    v9 |= 8u;
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support when querying feature check: D3D12_FEATURE_VIDEO_ENCODER_INPUT_FORMAT.");
  }
  if ( (int)ValidateVideoEncodeCodecConfig(
              *(_DWORD *)a1,
              v8,
              (const struct D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 *)((char *)a1 + 120),
              (const struct D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 *)((char *)a1 + 16),
              a3,
              a4) < 0 )
  {
    v9 |= 0x10u;
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support for resolution when querying feature checks: D3D12_FEATURE"
      "_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT.");
  }
  if ( !*(_DWORD *)v8 )
  {
    v84 = 0;
    v85 = 0;
    v59 = 0;
    v29[0] = *(_DWORD *)a1;
    v29[1] = 0;
    v30 = *(_OWORD *)((char *)a1 + 120);
    v31 = 0;
    v32 = 20;
    v33 = 0;
    v34 = &v84;
    if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))(**((_QWORD **)a3 + 85) + 24LL))(
           *((_QWORD *)a3 + 85),
           44,
           v29,
           48) < 0
      || !(_DWORD)v31 )
    {
      v9 |= 0x800u;
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support when querying feature check: D3D12_FEATURE_VIDEO_ENCODER"
        "_CODEC_PICTURE_CONTROL_SUPPORT.");
    }
    v10 = *((_QWORD *)a1 + 5);
    v24 = *(_DWORD *)v10;
    v11 = *(_DWORD *)(v10 + 4);
    v12 = *(_BYTE *)(v10 + 8);
    v21 = *(_BYTE *)(v10 + 9);
    v22 = *(_BYTE *)(v10 + 10);
    if ( (v12 & 0xFD) != 0 )
    {
      v9 |= 0x800u;
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Values allowed for pic_order_cnt_type are 0 or 2.");
    }
    o_log2_0();
    v13 = fmax(o_ceil_0() - 4.0, 0.0);
    if ( (double)v21 > v13 || (double)v22 > v13 )
    {
      v9 |= 0x800u;
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] log2_max_frame_num_minus4 or m_log2_max_pic_order_cnt_lsb_minus4 ha"
        "ve a bigger frame address range than MaxDPBCapacity reported in D3D12_FEATURE_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT");
    }
    if ( !v11 || v11 >= v24 )
    {
      if ( v11 > 1 || v12 == 2 )
        goto LABEL_32;
      v15 = "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Invalid pic_order_cnt_type should be 2 for GOPS with only I Frames";
      goto LABEL_31;
    }
    if ( v11 <= 1 )
    {
      if ( v12 != 2 )
      {
        v15 = "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Invalid pic_order_cnt_type should be 2 for GOPS with only I and P Frames";
        goto LABEL_31;
      }
    }
    else if ( v12 )
    {
      v15 = "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Invalid pic_order_cnt_type should be 0 for GOPS with B Frames";
LABEL_31:
      v9 |= 0x800u;
      TDebugOutputFunctor::operator()(a4, 1306, v15);
    }
LABEL_32:
    v6 = a2;
  }
  v82[0] = *(_DWORD *)a1;
  v82[1] = *(_DWORD *)v8;
  v82[2] = *((_DWORD *)a1 + 12);
  v83 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(*((_QWORD *)a3 + 85), 38, v82) < 0
    || !v83 )
  {
    v9 |= 0x20u;
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support when querying feature check: D3D12_FEATURE_VIDEO_ENCODER_R"
      "ATE_CONTROL_MODE.");
  }
  v16 = v9 | 0x40;
  if ( (int)ValidateVideoEncodeRateControl(
              (const struct D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 *)((char *)a1 + 48),
              a4) >= 0 )
    v16 = v9;
  v35[0] = *(_DWORD *)a1;
  v35[1] = *(_DWORD *)v8;
  v36 = *(_OWORD *)((char *)a1 + 120);
  v37 = *(_OWORD *)((char *)a1 + 136);
  v38 = *((_DWORD *)a1 + 20);
  v39 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))(**((_QWORD **)a3 + 85) + 24LL))(
         *((_QWORD *)a3 + 85),
         39,
         v35,
         48) < 0
    || !v39 )
  {
    v16 |= 0x80u;
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support when querying feature check: D3D12_FEATURE_VIDEO_ENCODER_I"
      "NTRA_REFRESH_MODE.");
  }
  v40[0] = *(_DWORD *)a1;
  v40[1] = *(_DWORD *)v8;
  v41 = *(_OWORD *)((char *)a1 + 120);
  v42 = *(_OWORD *)((char *)a1 + 136);
  v43 = *((_DWORD *)a1 + 21);
  v44 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(*((_QWORD *)a3 + 85), 40, v40) < 0
    || !v44 )
  {
    v16 |= 0x100u;
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support when querying feature check: D3D12_FEATURE_VIDEO_ENCODER_F"
      "RAME_SUBREGION_LAYOUT_MODE.");
  }
  if ( (int)ValidateVideoEncodeResolutionsListSupported(
              *(_DWORD *)a1,
              v8,
              *((_DWORD *)a1 + 22),
              *((const struct D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC **)a1 + 12),
              a3) < 0 )
  {
    v16 |= 0x200u;
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] No support for resolution when querying feature checks: D3D12_FEATURE"
      "_VIDEO_ENCODER_OUTPUT_RESOLUTION.");
  }
  v17 = *((_DWORD *)a1 + 27);
  v18 = v16 | 0x40;
  if ( (v17 & 0x40) == 0 )
    v18 = v16;
  v19 = v18 | 0x800;
  if ( (v17 & 0x800) == 0 )
    v19 = v18;
  v60[0] = *(_DWORD *)a1;
  v60[1] = 0;
  v61 = *(_OWORD *)v6;
  v62 = *((_OWORD *)v6 + 1);
  v63 = *((_OWORD *)v6 + 2);
  v64 = *((_OWORD *)v6 + 3);
  v65 = *((_OWORD *)v6 + 4);
  v66 = *((_OWORD *)v6 + 5);
  v67 = *((_DWORD *)a1 + 46);
  v68 = 0;
  v69 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(*((_QWORD *)a3 + 85), 50, v60) < 0
    || !(_DWORD)v68 )
  {
    v19 |= 0x2000u;
  }
  v70[0] = *(_DWORD *)a1;
  v70[1] = 0;
  v71 = *(_OWORD *)v6;
  v72 = *((_OWORD *)v6 + 1);
  v73 = *((_OWORD *)v6 + 2);
  v74 = *((_OWORD *)v6 + 3);
  v75 = *((_OWORD *)v6 + 4);
  v76 = *((_OWORD *)v6 + 5);
  v77 = *((_DWORD *)a1 + 48);
  v78 = *((_DWORD *)a1 + 49);
  v79 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(*((_QWORD *)a3 + 85), 51, v70) < 0
    || !(_DWORD)v79 )
  {
    v19 |= 0x4000u;
  }
  v45[0] = *(_DWORD *)a1;
  v45[1] = 0;
  v46 = *(_OWORD *)v6;
  v47 = *((_OWORD *)v6 + 1);
  v48 = *((_OWORD *)v6 + 2);
  v49 = *((_OWORD *)v6 + 3);
  v50 = *((_OWORD *)v6 + 4);
  v51 = *((_OWORD *)v6 + 5);
  v52 = *((_DWORD *)a1 + 52);
  v53 = *((_DWORD *)a1 + 51);
  v54 = *((_DWORD *)a1 + 53);
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(*((_QWORD *)a3 + 85), 52, v45) < 0
    || (v55 & 1) == 0 )
  {
    v19 |= 0x8000u;
  }
  if ( *((_DWORD *)a1 + 54) )
  {
    v86[0] = *(_DWORD *)a1;
    v86[1] = *(_DWORD *)v6;
    v87 = *(_OWORD *)((char *)v6 + 8);
    v88 = *(_OWORD *)((char *)v6 + 24);
    v89 = *((_DWORD *)v6 + 10);
    v90 = *(_QWORD *)((char *)v6 + 44);
    v91 = 0;
    v92 = *(_OWORD *)((char *)v6 + 56);
    v93 = *((_DWORD *)v6 + 18);
    v94 = 0;
    v95 = *((_OWORD *)v6 + 5);
    v96 = *(_QWORD *)((char *)a1 + 180);
    v97 = *(_QWORD *)((char *)a1 + 188);
    v98 = *((_DWORD *)a1 + 49);
    v99 = *(_OWORD *)((char *)a1 + 200);
    v100 = *((_DWORD *)a1 + 55);
    v101 = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a3 + 85) + 24LL))(
           *((_QWORD *)a3 + 85),
           57,
           v86) < 0
      || (v101 & 7) == 0 )
    {
      v19 |= 0x10000u;
    }
  }
  v20 = v19 ^ *((_DWORD *)a1 + 27);
  if ( v20 )
  {
    TDebugOutputFunctor::operator()(
      a4,
      1306,
      "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Individual feature query calls for input arguments for D3D12_FEATURE_"
      "DATA_VIDEO_ENCODER_SUPPORT2 are (0x%x) but combined support check returned (0x%x). This might be due to mutually e"
      "xclusive features that are supported individually but not together. Please check the following configuration areas"
      " for such restrictions.",
      v19,
      *((_DWORD *)a1 + 27));
    if ( (v20 & 1) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_CODEC_NOT_SUPPORTED.");
    if ( (v20 & 8) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_INPUT_FORMAT_NOT_SUPPORTED.");
    if ( (v20 & 0x10) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_CODEC_CONFIGURATION_NOT_SUPPORTED.");
    if ( (v20 & 0x20) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_RATE_CONTROL_MODE_NOT_SUPPORTED.");
    if ( (v20 & 0x40) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_RATE_CONTROL_CONFIGURATION_NOT_SUPPORTED.");
    if ( (v20 & 0x80u) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_INTRA_REFRESH_MODE_NOT_SUPPORTED.");
    if ( (v20 & 0x100) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_SUBREGION_LAYOUT_MODE_NOT_SUPPORTED.");
    if ( (v20 & 0x200) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_RESOLUTION_NOT_SUPPORTED_IN_LIST.");
    if ( (v20 & 0x800) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_GOP_STRUCTURE_NOT_SUPPORTED.");
    if ( (v20 & 0x4000) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_DIRTY_REGIONS_NOT_SUPPORTED.");
    if ( (v20 & 0x8000) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_MOTION_SEARCH_NOT_SUPPORTED.");
    if ( (v20 & 0x2000) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_QPMAP_NOT_SUPPORTED.");
    if ( (v20 & 0x10000) != 0 )
      TDebugOutputFunctor::operator()(
        a4,
        1306,
        "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUPPORT] Conflicting individual support and combined support checks for conf"
        "iguration area: D3D12_VIDEO_ENCODER_VALIDATION_FLAG_FRAME_ANALYSIS_NOT_SUPPORTED.");
  }
}

```

## disassembly

```asm
0x180246e70  push    rbp
0x180246e72  push    rbx
0x180246e73  push    rsi
0x180246e74  push    rdi
0x180246e75  push    r12
0x180246e77  push    r13
0x180246e79  push    r14
0x180246e7b  push    r15
0x180246e7d  lea     rbp, [rsp-288h]
0x180246e85  sub     rsp, 388h
0x180246e8c  mov     rax, cs:__security_cookie
0x180246e93  xor     rax, rsp
0x180246e96  mov     [rbp+2C0h+var_50], rax
0x180246e9d  mov     rbx, r9
0x180246ea0  mov     r13, r8
0x180246ea3  mov     r15, rdx
0x180246ea6  mov     [rsp+3C0h+var_388], rdx
0x180246eab  mov     rsi, rcx
0x180246eae  mov     eax, [rcx]
0x180246eb0  mov     [rbp+2C0h+var_120], eax
0x180246eb6  lea     r12, [rcx+4]
0x180246eba  mov     eax, [r12]
0x180246ebe  mov     [rbp+2C0h+var_11C], eax
0x180246ec4  mov     [rbp+2C0h+var_118], 0
0x180246ece  mov     rcx, [r8+2A8h]
0x180246ed5  mov     rax, [rcx]
0x180246ed8  mov     r9d, 0Ch
0x180246ede  lea     r8, [rbp+2C0h+var_120]
0x180246ee5  lea     edx, [r9+15h]
0x180246ee9  mov     rax, [rax+18h]
0x180246eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246ef2  test    eax, eax
0x180246ef4  js      short loc_180246F00
0x180246ef6  xor     edi, edi
0x180246ef8  cmp     [rbp+2C0h+var_118], edi
0x180246efe  jnz     short loc_180246F19
0x180246f00  mov     edi, 1
0x180246f05  lea     r8, aD3d12D3d12Feat_22; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x180246f0c  mov     edx, 51Ah
0x180246f11  mov     rcx, rbx
0x180246f14  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246f19  mov     eax, [rsi]
0x180246f1b  mov     [rsp+3C0h+var_378], eax
0x180246f1f  mov     eax, [r12]
0x180246f23  mov     [rsp+3C0h+var_374], eax
0x180246f27  lea     r14, [rsi+78h]
0x180246f2b  movups  xmm0, xmmword ptr [r14]
0x180246f2f  movdqu  [rsp+3C0h+var_370], xmm0
0x180246f35  mov     eax, [rsi+8]
0x180246f38  mov     [rsp+3C0h+var_360], eax
0x180246f3c  mov     [rsp+3C0h+var_35C], 0
0x180246f44  mov     rcx, [r13+2A8h]
0x180246f4b  mov     rax, [rcx]
0x180246f4e  mov     r9d, 20h ; ' '
0x180246f54  lea     r8, [rsp+3C0h+var_378]
0x180246f59  lea     edx, [r9+5]
0x180246f5d  mov     rax, [rax+18h]
0x180246f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246f66  test    eax, eax
0x180246f68  js      short loc_180246F71
0x180246f6a  cmp     [rsp+3C0h+var_35C], 0
0x180246f6f  jnz     short loc_180246F88
0x180246f71  or      edi, 8
0x180246f74  lea     r8, aD3d12D3d12Feat_0; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x180246f7b  mov     edx, 51Ah
0x180246f80  mov     rcx, rbx
0x180246f83  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246f88  lea     r9, [rsi+10h]; struct D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION *
0x180246f8c  mov     [rsp+3C0h+var_398], rbx; struct TDebugOutputFunctor *
0x180246f91  mov     [rsp+3C0h+var_3A0], r13; struct DeviceValidationInfo *
0x180246f96  mov     r8, r14; struct D3D12_VIDEO_ENCODER_PROFILE_DESC *
0x180246f99  mov     rdx, r12; enum D3D12_VIDEO_ENCODER_CODEC *
0x180246f9c  mov     ecx, [rsi]; unsigned int
0x180246f9e  call    ?ValidateVideoEncodeCodecConfig@@YAJIAEBW4D3D12_VIDEO_ENCODER_CODEC@@AEBUD3D12_VIDEO_ENCODER_PROFILE_DESC@@AEBUD3D12_VIDEO_ENCODER_CODEC_CONFIGURATION@@AEBUDeviceValidationInfo@@AEAUTDebugOutputFunctor@@@Z; ValidateVideoEncodeCodecConfig(uint,D3D12_VIDEO_ENCODER_CODEC const &,D3D12_VIDEO_ENCODER_PROFILE_DESC const &,D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION const &,DeviceValidationInfo const &,TDebugOutputFunctor &)
0x180246fa3  test    eax, eax
0x180246fa5  jns     short loc_180246FBE
0x180246fa7  or      edi, 10h
0x180246faa  lea     r8, aD3d12D3d12Feat_6; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x180246fb1  mov     edx, 51Ah
0x180246fb6  mov     rcx, rbx
0x180246fb9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246fbe  cmp     dword ptr [r12], 0
0x180246fc3  jnz     loc_180247161
0x180246fc9  xorps   xmm0, xmm0
0x180246fcc  xor     eax, eax
0x180246fce  movups  [rbp+2C0h+var_100], xmm0
0x180246fd5  mov     [rbp+2C0h+var_F0], eax
0x180246fdb  movups  [rbp+2C0h+var_230], xmm0
0x180246fe2  mov     eax, [rsi]
0x180246fe4  mov     [rsp+3C0h+var_358], eax
0x180246fe8  xor     r15d, r15d
0x180246feb  mov     [rsp+3C0h+var_354], r15d
0x180246ff0  movups  xmm0, xmmword ptr [r14]
0x180246ff4  movdqu  [rsp+3C0h+var_350], xmm0
0x180246ffa  mov     [rbp+2C0h+var_340], r15
0x180246ffe  mov     [rbp+2C0h+var_338], 14h
0x180247005  mov     eax, dword ptr [rbp+2C0h+var_230+4]
0x18024700b  mov     [rbp+2C0h+var_334], eax
0x18024700e  lea     rax, [rbp+2C0h+var_100]
0x180247015  mov     [rbp+2C0h+var_330], rax
0x180247019  mov     rcx, [r13+2A8h]
0x180247020  mov     rax, [rcx]
0x180247023  lea     r9d, [r15+30h]
0x180247027  lea     r8, [rsp+3C0h+var_358]
0x18024702c  lea     edx, [r15+2Ch]
0x180247030  mov     rax, [rax+18h]
0x180247034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180247039  test    eax, eax
0x18024703b  js      short loc_180247043
0x18024703d  cmp     dword ptr [rbp+2C0h+var_340], r15d
0x180247041  jnz     short loc_18024705B
0x180247043  bts     edi, 0Bh
0x180247047  lea     r8, aD3d12D3d12Feat_7; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x18024704e  mov     edx, 51Ah
0x180247053  mov     rcx, rbx
0x180247056  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024705b  mov     rax, [rsi+28h]
0x18024705f  mov     ecx, [rax]
0x180247061  mov     [rsp+3C0h+var_380], ecx
0x180247065  mov     r14d, [rax+4]
0x180247069  mov     r15b, [rax+8]
0x18024706d  mov     cl, [rax+9]
0x180247070  mov     [rsp+3C0h+var_390], cl
0x180247074  mov     al, [rax+0Ah]
0x180247077  mov     [rsp+3C0h+var_38F], al
0x18024707b  test    r15b, 0FDh
0x18024707f  jz      short loc_180247099
0x180247081  bts     edi, 0Bh
0x180247085  lea     r8, aD3d12D3d12Feat_13; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x18024708c  mov     edx, 51Ah
0x180247091  mov     rcx, rbx
0x180247094  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180247099  mov     eax, [rbp+2C0h+var_F0]
0x18024709f  xorps   xmm0, xmm0
0x1802470a2  cvtsi2sd xmm0, rax
0x1802470a7  call    _o_log2_0
0x1802470ac  call    _o_ceil_0
0x1802470b1  subsd   xmm0, cs:__real@4010000000000000
0x1802470b9  maxsd   xmm0, cs:__real@0000000000000000
0x1802470c1  movzx   eax, [rsp+3C0h+var_390]
0x1802470c6  movd    xmm1, eax
0x1802470ca  cvtdq2pd xmm1, xmm1
0x1802470ce  comisd  xmm1, xmm0
0x1802470d2  ja      short loc_1802470E7
0x1802470d4  movzx   eax, [rsp+3C0h+var_38F]
0x1802470d9  movd    xmm1, eax
0x1802470dd  cvtdq2pd xmm1, xmm1
0x1802470e1  comisd  xmm1, xmm0
0x1802470e5  jbe     short loc_1802470FF
0x1802470e7  bts     edi, 0Bh
0x1802470eb  lea     r8, aD3d12D3d12Feat_24; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x1802470f2  mov     edx, 51Ah
0x1802470f7  mov     rcx, rbx
0x1802470fa  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802470ff  test    r14d, r14d
0x180247102  jz      short loc_18024710F
0x180247104  cmp     r14d, [rsp+3C0h+var_380]
0x180247109  jnb     short loc_18024710F
0x18024710b  mov     al, 1
0x18024710d  jmp     short loc_180247111
0x18024710f  xor     al, al
0x180247111  test    al, al
0x180247113  jz      short loc_180247138
0x180247115  cmp     r14d, 1
0x180247119  jbe     short loc_180247129
0x18024711b  test    r15b, r15b
0x18024711e  jz      short loc_18024715C
0x180247120  lea     r8, aD3d12D3d12Feat_3; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x180247127  jmp     short loc_18024714B
0x180247129  cmp     r15b, 2
0x18024712d  jz      short loc_18024715C
0x18024712f  lea     r8, aD3d12D3d12Feat_19; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x180247136  jmp     short loc_18024714B
0x180247138  cmp     r14d, 1
0x18024713c  ja      short loc_18024715C
0x18024713e  cmp     r15b, 2
0x180247142  jz      short loc_18024715C
0x180247144  lea     r8, aD3d12D3d12Feat_18; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x18024714b  bts     edi, 0Bh
0x18024714f  mov     edx, 51Ah
0x180247154  mov     rcx, rbx
0x180247157  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024715c  mov     r15, [rsp+3C0h+var_388]
0x180247161  mov     eax, [rsi]
0x180247163  mov     [rbp+2C0h+var_110], eax
0x180247169  mov     eax, [r12]
0x18024716d  mov     [rbp+2C0h+var_10C], eax
0x180247173  mov     eax, [rsi+30h]
0x180247176  mov     [rbp+2C0h+var_108], eax
0x18024717c  mov     [rbp+2C0h+var_104], 0
0x180247186  mov     rcx, [r13+2A8h]
0x18024718d  mov     rax, [rcx]
0x180247190  mov     r9d, 10h
0x180247196  lea     r8, [rbp+2C0h+var_110]
0x18024719d  lea     edx, [r9+16h]
0x1802471a1  mov     rax, [rax+18h]
0x1802471a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802471aa  test    eax, eax
0x1802471ac  js      short loc_1802471B7
0x1802471ae  cmp     [rbp+2C0h+var_104], 0
0x1802471b5  jnz     short loc_1802471CE
0x1802471b7  or      edi, 20h
0x1802471ba  lea     r8, aD3d12D3d12Feat_4; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x1802471c1  mov     edx, 51Ah
0x1802471c6  mov     rcx, rbx
0x1802471c9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802471ce  mov     rdx, rbx; struct TDebugOutputFunctor *
0x1802471d1  lea     rcx, [rsi+30h]; struct D3D12_VIDEO_ENCODER_RATE_CONTROL *
0x1802471d5  call    ?ValidateVideoEncodeRateControl@@YAJAEBUD3D12_VIDEO_ENCODER_RATE_CONTROL@@AEAUTDebugOutputFunctor@@@Z; ValidateVideoEncodeRateControl(D3D12_VIDEO_ENCODER_RATE_CONTROL const &,TDebugOutputFunctor &)
0x1802471da  mov     r14d, edi
0x1802471dd  or      r14d, 40h
0x1802471e1  test    eax, eax
0x1802471e3  cmovns  r14d, edi
0x1802471e7  mov     eax, [rsi]
0x1802471e9  mov     [rbp+2C0h+var_328], eax
0x1802471ec  mov     eax, [r12]
0x1802471f0  mov     [rbp+2C0h+var_324], eax
0x1802471f3  movups  xmm0, xmmword ptr [rsi+78h]
0x1802471f7  movdqu  [rbp+2C0h+var_320], xmm0
0x1802471fc  movups  xmm0, xmmword ptr [rsi+88h]
0x180247203  movdqu  [rbp+2C0h+var_310], xmm0
0x180247208  mov     eax, [rsi+50h]
0x18024720b  mov     [rbp+2C0h+var_300], eax
0x18024720e  xor     edi, edi
0x180247210  mov     [rbp+2C0h+var_2FC], edi
0x180247213  mov     rcx, [r13+2A8h]
0x18024721a  mov     rax, [rcx]
0x18024721d  lea     r9d, [rdi+30h]
0x180247221  lea     r8, [rbp+2C0h+var_328]
0x180247225  lea     edx, [rdi+27h]
0x180247228  mov     rax, [rax+18h]
0x18024722c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180247231  test    eax, eax
0x180247233  js      short loc_18024723A
0x180247235  cmp     [rbp+2C0h+var_2FC], edi
0x180247238  jnz     short loc_180247253
0x18024723a  bts     r14d, 7
0x18024723f  lea     r8, aD3d12D3d12Feat_23; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x180247246  mov     edx, 51Ah
0x18024724b  mov     rcx, rbx
0x18024724e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180247253  mov     eax, [rsi]
0x180247255  mov     [rbp+2C0h+var_2F8], eax
0x180247258  mov     eax, [r12]
0x18024725c  mov     [rbp+2C0h+var_2F4], eax
0x18024725f  movups  xmm0, xmmword ptr [rsi+78h]
0x180247263  movdqu  [rbp+2C0h+var_2F0], xmm0
0x180247268  movups  xmm1, xmmword ptr [rsi+88h]
0x18024726f  movdqu  [rbp+2C0h+var_2E0], xmm1
0x180247274  mov     eax, [rsi+54h]
0x180247277  mov     [rbp+2C0h+var_2D0], eax
0x18024727a  mov     [rbp+2C0h+var_2CC], edi
0x18024727d  mov     rcx, [r13+2A8h]
0x180247284  mov     rax, [rcx]
0x180247287  mov     r9d, 30h ; '0'
0x18024728d  lea     r8, [rbp+2C0h+var_2F8]
0x180247291  lea     edx, [r9-8]
0x180247295  mov     rax, [rax+18h]
0x180247299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024729e  test    eax, eax
0x1802472a0  js      short loc_1802472A7
0x1802472a2  cmp     [rbp+2C0h+var_2CC], edi
0x1802472a5  jnz     short loc_1802472C0
0x1802472a7  bts     r14d, 8
0x1802472ac  lea     r8, aD3d12D3d12Feat_20; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x1802472b3  mov     edx, 51Ah
0x1802472b8  mov     rcx, rbx
0x1802472bb  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802472c0  mov     [rsp+3C0h+var_3A0], r13; struct DeviceValidationInfo *
0x1802472c5  mov     r9, [rsi+60h]; struct D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC *
0x1802472c9  mov     r8d, [rsi+58h]; unsigned int
0x1802472cd  mov     rdx, r12; enum D3D12_VIDEO_ENCODER_CODEC *
0x1802472d0  mov     ecx, [rsi]; unsigned int
0x1802472d2  call    ?ValidateVideoEncodeResolutionsListSupported@@YAJIAEBW4D3D12_VIDEO_ENCODER_CODEC@@IPEBUD3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC@@AEBUDeviceValidationInfo@@@Z; ValidateVideoEncodeResolutionsListSupported(uint,D3D12_VIDEO_ENCODER_CODEC const &,uint,D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC const *,DeviceValidationInfo const &)
0x1802472d7  mov     r12d, 51Ah
0x1802472dd  test    eax, eax
0x1802472df  jns     short loc_1802472F8
0x1802472e1  bts     r14d, 9
0x1802472e6  lea     r8, aD3d12D3d12Feat; "D3D12: [D3D12_FEATURE_VIDEO_ENCODER_SUP"...
0x1802472ed  mov     edx, r12d
0x1802472f0  mov     rcx, rbx
0x1802472f3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802472f8  mov     edx, [rsi+6Ch]
0x1802472fb  mov     ecx, r14d
0x1802472fe  or      ecx, 40h
0x180247301  test    dl, 40h
0x180247304  cmovz   ecx, r14d
0x180247308  mov     eax, 800h
0x18024730d  mov     r14d, ecx
0x180247310  or      r14d, eax
0x180247313  test    eax, edx
0x180247315  cmovz   r14d, ecx
0x180247319  mov     eax, [rsi]
0x18024731b  mov     [rbp+2C0h+var_220], eax
0x180247321  xor     eax, eax
0x180247323  mov     [rbp+2C0h+var_21C], eax
0x180247329  movaps  xmm0, xmmword ptr [r15]
0x18024732d  movups  [rbp+2C0h+var_218], xmm0
0x180247334  movaps  xmm1, xmmword ptr [r15+10h]
0x180247339  movups  [rbp+2C0h+var_208], xmm1
  ... truncated ...
```
