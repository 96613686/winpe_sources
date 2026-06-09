# Mso::SVG::SVGCreatingCommandSink::InitStylePropsFromBrush(ARC::IBrush const &,Mso::SVG::ISVGStyleProps &,bool)

- ea: `0x18004ff2c`
- end: `0x1800509a4`
- name: `?InitStylePropsFromBrush@SVGCreatingCommandSink@SVG@Mso@@AEAAXAEBUIBrush@ARC@@AEAUISVGStyleProps@23@_N@Z`
- size: `2680`
- prototype: `void __fastcall(Mso::SVG::SVGCreatingCommandSink *__hidden this, const struct ARC::IBrush *, struct Mso::SVG::ISVGStyleProps *, bool)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180052dbc`
- `0x180052f70`
- `0x180053664`
- `0x1800538f0`

## callees

- `0x180007310`
- `0x180023800`
- `0x18004f700`
- `0x18004ff2c`
- `0x180054c0c`
- `0x180058ea0`
- `0x180059c94`
- `0x18005a5a0`
- `0x18013f7a0`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18005050c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18005050c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180050548`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180050548`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18005051a`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18005051a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050301`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050674`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050301`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180050674`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x1800501bf`
- `gfx!??0LinearGradientInfo@GEL@@QEAA@XZ` at `0x1800501bf`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x180050338`
- `gfx!??1LinearGradientInfo@GEL@@UEAA@XZ` at `0x180050338`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800502d0`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x180050643`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x1800502d0`
- `gfx!?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z` at `0x180050643`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x18005039c`
- `gfx!??0RadialGradientInfo@GEL@@QEAA@XZ` at `0x18005039c`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1800506ae`
- `gfx!??1RadialGradientInfo@GEL@@UEAA@XZ` at `0x1800506ae`

## string_xrefs

- `0x18005098d`: `Unsupported radial gradient: the focus is outside the gradient area.`
- `0x18005096c`: `Unsupported gradient type: likely Path Gradient.`

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
0x18004ff2c  mov     rax, rsp
0x18004ff2f  mov     [rax+8], rbx
0x18004ff33  mov     [rax+18h], rsi
0x18004ff37  mov     [rax+20h], rdi
0x18004ff3b  push    rbp
0x18004ff3c  push    r14
0x18004ff3e  push    r15
0x18004ff40  lea     rbp, [rax-0D8h]
0x18004ff47  sub     rsp, 1C0h
0x18004ff4e  movaps  xmmword ptr [rax-28h], xmm6
0x18004ff52  movaps  xmmword ptr [rax-38h], xmm7
0x18004ff56  movaps  xmmword ptr [rax-48h], xmm8
0x18004ff5b  movaps  xmmword ptr [rax-58h], xmm9
0x18004ff60  movaps  xmmword ptr [rax-68h], xmm10
0x18004ff65  mov     r15b, r9b
0x18004ff68  mov     r14, r8
0x18004ff6b  mov     rdi, rdx
0x18004ff6e  mov     rbx, rcx
0x18004ff71  mov     rax, [rdx]
0x18004ff74  mov     [rsp+1D0h+var_160], 0
0x18004ff7d  lea     r8, [rsp+1D0h+var_160]
0x18004ff82  lea     rdx, _GUID_d14199d2_d661_4a45_ab06_99af4f715717
0x18004ff89  mov     rcx, rdi
0x18004ff8c  mov     rax, [rax+10h]
0x18004ff90  call    cs:__guard_dispatch_icall_fptr
0x18004ff96  test    al, al
0x18004ff98  jz      loc_18005002F
0x18004ff9e  mov     rcx, [rsp+1D0h+var_160]
0x18004ffa3  mov     rax, [rcx]
0x18004ffa6  lea     rdx, [rsp+1D0h+var_198+8]
0x18004ffab  mov     rax, [rax+60h]
0x18004ffaf  call    cs:__guard_dispatch_icall_fptr
0x18004ffb5  mov     rax, [r14]
0x18004ffb8  movaps  xmm0, [rsp+1D0h+var_198+8]
0x18004ffbd  lea     rdx, [rbp+0D0h+var_150]
0x18004ffc1  mov     rcx, r14
0x18004ffc4  movdqa  [rbp+0D0h+var_150], xmm0
0x18004ffc9  test    r15b, r15b
0x18004ffcc  jz      short loc_18004FFD4
0x18004ffce  mov     rax, [rax+20h]
0x18004ffd2  jmp     short loc_18004FFDB
0x18004ffd4  mov     rax, [rax+120h]
0x18004ffdb  call    cs:__guard_dispatch_icall_fptr
0x18004ffe1  nop
0x18004ffe2  mov     rcx, [rsp+1D0h+var_160]
0x18004ffe7  test    rcx, rcx
0x18004ffea  jz      short loc_18004FFF9
0x18004ffec  mov     rax, [rcx]
0x18004ffef  mov     rax, [rax+8]
0x18004fff3  call    cs:__guard_dispatch_icall_fptr
0x18004fff9  lea     r11, [rsp+1D0h+var_10]
0x180050001  mov     rbx, [r11+20h]
0x180050005  mov     rsi, [r11+30h]
0x180050009  mov     rdi, [r11+38h]
0x18005000d  movaps  xmm6, xmmword ptr [r11-10h]
0x180050012  movaps  xmm7, xmmword ptr [r11-20h]
0x180050017  movaps  xmm8, xmmword ptr [r11-30h]
0x18005001c  movaps  xmm9, xmmword ptr [r11-40h]
0x180050021  movaps  xmm10, xmmword ptr [r11-50h]
0x180050026  mov     rsp, r11
0x180050029  pop     r15
0x18005002b  pop     r14
0x18005002d  pop     rbp
0x18005002e  retn
0x18005002f  mov     rax, [rdi]
0x180050032  mov     [rsp+1D0h+var_168], 0
0x18005003b  lea     r8, [rsp+1D0h+var_168]
0x180050040  lea     rdx, _GUID_db6d09de_0055_4a4f_9077_0a24572f6b4a
0x180050047  mov     rcx, rdi
0x18005004a  mov     rax, [rax+10h]
0x18005004e  call    cs:__guard_dispatch_icall_fptr
0x180050054  test    al, al
0x180050056  jz      loc_18005035F
0x18005005c  mov     edi, 1
0x180050061  mov     [rbx+140h], dil
0x180050068  cmp     [rbx+0E8h], edi
0x18005006e  jz      loc_180050965
0x180050074  mov     rcx, [rsp+1D0h+var_168]
0x180050079  mov     rax, [rcx]
0x18005007c  lea     rdx, [rsp+1D0h+var_198+8]
0x180050081  mov     rax, [rax+48h]
0x180050085  call    cs:__guard_dispatch_icall_fptr
0x18005008b  mov     rcx, [rsp+1D0h+var_168]
0x180050090  mov     rax, [rcx]
0x180050093  lea     rdx, [rbp+0D0h+arg_8]
0x18005009a  mov     rax, [rax+68h]
0x18005009e  call    cs:__guard_dispatch_icall_fptr
0x1800500a4  movss   xmm6, dword ptr [rsp+1D0h+var_188+4]
0x1800500aa  mulss   xmm6, dword ptr [rax+4]
0x1800500af  movss   xmm0, dword ptr [rsp+1D0h+var_198+0Ch]
0x1800500b5  mulss   xmm0, dword ptr [rax]
0x1800500b9  addss   xmm6, xmm0
0x1800500bd  addss   xmm6, dword ptr [rsp+1D0h+var_180+4]
0x1800500c3  movss   xmm10, dword ptr [rsp+1D0h+var_188]
0x1800500ca  mulss   xmm10, dword ptr [rax+4]
0x1800500d0  movss   xmm0, dword ptr [rsp+1D0h+var_198+8]
0x1800500d6  mulss   xmm0, dword ptr [rax]
0x1800500da  addss   xmm10, xmm0
0x1800500df  addss   xmm10, dword ptr [rsp+1D0h+var_180]
0x1800500e6  mov     rcx, [rsp+1D0h+var_168]
0x1800500eb  mov     rax, [rcx]
0x1800500ee  lea     rdx, [rbp+0D0h+arg_8]
0x1800500f5  mov     rax, [rax+70h]
0x1800500f9  call    cs:__guard_dispatch_icall_fptr
0x1800500ff  movss   xmm1, dword ptr [rax]
0x180050103  movss   xmm9, dword ptr [rax+4]
0x180050109  movaps  xmm8, xmm1
0x18005010d  mulss   xmm8, dword ptr [rsp+1D0h+var_198+0Ch]
0x180050114  movaps  xmm0, xmm9
0x180050118  mulss   xmm0, dword ptr [rsp+1D0h+var_188+4]
0x18005011e  addss   xmm8, xmm0
0x180050123  addss   xmm8, dword ptr [rsp+1D0h+var_180+4]
0x18005012a  mulss   xmm9, dword ptr [rsp+1D0h+var_188]
0x180050131  mulss   xmm1, dword ptr [rsp+1D0h+var_198+8]
0x180050137  addss   xmm9, xmm1
0x18005013c  addss   xmm9, dword ptr [rsp+1D0h+var_180]
0x180050143  lea     rdx, [rbp+0D0h+var_90]
0x180050147  mov     rcx, rbx
0x18005014a  call    ?GetCurrentGeometryToShapeTransform@SVGCreatingCommandSink@SVG@Mso@@AEBA?AU?$TAffine3x3@M@Math@@XZ; Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(void)
0x18005014f  movaps  xmm7, xmm6
0x180050152  mulss   xmm7, dword ptr [rax+8]
0x180050157  movaps  xmm0, xmm10
0x18005015b  mulss   xmm0, dword ptr [rax]
0x18005015f  addss   xmm7, xmm0
0x180050163  addss   xmm7, dword ptr [rax+10h]
0x180050168  mulss   xmm10, dword ptr [rax+4]
0x18005016e  mulss   xmm6, dword ptr [rax+0Ch]
0x180050173  addss   xmm10, xmm6
0x180050178  addss   xmm10, dword ptr [rax+14h]
0x18005017e  lea     rdx, [rbp+0D0h+var_90]
0x180050182  mov     rcx, rbx
0x180050185  call    ?GetCurrentGeometryToShapeTransform@SVGCreatingCommandSink@SVG@Mso@@AEBA?AU?$TAffine3x3@M@Math@@XZ; Mso::SVG::SVGCreatingCommandSink::GetCurrentGeometryToShapeTransform(void)
0x18005018a  movaps  xmm6, xmm8
0x18005018e  mulss   xmm6, dword ptr [rax+8]
0x180050193  movaps  xmm0, xmm9
0x180050197  mulss   xmm0, dword ptr [rax]
0x18005019b  addss   xmm6, xmm0
0x18005019f  addss   xmm6, dword ptr [rax+10h]
0x1800501a4  mulss   xmm9, dword ptr [rax+4]
0x1800501aa  mulss   xmm8, dword ptr [rax+0Ch]
0x1800501b0  addss   xmm9, xmm8
0x1800501b5  addss   xmm9, dword ptr [rax+14h]
0x1800501bb  lea     rcx, [rbp+0D0h+var_110]
0x1800501bf  call    cs:__imp_??0LinearGradientInfo@GEL@@QEAA@XZ; GEL::LinearGradientInfo::LinearGradientInfo(void)
0x1800501c5  nop
0x1800501c6  cvtps2pd xmm3, xmm9
0x1800501ca  cvtps2pd xmm2, xmm6
0x1800501cd  cvtps2pd xmm1, xmm10
0x1800501d1  cvtps2pd xmm0, xmm7
0x1800501d4  movsd   [rbp+0D0h+var_D0], xmm0
0x1800501d9  movsd   [rbp+0D0h+var_C8], xmm1
0x1800501de  movsd   [rbp+0D0h+var_C0], xmm2
0x1800501e3  movsd   [rbp+0D0h+var_B8], xmm3
0x1800501e8  mov     rcx, [rsp+1D0h+var_168]
0x1800501ed  mov     rax, [rcx]
0x1800501f0  mov     rax, [rax+78h]
0x1800501f4  call    cs:__guard_dispatch_icall_fptr
0x1800501fa  mov     rbx, rax
0x1800501fd  mov     rcx, [rax]
0x180050200  mov     rax, [rcx+40h]
0x180050204  mov     rcx, rbx
0x180050207  call    cs:__guard_dispatch_icall_fptr
0x18005020d  mov     [rbp+0D0h+var_D8], eax
0x180050210  mov     rcx, [rbx]
0x180050213  mov     rax, [rcx+48h]
0x180050217  mov     rcx, rbx
0x18005021a  call    cs:__guard_dispatch_icall_fptr
0x180050220  cmp     eax, edi
0x180050222  setz    [rbp+0D0h+var_D9]
0x180050226  mov     rax, [rbx]
0x180050229  mov     rcx, rbx
0x18005022c  mov     rax, [rax+38h]
0x180050230  call    cs:__guard_dispatch_icall_fptr
0x180050236  mov     rsi, rax
0x180050239  mov     rcx, [rbx]
0x18005023c  mov     rax, [rcx+30h]
0x180050240  mov     rcx, rbx
0x180050243  call    cs:__guard_dispatch_icall_fptr
0x180050249  mov     rbx, rax
0x18005024c  mov     rdx, rsi
0x18005024f  lea     rcx, [rbp+0D0h+var_150]
0x180050253  call    ??0?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@QEAA@_KAEBV?$allocator@UGradientStop@GEL@@@1@@Z; std::vector<GEL::GradientStop>::vector<GEL::GradientStop>(unsigned __int64,std::allocator<GEL::GradientStop> const &)
0x180050258  nop
0x180050259  xor     r9d, r9d
0x18005025c  test    rsi, rsi
0x18005025f  jz      short loc_1800502C5
0x180050261  xor     ecx, ecx
0x180050263  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18005026d  lea     r8, [rcx+rcx*4]
0x180050271  movups  xmm0, xmmword ptr [rbx+r8*4+4]
0x180050277  mov     rax, qword ptr [rbp+0D0h+var_150+8]
0x18005027b  mov     r10, qword ptr [rbp+0D0h+var_150]
0x18005027f  sub     rax, r10
0x180050282  sar     rax, 2
0x180050286  imul    rax, rdx
0x18005028a  cmp     rcx, rax
0x18005028d  jnb     short loc_1800502EE
0x18005028f  movdqu  xmmword ptr [r10+r8*4], xmm0
0x180050295  movss   xmm0, dword ptr [rbx+r8*4]
0x18005029b  mov     rax, qword ptr [rbp+0D0h+var_150+8]
0x18005029f  mov     r10, qword ptr [rbp+0D0h+var_150]
0x1800502a3  sub     rax, r10
0x1800502a6  sar     rax, 2
0x1800502aa  imul    rax, rdx
0x1800502ae  cmp     rcx, rax
0x1800502b1  jnb     short loc_1800502EE
0x1800502b3  movss   dword ptr [r10+r8*4+10h], xmm0
0x1800502ba  add     r9d, edi
0x1800502bd  mov     ecx, r9d
0x1800502c0  cmp     rcx, rsi
0x1800502c3  jb      short loc_18005026D
0x1800502c5  mov     r8d, esi
0x1800502c8  mov     rdx, qword ptr [rbp+0D0h+var_150]
0x1800502cc  lea     rcx, [rbp+0D0h+var_110]
0x1800502d0  call    cs:__imp_?SetShadeColors@GradientInfo@GEL@@QEAAXPEBUGradientStop@2@I@Z; GEL::GradientInfo::SetShadeColors(GEL::GradientStop const *,uint)
0x1800502d6  mov     rax, [r14]
0x1800502d9  lea     rdx, [rbp+0D0h+var_110]
0x1800502dd  mov     rcx, r14
0x1800502e0  test    r15b, r15b
0x1800502e3  jz      short loc_180050308
0x1800502e5  mov     rax, [rax+80h]
0x1800502ec  jmp     short loc_18005030F
0x1800502ee  mov     [rsp+1D0h+Reserved], 0; Reserved
0x1800502f7  xor     r9d, r9d; LineNo
0x1800502fa  xor     r8d, r8d; FileName
0x1800502fd  xor     edx, edx; FunctionName
0x1800502ff  xor     ecx, ecx; Expression
0x180050301  call    cs:__imp__invoke_watson
0x180050308  mov     rax, [rax+180h]
0x18005030f  call    cs:__guard_dispatch_icall_fptr
0x180050315  nop
0x180050316  lea     rcx, [rbp+0D0h+var_150]
0x18005031a  call    ?_Tidy@?$vector@UGradientStop@GEL@@V?$allocator@UGradientStop@GEL@@@std@@@std@@AEAAXXZ; std::vector<GEL::GradientStop>::_Tidy(void)
0x18005031f  movdqa  xmm0, cs:__xmm@0000000000004de10000000000004de1
0x180050327  movdqu  [rbp+0D0h+var_150], xmm0
0x18005032c  mov     [rbp+0D0h+var_140], 4DE1h
0x180050334  lea     rcx, [rbp+0D0h+var_110]
0x180050338  call    cs:__imp_??1LinearGradientInfo@GEL@@UEAA@XZ; GEL::LinearGradientInfo::~LinearGradientInfo(void)
0x18005033e  nop
0x18005033f  mov     rcx, [rsp+1D0h+var_168]
0x180050344  test    rcx, rcx
0x180050347  jz      loc_18004FFE2
0x18005034d  mov     rax, [rcx]
0x180050350  mov     rax, [rax+8]
0x180050354  call    cs:__guard_dispatch_icall_fptr
0x18005035a  jmp     loc_18004FFE2
0x18005035f  mov     rax, [rdi]
0x180050362  mov     [rsp+1D0h+var_170], 0
0x18005036b  lea     r8, [rsp+1D0h+var_170]
0x180050370  lea     rdx, _GUID_934f0936_4b9a_4135_88f0_a32291a6393b
0x180050377  mov     rcx, rdi
0x18005037a  mov     rax, [rax+10h]
0x18005037e  call    cs:__guard_dispatch_icall_fptr
0x180050384  test    al, al
0x180050386  jz      loc_1800506D5
0x18005038c  mov     edi, 1
0x180050391  mov     [rbx+140h], dil
0x180050398  lea     rcx, [rbp+0D0h+var_110]
0x18005039c  call    cs:__imp_??0RadialGradientInfo@GEL@@QEAA@XZ; GEL::RadialGradientInfo::RadialGradientInfo(void)
0x1800503a2  mov     rcx, [rsp+1D0h+var_170]
0x1800503a7  mov     rax, [rcx]
0x1800503aa  lea     rdx, [rbp+0D0h+arg_8]
0x1800503b1  mov     rax, [rax+70h]
0x1800503b5  call    cs:__guard_dispatch_icall_fptr
0x1800503bb  mov     rcx, [rsp+1D0h+var_170]
0x1800503c0  mov     rax, [rcx]
0x1800503c3  lea     rdx, [rsp+1D0h+var_158]
0x1800503c8  mov     rax, [rax+80h]
0x1800503cf  call    cs:__guard_dispatch_icall_fptr
0x1800503d5  mov     rcx, [rsp+1D0h+var_170]
0x1800503da  mov     rax, [rcx]
0x1800503dd  lea     rdx, [rbp+0D0h+var_150]
0x1800503e1  mov     rax, [rax+78h]
0x1800503e5  call    cs:__guard_dispatch_icall_fptr
0x1800503eb  movss   xmm9, dword ptr [rbp+0D0h+arg_8+4]
0x1800503f4  movss   xmm6, dword ptr [rsp+1D0h+var_158+4]
0x1800503fa  addss   xmm9, xmm6
0x1800503ff  movss   xmm10, dword ptr [rbp+0D0h+arg_8]
0x180050408  movss   xmm1, dword ptr [rsp+1D0h+var_158]
0x18005040e  addss   xmm10, xmm1
0x180050413  mulss   xmm6, xmm6
0x180050417  movss   xmm8, dword ptr [rbp+0D0h+var_150+4]
0x18005041d  movaps  xmm0, xmm8
0x180050421  mulss   xmm0, xmm8
0x180050426  divss   xmm6, xmm0
0x18005042a  mulss   xmm1, xmm1
0x18005042e  movss   xmm7, dword ptr [rbp+0D0h+var_150]
0x180050433  movaps  xmm0, xmm7
0x180050436  mulss   xmm0, xmm7
0x18005043a  divss   xmm1, xmm0
0x18005043e  addss   xmm6, xmm1
0x180050442  movaps  xmm0, xmm6; X
0x180050445  call    _fdclass_0
0x18005044a  cmp     ax, di
0x18005044d  jz      short loc_180050460
0x18005044f  subss   xmm6, cs:__real@3f800000
0x180050457  comiss  xmm6, cs:__real@358637bd
0x18005045e  jmp     short loc_180050467
0x180050460  comiss  xmm6, cs:__real@3f800000
0x180050467  setnbe  al
  ... truncated ...
```
