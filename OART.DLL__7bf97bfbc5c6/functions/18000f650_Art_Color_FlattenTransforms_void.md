# Art::Color::FlattenTransforms(void)

- ea: `0x18000f650`
- end: `0x180010c3f`
- name: `?FlattenTransforms@Color@Art@@QEAAXXZ`
- size: `5615`
- prototype: `void __fastcall(Art::Color *__hidden this)`
- caller_count: `6`
- callee_count: `65`
- tags: `broker_com_uri`

## callers

- `0x1800032a0`
- `0x180037d30`
- `0x180199ea0`
- `0x1802d8e54`
- `0x1805893b0`
- `0x1808a4ac0`

## callees

- `0x1800034bc`
- `0x180003a10`
- `0x18000de80`
- `0x18000e354`
- `0x18000e370`
- `0x18000e5f0`
- `0x18000f650`
- `0x180010c40`
- `0x180017fe8`
- `0x18002c480`
- `0x180030be0`
- `0x180037ef0`
- `0x18003de2c`
- `0x180071720`
- `0x1800902e8`
- `0x1800b7da8`
- `0x1800b7ed0`
- `0x1800b8074`
- `0x18019cc58`
- `0x18019cc8c`
- `0x18019cce4`
- `0x18019ce7c`
- `0x18019cf04`
- `0x18019cf74`
- `0x18019cfcc`
- `0x18019d29c`
- `0x18019d30c`
- `0x1801d78c8`
- `0x1802973a0`
- `0x1802973c0`
- `0x1804a98a0`
- `0x1804acb90`
- `0x1804c8ebc`
- `0x1804d6450`
- `0x1804d6484`
- `0x1804de178`
- `0x1804de1ac`
- `0x1804e4620`
- `0x1804e4650`
- `0x180520e9c`
- `0x1805219fc`
- `0x18052ca2c`
- `0x1805fbf10`
- `0x1805fbf40`
- `0x180605024`
- `0x180606a94`
- `0x180613790`
- `0x18061e898`
- `0x18061e8c8`
- `0x1806278f0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x18000ffcc`
- `VCRUNTIME140!__std_type_info_compare` at `0x18000fff0`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010014`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010038`
- `VCRUNTIME140!__std_type_info_compare` at `0x18001005c`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010080`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800100a4`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800100c8`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800100ec`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010110`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010134`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010158`
- `VCRUNTIME140!__std_type_info_compare` at `0x18001017c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800101a0`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800101f2`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010216`
- `VCRUNTIME140!__std_type_info_compare` at `0x18000ffcc`
- `VCRUNTIME140!__std_type_info_compare` at `0x18000fff0`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010014`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010038`
- `VCRUNTIME140!__std_type_info_compare` at `0x18001005c`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010080`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800100a4`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800100c8`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800100ec`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010110`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010134`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010158`
- `VCRUNTIME140!__std_type_info_compare` at `0x18001017c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800101a0`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800101f2`
- `VCRUNTIME140!__std_type_info_compare` at `0x180010216`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180010c0f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180010c0f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18000f785`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18000fd71`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180010ae2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18000f785`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18000fd71`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180010ae2`

## pseudocode

```c
void __fastcall Art::Color::FlattenTransforms(Art::Color *this)
{
  unsigned int v1; // esi
  const int *v2; // r13
  float v3; // xmm6_4
  float v4; // xmm8_4
  float v5; // xmm10_4
  float v6; // xmm11_4
  double v7; // xmm12_8
  double v8; // xmm13_8
  float v9; // xmm14_4
  float v10; // xmm15_4
  __int64 v12; // rdi
  unsigned __int64 v13; // rax
  __int64 TransformListRef; // rbx
  void *v15; // rdx
  Mso::Memory *v16; // rcx
  int *v17; // rax
  unsigned int v18; // edx
  float v19; // xmm7_4
  unsigned int v20; // xmm0_4
  __int64 v21; // rbx
  __int64 *v22; // rcx
  __int64 v23; // rcx
  __int64 *v25; // rcx
  __int64 v26; // rcx
  __int64 *v28; // rcx
  __int64 v29; // rcx
  __int64 *v31; // rcx
  __int64 v32; // rcx
  __int64 *v34; // rcx
  __int64 v35; // rcx
  __int64 *v37; // rcx
  __int64 v38; // rcx
  bool v39; // al
  float v40; // xmm3_4
  float v41; // xmm0_4
  float v42; // xmm4_4
  float v43; // xmm8_4
  float v44; // xmm2_4
  float v45; // xmm6_4
  float v46; // xmm7_4
  float v47; // xmm9_4
  __int64 *v48; // rcx
  __int64 v49; // rcx
  __int64 *v51; // rcx
  __int64 v52; // rcx
  __int64 *v54; // rcx
  __int64 v55; // rcx
  __int64 *v57; // rcx
  __int64 v58; // rcx
  __int64 *v60; // rcx
  __int64 v61; // rcx
  __int64 *v63; // rcx
  __int64 v64; // rcx
  __int64 *v66; // rcx
  __int64 v67; // rcx
  __int64 *v69; // rcx
  __int64 v70; // rcx
  int *v72; // rax
  __int64 v73; // rbx
  double v74; // xmm0_8
  double v75; // xmm7_8
  double v76; // xmm1_8
  double v77; // xmm0_8
  double v78; // xmm1_8
  double v79; // xmm0_8
  double v80; // xmm1_8
  __int64 v81; // rcx
  __int64 v82; // rbx
  void *v83; // rdx
  Mso::Memory *v84; // rcx
  unsigned int v85; // ebx
  unsigned __int64 v86; // rdx
  Ofc::CArrayImpl *v87; // rsi
  double v88; // xmm0_8
  __int64 v89; // rbx
  __int64 v90; // rax
  unsigned __int64 *v91; // rax
  unsigned __int64 v92; // rdx
  __int64 *v93; // rcx
  __int64 v94; // rcx
  __int64 *v96; // rcx
  __int64 v97; // rcx
  __int64 v99; // rcx
  unsigned __int64 v100; // rdx
  Art::ExtendedColor *v101; // rcx
  float v102; // xmm0_4
  float v103; // xmm4_4
  float v104; // xmm7_4
  __int32 v105; // xmm2_4
  int *v106; // rax
  float v107; // xmm6_4
  float v108; // xmm8_4
  float v109; // xmm2_4
  float v110; // xmm1_4
  int *v111; // rax
  float v112; // xmm2_4
  float v113; // xmm1_4
  float v114; // xmm2_4
  float v115; // xmm1_4
  float v116; // xmm1_4
  float v117; // xmm7_4
  float v118; // xmm6_4
  int *v119; // rax
  float v120; // xmm1_4
  bool v121; // cc
  __int64 v122; // rdi
  unsigned int v123; // r8d
  int *v124; // rax
  float v125; // xmm0_4
  float v126; // xmm0_4
  int *v127; // rax
  int *v128; // rax
  int *v129; // rax
  int *v130; // rax
  float v131; // xmm0_4
  int *v132; // rax
  int *v133; // rax
  float v134; // xmm2_4
  int *v135; // rax
  int *v136; // rax
  float v137; // xmm0_4
  int *v138; // rax
  int *v139; // rax
  float v140; // xmm0_4
  void *v141; // rdx
  int *v142; // rax
  int *v143; // rax
  int *v144; // rax
  int *v145; // rax
  int *v146; // rax
  unsigned __int64 v147; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 v148; // [rsp+40h] [rbp-C8h]
  Art::ExtendedColor *v149; // [rsp+48h] [rbp-C0h]
  __int64 v150; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v151; // [rsp+58h] [rbp-B0h]
  Mso::Memory *v152; // [rsp+68h] [rbp-A0h] BYREF
  int v153; // [rsp+70h] [rbp-98h]
  int v154; // [rsp+74h] [rbp-94h]
  int v155; // [rsp+78h] [rbp-90h]
  int v156; // [rsp+7Ch] [rbp-8Ch]
  int v157; // [rsp+80h] [rbp-88h]

  v12 = ((__int64 (*)(void))Art::Color::GetTransformListRef)();
  if ( !*(_DWORD *)(v12 + 16) )
    return;
  v147 = 0;
  v13 = *((_QWORD *)this + 1);
  v148 = v13;
  if ( v13 <= 1 )
    v148 = 0;
  else
    (*(void (__fastcall **)(unsigned __int64 *, Art::Color *))(v13 + 8))(&v147, this);
  v149 = 0;
  if ( *((_QWORD *)this + 2) )
  {
    v153 = -1;
    v154 = -1;
    v155 = -1;
    v156 = -1;
    v152 = 0;
    v157 = 0x20000000;
    Art::Color::GetExtendedColor(this, (struct Art::ExtendedColor *)&v152);
    Art::Color::SetExtendedColor((Art::Color *)&v147, (const struct Art::ExtendedColor *)&v152);
    if ( v152 )
      Mso::Memory::Free(v152, v141);
  }
  TransformListRef = Art::Color::GetTransformListRef(&v147);
  Ofc::TDestructRange<Art::GvmlGroupShapeData::Child_<0>,0>::Do(
    *(unsigned __int8 **)(TransformListRef + 8),
    *(_DWORD *)(TransformListRef + 16));
  v16 = *(Mso::Memory **)(TransformListRef + 8);
  if ( v16 )
    Mso::Memory::Free(v16, v15);
  *(_QWORD *)(TransformListRef + 8) = 0;
  *(_DWORD *)(TransformListRef + 20) &= 0x80000000;
  *(_DWORD *)(TransformListRef + 16) = 0;
  *(_DWORD *)TransformListRef = 0;
  Art::Color::ConvertTo<Art::Clr::ScRgb>(&v147);
  v17 = (int *)Ofc::TChoice<Art::ColorDataChoiceIDsImpl>::GetPtr<Art::Clr::ScRgb>(&v147);
  if ( !v17 )
  {
    Ofc::CInvalidParamException::ThrowTag(0x66356D62u);
    goto LABEL_308;
  }
  v7 = DOUBLE_1000_0;
  v8 = DOUBLE_100_0;
  v19 = (double)v17[6] / 1000.0 / 100.0;
  v3 = (double)v17[7] / 1000.0 / 100.0;
  v4 = (double)v17[8] / 1000.0 / 100.0;
  if ( v149 )
    Art::ExtendedColor::`scalar deleting destructor'(v149, v18);
  if ( v148 > 1 )
    (*(void (__fastcall **)(unsigned __int64 *))(v148 + 16))(&v147);
  *(float *)&v20 = Art::Color::GetAlpha(this);
  v147 = __PAIR64__(LODWORD(v3), LODWORD(v19));
  v148 = __PAIR64__(v20, LODWORD(v4));
  v1 = 0;
  v2 = &Ofc::TypeInfo::s_moduleTag;
  v6 = FLOAT_1_0;
  v5 = 0.0;
  v10 = FLOAT_0_5;
  v9 = FLOAT_0_66666669;
  while ( v1 < *(_DWORD *)(v12 + 16) )
  {
    v21 = *(_QWORD *)(v12 + 8) + 16LL * v1;
    v22 = *(__int64 **)(v21 + 8);
    if ( (unsigned __int64)v22 <= 1
      || (v23 = *v22, (struct Art::Clr::Tint **)v23 == &Ofc::TypeInfoImpl<Art::Clr::Tint>::c_typeInfo)
      || *(const int **)(v23 + 8) != v2
      && !(unsigned int)__std_type_info_compare(*(_QWORD *)v23 + 8LL, &qword_180E1AE70) )
    {
      v111 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Tint>(v21);
      if ( !v111 )
        goto LABEL_324;
      v112 = v6 - (float)((double)*v111 / v7 / v8);
      if ( v112 <= v5 )
      {
        v134 = v112 + v6;
        v19 = v19 * v134;
        *(float *)&v147 = v19;
        v3 = v3 * v134;
        *((float *)&v147 + 1) = v3;
        v4 = v4 * v134;
      }
      else
      {
        v19 = (float)((float)(v6 - v112) * v19) + v112;
        *(float *)&v147 = v19;
        v3 = (float)((float)(v6 - v112) * v3) + v112;
        *((float *)&v147 + 1) = v3;
        v4 = (float)((float)(v6 - v112) * v4) + v112;
      }
LABEL_194:
      *(float *)&v148 = v4;
      goto LABEL_98;
    }
    v25 = *(__int64 **)(v21 + 8);
    if ( (unsigned __int64)v25 > 1 )
    {
      v26 = *v25;
      if ( (struct Art::Clr::Shade **)v26 == &Ofc::TypeInfoImpl<Art::Clr::Shade>::c_typeInfo
        || *(const int **)(v26 + 8) != v2
        && !(unsigned int)__std_type_info_compare(*(_QWORD *)v26 + 8LL, &qword_180E1AD70) )
      {
        v119 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Shade>(v21);
        if ( !v119 )
          goto LABEL_324;
        v120 = (double)*v119 / v7 / v8;
        v19 = v19 * v120;
        *(float *)&v147 = v19;
        v3 = v3 * v120;
        *((float *)&v147 + 1) = v3;
        v4 = v4 * v120;
        *(float *)&v148 = v4;
        if ( v5 > v19 )
        {
          v19 = v5;
        }
        else
        {
          if ( v19 <= v6 )
            goto LABEL_222;
LABEL_308:
          v19 = v6;
        }
        *(float *)&v147 = v19;
LABEL_222:
        if ( v5 > v3 )
        {
          v3 = v5;
        }
        else
        {
          if ( v3 <= v6 )
          {
LABEL_224:
            if ( v5 > v4 )
              goto LABEL_267;
            v121 = v4 <= v6;
            goto LABEL_226;
          }
          v3 = v6;
        }
        *((float *)&v147 + 1) = v3;
        goto LABEL_224;
      }
    }
    v28 = *(__int64 **)(v21 + 8);
    if ( (unsigned __int64)v28 <= 1
      || (v29 = *v28, (struct Art::Clr::Alpha **)v29 != &Ofc::TypeInfoImpl<Art::Clr::Alpha>::c_typeInfo)
      && (*(const int **)(v29 + 8) == v2 || (unsigned int)__std_type_info_compare(
                                                            *(_QWORD *)v29 + 8LL,
                                                            &qword_180E1AE48)) )
    {
      v31 = *(__int64 **)(v21 + 8);
      if ( (unsigned __int64)v31 <= 1
        || (v32 = *v31, (struct Art::Clr::AlphaOffset **)v32 != &Ofc::TypeInfoImpl<Art::Clr::AlphaOffset>::c_typeInfo)
        && (*(const int **)(v32 + 8) == v2
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v32 + 8LL, &qword_180E1B290)) )
      {
        v34 = *(__int64 **)(v21 + 8);
        if ( (unsigned __int64)v34 <= 1
          || (v35 = *v34,
              (struct Art::Clr::AlphaModulate **)v35 != &Ofc::TypeInfoImpl<Art::Clr::AlphaModulate>::c_typeInfo)
          && (*(const int **)(v35 + 8) == v2
           || (unsigned int)__std_type_info_compare(*(_QWORD *)v35 + 8LL, &qword_180E1AD40)) )
        {
          v37 = *(__int64 **)(v21 + 8);
          v39 = 0;
          if ( (unsigned __int64)v37 > 1 )
          {
            v38 = *v37;
            if ( (struct Art::Clr::Saturation **)v38 == &Ofc::TypeInfoImpl<Art::Clr::Saturation>::c_typeInfo
              || *(const int **)(v38 + 8) != v2
              && !(unsigned int)__std_type_info_compare(*(_QWORD *)v38 + 8LL, &qword_180E1AEC0) )
            {
              v39 = 1;
            }
          }
          if ( v39
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::SaturationOffset>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::SaturationModulate>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Luminance>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::LuminanceOffset>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::LuminanceModulate>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Hue>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::HueOffset>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::HueModulate>(v21)
            || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Complement>(v21) )
          {
            GEL::Color::scRGB_To_sRGB((GEL::Color *)&v147);
            v40 = fmaxf(fmaxf(*(float *)&v147, *((float *)&v147 + 1)), *(float *)&v148);
            v41 = fminf(fminf(*(float *)&v147, *((float *)&v147 + 1)), *(float *)&v148);
            v42 = v41 + v40;
            v43 = (float)(v41 + v40) * v10;
            v44 = v40 - v41;
            if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(v40 - v41) & _xmm) >= 0.00000023841858 )
            {
              if ( v10 >= v43 )
                v45 = v44 / v42;
              else
                v45 = v44 / (float)(2.0 - v42);
              v102 = (float)((float)(v40 - *(float *)&v147) * 0.16666667) / v44;
              v103 = (float)((float)(v40 - *((float *)&v147 + 1)) * 0.16666667) / v44;
              v47 = FLOAT_0_16666667;
              v104 = (float)((float)(v40 - *(float *)&v148) * 0.16666667) / v44;
              COERCE_FLOAT(v105 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
              v9 = FLOAT_0_66666669;
              if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v147 - v40) & v105) < 0.00000023841858 )
              {
                v46 = v104 - v103;
              }
              else if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)&v147 + 1) - v40) & v105) < 0.00000023841858 )
              {
                v46 = (float)(v102 + 0.33333334) - v104;
              }
              else
              {
                v46 = (float)(v103 + 0.66666669) - v102;
              }
              if ( v5 > v46 )
                v46 = v46 + v6;
              if ( v46 > v6 )
                v46 = v46 + -1.0;
            }
            else
            {
              v45 = v5;
              v46 = FLOAT_N1_0;
              v47 = FLOAT_0_16666667;
            }
            v48 = *(__int64 **)(v21 + 8);
            if ( (unsigned __int64)v48 > 1 )
            {
              v49 = *v48;
              if ( (struct Art::Clr::Hue **)v49 == &Ofc::TypeInfoImpl<Art::Clr::Hue>::c_typeInfo
                || *(const int **)(v49 + 8) != v2
                && !(unsigned int)__std_type_info_compare(*(_QWORD *)v49 + 8LL, &qword_180E1AE98) )
              {
                v128 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Hue>(v21);
                if ( !v128 )
                  goto LABEL_324;
                v125 = (float)((double)*v128 / 60000.0) / 360.0;
                goto LABEL_233;
              }
            }
            v51 = *(__int64 **)(v21 + 8);
            if ( (unsigned __int64)v51 > 1 )
            {
              v52 = *v51;
              if ( (struct Art::Clr::HueOffset **)v52 == &Ofc::TypeInfoImpl<Art::Clr::HueOffset>::c_typeInfo
                || *(const int **)(v52 + 8) != v2
                && !(unsigned int)__std_type_info_compare(*(_QWORD *)v52 + 8LL, &qword_180E1AB88) )
              {
                v124 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::HueOffset>(v21);
                if ( !v124 )
                  goto LABEL_324;
                v125 = (float)((float)((double)*v124 / 60000.0) / 360.0) + v46;
                goto LABEL_233;
              }
            }
            v54 = *(__int64 **)(v21 + 8);
            if ( (unsigned __int64)v54 > 1 )
            {
              v55 = *v54;
              if ( (struct Art::Clr::HueModulate **)v55 == &Ofc::TypeInfoImpl<Art::Clr::HueModulate>::c_typeInfo
                || *(const int **)(v55 + 8) != v2
                && !(unsigned int)__std_type_info_compare(*(_QWORD *)v55 + 8LL, &qword_180E1ACA8) )
              {
                v133 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::HueModulate>(v21);
                if ( !v133 )
                  goto LABEL_324;
                v125 = (float)((double)*v133 / v7 / v8) * v46;
                goto LABEL_233;
              }
            }
            v57 = *(__int64 **)(v21 + 8);
            if ( (unsigned __int64)v57 > 1
              && ((v58 = *v57,
                   (struct Art::Clr::Saturation **)v58 == &Ofc::TypeInfoImpl<Art::Clr::Saturation>::c_typeInfo)
               || *(const int **)(v58 + 8) != v2
               && !(unsigned int)__std_type_info_compare(*(_QWORD *)v58 + 8LL, &qword_180E1AEC0)) )
            {
              v138 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Saturation>(v21);
              if ( !v138 )
                goto LABEL_324;
              v45 = (double)*v138 / v7 / v8;
            }
            else
            {
              v60 = *(__int64 **)(v21 + 8);
              if ( (unsigned __int64)v60 > 1
                && ((v61 = *v60,
                     (struct Art::Clr::SaturationOffset **)v61 == &Ofc::TypeInfoImpl<Art::Clr::SaturationOffset>::c_typeInfo)
                 || *(const int **)(v61 + 8) != v2
                 && !(unsigned int)__std_type_info_compare(*(_QWORD *)v61 + 8LL, &qword_180E1AB30)) )
              {
                v127 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::SaturationOffset>(v21);
                if ( !v127 )
                  goto LABEL_324;
                v45 = v45 + (float)((double)*v127 / v7 / v8);
              }
              else
              {
                v63 = *(__int64 **)(v21 + 8);
                if ( (unsigned __int64)v63 > 1
                  && ((v64 = *v63,
                       (struct Art::Clr::SaturationModulate **)v64 == &Ofc::TypeInfoImpl<Art::Clr::SaturationModulate>::c_typeInfo)
                   || *(const int **)(v64 + 8) != v2
                   && !(unsigned int)__std_type_info_compare(*(_QWORD *)v64 + 8LL, &qword_180E1AD08)) )
                {
                  v129 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::SaturationModulate>(v21);
                  if ( !v129 )
                    goto LABEL_324;
                  v45 = v45 * (float)((double)*v129 / v7 / v8);
                }
                else
                {
                  v66 = *(__int64 **)(v21 + 8);
                  if ( (unsigned __int64)v66 > 1
                    && ((v67 = *v66,
                         (struct Art::Clr::Luminance **)v67 == &Ofc::TypeInfoImpl<Art::Clr::Luminance>::c_typeInfo)
                     || *(const int **)(v67 + 8) != v2
                     && !(unsigned int)__std_type_info_compare(*(_QWORD *)v67 + 8LL, &qword_180E1AE20)) )
                  {
                    v132 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Luminance>(v21);
                    if ( !v132 )
                      goto LABEL_324;
                    v43 = (double)*v132 / v7 / v8;
                  }
                  else
                  {
                    v69 = *(__int64 **)(v21 + 8);
                    if ( (unsigned __int64)v69 <= 1
                      || (v70 = *v69,
                          (struct Art::Clr::LuminanceOffset **)v70 != &Ofc::TypeInfoImpl<Art::Clr::LuminanceOffset>::c_typeInfo)
                      && (*(const int **)(v70 + 8) == v2
                       || (unsigned int)__std_type_info_compare(*(_QWORD *)v70 + 8LL, &qword_180E1AD98)) )
                    {
                      if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::LuminanceModulate>(v21) )
                      {
                        v72 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::LuminanceModulate>(v21);
                        if ( !v72 )
                          goto LABEL_324;
                        v43 = v43 * (float)((double)*v72 / v7 / v8);
                        goto LABEL_94;
                      }
                      if ( !(unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Complement>(v21) )
                        goto LABEL_94;
                      v125 = v46 + v10;
LABEL_233:
                      v126 = fmodf_0(v125, v6);
                      v46 = fmodf_0(v126 + v6, v6);
                      goto LABEL_94;
                    }
                    v106 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::LuminanceOffset>(v21);
                    if ( !v106 )
                      goto LABEL_324;
                    v43 = v43 + (float)((double)*v106 / v7 / v8);
                  }
                }
              }
            }
LABEL_94:
            if ( v45 == v5 )
            {
              *(float *)&v148 = v43;
              *((float *)&v147 + 1) = v43;
              *(float *)&v147 = v43;
              goto LABEL_96;
            }
            if ( v10 < v43 )
              v107 = (float)(v43 + v45) - (float)(v43 * v45);
            else
              v107 = (float)(v45 + v6) * v43;
            v108 = (float)(v43 + v43) - v107;
            v109 = v46 + 0.33333334;
            if ( v5 > (float)(v46 + 0.33333334) )
              v109 = v109 + v6;
            if ( v109 > v6 )
              v109 = v109 + -1.0;
            if ( v47 > v109 )
            {
              v113 = (float)(v107 - v108) * v109;
              goto LABEL_196;
            }
            if ( v10 > v109 )
            {
              v110 = v107;
            }
            else
            {
              if ( v9 <= v109 )
              {
                v110 = v108;
                goto LABEL_197;
              }
              v113 = (float)(v107 - v108) * (float)(v9 - v109);
LABEL_196:
              v110 = (float)(v113 * 6.0) + v108;
            }
LABEL_197:
            *(float *)&v147 = v110;
            v114 = v46;
            if ( v5 > v46 )
              v114 = v46 + v6;
            if ( v114 > v6 )
              v114 = v114 + -1.0;
            if ( v47 > v114 )
            {
              v116 = (float)(v107 - v108) * v114;
              goto LABEL_206;
            }
            if ( v10 > v114 )
            {
              v115 = v107;
            }
            else
            {
              if ( v9 <= v114 )
              {
                v115 = v108;
                goto LABEL_207;
              }
              v116 = (float)(v107 - v108) * (float)(v9 - v114);
LABEL_206:
              v115 = (float)(v116 * 6.0) + v108;
            }
LABEL_207:
            *((float *)&v147 + 1) = v115;
            v117 = v46 - 0.33333334;
            if ( v5 > v117 )
              v117 = v117 + v6;
            if ( v117 > v6 )
              v117 = v117 + -1.0;
            if ( v47 > v117 )
            {
              v118 = (float)(v107 - v108) * v117;
            }
            else
            {
              if ( v10 > v117 )
                goto LABEL_217;
              if ( v9 <= v117 )
              {
                v107 = v108;
                goto LABEL_217;
              }
              v118 = (float)(v107 - v108) * (float)(v9 - v117);
            }
            v107 = (float)(v118 * 6.0) + v108;
LABEL_217:
            *(float *)&v148 = v107;
LABEL_96:
            GEL::Color::sRGB_To_scRGB((GEL::Color *)&v147);
LABEL_97:
            LODWORD(v4) = v148;
            v3 = *((float *)&v147 + 1);
            LODWORD(v19) = v147;
            goto LABEL_98;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Inverse>(v21) )
          {
            v19 = v6 - v19;
            *(float *)&v147 = v19;
            v3 = v6 - v3;
            *((float *)&v147 + 1) = v3;
            v4 = v6 - v4;
            *(float *)&v148 = v4;
            goto LABEL_98;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Grayscale>(v21) )
          {
            GEL::Color::scRGB_To_sRGB((GEL::Color *)&v147);
            *(float *)&v148 = (float)((float)(*(float *)&v147 * 0.21265601) + (float)(*((float *)&v147 + 1) * 0.71515799))
                            + (float)(*(float *)&v148 * 0.072185598);
            HIDWORD(v147) = v148;
            LODWORD(v147) = v148;
            goto LABEL_96;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Red>(v21) )
          {
            v135 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Red>(v21);
            if ( !v135 )
              goto LABEL_324;
            v19 = (double)*v135 / v7 / v8;
            goto LABEL_282;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::RedOffset>(v21) )
          {
            v139 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::RedOffset>(v21);
            if ( !v139 )
              goto LABEL_324;
            v140 = (float)((double)*v139 / v7 / v8) + v19;
LABEL_301:
            *(float *)&v147 = v140;
            v19 = v140;
            if ( v5 > v140 )
            {
              v19 = v5;
              goto LABEL_282;
            }
            if ( v140 > v6 )
            {
              v19 = v6;
LABEL_282:
              *(float *)&v147 = v19;
              goto LABEL_98;
            }
            goto LABEL_98;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::RedModulate>(v21) )
          {
            v142 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::RedModulate>(v21);
            if ( !v142 )
              goto LABEL_324;
            v140 = (float)((double)*v142 / v7 / v8) * v19;
            goto LABEL_301;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Green>(v21) )
          {
            v143 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Green>(v21);
            if ( !v143 )
              goto LABEL_324;
            v3 = (double)*v143 / v7 / v8;
            goto LABEL_298;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::GreenOffset>(v21) )
          {
            v136 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::GreenOffset>(v21);
            if ( !v136 )
              goto LABEL_324;
            v137 = (float)((double)*v136 / v7 / v8) + v3;
LABEL_286:
            *((float *)&v147 + 1) = v137;
            v3 = v137;
            if ( v5 > v137 )
            {
              v3 = v5;
            }
            else
            {
              if ( v137 <= v6 )
                goto LABEL_98;
              v3 = v6;
            }
LABEL_298:
            *((float *)&v147 + 1) = v3;
            goto LABEL_98;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::GreenModulate>(v21) )
          {
            v144 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::GreenModulate>(v21);
            if ( !v144 )
              goto LABEL_324;
            v137 = (float)((double)*v144 / v7 / v8) * v3;
            goto LABEL_286;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Blue>(v21) )
          {
            v145 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::Blue>(v21);
            if ( !v145 )
              goto LABEL_324;
            v4 = (double)*v145 / v7 / v8;
            goto LABEL_194;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::BlueOffset>(v21) )
          {
            v130 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::BlueOffset>(v21);
            if ( !v130 )
              goto LABEL_324;
            v131 = (float)((double)*v130 / v7 / v8) + v4;
            goto LABEL_266;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::BlueModulate>(v21) )
          {
            v146 = (int *)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::GetPtr<Art::Clr::BlueModulate>(v21);
            if ( !v146 )
            {
LABEL_324:
              Ofc::CInvalidParamException::ThrowTag(0x66356D62u);
              __debugbreak();
            }
            v131 = (float)((double)*v146 / v7 / v8) * v4;
LABEL_266:
            *(float *)&v148 = v131;
            v4 = v131;
            if ( v5 > v131 )
            {
LABEL_267:
              v4 = v5;
              *(float *)&v148 = v5;
              goto LABEL_98;
            }
            v121 = v131 <= v6;
LABEL_226:
            if ( !v121 )
            {
              v4 = v6;
              *(float *)&v148 = v6;
            }
            goto LABEL_98;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Gamma>(v21) )
          {
            GEL::Color::scRGB_To_sRGB((GEL::Color *)&v147);
            goto LABEL_97;
          }
          if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::InverseGamma>(v21) )
            goto LABEL_96;
          MsoShipAssertTagProc(507826460);
        }
      }
    }
LABEL_98:
    ++v1;
  }
  v150 = 0;
  v151 = 0;
  v73 = Ofc::TChoice<Art::ColorDataChoiceIDsImpl>::SwitchTo<Art::Clr::ScRgb>(&v150);
  v74 = v19 * v8 * v7;
  v75 = DOUBLE_0_5;
  if ( v74 < 0.0 )
    v76 = DOUBLE_N0_5;
  else
    v76 = DOUBLE_0_5;
  *(_DWORD *)(v73 + 24) = (int)(v74 + v76);
  v77 = v3 * v8 * v7;
  if ( v77 < 0.0 )
    v78 = DOUBLE_N0_5;
  else
    v78 = DOUBLE_0_5;
  *(_DWORD *)(v73 + 28) = (int)(v77 + v78);
  v79 = v4 * v8 * v7;
  if ( v79 < 0.0 )
    v80 = DOUBLE_N0_5;
  else
    v80 = DOUBLE_0_5;
  *(_DWORD *)(v73 + 32) = (int)(v79 + v80);
  v81 = *(_QWORD *)(v73 + 40);
  if ( v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  *(_QWORD *)(v73 + 40) = 0;
  v82 = Art::Color::GetTransformListRef(&v150);
  Ofc::TDestructRange<Art::GvmlGroupShapeData::Child_<0>,0>::Do(*(unsigned __int8 **)(v82 + 8), *(_DWORD *)(v82 + 16));
  v84 = *(Mso::Memory **)(v82 + 8);
  if ( v84 )
    Mso::Memory::Free(v84, v83);
  *(_QWORD *)(v82 + 8) = 0;
  *(_DWORD *)(v82 + 20) &= 0x80000000;
  *(_DWORD *)(v82 + 16) = 0;
  *(_DWORD *)v82 = 0;
  if ( *((_QWORD *)&v151 + 1) )
    Art::ExtendedColor::`scalar deleting destructor'(*((Art::ExtendedColor **)&v151 + 1), (unsigned int)v83);
  *((_QWORD *)&v151 + 1) = 0;
  v85 = 0;
  v87 = (Ofc::CArrayImpl *)(Art::Color::GetTransformListRef(&v150) + 8);
  while ( v85 < *((_DWORD *)v87 + 2) )
  {
    v122 = *(_QWORD *)v87 + 16LL * v85;
    if ( (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Alpha>(v122)
      || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::AlphaOffset>(v122)
      || (unsigned __int8)Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::AlphaModulate>(v122) )
    {
      v123 = v85--;
      Ofc::CArrayImpl::DeleteAt(
        v87,
        0x10u,
        v123,
        1u,
        (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<Art::InkActionDataData::TraceChoice_<0>,1>::Do,
        Ofc::TDestructRange<Art::GvmlGroupShapeData::Child_<0>,0>::Do);
    }
    ++v85;
  }
  if ( *((float *)&v148 + 1) != v6 )
  {
    v88 = *((float *)&v148 + 1) * v8 * v7;
    if ( v88 < 0.0 )
      v75 = DOUBLE_N0_5;
    v89 = (unsigned int)(int)(v88 + v75);
    Ofc::TRangeRestricted<Art::Percentage,Art::PosFixedPercentageRange>::Validate(v89);
    v90 = Art::Color::GetTransformListRef(&v150);
    v91 = (unsigned __int64 *)Art::NewColorTransform(v90);
    v147 = (unsigned int)v89;
    v92 = *v91;
    *v91 = (unsigned int)v89;
    v147 = v92;
    v86 = v91[1];
    v91[1] = (unsigned __int64)&off_180AC0560;
    v148 = v86;
    if ( v86 > 1 )
      (*(void (__fastcall **)(unsigned __int64 *))(v86 + 16))(&v147);
  }
  if ( *((_QWORD *)&v151 + 1) )
    Art::ExtendedColor::`scalar deleting destructor'(*((Art::ExtendedColor **)&v151 + 1), v86);
  *((_QWORD *)&v151 + 1) = 0;
  v93 = (__int64 *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)v93 > 1
    && ((v94 = *v93, (struct Art::Clr::Hsl **)v94 == &Ofc::TypeInfoImpl<Art::Clr::Hsl>::c_typeInfo)
     || *(const int **)(v94 + 8) != v2 && !(unsigned int)__std_type_info_compare(*(_QWORD *)v94 + 8LL, &qword_180E13D50)) )
  {
    Art::Color::ConvertTo<Art::Clr::Hsl>(&v150);
  }
  else
  {
    v96 = (__int64 *)*((_QWORD *)this + 1);
    if ( (unsigned __int64)v96 > 1 )
    {
      v97 = *v96;
      if ( (struct Art::Clr::SRgb **)v97 == &Ofc::TypeInfoImpl<Art::Clr::SRgb>::c_typeInfo
        || *(const int **)(v97 + 8) != v2
        && !(unsigned int)__std_type_info_compare(*(_QWORD *)v97 + 8LL, &qword_180E13CB0) )
      {
        Art::Color::ConvertTo<Art::Clr::SRgb>(&v150);
      }
    }
  }
  v99 = *(_QWORD *)this;
  *(_QWORD *)this = v150;
  v150 = v99;
  v100 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v151;
  *(_QWORD *)&v151 = v100;
  v101 = (Art::ExtendedColor *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = *((_QWORD *)&v151 + 1);
  *((_QWORD *)&v151 + 1) = v101;
  if ( v101 )
  {
    Art::ExtendedColor::`scalar deleting destructor'(v101, v100);
    v100 = v151;
  }
  if ( v100 > 1 )
    (*(void (__fastcall **)(__int64 *))(v100 + 16))(&v150);
}

```

## disassembly

```asm
0x18000f650  mov     rax, rsp
0x18000f653  mov     [rax+8], rbx
0x18000f657  mov     [rax+10h], rsi
0x18000f65b  mov     [rax+18h], rdi
0x18000f65f  push    rbp
0x18000f660  push    r12
0x18000f662  push    r13
0x18000f664  push    r14
0x18000f666  push    r15
0x18000f668  lea     rbp, [rax-48h]
0x18000f66c  sub     rsp, 120h
0x18000f673  movaps  xmmword ptr [rax-38h], xmm6
0x18000f677  movaps  xmmword ptr [rax-48h], xmm7
0x18000f67b  movaps  xmmword ptr [rax-58h], xmm8
0x18000f680  movaps  xmmword ptr [rax-68h], xmm9
0x18000f685  movaps  xmmword ptr [rax-78h], xmm10
0x18000f68a  movaps  xmmword ptr [rax-88h], xmm11
0x18000f692  movaps  xmmword ptr [rax-98h], xmm12
0x18000f69a  movaps  xmmword ptr [rax-0A8h], xmm13
0x18000f6a2  movaps  xmmword ptr [rax-0B8h], xmm14
0x18000f6aa  movaps  xmmword ptr [rax-0C8h], xmm15
0x18000f6b2  mov     r14, rcx
0x18000f6b5  call    ?GetTransformListRef@Color@Art@@AEAAAEAV?$TVector@VColorTransform@Art@@$0A@$0PPPPPPPP@@Ofc@@XZ; Art::Color::GetTransformListRef(void)
0x18000f6ba  mov     rdi, rax
0x18000f6bd  xor     r15d, r15d
0x18000f6c0  cmp     [rax+10h], r15d
0x18000f6c4  jnz     short loc_18000F71F
0x18000f6c6  lea     r11, [rsp+140h+var_20]
0x18000f6ce  mov     rbx, [r11+30h]
0x18000f6d2  mov     rsi, [r11+38h]
0x18000f6d6  mov     rdi, [r11+40h]
0x18000f6da  movaps  xmm6, xmmword ptr [r11-10h]
0x18000f6df  movaps  xmm7, xmmword ptr [r11-20h]
0x18000f6e4  movaps  xmm8, xmmword ptr [r11-30h]
0x18000f6e9  movaps  xmm9, xmmword ptr [r11-40h]
0x18000f6ee  movaps  xmm10, xmmword ptr [r11-50h]
0x18000f6f3  movaps  xmm11, xmmword ptr [r11-60h]
0x18000f6f8  movaps  xmm12, xmmword ptr [r11-70h]
0x18000f6fd  movaps  xmm13, xmmword ptr [r11-80h]
0x18000f702  movaps  xmm14, xmmword ptr [r11-90h]
0x18000f70a  movaps  xmm15, xmmword ptr [r11-0A0h]
0x18000f712  mov     rsp, r11
0x18000f715  pop     r15
0x18000f717  pop     r14
0x18000f719  pop     r13
0x18000f71b  pop     r12
0x18000f71d  pop     rbp
0x18000f71e  retn
0x18000f71f  xor     eax, eax
0x18000f721  mov     [rsp+140h+var_110], rax
0x18000f726  mov     rax, [r14+8]
0x18000f72a  mov     [rsp+140h+var_108], rax
0x18000f72f  mov     r12d, 1
0x18000f735  cmp     rax, r12
0x18000f738  jbe     loc_18001056C
0x18000f73e  mov     rdx, r14
0x18000f741  lea     rcx, [rsp+140h+var_110]
0x18000f746  mov     rax, [rax+8]
0x18000f74a  call    cs:__guard_dispatch_icall_fptr
0x18000f750  nop
0x18000f751  mov     [rsp+140h+var_100], r15
0x18000f756  or      eax, 0FFFFFFFFh
0x18000f759  cmp     [r14+10h], r15
0x18000f75d  jnz     loc_180010A9A
0x18000f763  lea     rcx, [rsp+140h+var_110]
0x18000f768  call    ?GetTransformListRef@Color@Art@@AEAAAEAV?$TVector@VColorTransform@Art@@$0A@$0PPPPPPPP@@Ofc@@XZ; Art::Color::GetTransformListRef(void)
0x18000f76d  mov     rbx, rax
0x18000f770  mov     edx, [rax+10h]; unsigned int
0x18000f773  mov     rcx, [rax+8]; unsigned __int8 *
0x18000f777  call    ?Do@?$TDestructRange@V?$Child_@$0A@@GvmlGroupShapeData@Art@@$0A@@Ofc@@SAXPEAEK@Z; Ofc::TDestructRange<Art::GvmlGroupShapeData::Child_<0>,0>::Do(uchar *,ulong)
0x18000f77c  mov     rcx, [rbx+8]
0x18000f780  test    rcx, rcx
0x18000f783  jz      short loc_18000F78B
0x18000f785  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18000f78b  mov     [rbx+8], r15
0x18000f78f  and     dword ptr [rbx+14h], 80000000h
0x18000f796  mov     [rbx+10h], r15d
0x18000f79a  mov     [rbx], r15d
0x18000f79d  lea     rcx, [rsp+140h+var_110]
0x18000f7a2  call    ??$ConvertTo@UScRgb@Clr@Art@@@Color@Art@@AEAAXXZ; Art::Color::ConvertTo<Art::Clr::ScRgb>(void)
0x18000f7a7  lea     rcx, [rsp+140h+var_110]
0x18000f7ac  call    ??$GetPtr@UScRgb@Clr@Art@@@?$TChoice@VColorDataChoiceIDsImpl@Art@@@Ofc@@QEAAPEAVScRgbColor@Art@@XZ; Ofc::TChoice<Art::ColorDataChoiceIDsImpl>::GetPtr<Art::Clr::ScRgb>(void)
0x18000f7b1  test    rax, rax
0x18000f7b4  jz      loc_180010AF6
0x18000f7ba  xorps   xmm0, xmm0
0x18000f7bd  cvtsi2sd xmm0, dword ptr [rax+18h]
0x18000f7c2  movsd   xmm12, cs:__real@408f400000000000
0x18000f7cb  divsd   xmm0, xmm12
0x18000f7d0  movsd   xmm13, cs:__real@4059000000000000
0x18000f7d9  divsd   xmm0, xmm13
0x18000f7de  cvtpd2ps xmm7, xmm0
0x18000f7e2  xorps   xmm0, xmm0
0x18000f7e5  cvtsi2sd xmm0, dword ptr [rax+1Ch]
0x18000f7ea  divsd   xmm0, xmm12
0x18000f7ef  divsd   xmm0, xmm13
0x18000f7f4  cvtpd2ps xmm6, xmm0
0x18000f7f8  xorps   xmm1, xmm1
0x18000f7fb  cvtsi2sd xmm1, dword ptr [rax+20h]
0x18000f800  divsd   xmm1, xmm12
0x18000f805  divsd   xmm1, xmm13
0x18000f80a  cvtpd2ps xmm8, xmm1
0x18000f80f  mov     rcx, [rsp+140h+var_100]; this
0x18000f814  test    rcx, rcx
0x18000f817  jnz     loc_180010A37
0x18000f81d  mov     rax, [rsp+140h+var_108]
0x18000f822  cmp     rax, r12
0x18000f825  jbe     short loc_18000F837
0x18000f827  lea     rcx, [rsp+140h+var_110]
0x18000f82c  mov     rax, [rax+10h]
0x18000f830  call    cs:__guard_dispatch_icall_fptr
0x18000f836  nop
0x18000f837  mov     rcx, r14; this
0x18000f83a  call    ?GetAlpha@Color@Art@@QEBAMXZ; Art::Color::GetAlpha(void)
0x18000f83f  movss   dword ptr [rsp+140h+var_110], xmm7
0x18000f845  movss   dword ptr [rsp+140h+var_110+4], xmm6
0x18000f84b  movss   dword ptr [rsp+140h+var_108], xmm8
0x18000f852  movss   dword ptr [rsp+140h+var_108+4], xmm0
0x18000f858  mov     esi, r15d
0x18000f85b  lea     r13, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18000f862  movss   xmm11, cs:__real@3f800000
0x18000f86b  xorps   xmm10, xmm10
0x18000f86f  movss   xmm15, cs:__real@3f000000
0x18000f878  movss   xmm14, cs:__real@3f2aaaab
0x18000f881  cmp     esi, [rdi+10h]
0x18000f884  jnb     loc_18000FC84
0x18000f88a  mov     ebx, esi
0x18000f88c  shl     rbx, 4
0x18000f890  add     rbx, [rdi+8]
0x18000f894  mov     rcx, [rbx+8]
0x18000f898  cmp     rcx, r12
0x18000f89b  jbe     loc_18000FFDA
0x18000f8a1  mov     rcx, [rcx]
0x18000f8a4  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UTint@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::Tint>::c_typeInfo
0x18000f8ab  cmp     rcx, rax
0x18000f8ae  jz      loc_18000FFDA
0x18000f8b4  cmp     [rcx+8], r13
0x18000f8b8  jnz     loc_18000FFBE
0x18000f8be  mov     al, r15b
0x18000f8c1  test    al, al
0x18000f8c3  jnz     loc_1800102C8
0x18000f8c9  mov     rcx, [rbx+8]
0x18000f8cd  cmp     rcx, r12
0x18000f8d0  jbe     short loc_18000F8EF
0x18000f8d2  mov     rcx, [rcx]
0x18000f8d5  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UShade@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::Shade>::c_typeInfo
0x18000f8dc  cmp     rcx, rax
0x18000f8df  jz      loc_1800100D6
0x18000f8e5  cmp     [rcx+8], r13
0x18000f8e9  jnz     loc_1800100BA
0x18000f8ef  mov     al, r15b
0x18000f8f2  test    al, al
0x18000f8f4  jnz     loc_18001043B
0x18000f8fa  mov     rcx, [rbx+8]
0x18000f8fe  cmp     rcx, r12
0x18000f901  jbe     short loc_18000F920
0x18000f903  mov     rcx, [rcx]
0x18000f906  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UAlpha@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::Alpha>::c_typeInfo
0x18000f90d  cmp     rcx, rax
0x18000f910  jz      loc_18001008E
0x18000f916  cmp     [rcx+8], r13
0x18000f91a  jnz     loc_180010072
0x18000f920  mov     al, r15b
0x18000f923  test    al, al
0x18000f925  jnz     loc_18000FC7C
0x18000f92b  mov     rcx, [rbx+8]
0x18000f92f  cmp     rcx, r12
0x18000f932  jbe     short loc_18000F951
0x18000f934  mov     rcx, [rcx]
0x18000f937  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UAlphaOffset@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::AlphaOffset>::c_typeInfo
0x18000f93e  cmp     rcx, rax
0x18000f941  jz      loc_180010046
0x18000f947  cmp     [rcx+8], r13
0x18000f94b  jnz     loc_18001002A
0x18000f951  mov     al, r15b
0x18000f954  test    al, al
0x18000f956  jnz     loc_18000FC7C
0x18000f95c  mov     rcx, [rbx+8]
0x18000f960  cmp     rcx, r12
0x18000f963  jbe     short loc_18000F982
0x18000f965  mov     rcx, [rcx]
0x18000f968  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UAlphaModulate@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::AlphaModulate>::c_typeInfo
0x18000f96f  cmp     rcx, rax
0x18000f972  jz      loc_18000FFFE
0x18000f978  cmp     [rcx+8], r13
0x18000f97c  jnz     loc_18000FFE2
0x18000f982  mov     al, r15b
0x18000f985  test    al, al
0x18000f987  jnz     loc_18000FC7C
0x18000f98d  mov     rcx, [rbx+8]
0x18000f991  cmp     rcx, r12
0x18000f994  jbe     short loc_18000F9B3
0x18000f996  mov     rcx, [rcx]
0x18000f999  lea     rax, ?c_typeInfo@?$TypeInfoImpl@USaturation@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::Saturation>::c_typeInfo
0x18000f9a0  cmp     rcx, rax
0x18000f9a3  jz      loc_180010022
0x18000f9a9  cmp     [rcx+8], r13
0x18000f9ad  jnz     loc_180010006
0x18000f9b3  mov     al, r15b
0x18000f9b6  test    al, al
0x18000f9b8  jnz     short loc_18000F9FA
0x18000f9ba  mov     rcx, rbx
0x18000f9bd  call    ??$Is@USaturationOffset@Clr@Art@@@?$TChoice@VColorTransformDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::SaturationOffset>(void)
0x18000f9c2  test    al, al
0x18000f9c4  jnz     short loc_18000F9FA
0x18000f9c6  mov     rcx, rbx
0x18000f9c9  call    ??$Is@USaturationModulate@Clr@Art@@@?$TChoice@VColorTransformDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::SaturationModulate>(void)
0x18000f9ce  test    al, al
0x18000f9d0  jnz     short loc_18000F9FA
0x18000f9d2  mov     rcx, rbx
0x18000f9d5  call    ??$Is@ULuminance@Clr@Art@@@?$TChoice@VColorTransformDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::Luminance>(void)
0x18000f9da  test    al, al
0x18000f9dc  jnz     short loc_18000F9FA
0x18000f9de  mov     rcx, rbx
0x18000f9e1  call    ??$Is@ULuminanceOffset@Clr@Art@@@?$TChoice@VColorTransformDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::LuminanceOffset>(void)
0x18000f9e6  test    al, al
0x18000f9e8  jnz     short loc_18000F9FA
0x18000f9ea  mov     rcx, rbx
0x18000f9ed  call    ??$Is@ULuminanceModulate@Clr@Art@@@?$TChoice@VColorTransformDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::ColorTransformDataChoiceIDsImpl>::Is<Art::Clr::LuminanceModulate>(void)
0x18000f9f2  test    al, al
0x18000f9f4  jz      loc_180010698
0x18000f9fa  lea     rcx, [rsp+140h+var_110]; this
0x18000f9ff  call    ?scRGB_To_sRGB@Color@GEL@@QEAAXXZ; GEL::Color::scRGB_To_sRGB(void)
0x18000fa04  movss   xmm5, dword ptr [rsp+140h+var_110]
0x18000fa0a  movaps  xmm3, xmm5
0x18000fa0d  movss   xmm1, dword ptr [rsp+140h+var_110+4]
0x18000fa13  maxss   xmm3, xmm1
0x18000fa17  movss   xmm9, dword ptr [rsp+140h+var_108]
0x18000fa1e  maxss   xmm3, xmm9
0x18000fa23  movaps  xmm0, xmm5
0x18000fa26  minss   xmm0, xmm1
0x18000fa2a  minss   xmm0, xmm9
0x18000fa2f  movaps  xmm4, xmm0
0x18000fa32  addss   xmm4, xmm3
0x18000fa36  movaps  xmm8, xmm4
0x18000fa3a  mulss   xmm8, xmm15
0x18000fa3f  movaps  xmm2, xmm3
0x18000fa42  subss   xmm2, xmm0
0x18000fa46  movaps  xmm0, xmm2
0x18000fa49  andps   xmm0, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x18000fa50  movss   xmm6, cs:__real@34800000
0x18000fa58  comiss  xmm6, xmm0
0x18000fa5b  jbe     loc_18000FF0D
0x18000fa61  movaps  xmm6, xmm10
0x18000fa65  movss   xmm7, cs:__real@bf800000
0x18000fa6d  movss   xmm9, cs:__real@3e2aaaab
0x18000fa76  mov     rcx, [rbx+8]
0x18000fa7a  cmp     rcx, r12
0x18000fa7d  jbe     short loc_18000FA9C
0x18000fa7f  mov     rcx, [rcx]
0x18000fa82  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UHue@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::Hue>::c_typeInfo
0x18000fa89  cmp     rcx, rax
0x18000fa8c  jz      loc_18001006A
0x18000fa92  cmp     [rcx+8], r13
0x18000fa96  jnz     loc_18001004E
0x18000fa9c  mov     al, r15b
0x18000fa9f  test    al, al
0x18000faa1  jnz     loc_180010636
0x18000faa7  mov     rcx, [rbx+8]
0x18000faab  cmp     rcx, r12
0x18000faae  jbe     short loc_18000FACD
0x18000fab0  mov     rcx, [rcx]
0x18000fab3  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UHueOffset@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::HueOffset>::c_typeInfo
0x18000faba  cmp     rcx, rax
0x18000fabd  jz      loc_1800100B2
0x18000fac3  cmp     [rcx+8], r13
0x18000fac7  jnz     loc_180010096
0x18000facd  mov     al, r15b
0x18000fad0  test    al, al
0x18000fad2  jnz     loc_18001051C
0x18000fad8  mov     rcx, [rbx+8]
0x18000fadc  cmp     rcx, r12
0x18000fadf  jbe     short loc_18000FAFE
0x18000fae1  mov     rcx, [rcx]
0x18000fae4  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UHueModulate@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::HueModulate>::c_typeInfo
0x18000faeb  cmp     rcx, rax
0x18000faee  jz      loc_1800100FA
0x18000faf4  cmp     [rcx+8], r13
0x18000faf8  jnz     loc_1800100DE
0x18000fafe  mov     al, r15b
0x18000fb01  test    al, al
0x18000fb03  jnz     loc_1800107F5
0x18000fb09  mov     rcx, [rbx+8]
0x18000fb0d  cmp     rcx, r12
0x18000fb10  jbe     short loc_18000FB2F
0x18000fb12  mov     rcx, [rcx]
0x18000fb15  lea     rax, ?c_typeInfo@?$TypeInfoImpl@USaturation@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::Saturation>::c_typeInfo
0x18000fb1c  cmp     rcx, rax
0x18000fb1f  jz      loc_18001011E
0x18000fb25  cmp     [rcx+8], r13
0x18000fb29  jnz     loc_180010102
0x18000fb2f  mov     al, r15b
0x18000fb32  test    al, al
0x18000fb34  jnz     loc_180010934
0x18000fb3a  mov     rcx, [rbx+8]
0x18000fb3e  cmp     rcx, r12
0x18000fb41  jbe     short loc_18000FB60
0x18000fb43  mov     rcx, [rcx]
0x18000fb46  lea     rax, ?c_typeInfo@?$TypeInfoImpl@USaturationOffset@Clr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Clr::SaturationOffset>::c_typeInfo
0x18000fb4d  cmp     rcx, rax
0x18000fb50  jz      loc_180010142
  ... truncated ...
```
