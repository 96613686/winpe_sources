# xpsrdr::CreateGlyphRun(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &)

- ea: `0x18003dcd4`
- end: `0x18003e9eb`
- name: `?CreateGlyphRun@xpsrdr@@YA?AV?$shared_ptr@UGlyphRun@xpsrdr@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@@Z`
- size: `3351`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `service_task`

## callers

- `0x180019c1c`
- `0x180039cd4`

## callees

- `0x180008830`
- `0x180008854`
- `0x1800093c4`
- `0x18000da2c`
- `0x18000e934`
- `0x180011b2c`
- `0x180011da4`
- `0x180017ad0`
- `0x180023060`
- `0x18002b620`
- `0x180037278`
- `0x1800372e4`
- `0x18003d654`
- `0x18003d75c`
- `0x18003d868`
- `0x18003d938`
- `0x18003d9f4`
- `0x18003daf4`
- `0x18003db7c`
- `0x18003dc2c`
- `0x18003dcd4`
- `0x1800432dc`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD **__fastcall xpsrdr::CreateGlyphRun(_QWORD **a1, __int64 a2, __int64 **a3)
{
  _QWORD *v6; // rbx
  _DWORD *v7; // rax
  __int64 v8; // rax
  int v9; // eax
  int v10; // edx
  const char *v11; // r8
  int v12; // r9d
  int v13; // eax
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  int v17; // eax
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  int v21; // eax
  int v22; // edx
  const char *v23; // r8
  int v24; // r9d
  int v25; // eax
  int v26; // edx
  const char *v27; // r8
  int v28; // r9d
  char v29; // r13
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // r15d
  std::_Ref_count_base *v33; // rdi
  _DWORD *v34; // rbx
  int v35; // edx
  const char *v36; // r8
  int v37; // r9d
  _WORD *v38; // r12
  unsigned __int64 v39; // r15
  int v40; // ebx
  __m128 v41; // xmm8
  int v42; // eax
  int v43; // edx
  __int64 v44; // r8
  int v45; // r9d
  float v46; // xmm9_4
  unsigned __int64 v47; // r13
  int v48; // eax
  int v49; // edx
  const char *v50; // r8
  int v51; // r9d
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // r14
  unsigned __int64 v54; // rcx
  __int64 v55; // rbx
  unsigned __int64 v56; // rdx
  __int64 v57; // rax
  unsigned __int64 v58; // r12
  __int16 v59; // cx
  int v60; // eax
  int v61; // edx
  const char *v62; // r8
  int v63; // r9d
  _QWORD *v64; // rax
  __int16 *v65; // rdx
  float v66; // xmm2_4
  int v67; // eax
  int v68; // edx
  const char *v69; // r8
  int v70; // r9d
  int v71; // eax
  __int64 v72; // rcx
  float *v73; // rdx
  __int64 v74; // rcx
  _QWORD *v75; // rdx
  __int16 v76; // dx
  int v77; // eax
  int v78; // edx
  const char *v79; // r8
  int v80; // r9d
  __int64 v81; // rcx
  _WORD *v82; // rax
  __m128 v83; // xmm6
  __m128 v84; // xmm7
  float v85; // xmm0_4
  int v86; // eax
  int v87; // edx
  const char *v88; // r8
  int v89; // r9d
  int v90; // eax
  __int64 v91; // rcx
  float *v92; // rdx
  __int64 v93; // rcx
  unsigned __int64 *v94; // rdx
  __int16 v95; // dx
  int v96; // eax
  int v97; // edx
  const char *v98; // r8
  int v99; // r9d
  __int64 v100; // rcx
  _WORD *v101; // rax
  float v102; // xmm2_4
  int v103; // eax
  int v104; // edx
  const char *v105; // r8
  int v106; // r9d
  int v107; // eax
  __int64 v108; // rcx
  float *v109; // rdx
  __int64 v110; // rcx
  _QWORD *v111; // rdx
  std::_Ref_count_base *v112; // rcx
  unsigned __int64 v114; // rdi
  _QWORD *v115; // r14
  __int64 v116; // r12
  __int64 v117; // rdx
  unsigned __int64 v118; // rcx
  __int64 v119; // rax
  size_t v120; // rbx
  _QWORD *v121; // r14
  __int64 v122; // r12
  __int64 v123; // rdx
  unsigned __int64 v124; // rcx
  __int64 v125; // rax
  size_t v126; // rbx
  _QWORD *v127; // rbx
  __int64 v128; // rdx
  unsigned __int64 v129; // rcx
  __int64 v130; // rax
  unsigned __int64 i; // rbx
  int v132; // eax
  int v133; // edx
  int v134; // r9d
  __int16 v135; // dx
  float v136; // xmm0_4
  _QWORD *v137; // rax
  int v138; // eax
  int v139; // edx
  int v140; // r9d
  int v141; // eax
  float v142; // xmm0_4
  char v143; // dl
  int v144; // eax
  int v145; // edx
  const char *v146; // r8
  int v147; // r9d
  int v148; // eax
  int v149; // edx
  int v150; // r9d
  int v151; // eax
  _WORD v152[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v153[2]; // [rsp+34h] [rbp-CCh] BYREF
  float v154; // [rsp+38h] [rbp-C8h] BYREF
  char v155; // [rsp+3Ch] [rbp-C4h]
  int v156; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v157; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v158; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v159; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v160; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v161; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v162; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v163; // [rsp+70h] [rbp-90h]
  char *v164; // [rsp+78h] [rbp-88h] BYREF
  __int64 v165; // [rsp+80h] [rbp-80h]
  int v166; // [rsp+90h] [rbp-70h]
  _WORD *v167; // [rsp+98h] [rbp-68h] BYREF
  __int128 v168; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v169; // [rsp+B0h] [rbp-50h]
  _QWORD **v170; // [rsp+B8h] [rbp-48h]
  _OWORD v171[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v172; // [rsp+E0h] [rbp-20h] BYREF
  int v173; // [rsp+F0h] [rbp-10h]
  _OWORD v174[2]; // [rsp+F8h] [rbp-8h] BYREF

  v170 = a1;
  v166 = 0;
  v6 = operator new(0x68u);
  v6[2] = 0;
  v6[12] = 0;
  *v6 = 0;
  v6[1] = 0;
  v6[3] = 0;
  v6[4] = 0;
  v6[5] = 0;
  v6[6] = 0;
  v6[7] = 0;
  v6[8] = 0;
  v6[9] = 0;
  v6[10] = 0;
  v6[11] = 0;
  *a1 = 0;
  a1[1] = 0;
  v7 = operator new(0x18u);
  v162 = v7;
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count<xpsrdr::GlyphRun>::`vftable';
  *((_QWORD *)v7 + 2) = v6;
  *a1 = v6;
  a1[1] = v7;
  v161 = 0;
  std::_Temporary_owner<xpsrdr::GlyphRun>::~_Temporary_owner<xpsrdr::GlyphRun>(&v161);
  v166 = 1;
  v8 = xpsrdr::CreateFontFace(&v162, a2, a3);
  std::shared_ptr<_devicemodeW>::operator=(*a1, v8);
  if ( v163 )
    std::_Ref_count_base::_Decref(v163);
  v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(**a3 + 352))(*a3, *a1 + 2);
  if ( v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, v10, v11, v12);
  v172 = 0;
  v173 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)**a1 + 64LL))(**a1, &v172);
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 296))(*a3, (__int64)*a1 + 100);
  if ( v13 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
  v156 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 304))(*a3, &v156);
  if ( v17 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v18, v19, v20);
  *((_BYTE *)*a1 + 96) = v156 == 1;
  v157 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 248))(*a3, &v157);
  if ( v21 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v21, v22, v23, v24);
  std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021>::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021>(
    &v164,
    v157);
  if ( !v157 )
    goto LABEL_10;
  v25 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, char *))(**a3 + 256))(*a3, &v157, v164);
  if ( v25 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v26, v27, v28);
  v29 = 0;
  if ( !v157 )
LABEL_10:
    v29 = 1;
  v155 = v29;
  v167 = 0;
  v30 = *a3;
  v31 = **a3;
  v162 = 0;
  v163 = (std::_Ref_count_base *)&v167;
  v32 = (*(__int64 (__fastcall **)(__int64 *, _DWORD **))(v31 + 240))(v30, &v162);
  v33 = v163;
  v34 = v162;
  Holder<void *,close_funct<void (*)(void *),&void CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset((void **)v163);
  *(_QWORD *)v33 = v34;
  if ( v32 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, v35, v36, v37);
  v38 = v167;
  v160 = v167;
  if ( v167 )
  {
    v39 = -1;
    do
      ++v39;
    while ( v167[v39] );
  }
  else
  {
    v39 = 0;
  }
  v40 = (unsigned __int16)v172;
  v41 = (__m128)*((unsigned int *)*a1 + 4);
  v158 = 0;
  v42 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 264))(*a3, &v158);
  if ( v42 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v42, v43, (const char *)v44, v45);
  v46 = v41.m128_f32[0] / (float)v40;
  v41.m128_f32[0] = v41.m128_f32[0] / 100.0;
  v168 = 0;
  v169 = 0;
  if ( !v158 )
  {
    v114 = v39;
    if ( v157 > v39 )
      v114 = v157;
    v115 = *a1;
    v116 = (*a1)[4];
    v117 = (*a1)[3];
    v118 = (v116 - v117) >> 1;
    if ( v114 >= v118 )
    {
      if ( v114 <= v118 )
        goto LABEL_105;
      if ( v114 > (v115[5] - v117) >> 1 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v115 + 3, v114);
        goto LABEL_105;
      }
      v120 = 2 * (v114 - v118);
      memset_0((void *)(*a1)[4], 0, v120);
      v119 = v120 + v116;
    }
    else
    {
      v119 = v117 + 2 * v114;
    }
    v115[4] = v119;
LABEL_105:
    v121 = *a1;
    v122 = (*a1)[7];
    v123 = (*a1)[6];
    v124 = (v122 - v123) >> 2;
    if ( v114 >= v124 )
    {
      if ( v114 <= v124 )
        goto LABEL_112;
      if ( v114 > (v121[8] - v123) >> 2 )
      {
        std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(v121 + 6, v114);
        goto LABEL_112;
      }
      v126 = 4 * (v114 - v124);
      memset_0((void *)(*a1)[7], 0, v126);
      v125 = v126 + v122;
    }
    else
    {
      v125 = v123 + 4 * v114;
    }
    v121[7] = v125;
LABEL_112:
    v127 = *a1;
    v128 = (*a1)[9];
    v129 = ((*a1)[10] - v128) >> 3;
    if ( v114 < v129 )
    {
      v130 = v128 + 8 * v114;
LABEL_118:
      v127[10] = v130;
      goto LABEL_119;
    }
    if ( v114 > v129 )
    {
      if ( v114 <= (v127[11] - v128) >> 3 )
      {
        v130 = std::_Uninitialized_value_construct_n<std::allocator<DWRITE_GLYPH_OFFSET>>(v127[10], v114 - v129);
        goto LABEL_118;
      }
      std::vector<DWRITE_GLYPH_OFFSET>::_Resize_reallocate<std::_Value_init_tag>(v127 + 9, v114);
    }
LABEL_119:
    for ( i = 0; i < v157; *(float *)(v129 + 4 * i++) = v142 )
    {
      v153[0] = 0;
      if ( *(int *)&v164[16 * i] >= 0 )
      {
        v135 = *(_WORD *)&v164[16 * i];
        v153[0] = v135;
      }
      else
      {
        if ( i >= v39 )
          xpsrdr::ThrowLogicException((xpsrdr *)v129, v164, v44);
        LODWORD(v154) = (unsigned __int16)v160[i];
        v132 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
                 **a1,
                 &v154,
                 1,
                 v153);
        if ( v132 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v132, v133, (const char *)v44, v134);
        v135 = v153[0];
      }
      *(_WORD *)((*a1)[3] + 2 * i) = v135;
      *(float *)((*a1)[9] + 8 * i) = v41.m128_f32[0] * *(float *)&v164[16 * i + 8];
      *(float *)((*a1)[9] + 8 * i + 4) = v41.m128_f32[0] * *(float *)&v164[16 * i + 12];
      v136 = *(float *)&v164[16 * i + 4];
      v137 = *a1;
      if ( v136 >= 0.0 )
      {
        v142 = v136 * v41.m128_f32[0];
      }
      else
      {
        memset(v171, 0, 28);
        v138 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)*v137 + 80LL))(
                 *v137,
                 v153,
                 1,
                 v171,
                 v156);
        if ( v138 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v138, v139, (const char *)v44, v140);
        v141 = DWORD1(v171[0]);
        if ( v156 )
          v141 = v171[1];
        v142 = (float)v141 * v46;
        v137 = *a1;
      }
      v129 = v137[6];
    }
    if ( i < v39 )
    {
      do
      {
        LODWORD(v154) = (unsigned __int16)v160[i];
        v143 = 0;
        if ( LODWORD(v154) == 32 )
          v143 = v29;
        v29 = v143;
        v144 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, unsigned __int64))(*(_QWORD *)**a1 + 88LL))(
                 **a1,
                 &v154,
                 1,
                 (*a1)[3] + 2 * i);
        if ( v144 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v144, v145, v146, v147);
        memset(v171, 0, 28);
        v148 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
                 **a1,
                 (*a1)[3] + 2 * i,
                 1,
                 v171,
                 v156);
        if ( v148 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v148, v149, (const char *)v44, v150);
        *(_DWORD *)((*a1)[9] + 8 * i) = 0;
        *(_DWORD *)((*a1)[9] + 8 * i + 4) = 0;
        v151 = DWORD1(v171[0]);
        if ( v156 )
          v151 = v171[1];
        *(float *)((*a1)[6] + 4 * i++) = (float)v151 * v46;
      }
      while ( i < v39 );
      v155 = v29;
    }
    goto LABEL_90;
  }
  v47 = 0;
  std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022>::_Resize_reallocate<std::_Value_init_tag>(&v168, v158);
  v48 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, _QWORD))(**a3 + 272))(*a3, &v158, v168);
  if ( v48 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v49, v50, v51);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v162 = 0;
  v44 = 0xFFFF;
  if ( !v158 )
    goto LABEL_89;
  while ( 2 )
  {
    v55 = 16 * v54;
    while ( 1 )
    {
      v56 = *(unsigned int *)(v55 + v168);
      v57 = v55 + v168;
      if ( v52 < v56 )
        goto LABEL_25;
      v58 = *(unsigned int *)(v57 + 8);
      if ( v53 >= v58 )
        break;
      v38 = v160;
LABEL_25:
      v59 = -1;
      v152[0] = -1;
      if ( v53 >= *(unsigned int *)(v57 + 8) || (v59 = *(_WORD *)&v164[16 * v53], v152[0] = v59, v59 == -1) )
      {
        if ( v52 < v56 && v52 < v39 )
        {
          LODWORD(v154) = (unsigned __int16)v38[v52];
          v60 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
                  **a1,
                  &v154,
                  1,
                  v152);
          if ( v60 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v60, v61, v62, v63);
          v59 = v152[0];
        }
      }
      v64 = *a1;
      v65 = (__int16 *)(*a1)[4];
      if ( v65 == (__int16 *)(*a1)[5] )
      {
        std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(v64 + 3, v65, v152);
      }
      else
      {
        *v65 = v59;
        v64[4] += 2LL;
      }
      v159 = 0;
      if ( v53 >= *(unsigned int *)(v168 + v55 + 8)
        || (v66 = v41.m128_f32[0] * *(float *)&v164[16 * v53 + 4],
            v154 = v66,
            *(float *)&v159 = v41.m128_f32[0] * *(float *)&v164[16 * v53 + 8],
            *((float *)&v159 + 1) = v41.m128_f32[0] * *(float *)&v164[16 * v53 + 12],
            v66 < 0.0) )
      {
        memset(v174, 0, 28);
        v67 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
                **a1,
                v152,
                1,
                v174,
                v156);
        if ( v67 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v67, v68, v69, v70);
        v71 = DWORD1(v174[0]);
        if ( v156 )
          v71 = v174[1];
        v66 = (float)v71 * v46;
        v154 = v66;
      }
      ++v52;
      ++v53;
      v72 = (__int64)(*a1 + 6);
      v73 = (float *)(*a1)[7];
      if ( v73 == (float *)(*a1)[8] )
      {
        std::vector<float>::_Emplace_reallocate<float const &>(v72, v73, &v154);
      }
      else
      {
        *v73 = v66;
        *(_QWORD *)(v72 + 8) = v73 + 1;
      }
      v74 = (__int64)(*a1 + 9);
      v75 = (_QWORD *)(*a1)[10];
      if ( v75 == (_QWORD *)(*a1)[11] )
      {
        std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(v74, v75, &v159);
      }
      else
      {
        *v75 = v159;
        *(_QWORD *)(v74 + 8) += 8LL;
      }
      v44 = 0xFFFF;
    }
    if ( *(_WORD *)(v55 + v168 + 12) )
    {
      do
      {
        v76 = *(_WORD *)&v164[16 * v58];
        v153[0] = v76;
        if ( v76 == -1 && v52 < v39 )
        {
          LODWORD(v154) = (unsigned __int16)v160[v52];
          v77 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
                  **a1,
                  &v154,
                  1,
                  v153);
          if ( v77 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v77, v78, v79, v80);
          ++v52;
          v76 = v153[0];
        }
        v81 = (__int64)(*a1 + 3);
        v82 = (_WORD *)(*a1)[4];
        if ( v82 == (_WORD *)(*a1)[5] )
        {
          std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(v81, (*a1)[4], v153);
        }
        else
        {
          *v82 = v76;
          *(_QWORD *)(v81 + 8) += 2LL;
        }
        v83 = v41;
        v83.m128_f32[0] = v41.m128_f32[0] * *(float *)&v164[16 * v58 + 8];
        *(float *)&v161 = v83.m128_f32[0];
        v84 = v41;
        v84.m128_f32[0] = v41.m128_f32[0] * *(float *)&v164[16 * v58 + 12];
        *((float *)&v161 + 1) = v84.m128_f32[0];
        v85 = v41.m128_f32[0] * *(float *)&v164[16 * v58 + 4];
        v154 = v85;
        if ( v85 < 0.0 )
        {
          memset(v171, 0, 28);
          v86 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
                  **a1,
                  v153,
                  1,
                  v171,
                  v156);
          if ( v86 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v86, v87, v88, v89);
          v90 = DWORD1(v171[0]);
          if ( v156 )
            v90 = v171[1];
          v85 = (float)v90 * v46;
          v154 = v85;
        }
        ++v58;
        v91 = (__int64)(*a1 + 6);
        v92 = (float *)(*a1)[7];
        if ( v92 == (float *)(*a1)[8] )
        {
          std::vector<float>::_Emplace_reallocate<float const &>(v91, v92, &v154);
        }
        else
        {
          *v92 = v85;
          *(_QWORD *)(v91 + 8) = v92 + 1;
        }
        v93 = (__int64)(*a1 + 9);
        v94 = (unsigned __int64 *)(*a1)[10];
        if ( v94 == (unsigned __int64 *)(*a1)[11] )
        {
          std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(v93, v94, &v161);
        }
        else
        {
          v161 = _mm_unpacklo_ps(v83, v84).m128_u64[0];
          *v94 = v161;
          *(_QWORD *)(v93 + 8) += 8LL;
        }
        ++v47;
        v44 = 0xFFFF;
      }
      while ( v47 < *(unsigned __int16 *)(v168 + v55 + 12) );
    }
    v53 = *(_DWORD *)(v168 + v55 + 8) + (unsigned int)*(unsigned __int16 *)(v168 + v55 + 12);
    v52 = *(_DWORD *)(v168 + v55) + (unsigned int)*(unsigned __int16 *)(v168 + v55 + 4);
    v54 = (unsigned __int64)v162 + 1;
    v162 = (_DWORD *)v54;
    v38 = v160;
    v47 = 0;
    if ( v54 < v158 )
      continue;
    break;
  }
LABEL_89:
  while ( v52 < v39 )
  {
    v152[0] = -1;
    if ( v53 >= (v165 - (__int64)v164) >> 4 || (v95 = *(_WORD *)&v164[16 * v53], v152[0] = v95, v95 == -1) )
    {
      LODWORD(v154) = (unsigned __int16)v38[v52];
      v96 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
              **a1,
              &v154,
              1,
              v152);
      if ( v96 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v96, v97, v98, v99);
      v95 = v152[0];
    }
    v100 = (__int64)(*a1 + 3);
    v101 = (_WORD *)(*a1)[4];
    if ( v101 == (_WORD *)(*a1)[5] )
    {
      std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(v100, (*a1)[4], v152);
    }
    else
    {
      *v101 = v95;
      *(_QWORD *)(v100 + 8) += 2LL;
    }
    v159 = 0;
    if ( v53 >= (v165 - (__int64)v164) >> 4
      || (v102 = v41.m128_f32[0] * *(float *)&v164[16 * v53 + 4],
          v154 = v102,
          *(float *)&v159 = v41.m128_f32[0] * *(float *)&v164[16 * v53 + 8],
          *((float *)&v159 + 1) = v41.m128_f32[0] * *(float *)&v164[16 * v53 + 12],
          v102 < 0.0) )
    {
      memset(v171, 0, 28);
      v103 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
               **a1,
               v152,
               1,
               v171,
               v156);
      if ( v103 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v103, v104, v105, v106);
      v107 = DWORD1(v171[0]);
      if ( v156 )
        v107 = v171[1];
      v102 = (float)v107 * v46;
      v154 = v102;
    }
    ++v52;
    ++v53;
    v108 = (__int64)(*a1 + 6);
    v109 = (float *)(*a1)[7];
    if ( v109 == (float *)(*a1)[8] )
    {
      std::vector<float>::_Emplace_reallocate<float const &>(v108, v109, &v154);
    }
    else
    {
      *v109 = v102;
      *(_QWORD *)(v108 + 8) = v109 + 1;
    }
    v110 = (__int64)(*a1 + 9);
    v111 = (_QWORD *)(*a1)[10];
    if ( v111 == (_QWORD *)(*a1)[11] )
    {
      std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(v110, v111, &v159);
    }
    else
    {
      *v111 = v159;
      *(_QWORD *)(v110 + 8) += 8LL;
    }
    v44 = 0xFFFF;
  }
LABEL_90:
  if ( v155 )
  {
    *a1 = 0;
    v112 = (std::_Ref_count_base *)a1[1];
    a1[1] = 0;
    if ( v112 )
      std::_Ref_count_base::_Decref(v112);
  }
  if ( (_QWORD)v168 )
  {
    std::_Deallocate<16>(v168, (v169 - v168) & 0xFFFFFFFFFFFFFFF0uLL, v44);
    v168 = 0;
    v169 = 0;
  }
  Holder<void *,close_funct<void (*)(void *),&void CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset((void **)&v167);
  std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022>::_Tidy(&v164);
  return a1;
}

```

## disassembly

```asm
0x18003dcd4  mov     rax, rsp
0x18003dcd7  mov     [rax+20h], rbx
0x18003dcdb  push    rbp
0x18003dcdc  push    rsi
0x18003dcdd  push    rdi
0x18003dcde  push    r12
0x18003dce0  push    r13
0x18003dce2  push    r14
0x18003dce4  push    r15
0x18003dce6  lea     rbp, [rsp-70h]
0x18003dceb  sub     rsp, 170h
0x18003dcf2  movaps  xmmword ptr [rax-48h], xmm6
0x18003dcf6  movaps  xmmword ptr [rax-58h], xmm7
0x18003dcfa  movaps  xmmword ptr [rax-68h], xmm8
0x18003dcff  movaps  xmmword ptr [rax-78h], xmm9
0x18003dd04  movaps  xmmword ptr [rax-88h], xmm10
0x18003dd0c  mov     rax, cs:__security_cookie
0x18003dd13  xor     rax, rsp
0x18003dd16  mov     [rbp+0A0h+var_88], rax
0x18003dd1a  mov     r14, r8
0x18003dd1d  mov     rdi, rdx
0x18003dd20  mov     rsi, rcx
0x18003dd23  mov     [rbp+0A0h+var_E8], rcx
0x18003dd27  xor     r12d, r12d
0x18003dd2a  mov     [rbp+0A0h+var_110], r12d
0x18003dd2e  lea     ecx, [r12+68h]; Size
0x18003dd33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dd38  mov     rbx, rax
0x18003dd3b  xor     eax, eax
0x18003dd3d  mov     [rbx+10h], rax
0x18003dd41  mov     [rbx+60h], rax
0x18003dd45  mov     [rbx], r12
0x18003dd48  mov     [rbx+8], r12
0x18003dd4c  mov     [rbx+18h], r12
0x18003dd50  mov     [rbx+20h], r12
0x18003dd54  mov     [rbx+28h], r12
0x18003dd58  mov     [rbx+30h], r12
0x18003dd5c  mov     [rbx+38h], r12
0x18003dd60  mov     [rbx+40h], r12
0x18003dd64  mov     [rbx+48h], r12
0x18003dd68  mov     [rbx+50h], r12
0x18003dd6c  mov     [rbx+58h], r12
0x18003dd70  mov     [rsi], r12
0x18003dd73  mov     [rsi+8], r12
0x18003dd77  mov     [rsp+1A0h+var_140], rbx
0x18003dd7c  lea     ecx, [rax+18h]; Size
0x18003dd7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003dd84  mov     [rsp+1A0h+var_138], rax
0x18003dd89  xorps   xmm0, xmm0
0x18003dd8c  movups  xmmword ptr [rax], xmm0
0x18003dd8f  lea     r15d, [r12+1]
0x18003dd94  mov     [rax+8], r15d
0x18003dd98  mov     [rax+0Ch], r15d
0x18003dd9c  lea     rcx, ??_7?$_Ref_count@UGlyphRun@xpsrdr@@@std@@6B@; const std::_Ref_count<xpsrdr::GlyphRun>::`vftable'
0x18003dda3  mov     [rax], rcx
0x18003dda6  mov     [rax+10h], rbx
0x18003ddaa  mov     [rsi], rbx
0x18003ddad  mov     [rsi+8], rax
0x18003ddb1  mov     [rsp+1A0h+var_140], r12
0x18003ddb6  lea     rcx, [rsp+1A0h+var_140]
0x18003ddbb  call    ??1?$_Temporary_owner@UGlyphRun@xpsrdr@@@std@@QEAA@XZ; std::_Temporary_owner<xpsrdr::GlyphRun>::~_Temporary_owner<xpsrdr::GlyphRun>(void)
0x18003ddc0  mov     [rbp+0A0h+var_110], r15d
0x18003ddc4  mov     r8, r14
0x18003ddc7  mov     rdx, rdi
0x18003ddca  lea     rcx, [rsp+1A0h+var_138]
0x18003ddcf  call    ?CreateFontFace@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontFace@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@@Z; xpsrdr::CreateFontFace(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &)
0x18003ddd4  mov     rdx, rax
0x18003ddd7  mov     rcx, [rsi]
0x18003ddda  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x18003dddf  mov     rcx, [rsp+1A0h+var_130]; this
0x18003dde4  test    rcx, rcx
0x18003dde7  jz      short loc_18003DDEE
0x18003dde9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003ddee  mov     rcx, [r14]
0x18003ddf1  mov     rax, [rcx]
0x18003ddf4  mov     rdx, [rsi]
0x18003ddf7  add     rdx, 10h
0x18003ddfb  mov     rax, [rax+160h]
0x18003de02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de07  test    eax, eax
0x18003de09  js      loc_18003E964
0x18003de0f  xorps   xmm0, xmm0
0x18003de12  xor     eax, eax
0x18003de14  movups  [rbp+0A0h+var_C0], xmm0
0x18003de18  mov     [rbp+0A0h+var_B0], eax
0x18003de1b  mov     rax, [rsi]
0x18003de1e  mov     rcx, [rax]
0x18003de21  mov     rax, [rcx]
0x18003de24  lea     rdx, [rbp+0A0h+var_C0]
0x18003de28  mov     rax, [rax+40h]
0x18003de2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de31  mov     rcx, [r14]
0x18003de34  mov     rax, [rcx]
0x18003de37  mov     rdx, [rsi]
0x18003de3a  add     rdx, 64h ; 'd'
0x18003de3e  mov     rax, [rax+128h]
0x18003de45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de4a  test    eax, eax
0x18003de4c  js      loc_18003E96C
0x18003de52  mov     [rsp+1A0h+var_160], r12d
0x18003de57  mov     rcx, [r14]
0x18003de5a  mov     rax, [rcx]
0x18003de5d  lea     rdx, [rsp+1A0h+var_160]
0x18003de62  mov     rax, [rax+130h]
0x18003de69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de6e  test    eax, eax
0x18003de70  js      loc_18003E974
0x18003de76  cmp     [rsp+1A0h+var_160], r15d
0x18003de7b  setz    cl
0x18003de7e  mov     rax, [rsi]
0x18003de81  mov     [rax+60h], cl
0x18003de84  mov     [rsp+1A0h+var_15C], r12d
0x18003de89  mov     rcx, [r14]
0x18003de8c  mov     rax, [rcx]
0x18003de8f  lea     rdx, [rsp+1A0h+var_15C]
0x18003de94  mov     rax, [rax+0F8h]
0x18003de9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dea0  test    eax, eax
0x18003dea2  js      loc_18003E97C
0x18003dea8  mov     edx, [rsp+1A0h+var_15C]
0x18003deac  lea     rcx, [rsp+1A0h+var_128]
0x18003deb1  call    ??0?$vector@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021@@V?$allocator@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021@@@std@@@std@@QEAA@_KAEBV?$allocator@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021@@@1@@Z; std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021>::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021>(unsigned __int64,std::allocator<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021> const &)
0x18003deb6  nop
0x18003deb7  cmp     [rsp+1A0h+var_15C], r12d
0x18003debc  jz      short loc_18003DEEC
0x18003debe  mov     rcx, [r14]
0x18003dec1  mov     rax, [rcx]
0x18003dec4  mov     r8, [rsp+1A0h+var_128]
0x18003dec9  lea     rdx, [rsp+1A0h+var_15C]
0x18003dece  mov     rax, [rax+100h]
0x18003ded5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003deda  test    eax, eax
0x18003dedc  js      loc_18003E984
0x18003dee2  cmp     [rsp+1A0h+var_15C], r12d
0x18003dee7  mov     r13b, r12b
0x18003deea  jnz     short loc_18003DEEF
0x18003deec  mov     r13b, r15b
0x18003deef  mov     [rsp+1A0h+var_164], r13b
0x18003def4  mov     [rbp+0A0h+var_108], r12
0x18003def8  mov     rcx, [r14]
0x18003defb  mov     rax, [rcx]
0x18003defe  mov     [rsp+1A0h+var_138], r12
0x18003df03  lea     rdx, [rbp+0A0h+var_108]
0x18003df07  mov     [rsp+1A0h+var_130], rdx
0x18003df0c  lea     rdx, [rsp+1A0h+var_138]
0x18003df11  mov     rax, [rax+0F0h]
0x18003df18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df1d  mov     r15d, eax
0x18003df20  mov     rdi, [rsp+1A0h+var_130]
0x18003df25  mov     rbx, [rsp+1A0h+var_138]
0x18003df2a  mov     rcx, rdi
0x18003df2d  call    ?reset@?$Holder@PEAXU?$close_funct@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@U?$invalid_const@PEAX$0A@@@@@QEAAXXZ; Holder<void *,close_funct<void (*)(void *),&CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(void)
0x18003df32  mov     [rdi], rbx
0x18003df35  test    r15d, r15d
0x18003df38  js      loc_18003E98C
0x18003df3e  mov     r12, [rbp+0A0h+var_108]
0x18003df42  mov     [rsp+1A0h+var_148], r12
0x18003df47  xor     edi, edi
0x18003df49  test    r12, r12
0x18003df4c  jz      short loc_18003DF5E
0x18003df4e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003df52  inc     r15
0x18003df55  cmp     [r12+r15*2], di
0x18003df5a  jnz     short loc_18003DF52
0x18003df5c  jmp     short loc_18003DF61
0x18003df5e  mov     r15, rdi
0x18003df61  movzx   ebx, word ptr [rbp+0A0h+var_C0]
0x18003df65  mov     rax, [rsi]
0x18003df68  movss   xmm8, dword ptr [rax+10h]
0x18003df6e  mov     [rsp+1A0h+var_158], edi
0x18003df72  mov     rcx, [r14]
0x18003df75  mov     rax, [rcx]
0x18003df78  lea     rdx, [rsp+1A0h+var_158]
0x18003df7d  mov     rax, [rax+108h]
0x18003df84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df89  test    eax, eax
0x18003df8b  js      loc_18003E995
0x18003df91  movd    xmm0, ebx
0x18003df95  cvtdq2ps xmm0, xmm0
0x18003df98  movaps  xmm9, xmm8
0x18003df9c  divss   xmm9, xmm0
0x18003dfa1  divss   xmm8, cs:__real@42c80000
0x18003dfaa  xorps   xmm0, xmm0
0x18003dfad  movdqu  [rbp+0A0h+var_100], xmm0
0x18003dfb2  mov     [rbp+0A0h+var_F0], rdi
0x18003dfb6  mov     eax, [rsp+1A0h+var_158]
0x18003dfba  test    eax, eax
0x18003dfbc  jz      loc_18003E60F
0x18003dfc2  mov     edx, eax
0x18003dfc4  xor     r13d, r13d
0x18003dfc7  test    eax, eax
0x18003dfc9  jz      short loc_18003DFD4
0x18003dfcb  lea     rcx, [rbp+0A0h+var_100]
0x18003dfcf  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022@@V?$allocator@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003dfd4  mov     rcx, [r14]
0x18003dfd7  mov     rax, [rcx]
0x18003dfda  mov     r8, qword ptr [rbp+0A0h+var_100]
0x18003dfde  lea     rdx, [rsp+1A0h+var_158]
0x18003dfe3  mov     rax, [rax+110h]
0x18003dfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfef  test    eax, eax
0x18003dff1  js      loc_18003E99D
0x18003dff7  mov     rdi, r13
0x18003dffa  mov     r14, r13
0x18003dffd  mov     rcx, r13
0x18003e000  mov     [rsp+1A0h+var_138], rcx
0x18003e005  mov     r8d, 0FFFFh
0x18003e00b  xorps   xmm10, xmm10
0x18003e00f  cmp     [rsp+1A0h+var_158], r13d
0x18003e014  jbe     loc_18003E56A
0x18003e01a  mov     rbx, rcx
0x18003e01d  shl     rbx, 4
0x18003e021  mov     rcx, qword ptr [rbp+0A0h+var_100]
0x18003e025  mov     edx, [rbx+rcx]
0x18003e028  lea     rax, [rbx+rcx]
0x18003e02c  cmp     rdi, rdx
0x18003e02f  jb      short loc_18003E043
0x18003e031  mov     r12d, [rax+8]
0x18003e035  cmp     r14, r12
0x18003e038  jnb     loc_18003E1EB
0x18003e03e  mov     r12, [rsp+1A0h+var_148]
0x18003e043  movzx   ecx, r8w
0x18003e047  mov     [rsp+1A0h+var_170], cx
0x18003e04c  mov     eax, [rax+8]
0x18003e04f  cmp     r14, rax
0x18003e052  jnb     short loc_18003E06E
0x18003e054  mov     rcx, r14
0x18003e057  add     rcx, rcx
0x18003e05a  mov     rax, [rsp+1A0h+var_128]
0x18003e05f  movzx   ecx, word ptr [rax+rcx*8]
0x18003e063  mov     [rsp+1A0h+var_170], cx
0x18003e068  cmp     cx, r8w
0x18003e06c  jnz     short loc_18003E0B0
0x18003e06e  cmp     rdi, rdx
0x18003e071  jnb     short loc_18003E0B0
0x18003e073  cmp     rdi, r15
0x18003e076  jnb     short loc_18003E0B0
0x18003e078  movzx   eax, word ptr [r12+rdi*2]
0x18003e07d  mov     [rsp+1A0h+var_168], eax
0x18003e081  mov     rax, [rsi]
0x18003e084  mov     rcx, [rax]
0x18003e087  mov     rax, [rcx]
0x18003e08a  lea     r9, [rsp+1A0h+var_170]
0x18003e08f  mov     r8d, 1
0x18003e095  lea     rdx, [rsp+1A0h+var_168]
0x18003e09a  mov     rax, [rax+58h]
0x18003e09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0a3  test    eax, eax
0x18003e0a5  js      loc_18003E9B5
0x18003e0ab  movzx   ecx, [rsp+1A0h+var_170]
0x18003e0b0  mov     rax, [rsi]
0x18003e0b3  mov     rdx, [rax+20h]
0x18003e0b7  cmp     rdx, [rax+28h]
0x18003e0bb  jz      short loc_18003E0C7
0x18003e0bd  mov     [rdx], cx
0x18003e0c0  add     qword ptr [rax+20h], 2
0x18003e0c5  jmp     short loc_18003E0D5
0x18003e0c7  lea     r8, [rsp+1A0h+var_170]
0x18003e0cc  lea     rcx, [rax+18h]
0x18003e0d0  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x18003e0d5  xor     eax, eax
0x18003e0d7  mov     [rsp+1A0h+var_150], rax
0x18003e0dc  mov     rax, qword ptr [rbp+0A0h+var_100]
0x18003e0e0  mov     ecx, [rax+rbx+8]
0x18003e0e4  cmp     r14, rcx
0x18003e0e7  jnb     short loc_18003E12A
0x18003e0e9  mov     rcx, r14
0x18003e0ec  add     rcx, rcx
0x18003e0ef  mov     rax, [rsp+1A0h+var_128]
0x18003e0f4  movaps  xmm2, xmm8
0x18003e0f8  mulss   xmm2, dword ptr [rax+rcx*8+4]
0x18003e0fe  movss   [rsp+1A0h+var_168], xmm2
0x18003e104  movaps  xmm0, xmm8
0x18003e108  mulss   xmm0, dword ptr [rax+rcx*8+8]
0x18003e10e  movss   dword ptr [rsp+1A0h+var_150], xmm0
0x18003e114  movaps  xmm1, xmm8
0x18003e118  mulss   xmm1, dword ptr [rax+rcx*8+0Ch]
0x18003e11e  movss   dword ptr [rsp+1A0h+var_150+4], xmm1
0x18003e124  comiss  xmm10, xmm2
0x18003e128  jbe     short loc_18003E185
0x18003e12a  xorps   xmm0, xmm0
0x18003e12d  movups  [rbp+0A0h+var_A8], xmm0
0x18003e131  movups  [rbp+0A0h+var_A8+0Ch], xmm0
0x18003e135  mov     rax, [rsi]
0x18003e138  mov     rcx, [rax]
0x18003e13b  mov     edx, [rsp+1A0h+var_160]
0x18003e13f  mov     rax, [rcx]
0x18003e142  mov     [rsp+1A0h+var_180], edx
0x18003e146  lea     r9, [rbp+0A0h+var_A8]
0x18003e14a  mov     r8d, 1
0x18003e150  lea     rdx, [rsp+1A0h+var_170]
0x18003e155  mov     rax, [rax+50h]
0x18003e159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e15e  test    eax, eax
0x18003e160  js      loc_18003E9BD
0x18003e166  mov     eax, dword ptr [rbp+0A0h+var_A8+4]
0x18003e169  cmp     [rsp+1A0h+var_160], r13d
0x18003e16e  cmovnz  eax, [rbp+0A0h+var_98]
0x18003e172  xorps   xmm2, xmm2
0x18003e175  cvtsi2ss xmm2, rax
  ... truncated ...
```
