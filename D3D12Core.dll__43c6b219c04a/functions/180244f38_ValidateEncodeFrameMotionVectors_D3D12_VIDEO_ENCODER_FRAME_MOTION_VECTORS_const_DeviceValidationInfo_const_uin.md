# ValidateEncodeFrameMotionVectors(D3D12_VIDEO_ENCODER_FRAME_MOTION_VECTORS const &,DeviceValidationInfo const &,uint,D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO const &,D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE &,TDebugOutputFunctor &,D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC const &,bool,uint)

- ea: `0x180244f38`
- end: `0x180245326`
- name: `?ValidateEncodeFrameMotionVectors@@YAHAEBUD3D12_VIDEO_ENCODER_FRAME_MOTION_VECTORS@@AEBUDeviceValidationInfo@@IAEBUD3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO@@AEAUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@AEAUTDebugOutputFunctor@@AEBUD3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC@@_NI@Z`
- size: `1006`
- prototype: `__int64 __fastcall(const struct D3D12_VIDEO_ENCODER_FRAME_MOTION_VECTORS *, const struct DeviceValidationInfo *, unsigned int, const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *, struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *, struct TDebugOutputFunctor *, const struct D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1802404b4`

## callees

- `0x18002ef50`
- `0x18023c618`
- `0x180244e44`
- `0x180244f38`
- `0x180262020`

## string_xrefs

- `0x180245265`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions[%d].SourcePoint must fit within the bounds of the input frame resource. Destination Resource - width: %d, height: %d.  SourcePoint - x: %d, y: %d`
- `0x180245206`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions[%d].DestRect must fit within the bounds of the input frame resource. Destination Resource - width: %d, height: %d.  TargetRectangle - top: %d, left: %d, bottom: %d, right: %d`
- `0x1802452cc`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::MotionSearchModeConfiguration::SearchDeviationLimit (%d) must fit within the bounds reported in D3D12_FEATURE_DATA_VIDEO_ENCODER_MOTION_SEARCH (MinDeviation: %d) (MaxDeviation: %d)`
- `0x180245297`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions must not be NULL when D3D12_VIDEO_ENCODER_MOVEREGION_INFO::FullFrameIdentical is FALSE`
- `0x1802450f1`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::MotionUnitPrecision (%d) must be one of the supported ones in D3D12_FEATURE_VIDEO_ENCODER_MOTION_SEARCH.MotionUnitPrecisionSupport (%x)`
- `0x1802450c7`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO_FLAG_MULTIPLE_HINTS is set in D3D12_VIDEO_ENCODER_MOVEREGION_INFO::Flags but D3D12_FEATURE_VIDEO_ENCODER_MOTION_SEARCH.SupportFlags (%x) doesn't report D3D12_VIDEO_ENCODER_MOTION_SEARCH_SUPPORT_FLAG_MULTIPLE_HINTS.`
- `0x1802451aa`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions[%d].DestRect must have top >= 0, bottom > top, left >= 0, and right > left. TargetRectangle - top: %d, left: %d, bottom: %d, right: %d`
- `0x180245118`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::NumMoveRegions (%d) must be less or equal than D3D12_FEATURE_DATA_VIDEO_ENCODER_MOTION_SEARCH.MaxMotionHints (%d)`
- `0x1802452f8`: `D3D12_VIDEO_ENCODER_MOVEREGION_INFO::SourceDPBFrameReference (%d) must be within the range [0, NumReferencesInDPB (%d))`

## pseudocode

```c
__int64 __fastcall ValidateEncodeFrameMotionVectors(
        struct ID3D12Resource **a1,
        const struct DeviceValidationInfo *a2,
        unsigned int a3,
        const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *a4,
        struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *a5,
        struct TDebugOutputFunctor *a6,
        const struct D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC *a7,
        bool a8,
        unsigned int a9)
{
  int v11; // r9d
  unsigned int v12; // ebx
  bool v13; // zf
  int v15; // eax
  struct TDebugOutputFunctor *v16; // r14
  char v17; // si
  char v18; // cl
  unsigned int v19; // r9d
  int v20; // eax
  struct ID3D12Resource *v21; // rax
  struct ID3D12Resource *v22; // rcx
  char v23; // r12
  unsigned int v24; // r15d
  const struct D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC *v25; // r13
  ID3D12Resource_vtbl *v26; // rax
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // edx
  unsigned __int64 v31; // r10
  __int64 v32; // rax
  unsigned __int64 v33; // rdx
  char v34; // si
  unsigned int v35; // r9d
  unsigned int v36; // r9d
  int v37; // [rsp+50h] [rbp-B0h]
  int v38; // [rsp+54h] [rbp-ACh]
  int v39; // [rsp+58h] [rbp-A8h]
  _DWORD v40[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v41; // [rsp+78h] [rbp-88h]
  __int128 v42; // [rsp+88h] [rbp-78h]
  __int128 v43; // [rsp+98h] [rbp-68h]
  __int128 v44; // [rsp+A8h] [rbp-58h]
  __int128 v45; // [rsp+B8h] [rbp-48h]
  __int128 v46; // [rsp+C8h] [rbp-38h]
  int v47; // [rsp+D8h] [rbp-28h]
  int v48; // [rsp+DCh] [rbp-24h]
  BOOL v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E4h] [rbp-1Ch]
  __int64 v51; // [rsp+ECh] [rbp-14h]
  __int64 v52; // [rsp+F4h] [rbp-Ch]
  int v53; // [rsp+FCh] [rbp-4h]
  unsigned __int64 v54; // [rsp+150h] [rbp+50h] BYREF

  v11 = *(_DWORD *)a1;
  v12 = 0;
  if ( *(_DWORD *)a1 == 1 )
  {
    v54 = 0;
    if ( !(unsigned int)CheckVideoEncoderResolveInputParamLayoutSupport(a2, a6, a4, a3, 2, &v54) )
      return 0;
    v13 = ValidateEncodeFrameInputBuffer(
            a6,
            a5,
            a1[1],
            "D3D12_VIDEO_ENCODER_FRAME_MOTION_VECTORS::pOpaqueLayoutBuffer",
            v54) == 0;
  }
  else
  {
    v40[0] = a3;
    v40[1] = 0;
    v41 = *(_OWORD *)a4;
    v42 = *((_OWORD *)a4 + 1);
    v43 = *((_OWORD *)a4 + 2);
    v44 = *((_OWORD *)a4 + 3);
    v45 = *((_OWORD *)a4 + 4);
    v46 = *((_OWORD *)a4 + 5);
    v47 = (int)a1[1][2].__vftable;
    v48 = v11;
    v49 = a8;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, _DWORD *))(**((_QWORD **)a2 + 85) + 24LL))(
            *((_QWORD *)a2 + 85),
            52,
            v40);
    v16 = a6;
    if ( v15 < 0 || (v17 = 1, v18 = v50, (v50 & 1) == 0) )
    {
      v17 = 0;
      TDebugOutputFunctor::operator()(
        a6,
        1306,
        "CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_MOTION_SEARCH,...) for the given input returned failure or not s"
        "upported for the current frame with params: MapSource: %d MotionSearchMode: %d D3D12_VIDEO_ENCODER_CODEC: %d DXG"
        "I_FORMAT %d D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC::Width %d D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC::H"
        "eight %d D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE %d",
        *(_DWORD *)a1,
        LODWORD(a1[1][2].__vftable),
        *(_DWORD *)a4,
        *((_DWORD *)a4 + 10),
        *((_DWORD *)a4 + 11),
        *((_DWORD *)a4 + 12),
        *((_DWORD *)a4 + 18));
      v18 = v50;
    }
    if ( ((__int64)a1[1][4].__vftable & 1) != 0 && (v18 & 2) == 0 )
    {
      v17 = 0;
      TDebugOutputFunctor::operator()(
        v16,
        1306,
        "D3D12_VIDEO_ENCODER_MOVEREGION_INFO_FLAG_MULTIPLE_HINTS is set in D3D12_VIDEO_ENCODER_MOVEREGION_INFO::Flags but"
        " D3D12_FEATURE_VIDEO_ENCODER_MOTION_SEARCH.SupportFlags (%x) doesn't report D3D12_VIDEO_ENCODER_MOTION_SEARCH_SU"
        "PPORT_FLAG_MULTIPLE_HINTS.",
        HIDWORD(v52));
    }
    v19 = HIDWORD(a1[1][3].__vftable);
    v20 = HIDWORD(v52);
    if ( !_bittest(&v20, v19) )
    {
      v17 = 0;
      TDebugOutputFunctor::operator()(
        v16,
        1306,
        "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::MotionUnitPrecision (%d) must be one of the supported ones in D3D12_FEATURE"
        "_VIDEO_ENCODER_MOTION_SEARCH.MotionUnitPrecisionSupport (%x)",
        v19,
        HIDWORD(v52));
    }
    v21 = a1[1];
    if ( LODWORD(v21->__vftable) > HIDWORD(v50) )
    {
      v17 = 0;
      TDebugOutputFunctor::operator()(
        v16,
        1306,
        "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::NumMoveRegions (%d) must be less or equal than D3D12_FEATURE_DATA_VIDEO_ENC"
        "ODER_MOTION_SEARCH.MaxMotionHints (%d)",
        LODWORD(v21->__vftable),
        HIDWORD(v50));
    }
    v22 = a1[1];
    if ( v22[1].__vftable )
    {
      v23 = 1;
      if ( LODWORD(v22->__vftable) )
      {
        v24 = 0;
        v25 = a7;
        do
        {
          v26 = v22[1].__vftable;
          v27 = *((_DWORD *)&v26->AddRef + 6 * v24);
          v39 = v27;
          v28 = *((_DWORD *)&v26->AddRef + 6 * v24 + 1);
          LODWORD(v54) = v28;
          v29 = *((_DWORD *)&v26->Release + 6 * v24);
          v38 = v29;
          v30 = *((_DWORD *)&v26->Release + 6 * v24 + 1);
          v37 = v30;
          if ( v27 < 0 || v28 < 0 || v29 < v27 || v30 < v28 )
          {
            v23 = 0;
            TDebugOutputFunctor::operator()(
              v16,
              1306,
              "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions[%d].DestRect must have top >= 0, bottom > top, left >= 0"
              ", and right > left. TargetRectangle - top: %d, left: %d, bottom: %d, right: %d",
              v24,
              v28,
              v27,
              v30,
              v29);
            v28 = v54;
            v30 = v37;
            v29 = v38;
            v27 = v39;
          }
          v31 = *(unsigned int *)v25;
          if ( v29 > v31 || (unsigned int)v30 > *((_DWORD *)v25 + 1) )
          {
            v23 = 0;
            TDebugOutputFunctor::operator()(
              v16,
              1306,
              "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions[%d].DestRect must fit within the bounds of the input fra"
              "me resource. Destination Resource - width: %d, height: %d.  TargetRectangle - top: %d, left: %d, bottom: %d, right: %d",
              v24,
              v31,
              *((_DWORD *)v25 + 1),
              v28,
              v27,
              v30,
              v29);
          }
          v32 = *((_QWORD *)&a1[1][1].QueryInterface + 3 * v24);
          v33 = *(unsigned int *)v25;
          if ( (int)v32 > v33 || HIDWORD(v32) > *((_DWORD *)v25 + 1) )
          {
            v23 = 0;
            TDebugOutputFunctor::operator()(
              v16,
              1306,
              "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions[%d].SourcePoint must fit within the bounds of the input "
              "frame resource. Destination Resource - width: %d, height: %d.  SourcePoint - x: %d, y: %d",
              v24,
              v33,
              *((_DWORD *)v25 + 1),
              v32,
              HIDWORD(*((_QWORD *)&a1[1][1].QueryInterface + 3 * v24)));
          }
          ++v24;
          v22 = a1[1];
        }
        while ( v24 < LODWORD(v22->__vftable) );
      }
      v34 = v23 & v17;
    }
    else
    {
      v34 = 0;
      TDebugOutputFunctor::operator()(
        v16,
        1306,
        "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pMoveRegions must not be NULL when D3D12_VIDEO_ENCODER_MOVEREGION_INFO::Ful"
        "lFrameIdentical is FALSE");
    }
    v35 = HIDWORD(a1[1][2].__vftable);
    if ( v35 < (unsigned int)v51 || v35 > HIDWORD(v51) )
    {
      v34 = 0;
      TDebugOutputFunctor::operator()(
        v16,
        1306,
        "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::MotionSearchModeConfiguration::SearchDeviationLimit (%d) must fit within th"
        "e bounds reported in D3D12_FEATURE_DATA_VIDEO_ENCODER_MOTION_SEARCH (MinDeviation: %d) (MaxDeviation: %d)",
        v35,
        v51,
        HIDWORD(v51));
    }
    v36 = (unsigned int)a1[1][3].__vftable;
    if ( v36 >= a9 )
    {
      v34 = 0;
      TDebugOutputFunctor::operator()(
        v16,
        1306,
        "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::SourceDPBFrameReference (%d) must be within the range [0, NumReferencesInDPB (%d))",
        v36,
        a9);
    }
    v13 = v34 == 0;
  }
  LOBYTE(v12) = !v13;
  return v12;
}

```

## disassembly

```asm
0x180244f38  push    rbp
0x180244f3a  push    rbx
0x180244f3b  push    rsi
0x180244f3c  push    rdi
0x180244f3d  push    r12
0x180244f3f  push    r13
0x180244f41  push    r14
0x180244f43  push    r15
0x180244f45  lea     rbp, [rsp-8]
0x180244f4a  sub     rsp, 108h
0x180244f51  mov     r15, r9
0x180244f54  mov     r10, rdx
0x180244f57  mov     rdi, rcx
0x180244f5a  mov     r9d, [rcx]
0x180244f5d  xor     ebx, ebx
0x180244f5f  cmp     r9d, 1
0x180244f63  jnz     short loc_180244FBF
0x180244f65  mov     [rbp+40h+arg_0], rbx
0x180244f69  lea     rax, [rbp+40h+arg_0]
0x180244f6d  mov     [rsp+140h+var_118], rax
0x180244f72  mov     dword ptr [rsp+140h+var_120], 2
0x180244f7a  mov     r9d, r8d
0x180244f7d  mov     r8, r15
0x180244f80  mov     rdx, [rbp+40h+arg_28]
0x180244f84  mov     rcx, r10
0x180244f87  call    ?CheckVideoEncoderResolveInputParamLayoutSupport@@YAHAEBUDeviceValidationInfo@@AEAUTDebugOutputFunctor@@AEBUD3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO@@IW4D3D12_VIDEO_ENCODER_INPUT_MAP_TYPE@@AEA_K@Z; CheckVideoEncoderResolveInputParamLayoutSupport(DeviceValidationInfo const &,TDebugOutputFunctor &,D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO const &,uint,D3D12_VIDEO_ENCODER_INPUT_MAP_TYPE,unsigned __int64 &)
0x180244f8c  test    eax, eax
0x180244f8e  jz      short loc_180244FB8
0x180244f90  mov     rdx, [rbp+40h+arg_0]
0x180244f94  mov     [rsp+140h+var_120], rdx; unsigned __int64
0x180244f99  lea     r9, aD3d12VideoEnco_93; "D3D12_VIDEO_ENCODER_FRAME_MOTION_VECTOR"...
0x180244fa0  mov     r8, [rdi+8]; struct ID3D12Resource *
0x180244fa4  mov     rdx, [rbp+40h+arg_20]; struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *
0x180244fa8  mov     rcx, [rbp+40h+arg_28]; struct TDebugOutputFunctor *
0x180244fac  call    ?ValidateEncodeFrameInputBuffer@@YAHAEAUTDebugOutputFunctor@@AEAUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEAUID3D12Resource@@PEBD_K@Z; ValidateEncodeFrameInputBuffer(TDebugOutputFunctor &,D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE &,ID3D12Resource *,char const *,unsigned __int64)
0x180244fb1  test    eax, eax
0x180244fb3  jmp     loc_18024530D
0x180244fb8  xor     eax, eax
0x180244fba  jmp     loc_180245312
0x180244fbf  mov     [rsp+140h+var_D0], r8d
0x180244fc4  xor     eax, eax
0x180244fc6  mov     [rsp+140h+var_CC], eax
0x180244fca  movaps  xmm0, xmmword ptr [r15]
0x180244fce  movups  [rsp+140h+var_C8], xmm0
0x180244fd3  movaps  xmm1, xmmword ptr [r15+10h]
0x180244fd8  movups  [rbp+40h+var_B8], xmm1
0x180244fdc  movaps  xmm0, xmmword ptr [r15+20h]
0x180244fe1  movups  [rbp+40h+var_A8], xmm0
0x180244fe5  movaps  xmm1, xmmword ptr [r15+30h]
0x180244fea  movups  [rbp+40h+var_98], xmm1
0x180244fee  movaps  xmm0, xmmword ptr [r15+40h]
0x180244ff3  movups  [rbp+40h+var_88], xmm0
0x180244ff7  movaps  xmm1, xmmword ptr [r15+50h]
0x180244ffc  movups  [rbp+40h+var_78], xmm1
0x180245000  mov     rax, [rcx+8]
0x180245004  mov     ecx, [rax+10h]
0x180245007  mov     [rbp+40h+var_68], ecx
0x18024500a  mov     [rbp+40h+var_64], r9d
0x18024500e  movzx   eax, [rbp+40h+arg_38]
0x180245015  mov     [rbp+40h+var_60], eax
0x180245018  mov     [rbp+40h+var_5C], rbx
0x18024501c  mov     [rbp+40h+var_54], rbx
0x180245020  mov     [rbp+40h+var_4C], rbx
0x180245024  xor     eax, eax
0x180245026  mov     [rbp+40h+var_44], eax
0x180245029  mov     rcx, [rdx+2A8h]
0x180245030  mov     rax, [rcx]
0x180245033  mov     r9d, 90h
0x180245039  lea     r8, [rsp+140h+var_D0]
0x18024503e  lea     edx, [r9-5Ch]
0x180245042  mov     rax, [rax+18h]
0x180245046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024504b  mov     r12d, 51Ah
0x180245051  mov     r14, [rbp+40h+arg_28]
0x180245055  test    eax, eax
0x180245057  js      short loc_180245064
0x180245059  mov     sil, 1
0x18024505c  mov     ecx, dword ptr [rbp+40h+var_5C]
0x18024505f  test    sil, cl
0x180245062  jnz     short loc_1802450B1
0x180245064  mov     sil, bl
0x180245067  mov     rcx, [rdi+8]
0x18024506b  mov     eax, [r15+48h]
0x18024506f  mov     [rsp+140h+var_F8], eax
0x180245073  mov     eax, [r15+30h]
0x180245077  mov     [rsp+140h+var_100], eax
0x18024507b  mov     eax, [r15+2Ch]
0x18024507f  mov     [rsp+140h+var_108], eax
0x180245083  mov     eax, [r15+28h]
0x180245087  mov     [rsp+140h+var_110], eax
0x18024508b  mov     eax, [r15]
0x18024508e  mov     dword ptr [rsp+140h+var_118], eax
0x180245092  mov     eax, [rcx+10h]
0x180245095  mov     dword ptr [rsp+140h+var_120], eax
0x180245099  mov     r9d, [rdi]
0x18024509c  lea     r8, aCheckfeaturesu_5; "CheckFeatureSupport(D3D12_FEATURE_VIDEO"...
0x1802450a3  mov     edx, r12d
0x1802450a6  mov     rcx, r14
0x1802450a9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802450ae  mov     ecx, dword ptr [rbp+40h+var_5C]
0x1802450b1  mov     rax, [rdi+8]
0x1802450b5  test    byte ptr [rax+20h], 1
0x1802450b9  jz      short loc_1802450D9
0x1802450bb  test    cl, 2
0x1802450be  jnz     short loc_1802450D9
0x1802450c0  mov     sil, bl
0x1802450c3  mov     r9d, dword ptr [rbp+40h+var_4C+4]
0x1802450c7  lea     r8, aD3d12VideoEnco_53; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO_FLA"...
0x1802450ce  mov     edx, r12d
0x1802450d1  mov     rcx, r14
0x1802450d4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802450d9  mov     rax, [rdi+8]
0x1802450dd  mov     r9d, [rax+1Ch]
0x1802450e1  mov     eax, dword ptr [rbp+40h+var_4C+4]
0x1802450e4  bt      eax, r9d
0x1802450e8  jb      short loc_180245103
0x1802450ea  mov     sil, bl
0x1802450ed  mov     dword ptr [rsp+140h+var_120], eax
0x1802450f1  lea     r8, aD3d12VideoEnco_19; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::Mo"...
0x1802450f8  mov     edx, r12d
0x1802450fb  mov     rcx, r14
0x1802450fe  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245103  mov     rax, [rdi+8]
0x180245107  mov     ecx, dword ptr [rbp+40h+var_5C+4]
0x18024510a  cmp     [rax], ecx
0x18024510c  jbe     short loc_18024512A
0x18024510e  mov     sil, bl
0x180245111  mov     dword ptr [rsp+140h+var_120], ecx
0x180245115  mov     r9d, [rax]
0x180245118  lea     r8, aD3d12VideoEnco_55; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::Nu"...
0x18024511f  mov     edx, r12d
0x180245122  mov     rcx, r14
0x180245125  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024512a  mov     rcx, [rdi+8]
0x18024512e  cmp     [rcx+8], rbx
0x180245132  jz      loc_180245294
0x180245138  mov     r12b, 1
0x18024513b  cmp     [rcx], ebx
0x18024513d  jbe     loc_180245289
0x180245143  mov     r15d, ebx
0x180245146  mov     r13, [rbp+40h+arg_30]
0x18024514d  mov     eax, r15d
0x180245150  lea     rdx, [rax+rax*2]
0x180245154  mov     [rsp+140h+var_E0], rdx
0x180245159  mov     rax, [rcx+8]
0x18024515d  mov     r9d, [rax+rdx*8+8]
0x180245162  mov     [rsp+140h+var_E8], r9d
0x180245167  mov     ecx, [rax+rdx*8+0Ch]
0x18024516b  mov     dword ptr [rbp+40h+arg_0], ecx
0x18024516e  mov     r8d, [rax+rdx*8+10h]
0x180245173  mov     [rsp+140h+var_EC], r8d
0x180245178  mov     edx, [rax+rdx*8+14h]
0x18024517c  mov     [rsp+140h+var_F0], edx
0x180245180  test    r9d, r9d
0x180245183  js      short loc_180245192
0x180245185  test    ecx, ecx
0x180245187  js      short loc_180245192
0x180245189  cmp     r8d, r9d
0x18024518c  jl      short loc_180245192
0x18024518e  cmp     edx, ecx
0x180245190  jge     short loc_1802451CF
0x180245192  mov     r12b, bl
0x180245195  mov     [rsp+140h+var_108], r8d
0x18024519a  mov     [rsp+140h+var_110], edx
0x18024519e  mov     dword ptr [rsp+140h+var_118], r9d
0x1802451a3  mov     dword ptr [rsp+140h+var_120], ecx
0x1802451a7  mov     r9d, r15d
0x1802451aa  lea     r8, aD3d12VideoEnco_100; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pM"...
0x1802451b1  mov     edx, 51Ah
0x1802451b6  mov     rcx, r14
0x1802451b9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802451be  mov     ecx, dword ptr [rbp+40h+arg_0]
0x1802451c1  mov     edx, [rsp+140h+var_F0]
0x1802451c5  mov     r8d, [rsp+140h+var_EC]
0x1802451ca  mov     r9d, [rsp+140h+var_E8]
0x1802451cf  mov     r10d, [r13+0]
0x1802451d3  movsxd  rax, r8d
0x1802451d6  cmp     rax, r10
0x1802451d9  ja      short loc_1802451E1
0x1802451db  cmp     edx, [r13+4]
0x1802451df  jbe     short loc_18024521A
0x1802451e1  mov     r12b, bl
0x1802451e4  mov     [rsp+140h+var_F8], r8d
0x1802451e9  mov     [rsp+140h+var_100], edx
0x1802451ed  mov     [rsp+140h+var_108], r9d
0x1802451f2  mov     [rsp+140h+var_110], ecx
0x1802451f6  mov     eax, [r13+4]
0x1802451fa  mov     dword ptr [rsp+140h+var_118], eax
0x1802451fe  mov     dword ptr [rsp+140h+var_120], r10d
0x180245203  mov     r9d, r15d
0x180245206  lea     r8, aD3d12VideoEnco_22; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pM"...
0x18024520d  mov     edx, 51Ah
0x180245212  mov     rcx, r14
0x180245215  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024521a  mov     rax, [rdi+8]
0x18024521e  mov     rax, [rax+8]
0x180245222  mov     rcx, [rsp+140h+var_E0]
0x180245227  mov     rax, [rax+rcx*8]
0x18024522b  mov     edx, [r13+0]
0x18024522f  movsxd  rcx, eax
0x180245232  cmp     rcx, rdx
0x180245235  ja      short loc_180245244
0x180245237  mov     rcx, rax
0x18024523a  shr     rcx, 20h
0x18024523e  cmp     ecx, [r13+4]
0x180245242  jbe     short loc_180245279
0x180245244  mov     r12b, bl
0x180245247  mov     rcx, rax
0x18024524a  shr     rcx, 20h
0x18024524e  mov     [rsp+140h+var_108], ecx
0x180245252  mov     [rsp+140h+var_110], eax
0x180245256  mov     eax, [r13+4]
0x18024525a  mov     dword ptr [rsp+140h+var_118], eax
0x18024525e  mov     dword ptr [rsp+140h+var_120], edx
0x180245262  mov     r9d, r15d
0x180245265  lea     r8, aD3d12VideoEnco_87; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pM"...
0x18024526c  mov     edx, 51Ah
0x180245271  mov     rcx, r14
0x180245274  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180245279  inc     r15d
0x18024527c  mov     rcx, [rdi+8]
0x180245280  cmp     r15d, [rcx]
0x180245283  jb      loc_18024514D
0x180245289  and     sil, r12b
0x18024528c  mov     r12d, 51Ah
0x180245292  jmp     short loc_1802452A9
0x180245294  mov     sil, bl
0x180245297  lea     r8, aD3d12VideoEnco_67; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::pM"...
0x18024529e  mov     edx, r12d
0x1802452a1  mov     rcx, r14
0x1802452a4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802452a9  mov     rax, [rdi+8]
0x1802452ad  mov     r9d, [rax+14h]
0x1802452b1  mov     eax, dword ptr [rbp+40h+var_54+4]
0x1802452b4  mov     ecx, dword ptr [rbp+40h+var_54]
0x1802452b7  cmp     r9d, ecx
0x1802452ba  jb      short loc_1802452C1
0x1802452bc  cmp     r9d, eax
0x1802452bf  jbe     short loc_1802452DE
0x1802452c1  mov     sil, bl
0x1802452c4  mov     dword ptr [rsp+140h+var_118], eax
0x1802452c8  mov     dword ptr [rsp+140h+var_120], ecx
0x1802452cc  lea     r8, aD3d12VideoEnco_60; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::Mo"...
0x1802452d3  mov     edx, r12d
0x1802452d6  mov     rcx, r14
0x1802452d9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802452de  mov     rax, [rdi+8]
0x1802452e2  mov     r9d, [rax+18h]
0x1802452e6  mov     eax, [rbp+40h+arg_40]
0x1802452ec  cmp     r9d, eax
0x1802452ef  jb      short loc_18024530A
0x1802452f1  mov     sil, bl
0x1802452f4  mov     dword ptr [rsp+140h+var_120], eax
0x1802452f8  lea     r8, aD3d12VideoEnco_127; "D3D12_VIDEO_ENCODER_MOVEREGION_INFO::So"...
0x1802452ff  mov     edx, r12d
0x180245302  mov     rcx, r14
0x180245305  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024530a  test    sil, sil
0x18024530d  setnz   bl
0x180245310  mov     eax, ebx
0x180245312  add     rsp, 108h
0x180245319  pop     r15
0x18024531b  pop     r14
0x18024531d  pop     r13
0x18024531f  pop     r12
0x180245321  pop     rdi
0x180245322  pop     rsi
0x180245323  pop     rbx
0x180245324  pop     rbp
0x180245325  retn
```
