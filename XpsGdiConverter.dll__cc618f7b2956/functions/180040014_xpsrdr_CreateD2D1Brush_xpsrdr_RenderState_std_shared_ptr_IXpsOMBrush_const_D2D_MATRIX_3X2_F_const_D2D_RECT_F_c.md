# xpsrdr::CreateD2D1Brush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F const &,float *)

- ea: `0x180040014`
- end: `0x180040b83`
- name: `?CreateD2D1Brush@xpsrdr@@YA?AU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMBrush@@@3@AEBUD2D_MATRIX_3X2_F@@AEBUD2D_RECT_F@@PEAM@Z`
- size: `2927`
- prototype: ``
- caller_count: `3`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x1800384fc`
- `0x180039cd4`
- `0x18003a18c`

## callees

- `0x180008830`
- `0x18000d61c`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e990`
- `0x18000f9bc`
- `0x180011b0c`
- `0x1800122a8`
- `0x18001df50`
- `0x1800229e8`
- `0x18002b50c`
- `0x180033f38`
- `0x180037278`
- `0x1800372e4`
- `0x180037864`
- `0x18003edd0`
- `0x18003fbcc`
- `0x18003fc30`
- `0x18003fca0`
- `0x18003fcc8`
- `0x18003feb0`
- `0x180040014`
- `0x180040b8c`
- `0x180041548`
- `0x1800416a8`
- `0x180041a30`
- `0x180044b1c`
- `0x180045164`
- `0x180045b18`
- `0x180046228`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_DWORD *__fastcall xpsrdr::CreateD2D1Brush(
        _DWORD *a1,
        __int64 a2,
        __int64 (__fastcall ****a3)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *),
        xpsrdr *a4,
        __int128 *a5)
{
  int v9; // eax
  struct _GUID *v10; // rdx
  const char *v11; // r8
  int v12; // r9d
  __int64 *v13; // rcx
  __int64 (__fastcall **v14)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *); // rax
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
  int v38; // edx
  const char *v39; // r8
  int v40; // r9d
  int v41; // eax
  int v42; // edx
  const char *v43; // r8
  struct D2D_MATRIX_3X2_F *v44; // r9
  const struct D2D_MATRIX_3X2_F *v45; // rdx
  _QWORD *v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  float v49; // xmm2_4
  _QWORD *v50; // rax
  __int64 v51; // rax
  __int64 v52; // rbx
  __int64 D2D1GradientBrush; // rax
  __int64 v54; // rax
  __int64 *v55; // rcx
  __int64 (__fastcall **v56)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *); // rax
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
  int v75; // edx
  const char *v76; // r8
  int v77; // r9d
  const struct D2D_MATRIX_3X2_F *v78; // rdx
  int v79; // eax
  int v80; // edx
  const char *v81; // r8
  struct D2D_MATRIX_3X2_F *v82; // r9
  __int64 v83; // rax
  int v84; // r14d
  int v85; // edx
  const char *v86; // r8
  int v87; // r9d
  const char *v88; // rdx
  xpsrdr *v89; // rcx
  int v90; // r8d
  __int64 v91; // rax
  int v92; // r14d
  int v93; // edx
  const char *v94; // r8
  int v95; // r9d
  float BitmapBrushWeight; // xmm0_4
  _QWORD *v97; // rax
  _BYTE *v98; // rdx
  __int64 v99; // rax
  __int64 v100; // rbx
  __int64 v101; // rax
  __int64 *v103; // [rsp+38h] [rbp-D0h] BYREF
  struct D2D_MATRIX_3X2_F v104; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v105; // [rsp+58h] [rbp-B0h]
  _DWORD *v106; // [rsp+60h] [rbp-A8h] BYREF
  int v107; // [rsp+68h] [rbp-A0h] BYREF
  int v108; // [rsp+6Ch] [rbp-9Ch] BYREF
  __int64 v109; // [rsp+70h] [rbp-98h] BYREF
  struct D2D_MATRIX_3X2_F v110; // [rsp+78h] [rbp-90h] BYREF
  __int64 v111; // [rsp+90h] [rbp-78h]
  _BYTE v112[16]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v113[64]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 *v114; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v115; // [rsp+F0h] [rbp-18h]
  __int64 v116; // [rsp+100h] [rbp-8h]
  __int128 v117; // [rsp+108h] [rbp+0h]
  int v118; // [rsp+118h] [rbp+10h]
  int v119; // [rsp+11Ch] [rbp+14h]
  __int64 *v120; // [rsp+120h] [rbp+18h] BYREF
  __int128 v121; // [rsp+128h] [rbp+20h]
  __int64 v122; // [rsp+138h] [rbp+30h]
  __int128 v123; // [rsp+140h] [rbp+38h]
  int v124; // [rsp+150h] [rbp+48h]
  float v125; // [rsp+154h] [rbp+4Ch]
  struct D2D_MATRIX_3X2_F v126; // [rsp+158h] [rbp+50h] BYREF
  struct D2D_MATRIX_3X2_F v127; // [rsp+178h] [rbp+70h] BYREF
  struct D2D_MATRIX_3X2_F v128; // [rsp+190h] [rbp+88h] BYREF
  struct D2D_MATRIX_3X2_F v129; // [rsp+1A8h] [rbp+A0h] BYREF

  v106 = a1;
  v107 = 0;
  v9 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *), int *))(**a3)[4])(
         *a3,
         &v107);
  if ( v9 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v9, (int)v10, v11, v12);
  switch ( v107 )
  {
    case 6:
      *(_OWORD *)&v126.m11 = 0;
      v100 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v126);
      v101 = xpsrdr::CreateSolidColorBrush(&v129, a2, a3, 0);
      std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
        a1,
        v101,
        v100);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v129);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v126);
      return a1;
    case 7:
      ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 40LL);
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v103);
      v104.m21 = 0.0;
      v55 = (__int64 *)*a3;
      v56 = **a3;
      *(_QWORD *)&v127.m11 = 0;
      *(_QWORD *)&v127.m[1][0] = v104.m[1];
      *(_QWORD *)&v127.m[2][0] = &v103;
      v57 = (*v56)(v55, &GUID_3df0b466_d382_49ef_8550_dd94c80242e4, &v127);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v127);
      if ( v104.m21 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v104.m21), v58, v59, v60);
      if ( v57 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v57, v58, v59, v60);
      v108 = 0;
      v61 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *), int *))(**a3)[5])(
              *a3,
              &v108);
      if ( v61 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v61, v62, v63, v64);
      *(_OWORD *)&v126.m11 = 0;
      v65 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(*v103 + 96))(v103, &v126);
      if ( v65 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v66, v67, v68);
      *(_OWORD *)&v129.m11 = 0;
      v69 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(*v103 + 112))(v103, &v129);
      if ( v69 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v69, v70, v71, v72);
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v109);
      v104.m21 = 0.0;
      v73 = *v103;
      *(_QWORD *)&v127.m11 = 0;
      *(_QWORD *)&v127.m[1][0] = v104.m[1];
      *(_QWORD *)&v127.m[2][0] = &v109;
      v74 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(v73 + 56))(v103, &v127);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v127);
      if ( v104.m21 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v104.m21), v75, v76, v77);
      if ( v74 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v74, v75, v76, v77);
      *(_OWORD *)&v110.m[1][0] = 0;
      v111 = 0;
      if ( (unsigned __int8)std::operator!=<ID3D11Device>(&v109) )
      {
        memset(&v127, 0, sizeof(v127));
        v79 = (*(__int64 (__fastcall **)(__int64, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v109 + 40LL))(v109, &v127);
        if ( v79 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v79, v80, v81, (int)v82);
        v128 = v127;
        xpsrdr::MultiplyMatrix(a4, &v128, (struct D2D_MATRIX_3X2_F *)v110.m[1], v82);
      }
      else
      {
        *(_OWORD *)&v110.m[1][0] = *(_OWORD *)a4;
        v111 = *((_QWORD *)a4 + 2);
      }
      if ( v129.m21 == 0.0
        || v129.m22 == 0.0
        || v126.m21 == 0.0
        || v126.m22 == 0.0
        || xpsrdr::NullMatrix((xpsrdr *)v110.m[1], v78) )
      {
        xpsrdr::CreateEmptyBrushClipPair(a1, a2, 0);
      }
      else
      {
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v110.m[1]);
        v104.m21 = 0.0;
        v83 = *v103;
        v114 = 0;
        *(_QWORD *)&v115 = v104.m[1];
        *((_QWORD *)&v115 + 1) = v110.m[1];
        v84 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v83 + 144))(v103, &v114);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v114);
        if ( v104.m21 < 0.0 )
          xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v104.m21), v85, v86, v87);
        if ( v84 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v84, v85, v86, v87);
        if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v110.m[1]) )
          xpsrdr::ThrowLogicException(v89, v88, v90);
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v127);
        v104.m21 = 0.0;
        v91 = *v103;
        v114 = 0;
        *(_QWORD *)&v115 = v104.m[1];
        *((_QWORD *)&v115 + 1) = &v127;
        v92 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v91 + 160))(v103, &v114);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v114);
        if ( v104.m21 < 0.0 )
          xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v104.m21), v93, v94, v95);
        if ( v92 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v92, v93, v94, v95);
        xpsrdr::Image::CreateImage(&v128, a2, v110.m[1], &v127);
        std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(v104.m[1], &v103);
        xpsrdr::TileBrushBuilder::TileBrushBuilder(
          (unsigned int)v113,
          a2,
          (unsigned int)&v104.m21,
          (_DWORD)a4,
          (__int64)a5);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v104.m[1]);
        BitmapBrushWeight = xpsrdr::TileBrushBuilder::GetBitmapBrushWeight(v113, &v128);
        v120 = v103;
        v121 = *(_OWORD *)a4;
        v122 = *((_QWORD *)a4 + 2);
        v123 = *a5;
        v124 = *(_DWORD *)(a2 + 528);
        v125 = BitmapBrushWeight;
        if ( *(_BYTE *)(a2 + 481)
          || (xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(
                a2 + 240,
                &v106,
                &v120),
              v97 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                                a2 + 240,
                                v112),
              v106 == (_DWORD *)*v97) )
        {
          xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsImageBrush((xpsrdr::TileBrushBuilder *)v113);
          if ( !*(_BYTE *)(a2 + 481) )
          {
            v99 = xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](
                    a2 + 240,
                    &v120);
            std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
              v99,
              v113);
          }
          v98 = v113;
        }
        else
        {
          ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 44LL);
          v98 = (_BYTE *)(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v106)
                        + 56);
        }
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          a1,
          v98);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v113);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v128);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v127);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v110.m[1]);
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v109);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v103);
      break;
    case 8:
    case 9:
      *(_OWORD *)&v126.m11 = *(_OWORD *)(a2 + 100);
      if ( *(int *)(a2 + 80) <= 37632 )
        v49 = (float)xpsrdr::GetBytesPerPixel((xpsrdr *)&v126, v10) * 11264.0;
      else
        v49 = (float)xpsrdr::GetBytesPerPixel((xpsrdr *)&v126, v10) * 2047.0;
      v120 = (__int64 *)*a3;
      v121 = *(_OWORD *)a4;
      v122 = *((_QWORD *)a4 + 2);
      v123 = *a5;
      v124 = *(_DWORD *)(a2 + 528);
      v125 = v49 * 0.00000095367432;
      xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(
        a2 + 240,
        &v106,
        &v120);
      v50 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                        a2 + 240,
                        v112);
      if ( v106 == (_DWORD *)*v50 )
      {
        *(_OWORD *)&v126.m11 = 0;
        v52 = std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v126);
        D2D1GradientBrush = xpsrdr::CreateD2D1GradientBrush((unsigned int)&v129, a2, (_DWORD)a3, (unsigned int)&v107, 0);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          &v114,
          D2D1GradientBrush,
          v52);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v129);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v126);
        v54 = xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](
                a2 + 240,
                &v120);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
          v54,
          &v114);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          a1,
          &v114);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(&v114);
      }
      else
      {
        ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 44LL);
        v51 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(&v106);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          a1,
          v51 + 56);
      }
      break;
    case 10:
      ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 56LL);
      xpsrdr::DepthGuard::DepthGuard((xpsrdr::DepthGuard *)&v106, (int)v10, (int *)(a2 + 540));
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v103);
      v104.m21 = 0.0;
      v13 = (__int64 *)*a3;
      v14 = **a3;
      *(_QWORD *)&v126.m11 = 0;
      *(_QWORD *)&v126.m[1][0] = v104.m[1];
      *(_QWORD *)&v126.m[2][0] = &v103;
      v15 = (*v14)(v13, &GUID_97e294af_5b37_46b4_8057_874d2f64119b, &v126);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v126);
      if ( v104.m21 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v104.m21), v16, v17, v18);
      if ( v15 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
      v108 = 0;
      v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64 *, GUID *, struct D2D_MATRIX_3X2_F *), int *))(**a3)[5])(
              *a3,
              &v108);
      if ( v19 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v110.m[1]);
      v104.m21 = 0.0;
      v23 = *v103;
      *(_QWORD *)&v126.m11 = 0;
      *(_QWORD *)&v126.m[1][0] = v104.m[1];
      *(_QWORD *)&v126.m[2][0] = v110.m[1];
      v24 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(v23 + 144))(v103, &v126);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v126);
      if ( v104.m21 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v104.m21), v25, v26, v27);
      if ( v24 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v24, v25, v26, v27);
      *(_OWORD *)&v128.m11 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(*v103 + 96))(v103, &v128);
      if ( v28 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v29, v30, v31);
      *(_OWORD *)&v127.m11 = 0;
      v32 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(*v103 + 112))(v103, &v127);
      if ( v32 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v32, v33, v34, v35);
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v109);
      v104.m21 = 0.0;
      v36 = *v103;
      *(_QWORD *)&v126.m11 = 0;
      *(_QWORD *)&v126.m[1][0] = v104.m[1];
      *(_QWORD *)&v126.m[2][0] = &v109;
      v37 = (*(__int64 (__fastcall **)(__int64 *, struct D2D_MATRIX_3X2_F *))(v36 + 56))(v103, &v126);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v126);
      if ( v104.m21 < 0.0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v104.m21), v38, v39, v40);
      if ( v37 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v37, v38, v39, v40);
      *(_OWORD *)&v104.m[1][0] = 0;
      v105 = 0;
      if ( (unsigned __int8)std::operator!=<ID3D11Device>(&v109) )
      {
        memset(&v126, 0, sizeof(v126));
        v41 = (*(__int64 (__fastcall **)(__int64, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v109 + 40LL))(v109, &v126);
        if ( v41 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v41, v42, v43, (int)v44);
        v129 = v126;
        xpsrdr::MultiplyMatrix(a4, &v129, (struct D2D_MATRIX_3X2_F *)v104.m[1], v44);
      }
      else
      {
        *(_OWORD *)&v104.m[1][0] = *(_OWORD *)a4;
        v105 = *((_QWORD *)a4 + 2);
      }
      if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v110.m[1])
        || v127.m21 == 0.0
        || v127.m22 == 0.0
        || v128.m21 == 0.0
        || v128.m22 == 0.0
        || xpsrdr::NullMatrix((xpsrdr *)v104.m[1], v45) )
      {
        xpsrdr::CreateEmptyBrushClipPair(a1, a2, 0);
      }
      else
      {
        std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(&v126, &v103);
        xpsrdr::TileBrushBuilder::TileBrushBuilder((unsigned int)v113, a2, (unsigned int)&v126, (_DWORD)a4, (__int64)a5);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v126);
        v114 = v103;
        v115 = *(_OWORD *)a4;
        v116 = *((_QWORD *)a4 + 2);
        v117 = *a5;
        v118 = *(_DWORD *)(a2 + 528);
        v119 = 1048576000;
        if ( !*(_BYTE *)(a2 + 481) )
        {
          xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(
            a2 + 240,
            v104.m[1],
            &v114);
          v46 = (_QWORD *)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                            a2 + 240,
                            v112);
          if ( *(_QWORD *)&v104.m[1][0] != *v46 )
          {
            ++*(_DWORD *)(*(_QWORD *)(a2 + 544) + 44LL);
            v47 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v104.m[1]);
            std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
              a1,
              v47 + 56);
            std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v113);
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v109);
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(v110.m[1]);
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v103);
            --*v106;
            return a1;
          }
        }
        xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush((xpsrdr::TileBrushBuilder *)v113);
        if ( !*(_BYTE *)(a2 + 481) )
        {
          v48 = xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](
                  a2 + 240,
                  &v114);
          std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
            v48,
            v113);
        }
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(
          a1,
          v113);
        std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v113);
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v109);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(v110.m[1]);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v103);
      --*v106;
      return a1;
    default:
      xpsrdr::ThrowLogicException((xpsrdr *)(unsigned int)(v107 - 9), (const char *)v10, (int)v11);
  }
  return a1;
}

```

## disassembly

```asm
0x180040014  mov     rax, rsp
0x180040017  push    rbp
0x180040018  push    rbx
0x180040019  push    rsi
0x18004001a  push    rdi
0x18004001b  push    r12
0x18004001d  push    r13
0x18004001f  push    r14
0x180040021  push    r15
0x180040023  lea     rbp, [rax-118h]
0x18004002a  sub     rsp, 1D8h
0x180040031  movaps  xmmword ptr [rax-58h], xmm6
0x180040035  mov     rax, cs:__security_cookie
0x18004003c  xor     rax, rsp
0x18004003f  mov     qword ptr [rbp+110h+var_58], rax
0x180040046  mov     rbx, r9
0x180040049  mov     r14, r8
0x18004004c  mov     rdi, rdx
0x18004004f  mov     rsi, rcx
0x180040052  mov     qword ptr [rsp+210h+var_1B8], rcx
0x180040057  mov     r12, [rbp+110h+arg_20]
0x18004005e  xor     r13d, r13d
0x180040061  mov     dword ptr [rsp+210h+var_1B0], r13d
0x180040066  mov     rcx, [r8]
0x180040069  mov     rax, [rcx]
0x18004006c  lea     rdx, [rsp+210h+var_1B0]
0x180040071  mov     rax, [rax+20h]
0x180040075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004007a  test    eax, eax
0x18004007c  jns     short loc_180040086
0x18004007e  mov     ecx, eax; this
0x180040080  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180040086  mov     ecx, dword ptr [rsp+210h+var_1B0]
0x18004008a  sub     ecx, 6
0x18004008d  jz      loc_180040B09
0x180040093  sub     ecx, 1
0x180040096  jz      loc_18004065D
0x18004009c  sub     ecx, 1
0x18004009f  jz      loc_180040504
0x1800400a5  sub     ecx, 1; this
0x1800400a8  jz      loc_180040504
0x1800400ae  cmp     ecx, 1
0x1800400b1  jz      short loc_1800400B9
0x1800400b3  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800400b9  mov     rax, [rdi+220h]
0x1800400c0  inc     dword ptr [rax+38h]
0x1800400c3  lea     r8, [rdi+21Ch]; int *
0x1800400ca  lea     rcx, [rsp+210h+var_1B8]; this
0x1800400cf  call    ??0DepthGuard@xpsrdr@@QEAA@HAEAH@Z; xpsrdr::DepthGuard::DepthGuard(int,int &)
0x1800400d4  nop
0x1800400d5  lea     rcx, [rsp+210h+var_1E0]
0x1800400da  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800400df  nop
0x1800400e0  mov     dword ptr [rsp+210h+var_1D8+8], r13d
0x1800400e5  mov     rcx, [r14]
0x1800400e8  mov     rax, [rcx]
0x1800400eb  mov     qword ptr [rbp+110h+var_C0], r13
0x1800400ef  lea     rdx, [rsp+210h+var_1D8+8]
0x1800400f4  mov     qword ptr [rbp+110h+var_C0+8], rdx
0x1800400f8  lea     rdx, [rsp+210h+var_1E0]
0x1800400fd  mov     [rbp+110h+var_B0], rdx
0x180040101  lea     r8, [rbp+110h+var_C0]
0x180040105  lea     rdx, _GUID_97e294af_5b37_46b4_8057_874d2f64119b
0x18004010c  mov     rax, [rax]
0x18004010f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040114  mov     r15d, eax
0x180040117  lea     rcx, [rbp+110h+var_C0]
0x18004011b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180040120  mov     ecx, dword ptr [rsp+210h+var_1D8+8]; this
0x180040124  test    ecx, ecx
0x180040126  jns     short loc_18004012E
0x180040128  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004012e  test    r15d, r15d
0x180040131  jns     short loc_18004013C
0x180040133  mov     ecx, r15d; this
0x180040136  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18004013c  xorps   xmm6, xmm6
0x18004013f  mov     dword ptr [rsp+210h+var_1B0+4], 0
0x180040147  mov     rcx, [r14]
0x18004014a  mov     rax, [rcx]
0x18004014d  lea     rdx, [rsp+210h+var_1B0+4]
0x180040152  mov     rax, [rax+28h]
0x180040156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004015b  test    eax, eax
0x18004015d  jns     short loc_180040167
0x18004015f  mov     ecx, eax; this
0x180040161  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180040167  lea     rcx, [rsp+210h+var_1A0+8]
0x18004016c  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180040171  nop
0x180040172  mov     dword ptr [rsp+210h+var_1D8+8], r13d
0x180040177  mov     rcx, [rsp+210h+var_1E0]
0x18004017c  mov     rax, [rcx]
0x18004017f  mov     qword ptr [rbp+110h+var_C0], r13
0x180040183  lea     rdx, [rsp+210h+var_1D8+8]
0x180040188  mov     qword ptr [rbp+110h+var_C0+8], rdx
0x18004018c  lea     rdx, [rsp+210h+var_1A0+8]
0x180040191  mov     [rbp+110h+var_B0], rdx
0x180040195  lea     rdx, [rbp+110h+var_C0]
0x180040199  mov     rax, [rax+90h]
0x1800401a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401a5  mov     r14d, eax
0x1800401a8  lea     rcx, [rbp+110h+var_C0]
0x1800401ac  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800401b1  mov     ecx, dword ptr [rsp+210h+var_1D8+8]; this
0x1800401b5  test    ecx, ecx
0x1800401b7  jns     short loc_1800401BF
0x1800401b9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800401bf  test    r14d, r14d
0x1800401c2  jns     short loc_1800401CD
0x1800401c4  mov     ecx, r14d; this
0x1800401c7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800401cd  xorps   xmm0, xmm0
0x1800401d0  movups  xmmword ptr [rbp+110h+var_88], xmm0
0x1800401d7  mov     rcx, [rsp+210h+var_1E0]
0x1800401dc  mov     rax, [rcx]
0x1800401df  lea     rdx, [rbp+110h+var_88]
0x1800401e6  mov     rax, [rax+60h]
0x1800401ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401ef  test    eax, eax
0x1800401f1  jns     short loc_1800401FB
0x1800401f3  mov     ecx, eax; this
0x1800401f5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800401fb  xorps   xmm0, xmm0
0x1800401fe  movups  [rbp+110h+var_A0], xmm0
0x180040202  mov     rcx, [rsp+210h+var_1E0]
0x180040207  mov     rax, [rcx]
0x18004020a  lea     rdx, [rbp+110h+var_A0]
0x18004020e  mov     rax, [rax+70h]
0x180040212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040217  test    eax, eax
0x180040219  jns     short loc_180040223
0x18004021b  mov     ecx, eax; this
0x18004021d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180040223  lea     rcx, [rsp+210h+var_1A8]
0x180040228  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18004022d  nop
0x18004022e  mov     dword ptr [rsp+210h+var_1D8+8], r13d
0x180040233  mov     rcx, [rsp+210h+var_1E0]
0x180040238  mov     rax, [rcx]
0x18004023b  mov     qword ptr [rbp+110h+var_C0], r13
0x18004023f  lea     rdx, [rsp+210h+var_1D8+8]
0x180040244  mov     qword ptr [rbp+110h+var_C0+8], rdx
0x180040248  lea     rdx, [rsp+210h+var_1A8]
0x18004024d  mov     [rbp+110h+var_B0], rdx
0x180040251  lea     rdx, [rbp+110h+var_C0]
0x180040255  mov     rax, [rax+38h]
0x180040259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004025e  mov     r14d, eax
0x180040261  lea     rcx, [rbp+110h+var_C0]
0x180040265  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18004026a  mov     ecx, dword ptr [rsp+210h+var_1D8+8]; this
0x18004026e  test    ecx, ecx
0x180040270  jns     short loc_180040278
0x180040272  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180040278  test    r14d, r14d
0x18004027b  jns     short loc_180040286
0x18004027d  mov     ecx, r14d; this
0x180040280  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180040286  xorps   xmm0, xmm0
0x180040289  xor     eax, eax
0x18004028b  movups  xmmword ptr [rsp+210h+var_1D8+8], xmm0
0x180040290  mov     [rsp+210h+var_1C0], rax
0x180040295  lea     rcx, [rsp+210h+var_1A8]
0x18004029a  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18004029f  test    al, al
0x1800402a1  jz      short loc_180040309
0x1800402a3  xor     eax, eax
0x1800402a5  movups  [rbp+110h+var_C0], xmm0
0x1800402a9  mov     [rbp+110h+var_B0], rax
0x1800402ad  mov     rcx, [rsp+210h+var_1A8]
0x1800402b2  mov     rax, [rcx]
0x1800402b5  lea     rdx, [rbp+110h+var_C0]
0x1800402b9  mov     rax, [rax+28h]
0x1800402bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402c2  test    eax, eax
0x1800402c4  jns     short loc_1800402CE
0x1800402c6  mov     ecx, eax; this
0x1800402c8  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800402ce  movups  xmm0, [rbp+110h+var_C0]
0x1800402d2  movups  xmmword ptr [rbp+110h+var_70], xmm0
0x1800402d9  movss   xmm0, dword ptr [rbp+110h+var_B0]
0x1800402de  movss   dword ptr [rbp+110h+var_70+10h], xmm0
0x1800402e6  movss   xmm1, dword ptr [rbp+110h+var_B0+4]
0x1800402eb  movss   dword ptr [rbp+110h+var_70+14h], xmm1
0x1800402f3  lea     r8, [rsp+210h+var_1D8+8]; struct D2D_MATRIX_3X2_F *
0x1800402f8  lea     rdx, [rbp+110h+var_70]; struct D2D_MATRIX_3X2_F *
0x1800402ff  mov     rcx, rbx; this
0x180040302  call    ?MultiplyMatrix@xpsrdr@@YAXAEBUD2D_MATRIX_3X2_F@@0AEAU2@@Z; xpsrdr::MultiplyMatrix(D2D_MATRIX_3X2_F const &,D2D_MATRIX_3X2_F const &,D2D_MATRIX_3X2_F &)
0x180040307  jmp     short loc_18004031C
0x180040309  movups  xmm0, xmmword ptr [rbx]
0x18004030c  movups  xmmword ptr [rsp+210h+var_1D8+8], xmm0
0x180040311  movsd   xmm1, qword ptr [rbx+10h]
0x180040316  movsd   [rsp+210h+var_1C0], xmm1
0x18004031c  lea     rcx, [rsp+210h+var_1A0+8]
0x180040321  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180040326  test    al, al
0x180040328  jz      loc_1800404F4
0x18004032e  movss   xmm0, dword ptr [rbp+110h+var_A0+8]
0x180040333  ucomiss xmm0, xmm6
0x180040336  jp      short loc_18004033E
0x180040338  jz      loc_1800404F4
0x18004033e  movss   xmm0, dword ptr [rbp+110h+var_A0+0Ch]
0x180040343  ucomiss xmm0, xmm6
0x180040346  jp      short loc_18004034E
0x180040348  jz      loc_1800404F4
0x18004034e  movss   xmm0, dword ptr [rbp+110h+var_88+8]
0x180040356  ucomiss xmm0, xmm6
0x180040359  jp      short loc_180040361
0x18004035b  jz      loc_1800404F4
0x180040361  movss   xmm0, dword ptr [rbp+110h+var_88+0Ch]
0x180040369  ucomiss xmm0, xmm6
0x18004036c  jp      short loc_180040374
0x18004036e  jz      loc_1800404F4
0x180040374  lea     rcx, [rsp+210h+var_1D8+8]; this
0x180040379  call    ?NullMatrix@xpsrdr@@YA_NAEBUD2D_MATRIX_3X2_F@@@Z; xpsrdr::NullMatrix(D2D_MATRIX_3X2_F const &)
0x18004037e  test    al, al
0x180040380  jnz     loc_1800404F4
0x180040386  lea     rdx, [rsp+210h+var_1E0]
0x18004038b  lea     rcx, [rbp+110h+var_C0]
0x18004038f  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x180040394  mov     [rsp+20h], r12
0x180040399  mov     r9, rbx
0x18004039c  lea     r8, [rbp+110h+var_C0]
0x1800403a0  mov     rdx, rdi
0x1800403a3  lea     rcx, [rbp+110h+var_170]
0x1800403a7  call    ??0TileBrushBuilder@xpsrdr@@QEAA@AEAURenderState@1@AEBV?$shared_ptr@UIXpsOMTileBrush@@@std@@AEBUD2D_MATRIX_3X2_F@@AEBUD2D_RECT_F@@@Z; xpsrdr::TileBrushBuilder::TileBrushBuilder(xpsrdr::RenderState &,std::shared_ptr<IXpsOMTileBrush> const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F const &)
0x1800403ac  nop
0x1800403ad  lea     rcx, [rbp+110h+var_C0]
0x1800403b1  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800403b6  mov     rax, [rsp+210h+var_1E0]
0x1800403bb  mov     [rbp+110h+var_130], rax
0x1800403bf  movups  xmm0, xmmword ptr [rbx]
0x1800403c2  movups  [rbp+110h+var_128], xmm0
0x1800403c6  movsd   xmm1, qword ptr [rbx+10h]
0x1800403cb  movsd   [rbp+110h+var_118], xmm1
0x1800403d0  movups  xmm0, xmmword ptr [r12]
0x1800403d5  movdqu  [rbp+110h+var_110], xmm0
0x1800403da  mov     eax, [rdi+210h]
0x1800403e0  mov     [rbp+110h+var_100], eax
0x1800403e3  mov     [rbp+110h+var_FC], 3E800000h
0x1800403ea  cmp     [rdi+1E1h], r13b
0x1800403f1  jnz     loc_18004047D
0x1800403f7  lea     rbx, [rdi+0F0h]
0x1800403fe  lea     r8, [rbp+110h+var_130]
0x180040402  lea     rdx, [rsp+210h+var_1D8+8]
0x180040407  mov     rcx, rbx
0x18004040a  call    ?find@?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@std@@@std@@@std@@@std@@AEBUKeyBrush@2@@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::find(xpsrdr::KeyBrush const &)
0x18004040f  lea     rdx, [rbp+110h+var_180]
0x180040413  mov     rcx, rbx
0x180040416  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x18004041b  mov     rcx, [rax]
0x18004041e  cmp     qword ptr [rsp+210h+var_1D8+8], rcx
0x180040423  jz      short loc_18004047D
0x180040425  mov     rax, [rdi+220h]
0x18004042c  inc     dword ptr [rax+2Ch]
0x18004042f  lea     rcx, [rsp+210h+var_1D8+8]
0x180040434  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180040439  lea     rdx, [rax+38h]
0x18004043d  mov     rcx, rsi
0x180040440  call    ??0?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@AEBU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> const &)
0x180040445  nop
0x180040446  lea     rcx, [rbp+110h+var_170]
0x18004044a  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x18004044f  nop
0x180040450  lea     rcx, [rsp+210h+var_1A8]
0x180040455  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18004045a  nop
0x18004045b  lea     rcx, [rsp+210h+var_1A0+8]
0x180040460  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180040465  nop
0x180040466  lea     rcx, [rsp+210h+var_1E0]
0x18004046b  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180040470  nop
0x180040471  mov     rcx, qword ptr [rsp+210h+var_1B8]
0x180040476  dec     dword ptr [rcx]
0x180040478  jmp     loc_180040B55
0x18004047d  lea     rdx, [rsp+210h+var_1E0]
0x180040482  lea     rcx, [rbp+110h+var_170]; this
0x180040486  call    ?CreateD2DBrushFromXpsVisualBrush@TileBrushBuilder@xpsrdr@@QEAAXAEBV?$shared_ptr@UIXpsOMVisualBrush@@@std@@@Z; xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush(std::shared_ptr<IXpsOMVisualBrush> const &)
0x18004048b  cmp     [rdi+1E1h], r13b
0x180040492  jnz     short loc_1800404B0
0x180040494  lea     rcx, [rdi+0F0h]
0x18004049b  lea     rdx, [rbp+110h+var_130]
0x18004049f  call    ??A?$Cache@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@U?$Hash@UKeyBrush@xpsrdr@@@2@U?$Weight@UKeyBrush@xpsrdr@@U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@@2@@xpsrdr@@QEAAAEAU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEBUKeyBrush@1@@Z; xpsrdr::Cache<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,xpsrdr::Hash<xpsrdr::KeyBrush>,xpsrdr::Weight<xpsrdr::KeyBrush,std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>>>::operator[](xpsrdr::KeyBrush const &)
0x1800404a4  mov     rcx, rax
0x1800404a7  lea     rdx, [rbp+110h+var_170]
0x1800404ab  call    ??$?4U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAAAEAU01@AEBU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> const &)
0x1800404b0  lea     rdx, [rbp+110h+var_170]
0x1800404b4  mov     rcx, rsi
0x1800404b7  call    ??0?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@AEBU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> const &)
0x1800404bc  nop
0x1800404bd  lea     rcx, [rbp+110h+var_170]
0x1800404c1  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x1800404c6  nop
0x1800404c7  lea     rcx, [rsp+210h+var_1A8]
0x1800404cc  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800404d1  nop
0x1800404d2  lea     rcx, [rsp+210h+var_1A0+8]
0x1800404d7  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
  ... truncated ...
```
