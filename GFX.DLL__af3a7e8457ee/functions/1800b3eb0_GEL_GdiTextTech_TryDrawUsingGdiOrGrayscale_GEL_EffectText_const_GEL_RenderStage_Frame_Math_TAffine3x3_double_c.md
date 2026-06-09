# GEL::GdiTextTech::TryDrawUsingGdiOrGrayscale(GEL::EffectText const &,GEL::RenderStage::Frame &,Math::TAffine3x3<double> const &,ARC::AlphaMode)

- ea: `0x1800b3eb0`
- end: `0x1800b493b`
- name: `?TryDrawUsingGdiOrGrayscale@GdiTextTech@GEL@@UEBA_NAEBVEffectText@2@AEAVFrame@RenderStage@2@AEBU?$TAffine3x3@N@Math@@W4AlphaMode@ARC@@@Z`
- size: `2699`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `broker_com_uri`

## callees

- `0x18000a5e0`
- `0x18000a64c`
- `0x180011710`
- `0x180015520`
- `0x18004c6d8`
- `0x1800504e7`
- `0x180055b26`
- `0x180056ee0`
- `0x1800573f0`
- `0x180064c50`
- `0x1800774c0`
- `0x1800786fc`
- `0x18007d3b4`
- `0x1800b2508`
- `0x1800b253c`
- `0x1800b2a1c`
- `0x1800b2a6c`
- `0x1800b2ac0`
- `0x1800b2b5c`
- `0x1800b3eb0`
- `0x1800b493c`
- `0x1800b4a28`
- `0x1800b4a64`
- `0x1800b4f00`
- `0x1800b5ff4`
- `0x1800b76b4`
- `0x1800ceb9c`
- `0x1800da93c`
- `0x1800dbf08`
- `0x1800e75f0`
- `0x180100f84`
- `0x180108a30`
- `0x18010de18`
- `0x18010e060`
- `0x1801cb134`
- `0x1801cb194`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b409d`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b46a9`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b409d`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b46a9`
- `Mso20Win32Client!__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ` at `0x1800b438f`
- `Mso20Win32Client!__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ` at `0x1800b438f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b4353`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b4353`
- `GDI32!DeleteDC` at `0x1800b4746`
- `GDI32!DeleteDC` at `0x1800b4746`
- `GDI32!SelectObject` at `0x1800b40df`
- `GDI32!SelectObject` at `0x1800b46e9`
- `GDI32!SelectObject` at `0x1800b473d`
- `GDI32!SelectObject` at `0x1800b40df`
- `GDI32!SelectObject` at `0x1800b46e9`
- `GDI32!SelectObject` at `0x1800b473d`
- `GDI32!SetWorldTransform` at `0x1800b4687`
- `GDI32!SetWorldTransform` at `0x1800b4687`
- `GDI32!SetGraphicsMode` at `0x1800b45ef`
- `GDI32!SetGraphicsMode` at `0x1800b45ef`
- `GDI32!SetWindowOrgEx` at `0x1800b45be`
- `GDI32!SetWindowOrgEx` at `0x1800b45be`
- `GDI32!GetStockObject` at `0x1800b45d1`
- `GDI32!GetStockObject` at `0x1800b45d1`
- `USER32!FillRect` at `0x1800b45e1`
- `USER32!FillRect` at `0x1800b45e1`

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
  unsigned __int64 v29; // rdx
  unsigned int v30; // r8d
  void *v31; // rax
  unsigned __int64 v32; // rdx
  unsigned int v33; // r8d
  unsigned __int64 v34; // rbx
  __int64 v35; // r14
  void *v36; // rax
  unsigned __int64 v37; // rdx
  unsigned int v38; // r8d
  __int64 v39; // rsi
  _QWORD *v40; // rax
  _QWORD *v41; // rdi
  GEL::RenderStage::Frame *v42; // r12
  void *v43; // rdx
  int Sku; // eax
  int v45; // r8d
  unsigned int v46; // edi
  __int64 v47; // r14
  __int64 v48; // rsi
  __int64 v49; // r12
  unsigned int j; // ebx
  LONG v51; // ecx
  LONG v52; // esi
  LONG v53; // r8d
  LONG v54; // r14d
  LONG top; // edx
  int v56; // esi
  int v57; // r14d
  const struct Ofc::CDIBSection *v58; // rdx
  HDC v59; // rdi
  HBRUSH StockObject; // rax
  double v61; // xmm6_8
  double v62; // xmm7_8
  double v63; // xmm6_8
  double v64; // xmm7_8
  double v65; // xmm6_8
  double v66; // xmm7_8
  Mso::GDIAssistant *v67; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *GDIAssistant; // rax
  __int64 v69; // r8
  void *v70; // rax
  unsigned int i; // edx
  int v72; // r12d
  char v73; // cl
  unsigned int v74; // eax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  LONG v80; // eax
  __int64 v81; // r9
  char v82; // cl
  const struct tagFONTSIGNATURE *v83; // rax
  unsigned __int8 v84; // [rsp+38h] [rbp-D0h]
  unsigned __int8 v85; // [rsp+39h] [rbp-CFh]
  char v86; // [rsp+3Ah] [rbp-CEh]
  unsigned __int8 v87; // [rsp+3Bh] [rbp-CDh]
  unsigned __int64 v88; // [rsp+40h] [rbp-C8h] BYREF
  float hdc; // [rsp+48h] [rbp-C0h] BYREF
  float hdc_4; // [rsp+4Ch] [rbp-BCh]
  HDC hdc_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  double right; // [rsp+60h] [rbp-A8h]
  double bottom; // [rsp+68h] [rbp-A0h]
  struct Frame *v94[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v95; // [rsp+80h] [rbp-88h] BYREF
  __int64 v96; // [rsp+88h] [rbp-80h]
  int v97; // [rsp+90h] [rbp-78h]
  HBITMAP v98[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v99; // [rsp+A8h] [rbp-60h]
  __m256i v100; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v101; // [rsp+D0h] [rbp-38h]
  __int64 v102; // [rsp+D8h] [rbp-30h]
  __int64 v103; // [rsp+E0h] [rbp-28h]
  RECT x; // [rsp+E8h] [rbp-20h] BYREF
  XFORM xf; // [rsp+F8h] [rbp-10h] BYREF
  Mso::Memory *v106; // [rsp+110h] [rbp+8h]
  struct tagLOGFONTW v107; // [rsp+118h] [rbp+10h] BYREF
  struct tagLOGFONTW v108; // [rsp+178h] [rbp+70h] BYREF

  v94[0] = a3;
  v7.lpVtbl = a3->lpVtbl;
  v99 = 0;
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
  memset_0(&v108, 0, sizeof(v108));
  v15 = (const struct GEL::Font *)(a2 + 72);
  GEL::EffectText::GetLOGFONT((GEL::EffectText *)a2, *(_DWORD *)(a2 + 92), AvailableTypefaces, &v108);
  if ( dword_18052EAB8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18052EAB8);
    if ( dword_18052EAB8 == -1 )
    {
      dword_18052EABC = Mso::Orapi::ReadValue<&_msoreg const OrapiData::Gfx::c_msoridGELFixUpCharSetForMetafiles>();
      Init_thread_footer(&dword_18052EAB8);
    }
  }
  if ( dword_18052EABC > 0
    && !(*(unsigned __int8 (__fastcall **)(const struct GEL::ITypefaceList *))(*(_QWORD *)AvailableTypefaces + 72LL))(AvailableTypefaces)
    && (*(unsigned __int8 (__fastcall **)(HRESULT (__stdcall *)(Frame *, UINT, LCID, ITypeInfo **)))(*(_QWORD *)v7.lpVtbl->GetTypeInfo + 56LL))(v7.lpVtbl->GetTypeInfo) )
  {
    v83 = (const struct tagFONTSIGNATURE *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 112LL))(*(_QWORD *)v15);
    v108.lfCharSet = GetCharSet(v83);
  }
  if ( DeviceType != 3 )
  {
    if ( *(float *)(a2 + 88) >= (double)(float)(hdc_4 * 3.0) )
      return 0;
    Sku = Mso::Instance::GetSku();
    if ( DeviceType == 4 && Sku != 4 && (float)SDWORD2(xmmword_18051FD40) <= *(float *)(a2 + 88) )
      return 0;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 176) + 16LL))(*(_QWORD *)(a2 + 176));
  Ofc::Round<long,float>(v16);
  v18 = Ofc::Round<long,float>(v17);
  v19 = v18;
  v87 = v18;
  v84 = Ofc::Round<long,float>(v20);
  v85 = Ofc::Round<long,float>(v21);
  if ( v22 != -1 && (!v11 || v22) )
    return 0;
  if ( DeviceType != 3
    && !(*(unsigned __int8 (__fastcall **)(HRESULT (__stdcall *)(Frame *, UINT, LCID, ITypeInfo **)))(*(_QWORD *)v7.lpVtbl->GetTypeInfo + 56LL))(v7.lpVtbl->GetTypeInfo)
    && (DeviceType == 4 || a5 != 3) )
  {
    if ( *(double *)(a2 + 160) - *(double *)(a2 + 144) < 2048.0
      && *(double *)(a2 + 168) - *(double *)(a2 + 152) < 2048.0 )
    {
      v72 = (1920103 * v85 + 5036060 * v19 + 9886846 * v84) >> 24;
      if ( COERCE_DOUBLE(*(_QWORD *)(a4 + 8) & v12) > COERCE_DOUBLE(*(_QWORD *)a4 & v12)
        || (v73 = 0, COERCE_DOUBLE(*(_QWORD *)(a4 + 16) & v12) > COERCE_DOUBLE(*(_QWORD *)(a4 + 24) & v12)) )
      {
        v73 = 1;
      }
      v86 = v73;
      v52 = ((__int64 (*)(void))Ofc::Round<long,double>)();
      v74 = ((__int64 (*)(void))Ofc::Round<long,double>)();
      v54 = Ofc::Round<long,double>(v76, v75, v74);
      v80 = Ofc::Round<long,double>(v78, v77, v79);
      top = v80;
      if ( v82 )
      {
        x.left = v53;
        x.top = v80;
        x.right = v52;
        x.bottom = v54;
      }
      else
      {
        v51 = v52;
        v52 = v54;
        x.left = v80;
        x.top = v53;
        x.right = v54;
        x.bottom = v51;
        v53 = v80;
        v54 = v51;
        top = x.top;
      }
      v56 = v52 - v53;
      v57 = v54 - top;
      if ( (unsigned int)(v56 - 1) <= 0x7FE && (unsigned int)(v57 - 1) <= 0x7FE )
      {
        v95 = v81;
        v96 = v81;
        v97 = v81;
        *(_OWORD *)v98 = 0;
        v88 = __PAIR64__(v57, v56);
        Gfx::TDIBSection<ARC::Pixel32>::SetSize(&v95, &v88);
        GEL::ValidateDIBSection((GEL *)v98, v58);
        *(_OWORD *)hdc_8 = 0;
        Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc_8, 0, v98[0]);
        v59 = hdc_8[0];
        SetWindowOrgEx(hdc_8[0], x.left, x.top, 0);
        StockObject = (HBRUSH)GetStockObject((unsigned __int8)v72 > 0xD4u ? 4 : 0);
        FillRect(v59, &x, StockObject);
        SetGraphicsMode(v59, 2);
        v61 = *(double *)(a4 + 40);
        v62 = *(double *)(a4 + 32);
        v63 = v61 - floor_0(v61);
        v64 = v62 - floor_0(v62);
        if ( v86 )
        {
          v66 = v64 * *(double *)(a4 + 16);
          v65 = v63 * *(double *)(a4 + 8);
          *(__m128i *)v100.m256i_i8 = _mm_load_si128((const __m128i *)&_xmm);
          *(__m128i *)&v100.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
          v101 = *(_QWORD *)&v65 ^ _xmm;
          v102 = *(_QWORD *)&v66 ^ _xmm;
          *(__m128i *)&xf.eM11 = _mm_load_si128((const __m128i *)&_xmm);
        }
        else
        {
          v65 = v63 * *(double *)(a4 + 24);
          v66 = v64 * *(double *)a4;
          *(double *)&v100.m256i_i64[3] = DOUBLE_1_0;
          *(double *)v100.m256i_i64 = DOUBLE_1_0;
          *(_OWORD *)&v100.m256i_u64[1] = 0;
          v101 = *(_QWORD *)&v66 ^ _xmm;
          v102 = *(_QWORD *)&v65 ^ _xmm;
          *(__m128i *)&xf.eM11 = _mm_load_si128((const __m128i *)&_xmm);
        }
        xf.eDx = v66;
        xf.eDy = v65;
        SetWorldTransform(v59, &xf);
        memset_0(&v107, 0, sizeof(v107));
        Ofc::CHFont::FixupLOGFONT(&v108, &v107);
        GDIAssistant = Mso::GDIAssistant::GetGDIAssistant(v67);
        LOBYTE(v69) = 1;
        v70 = (void *)(*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, struct tagLOGFONTW *, __int64))(*(_QWORD *)GDIAssistant + 24LL))(
                        GDIAssistant,
                        &v107,
                        v69);
        *(_QWORD *)&xf.eDx = 0;
        *(_QWORD *)&xf.eM21 = v59;
        *(_QWORD *)&xf.eM11 = v70;
        if ( v59 && v70 )
          *(_QWORD *)&xf.eDx = SelectObject(v59, v70);
        sub_1800B2A6C(v59);
        sub_1800B76B4(a2, v59);
        Ofc::CHFont::~CHFont((Ofc::CHFont *)&xf);
        if ( v59 )
        {
          if ( hdc_8[1] )
            SelectObject(v59, hdc_8[1]);
          DeleteDC(v59);
        }
        v46 = 0;
        memset(&xf, 0, 20);
        v106 = 0;
        v88 = __PAIR64__(v57, v56);
        ARC::TPixelBuffer<ARC::Pixel32>::SetSize(&xf, &v88);
        LOBYTE(v88) = v85;
        BYTE1(v88) = v84;
        BYTE2(v88) = v87;
        BYTE3(v88) = (unsigned __int8)v72 <= 0xD4u;
        for ( i = 0; i < 2; ++i )
        {
          if ( *((_DWORD *)&xf.eM21 + i) != *((_DWORD *)&v96 + i) )
            goto LABEL_22;
        }
        v48 = v95;
        v49 = *(_QWORD *)&xf.eM11;
        for ( j = 0; j < LODWORD(xf.eM22); ++j )
        {
          v47 = v48;
          while ( v46 < LODWORD(xf.eM21) )
          {
            GEL::LuminanceToPremultipliedAlphaCopy::operator()(&v88, v47 + v49 - v48, v47);
            ++v46;
            v47 += 4;
          }
          v48 += v97;
          v49 += SLODWORD(xf.eDx);
          v46 = 0;
        }
        v15 = (const struct GEL::Font *)(a2 + 72);
LABEL_22:
        GEL::IImage::Create<ARC::Pixel32,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>>>(
          (unsigned int)&v88,
          (unsigned int)&xf,
          v45,
          1,
          (__int64)&hdc);
        v31 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x80, v29, v30);
        v34 = v88;
        if ( v31 )
        {
          *(double *)hdc_8 = (double)x.left;
          *(double *)&hdc_8[1] = (double)x.top;
          right = (double)x.right;
          bottom = (double)x.bottom;
          v35 = GEL::EffectImage::EffectImage(v31, v88, hdc_8);
        }
        else
        {
          v35 = 0;
        }
        v103 = v35;
        if ( v35 )
          (**(void (__fastcall ***)(__int64))v35)(v35);
        v36 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v32, v33);
        if ( v36 )
          v39 = GEL::EffectTransform::EffectTransform(v36, v35, &v100);
        else
          v39 = 0;
        hdc_8[0] = (HDC)v39;
        if ( v39 )
          (**(void (__fastcall ***)(__int64))v39)(v39);
        v40 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v37, v38);
        v41 = v40;
        if ( v40 )
        {
          GEL::TEffect<GEL::IEffectAlphaReplaceBinary>::TEffect<GEL::IEffectAlphaReplaceBinary>(v40);
          v41[5] = v39;
          (**(void (__fastcall ***)(__int64))v39)(v39);
          *v41 = &GEL::EffectNearestNeighborInterpolation::`vftable'{for `Mso::TRefCountedImpl<GEL::IEffectNearestNeighborInterpolation>'};
          v41[2] = &GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'};
          v41[3] = &GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'};
          v41[4] = &GEL::EffectNearestNeighborInterpolation::`vftable';
        }
        if ( v41 )
          (*(void (__fastcall **)(_QWORD *))*v41)(v41);
        v99 = v41;
        v42 = (GEL::RenderStage::Frame *)v94[0];
        GEL::MarkupText::MarkupText((GEL::MarkupText *)v94, v94[0], *(const struct GEL::ITextRun **)(a2 + 208), v15);
        GEL::RenderStage::Frame::Draw(v42, (const struct GEL::IEffect *)v41);
        GEL::MarkupText::Close((GEL::MarkupText *)v94);
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
        if ( v34 )
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v34 + 8LL))(v34);
        if ( v106 )
          Mso::Memory::Free(v106, v43);
        Ofc::CDIBSection::Reset((Ofc::CDIBSection *)v98);
        if ( v41 )
          (*(void (__fastcall **)(_QWORD *))(*v41 + 8LL))(v41);
        return 1;
      }
    }
    return 0;
  }
  GEL::MarkupText::MarkupText(
    (GEL::MarkupText *)&x,
    v94[0],
    *(const struct GEL::ITextRun **)(a2 + 208),
    (const struct GEL::Font *)(a2 + 72));
  GEL::StageDC::StageDC((GEL::StageDC *)hdc_8, (struct GEL::RenderStage *)v7.lpVtbl);
  memset_0(&v107, 0, sizeof(v107));
  Ofc::CHFont::FixupLOGFONT(&v108, &v107);
  v24 = Mso::GDIAssistant::GetGDIAssistant(v23);
  LOBYTE(v25) = 1;
  v26 = (void *)(*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, struct tagLOGFONTW *, __int64))(*(_QWORD *)v24 + 24LL))(
                  v24,
                  &v107,
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
  sub_1800B2A6C(v27);
  sub_1800B76B4(a2, hdc_8[0]);
  Ofc::CHFont::~CHFont((Ofc::CHFont *)&xf);
  Gfx::GpHDCHolder::Empty((Gfx::GpHDCHolder *)hdc_8);
  GEL::MarkupText::Close((GEL::MarkupText *)&x);
  return 1;
}

```

## disassembly

```asm
0x1800b3eb0  mov     rax, rsp
0x1800b3eb3  mov     [rax+8], rbx
0x1800b3eb7  push    rbp
0x1800b3eb8  push    rsi
0x1800b3eb9  push    rdi
0x1800b3eba  push    r12
0x1800b3ebc  push    r13
0x1800b3ebe  push    r14
0x1800b3ec0  push    r15
0x1800b3ec2  lea     rbp, [rax-138h]
0x1800b3ec9  sub     rsp, 200h
0x1800b3ed0  movaps  xmmword ptr [rax-48h], xmm6
0x1800b3ed4  movaps  xmmword ptr [rax-58h], xmm7
0x1800b3ed8  mov     rax, cs:__security_cookie
0x1800b3edf  xor     rax, rsp
0x1800b3ee2  mov     [rbp+130h+var_60], rax
0x1800b3ee9  mov     rbx, r9
0x1800b3eec  mov     [rsp+230h+var_1C8], r8
0x1800b3ef1  mov     r15, rdx
0x1800b3ef4  mov     rdi, [r8]
0x1800b3ef7  mov     [rbp+130h+var_190], 0
0x1800b3eff  mov     rcx, rdi
0x1800b3f02  call    ?GetDeviceType@RenderStage@GEL@@QEBA?AW4DeviceType@2@XZ; GEL::RenderStage::GetDeviceType(void)
0x1800b3f07  mov     sil, al
0x1800b3f0a  mov     rcx, rdi; this
0x1800b3f0d  call    ?GetAvailableTypefaces@RenderStage@GEL@@QEBAAEBUITypefaceList@2@XZ; GEL::RenderStage::GetAvailableTypefaces(void)
0x1800b3f12  mov     r14, rax
0x1800b3f15  call    ?IsInTransparentMarkup@EffectTransparentMarkup@GEL@@SA_NXZ; GEL::EffectTransparentMarkup::IsInTransparentMarkup(void)
0x1800b3f1a  mov     r12b, al
0x1800b3f1d  movdqa  xmm6, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1800b3f25  cmp     qword ptr [rdi+0B0h], 0
0x1800b3f2d  jz      loc_1800B41C7
0x1800b3f33  test    r12b, r12b
0x1800b3f36  jz      loc_1800B4191
0x1800b3f3c  mov     rcx, rdi
0x1800b3f3f  call    ?GetDPI@RenderStage@GEL@@QEBAAEBV?$TConvertibleDPI2@M@Gfx@@XZ; GEL::RenderStage::GetDPI(void)
0x1800b3f44  movss   xmm1, dword ptr [rax+4]
0x1800b3f49  movss   xmm0, dword ptr [rax]
0x1800b3f4d  movss   dword ptr [rsp+230h+hdc], xmm0
0x1800b3f53  movss   dword ptr [rsp+230h+hdc+4], xmm1
0x1800b3f59  xor     edx, edx; Val
0x1800b3f5b  lea     r8d, [rdx+5Ch]; Size
0x1800b3f5f  lea     rcx, [rbp+130h+var_C0]; void *
0x1800b3f63  call    memset_0
0x1800b3f68  lea     r13, [r15+48h]
0x1800b3f6c  lea     r9, [rbp+130h+var_C0]; struct tagLOGFONTW *
0x1800b3f70  mov     r8, r14; struct GEL::ITypefaceList *
0x1800b3f73  mov     edx, [r13+14h]; unsigned int
0x1800b3f77  mov     rcx, r15; this
0x1800b3f7a  call    ?GetLOGFONT@EffectText@GEL@@UEBAXIAEBUITypefaceList@2@AEAUtagLOGFONTW@@@Z; GEL::EffectText::GetLOGFONT(uint,GEL::ITypefaceList const &,tagLOGFONTW &)
0x1800b3f7f  mov     ecx, cs:_tls_index
0x1800b3f85  mov     rax, gs:58h
0x1800b3f8e  mov     edx, 4
0x1800b3f93  mov     rax, [rax+rcx*8]
0x1800b3f97  mov     ecx, [rdx+rax]
0x1800b3f9a  cmp     cs:dword_18052EAB8, ecx
0x1800b3fa0  jg      loc_1800B448E
0x1800b3fa6  cmp     cs:dword_18052EABC, 0
0x1800b3fad  jg      loc_1800B48A7
0x1800b3fb3  movss   xmm0, dword ptr [rsp+230h+hdc+4]
0x1800b3fb9  mulss   xmm0, cs:__real@40400000
0x1800b3fc1  cvtps2pd xmm1, xmm0
0x1800b3fc4  movss   xmm0, dword ptr [r13+10h]
0x1800b3fca  cvtps2pd xmm0, xmm0
0x1800b3fcd  comisd  xmm0, xmm1
0x1800b3fd1  setnb   al
0x1800b3fd4  cmp     sil, 3
0x1800b3fd8  jnz     loc_1800B4387
0x1800b3fde  mov     rcx, [r15+0B0h]
0x1800b3fe5  mov     rax, [rcx]
0x1800b3fe8  mov     rax, [rax+10h]
0x1800b3fec  call    cs:__guard_dispatch_icall_fptr
0x1800b3ff2  mov     rcx, rax
0x1800b3ff5  movss   xmm0, dword ptr [rax+14h]
0x1800b3ffa  movss   xmm3, cs:__real@437f0000
0x1800b4002  mulss   xmm0, xmm3
0x1800b4006  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b400b  mov     dl, al
0x1800b400d  movss   xmm0, dword ptr [rcx+8]
0x1800b4012  mulss   xmm0, xmm3
0x1800b4016  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b401b  movzx   r14d, al
0x1800b401f  mov     byte ptr [rsp+230h+var_200+3], r14b
0x1800b4024  movss   xmm0, dword ptr [rcx+0Ch]
0x1800b4029  mulss   xmm0, xmm3
0x1800b402d  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b4032  mov     byte ptr [rsp+230h+var_200], al
0x1800b4036  movss   xmm0, dword ptr [rcx+10h]
0x1800b403b  mulss   xmm0, xmm3
0x1800b403f  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b4044  mov     byte ptr [rsp+230h+var_200+1], al
0x1800b4048  cmp     dl, 0FFh
0x1800b404b  jnz     loc_1800B48FC
0x1800b4051  cmp     sil, 3
0x1800b4055  jnz     loc_1800B4140
0x1800b405b  mov     r9, r13; struct GEL::Font *
0x1800b405e  mov     r8, [r15+0D0h]; struct GEL::ITextRun *
0x1800b4065  mov     rdx, [rsp+230h+var_1C8]; struct Frame *
0x1800b406a  lea     rcx, [rbp+130h+x]; this
0x1800b406e  call    ??0MarkupText@GEL@@QEAA@AEAVFrame@RenderStage@1@AEBUITextRun@1@AEBUFont@1@@Z; GEL::MarkupText::MarkupText(GEL::RenderStage::Frame &,GEL::ITextRun const &,GEL::Font const &)
0x1800b4073  mov     rdx, rdi; struct GEL::RenderStage *
0x1800b4076  lea     rcx, [rsp+230h+hdc+8]; this
0x1800b407b  call    ??0StageDC@GEL@@QEAA@AEAVRenderStage@1@@Z; GEL::StageDC::StageDC(GEL::RenderStage &)
0x1800b4080  nop
0x1800b4081  xor     edx, edx; Val
0x1800b4083  lea     r8d, [rdx+5Ch]; Size
0x1800b4087  lea     rcx, [rbp+130h+var_120]; void *
0x1800b408b  call    memset_0
0x1800b4090  lea     rdx, [rbp+130h+var_120]; struct tagLOGFONTW *
0x1800b4094  lea     rcx, [rbp+130h+var_C0]; struct tagLOGFONTW *
0x1800b4098  call    ?FixupLOGFONT@CHFont@Ofc@@SAXAEBUtagLOGFONTW@@AEAU3@@Z; Ofc::CHFont::FixupLOGFONT(tagLOGFONTW const &,tagLOGFONTW &)
0x1800b409d  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1800b40a3  mov     r9, rax
0x1800b40a6  mov     rcx, [rax]
0x1800b40a9  mov     rax, [rcx+18h]
0x1800b40ad  mov     r8b, 1
0x1800b40b0  lea     rdx, [rbp+130h+var_120]
0x1800b40b4  mov     rcx, r9
0x1800b40b7  call    cs:__guard_dispatch_icall_fptr
0x1800b40bd  mov     qword ptr [rbp+130h+xf.eDx], 0
0x1800b40c5  mov     rcx, [rsp+230h+hdc+8]; hdc
0x1800b40ca  mov     qword ptr [rbp+130h+xf.eM21], rcx
0x1800b40ce  mov     qword ptr [rbp+130h+xf.eM11], rax
0x1800b40d2  test    rcx, rcx
0x1800b40d5  jz      short loc_1800B40EE
0x1800b40d7  test    rax, rax
0x1800b40da  jz      short loc_1800B40EE
0x1800b40dc  mov     rdx, rax; h
0x1800b40df  call    cs:__imp_SelectObject
0x1800b40e5  mov     qword ptr [rbp+130h+xf.eDx], rax
0x1800b40e9  mov     rcx, [rsp+230h+hdc+8]; hdc
0x1800b40ee  movzx   r8d, byte ptr [rsp+230h+var_200]
0x1800b40f4  shl     r8d, 8
0x1800b40f8  movzx   eax, byte ptr [rsp+230h+var_200+1]
0x1800b40fd  shl     eax, 10h
0x1800b4100  or      r8d, eax
0x1800b4103  or      r8d, r14d
0x1800b4106  mov     edx, [r15+78h]
0x1800b410a  call    sub_1800B2A6C
0x1800b410f  mov     rdx, [rsp+230h+hdc+8]
0x1800b4114  mov     rcx, r15
0x1800b4117  call    sub_1800B76B4
0x1800b411c  lea     rcx, [rbp+130h+xf]; this
0x1800b4120  call    ??1CHFont@Ofc@@QEAA@XZ; Ofc::CHFont::~CHFont(void)
0x1800b4125  lea     rcx, [rsp+230h+hdc+8]; this
0x1800b412a  call    ?Empty@GpHDCHolder@Gfx@@QEAAXXZ; Gfx::GpHDCHolder::Empty(void)
0x1800b412f  lea     rcx, [rbp+130h+x]; this
0x1800b4133  call    ?Close@MarkupText@GEL@@QEAAXXZ; GEL::MarkupText::Close(void)
0x1800b4138  jmp     loc_1800B4378
0x1800b4140  mov     rcx, [rdi+20h]
0x1800b4144  mov     rax, [rcx]
0x1800b4147  mov     rax, [rax+38h]
0x1800b414b  call    cs:__guard_dispatch_icall_fptr
0x1800b4151  xor     r9d, r9d
0x1800b4154  test    al, al
0x1800b4156  jnz     loc_1800B405B
0x1800b415c  cmp     sil, 4
0x1800b4160  jnz     loc_1800B447C
0x1800b4166  movsd   xmm2, qword ptr [r15+0A0h]
0x1800b416f  movsd   xmm3, qword ptr [r15+90h]
0x1800b4178  movaps  xmm0, xmm2
0x1800b417b  subsd   xmm0, xmm3
0x1800b417f  movsd   xmm1, cs:__real@40a0000000000000
0x1800b4187  comisd  xmm0, xmm1
0x1800b418b  jb      loc_1800B4912
0x1800b4191  xor     al, al
0x1800b4193  mov     rcx, [rbp+130h+var_60]
0x1800b419a  xor     rcx, rsp; StackCookie
0x1800b419d  call    __security_check_cookie
0x1800b41a2  lea     r11, [rsp+230h+var_30]
0x1800b41aa  mov     rbx, [r11+40h]
0x1800b41ae  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b41b3  movaps  xmm7, xmmword ptr [r11-20h]
0x1800b41b8  mov     rsp, r11
0x1800b41bb  pop     r15
0x1800b41bd  pop     r14
0x1800b41bf  pop     r13
0x1800b41c1  pop     r12
0x1800b41c3  pop     rdi
0x1800b41c4  pop     rsi
0x1800b41c5  pop     rbp
0x1800b41c6  retn
0x1800b41c7  cmp     sil, 5
0x1800b41cb  jz      loc_1800B3F33
0x1800b41d1  movsd   xmm0, qword ptr [rbx]
0x1800b41d5  andps   xmm0, xmm6
0x1800b41d8  movsd   xmm1, cs:__real@3cd203af9ee75616
0x1800b41e0  comisd  xmm1, xmm0
0x1800b41e4  ja      loc_1800B4465
0x1800b41ea  movsd   xmm0, qword ptr [rbx+8]
0x1800b41ef  andps   xmm0, xmm6
0x1800b41f2  comisd  xmm1, xmm0
0x1800b41f6  jbe     loc_1800B3F33
0x1800b41fc  movsd   xmm0, qword ptr [rbx+10h]
0x1800b4201  andps   xmm0, xmm6
0x1800b4204  comisd  xmm1, xmm0
0x1800b4208  ja      loc_1800B3F3C
0x1800b420e  jmp     loc_1800B3F33
0x1800b4213  lea     r13, [r15+48h]
0x1800b4217  lea     rax, [rsp+230h+hdc]
0x1800b421c  mov     [rsp+230h+var_210], rax
0x1800b4221  mov     r9d, 1
0x1800b4227  lea     rdx, [rbp+130h+xf]
0x1800b422b  lea     rcx, [rsp+230h+var_1F8]
0x1800b4230  call    ??$Create@UPixel32@ARC@@U?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEBV?$TPixelMap@UPixel32@ARC@@@ARC@@W4PixelFormat@Gfx@@W4AlphaMode@5@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@@Z; GEL::IImage::Create<ARC::Pixel32,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>>>(ARC::TPixelMap<ARC::Pixel32> const &,Gfx::PixelFormat,ARC::AlphaMode,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &)
0x1800b4235  mov     ecx, 80h; this
0x1800b423a  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800b423f  mov     rbx, [rsp+230h+var_1F8]
0x1800b4244  test    rax, rax
0x1800b4247  jnz     loc_1800B4411
0x1800b424d  mov     r14, rdi
0x1800b4250  mov     [rbp+130h+var_158], r14
0x1800b4254  test    r14, r14
0x1800b4257  jz      short loc_1800B4269
0x1800b4259  mov     rax, [r14]
0x1800b425c  mov     rcx, r14
0x1800b425f  mov     rax, [rax]
0x1800b4262  call    cs:__guard_dispatch_icall_fptr
0x1800b4268  nop
0x1800b4269  mov     ecx, 60h ; '`'; this
0x1800b426e  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800b4273  test    rax, rax
0x1800b4276  jz      loc_1800B437F
0x1800b427c  lea     r8, [rbp+130h+var_188]
0x1800b4280  mov     rdx, r14
0x1800b4283  mov     rcx, rax
0x1800b4286  call    ??0EffectTransform@GEL@@QEAA@AEBUIEffect@1@AEBU?$TAffine3x3@N@Math@@@Z; GEL::EffectTransform::EffectTransform(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x1800b428b  mov     rsi, rax
0x1800b428e  mov     [rsp+230h+hdc+8], rsi
0x1800b4293  test    rsi, rsi
0x1800b4296  jz      short loc_1800B42A8
0x1800b4298  mov     rax, [rsi]
0x1800b429b  mov     rcx, rsi
0x1800b429e  mov     rax, [rax]
0x1800b42a1  call    cs:__guard_dispatch_icall_fptr
0x1800b42a7  nop
0x1800b42a8  mov     ecx, 30h ; '0'; this
0x1800b42ad  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800b42b2  mov     rdi, rax
0x1800b42b5  test    rax, rax
0x1800b42b8  jnz     loc_1800B43C6
0x1800b42be  test    rdi, rdi
0x1800b42c1  jz      short loc_1800B42D2
0x1800b42c3  mov     rax, [rdi]
0x1800b42c6  mov     rcx, rdi
0x1800b42c9  mov     rax, [rax]
0x1800b42cc  call    cs:__guard_dispatch_icall_fptr
0x1800b42d2  mov     [rbp+130h+var_190], rdi
0x1800b42d6  mov     r9, r13; struct GEL::Font *
0x1800b42d9  mov     r8, [r15+0D0h]; struct GEL::ITextRun *
0x1800b42e0  mov     r12, [rsp+230h+var_1C8]
0x1800b42e5  mov     rdx, r12; struct Frame *
0x1800b42e8  lea     rcx, [rsp+230h+var_1C8]; this
0x1800b42ed  call    ??0MarkupText@GEL@@QEAA@AEAVFrame@RenderStage@1@AEBUITextRun@1@AEBUFont@1@@Z; GEL::MarkupText::MarkupText(GEL::RenderStage::Frame &,GEL::ITextRun const &,GEL::Font const &)
0x1800b42f2  mov     rdx, rdi; struct GEL::IEffect *
0x1800b42f5  mov     rcx, r12; this
0x1800b42f8  call    ?Draw@Frame@RenderStage@GEL@@QEAAXAEBUIEffect@3@@Z; GEL::RenderStage::Frame::Draw(GEL::IEffect const &)
0x1800b42fd  lea     rcx, [rsp+230h+var_1C8]; this
0x1800b4302  call    ?Close@MarkupText@GEL@@QEAAXXZ; GEL::MarkupText::Close(void)
0x1800b4307  nop
0x1800b4308  test    rsi, rsi
0x1800b430b  jz      short loc_1800B431E
0x1800b430d  mov     rax, [rsi]
0x1800b4310  mov     rcx, rsi
0x1800b4313  mov     rax, [rax+8]
0x1800b4317  call    cs:__guard_dispatch_icall_fptr
0x1800b431d  nop
0x1800b431e  test    r14, r14
0x1800b4321  jz      short loc_1800B4334
0x1800b4323  mov     rax, [r14]
0x1800b4326  mov     rcx, r14
0x1800b4329  mov     rax, [rax+8]
0x1800b432d  call    cs:__guard_dispatch_icall_fptr
0x1800b4333  nop
0x1800b4334  test    rbx, rbx
0x1800b4337  jz      short loc_1800B434A
0x1800b4339  mov     rax, [rbx]
0x1800b433c  mov     rcx, rbx
0x1800b433f  mov     rax, [rax+8]
0x1800b4343  call    cs:__guard_dispatch_icall_fptr
0x1800b4349  nop
0x1800b434a  mov     rcx, [rbp+130h+var_128]
0x1800b434e  test    rcx, rcx
0x1800b4351  jz      short loc_1800B435A
0x1800b4353  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800b4359  nop
0x1800b435a  lea     rcx, [rbp+130h+var_1A0]; this
0x1800b435e  call    ?Reset@CDIBSection@Ofc@@QEAAXXZ; Ofc::CDIBSection::Reset(void)
0x1800b4363  test    rdi, rdi
0x1800b4366  jz      short loc_1800B4378
0x1800b4368  mov     rdx, [rdi]
0x1800b436b  mov     rcx, rdi
0x1800b436e  mov     rax, [rdx+8]
0x1800b4372  call    cs:__guard_dispatch_icall_fptr
0x1800b4378  mov     al, 1
0x1800b437a  jmp     loc_1800B4193
0x1800b437f  mov     rsi, rdi
0x1800b4382  jmp     loc_1800B428E
0x1800b4387  test    al, al
0x1800b4389  jnz     loc_1800B4191
  ... truncated ...
```
