# GEL::GDITech::DrawPathOutline(Gdiplus::GpGraphics &,Gdiplus::GpPen const *,Gdiplus::GpPath const *,bool)

- ea: `0x18005eb78`
- end: `0x18005f20f`
- name: `?DrawPathOutline@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpPen@4@PEBVGpPath@4@_N@Z`
- size: `1687`
- prototype: `void __fastcall(struct Gdiplus::GpGraphics *, const struct Gdiplus::GpPen *, const struct Gdiplus::GpPath *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18005e810`

## callees

- `0x180051fb0`
- `0x18005eb78`
- `0x180061fe8`
- `0x180062394`
- `0x180062b24`
- `0x180064550`
- `0x1800bff78`
- `0x18014a470`
- `0x18014a4d0`
- `0x18014a530`
- `0x180178678`
- `0x180204a16`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005eced`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18005eced`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18005ecac`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18005ecac`
- `gdiplus!GdipGetPenUnit` at `0x18005ec83`
- `gdiplus!GdipGetPenUnit` at `0x18005ec83`
- `gdiplus!GdipGetPathWorldBounds` at `0x18005ee7e`
- `gdiplus!GdipGetPathWorldBounds` at `0x18005ee7e`
- `gdiplus!GdipIsVisibleClipEmpty` at `0x18005eea2`
- `gdiplus!GdipIsVisibleClipEmpty` at `0x18005eea2`
- `gdiplus!GdipGetVisibleClipBounds` at `0x18005eed9`
- `gdiplus!GdipGetVisibleClipBounds` at `0x18005eed9`
- `gdiplus!GdipDrawPath` at `0x18005ebfa`
- `gdiplus!GdipDrawPath` at `0x18005f128`
- `gdiplus!GdipDrawPath` at `0x18005ebfa`
- `gdiplus!GdipDrawPath` at `0x18005f128`
- `gdiplus!GdipGetWorldTransform` at `0x18005ed14`
- `gdiplus!GdipGetWorldTransform` at `0x18005ed14`
- `gdiplus!GdipSetWorldTransform` at `0x18005f0fa`
- `gdiplus!GdipSetWorldTransform` at `0x18005f0fa`
- `gdiplus!GdipGetPenWidth` at `0x18005eccc`
- `gdiplus!GdipGetPenWidth` at `0x18005eccc`
- `gdiplus!GdipGetMatrixElements` at `0x18005ed3c`
- `gdiplus!GdipGetMatrixElements` at `0x18005ed3c`
- `gdiplus!GdipCreateMatrix` at `0x18005ecf9`
- `gdiplus!GdipCreateMatrix` at `0x18005ecf9`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18005f076`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18005f076`
- `gdiplus!GdipDeleteMatrix` at `0x18005ec0b`
- `gdiplus!GdipDeleteMatrix` at `0x18005ec0b`
- `gdiplus!GdipDrawImageRectRect` at `0x18005f1be`
- `gdiplus!GdipDrawImageRectRect` at `0x18005f1be`
- `gdiplus!GdipSetPageUnit` at `0x18005f094`
- `gdiplus!GdipSetPageUnit` at `0x18005f094`
- `gdiplus!GdipDeleteGraphics` at `0x18005f141`
- `gdiplus!GdipDeleteGraphics` at `0x18005f141`
- `gdiplus!GdipDisposeImage` at `0x18005f1f1`
- `gdiplus!GdipDisposeImage` at `0x18005f1f1`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18005f057`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18005f057`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall GEL::GDITech::DrawPathOutline(
        struct Gdiplus::GpGraphics *a1,
        const struct Gdiplus::GpPen *a2,
        const struct Gdiplus::GpPath *a3,
        char a4)
{
  bool v7; // al
  bool v8; // al
  unsigned int PenUnit; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int PenWidth; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int WorldTransform; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rbx
  unsigned int MatrixElements; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  float v25; // xmm1_4
  float v26; // xmm0_4
  float v27; // xmm2_4
  float v28; // xmm3_4
  double v29; // xmm7_8
  double v30; // xmm9_8
  double v31; // xmm9_8
  bool v32; // cf
  bool v33; // zf
  __m128d v34; // xmm0
  __m128 v35; // xmm15
  __m128 v36; // xmm15
  unsigned int PathWorldBounds; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int IsVisibleClipEmpty; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  unsigned int VisibleClipBounds; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  float v46; // xmm12_4
  float v47; // xmm9_4
  float v48; // xmm11_4
  float v49; // xmm10_4
  float v50; // xmm3_4
  float v51; // xmm1_4
  unsigned int v52; // edi
  unsigned int v53; // ebx
  float v54; // xmm8_4
  float v55; // xmm6_4
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  unsigned int ImageGraphicsContext; // eax
  __int64 v60; // rdx
  __int64 v61; // r8
  unsigned int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // r8
  __m128 *Matrix; // rax
  unsigned int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // r8
  const struct Math::Identity *v69; // r8
  unsigned int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // [rsp+78h] [rbp-90h] BYREF
  __int64 v74; // [rsp+80h] [rbp-88h] BYREF
  __int64 v75; // [rsp+88h] [rbp-80h]
  __int64 v76; // [rsp+90h] [rbp-78h] BYREF
  __int64 v77; // [rsp+98h] [rbp-70h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-60h]
  __m128 v80; // [rsp+B0h] [rbp-58h] BYREF
  float v81; // [rsp+C0h] [rbp-48h]
  float v82; // [rsp+C4h] [rbp-44h]
  _BYTE v83[16]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v84[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v85[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v86[176]; // [rsp+F8h] [rbp-10h] BYREF
  float v87; // [rsp+1F0h] [rbp+E8h] BYREF

  if ( a4
    || (byte_180520008 < 0
      ? (v8 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180520008))
      : (v8 = byte_180520008 != 0),
        !v8) )
  {
    v7 = 0;
  }
  else
  {
    v87 = 0.0;
    PenUnit = GdipGetPenUnit(a2, &v87);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(PenUnit, v10, v11, 39081232);
    v7 = LODWORD(v87) == 0;
  }
  v73 = 0;
  if ( !v7 )
    goto LABEL_4;
  v87 = 0.0;
  PenWidth = GdipGetPenWidth(a2, &v87);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(PenWidth, v13, v14, 39081233);
  v15 = GdipCreateMatrix(&v73);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 39081234);
  WorldTransform = GdipGetWorldTransform(a1, v73);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(WorldTransform, v19, v20, 39081235);
  v21 = v73;
  if ( v73 )
  {
    MatrixElements = GdipGetMatrixElements(v73, &v80);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(MatrixElements, v23, v24, 38897232);
    v25 = v80.m128_f32[0];
    v21 = v73;
    LODWORD(v26) = _mm_shuffle_ps(v80, v80, 255).m128_u32[0];
    LODWORD(v27) = _mm_shuffle_ps(v80, v80, 170).m128_u32[0];
    LODWORD(v28) = _mm_shuffle_ps(v80, v80, 85).m128_u32[0];
  }
  else
  {
    v28 = 0.0;
    v27 = 0.0;
    v26 = FLOAT_1_0;
    v25 = FLOAT_1_0;
  }
  v29 = v87;
  v30 = sqrt_0(v26 * v26 + v28 * v28) * v29;
  v31 = fmin(v30, sqrt_0(v27 * v27 + v25 * v25) * v29);
  if ( v31 > 0.0 )
  {
    if ( COERCE_DOUBLE(*(_QWORD *)&v31 & _xmm) >= *(double *)&_xmm )
    {
      v32 = v31 > 1.0;
      v33 = 1.0 == v31;
    }
    else
    {
      v32 = v31 - 1.0 > -1.000000003627494e-15;
      v33 = -1.000000003627494e-15 == v31 - 1.0;
    }
    if ( !v32 && !v33 )
    {
      v34 = (__m128d)*(unsigned __int64 *)&DOUBLE_2_0;
      v34.m128d_f64[0] = 2.0 / v31;
      v35 = _mm_cvtpd_ps(v34);
      v36 = _mm_shuffle_ps(v35, v35, 0);
      v75 = 0;
      v74 = 0;
      PathWorldBounds = GdipGetPathWorldBounds(a3, &v74, v21, a2);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(PathWorldBounds, v38, v39, 39081236);
      v87 = 0.0;
      IsVisibleClipEmpty = GdipIsVisibleClipEmpty(a1, &v87);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(IsVisibleClipEmpty, v41, v42, 39081237);
      if ( v87 == 0.0 )
      {
        v79 = 0;
        v78 = 0;
        VisibleClipBounds = GdipGetVisibleClipBounds(a1, &v78);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(VisibleClipBounds, v44, v45, 39081238);
        v46 = *(float *)&v74;
        v47 = *(float *)&v75;
        if ( *(float *)&v78 > *(float *)&v74 )
        {
          v47 = *(float *)&v75 - (float)(*(float *)&v78 - *(float *)&v74);
          *(float *)&v75 = v47;
          v46 = *(float *)&v78;
          LODWORD(v74) = v78;
        }
        v48 = *((float *)&v74 + 1);
        v49 = *((float *)&v75 + 1);
        if ( *((float *)&v78 + 1) > *((float *)&v74 + 1) )
        {
          v49 = *((float *)&v75 + 1) - (float)(*((float *)&v78 + 1) - *((float *)&v74 + 1));
          *((float *)&v75 + 1) = v49;
          v48 = *((float *)&v78 + 1);
          HIDWORD(v74) = HIDWORD(v78);
        }
        v50 = *(float *)&v79 + *(float *)&v78;
        if ( (float)(v47 + v46) > (float)(*(float *)&v79 + *(float *)&v78) )
        {
          v47 = v50 - v46;
          *(float *)&v75 = v50 - v46;
        }
        v51 = *((float *)&v79 + 1) + *((float *)&v78 + 1);
        if ( (float)(v49 + v48) > (float)(*((float *)&v79 + 1) + *((float *)&v78 + 1)) )
        {
          v49 = v51 - v48;
          *((float *)&v75 + 1) = v51 - v48;
        }
        if ( v47 > 0.0 && v49 > 0.0 )
        {
          v52 = (int)ceilf_0((float)(v47 * v36.m128_f32[0]) + 1.0);
          v53 = (int)ceilf_0((float)(v49 * v36.m128_f32[0]) + 1.0);
          v54 = ceilf_0(COERCE_FLOAT(COERCE_UNSIGNED_INT(v48 * v36.m128_f32[0]) ^ _xmm) - 0.050000001);
          v55 = ceilf_0(COERCE_FLOAT(COERCE_UNSIGNED_INT(v46 * v36.m128_f32[0]) ^ _xmm) - 0.050000001);
          v77 = 0;
          v56 = GdipCreateBitmapFromScan0(v52, v53, 0, 2498570, 0, &v77);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v56, v57, v58, 39081239);
          v76 = 0;
          ImageGraphicsContext = GdipGetImageGraphicsContext(v77, &v76);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageGraphicsContext, v60, v61, 39081240);
          v62 = GdipSetPageUnit(v76, 2);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v62, v63, v64, 39081241);
          Matrix = (__m128 *)Gfx::GpMatrixHolder::GetMatrix(&v73, v86);
          v80 = _mm_mul_ps(*Matrix, v36);
          v81 = (float)(v36.m128_f32[0] * Matrix[1].m128_f32[0]) + v55;
          v82 = (float)(v36.m128_f32[0] * Matrix[1].m128_f32[1]) + v54;
          Gfx::GpMatrixHolder::operator=(&v73, &v80);
          v66 = GdipSetWorldTransform(v76, v73);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v66, v67, v68, 39081242);
          Gfx::TGpRestorer<enum Gdiplus::SmoothingMode>::TGpRestorer<enum Gdiplus::SmoothingMode>(v83, v76, 5);
          GdipDrawPath(v76, a2, a3);
          Gfx::TGpRestorer<enum Gdiplus::SmoothingMode>::~TGpRestorer<enum Gdiplus::SmoothingMode>(v83);
          if ( v76 )
            GdipDeleteGraphics();
          Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer((Gfx::GpWorldTransformRestorer *)v85, a1, v69);
          Gfx::TGpRestorer<enum Gdiplus::InterpolationMode>::TGpRestorer<enum Gdiplus::InterpolationMode>(v84, a1, 7);
          v70 = GdipDrawImageRectRect(a1, v77);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v70, v71, v72, 39081243);
          Gfx::TGpRestorer<enum Gdiplus::InterpolationMode>::~TGpRestorer<enum Gdiplus::InterpolationMode>(v84);
          Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer((Gfx::GpWorldTransformRestorer *)v85);
          if ( v77 )
            GdipDisposeImage();
        }
      }
LABEL_5:
      if ( !v73 )
        return;
      goto LABEL_6;
    }
LABEL_4:
    GdipDrawPath(a1, a2, a3);
    goto LABEL_5;
  }
  if ( v21 )
LABEL_6:
    GdipDeleteMatrix();
}

```

## disassembly

```asm
0x18005eb78  mov     rax, rsp
0x18005eb7b  mov     [rax+8], rbx
0x18005eb7f  mov     [rax+10h], rsi
0x18005eb83  push    rbp
0x18005eb84  push    rdi
0x18005eb85  push    r12
0x18005eb87  push    r14
0x18005eb89  push    r15
0x18005eb8b  lea     rbp, [rax-0C8h]
0x18005eb92  sub     rsp, 1A0h
0x18005eb99  movaps  xmmword ptr [rax-38h], xmm6
0x18005eb9d  movaps  xmmword ptr [rax-48h], xmm7
0x18005eba1  movaps  xmmword ptr [rax-58h], xmm8
0x18005eba6  movaps  xmmword ptr [rax-68h], xmm9
0x18005ebab  movaps  xmmword ptr [rax-78h], xmm10
0x18005ebb0  movaps  xmmword ptr [rax-88h], xmm11
0x18005ebb8  movaps  xmmword ptr [rax-98h], xmm12
0x18005ebc0  movaps  xmmword ptr [rax-0A8h], xmm13
0x18005ebc8  movaps  xmmword ptr [rax-0B8h], xmm15
0x18005ebd0  mov     r15, r8
0x18005ebd3  mov     r14, rdx
0x18005ebd6  mov     rsi, rcx
0x18005ebd9  xor     r12d, r12d
0x18005ebdc  test    r9b, r9b
0x18005ebdf  jz      short loc_18005EC5D
0x18005ebe1  mov     al, r12b
0x18005ebe4  mov     [rsp+1C0h+var_150], r12
0x18005ebe9  test    al, al
0x18005ebeb  jnz     loc_18005ECB4
0x18005ebf1  mov     r8, r15
0x18005ebf4  mov     rdx, r14
0x18005ebf7  mov     rcx, rsi
0x18005ebfa  call    cs:__imp_GdipDrawPath
0x18005ec00  nop
0x18005ec01  mov     rcx, [rsp+1C0h+var_150]
0x18005ec06  test    rcx, rcx
0x18005ec09  jz      short loc_18005EC11
0x18005ec0b  call    cs:__imp_GdipDeleteMatrix
0x18005ec11  lea     r11, [rsp+1C0h+var_20]
0x18005ec19  mov     rbx, [r11+30h]
0x18005ec1d  mov     rsi, [r11+38h]
0x18005ec21  movaps  xmm6, xmmword ptr [r11-10h]
0x18005ec26  movaps  xmm7, xmmword ptr [r11-20h]
0x18005ec2b  movaps  xmm8, xmmword ptr [r11-30h]
0x18005ec30  movaps  xmm9, xmmword ptr [r11-40h]
0x18005ec35  movaps  xmm10, xmmword ptr [r11-50h]
0x18005ec3a  movaps  xmm11, xmmword ptr [r11-60h]
0x18005ec3f  movaps  xmm12, xmmword ptr [r11-70h]
0x18005ec44  movaps  xmm13, xmmword ptr [r11-80h]
0x18005ec49  movaps  xmm15, xmmword ptr [r11-90h]
0x18005ec51  mov     rsp, r11
0x18005ec54  pop     r15
0x18005ec56  pop     r14
0x18005ec58  pop     r12
0x18005ec5a  pop     rdi
0x18005ec5b  pop     rbp
0x18005ec5c  retn
0x18005ec5d  mov     al, cs:byte_180520008
0x18005ec63  test    al, al
0x18005ec65  js      short loc_18005ECA5
0x18005ec67  setnz   al
0x18005ec6a  test    al, al
0x18005ec6c  jz      loc_18005EBE1
0x18005ec72  mov     [rbp+0C0h+arg_18], r12d
0x18005ec79  lea     rdx, [rbp+0C0h+arg_18]
0x18005ec80  mov     rcx, r14
0x18005ec83  call    cs:__imp_GdipGetPenUnit
0x18005ec89  mov     r9d, 2545510h
0x18005ec8f  mov     ecx, eax
0x18005ec91  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005ec96  cmp     [rbp+0C0h+arg_18], r12d
0x18005ec9d  setz    al
0x18005eca0  jmp     loc_18005EBE4
0x18005eca5  lea     rcx, byte_180520008
0x18005ecac  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x18005ecb2  jmp     short loc_18005EC6A
0x18005ecb4  xorps   xmm13, xmm13
0x18005ecb8  mov     [rbp+0C0h+arg_18], 0
0x18005ecc2  lea     rdx, [rbp+0C0h+arg_18]
0x18005ecc9  mov     rcx, r14
0x18005eccc  call    cs:__imp_GdipGetPenWidth
0x18005ecd2  mov     r9d, 2545511h
0x18005ecd8  mov     ecx, eax
0x18005ecda  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005ecdf  cmp     [rsp+1C0h+var_150], r12
0x18005ece4  jz      short loc_18005ECF4
0x18005ece6  xor     edx, edx
0x18005ece8  mov     ecx, 1E55E058h
0x18005eced  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18005ecf3  nop
0x18005ecf4  lea     rcx, [rsp+1C0h+var_150]
0x18005ecf9  call    cs:__imp_GdipCreateMatrix
0x18005ecff  mov     r9d, 2545512h
0x18005ed05  mov     ecx, eax
0x18005ed07  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005ed0c  mov     rdx, [rsp+1C0h+var_150]
0x18005ed11  mov     rcx, rsi
0x18005ed14  call    cs:__imp_GdipGetWorldTransform
0x18005ed1a  mov     r9d, 2545513h
0x18005ed20  mov     ecx, eax
0x18005ed22  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005ed27  mov     rbx, [rsp+1C0h+var_150]
0x18005ed2c  test    rbx, rbx
0x18005ed2f  jz      loc_18005EDF1
0x18005ed35  lea     rdx, [rbp+0C0h+var_118]
0x18005ed39  mov     rcx, rbx
0x18005ed3c  call    cs:__imp_GdipGetMatrixElements
0x18005ed42  mov     r9d, 2518650h
0x18005ed48  mov     ecx, eax
0x18005ed4a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005ed4f  movups  xmm1, [rbp+0C0h+var_118]
0x18005ed53  movsd   xmm0, [rbp+0C0h+var_108]
0x18005ed58  movsd   [rbp+0C0h+var_108], xmm0
0x18005ed5d  mov     rbx, [rsp+1C0h+var_150]
0x18005ed62  movaps  xmm0, xmm1
0x18005ed65  shufps  xmm0, xmm1, 0FFh
0x18005ed69  movaps  xmm2, xmm1
0x18005ed6c  shufps  xmm2, xmm1, 0AAh
0x18005ed70  movaps  xmm3, xmm1
0x18005ed73  shufps  xmm3, xmm1, 55h ; 'U'
0x18005ed77  xorps   xmm8, xmm8
0x18005ed7b  cvtss2sd xmm8, xmm1
0x18005ed80  xorps   xmm1, xmm1
0x18005ed83  cvtss2sd xmm1, xmm3
0x18005ed87  xorps   xmm6, xmm6
0x18005ed8a  cvtss2sd xmm6, xmm2
0x18005ed8e  cvtss2sd xmm0, xmm0
0x18005ed92  movss   xmm7, [rbp+0C0h+arg_18]
0x18005ed9a  cvtps2pd xmm7, xmm7
0x18005ed9d  mulsd   xmm0, xmm0
0x18005eda1  mulsd   xmm1, xmm1
0x18005eda5  addsd   xmm0, xmm1; X
0x18005eda9  call    sqrt_0
0x18005edae  movaps  xmm9, xmm0
0x18005edb2  mulsd   xmm9, xmm7
0x18005edb7  mulsd   xmm6, xmm6
0x18005edbb  mulsd   xmm8, xmm8
0x18005edc0  addsd   xmm6, xmm8
0x18005edc5  movaps  xmm0, xmm6; X
0x18005edc8  call    sqrt_0
0x18005edcd  mulsd   xmm0, xmm7
0x18005edd1  minsd   xmm9, xmm0
0x18005edd6  xorps   xmm0, xmm0
0x18005edd9  comisd  xmm0, xmm9
0x18005edde  jb      short loc_18005EE07
0x18005ede0  test    rbx, rbx
0x18005ede3  jz      loc_18005EC11
0x18005ede9  mov     rcx, rbx
0x18005edec  jmp     loc_18005EC0B
0x18005edf1  xorps   xmm3, xmm3
0x18005edf4  xorps   xmm2, xmm2
0x18005edf7  movss   xmm0, cs:__real@3f800000
0x18005edff  movaps  xmm1, xmm0
0x18005ee02  jmp     loc_18005ED77
0x18005ee07  movaps  xmm0, xmm9
0x18005ee0b  andps   xmm0, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x18005ee12  comisd  xmm0, qword ptr cs:__xmm@7ff00000000000007ff0000000000000
0x18005ee1a  setnb   al
0x18005ee1d  cmp     al, 1
0x18005ee1f  jz      loc_18005F1FC
0x18005ee25  movaps  xmm1, xmm9
0x18005ee29  subsd   xmm1, cs:__real@3ff0000000000000
0x18005ee31  movsd   xmm0, cs:__real@bcd203afa0000000
0x18005ee39  comisd  xmm0, xmm1
0x18005ee3d  setnbe  al
0x18005ee40  test    al, al
0x18005ee42  jz      loc_18005EBF1
0x18005ee48  movsd   xmm0, cs:__real@4000000000000000
0x18005ee50  divsd   xmm0, xmm9
0x18005ee55  cvtpd2ps xmm15, xmm0
0x18005ee5a  shufps  xmm15, xmm15, 0
0x18005ee5f  mov     [rbp+0C0h+var_140], 0
0x18005ee67  mov     [rsp+1C0h+var_148], 0
0x18005ee70  mov     r9, r14
0x18005ee73  mov     r8, rbx
0x18005ee76  lea     rdx, [rsp+1C0h+var_148]
0x18005ee7b  mov     rcx, r15
0x18005ee7e  call    cs:__imp_GdipGetPathWorldBounds
0x18005ee84  mov     r9d, 2545514h
0x18005ee8a  mov     ecx, eax
0x18005ee8c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005ee91  mov     [rbp+0C0h+arg_18], r12d
0x18005ee98  lea     rdx, [rbp+0C0h+arg_18]
0x18005ee9f  mov     rcx, rsi
0x18005eea2  call    cs:__imp_GdipIsVisibleClipEmpty
0x18005eea8  mov     r9d, 2545515h
0x18005eeae  mov     ecx, eax
0x18005eeb0  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005eeb5  cmp     [rbp+0C0h+arg_18], r12d
0x18005eebc  jnz     loc_18005EC01
0x18005eec2  mov     [rbp+0C0h+var_120], 0
0x18005eeca  mov     [rbp+0C0h+var_128], 0
0x18005eed2  lea     rdx, [rbp+0C0h+var_128]
0x18005eed6  mov     rcx, rsi
0x18005eed9  call    cs:__imp_GdipGetVisibleClipBounds
0x18005eedf  mov     r9d, 2545516h
0x18005eee5  mov     ecx, eax
0x18005eee7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005eeec  movss   xmm1, dword ptr [rbp+0C0h+var_128]
0x18005eef1  movss   xmm12, dword ptr [rsp+1C0h+var_148]
0x18005eef8  movss   xmm9, dword ptr [rbp+0C0h+var_140]
0x18005eefe  comiss  xmm1, xmm12
0x18005ef02  jbe     short loc_18005EF21
0x18005ef04  movaps  xmm0, xmm1
0x18005ef07  subss   xmm0, xmm12
0x18005ef0c  subss   xmm9, xmm0
0x18005ef11  movss   dword ptr [rbp+0C0h+var_140], xmm9
0x18005ef17  movaps  xmm12, xmm1
0x18005ef1b  movss   dword ptr [rsp+1C0h+var_148], xmm1
0x18005ef21  movss   xmm2, dword ptr [rbp+0C0h+var_128+4]
0x18005ef26  movss   xmm11, dword ptr [rsp+1C0h+var_148+4]
0x18005ef2d  movss   xmm10, dword ptr [rbp+0C0h+var_140+4]
0x18005ef33  comiss  xmm2, xmm11
0x18005ef37  jbe     short loc_18005EF56
0x18005ef39  movaps  xmm0, xmm2
0x18005ef3c  subss   xmm0, xmm11
0x18005ef41  subss   xmm10, xmm0
0x18005ef46  movss   dword ptr [rbp+0C0h+var_140+4], xmm10
0x18005ef4c  movaps  xmm11, xmm2
0x18005ef50  movss   dword ptr [rsp+1C0h+var_148+4], xmm2
0x18005ef56  movss   xmm3, dword ptr [rbp+0C0h+var_120]
0x18005ef5b  addss   xmm3, xmm1
0x18005ef5f  movaps  xmm0, xmm9
0x18005ef63  addss   xmm0, xmm12
0x18005ef68  comiss  xmm0, xmm3
0x18005ef6b  jbe     short loc_18005EF7C
0x18005ef6d  movaps  xmm9, xmm3
0x18005ef71  subss   xmm9, xmm12
0x18005ef76  movss   dword ptr [rbp+0C0h+var_140], xmm9
0x18005ef7c  movss   xmm1, dword ptr [rbp+0C0h+var_120+4]
0x18005ef81  addss   xmm1, xmm2
0x18005ef85  movaps  xmm0, xmm10
0x18005ef89  addss   xmm0, xmm11
0x18005ef8e  comiss  xmm0, xmm1
0x18005ef91  jbe     short loc_18005EFA2
0x18005ef93  movaps  xmm10, xmm1
0x18005ef97  subss   xmm10, xmm11
0x18005ef9c  movss   dword ptr [rbp+0C0h+var_140+4], xmm10
0x18005efa2  comiss  xmm13, xmm9
0x18005efa6  jnb     loc_18005EC01
0x18005efac  comiss  xmm13, xmm10
0x18005efb0  jnb     loc_18005EC01
0x18005efb6  mulss   xmm10, xmm15
0x18005efbb  mulss   xmm9, xmm15
0x18005efc0  mulss   xmm11, xmm15
0x18005efc5  mulss   xmm12, xmm15
0x18005efca  movaps  xmm0, xmm9
0x18005efce  addss   xmm0, cs:__real@3f800000; X
0x18005efd6  call    ceilf_0
0x18005efdb  cvttss2si edi, xmm0
0x18005efdf  movaps  xmm0, xmm10
0x18005efe3  addss   xmm0, cs:__real@3f800000; X
0x18005efeb  call    ceilf_0
0x18005eff0  cvttss2si ebx, xmm0
0x18005eff4  movaps  xmm0, xmm11
0x18005eff8  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18005efff  subss   xmm0, cs:__real@3d4ccccd; X
0x18005f007  call    ceilf_0
0x18005f00c  movaps  xmm8, xmm0
0x18005f010  movaps  xmm0, xmm12
0x18005f014  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18005f01b  subss   xmm0, cs:__real@3d4ccccd; X
0x18005f023  call    ceilf_0
0x18005f028  movaps  xmm6, xmm0
0x18005f02b  movaps  xmm7, xmm0
0x18005f02e  addss   xmm7, xmm12
0x18005f033  addss   xmm11, xmm8
0x18005f038  mov     [rbp+0C0h+var_130], r12
0x18005f03c  lea     rax, [rbp+0C0h+var_130]
0x18005f040  mov     qword ptr [rsp+1C0h+var_198], rax
0x18005f045  mov     [rsp+1C0h+var_1A0], r12
0x18005f04a  mov     r9d, 26200Ah
0x18005f050  xor     r8d, r8d
0x18005f053  mov     edx, ebx
0x18005f055  mov     ecx, edi
0x18005f057  call    cs:__imp_GdipCreateBitmapFromScan0
0x18005f05d  mov     r9d, 2545517h
0x18005f063  mov     ecx, eax
0x18005f065  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005f06a  mov     [rbp+0C0h+var_138], r12
0x18005f06e  lea     rdx, [rbp+0C0h+var_138]
0x18005f072  mov     rcx, [rbp+0C0h+var_130]
0x18005f076  call    cs:__imp_GdipGetImageGraphicsContext
0x18005f07c  mov     r9d, 2545518h
0x18005f082  mov     ecx, eax
0x18005f084  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005f089  mov     ebx, 2
0x18005f08e  mov     edx, ebx
0x18005f090  mov     rcx, [rbp+0C0h+var_138]
0x18005f094  call    cs:__imp_GdipSetPageUnit
0x18005f09a  mov     r9d, 2545519h
0x18005f0a0  mov     ecx, eax
0x18005f0a2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18005f0a7  lea     rdx, [rbp+0C0h+var_D0]
0x18005f0ab  lea     rcx, [rsp+1C0h+var_150]
0x18005f0b0  call    ?GetMatrix@GpMatrixHolder@Gfx@@QEBA?AU?$TAffine3x3@M@Math@@XZ; Gfx::GpMatrixHolder::GetMatrix(void)
0x18005f0b5  movups  xmm3, xmmword ptr [rax]
0x18005f0b8  mulps   xmm3, xmm15
0x18005f0bc  movups  [rbp+0C0h+var_118], xmm3
0x18005f0c0  movaps  xmm0, xmm15
  ... truncated ...
```
