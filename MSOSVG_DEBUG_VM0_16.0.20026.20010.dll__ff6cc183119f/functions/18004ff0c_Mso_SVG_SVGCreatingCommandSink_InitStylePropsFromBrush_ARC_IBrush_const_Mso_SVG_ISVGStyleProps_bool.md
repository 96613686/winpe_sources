# Mso::SVG::SVGCreatingCommandSink::InitStylePropsFromBrush(ARC::IBrush const &,Mso::SVG::ISVGStyleProps &,bool)

- ea: `0x18004ff0c`
- end: `0x180050984`
- name: `?InitStylePropsFromBrush@SVGCreatingCommandSink@SVG@Mso@@AEAAXAEBUIBrush@ARC@@AEAUISVGStyleProps@23@_N@Z`
- size: `2680`
- prototype: `void __fastcall(Mso::SVG::SVGCreatingCommandSink *__hidden this, const struct ARC::IBrush *, struct Mso::SVG::ISVGStyleProps *, bool)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180052d9c`
- `0x180052f50`
- `0x180053644`
- `0x1800538d0`

## callees

- `0x180007310`
- `0x180023800`
- `0x18004f6e0`
- `0x18004ff0c`
- `0x180054bec`
- `0x180058e80`
- `0x180059c74`
- `0x18005a580`
- `0x18013f6f0`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800504ec`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800504ec`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180050528`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180050528`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800504fa`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800504fa`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800502e1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050654`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800502e1`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050654`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x18005019f`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x18005019f`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x180050318`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x180050318`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800502b0`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x180050623`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800502b0`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x180050623`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x18005037c`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x18005037c`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x18005068e`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x18005068e`

## string_xrefs

- `0x18005096d`: `Unsupported radial gradient: the focus is outside the gradient area.`
- `0x18005094c`: `Unsupported gradient type: likely Path Gradient.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Mso::SVG::SVGCreatingCommandSink::InitStylePropsFromBrush(
        Mso::SVG::SVGCreatingCommandSink *this,
        const struct ARC::IBrush *a2,
        struct Mso::SVG::ISVGStyleProps *a3,
        char a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  float *v11; // rax
  float v12; // xmm6_4
  float v13; // xmm10_4
  float *v14; // rax
  float v15; // xmm8_4
  float v16; // xmm9_4
  float *v17; // rax
  float v18; // xmm7_4
  float v19; // xmm10_4
  float *v20; // rax
  float v21; // xmm6_4
  float v22; // xmm9_4
  __int64 v23; // rbx
  unsigned __int64 v24; // rsi
  __int64 v25; // rbx
  unsigned int v26; // r9d
  unsigned __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  float v30; // xmm9_4
  float v31; // xmm10_4
  float v32; // xmm8_4
  float v33; // xmm7_4
  float v34; // xmm6_4
  float v35; // xmm6_4
  bool v36; // cf
  bool v37; // zf
  __int64 CurrentGeometryToShapeTransform; // rax
  __int64 v39; // rax
  unsigned int v40; // r8d
  void *v41; // rdx
  Mso::Memory *v42; // rbx
  __int64 i; // rax
  __int64 v44; // rbx
  unsigned __int64 v45; // rsi
  __int64 v46; // rbx
  unsigned int v47; // r9d
  unsigned __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 *v51; // rsi
  __int64 v52; // rax
  float *v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rbx
  void (__fastcall *v59)(__int64, _QWORD, _QWORD); // rsi
  unsigned int v60; // edi
  unsigned int v61; // eax
  __int64 v62; // rax
  void (__fastcall *v63)(struct Mso::SVG::ISVGStyleProps *); // rdi
  __m128i si128; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v65; // [rsp+58h] [rbp-B0h]
  __int64 v66; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v67; // [rsp+70h] [rbp-98h] BYREF
  __int64 v68; // [rsp+78h] [rbp-90h] BYREF
  __int64 v69; // [rsp+80h] [rbp-88h] BYREF
  __m128i v70; // [rsp+88h] [rbp-80h] BYREF
  __int64 v71; // [rsp+98h] [rbp-70h]
  __m128i v72; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-50h]
  _BYTE v74[55]; // [rsp+C8h] [rbp-40h] BYREF
  bool v75; // [rsp+FFh] [rbp-9h]
  int v76; // [rsp+100h] [rbp-8h]
  double v77; // [rsp+108h] [rbp+0h]
  double v78; // [rsp+110h] [rbp+8h]
  double v79; // [rsp+118h] [rbp+10h]
  double v80; // [rsp+120h] [rbp+18h]
  double v81; // [rsp+128h] [rbp+20h]
  double v82; // [rsp+130h] [rbp+28h]
  Mso::Memory *v83; // [rsp+138h] [rbp+30h]
  __m64 v84[3]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v85[104]; // [rsp+160h] [rbp+58h] BYREF
  __int64 v86; // [rsp+1F0h] [rbp+E8h] BYREF

  v8 = *(_QWORD *)a2;
  v68 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IBrush *, GUID *, __int64 *))(v8 + 16))(
         a2,
         &GUID_d14199d2_d661_4a45_ab06_99af4f715717,
         &v68) )
  {
    (*(void (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v68 + 96LL))(v68, &si128);
    v9 = *(_QWORD *)a3;
    v70 = si128;
    if ( a4 )
      (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, __m128i *))(v9 + 32))(a3, &v70);
    else
      (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, __m128i *))(v9 + 288))(a3, &v70);
    goto LABEL_5;
  }
  v10 = *(_QWORD *)a2;
  v67 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(const struct ARC::IBrush *, GUID *, __int64 *))(v10 + 16))(
          a2,
          &GUID_db6d09de_0055_4a4f_9077_0a24572f6b4a,
          &v67) )
  {
    v29 = *(_QWORD *)a2;
    v66 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IBrush *, GUID *, __int64 *))(v29 + 16))(
           a2,
           &GUID_934f0936_4b9a_4135_88f0_a32291a6393b,
           &v66) )
    {
      *((_BYTE *)this + 320) = 1;
      GEL::RadialGradientInfo::RadialGradientInfo((GEL::RadialGradientInfo *)v74);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 112LL))(v66, &v86);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 128LL))(v66, &v69);
      (*(void (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v66 + 120LL))(v66, &v70);
      v30 = *((float *)&v86 + 1) + *((float *)&v69 + 1);
      v31 = *(float *)&v86 + *(float *)&v69;
      v32 = *(float *)&v70.m128i_i32[1];
      v33 = *(float *)v70.m128i_i32;
      v34 = (float)((float)(*((float *)&v69 + 1) * *((float *)&v69 + 1)) / (float)(v32 * v32))
          + (float)((float)(*(float *)&v69 * *(float *)&v69) / (float)(v33 * v33));
      if ( fdclass_0(v34) == 1 )
      {
        v36 = v34 < 1.0;
        v37 = v34 == 1.0;
      }
      else
      {
        v35 = v34 - 1.0;
        v36 = v35 < 0.000001;
        v37 = v35 == 0.000001;
      }
      if ( !v36 && !v37 )
      {
        *((_BYTE *)this + 321) = 1;
        OExceptionLog::ThrowTag(38027930, 55, L"Unsupported radial gradient: the focus is outside the gradient area.");
      }
      v77 = *(float *)&v86;
      v78 = *((float *)&v86 + 1);
      v79 = v31;
      v80 = v30;
      v81 = COERCE_FLOAT(LODWORD(v33) & _xmm);
      v82 = COERCE_FLOAT(LODWORD(v32) & _xmm);
      (*(void (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v66 + 72LL))(v66, &v72);
      CurrentGeometryToShapeTransform = Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(this, v84);
      v39 = Math::operator*<float,float,float>(v85, &v72, CurrentGeometryToShapeTransform);
      v72 = *(__m128i *)v39;
      v73 = *(_QWORD *)(v39 + 16);
      v42 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)0x30, 0, v40);
      if ( !v42 )
      {
        ThrowOOM();
        __debugbreak();
      }
      for ( i = 0; i < 6; ++i )
        *((double *)v42 + i) = *(float *)&v72.m128i_i32[i];
      if ( v83 != v42 )
      {
        if ( v83 )
          Mso::Memory::Free(v83, v41);
        v83 = v42;
      }
      v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 136LL))(v66);
      v76 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 64LL))(v44);
      v75 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v44 + 72LL))(v44) == 1;
      v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 56LL))(v44);
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 48LL))(v44);
      std::vector<GEL::GradientStop>::vector<GEL::GradientStop>(&si128, v45);
      v47 = 0;
      if ( v45 )
      {
        v48 = 0;
        do
        {
          if ( v48 >= 0xCCCCCCCCCCCCCCCDuLL * ((si128.m128i_i64[1] - si128.m128i_i64[0]) >> 2)
            || (*(_OWORD *)(si128.m128i_i64[0] + 20 * v48) = *(_OWORD *)(v46 + 20 * v48 + 4),
                v48 >= 0xCCCCCCCCCCCCCCCDuLL * ((si128.m128i_i64[1] - si128.m128i_i64[0]) >> 2)) )
          {
            _invoke_watson(0, 0, 0, 0, 0);
          }
          *(_DWORD *)(si128.m128i_i64[0] + 20 * v48 + 16) = *(_DWORD *)(v46 + 20 * v48);
          v48 = ++v47;
        }
        while ( v47 < v45 );
      }
      GEL::GradientInfo::SetShadeColors(
        (GEL::GradientInfo *)v74,
        (const struct GEL::GradientStop *)si128.m128i_i64[0],
        v45);
      v49 = *(_QWORD *)a3;
      if ( a4 )
        (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, _BYTE *))(v49 + 152))(a3, v74);
      else
        (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, _BYTE *))(v49 + 408))(a3, v74);
      std::vector<GEL::GradientStop>::_Tidy(&si128);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v65 = 19937;
      GEL::RadialGradientInfo::~RadialGradientInfo((GEL::RadialGradientInfo *)v74);
LABEL_45:
      if ( v66 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 8LL))(v66);
      goto LABEL_20;
    }
    if ( *((_BYTE *)this + 9) )
    {
      v50 = *(_QWORD *)a2;
      v86 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IBrush *, GUID *, __int64 *))(v50 + 16))(
             a2,
             &GUID_c8b664f8_1da6_4eb4_94ad_cca1eaf52958,
             &v86) )
      {
        *((_BYTE *)this + 322) = 1;
        v51 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 112LL))(v86);
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*v51 + 32))(v51) )
          OExceptionLog::ThrowTag(40109380, 38, L"Bitmap resource lost");
        v52 = (*(__int64 (__fastcall **)(__int64 *, __m128i *))(*v51 + 64))(v51, &v70);
        v53 = (float *)&v69;
        v54 = v52 - (_QWORD)&v69;
        v55 = 2;
        do
        {
          *v53 = (float)*(int *)((char *)v53 + v54);
          ++v53;
          --v55;
        }
        while ( v55 );
        si128.m128i_i64[0] = 0;
        si128.m128i_i64[1] = v69;
        v72 = _mm_load_si128((const __m128i *)&_xmm);
        v73 = 0;
        (*(void (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v86 + 72LL))(v86, &v72);
        v56 = Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(this, v85);
        Math::operator*<float,float,float>(v84, &v72, v56);
        v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 136LL))(v86);
        Mso::SVG::SVGCreatingCommandSink::GetEmbeddedImageForBitmap(
          (__int64)this,
          &v70,
          v51,
          (float *)si128.m128i_i32,
          v84,
          (__int64)&v72,
          v57);
        v58 = v70.m128i_i64[0];
        if ( v70.m128i_i64[0] )
        {
          v59 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v70.m128i_i64[0] + 184LL);
          v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 128LL))(v86);
          v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v86 + 120LL))(v86);
          v59(v58, v61, v60);
          v62 = *(_QWORD *)a3;
          if ( a4 )
          {
            (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, __int64))(v62 + 176))(a3, v58);
            v63 = *(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *))(*(_QWORD *)a3 + 192LL);
          }
          else
          {
            (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, __int64))(v62 + 432))(a3, v58);
            v63 = *(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *))(*(_QWORD *)a3 + 448LL);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 56LL))(v86);
          v63(a3);
        }
        if ( v58 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 8LL))(v58);
        if ( v86 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 8LL))(v86);
        goto LABEL_45;
      }
      Ofc::TCntPtr<GEL::IPen>::~TCntPtr<GEL::IPen>(&v86);
    }
    *((_BYTE *)this + 323) = 1;
    OExceptionLog::ThrowTag(37884062, 55, L"Unsupported brush type");
  }
  *((_BYTE *)this + 320) = 1;
  if ( *((_DWORD *)this + 58) == 1 )
  {
    *((_BYTE *)this + 321) = 1;
    OExceptionLog::ThrowTag(37884059, 55, L"Unsupported gradient type: likely Path Gradient.");
  }
  (*(void (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v67 + 72LL))(v67, &si128);
  v11 = (float *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 104LL))(v67, &v86);
  v12 = (float)((float)(*(float *)&si128.m128i_i32[3] * v11[1]) + (float)(*(float *)&si128.m128i_i32[1] * *v11))
      + *((float *)&v65 + 1);
  v13 = (float)((float)(*(float *)&si128.m128i_i32[2] * v11[1]) + (float)(*(float *)si128.m128i_i32 * *v11))
      + *(float *)&v65;
  v14 = (float *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 112LL))(v67, &v86);
  v15 = (float)((float)(*v14 * *(float *)&si128.m128i_i32[1]) + (float)(v14[1] * *(float *)&si128.m128i_i32[3]))
      + *((float *)&v65 + 1);
  v16 = (float)((float)(v14[1] * *(float *)&si128.m128i_i32[2]) + (float)(*v14 * *(float *)si128.m128i_i32))
      + *(float *)&v65;
  v17 = (float *)Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(this, v84);
  v18 = (float)((float)(v12 * v17[2]) + (float)(v13 * *v17)) + v17[4];
  v19 = (float)((float)(v13 * v17[1]) + (float)(v12 * v17[3])) + v17[5];
  v20 = (float *)Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(this, v84);
  v21 = (float)((float)(v15 * v20[2]) + (float)(v16 * *v20)) + v20[4];
  v22 = (float)((float)(v16 * v20[1]) + (float)(v15 * v20[3])) + v20[5];
  GEL::LinearGradientInfo::LinearGradientInfo((GEL::LinearGradientInfo *)v74);
  v77 = v18;
  v78 = v19;
  v79 = v21;
  v80 = v22;
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 120LL))(v67);
  v76 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 64LL))(v23);
  v75 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 72LL))(v23) == 1;
  v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 56LL))(v23);
  v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 48LL))(v23);
  std::vector<GEL::GradientStop>::vector<GEL::GradientStop>(&v70, v24);
  v26 = 0;
  if ( v24 )
  {
    v27 = 0;
    do
    {
      if ( v27 >= 0xCCCCCCCCCCCCCCCDuLL * ((v70.m128i_i64[1] - v70.m128i_i64[0]) >> 2)
        || (*(_OWORD *)(v70.m128i_i64[0] + 20 * v27) = *(_OWORD *)(v25 + 20 * v27 + 4),
            v27 >= 0xCCCCCCCCCCCCCCCDuLL * ((v70.m128i_i64[1] - v70.m128i_i64[0]) >> 2)) )
      {
        _invoke_watson(0, 0, 0, 0, 0);
      }
      *(_DWORD *)(v70.m128i_i64[0] + 20 * v27 + 16) = *(_DWORD *)(v25 + 20 * v27);
      v27 = ++v26;
    }
    while ( v26 < v24 );
  }
  GEL::GradientInfo::SetShadeColors((GEL::GradientInfo *)v74, (const struct GEL::GradientStop *)v70.m128i_i64[0], v24);
  v28 = *(_QWORD *)a3;
  if ( a4 )
    (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, _BYTE *))(v28 + 128))(a3, v74);
  else
    (*(void (__fastcall **)(struct Mso::SVG::ISVGStyleProps *, _BYTE *))(v28 + 384))(a3, v74);
  std::vector<GEL::GradientStop>::_Tidy(&v70);
  v70 = _mm_load_si128((const __m128i *)&_xmm);
  v71 = 19937;
  GEL::LinearGradientInfo::~LinearGradientInfo((GEL::LinearGradientInfo *)v74);
LABEL_20:
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 8LL))(v67);
LABEL_5:
  if ( v68 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v68);
}

```

## disassembly

```asm
0x18004ff0c  mov     rax, rsp
0x18004ff0f  mov     [rax+8], rbx
0x18004ff13  mov     [rax+18h], rsi
0x18004ff17  mov     [rax+20h], rdi
0x18004ff1b  push    rbp
0x18004ff1c  push    r14
0x18004ff1e  push    r15
0x18004ff20  lea     rbp, [rax-0D8h]
0x18004ff27  sub     rsp, 1C0h
0x18004ff2e  movaps  xmmword ptr [rax-28h], xmm6
0x18004ff32  movaps  xmmword ptr [rax-38h], xmm7
0x18004ff36  movaps  xmmword ptr [rax-48h], xmm8
0x18004ff3b  movaps  xmmword ptr [rax-58h], xmm9
0x18004ff40  movaps  xmmword ptr [rax-68h], xmm10
0x18004ff45  mov     r15b, r9b
0x18004ff48  mov     r14, r8
0x18004ff4b  mov     rdi, rdx
0x18004ff4e  mov     rbx, rcx
0x18004ff51  mov     rax, [rdx]
0x18004ff54  mov     [rsp+1D0h+var_160], 0
0x18004ff5d  lea     r8, [rsp+1D0h+var_160]
0x18004ff62  lea     rdx, _GUID_d14199d2_d661_4a45_ab06_99af4f715717
0x18004ff69  mov     rcx, rdi
0x18004ff6c  mov     rax, [rax+10h]
0x18004ff70  call    cs:__guard_dispatch_icall_fptr
0x18004ff76  test    al, al
0x18004ff78  jz      loc_18005000F
0x18004ff7e  mov     rcx, [rsp+1D0h+var_160]
0x18004ff83  mov     rax, [rcx]
0x18004ff86  lea     rdx, [rsp+1D0h+var_198+8]
0x18004ff8b  mov     rax, [rax+60h]
0x18004ff8f  call    cs:__guard_dispatch_icall_fptr
0x18004ff95  mov     rax, [r14]
0x18004ff98  movaps  xmm0, [rsp+1D0h+var_198+8]
0x18004ff9d  lea     rdx, [rbp+0D0h+var_150]
0x18004ffa1  mov     rcx, r14
0x18004ffa4  movdqa  [rbp+0D0h+var_150], xmm0
0x18004ffa9  test    r15b, r15b
0x18004ffac  jz      short loc_18004FFB4
0x18004ffae  mov     rax, [rax+20h]
0x18004ffb2  jmp     short loc_18004FFBB
0x18004ffb4  mov     rax, [rax+120h]
0x18004ffbb  call    cs:__guard_dispatch_icall_fptr
0x18004ffc1  nop
0x18004ffc2  mov     rcx, [rsp+1D0h+var_160]
0x18004ffc7  test    rcx, rcx
0x18004ffca  jz      short loc_18004FFD9
0x18004ffcc  mov     rax, [rcx]
0x18004ffcf  mov     rax, [rax+8]
0x18004ffd3  call    cs:__guard_dispatch_icall_fptr
0x18004ffd9  lea     r11, [rsp+1D0h+var_10]
0x18004ffe1  mov     rbx, [r11+20h]
0x18004ffe5  mov     rsi, [r11+30h]
0x18004ffe9  mov     rdi, [r11+38h]
0x18004ffed  movaps  xmm6, xmmword ptr [r11-10h]
0x18004fff2  movaps  xmm7, xmmword ptr [r11-20h]
0x18004fff7  movaps  xmm8, xmmword ptr [r11-30h]
0x18004fffc  movaps  xmm9, xmmword ptr [r11-40h]
0x180050001  movaps  xmm10, xmmword ptr [r11-50h]
0x180050006  mov     rsp, r11
0x180050009  pop     r15
0x18005000b  pop     r14
0x18005000d  pop     rbp
0x18005000e  retn
0x18005000f  mov     rax, [rdi]
0x180050012  mov     [rsp+1D0h+var_168], 0
0x18005001b  lea     r8, [rsp+1D0h+var_168]
0x180050020  lea     rdx, _GUID_db6d09de_0055_4a4f_9077_0a24572f6b4a
0x180050027  mov     rcx, rdi
0x18005002a  mov     rax, [rax+10h]
0x18005002e  call    cs:__guard_dispatch_icall_fptr
0x180050034  test    al, al
0x180050036  jz      loc_18005033F
0x18005003c  mov     edi, 1
0x180050041  mov     [rbx+140h], dil
0x180050048  cmp     [rbx+0E8h], edi
0x18005004e  jz      loc_180050945
0x180050054  mov     rcx, [rsp+1D0h+var_168]
0x180050059  mov     rax, [rcx]
0x18005005c  lea     rdx, [rsp+1D0h+var_198+8]
0x180050061  mov     rax, [rax+48h]
0x180050065  call    cs:__guard_dispatch_icall_fptr
0x18005006b  mov     rcx, [rsp+1D0h+var_168]
0x180050070  mov     rax, [rcx]
0x180050073  lea     rdx, [rbp+0D0h+arg_8]
0x18005007a  mov     rax, [rax+68h]
0x18005007e  call    cs:__guard_dispatch_icall_fptr
0x180050084  movss   xmm6, dword ptr [rsp+1D0h+var_188+4]
0x18005008a  mulss   xmm6, dword ptr [rax+4]
0x18005008f  movss   xmm0, dword ptr [rsp+1D0h+var_198+0Ch]
0x180050095  mulss   xmm0, dword ptr [rax]
0x180050099  addss   xmm6, xmm0
0x18005009d  addss   xmm6, dword ptr [rsp+1D0h+var_180+4]
0x1800500a3  movss   xmm10, dword ptr [rsp+1D0h+var_188]
0x1800500aa  mulss   xmm10, dword ptr [rax+4]
0x1800500b0  movss   xmm0, dword ptr [rsp+1D0h+var_198+8]
0x1800500b6  mulss   xmm0, dword ptr [rax]
0x1800500ba  addss   xmm10, xmm0
0x1800500bf  addss   xmm10, dword ptr [rsp+1D0h+var_180]
0x1800500c6  mov     rcx, [rsp+1D0h+var_168]
0x1800500cb  mov     rax, [rcx]
0x1800500ce  lea     rdx, [rbp+0D0h+arg_8]
0x1800500d5  mov     rax, [rax+70h]
0x1800500d9  call    cs:__guard_dispatch_icall_fptr
0x1800500df  movss   xmm1, dword ptr [rax]
0x1800500e3  movss   xmm9, dword ptr [rax+4]
0x1800500e9  movaps  xmm8, xmm1
0x1800500ed  mulss   xmm8, dword ptr [rsp+1D0h+var_198+0Ch]
0x1800500f4  movaps  xmm0, xmm9
0x1800500f8  mulss   xmm0, dword ptr [rsp+1D0h+var_188+4]
0x1800500fe  addss   xmm8, xmm0
0x180050103  addss   xmm8, dword ptr [rsp+1D0h+var_180+4]
0x18005010a  mulss   xmm9, dword ptr [rsp+1D0h+var_188]
0x180050111  mulss   xmm1, dword ptr [rsp+1D0h+var_198+8]
0x180050117  addss   xmm9, xmm1
0x18005011c  addss   xmm9, dword ptr [rsp+1D0h+var_180]
0x180050123  lea     rdx, [rbp+0D0h+var_90]
0x180050127  mov     rcx, rbx
0x18005012a  call    ?GetCurrentGeometryToShapeTransform@SVGCreatingCommandSink@SVG@Mso@@AEBA?AU?$TAffine3x3@M@Math@@XZ; Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(void)
0x18005012f  movaps  xmm7, xmm6
0x180050132  mulss   xmm7, dword ptr [rax+8]
0x180050137  movaps  xmm0, xmm10
0x18005013b  mulss   xmm0, dword ptr [rax]
0x18005013f  addss   xmm7, xmm0
0x180050143  addss   xmm7, dword ptr [rax+10h]
0x180050148  mulss   xmm10, dword ptr [rax+4]
0x18005014e  mulss   xmm6, dword ptr [rax+0Ch]
0x180050153  addss   xmm10, xmm6
0x180050158  addss   xmm10, dword ptr [rax+14h]
0x18005015e  lea     rdx, [rbp+0D0h+var_90]
0x180050162  mov     rcx, rbx
0x180050165  call    ?GetCurrentGeometryToShapeTransform@SVGCreatingCommandSink@SVG@Mso@@AEBA?AU?$TAffine3x3@M@Math@@XZ; Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(void)
0x18005016a  movaps  xmm6, xmm8
0x18005016e  mulss   xmm6, dword ptr [rax+8]
0x180050173  movaps  xmm0, xmm9
0x180050177  mulss   xmm0, dword ptr [rax]
0x18005017b  addss   xmm6, xmm0
0x18005017f  addss   xmm6, dword ptr [rax+10h]
0x180050184  mulss   xmm9, dword ptr [rax+4]
0x18005018a  mulss   xmm8, dword ptr [rax+0Ch]
0x180050190  addss   xmm9, xmm8
0x180050195  addss   xmm9, dword ptr [rax+14h]
0x18005019b  lea     rcx, [rbp+0D0h+var_110]
0x18005019f  call    cs:__imp_??0LinearGradientInfo@GEL@@QEAA@XZ; GEL::LinearGradientInfo::LinearGradientInfo(void)
0x1800501a5  nop
0x1800501a6  cvtps2pd xmm3, xmm9
0x1800501aa  cvtps2pd xmm2, xmm6
0x1800501ad  cvtps2pd xmm1, xmm10
0x1800501b1  cvtps2pd xmm0, xmm7
0x1800501b4  movsd   [rbp+0D0h+var_D0], xmm0
0x1800501b9  movsd   [rbp+0D0h+var_C8], xmm1
0x1800501be  movsd   [rbp+0D0h+var_C0], xmm2
0x1800501c3  movsd   [rbp+0D0h+var_B8], xmm3
0x1800501c8  mov     rcx, [rsp+1D0h+var_168]
0x1800501cd  mov     rax, [rcx]
0x1800501d0  mov     rax, [rax+78h]
0x1800501d4  call    cs:__guard_dispatch_icall_fptr
0x1800501da  mov     rbx, rax
0x1800501dd  mov     rcx, [rax]
0x1800501e0  mov     rax, [rcx+40h]
0x1800501e4  mov     rcx, rbx
0x1800501e7  call    cs:__guard_dispatch_icall_fptr
0x1800501ed  mov     [rbp+0D0h+var_D8], eax
0x1800501f0  mov     rcx, [rbx]
0x1800501f3  mov     rax, [rcx+48h]
0x1800501f7  mov     rcx, rbx
0x1800501fa  call    cs:__guard_dispatch_icall_fptr
0x180050200  cmp     eax, edi
0x180050202  setz    [rbp+0D0h+var_D9]
0x180050206  mov     rax, [rbx]
0x180050209  mov     rcx, rbx
0x18005020c  mov     rax, [rax+38h]
0x180050210  call    cs:__guard_dispatch_icall_fptr
0x180050216  mov     rsi, rax
0x180050219  mov     rcx, [rbx]
0x18005021c  mov     rax, [rcx+30h]
0x180050220  mov     rcx, rbx
0x180050223  call    cs:__guard_dispatch_icall_fptr
0x180050229  mov     rbx, rax
0x18005022c  mov     rdx, rsi
0x18005022f  lea     rcx, [rbp+0D0h+var_150]
0x180050233  call    ??0?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@QEAA@_KAEBV?$allocator@UGradientStop@GEL@@@1@@Z; std::vector<GEL::GradientStop>::vector<GEL::GradientStop>(unsigned __int64,std::allocator<GEL::GradientStop> const &)
0x180050238  nop
0x180050239  xor     r9d, r9d
0x18005023c  test    rsi, rsi
0x18005023f  jz      short loc_1800502A5
0x180050241  xor     ecx, ecx
0x180050243  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18005024d  lea     r8, [rcx+rcx*4]
0x180050251  movups  xmm0, xmmword ptr [rbx+r8*4+4]
0x180050257  mov     rax, qword ptr [rbp+0D0h+var_150+8]
0x18005025b  mov     r10, qword ptr [rbp+0D0h+var_150]
0x18005025f  sub     rax, r10
0x180050262  sar     rax, 2
0x180050266  imul    rax, rdx
0x18005026a  cmp     rcx, rax
0x18005026d  jnb     short loc_1800502CE
0x18005026f  movdqu  xmmword ptr [r10+r8*4], xmm0
0x180050275  movss   xmm0, dword ptr [rbx+r8*4]
0x18005027b  mov     rax, qword ptr [rbp+0D0h+var_150+8]
0x18005027f  mov     r10, qword ptr [rbp+0D0h+var_150]
0x180050283  sub     rax, r10
0x180050286  sar     rax, 2
0x18005028a  imul    rax, rdx
0x18005028e  cmp     rcx, rax
0x180050291  jnb     short loc_1800502CE
0x180050293  movss   dword ptr [r10+r8*4+10h], xmm0
0x18005029a  add     r9d, edi
0x18005029d  mov     ecx, r9d
0x1800502a0  cmp     rcx, rsi
0x1800502a3  jb      short loc_18005024D
0x1800502a5  mov     r8d, esi
0x1800502a8  mov     rdx, qword ptr [rbp+0D0h+var_150]
0x1800502ac  lea     rcx, [rbp+0D0h+var_110]
0x1800502b0  call    cs:__imp_?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z; GEL::GradientInfo::SetShadeColors(GEL::GradientStop const *,uint)
0x1800502b6  mov     rax, [r14]
0x1800502b9  lea     rdx, [rbp+0D0h+var_110]
0x1800502bd  mov     rcx, r14
0x1800502c0  test    r15b, r15b
0x1800502c3  jz      short loc_1800502E8
0x1800502c5  mov     rax, [rax+80h]
0x1800502cc  jmp     short loc_1800502EF
0x1800502ce  mov     [rsp+1D0h+Reserved], 0; Reserved
0x1800502d7  xor     r9d, r9d; LineNo
0x1800502da  xor     r8d, r8d; FileName
0x1800502dd  xor     edx, edx; FunctionName
0x1800502df  xor     ecx, ecx; Expression
0x1800502e1  call    cs:__imp__invoke_watson
0x1800502e8  mov     rax, [rax+180h]
0x1800502ef  call    cs:__guard_dispatch_icall_fptr
0x1800502f5  nop
0x1800502f6  lea     rcx, [rbp+0D0h+var_150]
0x1800502fa  call    ?_Tidy@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAXXZ; std::vector<GEL::GradientStop>::_Tidy(void)
0x1800502ff  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x180050307  movdqu  [rbp+0D0h+var_150], xmm0
0x18005030c  mov     [rbp+0D0h+var_140], 4DE1h
0x180050314  lea     rcx, [rbp+0D0h+var_110]
0x180050318  call    cs:__imp_??1LinearGradientInfo@GEL@@UEAA@XZ; GEL::LinearGradientInfo::~LinearGradientInfo(void)
0x18005031e  nop
0x18005031f  mov     rcx, [rsp+1D0h+var_168]
0x180050324  test    rcx, rcx
0x180050327  jz      loc_18004FFC2
0x18005032d  mov     rax, [rcx]
0x180050330  mov     rax, [rax+8]
0x180050334  call    cs:__guard_dispatch_icall_fptr
0x18005033a  jmp     loc_18004FFC2
0x18005033f  mov     rax, [rdi]
0x180050342  mov     [rsp+1D0h+var_170], 0
0x18005034b  lea     r8, [rsp+1D0h+var_170]
0x180050350  lea     rdx, _GUID_934f0936_4b9a_4135_88f0_a32291a6393b
0x180050357  mov     rcx, rdi
0x18005035a  mov     rax, [rax+10h]
0x18005035e  call    cs:__guard_dispatch_icall_fptr
0x180050364  test    al, al
0x180050366  jz      loc_1800506B5
0x18005036c  mov     edi, 1
0x180050371  mov     [rbx+140h], dil
0x180050378  lea     rcx, [rbp+0D0h+var_110]
0x18005037c  call    cs:__imp_??0RadialGradientInfo@GEL@@QEAA@XZ; GEL::RadialGradientInfo::RadialGradientInfo(void)
0x180050382  mov     rcx, [rsp+1D0h+var_170]
0x180050387  mov     rax, [rcx]
0x18005038a  lea     rdx, [rbp+0D0h+arg_8]
0x180050391  mov     rax, [rax+70h]
0x180050395  call    cs:__guard_dispatch_icall_fptr
0x18005039b  mov     rcx, [rsp+1D0h+var_170]
0x1800503a0  mov     rax, [rcx]
0x1800503a3  lea     rdx, [rsp+1D0h+var_158]
0x1800503a8  mov     rax, [rax+80h]
0x1800503af  call    cs:__guard_dispatch_icall_fptr
0x1800503b5  mov     rcx, [rsp+1D0h+var_170]
0x1800503ba  mov     rax, [rcx]
0x1800503bd  lea     rdx, [rbp+0D0h+var_150]
0x1800503c1  mov     rax, [rax+78h]
0x1800503c5  call    cs:__guard_dispatch_icall_fptr
0x1800503cb  movss   xmm9, dword ptr [rbp+0D0h+arg_8+4]
0x1800503d4  movss   xmm6, dword ptr [rsp+1D0h+var_158+4]
0x1800503da  addss   xmm9, xmm6
0x1800503df  movss   xmm10, dword ptr [rbp+0D0h+arg_8]
0x1800503e8  movss   xmm1, dword ptr [rsp+1D0h+var_158]
0x1800503ee  addss   xmm10, xmm1
0x1800503f3  mulss   xmm6, xmm6
0x1800503f7  movss   xmm8, dword ptr [rbp+0D0h+var_150+4]
0x1800503fd  movaps  xmm0, xmm8
0x180050401  mulss   xmm0, xmm8
0x180050406  divss   xmm6, xmm0
0x18005040a  mulss   xmm1, xmm1
0x18005040e  movss   xmm7, dword ptr [rbp+0D0h+var_150]
0x180050413  movaps  xmm0, xmm7
0x180050416  mulss   xmm0, xmm7
0x18005041a  divss   xmm1, xmm0
0x18005041e  addss   xmm6, xmm1
0x180050422  movaps  xmm0, xmm6; X
0x180050425  call    _fdclass_0
0x18005042a  cmp     ax, di
0x18005042d  jz      short loc_180050440
0x18005042f  subss   xmm6, cs:__real@3f800000
0x180050437  comiss  xmm6, cs:__real@358637bd
0x18005043e  jmp     short loc_180050447
0x180050440  comiss  xmm6, cs:__real@3f800000
0x180050447  setnbe  al
  ... truncated ...
```
