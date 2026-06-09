# xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsImageBrush(std::shared_ptr<xpsrdr::Image> const &)

- ea: `0x180045164`
- end: `0x180045b10`
- name: `?CreateD2DBrushFromXpsImageBrush@TileBrushBuilder@xpsrdr@@QEAAXAEBV?$shared_ptr@UImage@xpsrdr@@@std@@@Z`
- size: `2476`
- prototype: `__int64 __fastcall(xpsrdr::TileBrushBuilder *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180040014`

## callees

- `0x180008830`
- `0x18000e4c4`
- `0x18000e934`
- `0x180011b2c`
- `0x1800122a8`
- `0x1800152b8`
- `0x1800184e8`
- `0x180023fac`
- `0x180033f38`
- `0x1800345b4`
- `0x180034cd0`
- `0x180037278`
- `0x180041548`
- `0x180044aa8`
- `0x180044d08`
- `0x180044f78`
- `0x180045164`
- `0x180046304`
- `0x1800463b0`
- `0x1800464a8`
- `0x18004661c`
- `0x1800466d4`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsImageBrush(xpsrdr::TileBrushBuilder *this, __int64 *a2)
{
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  int v7; // r9d
  __int64 EmptyBrushClipPair; // rax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, std::_Ref_count_base **); // rcx
  int v10; // edi
  int v11; // edx
  const char *v12; // r8
  int v13; // r9d
  __int64 v14; // rcx
  enum D3D_FEATURE_LEVEL v15; // edx
  unsigned int MaxD3DTextureDimension; // edi
  unsigned int v17; // r14d
  __int64 v18; // r15
  __int64 v19; // r8
  struct _GUID *v20; // rdx
  int BytesPerPixel; // r8d
  __int64 v22; // rdx
  float v23; // xmm1_4
  char v24; // di
  bool v25; // al
  const struct D2D_RECT_F *v26; // r8
  bool v27; // r12
  enum D2D1_EXTEND_MODE v28; // r14d
  enum D2D1_EXTEND_MODE v29; // r15d
  __int64 v30; // rax
  __int64 (__fastcall *v31)(std::_Ref_count_base *, _QWORD, enum D2D1_EXTEND_MODE *, D2D1_BRUSH_PROPERTIES *, _BYTE *); // r10
  __int64 v32; // rax
  bool v33; // zf
  enum D2D1_EXTEND_MODE v34; // eax
  int v35; // edi
  int v36; // edx
  const char *v37; // r8
  int v38; // r9d
  std::_Ref_count_base *v39; // rcx
  std::_Ref_count_base *v40; // rax
  std::_Ref_count_base *v41; // rcx
  __int64 v42; // rdx
  int v43; // edi
  int v44; // edx
  const char *v45; // r8
  int v46; // r9d
  __int64 v47; // rax
  int v48; // edi
  int v49; // edx
  const char *v50; // r8
  int v51; // r9d
  int v52; // eax
  int v53; // edx
  const char *v54; // r8
  int v55; // r9d
  int v56; // eax
  int v57; // edx
  const char *v58; // r8
  struct D2D_RECT_F *v59; // r9
  __int64 v60; // rax
  struct D2D_RECT_F *v61; // r9
  __int64 v62; // rax
  std::_Ref_count_base *v63; // rcx
  __int64 BitmapFromWicBitmap; // rax
  int v65; // edi
  int v66; // edx
  const char *v67; // r8
  int v68; // r9d
  __int64 v69; // rax
  int v70; // eax
  __int64 v71; // rax
  int v72; // edi
  int v73; // edx
  const char *v74; // r8
  int v75; // r9d
  char v76; // al
  __int64 v77; // rdx
  int v78; // edi
  int v79; // edx
  const char *v80; // r8
  int v81; // r9d
  __int64 v82; // rax
  D2D1_EXTEND_MODE v83[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v84[28]; // [rsp+48h] [rbp-B8h] BYREF
  struct D2D_RECT_F v85; // [rsp+68h] [rbp-98h] BYREF
  __int64 v86; // [rsp+78h] [rbp-88h]
  struct D2D_MATRIX_3X2_F v87; // [rsp+80h] [rbp-80h] BYREF
  float v88; // [rsp+98h] [rbp-68h]
  float v89; // [rsp+9Ch] [rbp-64h]
  std::_Ref_count_base *v90[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct D2D_RECT_F v91; // [rsp+B0h] [rbp-50h] BYREF
  enum D2D1_EXTEND_MODE v92[4]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v93[2]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v94[2]; // [rsp+E0h] [rbp-20h] BYREF
  std::_Ref_count_base **v95; // [rsp+F0h] [rbp-10h]
  D2D1_BRUSH_PROPERTIES v96; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v97[28]; // [rsp+120h] [rbp+20h] BYREF

  if ( !xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(this) )
  {
    v92[0] = 1065353216;
    v4 = (*(__int64 (__fastcall **)(_QWORD, enum D2D1_EXTEND_MODE *))(***((_QWORD ***)this + 5) + 40LL))(
           **((_QWORD **)this + 5),
           v92);
    if ( v4 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v4, v5, v6, v7);
    EmptyBrushClipPair = xpsrdr::CreateEmptyBrushClipPair(v97, *((_QWORD *)this + 4), v92);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
      this,
      EmptyBrushClipPair);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v97);
    return;
  }
  *(_OWORD *)v90 = 0;
  v92[0] = D2D1_EXTEND_MODE_CLAMP;
  v9 = **(__int64 (__fastcall *****)(_QWORD, GUID *, std::_Ref_count_base **))(*(_QWORD *)(*((_QWORD *)this + 4) + 560LL)
                                                                             + 8
                                                                             * ((*(_QWORD *)(*((_QWORD *)this + 4)
                                                                                           + 568LL)
                                                                               - 1LL)
                                                                              & (*(_QWORD *)(*((_QWORD *)this + 4)
                                                                                           + 576LL)
                                                                               - 1LL
                                                                               + *(_QWORD *)(*((_QWORD *)this + 4)
                                                                                           + 584LL))));
  v94[0] = 0;
  v94[1] = (std::_Ref_count_base *)v92;
  v95 = v90;
  v10 = (**v9)(v9, &GUID_e8f7fe7a_191c_466d_ad95_975678bda998, v94);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v94);
  if ( v92[0] < D2D1_EXTEND_MODE_CLAMP )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v92[0], v11, v12, v13);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  v14 = *a2;
  v88 = (float)((float)*(int *)(*a2 + 52) / *(float *)(*a2 + 60)) * 96.0;
  v89 = (float)((float)*(int *)(v14 + 56) / *(float *)(v14 + 64)) * 96.0;
  memset(&v87, 0, sizeof(v87));
  v91 = 0;
  xpsrdr::TileBrushBuilder::GetViewboxAndViewport(this, (struct D2D_RECT_F *)&v87, &v91);
  v83[0] = D2D1_EXTEND_MODE_CLAMP;
  v92[0] = D2D1_EXTEND_MODE_CLAMP;
  xpsrdr::TileBrushBuilder::GetExtendMode(this, v83, v92);
  MaxD3DTextureDimension = xpsrdr::GetMaxD3DTextureDimension(
                             (xpsrdr *)*(unsigned int *)(*((_QWORD *)this + 4) + 80LL),
                             v15);
  v17 = *(_DWORD *)(*a2 + 56);
  v18 = *(unsigned int *)(*a2 + 52);
  *(_OWORD *)v94 = *(_OWORD *)(v19 + 100);
  BytesPerPixel = xpsrdr::GetBytesPerPixel((xpsrdr *)v94, v20);
  if ( *(_DWORD *)(*a2 + 52) > MaxD3DTextureDimension
    || *(_DWORD *)(*a2 + 56) > MaxD3DTextureDimension
    || ((v22 = v18 * v17, v22 < 0)
      ? (v23 = (float)(v22 & 1 | (unsigned int)((unsigned __int64)v22 >> 1))
             + (float)(v22 & 1 | (unsigned int)((unsigned __int64)v22 >> 1)))
      : (v23 = (float)(int)v22),
        v24 = 0,
        (float)(v23 * (float)((float)BytesPerPixel * 0.00000095367432)) > 32.0) )
  {
    v24 = 1;
  }
  v25 = xpsrdr::TileBrushBuilder::WillBrushTile(this, &v91);
  v27 = v25;
  v28 = v92[0];
  v29 = v83[0];
  if ( v24 || v25 && !xpsrdr::RectEqual((xpsrdr *)v87.m[2], (const struct D2D_RECT_F *)&v87, v26) && (v29 || v28) )
  {
    *(_OWORD *)v94 = 0;
    if ( v24 )
    {
      *(_OWORD *)v93 = 0;
      v83[0] = D2D1_EXTEND_MODE_CLAMP;
      v47 = *(_QWORD *)v90[0];
      *(_QWORD *)v84 = 0;
      *(_QWORD *)&v84[8] = v83;
      *(_QWORD *)&v84[16] = v93;
      v48 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, GUID *, _BYTE *))(v47 + 504))(
              v90[0],
              &CLSID_D2D1BitmapSource,
              v84);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v84);
      if ( v83[0] < D2D1_EXTEND_MODE_CLAMP )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v83[0], v49, v50, v51);
      if ( v48 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v49, v50, v51);
      *(_QWORD *)v83 = *(_QWORD *)(*a2 + 32);
      v52 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD, D2D1_EXTEND_MODE *, int))(*(_QWORD *)v93[0] + 72LL))(
              v93[0],
              0,
              0,
              v83,
              8);
      if ( v52 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v52, v53, v54, v55);
      v83[0] = D2D1_EXTEND_MODE_CLAMP;
      v56 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64, _QWORD, D2D1_EXTEND_MODE *, int))(*(_QWORD *)v93[0] + 72LL))(
              v93[0],
              3,
              0,
              v83,
              4);
      if ( v56 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v56, v57, v58, (int)v59);
      v60 = *a2;
      v85.left = *(float *)(*a2 + 60) / 96.0;
      *(_QWORD *)&v85.top = 0;
      v85.bottom = *(float *)(v60 + 64) / 96.0;
      v86 = 0;
      xpsrdr::TransformRectF((xpsrdr *)&v87, &v85, &v87, v59);
      xpsrdr::TransformRectF((xpsrdr *)v87.m[2], &v85, (struct D2D_MATRIX_3X2_F *)v87.m[2], v61);
      v83[0] = D2D1_EXTEND_MODE_CLAMP;
      v62 = *(_QWORD *)v93[0];
      *(_QWORD *)v84 = 0;
      *(_QWORD *)&v84[8] = v83;
      *(_QWORD *)&v84[16] = v94;
      (*(void (__fastcall **)(std::_Ref_count_base *, _BYTE *))(v62 + 144))(v93[0], v84);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v84);
      v63 = v93[1];
    }
    else
    {
      v85 = 0;
      if ( *(_BYTE *)(*((_QWORD *)this + 4) + 481LL) )
      {
        BitmapFromWicBitmap = xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(this, v93, a2, v90);
        std::shared_ptr<_devicemodeW>::operator=(&v85, BitmapFromWicBitmap);
        if ( v93[1] )
          std::_Ref_count_base::_Decref(v93[1]);
      }
      else
      {
        v83[0] = D2D1_EXTEND_MODE_CLAMP;
        *(_QWORD *)v84 = 0;
        *(_QWORD *)&v84[8] = v83;
        *(_QWORD *)&v84[16] = &v85;
        v77 = *a2;
        *(_QWORD *)v92 = 0;
        v93[0] = 0;
        v93[1] = *(std::_Ref_count_base **)(v77 + 60);
        v78 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, std::_Ref_count_base **, _BYTE *))(*(_QWORD *)v90[0] + 40LL))(
                v90[0],
                *(_QWORD *)(v77 + 32),
                v93,
                v84);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v84);
        if ( v83[0] < D2D1_EXTEND_MODE_CLAMP )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v83[0], v79, v80, v81);
        if ( v78 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v78, v79, v80, v81);
      }
      v83[0] = D2D1_EXTEND_MODE_CLAMP;
      *(_QWORD *)v84 = 0;
      *(_QWORD *)&v84[8] = v83;
      *(_QWORD *)&v84[16] = v94;
      v65 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _BYTE *))&v85.left)(
              *(_QWORD *)&v85.left,
              &GUID_65019f75_8da2_497c_b32c_dfa34e48ede6,
              v84);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v84);
      if ( v83[0] < D2D1_EXTEND_MODE_CLAMP )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v83[0], v66, v67, v68);
      if ( v65 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v66, v67, v68);
      v63 = *(std::_Ref_count_base **)&v85.right;
    }
    if ( v63 )
      std::_Ref_count_base::_Decref(v63);
    memset(&v96, 0, sizeof(v96));
    *(_QWORD *)&v85.left = 0;
    v85.right = v87.m21 - v87.m11;
    v85.bottom = v87.m22 - v87.m12;
    xpsrdr::TileBrushBuilder::PopulateBrushProperties(this, &v85, &v91, &v96);
    v69 = *((_QWORD *)this + 4);
    if ( *(_DWORD *)(v69 + 96) || (v33 = *(_DWORD *)(v69 + 88) == 1, v70 = 1, v33) )
      v70 = 0;
    *(_DWORD *)&v84[16] = v29;
    *(_DWORD *)&v84[20] = v28;
    *(_DWORD *)&v84[24] = v70;
    *(_OWORD *)v84 = *(_OWORD *)&v87.m11;
    *(_OWORD *)v97 = *(_OWORD *)&v87.m11;
    *(_OWORD *)&v97[12] = *(_OWORD *)&v84[12];
    *(_OWORD *)v92 = 0;
    v83[0] = D2D1_EXTEND_MODE_CLAMP;
    v71 = *(_QWORD *)v90[0];
    *(_QWORD *)v84 = 0;
    *(_QWORD *)&v84[8] = v83;
    *(_QWORD *)&v84[16] = v92;
    v72 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base *, _BYTE *, D2D1_BRUSH_PROPERTIES *, _BYTE *))(v71 + 520))(
            v90[0],
            v94[0],
            v97,
            &v96,
            v84);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v84);
    if ( v83[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v83[0], v73, v74, v75);
    if ( v72 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v72, v73, v74, v75);
    std::shared_ptr<ID2D1Brush>::operator=<ID2D1ImageBrush,0>(this, v92);
    if ( *(_QWORD *)&v92[2] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v92[2]);
    v41 = v94[1];
  }
  else
  {
    memset(&v96, 0, sizeof(v96));
    xpsrdr::TileBrushBuilder::PopulateBrushProperties(this, (const struct D2D_RECT_F *)&v87, &v91, &v96);
    v85 = 0;
    if ( *(_BYTE *)(*((_QWORD *)this + 4) + 481LL) )
    {
      v30 = xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(this, v94, a2, v90);
      std::shared_ptr<_devicemodeW>::operator=(&v85, v30);
      if ( v94[1] )
        std::_Ref_count_base::_Decref(v94[1]);
    }
    else
    {
      v83[0] = D2D1_EXTEND_MODE_CLAMP;
      *(_QWORD *)v84 = 0;
      *(_QWORD *)&v84[8] = v83;
      *(_QWORD *)&v84[16] = &v85;
      v42 = *a2;
      *(_QWORD *)v92 = 0;
      v94[0] = 0;
      v94[1] = *(std::_Ref_count_base **)(v42 + 60);
      v43 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, std::_Ref_count_base **, _BYTE *))(*(_QWORD *)v90[0] + 40LL))(
              v90[0],
              *(_QWORD *)(v42 + 32),
              v94,
              v84);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v84);
      if ( v83[0] < D2D1_EXTEND_MODE_CLAMP )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v83[0], v44, v45, v46);
      if ( v43 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v43, v44, v45, v46);
    }
    *(_OWORD *)v93 = 0;
    v83[0] = D2D1_EXTEND_MODE_CLAMP;
    v31 = *(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, enum D2D1_EXTEND_MODE *, D2D1_BRUSH_PROPERTIES *, _BYTE *))(*(_QWORD *)v90[0] + 56LL);
    *(_QWORD *)v84 = 0;
    *(_QWORD *)&v84[8] = v83;
    *(_QWORD *)&v84[16] = v93;
    v32 = *((_QWORD *)this + 4);
    if ( *(_DWORD *)(v32 + 96) || (v33 = *(_DWORD *)(v32 + 88) == 1, v34 = D2D1_EXTEND_MODE_WRAP, v33) )
      v34 = D2D1_EXTEND_MODE_CLAMP;
    v92[0] = v29;
    v92[1] = v28;
    v92[2] = v34;
    v35 = v31(v90[0], *(_QWORD *)&v85.left, v92, &v96, v84);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v84);
    if ( v83[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v83[0], v36, v37, v38);
    if ( v35 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v35, v36, v37, v38);
    v39 = v93[1];
    if ( v93[1] )
    {
      _InterlockedIncrement((volatile signed __int32 *)v93[1] + 2);
      v39 = v93[1];
    }
    *(std::_Ref_count_base **)this = v93[0];
    v40 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v39;
    if ( v40 )
    {
      std::_Ref_count_base::_Decref(v40);
      v39 = v93[1];
    }
    if ( v39 )
      std::_Ref_count_base::_Decref(v39);
    v41 = *(std::_Ref_count_base **)&v85.right;
  }
  if ( v41 )
    std::_Ref_count_base::_Decref(v41);
  if ( (float)(v87.dx - v87.m11) > 0.050000001
    || (float)(v87.dy - v87.m12) > 0.050000001
    || (float)(v88 - v87.m21) < -0.050000001
    || (v76 = 0, (float)(v89 - v87.m22) < -0.050000001) )
  {
    v76 = 1;
  }
  *(_OWORD *)v94 = 0;
  if ( v27 && (v29 == D2D1_EXTEND_MODE_CLAMP || v28 == D2D1_EXTEND_MODE_CLAMP) )
  {
    LOBYTE(v38) = v28 == D2D1_EXTEND_MODE_CLAMP;
    LOBYTE(v37) = v29 == D2D1_EXTEND_MODE_CLAMP;
    goto LABEL_75;
  }
  if ( v76 && !v27 )
  {
    LOBYTE(v38) = 1;
    LOBYTE(v37) = 1;
LABEL_75:
    v82 = xpsrdr::TileBrushBuilder::CalculateClipRect(
            (int)this,
            (int)&v85,
            (int)v37,
            v38,
            (xpsrdr *)&v87,
            &v91,
            (__int64)v87.m[2]);
    std::shared_ptr<_devicemodeW>::operator=(v94, v82);
    if ( *(_QWORD *)&v85.right )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v85.right);
  }
  std::shared_ptr<ID2D1Brush>::operator=((char *)this + 16, v94);
  if ( v94[1] )
    std::_Ref_count_base::_Decref(v94[1]);
  if ( v90[1] )
    std::_Ref_count_base::_Decref(v90[1]);
}

```

## disassembly

```asm
0x180045164  mov     [rsp-8+arg_10], rbx
0x180045169  push    rbp
0x18004516a  push    rsi
0x18004516b  push    rdi
0x18004516c  push    r12
0x18004516e  push    r13
0x180045170  push    r14
0x180045172  push    r15
0x180045174  lea     rbp, [rsp-50h]
0x180045179  sub     rsp, 150h
0x180045180  mov     rax, cs:__security_cookie
0x180045187  xor     rax, rsp
0x18004518a  mov     [rbp+80h+var_40], rax
0x18004518e  mov     rsi, rdx
0x180045191  mov     rbx, rcx
0x180045194  call    ?ValidBoxAndPortSizes@TileBrushBuilder@xpsrdr@@AEAA_NXZ; xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(void)
0x180045199  xor     r13d, r13d
0x18004519c  test    al, al
0x18004519e  jnz     short loc_1800451F0
0x1800451a0  mov     [rbp+80h+var_C0], 3F800000h
0x1800451a7  mov     rax, [rbx+28h]
0x1800451ab  mov     rcx, [rax]
0x1800451ae  mov     rax, [rcx]
0x1800451b1  lea     rdx, [rbp+80h+var_C0]
0x1800451b5  mov     rax, [rax+28h]
0x1800451b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451be  test    eax, eax
0x1800451c0  js      loc_180045AAE
0x1800451c6  lea     r8, [rbp+80h+var_C0]
0x1800451ca  mov     rdx, [rbx+20h]
0x1800451ce  lea     rcx, [rbp+80h+var_60]
0x1800451d2  call    ?CreateEmptyBrushClipPair@xpsrdr@@YA?AU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEAURenderState@1@PEAM@Z; xpsrdr::CreateEmptyBrushClipPair(xpsrdr::RenderState &,float *)
0x1800451d7  mov     rdx, rax
0x1800451da  mov     rcx, rbx
0x1800451dd  call    ??$?4U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> &&)
0x1800451e2  lea     rcx, [rbp+80h+var_60]
0x1800451e6  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x1800451eb  jmp     loc_180045A6F
0x1800451f0  xorps   xmm0, xmm0
0x1800451f3  movdqu  xmmword ptr [rbp+80h+var_E0], xmm0
0x1800451f8  mov     [rbp+80h+var_C0], r13d
0x1800451fc  mov     rdx, [rbx+20h]
0x180045200  mov     rcx, [rdx+248h]
0x180045207  mov     rax, [rdx+240h]
0x18004520e  dec     rax
0x180045211  add     rcx, rax
0x180045214  mov     rax, [rdx+238h]
0x18004521b  dec     rax
0x18004521e  and     rcx, rax
0x180045221  mov     rax, [rdx+230h]
0x180045228  mov     rcx, [rax+rcx*8]
0x18004522c  mov     rcx, [rcx]
0x18004522f  mov     [rbp+80h+var_A0], r13
0x180045233  lea     rax, [rbp+80h+var_C0]
0x180045237  mov     [rbp+80h+var_A0+8], rax
0x18004523b  lea     rax, [rbp+80h+var_E0]
0x18004523f  mov     [rbp+80h+var_90], rax
0x180045243  mov     rax, [rcx]
0x180045246  lea     r8, [rbp+80h+var_A0]
0x18004524a  lea     rdx, _GUID_e8f7fe7a_191c_466d_ad95_975678bda998
0x180045251  mov     rax, [rax]
0x180045254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045259  mov     edi, eax
0x18004525b  lea     rcx, [rbp+80h+var_A0]
0x18004525f  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180045264  mov     ecx, [rbp+80h+var_C0]; this
0x180045267  test    ecx, ecx
0x180045269  js      loc_180045AB6
0x18004526f  test    edi, edi
0x180045271  js      loc_180045ABC
0x180045277  mov     qword ptr [rbp+80h+var_100+10h], 0
0x18004527f  mov     rcx, [rsi]
0x180045282  mov     eax, [rcx+34h]
0x180045285  xorps   xmm0, xmm0
0x180045288  cvtsi2ss xmm0, rax
0x18004528d  divss   xmm0, dword ptr [rcx+3Ch]
0x180045292  mulss   xmm0, cs:__real@42c00000
0x18004529a  movss   [rbp+80h+var_E8], xmm0
0x18004529f  mov     eax, [rcx+38h]
0x1800452a2  xorps   xmm0, xmm0
0x1800452a5  cvtsi2ss xmm0, rax
0x1800452aa  divss   xmm0, dword ptr [rcx+40h]
0x1800452af  mulss   xmm0, cs:__real@42c00000
0x1800452b7  movss   [rbp+80h+var_E4], xmm0
0x1800452bc  xorps   xmm0, xmm0
0x1800452bf  movups  xmmword ptr [rbp+80h+var_100], xmm0
0x1800452c3  xorps   xmm1, xmm1
0x1800452c6  movups  xmmword ptr [rbp+80h+var_D0.left], xmm1
0x1800452ca  lea     r8, [rbp+80h+var_D0]; struct D2D_RECT_F *
0x1800452ce  lea     rdx, [rbp+80h+var_100]; struct D2D_RECT_F *
0x1800452d2  mov     rcx, rbx; this
0x1800452d5  call    ?GetViewboxAndViewport@TileBrushBuilder@xpsrdr@@AEAAXAEAUD2D_RECT_F@@0@Z; xpsrdr::TileBrushBuilder::GetViewboxAndViewport(D2D_RECT_F &,D2D_RECT_F &)
0x1800452da  mov     [rsp+180h+var_140], r13d
0x1800452df  mov     [rbp+80h+var_C0], r13d
0x1800452e3  lea     r8, [rbp+80h+var_C0]; enum D2D1_EXTEND_MODE *
0x1800452e7  lea     rdx, [rsp+180h+var_140]; enum D2D1_EXTEND_MODE *
0x1800452ec  mov     rcx, rbx; this
0x1800452ef  call    ?GetExtendMode@TileBrushBuilder@xpsrdr@@AEAAXAEAW4D2D1_EXTEND_MODE@@0@Z; xpsrdr::TileBrushBuilder::GetExtendMode(D2D1_EXTEND_MODE &,D2D1_EXTEND_MODE &)
0x1800452f4  mov     r8, [rbx+20h]
0x1800452f8  mov     ecx, [r8+50h]; this
0x1800452fc  call    ?GetMaxD3DTextureDimension@xpsrdr@@YAIW4D3D_FEATURE_LEVEL@@@Z; xpsrdr::GetMaxD3DTextureDimension(D3D_FEATURE_LEVEL)
0x180045301  mov     edi, eax
0x180045303  mov     rcx, [rsi]
0x180045306  mov     r14d, [rcx+38h]
0x18004530a  mov     r15d, [rcx+34h]
0x18004530e  movups  xmm0, xmmword ptr [r8+64h]
0x180045313  movdqu  xmmword ptr [rbp+80h+var_A0], xmm0
0x180045318  lea     rcx, [rbp+80h+var_A0]; this
0x18004531c  call    ?GetBytesPerPixel@xpsrdr@@YAFU_GUID@@@Z; xpsrdr::GetBytesPerPixel(_GUID)
0x180045321  movsx   r8d, ax
0x180045325  mov     rcx, [rsi]
0x180045328  cmp     [rcx+34h], edi
0x18004532b  ja      short loc_18004537D
0x18004532d  cmp     [rcx+38h], edi
0x180045330  ja      short loc_18004537D
0x180045332  mov     edx, r14d
0x180045335  imul    rdx, r15
0x180045339  xorps   xmm1, xmm1
0x18004533c  test    rdx, rdx
0x18004533f  js      short loc_180045348
0x180045341  cvtsi2ss xmm1, rdx
0x180045346  jmp     short loc_18004535D
0x180045348  mov     rax, rdx
0x18004534b  shr     rax, 1
0x18004534e  and     edx, 1
0x180045351  or      rax, rdx
0x180045354  cvtsi2ss xmm1, rax
0x180045359  addss   xmm1, xmm1
0x18004535d  movd    xmm0, r8d
0x180045362  cvtdq2ps xmm0, xmm0
0x180045365  mulss   xmm0, cs:__real@35800000
0x18004536d  mulss   xmm1, xmm0
0x180045371  comiss  xmm1, cs:__real@42000000
0x180045378  mov     dil, r13b
0x18004537b  jbe     short loc_180045380
0x18004537d  mov     dil, 1
0x180045380  lea     rdx, [rbp+80h+var_D0]; struct D2D_RECT_F *
0x180045384  mov     rcx, rbx; this
0x180045387  call    ?WillBrushTile@TileBrushBuilder@xpsrdr@@AEAA_NAEBUD2D_RECT_F@@@Z; xpsrdr::TileBrushBuilder::WillBrushTile(D2D_RECT_F const &)
0x18004538c  mov     r12b, al
0x18004538f  mov     r14d, [rbp+80h+var_C0]
0x180045393  mov     r15d, [rsp+180h+var_140]
0x180045398  test    dil, dil
0x18004539b  jnz     loc_180045591
0x1800453a1  test    al, al
0x1800453a3  jz      short loc_1800453C8
0x1800453a5  lea     rdx, [rbp+80h+var_100]; struct D2D_RECT_F *
0x1800453a9  lea     rcx, [rbp+80h+var_100+10h]; this
0x1800453ad  call    ?RectEqual@xpsrdr@@YA_NAEBUD2D_RECT_F@@0@Z; xpsrdr::RectEqual(D2D_RECT_F const &,D2D_RECT_F const &)
0x1800453b2  test    al, al
0x1800453b4  jnz     short loc_1800453C8
0x1800453b6  test    r15d, r15d
0x1800453b9  jnz     loc_180045591
0x1800453bf  test    r14d, r14d
0x1800453c2  jnz     loc_180045591
0x1800453c8  xorps   xmm0, xmm0
0x1800453cb  movups  xmmword ptr [rbp+80h+var_80.opacity], xmm0
0x1800453cf  movups  xmmword ptr [rbp+80h+var_80.transform+8], xmm0
0x1800453d3  lea     r9, [rbp+80h+var_80]; struct D2D1_BRUSH_PROPERTIES *
0x1800453d7  lea     r8, [rbp+80h+var_D0]; struct D2D_RECT_F *
0x1800453db  lea     rdx, [rbp+80h+var_100]; struct D2D_RECT_F *
0x1800453df  mov     rcx, rbx; this
0x1800453e2  call    ?PopulateBrushProperties@TileBrushBuilder@xpsrdr@@AEAAXAEBUD2D_RECT_F@@0AEAUD2D1_BRUSH_PROPERTIES@@@Z; xpsrdr::TileBrushBuilder::PopulateBrushProperties(D2D_RECT_F const &,D2D_RECT_F const &,D2D1_BRUSH_PROPERTIES &)
0x1800453e7  xorps   xmm0, xmm0
0x1800453ea  movdqu  xmmword ptr [rsp+180h+var_118.left], xmm0
0x1800453f0  mov     rax, [rbx+20h]
0x1800453f4  cmp     [rax+1E1h], r13b
0x1800453fb  jz      loc_180045507
0x180045401  lea     r9, [rbp+80h+var_E0]
0x180045405  mov     r8, rsi
0x180045408  lea     rdx, [rbp+80h+var_A0]
0x18004540c  mov     rcx, rbx
0x18004540f  call    ?CreateBitmapFromWicBitmap@TileBrushBuilder@xpsrdr@@AEAA?AV?$shared_ptr@UID2D1Bitmap@@@std@@AEBV?$shared_ptr@UImage@xpsrdr@@@4@AEAV?$shared_ptr@UID2D1DeviceContext@@@4@@Z; xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(std::shared_ptr<xpsrdr::Image> const &,std::shared_ptr<ID2D1DeviceContext> &)
0x180045414  mov     rdx, rax
0x180045417  lea     rcx, [rsp+180h+var_118]
0x18004541c  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x180045421  mov     rcx, [rbp+80h+var_A0+8]; this
0x180045425  test    rcx, rcx
0x180045428  jz      short loc_18004542F
0x18004542a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004542f  xorps   xmm0, xmm0
0x180045432  movdqu  xmmword ptr [rbp+80h+var_B0], xmm0
0x180045437  mov     [rsp+180h+var_140], r13d
0x18004543c  mov     rcx, [rbp+80h+var_E0]
0x180045440  mov     rax, [rcx]
0x180045443  mov     r10, [rax+38h]
0x180045447  mov     qword ptr [rsp+180h+var_138], r13
0x18004544c  lea     rax, [rsp+180h+var_140]
0x180045451  mov     qword ptr [rsp+180h+var_138+8], rax
0x180045456  lea     rax, [rbp+80h+var_B0]
0x18004545a  mov     [rsp+180h+var_128], rax
0x18004545f  mov     rax, [rbx+20h]
0x180045463  cmp     [rax+60h], r13d
0x180045467  jnz     short loc_180045474
0x180045469  cmp     dword ptr [rax+58h], 1
0x18004546d  mov     eax, 1
0x180045472  jnz     short loc_180045477
0x180045474  mov     eax, r13d
0x180045477  mov     [rbp+80h+var_C0], r15d
0x18004547b  mov     [rbp+80h+var_C0+4], r14d
0x18004547f  mov     [rbp+80h+var_C0+8], eax
0x180045482  lea     rax, [rsp+180h+var_138]
0x180045487  mov     [rsp+180h+var_160], rax
0x18004548c  lea     r9, [rbp+80h+var_80]
0x180045490  lea     r8, [rbp+80h+var_C0]
0x180045494  mov     rdx, qword ptr [rsp+180h+var_118.left]
0x180045499  mov     rax, r10
0x18004549c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454a1  mov     edi, eax
0x1800454a3  lea     rcx, [rsp+180h+var_138]
0x1800454a8  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800454ad  mov     ecx, [rsp+180h+var_140]; this
0x1800454b1  test    ecx, ecx
0x1800454b3  js      loc_180045AC4
0x1800454b9  test    edi, edi
0x1800454bb  js      loc_180045AD0
0x1800454c1  mov     rcx, [rbp+80h+var_B0+8]
0x1800454c5  test    rcx, rcx
0x1800454c8  jz      short loc_1800454D2
0x1800454ca  lock inc dword ptr [rcx+8]
0x1800454ce  mov     rcx, [rbp+80h+var_B0+8]
0x1800454d2  mov     rax, [rbp+80h+var_B0]
0x1800454d6  mov     [rbx], rax
0x1800454d9  mov     rax, [rbx+8]
0x1800454dd  mov     [rbx+8], rcx
0x1800454e1  test    rax, rax
0x1800454e4  jz      short loc_1800454F2
0x1800454e6  mov     rcx, rax; this
0x1800454e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800454ee  mov     rcx, [rbp+80h+var_B0+8]; this
0x1800454f2  test    rcx, rcx
0x1800454f5  jz      short loc_1800454FD
0x1800454f7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800454fc  nop
0x1800454fd  mov     rcx, qword ptr [rsp+180h+var_118.right]
0x180045502  jmp     loc_1800458DB
0x180045507  mov     [rsp+180h+var_140], r13d
0x18004550c  mov     rcx, [rbp+80h+var_E0]
0x180045510  mov     qword ptr [rsp+180h+var_138], r13
0x180045515  lea     rax, [rsp+180h+var_140]
0x18004551a  mov     qword ptr [rsp+180h+var_138+8], rax
0x18004551f  lea     rax, [rsp+180h+var_118]
0x180045524  mov     [rsp+180h+var_128], rax
0x180045529  mov     rdx, [rsi]
0x18004552c  mov     qword ptr [rbp+80h+var_C0], r13
0x180045530  mov     rax, r13
0x180045533  mov     [rbp+80h+var_A0], rax
0x180045537  movss   xmm0, dword ptr [rdx+3Ch]
0x18004553c  movss   dword ptr [rbp+80h+var_A0+8], xmm0
0x180045541  movss   xmm1, dword ptr [rdx+40h]
0x180045546  movss   dword ptr [rbp+80h+var_A0+0Ch], xmm1
0x18004554b  movups  xmm0, xmmword ptr [rbp+80h+var_A0]
0x18004554f  movups  xmmword ptr [rbp+80h+var_A0], xmm0
0x180045553  mov     rax, [rcx]
0x180045556  lea     r9, [rsp+180h+var_138]
0x18004555b  lea     r8, [rbp+80h+var_A0]
0x18004555f  mov     rdx, [rdx+20h]
0x180045563  mov     rax, [rax+28h]
0x180045567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004556c  mov     edi, eax
0x18004556e  lea     rcx, [rsp+180h+var_138]
0x180045573  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180045578  mov     ecx, [rsp+180h+var_140]; this
0x18004557c  test    ecx, ecx
0x18004557e  js      loc_180045ACA
0x180045584  test    edi, edi
0x180045586  js      loc_180045A9E
0x18004558c  jmp     loc_18004542F
0x180045591  xorps   xmm0, xmm0
0x180045594  movdqu  xmmword ptr [rbp+80h+var_A0], xmm0
0x180045599  test    dil, dil
0x18004559c  jz      loc_180045713
0x1800455a2  movdqu  xmmword ptr [rbp+80h+var_B0], xmm0
0x1800455a7  mov     [rsp+180h+var_140], r13d
0x1800455ac  mov     rcx, [rbp+80h+var_E0]
0x1800455b0  mov     rax, [rcx]
0x1800455b3  mov     qword ptr [rsp+180h+var_138], r13
0x1800455b8  lea     rdx, [rsp+180h+var_140]
0x1800455bd  mov     qword ptr [rsp+180h+var_138+8], rdx
0x1800455c2  lea     rdx, [rbp+80h+var_B0]
0x1800455c6  mov     [rsp+180h+var_128], rdx
0x1800455cb  lea     r8, [rsp+180h+var_138]
0x1800455d0  lea     rdx, CLSID_D2D1BitmapSource
0x1800455d7  mov     rax, [rax+1F8h]
0x1800455de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455e3  mov     edi, eax
0x1800455e5  lea     rcx, [rsp+180h+var_138]
0x1800455ea  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800455ef  mov     ecx, [rsp+180h+var_140]; this
0x1800455f3  test    ecx, ecx
0x1800455f5  js      loc_180045AD8
0x1800455fb  test    edi, edi
0x1800455fd  js      loc_180045ADE
0x180045603  mov     rcx, [rbp+80h+var_B0]
0x180045607  mov     rax, [rsi]
0x18004560a  mov     rdx, [rax+20h]
0x18004560e  mov     qword ptr [rsp+180h+var_140], rdx
0x180045613  mov     rax, [rcx]
0x180045616  mov     dword ptr [rsp+180h+var_160], 8
0x18004561e  lea     r9, [rsp+180h+var_140]
  ... truncated ...
```
