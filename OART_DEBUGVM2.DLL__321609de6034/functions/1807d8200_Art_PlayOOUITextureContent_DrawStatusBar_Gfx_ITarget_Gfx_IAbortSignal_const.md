# Art::PlayOOUITextureContent::DrawStatusBar(Gfx::ITarget &,Gfx::IAbortSignal const *)

- ea: `0x1807d8200`
- end: `0x1807d8d68`
- name: `?DrawStatusBar@PlayOOUITextureContent@Art@@AEAA_NAEAUITarget@Gfx@@PEBUIAbortSignal@4@@Z`
- size: `2920`
- prototype: `bool __fastcall(Art::PlayOOUITextureContent *__hidden this, struct Gfx::ITarget *, const struct Gfx::IAbortSignal *)`
- caller_count: `1`
- callee_count: `52`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1805197e0`

## callees

- `0x18000eb20`
- `0x180012630`
- `0x180028b00`
- `0x18002a690`
- `0x18002a750`
- `0x180049470`
- `0x180055990`
- `0x1800559f0`
- `0x180072130`
- `0x180077440`
- `0x18007d870`
- `0x18007f780`
- `0x180083e60`
- `0x1800a5c60`
- `0x1800b48a0`
- `0x1800b968c`
- `0x1800b9770`
- `0x1800d4030`
- `0x1800dbc90`
- `0x1800e1e60`
- `0x1800e3230`
- `0x1800e8040`
- `0x1800ec1e0`
- `0x1800ef520`
- `0x18015332c`
- `0x1801b66f8`
- `0x180210de4`
- `0x180219294`
- `0x180221d98`
- `0x180276a40`
- `0x1802770a0`
- `0x180279030`
- `0x180279050`
- `0x1802f9e28`
- `0x180301368`
- `0x180345ab4`
- `0x180345eec`
- `0x180411654`
- `0x180526580`
- `0x18053ec70`
- `0x18062e398`
- `0x18066ea48`
- `0x1806b2890`
- `0x1806b9768`
- `0x1806b9794`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806cf9e8`
- `0x1806d1070`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x1807d8386`
- `KERNEL32!DecodePointer` at `0x1807d8398`
- `KERNEL32!DecodePointer` at `0x1807d8386`
- `KERNEL32!DecodePointer` at `0x1807d8398`
- `KERNEL32!EncodePointer` at `0x1807d8679`
- `KERNEL32!EncodePointer` at `0x1807d895d`
- `KERNEL32!EncodePointer` at `0x1807d8679`
- `KERNEL32!EncodePointer` at `0x1807d895d`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d8583`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d85b0`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d85cd`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d85f8`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d8583`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d85b0`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d85cd`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807d85f8`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1807d8454`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1807d8454`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1807d851c`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1807d851c`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1807d8418`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1807d8418`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1807d8276`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1807d8276`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1807d82dd`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1807d82dd`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1807d849b`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1807d849b`

## pseudocode

```c
char __fastcall Art::PlayOOUITextureContent::DrawStatusBar(
        Art::PlayOOUITextureContent *this,
        struct Gfx::ITarget *a2,
        const struct Gfx::IAbortSignal *a3)
{
  float *v5; // rdi
  unsigned int OptimalRenderingPolicyForTarget; // eax
  double v7; // xmm8_8
  double v8; // xmm7_8
  double v9; // xmm6_8
  __int64 *v10; // rax
  __int64 v11; // rdi
  Art *v12; // rcx
  void (*v13)(void); // rdx
  bool v14; // r8
  void *v15; // rcx
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  __int64 (__fastcall *v18)(__int64); // rax
  _QWORD *v19; // rax
  __int64 *v20; // rax
  __int64 v21; // r14
  struct GEL::ITopLevelEffect *v22; // rbx
  _QWORD *v23; // rax
  Art *v24; // rcx
  struct Art::IAppHost *AppHost; // rax
  unsigned int v26; // eax
  double v27; // xmm9_8
  char v28; // r12
  double v29; // xmm7_8
  char v30; // bl
  char v31; // di
  __int64 DefaultTypefaces; // rax
  __int64 v33; // r9
  __int64 *v34; // rax
  __int64 v35; // r13
  __int64 v36; // rdi
  double v37; // xmm1_8
  __int64 v38; // rbx
  __int64 v39; // r15
  unsigned __int64 v40; // rdx
  unsigned int v41; // r8d
  Art::TextBody *v42; // rax
  __int64 v43; // r15
  int *v44; // rdi
  int *v45; // rbx
  Art::TextBody *Checked; // rax
  const wchar_t **v47; // rax
  __int64 v48; // rax
  Art *v49; // rcx
  __int64 v50; // rax
  Art::TextBody *v51; // rbx
  Art::TextBody *v52; // rax
  int v53; // eax
  Art::TextBody *v54; // rbx
  Art::TextBody *v55; // rax
  int v56; // eax
  unsigned __int64 v57; // rdx
  unsigned int v58; // r8d
  Art::SimpleTextFrame *v59; // rax
  __int64 v60; // rbx
  Art::SimpleTextFrame *v61; // rax
  struct Ofc::CProxyPtrImpl *v62; // rdx
  Art::SimpleTextFrame *v63; // rax
  struct Art::PosSize2D *v64; // r9
  Art::SimpleTextFrame *v65; // rax
  int v66; // edi
  struct Ofc::CProxyPtrImpl *v67; // rcx
  struct GEL::ITopLevelEffect *v68; // rbx
  _QWORD *TextBuilderEffects; // rax
  unsigned int v70; // edx
  __int64 v71; // rbx
  const struct Art::TextViewLine *TextViewLine; // rax
  bool v73; // cc
  char v74; // al
  int v76; // [rsp+30h] [rbp-D8h]
  __int64 v77; // [rsp+68h] [rbp-A0h] BYREF
  struct Ofc::CProxyPtrImpl *v78; // [rsp+70h] [rbp-98h] BYREF
  double v79; // [rsp+78h] [rbp-90h] BYREF
  __int128 v80; // [rsp+80h] [rbp-88h] BYREF
  __int64 v81; // [rsp+90h] [rbp-78h]
  Ofc::CProxyPtrImpl *v82; // [rsp+98h] [rbp-70h] BYREF
  __int64 v83[2]; // [rsp+A0h] [rbp-68h] BYREF
  char v84; // [rsp+B0h] [rbp-58h]
  struct GEL::ITopLevelEffect *v85; // [rsp+B8h] [rbp-50h] BYREF
  Ofc::CProxyPtrImpl *v86; // [rsp+C0h] [rbp-48h] BYREF
  wchar_t *v87; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v88; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v89[2]; // [rsp+E0h] [rbp-28h] BYREF
  __m128i v90; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v91; // [rsp+100h] [rbp-8h] BYREF
  __int64 v92; // [rsp+110h] [rbp+8h]
  __int128 v93; // [rsp+118h] [rbp+10h] BYREF
  __int64 v94; // [rsp+128h] [rbp+20h]
  __int64 v95; // [rsp+130h] [rbp+28h]
  __int64 v96; // [rsp+138h] [rbp+30h]
  const struct Gfx::IAbortSignal *v97; // [rsp+140h] [rbp+38h]
  __int64 v98; // [rsp+148h] [rbp+40h]
  __int64 v99; // [rsp+150h] [rbp+48h] BYREF
  __int128 v100; // [rsp+158h] [rbp+50h]
  double v101; // [rsp+168h] [rbp+60h]
  __int128 v102; // [rsp+170h] [rbp+68h]
  void *v103[2]; // [rsp+180h] [rbp+78h] BYREF
  __m128i v104; // [rsp+190h] [rbp+88h]
  __int128 v105; // [rsp+1A0h] [rbp+98h]
  __int128 v106; // [rsp+1B0h] [rbp+A8h]
  __int64 v107; // [rsp+1C0h] [rbp+B8h]
  __int64 v108; // [rsp+1C8h] [rbp+C0h]
  __int16 v109; // [rsp+1D0h] [rbp+C8h]
  __int64 v110; // [rsp+1D4h] [rbp+CCh]
  char v111; // [rsp+1DCh] [rbp+D4h]
  __int128 v112; // [rsp+1E0h] [rbp+D8h] BYREF
  __int128 v113; // [rsp+1F0h] [rbp+E8h] BYREF
  int v114; // [rsp+200h] [rbp+F8h]
  __int16 v115; // [rsp+204h] [rbp+FCh]
  __int64 v116; // [rsp+208h] [rbp+100h]
  __int64 v117; // [rsp+210h] [rbp+108h]
  __m128i si128; // [rsp+218h] [rbp+110h] BYREF
  _QWORD v119[5]; // [rsp+228h] [rbp+120h] BYREF
  __int64 v120; // [rsp+250h] [rbp+148h] BYREF
  __int128 v121; // [rsp+260h] [rbp+158h] BYREF
  double v122; // [rsp+270h] [rbp+168h]
  double v123; // [rsp+278h] [rbp+170h]
  _BYTE v124[432]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v125[1088]; // [rsp+438h] [rbp+330h] BYREF

  v97 = a3;
  *(_QWORD *)&v88 = a2;
  v5 = (float *)(*(__int64 (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)a2 + 24LL))(a2);
  v90.m128i_i64[0] = (__int64)v5;
  OptimalRenderingPolicyForTarget = Gfx::GetOptimalRenderingPolicyForTarget(a2);
  GEL::ITopLevelEffect::Create(&v85, OptimalRenderingPolicyForTarget);
  v7 = 914400.0 / *v5;
  v8 = (double)(*((_DWORD *)this + 10) - *((_DWORD *)this + 8)) * v7;
  v9 = (double)(*((_DWORD *)this + 11) - *((_DWORD *)this + 9)) * v7;
  v121 = 0;
  v122 = v8;
  v123 = v9;
  v10 = (__int64 *)GEL::IRectanglePath::Create(&v78, &v121);
  v98 = *v10;
  v11 = v98;
  *v10 = 0;
  v119[4] = v11;
  v12 = v78;
  if ( v78 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v78 + 8LL))(v78);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( Art::FInHighContrastMode(v12) )
  {
    Art::Color::Color(&v99, 1);
    v15 = Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
    {
      while ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
      {
        if ( _InterlockedCompareExchange64(
               (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
               1,
               0) )
        {
          v79 = 0.0;
          std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v79);
        }
        else
        {
          LOBYTE(v13) = 1;
          Ofc::AtExit(Ofc::TSingleton<Art::GelTranslator>::Shutdown, v13, v14);
          if ( DecodePointer(Ptr) )
          {
            v18 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
            v19 = (_QWORD *)v18(8);
          }
          else
          {
            v19 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v16, v17);
          }
          *v19 = &Art::GelTranslator::`vftable';
          _InterlockedCompareExchange64(
            (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
            (signed __int64)v19,
            1);
        }
      }
      v15 = Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    }
    si128 = *(__m128i *)(*(__int64 (__fastcall **)(void *, __int64 *, __int64 *))(*(_QWORD *)v15 + 112LL))(
                          v15,
                          &v120,
                          &v99);
    Art::Color::~Color((Art::Color *)&v99);
  }
  v20 = (__int64 *)GEL::IBrushSolid::Create(&v79, &si128, 0);
  v21 = *v20;
  *v20 = 0;
  v120 = v21;
  if ( v79 != 0.0 )
    (*(void (__fastcall **)(double))(**(_QWORD **)&v79 + 8LL))(COERCE_DOUBLE(*(_QWORD *)&v79));
  v22 = v85;
  v23 = (_QWORD *)GEL::IEffectFilledPath::Create(&v78, v11, v21, 0);
  GEL::ITopLevelEffect::Add<Math::Identity,0>(v22, *v23);
  v24 = v78;
  if ( v78 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v78 + 8LL))(v78);
  AppHost = Art::GetAppHost(v24);
  v26 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)AppHost + 312LL))(AppHost);
  v27 = 0.0;
  if ( (unsigned int)MsoFLidBiDi(v26) )
  {
    v28 = 1;
    LOBYTE(v77) = 1;
    v29 = v8 - v9;
    v30 = 1;
    v31 = 1;
  }
  else
  {
    v28 = 0;
    LOBYTE(v77) = 0;
    v29 = 0.0;
    v30 = 0;
    v31 = 0;
  }
  Art::PlayOOUITextureContent::DrawStatusBarIcon(this, v85, v9 * 0.5, v29);
  v106 = 0;
  v107 = 1094713344;
  v108 = 0;
  v109 = 1;
  v110 = 0;
  v111 = 0;
  DefaultTypefaces = GEL::ITypefaceList::GetDefaultTypefaces();
  LOBYTE(v33) = 1;
  v34 = (__int64 *)(*(__int64 (__fastcall **)(__int64, double *, const wchar_t *, __int64, _BYTE, _QWORD))(*(_QWORD *)DefaultTypefaces + 16LL))(
                     DefaultTypefaces,
                     &v79,
                     L"Segoe UI",
                     v33,
                     0,
                     0);
  v35 = *v34;
  *v34 = 0;
  *(_QWORD *)&v106 = v35;
  if ( v79 != 0.0 )
  {
    (*(void (__fastcall **)(double))(**(_QWORD **)&v79 + 8LL))(COERCE_DOUBLE(*(_QWORD *)&v79));
    v30 = v31;
  }
  v36 = (unsigned int)(int)round((double)*((int *)this + 11) * v7);
  v95 = v36;
  if ( v30 )
    v37 = v9;
  else
    v37 = 0.0;
  v38 = (unsigned int)(int)round((double)*((int *)this + 10) * v7 - v37);
  v89[0] = v38;
  v39 = (unsigned int)(int)round((double)*((int *)this + 9) * v7);
  v96 = v39;
  if ( !v28 )
    v27 = v9;
  v119[0] = (unsigned int)(int)round((double)*((int *)this + 8) * v7 + v27);
  v119[1] = v39;
  v119[2] = v38;
  v119[3] = v36;
  (*(void (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)this + 3) + 192LL))(*((_QWORD *)this + 3), &v87);
  v42 = (Art::TextBody *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v40, v41);
  v83[0] = (__int64)v42;
  if ( v42 )
    v43 = Art::TextBody::TextBody(v42);
  else
    v43 = 0;
  v44 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  if ( v43 )
  {
    v45 = *(int **)(v43 + 32);
    _InterlockedExchange(v45, 1);
    *((_QWORD *)v45 + 1) = EncodePointer(Ofc::TDestructFromProxy<Dr::ScrapOwningCutCopyHandler const>);
    *((_QWORD *)v45 + 2) = v43;
  }
  else
  {
    v45 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  }
  v82 = (Ofc::CProxyPtrImpl *)v45;
  Ofc::CTransaction::CTransaction((Ofc::CTransaction *)v125);
  Checked = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v82);
  v78 = 0;
  Art::TextBody::PutChars(Checked, (struct Ofc::CTransaction *)v125, (const struct Art::TextRange *)&v78, v87, 0, 0);
  v47 = (const wchar_t **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 24LL))(v35);
  Art::TextFont::TextFont((Art::TextFont *)v103, *v47);
  v91 = 0;
  v92 = 0;
  v79 = DOUBLE_12_0;
  v48 = Art::TextFontSize::TextFontSize((Art::TextFontSize *)&v78, (const struct Art::Points *)&v79);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::FontSize>(&v91, v48);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::LatinFont>((Ofc::Tph::CPropertySetImpl *)&v91);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::EastAsianFont>((Ofc::Tph::CPropertySetImpl *)&v91);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::ComplexScriptFont>((Ofc::Tph::CPropertySetImpl *)&v91);
  v79 = DOUBLE_0_1882352941176471;
  v78 = *(struct Ofc::CProxyPtrImpl **)&DOUBLE_0_1921568627450981;
  *(double *)v83 = DOUBLE_0_196078431372549;
  Art::Color::Color(
    (Art::Color *)&v99,
    (const struct Art::Factor *)v83,
    (const struct Art::Factor *)&v78,
    (const struct Art::Factor *)&v79);
  if ( Art::FInHighContrastMode(v49) )
  {
    v50 = Art::Color::Color(v83, 18);
    Art::Color::operator=(&v99, v50);
    Art::Color::~Color((Art::Color *)v83);
  }
  Art::TextCharPropertyBag::SetSolidColor((Art::TextCharPropertyBag *)&v91, 0, 0, (const struct Art::Color *)&v99);
  v51 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v82);
  v52 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v82);
  v53 = Art::TextBody::Length(v52);
  LODWORD(v78) = 0;
  HIDWORD(v78) = v53;
  Art::TextBody::SetCharPropertyBag(
    v51,
    (struct Ofc::CTransaction *)v125,
    (const struct Art::TextRange *)&v78,
    (const struct Art::TextCharPropertyBag *)&v91,
    0);
  v80 = 0;
  v81 = 0;
  Ofc::TPropertySet<Art::TextParaPropertyBagIDs>::Set<Art::Text::TextRtl>(&v80, &v77);
  v83[1] = (__int64)Art::TextEffectRecorder::Visit;
  v84 = 1;
  v83[0] = v28 != 0 ? 2 : 0;
  Ofc::TPropertySet<Art::TextParaPropertyBagIDs>::SetImpl(&v80, 14, v83);
  Ofc::Tph::StgTypeOwner::Reset((Ofc::Tph::StgTypeOwner *)v83);
  v83[1] = (__int64)Art::TextEffectRecorder::Visit;
  v84 = 1;
  v83[0] = 2;
  Ofc::TPropertySet<Art::TextParaPropertyBagIDs>::SetImpl(&v80, 18, v83);
  Ofc::Tph::StgTypeOwner::Reset((Ofc::Tph::StgTypeOwner *)v83);
  v54 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v82);
  v55 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v82);
  v56 = Art::TextBody::Length(v55);
  LODWORD(v78) = 0;
  HIDWORD(v78) = v56;
  Art::TextBody::SetParaPropertyBag(
    v54,
    (struct Ofc::CTransaction *)v125,
    (const struct Art::TextRange *)&v78,
    (const struct Art::TextParaPropertyBag *)&v80,
    0);
  Ofc::CTransaction::Commit((Ofc::CTransaction *)v125);
  Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)&v80);
  Art::Color::~Color((Art::Color *)&v99);
  Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)&v91);
  operator delete(v103[1]);
  Ofc::CRollbackTransaction::~CRollbackTransaction((Ofc::CRollbackTransaction *)v125);
  v59 = (Art::SimpleTextFrame *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0xC8, v57, v58);
  if ( v59 )
    v60 = Art::SimpleTextFrame::SimpleTextFrame(v59);
  else
    v60 = 0;
  if ( v60 )
  {
    v44 = *(int **)(v60 + 32);
    _InterlockedExchange(v44, 1);
    *((_QWORD *)v44 + 1) = EncodePointer(Ofc::TDestructFromProxy<Art::TextDragTracker>);
    *((_QWORD *)v44 + 2) = v60;
  }
  v86 = (Ofc::CProxyPtrImpl *)v44;
  v61 = (Art::SimpleTextFrame *)Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v44);
  v62 = v82;
  if ( *((_DWORD *)v82 + 1) != 0x80000000 )
    _InterlockedAdd((volatile signed __int32 *)v82 + 1, 1u);
  v78 = v62;
  Art::SimpleTextFrame::SetTextBody(v61);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v78);
  v93 = 0;
  v94 = 0;
  *((_QWORD *)&v80 + 1) = Art::TextEffectRecorder::Visit;
  LOBYTE(v81) = 1;
  *(_QWORD *)&v80 = 1;
  Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::SetImpl(&v93, 10, &v80);
  Ofc::Tph::StgTypeOwner::Reset((Ofc::Tph::StgTypeOwner *)&v80);
  *((_QWORD *)&v80 + 1) = Art::TextEffectRecorder::Visit;
  LOBYTE(v81) = 1;
  *(_QWORD *)&v80 = 1;
  Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::SetImpl(&v93, 7, &v80);
  Ofc::Tph::StgTypeOwner::Reset((Ofc::Tph::StgTypeOwner *)&v80);
  *((_QWORD *)&v80 + 1) = Art::TextEffectRecorder::Visit;
  LOBYTE(v81) = 1;
  *(_QWORD *)&v80 = 0;
  Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::SetImpl(&v93, 19, &v80);
  Ofc::Tph::StgTypeOwner::Reset((Ofc::Tph::StgTypeOwner *)&v80);
  v63 = (Art::SimpleTextFrame *)Ofc::CProxyPtrImpl::GetChecked(v86);
  Art::SimpleTextFrame::SetTextFramePropertyBag(v63, (const struct Art::TextBodyPropertyBag *)&v93);
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  Art::SetBoundsToOffsetExtents((Art *)v119, (const struct Art::Rect64 *)&v112, (struct Art::Point2D *)&v113, v64);
  v65 = (Art::SimpleTextFrame *)Ofc::CProxyPtrImpl::GetChecked(v86);
  Art::SimpleTextFrame::SetTransform(v65, (const struct Art::Transform2D *)&v112);
  *(_OWORD *)v83 = 0;
  v66 = v88;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v88 + 24LL))(v88);
  Gfx::ToRectPxI(&v88, v83);
  *(__m128i *)v103 = _mm_load_si128((const __m128i *)&_xmm);
  v104 = _mm_load_si128((const __m128i *)&_xmm);
  v105 = v88;
  v99 = *(_QWORD *)&v7;
  v100 = 0;
  v101 = v7;
  v102 = 0;
  Art::PosSize2D::PosSize2D((Art::PosSize2D *)v89, v89[0] - v119[0], v95 - v96);
  v67 = v86;
  if ( *((_DWORD *)v86 + 1) != 0x80000000 )
    _InterlockedAdd((volatile signed __int32 *)v86 + 1, 1u);
  v78 = v67;
  Art::TextBuilder::TextBuilder((Art::TextBuilder *)v124, (__int64)v89, (__int64)&v99, (__int64)v83, 0, 0, 0, 1);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v78);
  v68 = v85;
  TextBuilderEffects = (_QWORD *)Art::GetTextBuilderEffects(&v90, v124);
  GEL::ITopLevelEffect::Add<Math::Identity,0>(v68, *TextBuilderEffects);
  if ( v90.m128i_i64[0] )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90.m128i_i64[0] + 8LL))(v90.m128i_i64[0]);
  v71 = *(_QWORD *)(*((_QWORD *)this + 3) + 16LL);
  if ( v71 )
  {
    TextViewLine = Art::TextBuilder::GetTextViewLine((Art::TextBuilder *)v124, v70);
    if ( !TextViewLine
      || (v73 = *((int *)TextViewLine + 13) <= (unsigned __int64)(unsigned int)(*((_DWORD *)v87 - 1) / 2), v74 = 1, !v73) )
    {
      v74 = 0;
    }
    *(_BYTE *)(v71 + 80) = v74;
  }
  v90 = _mm_load_si128((const __m128i *)&_xmm);
  *(_OWORD *)v89 = 0;
  GEL::ITopLevelEffect::Draw((_DWORD)v85, v66, (unsigned int)v103, (_DWORD)v97, 0, v76, (__int64)v89, (__int64)&v90);
  Art::TextBuilder::~TextBuilder((Art::TextBuilder *)v124);
  Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)&v93);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v82);
  Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)&v87);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
  if ( v98 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 8LL))(v98);
  if ( v85 )
    (*(void (__fastcall **)(char *))(*((_QWORD *)v85 + 1) + 8LL))((char *)v85 + 8);
  return 1;
}

```

## disassembly

```asm
0x1807d8200  mov     rax, rsp
0x1807d8203  mov     [rax+20h], rbx
0x1807d8207  push    rbp
0x1807d8208  push    rsi
0x1807d8209  push    rdi
0x1807d820a  push    r12
0x1807d820c  push    r13
0x1807d820e  push    r14
0x1807d8210  push    r15
0x1807d8212  lea     rbp, [rax-7F8h]
0x1807d8219  sub     rsp, 8C0h
0x1807d8220  movaps  xmmword ptr [rax-48h], xmm6
0x1807d8224  movaps  xmmword ptr [rax-58h], xmm7
0x1807d8228  movaps  xmmword ptr [rax-68h], xmm8
0x1807d822d  movaps  xmmword ptr [rax-78h], xmm9
0x1807d8232  mov     rax, cs:__security_cookie
0x1807d8239  xor     rax, rsp
0x1807d823c  mov     [rbp+7F0h+var_80], rax
0x1807d8243  mov     [rbp+7F0h+var_7B8], r8
0x1807d8247  mov     rbx, rdx
0x1807d824a  mov     qword ptr [rbp+7F0h+var_828], rdx
0x1807d824e  mov     rsi, rcx
0x1807d8251  mov     rax, [rdx]
0x1807d8254  mov     rcx, rdx
0x1807d8257  mov     rax, [rax+18h]
0x1807d825b  call    cs:__guard_dispatch_icall_fptr
0x1807d8261  mov     rdi, rax
0x1807d8264  mov     qword ptr [rbp+7F0h+var_808], rax
0x1807d8268  mov     rcx, rbx
0x1807d826b  call    ?GetOptimalRenderingPolicyForTarget@Gfx@@YA?AW4RenderingPolicy@1@AEBUITarget@1@@Z; Gfx::GetOptimalRenderingPolicyForTarget(Gfx::ITarget const &)
0x1807d8270  mov     edx, eax
0x1807d8272  lea     rcx, [rbp+7F0h+var_840]
0x1807d8276  call    cs:__imp_?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z; GEL::ITopLevelEffect::Create(Gfx::RenderingPolicy)
0x1807d827c  movss   xmm0, dword ptr [rdi]
0x1807d8280  cvtps2pd xmm0, xmm0
0x1807d8283  movsd   xmm8, cs:__real@412be7c000000000
0x1807d828c  divsd   xmm8, xmm0
0x1807d8291  mov     eax, [rsi+28h]
0x1807d8294  sub     eax, [rsi+20h]
0x1807d8297  movd    xmm7, eax
0x1807d829b  cvtdq2pd xmm7, xmm7
0x1807d829f  mulsd   xmm7, xmm8
0x1807d82a4  mov     eax, [rsi+2Ch]
0x1807d82a7  sub     eax, [rsi+24h]
0x1807d82aa  movd    xmm6, eax
0x1807d82ae  cvtdq2pd xmm6, xmm6
0x1807d82b2  mulsd   xmm6, xmm8
0x1807d82b7  xorps   xmm0, xmm0
0x1807d82ba  movups  [rbp+7F0h+var_698], xmm0
0x1807d82c1  movsd   [rbp+7F0h+var_688], xmm7
0x1807d82c9  movsd   [rbp+7F0h+var_680], xmm6
0x1807d82d1  lea     rdx, [rbp+7F0h+var_698]
0x1807d82d8  lea     rcx, [rsp+8F0h+var_888]
0x1807d82dd  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x1807d82e3  mov     rdi, [rax]
0x1807d82e6  mov     [rbp+7F0h+var_7B0], rdi
0x1807d82ea  xor     r15d, r15d
0x1807d82ed  mov     [rax], r15
0x1807d82f0  mov     [rbp+7F0h+var_6B0], rdi
0x1807d82f7  mov     rcx, [rsp+8F0h+var_888]
0x1807d82fc  test    rcx, rcx
0x1807d82ff  jz      short loc_1807D830E
0x1807d8301  mov     rax, [rcx]
0x1807d8304  mov     rax, [rax+8]
0x1807d8308  call    cs:__guard_dispatch_icall_fptr
0x1807d830e  movdqa  xmm0, cs:__xmm@3f8000003f69e9ea3f67e7e83f7dfdfe
0x1807d8316  movups  [rbp+7F0h+var_6E0], xmm0
0x1807d831d  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1807d8322  mov     r13d, 1
0x1807d8328  test    al, al
0x1807d832a  jz      loc_1807D8409
0x1807d8330  mov     edx, r13d
0x1807d8333  lea     rcx, [rbp+7F0h+var_7A8]
0x1807d8337  call    ??0Color@Art@@QEAA@W4SystemColorVal@1@@Z; Art::Color::Color(Art::SystemColorVal)
0x1807d833c  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1807d8343  cmp     rcx, r13
0x1807d8346  ja      loc_1807D83DD
0x1807d834c  lea     ebx, [r13+7]
0x1807d8350  lea     r14, ??_7GelTranslator@Art@@6B@; const Art::GelTranslator::`vftable'
0x1807d8357  mov     rax, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1807d835e  cmp     rax, r13
0x1807d8361  ja      short loc_1807D83D6
0x1807d8363  xor     eax, eax
0x1807d8365  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, r13; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1807d836e  jnz     short loc_1807D83C5
0x1807d8370  mov     dl, r13b; void (*)(void)
0x1807d8373  lea     rcx, ?Shutdown@?$TSingleton@VGelTranslator@Art@@@Ofc@@SAXXZ; Ptr
0x1807d837a  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x1807d837f  mov     rcx, cs:Ptr; Ptr
0x1807d8386  call    cs:__imp_DecodePointer
0x1807d838c  test    rax, rax
0x1807d838f  jz      short loc_1807D83A9
0x1807d8391  mov     rcx, cs:Ptr; Ptr
0x1807d8398  call    cs:__imp_DecodePointer
0x1807d839e  mov     rcx, rbx
0x1807d83a1  call    cs:__guard_dispatch_icall_fptr
0x1807d83a7  jmp     short loc_1807D83B1
0x1807d83a9  mov     rcx, rbx; this
0x1807d83ac  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1807d83b1  mov     [rax], r14
0x1807d83b4  mov     rcx, rax
0x1807d83b7  mov     rax, r13
0x1807d83ba  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rcx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1807d83c3  jmp     short loc_1807D8357
0x1807d83c5  mov     qword ptr [rsp+8F0h+var_880], r15
0x1807d83ca  lea     rcx, [rsp+8F0h+var_880]
0x1807d83cf  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1807d83d4  jmp     short loc_1807D8357
0x1807d83d6  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1807d83dd  mov     rax, [rcx]
0x1807d83e0  lea     r8, [rbp+7F0h+var_7A8]
0x1807d83e4  lea     rdx, [rbp+7F0h+var_6A8]
0x1807d83eb  mov     rax, [rax+70h]
0x1807d83ef  call    cs:__guard_dispatch_icall_fptr
0x1807d83f5  movups  xmm0, xmmword ptr [rax]
0x1807d83f8  movdqu  [rbp+7F0h+var_6E0], xmm0
0x1807d8400  lea     rcx, [rbp+7F0h+var_7A8]; this
0x1807d8404  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x1807d8409  xor     r8d, r8d
0x1807d840c  lea     rdx, [rbp+7F0h+var_6E0]
0x1807d8413  lea     rcx, [rsp+8F0h+var_880]
0x1807d8418  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x1807d841e  mov     r14, [rax]
0x1807d8421  mov     [rax], r15
0x1807d8424  mov     [rbp+7F0h+var_6A8], r14
0x1807d842b  mov     rcx, qword ptr [rsp+8F0h+var_880]
0x1807d8430  test    rcx, rcx
0x1807d8433  jz      short loc_1807D8442
0x1807d8435  mov     rax, [rcx]
0x1807d8438  mov     rax, [rax+8]
0x1807d843c  call    cs:__guard_dispatch_icall_fptr
0x1807d8442  mov     rbx, [rbp+7F0h+var_840]
0x1807d8446  xor     r9d, r9d
0x1807d8449  mov     r8, r14
0x1807d844c  mov     rdx, rdi
0x1807d844f  lea     rcx, [rsp+8F0h+var_888]
0x1807d8454  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x1807d845a  nop
0x1807d845b  mov     rdx, [rax]
0x1807d845e  mov     rcx, rbx
0x1807d8461  call    ??$Add@UIdentity@Math@@$0A@@ITopLevelEffect@GEL@@QEAAXAEBUIEffect@1@AEBUIdentity@Math@@@Z; GEL::ITopLevelEffect::Add<Math::Identity,0>(GEL::IEffect const &,Math::Identity const &)
0x1807d8466  nop
0x1807d8467  mov     rcx, [rsp+8F0h+var_888]
0x1807d846c  test    rcx, rcx
0x1807d846f  jz      short loc_1807D847E
0x1807d8471  mov     rax, [rcx]
0x1807d8474  mov     rax, [rax+8]
0x1807d8478  call    cs:__guard_dispatch_icall_fptr
0x1807d847e  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1807d8483  mov     rdx, rax
0x1807d8486  mov     rcx, [rax]
0x1807d8489  mov     rax, [rcx+138h]
0x1807d8490  mov     rcx, rdx
0x1807d8493  call    cs:__guard_dispatch_icall_fptr
0x1807d8499  mov     ecx, eax
0x1807d849b  call    cs:__imp_MsoFLidBiDi
0x1807d84a1  xorps   xmm9, xmm9
0x1807d84a5  test    eax, eax
0x1807d84a7  jz      short loc_1807D84BD
0x1807d84a9  mov     r12b, r13b
0x1807d84ac  mov     byte ptr [rsp+8F0h+var_890], r13b
0x1807d84b1  subsd   xmm7, xmm6
0x1807d84b5  mov     bl, r13b
0x1807d84b8  mov     dil, r13b
0x1807d84bb  jmp     short loc_1807D84CE
0x1807d84bd  mov     r12b, r15b
0x1807d84c0  mov     byte ptr [rsp+8F0h+var_890], r15b
0x1807d84c5  xorps   xmm7, xmm7
0x1807d84c8  mov     bl, r15b
0x1807d84cb  mov     dil, r15b
0x1807d84ce  movaps  xmm2, xmm6
0x1807d84d1  mulsd   xmm2, cs:__real@3fe0000000000000; double
0x1807d84d9  movaps  xmm3, xmm7; double
0x1807d84dc  mov     rdx, [rbp+7F0h+var_840]; struct GEL::ITopLevelEffect *
0x1807d84e0  mov     rcx, rsi; this
0x1807d84e3  call    ?DrawStatusBarIcon@PlayOOUITextureContent@Art@@AEBAXAEAUITopLevelEffect@GEL@@NN@Z; Art::PlayOOUITextureContent::DrawStatusBarIcon(GEL::ITopLevelEffect &,double,double)
0x1807d84e8  xorps   xmm0, xmm0
0x1807d84eb  movdqu  [rbp+7F0h+var_748], xmm0
0x1807d84f3  mov     [rbp+7F0h+var_738], 41400000h
0x1807d84fe  mov     [rbp+7F0h+var_730], r15
0x1807d8505  mov     [rbp+7F0h+var_728], 1
0x1807d850e  mov     [rbp+7F0h+var_724], r15
0x1807d8515  mov     [rbp+7F0h+var_71C], r15b
0x1807d851c  call    cs:__imp_?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x1807d8522  mov     r10, rax
0x1807d8525  mov     rcx, [rax]
0x1807d8528  mov     rax, [rcx+10h]
0x1807d852c  mov     qword ptr [rsp+8F0h+var_8C8], r15
0x1807d8531  mov     [rsp+8F0h+var_8D0], r15b
0x1807d8536  mov     r9b, r13b
0x1807d8539  lea     r8, aSegoeUi; "Segoe UI"
0x1807d8540  lea     rdx, [rsp+8F0h+var_880]
0x1807d8545  mov     rcx, r10
0x1807d8548  call    cs:__guard_dispatch_icall_fptr
0x1807d854e  mov     r13, [rax]
0x1807d8551  mov     [rax], r15
0x1807d8554  mov     qword ptr [rbp+7F0h+var_748], r13
0x1807d855b  mov     rcx, qword ptr [rsp+8F0h+var_880]
0x1807d8560  test    rcx, rcx
0x1807d8563  jz      short loc_1807D8575
0x1807d8565  mov     rax, [rcx]
0x1807d8568  mov     rax, [rax+8]
0x1807d856c  call    cs:__guard_dispatch_icall_fptr
0x1807d8572  mov     bl, dil
0x1807d8575  movd    xmm0, dword ptr [rsi+2Ch]
0x1807d857a  cvtdq2pd xmm0, xmm0
0x1807d857e  mulsd   xmm0, xmm8; X
0x1807d8583  call    cs:__imp_round
0x1807d8589  cvttsd2si rdi, xmm0
0x1807d858e  mov     [rbp+7F0h+var_7C8], rdi
0x1807d8592  test    bl, bl
0x1807d8594  jz      short loc_1807D859B
0x1807d8596  movaps  xmm1, xmm6
0x1807d8599  jmp     short loc_1807D859E
0x1807d859b  xorps   xmm1, xmm1
0x1807d859e  movd    xmm0, dword ptr [rsi+28h]
0x1807d85a3  cvtdq2pd xmm0, xmm0
0x1807d85a7  mulsd   xmm0, xmm8
0x1807d85ac  subsd   xmm0, xmm1; X
0x1807d85b0  call    cs:__imp_round
0x1807d85b6  cvttsd2si rbx, xmm0
0x1807d85bb  mov     [rbp+7F0h+var_818], rbx
0x1807d85bf  movd    xmm0, dword ptr [rsi+24h]
0x1807d85c4  cvtdq2pd xmm0, xmm0
0x1807d85c8  mulsd   xmm0, xmm8; X
0x1807d85cd  call    cs:__imp_round
0x1807d85d3  cvttsd2si r15, xmm0
0x1807d85d8  mov     [rbp+7F0h+var_7C0], r15
0x1807d85dc  test    r12b, r12b
0x1807d85df  jnz     short loc_1807D85E5
0x1807d85e1  movaps  xmm9, xmm6
0x1807d85e5  movd    xmm0, dword ptr [rsi+20h]
0x1807d85ea  cvtdq2pd xmm0, xmm0
0x1807d85ee  mulsd   xmm0, xmm8
0x1807d85f3  addsd   xmm0, xmm9; X
0x1807d85f8  call    cs:__imp_round
0x1807d85fe  cvttsd2si rax, xmm0
0x1807d8603  mov     [rbp+7F0h+var_6D0], rax
0x1807d860a  mov     [rbp+7F0h+var_6C8], r15
0x1807d8611  mov     [rbp+7F0h+var_6C0], rbx
0x1807d8618  mov     [rbp+7F0h+var_6B8], rdi
0x1807d861f  mov     rcx, [rsi+18h]
0x1807d8623  mov     rax, [rcx]
0x1807d8626  lea     rdx, [rbp+7F0h+var_830]
0x1807d862a  mov     rax, [rax+0C0h]
0x1807d8631  call    cs:__guard_dispatch_icall_fptr
0x1807d8637  nop
0x1807d8638  mov     ecx, 30h ; '0'; this
0x1807d863d  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1807d8642  mov     [rbp+7F0h+var_858], rax
0x1807d8646  test    rax, rax
0x1807d8649  jz      short loc_1807D8658
0x1807d864b  mov     rcx, rax; this
0x1807d864e  call    ??0TextBody@Art@@QEAA@XZ; Art::TextBody::TextBody(void)
0x1807d8653  mov     r15, rax
0x1807d8656  jmp     short loc_1807D865B
0x1807d8658  xor     r15d, r15d
0x1807d865b  lea     rdi, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1807d8662  test    r15, r15
0x1807d8665  jz      short loc_1807D8689
0x1807d8667  mov     rbx, [r15+20h]
0x1807d866b  mov     eax, 1
0x1807d8670  xchg    eax, [rbx]
0x1807d8672  lea     rcx, ??$TDestructFromProxy@$$CBVScrapOwningCutCopyHandler@Dr@@@Ofc@@YAXPEAX@Z; Ptr
0x1807d8679  call    cs:__imp_EncodePointer
0x1807d867f  mov     [rbx+8], rax
0x1807d8683  mov     [rbx+10h], r15
0x1807d8687  jmp     short loc_1807D868C
0x1807d8689  mov     rbx, rdi
0x1807d868c  mov     [rbp+7F0h+var_860], rbx
0x1807d8690  lea     rcx, [rbp+7F0h+var_4C0]; this
0x1807d8697  call    ??0CTransaction@Ofc@@QEAA@XZ; Ofc::CTransaction::CTransaction(void)
0x1807d869c  mov     rcx, [rbp+7F0h+var_860]; this
0x1807d86a0  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1807d86a5  xor     r15d, r15d
0x1807d86a8  mov     [rsp+8F0h+var_888], r15
0x1807d86ad  mov     [rsp+8F0h+var_8C8], r15b; bool
0x1807d86b2  mov     [rsp+8F0h+var_8D0], r15b; bool
0x1807d86b7  mov     r9, [rbp+7F0h+var_830]; wchar_t *
0x1807d86bb  lea     r8, [rsp+8F0h+var_888]; struct Art::TextRange *
0x1807d86c0  lea     rdx, [rbp+7F0h+var_4C0]; struct Ofc::CTransaction *
0x1807d86c7  mov     rcx, rax; this
0x1807d86ca  call    ?PutChars@TextBody@Art@@QEAAXAEAVCTransaction@Ofc@@AEBUTextRange@2@PEB_W_N3@Z; Art::TextBody::PutChars(Ofc::CTransaction &,Art::TextRange const &,wchar_t const *,bool,bool)
0x1807d86cf  mov     rax, [r13+0]
0x1807d86d3  mov     rcx, r13
0x1807d86d6  mov     rax, [rax+18h]
0x1807d86da  call    cs:__guard_dispatch_icall_fptr
0x1807d86e0  mov     rdx, [rax]; wchar_t *
0x1807d86e3  lea     rcx, [rbp+7F0h+var_778]; this
0x1807d86e7  call    ??0TextFont@Art@@QEAA@PEB_W@Z; Art::TextFont::TextFont(wchar_t const *)
0x1807d86ec  nop
0x1807d86ed  nop     dword ptr [rax]
0x1807d86f0  xorps   xmm0, xmm0
0x1807d86f3  movdqu  [rbp+7F0h+var_7F8], xmm0
0x1807d86f8  mov     [rbp+7F0h+var_7E8], r15
0x1807d86fc  movsd   xmm0, cs:__real@4028000000000000
0x1807d8704  movsd   qword ptr [rsp+8F0h+var_880], xmm0
0x1807d870a  lea     rdx, [rsp+8F0h+var_880]; struct Art::Points *
0x1807d870f  lea     rcx, [rsp+8F0h+var_888]; this
0x1807d8714  call    ??0TextFontSize@Art@@QEAA@AEBVPoints@1@@Z; Art::TextFontSize::TextFontSize(Art::Points const &)
  ... truncated ...
```
