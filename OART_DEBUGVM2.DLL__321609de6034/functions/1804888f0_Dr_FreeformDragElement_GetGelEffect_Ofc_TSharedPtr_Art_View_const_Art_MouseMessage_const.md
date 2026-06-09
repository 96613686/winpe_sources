# Dr::FreeformDragElement::GetGelEffect(Ofc::TSharedPtr<Art::View> const &,Art::MouseMessage const &)

- ea: `0x1804888f0`
- end: `0x180489388`
- name: `?GetGelEffect@FreeformDragElement@Dr@@UEBA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBV?$TSharedPtr@VView@Art@@@4@AEBVMouseMessage@Art@@@Z`
- size: `2712`
- prototype: ``
- caller_count: `0`
- callee_count: `49`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000eb20`
- `0x18001a840`
- `0x180025300`
- `0x18002a690`
- `0x1800473f8`
- `0x180052708`
- `0x18007caa0`
- `0x180083ff0`
- `0x1800b9620`
- `0x1800ba0f0`
- `0x1800ba280`
- `0x1800e34d0`
- `0x1800ea450`
- `0x1800f82f0`
- `0x1800fbb00`
- `0x1800fcf60`
- `0x1801011b0`
- `0x180104824`
- `0x18010db54`
- `0x1801aa980`
- `0x180210de4`
- `0x180237470`
- `0x18023ae20`
- `0x18023fddc`
- `0x1802493a0`
- `0x180249430`
- `0x180249480`
- `0x180249600`
- `0x1802769e0`
- `0x180279000`
- `0x180279010`
- `0x180279030`
- `0x180279050`
- `0x18027c460`
- `0x18027c4c0`
- `0x180286888`
- `0x18029a1c0`
- `0x18029d430`
- `0x180445080`
- `0x1804888f0`
- `0x180489684`
- `0x18055ebb0`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bcadc`
- `0x1806cf9e8`
- `0x1806d19bc`
- `0x1806d19e4`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x180488eaf`
- `KERNEL32!DecodePointer` at `0x180488ec1`
- `KERNEL32!DecodePointer` at `0x180488eaf`
- `KERNEL32!DecodePointer` at `0x180488ec1`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18048910b`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x180489210`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18048910b`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x180489210`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1804890e6`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x180489168`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1804890e6`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x180489168`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1804890b4`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1804890b4`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1804890aa`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1804890aa`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180488ff5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18048907e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804892c3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180488ff5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18048907e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1804892c3`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x180488fb5`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x180488fb5`

## pseudocode

```c
_QWORD *__fastcall Dr::FreeformDragElement::GetGelEffect(__int64 a1, _QWORD *a2, Ofc::CProxyPtrImpl **a3, __int64 a4)
{
  unsigned int v8; // r12d
  _DWORD *Checked; // rax
  __int64 v10; // r8
  __int64 v11; // rbx
  bool v12; // si
  _DWORD *v13; // rax
  int v14; // edx
  struct Ofc::CProxyPtrImpl **v15; // rax
  void *v16; // rax
  void *v17; // rax
  struct Ofc::CProxyPtrImpl **v18; // rax
  void *v19; // rax
  struct Ofc::CProxyPtrImpl **v20; // rax
  struct Ofc::CProxyPtrImpl **v21; // rax
  struct Ofc::CProxyPtrImpl *v22; // rax
  struct Ofc::CProxyPtrImpl **v23; // rax
  void *v24; // rax
  struct Ofc::CProxyPtrImpl **v25; // rax
  void *v26; // rax
  struct Ofc::CProxyPtrImpl *v27; // rax
  void *v28; // rax
  __int64 v29; // rax
  Art::ShapeStyleData *v30; // rbx
  struct Art::Path2DTable *Paths; // rdi
  Art::Path2DTable *v32; // rax
  __int64 v33; // r8
  void (*v34)(void); // rdx
  char *v35; // rdi
  bool v36; // r8
  __int64 *v37; // rcx
  unsigned __int64 v38; // rdx
  unsigned int v39; // r8d
  __int64 (__fastcall *v40)(__int64); // rax
  _QWORD *v41; // rax
  __int64 v42; // rax
  __m128d v43; // xmm2
  double v44; // xmm1_8
  __int64 *v45; // rax
  __int64 v46; // rdi
  void *v47; // rdx
  void (*v48)(void); // rax
  void *v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rbx
  void (__fastcall *v53)(__int64, _QWORD); // rsi
  __int64 v54; // rdi
  _QWORD *v55; // rax
  _QWORD *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rbx
  void (__fastcall *v59)(__int64, _QWORD); // rsi
  _QWORD *v60; // rax
  double v61; // xmm3_8
  __int64 v62; // r8
  void *v63; // rdx
  struct Ofc::CProxyPtrImpl *v65; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v66; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v67; // [rsp+50h] [rbp-B0h] BYREF
  Ofc::CProxyPtrImpl *v68; // [rsp+58h] [rbp-A8h] BYREF
  Art::ShapeStyleData *v69; // [rsp+60h] [rbp-A0h] BYREF
  Ofc::CProxyPtrImpl *v70; // [rsp+68h] [rbp-98h] BYREF
  Ofc::CProxyPtrImpl *v71; // [rsp+70h] [rbp-90h] BYREF
  struct Ofc::CProxyPtrImpl *v72; // [rsp+78h] [rbp-88h] BYREF
  Mso::Memory *v73; // [rsp+80h] [rbp-80h] BYREF
  int v74; // [rsp+88h] [rbp-78h]
  unsigned int v75; // [rsp+8Ch] [rbp-74h]
  __m128i v76; // [rsp+90h] [rbp-70h] BYREF
  __int64 v77; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v78; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v79; // [rsp+B0h] [rbp-50h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v82; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v83[24]; // [rsp+E0h] [rbp-20h] BYREF
  void **v84; // [rsp+F8h] [rbp-8h] BYREF
  struct Ofc::CProxyPtrImpl *v85; // [rsp+100h] [rbp+0h]
  struct Ofc::CProxyPtrImpl *v86; // [rsp+108h] [rbp+8h]
  struct Ofc::CProxyPtrImpl *v87; // [rsp+110h] [rbp+10h]
  struct Ofc::CProxyPtrImpl *v88; // [rsp+118h] [rbp+18h]
  int v89; // [rsp+120h] [rbp+20h]
  __int64 v90; // [rsp+138h] [rbp+38h]
  _OWORD v91[2]; // [rsp+140h] [rbp+40h] BYREF
  double v92; // [rsp+160h] [rbp+60h]
  double v93; // [rsp+168h] [rbp+68h]
  _BYTE v94[72]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v95[16]; // [rsp+1B8h] [rbp+B8h] BYREF
  char v96[16]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v97; // [rsp+1D8h] [rbp+D8h]
  char v98; // [rsp+1FDh] [rbp+FDh]
  char v99; // [rsp+1FEh] [rbp+FEh]
  __int128 v100; // [rsp+200h] [rbp+100h] BYREF
  __int128 v101; // [rsp+210h] [rbp+110h]
  int v102; // [rsp+220h] [rbp+120h]
  __int16 v103; // [rsp+224h] [rbp+124h]
  __int64 v104; // [rsp+228h] [rbp+128h]
  __int64 v105; // [rsp+230h] [rbp+130h]
  char v106; // [rsp+238h] [rbp+138h]
  __int64 v107; // [rsp+240h] [rbp+140h]
  __int16 v108; // [rsp+248h] [rbp+148h]
  __int64 v109; // [rsp+250h] [rbp+150h]
  char v110; // [rsp+258h] [rbp+158h]

  v66 = a2;
  v8 = *((_DWORD *)Ofc::CProxyPtrImpl::GetChecked(*a3) + 96);
  Art::ConvertPath2DToGelPath(&v81, *(_QWORD *)(a1 + 184), 1, 1);
  Checked = Ofc::CProxyPtrImpl::GetChecked(*a3);
  v68 = (Ofc::CProxyPtrImpl *)__PAIR64__(*(_DWORD *)(a4 + 28) - Checked[47], *(_DWORD *)(a4 + 24) - Checked[46]);
  v65 = v68;
  Art::View::ConvertViewToHostCoordinates(Checked, &v76, &v65);
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
    &v69,
    *(_QWORD *)(a1 + 176));
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
    &v65,
    v10 + 8);
  v11 = v76.m128i_i64[0] - (_QWORD)v69;
  v65 = (struct Ofc::CProxyPtrImpl *)Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(v76.m128i_i64[1] - (_QWORD)v65);
  v69 = (Art::ShapeStyleData *)Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(v11);
  Art::Point2D::Point2D(&si128, &v69, &v65);
  v12 = Dr::FreeformDragTracker::FClickedAtBeginning((const struct Art::Point2D *)&si128);
  v71 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v70 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v13 = Ofc::CProxyPtrImpl::GetChecked(*a3);
  v14 = v13[64];
  if ( v14 )
  {
    v15 = (struct Ofc::CProxyPtrImpl **)Ofc::TArray<Ofc::CVarStr>::operator[](v13 + 62, (unsigned int)(v14 - 1));
    Ofc::CProxyPtrImpl::StrongAssign(&v70, *v15);
  }
  v16 = Ofc::CProxyPtrImpl::GetChecked(v70);
  if ( *(_QWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v16 + 328LL))(v16) + 16LL) )
  {
    v17 = Ofc::CProxyPtrImpl::GetChecked(v70);
    v18 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v17 + 328LL))(v17);
    v69 = Ofc::CProxyPtrImpl::WeakAddRef(*v18);
    v65 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v69);
    v19 = Ofc::CProxyPtrImpl::GetChecked(v65);
    v20 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v19 + 184LL))(v19);
    Ofc::CProxyPtrImpl::CheckedStrongAssign(&v71, *v20);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v65);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v69);
  }
  else
  {
    v21 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(*a3);
    v22 = Ofc::CProxyPtrImpl::StrongAddRef(v21[6]);
    v72 = v22;
    if ( *((_QWORD *)v22 + 2) )
    {
      v23 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v22);
      v65 = Ofc::CProxyPtrImpl::WeakAddRef(v23[11]);
      v68 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v65);
      Ofc::CProxyPtrImpl::DtorWeakRelease(&v65);
      if ( *((_QWORD *)v68 + 2) )
      {
        v24 = Ofc::CProxyPtrImpl::GetChecked(v68);
        v25 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *, Art::ShapeStyleData **))(*(_QWORD *)v24 + 96LL))(
                                              v24,
                                              &v69);
        Ofc::CProxyPtrImpl::CheckedStrongAssign(&v71, *v25);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v69);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v68);
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v72);
  }
  if ( *((_QWORD *)v71 + 2) )
  {
    v84 = &Art::ThemeInfo::`vftable';
    v85 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v86 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v87 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v88 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v89 = 0;
    v26 = Ofc::CProxyPtrImpl::GetChecked(v71);
    (*(void (__fastcall **)(void *, void ***))(*(_QWORD *)v26 + 160LL))(v26, &v84);
    v27 = Ofc::CProxyPtrImpl::WeakAddRef(v85);
    v65 = v27;
    if ( *((_QWORD *)v27 + 2) )
    {
      v68 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v27);
      v69 = 0;
      Art::LinearShadeProps::LinearShadeProps((Art::LinearShadeProps *)v83);
      v28 = Ofc::CProxyPtrImpl::GetChecked(v68);
      v29 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v28 + 88LL))(v28);
      Ofc::TOptional<Art::ShapeStyle>::operator=(&v69, v29 + 56);
      Art::EffectList::operator=((Art::EffectList *)v83);
      Art::ShapePropertyBag::ShapePropertyBag((Art::ShapePropertyBag *)v94);
      v30 = v69;
      if ( v69 )
        Art::StyleResolverHelper::ResolvePropLists(&v68, v69, v83);
      Art::StyleResolverHelper::ResolveColorsForPropLists(&v84, v83);
      v76 = 0u;
      Art::GeometryBuilder::GeometryBuilder((Art::GeometryBuilder *)&si128, (struct Art::Geometry2D *)&v76);
      Paths = Art::GeometryBuilder::GetPaths((Art::GeometryBuilder *)&si128);
      Ofc::CArrayImpl::Reset((struct Art::Path2DTable *)((char *)Paths + 8), Ofc::TDestructRange<Art::Path2D,0>::Do);
      *(_DWORD *)Paths = 0;
      v32 = Art::GeometryBuilder::GetPaths((Art::GeometryBuilder *)&si128);
      Art::Path2DTable::AddPath2D(v32, *(const struct Art::Path2D **)(a1 + 184));
      Art::GeometryBuilder::Validate((Art::GeometryBuilder *)&si128);
      Art::GeometryBuilder::~GeometryBuilder((Art::GeometryBuilder *)&si128);
      Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Geometry>((Ofc::Tph::CPropertySetImpl *)v83);
      v100 = 0;
      v101 = 0;
      v102 = 0;
      v103 = 0;
      v104 = 0;
      v105 = 0;
      Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
        &v72,
        *(_QWORD *)(a1 + 176) + 8LL);
      Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
        &v66,
        v33);
      Art::Point2D::SetXY(&v100, &v66, &v72);
      Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Transform>((Ofc::Tph::CPropertySetImpl *)v83);
      v67 = 0;
      Art::PropListToObj(v83, v94, &v67);
      v90 = 0;
      if ( v98 )
      {
        if ( v99 && (v99 = 1, !(unsigned __int8)Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::Is<Art::Line::None>(v96))
          || v12 && !(unsigned __int8)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::Is<Art::Fill::None>(v95) )
        {
          if ( !v12 )
            Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::None>(v95);
          if ( v97 )
            Art::Model3DStorageUpdateParamsData::ProjectionType_<0>::`scalar deleting destructor'(v97);
          v97 = 0;
          LODWORD(v100) = v8;
          *((_QWORD *)&v100 + 1) = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
          *(_QWORD *)&v101 = 0;
          *((_QWORD *)&v101 + 1) = 0x10000;
          LOWORD(v102) = 0;
          v104 = 0;
          LOBYTE(v105) = 0;
          v106 = 1;
          v107 = 0;
          v108 = 0;
          v109 = 0;
          v110 = 0;
          v35 = (char *)Ofc::CProxyPtrImpl::GetChecked(*a3);
          v37 = (__int64 *)Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
          if ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
          {
            while ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
            {
              if ( _InterlockedCompareExchange64(
                     (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
                     1,
                     0) )
              {
                v66 = 0;
                std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v66);
              }
              else
              {
                LOBYTE(v34) = 1;
                Ofc::AtExit(Ofc::TSingleton<Art::GelTranslator>::Shutdown, v34, v36);
                if ( DecodePointer(Ptr) )
                {
                  v40 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
                  v41 = (_QWORD *)v40(8);
                }
                else
                {
                  v41 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v38, v39);
                }
                *v41 = &Art::GelTranslator::`vftable';
                _InterlockedCompareExchange64(
                  (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
                  (signed __int64)v41,
                  1);
              }
            }
            v37 = (__int64 *)Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
          }
          v42 = *v37;
          v43 = *(__m128d *)(v35 + 168);
          v44 = *((float *)v35 + 41) * _mm_unpackhi_pd(v43, v43).m128d_f64[0];
          *(double *)si128.m128i_i64 = *((float *)v35 + 40) * v43.m128d_f64[0];
          *(double *)&si128.m128i_i64[1] = v44;
          v45 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, struct Ofc::CProxyPtrImpl **, _BYTE *, char *, char *, __m128i *, __int128 *))(v42 + 64))(
                             v37,
                             &v72,
                             v94,
                             v35 + 208,
                             v35 + 200,
                             &si128,
                             &v100);
          v46 = *v45;
          *v45 = 0;
          if ( v72 )
            (*(void (__fastcall **)(char *))(*((_QWORD *)v72 + 1) + 8LL))((char *)v72 + 8);
          if ( !v46 )
            Mso::Diagnostics::SendErrorTag(507277983, 1339);
          *a2 = v46;
          Art::GelEffectCreateParams::~GelEffectCreateParams((Art::GelEffectCreateParams *)&v100);
          Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v76);
          Art::ShapePropertyBag::~ShapePropertyBag((Art::ShapePropertyBag *)v94);
          Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v83);
          if ( v30 )
          {
            Art::ShapeStyleData::~ShapeStyleData(v30);
            Mso::Memory::Free(v30, v47);
          }
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v68);
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v65);
          Art::ThemeInfo::~ThemeInfo((Art::ThemeInfo *)&v84);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v70);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v71);
          if ( v81 )
          {
            v48 = *(void (**)(void))(*(_QWORD *)v81 + 8LL);
LABEL_60:
            v48();
            return a2;
          }
          return a2;
        }
      }
      Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v76);
      Art::ShapePropertyBag::~ShapePropertyBag((Art::ShapePropertyBag *)v94);
      Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v83);
      if ( v30 )
      {
        Art::ShapeStyleData::~ShapeStyleData(v30);
        Mso::Memory::Free(v30, v49);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v68);
    }
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v65);
    Art::ThemeInfo::~ThemeInfo((Art::ThemeInfo *)&v84);
  }
  GEL::ITopLevelEffect::Create(&v79, v8);
  GEL::IEffectContainer::Create(&v78);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Art::ViewToHostX(v50, a3);
  GEL::IPen::Create(&v82, v51, &si128);
  v52 = v78;
  v53 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v78 + 144LL);
  v54 = v81;
  v55 = (_QWORD *)GEL::IEffectPennedPath::Create(&v66, v81, v82);
  v53(v52, *v55);
  v56 = v66;
  if ( v66 )
    (*(void (__fastcall **)(_QWORD *))(*v66 + 8LL))(v66);
  v76 = _mm_load_si128((const __m128i *)&_xmm);
  Art::ViewToHostX(v56, a3);
  GEL::IPen::Create(&v77, v57, &v76);
  v73 = 0;
  v74 = 0;
  v75 = 0x80000000;
  *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v73) = 0x4008000000000000LL;
  *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v73) = 0x4008000000000000LL;
  (*(void (__fastcall **)(__int64, Mso::Memory **))(*(_QWORD *)v77 + 96LL))(v77, &v73);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v77 + 112LL))(v77, 0);
  v58 = v78;
  v59 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v78 + 144LL);
  v60 = (_QWORD *)GEL::IEffectPennedPath::Create(&v66, v54, v77);
  v59(v58, *v60);
  if ( v66 )
    (*(void (__fastcall **)(_QWORD *))(*v66 + 8LL))(v66);
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
    &v66,
    *(_QWORD *)(a1 + 176) + 8LL);
  v61 = (double)(int)v66;
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
    &v66,
    v62);
  v91[0] = _mm_load_si128((const __m128i *)&_xmm);
  v91[1] = _mm_load_si128((const __m128i *)&_xmm);
  v92 = (double)(int)v66;
  v93 = v61;
  (*(void (__fastcall **)(_QWORD *, __int64, _OWORD *))(*v79 + 120LL))(v79, v78, v91);
  *a2 = v79;
  v79 = 0;
  if ( v73 )
    Mso::Memory::Free(v73, v63);
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 8LL))(v77);
  if ( v82 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 8LL))(v82);
  if ( v78 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 8LL))(v78);
  if ( v79 )
    (*(void (__fastcall **)(_QWORD *))(v79[1] + 8LL))(v79 + 1);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v70);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v71);
  if ( v54 )
  {
    v48 = *(void (**)(void))(*(_QWORD *)v54 + 8LL);
    goto LABEL_60;
  }
  return a2;
}

```

## disassembly

```asm
0x1804888f0  mov     [rsp-8+arg_18], rbx
0x1804888f5  push    rbp
0x1804888f6  push    rsi
0x1804888f7  push    rdi
0x1804888f8  push    r12
0x1804888fa  push    r13
0x1804888fc  push    r14
0x1804888fe  push    r15
0x180488900  lea     rbp, [rsp-170h]
0x180488908  sub     rsp, 270h
0x18048890f  mov     rax, cs:__security_cookie
0x180488916  xor     rax, rsp
0x180488919  mov     [rbp+1A0h+var_40], rax
0x180488920  mov     rbx, r9
0x180488923  mov     r14, r8
0x180488926  mov     r15, rdx
0x180488929  mov     r13, rcx
0x18048892c  mov     [rsp+2A0h+var_258], rdx
0x180488931  xor     edi, edi
0x180488933  mov     rcx, [r8]; this
0x180488936  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18048893b  mov     r12d, [rax+180h]
0x180488942  lea     eax, [rdi+1]
0x180488945  mov     r9d, eax
0x180488948  mov     r8d, eax
0x18048894b  mov     rdx, [r13+0B8h]
0x180488952  lea     rcx, [rbp+1A0h+var_1D0]
0x180488956  call    ?ConvertPath2DToGelPath@Art@@YA?AV?$TCntPtr@$$CBUIPath@GEL@@@Ofc@@AEBVPath2D@1@_K1@Z; Art::ConvertPath2DToGelPath(Art::Path2D const &,unsigned __int64,unsigned __int64)
0x18048895b  nop
0x18048895c  mov     rcx, [r14]; this
0x18048895f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488964  mov     edx, [rbx+1Ch]
0x180488967  sub     edx, [rax+0BCh]
0x18048896d  mov     ecx, [rbx+18h]
0x180488970  sub     ecx, [rax+0B8h]
0x180488976  mov     dword ptr [rsp+2A0h+var_248], ecx
0x18048897a  mov     dword ptr [rsp+2A0h+var_248+4], edx
0x18048897e  mov     rcx, [rsp+2A0h+var_248]
0x180488983  mov     [rsp+2A0h+var_260], rcx
0x180488988  lea     r8, [rsp+2A0h+var_260]
0x18048898d  lea     rdx, [rbp+1A0h+var_210]
0x180488991  mov     rcx, rax
0x180488994  call    ?ConvertViewToHostCoordinates@View@Art@@QEBA?AVPoint64@2@AEBVCPoint@Ofc@@@Z; Art::View::ConvertViewToHostCoordinates(Ofc::CPoint const &)
0x180488999  mov     r8, [r13+0B0h]
0x1804889a0  mov     rdx, r8
0x1804889a3  lea     rcx, [rsp+2A0h+var_240]
0x1804889a8  call    ??0?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAA@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1804889ad  lea     rdx, [r8+8]
0x1804889b1  lea     rcx, [rsp+2A0h+var_260]
0x1804889b6  call    ??0?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAA@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1804889bb  mov     rcx, qword ptr [rbp+1A0h+var_210+8]
0x1804889bf  sub     rcx, [rsp+2A0h+var_260]
0x1804889c4  mov     rbx, qword ptr [rbp+1A0h+var_210]
0x1804889c8  sub     rbx, [rsp+2A0h+var_240]
0x1804889cd  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x1804889d2  mov     [rsp+2A0h+var_260], rax
0x1804889d7  mov     rcx, rbx
0x1804889da  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x1804889df  mov     [rsp+2A0h+var_240], rax
0x1804889e4  lea     r8, [rsp+2A0h+var_260]
0x1804889e9  lea     rdx, [rsp+2A0h+var_240]
0x1804889ee  lea     rcx, [rbp+1A0h+var_1E8]
0x1804889f2  call    ??0Point2D@Art@@QEAA@AEBV?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@1@0@Z; Art::Point2D::Point2D(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &,Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1804889f7  lea     rcx, [rbp+1A0h+var_1E8]; struct Art::Point2D *
0x1804889fb  call    ?FClickedAtBeginning@FreeformDragTracker@Dr@@SA_NAEBVPoint2D@Art@@@Z; Dr::FreeformDragTracker::FClickedAtBeginning(Art::Point2D const &)
0x180488a00  mov     sil, al
0x180488a03  mov     rcx, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180488a0a  mov     [rsp+2A0h+var_230], rcx
0x180488a0f  mov     [rsp+2A0h+var_238], rcx
0x180488a14  mov     rcx, [r14]; this
0x180488a17  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488a1c  mov     edx, [rax+100h]
0x180488a22  test    edx, edx
0x180488a24  jz      short loc_180488A41
0x180488a26  lea     rcx, [rax+0F8h]
0x180488a2d  dec     edx
0x180488a2f  call    ??A?$TArray@VCVarStr@Ofc@@@Ofc@@QEBAAEBVCVarStr@1@K@Z; Ofc::TArray<Ofc::CVarStr>::operator[](ulong)
0x180488a34  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x180488a37  lea     rcx, [rsp+2A0h+var_238]; struct Ofc::CProxyPtrImpl **
0x180488a3c  call    ?StrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x180488a41  mov     rcx, [rsp+2A0h+var_238]; this
0x180488a46  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488a4b  mov     rdx, rax
0x180488a4e  mov     rcx, [rax]
0x180488a51  mov     rax, [rcx+148h]
0x180488a58  mov     rcx, rdx
0x180488a5b  call    cs:__guard_dispatch_icall_fptr
0x180488a61  mov     rcx, [rax]
0x180488a64  cmp     [rcx+10h], rdi
0x180488a68  jz      short loc_180488AE9
0x180488a6a  mov     rcx, [rsp+2A0h+var_238]; this
0x180488a6f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488a74  mov     rdx, rax
0x180488a77  mov     rcx, [rax]
0x180488a7a  mov     rax, [rcx+148h]
0x180488a81  mov     rcx, rdx
0x180488a84  call    cs:__guard_dispatch_icall_fptr
0x180488a8a  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x180488a8d  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x180488a92  mov     [rsp+2A0h+var_240], rax
0x180488a97  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x180488a9a  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180488a9f  mov     [rsp+2A0h+var_260], rax
0x180488aa4  mov     rcx, rax; this
0x180488aa7  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488aac  mov     rdx, rax
0x180488aaf  mov     rcx, [rax]
0x180488ab2  mov     rax, [rcx+0B8h]
0x180488ab9  mov     rcx, rdx
0x180488abc  call    cs:__guard_dispatch_icall_fptr
0x180488ac2  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x180488ac5  lea     rcx, [rsp+2A0h+var_230]; struct Ofc::CProxyPtrImpl **
0x180488aca  call    ?CheckedStrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x180488acf  nop
0x180488ad0  lea     rcx, [rsp+2A0h+var_260]; struct Ofc::CProxyPtrImpl **
0x180488ad5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180488ada  lea     rcx, [rsp+2A0h+var_240]; struct Ofc::CProxyPtrImpl **
0x180488adf  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180488ae4  jmp     loc_180488B87
0x180488ae9  mov     rcx, [r14]; this
0x180488aec  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488af1  mov     rcx, [rax+30h]; struct Ofc::CProxyPtrImpl *
0x180488af5  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x180488afa  mov     [rsp+2A0h+var_228], rax
0x180488aff  cmp     [rax+10h], rdi
0x180488b03  jz      short loc_180488B7D
0x180488b05  mov     rcx, rax; this
0x180488b08  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488b0d  mov     rcx, [rax+58h]; struct Ofc::CProxyPtrImpl *
0x180488b11  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x180488b16  mov     [rsp+2A0h+var_260], rax
0x180488b1b  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x180488b1e  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180488b23  mov     [rsp+2A0h+var_248], rax
0x180488b28  lea     rcx, [rsp+2A0h+var_260]; struct Ofc::CProxyPtrImpl **
0x180488b2d  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180488b32  mov     rcx, [rsp+2A0h+var_248]; this
0x180488b37  cmp     [rcx+10h], rdi
0x180488b3b  jz      short loc_180488B72
0x180488b3d  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488b42  mov     r8, rax
0x180488b45  mov     rcx, [rax]
0x180488b48  mov     rax, [rcx+60h]
0x180488b4c  lea     rdx, [rsp+2A0h+var_240]
0x180488b51  mov     rcx, r8
0x180488b54  call    cs:__guard_dispatch_icall_fptr
0x180488b5a  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x180488b5d  lea     rcx, [rsp+2A0h+var_230]; struct Ofc::CProxyPtrImpl **
0x180488b62  call    ?CheckedStrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x180488b67  lea     rcx, [rsp+2A0h+var_240]; struct Ofc::CProxyPtrImpl **
0x180488b6c  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180488b71  nop
0x180488b72  lea     rcx, [rsp+2A0h+var_248]; struct Ofc::CProxyPtrImpl **
0x180488b77  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180488b7c  nop
0x180488b7d  lea     rcx, [rsp+2A0h+var_228]; struct Ofc::CProxyPtrImpl **
0x180488b82  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180488b87  mov     rcx, [rsp+2A0h+var_230]; this
0x180488b8c  cmp     [rcx+10h], rdi
0x180488b90  jz      loc_1804890A3
0x180488b96  lea     rax, ??_7ThemeInfo@Art@@6B@; const Art::ThemeInfo::`vftable'
0x180488b9d  mov     [rbp+1A0h+var_1A8], rax
0x180488ba1  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180488ba8  mov     [rbp+1A0h+var_1A0], rax
0x180488bac  mov     [rbp+1A0h+var_198], rax
0x180488bb0  mov     [rbp+1A0h+var_190], rax
0x180488bb4  mov     [rbp+1A0h+var_188], rax
0x180488bb8  mov     [rbp+1A0h+var_180], edi
0x180488bbb  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488bc0  mov     r8, rax
0x180488bc3  mov     rcx, [rax]
0x180488bc6  mov     rax, [rcx+0A0h]
0x180488bcd  lea     rdx, [rbp+1A0h+var_1A8]
0x180488bd1  mov     rcx, r8
0x180488bd4  call    cs:__guard_dispatch_icall_fptr
0x180488bda  mov     rcx, [rbp+1A0h+var_1A0]; struct Ofc::CProxyPtrImpl *
0x180488bde  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x180488be3  mov     [rsp+2A0h+var_260], rax
0x180488be8  cmp     [rax+10h], rdi
0x180488bec  jz      loc_180489090
0x180488bf2  mov     rcx, rax; struct Ofc::CProxyPtrImpl *
0x180488bf5  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180488bfa  mov     [rsp+2A0h+var_248], rax
0x180488bff  mov     [rsp+2A0h+var_240], rdi
0x180488c04  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180488c08  call    ??0LinearShadeProps@Art@@QEAA@XZ; Art::LinearShadeProps::LinearShadeProps(void)
0x180488c0d  mov     rcx, [rsp+2A0h+var_248]; this
0x180488c12  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180488c17  mov     rdx, rax
0x180488c1a  mov     rcx, [rax]
0x180488c1d  mov     rax, [rcx+58h]
0x180488c21  mov     rcx, rdx
0x180488c24  call    cs:__guard_dispatch_icall_fptr
0x180488c2a  mov     rbx, rax
0x180488c2d  lea     rdx, [rax+38h]
0x180488c31  lea     rcx, [rsp+2A0h+var_240]
0x180488c36  call    ??4?$TOptional@VShapeStyle@Art@@@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::TOptional<Art::ShapeStyle>::operator=(Ofc::TOptional<Art::ShapeStyle> const &)
0x180488c3b  mov     rdx, rbx
0x180488c3e  lea     rcx, [rbp+1A0h+var_1C0]; this
0x180488c42  call    ??4EffectList@Art@@QEAAAEAV01@AEBV01@@Z; Art::EffectList::operator=(Art::EffectList const &)
0x180488c47  lea     rcx, [rbp+1A0h+var_130]; this
0x180488c4b  call    ??0ShapePropertyBag@Art@@QEAA@XZ; Art::ShapePropertyBag::ShapePropertyBag(void)
0x180488c50  nop
0x180488c51  mov     rbx, [rsp+2A0h+var_240]
0x180488c56  test    rbx, rbx
0x180488c59  jz      short loc_180488C6C
0x180488c5b  lea     r8, [rbp+1A0h+var_1C0]
0x180488c5f  mov     rdx, rbx
0x180488c62  lea     rcx, [rsp+2A0h+var_248]
0x180488c67  call    ?ResolvePropLists@StyleResolverHelper@Art@@SAXAEBV?$TReferringPtr@$$CBVITheme@Art@@@Ofc@@AEBVShapeStyle@2@AEAV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@2@@Z; Art::StyleResolverHelper::ResolvePropLists(Ofc::TReferringPtr<Art::ITheme const> const &,Art::ShapeStyle const &,Art::ShapePropsMethods<Art::ShapePropsData_<0>> &)
0x180488c6c  lea     rdx, [rbp+1A0h+var_1C0]
0x180488c70  lea     rcx, [rbp+1A0h+var_1A8]
0x180488c74  call    ?ResolveColorsForPropLists@StyleResolverHelper@Art@@SAXAEBVThemeInfo@2@AEAV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@2@@Z; Art::StyleResolverHelper::ResolveColorsForPropLists(Art::ThemeInfo const &,Art::ShapePropsMethods<Art::ShapePropsData_<0>> &)
0x180488c79  xor     eax, eax
0x180488c7b  mov     qword ptr [rbp+1A0h+var_210], rax
0x180488c7f  mov     qword ptr [rbp+1A0h+var_210+8], rdi
0x180488c83  lea     rdx, [rbp+1A0h+var_210]; struct Art::Geometry2D *
0x180488c87  lea     rcx, [rbp+1A0h+var_1E8]; this
0x180488c8b  call    ??0GeometryBuilder@Art@@QEAA@AEAVGeometry2D@1@@Z; Art::GeometryBuilder::GeometryBuilder(Art::Geometry2D &)
0x180488c90  nop
0x180488c91  lea     rcx, [rbp+1A0h+var_1E8]; this
0x180488c95  call    ?GetPaths@GeometryBuilder@Art@@QEAAAEAVPath2DTable@2@XZ; Art::GeometryBuilder::GetPaths(void)
0x180488c9a  mov     rdi, rax
0x180488c9d  lea     rcx, [rax+8]; this
0x180488ca1  lea     rdx, ?Do@?$TDestructRange@VPath2D@Art@@$0A@@Ofc@@SAXPEAEK@Z; void (*)(unsigned __int8 *, unsigned int)
0x180488ca8  call    ?Reset@CArrayImpl@Ofc@@IEAAXP6AXPEAEK@Z@Z; Ofc::CArrayImpl::Reset(void (*)(uchar *,ulong))
0x180488cad  mov     dword ptr [rdi], 0
0x180488cb3  lea     rcx, [rbp+1A0h+var_1E8]; this
0x180488cb7  call    ?GetPaths@GeometryBuilder@Art@@QEAAAEAVPath2DTable@2@XZ; Art::GeometryBuilder::GetPaths(void)
0x180488cbc  mov     rdx, [r13+0B8h]; struct Art::Path2D *
0x180488cc3  mov     rcx, rax; this
0x180488cc6  call    ?AddPath2D@Path2DTable@Art@@QEAAXAEBVPath2D@2@@Z; Art::Path2DTable::AddPath2D(Art::Path2D const &)
0x180488ccb  lea     rcx, [rbp+1A0h+var_1E8]; this
0x180488ccf  call    ?Validate@GeometryBuilder@Art@@QEBAXXZ; Art::GeometryBuilder::Validate(void)
0x180488cd4  nop
0x180488cd5  lea     rcx, [rbp+1A0h+var_1E8]; this
0x180488cd9  call    ??1GeometryBuilder@Art@@QEAA@XZ; Art::GeometryBuilder::~GeometryBuilder(void)
0x180488cde  lea     rdx, [rbp+1A0h+var_210]
0x180488ce2  lea     rcx, [rbp+1A0h+var_1C0]
0x180488ce6  call    ??$Set@UGeometry@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEAAXAEBVGeometry2D@Art@@@Z; Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Geometry>(Art::Geometry2D const &)
0x180488ceb  xorps   xmm0, xmm0
0x180488cee  movdqu  [rbp+1A0h+var_A0], xmm0
0x180488cf6  xorps   xmm1, xmm1
0x180488cf9  movdqu  [rbp+1A0h+var_90], xmm1
0x180488d01  xor     edi, edi
0x180488d03  mov     [rbp+1A0h+var_80], edi
0x180488d09  mov     [rbp+1A0h+var_7C], di
0x180488d10  xor     eax, eax
0x180488d12  mov     [rbp+1A0h+var_78], rax
0x180488d19  mov     [rbp+1A0h+var_70], rax
0x180488d20  mov     r8, [r13+0B0h]
0x180488d27  lea     rdx, [r8+8]
0x180488d2b  lea     rcx, [rsp+2A0h+var_228]
0x180488d30  call    ??0?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAA@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x180488d35  mov     rdx, r8
0x180488d38  lea     rcx, [rsp+2A0h+var_258]
0x180488d3d  call    ??0?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAA@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x180488d42  lea     r8, [rsp+2A0h+var_228]
0x180488d47  lea     rdx, [rsp+2A0h+var_258]
0x180488d4c  lea     rcx, [rbp+1A0h+var_A0]
0x180488d53  call    ?SetXY@Point2D@Art@@QEAAXV?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@2@0@Z; Art::Point2D::SetXY(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>,Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>)
0x180488d58  lea     rdx, [rbp+1A0h+var_A0]
0x180488d5f  lea     rcx, [rbp+1A0h+var_1C0]
0x180488d63  call    ??$Set@UTransform@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEAAXAEBVTransform2D@Art@@@Z; Ofc::TPropertySet<Art::ShapePropsIDs>::Set<Art::SpPr::Transform>(Art::Transform2D const &)
0x180488d68  mov     [rsp+2A0h+var_250], di
0x180488d6d  lea     r8, [rsp+2A0h+var_250]
0x180488d72  lea     rdx, [rbp+1A0h+var_130]
0x180488d76  lea     rcx, [rbp+1A0h+var_1C0]
0x180488d7a  call    ?PropListToObj@Art@@YAXAEBV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@1@AEAVShapePropertyBag@1@AEAUPropListConversionOptions@1@@Z; Art::PropListToObj(Art::ShapePropsMethods<Art::ShapePropsData_<0>> const &,Art::ShapePropertyBag &,Art::PropListConversionOptions &)
0x180488d7f  mov     [rbp+1A0h+var_168], rdi
0x180488d83  cmp     [rbp+1A0h+var_A3], dil
0x180488d8a  jz      loc_180489053
0x180488d90  cmp     [rbp+1A0h+var_A2], dil
0x180488d97  jz      short loc_180488DB0
0x180488d99  mov     [rbp+1A0h+var_A2], 1
0x180488da0  lea     rcx, [rbp+1A0h+var_D8]
0x180488da7  call    ??$Is@UNone@Line@Art@@@?$TChoice@VLineStyleDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::Is<Art::Line::None>(void)
0x180488dac  test    al, al
0x180488dae  jz      short loc_180488DCD
0x180488db0  test    sil, sil
0x180488db3  jz      loc_180489053
0x180488db9  lea     rcx, [rbp+1A0h+var_E8]
0x180488dc0  call    ??$Is@UNone@Fill@Art@@@?$TChoice@VFillStyleDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::Is<Art::Fill::None>(void)
0x180488dc5  test    al, al
0x180488dc7  jnz     loc_180489053
0x180488dcd  test    sil, sil
0x180488dd0  jnz     short loc_180488DDE
0x180488dd2  lea     rcx, [rbp+1A0h+var_E8]
0x180488dd9  call    ??$SwitchTo@UNone@Fill@Art@@@?$TChoice@VFillStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVNoFill@Art@@XZ; Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::None>(void)
0x180488dde  mov     rcx, [rbp+1A0h+var_C8]
0x180488de5  test    rcx, rcx
0x180488de8  jz      short loc_180488DEF
0x180488dea  call    ??_G?$ProjectionType_@$0A@@Model3DStorageUpdateParamsData@Art@@QEAAPEAXI@Z; Art::Model3DStorageUpdateParamsData::ProjectionType_<0>::`scalar deleting destructor'(uint)
0x180488def  mov     [rbp+1A0h+var_C8], rdi
0x180488df6  mov     dword ptr [rbp+1A0h+var_A0], r12d
0x180488dfd  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180488e04  mov     qword ptr [rbp+1A0h+var_A0+8], rax
0x180488e0b  mov     qword ptr [rbp+1A0h+var_90], rdi
0x180488e12  mov     qword ptr [rbp+1A0h+var_90+8], 10000h
0x180488e1d  mov     esi, 1
  ... truncated ...
```
