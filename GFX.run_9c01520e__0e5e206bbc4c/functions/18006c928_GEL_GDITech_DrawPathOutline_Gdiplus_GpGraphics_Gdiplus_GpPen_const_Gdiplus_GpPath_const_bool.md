# GEL::GDITech::DrawPathOutline(Gdiplus::GpGraphics &,Gdiplus::GpPen const *,Gdiplus::GpPath const *,bool)

- ea: `0x18006c928`
- end: `0x18006cfbe`
- name: `?DrawPathOutline@GDITech@GEL@@CAXAEAVGpGraphics@Gdiplus@@PEBVGpPen@4@PEBVGpPath@4@_N@Z`
- size: `1686`
- prototype: `void __fastcall(struct Gdiplus::GpGraphics *, const struct Gdiplus::GpPen *, const struct Gdiplus::GpPath *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18006c5c0`

## callees

- `0x180050b64`
- `0x18006c928`
- `0x18007f398`
- `0x18007f754`
- `0x1800815c0`
- `0x1800bd870`
- `0x1800be670`
- `0x1800be6d0`
- `0x1800be730`
- `0x18015d388`
- `0x18017ccf4`
- `0x180207d46`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006ca67`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006ca67`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18006c9a2`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18006c9a2`
- `gdiplus!GdipGetPenUnit` at `0x18006ca7f`
- `gdiplus!GdipGetPenUnit` at `0x18006ca7f`
- `gdiplus!GdipGetPathWorldBounds` at `0x18006cc2b`
- `gdiplus!GdipGetPathWorldBounds` at `0x18006cc2b`
- `gdiplus!GdipIsVisibleClipEmpty` at `0x18006cc4f`
- `gdiplus!GdipIsVisibleClipEmpty` at `0x18006cc4f`
- `gdiplus!GdipGetVisibleClipBounds` at `0x18006cc86`
- `gdiplus!GdipGetVisibleClipBounds` at `0x18006cc86`
- `gdiplus!GdipDrawPath` at `0x18006c9ca`
- `gdiplus!GdipDrawPath` at `0x18006ced5`
- `gdiplus!GdipDrawPath` at `0x18006c9ca`
- `gdiplus!GdipDrawPath` at `0x18006ced5`
- `gdiplus!GdipGetWorldTransform` at `0x18006cac1`
- `gdiplus!GdipGetWorldTransform` at `0x18006cac1`
- `gdiplus!GdipSetWorldTransform` at `0x18006cea7`
- `gdiplus!GdipSetWorldTransform` at `0x18006cea7`
- `gdiplus!GdipGetPenWidth` at `0x18006ca45`
- `gdiplus!GdipGetPenWidth` at `0x18006ca45`
- `gdiplus!GdipGetMatrixElements` at `0x18006cae9`
- `gdiplus!GdipGetMatrixElements` at `0x18006cae9`
- `gdiplus!GdipCreateMatrix` at `0x18006caa6`
- `gdiplus!GdipCreateMatrix` at `0x18006caa6`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18006ce23`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18006ce23`
- `gdiplus!GdipDeleteMatrix` at `0x18006c9db`
- `gdiplus!GdipDeleteMatrix` at `0x18006c9db`
- `gdiplus!GdipDrawImageRectRect` at `0x18006cf6b`
- `gdiplus!GdipDrawImageRectRect` at `0x18006cf6b`
- `gdiplus!GdipSetPageUnit` at `0x18006ce41`
- `gdiplus!GdipSetPageUnit` at `0x18006ce41`
- `gdiplus!GdipDeleteGraphics` at `0x18006ceee`
- `gdiplus!GdipDeleteGraphics` at `0x18006ceee`
- `gdiplus!GdipDisposeImage` at `0x18006cfa0`
- `gdiplus!GdipDisposeImage` at `0x18006cfa0`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18006ce04`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18006ce04`

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
  unsigned int PenWidth; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int PenUnit; // eax
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

  if ( !a4
    && (byte_180524050 >= 0
      ? (v7 = byte_180524050 != 0)
      : (v7 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180524050)),
        v7) )
  {
    v87 = 0.0;
    PenUnit = GdipGetPenUnit(a2, &v87);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(PenUnit, v13, v14, 39081232);
    v8 = LODWORD(v87) == 0;
  }
  else
  {
    v8 = 0;
  }
  v73 = 0;
  if ( !v8 )
    goto LABEL_8;
  v87 = 0.0;
  PenWidth = GdipGetPenWidth(a2, &v87);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(PenWidth, v10, v11, 39081233);
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
LABEL_9:
      if ( !v73 )
        return;
      goto LABEL_10;
    }
LABEL_8:
    GdipDrawPath(a1, a2, a3);
    goto LABEL_9;
  }
  if ( v21 )
LABEL_10:
    GdipDeleteMatrix();
}

```

## disassembly

```asm
0x18006c928  mov     rax, rsp
0x18006c92b  mov     [rax+8], rbx
0x18006c92f  mov     [rax+10h], rsi
0x18006c933  push    rbp
0x18006c934  push    rdi
0x18006c935  push    r12
0x18006c937  push    r14
0x18006c939  push    r15
0x18006c93b  lea     rbp, [rax-0C8h]
0x18006c942  sub     rsp, 1A0h
0x18006c949  movaps  xmmword ptr [rax-38h], xmm6
0x18006c94d  movaps  xmmword ptr [rax-48h], xmm7
0x18006c951  movaps  xmmword ptr [rax-58h], xmm8
0x18006c956  movaps  xmmword ptr [rax-68h], xmm9
0x18006c95b  movaps  xmmword ptr [rax-78h], xmm10
0x18006c960  movaps  xmmword ptr [rax-88h], xmm11
0x18006c968  movaps  xmmword ptr [rax-98h], xmm12
0x18006c970  movaps  xmmword ptr [rax-0A8h], xmm13
0x18006c978  movaps  xmmword ptr [rax-0B8h], xmm15
0x18006c980  mov     r15, r8
0x18006c983  mov     r14, rdx
0x18006c986  mov     rsi, rcx
0x18006c989  xor     r12d, r12d
0x18006c98c  test    r9b, r9b
0x18006c98f  jnz     short loc_18006C9B5
0x18006c991  mov     al, cs:byte_180524050
0x18006c997  test    al, al
0x18006c999  jns     short loc_18006C9AA
0x18006c99b  lea     rcx, byte_180524050
0x18006c9a2  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x18006c9a8  jmp     short loc_18006C9AD
0x18006c9aa  setnz   al
0x18006c9ad  test    al, al
0x18006c9af  jnz     loc_18006CA6E
0x18006c9b5  mov     al, r12b
0x18006c9b8  mov     [rsp+1C0h+var_150], r12
0x18006c9bd  test    al, al
0x18006c9bf  jnz     short loc_18006CA2D
0x18006c9c1  mov     r8, r15
0x18006c9c4  mov     rdx, r14
0x18006c9c7  mov     rcx, rsi
0x18006c9ca  call    cs:__imp_GdipDrawPath
0x18006c9d0  nop
0x18006c9d1  mov     rcx, [rsp+1C0h+var_150]
0x18006c9d6  test    rcx, rcx
0x18006c9d9  jz      short loc_18006C9E1
0x18006c9db  call    cs:__imp_GdipDeleteMatrix
0x18006c9e1  lea     r11, [rsp+1C0h+var_20]
0x18006c9e9  mov     rbx, [r11+30h]
0x18006c9ed  mov     rsi, [r11+38h]
0x18006c9f1  movaps  xmm6, xmmword ptr [r11-10h]
0x18006c9f6  movaps  xmm7, xmmword ptr [r11-20h]
0x18006c9fb  movaps  xmm8, xmmword ptr [r11-30h]
0x18006ca00  movaps  xmm9, xmmword ptr [r11-40h]
0x18006ca05  movaps  xmm10, xmmword ptr [r11-50h]
0x18006ca0a  movaps  xmm11, xmmword ptr [r11-60h]
0x18006ca0f  movaps  xmm12, xmmword ptr [r11-70h]
0x18006ca14  movaps  xmm13, xmmword ptr [r11-80h]
0x18006ca19  movaps  xmm15, xmmword ptr [r11-90h]
0x18006ca21  mov     rsp, r11
0x18006ca24  pop     r15
0x18006ca26  pop     r14
0x18006ca28  pop     r12
0x18006ca2a  pop     rdi
0x18006ca2b  pop     rbp
0x18006ca2c  retn
0x18006ca2d  xorps   xmm13, xmm13
0x18006ca31  mov     [rbp+0C0h+arg_18], 0
0x18006ca3b  lea     rdx, [rbp+0C0h+arg_18]
0x18006ca42  mov     rcx, r14
0x18006ca45  call    cs:__imp_GdipGetPenWidth
0x18006ca4b  mov     r9d, 2545511h
0x18006ca51  mov     ecx, eax
0x18006ca53  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006ca58  cmp     [rsp+1C0h+var_150], r12
0x18006ca5d  jz      short loc_18006CAA1
0x18006ca5f  nop
0x18006ca60  xor     edx, edx
0x18006ca62  mov     ecx, 1E55E058h
0x18006ca67  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006ca6d  nop
0x18006ca6e  mov     [rbp+0C0h+arg_18], r12d
0x18006ca75  lea     rdx, [rbp+0C0h+arg_18]
0x18006ca7c  mov     rcx, r14
0x18006ca7f  call    cs:__imp_GdipGetPenUnit
0x18006ca85  mov     r9d, 2545510h
0x18006ca8b  mov     ecx, eax
0x18006ca8d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006ca92  cmp     [rbp+0C0h+arg_18], r12d
0x18006ca99  setz    al
0x18006ca9c  jmp     loc_18006C9B8
0x18006caa1  lea     rcx, [rsp+1C0h+var_150]
0x18006caa6  call    cs:__imp_GdipCreateMatrix
0x18006caac  mov     r9d, 2545512h
0x18006cab2  mov     ecx, eax
0x18006cab4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006cab9  mov     rdx, [rsp+1C0h+var_150]
0x18006cabe  mov     rcx, rsi
0x18006cac1  call    cs:__imp_GdipGetWorldTransform
0x18006cac7  mov     r9d, 2545513h
0x18006cacd  mov     ecx, eax
0x18006cacf  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006cad4  mov     rbx, [rsp+1C0h+var_150]
0x18006cad9  test    rbx, rbx
0x18006cadc  jz      loc_18006CB9E
0x18006cae2  lea     rdx, [rbp+0C0h+var_118]
0x18006cae6  mov     rcx, rbx
0x18006cae9  call    cs:__imp_GdipGetMatrixElements
0x18006caef  mov     r9d, 2518650h
0x18006caf5  mov     ecx, eax
0x18006caf7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006cafc  movups  xmm1, [rbp+0C0h+var_118]
0x18006cb00  movsd   xmm0, [rbp+0C0h+var_108]
0x18006cb05  movsd   [rbp+0C0h+var_108], xmm0
0x18006cb0a  mov     rbx, [rsp+1C0h+var_150]
0x18006cb0f  movaps  xmm0, xmm1
0x18006cb12  shufps  xmm0, xmm1, 0FFh
0x18006cb16  movaps  xmm2, xmm1
0x18006cb19  shufps  xmm2, xmm1, 0AAh
0x18006cb1d  movaps  xmm3, xmm1
0x18006cb20  shufps  xmm3, xmm1, 55h ; 'U'
0x18006cb24  xorps   xmm8, xmm8
0x18006cb28  cvtss2sd xmm8, xmm1
0x18006cb2d  xorps   xmm1, xmm1
0x18006cb30  cvtss2sd xmm1, xmm3
0x18006cb34  xorps   xmm6, xmm6
0x18006cb37  cvtss2sd xmm6, xmm2
0x18006cb3b  cvtss2sd xmm0, xmm0
0x18006cb3f  movss   xmm7, [rbp+0C0h+arg_18]
0x18006cb47  cvtps2pd xmm7, xmm7
0x18006cb4a  mulsd   xmm0, xmm0
0x18006cb4e  mulsd   xmm1, xmm1
0x18006cb52  addsd   xmm0, xmm1; X
0x18006cb56  call    sqrt_0
0x18006cb5b  movaps  xmm9, xmm0
0x18006cb5f  mulsd   xmm9, xmm7
0x18006cb64  mulsd   xmm6, xmm6
0x18006cb68  mulsd   xmm8, xmm8
0x18006cb6d  addsd   xmm6, xmm8
0x18006cb72  movaps  xmm0, xmm6; X
0x18006cb75  call    sqrt_0
0x18006cb7a  mulsd   xmm0, xmm7
0x18006cb7e  minsd   xmm9, xmm0
0x18006cb83  xorps   xmm0, xmm0
0x18006cb86  comisd  xmm0, xmm9
0x18006cb8b  jb      short loc_18006CBB4
0x18006cb8d  test    rbx, rbx
0x18006cb90  jz      loc_18006C9E1
0x18006cb96  mov     rcx, rbx
0x18006cb99  jmp     loc_18006C9DB
0x18006cb9e  xorps   xmm3, xmm3
0x18006cba1  xorps   xmm2, xmm2
0x18006cba4  movss   xmm0, cs:__real@3f800000
0x18006cbac  movaps  xmm1, xmm0
0x18006cbaf  jmp     loc_18006CB24
0x18006cbb4  movaps  xmm0, xmm9
0x18006cbb8  andps   xmm0, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x18006cbbf  comisd  xmm0, qword ptr cs:__xmm@7ff00000000000007ff0000000000000
0x18006cbc7  setnb   al
0x18006cbca  cmp     al, 1
0x18006cbcc  jz      loc_18006CFAB
0x18006cbd2  movaps  xmm1, xmm9
0x18006cbd6  subsd   xmm1, cs:__real@3ff0000000000000
0x18006cbde  movsd   xmm0, cs:__real@bcd203afa0000000
0x18006cbe6  comisd  xmm0, xmm1
0x18006cbea  setnbe  al
0x18006cbed  test    al, al
0x18006cbef  jz      loc_18006C9C1
0x18006cbf5  movsd   xmm0, cs:__real@4000000000000000
0x18006cbfd  divsd   xmm0, xmm9
0x18006cc02  cvtpd2ps xmm15, xmm0
0x18006cc07  shufps  xmm15, xmm15, 0
0x18006cc0c  mov     [rbp+0C0h+var_140], 0
0x18006cc14  mov     [rsp+1C0h+var_148], 0
0x18006cc1d  mov     r9, r14
0x18006cc20  mov     r8, rbx
0x18006cc23  lea     rdx, [rsp+1C0h+var_148]
0x18006cc28  mov     rcx, r15
0x18006cc2b  call    cs:__imp_GdipGetPathWorldBounds
0x18006cc31  mov     r9d, 2545514h
0x18006cc37  mov     ecx, eax
0x18006cc39  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006cc3e  mov     [rbp+0C0h+arg_18], r12d
0x18006cc45  lea     rdx, [rbp+0C0h+arg_18]
0x18006cc4c  mov     rcx, rsi
0x18006cc4f  call    cs:__imp_GdipIsVisibleClipEmpty
0x18006cc55  mov     r9d, 2545515h
0x18006cc5b  mov     ecx, eax
0x18006cc5d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006cc62  cmp     [rbp+0C0h+arg_18], r12d
0x18006cc69  jnz     loc_18006C9D1
0x18006cc6f  mov     [rbp+0C0h+var_120], 0
0x18006cc77  mov     [rbp+0C0h+var_128], 0
0x18006cc7f  lea     rdx, [rbp+0C0h+var_128]
0x18006cc83  mov     rcx, rsi
0x18006cc86  call    cs:__imp_GdipGetVisibleClipBounds
0x18006cc8c  mov     r9d, 2545516h
0x18006cc92  mov     ecx, eax
0x18006cc94  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006cc99  movss   xmm1, dword ptr [rbp+0C0h+var_128]
0x18006cc9e  movss   xmm12, dword ptr [rsp+1C0h+var_148]
0x18006cca5  movss   xmm9, dword ptr [rbp+0C0h+var_140]
0x18006ccab  comiss  xmm1, xmm12
0x18006ccaf  jbe     short loc_18006CCCE
0x18006ccb1  movaps  xmm0, xmm1
0x18006ccb4  subss   xmm0, xmm12
0x18006ccb9  subss   xmm9, xmm0
0x18006ccbe  movss   dword ptr [rbp+0C0h+var_140], xmm9
0x18006ccc4  movaps  xmm12, xmm1
0x18006ccc8  movss   dword ptr [rsp+1C0h+var_148], xmm1
0x18006ccce  movss   xmm2, dword ptr [rbp+0C0h+var_128+4]
0x18006ccd3  movss   xmm11, dword ptr [rsp+1C0h+var_148+4]
0x18006ccda  movss   xmm10, dword ptr [rbp+0C0h+var_140+4]
0x18006cce0  comiss  xmm2, xmm11
0x18006cce4  jbe     short loc_18006CD03
0x18006cce6  movaps  xmm0, xmm2
0x18006cce9  subss   xmm0, xmm11
0x18006ccee  subss   xmm10, xmm0
0x18006ccf3  movss   dword ptr [rbp+0C0h+var_140+4], xmm10
0x18006ccf9  movaps  xmm11, xmm2
0x18006ccfd  movss   dword ptr [rsp+1C0h+var_148+4], xmm2
0x18006cd03  movss   xmm3, dword ptr [rbp+0C0h+var_120]
0x18006cd08  addss   xmm3, xmm1
0x18006cd0c  movaps  xmm0, xmm9
0x18006cd10  addss   xmm0, xmm12
0x18006cd15  comiss  xmm0, xmm3
0x18006cd18  jbe     short loc_18006CD29
0x18006cd1a  movaps  xmm9, xmm3
0x18006cd1e  subss   xmm9, xmm12
0x18006cd23  movss   dword ptr [rbp+0C0h+var_140], xmm9
0x18006cd29  movss   xmm1, dword ptr [rbp+0C0h+var_120+4]
0x18006cd2e  addss   xmm1, xmm2
0x18006cd32  movaps  xmm0, xmm10
0x18006cd36  addss   xmm0, xmm11
0x18006cd3b  comiss  xmm0, xmm1
0x18006cd3e  jbe     short loc_18006CD4F
0x18006cd40  movaps  xmm10, xmm1
0x18006cd44  subss   xmm10, xmm11
0x18006cd49  movss   dword ptr [rbp+0C0h+var_140+4], xmm10
0x18006cd4f  comiss  xmm13, xmm9
0x18006cd53  jnb     loc_18006C9D1
0x18006cd59  comiss  xmm13, xmm10
0x18006cd5d  jnb     loc_18006C9D1
0x18006cd63  mulss   xmm10, xmm15
0x18006cd68  mulss   xmm9, xmm15
0x18006cd6d  mulss   xmm11, xmm15
0x18006cd72  mulss   xmm12, xmm15
0x18006cd77  movaps  xmm0, xmm9
0x18006cd7b  addss   xmm0, cs:__real@3f800000; X
0x18006cd83  call    ceilf_0
0x18006cd88  cvttss2si edi, xmm0
0x18006cd8c  movaps  xmm0, xmm10
0x18006cd90  addss   xmm0, cs:__real@3f800000; X
0x18006cd98  call    ceilf_0
0x18006cd9d  cvttss2si ebx, xmm0
0x18006cda1  movaps  xmm0, xmm11
0x18006cda5  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18006cdac  subss   xmm0, cs:__real@3d4ccccd; X
0x18006cdb4  call    ceilf_0
0x18006cdb9  movaps  xmm8, xmm0
0x18006cdbd  movaps  xmm0, xmm12
0x18006cdc1  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18006cdc8  subss   xmm0, cs:__real@3d4ccccd; X
0x18006cdd0  call    ceilf_0
0x18006cdd5  movaps  xmm6, xmm0
0x18006cdd8  movaps  xmm7, xmm0
0x18006cddb  addss   xmm7, xmm12
0x18006cde0  addss   xmm11, xmm8
0x18006cde5  mov     [rbp+0C0h+var_130], r12
0x18006cde9  lea     rax, [rbp+0C0h+var_130]
0x18006cded  mov     qword ptr [rsp+1C0h+var_198], rax
0x18006cdf2  mov     [rsp+1C0h+var_1A0], r12
0x18006cdf7  mov     r9d, 26200Ah
0x18006cdfd  xor     r8d, r8d
0x18006ce00  mov     edx, ebx
0x18006ce02  mov     ecx, edi
0x18006ce04  call    cs:__imp_GdipCreateBitmapFromScan0
0x18006ce0a  mov     r9d, 2545517h
0x18006ce10  mov     ecx, eax
0x18006ce12  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006ce17  mov     [rbp+0C0h+var_138], r12
0x18006ce1b  lea     rdx, [rbp+0C0h+var_138]
0x18006ce1f  mov     rcx, [rbp+0C0h+var_130]
0x18006ce23  call    cs:__imp_GdipGetImageGraphicsContext
0x18006ce29  mov     r9d, 2545518h
0x18006ce2f  mov     ecx, eax
0x18006ce31  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006ce36  mov     ebx, 2
0x18006ce3b  mov     edx, ebx
0x18006ce3d  mov     rcx, [rbp+0C0h+var_138]
0x18006ce41  call    cs:__imp_GdipSetPageUnit
0x18006ce47  mov     r9d, 2545519h
0x18006ce4d  mov     ecx, eax
0x18006ce4f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006ce54  lea     rdx, [rbp+0C0h+var_D0]
0x18006ce58  lea     rcx, [rsp+1C0h+var_150]
0x18006ce5d  call    ?GetMatrix@GpMatrixHolder@Gfx@@QEBA?AU?$TAffine3x3@M@Math@@XZ; Gfx::GpMatrixHolder::GetMatrix(void)
0x18006ce62  movups  xmm3, xmmword ptr [rax]
0x18006ce65  mulps   xmm3, xmm15
0x18006ce69  movups  [rbp+0C0h+var_118], xmm3
  ... truncated ...
```
