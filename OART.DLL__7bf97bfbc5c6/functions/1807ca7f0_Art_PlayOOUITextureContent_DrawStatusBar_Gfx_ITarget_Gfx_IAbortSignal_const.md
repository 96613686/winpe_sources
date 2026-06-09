# Art::PlayOOUITextureContent::DrawStatusBar(Gfx::ITarget &,Gfx::IAbortSignal const *)

- ea: `0x1807ca7f0`
- end: `0x1807cb285`
- name: `?DrawStatusBar@PlayOOUITextureContent@Art@@AEAA_NAEAUITarget@Gfx@@PEBUIAbortSignal@4@@Z`
- size: `2709`
- prototype: `bool __fastcall(Art::PlayOOUITextureContent *__hidden this, struct Gfx::ITarget *, const struct Gfx::IAbortSignal *)`
- caller_count: `1`
- callee_count: `52`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801452d0`

## callees

- `0x18001daf0`
- `0x18001df00`
- `0x18003ff50`
- `0x180040d20`
- `0x18004111c`
- `0x1800424d0`
- `0x180065990`
- `0x1800659a0`
- `0x18006d0a0`
- `0x180070fe0`
- `0x180071720`
- `0x180079890`
- `0x1800ba4e0`
- `0x180101590`
- `0x1801029bc`
- `0x180103b6c`
- `0x180137b98`
- `0x180138de4`
- `0x18014bc30`
- `0x18014d858`
- `0x1801ad3e0`
- `0x1801ada80`
- `0x1801b7fe0`
- `0x1801bd760`
- `0x1801c2ad8`
- `0x1801cf720`
- `0x1801f44a0`
- `0x1802793e0`
- `0x180279e20`
- `0x18027b0c0`
- `0x18027b1c0`
- `0x18027b270`
- `0x18027c0e8`
- `0x18032ef3c`
- `0x1803d3280`
- `0x1804c46dc`
- `0x1804ef7d4`
- `0x18050d290`
- `0x1805516c0`
- `0x1805f1970`
- `0x180653700`
- `0x18067bb58`
- `0x180699eb8`
- `0x1806a0f48`
- `0x1806a0f74`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806bac28`
- `0x1806bace0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1807cabb6`
- `KERNEL32!EncodePointer` at `0x1807cae90`
- `KERNEL32!EncodePointer` at `0x1807cabb6`
- `KERNEL32!EncodePointer` at `0x1807cae90`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807caabf`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807caaed`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807cab0a`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807cab35`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807caabf`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807caaed`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807cab0a`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1807cab35`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1807ca9a7`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z` at `0x1807ca9a7`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1807caa5b`
- `gfx!?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ` at `0x1807caa5b`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1807ca96b`
- `gfx!?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z` at `0x1807ca96b`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1807ca866`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1807ca866`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1807ca8cd`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1807ca8cd`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1807ca9ec`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1807ca9ec`

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
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 v15; // r15
  struct GEL::ITopLevelEffect *v16; // rbx
  _QWORD *v17; // rax
  Art *v18; // rcx
  struct Art::IAppHost *AppHost; // rax
  unsigned int v20; // eax
  int v21; // r13d
  double v22; // xmm9_8
  double v23; // xmm7_8
  __int64 DefaultTypefaces; // rax
  __int64 v25; // r9
  __int64 *v26; // rax
  __int64 v27; // r12
  __int64 v28; // rdi
  double v29; // xmm1_8
  __int64 v30; // rbx
  __int64 v31; // r14
  unsigned __int64 v32; // rdx
  unsigned int v33; // r8d
  Art::TextBody *v34; // rax
  __int64 v35; // r14
  int *v36; // rdi
  int *v37; // rbx
  Art::TextBody *Checked; // rax
  const wchar_t **v39; // rax
  __int64 v40; // rax
  Art *v41; // rcx
  __int64 v42; // rax
  Art::TextBody *v43; // rbx
  Art::TextBody *v44; // rax
  int v45; // eax
  Art::TextBody *v46; // rbx
  Art::TextBody *v47; // rax
  int v48; // eax
  unsigned __int64 v49; // rdx
  unsigned int v50; // r8d
  Art::SimpleTextFrame *v51; // rax
  __int64 v52; // rbx
  Art::SimpleTextFrame *v53; // rax
  struct Ofc::CProxyPtrImpl *v54; // rdx
  Art::SimpleTextFrame *v55; // rax
  struct Art::PosSize2D *v56; // r9
  Art::SimpleTextFrame *v57; // rax
  int v58; // edi
  struct Ofc::CProxyPtrImpl *v59; // rcx
  struct GEL::ITopLevelEffect *v60; // rbx
  _QWORD *TextBuilderEffects; // rax
  unsigned int v62; // edx
  __int64 v63; // rbx
  const struct Art::TextViewLine *TextViewLine; // rax
  bool v65; // cc
  char v66; // al
  int v68; // [rsp+30h] [rbp-D8h]
  struct Ofc::CProxyPtrImpl *v69; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v70; // [rsp+70h] [rbp-98h] BYREF
  Ofc::CProxyPtrImpl *v71; // [rsp+78h] [rbp-90h] BYREF
  double v72; // [rsp+80h] [rbp-88h] BYREF
  __int64 v73; // [rsp+88h] [rbp-80h] BYREF
  void (__fastcall *v74)(Art::TextEffectRecorder *__hidden, const struct Art::AlphaModulateEffect *); // [rsp+90h] [rbp-78h]
  char v75; // [rsp+98h] [rbp-70h]
  __int64 v76[2]; // [rsp+A0h] [rbp-68h] BYREF
  char v77; // [rsp+B0h] [rbp-58h]
  struct GEL::ITopLevelEffect *v78; // [rsp+B8h] [rbp-50h] BYREF
  Ofc::CProxyPtrImpl *v79; // [rsp+C0h] [rbp-48h] BYREF
  wchar_t *v80; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v81; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v82[2]; // [rsp+E0h] [rbp-28h] BYREF
  __m128i v83; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v84[24]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v85; // [rsp+118h] [rbp+10h]
  __int64 v86; // [rsp+120h] [rbp+18h]
  const struct Gfx::IAbortSignal *v87; // [rsp+128h] [rbp+20h]
  __int64 v88; // [rsp+130h] [rbp+28h]
  _BYTE v89[24]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v90[3]; // [rsp+150h] [rbp+48h] BYREF
  __int64 v91; // [rsp+180h] [rbp+78h] BYREF
  __int128 v92; // [rsp+188h] [rbp+80h]
  double v93; // [rsp+198h] [rbp+90h]
  __int128 v94; // [rsp+1A0h] [rbp+98h]
  __int128 v95; // [rsp+1B0h] [rbp+A8h]
  __int64 v96; // [rsp+1C0h] [rbp+B8h]
  __int64 v97; // [rsp+1C8h] [rbp+C0h]
  __int16 v98; // [rsp+1D0h] [rbp+C8h]
  __int64 v99; // [rsp+1D4h] [rbp+CCh]
  char v100; // [rsp+1DCh] [rbp+D4h]
  __int128 v101; // [rsp+1E0h] [rbp+D8h] BYREF
  __int128 v102; // [rsp+1F0h] [rbp+E8h] BYREF
  int v103; // [rsp+200h] [rbp+F8h]
  __int16 v104; // [rsp+204h] [rbp+FCh]
  __int64 v105; // [rsp+208h] [rbp+100h]
  __int64 v106; // [rsp+210h] [rbp+108h]
  __m128i si128; // [rsp+218h] [rbp+110h] BYREF
  _QWORD v108[5]; // [rsp+228h] [rbp+120h] BYREF
  __int64 v109; // [rsp+250h] [rbp+148h] BYREF
  __int128 v110; // [rsp+260h] [rbp+158h] BYREF
  double v111; // [rsp+270h] [rbp+168h]
  double v112; // [rsp+278h] [rbp+170h]
  _BYTE v113[432]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v114[1088]; // [rsp+438h] [rbp+330h] BYREF

  v87 = a3;
  *(_QWORD *)&v81 = a2;
  v5 = (float *)(*(__int64 (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)a2 + 24LL))(a2);
  v83.m128i_i64[0] = (__int64)v5;
  OptimalRenderingPolicyForTarget = Gfx::GetOptimalRenderingPolicyForTarget(a2);
  GEL::ITopLevelEffect::Create(&v78, OptimalRenderingPolicyForTarget);
  v7 = 914400.0 / *v5;
  v8 = (double)(*((_DWORD *)this + 10) - *((_DWORD *)this + 8)) * v7;
  v9 = (double)(*((_DWORD *)this + 11) - *((_DWORD *)this + 9)) * v7;
  v110 = 0;
  v111 = v8;
  v112 = v9;
  v10 = (__int64 *)GEL::IRectanglePath::Create(&v69, &v110);
  v88 = *v10;
  v11 = v88;
  *v10 = 0;
  v108[4] = v11;
  v12 = v69;
  if ( v69 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v69 + 8LL))(v69);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( Art::FInHighContrastMode(v12) )
  {
    Art::Color::Color(v90, 1);
    v13 = Ofc::TSingleton<Art::GelTranslator>::Instance();
    si128 = *(__m128i *)(*(__int64 (__fastcall **)(__int64, __int64 *, _OWORD *))(*(_QWORD *)v13 + 112LL))(
                          v13,
                          &v109,
                          v90);
    Art::Color::~Color((Art::Color *)v90);
  }
  v14 = (__int64 *)GEL::IBrushSolid::Create(&v69, &si128, 0);
  v15 = *v14;
  *v14 = 0;
  v109 = v15;
  if ( v69 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v69 + 8LL))(v69);
  v16 = v78;
  v17 = (_QWORD *)GEL::IEffectFilledPath::Create(&v72, v11, v15, 0);
  GEL::ITopLevelEffect::Add<Math::Identity,0>(v16, *v17);
  v18 = *(Art **)&v72;
  if ( v72 != 0.0 )
    (*(void (__fastcall **)(double))(**(_QWORD **)&v72 + 8LL))(COERCE_DOUBLE(*(_QWORD *)&v72));
  AppHost = Art::GetAppHost(v18);
  v20 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)AppHost + 312LL))(AppHost);
  v21 = MsoFLidBiDi(v20);
  LOBYTE(v70) = v21 != 0;
  v22 = 0.0;
  if ( v21 )
    v23 = v8 - v9;
  else
    v23 = 0.0;
  Art::PlayOOUITextureContent::DrawStatusBarIcon(this, v78, v9 * 0.5, v23);
  v95 = 0;
  v96 = 1094713344;
  v97 = 0;
  v98 = 1;
  v99 = 0;
  v100 = 0;
  DefaultTypefaces = GEL::ITypefaceList::GetDefaultTypefaces();
  LOBYTE(v25) = 1;
  v26 = (__int64 *)(*(__int64 (__fastcall **)(__int64, double *, const wchar_t *, __int64, _BYTE, _QWORD))(*(_QWORD *)DefaultTypefaces + 16LL))(
                     DefaultTypefaces,
                     &v72,
                     L"Segoe UI",
                     v25,
                     0,
                     0);
  v27 = *v26;
  *v26 = 0;
  *(_QWORD *)&v95 = v27;
  if ( v72 != 0.0 )
    (*(void (__fastcall **)(double))(**(_QWORD **)&v72 + 8LL))(COERCE_DOUBLE(*(_QWORD *)&v72));
  v28 = (unsigned int)(int)round((double)*((int *)this + 11) * v7);
  v85 = v28;
  if ( v21 )
    v29 = v9;
  else
    v29 = 0.0;
  v30 = (unsigned int)(int)round((double)*((int *)this + 10) * v7 - v29);
  v82[0] = v30;
  v31 = (unsigned int)(int)round((double)*((int *)this + 9) * v7);
  v86 = v31;
  if ( !v21 )
    v22 = v9;
  v108[0] = (unsigned int)(int)round((double)*((int *)this + 8) * v7 + v22);
  v108[1] = v31;
  v108[2] = v30;
  v108[3] = v28;
  (*(void (__fastcall **)(_QWORD, wchar_t **))(**((_QWORD **)this + 3) + 192LL))(*((_QWORD *)this + 3), &v80);
  v34 = (Art::TextBody *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x30, v32, v33);
  v76[0] = (__int64)v34;
  if ( v34 )
    v35 = Art::TextBody::TextBody(v34);
  else
    v35 = 0;
  v36 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  if ( v35 )
  {
    v37 = *(int **)(v35 + 32);
    _InterlockedExchange(v37, 1);
    *((_QWORD *)v37 + 1) = EncodePointer(Ofc::TDestructFromProxy<Dr::ScrapOwningCutCopyHandler const>);
    *((_QWORD *)v37 + 2) = v35;
  }
  else
  {
    v37 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  }
  v71 = (Ofc::CProxyPtrImpl *)v37;
  Ofc::CTransaction::CTransaction((Ofc::CTransaction *)v114);
  Checked = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v71);
  v69 = 0;
  Art::TextBody::PutChars(Checked, (struct Ofc::CTransaction *)v114, (const struct Art::TextRange *)&v69, v80, 0, 0);
  v39 = (const wchar_t **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
  Art::TextFont::TextFont((Art::TextFont *)&v91, *v39);
  Art::LinearShadeProps::LinearShadeProps((Art::LinearShadeProps *)v84);
  v72 = DOUBLE_12_0;
  v40 = Art::TextFontSize::TextFontSize((Art::TextFontSize *)&v69, (const struct Art::Points *)&v72);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::FontSize>(v84, v40);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::LatinFont>((Ofc::Tph::CPropertySetImpl *)v84);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::EastAsianFont>((Ofc::Tph::CPropertySetImpl *)v84);
  Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::ComplexScriptFont>((Ofc::Tph::CPropertySetImpl *)v84);
  v72 = DOUBLE_0_1882352941176471;
  v69 = *(struct Ofc::CProxyPtrImpl **)&DOUBLE_0_1921568627450981;
  *(double *)v76 = DOUBLE_0_196078431372549;
  Art::Color::Color(
    (Art::Color *)v90,
    (const struct Art::Factor *)v76,
    (const struct Art::Factor *)&v69,
    (const struct Art::Factor *)&v72);
  if ( Art::FInHighContrastMode(v41) )
  {
    v42 = Art::Color::Color(v76, 18);
    Art::Color::operator=(v90, v42);
    Art::Color::~Color((Art::Color *)v76);
  }
  Art::TextCharPropertyBag::SetSolidColor((Art::TextCharPropertyBag *)v84, 0, 0, (const struct Art::Color *)v90);
  v43 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v71);
  v44 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v71);
  v45 = Art::TextBody::Length(v44);
  LODWORD(v69) = 0;
  HIDWORD(v69) = v45;
  Art::TextBody::SetCharPropertyBag(
    v43,
    (struct Ofc::CTransaction *)v114,
    (const struct Art::TextRange *)&v69,
    (const struct Art::TextCharPropertyBag *)v84,
    0);
  Art::LinearShadeProps::LinearShadeProps((Art::LinearShadeProps *)&v73);
  Ofc::TPropertySet<Art::TextParaPropertyBagIDs>::Set<Art::Text::TextRtl>(&v73, &v70);
  v76[1] = (__int64)Art::TextEffectRecorder::Visit;
  v77 = 1;
  v76[0] = v21 != 0 ? 2uLL : 0;
  Ofc::TPropertySet<Art::TextParaPropertyBagIDs>::SetImpl(&v73, 14, v76);
  Ofc::Tph::StgTypeOwner::~StgTypeOwner((Ofc::Tph::StgTypeOwner *)v76);
  v76[1] = (__int64)Art::TextEffectRecorder::Visit;
  v77 = 1;
  v76[0] = 2;
  Ofc::TPropertySet<Art::TextParaPropertyBagIDs>::SetImpl(&v73, 18, v76);
  Ofc::Tph::StgTypeOwner::~StgTypeOwner((Ofc::Tph::StgTypeOwner *)v76);
  v46 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v71);
  v47 = (Art::TextBody *)Ofc::CProxyPtrImpl::GetChecked(v71);
  v48 = Art::TextBody::Length(v47);
  LODWORD(v69) = 0;
  HIDWORD(v69) = v48;
  Art::TextBody::SetParaPropertyBag(
    v46,
    (struct Ofc::CTransaction *)v114,
    (const struct Art::TextRange *)&v69,
    (const struct Art::TextParaPropertyBag *)&v73,
    0);
  Ofc::CTransaction::Commit((Ofc::CTransaction *)v114);
  Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)&v73);
  Art::Color::~Color((Art::Color *)v90);
  Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v84);
  operator delete(*((void **)&v92 + 1));
  Ofc::CRollbackTransaction::~CRollbackTransaction((Ofc::CRollbackTransaction *)v114);
  v51 = (Art::SimpleTextFrame *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0xC8, v49, v50);
  if ( v51 )
    v52 = Art::SimpleTextFrame::SimpleTextFrame(v51);
  else
    v52 = 0;
  if ( v52 )
  {
    v36 = *(int **)(v52 + 32);
    _InterlockedExchange(v36, 1);
    *((_QWORD *)v36 + 1) = EncodePointer(Ofc::TDestructFromProxy<Art::TextDragTracker>);
    *((_QWORD *)v36 + 2) = v52;
  }
  v79 = (Ofc::CProxyPtrImpl *)v36;
  v53 = (Art::SimpleTextFrame *)Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v36);
  v54 = v71;
  if ( *((_DWORD *)v71 + 1) != 0x80000000 )
    _InterlockedAdd((volatile signed __int32 *)v71 + 1, 1u);
  v69 = v54;
  Art::SimpleTextFrame::SetTextBody(v53);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v69);
  Art::LinearShadeProps::LinearShadeProps((Art::LinearShadeProps *)v89);
  v74 = Art::TextEffectRecorder::Visit;
  v75 = 1;
  v73 = 1;
  Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::SetImpl(v89, 10, &v73);
  Ofc::Tph::StgTypeOwner::~StgTypeOwner((Ofc::Tph::StgTypeOwner *)&v73);
  v74 = Art::TextEffectRecorder::Visit;
  v75 = 1;
  v73 = 1;
  Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::SetImpl(v89, 7, &v73);
  Ofc::Tph::StgTypeOwner::~StgTypeOwner((Ofc::Tph::StgTypeOwner *)&v73);
  v74 = Art::TextEffectRecorder::Visit;
  v75 = 1;
  v73 = 0;
  Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::SetImpl(v89, 19, &v73);
  Ofc::Tph::StgTypeOwner::~StgTypeOwner((Ofc::Tph::StgTypeOwner *)&v73);
  v55 = (Art::SimpleTextFrame *)Ofc::CProxyPtrImpl::GetChecked(v79);
  Art::SimpleTextFrame::SetTextFramePropertyBag(v55, (const struct Art::TextBodyPropertyBag *)v89);
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  Art::SetBoundsToOffsetExtents((Art *)v108, (const struct Art::Rect64 *)&v101, (struct Art::Point2D *)&v102, v56);
  v57 = (Art::SimpleTextFrame *)Ofc::CProxyPtrImpl::GetChecked(v79);
  Art::SimpleTextFrame::SetTransform(v57, (const struct Art::Transform2D *)&v101);
  *(_OWORD *)v76 = 0;
  v58 = v81;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81 + 24LL))(v81);
  Gfx::ToRectPxI(&v81, v76);
  v90[0] = _mm_load_si128((const __m128i *)&_xmm);
  v90[1] = _mm_load_si128((const __m128i *)&_xmm);
  v90[2] = v81;
  v91 = *(_QWORD *)&v7;
  v92 = 0;
  v93 = v7;
  v94 = 0;
  Art::PosSize2D::PosSize2D((Art::PosSize2D *)v82, v82[0] - v108[0], v85 - v86);
  v59 = v79;
  if ( *((_DWORD *)v79 + 1) != 0x80000000 )
    _InterlockedAdd((volatile signed __int32 *)v79 + 1, 1u);
  v69 = v59;
  Art::TextBuilder::TextBuilder((Art::TextBuilder *)v113, (__int64)v82, (__int64)&v91, (__int64)v76, 0, 0, 0, 1);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v69);
  v60 = v78;
  TextBuilderEffects = (_QWORD *)Art::GetTextBuilderEffects(&v83, v113);
  GEL::ITopLevelEffect::Add<Math::Identity,0>(v60, *TextBuilderEffects);
  if ( v83.m128i_i64[0] )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83.m128i_i64[0] + 8LL))(v83.m128i_i64[0]);
  v63 = *(_QWORD *)(*((_QWORD *)this + 3) + 16LL);
  if ( v63 )
  {
    TextViewLine = Art::TextBuilder::GetTextViewLine((Art::TextBuilder *)v113, v62);
    if ( !TextViewLine
      || (v65 = *((int *)TextViewLine + 13) <= (unsigned __int64)(unsigned int)(*((_DWORD *)v80 - 1) / 2), v66 = 1, !v65) )
    {
      v66 = 0;
    }
    *(_BYTE *)(v63 + 80) = v66;
  }
  v83 = _mm_load_si128((const __m128i *)&_xmm);
  *(_OWORD *)v82 = 0;
  GEL::ITopLevelEffect::Draw((_DWORD)v78, v58, (unsigned int)v90, (_DWORD)v87, 0, v68, (__int64)v82, (__int64)&v83);
  Art::TextBuilder::~TextBuilder((Art::TextBuilder *)v113);
  Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v89);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v79);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v71);
  Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)&v80);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  if ( v88 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 8LL))(v88);
  if ( v78 )
    (*(void (__fastcall **)(char *))(*((_QWORD *)v78 + 1) + 8LL))((char *)v78 + 8);
  return 1;
}

```

## disassembly

```asm
0x1807ca7f0  mov     rax, rsp
0x1807ca7f3  mov     [rax+20h], rbx
0x1807ca7f7  push    rbp
0x1807ca7f8  push    rsi
0x1807ca7f9  push    rdi
0x1807ca7fa  push    r12
0x1807ca7fc  push    r13
0x1807ca7fe  push    r14
0x1807ca800  push    r15
0x1807ca802  lea     rbp, [rax-7F8h]
0x1807ca809  sub     rsp, 8C0h
0x1807ca810  movaps  xmmword ptr [rax-48h], xmm6
0x1807ca814  movaps  xmmword ptr [rax-58h], xmm7
0x1807ca818  movaps  xmmword ptr [rax-68h], xmm8
0x1807ca81d  movaps  xmmword ptr [rax-78h], xmm9
0x1807ca822  mov     rax, cs:__security_cookie
0x1807ca829  xor     rax, rsp
0x1807ca82c  mov     [rbp+7F0h+var_80], rax
0x1807ca833  mov     [rbp+7F0h+var_7D0], r8
0x1807ca837  mov     rbx, rdx
0x1807ca83a  mov     qword ptr [rbp+7F0h+var_828], rdx
0x1807ca83e  mov     rsi, rcx
0x1807ca841  mov     rax, [rdx]
0x1807ca844  mov     rcx, rdx
0x1807ca847  mov     rax, [rax+18h]
0x1807ca84b  call    cs:__guard_dispatch_icall_fptr
0x1807ca851  mov     rdi, rax
0x1807ca854  mov     qword ptr [rbp+7F0h+var_808], rax
0x1807ca858  mov     rcx, rbx
0x1807ca85b  call    ?GetOptimalRenderingPolicyForTarget@Gfx@@YA?AW4RenderingPolicy@1@AEBUITarget@1@@Z; Gfx::GetOptimalRenderingPolicyForTarget(Gfx::ITarget const &)
0x1807ca860  mov     edx, eax
0x1807ca862  lea     rcx, [rbp+7F0h+var_840]
0x1807ca866  call    cs:__imp_?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z; GEL::ITopLevelEffect::Create(Gfx::RenderingPolicy)
0x1807ca86c  movss   xmm0, dword ptr [rdi]
0x1807ca870  cvtps2pd xmm0, xmm0
0x1807ca873  movsd   xmm8, cs:__real@412be7c000000000
0x1807ca87c  divsd   xmm8, xmm0
0x1807ca881  mov     eax, [rsi+28h]
0x1807ca884  sub     eax, [rsi+20h]
0x1807ca887  movd    xmm7, eax
0x1807ca88b  cvtdq2pd xmm7, xmm7
0x1807ca88f  mulsd   xmm7, xmm8
0x1807ca894  mov     eax, [rsi+2Ch]
0x1807ca897  sub     eax, [rsi+24h]
0x1807ca89a  movd    xmm6, eax
0x1807ca89e  cvtdq2pd xmm6, xmm6
0x1807ca8a2  mulsd   xmm6, xmm8
0x1807ca8a7  xorps   xmm0, xmm0
0x1807ca8aa  movups  [rbp+7F0h+var_698], xmm0
0x1807ca8b1  movsd   [rbp+7F0h+var_688], xmm7
0x1807ca8b9  movsd   [rbp+7F0h+var_680], xmm6
0x1807ca8c1  lea     rdx, [rbp+7F0h+var_698]
0x1807ca8c8  lea     rcx, [rsp+8F0h+var_890]
0x1807ca8cd  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x1807ca8d3  mov     rdi, [rax]
0x1807ca8d6  mov     [rbp+7F0h+var_7C8], rdi
0x1807ca8da  xor     r14d, r14d
0x1807ca8dd  mov     [rax], r14
0x1807ca8e0  mov     [rbp+7F0h+var_6B0], rdi
0x1807ca8e7  mov     rcx, [rsp+8F0h+var_890]
0x1807ca8ec  test    rcx, rcx
0x1807ca8ef  jz      short loc_1807CA8FE
0x1807ca8f1  mov     rax, [rcx]
0x1807ca8f4  mov     rax, [rax+8]
0x1807ca8f8  call    cs:__guard_dispatch_icall_fptr
0x1807ca8fe  movdqa  xmm0, cs:__xmm@3f8000003f69e9ea3f67e7e83f7dfdfe
0x1807ca906  movups  [rbp+7F0h+var_6E0], xmm0
0x1807ca90d  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1807ca912  test    al, al
0x1807ca914  jz      short loc_1807CA95C
0x1807ca916  mov     edx, 1
0x1807ca91b  lea     rcx, [rbp+7F0h+var_7A8]
0x1807ca91f  call    ??0Color@Art@@QEAA@W4SystemColorVal@1@@Z; Art::Color::Color(Art::SystemColorVal)
0x1807ca924  nop
0x1807ca925  call    ?Instance@?$TSingleton@VGelTranslator@Art@@@Ofc@@SAAEAVGelTranslator@Art@@XZ; Ofc::TSingleton<Art::GelTranslator>::Instance(void)
0x1807ca92a  mov     r9, rax
0x1807ca92d  mov     rcx, [rax]
0x1807ca930  mov     rax, [rcx+70h]
0x1807ca934  lea     r8, [rbp+7F0h+var_7A8]
0x1807ca938  lea     rdx, [rbp+7F0h+var_6A8]
0x1807ca93f  mov     rcx, r9
0x1807ca942  call    cs:__guard_dispatch_icall_fptr
0x1807ca948  movups  xmm0, xmmword ptr [rax]
0x1807ca94b  movdqu  [rbp+7F0h+var_6E0], xmm0
0x1807ca953  lea     rcx, [rbp+7F0h+var_7A8]; this
0x1807ca957  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x1807ca95c  xor     r8d, r8d
0x1807ca95f  lea     rdx, [rbp+7F0h+var_6E0]
0x1807ca966  lea     rcx, [rsp+8F0h+var_890]
0x1807ca96b  call    cs:__imp_?Create@IBrushSolid@GEL@@SA?AV?$TCntPtr@UIBrushSolid@GEL@@@Ofc@@AEBUColor@2@PEBUCropInfo@2@@Z; GEL::IBrushSolid::Create(GEL::Color const &,GEL::CropInfo const *)
0x1807ca971  mov     r15, [rax]
0x1807ca974  mov     [rax], r14
0x1807ca977  mov     [rbp+7F0h+var_6A8], r15
0x1807ca97e  mov     rcx, [rsp+8F0h+var_890]
0x1807ca983  test    rcx, rcx
0x1807ca986  jz      short loc_1807CA995
0x1807ca988  mov     rax, [rcx]
0x1807ca98b  mov     rax, [rax+8]
0x1807ca98f  call    cs:__guard_dispatch_icall_fptr
0x1807ca995  mov     rbx, [rbp+7F0h+var_840]
0x1807ca999  xor     r9d, r9d
0x1807ca99c  mov     r8, r15
0x1807ca99f  mov     rdx, rdi
0x1807ca9a2  lea     rcx, [rsp+8F0h+var_878]
0x1807ca9a7  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIBrush@2@PEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::IBrush const &,Math::TAffine3x3<double> const *)
0x1807ca9ad  mov     rdx, [rax]
0x1807ca9b0  mov     rcx, rbx
0x1807ca9b3  call    ??$Add@UIdentity@Math@@$0A@@ITopLevelEffect@GEL@@QEAAXAEBUIEffect@1@AEBUIdentity@Math@@@Z; GEL::ITopLevelEffect::Add<Math::Identity,0>(GEL::IEffect const &,Math::Identity const &)
0x1807ca9b8  mov     rcx, [rsp+8F0h+var_878]
0x1807ca9bd  test    rcx, rcx
0x1807ca9c0  jz      short loc_1807CA9CF
0x1807ca9c2  mov     rax, [rcx]
0x1807ca9c5  mov     rax, [rax+8]
0x1807ca9c9  call    cs:__guard_dispatch_icall_fptr
0x1807ca9cf  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1807ca9d4  mov     rdx, rax
0x1807ca9d7  mov     rcx, [rax]
0x1807ca9da  mov     rax, [rcx+138h]
0x1807ca9e1  mov     rcx, rdx
0x1807ca9e4  call    cs:__guard_dispatch_icall_fptr
0x1807ca9ea  mov     ecx, eax
0x1807ca9ec  call    cs:__imp_MsoFLidBiDi
0x1807ca9f2  mov     r13d, eax
0x1807ca9f5  test    eax, eax
0x1807ca9f7  setnz   byte ptr [rsp+8F0h+var_888]
0x1807ca9fc  xorps   xmm9, xmm9
0x1807caa00  test    eax, eax
0x1807caa02  jz      short loc_1807CAA0A
0x1807caa04  subsd   xmm7, xmm6
0x1807caa08  jmp     short loc_1807CAA0D
0x1807caa0a  xorps   xmm7, xmm7
0x1807caa0d  movaps  xmm2, xmm6
0x1807caa10  mulsd   xmm2, cs:__real@3fe0000000000000; double
0x1807caa18  movaps  xmm3, xmm7; double
0x1807caa1b  mov     rdx, [rbp+7F0h+var_840]; struct GEL::ITopLevelEffect *
0x1807caa1f  mov     rcx, rsi; this
0x1807caa22  call    ?DrawStatusBarIcon@PlayOOUITextureContent@Art@@AEBAXAEAUITopLevelEffect@GEL@@NN@Z; Art::PlayOOUITextureContent::DrawStatusBarIcon(GEL::ITopLevelEffect &,double,double)
0x1807caa27  xorps   xmm0, xmm0
0x1807caa2a  movdqu  [rbp+7F0h+var_748], xmm0
0x1807caa32  mov     [rbp+7F0h+var_738], 41400000h
0x1807caa3d  mov     [rbp+7F0h+var_730], r14
0x1807caa44  mov     [rbp+7F0h+var_728], 1
0x1807caa4d  mov     [rbp+7F0h+var_724], r14
0x1807caa54  mov     [rbp+7F0h+var_71C], r14b
0x1807caa5b  call    cs:__imp_?GetDefaultTypefaces@ITypefaceList@GEL@@SAAEAU12@XZ; GEL::ITypefaceList::GetDefaultTypefaces(void)
0x1807caa61  mov     r10, rax
0x1807caa64  mov     rcx, [rax]
0x1807caa67  mov     rax, [rcx+10h]
0x1807caa6b  mov     qword ptr [rsp+8F0h+var_8C8], r14
0x1807caa70  mov     [rsp+8F0h+var_8D0], r14b
0x1807caa75  mov     r9b, 1
0x1807caa78  lea     r8, aSegoeUi; "Segoe UI"
0x1807caa7f  lea     rdx, [rsp+8F0h+var_878]
0x1807caa84  mov     rcx, r10
0x1807caa87  call    cs:__guard_dispatch_icall_fptr
0x1807caa8d  mov     r12, [rax]
0x1807caa90  mov     [rax], r14
0x1807caa93  mov     qword ptr [rbp+7F0h+var_748], r12
0x1807caa9a  mov     rcx, [rsp+8F0h+var_878]
0x1807caa9f  test    rcx, rcx
0x1807caaa2  jz      short loc_1807CAAB1
0x1807caaa4  mov     rax, [rcx]
0x1807caaa7  mov     rax, [rax+8]
0x1807caaab  call    cs:__guard_dispatch_icall_fptr
0x1807caab1  movd    xmm0, dword ptr [rsi+2Ch]
0x1807caab6  cvtdq2pd xmm0, xmm0
0x1807caaba  mulsd   xmm0, xmm8; X
0x1807caabf  call    cs:__imp_round
0x1807caac5  cvttsd2si rdi, xmm0
0x1807caaca  mov     [rbp+7F0h+var_7E0], rdi
0x1807caace  test    r13d, r13d
0x1807caad1  jz      short loc_1807CAAD8
0x1807caad3  movaps  xmm1, xmm6
0x1807caad6  jmp     short loc_1807CAADB
0x1807caad8  xorps   xmm1, xmm1
0x1807caadb  movd    xmm0, dword ptr [rsi+28h]
0x1807caae0  cvtdq2pd xmm0, xmm0
0x1807caae4  mulsd   xmm0, xmm8
0x1807caae9  subsd   xmm0, xmm1; X
0x1807caaed  call    cs:__imp_round
0x1807caaf3  cvttsd2si rbx, xmm0
0x1807caaf8  mov     [rbp+7F0h+var_818], rbx
0x1807caafc  movd    xmm0, dword ptr [rsi+24h]
0x1807cab01  cvtdq2pd xmm0, xmm0
0x1807cab05  mulsd   xmm0, xmm8; X
0x1807cab0a  call    cs:__imp_round
0x1807cab10  cvttsd2si r14, xmm0
0x1807cab15  mov     [rbp+7F0h+var_7D8], r14
0x1807cab19  test    r13d, r13d
0x1807cab1c  jnz     short loc_1807CAB22
0x1807cab1e  movaps  xmm9, xmm6
0x1807cab22  movd    xmm0, dword ptr [rsi+20h]
0x1807cab27  cvtdq2pd xmm0, xmm0
0x1807cab2b  mulsd   xmm0, xmm8
0x1807cab30  addsd   xmm0, xmm9; X
0x1807cab35  call    cs:__imp_round
0x1807cab3b  cvttsd2si rax, xmm0
0x1807cab40  mov     [rbp+7F0h+var_6D0], rax
0x1807cab47  mov     [rbp+7F0h+var_6C8], r14
0x1807cab4e  mov     [rbp+7F0h+var_6C0], rbx
0x1807cab55  mov     [rbp+7F0h+var_6B8], rdi
0x1807cab5c  mov     rcx, [rsi+18h]
0x1807cab60  mov     rax, [rcx]
0x1807cab63  lea     rdx, [rbp+7F0h+var_830]
0x1807cab67  mov     rax, [rax+0C0h]
0x1807cab6e  call    cs:__guard_dispatch_icall_fptr
0x1807cab74  nop
0x1807cab75  mov     ecx, 30h ; '0'; this
0x1807cab7a  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1807cab7f  mov     [rbp+7F0h+var_858], rax
0x1807cab83  test    rax, rax
0x1807cab86  jz      short loc_1807CAB95
0x1807cab88  mov     rcx, rax; this
0x1807cab8b  call    ??0TextBody@Art@@QEAA@XZ; Art::TextBody::TextBody(void)
0x1807cab90  mov     r14, rax
0x1807cab93  jmp     short loc_1807CAB98
0x1807cab95  xor     r14d, r14d
0x1807cab98  lea     rdi, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1807cab9f  test    r14, r14
0x1807caba2  jz      short loc_1807CABC6
0x1807caba4  mov     rbx, [r14+20h]
0x1807caba8  mov     eax, 1
0x1807cabad  xchg    eax, [rbx]
0x1807cabaf  lea     rcx, ??$TDestructFromProxy@$$CBVScrapOwningCutCopyHandler@Dr@@@Ofc@@YAXPEAX@Z; Ptr
0x1807cabb6  call    cs:__imp_EncodePointer
0x1807cabbc  mov     [rbx+8], rax
0x1807cabc0  mov     [rbx+10h], r14
0x1807cabc4  jmp     short loc_1807CABC9
0x1807cabc6  mov     rbx, rdi
0x1807cabc9  mov     [rsp+8F0h+var_880], rbx
0x1807cabce  lea     rcx, [rbp+7F0h+var_4C0]; this
0x1807cabd5  call    ??0CTransaction@Ofc@@QEAA@XZ; Ofc::CTransaction::CTransaction(void)
0x1807cabda  mov     rcx, [rsp+8F0h+var_880]; this
0x1807cabdf  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1807cabe4  xor     r14d, r14d
0x1807cabe7  mov     [rsp+8F0h+var_890], r14
0x1807cabec  mov     [rsp+8F0h+var_8C8], r14b; bool
0x1807cabf1  mov     [rsp+8F0h+var_8D0], r14b; bool
0x1807cabf6  mov     r9, [rbp+7F0h+var_830]; wchar_t *
0x1807cabfa  lea     r8, [rsp+8F0h+var_890]; struct Art::TextRange *
0x1807cabff  lea     rdx, [rbp+7F0h+var_4C0]; struct Ofc::CTransaction *
0x1807cac06  mov     rcx, rax; this
0x1807cac09  call    ?PutChars@TextBody@Art@@QEAAXAEAVCTransaction@Ofc@@AEBUTextRange@2@PEB_W_N3@Z; Art::TextBody::PutChars(Ofc::CTransaction &,Art::TextRange const &,wchar_t const *,bool,bool)
0x1807cac0e  mov     rax, [r12]
0x1807cac12  mov     rcx, r12
0x1807cac15  mov     rax, [rax+18h]
0x1807cac19  call    cs:__guard_dispatch_icall_fptr
0x1807cac1f  mov     rdx, [rax]; wchar_t *
0x1807cac22  lea     rcx, [rbp+7F0h+var_778]; this
0x1807cac26  call    ??0TextFont@Art@@QEAA@PEB_W@Z; Art::TextFont::TextFont(wchar_t const *)
0x1807cac2b  nop
0x1807cac2c  nop     dword ptr [rax+00h]
0x1807cac30  lea     rcx, [rbp+7F0h+var_7F8]; this
0x1807cac34  call    ??0LinearShadeProps@Art@@QEAA@XZ; Art::LinearShadeProps::LinearShadeProps(void)
0x1807cac39  movsd   xmm0, cs:__real@4028000000000000
0x1807cac41  movsd   [rsp+8F0h+var_878], xmm0
0x1807cac47  lea     rdx, [rsp+8F0h+var_878]; struct Art::Points *
0x1807cac4c  lea     rcx, [rsp+8F0h+var_890]; this
0x1807cac51  call    ??0TextFontSize@Art@@QEAA@AEBVPoints@1@@Z; Art::TextFontSize::TextFontSize(Art::Points const &)
0x1807cac56  mov     rdx, rax
0x1807cac59  lea     rcx, [rbp+7F0h+var_7F8]
0x1807cac5d  call    ??$Set@UFontSize@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEAAX$$QEAVTextFontSize@Art@@@Z; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::FontSize>(Art::TextFontSize &&)
0x1807cac62  lea     rdx, [rbp+7F0h+var_778]
0x1807cac66  lea     rcx, [rbp+7F0h+var_7F8]
0x1807cac6a  call    ??$Set@ULatinFont@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEAAXAEBVTextFont@Art@@@Z; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::LatinFont>(Art::TextFont const &)
0x1807cac6f  lea     rdx, [rbp+7F0h+var_778]
0x1807cac73  lea     rcx, [rbp+7F0h+var_7F8]
0x1807cac77  call    ??$Set@UEastAsianFont@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEAAXAEBVTextFont@Art@@@Z; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::EastAsianFont>(Art::TextFont const &)
0x1807cac7c  lea     rdx, [rbp+7F0h+var_778]
0x1807cac80  lea     rcx, [rbp+7F0h+var_7F8]
0x1807cac84  call    ??$Set@UComplexScriptFont@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEAAXAEBVTextFont@Art@@@Z; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::Set<Art::Text::ComplexScriptFont>(Art::TextFont const &)
0x1807cac89  movsd   xmm0, cs:__real@3fc8181818181818
0x1807cac91  movsd   [rsp+8F0h+var_878], xmm0
0x1807cac97  movsd   xmm1, cs:__real@3fc8989898989899
0x1807cac9f  movsd   [rsp+8F0h+var_890], xmm1
0x1807caca5  movsd   xmm0, cs:__real@3fc9191919191919
0x1807cacad  movsd   [rbp+7F0h+var_858], xmm0
0x1807cacb2  lea     r9, [rsp+8F0h+var_878]; struct Art::Factor *
0x1807cacb7  lea     r8, [rsp+8F0h+var_890]; struct Art::Factor *
0x1807cacbc  lea     rdx, [rbp+7F0h+var_858]; struct Art::Factor *
0x1807cacc0  lea     rcx, [rbp+7F0h+var_7A8]; this
0x1807cacc4  call    ??0Color@Art@@QEAA@AEBVFactor@1@00@Z; Art::Color::Color(Art::Factor const &,Art::Factor const &,Art::Factor const &)
0x1807cacc9  nop
0x1807cacca  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1807caccf  test    al, al
0x1807cacd1  jz      short loc_1807CACF5
0x1807cacd3  lea     edx, [r14+12h]
0x1807cacd7  lea     rcx, [rbp+7F0h+var_858]
0x1807cacdb  call    ??0Color@Art@@QEAA@W4SystemColorVal@1@@Z; Art::Color::Color(Art::SystemColorVal)
0x1807cace0  mov     rdx, rax
0x1807cace3  lea     rcx, [rbp+7F0h+var_7A8]
0x1807cace7  call    ??4Color@Art@@QEAAAEAV01@$$QEAV01@@Z; Art::Color::operator=(Art::Color &&)
0x1807cacec  lea     rcx, [rbp+7F0h+var_858]; this
0x1807cacf0  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x1807cacf5  lea     r9, [rbp+7F0h+var_7A8]; struct Art::Color *
0x1807cacf9  xor     r8d, r8d; bool
0x1807cacfc  xor     edx, edx; bool
0x1807cacfe  lea     rcx, [rbp+7F0h+var_7F8]; this
0x1807cad02  call    ?SetSolidColor@TextCharPropertyBag@Art@@QEAAX_N0AEBVColor@2@@Z; Art::TextCharPropertyBag::SetSolidColor(bool,bool,Art::Color const &)
0x1807cad07  mov     rcx, [rsp+8F0h+var_880]; this
  ... truncated ...
```
