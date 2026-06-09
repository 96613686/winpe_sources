# GEL::GdiTextTech::TryDrawUsingGdiOrGrayscale(GEL::EffectText const &,GEL::RenderStage::Frame &,Math::TAffine3x3<double> const &,ARC::AlphaMode)

- ea: `0x1800bb5c0`
- end: `0x1800bc043`
- name: `?TryDrawUsingGdiOrGrayscale@GdiTextTech@GEL@@UEBA_NAEBVEffectText@2@AEAVFrame@RenderStage@2@AEBU?$TAffine3x3@N@Math@@W4AlphaMode@ARC@@@Z`
- size: `2691`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `broker_com_uri`

## callees

- `0x18000a71c`
- `0x18000a788`
- `0x180011694`
- `0x1800157c0`
- `0x18004d1a0`
- `0x180051dbb`
- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x18006f3c4`
- `0x180070398`
- `0x18007b304`
- `0x180082960`
- `0x18008faa0`
- `0x180091710`
- `0x180092a58`
- `0x180093d58`
- `0x1800acb9c`
- `0x1800b3b14`
- `0x1800b7fe8`
- `0x1800ba108`
- `0x1800ba25c`
- `0x1800bb5c0`
- `0x1800bc044`
- `0x1800bc130`
- `0x1800bc16c`
- `0x1800bd8a0`
- `0x1800bd93c`
- `0x1800c05c0`
- `0x1800d35c0`
- `0x1800e29cc`
- `0x1800ea7c4`
- `0x18014733c`
- `0x180153a8c`
- `0x1801cfd14`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800bb7ad`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800bbdb7`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800bb7ad`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800bbdb7`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1800bbaea`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1800bbaea`
- `Mso20Win32Client!__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ` at `0x1800bba1f`
- `Mso20Win32Client!__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ` at `0x1800bba1f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800bb9eb`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800bb9eb`
- `GDI32!DeleteDC` at `0x1800bbe4e`
- `GDI32!DeleteDC` at `0x1800bbe4e`
- `GDI32!SelectObject` at `0x1800bb7ef`
- `GDI32!SelectObject` at `0x1800bbdf7`
- `GDI32!SelectObject` at `0x1800bbe45`
- `GDI32!SelectObject` at `0x1800bb7ef`
- `GDI32!SelectObject` at `0x1800bbdf7`
- `GDI32!SelectObject` at `0x1800bbe45`
- `GDI32!SetWorldTransform` at `0x1800bbd95`
- `GDI32!SetWorldTransform` at `0x1800bbd95`
- `GDI32!SetGraphicsMode` at `0x1800bbcfd`
- `GDI32!SetGraphicsMode` at `0x1800bbcfd`
- `GDI32!SetWindowOrgEx` at `0x1800bbccc`
- `GDI32!SetWindowOrgEx` at `0x1800bbccc`
- `GDI32!GetStockObject` at `0x1800bbcdf`
- `GDI32!GetStockObject` at `0x1800bbcdf`
- `USER32!FillRect` at `0x1800bbcef`
- `USER32!FillRect` at `0x1800bbcef`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall GEL::GdiTextTech::TryDrawUsingGdiOrGrayscale(
        __int64 a1,
        __int64 a2,
        struct Frame *a3,
        __int64 a4,
        int a5)
{
  struct Frame v7; // rdi
  char DeviceType; // si
  const struct GEL::ITypefaceList *AvailableTypefaces; // r14
  bool v10; // al
  bool v11; // r12
  unsigned __int64 v12; // xmm6_8
  float *DPI; // rax
  float v14; // xmm1_4
  const struct GEL::Font *v15; // r13
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int8 v18; // al
  int v19; // r14d
  __int64 v20; // rcx
  __int64 v21; // rcx
  char v22; // dl
  Mso::GDIAssistant *v23; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *v24; // rax
  __int64 v25; // r8
  void *v26; // rax
  HDC v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v31; // rsi
  unsigned __int64 v32; // rdx
  unsigned int v33; // r8d
  _QWORD *v34; // rax
  _QWORD *v35; // rdi
  GEL::RenderStage::Frame *v36; // r12
  void *v37; // rdx
  int Sku; // eax
  __int64 v39; // r14
  int v40; // r8d
  unsigned int v41; // edi
  __int64 v42; // rsi
  __int64 v43; // r12
  unsigned int j; // ebx
  unsigned __int64 v45; // rdx
  unsigned int v46; // r8d
  void *v47; // rax
  unsigned __int64 v48; // rdx
  unsigned int v49; // r8d
  unsigned __int64 v50; // rbx
  __int64 v51; // r14
  void *v52; // rax
  LONG v53; // ecx
  LONG v54; // esi
  LONG v55; // r8d
  LONG v56; // r14d
  LONG top; // edx
  int v58; // esi
  int v59; // r14d
  const struct Ofc::CDIBSection *v60; // rdx
  HDC v61; // rdi
  HBRUSH StockObject; // rax
  double v63; // xmm6_8
  double v64; // xmm7_8
  double v65; // xmm6_8
  double v66; // xmm7_8
  double v67; // xmm6_8
  double v68; // xmm7_8
  Mso::GDIAssistant *v69; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *GDIAssistant; // rax
  __int64 v71; // r8
  void *v72; // rax
  unsigned int i; // edx
  __int64 v74; // rcx
  int v75; // r12d
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  unsigned int v79; // eax
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  LONG v85; // eax
  __int64 v86; // r9
  char v87; // cl
  const struct tagFONTSIGNATURE *v88; // rax
  unsigned __int8 v89; // [rsp+38h] [rbp-D0h]
  unsigned __int8 v90; // [rsp+39h] [rbp-CFh]
  char v91; // [rsp+3Ah] [rbp-CEh]
  unsigned __int8 v92; // [rsp+3Bh] [rbp-CDh]
  unsigned __int64 v93; // [rsp+40h] [rbp-C8h] BYREF
  float hdc; // [rsp+48h] [rbp-C0h] BYREF
  float hdc_4; // [rsp+4Ch] [rbp-BCh]
  HDC hdc_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  double right; // [rsp+60h] [rbp-A8h]
  double bottom; // [rsp+68h] [rbp-A0h]
  struct Frame *v99[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v100; // [rsp+80h] [rbp-88h] BYREF
  __int64 v101; // [rsp+88h] [rbp-80h]
  int v102; // [rsp+90h] [rbp-78h]
  HBITMAP v103[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v104; // [rsp+A8h] [rbp-60h]
  __m256i v105; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v106; // [rsp+D0h] [rbp-38h]
  __int64 v107; // [rsp+D8h] [rbp-30h]
  __int64 v108; // [rsp+E0h] [rbp-28h]
  RECT x; // [rsp+E8h] [rbp-20h] BYREF
  XFORM xf; // [rsp+F8h] [rbp-10h] BYREF
  Mso::Memory *v111; // [rsp+110h] [rbp+8h]
  struct tagLOGFONTW v112; // [rsp+118h] [rbp+10h] BYREF
  struct tagLOGFONTW v113; // [rsp+178h] [rbp+70h] BYREF

  v99[0] = a3;
  v7.lpVtbl = a3->lpVtbl;
  v104 = 0;
  DeviceType = GEL::RenderStage::GetDeviceType(v7.lpVtbl);
  AvailableTypefaces = GEL::RenderStage::GetAvailableTypefaces((GEL::RenderStage *)v7.lpVtbl);
  v10 = GEL::EffectTransparentMarkup::IsInTransparentMarkup();
  v11 = v10;
  v12 = _mm_load_si128((const __m128i *)&_xmm).m128i_u64[0];
  if ( (v7.lpVtbl[1].GetTypeInfo
     || DeviceType == 5
     || (COERCE_DOUBLE(*(_QWORD *)a4 & v12) >= 1.0e-15 || COERCE_DOUBLE(*(_QWORD *)(a4 + 24) & v12) >= 1.0e-15)
     && (COERCE_DOUBLE(*(_QWORD *)(a4 + 8) & v12) >= 1.0e-15 || COERCE_DOUBLE(*(_QWORD *)(a4 + 16) & v12) >= 1.0e-15))
    && !v10 )
  {
    return 0;
  }
  DPI = (float *)GEL::RenderStage::GetDPI(v7.lpVtbl);
  v14 = DPI[1];
  hdc = *DPI;
  hdc_4 = v14;
  memset_0(&v113, 0, sizeof(v113));
  v15 = (const struct GEL::Font *)(a2 + 72);
  GEL::EffectText::GetLOGFONT((GEL::EffectText *)a2, *(_DWORD *)(a2 + 92), AvailableTypefaces, &v113);
  if ( dword_180532AE8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180532AE8);
    if ( dword_180532AE8 == -1 )
    {
      dword_180532AEC = MsoDwRegGetDw((const struct _msoreg *)&vmsoridGELFixUpCharSetForMetafiles);
      Init_thread_footer(&dword_180532AE8);
    }
  }
  if ( dword_180532AEC > 0
    && !(*(unsigned __int8 (__fastcall **)(const struct GEL::ITypefaceList *))(*(_QWORD *)AvailableTypefaces + 72LL))(AvailableTypefaces)
    && (*(unsigned __int8 (__fastcall **)(HRESULT (__stdcall *)(Frame *, UINT, LCID, ITypeInfo **)))(*(_QWORD *)v7.lpVtbl->GetTypeInfo + 56LL))(v7.lpVtbl->GetTypeInfo) )
  {
    v88 = (const struct tagFONTSIGNATURE *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 112LL))(*(_QWORD *)v15);
    v113.lfCharSet = GetCharSet(v88);
  }
  if ( DeviceType != 3 )
  {
    if ( *(float *)(a2 + 88) >= (double)(float)(hdc_4 * 3.0) )
      return 0;
    Sku = Mso::Instance::GetSku();
    if ( DeviceType == 4 && Sku != 4 && (float)SDWORD2(xmmword_180523DC0) <= *(float *)(a2 + 88) )
      return 0;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 176) + 16LL))(*(_QWORD *)(a2 + 176));
  Ofc::Round<long,float>(v16);
  v18 = Ofc::Round<long,float>(v17);
  v19 = v18;
  v92 = v18;
  v89 = Ofc::Round<long,float>(v20);
  v90 = Ofc::Round<long,float>(v21);
  if ( v22 != -1 && (!v11 || v22) )
    return 0;
  if ( DeviceType != 3
    && !(*(unsigned __int8 (__fastcall **)(HRESULT (__stdcall *)(Frame *, UINT, LCID, ITypeInfo **)))(*(_QWORD *)v7.lpVtbl->GetTypeInfo + 56LL))(v7.lpVtbl->GetTypeInfo)
    && (DeviceType == 4 || a5 != 3) )
  {
    if ( *(double *)(a2 + 160) - *(double *)(a2 + 144) < 2048.0
      && *(double *)(a2 + 168) - *(double *)(a2 + 152) < 2048.0 )
    {
      v74 = 1920103 * (unsigned int)v90;
      v75 = (int)(v74 + 5036060 * v19 + 9886846 * v89) >> 24;
      if ( COERCE_DOUBLE(*(_QWORD *)(a4 + 8) & v12) > COERCE_DOUBLE(*(_QWORD *)a4 & v12)
        || (LOBYTE(v74) = 0, COERCE_DOUBLE(*(_QWORD *)(a4 + 16) & v12) > COERCE_DOUBLE(*(_QWORD *)(a4 + 24) & v12)) )
      {
        LOBYTE(v74) = 1;
      }
      v91 = v74;
      v54 = Ofc::Round<long,double>(v74, v28, v29);
      v79 = Ofc::Round<long,double>(v77, v76, v78);
      v56 = Ofc::Round<long,double>(v81, v80, v79);
      v85 = Ofc::Round<long,double>(v83, v82, v84);
      top = v85;
      if ( v87 )
      {
        x.left = v55;
        x.top = v85;
        x.right = v54;
        x.bottom = v56;
      }
      else
      {
        v53 = v54;
        v54 = v56;
        x.left = v85;
        x.top = v55;
        x.right = v56;
        x.bottom = v53;
        v55 = v85;
        v56 = v53;
        top = x.top;
      }
      v58 = v54 - v55;
      v59 = v56 - top;
      if ( (unsigned int)(v58 - 1) <= 0x7FE && (unsigned int)(v59 - 1) <= 0x7FE )
      {
        v100 = v86;
        v101 = v86;
        v102 = v86;
        *(_OWORD *)v103 = 0;
        v93 = __PAIR64__(v59, v58);
        Gfx::TDIBSection<ARC::Pixel32>::SetSize(&v100, &v93);
        GEL::ValidateDIBSection((GEL *)v103, v60);
        *(_OWORD *)hdc_8 = 0;
        Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc_8, 0, v103[0]);
        v61 = hdc_8[0];
        SetWindowOrgEx(hdc_8[0], x.left, x.top, 0);
        StockObject = (HBRUSH)GetStockObject((unsigned __int8)v75 > 0xD4u ? 4 : 0);
        FillRect(v61, &x, StockObject);
        SetGraphicsMode(v61, 2);
        v63 = *(double *)(a4 + 40);
        v64 = *(double *)(a4 + 32);
        v65 = v63 - floor_0(v63);
        v66 = v64 - floor_0(v64);
        if ( v91 )
        {
          v68 = v66 * *(double *)(a4 + 16);
          v67 = v65 * *(double *)(a4 + 8);
          *(__m128i *)v105.m256i_i8 = _mm_load_si128((const __m128i *)&_xmm);
          *(__m128i *)&v105.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
          v106 = *(_QWORD *)&v67 ^ _xmm;
          v107 = *(_QWORD *)&v68 ^ _xmm;
          *(__m128i *)&xf.eM11 = _mm_load_si128((const __m128i *)&_xmm);
        }
        else
        {
          v67 = v65 * *(double *)(a4 + 24);
          v68 = v66 * *(double *)a4;
          *(double *)&v105.m256i_i64[3] = DOUBLE_1_0;
          *(double *)v105.m256i_i64 = DOUBLE_1_0;
          *(_OWORD *)&v105.m256i_u64[1] = 0;
          v106 = *(_QWORD *)&v68 ^ _xmm;
          v107 = *(_QWORD *)&v67 ^ _xmm;
          *(__m128i *)&xf.eM11 = _mm_load_si128((const __m128i *)&_xmm);
        }
        xf.eDx = v68;
        xf.eDy = v67;
        SetWorldTransform(v61, &xf);
        memset_0(&v112, 0, sizeof(v112));
        Ofc::CHFont::FixupLOGFONT(&v113, &v112);
        GDIAssistant = Mso::GDIAssistant::GetGDIAssistant(v69);
        LOBYTE(v71) = 1;
        v72 = (void *)(*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, struct tagLOGFONTW *, __int64))(*(_QWORD *)GDIAssistant + 24LL))(
                        GDIAssistant,
                        &v112,
                        v71);
        *(_QWORD *)&xf.eDx = 0;
        *(_QWORD *)&xf.eM21 = v61;
        *(_QWORD *)&xf.eM11 = v72;
        if ( v61 && v72 )
          *(_QWORD *)&xf.eDx = SelectObject(v61, v72);
        sub_1800BD93C(v61);
        sub_1800ACB9C(a2, v61);
        Ofc::CHFont::~CHFont((Ofc::CHFont *)&xf);
        if ( v61 )
        {
          if ( hdc_8[1] )
            SelectObject(v61, hdc_8[1]);
          DeleteDC(v61);
        }
        v41 = 0;
        memset(&xf, 0, 20);
        v111 = 0;
        v93 = __PAIR64__(v59, v58);
        ARC::TPixelBuffer<ARC::Pixel32>::SetSize(&xf, &v93);
        LOBYTE(v93) = v90;
        BYTE1(v93) = v89;
        BYTE2(v93) = v92;
        BYTE3(v93) = (unsigned __int8)v75 <= 0xD4u;
        for ( i = 0; i < 2; ++i )
        {
          if ( *((_DWORD *)&xf.eM21 + i) != *((_DWORD *)&v101 + i) )
            goto LABEL_57;
        }
        v42 = v100;
        v43 = *(_QWORD *)&xf.eM11;
        for ( j = 0; j < LODWORD(xf.eM22); ++j )
        {
          v39 = v42;
          while ( v41 < LODWORD(xf.eM21) )
          {
            GEL::LuminanceToPremultipliedAlphaCopy::operator()(&v93, v39 + v43 - v42, v39);
            ++v41;
            v39 += 4;
          }
          v42 += v102;
          v43 += SLODWORD(xf.eDx);
          v41 = 0;
        }
        v15 = (const struct GEL::Font *)(a2 + 72);
LABEL_57:
        GEL::IImage::Create<ARC::Pixel32,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>>>(
          (unsigned int)&v93,
          (unsigned int)&xf,
          v40,
          1,
          (__int64)&hdc);
        v47 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x80, v45, v46);
        v50 = v93;
        if ( v47 )
        {
          *(double *)hdc_8 = (double)x.left;
          *(double *)&hdc_8[1] = (double)x.top;
          right = (double)x.right;
          bottom = (double)x.bottom;
          v51 = GEL::EffectImage::EffectImage(v47, v93, hdc_8);
        }
        else
        {
          v51 = 0;
        }
        v108 = v51;
        if ( v51 )
          (**(void (__fastcall ***)(__int64))v51)(v51);
        v52 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v48, v49);
        if ( v52 )
          v31 = GEL::EffectTransform::EffectTransform(v52, v51, &v105);
        else
          v31 = 0;
        hdc_8[0] = (HDC)v31;
        if ( v31 )
          (**(void (__fastcall ***)(__int64))v31)(v31);
        v34 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v32, v33);
        v35 = v34;
        if ( v34 )
        {
          GEL::TEffect<GEL::IEffectAlphaReplaceBinary>::TEffect<GEL::IEffectAlphaReplaceBinary>(v34);
          v35[5] = v31;
          (**(void (__fastcall ***)(__int64))v31)(v31);
          *v35 = &GEL::EffectNearestNeighborInterpolation::`vftable'{for `Mso::TRefCountedImpl<GEL::IEffectNearestNeighborInterpolation>'};
          v35[2] = &GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'};
          v35[3] = &GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'};
          v35[4] = &GEL::EffectNearestNeighborInterpolation::`vftable';
        }
        if ( v35 )
          (*(void (__fastcall **)(_QWORD *))*v35)(v35);
        v104 = v35;
        v36 = (GEL::RenderStage::Frame *)v99[0];
        GEL::MarkupText::MarkupText((GEL::MarkupText *)v99, v99[0], *(const struct GEL::ITextRun **)(a2 + 208), v15);
        GEL::RenderStage::Frame::Draw(v36, (const struct GEL::IEffect *)v35);
        GEL::MarkupText::Close((GEL::MarkupText *)v99);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
        if ( v50 )
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v50 + 8LL))(v50);
        if ( v111 )
          Mso::Memory::Free(v111, v37);
        Ofc::CDIBSection::Reset((Ofc::CDIBSection *)v103);
        if ( v35 )
          (*(void (__fastcall **)(_QWORD *))(*v35 + 8LL))(v35);
        return 1;
      }
    }
    return 0;
  }
  GEL::MarkupText::MarkupText(
    (GEL::MarkupText *)&x,
    v99[0],
    *(const struct GEL::ITextRun **)(a2 + 208),
    (const struct GEL::Font *)(a2 + 72));
  GEL::StageDC::StageDC((GEL::StageDC *)hdc_8, (struct GEL::RenderStage *)v7.lpVtbl);
  memset_0(&v112, 0, sizeof(v112));
  Ofc::CHFont::FixupLOGFONT(&v113, &v112);
  v24 = Mso::GDIAssistant::GetGDIAssistant(v23);
  LOBYTE(v25) = 1;
  v26 = (void *)(*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, struct tagLOGFONTW *, __int64))(*(_QWORD *)v24 + 24LL))(
                  v24,
                  &v112,
                  v25);
  *(_QWORD *)&xf.eDx = 0;
  v27 = hdc_8[0];
  *(HDC *)&xf.eM21 = hdc_8[0];
  *(_QWORD *)&xf.eM11 = v26;
  if ( hdc_8[0] )
  {
    if ( v26 )
    {
      *(_QWORD *)&xf.eDx = SelectObject(hdc_8[0], v26);
      v27 = hdc_8[0];
    }
  }
  sub_1800BD93C(v27);
  sub_1800ACB9C(a2, hdc_8[0]);
  Ofc::CHFont::~CHFont((Ofc::CHFont *)&xf);
  Gfx::GpHDCHolder::Empty((Gfx::GpHDCHolder *)hdc_8);
  GEL::MarkupText::Close((GEL::MarkupText *)&x);
  return 1;
}

```

## disassembly

```asm
0x1800bb5c0  mov     rax, rsp
0x1800bb5c3  mov     [rax+8], rbx
0x1800bb5c7  push    rbp
0x1800bb5c8  push    rsi
0x1800bb5c9  push    rdi
0x1800bb5ca  push    r12
0x1800bb5cc  push    r13
0x1800bb5ce  push    r14
0x1800bb5d0  push    r15
0x1800bb5d2  lea     rbp, [rax-138h]
0x1800bb5d9  sub     rsp, 200h
0x1800bb5e0  movaps  xmmword ptr [rax-48h], xmm6
0x1800bb5e4  movaps  xmmword ptr [rax-58h], xmm7
0x1800bb5e8  mov     rax, cs:__security_cookie
0x1800bb5ef  xor     rax, rsp
0x1800bb5f2  mov     [rbp+130h+var_60], rax
0x1800bb5f9  mov     rbx, r9
0x1800bb5fc  mov     [rsp+230h+var_1C8], r8
0x1800bb601  mov     r15, rdx
0x1800bb604  mov     rdi, [r8]
0x1800bb607  mov     [rbp+130h+var_190], 0
0x1800bb60f  mov     rcx, rdi
0x1800bb612  call    ?GetDeviceType@RenderStage@GEL@@QEBA?AW4DeviceType@2@XZ; GEL::RenderStage::GetDeviceType(void)
0x1800bb617  mov     sil, al
0x1800bb61a  mov     rcx, rdi; this
0x1800bb61d  call    ?GetAvailableTypefaces@RenderStage@GEL@@QEBAAEBUITypefaceList@2@XZ; GEL::RenderStage::GetAvailableTypefaces(void)
0x1800bb622  mov     r14, rax
0x1800bb625  call    ?IsInTransparentMarkup@EffectTransparentMarkup@GEL@@SA_NXZ; GEL::EffectTransparentMarkup::IsInTransparentMarkup(void)
0x1800bb62a  mov     r12b, al
0x1800bb62d  movdqa  xmm6, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1800bb635  cmp     qword ptr [rdi+0B0h], 0
0x1800bb63d  jz      loc_1800BB850
0x1800bb643  test    r12b, r12b
0x1800bb646  jz      loc_1800BB8ED
0x1800bb64c  mov     rcx, rdi
0x1800bb64f  call    ?GetDPI@RenderStage@GEL@@QEBAAEBV?$TConvertibleDPI2@M@Gfx@@XZ; GEL::RenderStage::GetDPI(void)
0x1800bb654  movss   xmm1, dword ptr [rax+4]
0x1800bb659  movss   xmm0, dword ptr [rax]
0x1800bb65d  movss   dword ptr [rsp+230h+hdc], xmm0
0x1800bb663  movss   dword ptr [rsp+230h+hdc+4], xmm1
0x1800bb669  xor     edx, edx; Val
0x1800bb66b  lea     r8d, [rdx+5Ch]; Size
0x1800bb66f  lea     rcx, [rbp+130h+var_C0]; void *
0x1800bb673  call    memset_0
0x1800bb678  lea     r13, [r15+48h]
0x1800bb67c  lea     r9, [rbp+130h+var_C0]; struct tagLOGFONTW *
0x1800bb680  mov     r8, r14; struct GEL::ITypefaceList *
0x1800bb683  mov     edx, [r13+14h]; unsigned int
0x1800bb687  mov     rcx, r15; this
0x1800bb68a  call    ?GetLOGFONT@EffectText@GEL@@UEBAXIAEBUITypefaceList@2@AEAUtagLOGFONTW@@@Z; GEL::EffectText::GetLOGFONT(uint,GEL::ITypefaceList const &,tagLOGFONTW &)
0x1800bb68f  mov     ecx, cs:_tls_index
0x1800bb695  mov     rax, gs:58h
0x1800bb69e  mov     edx, 4
0x1800bb6a3  mov     rax, [rax+rcx*8]
0x1800bb6a7  mov     ecx, [rdx+rax]
0x1800bb6aa  cmp     cs:dword_180532AE8, ecx
0x1800bb6b0  jg      loc_1800BBACA
0x1800bb6b6  cmp     cs:dword_180532AEC, 0
0x1800bb6bd  jg      loc_1800BBFAF
0x1800bb6c3  movss   xmm0, dword ptr [rsp+230h+hdc+4]
0x1800bb6c9  mulss   xmm0, cs:__real@40400000
0x1800bb6d1  cvtps2pd xmm1, xmm0
0x1800bb6d4  movss   xmm0, dword ptr [r13+10h]
0x1800bb6da  cvtps2pd xmm0, xmm0
0x1800bb6dd  comisd  xmm0, xmm1
0x1800bb6e1  setnb   al
0x1800bb6e4  cmp     sil, 3
0x1800bb6e8  jnz     loc_1800BBA17
0x1800bb6ee  mov     rcx, [r15+0B0h]
0x1800bb6f5  mov     rax, [rcx]
0x1800bb6f8  mov     rax, [rax+10h]
0x1800bb6fc  call    cs:__guard_dispatch_icall_fptr
0x1800bb702  mov     rcx, rax
0x1800bb705  movss   xmm0, dword ptr [rax+14h]
0x1800bb70a  movss   xmm3, cs:__real@437f0000
0x1800bb712  mulss   xmm0, xmm3
0x1800bb716  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800bb71b  mov     dl, al
0x1800bb71d  movss   xmm0, dword ptr [rcx+8]
0x1800bb722  mulss   xmm0, xmm3
0x1800bb726  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800bb72b  movzx   r14d, al
0x1800bb72f  mov     byte ptr [rsp+230h+var_200+3], r14b
0x1800bb734  movss   xmm0, dword ptr [rcx+0Ch]
0x1800bb739  mulss   xmm0, xmm3
0x1800bb73d  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800bb742  mov     byte ptr [rsp+230h+var_200], al
0x1800bb746  movss   xmm0, dword ptr [rcx+10h]
0x1800bb74b  mulss   xmm0, xmm3
0x1800bb74f  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800bb754  mov     byte ptr [rsp+230h+var_200+1], al
0x1800bb758  cmp     dl, 0FFh
0x1800bb75b  jnz     loc_1800BC004
0x1800bb761  cmp     sil, 3
0x1800bb765  jnz     loc_1800BB89C
0x1800bb76b  mov     r9, r13; struct GEL::Font *
0x1800bb76e  mov     r8, [r15+0D0h]; struct GEL::ITextRun *
0x1800bb775  mov     rdx, [rsp+230h+var_1C8]; struct Frame *
0x1800bb77a  lea     rcx, [rbp+130h+x]; this
0x1800bb77e  call    ??0MarkupText@GEL@@QEAA@AEAVFrame@RenderStage@1@AEBUITextRun@1@AEBUFont@1@@Z; GEL::MarkupText::MarkupText(GEL::RenderStage::Frame &,GEL::ITextRun const &,GEL::Font const &)
0x1800bb783  mov     rdx, rdi; struct GEL::RenderStage *
0x1800bb786  lea     rcx, [rsp+230h+hdc+8]; this
0x1800bb78b  call    ??0StageDC@GEL@@QEAA@AEAVRenderStage@1@@Z; GEL::StageDC::StageDC(GEL::RenderStage &)
0x1800bb790  nop
0x1800bb791  xor     edx, edx; Val
0x1800bb793  lea     r8d, [rdx+5Ch]; Size
0x1800bb797  lea     rcx, [rbp+130h+var_120]; void *
0x1800bb79b  call    memset_0
0x1800bb7a0  lea     rdx, [rbp+130h+var_120]; struct tagLOGFONTW *
0x1800bb7a4  lea     rcx, [rbp+130h+var_C0]; struct tagLOGFONTW *
0x1800bb7a8  call    ?FixupLOGFONT@CHFont@Ofc@@SAXAEBUtagLOGFONTW@@AEAU3@@Z; Ofc::CHFont::FixupLOGFONT(tagLOGFONTW const &,tagLOGFONTW &)
0x1800bb7ad  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1800bb7b3  mov     r9, rax
0x1800bb7b6  mov     rcx, [rax]
0x1800bb7b9  mov     rax, [rcx+18h]
0x1800bb7bd  mov     r8b, 1
0x1800bb7c0  lea     rdx, [rbp+130h+var_120]
0x1800bb7c4  mov     rcx, r9
0x1800bb7c7  call    cs:__guard_dispatch_icall_fptr
0x1800bb7cd  mov     qword ptr [rbp+130h+xf.eDx], 0
0x1800bb7d5  mov     rcx, [rsp+230h+hdc+8]; hdc
0x1800bb7da  mov     qword ptr [rbp+130h+xf.eM21], rcx
0x1800bb7de  mov     qword ptr [rbp+130h+xf.eM11], rax
0x1800bb7e2  test    rcx, rcx
0x1800bb7e5  jz      short loc_1800BB7FE
0x1800bb7e7  test    rax, rax
0x1800bb7ea  jz      short loc_1800BB7FE
0x1800bb7ec  mov     rdx, rax; h
0x1800bb7ef  call    cs:__imp_SelectObject
0x1800bb7f5  mov     qword ptr [rbp+130h+xf.eDx], rax
0x1800bb7f9  mov     rcx, [rsp+230h+hdc+8]; hdc
0x1800bb7fe  movzx   r8d, byte ptr [rsp+230h+var_200]
0x1800bb804  shl     r8d, 8
0x1800bb808  movzx   eax, byte ptr [rsp+230h+var_200+1]
0x1800bb80d  shl     eax, 10h
0x1800bb810  or      r8d, eax
0x1800bb813  or      r8d, r14d
0x1800bb816  mov     edx, [r15+78h]
0x1800bb81a  call    sub_1800BD93C
0x1800bb81f  mov     rdx, [rsp+230h+hdc+8]
0x1800bb824  mov     rcx, r15
0x1800bb827  call    sub_1800ACB9C
0x1800bb82c  lea     rcx, [rbp+130h+xf]; this
0x1800bb830  call    ??1CHFont@Ofc@@QEAA@XZ; Ofc::CHFont::~CHFont(void)
0x1800bb835  lea     rcx, [rsp+230h+hdc+8]; this
0x1800bb83a  call    ?Empty@GpHDCHolder@Gfx@@QEAAXXZ; Gfx::GpHDCHolder::Empty(void)
0x1800bb83f  lea     rcx, [rbp+130h+x]; this
0x1800bb843  call    ?Close@MarkupText@GEL@@QEAAXXZ; GEL::MarkupText::Close(void)
0x1800bb848  jmp     loc_1800BBA10
0x1800bb850  cmp     sil, 5
0x1800bb854  jz      loc_1800BB643
0x1800bb85a  movsd   xmm0, qword ptr [rbx]
0x1800bb85e  andps   xmm0, xmm6
0x1800bb861  movsd   xmm1, cs:__real@3cd203af9ee75616
0x1800bb869  comisd  xmm1, xmm0
0x1800bb86d  ja      loc_1800BBAA1
0x1800bb873  movsd   xmm0, qword ptr [rbx+8]
0x1800bb878  andps   xmm0, xmm6
0x1800bb87b  comisd  xmm1, xmm0
0x1800bb87f  jbe     loc_1800BB643
0x1800bb885  movsd   xmm0, qword ptr [rbx+10h]
0x1800bb88a  andps   xmm0, xmm6
0x1800bb88d  comisd  xmm1, xmm0
0x1800bb891  ja      loc_1800BB64C
0x1800bb897  jmp     loc_1800BB643
0x1800bb89c  mov     rcx, [rdi+20h]
0x1800bb8a0  mov     rax, [rcx]
0x1800bb8a3  mov     rax, [rax+38h]
0x1800bb8a7  call    cs:__guard_dispatch_icall_fptr
0x1800bb8ad  xor     r9d, r9d
0x1800bb8b0  test    al, al
0x1800bb8b2  jnz     loc_1800BB76B
0x1800bb8b8  cmp     sil, 4
0x1800bb8bc  jnz     loc_1800BBAB8
0x1800bb8c2  movsd   xmm2, qword ptr [r15+0A0h]
0x1800bb8cb  movsd   xmm3, qword ptr [r15+90h]
0x1800bb8d4  movaps  xmm0, xmm2
0x1800bb8d7  subsd   xmm0, xmm3
0x1800bb8db  movsd   xmm1, cs:__real@40a0000000000000
0x1800bb8e3  comisd  xmm0, xmm1
0x1800bb8e7  jb      loc_1800BC01A
0x1800bb8ed  xor     al, al
0x1800bb8ef  mov     rcx, [rbp+130h+var_60]
0x1800bb8f6  xor     rcx, rsp; StackCookie
0x1800bb8f9  call    __security_check_cookie
0x1800bb8fe  lea     r11, [rsp+230h+var_30]
0x1800bb906  mov     rbx, [r11+40h]
0x1800bb90a  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bb90f  movaps  xmm7, xmmword ptr [r11-20h]
0x1800bb914  mov     rsp, r11
0x1800bb917  pop     r15
0x1800bb919  pop     r14
0x1800bb91b  pop     r13
0x1800bb91d  pop     r12
0x1800bb91f  pop     rdi
0x1800bb920  pop     rsi
0x1800bb921  pop     rbp
0x1800bb922  retn
0x1800bb923  mov     rsi, rdi
0x1800bb926  mov     [rsp+230h+hdc+8], rsi
0x1800bb92b  test    rsi, rsi
0x1800bb92e  jz      short loc_1800BB940
0x1800bb930  mov     rax, [rsi]
0x1800bb933  mov     rcx, rsi
0x1800bb936  mov     rax, [rax]
0x1800bb939  call    cs:__guard_dispatch_icall_fptr
0x1800bb93f  nop
0x1800bb940  mov     ecx, 30h ; '0'; this
0x1800bb945  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800bb94a  mov     rdi, rax
0x1800bb94d  test    rax, rax
0x1800bb950  jnz     loc_1800BBA56
0x1800bb956  test    rdi, rdi
0x1800bb959  jz      short loc_1800BB96A
0x1800bb95b  mov     rax, [rdi]
0x1800bb95e  mov     rcx, rdi
0x1800bb961  mov     rax, [rax]
0x1800bb964  call    cs:__guard_dispatch_icall_fptr
0x1800bb96a  mov     [rbp+130h+var_190], rdi
0x1800bb96e  mov     r9, r13; struct GEL::Font *
0x1800bb971  mov     r8, [r15+0D0h]; struct GEL::ITextRun *
0x1800bb978  mov     r12, [rsp+230h+var_1C8]
0x1800bb97d  mov     rdx, r12; struct Frame *
0x1800bb980  lea     rcx, [rsp+230h+var_1C8]; this
0x1800bb985  call    ??0MarkupText@GEL@@QEAA@AEAVFrame@RenderStage@1@AEBUITextRun@1@AEBUFont@1@@Z; GEL::MarkupText::MarkupText(GEL::RenderStage::Frame &,GEL::ITextRun const &,GEL::Font const &)
0x1800bb98a  mov     rdx, rdi; struct GEL::IEffect *
0x1800bb98d  mov     rcx, r12; this
0x1800bb990  call    ?Draw@Frame@RenderStage@GEL@@QEAAXAEBUIEffect@3@@Z; GEL::RenderStage::Frame::Draw(GEL::IEffect const &)
0x1800bb995  lea     rcx, [rsp+230h+var_1C8]; this
0x1800bb99a  call    ?Close@MarkupText@GEL@@QEAAXXZ; GEL::MarkupText::Close(void)
0x1800bb99f  nop
0x1800bb9a0  test    rsi, rsi
0x1800bb9a3  jz      short loc_1800BB9B6
0x1800bb9a5  mov     rax, [rsi]
0x1800bb9a8  mov     rcx, rsi
0x1800bb9ab  mov     rax, [rax+8]
0x1800bb9af  call    cs:__guard_dispatch_icall_fptr
0x1800bb9b5  nop
0x1800bb9b6  test    r14, r14
0x1800bb9b9  jz      short loc_1800BB9CC
0x1800bb9bb  mov     rax, [r14]
0x1800bb9be  mov     rcx, r14
0x1800bb9c1  mov     rax, [rax+8]
0x1800bb9c5  call    cs:__guard_dispatch_icall_fptr
0x1800bb9cb  nop
0x1800bb9cc  test    rbx, rbx
0x1800bb9cf  jz      short loc_1800BB9E2
0x1800bb9d1  mov     rax, [rbx]
0x1800bb9d4  mov     rcx, rbx
0x1800bb9d7  mov     rax, [rax+8]
0x1800bb9db  call    cs:__guard_dispatch_icall_fptr
0x1800bb9e1  nop
0x1800bb9e2  mov     rcx, [rbp+130h+var_128]
0x1800bb9e6  test    rcx, rcx
0x1800bb9e9  jz      short loc_1800BB9F2
0x1800bb9eb  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800bb9f1  nop
0x1800bb9f2  lea     rcx, [rbp+130h+var_1A0]; this
0x1800bb9f6  call    ?Reset@CDIBSection@Ofc@@QEAAXXZ; Ofc::CDIBSection::Reset(void)
0x1800bb9fb  test    rdi, rdi
0x1800bb9fe  jz      short loc_1800BBA10
0x1800bba00  mov     rdx, [rdi]
0x1800bba03  mov     rcx, rdi
0x1800bba06  mov     rax, [rdx+8]
0x1800bba0a  call    cs:__guard_dispatch_icall_fptr
0x1800bba10  mov     al, 1
0x1800bba12  jmp     loc_1800BB8EF
0x1800bba17  test    al, al
0x1800bba19  jnz     loc_1800BB8ED
0x1800bba1f  call    cs:__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ; Mso::Instance::GetSku(void)
0x1800bba25  cmp     sil, 4
0x1800bba29  jnz     loc_1800BB6EE
0x1800bba2f  cmp     eax, 4
0x1800bba32  jz      loc_1800BB6EE
0x1800bba38  mov     eax, dword ptr cs:xmmword_180523DC0+8
0x1800bba3e  xorps   xmm0, xmm0
0x1800bba41  cvtsi2ss xmm0, rax
0x1800bba46  comiss  xmm0, dword ptr [r13+10h]
0x1800bba4b  ja      loc_1800BB6EE
0x1800bba51  jmp     loc_1800BB8ED
0x1800bba56  mov     rcx, rdi
0x1800bba59  call    ??0?$TEffect@UIEffectAlphaReplaceBinary@GEL@@@GEL@@IEAA@XZ; GEL::TEffect<GEL::IEffectAlphaReplaceBinary>::TEffect<GEL::IEffectAlphaReplaceBinary>(void)
0x1800bba5e  mov     [rdi+28h], rsi
0x1800bba62  mov     rax, [rsi]
0x1800bba65  mov     rcx, rsi
0x1800bba68  mov     rax, [rax]
0x1800bba6b  call    cs:__guard_dispatch_icall_fptr
0x1800bba71  lea     rax, ??_7EffectNearestNeighborInterpolation@GEL@@6B?$TRefCountedImpl@UIEffectNearestNeighborInterpolation@GEL@@@Mso@@@; const GEL::EffectNearestNeighborInterpolation::`vftable'{for `Mso::TRefCountedImpl<GEL::IEffectNearestNeighborInterpolation>'}
0x1800bba78  mov     [rdi], rax
0x1800bba7b  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x1800bba82  mov     [rdi+10h], rax
0x1800bba86  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x1800bba8d  mov     [rdi+18h], rax
0x1800bba91  lea     rax, ??_7EffectNearestNeighborInterpolation@GEL@@6B@; const GEL::EffectNearestNeighborInterpolation::`vftable'
0x1800bba98  mov     [rdi+20h], rax
0x1800bba9c  jmp     loc_1800BB956
0x1800bbaa1  movsd   xmm0, qword ptr [rbx+18h]
0x1800bbaa6  andps   xmm0, xmm6
0x1800bbaa9  comisd  xmm1, xmm0
0x1800bbaad  ja      loc_1800BB64C
  ... truncated ...
```
