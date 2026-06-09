# xpsrdr::CreateD2D1Brush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F const &,float *)

- ea: `0x1800b3ecc`
- end: `0x1800b4a79`
- name: `?CreateD2D1Brush@xpsrdr@@YA?AU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBUD2D_MATRIX_3X2_F@@AEBUD2D_RECT_F@@PEAM@Z`
- size: `2989`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1800aeb6c`
- `0x1800b0298`
- `0x1800b0710`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a86b4`
- `0x1800aa83c`
- `0x1800adb68`
- `0x1800ae980`
- `0x1800b20e8`
- `0x1800b2154`
- `0x1800b3918`
- `0x1800b3bc8`
- `0x1800b3d30`
- `0x1800b3ecc`
- `0x1800b4a80`
- `0x1800b5360`
- `0x1800b54c4`
- `0x1800b567c`
- `0x1800b5858`
- `0x1800bad68`
- `0x1800bbca0`
- `0x1800bc69c`
- `0x1800bcde0`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 *__fastcall xpsrdr::CreateD2D1Brush(
        __int64 *a1,
        __int64 a2,
        __int64 (__fastcall ****a3)(__int64, GUID *, struct D2D_MATRIX_3X2_F *),
        xpsrdr *a4,
        _OWORD *a5)
{
  int v9; // eax
  struct _GUID *v10; // rdx
  const char *v11; // r8
  int v12; // r9d
  __int64 (__fastcall ***v13)(__int64, GUID *, struct D2D_MATRIX_3X2_F *); // rcx
  __int64 (__fastcall **v14)(__int64, GUID *, struct D2D_MATRIX_3X2_F *); // rax
  int v15; // r15d
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  int v19; // eax
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  __int64 v23; // rax
  int v24; // r14d
  int v25; // edx
  const char *v26; // r8
  int v27; // r9d
  int v28; // eax
  int v29; // edx
  const char *v30; // r8
  int v31; // r9d
  int v32; // eax
  int v33; // edx
  const char *v34; // r8
  int v35; // r9d
  __int64 v36; // rax
  int v37; // r14d
  const struct D2D_MATRIX_3X2_F *v38; // rdx
  const char *v39; // r8
  int v40; // r9d
  int v41; // eax
  int v42; // edx
  const char *v43; // r8
  struct D2D_MATRIX_3X2_F *v44; // r9
  std::_Ref_count_base *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  float v48; // xmm2_4
  __int64 v49; // r15
  __int64 *v50; // rdx
  __int64 *D2D1GradientBrush; // rax
  __int64 v52; // rbx
  __int64 v53; // rsi
  __int64 v54; // rax
  __int64 (__fastcall ***v55)(__int64, GUID *, struct D2D_MATRIX_3X2_F *); // rcx
  __int64 (__fastcall **v56)(__int64, GUID *, struct D2D_MATRIX_3X2_F *); // rax
  int v57; // r15d
  int v58; // edx
  const char *v59; // r8
  int v60; // r9d
  int v61; // eax
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
  __int64 v73; // rax
  int v74; // r14d
  const struct D2D_MATRIX_3X2_F *v75; // rdx
  const char *v76; // r8
  int v77; // r9d
  int v78; // eax
  int v79; // edx
  const char *v80; // r8
  struct D2D_MATRIX_3X2_F *v81; // r9
  __int64 v82; // rax
  int v83; // r14d
  const char *v84; // rdx
  const char *v85; // r8
  int v86; // r9d
  __int64 v87; // rax
  int v88; // r14d
  int v89; // edx
  const char *v90; // r8
  int v91; // r9d
  std::_Ref_count_base *v92; // rcx
  float BitmapBrushWeight; // xmm0_4
  __int64 *v94; // rdx
  __int128 *v95; // rdx
  __int64 v96; // rax
  __int64 *v97; // rax
  __int128 v99; // [rsp+38h] [rbp-D0h] BYREF
  struct D2D_MATRIX_3X2_F v100; // [rsp+48h] [rbp-C0h] BYREF
  __int64 *v101; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v102[3]; // [rsp+70h] [rbp-98h] BYREF
  struct D2D_MATRIX_3X2_F v103; // [rsp+88h] [rbp-80h] BYREF
  __int128 v104; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v105; // [rsp+B8h] [rbp-50h]
  __int64 v106; // [rsp+C8h] [rbp-40h]
  struct D2D_MATRIX_3X2_F *v107; // [rsp+D0h] [rbp-38h]
  _OWORD *v108; // [rsp+D8h] [rbp-30h]
  xpsrdr *v109; // [rsp+E0h] [rbp-28h]
  __m256i v110; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v111; // [rsp+110h] [rbp+8h]
  int v112; // [rsp+120h] [rbp+18h]
  int v113; // [rsp+124h] [rbp+1Ch]
  __int64 (__fastcall ***v114)(__int64, GUID *, struct D2D_MATRIX_3X2_F *); // [rsp+128h] [rbp+20h] BYREF
  __int128 v115; // [rsp+130h] [rbp+28h]
  __int64 v116; // [rsp+140h] [rbp+38h]
  __int128 v117; // [rsp+148h] [rbp+40h]
  int v118; // [rsp+158h] [rbp+50h]
  float v119; // [rsp+15Ch] [rbp+54h]
  struct D2D_MATRIX_3X2_F v120; // [rsp+168h] [rbp+60h] BYREF
  struct D2D_MATRIX_3X2_F v121; // [rsp+188h] [rbp+80h] BYREF
  struct D2D_MATRIX_3X2_F v122; // [rsp+1A0h] [rbp+98h] BYREF
  struct D2D_MATRIX_3X2_F v123; // [rsp+1B8h] [rbp+B0h] BYREF

  v101 = a1;
  LODWORD(v102[0]) = 0;
  v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct D2D_MATRIX_3X2_F *), _QWORD *))(**a3)[4])(
         *a3,
         v102);
  if ( v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, (int)v10, v11, v12);
  switch ( LODWORD(v102[0]) )
  {
    case 6:
      *(_OWORD *)&v120.m11 = 0;
      v97 = (__int64 *)xpsrdr::CreateSolidColorBrush(&v123, a2, a3, 0);
      *a1 = 0;
      a1[1] = 0;
      *a1 = *v97;
      a1[1] = v97[1];
      *v97 = 0;
      v97[1] = 0;
      a1[2] = 0;
      a1[3] = 0;
      if ( *(_QWORD *)&v123.m[1][0] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v123.m[1][0]);
      break;
    case 7:
      ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 40LL);
      v99 = 0;
      v100.m11 = 0.0;
      v55 = *a3;
      v56 = **a3;
      *(_QWORD *)&v121.m11 = 0;
      *(_QWORD *)&v121.m[1][0] = &v100;
      *(_QWORD *)&v121.m[2][0] = &v99;
      v57 = (*v56)((__int64)v55, &GUID_3df0b466_d382_49ef_8550_dd94c80242e4, &v121);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v121);
      if ( v100.m11 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v100.m11), v58, v59, v60);
      if ( v57 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v57, v58, v59, v60);
      HIDWORD(v102[0]) = 0;
      v61 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct D2D_MATRIX_3X2_F *), char *))(**a3)[5])(
              *a3,
              (char *)v102 + 4);
      if ( v61 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v61, v62, v63, v64);
      *(_OWORD *)&v120.m11 = 0;
      v65 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v99 + 96LL))(v99, &v120);
      if ( v65 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v66, v67, v68);
      *(_OWORD *)&v123.m11 = 0;
      v69 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v99 + 112LL))(v99, &v123);
      if ( v69 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v69, v70, v71, v72);
      *(_OWORD *)&v102[1] = 0;
      v100.m11 = 0.0;
      v73 = *(_QWORD *)v99;
      *(_QWORD *)&v121.m11 = 0;
      *(_QWORD *)&v121.m[1][0] = &v100;
      *(_QWORD *)&v121.m[2][0] = &v102[1];
      v74 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(v73 + 56))(v99, &v121);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v121);
      if ( v100.m11 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v100.m11), (int)v75, v76, v77);
      if ( v74 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v74, (int)v75, v76, v77);
      memset(&v103, 0, sizeof(v103));
      if ( v102[1] )
      {
        memset(&v121, 0, sizeof(v121));
        v78 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v102[1] + 40LL))(v102[1], &v121);
        if ( v78 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v78, v79, v80, (int)v81);
        v122 = v121;
        xpsrdr::MultiplyMatrix(a4, &v122, &v103, v81);
      }
      else
      {
        v103 = *(struct D2D_MATRIX_3X2_F *)a4;
      }
      if ( v123.m21 == 0.0
        || v123.m22 == 0.0
        || v120.m21 == 0.0
        || v120.m22 == 0.0
        || xpsrdr::NullMatrix((xpsrdr *)&v103, v75) )
      {
        xpsrdr::CreateEmptyBrushClipPair(a1, a2, 0);
      }
      else
      {
        *(_OWORD *)&v103.m11 = 0;
        v100.m11 = 0.0;
        v82 = *(_QWORD *)v99;
        v110.m256i_i64[0] = 0;
        v110.m256i_i64[1] = (__int64)&v100;
        v110.m256i_i64[2] = (__int64)&v103;
        v83 = (*(__int64 (__fastcall **)(_QWORD, __m256i *))(v82 + 144))(v99, &v110);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v110);
        if ( v100.m11 < 0.0 )
          xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v100.m11), (int)v84, v85, v86);
        if ( v83 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v83, (int)v84, v85, v86);
        if ( !*(_QWORD *)&v103.m11 )
          xpsrdr::ThrowLogicException((xpsrdr *)LODWORD(v100.m11), v84, (int)v85);
        *(_OWORD *)&v121.m11 = 0;
        v100.m11 = 0.0;
        v87 = *(_QWORD *)v99;
        v110.m256i_i64[0] = 0;
        v110.m256i_i64[1] = (__int64)&v100;
        v110.m256i_i64[2] = (__int64)&v121;
        v88 = (*(__int64 (__fastcall **)(_QWORD, __m256i *))(v87 + 160))(v99, &v110);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v110);
        if ( v100.m11 < 0.0 )
          xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v100.m11), v89, v90, v91);
        if ( v88 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v88, v89, v90, v91);
        xpsrdr::Image::CreateImage(&v122, a2, &v103, &v121);
        *(_OWORD *)&v100.m11 = 0;
        v92 = (std::_Ref_count_base *)*((_QWORD *)&v99 + 1);
        if ( *((_QWORD *)&v99 + 1) )
        {
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v99 + 1) + 8LL));
          v92 = (std::_Ref_count_base *)*((_QWORD *)&v99 + 1);
        }
        *(_OWORD *)&v100.m11 = v99;
        v104 = 0;
        v105 = 0;
        v106 = a2;
        v107 = &v100;
        v108 = a5;
        v109 = a4;
        if ( v92 )
          std::_Ref_count_base::_Decref(v92);
        BitmapBrushWeight = xpsrdr::TileBrushBuilder::GetBitmapBrushWeight(&v104, &v122);
        v114 = (__int64 (__fastcall ***)(__int64, GUID *, struct D2D_MATRIX_3X2_F *))v99;
        v115 = *(_OWORD *)a4;
        v116 = *((_QWORD *)a4 + 2);
        v117 = *a5;
        v118 = *(_DWORD *)(a2 + 528);
        v119 = BitmapBrushWeight;
        if ( *(_BYTE *)(a2 + 481)
          || (xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(
                a2 + 240,
                &v101,
                &v114),
              v94 = v101,
              v101 == *(__int64 **)(a2 + 248)) )
        {
          xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsImageBrush((xpsrdr::TileBrushBuilder *)&v104);
          if ( !*(_BYTE *)(a2 + 481) )
          {
            v96 = xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](
                    a2 + 240,
                    &v114);
            std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
              v96,
              &v104);
          }
          v95 = &v104;
        }
        else
        {
          ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 44LL);
          v95 = (__int128 *)(v94 + 9);
        }
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          a1,
          v95);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(&v104);
        if ( *(_QWORD *)&v122.m[1][0] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v122.m[1][0]);
        if ( *(_QWORD *)&v121.m[1][0] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v121.m[1][0]);
        if ( *(_QWORD *)&v103.m[1][0] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v103.m[1][0]);
      }
      if ( v102[2] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v102[2]);
      if ( *((_QWORD *)&v99 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v99 + 1));
      break;
    case 8:
    case 9:
      *(_OWORD *)&v120.m11 = *(_OWORD *)(a2 + 100);
      if ( *(int *)(a2 + 80) <= 37632 )
        v48 = (float)xpsrdr::GetBytesPerPixel((xpsrdr *)&v120, v10) * 11264.0;
      else
        v48 = (float)xpsrdr::GetBytesPerPixel((xpsrdr *)&v120, v10) * 2047.0;
      v114 = *a3;
      v115 = *(_OWORD *)a4;
      v116 = *((_QWORD *)a4 + 2);
      v117 = *a5;
      v118 = *(_DWORD *)(a2 + 528);
      v119 = v48 * 0.00000095367432;
      v49 = a2 + 240;
      xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(
        a2 + 240,
        &v101,
        &v114);
      v50 = v101;
      if ( v101 == *(__int64 **)(a2 + 248) )
      {
        *(_OWORD *)&v120.m11 = 0;
        D2D1GradientBrush = (__int64 *)xpsrdr::CreateD2D1GradientBrush(
                                         (unsigned int)&v123,
                                         a2,
                                         (_DWORD)a3,
                                         (unsigned int)v102,
                                         0);
        v52 = *D2D1GradientBrush;
        v110.m256i_i64[0] = *D2D1GradientBrush;
        v53 = D2D1GradientBrush[1];
        v110.m256i_i64[1] = v53;
        *D2D1GradientBrush = 0;
        D2D1GradientBrush[1] = 0;
        *(_OWORD *)&v110.m256i_u64[2] = 0;
        if ( *(_QWORD *)&v123.m[1][0] )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v123.m[1][0]);
        v54 = xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](
                v49,
                &v114);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
          v54,
          &v110);
        *a1 = v52;
        a1[1] = v53;
        *(_OWORD *)v110.m256i_i8 = 0;
        a1[2] = 0;
        a1[3] = 0;
        *(_OWORD *)&v110.m256i_u64[2] = 0;
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(&v110);
      }
      else
      {
        ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 44LL);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          a1,
          v50 + 9);
      }
      break;
    case 0xA:
      ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 56LL);
      xpsrdr::DepthGuard::DepthGuard((xpsrdr::DepthGuard *)&v101, (int)v10, (int *)(a2 + 540));
      v99 = 0;
      v100.m11 = 0.0;
      v13 = *a3;
      v14 = **a3;
      *(_QWORD *)&v120.m11 = 0;
      *(_QWORD *)&v120.m[1][0] = &v100;
      *(_QWORD *)&v120.m[2][0] = &v99;
      v15 = (*v14)((__int64)v13, &GUID_97e294af_5b37_46b4_8057_874d2f64119b, &v120);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v120);
      if ( v100.m11 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v100.m11), v16, v17, v18);
      if ( v15 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
      HIDWORD(v102[0]) = 0;
      v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct D2D_MATRIX_3X2_F *), char *))(**a3)[5])(
              *a3,
              (char *)v102 + 4);
      if ( v19 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
      *(_OWORD *)&v103.m11 = 0;
      v100.m11 = 0.0;
      v23 = *(_QWORD *)v99;
      *(_QWORD *)&v120.m11 = 0;
      *(_QWORD *)&v120.m[1][0] = &v100;
      *(_QWORD *)&v120.m[2][0] = &v103;
      v24 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(v23 + 144))(v99, &v120);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v120);
      if ( v100.m11 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v100.m11), v25, v26, v27);
      if ( v24 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
      *(_OWORD *)&v122.m11 = 0;
      v28 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v99 + 96LL))(v99, &v122);
      if ( v28 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v29, v30, v31);
      *(_OWORD *)&v121.m11 = 0;
      v32 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v99 + 112LL))(v99, &v121);
      if ( v32 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, v33, v34, v35);
      *(_OWORD *)&v102[1] = 0;
      v100.m11 = 0.0;
      v36 = *(_QWORD *)v99;
      *(_QWORD *)&v120.m11 = 0;
      *(_QWORD *)&v120.m[1][0] = &v100;
      *(_QWORD *)&v120.m[2][0] = &v102[1];
      v37 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(v36 + 56))(v99, &v120);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v120);
      if ( v100.m11 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v100.m11), (int)v38, v39, v40);
      if ( v37 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v37, (int)v38, v39, v40);
      memset(&v100, 0, sizeof(v100));
      if ( v102[1] )
      {
        memset(&v120, 0, sizeof(v120));
        v41 = (*(__int64 (__fastcall **)(_QWORD, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v102[1] + 40LL))(v102[1], &v120);
        if ( v41 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v41, v42, v43, (int)v44);
        v123 = v120;
        xpsrdr::MultiplyMatrix(a4, &v123, &v100, v44);
      }
      else
      {
        v100 = *(struct D2D_MATRIX_3X2_F *)a4;
      }
      if ( !*(_QWORD *)&v103.m11
        || v121.m21 == 0.0
        || v121.m22 == 0.0
        || v122.m21 == 0.0
        || v122.m22 == 0.0
        || xpsrdr::NullMatrix((xpsrdr *)&v100, v38) )
      {
        xpsrdr::CreateEmptyBrushClipPair(a1, a2, 0);
      }
      else
      {
        *(_OWORD *)&v120.m11 = 0;
        v45 = (std::_Ref_count_base *)*((_QWORD *)&v99 + 1);
        if ( *((_QWORD *)&v99 + 1) )
        {
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v99 + 1) + 8LL));
          v45 = (std::_Ref_count_base *)*((_QWORD *)&v99 + 1);
        }
        *(_OWORD *)&v120.m11 = v99;
        v104 = 0;
        v105 = 0;
        v106 = a2;
        v107 = &v120;
        v108 = a5;
        v109 = a4;
        if ( v45 )
          std::_Ref_count_base::_Decref(v45);
        v110.m256i_i64[0] = v99;
        *(_OWORD *)&v110.m256i_u64[1] = *(_OWORD *)a4;
        v110.m256i_i64[3] = *((_QWORD *)a4 + 2);
        v111 = *a5;
        v112 = *(_DWORD *)(a2 + 528);
        v113 = 1048576000;
        if ( !*(_BYTE *)(a2 + 481) )
        {
          xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(
            a2 + 240,
            &v100,
            &v110);
          v46 = *(_QWORD *)&v100.m11;
          if ( *(_QWORD *)&v100.m11 != *(_QWORD *)(a2 + 248) )
          {
            ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 44LL);
            std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
              a1,
              v46 + 72);
            std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(&v104);
            if ( v102[2] )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v102[2]);
            if ( *(_QWORD *)&v103.m[1][0] )
              std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v103.m[1][0]);
            if ( *((_QWORD *)&v99 + 1) )
              std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v99 + 1));
            --*(_DWORD *)v101;
            return a1;
          }
        }
        xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush((xpsrdr::TileBrushBuilder *)&v104);
        if ( !*(_BYTE *)(a2 + 481) )
        {
          v47 = xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](
                  a2 + 240,
                  &v110);
          std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
            v47,
            &v104);
        }
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          a1,
          &v104);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(&v104);
      }
      if ( v102[2] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v102[2]);
      if ( *(_QWORD *)&v103.m[1][0] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v103.m[1][0]);
      if ( *((_QWORD *)&v99 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v99 + 1));
      --*(_DWORD *)v101;
      break;
    default:
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(LODWORD(v102[0]) - 9), (const char *)v10, (int)v11);
  }
  return a1;
}

```

## disassembly

```asm
0x1800b3ecc  mov     rax, rsp
0x1800b3ecf  push    rbp
0x1800b3ed0  push    rbx
0x1800b3ed1  push    rsi
0x1800b3ed2  push    rdi
0x1800b3ed3  push    r12
0x1800b3ed5  push    r13
0x1800b3ed7  push    r14
0x1800b3ed9  push    r15
0x1800b3edb  lea     rbp, [rax-128h]
0x1800b3ee2  sub     rsp, 1E8h
0x1800b3ee9  movaps  xmmword ptr [rax-58h], xmm6
0x1800b3eed  mov     rax, cs:__security_cookie
0x1800b3ef4  xor     rax, rsp
0x1800b3ef7  mov     qword ptr [rbp+120h+var_58], rax
0x1800b3efe  mov     rsi, r9
0x1800b3f01  mov     r14, r8
0x1800b3f04  mov     rbx, rdx
0x1800b3f07  mov     rdi, rcx
0x1800b3f0a  mov     qword ptr [rsp+220h+var_1C0], rcx
0x1800b3f0f  mov     r12, [rbp+120h+arg_20]
0x1800b3f16  xor     r13d, r13d
0x1800b3f19  mov     dword ptr [rsp+220h+var_1B8], r13d
0x1800b3f1e  mov     rcx, [r8]
0x1800b3f21  mov     rax, [rcx]
0x1800b3f24  lea     rdx, [rsp+220h+var_1B8]
0x1800b3f29  mov     rax, [rax+20h]
0x1800b3f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f32  test    eax, eax
0x1800b3f34  jns     short loc_1800B3F3E
0x1800b3f36  mov     ecx, eax; this
0x1800b3f38  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b3f3e  mov     ecx, dword ptr [rsp+220h+var_1B8]
0x1800b3f42  sub     ecx, 6
0x1800b3f45  jz      loc_1800B49F8
0x1800b3f4b  sub     ecx, 1
0x1800b3f4e  jz      loc_1800B4525
0x1800b3f54  sub     ecx, 1
0x1800b3f57  jz      loc_1800B43D0
0x1800b3f5d  sub     ecx, 1; this
0x1800b3f60  jz      loc_1800B43D0
0x1800b3f66  cmp     ecx, 1
0x1800b3f69  jz      short loc_1800B3F71
0x1800b3f6b  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800b3f71  mov     rax, [rbx+220h]
0x1800b3f78  inc     dword ptr [rax+38h]
0x1800b3f7b  lea     r8, [rbx+21Ch]; int *
0x1800b3f82  lea     rcx, [rsp+220h+var_1C0]; this
0x1800b3f87  call    ??0DepthGuard@xpsrdr@@QEAA@HAEAH@Z; xpsrdr::DepthGuard::DepthGuard(int,int &)
0x1800b3f8c  nop
0x1800b3f8d  xorps   xmm0, xmm0
0x1800b3f90  movdqa  [rsp+220h+var_1F8+8], xmm0
0x1800b3f96  mov     dword ptr [rsp+220h+var_1E8+8], r13d
0x1800b3f9b  mov     rcx, [r14]
0x1800b3f9e  mov     rax, [rcx]
0x1800b3fa1  mov     qword ptr [rbp+120h+var_C0], r13
0x1800b3fa5  lea     rdx, [rsp+220h+var_1E8+8]
0x1800b3faa  mov     qword ptr [rbp+120h+var_C0+8], rdx
0x1800b3fae  lea     rdx, [rsp+220h+var_1F8+8]
0x1800b3fb3  mov     [rbp+120h+var_B0], rdx
0x1800b3fb7  lea     r8, [rbp+120h+var_C0]
0x1800b3fbb  lea     rdx, _GUID_97e294af_5b37_46b4_8057_874d2f64119b
0x1800b3fc2  mov     rax, [rax]
0x1800b3fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3fca  mov     r15d, eax
0x1800b3fcd  lea     rcx, [rbp+120h+var_C0]
0x1800b3fd1  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b3fd6  mov     ecx, dword ptr [rsp+220h+var_1E8+8]; this
0x1800b3fda  test    ecx, ecx
0x1800b3fdc  jns     short loc_1800B3FE4
0x1800b3fde  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b3fe4  test    r15d, r15d
0x1800b3fe7  jns     short loc_1800B3FF2
0x1800b3fe9  mov     ecx, r15d; this
0x1800b3fec  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b3ff2  xorps   xmm6, xmm6
0x1800b3ff5  mov     dword ptr [rsp+220h+var_1B8+4], 0
0x1800b3ffd  mov     rcx, [r14]
0x1800b4000  mov     rax, [rcx]
0x1800b4003  lea     rdx, [rsp+220h+var_1B8+4]
0x1800b4008  mov     rax, [rax+28h]
0x1800b400c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4011  test    eax, eax
0x1800b4013  jns     short loc_1800B401D
0x1800b4015  mov     ecx, eax; this
0x1800b4017  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b401d  xorps   xmm0, xmm0
0x1800b4020  movdqu  xmmword ptr [rbp+120h+var_1A0], xmm0
0x1800b4025  mov     dword ptr [rsp+220h+var_1E8+8], r13d
0x1800b402a  mov     rcx, qword ptr [rsp+220h+var_1F8+8]
0x1800b402f  mov     rax, [rcx]
0x1800b4032  mov     qword ptr [rbp+120h+var_C0], r13
0x1800b4036  lea     rdx, [rsp+220h+var_1E8+8]
0x1800b403b  mov     qword ptr [rbp+120h+var_C0+8], rdx
0x1800b403f  lea     rdx, [rbp+120h+var_1A0]
0x1800b4043  mov     [rbp+120h+var_B0], rdx
0x1800b4047  lea     rdx, [rbp+120h+var_C0]
0x1800b404b  mov     rax, [rax+90h]
0x1800b4052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4057  mov     r14d, eax
0x1800b405a  lea     rcx, [rbp+120h+var_C0]
0x1800b405e  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b4063  mov     ecx, dword ptr [rsp+220h+var_1E8+8]; this
0x1800b4067  test    ecx, ecx
0x1800b4069  jns     short loc_1800B4071
0x1800b406b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b4071  test    r14d, r14d
0x1800b4074  jns     short loc_1800B407F
0x1800b4076  mov     ecx, r14d; this
0x1800b4079  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b407f  xorps   xmm0, xmm0
0x1800b4082  movups  xmmword ptr [rbp+120h+var_88], xmm0
0x1800b4089  mov     rcx, qword ptr [rsp+220h+var_1F8+8]
0x1800b408e  mov     rax, [rcx]
0x1800b4091  lea     rdx, [rbp+120h+var_88]
0x1800b4098  mov     rax, [rax+60h]
0x1800b409c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b40a1  test    eax, eax
0x1800b40a3  jns     short loc_1800B40AD
0x1800b40a5  mov     ecx, eax; this
0x1800b40a7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b40ad  xorps   xmm0, xmm0
0x1800b40b0  movups  xmmword ptr [rbp+120h+var_A0], xmm0
0x1800b40b7  mov     rcx, qword ptr [rsp+220h+var_1F8+8]
0x1800b40bc  mov     rax, [rcx]
0x1800b40bf  lea     rdx, [rbp+120h+var_A0]
0x1800b40c6  mov     rax, [rax+70h]
0x1800b40ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b40cf  test    eax, eax
0x1800b40d1  jns     short loc_1800B40DB
0x1800b40d3  mov     ecx, eax; this
0x1800b40d5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b40db  xorps   xmm0, xmm0
0x1800b40de  movdqu  xmmword ptr [rsp+220h+var_1B8+8], xmm0
0x1800b40e4  mov     dword ptr [rsp+220h+var_1E8+8], r13d
0x1800b40e9  mov     rcx, qword ptr [rsp+220h+var_1F8+8]
0x1800b40ee  mov     rax, [rcx]
0x1800b40f1  mov     qword ptr [rbp+120h+var_C0], r13
0x1800b40f5  lea     rdx, [rsp+220h+var_1E8+8]
0x1800b40fa  mov     qword ptr [rbp+120h+var_C0+8], rdx
0x1800b40fe  lea     rdx, [rsp+220h+var_1B8+8]
0x1800b4103  mov     [rbp+120h+var_B0], rdx
0x1800b4107  lea     rdx, [rbp+120h+var_C0]
0x1800b410b  mov     rax, [rax+38h]
0x1800b410f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4114  mov     r14d, eax
0x1800b4117  lea     rcx, [rbp+120h+var_C0]
0x1800b411b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800b4120  mov     ecx, dword ptr [rsp+220h+var_1E8+8]; this
0x1800b4124  test    ecx, ecx
0x1800b4126  jns     short loc_1800B412E
0x1800b4128  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b412e  test    r14d, r14d
0x1800b4131  jns     short loc_1800B413C
0x1800b4133  mov     ecx, r14d; this
0x1800b4136  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b413c  xorps   xmm0, xmm0
0x1800b413f  xor     eax, eax
0x1800b4141  movups  xmmword ptr [rsp+220h+var_1E8+8], xmm0
0x1800b4146  mov     qword ptr [rsp+220h+var_1E8+18h], rax
0x1800b414b  mov     rcx, qword ptr [rsp+220h+var_1B8+8]
0x1800b4150  test    rcx, rcx
0x1800b4153  jnz     short loc_1800B416A
0x1800b4155  movups  xmm0, xmmword ptr [rsi]
0x1800b4158  movups  xmmword ptr [rsp+220h+var_1E8+8], xmm0
0x1800b415d  movsd   xmm1, qword ptr [rsi+10h]
0x1800b4162  movsd   qword ptr [rsp+220h+var_1E8+18h], xmm1
0x1800b4168  jmp     short loc_1800B41C7
0x1800b416a  movups  [rbp+120h+var_C0], xmm0
0x1800b416e  mov     [rbp+120h+var_B0], rax
0x1800b4172  mov     rax, [rcx]
0x1800b4175  lea     rdx, [rbp+120h+var_C0]
0x1800b4179  mov     rax, [rax+28h]
0x1800b417d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4182  test    eax, eax
0x1800b4184  jns     short loc_1800B418E
0x1800b4186  mov     ecx, eax; this
0x1800b4188  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800b418e  movups  xmm0, [rbp+120h+var_C0]
0x1800b4192  movups  xmmword ptr [rbp+120h+var_70], xmm0
0x1800b4199  movss   xmm0, dword ptr [rbp+120h+var_B0]
0x1800b419e  movss   dword ptr [rbp+120h+var_70+10h], xmm0
0x1800b41a6  movss   xmm1, dword ptr [rbp+120h+var_B0+4]
0x1800b41ab  movss   dword ptr [rbp+120h+var_70+14h], xmm1
0x1800b41b3  lea     r8, [rsp+220h+var_1E8+8]; struct D2D_MATRIX_3X2_F *
0x1800b41b8  lea     rdx, [rbp+120h+var_70]; struct D2D_MATRIX_3X2_F *
0x1800b41bf  mov     rcx, rsi; this
0x1800b41c2  call    ?MultiplyMatrix@xpsrdr@@YAXAEBUD2D_MATRIX_3X2_F@@0AEAU2@@Z; xpsrdr::MultiplyMatrix(D2D_MATRIX_3X2_F const &,D2D_MATRIX_3X2_F const &,D2D_MATRIX_3X2_F &)
0x1800b41c7  cmp     qword ptr [rbp+120h+var_1A0], r13
0x1800b41cb  jz      loc_1800B43C0
0x1800b41d1  movss   xmm0, dword ptr [rbp+120h+var_A0+8]
0x1800b41d9  ucomiss xmm0, xmm6
0x1800b41dc  jp      short loc_1800B41E4
0x1800b41de  jz      loc_1800B43C0
0x1800b41e4  movss   xmm0, dword ptr [rbp+120h+var_A0+0Ch]
0x1800b41ec  ucomiss xmm0, xmm6
0x1800b41ef  jp      short loc_1800B41F7
0x1800b41f1  jz      loc_1800B43C0
0x1800b41f7  movss   xmm0, dword ptr [rbp+120h+var_88+8]
0x1800b41ff  ucomiss xmm0, xmm6
0x1800b4202  jp      short loc_1800B420A
0x1800b4204  jz      loc_1800B43C0
0x1800b420a  movss   xmm0, dword ptr [rbp+120h+var_88+0Ch]
0x1800b4212  ucomiss xmm0, xmm6
0x1800b4215  jp      short loc_1800B421D
0x1800b4217  jz      loc_1800B43C0
0x1800b421d  lea     rcx, [rsp+220h+var_1E8+8]; this
0x1800b4222  call    ?NullMatrix@xpsrdr@@YA_NAEBUD2D_MATRIX_3X2_F@@@Z; xpsrdr::NullMatrix(D2D_MATRIX_3X2_F const &)
0x1800b4227  test    al, al
0x1800b4229  jnz     loc_1800B43C0
0x1800b422f  xorps   xmm0, xmm0
0x1800b4232  movdqa  [rbp+120h+var_C0], xmm0
0x1800b4237  mov     rcx, qword ptr [rsp+220h+var_1E8]
0x1800b423c  test    rcx, rcx
0x1800b423f  jz      short loc_1800B424A
0x1800b4241  lock inc dword ptr [rcx+8]
0x1800b4245  mov     rcx, qword ptr [rsp+220h+var_1E8]; this
0x1800b424a  movaps  xmm0, [rsp+220h+var_1F8+8]
0x1800b424f  movdqa  [rbp+120h+var_C0], xmm0
0x1800b4254  xorps   xmm0, xmm0
0x1800b4257  movdqa  [rbp+120h+var_180], xmm0
0x1800b425c  movdqa  [rbp+120h+var_170], xmm0
0x1800b4261  mov     [rbp+120h+var_160], rbx
0x1800b4265  lea     rax, [rbp+120h+var_C0]
0x1800b4269  mov     [rbp+120h+var_158], rax
0x1800b426d  mov     [rbp+120h+var_150], r12
0x1800b4271  mov     [rbp+120h+var_148], rsi
0x1800b4275  test    rcx, rcx
0x1800b4278  jz      short loc_1800B427F
0x1800b427a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b427f  mov     rax, qword ptr [rsp+220h+var_1F8+8]
0x1800b4284  mov     qword ptr [rbp+120h+var_138], rax
0x1800b4288  movups  xmm0, xmmword ptr [rsi]
0x1800b428b  movups  [rbp+120h+var_138+8], xmm0
0x1800b428f  movsd   xmm1, qword ptr [rsi+10h]
0x1800b4294  movsd   [rbp+120h+var_120], xmm1
0x1800b4299  movups  xmm0, xmmword ptr [r12]
0x1800b429e  movdqu  [rbp+120h+var_118], xmm0
0x1800b42a3  mov     eax, [rbx+210h]
0x1800b42a9  mov     [rbp+120h+var_108], eax
0x1800b42ac  mov     [rbp+120h+var_104], 3E800000h
0x1800b42b3  cmp     [rbx+1E1h], r13b
0x1800b42ba  jnz     short loc_1800B433B
0x1800b42bc  lea     rcx, [rbx+0F0h]
0x1800b42c3  lea     r8, [rbp+120h+var_138]
0x1800b42c7  lea     rdx, [rsp+220h+var_1E8+8]
0x1800b42cc  call    ?find@?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@std@@@std@@@std@@AEBUKeyBrush@2@@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(xpsrdr::KeyBrush const &)
0x1800b42d1  mov     rdx, qword ptr [rsp+220h+var_1E8+8]
0x1800b42d6  cmp     rdx, [rbx+0F8h]
0x1800b42dd  jz      short loc_1800B433B
0x1800b42df  mov     rax, [rbx+220h]
0x1800b42e6  inc     dword ptr [rax+2Ch]
0x1800b42e9  add     rdx, 48h ; 'H'
0x1800b42ed  mov     rcx, rdi
0x1800b42f0  call    ??0?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@AEBU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> const &)
0x1800b42f5  nop
0x1800b42f6  lea     rcx, [rbp+120h+var_180]
0x1800b42fa  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x1800b42ff  nop
0x1800b4300  mov     rcx, qword ptr [rsp+220h+var_1B8+10h]; this
0x1800b4305  test    rcx, rcx
0x1800b4308  jz      short loc_1800B4310
0x1800b430a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b430f  nop
0x1800b4310  mov     rcx, qword ptr [rbp+120h+var_1A0+8]; this
0x1800b4314  test    rcx, rcx
0x1800b4317  jz      short loc_1800B431F
0x1800b4319  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b431e  nop
0x1800b431f  mov     rcx, qword ptr [rsp+220h+var_1E8]; this
0x1800b4324  test    rcx, rcx
0x1800b4327  jz      short loc_1800B432F
0x1800b4329  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b432e  nop
0x1800b432f  mov     rcx, qword ptr [rsp+220h+var_1C0]
0x1800b4334  dec     dword ptr [rcx]
0x1800b4336  jmp     loc_1800B4A4B
0x1800b433b  lea     rdx, [rsp+220h+var_1F8+8]
0x1800b4340  lea     rcx, [rbp+120h+var_180]; this
0x1800b4344  call    ?CreateD2DBrushFromXpsVisualBrush@TileBrushBuilder@xpsrdr@@QEAAXAEBV?$shared_ptr@UIXpsOMVisualBrush@@@std@@@Z; xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush(std::shared_ptr<IXpsOMVisualBrush> const &)
0x1800b4349  cmp     [rbx+1E1h], r13b
0x1800b4350  jnz     short loc_1800B436E
0x1800b4352  lea     rcx, [rbx+0F0h]
0x1800b4359  lea     rdx, [rbp+120h+var_138]
0x1800b435d  call    ??A?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAAAEAU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEBUKeyBrush@1@@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](xpsrdr::KeyBrush const &)
0x1800b4362  mov     rcx, rax
0x1800b4365  lea     rdx, [rbp+120h+var_180]
0x1800b4369  call    ??$?4U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAAAEAU01@AEBU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> const &)
0x1800b436e  lea     rdx, [rbp+120h+var_180]
0x1800b4372  mov     rcx, rdi
0x1800b4375  call    ??0?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@AEBU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> const &)
0x1800b437a  nop
0x1800b437b  lea     rcx, [rbp+120h+var_180]
0x1800b437f  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x1800b4384  nop
0x1800b4385  mov     rcx, qword ptr [rsp+220h+var_1B8+10h]; this
0x1800b438a  test    rcx, rcx
0x1800b438d  jz      short loc_1800B4395
0x1800b438f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b4394  nop
  ... truncated ...
```
