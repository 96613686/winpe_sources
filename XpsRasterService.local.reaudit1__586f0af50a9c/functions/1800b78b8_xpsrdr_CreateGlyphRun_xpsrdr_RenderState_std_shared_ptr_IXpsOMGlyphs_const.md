# xpsrdr::CreateGlyphRun(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &)

- ea: `0x1800b78b8`
- end: `0x1800b853f`
- name: `?CreateGlyphRun@xpsrdr@@YA?AV?$shared_ptr@UGlyphRun@xpsrdr@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@@Z`
- size: `3207`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `service_task`

## callers

- `0x1800b0298`

## callees

- `0x180003180`
- `0x18000358c`
- `0x180003cc4`
- `0x1800a5230`
- `0x1800a7db8`
- `0x1800a831c`
- `0x1800add10`
- `0x1800b20e8`
- `0x1800b2154`
- `0x1800b5c70`
- `0x1800b6ebc`
- `0x1800b6f78`
- `0x1800b7020`
- `0x1800b7048`
- `0x1800b7070`
- `0x1800b716c`
- `0x1800b7268`
- `0x1800b7368`
- `0x1800b7434`
- `0x1800b74f0`
- `0x1800b7674`
- `0x1800b76b4`
- `0x1800b7790`
- `0x1800b78b8`
- `0x1800b8728`
- `0x1800bdc84`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD **__fastcall xpsrdr::CreateGlyphRun(_QWORD **a1, __int64 a2, __int64 **a3)
{
  _QWORD *v6; // rbx
  __int64 v7; // rax
  int v8; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  int v12; // eax
  int v13; // edx
  const char *v14; // r8
  int v15; // r9d
  int v16; // eax
  int v17; // edx
  const char *v18; // r8
  int v19; // r9d
  int v20; // eax
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  int v24; // eax
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  __int64 *v28; // rcx
  __int64 v29; // rax
  int v30; // r15d
  std::_Ref_count_base *v31; // rdi
  unsigned __int16 *v32; // rbx
  int v33; // edx
  const char *v34; // r8
  int v35; // r9d
  unsigned __int16 *v36; // r12
  unsigned __int64 v37; // r13
  int v38; // ebx
  float v39; // xmm7_4
  int v40; // eax
  int v41; // edx
  const char *v42; // r8
  int v43; // r9d
  float v44; // xmm8_4
  float v45; // xmm7_4
  unsigned __int64 v46; // rcx
  int v47; // eax
  int v48; // edx
  const char *v49; // r8
  int v50; // r9d
  unsigned __int64 v51; // r14
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // r9
  __int64 v54; // rbx
  unsigned __int64 v55; // r8
  __int64 v56; // rdx
  unsigned __int64 v57; // r12
  __int16 v58; // cx
  int v59; // eax
  int v60; // edx
  const char *v61; // r8
  int v62; // r9d
  __int64 v63; // rax
  __int16 *v64; // rdx
  int v65; // eax
  int v66; // edx
  const char *v67; // r8
  int v68; // r9d
  int v69; // eax
  __int64 v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rdx
  unsigned __int64 v74; // rdi
  __int64 v75; // r15
  unsigned __int64 v76; // rax
  __int16 v77; // dx
  int v78; // eax
  int v79; // edx
  const char *v80; // r8
  int v81; // r9d
  __int64 v82; // rcx
  _WORD *v83; // rax
  int v84; // eax
  int v85; // edx
  const char *v86; // r8
  int v87; // r9d
  int v88; // eax
  __int64 v89; // rcx
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // rdx
  __int16 v93; // dx
  int v94; // eax
  int v95; // edx
  const char *v96; // r8
  int v97; // r9d
  __int64 v98; // rcx
  _WORD *v99; // rax
  int v100; // eax
  int v101; // edx
  const char *v102; // r8
  int v103; // r9d
  int v104; // eax
  __int64 v105; // rcx
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // rdx
  unsigned __int64 v109; // rdi
  __int64 v110; // r14
  __int64 v111; // r15
  __int64 v112; // rdx
  unsigned __int64 v113; // rcx
  __int64 v114; // rax
  size_t v115; // rbx
  __int64 v116; // r14
  __int64 v117; // r15
  __int64 v118; // rdx
  unsigned __int64 v119; // rcx
  __int64 v120; // rax
  size_t v121; // rbx
  __int64 v122; // r8
  __int64 v123; // rdx
  unsigned __int64 v124; // rcx
  __int64 v125; // rax
  unsigned __int64 i; // rbx
  int v127; // eax
  int v128; // edx
  int v129; // r9d
  __int16 v130; // dx
  float v131; // xmm0_4
  _QWORD *v132; // rax
  int v133; // eax
  int v134; // edx
  int v135; // r9d
  int v136; // eax
  float v137; // xmm0_4
  char v138; // dl
  int v139; // eax
  int v140; // edx
  const char *v141; // r8
  int v142; // r9d
  int v143; // eax
  int v144; // edx
  const char *v145; // r8
  int v146; // r9d
  int v147; // eax
  std::_Ref_count_base *v148; // rcx
  _WORD v150[2]; // [rsp+30h] [rbp-D0h] BYREF
  float v151; // [rsp+34h] [rbp-CCh] BYREF
  char v152; // [rsp+38h] [rbp-C8h]
  _WORD v153[2]; // [rsp+3Ch] [rbp-C4h] BYREF
  int v154; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v155; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v156; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v157; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v158; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v159; // [rsp+68h] [rbp-98h]
  char *v160[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v161; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v162; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v163; // [rsp+90h] [rbp-70h]
  int v164; // [rsp+98h] [rbp-68h]
  float v165[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v166; // [rsp+A8h] [rbp-58h]
  void *v167[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v168[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v169; // [rsp+E0h] [rbp-20h] BYREF
  int v170; // [rsp+F0h] [rbp-10h]
  _OWORD v171[2]; // [rsp+F8h] [rbp-8h] BYREF

  v167[1] = a1;
  v6 = operator new(0x68u);
  memset_0(v6 + 2, 0, 0x58u);
  *v6 = 0;
  v6[1] = 0;
  std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(v6 + 3);
  std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(v6 + 6);
  std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(v6 + 9);
  std::shared_ptr<xpsrdr::GlyphRun>::shared_ptr<xpsrdr::GlyphRun>(a1, v6);
  v164 = 1;
  v7 = xpsrdr::CreateFontFace(&v162, a2, a3);
  std::shared_ptr<ID2D1Bitmap>::operator=(*a1, v7);
  if ( v163 )
    std::_Ref_count_base::_Decref(v163);
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(**a3 + 352))(*a3, *a1 + 2);
  if ( v8 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v8, v9, v10, v11);
  v169 = 0;
  v170 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)**a1 + 64LL))(**a1, &v169);
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64))(**a3 + 296))(*a3, (__int64)*a1 + 100);
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v13, v14, v15);
  v154 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a3 + 304))(*a3, &v154);
  if ( v16 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v16, v17, v18, v19);
  *((_BYTE *)*a1 + 96) = v154 == 1;
  v155 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 248))(*a3, &v155);
  if ( v20 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v20, v21, v22, v23);
  *(_OWORD *)v160 = 0;
  v161 = 0;
  std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021>::_Construct_n<>(v160, v155);
  if ( !v155 )
    goto LABEL_15;
  v24 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, char *))(**a3 + 256))(*a3, &v155, v160[0]);
  if ( v24 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
  v152 = 0;
  if ( !v155 )
LABEL_15:
    v152 = 1;
  v167[0] = 0;
  v28 = *a3;
  v29 = **a3;
  v162 = 0;
  v163 = (std::_Ref_count_base *)v167;
  v30 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 **))(v29 + 240))(v28, &v162);
  v31 = v163;
  v32 = v162;
  Holder<void *,close_funct<void (*)(void *),&void CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset((void **)v163);
  *(_QWORD *)v31 = v32;
  if ( v30 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v33, v34, v35);
  v36 = (unsigned __int16 *)v167[0];
  v162 = (unsigned __int16 *)v167[0];
  if ( v167[0] )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v167[0] + v37) );
  }
  else
  {
    v37 = 0;
  }
  v38 = (unsigned __int16)v169;
  v39 = *((float *)*a1 + 4);
  v156 = 0;
  v40 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 264))(*a3, &v156);
  if ( v40 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v40, v41, v42, v43);
  v44 = v39 / (float)v38;
  v45 = v39 / 100.0;
  std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(&v158);
  if ( !v156 )
  {
    v109 = v37;
    if ( v155 > v37 )
      v109 = v155;
    v110 = (__int64)*a1;
    v111 = (*a1)[4];
    v112 = (*a1)[3];
    v113 = (v111 - v112) >> 1;
    if ( v109 >= v113 )
    {
      if ( v109 <= v113 )
        goto LABEL_118;
      if ( v109 > (*(_QWORD *)(v110 + 40) - v112) >> 1 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v110 + 24, v109);
        goto LABEL_118;
      }
      v115 = 2 * (v109 - v113);
      memset_0((void *)(*a1)[4], 0, v115);
      v114 = v115 + v111;
    }
    else
    {
      v114 = v112 + 2 * v109;
    }
    *(_QWORD *)(v110 + 32) = v114;
LABEL_118:
    v116 = (__int64)*a1;
    v117 = (*a1)[7];
    v118 = (*a1)[6];
    v119 = (v117 - v118) >> 2;
    if ( v109 >= v119 )
    {
      if ( v109 <= v119 )
        goto LABEL_125;
      if ( v109 > (*(_QWORD *)(v116 + 64) - v118) >> 2 )
      {
        std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(v116 + 48, v109);
        goto LABEL_125;
      }
      v121 = 4 * (v109 - v119);
      memset_0((void *)(*a1)[7], 0, v121);
      v120 = v121 + v117;
    }
    else
    {
      v120 = v118 + 4 * v109;
    }
    *(_QWORD *)(v116 + 56) = v120;
LABEL_125:
    v122 = (__int64)(*a1 + 9);
    v123 = *(_QWORD *)v122;
    v124 = (__int64)((*a1)[10] - *(_QWORD *)v122) >> 3;
    if ( v109 < v124 )
    {
      v125 = v123 + 8 * v109;
LABEL_131:
      *(_QWORD *)(v122 + 8) = v125;
      goto LABEL_132;
    }
    if ( v109 > v124 )
    {
      if ( v109 <= ((*a1)[11] - v123) >> 3 )
      {
        v125 = std::_Uninitialized_value_construct_n<std::allocator<DWRITE_GLYPH_OFFSET>>((*a1)[10], v109 - v124);
        goto LABEL_131;
      }
      std::vector<DWRITE_GLYPH_OFFSET>::_Resize_reallocate<std::_Value_init_tag>(*a1 + 9, v109);
    }
LABEL_132:
    for ( i = 0; i < v155; ++i )
    {
      v153[0] = 0;
      if ( *(int *)&v160[0][16 * i] >= 0 )
      {
        v130 = *(_WORD *)&v160[0][16 * i];
        v153[0] = v130;
      }
      else
      {
        if ( i >= v37 )
          xpsrdr::ThrowLogicException((xpsrdr *)v124, v160[0], v122);
        LODWORD(v151) = v36[i];
        v127 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
                 **a1,
                 &v151,
                 1,
                 v153);
        if ( v127 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v127, v128, (const char *)v122, v129);
        v130 = v153[0];
      }
      *(_WORD *)((*a1)[3] + 2 * i) = v130;
      *(float *)((*a1)[9] + 8 * i) = v45 * *(float *)&v160[0][16 * i + 8];
      *(float *)((*a1)[9] + 8 * i + 4) = v45 * *(float *)&v160[0][16 * i + 12];
      v131 = *(float *)&v160[0][16 * i + 4];
      v132 = *a1;
      if ( v131 >= 0.0 )
      {
        v137 = v131 * v45;
      }
      else
      {
        memset(v168, 0, 28);
        v133 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)*v132 + 80LL))(
                 *v132,
                 v153,
                 1,
                 v168,
                 v154);
        if ( v133 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v133, v134, (const char *)v122, v135);
        v136 = DWORD1(v168[0]);
        if ( v154 )
          v136 = v168[1];
        v137 = (float)v136 * v44;
        v132 = *a1;
      }
      v124 = v132[6];
      *(float *)(v124 + 4 * i) = v137;
    }
    while ( i < v37 )
    {
      LODWORD(v151) = v36[i];
      v138 = 0;
      if ( LODWORD(v151) == 32 )
        v138 = v152;
      v152 = v138;
      v139 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, unsigned __int64))(*(_QWORD *)**a1 + 88LL))(
               **a1,
               &v151,
               1,
               (*a1)[3] + 2 * i);
      if ( v139 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v139, v140, v141, v142);
      memset(v168, 0, 28);
      v143 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
               **a1,
               (*a1)[3] + 2 * i,
               1,
               v168,
               v154);
      if ( v143 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v143, v144, v145, v146);
      *(_DWORD *)((*a1)[9] + 8 * i) = 0;
      *(_DWORD *)((*a1)[9] + 8 * i + 4) = 0;
      v147 = DWORD1(v168[0]);
      if ( v154 )
        v147 = v168[1];
      *(float *)((*a1)[6] + 4 * i++) = (float)v147 * v44;
    }
    goto LABEL_159;
  }
  v46 = (__int64)(*((_QWORD *)&v158 + 1) - v158) >> 4;
  if ( v156 >= v46 )
  {
    if ( v156 > v46 )
    {
      if ( v156 <= (unsigned __int64)((v159 - (__int64)v158) >> 4) )
        *((_QWORD *)&v158 + 1) = std::_Uninitialized_value_construct_n<std::allocator<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022>>(
                                   *((_QWORD *)&v158 + 1),
                                   v156 - v46,
                                   &v158);
      else
        std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022>::_Resize_reallocate<std::_Value_init_tag>(&v158);
    }
  }
  else
  {
    *((_QWORD *)&v158 + 1) = v158 + 16LL * v156;
  }
  v47 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a3 + 272))(*a3, &v156);
  if ( v47 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v47, v48, v49, v50);
  v51 = 0;
  v52 = 0;
  v53 = 0;
LABEL_35:
  v166 = v53;
  if ( v53 < v156 )
  {
    v54 = 2 * v53;
    while ( 1 )
    {
      v55 = *(unsigned int *)(v158 + 8 * v54);
      v56 = v158 + 8 * v54;
      if ( v51 >= v55 )
      {
        v57 = *(unsigned int *)(v56 + 8);
        if ( v52 >= v57 )
        {
          v74 = 0;
          v75 = 16 * v166;
          while ( 1 )
          {
            v76 = *(unsigned __int16 *)(v75 + v158 + 12);
            if ( v74 >= v76 )
              break;
            v77 = *(_WORD *)&v160[0][16 * v57];
            v153[0] = v77;
            if ( v77 == -1 && v51 < v37 )
            {
              LODWORD(v151) = v162[v51];
              v78 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
                      **a1,
                      &v151,
                      1,
                      v153);
              if ( v78 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v78, v79, v80, v81);
              ++v51;
              v77 = v153[0];
            }
            v82 = (__int64)(*a1 + 3);
            v83 = (_WORD *)(*a1)[4];
            if ( v83 == (_WORD *)(*a1)[5] )
            {
              std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(v82, (*a1)[4], v153);
            }
            else
            {
              *v83 = v77;
              *(_QWORD *)(v82 + 8) += 2LL;
            }
            v165[0] = v45 * *(float *)&v160[0][16 * v57 + 8];
            v165[1] = v45 * *(float *)&v160[0][16 * v57 + 12];
            v151 = v45 * *(float *)&v160[0][16 * v57 + 4];
            if ( v151 < 0.0 )
            {
              memset(v168, 0, 28);
              v84 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
                      **a1,
                      v153,
                      1,
                      v168,
                      v154);
              if ( v84 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v84, v85, v86, v87);
              v88 = DWORD1(v168[0]);
              if ( v154 )
                v88 = v168[1];
              v151 = (float)v88 * v44;
            }
            ++v57;
            v89 = (__int64)(*a1 + 6);
            v90 = (*a1)[7];
            if ( v90 == (*a1)[8] )
              std::vector<float>::_Emplace_reallocate<float const &>(v89, v90, &v151);
            else
              std::vector<float>::_Emplace_back_with_unused_capacity<float const &>(v89, &v151);
            v91 = (__int64)(*a1 + 9);
            v92 = (*a1)[10];
            if ( v92 == (*a1)[11] )
              std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(v91, v92, v165);
            else
              std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_back_with_unused_capacity<DWRITE_GLYPH_OFFSET const &>(
                v91,
                v165);
            ++v74;
          }
          v52 = (unsigned int)(v76 + *(_DWORD *)(v75 + v158 + 8));
          v51 = *(_DWORD *)(v75 + v158) + (unsigned int)*(unsigned __int16 *)(v75 + v158 + 4);
          v53 = v166 + 1;
          v36 = v162;
          goto LABEL_35;
        }
        v36 = v162;
      }
      v58 = -1;
      v150[0] = -1;
      if ( v52 >= *(unsigned int *)(v56 + 8) || (v58 = *(_WORD *)&v160[0][16 * v52], v150[0] = v58, v58 == -1) )
      {
        if ( v51 < v55 && v51 < v37 )
        {
          LODWORD(v151) = v36[v51];
          v59 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
                  **a1,
                  &v151,
                  1,
                  v150);
          if ( v59 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v59, v60, v61, v62);
          v58 = v150[0];
        }
      }
      v63 = (__int64)*a1;
      v64 = (__int16 *)(*a1)[4];
      if ( v64 == (__int16 *)(*a1)[5] )
      {
        std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(v63 + 24, v64, v150);
      }
      else
      {
        *v64 = v58;
        *(_QWORD *)(v63 + 32) += 2LL;
      }
      v157 = 0;
      if ( v52 >= *(unsigned int *)(v158 + 8 * v54 + 8)
        || (v151 = v45 * *(float *)&v160[0][16 * v52 + 4],
            *(float *)&v157 = v45 * *(float *)&v160[0][16 * v52 + 8],
            *((float *)&v157 + 1) = v45 * *(float *)&v160[0][16 * v52 + 12],
            v151 < 0.0) )
      {
        memset(v171, 0, 28);
        v65 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
                **a1,
                v150,
                1,
                v171,
                v154);
        if ( v65 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v66, v67, v68);
        v69 = DWORD1(v171[0]);
        if ( v154 )
          v69 = v171[1];
        v151 = (float)v69 * v44;
      }
      ++v51;
      ++v52;
      v70 = (__int64)(*a1 + 6);
      v71 = (*a1)[7];
      if ( v71 == (*a1)[8] )
        std::vector<float>::_Emplace_reallocate<float const &>(v70, v71, &v151);
      else
        std::vector<float>::_Emplace_back_with_unused_capacity<float const &>(v70, &v151);
      v72 = (__int64)(*a1 + 9);
      v73 = (*a1)[10];
      if ( v73 == (*a1)[11] )
        std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(v72, v73, &v157);
      else
        std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_back_with_unused_capacity<DWRITE_GLYPH_OFFSET const &>(v72, &v157);
    }
  }
  while ( v51 < v37 )
  {
    v150[0] = -1;
    if ( v52 >= (v160[1] - v160[0]) >> 4 || (v93 = *(_WORD *)&v160[0][16 * v52], v150[0] = v93, v93 == -1) )
    {
      LODWORD(v151) = v36[v51];
      v94 = (*(__int64 (__fastcall **)(_QWORD, float *, __int64, _WORD *))(*(_QWORD *)**a1 + 88LL))(
              **a1,
              &v151,
              1,
              v150);
      if ( v94 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v94, v95, v96, v97);
      v93 = v150[0];
    }
    v98 = (__int64)(*a1 + 3);
    v99 = (_WORD *)(*a1)[4];
    if ( v99 == (_WORD *)(*a1)[5] )
    {
      std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>(v98, (*a1)[4], v150);
    }
    else
    {
      *v99 = v93;
      *(_QWORD *)(v98 + 8) += 2LL;
    }
    v157 = 0;
    if ( v52 >= (v160[1] - v160[0]) >> 4
      || (v151 = v45 * *(float *)&v160[0][16 * v52 + 4],
          *(float *)&v157 = v45 * *(float *)&v160[0][16 * v52 + 8],
          *((float *)&v157 + 1) = v45 * *(float *)&v160[0][16 * v52 + 12],
          v151 < 0.0) )
    {
      memset(v168, 0, 28);
      v100 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _OWORD *, int))(*(_QWORD *)**a1 + 80LL))(
               **a1,
               v150,
               1,
               v168,
               v154);
      if ( v100 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v100, v101, v102, v103);
      v104 = DWORD1(v168[0]);
      if ( v154 )
        v104 = v168[1];
      v151 = (float)v104 * v44;
    }
    ++v51;
    ++v52;
    v105 = (__int64)(*a1 + 6);
    v106 = (*a1)[7];
    if ( v106 == (*a1)[8] )
      std::vector<float>::_Emplace_reallocate<float const &>(v105, v106, &v151);
    else
      std::vector<float>::_Emplace_back_with_unused_capacity<float const &>(v105, &v151);
    v107 = (__int64)(*a1 + 9);
    v108 = (*a1)[10];
    if ( v108 == (*a1)[11] )
      std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(v107, v108, &v157);
    else
      std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_back_with_unused_capacity<DWRITE_GLYPH_OFFSET const &>(v107, &v157);
  }
LABEL_159:
  if ( v152 )
  {
    *a1 = 0;
    v148 = (std::_Ref_count_base *)a1[1];
    a1[1] = 0;
    if ( v148 )
      std::_Ref_count_base::_Decref(v148);
  }
  if ( (_QWORD)v158 )
  {
    std::_Deallocate<16>(v158, (v159 - v158) & 0xFFFFFFFFFFFFFFF0uLL);
    v158 = 0;
    v159 = 0;
  }
  Holder<void *,close_funct<void (*)(void *),&void CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(v167);
  std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021>::_Tidy(v160);
  return a1;
}

```

## disassembly

```asm
0x1800b78b8  mov     rax, rsp
0x1800b78bb  mov     [rax+20h], rbx
0x1800b78bf  push    rbp
0x1800b78c0  push    rsi
0x1800b78c1  push    rdi
0x1800b78c2  push    r12
0x1800b78c4  push    r13
0x1800b78c6  push    r14
0x1800b78c8  push    r15
0x1800b78ca  lea     rbp, [rsp-50h]
0x1800b78cf  sub     rsp, 150h
0x1800b78d6  movaps  xmmword ptr [rax-48h], xmm6
0x1800b78da  movaps  xmmword ptr [rax-58h], xmm7
0x1800b78de  movaps  xmmword ptr [rax-68h], xmm8
0x1800b78e3  mov     rax, cs:__security_cookie
0x1800b78ea  xor     rax, rsp
0x1800b78ed  mov     [rbp+80h+var_68], rax
0x1800b78f1  mov     r14, r8
0x1800b78f4  mov     rdi, rdx
0x1800b78f7  mov     rsi, rcx
0x1800b78fa  mov     [rbp+80h+var_C8], rcx
0x1800b78fe  xor     r12d, r12d
0x1800b7901  mov     [rbp+80h+var_E8], r12d
0x1800b7905  lea     ecx, [r12+68h]; Size
0x1800b790a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b790f  mov     rbx, rax
0x1800b7912  lea     rcx, [rax+10h]; void *
0x1800b7916  xor     edx, edx; Val
0x1800b7918  lea     r8d, [r12+58h]; Size
0x1800b791d  call    memset_0
0x1800b7922  mov     [rbx], r12
0x1800b7925  mov     [rbx+8], r12
0x1800b7929  lea     rcx, [rbx+18h]
0x1800b792d  call    ??0?$vector@V?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(void)
0x1800b7932  lea     rcx, [rbx+30h]
0x1800b7936  call    ??0?$vector@V?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(void)
0x1800b793b  lea     rcx, [rbx+48h]
0x1800b793f  call    ??0?$vector@V?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(void)
0x1800b7944  mov     rdx, rbx
0x1800b7947  mov     rcx, rsi
0x1800b794a  call    ??$?0UGlyphRun@xpsrdr@@$0A@@?$shared_ptr@UGlyphRun@xpsrdr@@@std@@QEAA@PEAUGlyphRun@xpsrdr@@@Z; std::shared_ptr<xpsrdr::GlyphRun>::shared_ptr<xpsrdr::GlyphRun>(xpsrdr::GlyphRun *)
0x1800b794f  mov     [rbp+80h+var_E8], 1
0x1800b7956  mov     r8, r14
0x1800b7959  mov     rdx, rdi
0x1800b795c  lea     rcx, [rbp+80h+var_F8]
0x1800b7960  call    ?CreateFontFace@xpsrdr@@YA?AV?$shared_ptr@UIDWriteFontFace@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMGlyphs@@@3@@Z; xpsrdr::CreateFontFace(xpsrdr::RenderState &,std::shared_ptr<IXpsOMGlyphs> const &)
0x1800b7965  mov     rdx, rax
0x1800b7968  mov     rcx, [rsi]
0x1800b796b  call    ??4?$shared_ptr@UID2D1Bitmap@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ID2D1Bitmap>::operator=(std::shared_ptr<ID2D1Bitmap> &&)
0x1800b7970  mov     rcx, [rbp+80h+var_F0]; this
0x1800b7974  test    rcx, rcx
0x1800b7977  jz      short loc_1800B797E
0x1800b7979  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b797e  mov     rcx, [r14]
0x1800b7981  mov     rax, [rcx]
0x1800b7984  mov     rdx, [rsi]
0x1800b7987  add     rdx, 10h
0x1800b798b  mov     rax, [rax+160h]
0x1800b7992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7997  test    eax, eax
0x1800b7999  jns     short loc_1800B79A3
0x1800b799b  mov     ecx, eax; this
0x1800b799d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b79a3  xorps   xmm0, xmm0
0x1800b79a6  xor     eax, eax
0x1800b79a8  movups  [rbp+80h+var_A0], xmm0
0x1800b79ac  mov     [rbp+80h+var_90], eax
0x1800b79af  mov     rax, [rsi]
0x1800b79b2  mov     rcx, [rax]
0x1800b79b5  mov     rax, [rcx]
0x1800b79b8  lea     rdx, [rbp+80h+var_A0]
0x1800b79bc  mov     rax, [rax+40h]
0x1800b79c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b79c5  mov     rcx, [r14]
0x1800b79c8  mov     rax, [rcx]
0x1800b79cb  mov     rdx, [rsi]
0x1800b79ce  add     rdx, 64h ; 'd'
0x1800b79d2  mov     rax, [rax+128h]
0x1800b79d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b79de  test    eax, eax
0x1800b79e0  jns     short loc_1800B79EA
0x1800b79e2  mov     ecx, eax; this
0x1800b79e4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b79ea  mov     [rsp+180h+var_140], r12d
0x1800b79ef  mov     rcx, [r14]
0x1800b79f2  mov     rax, [rcx]
0x1800b79f5  lea     rdx, [rsp+180h+var_140]
0x1800b79fa  mov     rax, [rax+130h]
0x1800b7a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7a06  test    eax, eax
0x1800b7a08  jns     short loc_1800B7A12
0x1800b7a0a  mov     ecx, eax; this
0x1800b7a0c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b7a12  cmp     [rsp+180h+var_140], 1
0x1800b7a17  setz    cl
0x1800b7a1a  mov     rax, [rsi]
0x1800b7a1d  mov     [rax+60h], cl
0x1800b7a20  mov     [rsp+180h+var_13C], r12d
0x1800b7a25  mov     rcx, [r14]
0x1800b7a28  mov     rax, [rcx]
0x1800b7a2b  lea     rdx, [rsp+180h+var_13C]
0x1800b7a30  mov     rax, [rax+0F8h]
0x1800b7a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7a3c  test    eax, eax
0x1800b7a3e  jns     short loc_1800B7A48
0x1800b7a40  mov     ecx, eax; this
0x1800b7a42  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b7a48  xorps   xmm0, xmm0
0x1800b7a4b  movdqu  xmmword ptr [rsp+180h+var_110], xmm0
0x1800b7a51  mov     [rbp+80h+var_100], r12
0x1800b7a55  mov     edx, [rsp+180h+var_13C]
0x1800b7a59  lea     rcx, [rsp+180h+var_110]
0x1800b7a5e  call    ??$_Construct_n@$$V@?$vector@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021@@V?$allocator@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021@@@std@@@std@@AEAAX_K@Z; std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0021>::_Construct_n<>(unsigned __int64)
0x1800b7a63  nop
0x1800b7a64  cmp     [rsp+180h+var_13C], r12d
0x1800b7a69  jz      short loc_1800B7A9F
0x1800b7a6b  mov     rcx, [r14]
0x1800b7a6e  mov     rax, [rcx]
0x1800b7a71  mov     r8, [rsp+180h+var_110]
0x1800b7a76  lea     rdx, [rsp+180h+var_13C]
0x1800b7a7b  mov     rax, [rax+100h]
0x1800b7a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7a87  test    eax, eax
0x1800b7a89  jns     short loc_1800B7A93
0x1800b7a8b  mov     ecx, eax; this
0x1800b7a8d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b7a93  cmp     [rsp+180h+var_13C], r12d
0x1800b7a98  mov     [rsp+180h+var_148], r12b
0x1800b7a9d  jnz     short loc_1800B7AA4
0x1800b7a9f  mov     [rsp+180h+var_148], 1
0x1800b7aa4  mov     [rbp+80h+var_D0], r12
0x1800b7aa8  mov     rcx, [r14]
0x1800b7aab  mov     rax, [rcx]
0x1800b7aae  mov     [rbp+80h+var_F8], r12
0x1800b7ab2  lea     rdx, [rbp+80h+var_D0]
0x1800b7ab6  mov     [rbp+80h+var_F0], rdx
0x1800b7aba  lea     rdx, [rbp+80h+var_F8]
0x1800b7abe  mov     rax, [rax+0F0h]
0x1800b7ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7aca  mov     r15d, eax
0x1800b7acd  mov     rdi, [rbp+80h+var_F0]
0x1800b7ad1  mov     rbx, [rbp+80h+var_F8]
0x1800b7ad5  mov     rcx, rdi
0x1800b7ad8  call    ?reset@?$Holder@PEAXU?$close_funct@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@U?$invalid_const@PEAX$0A@@@@@QEAAXXZ; Holder<void *,close_funct<void (*)(void *),&CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(void)
0x1800b7add  mov     [rdi], rbx
0x1800b7ae0  test    r15d, r15d
0x1800b7ae3  jns     short loc_1800B7AEE
0x1800b7ae5  mov     ecx, r15d; this
0x1800b7ae8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b7aee  mov     r12, [rbp+80h+var_D0]
0x1800b7af2  mov     [rbp+80h+var_F8], r12
0x1800b7af6  xor     r15d, r15d
0x1800b7af9  test    r12, r12
0x1800b7afc  jz      short loc_1800B7B0E
0x1800b7afe  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800b7b02  inc     r13
0x1800b7b05  cmp     [r12+r13*2], r15w
0x1800b7b0a  jnz     short loc_1800B7B02
0x1800b7b0c  jmp     short loc_1800B7B11
0x1800b7b0e  mov     r13, r15
0x1800b7b11  movzx   ebx, word ptr [rbp+80h+var_A0]
0x1800b7b15  mov     rax, [rsi]
0x1800b7b18  movss   xmm7, dword ptr [rax+10h]
0x1800b7b1d  mov     [rsp+180h+var_138], r15d
0x1800b7b22  mov     rcx, [r14]
0x1800b7b25  mov     rax, [rcx]
0x1800b7b28  lea     rdx, [rsp+180h+var_138]
0x1800b7b2d  mov     rax, [rax+108h]
0x1800b7b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7b39  test    eax, eax
0x1800b7b3b  jns     short loc_1800B7B45
0x1800b7b3d  mov     ecx, eax; this
0x1800b7b3f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b7b45  movd    xmm0, ebx
0x1800b7b49  cvtdq2ps xmm0, xmm0
0x1800b7b4c  movaps  xmm8, xmm7
0x1800b7b50  divss   xmm8, xmm0
0x1800b7b55  divss   xmm7, cs:__real@42c80000
0x1800b7b5d  lea     rcx, [rsp+180h+var_128]
0x1800b7b62  call    ??0?$vector@V?$shared_ptr@UIXpsOMVisual@@@std@@V?$allocator@V?$shared_ptr@UIXpsOMVisual@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<IXpsOMVisual>>::vector<std::shared_ptr<IXpsOMVisual>>(void)
0x1800b7b67  nop
0x1800b7b68  mov     eax, [rsp+180h+var_138]
0x1800b7b6c  test    eax, eax
0x1800b7b6e  jz      loc_1800B8167
0x1800b7b74  mov     edx, eax
0x1800b7b76  mov     rcx, qword ptr [rsp+180h+var_128+8]
0x1800b7b7b  mov     r8, qword ptr [rsp+180h+var_128]
0x1800b7b80  sub     rcx, r8
0x1800b7b83  sar     rcx, 4
0x1800b7b87  cmp     rax, rcx
0x1800b7b8a  jnb     short loc_1800B7B9A
0x1800b7b8c  shl     rdx, 4
0x1800b7b90  add     rdx, r8
0x1800b7b93  mov     qword ptr [rsp+180h+var_128+8], rdx
0x1800b7b98  jmp     short loc_1800B7BD5
0x1800b7b9a  jbe     short loc_1800B7BD5
0x1800b7b9c  mov     rax, [rsp+180h+var_118]
0x1800b7ba1  sub     rax, r8
0x1800b7ba4  sar     rax, 4
0x1800b7ba8  cmp     rdx, rax
0x1800b7bab  jbe     short loc_1800B7BB9
0x1800b7bad  lea     rcx, [rsp+180h+var_128]
0x1800b7bb2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022@@V?$allocator@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b7bb7  jmp     short loc_1800B7BD0
0x1800b7bb9  sub     rdx, rcx
0x1800b7bbc  lea     r8, [rsp+180h+var_128]
0x1800b7bc1  mov     rcx, qword ptr [rsp+180h+var_128+8]
0x1800b7bc6  call    ??$_Uninitialized_value_construct_n@V?$allocator@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022@@@std@@@std@@YAPEAU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022@@PEAU1@_KAEAV?$allocator@U__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022>>(__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022 *,unsigned __int64,std::allocator<__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0022> &)
0x1800b7bcb  mov     qword ptr [rsp+180h+var_128+8], rax
0x1800b7bd0  mov     r8, qword ptr [rsp+180h+var_128]
0x1800b7bd5  mov     rcx, [r14]
0x1800b7bd8  mov     rax, [rcx]
0x1800b7bdb  lea     rdx, [rsp+180h+var_138]
0x1800b7be0  mov     rax, [rax+110h]
0x1800b7be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7bec  test    eax, eax
0x1800b7bee  jns     short loc_1800B7BF8
0x1800b7bf0  mov     ecx, eax; this
0x1800b7bf2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b7bf8  mov     r14, r15
0x1800b7bfb  mov     rdi, r15
0x1800b7bfe  mov     r9, r15
0x1800b7c01  mov     r10d, 0FFFFh
0x1800b7c07  xorps   xmm6, xmm6
0x1800b7c0a  mov     [rbp+80h+var_D8], r9
0x1800b7c0e  mov     eax, [rsp+180h+var_138]
0x1800b7c12  cmp     r9, rax
0x1800b7c15  jnb     loc_1800B7FB8
0x1800b7c1b  mov     rbx, r9
0x1800b7c1e  add     rbx, rbx
0x1800b7c21  mov     rax, qword ptr [rsp+180h+var_128]
0x1800b7c26  mov     r8d, [rax+rbx*8]
0x1800b7c2a  lea     rdx, [rax+rbx*8]
0x1800b7c2e  cmp     r14, r8
0x1800b7c31  jb      short loc_1800B7C44
0x1800b7c33  mov     r12d, [rdx+8]
0x1800b7c37  cmp     rdi, r12
0x1800b7c3a  jnb     loc_1800B7DE2
0x1800b7c40  mov     r12, [rbp+80h+var_F8]
0x1800b7c44  movzx   ecx, r10w
0x1800b7c48  mov     [rsp+180h+var_150], cx
0x1800b7c4d  mov     eax, [rdx+8]
0x1800b7c50  cmp     rdi, rax
0x1800b7c53  jnb     short loc_1800B7C6F
0x1800b7c55  mov     rcx, rdi
0x1800b7c58  add     rcx, rcx
0x1800b7c5b  mov     rax, [rsp+180h+var_110]
0x1800b7c60  movzx   ecx, word ptr [rax+rcx*8]
0x1800b7c64  mov     [rsp+180h+var_150], cx
0x1800b7c69  cmp     cx, r10w
0x1800b7c6d  jnz     short loc_1800B7CB1
0x1800b7c6f  cmp     r14, r8
0x1800b7c72  jnb     short loc_1800B7CB1
0x1800b7c74  cmp     r14, r13
0x1800b7c77  jnb     short loc_1800B7CB1
0x1800b7c79  movzx   eax, word ptr [r12+r14*2]
0x1800b7c7e  mov     [rsp+180h+var_14C], eax
0x1800b7c82  mov     rax, [rsi]
0x1800b7c85  mov     rcx, [rax]
0x1800b7c88  mov     rax, [rcx]
0x1800b7c8b  lea     r9, [rsp+180h+var_150]
0x1800b7c90  mov     r8d, 1
0x1800b7c96  lea     rdx, [rsp+180h+var_14C]
0x1800b7c9b  mov     rax, [rax+58h]
0x1800b7c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ca4  test    eax, eax
0x1800b7ca6  js      loc_1800B7FA8
0x1800b7cac  movzx   ecx, [rsp+180h+var_150]
0x1800b7cb1  mov     rax, [rsi]
0x1800b7cb4  mov     rdx, [rax+20h]
0x1800b7cb8  cmp     rdx, [rax+28h]
0x1800b7cbc  jz      short loc_1800B7CC8
0x1800b7cbe  mov     [rdx], cx
0x1800b7cc1  add     qword ptr [rax+20h], 2
0x1800b7cc6  jmp     short loc_1800B7CD6
0x1800b7cc8  lea     r8, [rsp+180h+var_150]
0x1800b7ccd  lea     rcx, [rax+18h]
0x1800b7cd1  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x1800b7cd6  xor     eax, eax
0x1800b7cd8  mov     [rsp+180h+var_130], rax
0x1800b7cdd  mov     rax, qword ptr [rsp+180h+var_128]
0x1800b7ce2  mov     ecx, [rax+rbx*8+8]
0x1800b7ce6  cmp     rdi, rcx
0x1800b7ce9  jnb     short loc_1800B7D28
0x1800b7ceb  mov     rcx, rdi
0x1800b7cee  add     rcx, rcx
0x1800b7cf1  mov     rax, [rsp+180h+var_110]
0x1800b7cf6  movaps  xmm2, xmm7
0x1800b7cf9  mulss   xmm2, dword ptr [rax+rcx*8+4]
0x1800b7cff  movss   [rsp+180h+var_14C], xmm2
0x1800b7d05  movaps  xmm0, xmm7
0x1800b7d08  mulss   xmm0, dword ptr [rax+rcx*8+8]
0x1800b7d0e  movss   dword ptr [rsp+180h+var_130], xmm0
0x1800b7d14  movaps  xmm1, xmm7
0x1800b7d17  mulss   xmm1, dword ptr [rax+rcx*8+0Ch]
0x1800b7d1d  movss   dword ptr [rsp+180h+var_130+4], xmm1
0x1800b7d23  comiss  xmm6, xmm2
0x1800b7d26  jbe     short loc_1800B7D83
0x1800b7d28  xorps   xmm0, xmm0
0x1800b7d2b  movups  [rbp+80h+var_88], xmm0
  ... truncated ...
```
