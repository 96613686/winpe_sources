# Dr::FreeformDragElement::GetGelEffect(Ofc::TSharedPtr<Art::View> const &,Art::MouseMessage const &)

- ea: `0x1805a47c0`
- end: `0x1805a51b9`
- name: `?GetGelEffect@FreeformDragElement@Dr@@UEBA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBV?$TSharedPtr@VView@Art@@@4@AEBVMouseMessage@Art@@@Z`
- size: `2553`
- prototype: ``
- caller_count: `0`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180001320`
- `0x18000dc60`
- `0x18002e9cc`
- `0x1800373d0`
- `0x18003dcb0`
- `0x1800428c8`
- `0x180049050`
- `0x180070fe0`
- `0x180071720`
- `0x180079890`
- `0x1800f6964`
- `0x1801600a0`
- `0x180160a60`
- `0x180174b30`
- `0x18017a484`
- `0x180185dec`
- `0x18018a670`
- `0x18018b540`
- `0x18018b6a0`
- `0x18018b6f0`
- `0x1801a1280`
- `0x1801a1d50`
- `0x1801a2150`
- `0x1801a3f00`
- `0x1801c2ad8`
- `0x1801c5e20`
- `0x1801c6b10`
- `0x1801c764c`
- `0x1801cf7f8`
- `0x1801d04f0`
- `0x1801dec78`
- `0x180207920`
- `0x18023c660`
- `0x180273850`
- `0x180416e40`
- `0x180431500`
- `0x1805a47c0`
- `0x1805a51bc`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a5c5c`
- `0x1806bac28`
- `0x1806bce1c`

## import_xrefs

- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1805a4f48`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1805a5051`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1805a4f48`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1805a5051`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1805a4f24`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1805a4fa4`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1805a4f24`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1805a4fa4`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1805a4eef`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1805a4eef`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1805a4ee5`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1805a4ee5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1805a4e32`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1805a4eae`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1805a50f7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1805a4e32`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1805a4eae`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1805a50f7`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1805a4deb`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1805a4deb`

## pseudocode

```c
_QWORD *__fastcall Dr::FreeformDragElement::GetGelEffect(__int64 a1, _QWORD *a2, Ofc::CProxyPtrImpl **a3, __int64 a4)
{
  unsigned int v8; // r12d
  _DWORD *Checked; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  bool v13; // si
  _DWORD *v14; // rax
  int v15; // edx
  struct Ofc::CProxyPtrImpl **v16; // rax
  void *v17; // rax
  void *v18; // rax
  __int64 v19; // rax
  volatile signed __int32 *v20; // rcx
  void *v21; // rax
  struct Ofc::CProxyPtrImpl **v22; // rax
  __int64 v23; // rcx
  volatile signed __int32 *v24; // rcx
  void *v25; // rax
  struct Ofc::CProxyPtrImpl **v26; // rax
  void *v27; // rax
  struct Ofc::CProxyPtrImpl *v28; // rcx
  void *v29; // rax
  __int64 v30; // rax
  Art::ShapeStyleData *v31; // rbx
  struct Art::Path2DTable *Paths; // rdi
  Art::Path2DTable *v33; // rax
  __int64 v34; // r9
  char *v35; // rdi
  __int64 v36; // r10
  __int64 (__fastcall *v37)(__int64, _QWORD **, _BYTE *, char *, char *, __m128i *, __int128 *); // rax
  __m128d v38; // xmm2
  double v39; // xmm1_8
  __int64 *v40; // rax
  __int64 v41; // rdi
  void *v42; // rdx
  void (*v43)(void); // rax
  void *v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rbx
  void (__fastcall *v48)(__int64, _QWORD); // rsi
  __int64 v49; // rdi
  _QWORD *v50; // rax
  _QWORD *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rbx
  void (__fastcall *v54)(__int64, _QWORD); // rsi
  _QWORD *v55; // rax
  _QWORD *v56; // rbx
  double v57; // xmm6_8
  double v58; // xmm2_8
  void *v59; // rdx
  __int64 v61; // [rsp+48h] [rbp-C0h] BYREF
  Ofc::CProxyPtrImpl *v62; // [rsp+50h] [rbp-B8h] BYREF
  struct Ofc::CProxyPtrImpl *v63; // [rsp+58h] [rbp-B0h] BYREF
  Art::ShapeStyleData *v64; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v65; // [rsp+68h] [rbp-A0h] BYREF
  Ofc::CProxyPtrImpl *v66; // [rsp+70h] [rbp-98h] BYREF
  Ofc::CProxyPtrImpl *v67; // [rsp+78h] [rbp-90h] BYREF
  Mso::Memory *v68; // [rsp+80h] [rbp-88h] BYREF
  int v69; // [rsp+88h] [rbp-80h]
  unsigned int v70; // [rsp+8Ch] [rbp-7Ch]
  __m128i v71; // [rsp+90h] [rbp-78h] BYREF
  __int64 v72; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD *v74; // [rsp+B0h] [rbp-58h] BYREF
  struct Ofc::CProxyPtrImpl *v75; // [rsp+B8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v78; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v79[24]; // [rsp+E8h] [rbp-20h] BYREF
  void **v80; // [rsp+100h] [rbp-8h] BYREF
  struct Ofc::CProxyPtrImpl *v81; // [rsp+108h] [rbp+0h]
  __int64 v82; // [rsp+110h] [rbp+8h]
  __int64 v83; // [rsp+118h] [rbp+10h]
  __int64 v84; // [rsp+120h] [rbp+18h]
  int v85; // [rsp+128h] [rbp+20h]
  _OWORD v86[2]; // [rsp+140h] [rbp+38h] BYREF
  double v87; // [rsp+160h] [rbp+58h]
  double v88; // [rsp+168h] [rbp+60h]
  _BYTE v89[72]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v90[16]; // [rsp+1C0h] [rbp+B8h] BYREF
  _BYTE v91[16]; // [rsp+1D0h] [rbp+C8h] BYREF
  __int64 v92; // [rsp+1E0h] [rbp+D8h]
  char v93; // [rsp+205h] [rbp+FDh]
  char v94; // [rsp+206h] [rbp+FEh]
  __int128 v95; // [rsp+208h] [rbp+100h] BYREF
  __int128 v96; // [rsp+218h] [rbp+110h]
  int v97; // [rsp+228h] [rbp+120h]
  __int16 v98; // [rsp+22Ch] [rbp+124h]
  __int64 v99; // [rsp+230h] [rbp+128h]
  __int64 v100; // [rsp+238h] [rbp+130h]
  char v101; // [rsp+240h] [rbp+138h]
  __int64 v102; // [rsp+248h] [rbp+140h]
  __int16 v103; // [rsp+250h] [rbp+148h]
  __int64 v104; // [rsp+258h] [rbp+150h]
  char v105; // [rsp+260h] [rbp+158h]

  v65 = a2;
  v8 = *((_DWORD *)Ofc::CProxyPtrImpl::GetChecked(*a3) + 96);
  Art::ConvertPath2DToGelPath(&v77, *(_QWORD *)(a1 + 184), 1, 1);
  Checked = Ofc::CProxyPtrImpl::GetChecked(*a3);
  v62 = (Ofc::CProxyPtrImpl *)__PAIR64__(*(_DWORD *)(a4 + 28) - Checked[47], *(_DWORD *)(a4 + 24) - Checked[46]);
  v63 = v62;
  Art::View::ConvertViewToHostCoordinates(Checked, &v71, &v63);
  v10 = *(_QWORD **)(a1 + 176);
  v11 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(v10[1]);
  v63 = (struct Ofc::CProxyPtrImpl *)Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(v71.m128i_i64[1] - v11);
  v12 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*v10);
  v64 = (Art::ShapeStyleData *)Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(v71.m128i_i64[0] - v12);
  Art::Point2D::Point2D(&si128, &v64, &v63);
  v13 = Dr::FreeformDragTracker::FClickedAtBeginning((const struct Art::Point2D *)&si128);
  v67 = (Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v66 = (Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v14 = Ofc::CProxyPtrImpl::GetChecked(*a3);
  v15 = v14[64];
  if ( v15 )
  {
    v16 = (struct Ofc::CProxyPtrImpl **)Ofc::TArray<Ofc::CVarStr>::operator[](v14 + 62, (unsigned int)(v15 - 1));
    Ofc::CProxyPtrImpl::StrongAssign(&v66, *v16);
  }
  v17 = Ofc::CProxyPtrImpl::GetChecked(v66);
  if ( *(_QWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v17 + 328LL))(v17) + 16LL) )
  {
    v18 = Ofc::CProxyPtrImpl::GetChecked(v66);
    v19 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v18 + 328LL))(v18);
    v20 = *(volatile signed __int32 **)v19;
    if ( *(_DWORD *)(*(_QWORD *)v19 + 4LL) != 0x80000000 )
      _InterlockedIncrement(v20 + 1);
    v64 = (Art::ShapeStyleData *)v20;
    v63 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)v20);
    v21 = Ofc::CProxyPtrImpl::GetChecked(v63);
    v22 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v21 + 184LL))(v21);
    Ofc::CProxyPtrImpl::CheckedStrongAssign(&v67, *v22);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v63);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v64);
  }
  else
  {
    v23 = *((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(*a3) + 6);
    if ( *(_DWORD *)v23 != 0x80000000 )
      _InterlockedIncrement((volatile signed __int32 *)v23);
    v75 = (struct Ofc::CProxyPtrImpl *)v23;
    if ( *(_QWORD *)(v23 + 16) )
    {
      v24 = (volatile signed __int32 *)*((_QWORD *)Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v23) + 11);
      if ( *((_DWORD *)v24 + 1) != 0x80000000 )
        _InterlockedIncrement(v24 + 1);
      v63 = (struct Ofc::CProxyPtrImpl *)v24;
      v62 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)v24);
      Ofc::CProxyPtrImpl::DtorWeakRelease(&v63);
      if ( *((_QWORD *)v62 + 2) )
      {
        v25 = Ofc::CProxyPtrImpl::GetChecked(v62);
        v26 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *, Art::ShapeStyleData **))(*(_QWORD *)v25 + 96LL))(
                                              v25,
                                              &v64);
        Ofc::CProxyPtrImpl::CheckedStrongAssign(&v67, *v26);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v64);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v62);
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v75);
  }
  if ( *((_QWORD *)v67 + 2) )
  {
    v80 = &Art::ThemeInfo::`vftable';
    v81 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v82 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v83 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v84 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v85 = 0;
    v27 = Ofc::CProxyPtrImpl::GetChecked(v67);
    (*(void (__fastcall **)(void *, void ***))(*(_QWORD *)v27 + 160LL))(v27, &v80);
    v28 = v81;
    if ( *((_DWORD *)v81 + 1) != 0x80000000 )
      _InterlockedIncrement((volatile signed __int32 *)v81 + 1);
    v63 = v28;
    if ( *((_QWORD *)v28 + 2) )
    {
      v62 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v28);
      v64 = 0;
      Art::LinearShadeProps::LinearShadeProps((Art::LinearShadeProps *)v79);
      v29 = Ofc::CProxyPtrImpl::GetChecked(v62);
      v30 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v29 + 88LL))(v29);
      Ofc::TOptional<Art::ShapeStyle>::operator=(&v64, v30 + 56);
      Art::EffectList::operator=((Art::EffectList *)v79);
      Art::ShapePropertyBag::ShapePropertyBag((Art::ShapePropertyBag *)v89);
      v31 = v64;
      if ( v64 )
        Art::StyleResolverHelper::ResolvePropLists(&v62, v64, v79);
      Art::StyleResolverHelper::ResolveColorsForPropLists(&v80, v79);
      v71 = 0u;
      Art::GeometryBuilder::GeometryBuilder((Art::GeometryBuilder *)&si128, (struct Art::Geometry2D *)&v71);
      Paths = Art::GeometryBuilder::GetPaths((Art::GeometryBuilder *)&si128);
      Ofc::CArrayImpl::Reset((struct Art::Path2DTable *)((char *)Paths + 8), Ofc::TDestructRange<Art::Path2D,0>::Do);
      *(_DWORD *)Paths = 0;
      v33 = Art::GeometryBuilder::GetPaths((Art::GeometryBuilder *)&si128);
      Art::Path2DTable::AddPath2D(v33, *(const struct Art::Path2D **)(a1 + 184));
      Art::GeometryBuilder::Validate((Art::GeometryBuilder *)&si128);
      Art::GeometryBuilder::~GeometryBuilder((Art::GeometryBuilder *)&si128);
      Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Geometry>((Ofc::Tph::CPropertySetImpl *)v79);
      v95 = 0;
      v96 = 0;
      v97 = 0;
      v98 = 0;
      v99 = 0;
      v100 = 0;
      Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
        &v75,
        *(_QWORD *)(a1 + 176) + 8LL);
      Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
        &v65,
        v34);
      Art::Point2D::SetXY(&v95, &v65, &v75);
      Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Transform>((Ofc::Tph::CPropertySetImpl *)v79);
      LOWORD(v61) = 0;
      Art::PropListToObj(v79, v89, &v61);
      v75 = 0;
      if ( v93 )
      {
        if ( v94 && (v94 = 1, !(unsigned __int8)Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::Is<Art::Line::None>(v91))
          || v13 && !(unsigned __int8)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::Is<Art::Fill::None>(v90) )
        {
          if ( !v13 )
            Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::None>(v90);
          if ( v92 )
            Art::Model3DStorageUpdateParamsData::ProjectionType_<0>::`scalar deleting destructor'(v92);
          v92 = 0;
          LODWORD(v95) = v8;
          *((_QWORD *)&v95 + 1) = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
          *(_QWORD *)&v96 = 0;
          *((_QWORD *)&v96 + 1) = 0x10000;
          LOWORD(v97) = 0;
          v99 = 0;
          LOBYTE(v100) = 0;
          v101 = 1;
          v102 = 0;
          v103 = 0;
          v104 = 0;
          v105 = 0;
          v35 = (char *)Ofc::CProxyPtrImpl::GetChecked(*a3);
          v36 = Ofc::TSingleton<Art::GelTranslator>::Instance();
          v37 = *(__int64 (__fastcall **)(__int64, _QWORD **, _BYTE *, char *, char *, __m128i *, __int128 *))(*(_QWORD *)v36 + 64LL);
          v38 = *(__m128d *)(v35 + 168);
          v39 = *((float *)v35 + 41) * _mm_unpackhi_pd(v38, v38).m128d_f64[0];
          *(double *)si128.m128i_i64 = *((float *)v35 + 40) * v38.m128d_f64[0];
          *(double *)&si128.m128i_i64[1] = v39;
          v40 = (__int64 *)v37(v36, &v65, v89, v35 + 208, v35 + 200, &si128, &v95);
          v41 = *v40;
          *v40 = 0;
          if ( v65 )
            (*(void (__fastcall **)(_QWORD *))(v65[1] + 8LL))(v65 + 1);
          if ( !v41 )
            Mso::Diagnostics::SendErrorTag(507277983, 1339);
          *a2 = v41;
          Art::GelEffectCreateParams::~GelEffectCreateParams((Art::GelEffectCreateParams *)&v95);
          Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v71);
          Art::ShapePropertyBag::~ShapePropertyBag((Art::ShapePropertyBag *)v89);
          Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v79);
          if ( v31 )
          {
            Art::ShapeStyleData::~ShapeStyleData(v31);
            Mso::Memory::Free(v31, v42);
          }
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v62);
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v63);
          Art::ThemeInfo::~ThemeInfo((Art::ThemeInfo *)&v80);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v66);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v67);
          if ( v77 )
          {
            v43 = *(void (**)(void))(*(_QWORD *)v77 + 8LL);
LABEL_59:
            v43();
            return a2;
          }
          return a2;
        }
      }
      Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v71);
      Art::ShapePropertyBag::~ShapePropertyBag((Art::ShapePropertyBag *)v89);
      Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v79);
      if ( v31 )
      {
        Art::ShapeStyleData::~ShapeStyleData(v31);
        Mso::Memory::Free(v31, v44);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v62);
    }
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v63);
    Art::ThemeInfo::~ThemeInfo((Art::ThemeInfo *)&v80);
  }
  GEL::ITopLevelEffect::Create(&v74, v8);
  GEL::IEffectContainer::Create(&v73);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Art::ViewToHostX(v45, a3);
  GEL::IPen::Create(&v78, v46, &si128);
  v47 = v73;
  v48 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 144LL);
  v49 = v77;
  v50 = (_QWORD *)GEL::IEffectPennedPath::Create(&v65, v77, v78);
  v48(v47, *v50);
  v51 = v65;
  if ( v65 )
    (*(void (__fastcall **)(_QWORD *))(*v65 + 8LL))(v65);
  v71 = _mm_load_si128((const __m128i *)&_xmm);
  Art::ViewToHostX(v51, a3);
  GEL::IPen::Create(&v72, v52, &v71);
  v68 = 0;
  v69 = 0;
  v70 = 0x80000000;
  *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v68) = 0x4008000000000000LL;
  *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v68) = 0x4008000000000000LL;
  (*(void (__fastcall **)(__int64, Mso::Memory **))(*(_QWORD *)v72 + 96LL))(v72, &v68);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 112LL))(v72, 0);
  v53 = v73;
  v54 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 144LL);
  v55 = (_QWORD *)GEL::IEffectPennedPath::Create(&v65, v49, v72);
  v54(v53, *v55);
  if ( v65 )
    (*(void (__fastcall **)(_QWORD *))(*v65 + 8LL))(v65);
  v56 = *(_QWORD **)(a1 + 176);
  v57 = (double)(int)Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(v56[1]);
  v58 = (double)(int)Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*v56);
  v86[0] = _mm_load_si128((const __m128i *)&_xmm);
  v86[1] = _mm_load_si128((const __m128i *)&_xmm);
  v87 = v58;
  v88 = v57;
  (*(void (__fastcall **)(_QWORD *, __int64, _OWORD *))(*v74 + 120LL))(v74, v73, v86);
  *a2 = v74;
  v74 = 0;
  if ( v68 )
    Mso::Memory::Free(v68, v59);
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 8LL))(v72);
  if ( v78 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 8LL))(v78);
  if ( v73 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 8LL))(v73);
  if ( v74 )
    (*(void (__fastcall **)(_QWORD *))(v74[1] + 8LL))(v74 + 1);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v66);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v67);
  if ( v49 )
  {
    v43 = *(void (**)(void))(*(_QWORD *)v49 + 8LL);
    goto LABEL_59;
  }
  return a2;
}

```

## disassembly

```asm
0x1805a47c0  mov     rax, rsp
0x1805a47c3  mov     [rax+20h], rbx
0x1805a47c7  push    rbp
0x1805a47c8  push    rsi
0x1805a47c9  push    rdi
0x1805a47ca  push    r12
0x1805a47cc  push    r13
0x1805a47ce  push    r14
0x1805a47d0  push    r15
0x1805a47d2  lea     rbp, [rax-1B8h]
0x1805a47d9  sub     rsp, 280h
0x1805a47e0  movaps  xmmword ptr [rax-48h], xmm6
0x1805a47e4  mov     rax, cs:__security_cookie
0x1805a47eb  xor     rax, rsp
0x1805a47ee  mov     [rbp+1B0h+var_50], rax
0x1805a47f5  mov     rbx, r9
0x1805a47f8  mov     r14, r8
0x1805a47fb  mov     r15, rdx
0x1805a47fe  mov     r13, rcx
0x1805a4801  mov     [rsp+2B0h+var_250], rdx
0x1805a4806  xor     edi, edi
0x1805a4808  mov     rcx, [r8]; this
0x1805a480b  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a4810  mov     r12d, [rax+180h]
0x1805a4817  lea     eax, [rdi+1]
0x1805a481a  mov     r9d, eax
0x1805a481d  mov     r8d, eax
0x1805a4820  mov     rdx, [r13+0B8h]
0x1805a4827  lea     rcx, [rbp+1B0h+var_1E0]
0x1805a482b  call    ?ConvertPath2DToGelPath@Art@@YA?AV?$TCntPtr@$$CBUIPath@GEL@@@Ofc@@AEBVPath2D@1@_K1@Z; Art::ConvertPath2DToGelPath(Art::Path2D const &,unsigned __int64,unsigned __int64)
0x1805a4830  nop
0x1805a4831  mov     rcx, [r14]; this
0x1805a4834  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a4839  mov     edx, [rbx+1Ch]
0x1805a483c  sub     edx, [rax+0BCh]
0x1805a4842  mov     ecx, [rbx+18h]
0x1805a4845  sub     ecx, [rax+0B8h]
0x1805a484b  mov     dword ptr [rsp+2B0h+var_268], ecx
0x1805a484f  mov     dword ptr [rsp+2B0h+var_268+4], edx
0x1805a4853  mov     rcx, [rsp+2B0h+var_268]
0x1805a4858  mov     [rsp+2B0h+var_260], rcx
0x1805a485d  lea     r8, [rsp+2B0h+var_260]
0x1805a4862  lea     rdx, [rbp+1B0h+var_228]
0x1805a4866  mov     rcx, rax
0x1805a4869  call    ?ConvertViewToHostCoordinates@View@Art@@QEBA?AVPoint64@2@AEBVCPoint@Ofc@@@Z; Art::View::ConvertViewToHostCoordinates(Ofc::CPoint const &)
0x1805a486e  mov     rbx, [r13+0B0h]
0x1805a4875  mov     rcx, [rbx+8]
0x1805a4879  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x1805a487e  mov     rcx, qword ptr [rbp+1B0h+var_228+8]
0x1805a4882  sub     rcx, rax
0x1805a4885  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x1805a488a  mov     [rsp+2B0h+var_260], rax
0x1805a488f  mov     rcx, [rbx]
0x1805a4892  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x1805a4897  mov     rcx, qword ptr [rbp+1B0h+var_228]
0x1805a489b  sub     rcx, rax
0x1805a489e  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x1805a48a3  mov     [rsp+2B0h+var_258], rax
0x1805a48a8  lea     r8, [rsp+2B0h+var_260]
0x1805a48ad  lea     rdx, [rsp+2B0h+var_258]
0x1805a48b2  lea     rcx, [rbp+1B0h+var_1F8]
0x1805a48b6  call    ??0Point2D@Art@@QEAA@AEBV?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@1@0@Z; Art::Point2D::Point2D(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &,Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1805a48bb  lea     rcx, [rbp+1B0h+var_1F8]; struct Art::Point2D *
0x1805a48bf  call    ?FClickedAtBeginning@FreeformDragTracker@Dr@@SA_NAEBVPoint2D@Art@@@Z; Dr::FreeformDragTracker::FClickedAtBeginning(Art::Point2D const &)
0x1805a48c4  mov     sil, al
0x1805a48c7  mov     rcx, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1805a48ce  mov     [rsp+2B0h+var_240], rcx
0x1805a48d3  mov     [rsp+2B0h+var_248], rcx
0x1805a48d8  mov     rcx, [r14]; this
0x1805a48db  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a48e0  mov     edx, [rax+100h]
0x1805a48e6  test    edx, edx
0x1805a48e8  jz      short loc_1805A4905
0x1805a48ea  dec     edx
0x1805a48ec  lea     rcx, [rax+0F8h]
0x1805a48f3  call    ??A?$TArray@VCVarStr@Ofc@@@Ofc@@QEBAAEBVCVarStr@1@K@Z; Ofc::TArray<Ofc::CVarStr>::operator[](ulong)
0x1805a48f8  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1805a48fb  lea     rcx, [rsp+2B0h+var_248]; struct Ofc::CProxyPtrImpl **
0x1805a4900  call    ?StrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1805a4905  mov     rcx, [rsp+2B0h+var_248]; this
0x1805a490a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a490f  mov     rdx, rax
0x1805a4912  mov     rcx, [rax]
0x1805a4915  mov     rax, [rcx+148h]
0x1805a491c  mov     rcx, rdx
0x1805a491f  call    cs:__guard_dispatch_icall_fptr
0x1805a4925  mov     rcx, [rax]
0x1805a4928  cmp     [rcx+10h], rdi
0x1805a492c  jz      loc_1805A49B9
0x1805a4932  mov     rcx, [rsp+2B0h+var_248]; this
0x1805a4937  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a493c  mov     rdx, rax
0x1805a493f  mov     rcx, [rax]
0x1805a4942  mov     rax, [rcx+148h]
0x1805a4949  mov     rcx, rdx
0x1805a494c  call    cs:__guard_dispatch_icall_fptr
0x1805a4952  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x1805a4955  mov     eax, [rcx+4]
0x1805a4958  mov     ebx, 80000000h
0x1805a495d  cmp     eax, ebx
0x1805a495f  jz      short loc_1805A4965
0x1805a4961  lock inc dword ptr [rcx+4]
0x1805a4965  mov     [rsp+2B0h+var_258], rcx
0x1805a496a  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1805a496f  mov     [rsp+2B0h+var_260], rax
0x1805a4974  mov     rcx, rax; this
0x1805a4977  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a497c  mov     rdx, rax
0x1805a497f  mov     rcx, [rax]
0x1805a4982  mov     rax, [rcx+0B8h]
0x1805a4989  mov     rcx, rdx
0x1805a498c  call    cs:__guard_dispatch_icall_fptr
0x1805a4992  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1805a4995  lea     rcx, [rsp+2B0h+var_240]; struct Ofc::CProxyPtrImpl **
0x1805a499a  call    ?CheckedStrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1805a499f  nop
0x1805a49a0  lea     rcx, [rsp+2B0h+var_260]; struct Ofc::CProxyPtrImpl **
0x1805a49a5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1805a49aa  lea     rcx, [rsp+2B0h+var_258]; struct Ofc::CProxyPtrImpl **
0x1805a49af  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1805a49b4  jmp     loc_1805A4A5E
0x1805a49b9  mov     rcx, [r14]; this
0x1805a49bc  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a49c1  mov     rcx, [rax+30h]; this
0x1805a49c5  mov     eax, [rcx]
0x1805a49c7  mov     ebx, 80000000h
0x1805a49cc  cmp     eax, ebx
0x1805a49ce  jz      short loc_1805A49D3
0x1805a49d0  lock inc dword ptr [rcx]
0x1805a49d3  mov     [rbp+1B0h+var_200], rcx
0x1805a49d7  cmp     [rcx+10h], rdi
0x1805a49db  jz      short loc_1805A4A55
0x1805a49dd  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a49e2  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x1805a49e6  mov     eax, [rcx+4]
0x1805a49e9  cmp     eax, ebx
0x1805a49eb  jz      short loc_1805A49F1
0x1805a49ed  lock inc dword ptr [rcx+4]
0x1805a49f1  mov     [rsp+2B0h+var_260], rcx
0x1805a49f6  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1805a49fb  mov     [rsp+2B0h+var_268], rax
0x1805a4a00  lea     rcx, [rsp+2B0h+var_260]; struct Ofc::CProxyPtrImpl **
0x1805a4a05  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1805a4a0a  mov     rcx, [rsp+2B0h+var_268]; this
0x1805a4a0f  cmp     [rcx+10h], rdi
0x1805a4a13  jz      short loc_1805A4A4A
0x1805a4a15  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a4a1a  mov     r8, rax
0x1805a4a1d  mov     rcx, [rax]
0x1805a4a20  mov     rax, [rcx+60h]
0x1805a4a24  lea     rdx, [rsp+2B0h+var_258]
0x1805a4a29  mov     rcx, r8
0x1805a4a2c  call    cs:__guard_dispatch_icall_fptr
0x1805a4a32  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1805a4a35  lea     rcx, [rsp+2B0h+var_240]; struct Ofc::CProxyPtrImpl **
0x1805a4a3a  call    ?CheckedStrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1805a4a3f  lea     rcx, [rsp+2B0h+var_258]; struct Ofc::CProxyPtrImpl **
0x1805a4a44  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1805a4a49  nop
0x1805a4a4a  lea     rcx, [rsp+2B0h+var_268]; struct Ofc::CProxyPtrImpl **
0x1805a4a4f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1805a4a54  nop
0x1805a4a55  lea     rcx, [rbp+1B0h+var_200]; struct Ofc::CProxyPtrImpl **
0x1805a4a59  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1805a4a5e  mov     rcx, [rsp+2B0h+var_240]; this
0x1805a4a63  cmp     [rcx+10h], rdi
0x1805a4a67  jz      loc_1805A4EDE
0x1805a4a6d  lea     rax, ??_7ThemeInfo@Art@@6B@; const Art::ThemeInfo::`vftable'
0x1805a4a74  mov     [rbp+1B0h+var_1B8], rax
0x1805a4a78  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1805a4a7f  mov     [rbp+1B0h+var_1B0], rax
0x1805a4a83  mov     [rbp+1B0h+var_1A8], rax
0x1805a4a87  mov     [rbp+1B0h+var_1A0], rax
0x1805a4a8b  mov     [rbp+1B0h+var_198], rax
0x1805a4a8f  mov     [rbp+1B0h+var_190], edi
0x1805a4a92  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a4a97  mov     r8, rax
0x1805a4a9a  mov     rcx, [rax]
0x1805a4a9d  mov     rax, [rcx+0A0h]
0x1805a4aa4  lea     rdx, [rbp+1B0h+var_1B8]
0x1805a4aa8  mov     rcx, r8
0x1805a4aab  call    cs:__guard_dispatch_icall_fptr
0x1805a4ab1  mov     rcx, [rbp+1B0h+var_1B0]; struct Ofc::CProxyPtrImpl *
0x1805a4ab5  mov     eax, [rcx+4]
0x1805a4ab8  cmp     eax, ebx
0x1805a4aba  jz      short loc_1805A4AC0
0x1805a4abc  lock inc dword ptr [rcx+4]
0x1805a4ac0  mov     [rsp+2B0h+var_260], rcx
0x1805a4ac5  cmp     [rcx+10h], rdi
0x1805a4ac9  jz      loc_1805A4ECB
0x1805a4acf  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1805a4ad4  mov     [rsp+2B0h+var_268], rax
0x1805a4ad9  mov     [rsp+2B0h+var_258], rdi
0x1805a4ade  lea     rcx, [rbp+1B0h+var_1D0]; this
0x1805a4ae2  call    ??0LinearShadeProps@Art@@QEAA@XZ; Art::LinearShadeProps::LinearShadeProps(void)
0x1805a4ae7  mov     rcx, [rsp+2B0h+var_268]; this
0x1805a4aec  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a4af1  mov     rdx, rax
0x1805a4af4  mov     rcx, [rax]
0x1805a4af7  mov     rax, [rcx+58h]
0x1805a4afb  mov     rcx, rdx
0x1805a4afe  call    cs:__guard_dispatch_icall_fptr
0x1805a4b04  mov     rbx, rax
0x1805a4b07  lea     rdx, [rax+38h]
0x1805a4b0b  lea     rcx, [rsp+2B0h+var_258]
0x1805a4b10  call    ??4?$TOptional@VShapeStyle@Art@@@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::TOptional<Art::ShapeStyle>::operator=(Ofc::TOptional<Art::ShapeStyle> const &)
0x1805a4b15  mov     rdx, rbx
0x1805a4b18  lea     rcx, [rbp+1B0h+var_1D0]; this
0x1805a4b1c  call    ??4EffectList@Art@@QEAAAEAV01@AEBV01@@Z; Art::EffectList::operator=(Art::EffectList const &)
0x1805a4b21  lea     rcx, [rbp+1B0h+var_140]; this
0x1805a4b25  call    ??0ShapePropertyBag@Art@@QEAA@XZ; Art::ShapePropertyBag::ShapePropertyBag(void)
0x1805a4b2a  nop
0x1805a4b2b  mov     rbx, [rsp+2B0h+var_258]
0x1805a4b30  test    rbx, rbx
0x1805a4b33  jz      short loc_1805A4B46
0x1805a4b35  lea     r8, [rbp+1B0h+var_1D0]
0x1805a4b39  mov     rdx, rbx
0x1805a4b3c  lea     rcx, [rsp+2B0h+var_268]
0x1805a4b41  call    ?ResolvePropLists@StyleResolverHelper@Art@@SAXAEBV?$TReferringPtr@$$CBVITheme@Art@@@Ofc@@AEBVShapeStyle@2@AEAV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@2@@Z; Art::StyleResolverHelper::ResolvePropLists(Ofc::TReferringPtr<Art::ITheme const> const &,Art::ShapeStyle const &,Art::ShapePropsMethods<Art::ShapePropsData_<0>> &)
0x1805a4b46  lea     rdx, [rbp+1B0h+var_1D0]
0x1805a4b4a  lea     rcx, [rbp+1B0h+var_1B8]
0x1805a4b4e  call    ?ResolveColorsForPropLists@StyleResolverHelper@Art@@SAXAEBVThemeInfo@2@AEAV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@2@@Z; Art::StyleResolverHelper::ResolveColorsForPropLists(Art::ThemeInfo const &,Art::ShapePropsMethods<Art::ShapePropsData_<0>> &)
0x1805a4b53  xor     eax, eax
0x1805a4b55  mov     qword ptr [rbp+1B0h+var_228], rax
0x1805a4b59  mov     qword ptr [rbp+1B0h+var_228+8], rdi
0x1805a4b5d  lea     rdx, [rbp+1B0h+var_228]; struct Art::Geometry2D *
0x1805a4b61  lea     rcx, [rbp+1B0h+var_1F8]; this
0x1805a4b65  call    ??0GeometryBuilder@Art@@QEAA@AEAVGeometry2D@1@@Z; Art::GeometryBuilder::GeometryBuilder(Art::Geometry2D &)
0x1805a4b6a  nop
0x1805a4b6b  lea     rcx, [rbp+1B0h+var_1F8]; this
0x1805a4b6f  call    ?GetPaths@GeometryBuilder@Art@@QEAAAEAVPath2DTable@2@XZ; Art::GeometryBuilder::GetPaths(void)
0x1805a4b74  mov     rdi, rax
0x1805a4b77  lea     rcx, [rax+8]; this
0x1805a4b7b  lea     rdx, ?Do@?$TDestructRange@VPath2D@Art@@$0A@@Ofc@@SAXPEAEK@Z; void (*)(unsigned __int8 *, unsigned int)
0x1805a4b82  call    ?Reset@CArrayImpl@Ofc@@IEAAXP6AXPEAEK@Z@Z; Ofc::CArrayImpl::Reset(void (*)(uchar *,ulong))
0x1805a4b87  mov     dword ptr [rdi], 0
0x1805a4b8d  lea     rcx, [rbp+1B0h+var_1F8]; this
0x1805a4b91  call    ?GetPaths@GeometryBuilder@Art@@QEAAAEAVPath2DTable@2@XZ; Art::GeometryBuilder::GetPaths(void)
0x1805a4b96  mov     rdx, [r13+0B8h]; struct Art::Path2D *
0x1805a4b9d  mov     rcx, rax; this
0x1805a4ba0  call    ?AddPath2D@Path2DTable@Art@@QEAAXAEBVPath2D@2@@Z; Art::Path2DTable::AddPath2D(Art::Path2D const &)
0x1805a4ba5  lea     rcx, [rbp+1B0h+var_1F8]; this
0x1805a4ba9  call    ?Validate@GeometryBuilder@Art@@QEBAXXZ; Art::GeometryBuilder::Validate(void)
0x1805a4bae  nop
0x1805a4baf  lea     rcx, [rbp+1B0h+var_1F8]; this
0x1805a4bb3  call    ??1GeometryBuilder@Art@@QEAA@XZ; Art::GeometryBuilder::~GeometryBuilder(void)
0x1805a4bb8  lea     rdx, [rbp+1B0h+var_228]
0x1805a4bbc  lea     rcx, [rbp+1B0h+var_1D0]
0x1805a4bc0  call    ??$Set@UGeometry@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEAAXAEBVGeometry2D@Art@@@Z; Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Geometry>(Art::Geometry2D const &)
0x1805a4bc5  xorps   xmm0, xmm0
0x1805a4bc8  movdqu  [rbp+1B0h+var_B0], xmm0
0x1805a4bd0  xorps   xmm1, xmm1
0x1805a4bd3  movdqu  [rbp+1B0h+var_A0], xmm1
0x1805a4bdb  xor     edi, edi
0x1805a4bdd  mov     [rbp+1B0h+var_90], edi
0x1805a4be3  mov     [rbp+1B0h+var_8C], di
0x1805a4bea  xor     eax, eax
0x1805a4bec  mov     [rbp+1B0h+var_88], rax
0x1805a4bf3  mov     [rbp+1B0h+var_80], rax
0x1805a4bfa  mov     r9, [r13+0B0h]
0x1805a4c01  lea     rdx, [r9+8]
0x1805a4c05  lea     rcx, [rbp+1B0h+var_200]
0x1805a4c09  call    ??0?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAA@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1805a4c0e  mov     rdx, r9
0x1805a4c11  lea     rcx, [rsp+2B0h+var_250]
0x1805a4c16  call    ??0?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAA@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1805a4c1b  lea     r8, [rbp+1B0h+var_200]
0x1805a4c1f  lea     rdx, [rsp+2B0h+var_250]
0x1805a4c24  lea     rcx, [rbp+1B0h+var_B0]
0x1805a4c2b  call    ?SetXY@Point2D@Art@@QEAAXV?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@2@0@Z; Art::Point2D::SetXY(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>,Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>)
0x1805a4c30  lea     rdx, [rbp+1B0h+var_B0]
0x1805a4c37  lea     rcx, [rbp+1B0h+var_1D0]
0x1805a4c3b  call    ??$Set@UTransform@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEAAXAEBVTransform2D@Art@@@Z; Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Transform>(Art::Transform2D const &)
0x1805a4c40  mov     word ptr [rsp+2B0h+var_270], di
0x1805a4c45  lea     r8, [rsp+2B0h+var_270]
0x1805a4c4a  lea     rdx, [rbp+1B0h+var_140]
0x1805a4c4e  lea     rcx, [rbp+1B0h+var_1D0]
0x1805a4c52  call    ?PropListToObj@Art@@YAXAEBV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@1@AEAVShapePropertyBag@1@AEAUPropListConversionOptions@1@@Z; Art::PropListToObj(Art::ShapePropsMethods<Art::ShapePropsData_<0>> const &,Art::ShapePropertyBag &,Art::PropListConversionOptions &)
0x1805a4c57  mov     [rbp+1B0h+var_200], rdi
0x1805a4c5b  cmp     [rbp+1B0h+var_B3], dil
0x1805a4c62  jz      loc_1805A4E83
0x1805a4c68  cmp     [rbp+1B0h+var_B2], dil
0x1805a4c6f  jz      short loc_1805A4C88
0x1805a4c71  mov     [rbp+1B0h+var_B2], 1
0x1805a4c78  lea     rcx, [rbp+1B0h+var_E8]
0x1805a4c7f  call    ??$Is@UNone@Line@Art@@@?$TChoice@VLineStyleDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::Is<Art::Line::None>(void)
0x1805a4c84  test    al, al
0x1805a4c86  jz      short loc_1805A4CA5
0x1805a4c88  test    sil, sil
0x1805a4c8b  jz      loc_1805A4E83
0x1805a4c91  lea     rcx, [rbp+1B0h+var_F8]
0x1805a4c98  call    ??$Is@UNone@Fill@Art@@@?$TChoice@VFillStyleDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::Is<Art::Fill::None>(void)
0x1805a4c9d  test    al, al
0x1805a4c9f  jnz     loc_1805A4E83
0x1805a4ca5  test    sil, sil
0x1805a4ca8  jnz     short loc_1805A4CB6
0x1805a4caa  lea     rcx, [rbp+1B0h+var_F8]
0x1805a4cb1  call    ??$SwitchTo@UNone@Fill@Art@@@?$TChoice@VFillStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVNoFill@Art@@XZ; Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::None>(void)
0x1805a4cb6  mov     rcx, [rbp+1B0h+var_D8]
0x1805a4cbd  test    rcx, rcx
  ... truncated ...
```
