# GEL::GdiTextTech::TryDrawUsingGdiOrGrayscale(GEL::EffectGlyphs const &,GEL::RenderStage::Frame &,Math::TAffine3x3<double> const &,ARC::AlphaMode)

- ea: `0x1800b3430`
- end: `0x1800b3eaf`
- name: `?TryDrawUsingGdiOrGrayscale@GdiTextTech@GEL@@UEBA_NAEBVEffectGlyphs@2@AEAVFrame@RenderStage@2@AEBU?$TAffine3x3@N@Math@@W4AlphaMode@ARC@@@Z`
- size: `2687`
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
- `0x1800b3430`
- `0x1800b493c`
- `0x1800b4a28`
- `0x1800b4a64`
- `0x1800b5ff4`
- `0x1800b6d60`
- `0x1800b7820`
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

- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b361d`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b3a4b`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b361d`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1800b3a4b`
- `Mso20Win32Client!__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ` at `0x1800b37a6`
- `Mso20Win32Client!__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ` at `0x1800b37a6`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b3c8c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800b3c8c`
- `GDI32!DeleteDC` at `0x1800b3ae2`
- `GDI32!DeleteDC` at `0x1800b3ae2`
- `GDI32!SelectObject` at `0x1800b365f`
- `GDI32!SelectObject` at `0x1800b3a8b`
- `GDI32!SelectObject` at `0x1800b3ad9`
- `GDI32!SelectObject` at `0x1800b365f`
- `GDI32!SelectObject` at `0x1800b3a8b`
- `GDI32!SelectObject` at `0x1800b3ad9`
- `GDI32!SetWorldTransform` at `0x1800b3a29`
- `GDI32!SetWorldTransform` at `0x1800b3a29`
- `GDI32!SetGraphicsMode` at `0x1800b3991`
- `GDI32!SetGraphicsMode` at `0x1800b3991`
- `GDI32!SetWindowOrgEx` at `0x1800b3960`
- `GDI32!SetWindowOrgEx` at `0x1800b3960`
- `GDI32!GetStockObject` at `0x1800b3973`
- `GDI32!GetStockObject` at `0x1800b3973`
- `USER32!FillRect` at `0x1800b3983`
- `USER32!FillRect` at `0x1800b3983`

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
  struct Mso::GDIAssistant::IGDIAssistant *GDIAssistant; // rax
  __int64 v25; // r8
  void *v26; // rax
  HDC v27; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  int Sku; // eax
  __int64 v32; // rcx
  int v33; // r12d
  LONG v34; // esi
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  LONG v41; // r14d
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  LONG v45; // eax
  LONG v46; // r8d
  __int64 v47; // r9
  LONG top; // edx
  char v49; // cl
  int v50; // esi
  int v51; // r14d
  const struct Ofc::CDIBSection *v52; // rdx
  HDC v53; // rdi
  HBRUSH StockObject; // rax
  double v55; // xmm6_8
  double v56; // xmm7_8
  double v57; // xmm6_8
  double v58; // xmm7_8
  double v59; // xmm6_8
  double v60; // xmm7_8
  Mso::GDIAssistant *v61; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *v62; // rax
  __int64 v63; // r8
  void *v64; // rax
  unsigned int v65; // edi
  int v66; // r8d
  unsigned int i; // edx
  __int64 v68; // rsi
  __int64 v69; // r12
  unsigned int j; // ebx
  unsigned __int64 v71; // rdx
  unsigned int v72; // r8d
  void *v73; // rax
  unsigned __int64 v74; // rdx
  unsigned int v75; // r8d
  unsigned __int64 v76; // rbx
  __int64 v77; // r14
  void *v78; // rax
  unsigned __int64 v79; // rdx
  unsigned int v80; // r8d
  __int64 v81; // rsi
  _QWORD *v82; // rax
  _QWORD *v83; // rdi
  GEL::RenderStage::Frame *v84; // r12
  void *v85; // rdx
  __int64 v86; // r14
  LONG v87; // ecx
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
  if ( !v7.lpVtbl[1].GetTypeInfo
    && DeviceType != 5
    && (COERCE_DOUBLE(*(_QWORD *)a4 & v12) < 1.0e-15 && COERCE_DOUBLE(*(_QWORD *)(a4 + 24) & v12) < 1.0e-15
     || COERCE_DOUBLE(*(_QWORD *)(a4 + 8) & v12) < 1.0e-15 && COERCE_DOUBLE(*(_QWORD *)(a4 + 16) & v12) < 1.0e-15)
    || v10 )
  {
    DPI = (float *)GEL::RenderStage::GetDPI(v7.lpVtbl);
    v14 = DPI[1];
    hdc = *DPI;
    hdc_4 = v14;
    memset_0(&v113, 0, sizeof(v113));
    v15 = (const struct GEL::Font *)(a2 + 72);
    GEL::EffectGlyphs::GetLOGFONT((GEL::EffectGlyphs *)a2, *(_DWORD *)(a2 + 92), AvailableTypefaces, &v113);
    if ( dword_18052EAC0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_18052EAC0);
      if ( dword_18052EAC0 == -1 )
      {
        dword_18052EAC4 = Mso::Orapi::ReadValue<&_msoreg const OrapiData::Gfx::c_msoridGELFixUpCharSetForMetafiles>();
        Init_thread_footer(&dword_18052EAC0);
      }
    }
    if ( dword_18052EAC4 > 0
      && !(*(unsigned __int8 (__fastcall **)(const struct GEL::ITypefaceList *))(*(_QWORD *)AvailableTypefaces + 72LL))(AvailableTypefaces)
      && (*(unsigned __int8 (__fastcall **)(HRESULT (__stdcall *)(Frame *, UINT, LCID, ITypeInfo **)))(*(_QWORD *)v7.lpVtbl->GetTypeInfo + 56LL))(v7.lpVtbl->GetTypeInfo) )
    {
      v88 = (const struct tagFONTSIGNATURE *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 112LL))(*(_QWORD *)v15);
      v113.lfCharSet = GetCharSet(v88);
    }
    if ( DeviceType == 3
      || *(float *)(a2 + 88) < (double)(float)(hdc_4 * 3.0)
      && ((Sku = Mso::Instance::GetSku(), DeviceType != 4)
       || Sku == 4
       || (float)SDWORD2(xmmword_18051FD40) > *(float *)(a2 + 88)) )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 176) + 16LL))(*(_QWORD *)(a2 + 176));
      Ofc::Round<long,float>(v16);
      v18 = Ofc::Round<long,float>(v17);
      v19 = v18;
      v92 = v18;
      v89 = Ofc::Round<long,float>(v20);
      v90 = Ofc::Round<long,float>(v21);
      if ( v22 == -1 || v11 && !v22 )
      {
        if ( DeviceType == 3
          || (*(unsigned __int8 (__fastcall **)(HRESULT (__stdcall *)(Frame *, UINT, LCID, ITypeInfo **)))(*(_QWORD *)v7.lpVtbl->GetTypeInfo + 56LL))(v7.lpVtbl->GetTypeInfo)
          || DeviceType != 4 && a5 == 3 )
        {
          GEL::MarkupText::MarkupText(
            (GEL::MarkupText *)&x,
            v99[0],
            *(const struct GEL::ITextRun **)(a2 + 208),
            (const struct GEL::Font *)(a2 + 72));
          GEL::StageDC::StageDC((GEL::StageDC *)hdc_8, (struct GEL::RenderStage *)v7.lpVtbl);
          memset_0(&v112, 0, sizeof(v112));
          Ofc::CHFont::FixupLOGFONT(&v113, &v112);
          GDIAssistant = Mso::GDIAssistant::GetGDIAssistant(v23);
          LOBYTE(v25) = 1;
          v26 = (void *)(*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, struct tagLOGFONTW *, __int64))(*(_QWORD *)GDIAssistant + 24LL))(
                          GDIAssistant,
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
          sub_1800B2A6C(v27);
          sub_1800B7820(a2, hdc_8[0]);
          Ofc::CHFont::~CHFont((Ofc::CHFont *)&xf);
          Gfx::GpHDCHolder::Empty((Gfx::GpHDCHolder *)hdc_8);
          GEL::MarkupText::Close((GEL::MarkupText *)&x);
          return 1;
        }
        if ( *(double *)(a2 + 160) - *(double *)(a2 + 144) < 2048.0
          && *(double *)(a2 + 168) - *(double *)(a2 + 152) < 2048.0 )
        {
          v32 = 1920103 * (unsigned int)v90;
          v33 = (int)(v32 + 5036060 * v19 + 9886846 * v89) >> 24;
          if ( COERCE_DOUBLE(*(_QWORD *)(a4 + 8) & v12) > COERCE_DOUBLE(*(_QWORD *)a4 & v12)
            || (LOBYTE(v32) = 0, COERCE_DOUBLE(*(_QWORD *)(a4 + 16) & v12) > COERCE_DOUBLE(*(_QWORD *)(a4 + 24) & v12)) )
          {
            LOBYTE(v32) = 1;
          }
          v91 = v32;
          v34 = Ofc::Round<long,double>(v32, v29, v30);
          v38 = Ofc::Round<long,double>(v36, v35, v37);
          v41 = Ofc::Round<long,double>(v40, v39, v38);
          v45 = Ofc::Round<long,double>(v43, v42, v44);
          top = v45;
          if ( v49 )
          {
            x.left = v46;
            x.top = v45;
            x.right = v34;
            x.bottom = v41;
          }
          else
          {
            v87 = v34;
            v34 = v41;
            x.left = v45;
            x.top = v46;
            x.right = v41;
            x.bottom = v87;
            v46 = v45;
            v41 = v87;
            top = x.top;
          }
          v50 = v34 - v46;
          v51 = v41 - top;
          if ( (unsigned int)(v50 - 1) <= 0x7FE && (unsigned int)(v51 - 1) <= 0x7FE )
          {
            v100 = v47;
            v101 = v47;
            v102 = v47;
            *(_OWORD *)v103 = 0;
            v93 = __PAIR64__(v51, v50);
            Gfx::TDIBSection<ARC::Pixel32>::SetSize(&v100, &v93);
            GEL::ValidateDIBSection((GEL *)v103, v52);
            *(_OWORD *)hdc_8 = 0;
            Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc_8, 0, v103[0]);
            v53 = hdc_8[0];
            SetWindowOrgEx(hdc_8[0], x.left, x.top, 0);
            StockObject = (HBRUSH)GetStockObject((unsigned __int8)v33 > 0xD4u ? 4 : 0);
            FillRect(v53, &x, StockObject);
            SetGraphicsMode(v53, 2);
            v55 = *(double *)(a4 + 40);
            v56 = *(double *)(a4 + 32);
            v57 = v55 - floor_0(v55);
            v58 = v56 - floor_0(v56);
            if ( v91 )
            {
              v60 = v58 * *(double *)(a4 + 16);
              v59 = v57 * *(double *)(a4 + 8);
              *(__m128i *)v105.m256i_i8 = _mm_load_si128((const __m128i *)&_xmm);
              *(__m128i *)&v105.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
              v106 = *(_QWORD *)&v59 ^ _xmm;
              v107 = *(_QWORD *)&v60 ^ _xmm;
              *(__m128i *)&xf.eM11 = _mm_load_si128((const __m128i *)&_xmm);
            }
            else
            {
              v59 = v57 * *(double *)(a4 + 24);
              v60 = v58 * *(double *)a4;
              *(double *)&v105.m256i_i64[3] = DOUBLE_1_0;
              *(double *)v105.m256i_i64 = DOUBLE_1_0;
              *(_OWORD *)&v105.m256i_u64[1] = 0;
              v106 = *(_QWORD *)&v60 ^ _xmm;
              v107 = *(_QWORD *)&v59 ^ _xmm;
              *(__m128i *)&xf.eM11 = _mm_load_si128((const __m128i *)&_xmm);
            }
            xf.eDx = v60;
            xf.eDy = v59;
            SetWorldTransform(v53, &xf);
            memset_0(&v112, 0, sizeof(v112));
            Ofc::CHFont::FixupLOGFONT(&v113, &v112);
            v62 = Mso::GDIAssistant::GetGDIAssistant(v61);
            LOBYTE(v63) = 1;
            v64 = (void *)(*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, struct tagLOGFONTW *, __int64))(*(_QWORD *)v62 + 24LL))(
                            v62,
                            &v112,
                            v63);
            *(_QWORD *)&xf.eDx = 0;
            *(_QWORD *)&xf.eM21 = v53;
            *(_QWORD *)&xf.eM11 = v64;
            if ( v53 && v64 )
              *(_QWORD *)&xf.eDx = SelectObject(v53, v64);
            sub_1800B2A6C(v53);
            sub_1800B7820(a2, v53);
            Ofc::CHFont::~CHFont((Ofc::CHFont *)&xf);
            if ( v53 )
            {
              if ( hdc_8[1] )
                SelectObject(v53, hdc_8[1]);
              DeleteDC(v53);
            }
            v65 = 0;
            memset(&xf, 0, 20);
            v111 = 0;
            v93 = __PAIR64__(v51, v50);
            ARC::TPixelBuffer<ARC::Pixel32>::SetSize(&xf, &v93);
            LOBYTE(v93) = v90;
            BYTE1(v93) = v89;
            BYTE2(v93) = v92;
            BYTE3(v93) = (unsigned __int8)v33 <= 0xD4u;
            for ( i = 0; i < 2; ++i )
            {
              if ( *((_DWORD *)&xf.eM21 + i) != *((_DWORD *)&v101 + i) )
                goto LABEL_56;
            }
            v68 = v100;
            v69 = *(_QWORD *)&xf.eM11;
            for ( j = 0; j < LODWORD(xf.eM22); ++j )
            {
              v86 = v68;
              while ( v65 < LODWORD(xf.eM21) )
              {
                GEL::LuminanceToPremultipliedAlphaCopy::operator()(&v93, v86 + v69 - v68, v86);
                ++v65;
                v86 += 4;
              }
              v68 += v102;
              v69 += SLODWORD(xf.eDx);
              v65 = 0;
            }
            v15 = (const struct GEL::Font *)(a2 + 72);
LABEL_56:
            GEL::IImage::Create<ARC::Pixel32,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>>>(
              (unsigned int)&v93,
              (unsigned int)&xf,
              v66,
              1,
              (__int64)&hdc);
            v73 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x80, v71, v72);
            v76 = v93;
            if ( v73 )
            {
              *(double *)hdc_8 = (double)x.left;
              *(double *)&hdc_8[1] = (double)x.top;
              right = (double)x.right;
              bottom = (double)x.bottom;
              v77 = GEL::EffectImage::EffectImage(v73, v93, hdc_8);
            }
            else
            {
              v77 = 0;
            }
            v108 = v77;
            if ( v77 )
              (**(void (__fastcall ***)(__int64))v77)(v77);
            v78 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v74, v75);
            if ( v78 )
              v81 = GEL::EffectTransform::EffectTransform(v78, v77, &v105);
            else
              v81 = 0;
            hdc_8[0] = (HDC)v81;
            if ( v81 )
              (**(void (__fastcall ***)(__int64))v81)(v81);
            v82 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v79, v80);
            v83 = v82;
            if ( v82 )
            {
              GEL::TEffect<GEL::IEffectAlphaReplaceBinary>::TEffect<GEL::IEffectAlphaReplaceBinary>(v82);
              v83[5] = v81;
              (**(void (__fastcall ***)(__int64))v81)(v81);
              *v83 = &GEL::EffectNearestNeighborInterpolation::`vftable'{for `Mso::TRefCountedImpl<GEL::IEffectNearestNeighborInterpolation>'};
              v83[2] = &GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'};
              v83[3] = &GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'};
              v83[4] = &GEL::EffectNearestNeighborInterpolation::`vftable';
            }
            if ( v83 )
              (*(void (__fastcall **)(_QWORD *))*v83)(v83);
            v104 = v83;
            v84 = (GEL::RenderStage::Frame *)v99[0];
            GEL::MarkupText::MarkupText((GEL::MarkupText *)v99, v99[0], *(const struct GEL::ITextRun **)(a2 + 208), v15);
            GEL::RenderStage::Frame::Draw(v84, (const struct GEL::IEffect *)v83);
            GEL::MarkupText::Close((GEL::MarkupText *)v99);
            if ( v81 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 8LL))(v81);
            if ( v77 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 8LL))(v77);
            if ( v76 )
              (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v76 + 8LL))(v76);
            if ( v111 )
              Mso::Memory::Free(v111, v85);
            Ofc::CDIBSection::Reset((Ofc::CDIBSection *)v103);
            if ( v83 )
              (*(void (__fastcall **)(_QWORD *))(*v83 + 8LL))(v83);
            return 1;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800b3430  mov     rax, rsp
0x1800b3433  mov     [rax+8], rbx
0x1800b3437  push    rbp
0x1800b3438  push    rsi
0x1800b3439  push    rdi
0x1800b343a  push    r12
0x1800b343c  push    r13
0x1800b343e  push    r14
0x1800b3440  push    r15
0x1800b3442  lea     rbp, [rax-138h]
0x1800b3449  sub     rsp, 200h
0x1800b3450  movaps  xmmword ptr [rax-48h], xmm6
0x1800b3454  movaps  xmmword ptr [rax-58h], xmm7
0x1800b3458  mov     rax, cs:__security_cookie
0x1800b345f  xor     rax, rsp
0x1800b3462  mov     [rbp+130h+var_60], rax
0x1800b3469  mov     rbx, r9
0x1800b346c  mov     [rsp+230h+var_1C8], r8
0x1800b3471  mov     r15, rdx
0x1800b3474  mov     rdi, [r8]
0x1800b3477  mov     [rbp+130h+var_190], 0
0x1800b347f  mov     rcx, rdi
0x1800b3482  call    ?GetDeviceType@RenderStage@GEL@@QEBA?AW4DeviceType@2@XZ; GEL::RenderStage::GetDeviceType(void)
0x1800b3487  mov     sil, al
0x1800b348a  mov     rcx, rdi; this
0x1800b348d  call    ?GetAvailableTypefaces@RenderStage@GEL@@QEBAAEBUITypefaceList@2@XZ; GEL::RenderStage::GetAvailableTypefaces(void)
0x1800b3492  mov     r14, rax
0x1800b3495  call    ?IsInTransparentMarkup@EffectTransparentMarkup@GEL@@SA_NXZ; GEL::EffectTransparentMarkup::IsInTransparentMarkup(void)
0x1800b349a  mov     r12b, al
0x1800b349d  movdqa  xmm6, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1800b34a5  cmp     qword ptr [rdi+0B0h], 0
0x1800b34ad  jz      loc_1800B3744
0x1800b34b3  test    r12b, r12b
0x1800b34b6  jz      loc_1800B370E
0x1800b34bc  mov     rcx, rdi
0x1800b34bf  call    ?GetDPI@RenderStage@GEL@@QEBAAEBV?$TConvertibleDPI2@M@Gfx@@XZ; GEL::RenderStage::GetDPI(void)
0x1800b34c4  movss   xmm1, dword ptr [rax+4]
0x1800b34c9  movss   xmm0, dword ptr [rax]
0x1800b34cd  movss   dword ptr [rsp+230h+hdc], xmm0
0x1800b34d3  movss   dword ptr [rsp+230h+hdc+4], xmm1
0x1800b34d9  xor     edx, edx; Val
0x1800b34db  lea     r8d, [rdx+5Ch]; Size
0x1800b34df  lea     rcx, [rbp+130h+var_C0]; void *
0x1800b34e3  call    memset_0
0x1800b34e8  lea     r13, [r15+48h]
0x1800b34ec  lea     r9, [rbp+130h+var_C0]; struct tagLOGFONTW *
0x1800b34f0  mov     r8, r14; struct GEL::ITypefaceList *
0x1800b34f3  mov     edx, [r13+14h]; unsigned int
0x1800b34f7  mov     rcx, r15; this
0x1800b34fa  call    ?GetLOGFONT@EffectGlyphs@GEL@@UEBAXIAEBUITypefaceList@2@AEAUtagLOGFONTW@@@Z; GEL::EffectGlyphs::GetLOGFONT(uint,GEL::ITypefaceList const &,tagLOGFONTW &)
0x1800b34ff  mov     ecx, cs:_tls_index
0x1800b3505  mov     rax, gs:58h
0x1800b350e  mov     edx, 4
0x1800b3513  mov     rax, [rax+rcx*8]
0x1800b3517  mov     ecx, [rdx+rax]
0x1800b351a  cmp     cs:dword_18052EAC0, ecx
0x1800b3520  jg      loc_1800B37F4
0x1800b3526  cmp     cs:dword_18052EAC4, 0
0x1800b352d  jg      loc_1800B3E59
0x1800b3533  movss   xmm0, dword ptr [rsp+230h+hdc+4]
0x1800b3539  mulss   xmm0, cs:__real@40400000
0x1800b3541  cvtps2pd xmm1, xmm0
0x1800b3544  movss   xmm0, dword ptr [r13+10h]
0x1800b354a  cvtps2pd xmm0, xmm0
0x1800b354d  comisd  xmm0, xmm1
0x1800b3551  setnb   al
0x1800b3554  cmp     sil, 3
0x1800b3558  jnz     loc_1800B379E
0x1800b355e  mov     rcx, [r15+0B0h]
0x1800b3565  mov     rax, [rcx]
0x1800b3568  mov     rax, [rax+10h]
0x1800b356c  call    cs:__guard_dispatch_icall_fptr
0x1800b3572  mov     rcx, rax
0x1800b3575  movss   xmm0, dword ptr [rax+14h]
0x1800b357a  movss   xmm3, cs:__real@437f0000
0x1800b3582  mulss   xmm0, xmm3
0x1800b3586  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b358b  mov     dl, al
0x1800b358d  movss   xmm0, dword ptr [rcx+8]
0x1800b3592  mulss   xmm0, xmm3
0x1800b3596  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b359b  movzx   r14d, al
0x1800b359f  mov     byte ptr [rsp+230h+var_200+3], r14b
0x1800b35a4  movss   xmm0, dword ptr [rcx+0Ch]
0x1800b35a9  mulss   xmm0, xmm3
0x1800b35ad  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b35b2  mov     byte ptr [rsp+230h+var_200], al
0x1800b35b6  movss   xmm0, dword ptr [rcx+10h]
0x1800b35bb  mulss   xmm0, xmm3
0x1800b35bf  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x1800b35c4  mov     byte ptr [rsp+230h+var_200+1], al
0x1800b35c8  cmp     dl, 0FFh
0x1800b35cb  jnz     loc_1800B3E43
0x1800b35d1  cmp     sil, 3
0x1800b35d5  jnz     loc_1800B36BD
0x1800b35db  mov     r9, r13; struct GEL::Font *
0x1800b35de  mov     r8, [r15+0D0h]; struct GEL::ITextRun *
0x1800b35e5  mov     rdx, [rsp+230h+var_1C8]; struct Frame *
0x1800b35ea  lea     rcx, [rbp+130h+x]; this
0x1800b35ee  call    ??0MarkupText@GEL@@QEAA@AEAVFrame@RenderStage@1@AEBUITextRun@1@AEBUFont@1@@Z; GEL::MarkupText::MarkupText(GEL::RenderStage::Frame &,GEL::ITextRun const &,GEL::Font const &)
0x1800b35f3  mov     rdx, rdi; struct GEL::RenderStage *
0x1800b35f6  lea     rcx, [rsp+230h+hdc+8]; this
0x1800b35fb  call    ??0StageDC@GEL@@QEAA@AEAVRenderStage@1@@Z; GEL::StageDC::StageDC(GEL::RenderStage &)
0x1800b3600  nop
0x1800b3601  xor     edx, edx; Val
0x1800b3603  lea     r8d, [rdx+5Ch]; Size
0x1800b3607  lea     rcx, [rbp+130h+var_120]; void *
0x1800b360b  call    memset_0
0x1800b3610  lea     rdx, [rbp+130h+var_120]; struct tagLOGFONTW *
0x1800b3614  lea     rcx, [rbp+130h+var_C0]; struct tagLOGFONTW *
0x1800b3618  call    ?FixupLOGFONT@CHFont@Ofc@@SAXAEBUtagLOGFONTW@@AEAU3@@Z; Ofc::CHFont::FixupLOGFONT(tagLOGFONTW const &,tagLOGFONTW &)
0x1800b361d  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1800b3623  mov     r9, rax
0x1800b3626  mov     rcx, [rax]
0x1800b3629  mov     rax, [rcx+18h]
0x1800b362d  mov     r8b, 1
0x1800b3630  lea     rdx, [rbp+130h+var_120]
0x1800b3634  mov     rcx, r9
0x1800b3637  call    cs:__guard_dispatch_icall_fptr
0x1800b363d  mov     qword ptr [rbp+130h+xf.eDx], 0
0x1800b3645  mov     rcx, [rsp+230h+hdc+8]; hdc
0x1800b364a  mov     qword ptr [rbp+130h+xf.eM21], rcx
0x1800b364e  mov     qword ptr [rbp+130h+xf.eM11], rax
0x1800b3652  test    rcx, rcx
0x1800b3655  jz      short loc_1800B366E
0x1800b3657  test    rax, rax
0x1800b365a  jz      short loc_1800B366E
0x1800b365c  mov     rdx, rax; h
0x1800b365f  call    cs:__imp_SelectObject
0x1800b3665  mov     qword ptr [rbp+130h+xf.eDx], rax
0x1800b3669  mov     rcx, [rsp+230h+hdc+8]; hdc
0x1800b366e  movzx   r8d, byte ptr [rsp+230h+var_200]
0x1800b3674  shl     r8d, 8
0x1800b3678  movzx   eax, byte ptr [rsp+230h+var_200+1]
0x1800b367d  shl     eax, 10h
0x1800b3680  or      r8d, eax
0x1800b3683  or      r8d, r14d
0x1800b3686  mov     edx, [r15+78h]
0x1800b368a  call    sub_1800B2A6C
0x1800b368f  mov     rdx, [rsp+230h+hdc+8]
0x1800b3694  mov     rcx, r15
0x1800b3697  call    sub_1800B7820
0x1800b369c  lea     rcx, [rbp+130h+xf]; this
0x1800b36a0  call    ??1CHFont@Ofc@@QEAA@XZ; Ofc::CHFont::~CHFont(void)
0x1800b36a5  lea     rcx, [rsp+230h+hdc+8]; this
0x1800b36aa  call    ?Empty@GpHDCHolder@Gfx@@QEAAXXZ; Gfx::GpHDCHolder::Empty(void)
0x1800b36af  lea     rcx, [rbp+130h+x]; this
0x1800b36b3  call    ?Close@MarkupText@GEL@@QEAAXXZ; GEL::MarkupText::Close(void)
0x1800b36b8  nop
0x1800b36b9  mov     al, 1
0x1800b36bb  jmp     short loc_1800B3710
0x1800b36bd  mov     rcx, [rdi+20h]
0x1800b36c1  mov     rax, [rcx]
0x1800b36c4  mov     rax, [rax+38h]
0x1800b36c8  call    cs:__guard_dispatch_icall_fptr
0x1800b36ce  xor     r9d, r9d
0x1800b36d1  test    al, al
0x1800b36d3  jnz     loc_1800B35DB
0x1800b36d9  cmp     sil, 4
0x1800b36dd  jnz     loc_1800B378C
0x1800b36e3  movsd   xmm2, qword ptr [r15+0A0h]
0x1800b36ec  movsd   xmm3, qword ptr [r15+90h]
0x1800b36f5  movaps  xmm0, xmm2
0x1800b36f8  subsd   xmm0, xmm3
0x1800b36fc  movsd   xmm1, cs:__real@40a0000000000000
0x1800b3704  comisd  xmm0, xmm1
0x1800b3708  jb      loc_1800B3829
0x1800b370e  xor     al, al
0x1800b3710  mov     rcx, [rbp+130h+var_60]
0x1800b3717  xor     rcx, rsp; StackCookie
0x1800b371a  call    __security_check_cookie
0x1800b371f  lea     r11, [rsp+230h+var_30]
0x1800b3727  mov     rbx, [r11+40h]
0x1800b372b  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b3730  movaps  xmm7, xmmword ptr [r11-20h]
0x1800b3735  mov     rsp, r11
0x1800b3738  pop     r15
0x1800b373a  pop     r14
0x1800b373c  pop     r13
0x1800b373e  pop     r12
0x1800b3740  pop     rdi
0x1800b3741  pop     rsi
0x1800b3742  pop     rbp
0x1800b3743  retn
0x1800b3744  cmp     sil, 5
0x1800b3748  jz      loc_1800B34B3
0x1800b374e  movsd   xmm0, qword ptr [rbx]
0x1800b3752  andps   xmm0, xmm6
0x1800b3755  movsd   xmm1, cs:__real@3cd203af9ee75616
0x1800b375d  comisd  xmm1, xmm0
0x1800b3761  ja      short loc_1800B37DD
0x1800b3763  movsd   xmm0, qword ptr [rbx+8]
0x1800b3768  andps   xmm0, xmm6
0x1800b376b  comisd  xmm1, xmm0
0x1800b376f  jbe     loc_1800B34B3
0x1800b3775  movsd   xmm0, qword ptr [rbx+10h]
0x1800b377a  andps   xmm0, xmm6
0x1800b377d  comisd  xmm1, xmm0
0x1800b3781  ja      loc_1800B34BC
0x1800b3787  jmp     loc_1800B34B3
0x1800b378c  cmp     [rbp+130h+arg_20], 3
0x1800b3793  jz      loc_1800B35DB
0x1800b3799  jmp     loc_1800B36E3
0x1800b379e  test    al, al
0x1800b37a0  jnz     loc_1800B370E
0x1800b37a6  call    cs:__imp_?GetSku@Instance@Mso@@YA?AW4SKU@12@XZ; Mso::Instance::GetSku(void)
0x1800b37ac  cmp     sil, 4
0x1800b37b0  jnz     loc_1800B355E
0x1800b37b6  cmp     eax, 4
0x1800b37b9  jz      loc_1800B355E
0x1800b37bf  mov     eax, dword ptr cs:xmmword_18051FD40+8
0x1800b37c5  xorps   xmm0, xmm0
0x1800b37c8  cvtsi2ss xmm0, rax
0x1800b37cd  comiss  xmm0, dword ptr [r13+10h]
0x1800b37d2  jbe     loc_1800B370E
0x1800b37d8  jmp     loc_1800B355E
0x1800b37dd  movsd   xmm0, qword ptr [rbx+18h]
0x1800b37e2  andps   xmm0, xmm6
0x1800b37e5  comisd  xmm1, xmm0
0x1800b37e9  ja      loc_1800B34BC
0x1800b37ef  jmp     loc_1800B3763
0x1800b37f4  lea     rcx, dword_18052EAC0
0x1800b37fb  call    _Init_thread_header
0x1800b3800  cmp     cs:dword_18052EAC0, 0FFFFFFFFh
0x1800b3807  jnz     loc_1800B3526
0x1800b380d  call    ??$ReadValue@$1?c_msoridGELFixUpCharSetForMetafiles@Gfx@OrapiData@@3U_msoreg@@B@Orapi@Mso@@YAIXZ; Mso::Orapi::ReadValue<&_msoreg const OrapiData::Gfx::c_msoridGELFixUpCharSetForMetafiles>(void)
0x1800b3812  mov     cs:dword_18052EAC4, eax
0x1800b3818  lea     rcx, dword_18052EAC0
0x1800b381f  call    _Init_thread_footer
0x1800b3824  jmp     loc_1800B3526
0x1800b3829  movsd   xmm4, qword ptr [r15+0A8h]
0x1800b3832  movsd   xmm5, qword ptr [r15+98h]
0x1800b383b  movaps  xmm0, xmm4
0x1800b383e  subsd   xmm0, xmm5
0x1800b3842  comisd  xmm0, xmm1
0x1800b3846  jnb     loc_1800B370E
0x1800b384c  movzx   eax, byte ptr [rsp+230h+var_200]
0x1800b3851  imul    r12d, eax, 96DC7Eh
0x1800b3858  imul    ecx, r14d, 4CD81Ch
0x1800b385f  add     r12d, ecx
0x1800b3862  movzx   eax, byte ptr [rsp+230h+var_200+1]
0x1800b3867  imul    ecx, eax, 1D4C67h
0x1800b386d  add     r12d, ecx
0x1800b3870  sar     r12d, 18h
0x1800b3874  movsd   xmm1, qword ptr [rbx+8]
0x1800b3879  movsd   xmm0, qword ptr [rbx]
0x1800b387d  andps   xmm1, xmm6
0x1800b3880  andps   xmm0, xmm6
0x1800b3883  comisd  xmm1, xmm0
0x1800b3887  jbe     loc_1800B3E21
0x1800b388d  mov     cl, 1
0x1800b388f  mov     byte ptr [rsp+230h+var_200+2], cl
0x1800b3893  movaps  xmm0, xmm4
0x1800b3896  call    ??$Round@JN@Ofc@@YAJN@Z; Ofc::Round<long,double>(double)
0x1800b389b  mov     esi, eax
0x1800b389d  movaps  xmm0, xmm5
0x1800b38a0  call    ??$Round@JN@Ofc@@YAJN@Z; Ofc::Round<long,double>(double)
0x1800b38a5  mov     r8d, eax
0x1800b38a8  movaps  xmm0, xmm2
0x1800b38ab  call    ??$Round@JN@Ofc@@YAJN@Z; Ofc::Round<long,double>(double)
0x1800b38b0  mov     r14d, eax
0x1800b38b3  movaps  xmm0, xmm3
0x1800b38b6  call    ??$Round@JN@Ofc@@YAJN@Z; Ofc::Round<long,double>(double)
0x1800b38bb  mov     edx, eax
0x1800b38bd  test    cl, cl
0x1800b38bf  jz      loc_1800B3CF8
0x1800b38c5  mov     [rbp+130h+x], r8d
0x1800b38c9  mov     [rbp+130h+y], eax
0x1800b38cc  mov     [rbp+130h+var_148], esi
0x1800b38cf  mov     [rbp+130h+var_144], r14d
0x1800b38d3  sub     esi, r8d
0x1800b38d6  sub     r14d, edx
0x1800b38d9  lea     eax, [rsi-1]
0x1800b38dc  mov     ecx, 7FEh
0x1800b38e1  cmp     eax, ecx
0x1800b38e3  ja      loc_1800B370E
0x1800b38e9  lea     eax, [r14-1]
0x1800b38ed  cmp     eax, ecx
0x1800b38ef  ja      loc_1800B370E
0x1800b38f5  mov     [rsp+230h+var_1B8], r9
0x1800b38fa  mov     [rbp+130h+var_1B0], r9
0x1800b38fe  mov     [rbp+130h+var_1A8], r9d
0x1800b3902  xorps   xmm0, xmm0
0x1800b3905  movdqu  xmmword ptr [rbp+130h+var_1A0], xmm0
0x1800b390a  mov     dword ptr [rsp+230h+var_1F8], esi
0x1800b390e  mov     dword ptr [rsp+230h+var_1F8+4], r14d
0x1800b3913  mov     rax, [rsp+230h+var_1F8]
0x1800b3918  mov     [rsp+230h+var_1F8], rax
0x1800b391d  lea     rdx, [rsp+230h+var_1F8]
0x1800b3922  lea     rcx, [rsp+230h+var_1B8]
0x1800b3927  call    ?SetSize@?$TDIBSection@UPixel32@ARC@@@Gfx@@QEAAXAEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; Gfx::TDIBSection<ARC::Pixel32>::SetSize(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800b392c  lea     rcx, [rbp+130h+var_1A0]; this
0x1800b3930  call    ?ValidateDIBSection@GEL@@YAXAEBVCDIBSection@Ofc@@@Z; GEL::ValidateDIBSection(Ofc::CDIBSection const &)
0x1800b3935  xorps   xmm0, xmm0
0x1800b3938  movdqu  xmmword ptr [rsp+230h+hdc+8], xmm0
0x1800b393e  mov     r8, [rbp+130h+var_1A0]; HBITMAP
0x1800b3942  xor     edx, edx; HDC
0x1800b3944  lea     rcx, [rsp+230h+hdc+8]; this
0x1800b3949  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1800b394e  xor     r9d, r9d; lppt
  ... truncated ...
```
