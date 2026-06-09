# xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMImageBrush> const &)

- ea: `0x18002f6e8`
- end: `0x1800300af`
- name: `?Fill@CGDIPathData@xgc@@AEBAXAEBV?$shared_ptr@UIXpsOMImageBrush@@@std@@@Z`
- size: `2503`
- prototype: `__int64 __fastcall(xgc::CGDIPathData *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180030284`

## callees

- `0x180008830`
- `0x180009304`
- `0x18000931c`
- `0x18000d428`
- `0x18000d61c`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x180012088`
- `0x1800255bc`
- `0x180026c28`
- `0x180026c5c`
- `0x180026f94`
- `0x18002ccb4`
- `0x18002e220`
- `0x18002f6e8`
- `0x180036674`
- `0x180037278`
- `0x1800372e4`
- `0x18004a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002fe4f`
- `KERNEL32!GetLastError` at `0x18002fe4f`
- `GDI32!SaveDC` at `0x18002fe45`
- `GDI32!SaveDC` at `0x18002fe45`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
double __fastcall xgc::CGDIPathData::Fill(xgc::CGDIPathData *this, __int64 **a2)
{
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  int v7; // r9d
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // esi
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  const char *v14; // rdx
  xpsrdr *v15; // rcx
  int v16; // r8d
  __int64 v17; // rax
  int v18; // esi
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  int v22; // eax
  int v23; // edx
  const char *v24; // r8
  int v25; // r9d
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // esi
  int v29; // edx
  const char *v30; // r8
  int v31; // r9d
  int v32; // eax
  const char *v33; // rdx
  xpsrdr *v34; // rcx
  const char *v35; // r8
  int v36; // r9d
  __int64 v37; // rax
  int v38; // esi
  int v39; // edx
  const char *v40; // r8
  int v41; // r9d
  __int64 v42; // rax
  int v43; // esi
  int v44; // edx
  const char *v45; // r8
  int v46; // r9d
  int v47; // eax
  int v48; // edx
  const char *v49; // r8
  int v50; // r9d
  __int64 *v51; // rcx
  __int64 v52; // rax
  int v53; // esi
  int v54; // edx
  const char *v55; // r8
  int v56; // r9d
  __int64 WICBitmap; // rax
  __int64 v58; // rax
  __int64 *v59; // rcx
  __int64 v60; // rax
  int v61; // esi
  int v62; // edx
  const char *v63; // r8
  int v64; // r9d
  int v65; // eax
  int v66; // edx
  const char *v67; // r8
  int v68; // r9d
  int v69; // eax
  int v70; // edx
  const char *v71; // r8
  int v72; // r9d
  double v73; // xmm7_8
  double v74; // xmm0_8
  double v75; // xmm4_8
  float v76; // xmm0_4
  float v77; // xmm0_4
  float v78; // xmm0_4
  int v79; // eax
  const struct D2D_MATRIX_3X2_F *v80; // rdx
  const char *v81; // r8
  int v82; // r9d
  float v83; // xmm9_4
  float v84; // xmm3_4
  float v85; // xmm1_4
  float v86; // xmm5_4
  float v87; // xmm2_4
  float v88; // xmm6_4
  float v89; // xmm9_4
  const struct D2D_MATRIX_3X2_F *v90; // rdx
  const struct D2D_MATRIX_3X2_F *v91; // rdx
  const struct D2D_MATRIX_3X2_F *v92; // rdx
  __int64 v93; // r8
  signed int LastError; // eax
  int v95; // edx
  const char *v96; // r8
  int v97; // r9d
  int v98; // r15d
  int v99; // r12d
  int v100; // esi
  int v101; // r14d
  int v102; // eax
  int v103; // edx
  const char *v104; // r8
  int v105; // r9d
  __int64 *v106; // rdx
  __int64 v107; // rax
  __int64 v108; // rcx
  int v109; // r8d
  int v110; // r9d
  int v111; // r10d
  int v112; // r11d
  bool v114; // [rsp+28h] [rbp-E0h]
  bool v115; // [rsp+28h] [rbp-E0h]
  bool v116; // [rsp+28h] [rbp-E0h]
  struct D2D_MATRIX_3X2_F v117; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v118; // [rsp+90h] [rbp-78h]
  int v119; // [rsp+98h] [rbp-70h] BYREF
  int v120; // [rsp+9Ch] [rbp-6Ch] BYREF
  int v121; // [rsp+A0h] [rbp-68h] BYREF
  int v122; // [rsp+A4h] [rbp-64h] BYREF
  __int64 v123; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v124; // [rsp+B0h] [rbp-58h]
  _QWORD v125[2]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v126[2]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v127[2]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v128[2]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v129[16]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v130[2]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v131[2]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v132[2]; // [rsp+128h] [rbp+20h] BYREF
  __int128 X; // [rsp+138h] [rbp+30h] BYREF
  __int128 v134; // [rsp+148h] [rbp+40h] BYREF
  __int128 v135; // [rsp+158h] [rbp+50h] BYREF
  _QWORD *v136; // [rsp+168h] [rbp+60h]
  __int128 v137; // [rsp+170h] [rbp+68h] BYREF
  _QWORD v138[3]; // [rsp+180h] [rbp+78h] BYREF

  v117.m11 = 0.0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(**a2 + 128))(*a2, &v117);
  if ( v4 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v4, v5, v6, v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      18,
      WPP_00624022ad39391a483a764a1c0090f0_Traceguids,
      LODWORD(v117.m11));
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v131);
  v117.m21 = 0.0;
  v8 = *a2;
  v9 = **a2;
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = v117.m[1];
  v136 = v131;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v9 + 144))(v8, &v135);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v135);
  if ( v117.m21 < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v117.m21), v11, v12, v13);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v131) )
    xpsrdr::ThrowLogicException(v15, v14, v16);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v128);
  v117.m21 = 0.0;
  v17 = *(_QWORD *)v131[0];
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = v117.m[1];
  v136 = v128;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(v17 + 40))(v131[0], &v135);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v135);
  if ( v117.m21 < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v117.m21), v19, v20, v21);
  if ( v18 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
  *(_QWORD *)&v117.m[1][0] = 0;
  v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v128[0] + 40LL))(v128[0], 0, 0, 0);
  if ( v22 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, v23, v24, v25);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v127);
  v117.m21 = 0.0;
  v26 = (__int64 *)**((_QWORD **)this + 14);
  v27 = *v26;
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = v117.m[1];
  v136 = v127;
  v28 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int128 *))(v27 + 32))(v26, v128[0], 0, 0, &v135);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v135);
  if ( v117.m21 < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v117.m21), v29, v30, v31);
  if ( v28 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v29, v30, v31);
  v121 = 0;
  v32 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v127[0] + 96LL))(v127[0], &v121);
  if ( v32 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, (int)v33, v35, v36);
  if ( !v121 )
    xpsrdr::ThrowLogicException(v34, v33, (int)v35);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v126);
  v117.m21 = 0.0;
  v37 = *(_QWORD *)v127[0];
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = v117.m[1];
  v136 = v126;
  v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(v37 + 104))(v127[0], 0, &v135);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v135);
  if ( v117.m21 < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v117.m21), v39, v40, v41);
  if ( v38 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v38, v39, v40, v41);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v132);
  v117.m21 = 0.0;
  v42 = *(_QWORD *)v127[0];
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = v117.m[1];
  v136 = v132;
  v43 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(v42 + 48))(v127[0], &v135);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v135);
  if ( v117.m21 < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v117.m21), v44, v45, v46);
  if ( v43 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v43, v44, v45, v46);
  v137 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v132[0] + 88LL))(v132[0], &v137);
  v120 = 0;
  v119 = 0;
  v47 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(*(_QWORD *)v126[0] + 24LL))(v126[0], &v120, &v119);
  if ( v47 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v47, v48, v49, v50);
  std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(v130, v126);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v129);
  v117.m21 = 0.0;
  v51 = *a2;
  v52 = **a2;
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = v117.m[1];
  v136 = v129;
  v53 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v52 + 160))(v51, &v135);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v135);
  if ( v117.m21 < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v117.m21), v54, v55, v56);
  if ( v53 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v53, v54, v55, v56);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v129) )
    v137 = xmmword_18004E1F0;
  WICBitmap = xpsrdr::GetWICBitmap(
                (unsigned int)&v117.m21,
                *((_QWORD *)this + 14),
                (unsigned int)v126,
                (unsigned int)v129,
                1);
  v58 = std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(&v135, WICBitmap);
  std::shared_ptr<XgcSolidPath>::swap(v58, v130);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v135);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v117.m[1]);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v125);
  v117.m21 = 0.0;
  v59 = *a2;
  v60 = **a2;
  *(_QWORD *)&v135 = 0;
  *((_QWORD *)&v135 + 1) = v117.m[1];
  v136 = v125;
  v61 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v60 + 56))(v59, &v135);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v135);
  if ( v117.m21 < 0.0 )
    xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v117.m21), v62, v63, v64);
  if ( v61 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v61, v62, v63, v64);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v125) )
  {
    v135 = 0;
    v136 = 0;
    v65 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v125[0] + 40LL))(v125[0], &v135);
    if ( v65 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v66, v67, v68);
    *(_OWORD *)&v117.m[1][0] = v135;
    v118 = v136;
    xgc::CDeviceContext::PushTransform(*((struct D2D_MATRIX_3X2_F **)this + 2), (struct D2D_MATRIX_3X2_F *)v117.m[1]);
  }
  X = 0;
  v69 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(**a2 + 96))(*a2, &X);
  if ( v69 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v69, v70, v71, v72);
  *(_QWORD *)&v117.m[1][0] = 0;
  *(_QWORD *)&v135 = 0;
  (*(void (__fastcall **)(_QWORD, FLOAT *, __int128 *))(*(_QWORD *)v130[0] + 40LL))(v130[0], &v117.m21, &v135);
  v73 = floor(*(double *)&v117.m[1][0] + 0.5);
  v74 = floor(*(double *)&v135 + 0.5);
  v75 = v74;
  if ( v73 == 0.0 )
    v73 = DOUBLE_96_0;
  if ( v74 == 0.0 )
    v75 = DOUBLE_96_0;
  v76 = *(float *)&X * v73 / 96.0;
  *(float *)&X = v76;
  v77 = *((float *)&X + 1) * v75 / 96.0;
  *((float *)&X + 1) = v77;
  v78 = *((float *)&X + 2) * v73 / 96.0;
  *((float *)&X + 2) = v78;
  *((float *)&X + 3) = *((float *)&X + 3) * v75 / 96.0;
  v134 = 0;
  v79 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(**a2 + 112))(*a2, &v134);
  if ( v79 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v79, (int)v80, v81, v82);
  v83 = *((float *)&X + 3);
  v84 = *((float *)&v134 + 3) / *((float *)&X + 3);
  v85 = *((float *)&X + 1);
  v86 = *((float *)&v134 + 1) - (float)((float)(*((float *)&v134 + 3) / *((float *)&X + 3)) * *((float *)&X + 1));
  v87 = *(float *)&X;
  if ( LODWORD(v117.m11) == 1 )
  {
    if ( *(float *)&X <= 0.0 )
    {
      v87 = 0.0;
      LODWORD(X) = 0;
    }
    if ( *((float *)&X + 1) <= 0.0 )
    {
      v85 = 0.0;
      DWORD1(X) = 0;
    }
    if ( (float)((float)v120 - v87) <= *((float *)&X + 2) )
      *((float *)&X + 2) = (float)v120 - v87;
    if ( (float)((float)v119 - v85) <= *((float *)&X + 3) )
    {
      v83 = (float)v119 - v85;
      *((float *)&X + 3) = v83;
    }
  }
  v88 = (float)(v84 * v85) + v86;
  v89 = (float)((float)(v83 + v85) * v84) + v86;
  v138[0] = xgc::TransformPoints((xgc *)(*((_QWORD *)this + 2) + 40LL), v80, v88, v84, v114);
  v138[1] = xgc::TransformPoints((xgc *)(*((_QWORD *)this + 2) + 40LL), v90, v88, v84, v115);
  v138[2] = xgc::TransformPoints((xgc *)(*((_QWORD *)this + 2) + 40LL), v91, v89, v84, v116);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v125) )
    xgc::CDeviceContext::PopTransform(*((xgc::CDeviceContext **)this + 2));
  if ( !SaveDC(*(HDC *)(*((_QWORD *)this + 2) + 32LL)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v95, v96, v97);
  }
  xgc::CGDIPathData::Clip(this, v92, v93, v84);
  v98 = (int)(o_ceilf_0(*(float *)&X) + 0.5);
  v99 = (int)(o_ceilf_0(*((float *)&X + 1)) + 0.5);
  if ( LODWORD(v117.m11) == 1 )
  {
    v100 = (int)fminf(*((float *)&X + 2), (float)(v120 - v98));
    v101 = (int)fminf(*((float *)&X + 3), (float)(v119 - v99));
  }
  else
  {
    v100 = (int)(*((float *)&X + 2) + 0.5);
    v101 = (int)(*((float *)&X + 3) + 0.5);
  }
  v122 = 1065353216;
  v102 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a2 + 40))(*a2, &v122);
  if ( v102 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v102, v103, v104, v105);
  v106 = (__int64 *)*((_QWORD *)this + 5);
  v123 = *v106;
  v107 = *v106;
  v124 = *v106;
  if ( LODWORD(v117.m11) != 1 )
  {
    v108 = (unsigned int)((__int64)(*((_QWORD *)this + 6) - (_QWORD)v106) >> 3) - 1;
    if ( (int)(((__int64)(*((_QWORD *)this + 6) - (_QWORD)v106) >> 3) - 1) > 0 )
    {
      v109 = HIDWORD(v124);
      v110 = v107;
      v111 = HIDWORD(v123);
      v112 = v123;
      do
      {
        if ( SLODWORD(v106[v108]) < v112 )
          v112 = v106[v108];
        LODWORD(v123) = v112;
        if ( SHIDWORD(v106[v108]) < v111 )
          v111 = HIDWORD(v106[v108]);
        HIDWORD(v123) = v111;
        if ( SLODWORD(v106[v108]) > v110 )
          v110 = v106[v108];
        LODWORD(v124) = v110;
        if ( SHIDWORD(v106[v108]) > v109 )
          v109 = HIDWORD(v106[v108]);
        HIDWORD(v124) = v109;
        v108 = (unsigned int)(v108 - 1);
      }
      while ( (int)v108 > 0 );
    }
  }
  xgc::CDeviceContext::DrawImage(
    *((_QWORD *)this + 2),
    (unsigned int)v130,
    (unsigned int)&v137,
    LODWORD(v117.m11),
    (__int64)v128,
    v120,
    v119,
    v122,
    v98,
    v99,
    v100,
    v101,
    (__int64)&v123,
    (__int64)v138);
  xgc::CDeviceContext::Restore(*((xgc::CDeviceContext **)this + 2));
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v125);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v129);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v130);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v132);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v126);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v127);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v128);
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v131);
}

```

## disassembly

```asm
0x18002f6e8  mov     rax, rsp
0x18002f6eb  mov     [rax+18h], rbx
0x18002f6ef  push    rbp
0x18002f6f0  push    rsi
0x18002f6f1  push    rdi
0x18002f6f2  push    r12
0x18002f6f4  push    r13
0x18002f6f6  push    r14
0x18002f6f8  push    r15
0x18002f6fa  lea     rbp, [rax-138h]
0x18002f701  sub     rsp, 200h
0x18002f708  movaps  xmmword ptr [rax-48h], xmm6
0x18002f70c  movaps  xmmword ptr [rax-58h], xmm7
0x18002f710  movaps  xmmword ptr [rax-68h], xmm8
0x18002f715  movaps  xmmword ptr [rax-78h], xmm9
0x18002f71a  movaps  xmmword ptr [rax-88h], xmm10
0x18002f722  movaps  xmmword ptr [rax-98h], xmm11
0x18002f72a  mov     rax, cs:__security_cookie
0x18002f731  xor     rax, rsp
0x18002f734  mov     [rbp+130h+var_A0], rax
0x18002f73b  mov     rdi, rdx
0x18002f73e  mov     rbx, rcx
0x18002f741  xor     r13d, r13d
0x18002f744  mov     dword ptr [rsp+230h+var_1C0], r13d
0x18002f749  mov     rcx, [rdx]
0x18002f74c  mov     rax, [rcx]
0x18002f74f  lea     rdx, [rsp+230h+var_1C0]
0x18002f754  mov     rax, [rax+80h]
0x18002f75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f760  test    eax, eax
0x18002f762  jns     short loc_18002F76C
0x18002f764  mov     ecx, eax; this
0x18002f766  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f76c  lea     rax, WPP_GLOBAL_Control
0x18002f773  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f77a  cmp     rcx, rax
0x18002f77d  jz      short loc_18002F7A5
0x18002f77f  test    byte ptr [rcx+0E4h], 8
0x18002f786  jz      short loc_18002F7A5
0x18002f788  mov     edx, 12h
0x18002f78d  mov     r9d, dword ptr [rsp+230h+var_1C0]
0x18002f792  lea     r8, WPP_00624022ad39391a483a764a1c0090f0_Traceguids
0x18002f799  mov     rcx, [rcx+0D8h]
0x18002f7a0  call    WPP_SF_d
0x18002f7a5  lea     rcx, [rbp+130h+var_120]
0x18002f7a9  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002f7ae  nop
0x18002f7af  mov     dword ptr [rsp+230h+var_1C0+8], r13d
0x18002f7b4  mov     rcx, [rdi]
0x18002f7b7  mov     rax, [rcx]
0x18002f7ba  mov     qword ptr [rbp+130h+var_E0], r13
0x18002f7be  lea     rdx, [rsp+230h+var_1C0+8]
0x18002f7c3  mov     qword ptr [rbp+130h+var_E0+8], rdx
0x18002f7c7  lea     rdx, [rbp+130h+var_120]
0x18002f7cb  mov     [rbp+130h+var_D0], rdx
0x18002f7cf  lea     rdx, [rbp+130h+var_E0]
0x18002f7d3  mov     rax, [rax+90h]
0x18002f7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7df  mov     esi, eax
0x18002f7e1  lea     rcx, [rbp+130h+var_E0]
0x18002f7e5  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002f7ea  mov     ecx, dword ptr [rsp+230h+var_1C0+8]; this
0x18002f7ee  test    ecx, ecx
0x18002f7f0  jns     short loc_18002F7F8
0x18002f7f2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f7f8  test    esi, esi
0x18002f7fa  jns     short loc_18002F804
0x18002f7fc  mov     ecx, esi; this
0x18002f7fe  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f804  lea     rcx, [rbp+130h+var_120]
0x18002f808  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18002f80d  test    al, al
0x18002f80f  jnz     short loc_18002F817
0x18002f811  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18002f817  lea     rcx, [rbp+130h+var_150]
0x18002f81b  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002f820  nop
0x18002f821  mov     dword ptr [rsp+230h+var_1C0+8], r13d
0x18002f826  mov     rcx, [rbp+130h+var_120]
0x18002f82a  mov     rax, [rcx]
0x18002f82d  mov     qword ptr [rbp+130h+var_E0], r13
0x18002f831  lea     rdx, [rsp+230h+var_1C0+8]
0x18002f836  mov     qword ptr [rbp+130h+var_E0+8], rdx
0x18002f83a  lea     rdx, [rbp+130h+var_150]
0x18002f83e  mov     [rbp+130h+var_D0], rdx
0x18002f842  lea     rdx, [rbp+130h+var_E0]
0x18002f846  mov     rax, [rax+28h]
0x18002f84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f84f  mov     esi, eax
0x18002f851  lea     rcx, [rbp+130h+var_E0]
0x18002f855  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002f85a  mov     ecx, dword ptr [rsp+230h+var_1C0+8]; this
0x18002f85e  test    ecx, ecx
0x18002f860  jns     short loc_18002F868
0x18002f862  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f868  test    esi, esi
0x18002f86a  jns     short loc_18002F874
0x18002f86c  mov     ecx, esi; this
0x18002f86e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f874  mov     qword ptr [rsp+230h+var_1C0+8], r13
0x18002f879  mov     rcx, [rbp+130h+var_150]
0x18002f87d  mov     rax, [rcx]
0x18002f880  xor     r9d, r9d
0x18002f883  xor     r8d, r8d
0x18002f886  mov     rdx, r13
0x18002f889  mov     rax, [rax+28h]
0x18002f88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f892  test    eax, eax
0x18002f894  jns     short loc_18002F89E
0x18002f896  mov     ecx, eax; this
0x18002f898  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f89e  lea     rcx, [rbp+130h+var_160]
0x18002f8a2  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002f8a7  nop
0x18002f8a8  mov     dword ptr [rsp+230h+var_1C0+8], r13d
0x18002f8ad  mov     rax, [rbx+70h]
0x18002f8b1  mov     rcx, [rax]
0x18002f8b4  mov     rax, [rcx]
0x18002f8b7  mov     qword ptr [rbp+130h+var_E0], r13
0x18002f8bb  lea     rdx, [rsp+230h+var_1C0+8]
0x18002f8c0  mov     qword ptr [rbp+130h+var_E0+8], rdx
0x18002f8c4  lea     rdx, [rbp+130h+var_160]
0x18002f8c8  mov     [rbp+130h+var_D0], rdx
0x18002f8cc  lea     rdx, [rbp+130h+var_E0]
0x18002f8d0  mov     qword ptr [rsp+230h+var_210], rdx
0x18002f8d5  xor     r9d, r9d
0x18002f8d8  xor     r8d, r8d
0x18002f8db  mov     rdx, [rbp+130h+var_150]
0x18002f8df  mov     rax, [rax+20h]
0x18002f8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8e8  mov     esi, eax
0x18002f8ea  lea     rcx, [rbp+130h+var_E0]
0x18002f8ee  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002f8f3  mov     ecx, dword ptr [rsp+230h+var_1C0+8]; this
0x18002f8f7  test    ecx, ecx
0x18002f8f9  jns     short loc_18002F901
0x18002f8fb  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f901  test    esi, esi
0x18002f903  jns     short loc_18002F90D
0x18002f905  mov     ecx, esi; this
0x18002f907  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f90d  mov     [rbp+130h+var_198], r13d
0x18002f911  mov     rcx, [rbp+130h+var_160]
0x18002f915  mov     rax, [rcx]
0x18002f918  lea     rdx, [rbp+130h+var_198]
0x18002f91c  mov     rax, [rax+60h]
0x18002f920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f925  test    eax, eax
0x18002f927  jns     short loc_18002F931
0x18002f929  mov     ecx, eax; this
0x18002f92b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f931  cmp     [rbp+130h+var_198], 1
0x18002f935  jnb     short loc_18002F93D
0x18002f937  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18002f93d  lea     rcx, [rbp+130h+var_170]
0x18002f941  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002f946  nop
0x18002f947  mov     dword ptr [rsp+230h+var_1C0+8], r13d
0x18002f94c  mov     rcx, [rbp+130h+var_160]
0x18002f950  mov     rax, [rcx]
0x18002f953  mov     qword ptr [rbp+130h+var_E0], r13
0x18002f957  lea     rdx, [rsp+230h+var_1C0+8]
0x18002f95c  mov     qword ptr [rbp+130h+var_E0+8], rdx
0x18002f960  lea     rdx, [rbp+130h+var_170]
0x18002f964  mov     [rbp+130h+var_D0], rdx
0x18002f968  lea     r8, [rbp+130h+var_E0]
0x18002f96c  xor     edx, edx
0x18002f96e  mov     rax, [rax+68h]
0x18002f972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f977  mov     esi, eax
0x18002f979  lea     rcx, [rbp+130h+var_E0]
0x18002f97d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002f982  mov     ecx, dword ptr [rsp+230h+var_1C0+8]; this
0x18002f986  test    ecx, ecx
0x18002f988  jns     short loc_18002F990
0x18002f98a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f990  test    esi, esi
0x18002f992  jns     short loc_18002F99C
0x18002f994  mov     ecx, esi; this
0x18002f996  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f99c  lea     rcx, [rbp+130h+var_110]
0x18002f9a0  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002f9a5  nop
0x18002f9a6  mov     dword ptr [rsp+230h+var_1C0+8], r13d
0x18002f9ab  mov     rcx, [rbp+130h+var_160]
0x18002f9af  mov     rax, [rcx]
0x18002f9b2  mov     qword ptr [rbp+130h+var_E0], r13
0x18002f9b6  lea     rdx, [rsp+230h+var_1C0+8]
0x18002f9bb  mov     qword ptr [rbp+130h+var_E0+8], rdx
0x18002f9bf  lea     rdx, [rbp+130h+var_110]
0x18002f9c3  mov     [rbp+130h+var_D0], rdx
0x18002f9c7  lea     rdx, [rbp+130h+var_E0]
0x18002f9cb  mov     rax, [rax+30h]
0x18002f9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9d4  mov     esi, eax
0x18002f9d6  lea     rcx, [rbp+130h+var_E0]
0x18002f9da  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002f9df  mov     ecx, dword ptr [rsp+230h+var_1C0+8]; this
0x18002f9e3  test    ecx, ecx
0x18002f9e5  jns     short loc_18002F9ED
0x18002f9e7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f9ed  test    esi, esi
0x18002f9ef  jns     short loc_18002F9F9
0x18002f9f1  mov     ecx, esi; this
0x18002f9f3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002f9f9  xorps   xmm0, xmm0
0x18002f9fc  movups  [rbp+130h+var_C8], xmm0
0x18002fa00  mov     rcx, [rbp+130h+var_110]
0x18002fa04  mov     rax, [rcx]
0x18002fa07  lea     rdx, [rbp+130h+var_C8]
0x18002fa0b  mov     rax, [rax+58h]
0x18002fa0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa14  mov     [rbp+130h+var_19C], r13d
0x18002fa18  mov     [rbp+130h+var_1A0], r13d
0x18002fa1c  mov     rcx, [rbp+130h+var_170]
0x18002fa20  mov     rax, [rcx]
0x18002fa23  lea     r8, [rbp+130h+var_1A0]
0x18002fa27  lea     rdx, [rbp+130h+var_19C]
0x18002fa2b  mov     rax, [rax+18h]
0x18002fa2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa34  test    eax, eax
0x18002fa36  jns     short loc_18002FA40
0x18002fa38  mov     ecx, eax; this
0x18002fa3a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002fa40  lea     rdx, [rbp+130h+var_170]
0x18002fa44  lea     rcx, [rbp+130h+var_130]
0x18002fa48  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x18002fa4d  nop
0x18002fa4e  lea     rcx, [rbp+130h+var_140]
0x18002fa52  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002fa57  nop
0x18002fa58  mov     dword ptr [rsp+230h+var_1C0+8], r13d
0x18002fa5d  mov     rcx, [rdi]
0x18002fa60  mov     rax, [rcx]
0x18002fa63  mov     qword ptr [rbp+130h+var_E0], r13
0x18002fa67  lea     rdx, [rsp+230h+var_1C0+8]
0x18002fa6c  mov     qword ptr [rbp+130h+var_E0+8], rdx
0x18002fa70  lea     rdx, [rbp+130h+var_140]
0x18002fa74  mov     [rbp+130h+var_D0], rdx
0x18002fa78  lea     rdx, [rbp+130h+var_E0]
0x18002fa7c  mov     rax, [rax+0A0h]
0x18002fa83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa88  mov     esi, eax
0x18002fa8a  lea     rcx, [rbp+130h+var_E0]
0x18002fa8e  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002fa93  mov     ecx, dword ptr [rsp+230h+var_1C0+8]; this
0x18002fa97  test    ecx, ecx
0x18002fa99  jns     short loc_18002FAA1
0x18002fa9b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002faa1  test    esi, esi
0x18002faa3  jns     short loc_18002FAAD
0x18002faa5  mov     ecx, esi; this
0x18002faa7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002faad  lea     rcx, [rbp+130h+var_140]
0x18002fab1  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18002fab6  test    al, al
0x18002fab8  jz      short loc_18002FAC6
0x18002faba  movups  xmm0, cs:xmmword_18004E1F0
0x18002fac1  movdqu  [rbp+130h+var_C8], xmm0
0x18002fac6  mov     [rsp+230h+var_210], 1; bool
0x18002facb  lea     r9, [rbp+130h+var_140]
0x18002facf  lea     r8, [rbp+130h+var_170]
0x18002fad3  mov     rdx, [rbx+70h]
0x18002fad7  lea     rcx, [rsp+230h+var_1C0+8]
0x18002fadc  call    ?GetWICBitmap@xpsrdr@@YA?AV?$shared_ptr@UIWICBitmapSource@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIWICBitmapFrameDecode@@@3@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@3@_N@Z; xpsrdr::GetWICBitmap(xpsrdr::RenderState &,std::shared_ptr<IWICBitmapFrameDecode> const &,std::shared_ptr<IXpsOMColorProfileResource> const &,bool)
0x18002fae1  mov     rdx, rax
0x18002fae4  lea     rcx, [rbp+130h+var_E0]
0x18002fae8  call    ??$?0UIWICColorTransform@@$0A@@?$shared_ptr@UIWICBitmapSource@@@std@@QEAA@$$QEAV?$shared_ptr@UIWICColorTransform@@@1@@Z; std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(std::shared_ptr<IWICColorTransform> &&)
0x18002faed  lea     rdx, [rbp+130h+var_130]
0x18002faf1  mov     rcx, rax
0x18002faf4  call    ?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)
0x18002faf9  lea     rcx, [rbp+130h+var_E0]
0x18002fafd  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002fb02  lea     rcx, [rsp+230h+var_1C0+8]
0x18002fb07  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18002fb0c  lea     rcx, [rbp+130h+var_180]
0x18002fb10  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18002fb15  nop
0x18002fb16  mov     dword ptr [rsp+230h+var_1C0+8], r13d
0x18002fb1b  mov     rcx, [rdi]
0x18002fb1e  mov     rax, [rcx]
0x18002fb21  mov     qword ptr [rbp+130h+var_E0], r13
0x18002fb25  lea     rdx, [rsp+230h+var_1C0+8]
0x18002fb2a  mov     qword ptr [rbp+130h+var_E0+8], rdx
0x18002fb2e  lea     rdx, [rbp+130h+var_180]
0x18002fb32  mov     [rbp+130h+var_D0], rdx
0x18002fb36  lea     rdx, [rbp+130h+var_E0]
0x18002fb3a  mov     rax, [rax+38h]
0x18002fb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb43  mov     esi, eax
0x18002fb45  lea     rcx, [rbp+130h+var_E0]
0x18002fb49  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002fb4e  mov     ecx, dword ptr [rsp+230h+var_1C0+8]; this
0x18002fb52  test    ecx, ecx
0x18002fb54  jns     short loc_18002FB5C
0x18002fb56  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002fb5c  test    esi, esi
0x18002fb5e  jns     short loc_18002FB68
0x18002fb60  mov     ecx, esi; this
0x18002fb62  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
  ... truncated ...
```
