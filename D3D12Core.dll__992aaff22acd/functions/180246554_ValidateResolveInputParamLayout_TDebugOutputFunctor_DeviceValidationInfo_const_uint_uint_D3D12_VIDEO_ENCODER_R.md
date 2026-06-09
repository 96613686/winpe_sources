# ValidateResolveInputParamLayout(TDebugOutputFunctor &,DeviceValidationInfo const &,uint,uint,D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_INPUT_ARGUMENTS const *,D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_OUTPUT_ARGUMENTS const *)

- ea: `0x180246554`
- end: `0x180246be1`
- name: `?ValidateResolveInputParamLayout@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@IIPEBUD3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_INPUT_ARGUMENTS@@PEBUD3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_OUTPUT_ARGUMENTS@@@Z`
- size: `1677`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, const struct DeviceValidationInfo *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const struct D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_INPUT_ARGUMENTS *, const struct D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_OUTPUT_ARGUMENTS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18023f318`

## callees

- `0x18002ef50`
- `0x1800bc01c`
- `0x18023ae58`
- `0x18023c618`
- `0x180244e44`
- `0x180246554`
- `0x180262020`

## string_xrefs

- `0x1802465a2`: `ID3D12VideoEncodeCommandList::ResolveInputParamLayout arguments are not correct - pInputArguments cannot be null.`
- `0x180246aa7`: `D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::MotionSearchModeConfiguration::SearchDeviationLimit (%d) must fit within the bounds reported in D3D12_FEATURE_DATA_VIDEO_ENCODER_MOTION_SEARCH (MinDeviation: %d) (MaxDeviation: %d)`
- `0x180246af2`: `D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::NumHintsPerPixel (%d) must be greater than zero to perform the ResolveInputParamLayout command.`
- `0x1802465de`: `ID3D12VideoEncodeCommandList::ResolveInputParamLayout arguments are not correct - pOutputArguments->pOpaqueLayoutBuffer cannot be null.`
- `0x1802465c3`: `ID3D12VideoEncodeCommandList::ResolveInputParamLayout arguments are not correct - pOutputArguments cannot be null.`
- `0x180246664`: `ID3D12VideoEncodeCommandList::ResolveInputParamLayout Failure on call to CheckFeatureSupport(D3D12_FEATURE_VIDEO_ARCHITECTURE,...).`

## pseudocode

```c
__int64 __fastcall ValidateResolveInputParamLayout(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        __int64 a3,
        unsigned int a4,
        const struct D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_INPUT_ARGUMENTS *a5,
        struct ID3D12Resource **a6)
{
  unsigned int v8; // eax
  unsigned int v9; // r12d
  char v10; // al
  const struct D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_INPUT_ARGUMENTS *v11; // rsi
  struct ID3D12Resource **v12; // rbx
  __int64 result; // rax
  char v15; // r14
  int v16; // eax
  int *v17; // rbx
  float v18; // xmm6_4
  int v19; // ebx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  char v23; // al
  _DWORD *v24; // rbx
  unsigned int v25; // r9d
  int v26; // eax
  unsigned int v27; // r9d
  __int64 v28; // rcx
  unsigned int v29; // r9d
  unsigned int i; // r12d
  char v31; // bl
  __int64 v32; // rcx
  unsigned int v33; // [rsp+50h] [rbp-D8h] BYREF
  int v34; // [rsp+54h] [rbp-D4h]
  __int128 v35; // [rsp+58h] [rbp-D0h]
  __int128 v36; // [rsp+68h] [rbp-C0h]
  __int128 v37; // [rsp+78h] [rbp-B0h]
  __int128 v38; // [rsp+88h] [rbp-A0h]
  __int128 v39; // [rsp+98h] [rbp-90h]
  __int128 v40; // [rsp+A8h] [rbp-80h]
  _BYTE v41[20]; // [rsp+B8h] [rbp-70h]
  __int64 v42; // [rsp+CCh] [rbp-5Ch]
  __int64 v43; // [rsp+D4h] [rbp-54h]
  int v44; // [rsp+DCh] [rbp-4Ch]
  _com_error *v45; // [rsp+E0h] [rbp-48h] BYREF
  struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE v46; // [rsp+140h] [rbp+18h] BYREF

  v46.IOCoherent = 0;
  v8 = 1;
  if ( a4 )
    v8 = a4;
  _BitScanForward(&v9, v8);
  v10 = 1;
  v11 = a5;
  if ( !a5 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1416,
      "ID3D12VideoEncodeCommandList::ResolveInputParamLayout arguments are not correct - pInputArguments cannot be null.");
    v10 = 0;
  }
  v12 = a6;
  if ( !a6 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1416,
      "ID3D12VideoEncodeCommandList::ResolveInputParamLayout arguments are not correct - pOutputArguments cannot be null.");
    return 2147942487LL;
  }
  if ( !*a6 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1416,
      "ID3D12VideoEncodeCommandList::ResolveInputParamLayout arguments are not correct - pOutputArguments->pOpaqueLayoutB"
      "uffer cannot be null.");
    return 2147942487LL;
  }
  if ( !v10 )
    return 2147942487LL;
  a5 = 0;
  if ( !(unsigned int)CheckVideoEncoderResolveInputParamLayoutSupport(a2, a1, v11, v9, *((_DWORD *)v11 + 24), &a5) )
    return 2147942487LL;
  v46.IOCoherent = 0;
  try
  {
    if ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 85) + 24LL))(*((_QWORD *)a2 + 85)) < 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1307,
        "ID3D12VideoEncodeCommandList::ResolveInputParamLayout Failure on call to CheckFeatureSupport(D3D12_FEATURE_VIDEO"
        "_ARCHITECTURE,...).");
      return 2147942487LL;
    }
    if ( !ValidateEncodeFrameInputBuffer(
            a1,
            &v46,
            *v12,
            "D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM_LAYOUT_OUTPUT_ARGUMENTS::pOpaqueLayoutBuffer",
            (unsigned __int64)a5) )
      return 2147942487LL;
    v15 = 1;
    v16 = *((_DWORD *)v11 + 24);
    if ( !v16 )
    {
      v33 = v9;
      v34 = 0;
      v35 = *(_OWORD *)v11;
      v36 = *((_OWORD *)v11 + 1);
      v37 = *((_OWORD *)v11 + 2);
      v38 = *((_OWORD *)v11 + 3);
      v39 = *((_OWORD *)v11 + 4);
      v40 = *((_OWORD *)v11 + 5);
      *(_QWORD *)v41 = 1;
      *(_QWORD *)&v41[8] = 0;
      if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned int *, __int64))(**((_QWORD **)a2 + 85) + 24LL))(
             *((_QWORD *)a2 + 85),
             50,
             &v33,
             120) >= 0
        && *(_DWORD *)&v41[4] )
      {
        v17 = (int *)((char *)v11 + 48);
      }
      else
      {
        v15 = 0;
        v17 = (int *)((char *)v11 + 48);
        TDebugOutputFunctor::operator()(
          a1,
          1306,
          "CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_QPMAP_INPUT,...) for the given input returned failure or not s"
          "upported for the current frame with params: MapSource: D3D12_VIDEO_ENCODER_INPUT_MAP_SOURCE_GPU_TEXTURE D3D12_"
          "VIDEO_ENCODER_CODEC: %d DXGI_FORMAT %d D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC::Width %d D3D12_VIDEO_ENCOD"
          "ER_PICTURE_RESOLUTION_DESC::Height %d D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE %d",
          *(_DWORD *)v11,
          *((_DWORD *)v11 + 10),
          *((_DWORD *)v11 + 11),
          *((_DWORD *)v11 + 12),
          *((_DWORD *)v11 + 18));
      }
      v18 = (float)*(int *)&v41[12];
      v19 = (int)o_ceilf_0((float)*v17 / (float)*(int *)&v41[12]);
      v20 = (int)o_ceilf_0((float)*((int *)v11 + 11) / v18);
      v21 = 59;
      if ( *(_DWORD *)v11 != 2 )
        v21 = 64;
      v15 &= _lambda_a3c648283d397d322178ddb22cf4c3de_::operator()(
               v21,
               a1,
               *((_QWORD *)v11 + 13),
               &v46,
               "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_QUANTIZATION_MATRIX::pQuantizationMap",
               v21,
               v20,
               v19);
      return v15 == 0 ? 0x80070057 : 0;
    }
    if ( v16 != 1 )
    {
      if ( v16 == 2 )
      {
        v33 = v9;
        v34 = 0;
        v35 = *(_OWORD *)v11;
        v36 = *((_OWORD *)v11 + 1);
        v37 = *((_OWORD *)v11 + 2);
        v38 = *((_OWORD *)v11 + 3);
        v39 = *((_OWORD *)v11 + 4);
        v40 = *((_OWORD *)v11 + 5);
        *(_DWORD *)v41 = *((_DWORD *)v11 + 26);
        *(_OWORD *)&v41[4] = 1u;
        v42 = 0;
        v43 = 0;
        v44 = 0;
        if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned int *))(**((_QWORD **)a2 + 85) + 24LL))(
               *((_QWORD *)a2 + 85),
               52,
               &v33) < 0
          || (v41[12] & 1) == 0 )
        {
          v15 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_MOTION_SEARCH,...) for the given input returned failure or n"
            "ot supported for the current frame with params: D3D12_VIDEO_ENCODER_INPUT_MAP_SOURCE_GPU_TEXTURE MotionSearc"
            "hMode: %d D3D12_VIDEO_ENCODER_CODEC: %d DXGI_FORMAT %d D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC::Width %d"
            " D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC::Height %d D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE %d",
            *((_DWORD *)v11 + 26),
            *(_DWORD *)v11,
            *((_DWORD *)v11 + 10),
            *((_DWORD *)v11 + 11),
            *((_DWORD *)v11 + 12),
            *((_DWORD *)v11 + 18));
        }
        v25 = *((_DWORD *)v11 + 38);
        v26 = HIDWORD(v43);
        if ( !_bittest(&v26, v25) )
        {
          v15 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::MotionUnitPrecision (%d) must be one of the supported one"
            "s in D3D12_FEATURE_VIDEO_ENCODER_MOTION_SEARCH.MotionUnitPrecisionSupport (%x)",
            v25,
            HIDWORD(v43));
        }
        v27 = *((_DWORD *)v11 + 27);
        v28 = (unsigned int)v42;
        if ( v27 < (unsigned int)v42 || v27 > HIDWORD(v42) )
        {
          v15 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::MotionSearchModeConfiguration::SearchDeviationLimit (%d) "
            "must fit within the bounds reported in D3D12_FEATURE_DATA_VIDEO_ENCODER_MOTION_SEARCH (MinDeviation: %d) (MaxDeviation: %d)",
            v27,
            v42,
            HIDWORD(v42));
        }
        v29 = *((_DWORD *)v11 + 28);
        if ( v29 > *(_DWORD *)&v41[16] )
        {
          v15 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::NumHintsPerPixel (%d) must fit within the bounds reported"
            " in D3D12_FEATURE_DATA_VIDEO_ENCODER_MOTION_SEARCH (MaxMotionHints: %d)",
            v29,
            *(_DWORD *)&v41[16]);
        }
        if ( !*((_DWORD *)v11 + 28) )
        {
          v15 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::NumHintsPerPixel (%d) must be greater than zero to perfor"
            "m the ResolveInputParamLayout command.",
            0);
        }
        for ( i = 0; i < *((_DWORD *)v11 + 28); ++i )
        {
          v31 = (unsigned __int8)_lambda_a3c648283d397d322178ddb22cf4c3de_::operator()(
                                   v28,
                                   a1,
                                   *(_QWORD *)(*((_QWORD *)v11 + 15) + 8LL * i),
                                   &v46,
                                   "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::ppMotionVectorMaps[]",
                                   38,
                                   *((_DWORD *)v11 + 11),
                                   *((_DWORD *)v11 + 12)) != 0
              ? v15
              : 0;
          v15 = (unsigned __int8)_lambda_a3c648283d397d322178ddb22cf4c3de_::operator()(
                                   v32,
                                   a1,
                                   *(_QWORD *)(*((_QWORD *)v11 + 17) + 8LL * i),
                                   &v46,
                                   "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTION_VECTORS::ppMotionVectorMapsMetadata[]",
                                   62,
                                   *((_DWORD *)v11 + 11),
                                   *((_DWORD *)v11 + 12)) != 0
              ? v31
              : 0;
        }
      }
      return v15 == 0 ? 0x80070057 : 0;
    }
    v33 = v9;
    v34 = 0;
    v35 = *(_OWORD *)v11;
    v36 = *((_OWORD *)v11 + 1);
    v37 = *((_OWORD *)v11 + 2);
    v38 = *((_OWORD *)v11 + 3);
    v39 = *((_OWORD *)v11 + 4);
    v40 = *((_OWORD *)v11 + 5);
    *(_DWORD *)v41 = 1;
    *(_DWORD *)&v41[4] = *((_DWORD *)v11 + 27);
    *(_QWORD *)&v41[8] = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned int *))(**((_QWORD **)a2 + 85) + 24LL))(
           *((_QWORD *)a2 + 85),
           51,
           &v33) >= 0
      && (v23 = v41[8], *(_DWORD *)&v41[8]) )
    {
      v24 = (_DWORD *)((char *)v11 + 48);
    }
    else
    {
      v15 = 0;
      v24 = (_DWORD *)((char *)v11 + 48);
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_DIRTY_REGIONS,...) for the given input returned failure or not s"
        "upported for the current frame with params: MapSource: D3D12_VIDEO_ENCODER_INPUT_MAP_SOURCE_GPU_TEXTURE D3D12_VI"
        "DEO_ENCODER_CODEC: %d DXGI_FORMAT %d D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC::Width %d D3D12_VIDEO_ENCODER_P"
        "ICTURE_RESOLUTION_DESC::Height %d D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE %d",
        *(_DWORD *)v11,
        *((_DWORD *)v11 + 10),
        *((_DWORD *)v11 + 11),
        *((_DWORD *)v11 + 12),
        *((_DWORD *)v11 + 18));
      v23 = v41[8];
    }
    if ( (v23 & 2) == 0 )
    {
      if ( *((_DWORD *)v11 + 26) )
        return v15 == 0 ? 0x80070057 : 0;
      v15 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_DIRTY_REGIONS::FullFrameIdentical must be TRUE when D3D12_FEATURE_DATA_VIDEO_"
        "ENCODER_DIRTY_REGIONS::SupportFlags does not support D3D12_VIDEO_ENCODER_DIRTY_REGIONS_SUPPORT_FLAG_DIRTY_REGIONS");
    }
    if ( !*((_DWORD *)v11 + 26)
      && !(unsigned __int8)_lambda_a3c648283d397d322178ddb22cf4c3de_::operator()(
                             v22,
                             a1,
                             *((_QWORD *)v11 + 14),
                             &v46,
                             "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_DIRTY_REGIONS::pDirtyRegionsMap",
                             62,
                             *((_DWORD *)v11 + 11),
                             *v24) )
    {
      v15 = 0;
    }
    return v15 == 0 ? 0x80070057 : 0;
  }
  catch ( _com_error *v45 )
  {
    return (unsigned int)*((_DWORD *)v45 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x180246554  mov     rax, rsp
0x180246557  mov     [rax+8], rbx
0x18024655b  mov     [rax+10h], rsi
0x18024655f  mov     [rax+18h], r8d
0x180246563  push    rdi
0x180246564  push    r12
0x180246566  push    r13
0x180246568  push    r14
0x18024656a  push    r15
0x18024656c  sub     rsp, 100h
0x180246573  movaps  xmmword ptr [rax-38h], xmm6
0x180246577  mov     rdi, rdx
0x18024657a  mov     r15, rcx
0x18024657d  xor     r13d, r13d
0x180246580  mov     [rax+18h], r13d
0x180246584  lea     eax, [r13+1]
0x180246588  test    r9d, r9d
0x18024658b  cmovnz  eax, r9d
0x18024658f  bsf     r12d, eax
0x180246593  mov     al, 1
0x180246595  mov     rsi, [rsp+128h+arg_20]
0x18024659d  test    rsi, rsi
0x1802465a0  jnz     short loc_1802465B6
0x1802465a2  lea     r8, aId3d12videoenc_39; "ID3D12VideoEncodeCommandList::ResolveIn"...
0x1802465a9  mov     edx, 588h
0x1802465ae  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802465b3  mov     al, r13b
0x1802465b6  mov     rbx, [rsp+128h+arg_28]
0x1802465be  test    rbx, rbx
0x1802465c1  jnz     short loc_1802465D9
0x1802465c3  lea     r8, aId3d12videoenc_71; "ID3D12VideoEncodeCommandList::ResolveIn"...
0x1802465ca  mov     edx, 588h
0x1802465cf  mov     rcx, r15
0x1802465d2  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802465d7  jmp     short loc_1802465EB
0x1802465d9  cmp     [rbx], r13
0x1802465dc  jnz     short loc_1802465E7
0x1802465de  lea     r8, aId3d12videoenc_63; "ID3D12VideoEncodeCommandList::ResolveIn"...
0x1802465e5  jmp     short loc_1802465CA
0x1802465e7  test    al, al
0x1802465e9  jnz     short loc_1802465F5
0x1802465eb  mov     eax, 80070057h
0x1802465f0  jmp     loc_180246BBE
0x1802465f5  mov     [rsp+128h+arg_20], r13
0x1802465fd  lea     rax, [rsp+128h+arg_20]
0x180246605  mov     [rsp+128h+var_100], rax
0x18024660a  mov     eax, [rsi+60h]
0x18024660d  mov     dword ptr [rsp+128h+var_108], eax
0x180246611  mov     r9d, r12d
0x180246614  mov     r8, rsi
0x180246617  mov     rdx, r15
0x18024661a  mov     rcx, rdi
0x18024661d  call    ?CheckVideoEncoderResolveInputParamLayoutSupport@@YAHAEBUDeviceValidationInfo@@AEAUTDebugOutputFunctor@@AEBUD3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO@@IW4D3D12_VIDEO_ENCODER_INPUT_MAP_TYPE@@AEA_K@Z; CheckVideoEncoderResolveInputParamLayoutSupport(DeviceValidationInfo const &,TDebugOutputFunctor &,D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO const &,uint,D3D12_VIDEO_ENCODER_INPUT_MAP_TYPE,unsigned __int64 &)
0x180246622  test    eax, eax
0x180246624  jnz     short loc_180246630
0x180246626  mov     eax, 80070057h
0x18024662b  jmp     loc_180246BBE
0x180246630  mov     [rsp+128h+arg_10.IOCoherent], r13d
0x180246638  mov     rcx, [rdi+2A8h]
0x18024663f  mov     rax, [rcx]
0x180246642  mov     r9d, 4
0x180246648  lea     r8, [rsp+128h+arg_10]
0x180246650  lea     edx, [r9+0Dh]
0x180246654  mov     rax, [rax+18h]
0x180246658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024665d  mov     rcx, r15; struct TDebugOutputFunctor *
0x180246660  test    eax, eax
0x180246662  jns     short loc_18024667F
0x180246664  lea     r8, aId3d12videoenc_104; "ID3D12VideoEncodeCommandList::ResolveIn"...
0x18024666b  mov     edx, 51Bh
0x180246670  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246675  mov     eax, 80070057h
0x18024667a  jmp     loc_180246BBE
0x18024667f  mov     rax, [rsp+128h+arg_20]
0x180246687  mov     [rsp+128h+var_108], rax; unsigned __int64
0x18024668c  lea     r9, aD3d12VideoEnco_122; "D3D12_VIDEO_ENCODER_RESOLVE_INPUT_PARAM"...
0x180246693  mov     r8, [rbx]; struct ID3D12Resource *
0x180246696  lea     rdx, [rsp+128h+arg_10]; struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *
0x18024669e  call    ?ValidateEncodeFrameInputBuffer@@YAHAEAUTDebugOutputFunctor@@AEAUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEAUID3D12Resource@@PEBD_K@Z; ValidateEncodeFrameInputBuffer(TDebugOutputFunctor &,D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE &,ID3D12Resource *,char const *,unsigned __int64)
0x1802466a3  test    eax, eax
0x1802466a5  jnz     short loc_1802466B1
0x1802466a7  mov     eax, 80070057h
0x1802466ac  jmp     loc_180246BBE
0x1802466b1  mov     ebx, 1
0x1802466b6  mov     r14b, bl
0x1802466b9  mov     eax, [rsi+60h]
0x1802466bc  test    eax, eax
0x1802466be  jnz     loc_18024680B
0x1802466c4  mov     [rsp+128h+var_D8], r12d
0x1802466c9  xor     eax, eax
0x1802466cb  mov     [rsp+128h+var_D4], eax
0x1802466cf  movups  xmm0, xmmword ptr [rsi]
0x1802466d2  movups  [rsp+128h+var_D0], xmm0
0x1802466d7  movups  xmm1, xmmword ptr [rsi+10h]
0x1802466db  movups  [rsp+128h+var_C0], xmm1
0x1802466e0  movups  xmm0, xmmword ptr [rsi+20h]
0x1802466e4  movups  [rsp+128h+var_B0], xmm0
0x1802466e9  movups  xmm1, xmmword ptr [rsi+30h]
0x1802466ed  movups  [rsp+128h+var_A0], xmm1
0x1802466f5  movups  xmm0, xmmword ptr [rsi+40h]
0x1802466f9  movups  [rsp+128h+var_90], xmm0
0x180246701  movups  xmm1, xmmword ptr [rsi+50h]
0x180246705  movups  [rsp+128h+var_80], xmm1
0x18024670d  mov     qword ptr [rsp+128h+var_70], rbx
0x180246715  mov     qword ptr [rsp+128h+var_70+8], r13
0x18024671d  mov     rcx, [rdi+2A8h]
0x180246724  mov     rax, [rcx]
0x180246727  lea     r9d, [rbx+77h]
0x18024672b  lea     r8, [rsp+128h+var_D8]
0x180246730  lea     edx, [rbx+31h]
0x180246733  mov     rax, [rax+18h]
0x180246737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024673c  test    eax, eax
0x18024673e  js      short loc_180246750
0x180246740  cmp     dword ptr [rsp+128h+var_70+4], r13d
0x180246748  jz      short loc_180246750
0x18024674a  lea     rbx, [rsi+30h]
0x18024674e  jmp     short loc_180246789
0x180246750  mov     r14b, r13b
0x180246753  lea     rbx, [rsi+30h]
0x180246757  mov     eax, [rsi+48h]
0x18024675a  mov     [rsp+128h+var_F0], eax
0x18024675e  mov     eax, [rbx]
0x180246760  mov     [rsp+128h+var_F8], eax
0x180246764  mov     eax, [rsi+2Ch]
0x180246767  mov     dword ptr [rsp+128h+var_100], eax
0x18024676b  mov     eax, [rsi+28h]
0x18024676e  mov     dword ptr [rsp+128h+var_108], eax
0x180246772  mov     r9d, [rsi]
0x180246775  lea     r8, aCheckfeaturesu_6; "CheckFeatureSupport(D3D12_FEATURE_VIDEO"...
0x18024677c  mov     edx, 51Ah
0x180246781  mov     rcx, r15
0x180246784  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246789  mov     eax, dword ptr [rsp+128h+var_70+0Ch]
0x180246790  xorps   xmm6, xmm6
0x180246793  cvtsi2ss xmm6, rax
0x180246798  mov     eax, [rbx]
0x18024679a  xorps   xmm0, xmm0
0x18024679d  cvtsi2ss xmm0, rax
0x1802467a2  divss   xmm0, xmm6; X
0x1802467a6  call    _o_ceilf_0
0x1802467ab  cvttss2si rbx, xmm0
0x1802467b0  mov     eax, [rsi+2Ch]
0x1802467b3  xorps   xmm0, xmm0
0x1802467b6  cvtsi2ss xmm0, rax
0x1802467bb  divss   xmm0, xmm6; X
0x1802467bf  call    _o_ceilf_0
0x1802467c4  cvttss2si rax, xmm0
0x1802467c9  mov     ecx, 3Bh ; ';'
0x1802467ce  lea     edx, [rcx+5]
0x1802467d1  cmp     dword ptr [rsi], 2
0x1802467d4  cmovnz  ecx, edx
0x1802467d7  mov     [rsp+128h+var_F0], ebx
0x1802467db  mov     [rsp+128h+var_F8], eax
0x1802467df  mov     dword ptr [rsp+128h+var_100], ecx
0x1802467e3  lea     rax, aD3d12VideoEnco_120; "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_QUAN"...
0x1802467ea  mov     [rsp+128h+var_108], rax
0x1802467ef  lea     r9, [rsp+128h+arg_10]
0x1802467f7  mov     r8, [rsi+68h]
0x1802467fb  mov     rdx, r15
0x1802467fe  call    ??R_lambda_a3c648283d397d322178ddb22cf4c3de_@@QEBA_NAEAUTDebugOutputFunctor@@PEAUID3D12Resource@@AEAUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEBDW4DXGI_FORMAT@@II@Z; _lambda_a3c648283d397d322178ddb22cf4c3de_::operator()(TDebugOutputFunctor &,ID3D12Resource *,D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE &,char const *,DXGI_FORMAT,uint,uint)
0x180246803  and     r14b, al
0x180246806  jmp     loc_180246BA9
0x18024680b  cmp     eax, ebx
0x18024680d  jnz     loc_180246960
0x180246813  mov     [rsp+128h+var_D8], r12d
0x180246818  xor     eax, eax
0x18024681a  mov     [rsp+128h+var_D4], eax
0x18024681e  movups  xmm0, xmmword ptr [rsi]
0x180246821  movups  [rsp+128h+var_D0], xmm0
0x180246826  movups  xmm1, xmmword ptr [rsi+10h]
0x18024682a  movups  [rsp+128h+var_C0], xmm1
0x18024682f  movups  xmm0, xmmword ptr [rsi+20h]
0x180246833  movups  [rsp+128h+var_B0], xmm0
0x180246838  movups  xmm1, xmmword ptr [rsi+30h]
0x18024683c  movups  [rsp+128h+var_A0], xmm1
0x180246844  movups  xmm0, xmmword ptr [rsi+40h]
0x180246848  movups  [rsp+128h+var_90], xmm0
0x180246850  movups  xmm1, xmmword ptr [rsi+50h]
0x180246854  movups  [rsp+128h+var_80], xmm1
0x18024685c  mov     dword ptr [rsp+128h+var_70], ebx
0x180246863  mov     eax, [rsi+6Ch]
0x180246866  mov     dword ptr [rsp+128h+var_70+4], eax
0x18024686d  mov     qword ptr [rsp+128h+var_70+8], r13
0x180246875  mov     rcx, [rdi+2A8h]
0x18024687c  mov     rax, [rcx]
0x18024687f  mov     r9d, 78h ; 'x'
0x180246885  lea     r8, [rsp+128h+var_D8]
0x18024688a  lea     edx, [r9-45h]
0x18024688e  mov     rax, [rax+18h]
0x180246892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246897  test    eax, eax
0x180246899  js      short loc_1802468AC
0x18024689b  mov     eax, dword ptr [rsp+128h+var_70+8]
0x1802468a2  test    eax, eax
0x1802468a4  jz      short loc_1802468AC
0x1802468a6  lea     rbx, [rsi+30h]
0x1802468aa  jmp     short loc_1802468EC
0x1802468ac  mov     r14b, r13b
0x1802468af  lea     rbx, [rsi+30h]
0x1802468b3  mov     eax, [rsi+48h]
0x1802468b6  mov     [rsp+128h+var_F0], eax
0x1802468ba  mov     eax, [rbx]
0x1802468bc  mov     [rsp+128h+var_F8], eax
0x1802468c0  mov     eax, [rsi+2Ch]
0x1802468c3  mov     dword ptr [rsp+128h+var_100], eax
0x1802468c7  mov     eax, [rsi+28h]
0x1802468ca  mov     dword ptr [rsp+128h+var_108], eax
0x1802468ce  mov     r9d, [rsi]
0x1802468d1  lea     r8, aCheckfeaturesu_2; "CheckFeatureSupport(D3D12_FEATURE_VIDEO"...
0x1802468d8  mov     edx, 51Ah
0x1802468dd  mov     rcx, r15
0x1802468e0  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802468e5  mov     eax, dword ptr [rsp+128h+var_70+8]
0x1802468ec  test    al, 2
0x1802468ee  jnz     short loc_180246911
0x1802468f0  cmp     [rsi+68h], r13d
0x1802468f4  jnz     loc_180246BA9
0x1802468fa  mov     r14b, r13b
0x1802468fd  lea     r8, aD3d12VideoEnco_64; "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_DIRT"...
0x180246904  mov     edx, 51Ah
0x180246909  mov     rcx, r15
0x18024690c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246911  cmp     [rsi+68h], r13d
0x180246915  jnz     loc_180246BA9
0x18024691b  mov     eax, [rbx]
0x18024691d  mov     [rsp+128h+var_F0], eax
0x180246921  mov     eax, [rsi+2Ch]
0x180246924  mov     [rsp+128h+var_F8], eax
0x180246928  mov     dword ptr [rsp+128h+var_100], 3Eh ; '>'
0x180246930  lea     rax, aD3d12VideoEnco_98; "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_DIRT"...
0x180246937  mov     [rsp+128h+var_108], rax
0x18024693c  lea     r9, [rsp+128h+arg_10]
0x180246944  mov     r8, [rsi+70h]
0x180246948  mov     rdx, r15
0x18024694b  call    ??R_lambda_a3c648283d397d322178ddb22cf4c3de_@@QEBA_NAEAUTDebugOutputFunctor@@PEAUID3D12Resource@@AEAUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEBDW4DXGI_FORMAT@@II@Z; _lambda_a3c648283d397d322178ddb22cf4c3de_::operator()(TDebugOutputFunctor &,ID3D12Resource *,D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE &,char const *,DXGI_FORMAT,uint,uint)
0x180246950  test    al, al
0x180246952  jnz     loc_180246BA9
0x180246958  mov     r14b, r13b
0x18024695b  jmp     loc_180246BA9
0x180246960  cmp     eax, 2
0x180246963  jnz     loc_180246BA9
0x180246969  mov     [rsp+128h+var_D8], r12d
0x18024696e  xor     eax, eax
0x180246970  mov     [rsp+128h+var_D4], eax
0x180246974  movups  xmm0, xmmword ptr [rsi]
0x180246977  movups  [rsp+128h+var_D0], xmm0
0x18024697c  movups  xmm1, xmmword ptr [rsi+10h]
0x180246980  movups  [rsp+128h+var_C0], xmm1
0x180246985  movups  xmm0, xmmword ptr [rsi+20h]
0x180246989  movups  [rsp+128h+var_B0], xmm0
0x18024698e  movups  xmm1, xmmword ptr [rsi+30h]
0x180246992  movups  [rsp+128h+var_A0], xmm1
0x18024699a  movups  xmm0, xmmword ptr [rsi+40h]
0x18024699e  movups  [rsp+128h+var_90], xmm0
0x1802469a6  movups  xmm1, xmmword ptr [rsi+50h]
0x1802469aa  movups  [rsp+128h+var_80], xmm1
0x1802469b2  mov     eax, [rsi+68h]
0x1802469b5  mov     dword ptr [rsp+128h+var_70], eax
0x1802469bc  mov     qword ptr [rsp+128h+var_70+4], rbx
0x1802469c4  mov     qword ptr [rsp+128h+var_70+0Ch], r13
0x1802469cc  mov     [rsp+128h+var_5C], r13
0x1802469d4  mov     [rsp+128h+var_54], r13
0x1802469dc  xor     eax, eax
0x1802469de  mov     [rsp+128h+var_4C], eax
0x1802469e5  mov     rcx, [rdi+2A8h]
0x1802469ec  mov     rax, [rcx]
0x1802469ef  mov     r9d, 90h
0x1802469f5  lea     r8, [rsp+128h+var_D8]
0x1802469fa  lea     edx, [r9-5Ch]
0x1802469fe  mov     rax, [rax+18h]
0x180246a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246a07  test    eax, eax
0x180246a09  js      short loc_180246A14
0x180246a0b  test    [rsp+128h+var_70+0Ch], bl
0x180246a12  jnz     short loc_180246A51
0x180246a14  mov     r14b, r13b
0x180246a17  mov     eax, [rsi+48h]
0x180246a1a  mov     [rsp+128h+var_E8], eax
0x180246a1e  mov     eax, [rsi+30h]
0x180246a21  mov     [rsp+128h+var_F0], eax
0x180246a25  mov     eax, [rsi+2Ch]
0x180246a28  mov     [rsp+128h+var_F8], eax
0x180246a2c  mov     eax, [rsi+28h]
0x180246a2f  mov     dword ptr [rsp+128h+var_100], eax
0x180246a33  mov     eax, [rsi]
0x180246a35  mov     dword ptr [rsp+128h+var_108], eax
0x180246a39  mov     r9d, [rsi+68h]
0x180246a3d  lea     r8, aCheckfeaturesu_4; "CheckFeatureSupport(D3D12_FEATURE_VIDEO"...
0x180246a44  mov     edx, 51Ah
0x180246a49  mov     rcx, r15
0x180246a4c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180246a51  mov     r9d, [rsi+98h]
0x180246a58  mov     eax, dword ptr [rsp+128h+var_54+4]
0x180246a5f  bt      eax, r9d
0x180246a63  jb      short loc_180246A80
0x180246a65  mov     r14b, r13b
0x180246a68  mov     dword ptr [rsp+128h+var_108], eax
0x180246a6c  lea     r8, aD3d12VideoEnco_26; "D3D12_VIDEO_ENCODER_INPUT_MAP_DATA_MOTI"...
0x180246a73  mov     edx, 51Ah
  ... truncated ...
```
