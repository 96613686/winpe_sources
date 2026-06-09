# xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMGradientBrush> const &)

- ea: `0x18002e684`
- end: `0x18002f6e0`
- name: `?Fill@CGDIPathData@xgc@@AEBAXAEBV?$shared_ptr@UIXpsOMGradientBrush@@@std@@@Z`
- size: `4188`
- prototype: `__int64 __fastcall(xgc::CGDIPathData *this)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x180030284`

## callees

- `0x180008830`
- `0x180009de0`
- `0x18000d428`
- `0x18000e15c`
- `0x18000e174`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x180011d1c`
- `0x180011fb8`
- `0x18001599c`
- `0x180015aac`
- `0x180015c00`
- `0x180026100`
- `0x180026438`
- `0x180026c28`
- `0x180026c5c`
- `0x180026f94`
- `0x18002bb00`
- `0x18002ccb4`
- `0x18002dcfc`
- `0x18002e15c`
- `0x18002e220`
- `0x18002e684`
- `0x180030934`
- `0x18003095c`
- `0x1800309b0`
- `0x180036250`
- `0x180037278`
- `0x1800372e4`
- `0x18004a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002f0c1`
- `KERNEL32!GetLastError` at `0x18002f0c1`
- `GDI32!SaveDC` at `0x18002f0b4`
- `GDI32!SaveDC` at `0x18002f0b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
double __fastcall xgc::CGDIPathData::Fill(xgc::CGDIPathData *this, __int64 **a2, __int64 a3, float a4)
{
  xgc::CGDIPathData *v5; // rsi
  int v6; // eax
  int v7; // edx
  const char *v8; // r8
  int v9; // r9d
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  const char *v13; // rdx
  const char *v14; // r8
  int v15; // r9d
  xpsrdr *v16; // rcx
  int v17; // eax
  const char *v18; // rdx
  const char *v19; // r8
  int v20; // r9d
  xpsrdr *v21; // rcx
  __int64 *v22; // rcx
  __int64 v23; // rax
  int v24; // ebx
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  int v28; // eax
  const char *v29; // rdx
  xpsrdr *v30; // rcx
  const char *v31; // r8
  int v32; // r9d
  unsigned int i; // ebx
  __int64 v34; // rax
  int v35; // r14d
  int v36; // edx
  const char *v37; // r8
  int v38; // r9d
  int v39; // eax
  int v40; // edx
  const char *v41; // r8
  int v42; // r9d
  __int64 v43; // rax
  int v44; // r14d
  int v45; // edx
  const char *v46; // r8
  int v47; // r9d
  _OWORD *D2D1Color; // rax
  _QWORD *v49; // rax
  _QWORD *v50; // rax
  __int64 v51; // r8
  int v52; // r14d
  int v53; // r15d
  __int64 j; // rdx
  float v55; // xmm0_4
  int v56; // eax
  float v57; // xmm9_4
  float v58; // xmm10_4
  float v59; // xmm7_4
  float v60; // xmm11_4
  __int64 v61; // rax
  float v62; // xmm1_4
  float v63; // xmm12_4
  float v64; // xmm13_4
  float v65; // xmm6_4
  float v66; // xmm14_4
  float v67; // xmm6_4
  unsigned int v68; // r13d
  unsigned int v69; // r12d
  __int64 v70; // rdx
  unsigned int k; // esi
  int v72; // edx
  int v73; // ecx
  int v74; // eax
  unsigned int m; // esi
  const struct D2D_MATRIX_3X2_F *v76; // rdx
  __int64 v77; // r8
  signed int LastError; // eax
  int v79; // edx
  const char *v80; // r8
  int v81; // r9d
  unsigned __int64 *v82; // r14
  int v83; // eax
  unsigned __int64 v84; // r10
  signed int v85; // r11d
  int v86; // ebx
  __int64 v87; // r9
  int v88; // r8d
  int v89; // ecx
  int v90; // ecx
  _QWORD **v91; // r14
  __int64 v92; // rcx
  __int64 v93; // rax
  int v94; // ebx
  int v95; // edx
  const char *v96; // r8
  int v97; // r9d
  const char *v98; // rdx
  int v99; // r8d
  int v100; // eax
  int v101; // edx
  const char *v102; // r8
  int v103; // r9d
  xpsrdr *v104; // rcx
  __int64 (__fastcall ***v105)(_QWORD, GUID *, _BYTE *); // rcx
  __int64 (__fastcall **v106)(_QWORD, GUID *, _BYTE *); // rax
  int v107; // ebx
  int v108; // edx
  const char *v109; // r8
  int v110; // r9d
  int v111; // eax
  int v112; // edx
  const char *v113; // r8
  int v114; // r9d
  int v115; // eax
  int v116; // edx
  const char *v117; // r8
  int v118; // r9d
  int v119; // eax
  const struct D2D_MATRIX_3X2_F *v120; // rdx
  const char *v121; // r8
  int v122; // r9d
  struct tagPOINT v123; // rbx
  float v124; // xmm9_4
  float v125; // xmm8_4
  float v126; // xmm7_4
  const struct D2D_MATRIX_3X2_F *v127; // rdx
  const struct D2D_MATRIX_3X2_F *v128; // rdx
  const struct D2D_MATRIX_3X2_F *v129; // rdx
  __int64 (__fastcall ***v130)(_QWORD, GUID *, _BYTE *); // rcx
  __int64 (__fastcall **v131)(_QWORD, GUID *, _BYTE *); // rax
  int v132; // ebx
  int v133; // edx
  const char *v134; // r8
  int v135; // r9d
  int v136; // eax
  int v137; // edx
  const char *v138; // r8
  int v139; // r9d
  int v140; // eax
  const struct D2D_MATRIX_3X2_F *v141; // rdx
  const char *v142; // r8
  int v143; // r9d
  xgc *v144; // rdi
  const struct D2D_MATRIX_3X2_F *v145; // rdx
  struct tagPOINT v146; // rbx
  const struct D2D_MATRIX_3X2_F *v147; // rdx
  struct tagPOINT v148; // rax
  struct tagPOINT v149; // r9
  struct tagPOINT v150; // r10
  bool v152; // [rsp+28h] [rbp-E0h]
  bool v153; // [rsp+28h] [rbp-E0h]
  bool v154; // [rsp+28h] [rbp-E0h]
  bool v155; // [rsp+28h] [rbp-E0h]
  bool v156; // [rsp+28h] [rbp-E0h]
  bool v157; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v158; // [rsp+58h] [rbp-B0h]
  xpsrdr *v159; // [rsp+60h] [rbp-A8h] BYREF
  float v160[4]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v161; // [rsp+78h] [rbp-90h] BYREF
  float v162[4]; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v163; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v164; // [rsp+94h] [rbp-74h]
  xgc::CGDIPathData *v165; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v166; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v167; // [rsp+A8h] [rbp-60h]
  struct D2D_MATRIX_3X2_F v168; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int v169; // [rsp+C8h] [rbp-40h] BYREF
  unsigned int v170; // [rsp+CCh] [rbp-3Ch] BYREF
  struct Gdiplus::Color *v171; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v172; // [rsp+D8h] [rbp-30h]
  __int64 v173; // [rsp+E0h] [rbp-28h]
  _QWORD v174[3]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v175[3]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v176[2]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v177[2]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v178[24]; // [rsp+138h] [rbp+30h] BYREF
  struct D2D_MATRIX_3X2_F v179; // [rsp+150h] [rbp+48h] BYREF
  _OWORD v180[3]; // [rsp+168h] [rbp+60h] BYREF

  *(_QWORD *)&v168.m11 = a2;
  v5 = this;
  v165 = this;
  v163 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a2 + 32))(*a2, &v163);
  if ( v6 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v6, v7, v8, v9);
  if ( v163 == 9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) == 0 )
      goto LABEL_11;
    v11 = 13;
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) == 0 )
      goto LABEL_11;
    v11 = 14;
  }
  WPP_SF_(v10[27], v11, WPP_00624022ad39391a483a764a1c0090f0_Traceguids);
LABEL_11:
  v169 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a2 + 104))(*a2, &v169);
  if ( v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, (int)v13, v14, v15);
  switch ( v169 )
  {
    case 1u:
      v164 = 4;
      break;
    case 2u:
      v164 = 3;
      break;
    case 3u:
      v164 = 0;
      break;
    default:
      v16 = (xpsrdr *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, WPP_00624022ad39391a483a764a1c0090f0_Traceguids, v169);
      xpsrdr::ThrowLogicException(v16, v13, (int)v14);
  }
  v170 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(**a2 + 120))(*a2, &v170);
  if ( v17 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, (int)v18, v19, v20);
  if ( v170 == 1 )
  {
    v158 = 1;
  }
  else
  {
    if ( v170 != 2 )
    {
      v21 = (xpsrdr *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, WPP_00624022ad39391a483a764a1c0090f0_Traceguids, v170);
      xpsrdr::ThrowLogicException(v21, v18, (int)v19);
    }
    v158 = 0;
  }
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v177);
  LODWORD(v159) = 0;
  v22 = *a2;
  v23 = **a2;
  *(_QWORD *)&v179.m11 = 0;
  *(_QWORD *)&v179.m[1][0] = &v159;
  *(_QWORD *)&v179.m[2][0] = v177;
  v24 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(v23 + 56))(v22, &v179);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v179);
  if ( (int)v159 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v159, v25, v26, v27);
  if ( v24 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
  LODWORD(v161) = 0;
  v28 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v177[0] + 24LL))(v177[0], &v161);
  if ( v28 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, (int)v29, v31, v32);
  if ( !(_DWORD)v161 )
    xpsrdr::ThrowLogicException(v30, v29, (int)v31);
  std::vector<CCoordinate>::vector<CCoordinate>(v174, v29);
  std::vector<xgc::CGradientStop>::reserve(v174, (unsigned int)v161);
  for ( i = 0; i < (unsigned int)v161; ++i )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v166);
    LODWORD(v159) = 0;
    v34 = *(_QWORD *)v177[0];
    *(_QWORD *)v178 = 0;
    *(_QWORD *)&v178[8] = &v159;
    *(_QWORD *)&v178[16] = &v166;
    v35 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *))(v34 + 32))(v177[0], i, v178);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v178);
    if ( (int)v159 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v159, v36, v37, v38);
    if ( v35 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v36, v37, v38);
    v160[0] = 0.0;
    v39 = (*(__int64 (__fastcall **)(unsigned __int64, float *))(*(_QWORD *)v166 + 32LL))(v166, v160);
    if ( v39 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v39, v40, v41, v42);
    memset(v180, 0, 44);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v162);
    LODWORD(v159) = 0;
    v43 = *(_QWORD *)v166;
    *(_QWORD *)v178 = 0;
    *(_QWORD *)&v178[8] = &v159;
    *(_QWORD *)&v178[16] = v162;
    v44 = (*(__int64 (__fastcall **)(unsigned __int64, _OWORD *, _BYTE *))(v43 + 48))(v166, v180, v178);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v178);
    if ( (int)v159 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v159, v45, v46, v47);
    if ( v44 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v44, v45, v46, v47);
    D2D1Color = (_OWORD *)xpsrdr::GetD2D1Color(&v179, *((_QWORD *)v5 + 14), v180, v162);
    *(float *)v178 = v160[0];
    *(_OWORD *)&v178[4] = *D2D1Color;
    *(_DWORD *)&v178[20] = i;
    std::vector<xgc::CGradientStop>::push_back(v174, v178);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v162);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v166);
  }
  v49 = (_QWORD *)std::vector<CCoordinate>::end(v174, v162);
  v50 = (_QWORD *)std::vector<tagRGBQUAD>::begin(v174, v160, *v49);
  std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<xgc::CGradientStop>>>>(*v50, v51);
  v52 = -1;
  v53 = v161;
  for ( j = 0; (unsigned int)j < (unsigned int)v161; j = (unsigned int)(j + 1) )
  {
    v55 = *(float *)(v174[0] + 24LL * (unsigned int)j);
    v56 = v52 + 1;
    if ( v55 >= 0.0 )
      v56 = v52;
    v52 = v56;
    if ( v55 > 1.0 )
    {
      v53 = j;
      break;
    }
  }
  if ( v52 == -1 )
  {
    v57 = *(float *)(v174[0] + 4LL);
    v58 = *(float *)(v174[0] + 8LL);
    v59 = *(float *)(v174[0] + 12LL);
    v60 = *(float *)(v174[0] + 16LL);
  }
  else
  {
    v61 = (unsigned int)(v161 - 1);
    if ( v52 == (_DWORD)v61 )
    {
      v57 = *(float *)(v174[0] + 24 * v61 + 4);
      v58 = *(float *)(v174[0] + 24 * v61 + 8);
      v59 = *(float *)(v174[0] + 24 * v61 + 12);
      v60 = *(float *)(v174[0] + 24 * v61 + 16);
    }
    else
    {
      j = 3LL * v52;
      v62 = (float)(0.0 - *(float *)(v174[0] + 24LL * v52))
          / (float)(*(float *)(v174[0] + 24LL * v52 + 24) - *(float *)(v174[0] + 24LL * v52));
      v60 = (float)((float)(1.0 - v62) * *(float *)(v174[0] + 24LL * v52 + 16))
          + (float)(v62 * *(float *)(v174[0] + 24LL * v52 + 40));
      v57 = (float)((float)(1.0 - v62) * *(float *)(v174[0] + 24LL * v52 + 4))
          + (float)(v62 * *(float *)(v174[0] + 24LL * v52 + 28));
      v58 = (float)((float)(1.0 - v62) * *(float *)(v174[0] + 24LL * v52 + 8))
          + (float)(v62 * *(float *)(v174[0] + 24LL * v52 + 32));
      v59 = (float)((float)(1.0 - v62) * *(float *)(v174[0] + 24LL * v52 + 12))
          + (float)(v62 * *(float *)(v174[0] + 24LL * v52 + 36));
    }
  }
  if ( v53 )
  {
    if ( v53 == (_DWORD)v161 )
    {
      v63 = *(float *)(v174[0] + 24LL * (unsigned int)(v161 - 1) + 4);
      v64 = *(float *)(v174[0] + 24LL * (unsigned int)(v161 - 1) + 8);
      v65 = *(float *)(v174[0] + 24LL * (unsigned int)(v161 - 1) + 12);
      v66 = *(float *)(v174[0] + 24LL * (unsigned int)(v161 - 1) + 16);
    }
    else
    {
      j = 3LL * v53;
      v67 = (float)(1.0 - *(float *)(v174[0] + 24LL * v53 - 24))
          / (float)(*(float *)(v174[0] + 24LL * v53) - *(float *)(v174[0] + 24LL * v53 - 24));
      v66 = (float)(v67 * *(float *)(v174[0] + 24LL * v53 + 16))
          + (float)((float)(1.0 - v67) * *(float *)(v174[0] + 24LL * v53 - 8));
      v63 = (float)(v67 * *(float *)(v174[0] + 24LL * v53 + 4))
          + (float)((float)(1.0 - v67) * *(float *)(v174[0] + 24LL * v53 - 20));
      v64 = (float)(v67 * *(float *)(v174[0] + 24LL * v53 + 8))
          + (float)((float)(1.0 - v67) * *(float *)(v174[0] + 24LL * v53 - 16));
      v65 = (float)(v67 * *(float *)(v174[0] + 24LL * v53 + 12))
          + (float)((float)(1.0 - v67) * *(float *)(v174[0] + 24LL * v53 - 12));
    }
  }
  else
  {
    v63 = *(float *)(v174[0] + 4LL);
    v64 = *(float *)(v174[0] + 8LL);
    v65 = *(float *)(v174[0] + 12LL);
    v66 = *(float *)(v174[0] + 16LL);
  }
  v68 = v53 - v52;
  v69 = v53 - v52 + 1;
  std::vector<CCoordinate>::vector<CCoordinate>(&v171, j);
  *(_QWORD *)v162 = v69;
  if ( v69 > (unsigned __int64)((v173 - (__int64)v171) >> 2) )
    std::vector<float>::_Reallocate<0>(&v171, v162);
  std::vector<CCoordinate>::vector<CCoordinate>(v175, v70);
  *(_QWORD *)v162 = v69;
  if ( v69 > (unsigned __int64)((v175[2] - v175[0]) >> 2) )
    std::vector<float>::_Reallocate<0>(v175, v162);
  if ( v163 == 9 )
  {
    if ( v69 <= 2 || *(float *)(v174[0] + 24LL * v53 - 24) < 1.0 )
    {
      v160[0] = 0.0;
      std::vector<float>::push_back(v175, v160);
      LODWORD(v160[0]) = (unsigned __int8)(int)(float)(v65 * 255.0)
                       | (((unsigned __int8)(int)(float)(v64 * 255.0)
                         | (((unsigned __int8)(int)(float)(v63 * 255.0)
                           | ((unsigned __int8)(int)(float)(v66 * 255.0) << 8)) << 8)) << 8);
      std::vector<Gdiplus::Color>::push_back(&v171, v160);
    }
    LODWORD(v160[0]) = 1;
    if ( v68 > 1 )
    {
      for ( k = 1; k < v68; ++k )
      {
        v160[0] = 1.0 - *(float *)(v174[0] + 24LL * (v53 - k));
        std::vector<float>::push_back(v175, v160);
        LODWORD(v160[0]) = (unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (v53 - k) + 12) * 255.0)
                         | (((unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (v53 - k) + 8) * 255.0)
                           | (((unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (v53 - k) + 4) * 255.0)
                             | ((unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (v53 - k) + 16) * 255.0) << 8)) << 8)) << 8);
        std::vector<Gdiplus::Color>::push_back(&v171, v160);
      }
      v5 = v165;
    }
    if ( v69 <= 2 || *(float *)(v174[0] + 24 * (v52 + 1LL)) > 0.0 )
    {
      v160[0] = 1.0;
      std::vector<float>::push_back(v175, v160);
      v72 = (unsigned __int8)(int)(float)(v57 * 255.0) | ((unsigned __int8)(int)(float)(v60 * 255.0) << 8);
      v73 = (unsigned __int8)(int)(float)(v58 * 255.0);
      v74 = (int)(float)(v59 * 255.0);
LABEL_96:
      LODWORD(v160[0]) = (unsigned __int8)v74 | ((v73 | (v72 << 8)) << 8);
      std::vector<Gdiplus::Color>::push_back(&v171, v160);
    }
  }
  else
  {
    if ( v69 <= 2 || *(float *)(v174[0] + 24 * (v52 + 1LL)) > 0.0 )
    {
      v160[0] = 0.0;
      std::vector<float>::push_back(v175, v160);
      LODWORD(v160[0]) = (unsigned __int8)(int)(float)(v59 * 255.0)
                       | (((unsigned __int8)(int)(float)(v58 * 255.0)
                         | (((unsigned __int8)(int)(float)(v57 * 255.0)
                           | ((unsigned __int8)(int)(float)(v60 * 255.0) << 8)) << 8)) << 8);
      std::vector<Gdiplus::Color>::push_back(&v171, v160);
    }
    LODWORD(v160[0]) = 1;
    if ( v68 > 1 )
    {
      for ( m = 1; m < v68; ++m )
      {
        std::vector<float>::push_back(v175, v174[0] + 24LL * (m + v52));
        LODWORD(v160[0]) = (unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (m + v52) + 12) * 255.0)
                         | (((unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (m + v52) + 8) * 255.0)
                           | (((unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (m + v52) + 4) * 255.0)
                             | ((unsigned __int8)(int)(float)(*(float *)(v174[0] + 24LL * (m + v52) + 16) * 255.0) << 8)) << 8)) << 8);
        std::vector<Gdiplus::Color>::push_back(&v171, v160);
      }
      v5 = v165;
    }
    if ( v69 <= 2 || *(float *)(v174[0] + 24LL * v53 - 24) < 1.0 )
    {
      v160[0] = 1.0;
      std::vector<float>::push_back(v175, v160);
      v72 = (unsigned __int8)(int)(float)(v63 * 255.0) | ((unsigned __int8)(int)(float)(v66 * 255.0) << 8);
      v73 = (unsigned __int8)(int)(float)(v64 * 255.0);
      v74 = (int)(float)(v65 * 255.0);
      goto LABEL_96;
    }
  }
  if ( !SaveDC(*(HDC *)(*((_QWORD *)v5 + 2) + 32LL)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v79, v80, v81);
  }
  xgc::CGDIPathData::Clip(v5, v76, v77, a4);
  v82 = (unsigned __int64 *)*((_QWORD *)v5 + 5);
  v166 = *v82;
  v83 = v166;
  v84 = HIDWORD(v166);
  v85 = v166;
  v167 = v166;
  v86 = HIDWORD(v166);
  v87 = (unsigned int)((__int64)(*((_QWORD *)v5 + 6) - (_QWORD)v82) >> 3) - 1;
  if ( (int)(((__int64)(*((_QWORD *)v5 + 6) - (_QWORD)v82) >> 3) - 1) > 0 )
  {
    do
    {
      v88 = v82[v87];
      v89 = v88;
      if ( v88 >= v83 )
        v89 = v83;
      v83 = v89;
      LODWORD(v166) = v89;
      v90 = HIDWORD(v82[v87]);
      if ( v90 < (int)v84 )
        LODWORD(v84) = HIDWORD(v82[v87]);
      HIDWORD(v166) = v84;
      if ( v88 > v85 )
        v85 = v88;
      if ( v90 > v86 )
        v86 = v90;
      v87 = (unsigned int)(v87 - 1);
    }
    while ( (int)v87 > 0 );
    v167 = __PAIR64__(v86, v85);
  }
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v176);
  v160[0] = 0.0;
  v91 = *(_QWORD ***)&v168.m11;
  v92 = **(_QWORD **)&v168.m11;
  v93 = ***(_QWORD ***)&v168.m11;
  *(_QWORD *)v178 = 0;
  *(_QWORD *)&v178[8] = v160;
  *(_QWORD *)&v178[16] = v176;
  v94 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(v93 + 64))(v92, v178);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v178);
  if ( v160[0] < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v160[0]), v95, v96, v97);
  if ( v94 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v94, v95, v96, v97);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v176) )
  {
    memset(&v179, 0, sizeof(v179));
    v100 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v176[0] + 40LL))(v176[0], &v179);
    if ( v100 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v100, v101, v102, v103);
    v168 = v179;
    xgc::CDeviceContext::PushTransform(*((struct D2D_MATRIX_3X2_F **)v5 + 2), &v168);
  }
  if ( v163 == 8 )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v168);
    v160[0] = 0.0;
    v130 = (__int64 (__fastcall ***)(_QWORD, GUID *, _BYTE *))*v91;
    v131 = (__int64 (__fastcall **)(_QWORD, GUID *, _BYTE *))**v91;
    *(_QWORD *)v178 = 0;
    *(_QWORD *)&v178[8] = v160;
    *(_QWORD *)&v178[16] = &v168;
    v132 = (*v131)(v130, &GUID_005e279f_c30d_40ff_93ec_1950d3c528db, v178);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v178);
    if ( v160[0] < 0.0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v160[0]), v133, v134, v135);
    if ( v132 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v132, v133, v134, v135);
    *(_QWORD *)v162 = 0;
    v159 = 0;
    v136 = (*(__int64 (__fastcall **)(_QWORD, float *))(**(_QWORD **)&v168.m11 + 136LL))(*(_QWORD *)&v168.m11, v162);
    if ( v136 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v136, v137, v138, v139);
    v140 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(**(_QWORD **)&v168.m11 + 152LL))(*(_QWORD *)&v168.m11, &v159);
    if ( v140 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v140, (int)v141, v142, v143);
    v144 = (xgc *)xgc::TransformPoints((xgc *)(*((_QWORD *)v5 + 2) + 40LL), v141, v162[1], a4, v152);
    v146 = xgc::TransformPoints((xgc *)(*((_QWORD *)v5 + 2) + 40LL), v145, *((float *)&v159 + 1), a4, v156);
    v148 = xgc::TransformPoints(
             (xgc *)(*((_QWORD *)v5 + 2) + 40LL),
             v147,
             (float)(*((float *)&v159 + 1) - v162[0]) + *(float *)&v159,
             a4,
             v157);
    xgc::CalculateProjectionPoint(v144, v146, v148, v149);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v176) )
      xgc::CDeviceContext::PopTransform(*((xgc::CDeviceContext **)v5 + 2));
    xgc::CDeviceContext::DrawLinearGradient(
      *((_QWORD *)v5 + 2),
      v144,
      v150,
      v164,
      v171,
      v175[0],
      (v172 - (__int64)v171) >> 2,
      v158,
      (struct tagPOINT)&v166);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v168);
  }
  else
  {
    if ( v163 != 9 )
    {
      v104 = (xpsrdr *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, WPP_00624022ad39391a483a764a1c0090f0_Traceguids, v163);
      xpsrdr::ThrowLogicException(v104, v98, v99);
    }
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v168);
    v160[0] = 0.0;
    v105 = (__int64 (__fastcall ***)(_QWORD, GUID *, _BYTE *))*v91;
    v106 = (__int64 (__fastcall **)(_QWORD, GUID *, _BYTE *))**v91;
    *(_QWORD *)v178 = 0;
    *(_QWORD *)&v178[8] = v160;
    *(_QWORD *)&v178[16] = &v168;
    v107 = (*v106)(v105, &GUID_75f207e5_08bf_413c_96b1_b82b4064176b, v178);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v178);
    if ( v160[0] < 0.0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v160[0]), v108, v109, v110);
    if ( v107 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v107, v108, v109, v110);
    v159 = 0;
    v165 = 0;
    *(_QWORD *)v162 = 0;
    v111 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(**(_QWORD **)&v168.m11 + 136LL))(*(_QWORD *)&v168.m11, &v159);
    if ( v111 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v111, v112, v113, v114);
    v115 = (*(__int64 (__fastcall **)(_QWORD, xgc::CGDIPathData **))(**(_QWORD **)&v168.m11 + 168LL))(
             *(_QWORD *)&v168.m11,
             &v165);
    if ( v115 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v115, v116, v117, v118);
    v119 = (*(__int64 (__fastcall **)(_QWORD, float *))(**(_QWORD **)&v168.m11 + 152LL))(*(_QWORD *)&v168.m11, v162);
    if ( v119 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v119, (int)v120, v121, v122);
    v123 = xgc::TransformPoints((xgc *)(*((_QWORD *)v5 + 2) + 40LL), v120, *((float *)&v165 + 1), a4, v152);
    v124 = *(float *)&v159 - v162[0];
    v125 = *((float *)&v159 + 1) - v162[1];
    v126 = v162[1] + *((float *)&v159 + 1);
    *(struct tagPOINT *)v178 = xgc::TransformPoints(
                                 (xgc *)(*((_QWORD *)v5 + 2) + 40LL),
                                 v127,
                                 *((float *)&v159 + 1) - v162[1],
                                 a4,
                                 v153);
    *(struct tagPOINT *)&v178[8] = xgc::TransformPoints((xgc *)(*((_QWORD *)v5 + 2) + 40LL), v128, v125, a4, v154);
    *(struct tagPOINT *)&v178[16] = xgc::TransformPoints((xgc *)(*((_QWORD *)v5 + 2) + 40LL), v129, v126, a4, v155);
    v160[0] = v124;
    v160[1] = v125;
    v160[2] = v162[0] * 2.0;
    v160[3] = v162[1] * 2.0;
    if ( (unsigned __int8)std::operator!=<ID3D11Device>(v176) )
      xgc::CDeviceContext::PopTransform(*((xgc::CDeviceContext **)v5 + 2));
    xgc::CDeviceContext::DrawRadialGradient(
      *((_QWORD *)v5 + 2),
      *(_QWORD *)&v123,
      (__int64)v160,
      v164,
      v171,
      v175[0],
      (v172 - (__int64)v171) >> 2,
      v158,
      (int *)v178,
      (unsigned int *)&v166);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v168);
  }
  xgc::CDeviceContext::Restore(*((xgc::CDeviceContext **)v5 + 2));
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v176);
  std::vector<tagRGBQUAD>::_Tidy(v175);
  std::vector<tagRGBQUAD>::_Tidy(&v171);
  std::vector<D2D_MATRIX_3X2_F>::_Tidy(v174);
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v177);
}

```

## disassembly

```asm
0x18002e684  mov     rax, rsp
0x18002e687  mov     [rax+18h], rbx
0x18002e68b  push    rbp
0x18002e68c  push    rsi
0x18002e68d  push    rdi
0x18002e68e  push    r12
0x18002e690  push    r13
0x18002e692  push    r14
0x18002e694  push    r15
0x18002e696  lea     rbp, [rax-178h]
0x18002e69d  sub     rsp, 240h
0x18002e6a4  movaps  xmmword ptr [rax-48h], xmm6
0x18002e6a8  movaps  xmmword ptr [rax-58h], xmm7
0x18002e6ac  movaps  xmmword ptr [rax-68h], xmm8
0x18002e6b1  movaps  xmmword ptr [rax-78h], xmm9
0x18002e6b6  movaps  xmmword ptr [rax-88h], xmm10
0x18002e6be  movaps  xmmword ptr [rax-98h], xmm11
0x18002e6c6  movaps  xmmword ptr [rax-0A8h], xmm12
0x18002e6ce  movaps  xmmword ptr [rax-0B8h], xmm13
0x18002e6d6  movaps  xmmword ptr [rax-0C8h], xmm14
0x18002e6de  movaps  xmmword ptr [rax-0D8h], xmm15
0x18002e6e6  mov     rax, cs:__security_cookie
0x18002e6ed  xor     rax, rsp
0x18002e6f0  mov     [rbp+170h+var_E0], rax
0x18002e6f7  mov     r14, rdx
0x18002e6fa  mov     qword ptr [rbp+170h+var_1C8], rdx
0x18002e6fe  mov     rsi, rcx
0x18002e701  mov     qword ptr [rbp+170h+var_1E0], rcx
0x18002e705  xor     r12d, r12d
0x18002e708  mov     [rbp+170h+var_1E8], r12d
0x18002e70c  mov     rcx, [rdx]
0x18002e70f  mov     rax, [rcx]
0x18002e712  lea     rdx, [rbp+170h+var_1E8]
0x18002e716  mov     rax, [rax+20h]
0x18002e71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e71f  test    eax, eax
0x18002e721  jns     short loc_18002E72B
0x18002e723  mov     ecx, eax; this
0x18002e725  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e72b  lea     r15, WPP_00624022ad39391a483a764a1c0090f0_Traceguids
0x18002e732  cmp     [rbp+170h+var_1E8], 9
0x18002e736  jnz     short loc_18002E75B
0x18002e738  lea     rbx, WPP_GLOBAL_Control
0x18002e73f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e746  cmp     rcx, rbx
0x18002e749  jz      short loc_18002E78B
0x18002e74b  test    byte ptr [rcx+0E4h], 8
0x18002e752  jz      short loc_18002E78B
0x18002e754  mov     edx, 0Dh
0x18002e759  jmp     short loc_18002E77C
0x18002e75b  lea     rbx, WPP_GLOBAL_Control
0x18002e762  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e769  cmp     rcx, rbx
0x18002e76c  jz      short loc_18002E78B
0x18002e76e  test    byte ptr [rcx+0E4h], 8
0x18002e775  jz      short loc_18002E78B
0x18002e777  mov     edx, 0Eh
0x18002e77c  mov     r8, r15
0x18002e77f  mov     rcx, [rcx+0D8h]
0x18002e786  call    WPP_SF_
0x18002e78b  mov     [rbp+170h+var_1B0], r12d
0x18002e78f  mov     rcx, [r14]
0x18002e792  mov     rax, [rcx]
0x18002e795  lea     rdx, [rbp+170h+var_1B0]
0x18002e799  mov     rax, [rax+68h]
0x18002e79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7a2  test    eax, eax
0x18002e7a4  jns     short loc_18002E7AE
0x18002e7a6  mov     ecx, eax; this
0x18002e7a8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e7ae  mov     r9d, [rbp+170h+var_1B0]
0x18002e7b2  mov     ecx, r9d
0x18002e7b5  sub     ecx, 1
0x18002e7b8  jz      short loc_18002E805
0x18002e7ba  sub     ecx, 1
0x18002e7bd  jz      short loc_18002E7FC
0x18002e7bf  cmp     ecx, 1
0x18002e7c2  jz      short loc_18002E7F6
0x18002e7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7cb  cmp     rcx, rbx
0x18002e7ce  jz      short loc_18002E7F0
0x18002e7d0  mov     edi, 1
0x18002e7d5  test    [rcx+0E4h], dil
0x18002e7dc  jz      short loc_18002E7F0
0x18002e7de  lea     edx, [rdi+0Eh]
0x18002e7e1  mov     r8, r15
0x18002e7e4  mov     rcx, [rcx+0D8h]
0x18002e7eb  call    WPP_SF_d
0x18002e7f0  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18002e7f6  mov     [rbp+170h+var_1E4], r12d
0x18002e7fa  jmp     short loc_18002E80C
0x18002e7fc  mov     [rbp+170h+var_1E4], 3
0x18002e803  jmp     short loc_18002E80C
0x18002e805  mov     [rbp+170h+var_1E4], 4
0x18002e80c  mov     [rbp+170h+var_1AC], r12d
0x18002e810  mov     rcx, [r14]
0x18002e813  mov     rax, [rcx]
0x18002e816  lea     rdx, [rbp+170h+var_1AC]
0x18002e81a  mov     rax, [rax+78h]
0x18002e81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e823  test    eax, eax
0x18002e825  jns     short loc_18002E82F
0x18002e827  mov     ecx, eax; this
0x18002e829  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e82f  mov     r9d, [rbp+170h+var_1AC]
0x18002e833  mov     ecx, r9d
0x18002e836  mov     edi, 1
0x18002e83b  sub     ecx, edi
0x18002e83d  jz      short loc_18002E877
0x18002e83f  cmp     ecx, edi
0x18002e841  jz      short loc_18002E870
0x18002e843  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e84a  cmp     rcx, rbx
0x18002e84d  jz      short loc_18002E86A
0x18002e84f  test    [rcx+0E4h], dil
0x18002e856  jz      short loc_18002E86A
0x18002e858  lea     edx, [rdi+0Fh]
0x18002e85b  mov     r8, r15
0x18002e85e  mov     rcx, [rcx+0D8h]
0x18002e865  call    WPP_SF_d
0x18002e86a  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18002e870  mov     byte ptr [rsp+270h+var_220], r12b
0x18002e875  jmp     short loc_18002E87C
0x18002e877  mov     byte ptr [rsp+270h+var_220], dil
0x18002e87c  lea     rcx, [rbp+170h+var_150]
0x18002e880  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002e885  nop
0x18002e886  mov     dword ptr [rsp+270h+var_218], r12d
0x18002e88b  mov     rcx, [r14]
0x18002e88e  mov     rax, [rcx]
0x18002e891  mov     qword ptr [rbp+170h+var_128], r12
0x18002e895  lea     rdx, [rsp+270h+var_218]
0x18002e89a  mov     qword ptr [rbp+170h+var_128+8], rdx
0x18002e89e  lea     rdx, [rbp+170h+var_150]
0x18002e8a2  mov     [rbp+170h+var_118], rdx
0x18002e8a6  lea     rdx, [rbp+170h+var_128]
0x18002e8aa  mov     rax, [rax+38h]
0x18002e8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8b3  mov     ebx, eax
0x18002e8b5  lea     rcx, [rbp+170h+var_128]
0x18002e8b9  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002e8be  mov     ecx, dword ptr [rsp+270h+var_218]; this
0x18002e8c2  test    ecx, ecx
0x18002e8c4  jns     short loc_18002E8CC
0x18002e8c6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e8cc  test    ebx, ebx
0x18002e8ce  jns     short loc_18002E8D8
0x18002e8d0  mov     ecx, ebx; this
0x18002e8d2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e8d8  mov     dword ptr [rsp+270h+var_200], r12d
0x18002e8dd  mov     rcx, [rbp+170h+var_150]
0x18002e8e1  mov     rax, [rcx]
0x18002e8e4  lea     rdx, [rsp+270h+var_200]
0x18002e8e9  mov     rax, [rax+18h]
0x18002e8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8f2  test    eax, eax
0x18002e8f4  jns     short loc_18002E8FE
0x18002e8f6  mov     ecx, eax; this
0x18002e8f8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e8fe  cmp     dword ptr [rsp+270h+var_200], r12d
0x18002e903  ja      short loc_18002E90B
0x18002e905  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18002e90b  lea     rcx, [rbp+170h+var_190]
0x18002e90f  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x18002e914  nop
0x18002e915  mov     edx, dword ptr [rsp+270h+var_200]
0x18002e919  lea     rcx, [rbp+170h+var_190]
0x18002e91d  call    ?reserve@?$vector@UCGradientStop@xgc@@V?$allocator@UCGradientStop@xgc@@@std@@@std@@QEAAX_K@Z; std::vector<xgc::CGradientStop>::reserve(unsigned __int64)
0x18002e922  mov     ebx, r12d
0x18002e925  cmp     ebx, dword ptr [rsp+270h+var_200]
0x18002e929  jnb     loc_18002EA90
0x18002e92f  lea     rcx, [rbp+170h+var_1D8]
0x18002e933  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002e938  nop
0x18002e939  mov     dword ptr [rsp+270h+var_218], r12d
0x18002e93e  mov     rcx, [rbp+170h+var_150]
0x18002e942  mov     rax, [rcx]
0x18002e945  mov     qword ptr [rbp+170h+var_140], r12
0x18002e949  lea     rdx, [rsp+270h+var_218]
0x18002e94e  mov     qword ptr [rbp+170h+var_140+8], rdx
0x18002e952  lea     rdx, [rbp+170h+var_1D8]
0x18002e956  mov     [rbp+170h+var_130], rdx
0x18002e95a  lea     r8, [rbp+170h+var_140]
0x18002e95e  mov     edx, ebx
0x18002e960  mov     rax, [rax+20h]
0x18002e964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e969  mov     r14d, eax
0x18002e96c  lea     rcx, [rbp+170h+var_140]
0x18002e970  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002e975  mov     ecx, dword ptr [rsp+270h+var_218]; this
0x18002e979  test    ecx, ecx
0x18002e97b  js      loc_18002EA8A
0x18002e981  test    r14d, r14d
0x18002e984  js      loc_18002EA81
0x18002e98a  mov     dword ptr [rsp+270h+var_210], 0
0x18002e992  mov     rcx, [rbp+170h+var_1D8]
0x18002e996  mov     rax, [rcx]
0x18002e999  lea     rdx, [rsp+270h+var_210]
0x18002e99e  mov     rax, [rax+20h]
0x18002e9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9a7  test    eax, eax
0x18002e9a9  js      loc_18002EA79
0x18002e9af  xorps   xmm0, xmm0
0x18002e9b2  movups  [rbp+170h+var_110], xmm0
0x18002e9b6  movups  xmmword ptr [rbp+170h+var_100], xmm0
0x18002e9ba  movups  xmmword ptr [rbp+170h+var_100+0Ch], xmm0
0x18002e9be  lea     rcx, [rsp+270h+var_1F8]
0x18002e9c3  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002e9c8  nop
0x18002e9c9  mov     dword ptr [rsp+270h+var_218], r12d
0x18002e9ce  mov     rcx, [rbp+170h+var_1D8]
0x18002e9d2  mov     rax, [rcx]
0x18002e9d5  mov     qword ptr [rbp+170h+var_140], r12
0x18002e9d9  lea     rdx, [rsp+270h+var_218]
0x18002e9de  mov     qword ptr [rbp+170h+var_140+8], rdx
0x18002e9e2  lea     rdx, [rsp+270h+var_1F8]
0x18002e9e7  mov     [rbp+170h+var_130], rdx
0x18002e9eb  lea     r8, [rbp+170h+var_140]
0x18002e9ef  lea     rdx, [rbp+170h+var_110]
0x18002e9f3  mov     rax, [rax+30h]
0x18002e9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9fc  mov     r14d, eax
0x18002e9ff  lea     rcx, [rbp+170h+var_140]
0x18002ea03  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002ea08  mov     ecx, dword ptr [rsp+270h+var_218]; this
0x18002ea0c  test    ecx, ecx
0x18002ea0e  js      short loc_18002EA73
0x18002ea10  test    r14d, r14d
0x18002ea13  js      short loc_18002EA6A
0x18002ea15  lea     r9, [rsp+270h+var_1F8]
0x18002ea1a  lea     r8, [rbp+170h+var_110]
0x18002ea1e  mov     rdx, [rsi+70h]
0x18002ea22  lea     rcx, [rbp+170h+var_128]
0x18002ea26  call    ?GetD2D1Color@xpsrdr@@YA?AU_D3DCOLORVALUE@@AEAURenderState@1@AEBU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@std@@@Z; xpsrdr::GetD2D1Color(xpsrdr::RenderState &,__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 const &,std::shared_ptr<IXpsOMColorProfileResource> const &)
0x18002ea2b  movss   xmm0, dword ptr [rsp+270h+var_210]
0x18002ea31  movss   dword ptr [rbp+170h+var_140], xmm0
0x18002ea36  movups  xmm1, xmmword ptr [rax]
0x18002ea39  movdqu  [rbp+170h+var_140+4], xmm1
0x18002ea3e  mov     dword ptr [rbp+170h+var_130+4], ebx
0x18002ea41  lea     rdx, [rbp+170h+var_140]
0x18002ea45  lea     rcx, [rbp+170h+var_190]
0x18002ea49  call    ?push_back@?$vector@UCGradientStop@xgc@@V?$allocator@UCGradientStop@xgc@@@std@@@std@@QEAAX$$QEAUCGradientStop@xgc@@@Z; std::vector<xgc::CGradientStop>::push_back(xgc::CGradientStop &&)
0x18002ea4e  nop
0x18002ea4f  lea     rcx, [rsp+270h+var_1F8]
0x18002ea54  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002ea59  nop
0x18002ea5a  lea     rcx, [rbp+170h+var_1D8]
0x18002ea5e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002ea63  add     ebx, edi
0x18002ea65  jmp     loc_18002E925
0x18002ea6a  mov     ecx, r14d; this
0x18002ea6d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002ea73  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002ea79  mov     ecx, eax; this
0x18002ea7b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002ea81  mov     ecx, r14d; this
0x18002ea84  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002ea8a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002ea90  lea     rdx, [rsp+270h+var_1F8]
0x18002ea95  lea     rcx, [rbp+170h+var_190]
0x18002ea99  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18002ea9e  mov     r8, [rax]
0x18002eaa1  lea     rdx, [rsp+270h+var_210]
0x18002eaa6  lea     rcx, [rbp+170h+var_190]
0x18002eaaa  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18002eaaf  mov     rdx, r8
0x18002eab2  mov     rcx, [rax]
0x18002eab5  call    ??$sort@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCGradientStop@xgc@@@std@@@std@@@std@@@std@@YAXV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCGradientStop@xgc@@@std@@@std@@@0@0@Z; std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<xgc::CGradientStop>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<xgc::CGradientStop>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<xgc::CGradientStop>>>)
0x18002eaba  or      r14d, 0FFFFFFFFh
0x18002eabe  mov     r9d, dword ptr [rsp+270h+var_200]
0x18002eac3  mov     r15d, r9d
0x18002eac6  mov     edx, r12d
0x18002eac9  mov     r8, [rbp+170h+var_190]
0x18002eacd  movss   xmm15, cs:__real@3f800000
0x18002ead6  xorps   xmm1, xmm1
0x18002ead9  cmp     edx, r9d
0x18002eadc  jnb     short loc_18002EB05
0x18002eade  mov     eax, edx
0x18002eae0  lea     rcx, [rax+rax*2]
0x18002eae4  movss   xmm0, dword ptr [r8+rcx*8]
0x18002eaea  lea     eax, [r14+1]
0x18002eaee  comiss  xmm1, xmm0
0x18002eaf1  cmovbe  eax, r14d
0x18002eaf5  mov     r14d, eax
0x18002eaf8  comiss  xmm0, xmm15
0x18002eafc  ja      short loc_18002EB02
0x18002eafe  add     edx, edi
0x18002eb00  jmp     short loc_18002EAD9
0x18002eb02  mov     r15d, edx
0x18002eb05  cmp     r14d, 0FFFFFFFFh
0x18002eb09  jnz     short loc_18002EB28
0x18002eb0b  movss   xmm9, dword ptr [r8+4]
0x18002eb11  movss   xmm10, dword ptr [r8+8]
0x18002eb17  movss   xmm7, dword ptr [r8+0Ch]
0x18002eb1d  movss   xmm11, dword ptr [r8+10h]
0x18002eb23  jmp     loc_18002EBE0
0x18002eb28  lea     eax, [r9-1]
0x18002eb2c  cmp     r14d, eax
0x18002eb2f  jnz     short loc_18002EB56
0x18002eb31  lea     rcx, [rax+rax*2]
  ... truncated ...
```
