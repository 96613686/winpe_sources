# SingleSideReduce

- ea: `0x1004162a0`
- end: `0x100416a78`
- name: `SingleSideReduce`
- size: `2008`
- prototype: `__int64 __fastcall(struct GeoData *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x100401be0`
- `0x100403880`
- `0x10040d210`
- `0x10040dc20`
- `0x10040ddc0`
- `0x100415880`
- `0x1004162a0`
- `0x100421170`
- `0x100422970`
- `0x100423450`
- `0x100425d60`
- `0x100432b80`
- `0x100436ff0`
- `0x100437180`
- `0x1004391b0`
- `0x100439310`
- `0x10043b830`
- `0x100445370`
- `0x100468a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=104
__int64 __fastcall SingleSideReduce(struct GeoData *a1, double a2, char a3, struct GeoDataAllocator *a4)
{
  __int64 v7; // rax
  int v8; // esi
  unsigned int v9; // r14d
  unsigned int v10; // r14d
  __m128i v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm2
  __int128 v14; // xmm3
  __int128 v15; // xmm4
  unsigned int v16; // ebx
  bool v18[8]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v19; // [rsp+50h] [rbp-B8h]
  _QWORD v20[2]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v21[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v22[24]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v23[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v24[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v25[24]; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v26; // [rsp+D0h] [rbp-38h]
  __int128 v27; // [rsp+E0h] [rbp-28h]
  __int128 v28; // [rsp+F0h] [rbp-18h]
  __int128 v29; // [rsp+100h] [rbp-8h]
  __int128 v30; // [rsp+110h] [rbp+8h]
  _QWORD v31[2]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v32[6]; // [rsp+158h] [rbp+50h] BYREF
  int v33[4]; // [rsp+188h] [rbp+80h] BYREF
  __int128 v34; // [rsp+198h] [rbp+90h]
  __int128 v35; // [rsp+1A8h] [rbp+A0h]
  __int128 v36; // [rsp+1B8h] [rbp+B0h]
  __int128 v37; // [rsp+1C8h] [rbp+C0h]
  _OWORD v38[5]; // [rsp+1D8h] [rbp+D0h] BYREF
  int v39[2]; // [rsp+228h] [rbp+120h] BYREF
  _BYTE *v40; // [rsp+230h] [rbp+128h]
  __int128 v41; // [rsp+238h] [rbp+130h]
  __int128 v42; // [rsp+248h] [rbp+140h]
  _QWORD v43[2]; // [rsp+258h] [rbp+150h] BYREF
  __int128 v44; // [rsp+268h] [rbp+160h]
  __m128d v45; // [rsp+278h] [rbp+170h]
  _BYTE v46[24]; // [rsp+288h] [rbp+180h] BYREF
  double v47; // [rsp+2A0h] [rbp+198h]
  double v48; // [rsp+2A8h] [rbp+1A0h]
  _QWORD *v49; // [rsp+2B0h] [rbp+1A8h]
  _BYTE v50[16]; // [rsp+328h] [rbp+220h] BYREF
  _BYTE v51[16]; // [rsp+338h] [rbp+230h] BYREF
  unsigned int v52; // [rsp+348h] [rbp+240h]
  void **v53; // [rsp+358h] [rbp+250h] BYREF
  _BYTE v54[8]; // [rsp+360h] [rbp+258h] BYREF
  _BYTE *v55; // [rsp+368h] [rbp+260h]
  _BYTE v56[8]; // [rsp+390h] [rbp+288h] BYREF
  _BYTE *v57; // [rsp+398h] [rbp+290h]
  double v58; // [rsp+3B0h] [rbp+2A8h]
  double v59; // [rsp+3B8h] [rbp+2B0h]
  _BYTE v60[24]; // [rsp+418h] [rbp+310h] BYREF
  double v61; // [rsp+430h] [rbp+328h]
  double v62; // [rsp+438h] [rbp+330h]
  _QWORD *v63; // [rsp+440h] [rbp+338h]
  _BYTE v64[16]; // [rsp+4B8h] [rbp+3B0h] BYREF
  _BYTE v65[16]; // [rsp+4C8h] [rbp+3C0h] BYREF
  unsigned int v66; // [rsp+4D8h] [rbp+3D0h]
  _QWORD v67[71]; // [rsp+4E0h] [rbp+3D8h] BYREF
  int v68; // [rsp+718h] [rbp+610h]
  _QWORD v69[18]; // [rsp+720h] [rbp+618h] BYREF
  char v70; // [rsp+7B0h] [rbp+6A8h]

  v32[4] = -2;
  v7 = *(_QWORD *)a1;
  v31[0] = 0;
  v31[1] = v7;
  GeometryDataBuilder::GeometryDataBuilder((GeometryDataBuilder *)v21, a4, (struct COriginalPoints *)v31);
  *(double *)&v32[2] = DOUBLE_1_797693134862316e308;
  *(double *)v32 = DOUBLE_1_797693134862316e308;
  *(double *)&v32[3] = DOUBLE_2_225073858507201eN308;
  *(double *)&v32[1] = DOUBLE_2_225073858507201eN308;
  *(_OWORD *)v33 = *(_OWORD *)a1;
  v34 = *((_OWORD *)a1 + 1);
  v35 = *((_OWORD *)a1 + 2);
  v36 = *((_OWORD *)a1 + 3);
  v37 = *((_OWORD *)a1 + 4);
  v8 = ComputeBounds((int)v33);
  if ( v8 >= 0 )
  {
    if ( *(_BYTE *)(*((_QWORD *)a1 + 6) + 8LL) == 7 || a2 >= 0.0 && *((_DWORD *)a1 + 14) != 1 )
    {
      v20[0] = &C2DMetadataResolver::`vftable';
      v20[1] = v31;
      CScannerModuleD::CScannerModuleD((CScannerModuleD *)&v53, (struct CScanner *)v67);
      v53 = &CReducerBooleanModule::`vftable';
      CSingleSideReducer::CSingleSideReducer((CSingleSideReducer *)v60, a2, 1);
      v19 = v67;
      C2ShapesProcessor::C2ShapesProcessor((C2ShapesProcessor *)v67, 0, 0);
      v67[0] = &CBoolean::`vftable';
      v67[70] = v69;
      v68 = 0;
      v32[5] = v69;
      CReconstructor::CReconstructor((CReconstructor *)v69, (struct IMglGeometrySink *)v56, 0, 0);
      v69[0] = &CStructuredReconstructor::`vftable';
      v70 = 0;
      v55 = v60;
      v63 = v67;
      v57 = v21;
      v67[47] = v20;
      if ( (int)CWorkspaceTransform::SetWithScaleFactor(v54, v32) >= 0 )
      {
        v61 = fmin(v58, v59);
        v62 = v61 * v61;
      }
      v10 = *((_DWORD *)a1 + 2);
      v8 = CAutoArray<CMglPoint<double>,0,Default_Allocator<CMglPoint<double>>>::Reserve(v64, v10);
      if ( v8 < 0
        || v60[16]
        && (_mm_lfence(),
            v8 = CAutoArray<unsigned __int64,0,Default_Allocator<unsigned __int64>>::Reserve(v65, v10),
            v8 < 0)
        || (v66 = v10,
            v8 = PopulateAsUnion(a1, (struct CGeometrySinkD *)v54, 1, 1, (struct C2DMetadataResolver *)v20, 0),
            v8 < 0) )
      {
        _mm_lfence();
        CReducerBooleanModule::~CReducerBooleanModule((CReducerBooleanModule *)&v53);
        v20[0] = &CMetadataResolver::`vftable';
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v25);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v24);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v23);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v22);
        return (unsigned int)v8;
      }
      CReducerBooleanModule::~CReducerBooleanModule((CReducerBooleanModule *)&v53);
      v20[0] = &CMetadataResolver::`vftable';
    }
    else
    {
      CSingleSideReducer::CSingleSideReducer((CSingleSideReducer *)v46, a2, 1);
      *(_QWORD *)v39 = &CWorkspaceTransform::`vftable';
      v42 = _xmm;
      v19 = v43;
      v43[0] = &CScaleAndShift::`vftable';
      v45 = (__m128d)_xmm;
      v44 = 0;
      v41 = 0;
      v40 = v46;
      v49 = v43;
      v43[1] = v21;
      v8 = CWorkspaceTransform::SetWithScaleFactor(v39, v32);
      if ( v8 < 0 )
        goto LABEL_7;
      *(_QWORD *)&v45.m128d_f64[1] = *(_OWORD *)&_mm_unpackhi_pd(v45, v45);
      v47 = fmin(v45.m128d_f64[0], v45.m128d_f64[1]);
      v48 = v47 * v47;
      v9 = *((_DWORD *)a1 + 2);
      v8 = CAutoArray<CMglPoint<double>,0,Default_Allocator<CMglPoint<double>>>::Reserve(v50, v9);
      if ( v8 < 0 )
        goto LABEL_7;
      if ( v46[16] )
      {
        _mm_lfence();
        v8 = CAutoArray<unsigned __int64,0,Default_Allocator<unsigned __int64>>::Reserve(v51, v9);
        if ( v8 < 0 )
          goto LABEL_7;
      }
      v52 = v9;
      v8 = InternalPopulate<CGeometrySinkD>((__int64)a1, (__int64)v39, 0, 1u, 1, 0, 1);
      if ( v8 < 0 )
      {
LABEL_7:
        _mm_lfence();
        v19 = v43;
        v43[0] = &IMglGeometrySink::`vftable';
        *(_QWORD *)v39 = &IMglGeometrySink::`vftable';
        CSingleSideReducer::~CSingleSideReducer((CSingleSideReducer *)v46);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v25);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v24);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v23);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v22);
        return (unsigned int)v8;
      }
      v19 = v43;
      v43[0] = &IMglGeometrySink::`vftable';
      *(_QWORD *)v39 = &IMglGeometrySink::`vftable';
      CSingleSideReducer::~CSingleSideReducer((CSingleSideReducer *)v46);
    }
    v11 = v26;
    *(__m128i *)a1 = v26;
    v12 = v27;
    *((_OWORD *)a1 + 1) = v27;
    v13 = v28;
    *((_OWORD *)a1 + 2) = v28;
    v14 = v29;
    *((_OWORD *)a1 + 3) = v29;
    v15 = v30;
    *((_OWORD *)a1 + 4) = v30;
    if ( a3 )
    {
      v16 = ValidateOutput(a1, a4);
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v25);
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v24);
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v23);
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v22);
      return v16;
    }
    v38[0] = v11;
    v38[1] = v12;
    v38[2] = v13;
    v38[3] = v14;
    v38[4] = v15;
    v26.m128i_i32[2] = _mm_cvtsi128_si32(_mm_srli_si128(v11, 8));
    if ( v26.m128i_i32[2] || *(_BYTE *)(v29 + 8) == 11 )
    {
      IsValidCore((const struct GeoData *)v38, v18, 0, 0);
      if ( !v18[0] )
      {
        GetEmpty(a4);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v25);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v24);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v23);
        ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v22);
        return 1;
      }
    }
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v25);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v24);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v23);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v22);
  }
  else
  {
    _mm_lfence();
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v25);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v24);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v23);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v22);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1004162a0  mov     rax, rsp
0x1004162a3  push    rbp
0x1004162a4  push    r12
0x1004162a6  push    r13
0x1004162a8  push    r14
0x1004162aa  push    r15
0x1004162ac  lea     rbp, [rax-6F8h]
0x1004162b3  sub     rsp, 7D0h
0x1004162ba  mov     [rbp+6F0h+var_680], 0FFFFFFFFFFFFFFFEh
0x1004162c2  mov     [rax+10h], rbx
0x1004162c6  mov     [rax+18h], rsi
0x1004162ca  mov     [rax+20h], rdi
0x1004162ce  movaps  xmmword ptr [rax-38h], xmm6
0x1004162d2  mov     rax, cs:__security_cookie
0x1004162d9  xor     rax, rsp
0x1004162dc  mov     [rbp+6F0h+var_40], rax
0x1004162e3  mov     r15, r9
0x1004162e6  movzx   r12d, r8b
0x1004162ea  movaps  xmm6, xmm1
0x1004162ed  mov     rbx, rcx
0x1004162f0  mov     rax, [rcx]
0x1004162f3  xor     r14d, r14d
0x1004162f6  mov     [rbp+6F0h+var_6B0], r14
0x1004162fa  mov     [rbp+6F0h+var_6A8], rax
0x1004162fe  lea     r8, [rbp+6F0h+var_6B0]; struct COriginalPoints *
0x100416302  mov     rdx, r9; struct GeoDataAllocator *
0x100416305  lea     rcx, [rsp+7F0h+var_790]; this
0x10041630a  call    ??0GeometryDataBuilder@@QEAA@PEAUGeoDataAllocator@@PEAVCOriginalPoints@@@Z; GeometryDataBuilder::GeometryDataBuilder(GeoDataAllocator *,COriginalPoints *)
0x10041630f  nop
0x100416310  movsd   xmm0, cs:__real@7fefffffffffffff
0x100416318  movsd   [rbp+6F0h+var_690], xmm0
0x10041631d  movsd   [rbp+6F0h+var_6A0], xmm0
0x100416322  movsd   xmm1, cs:__real@0010000000000000
0x10041632a  movsd   [rbp+6F0h+var_688], xmm1
0x10041632f  movsd   [rbp+6F0h+var_698], xmm1
0x100416334  movups  xmm0, xmmword ptr [rbx]
0x100416337  movaps  xmmword ptr [rbp+6F0h+var_670], xmm0
0x10041633e  movups  xmm1, xmmword ptr [rbx+10h]
0x100416342  movaps  [rbp+6F0h+var_660], xmm1
0x100416349  movups  xmm0, xmmword ptr [rbx+20h]
0x10041634d  movaps  [rbp+6F0h+var_650], xmm0
0x100416354  movups  xmm1, xmmword ptr [rbx+30h]
0x100416358  movaps  [rbp+6F0h+var_640], xmm1
0x10041635f  movups  xmm0, xmmword ptr [rbx+40h]
0x100416363  movaps  [rbp+6F0h+var_630], xmm0
0x10041636a  lea     rdx, [rbp+6F0h+var_6A0]
0x10041636e  lea     rcx, [rbp+6F0h+var_670]; int
0x100416375  call    ?ComputeBounds@@YAJUGeoData@@PEAV?$CMglRect@N@@@Z; ComputeBounds(GeoData,CMglRect<double> *)
0x10041637a  mov     esi, eax
0x10041637c  test    eax, eax
0x10041637e  jns     short loc_1004163B1
0x100416380  lfence
0x100416383  lea     rcx, [rbp+6F0h+var_740]
0x100416387  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041638c  nop
0x10041638d  lea     rcx, [rbp+6F0h+var_758]
0x100416391  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416396  nop
0x100416397  lea     rcx, [rbp+6F0h+var_770]
0x10041639b  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x1004163a0  nop
0x1004163a1  lea     rcx, [rsp+7F0h+var_788]
0x1004163a6  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x1004163ab  nop
0x1004163ac  jmp     loc_100416A35
0x1004163b1  mov     rax, [rbx+30h]
0x1004163b5  lea     rdi, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x1004163bc  cmp     byte ptr [rax+8], 7
0x1004163c0  jz      loc_10041669D
0x1004163c6  xorps   xmm0, xmm0
0x1004163c9  comisd  xmm0, xmm6
0x1004163cd  ja      short loc_1004163D9
0x1004163cf  cmp     dword ptr [rbx+38h], 1
0x1004163d3  jnz     loc_10041669D
0x1004163d9  mov     r8b, 1; bool
0x1004163dc  movaps  xmm1, xmm6; double
0x1004163df  lea     rcx, [rbp+6F0h+var_570]; this
0x1004163e6  call    ??0CSingleSideReducer@@QEAA@N_N@Z; CSingleSideReducer::CSingleSideReducer(double,bool)
0x1004163eb  nop
0x1004163ec  mov     qword ptr [rbp+6F0h+var_5D0], rdi
0x1004163f3  lea     rdx, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x1004163fa  mov     qword ptr [rbp+6F0h+var_5D0], rdx
0x100416401  lea     rcx, ??_7CPointSink@@6B@; const CPointSink::`vftable'
0x100416408  mov     qword ptr [rbp+6F0h+var_5D0], rcx
0x10041640f  mov     [rbp+6F0h+var_5C8], r14
0x100416416  lea     rax, ??_7CWorkspaceTransform@@6B@; const CWorkspaceTransform::`vftable'
0x10041641d  mov     qword ptr [rbp+6F0h+var_5D0], rax
0x100416424  movaps  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x10041642b  movaps  [rbp+6F0h+var_5B0], xmm0
0x100416432  lea     rax, [rbp+6F0h+var_5A0]
0x100416439  mov     [rsp+7F0h+var_7A8], rax
0x10041643e  mov     [rbp+6F0h+var_5A0], rdi
0x100416445  mov     [rbp+6F0h+var_5A0], rdx
0x10041644c  mov     [rbp+6F0h+var_5A0], rcx
0x100416453  mov     [rbp+6F0h+var_598], r14
0x10041645a  lea     rax, ??_7CScaleAndShift@@6B@; const CScaleAndShift::`vftable'
0x100416461  mov     [rbp+6F0h+var_5A0], rax
0x100416468  movaps  [rbp+6F0h+var_580], xmm0
0x10041646f  xorps   xmm1, xmm1
0x100416472  movaps  [rbp+6F0h+var_590], xmm1
0x100416479  xorps   xmm0, xmm0
0x10041647c  movaps  [rbp+6F0h+var_5C0], xmm0
0x100416483  lea     rax, [rbp+6F0h+var_570]
0x10041648a  mov     [rbp+6F0h+var_5C8], rax
0x100416491  lea     rax, [rbp+6F0h+var_5A0]
0x100416498  mov     [rbp+6F0h+var_548], rax
0x10041649f  lea     rax, [rsp+7F0h+var_790]
0x1004164a4  mov     [rbp+6F0h+var_598], rax
0x1004164ab  movsd   xmm2, cs:__real@3ff0000000000000
0x1004164b3  lea     rdx, [rbp+6F0h+var_6A0]
0x1004164b7  lea     rcx, [rbp+6F0h+var_5D0]
0x1004164be  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x1004164c3  mov     esi, eax
0x1004164c5  test    eax, eax
0x1004164c7  jns     short loc_100416521
0x1004164c9  lfence
0x1004164cc  lea     rax, [rbp+6F0h+var_5A0]
0x1004164d3  mov     [rsp+7F0h+var_7A8], rax
0x1004164d8  mov     [rbp+6F0h+var_5A0], rdi
0x1004164df  mov     qword ptr [rbp+6F0h+var_5D0], rdi
0x1004164e6  lea     rcx, [rbp+6F0h+var_570]; this
0x1004164ed  call    ??1CSingleSideReducer@@UEAA@XZ; CSingleSideReducer::~CSingleSideReducer(void)
0x1004164f2  nop
0x1004164f3  lea     rcx, [rbp+6F0h+var_740]
0x1004164f7  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x1004164fc  nop
0x1004164fd  lea     rcx, [rbp+6F0h+var_758]
0x100416501  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416506  nop
0x100416507  lea     rcx, [rbp+6F0h+var_770]
0x10041650b  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416510  nop
0x100416511  lea     rcx, [rsp+7F0h+var_788]
0x100416516  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041651b  nop
0x10041651c  jmp     loc_100416A3C
0x100416521  movaps  xmm1, [rbp+6F0h+var_580]
0x100416528  movaps  xmm0, xmm1
0x10041652b  unpckhpd xmm0, xmm1
0x10041652f  movsd   qword ptr [rbp+6F0h+var_580+8], xmm0
0x100416537  minsd   xmm1, xmm0
0x10041653b  movsd   [rbp+6F0h+var_558], xmm1
0x100416543  mulsd   xmm1, xmm1
0x100416547  movsd   [rbp+6F0h+var_550], xmm1
0x10041654f  mov     r14d, [rbx+8]
0x100416553  mov     edx, r14d
0x100416556  lea     rcx, [rbp+6F0h+var_4D0]
0x10041655d  call    ?Reserve@?$CAutoArray@V?$CMglPoint@N@@$0A@V?$Default_Allocator@V?$CMglPoint@N@@@@@@QEAAJI@Z; CAutoArray<CMglPoint<double>,0,Default_Allocator<CMglPoint<double>>>::Reserve(uint)
0x100416562  mov     esi, eax
0x100416564  test    eax, eax
0x100416566  js      loc_100416645
0x10041656c  cmp     [rbp+6F0h+var_560], 0
0x100416573  jz      short loc_100416591
0x100416575  lfence
0x100416578  mov     edx, r14d
0x10041657b  lea     rcx, [rbp+6F0h+var_4C0]
0x100416582  call    ?Reserve@?$CAutoArray@_K$0A@V?$Default_Allocator@_K@@@@QEAAJI@Z; CAutoArray<unsigned __int64,0,Default_Allocator<unsigned __int64>>::Reserve(uint)
0x100416587  mov     esi, eax
0x100416589  test    eax, eax
0x10041658b  js      loc_100416645
0x100416591  mov     [rbp+6F0h+var_4B0], r14d
0x100416598  mov     [rsp+7F0h+var_7C0], 1; char
0x10041659d  mov     [rsp+7F0h+var_7C8], 0; char
0x1004165a2  mov     byte ptr [rsp+7F0h+var_7D0], 1; char
0x1004165a7  mov     r9b, 1
0x1004165aa  xor     r8d, r8d
0x1004165ad  lea     rdx, [rbp+6F0h+var_5D0]; int
0x1004165b4  mov     rcx, rbx; int
0x1004165b7  call    ??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z; InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)
0x1004165bc  mov     esi, eax
0x1004165be  test    eax, eax
0x1004165c0  jns     short loc_10041661A
0x1004165c2  lfence
0x1004165c5  lea     rax, [rbp+6F0h+var_5A0]
0x1004165cc  mov     [rsp+7F0h+var_7A8], rax
0x1004165d1  mov     [rbp+6F0h+var_5A0], rdi
0x1004165d8  mov     qword ptr [rbp+6F0h+var_5D0], rdi
0x1004165df  lea     rcx, [rbp+6F0h+var_570]; this
0x1004165e6  call    ??1CSingleSideReducer@@UEAA@XZ; CSingleSideReducer::~CSingleSideReducer(void)
0x1004165eb  nop
0x1004165ec  lea     rcx, [rbp+6F0h+var_740]
0x1004165f0  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x1004165f5  nop
0x1004165f6  lea     rcx, [rbp+6F0h+var_758]
0x1004165fa  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x1004165ff  nop
0x100416600  lea     rcx, [rbp+6F0h+var_770]
0x100416604  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416609  nop
0x10041660a  lea     rcx, [rsp+7F0h+var_788]
0x10041660f  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416614  nop
0x100416615  jmp     loc_100416A3C
0x10041661a  lea     rax, [rbp+6F0h+var_5A0]
0x100416621  mov     [rsp+7F0h+var_7A8], rax
0x100416626  mov     [rbp+6F0h+var_5A0], rdi
0x10041662d  mov     qword ptr [rbp+6F0h+var_5D0], rdi
0x100416634  lea     rcx, [rbp+6F0h+var_570]; this
0x10041663b  call    ??1CSingleSideReducer@@UEAA@XZ; CSingleSideReducer::~CSingleSideReducer(void)
0x100416640  jmp     loc_1004168C3
0x100416645  lfence
0x100416648  lea     rax, [rbp+6F0h+var_5A0]
0x10041664f  mov     [rsp+7F0h+var_7A8], rax
0x100416654  mov     [rbp+6F0h+var_5A0], rdi
0x10041665b  mov     qword ptr [rbp+6F0h+var_5D0], rdi
0x100416662  lea     rcx, [rbp+6F0h+var_570]; this
0x100416669  call    ??1CSingleSideReducer@@UEAA@XZ; CSingleSideReducer::~CSingleSideReducer(void)
0x10041666e  nop
0x10041666f  lea     rcx, [rbp+6F0h+var_740]
0x100416673  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416678  nop
0x100416679  lea     rcx, [rbp+6F0h+var_758]
0x10041667d  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416682  nop
0x100416683  lea     rcx, [rbp+6F0h+var_770]
0x100416687  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041668c  nop
0x10041668d  lea     rcx, [rsp+7F0h+var_788]
0x100416692  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100416697  nop
0x100416698  jmp     loc_100416A3C
0x10041669d  lea     r13, ??_7CMetadataResolver@@6B@; const CMetadataResolver::`vftable'
0x1004166a4  mov     [rsp+7F0h+var_7A0], r13
0x1004166a9  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x1004166b0  mov     [rsp+7F0h+var_7A0], rax
0x1004166b5  lea     rax, [rbp+6F0h+var_6B0]
0x1004166b9  mov     [rsp+7F0h+var_798], rax
0x1004166be  lea     rdx, [rbp+6F0h+var_318]; struct CScanner *
0x1004166c5  lea     rcx, [rbp+6F0h+var_4A0]; this
0x1004166cc  call    ??0CScannerModuleD@@QEAA@AEAVCScanner@@@Z; CScannerModuleD::CScannerModuleD(CScanner &)
0x1004166d1  nop
0x1004166d2  lea     rax, ??_7CReducerBooleanModule@@6B@; const CReducerBooleanModule::`vftable'
0x1004166d9  mov     [rbp+6F0h+var_4A0], rax
0x1004166e0  mov     r8b, 1; bool
0x1004166e3  movaps  xmm1, xmm6; double
0x1004166e6  lea     rcx, [rbp+6F0h+var_3E0]; this
0x1004166ed  call    ??0CSingleSideReducer@@QEAA@N_N@Z; CSingleSideReducer::CSingleSideReducer(double,bool)
0x1004166f2  nop
0x1004166f3  lea     rax, [rbp+6F0h+var_318]
0x1004166fa  mov     [rsp+7F0h+var_7A8], rax
0x1004166ff  xor     r8d, r8d; bool
0x100416702  xor     edx, edx; bool
0x100416704  lea     rcx, [rbp+6F0h+var_318]; this
0x10041670b  call    ??0C2ShapesProcessor@@QEAA@_N0@Z; C2ShapesProcessor::C2ShapesProcessor(bool,bool)
0x100416710  nop
0x100416711  lea     rax, ??_7CBoolean@@6B@; const CBoolean::`vftable'
0x100416718  mov     [rbp+6F0h+var_318], rax
0x10041671f  lea     rax, [rbp+6F0h+var_D8]
0x100416726  mov     [rbp+6F0h+var_E8], rax
0x10041672d  mov     [rbp+6F0h+var_E0], r14d
0x100416734  lea     rax, [rbp+6F0h+var_D8]
0x10041673b  mov     [rbp+6F0h+var_678], rax
0x10041673f  xor     r9d, r9d; bool
0x100416742  xor     r8d, r8d; bool
0x100416745  lea     rdx, [rbp+6F0h+var_468]; struct IMglGeometrySink *
0x10041674c  lea     rcx, [rbp+6F0h+var_D8]; this
0x100416753  call    ??0CReconstructor@@QEAA@PEAUIMglGeometrySink@@_N1@Z; CReconstructor::CReconstructor(IMglGeometrySink *,bool,bool)
0x100416758  nop
0x100416759  lea     rax, ??_7CStructuredReconstructor@@6B@; const CStructuredReconstructor::`vftable'
0x100416760  mov     [rbp+6F0h+var_D8], rax
0x100416767  mov     [rbp+6F0h+var_48], 0
0x10041676e  lea     rax, [rbp+6F0h+var_3E0]
0x100416775  mov     [rbp+6F0h+var_490], rax
0x10041677c  lea     rax, [rbp+6F0h+var_318]
0x100416783  mov     [rbp+6F0h+var_3B8], rax
0x10041678a  lea     rax, [rsp+7F0h+var_790]
0x10041678f  mov     [rbp+6F0h+var_460], rax
0x100416796  lea     rax, [rsp+7F0h+var_7A0]
0x10041679b  mov     [rbp+6F0h+var_1A0], rax
0x1004167a2  movsd   xmm2, cs:__real@3ff0000000000000
0x1004167aa  lea     rdx, [rbp+6F0h+var_6A0]
0x1004167ae  lea     rcx, [rbp+6F0h+var_498]
0x1004167b5  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x1004167ba  test    eax, eax
0x1004167bc  js      short loc_1004167E2
0x1004167be  movsd   xmm0, [rbp+6F0h+var_448]
0x1004167c6  minsd   xmm0, [rbp+6F0h+var_440]
0x1004167ce  movsd   [rbp+6F0h+var_3C8], xmm0
0x1004167d6  mulsd   xmm0, xmm0
0x1004167da  movsd   [rbp+6F0h+var_3C0], xmm0
0x1004167e2  mov     r14d, [rbx+8]
0x1004167e6  mov     edx, r14d
0x1004167e9  lea     rcx, [rbp+6F0h+var_340]
0x1004167f0  call    ?Reserve@?$CAutoArray@V?$CMglPoint@N@@$0A@V?$Default_Allocator@V?$CMglPoint@N@@@@@@QEAAJI@Z; CAutoArray<CMglPoint<double>,0,Default_Allocator<CMglPoint<double>>>::Reserve(uint)
0x1004167f5  mov     esi, eax
0x1004167f7  test    eax, eax
0x1004167f9  js      loc_1004169EB
0x1004167ff  cmp     [rbp+6F0h+var_3D0], 0
0x100416806  jz      short loc_100416824
0x100416808  lfence
0x10041680b  mov     edx, r14d
0x10041680e  lea     rcx, [rbp+6F0h+var_330]
0x100416815  call    ?Reserve@?$CAutoArray@_K$0A@V?$Default_Allocator@_K@@@@QEAAJI@Z; CAutoArray<unsigned __int64,0,Default_Allocator<unsigned __int64>>::Reserve(uint)
0x10041681a  mov     esi, eax
0x10041681c  test    eax, eax
0x10041681e  js      loc_1004169EB
0x100416824  mov     [rbp+6F0h+var_320], r14d
0x10041682b  mov     [rsp+7F0h+var_7C8], 0; bool
0x100416830  lea     rax, [rsp+7F0h+var_7A0]
0x100416835  mov     [rsp+7F0h+var_7D0], rax; struct C2DMetadataResolver *
  ... truncated ...
```
