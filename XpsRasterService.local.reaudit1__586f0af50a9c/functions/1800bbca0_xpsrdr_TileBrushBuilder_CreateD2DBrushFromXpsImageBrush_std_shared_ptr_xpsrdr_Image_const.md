# xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsImageBrush(std::shared_ptr<xpsrdr::Image> const &)

- ea: `0x1800bbca0`
- end: `0x1800bc693`
- name: `?CreateD2DBrushFromXpsImageBrush@TileBrushBuilder@xpsrdr@@QEAAXAEBV?$shared_ptr@UImage@xpsrdr@@@std@@@Z`
- size: `2547`
- prototype: `__int64 __fastcall(xpsrdr::TileBrushBuilder *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b3ecc`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a86b4`
- `0x1800aa83c`
- `0x1800aae8c`
- `0x1800ab7ac`
- `0x1800adcc0`
- `0x1800add10`
- `0x1800b20e8`
- `0x1800b5360`
- `0x1800bb5cc`
- `0x1800bb628`
- `0x1800bb854`
- `0x1800bbabc`
- `0x1800bbca0`
- `0x1800bcebc`
- `0x1800bcf68`
- `0x1800bd060`
- `0x1800bd1d0`
- `0x1800bd288`
- `0x1800c3010`

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
  float v15; // xmm7_4
  float v16; // xmm6_4
  unsigned int MaxD3DTextureDimension; // edi
  unsigned int v18; // r14d
  __int64 v19; // r15
  __int64 v20; // rdx
  int BytesPerPixel; // r8d
  __int64 v22; // rdx
  float v23; // xmm1_4
  char v24; // di
  bool v25; // al
  bool v26; // r12
  enum D2D1_EXTEND_MODE v27; // r14d
  enum D2D1_EXTEND_MODE v28; // r15d
  __int64 v29; // rax
  __int64 (__fastcall *v30)(_QWORD, _QWORD, enum D2D1_EXTEND_MODE *, D2D1_BRUSH_PROPERTIES *, _BYTE *); // r10
  __int64 v31; // rax
  bool v32; // zf
  enum D2D1_EXTEND_MODE v33; // eax
  int v34; // edi
  int v35; // edx
  const char *v36; // r8
  int v37; // r9d
  std::_Ref_count_base *v38; // rcx
  std::_Ref_count_base *v39; // rax
  std::_Ref_count_base *v40; // rcx
  __int64 v41; // rdx
  int v42; // edi
  int v43; // edx
  const char *v44; // r8
  int v45; // r9d
  __int64 v46; // rax
  int v47; // edi
  int v48; // edx
  const char *v49; // r8
  int v50; // r9d
  int v51; // eax
  int v52; // edx
  const char *v53; // r8
  int v54; // r9d
  int v55; // eax
  int v56; // edx
  const char *v57; // r8
  struct D2D_RECT_F *v58; // r9
  __int64 v59; // rax
  struct D2D_RECT_F *v60; // r9
  __int64 v61; // rax
  __int64 BitmapFromWicBitmap; // rax
  int v63; // edi
  int v64; // edx
  const char *v65; // r8
  int v66; // r9d
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // rax
  int v70; // edi
  int v71; // edx
  const char *v72; // r8
  int v73; // r9d
  char v74; // al
  __int64 v75; // rdx
  int v76; // edi
  int v77; // edx
  const char *v78; // r8
  int v79; // r9d
  __int64 v80; // rax
  D2D1_EXTEND_MODE v81[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v82[28]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v83[32]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v84; // [rsp+88h] [rbp-78h]
  _BYTE v85[32]; // [rsp+90h] [rbp-70h] BYREF
  struct D2D_RECT_F v86; // [rsp+B0h] [rbp-50h] BYREF
  enum D2D1_EXTEND_MODE v87[4]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v88[2]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v89[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v90; // [rsp+F0h] [rbp-10h]
  D2D1_BRUSH_PROPERTIES v91; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v92[28]; // [rsp+120h] [rbp+20h] BYREF

  if ( !xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(this) )
  {
    v87[0] = 1065353216;
    v4 = (*(__int64 (__fastcall **)(_QWORD, enum D2D1_EXTEND_MODE *))(***((_QWORD ***)this + 5) + 40LL))(
           **((_QWORD **)this + 5),
           v87);
    if ( v4 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v4, v5, v6, v7);
    EmptyBrushClipPair = xpsrdr::CreateEmptyBrushClipPair(v92, *((_QWORD *)this + 4), v87);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
      this,
      EmptyBrushClipPair);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(v92);
    return;
  }
  *(_OWORD *)&v85[16] = 0;
  v87[0] = D2D1_EXTEND_MODE_CLAMP;
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
  v89[0] = 0;
  v89[1] = (std::_Ref_count_base *)v87;
  v90 = &v85[16];
  v10 = (**v9)(v9, &GUID_e8f7fe7a_191c_466d_ad95_975678bda998, v89);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v89);
  if ( v87[0] < D2D1_EXTEND_MODE_CLAMP )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v87[0], v11, v12, v13);
  if ( v10 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v10, v11, v12, v13);
  *(_QWORD *)v85 = 0;
  v14 = *a2;
  v15 = (float)((float)*(int *)(*a2 + 52) / *(float *)(*a2 + 60)) * 96.0;
  *(float *)&v85[8] = v15;
  v16 = (float)((float)*(int *)(v14 + 56) / *(float *)(v14 + 64)) * 96.0;
  *(float *)&v85[12] = v16;
  *(_OWORD *)v83 = 0;
  v86 = 0;
  xpsrdr::TileBrushBuilder::GetViewboxAndViewport(this, (struct D2D_RECT_F *)v83, &v86);
  v81[0] = D2D1_EXTEND_MODE_CLAMP;
  v87[0] = D2D1_EXTEND_MODE_CLAMP;
  xpsrdr::TileBrushBuilder::GetExtendMode(this, v81, v87);
  MaxD3DTextureDimension = xpsrdr::GetMaxD3DTextureDimension(
                             (xpsrdr *)*(unsigned int *)(*((_QWORD *)this + 4) + 80LL),
                             (enum D3D_FEATURE_LEVEL)*((_QWORD *)this + 4));
  v18 = *(_DWORD *)(*a2 + 56);
  v19 = *(unsigned int *)(*a2 + 52);
  *(_OWORD *)v89 = *(_OWORD *)(v20 + 100);
  BytesPerPixel = xpsrdr::GetBytesPerPixel((xpsrdr *)v89, (struct _GUID *)v20);
  if ( *(_DWORD *)(*a2 + 52) > MaxD3DTextureDimension
    || *(_DWORD *)(*a2 + 56) > MaxD3DTextureDimension
    || ((v22 = v19 * v18, v22 < 0)
      ? (v23 = (float)(v22 & 1 | (unsigned int)((unsigned __int64)v22 >> 1))
             + (float)(v22 & 1 | (unsigned int)((unsigned __int64)v22 >> 1)))
      : (v23 = (float)(int)v22),
        v24 = 0,
        (float)(v23 * (float)((float)BytesPerPixel * 0.00000095367432)) > 32.0) )
  {
    v24 = 1;
  }
  v25 = xpsrdr::TileBrushBuilder::WillBrushTile(this, &v86);
  v26 = v25;
  v27 = v87[0];
  v28 = v81[0];
  if ( v24
    || v25
    && (*(float *)v83 != 0.0 || *(float *)&v83[4] != 0.0 || v15 != *(float *)&v83[8] || v16 != *(float *)&v83[12])
    && (v81[0] || v87[0]) )
  {
    *(_OWORD *)v89 = 0;
    if ( v24 )
    {
      *(_OWORD *)v88 = 0;
      v81[0] = D2D1_EXTEND_MODE_CLAMP;
      v46 = **(_QWORD **)&v85[16];
      *(_QWORD *)v82 = 0;
      *(_QWORD *)&v82[8] = v81;
      *(_QWORD *)&v82[16] = v88;
      v47 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _BYTE *))(v46 + 504))(
              *(_QWORD *)&v85[16],
              &CLSID_D2D1BitmapSource,
              v82);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v82);
      if ( v81[0] < D2D1_EXTEND_MODE_CLAMP )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v81[0], v48, v49, v50);
      if ( v47 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v47, v48, v49, v50);
      *(_QWORD *)v81 = *(_QWORD *)(*a2 + 32);
      v51 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD, D2D1_EXTEND_MODE *, int))(*(_QWORD *)v88[0] + 72LL))(
              v88[0],
              0,
              0,
              v81,
              8);
      if ( v51 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v51, v52, v53, v54);
      v81[0] = D2D1_EXTEND_MODE_CLAMP;
      v55 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64, _QWORD, D2D1_EXTEND_MODE *, int))(*(_QWORD *)v88[0] + 72LL))(
              v88[0],
              3,
              0,
              v81,
              4);
      if ( v55 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v55, v56, v57, (int)v58);
      v59 = *a2;
      *(float *)&v83[16] = *(float *)(*a2 + 60) / 96.0;
      *(_QWORD *)&v83[20] = 0;
      *(float *)&v83[28] = *(float *)(v59 + 64) / 96.0;
      v84 = 0;
      xpsrdr::TransformRectF(
        (xpsrdr *)v83,
        (const struct D2D_RECT_F *)&v83[16],
        (const struct D2D_MATRIX_3X2_F *)v83,
        v58);
      xpsrdr::TransformRectF(
        (xpsrdr *)v85,
        (const struct D2D_RECT_F *)&v83[16],
        (const struct D2D_MATRIX_3X2_F *)v85,
        v60);
      v81[0] = D2D1_EXTEND_MODE_CLAMP;
      v61 = *(_QWORD *)v88[0];
      *(_QWORD *)v82 = 0;
      *(_QWORD *)&v82[8] = v81;
      *(_QWORD *)&v82[16] = v89;
      (*(void (__fastcall **)(std::_Ref_count_base *, _BYTE *))(v61 + 144))(v88[0], v82);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v82);
      if ( v88[1] )
        std::_Ref_count_base::_Decref(v88[1]);
      v16 = *(float *)&v85[12];
      v15 = *(float *)&v85[8];
    }
    else
    {
      *(_OWORD *)&v83[16] = 0;
      if ( *(_BYTE *)(*((_QWORD *)this + 4) + 481LL) )
      {
        BitmapFromWicBitmap = xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(this, v88, a2, &v85[16]);
        std::shared_ptr<ID2D1Bitmap>::operator=(&v83[16], BitmapFromWicBitmap);
        if ( v88[1] )
          std::_Ref_count_base::_Decref(v88[1]);
      }
      else
      {
        v81[0] = D2D1_EXTEND_MODE_CLAMP;
        *(_QWORD *)v82 = 0;
        *(_QWORD *)&v82[8] = v81;
        *(_QWORD *)&v82[16] = &v83[16];
        v75 = *a2;
        *(_QWORD *)v87 = 0;
        v88[0] = 0;
        v88[1] = *(std::_Ref_count_base **)(v75 + 60);
        v76 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, std::_Ref_count_base **, _BYTE *))(**(_QWORD **)&v85[16] + 40LL))(
                *(_QWORD *)&v85[16],
                *(_QWORD *)(v75 + 32),
                v88,
                v82);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v82);
        if ( v81[0] < D2D1_EXTEND_MODE_CLAMP )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v81[0], v77, v78, v79);
        if ( v76 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v76, v77, v78, v79);
      }
      v81[0] = D2D1_EXTEND_MODE_CLAMP;
      *(_QWORD *)v82 = 0;
      *(_QWORD *)&v82[8] = v81;
      *(_QWORD *)&v82[16] = v89;
      v63 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _BYTE *))&v83[16])(
              *(_QWORD *)&v83[16],
              &GUID_65019f75_8da2_497c_b32c_dfa34e48ede6,
              v82);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v82);
      if ( v81[0] < D2D1_EXTEND_MODE_CLAMP )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v81[0], v64, v65, v66);
      if ( v63 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v63, v64, v65, v66);
      if ( *(_QWORD *)&v83[24] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v83[24]);
    }
    memset(&v91, 0, sizeof(v91));
    *(_QWORD *)&v83[16] = 0;
    *(float *)&v83[24] = *(float *)&v83[8] - *(float *)v83;
    *(float *)&v83[28] = *(float *)&v83[12] - *(float *)&v83[4];
    xpsrdr::TileBrushBuilder::PopulateBrushProperties(this, (const struct D2D_RECT_F *)&v83[16], &v86, &v91);
    v67 = *((_QWORD *)this + 4);
    if ( *(_DWORD *)(v67 + 96) || (v32 = *(_DWORD *)(v67 + 88) == 1, v68 = 1, v32) )
      v68 = 0;
    *(_DWORD *)&v82[16] = v28;
    *(_DWORD *)&v82[20] = v27;
    *(_DWORD *)&v82[24] = v68;
    *(_OWORD *)v82 = *(_OWORD *)v83;
    *(_OWORD *)v92 = *(_OWORD *)v83;
    *(_OWORD *)&v92[12] = *(_OWORD *)&v82[12];
    *(_OWORD *)v87 = 0;
    v81[0] = D2D1_EXTEND_MODE_CLAMP;
    v69 = **(_QWORD **)&v85[16];
    *(_QWORD *)v82 = 0;
    *(_QWORD *)&v82[8] = v81;
    *(_QWORD *)&v82[16] = v87;
    v70 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base *, _BYTE *, D2D1_BRUSH_PROPERTIES *, _BYTE *))(v69 + 520))(
            *(_QWORD *)&v85[16],
            v89[0],
            v92,
            &v91,
            v82);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v82);
    if ( v81[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v81[0], v71, v72, v73);
    if ( v70 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v70, v71, v72, v73);
    std::shared_ptr<ID2D1Brush>::operator=<ID2D1ImageBrush,0>(this, v87);
    if ( *(_QWORD *)&v87[2] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v87[2]);
    v40 = v89[1];
  }
  else
  {
    memset(&v91, 0, sizeof(v91));
    xpsrdr::TileBrushBuilder::PopulateBrushProperties(this, (const struct D2D_RECT_F *)v83, &v86, &v91);
    *(_OWORD *)&v83[16] = 0;
    if ( *(_BYTE *)(*((_QWORD *)this + 4) + 481LL) )
    {
      v29 = xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(this, v89, a2, &v85[16]);
      std::shared_ptr<ID2D1Bitmap>::operator=(&v83[16], v29);
      if ( v89[1] )
        std::_Ref_count_base::_Decref(v89[1]);
    }
    else
    {
      v81[0] = D2D1_EXTEND_MODE_CLAMP;
      *(_QWORD *)v82 = 0;
      *(_QWORD *)&v82[8] = v81;
      *(_QWORD *)&v82[16] = &v83[16];
      v41 = *a2;
      *(_QWORD *)v87 = 0;
      v89[0] = 0;
      v89[1] = *(std::_Ref_count_base **)(v41 + 60);
      v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, std::_Ref_count_base **, _BYTE *))(**(_QWORD **)&v85[16] + 40LL))(
              *(_QWORD *)&v85[16],
              *(_QWORD *)(v41 + 32),
              v89,
              v82);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v82);
      if ( v81[0] < D2D1_EXTEND_MODE_CLAMP )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v81[0], v43, v44, v45);
      if ( v42 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v42, v43, v44, v45);
    }
    *(_OWORD *)v88 = 0;
    v81[0] = D2D1_EXTEND_MODE_CLAMP;
    v30 = *(__int64 (__fastcall **)(_QWORD, _QWORD, enum D2D1_EXTEND_MODE *, D2D1_BRUSH_PROPERTIES *, _BYTE *))(**(_QWORD **)&v85[16] + 56LL);
    *(_QWORD *)v82 = 0;
    *(_QWORD *)&v82[8] = v81;
    *(_QWORD *)&v82[16] = v88;
    v31 = *((_QWORD *)this + 4);
    if ( *(_DWORD *)(v31 + 96) || (v32 = *(_DWORD *)(v31 + 88) == 1, v33 = D2D1_EXTEND_MODE_WRAP, v32) )
      v33 = D2D1_EXTEND_MODE_CLAMP;
    v87[0] = v28;
    v87[1] = v27;
    v87[2] = v33;
    v34 = v30(*(_QWORD *)&v85[16], *(_QWORD *)&v83[16], v87, &v91, v82);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v82);
    if ( v81[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v81[0], v35, v36, v37);
    if ( v34 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v34, v35, v36, v37);
    v38 = v88[1];
    if ( v88[1] )
    {
      _InterlockedIncrement((volatile signed __int32 *)v88[1] + 2);
      v38 = v88[1];
    }
    *(std::_Ref_count_base **)this = v88[0];
    v39 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v38;
    if ( v39 )
    {
      std::_Ref_count_base::_Decref(v39);
      v38 = v88[1];
    }
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    v40 = *(std::_Ref_count_base **)&v83[24];
  }
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  if ( (float)(*(float *)v85 - *(float *)v83) > 0.050000001
    || (float)(*(float *)&v85[4] - *(float *)&v83[4]) > 0.050000001
    || (float)(v15 - *(float *)&v83[8]) < -0.050000001
    || (v74 = 0, (float)(v16 - *(float *)&v83[12]) < -0.050000001) )
  {
    v74 = 1;
  }
  *(_OWORD *)v89 = 0;
  if ( v26 && (v28 == D2D1_EXTEND_MODE_CLAMP || v27 == D2D1_EXTEND_MODE_CLAMP) )
  {
    LOBYTE(v37) = v27 == D2D1_EXTEND_MODE_CLAMP;
    LOBYTE(v36) = v28 == D2D1_EXTEND_MODE_CLAMP;
    goto LABEL_79;
  }
  if ( v74 && !v26 )
  {
    LOBYTE(v37) = 1;
    LOBYTE(v36) = 1;
LABEL_79:
    v80 = xpsrdr::TileBrushBuilder::CalculateClipRect(
            (int)this,
            (int)&v83[16],
            (int)v36,
            v37,
            (xpsrdr *)v83,
            &v86,
            (__int64)v85);
    std::shared_ptr<ID2D1Bitmap>::operator=(v89, v80);
    if ( *(_QWORD *)&v83[24] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v83[24]);
  }
  std::shared_ptr<ID2D1Brush>::operator=((char *)this + 16, v89);
  if ( v89[1] )
    std::_Ref_count_base::_Decref(v89[1]);
  if ( *(_QWORD *)&v85[24] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v85[24]);
}

```

## disassembly

```asm
0x1800bbca0  mov     rax, rsp
0x1800bbca3  mov     [rax+18h], rbx
0x1800bbca7  push    rbp
0x1800bbca8  push    rsi
0x1800bbca9  push    rdi
0x1800bbcaa  push    r12
0x1800bbcac  push    r13
0x1800bbcae  push    r14
0x1800bbcb0  push    r15
0x1800bbcb2  lea     rbp, [rsp-80h]
0x1800bbcb7  sub     rsp, 180h
0x1800bbcbe  movaps  xmmword ptr [rax-48h], xmm6
0x1800bbcc2  movaps  xmmword ptr [rax-58h], xmm7
0x1800bbcc6  movaps  xmmword ptr [rax-68h], xmm8
0x1800bbccb  mov     rax, cs:__security_cookie
0x1800bbcd2  xor     rax, rsp
0x1800bbcd5  mov     [rbp+0B0h+var_70], rax
0x1800bbcd9  mov     rsi, rdx
0x1800bbcdc  mov     rbx, rcx
0x1800bbcdf  call    ?ValidBoxAndPortSizes@TileBrushBuilder@xpsrdr@@AEAA_NXZ; xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(void)
0x1800bbce4  xor     r13d, r13d
0x1800bbce7  test    al, al
0x1800bbce9  jnz     short loc_1800BBD3B
0x1800bbceb  mov     [rbp+0B0h+var_F0], 3F800000h
0x1800bbcf2  mov     rax, [rbx+28h]
0x1800bbcf6  mov     rcx, [rax]
0x1800bbcf9  mov     rax, [rcx]
0x1800bbcfc  lea     rdx, [rbp+0B0h+var_F0]
0x1800bbd00  mov     rax, [rax+28h]
0x1800bbd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd09  test    eax, eax
0x1800bbd0b  js      loc_1800BC631
0x1800bbd11  lea     r8, [rbp+0B0h+var_F0]
0x1800bbd15  mov     rdx, [rbx+20h]
0x1800bbd19  lea     rcx, [rbp+0B0h+var_90]
0x1800bbd1d  call    ?CreateEmptyBrushClipPair@xpsrdr@@YA?AU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEAURenderState@1@PEAM@Z; xpsrdr::CreateEmptyBrushClipPair(xpsrdr::RenderState &,float *)
0x1800bbd22  mov     rdx, rax
0x1800bbd25  mov     rcx, rbx
0x1800bbd28  call    ??$?4U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> &&)
0x1800bbd2d  lea     rcx, [rbp+0B0h+var_90]
0x1800bbd31  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x1800bbd36  jmp     loc_1800BC5E3
0x1800bbd3b  xorps   xmm0, xmm0
0x1800bbd3e  movdqu  xmmword ptr [rbp+0B0h+var_120+10h], xmm0
0x1800bbd43  mov     [rbp+0B0h+var_F0], r13d
0x1800bbd47  mov     rdx, [rbx+20h]
0x1800bbd4b  mov     rcx, [rdx+248h]
0x1800bbd52  mov     rax, [rdx+240h]
0x1800bbd59  dec     rax
0x1800bbd5c  add     rcx, rax
0x1800bbd5f  mov     rax, [rdx+238h]
0x1800bbd66  dec     rax
0x1800bbd69  and     rcx, rax
0x1800bbd6c  mov     rax, [rdx+230h]
0x1800bbd73  mov     rcx, [rax+rcx*8]
0x1800bbd77  mov     rcx, [rcx]
0x1800bbd7a  mov     [rbp+0B0h+var_D0], r13
0x1800bbd7e  lea     rax, [rbp+0B0h+var_F0]
0x1800bbd82  mov     [rbp+0B0h+var_D0+8], rax
0x1800bbd86  lea     rax, [rbp+0B0h+var_120+10h]
0x1800bbd8a  mov     [rbp+0B0h+var_C0], rax
0x1800bbd8e  mov     rax, [rcx]
0x1800bbd91  lea     r8, [rbp+0B0h+var_D0]
0x1800bbd95  lea     rdx, _GUID_e8f7fe7a_191c_466d_ad95_975678bda998
0x1800bbd9c  mov     rax, [rax]
0x1800bbd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbda4  mov     edi, eax
0x1800bbda6  lea     rcx, [rbp+0B0h+var_D0]
0x1800bbdaa  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bbdaf  mov     ecx, [rbp+0B0h+var_F0]; this
0x1800bbdb2  test    ecx, ecx
0x1800bbdb4  js      loc_1800BC639
0x1800bbdba  test    edi, edi
0x1800bbdbc  js      loc_1800BC63F
0x1800bbdc2  xorps   xmm8, xmm8
0x1800bbdc6  mov     qword ptr [rbp+0B0h+var_120], 0
0x1800bbdce  mov     rcx, [rsi]
0x1800bbdd1  mov     eax, [rcx+34h]
0x1800bbdd4  xorps   xmm7, xmm7
0x1800bbdd7  cvtsi2ss xmm7, rax
0x1800bbddc  divss   xmm7, dword ptr [rcx+3Ch]
0x1800bbde1  mulss   xmm7, cs:__real@42c00000
0x1800bbde9  movss   dword ptr [rbp+0B0h+var_120+8], xmm7
0x1800bbdee  mov     eax, [rcx+38h]
0x1800bbdf1  xorps   xmm6, xmm6
0x1800bbdf4  cvtsi2ss xmm6, rax
0x1800bbdf9  divss   xmm6, dword ptr [rcx+40h]
0x1800bbdfe  mulss   xmm6, cs:__real@42c00000
0x1800bbe06  movss   dword ptr [rbp+0B0h+var_120+0Ch], xmm6
0x1800bbe0b  xorps   xmm0, xmm0
0x1800bbe0e  movups  xmmword ptr [rsp+1B0h+var_148], xmm0
0x1800bbe13  xorps   xmm1, xmm1
0x1800bbe16  movups  xmmword ptr [rbp+0B0h+var_100.left], xmm1
0x1800bbe1a  lea     r8, [rbp+0B0h+var_100]; struct D2D_RECT_F *
0x1800bbe1e  lea     rdx, [rsp+1B0h+var_148]; struct D2D_RECT_F *
0x1800bbe23  mov     rcx, rbx; this
0x1800bbe26  call    ?GetViewboxAndViewport@TileBrushBuilder@xpsrdr@@AEAAXAEAUD2D_RECT_F@@0@Z; xpsrdr::TileBrushBuilder::GetViewboxAndViewport(D2D_RECT_F &,D2D_RECT_F &)
0x1800bbe2b  mov     [rsp+1B0h+var_170], r13d
0x1800bbe30  mov     [rbp+0B0h+var_F0], r13d
0x1800bbe34  lea     r8, [rbp+0B0h+var_F0]; enum D2D1_EXTEND_MODE *
0x1800bbe38  lea     rdx, [rsp+1B0h+var_170]; enum D2D1_EXTEND_MODE *
0x1800bbe3d  mov     rcx, rbx; this
0x1800bbe40  call    ?GetExtendMode@TileBrushBuilder@xpsrdr@@AEAAXAEAW4D2D1_EXTEND_MODE@@0@Z; xpsrdr::TileBrushBuilder::GetExtendMode(D2D1_EXTEND_MODE &,D2D1_EXTEND_MODE &)
0x1800bbe45  mov     rdx, [rbx+20h]; enum D3D_FEATURE_LEVEL
0x1800bbe49  mov     ecx, [rdx+50h]; this
0x1800bbe4c  call    ?GetMaxD3DTextureDimension@xpsrdr@@YAIW4D3D_FEATURE_LEVEL@@@Z; xpsrdr::GetMaxD3DTextureDimension(D3D_FEATURE_LEVEL)
0x1800bbe51  mov     edi, eax
0x1800bbe53  mov     rcx, [rsi]
0x1800bbe56  mov     r14d, [rcx+38h]
0x1800bbe5a  mov     r15d, [rcx+34h]
0x1800bbe5e  movups  xmm0, xmmword ptr [rdx+64h]
0x1800bbe62  movdqu  xmmword ptr [rbp+0B0h+var_D0], xmm0
0x1800bbe67  lea     rcx, [rbp+0B0h+var_D0]; this
0x1800bbe6b  call    ?GetBytesPerPixel@xpsrdr@@YAFU_GUID@@@Z; xpsrdr::GetBytesPerPixel(_GUID)
0x1800bbe70  movsx   r8d, ax
0x1800bbe74  mov     rcx, [rsi]
0x1800bbe77  cmp     [rcx+34h], edi
0x1800bbe7a  ja      short loc_1800BBECC
0x1800bbe7c  cmp     [rcx+38h], edi
0x1800bbe7f  ja      short loc_1800BBECC
0x1800bbe81  mov     edx, r14d
0x1800bbe84  imul    rdx, r15
0x1800bbe88  xorps   xmm1, xmm1
0x1800bbe8b  test    rdx, rdx
0x1800bbe8e  js      short loc_1800BBE97
0x1800bbe90  cvtsi2ss xmm1, rdx
0x1800bbe95  jmp     short loc_1800BBEAC
0x1800bbe97  mov     rax, rdx
0x1800bbe9a  shr     rax, 1
0x1800bbe9d  and     edx, 1
0x1800bbea0  or      rax, rdx
0x1800bbea3  cvtsi2ss xmm1, rax
0x1800bbea8  addss   xmm1, xmm1
0x1800bbeac  movd    xmm0, r8d
0x1800bbeb1  cvtdq2ps xmm0, xmm0
0x1800bbeb4  mulss   xmm0, cs:__real@35800000
0x1800bbebc  mulss   xmm1, xmm0
0x1800bbec0  comiss  xmm1, cs:__real@42000000
0x1800bbec7  mov     dil, r13b
0x1800bbeca  jbe     short loc_1800BBECF
0x1800bbecc  mov     dil, 1
0x1800bbecf  lea     rdx, [rbp+0B0h+var_100]; struct D2D_RECT_F *
0x1800bbed3  mov     rcx, rbx; this
0x1800bbed6  call    ?WillBrushTile@TileBrushBuilder@xpsrdr@@AEAA_NAEBUD2D_RECT_F@@@Z; xpsrdr::TileBrushBuilder::WillBrushTile(D2D_RECT_F const &)
0x1800bbedb  mov     r12b, al
0x1800bbede  mov     r14d, [rbp+0B0h+var_F0]
0x1800bbee2  mov     r15d, [rsp+1B0h+var_170]
0x1800bbee7  test    dil, dil
0x1800bbeea  jnz     loc_1800BC0F5
0x1800bbef0  test    al, al
0x1800bbef2  jz      short loc_1800BBF2C
0x1800bbef4  ucomiss xmm8, dword ptr [rsp+1B0h+var_148]
0x1800bbefa  jp      short loc_1800BBF1A
0x1800bbefc  jnz     short loc_1800BBF1A
0x1800bbefe  ucomiss xmm8, dword ptr [rsp+1B0h+var_148+4]
0x1800bbf04  jp      short loc_1800BBF1A
0x1800bbf06  jnz     short loc_1800BBF1A
0x1800bbf08  ucomiss xmm7, dword ptr [rsp+1B0h+var_148+8]
0x1800bbf0d  jp      short loc_1800BBF1A
0x1800bbf0f  jnz     short loc_1800BBF1A
0x1800bbf11  ucomiss xmm6, dword ptr [rsp+1B0h+var_148+0Ch]
0x1800bbf16  jp      short loc_1800BBF1A
0x1800bbf18  jz      short loc_1800BBF2C
0x1800bbf1a  test    r15d, r15d
0x1800bbf1d  jnz     loc_1800BC0F5
0x1800bbf23  test    r14d, r14d
0x1800bbf26  jnz     loc_1800BC0F5
0x1800bbf2c  xorps   xmm0, xmm0
0x1800bbf2f  movups  xmmword ptr [rbp+0B0h+var_B0.opacity], xmm0
0x1800bbf33  movups  xmmword ptr [rbp+0B0h+var_B0.transform+8], xmm0
0x1800bbf37  lea     r9, [rbp+0B0h+var_B0]; struct D2D1_BRUSH_PROPERTIES *
0x1800bbf3b  lea     r8, [rbp+0B0h+var_100]; struct D2D_RECT_F *
0x1800bbf3f  lea     rdx, [rsp+1B0h+var_148]; struct D2D_RECT_F *
0x1800bbf44  mov     rcx, rbx; this
0x1800bbf47  call    ?PopulateBrushProperties@TileBrushBuilder@xpsrdr@@AEAAXAEBUD2D_RECT_F@@0AEAUD2D1_BRUSH_PROPERTIES@@@Z; xpsrdr::TileBrushBuilder::PopulateBrushProperties(D2D_RECT_F const &,D2D_RECT_F const &,D2D1_BRUSH_PROPERTIES &)
0x1800bbf4c  xorps   xmm0, xmm0
0x1800bbf4f  movdqu  xmmword ptr [rsp+1B0h+var_148+10h], xmm0
0x1800bbf55  mov     rax, [rbx+20h]
0x1800bbf59  cmp     [rax+1E1h], r13b
0x1800bbf60  jz      loc_1800BC06B
0x1800bbf66  lea     r9, [rbp+0B0h+var_120+10h]
0x1800bbf6a  mov     r8, rsi
0x1800bbf6d  lea     rdx, [rbp+0B0h+var_D0]
0x1800bbf71  mov     rcx, rbx
0x1800bbf74  call    ?CreateBitmapFromWicBitmap@TileBrushBuilder@xpsrdr@@AEAA?AV?$shared_ptr@UID2D1Bitmap@@@std@@AEBV?$shared_ptr@UImage@xpsrdr@@@4@AEAV?$shared_ptr@UID2D1DeviceContext@@@4@@Z; xpsrdr::TileBrushBuilder::CreateBitmapFromWicBitmap(std::shared_ptr<xpsrdr::Image> const &,std::shared_ptr<ID2D1DeviceContext> &)
0x1800bbf79  mov     rdx, rax
0x1800bbf7c  lea     rcx, [rsp+1B0h+var_148+10h]
0x1800bbf81  call    ??4?$shared_ptr@UID2D1Bitmap@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ID2D1Bitmap>::operator=(std::shared_ptr<ID2D1Bitmap> &&)
0x1800bbf86  mov     rcx, [rbp+0B0h+var_D0+8]; this
0x1800bbf8a  test    rcx, rcx
0x1800bbf8d  jz      short loc_1800BBF94
0x1800bbf8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bbf94  xorps   xmm0, xmm0
0x1800bbf97  movdqu  xmmword ptr [rbp+0B0h+var_E0], xmm0
0x1800bbf9c  mov     [rsp+1B0h+var_170], r13d
0x1800bbfa1  mov     rcx, qword ptr [rbp+0B0h+var_120+10h]
0x1800bbfa5  mov     rax, [rcx]
0x1800bbfa8  mov     r10, [rax+38h]
0x1800bbfac  mov     qword ptr [rsp+1B0h+var_168], r13
0x1800bbfb1  lea     rax, [rsp+1B0h+var_170]
0x1800bbfb6  mov     qword ptr [rsp+1B0h+var_168+8], rax
0x1800bbfbb  lea     rax, [rbp+0B0h+var_E0]
0x1800bbfbf  mov     [rsp+1B0h+var_158], rax
0x1800bbfc4  mov     rax, [rbx+20h]
0x1800bbfc8  cmp     [rax+60h], r13d
0x1800bbfcc  jnz     short loc_1800BBFD9
0x1800bbfce  cmp     dword ptr [rax+58h], 1
0x1800bbfd2  mov     eax, 1
0x1800bbfd7  jnz     short loc_1800BBFDC
0x1800bbfd9  mov     eax, r13d
0x1800bbfdc  mov     [rbp+0B0h+var_F0], r15d
0x1800bbfe0  mov     [rbp+0B0h+var_F0+4], r14d
0x1800bbfe4  mov     [rbp+0B0h+var_F0+8], eax
0x1800bbfe7  lea     rax, [rsp+1B0h+var_168]
0x1800bbfec  mov     [rsp+1B0h+var_190], rax
0x1800bbff1  lea     r9, [rbp+0B0h+var_B0]
0x1800bbff5  lea     r8, [rbp+0B0h+var_F0]
0x1800bbff9  mov     rdx, qword ptr [rsp+1B0h+var_148+10h]
0x1800bbffe  mov     rax, r10
0x1800bc001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc006  mov     edi, eax
0x1800bc008  lea     rcx, [rsp+1B0h+var_168]
0x1800bc00d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bc012  mov     ecx, [rsp+1B0h+var_170]; this
0x1800bc016  test    ecx, ecx
0x1800bc018  js      loc_1800BC647
0x1800bc01e  test    edi, edi
0x1800bc020  js      loc_1800BC653
0x1800bc026  mov     rcx, [rbp+0B0h+var_E0+8]
0x1800bc02a  test    rcx, rcx
0x1800bc02d  jz      short loc_1800BC037
0x1800bc02f  lock inc dword ptr [rcx+8]
0x1800bc033  mov     rcx, [rbp+0B0h+var_E0+8]
0x1800bc037  mov     rax, [rbp+0B0h+var_E0]
0x1800bc03b  mov     [rbx], rax
0x1800bc03e  mov     rax, [rbx+8]
0x1800bc042  mov     [rbx+8], rcx
0x1800bc046  test    rax, rax
0x1800bc049  jz      short loc_1800BC057
0x1800bc04b  mov     rcx, rax; this
0x1800bc04e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bc053  mov     rcx, [rbp+0B0h+var_E0+8]; this
0x1800bc057  test    rcx, rcx
0x1800bc05a  jz      short loc_1800BC062
0x1800bc05c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bc061  nop
0x1800bc062  mov     rcx, qword ptr [rbp+0B0h+var_148+18h]
0x1800bc066  jmp     loc_1800BC455
0x1800bc06b  mov     [rsp+1B0h+var_170], r13d
0x1800bc070  mov     rcx, qword ptr [rbp+0B0h+var_120+10h]
0x1800bc074  mov     qword ptr [rsp+1B0h+var_168], r13
0x1800bc079  lea     rax, [rsp+1B0h+var_170]
0x1800bc07e  mov     qword ptr [rsp+1B0h+var_168+8], rax
0x1800bc083  lea     rax, [rsp+1B0h+var_148+10h]
0x1800bc088  mov     [rsp+1B0h+var_158], rax
0x1800bc08d  mov     rdx, [rsi]
0x1800bc090  mov     qword ptr [rbp+0B0h+var_F0], r13
0x1800bc094  mov     rax, r13
0x1800bc097  mov     [rbp+0B0h+var_D0], rax
0x1800bc09b  movss   xmm0, dword ptr [rdx+3Ch]
0x1800bc0a0  movss   dword ptr [rbp+0B0h+var_D0+8], xmm0
0x1800bc0a5  movss   xmm1, dword ptr [rdx+40h]
0x1800bc0aa  movss   dword ptr [rbp+0B0h+var_D0+0Ch], xmm1
0x1800bc0af  movups  xmm0, xmmword ptr [rbp+0B0h+var_D0]
0x1800bc0b3  movups  xmmword ptr [rbp+0B0h+var_D0], xmm0
0x1800bc0b7  mov     rax, [rcx]
0x1800bc0ba  lea     r9, [rsp+1B0h+var_168]
0x1800bc0bf  lea     r8, [rbp+0B0h+var_D0]
0x1800bc0c3  mov     rdx, [rdx+20h]
0x1800bc0c7  mov     rax, [rax+28h]
0x1800bc0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc0d0  mov     edi, eax
0x1800bc0d2  lea     rcx, [rsp+1B0h+var_168]
0x1800bc0d7  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bc0dc  mov     ecx, [rsp+1B0h+var_170]; this
0x1800bc0e0  test    ecx, ecx
0x1800bc0e2  js      loc_1800BC64D
0x1800bc0e8  test    edi, edi
0x1800bc0ea  js      loc_1800BC621
0x1800bc0f0  jmp     loc_1800BBF94
0x1800bc0f5  xorps   xmm0, xmm0
0x1800bc0f8  movdqu  xmmword ptr [rbp+0B0h+var_D0], xmm0
0x1800bc0fd  test    dil, dil
0x1800bc100  jz      loc_1800BC28B
0x1800bc106  movdqu  xmmword ptr [rbp+0B0h+var_E0], xmm0
0x1800bc10b  mov     [rsp+1B0h+var_170], r13d
0x1800bc110  mov     rcx, qword ptr [rbp+0B0h+var_120+10h]
0x1800bc114  mov     rax, [rcx]
0x1800bc117  mov     qword ptr [rsp+1B0h+var_168], r13
0x1800bc11c  lea     rdx, [rsp+1B0h+var_170]
0x1800bc121  mov     qword ptr [rsp+1B0h+var_168+8], rdx
0x1800bc126  lea     rdx, [rbp+0B0h+var_E0]
0x1800bc12a  mov     [rsp+1B0h+var_158], rdx
0x1800bc12f  lea     r8, [rsp+1B0h+var_168]
0x1800bc134  lea     rdx, CLSID_D2D1BitmapSource
0x1800bc13b  mov     rax, [rax+1F8h]
0x1800bc142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc147  mov     edi, eax
0x1800bc149  lea     rcx, [rsp+1B0h+var_168]
0x1800bc14e  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
  ... truncated ...
```
