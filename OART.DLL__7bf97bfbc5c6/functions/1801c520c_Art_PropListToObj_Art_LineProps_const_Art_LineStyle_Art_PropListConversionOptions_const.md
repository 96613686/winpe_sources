# Art::PropListToObj(Art::LineProps const &,Art::LineStyle &,Art::PropListConversionOptions const &)

- ea: `0x1801c520c`
- end: `0x1801c5d1d`
- name: `?PropListToObj@Art@@YAXAEBVLineProps@1@AEAVLineStyle@1@AEBUPropListConversionOptions@1@@Z`
- size: `2833`
- prototype: `void __fastcall(Art *__hidden this, const struct Art::LineProps *, struct Art::LineStyle *, const struct Art::PropListConversionOptions *)`
- caller_count: `3`
- callee_count: `60`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801c51f0`
- `0x1801c5e20`
- `0x180349930`

## callees

- `0x18001df00`
- `0x18002c260`
- `0x1800428c8`
- `0x180043ab0`
- `0x1800659a0`
- `0x18006d0a0`
- `0x180071720`
- `0x180077bf0`
- `0x1800902e8`
- `0x1800bac50`
- `0x1800c4740`
- `0x1800cb138`
- `0x1800f0b20`
- `0x180132908`
- `0x180135a08`
- `0x18017e418`
- `0x1801919d0`
- `0x1801c509c`
- `0x1801c520c`
- `0x1801c72e8`
- `0x1801c7300`
- `0x1801c730c`
- `0x1801c7318`
- `0x1801c7338`
- `0x1801c7344`
- `0x1801c73c0`
- `0x1801c7418`
- `0x1801c7470`
- `0x1801c74bc`
- `0x1801c8dc4`
- `0x1801ccc6c`
- `0x1801cccc4`
- `0x1801d0fa8`
- `0x1801d1040`
- `0x1801d3418`
- `0x1801d36ac`
- `0x1801d78c8`
- `0x18020e38c`
- `0x18020f254`
- `0x18020f330`
- `0x1802118bc`
- `0x1803e8170`
- `0x1803e82e8`
- `0x1803e9e8c`
- `0x1803e9edc`
- `0x1803ea0ec`
- `0x180456590`
- `0x180472b28`
- `0x1804e9690`
- `0x1804f4948`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1801c537c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c539f`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c5a44`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c537c`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c539f`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c5a44`
- `mso40uiWin32Client!__imp_?MsoFLockShrGlobals@@YAHPEAPEAUMSOSG@@@Z` at `0x1801c52e5`
- `mso40uiWin32Client!__imp_?MsoFLockShrGlobals@@YAHPEAPEAUMSOSG@@@Z` at `0x1801c52e5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c5b17`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c5ba2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c5cb1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c5b17`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c5ba2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c5cb1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c5367`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c59d9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c59e7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c59f5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c5a03`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c5a11`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c5367`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c59d9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c59e7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c59f5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c5a03`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c5a11`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c5afa`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c5afa`

## pseudocode

```c
void __fastcall Art::PropListToObj(
        Art *this,
        const struct Art::LineProps *a2,
        struct Art::LineStyle *a3,
        const struct Art::PropListConversionOptions *a4)
{
  __int64 v4; // rdi
  __int64 v5; // r14
  const int *v6; // r15
  __int64 v8; // rbx
  __int64 v10; // rax
  __int64 *PropertyStgType; // rax
  __int64 v12; // rax
  __int64 *v13; // rcx
  __int64 v14; // rcx
  char v15; // al
  __int64 *v16; // rcx
  __int64 v17; // rcx
  __int64 *v19; // rcx
  __int64 v20; // rcx
  __int64 v22; // r14
  __int64 v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 *v27; // rax
  unsigned int v28; // edx
  __int64 v29; // rax
  Art::ExtendedColor *v30; // rcx
  __int64 v31; // rcx
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rdx
  __int64 v34; // rax
  unsigned __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rax
  __int64 v39; // rdi
  __int64 v40; // rax
  _DWORD *v41; // rsi
  __int64 v42; // r13
  __int64 v43; // rax
  __int64 v44; // rax
  _DWORD *v45; // rdi
  __int64 v46; // rax
  __int64 v47; // r13
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rsi
  _DWORD *v51; // rdi
  __int64 v52; // rax
  _DWORD *v53; // rdi
  __int64 v54; // rax
  _DWORD *v55; // rdi
  __int64 v56; // rax
  __int64 v57; // r13
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rsi
  _DWORD *v61; // rdi
  __int64 v62; // rax
  _DWORD *v63; // rdi
  __int64 v64; // rax
  _DWORD *v65; // rdi
  __int64 v66; // rax
  __int64 v67; // r13
  __int64 v68; // rax
  Art *v69; // rcx
  struct Art::IAppHost *AppHost; // rax
  __int64 v71; // rax
  __int64 v72; // rdi
  const struct Ofc::Tph::CPropertySetImpl *v73; // rbx
  __int64 v74; // rax
  _DWORD *v75; // rbx
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // r8
  unsigned __int64 v79; // rax
  unsigned __int64 v80; // rcx
  __int64 v81; // rax
  unsigned __int64 v82; // rax
  _DWORD *v83; // rbx
  __int64 v84; // rax
  _DWORD *v85; // rbx
  __int64 v86; // rax
  _DWORD *v87; // rbx
  __int64 v88; // rax
  _DWORD *v89; // rbx
  __int64 v90; // rax
  const struct Art::LineJoinMiterProps *v91; // rdi
  Art *v92; // rax
  struct Art::LineJoinMiter *v93; // r8
  unsigned __int64 v94; // rdx
  unsigned int v95; // r8d
  struct MSOSG *v96; // rax
  __int64 v97; // rax
  void *v98; // rdx
  const struct Art::GradientFillProps *v99; // rbx
  Art *v100; // rax
  struct Art::GradientFill *v101; // r8
  __int64 v102; // rdi
  __int64 v103; // rax
  const struct Art::Color *v104; // rax
  struct Art::FillModeProps *v105; // rax
  __int64 v106; // rdi
  __int64 v107; // rax
  const struct Art::SolidColorFillProps *v108; // rbx
  Art *v109; // rax
  struct Art::SolidColorFill *v110; // r8
  const struct Art::PatternFillProps *v111; // rbx
  Art *v112; // rax
  struct Art::PatternFill *v113; // r8
  __int64 v114; // rcx
  unsigned __int64 v115; // rcx
  __int64 v116; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v117; // [rsp+28h] [rbp-48h]
  _BYTE v118[24]; // [rsp+30h] [rbp-40h] BYREF
  Mso::Memory *v119; // [rsp+48h] [rbp-28h] BYREF
  int v120; // [rsp+50h] [rbp-20h]
  int v121; // [rsp+54h] [rbp-1Ch]
  int v122; // [rsp+58h] [rbp-18h]
  int v123; // [rsp+5Ch] [rbp-14h]
  int v124; // [rsp+60h] [rbp-10h]
  struct MSOSG *v125; // [rsp+B8h] [rbp+48h] BYREF

  v8 = (__int64)a2;
  if ( Art::s_pHost )
  {
    v10 = (*(__int64 (__fastcall **)(struct Art::IAppHost *, const struct Art::LineProps *, struct Art::LineStyle *, const struct Art::PropListConversionOptions *))(*(_QWORD *)Art::s_pHost + 376LL))(
            Art::s_pHost,
            a2,
            a3,
            a4);
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 104LL))(v10);
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 336LL))(v5);
    PropertyStgType = (__int64 *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(this, 0);
    if ( PropertyStgType )
      v12 = *PropertyStgType;
    else
      v12 = 0;
    if ( v12 )
      v4 = v12;
    v13 = *(__int64 **)(v4 + 8);
    v6 = &Ofc::TypeInfo::s_moduleTag;
    if ( (unsigned __int64)v13 <= 1 )
      goto LABEL_23;
    v14 = *v13;
    if ( (struct Art::LinePr::NoFill **)v14 == &Ofc::TypeInfoImpl<Art::LinePr::NoFill>::c_typeInfo )
      goto LABEL_23;
    if ( *(const int **)(v14 + 8) == &Ofc::TypeInfo::s_moduleTag )
    {
LABEL_9:
      v15 = 0;
      goto LABEL_10;
    }
  }
  else
  {
    CrashWithRecovery(0x1E44D300u, 0);
  }
  if ( (unsigned int)__std_type_info_compare(*(_QWORD *)v14 + 8LL, &qword_180E139A8) )
    goto LABEL_9;
LABEL_23:
  v15 = 1;
LABEL_10:
  if ( v15 )
  {
    v125 = 0;
    MsoFLockShrGlobals(&v125);
    if ( v125 && *((_DWORD *)v125 + 114) && *((_BYTE *)a3 + 1) )
    {
      Art::LineSketchTypeProps::LineSketchTypeProps((Art::LineSketchTypeProps *)v118, this);
      v104 = (const struct Art::Color *)Art::Color::Color((Art::Color *)&v119, 4u);
      v105 = (struct Art::FillModeProps *)Art::LineFillProps::LineFillProps((Art::LineFillProps *)&v116, v104);
      Ofc::TPropertySet<Art::LinePropsIDs>::Set<Art::LnPr::LineFill>((Ofc::Tph::CPropertySetImpl *)v118, v105);
      Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v116);
      Art::Color::~Color((Art::Color *)&v119);
      v106 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 336LL))(v5);
      v107 = Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Line>(v118);
      if ( v107 )
        v106 = v107;
      v108 = (const struct Art::SolidColorFillProps *)Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::SwitchTo<Art::Line::SolidColor>(v8);
      v109 = (Art *)Ofc::TChoice<Art::LineFillPropsDataChoiceIDsImpl>::Get<Art::LinePr::SolidFill>(v106);
      Art::PropListToObj(v109, v108, v110);
      Art::PropListToObj<Art::SolidColorLine>(v118, v108, *(unsigned __int16 *)a3);
      Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v118);
    }
    else
    {
      v16 = *(__int64 **)(v8 + 8);
      if ( (unsigned __int64)v16 <= 1
        || (v17 = *v16, (struct Art::Line::None **)v17 == &Ofc::TypeInfoImpl<Art::Line::None>::c_typeInfo)
        || *(const int **)(v17 + 8) != v6
        && !(unsigned int)__std_type_info_compare(*(_QWORD *)v17 + 8LL, &qword_180E1AAE0) )
      {
        if ( *(_QWORD *)(v8 + 8) <= 1u )
          Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::DemandInit(v8);
      }
      else
      {
        Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::TChoice<Art::LineStyleDataChoiceIDsImpl>(&v116);
        v114 = *(_QWORD *)v8;
        *(_QWORD *)v8 = v116;
        v116 = v114;
        v115 = *(_QWORD *)(v8 + 8);
        *(_QWORD *)(v8 + 8) = v117;
        v117 = v115;
        Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v116);
      }
    }
    return;
  }
  v19 = *(__int64 **)(v4 + 8);
  if ( (unsigned __int64)v19 <= 1
    || (v20 = *v19, (struct Art::LinePr::SolidFill **)v20 != &Ofc::TypeInfoImpl<Art::LinePr::SolidFill>::c_typeInfo)
    && (*(const int **)(v20 + 8) == v6 || (unsigned int)__std_type_info_compare(*(_QWORD *)v20 + 8LL, &qword_180E13AE8)) )
  {
    if ( (unsigned __int8)Ofc::TChoice<Art::LineFillPropsDataChoiceIDsImpl>::Is<Art::LinePr::GradientFill>(v4) )
    {
      v99 = (const struct Art::GradientFillProps *)Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::SwitchTo<Art::Line::Gradient>(v8);
      v100 = (Art *)Ofc::TChoice<Art::LineFillPropsDataChoiceIDsImpl>::Get<Art::LinePr::GradientFill>(v4);
      Art::PropListToObj(v100, v99, v101);
      Art::PropListToObj<Art::GradientLine>(this, v99, *(unsigned __int16 *)a3);
    }
    else if ( (unsigned __int8)Ofc::TChoice<Art::LineFillPropsDataChoiceIDsImpl>::Is<Art::LinePr::PatternFill>(v4) )
    {
      v111 = (const struct Art::PatternFillProps *)Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::SwitchTo<Art::Line::Pattern>(v8);
      v112 = (Art *)Ofc::TChoice<Art::LineFillPropsDataChoiceIDsImpl>::Get<Art::LinePr::PatternFill>(v4);
      Art::PropListToObj(v112, v111, v113);
      Art::PropListToObj<Art::PatternLine>(this, v111, *(unsigned __int16 *)a3);
    }
    else
    {
      MsoShipAssertTagProc(2750554);
    }
    return;
  }
  v22 = Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::SwitchTo<Art::Line::SolidColor>(v8);
  v23 = Ofc::TChoice<Art::LineFillPropsDataChoiceIDsImpl>::Get<Art::LinePr::SolidFill>(v4);
  if ( !Art::s_pHost )
  {
    CrashWithRecovery(0x1E44D300u, 0);
LABEL_96:
    CrashWithRecovery(0x1E44D300u, 0);
LABEL_97:
    CrashWithRecovery(0x1E44D300u, 0);
LABEL_98:
    CrashWithRecovery(0x1E44D300u, 0);
    goto LABEL_99;
  }
  v24 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
  v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 104LL))(v24);
  v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
  v27 = (__int64 *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v23, 0);
  if ( v27 )
    v29 = *v27;
  else
    v29 = 0;
  if ( v29 )
    v26 = v29;
  v30 = *(Art::ExtendedColor **)(v22 + 16);
  if ( v30 )
    Art::ExtendedColor::`scalar deleting destructor'(v30, v28);
  *(_QWORD *)(v22 + 16) = 0;
  v31 = 0;
  v116 = 0;
  v32 = *(_QWORD *)(v26 + 8);
  v117 = v32;
  if ( v32 <= 1 )
  {
    v33 = 0;
  }
  else
  {
    (*(void (__fastcall **)(__int64 *, __int64))(v32 + 8))(&v116, v26);
    v33 = v117;
    v31 = v116;
  }
  v34 = *(_QWORD *)v22;
  *(_QWORD *)v22 = v31;
  v116 = v34;
  v35 = *(_QWORD *)(v22 + 8);
  *(_QWORD *)(v22 + 8) = v33;
  v117 = v35;
  if ( v35 > 1 )
    (*(void (__fastcall **)(__int64 *))(v35 + 16))(&v116);
  if ( *(_QWORD *)(v26 + 16) )
  {
    v120 = -1;
    v121 = -1;
    v122 = -1;
    v123 = -1;
    v119 = 0;
    v124 = 0x20000000;
    Art::ExtendedColor::operator=(&v119);
    v96 = (struct MSOSG *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v94, v95);
    v125 = v96;
    v97 = v96 ? Art::ExtendedColor::ExtendedColor(v96, (const struct Art::ExtendedColor *)&v119) : 0LL;
    Ofc::TOwnerPtr<Art::ExtendedColor>::Attach(v22 + 16, v97);
    if ( v119 )
      Mso::Memory::Free(v119, v98);
  }
  v8 = *(unsigned __int16 *)a3;
  if ( !Art::s_pHost )
    goto LABEL_96;
  v36 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
  v6 = (const int *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 104LL))(v36);
  v37 = (*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 304LL))(v6);
  v38 = Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(this);
  if ( v38 )
    v37 = v38;
  if ( (unsigned __int8)Ofc::TChoice<Art::LineJoinPropsDataChoiceIDsImpl>::Is<Art::LinePr::Round>(v37) )
  {
    Ofc::TChoice<Art::LineJoinDataChoiceIDsImpl>::SwitchTo<Art::Line::Round>(v22 + 40);
  }
  else if ( (unsigned __int8)Ofc::TChoice<Art::LineJoinPropsDataChoiceIDsImpl>::Is<Art::LinePr::Bevel>(v37) )
  {
    Ofc::TChoice<Art::LineJoinDataChoiceIDsImpl>::SwitchTo<Art::Line::Bevel>(v22 + 40);
  }
  else if ( (unsigned __int8)Ofc::TChoice<Art::LineJoinPropsDataChoiceIDsImpl>::Is<Art::LinePr::Miter>(v37) )
  {
    v91 = (const struct Art::LineJoinMiterProps *)Ofc::TChoice<Art::LineJoinDataChoiceIDsImpl>::SwitchTo<Art::Line::Miter>(v22 + 40);
    v92 = (Art *)Ofc::TChoice<Art::LineJoinPropsDataChoiceIDsImpl>::Get<Art::LinePr::Miter>(v37);
    Art::PropListToObj(v92, v91, v93);
  }
  else
  {
    MsoShipAssertTagProc(506327499);
  }
  v39 = (*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 328LL))(v6);
  v40 = Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::GetPtrIfValid<Art::Text::AutofitProp>(this);
  if ( v40 )
    v39 = v40;
  if ( (unsigned __int8)Ofc::TChoice<Art::LineDashPropsDataChoiceIDsImpl>::Is<Art::LinePr::PresetDash>(v39) )
  {
    v41 = (_DWORD *)Ofc::TChoice<Art::LineDashDataChoiceIDsImpl>::SwitchTo<Art::Line::PresetDash>(v22 + 24);
    v42 = Ofc::TChoice<Art::LineDashPropsDataChoiceIDsImpl>::Get<Art::LinePr::PresetDash>(v39);
    if ( !Art::s_pHost )
    {
LABEL_99:
      CrashWithRecovery(0x1E44D300u, 0);
      goto LABEL_100;
    }
    v43 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
    v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 104LL))(v43);
    v45 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 368LL))(v44);
    v46 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v42, 0);
    if ( v46 )
      v45 = (_DWORD *)v46;
    *v41 = *v45;
  }
  else if ( (unsigned __int8)Ofc::TChoice<Art::LineDashPropsDataChoiceIDsImpl>::Is<Art::LinePr::CustomDash>(v39) )
  {
    v102 = Ofc::TChoice<Art::LineDashPropsDataChoiceIDsImpl>::GetPtr<Art::LinePr::CustomDash>(v39);
    if ( !v102 )
    {
      Ofc::CInvalidParamException::ThrowTag(0x66356D62u);
      __debugbreak();
    }
    v103 = Ofc::TChoice<Art::LineDashDataChoiceIDsImpl>::SwitchTo<Art::Line::CustomDash>(v22 + 24);
    Art::DashStopList::operator=(v103, v102);
  }
  else
  {
    MsoShipAssertTagProc(506327498);
  }
  v47 = (*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 296LL))(v6);
  v48 = Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Highlight>(this);
  if ( v48 )
    v47 = v48;
  if ( !Art::s_pHost )
    goto LABEL_97;
  v49 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
  v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 104LL))(v49);
  v51 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 248LL))(v50);
  v52 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v47, 0);
  if ( v52 )
    v51 = (_DWORD *)v52;
  *(_DWORD *)(v22 + 56) = *v51;
  v53 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 256LL))(v50);
  v54 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v47, 1);
  if ( v54 )
    v53 = (_DWORD *)v54;
  *(_DWORD *)(v22 + 60) = *v53;
  v55 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 240LL))(v50);
  v56 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v47, 2);
  if ( v56 )
    v55 = (_DWORD *)v56;
  *(_DWORD *)(v22 + 64) = *v55;
  v57 = (*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 376LL))(v6);
  v58 = Ofc::TPropertySet<Art::EffectListIDs>::GetPtrIfValid<Art::EfPr::OuterShadow>(this);
  if ( v58 )
    v57 = v58;
  if ( !Art::s_pHost )
    goto LABEL_98;
  v59 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
  v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 104LL))(v59);
  v61 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 248LL))(v60);
  v62 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v57, 0);
  if ( v62 )
    v61 = (_DWORD *)v62;
  *(_DWORD *)(v22 + 68) = *v61;
  v63 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 256LL))(v60);
  v64 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v57, 1);
  if ( v64 )
    v63 = (_DWORD *)v64;
  *(_DWORD *)(v22 + 72) = *v63;
  v65 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 240LL))(v60);
  v66 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v57, 2);
  if ( v66 )
    v65 = (_DWORD *)v66;
  *(_DWORD *)(v22 + 76) = *v65;
  v67 = (*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 288LL))(v6);
  v68 = Ofc::TPropertySet<Art::ShapePropsIDs>::GetPtrIfValid<Art::SpPr::Scene3D>(this);
  if ( v68 )
    v67 = v68;
  if ( !(_BYTE)v8 )
    goto LABEL_86;
  AppHost = Art::GetAppHost(v69);
  v71 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)AppHost + 376LL))(AppHost);
  v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 104LL))(v71);
  v73 = (const struct Ofc::Tph::CPropertySetImpl *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 264LL))(v72);
  v74 = Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::GetPtrIfValid<Art::Text::AutofitProp>(v67);
  if ( v74 )
    v73 = (const struct Ofc::Tph::CPropertySetImpl *)v74;
  Ofc::Tph::CPropertySetImpl::CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v118, v73);
  Art::EffectList::Swap((Art::EffectList *)(v22 + 80), (struct Art::EffectList *)v118);
  Ofc::Tph::CPropertySetImpl::~CPropertySetImpl((Ofc::Tph::CPropertySetImpl *)v118);
  v75 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 272LL))(v72);
  v76 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v67, 4);
  if ( v76 )
    v75 = (_DWORD *)v76;
  *(_DWORD *)(v22 + 104) = *v75;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 408LL))(v72);
  v77 = Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Line>(v67);
  if ( v77 )
    v8 = v77;
  v78 = 0;
  v116 = 0;
  v79 = *(_QWORD *)(v8 + 8);
  v117 = v79;
  if ( v79 <= 1 )
  {
    v80 = 0;
    goto LABEL_84;
  }
LABEL_100:
  (*(void (__fastcall **)(__int64 *, __int64))(v79 + 8))(&v116, v8);
  v80 = v117;
  v78 = v116;
LABEL_84:
  v81 = *(_QWORD *)(v22 + 112);
  *(_QWORD *)(v22 + 112) = v78;
  v116 = v81;
  v82 = *(_QWORD *)(v22 + 120);
  *(_QWORD *)(v22 + 120) = v80;
  v117 = v82;
  if ( v82 > 1 )
    (*(void (__fastcall **)(__int64 *))(v82 + 16))(&v116);
LABEL_86:
  v83 = (_DWORD *)(*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 344LL))(v6);
  v84 = Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::LineWidth>(this);
  if ( v84 )
    v83 = (_DWORD *)v84;
  *(_DWORD *)(v22 + 128) = *v83;
  v85 = (_DWORD *)(*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 312LL))(v6);
  v86 = Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::GetPtrIfValid<Art::Text::HorizontalOverflow>(this);
  if ( v86 )
    v85 = (_DWORD *)v86;
  *(_DWORD *)(v22 + 132) = *v85;
  v87 = (_DWORD *)(*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 320LL))(v6);
  v88 = Ofc::TPropertySet<Dr::ResetTextListStylePropertyBagIDs>::GetPtrIfValid<Dr::Text::listLevel9StyleR>(this);
  if ( v88 )
    v87 = (_DWORD *)v88;
  *(_DWORD *)(v22 + 136) = *v87;
  v89 = (_DWORD *)(*(__int64 (__fastcall **)(const int *))(*(_QWORD *)v6 + 360LL))(v6);
  v90 = Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::PenAlign>(this);
  if ( v90 )
    v89 = (_DWORD *)v90;
  *(_DWORD *)(v22 + 140) = *v89;
}

```

## disassembly

```asm
0x1801c520c  mov     [rsp-28h+arg_0], rbx
0x1801c5211  mov     [rsp-28h+arg_8], rsi
0x1801c5216  mov     [rsp-28h+arg_10], rdi
0x1801c521b  push    rbp
0x1801c521c  push    r12
0x1801c521e  push    r13
0x1801c5220  push    r14
0x1801c5222  push    r15
0x1801c5224  mov     rbp, rsp
0x1801c5227  sub     rsp, 70h
0x1801c522b  mov     rsi, r8
0x1801c522e  mov     rbx, rdx
0x1801c5231  mov     r12, rcx
0x1801c5234  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1801c523b  xor     r13d, r13d
0x1801c523e  test    rcx, rcx
0x1801c5241  jz      loc_1801C5360
0x1801c5247  mov     rax, [rcx]
0x1801c524a  mov     rax, [rax+178h]
0x1801c5251  call    cs:__guard_dispatch_icall_fptr
0x1801c5257  mov     rdx, rax
0x1801c525a  mov     rcx, [rax]
0x1801c525d  mov     rax, [rcx+68h]
0x1801c5261  mov     rcx, rdx
0x1801c5264  call    cs:__guard_dispatch_icall_fptr
0x1801c526a  mov     r14, rax
0x1801c526d  mov     rcx, [rax]
0x1801c5270  mov     rax, [rcx+150h]
0x1801c5277  mov     rcx, r14
0x1801c527a  call    cs:__guard_dispatch_icall_fptr
0x1801c5280  mov     rdi, rax
0x1801c5283  xor     edx, edx
0x1801c5285  mov     rcx, r12
0x1801c5288  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c528d  test    rax, rax
0x1801c5290  jz      loc_1801C5CBC
0x1801c5296  mov     rax, [rax]
0x1801c5299  test    rax, rax
0x1801c529c  cmovnz  rdi, rax
0x1801c52a0  mov     rcx, [rdi+8]
0x1801c52a4  lea     r15, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x1801c52ab  cmp     rcx, 1
0x1801c52af  jbe     loc_1801C538A
0x1801c52b5  mov     rcx, [rcx]
0x1801c52b8  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UNoFill@LinePr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::LinePr::NoFill>::c_typeInfo
0x1801c52bf  cmp     rcx, rax
0x1801c52c2  jz      loc_1801C538A
0x1801c52c8  cmp     [rcx+8], r15
0x1801c52cc  jnz     loc_1801C536E
0x1801c52d2  mov     al, r13b
0x1801c52d5  test    al, al
0x1801c52d7  jz      loc_1801C53B4
0x1801c52dd  mov     [rbp+arg_18], r13
0x1801c52e1  lea     rcx, [rbp+arg_18]
0x1801c52e5  call    cs:__imp_?MsoFLockShrGlobals@@YAHPEAPEAUMSOSG@@@Z; MsoFLockShrGlobals(MSOSG * *)
0x1801c52eb  mov     rax, [rbp+arg_18]
0x1801c52ef  test    rax, rax
0x1801c52f2  jz      short loc_1801C5301
0x1801c52f4  cmp     [rax+1C8h], r13d
0x1801c52fb  jnz     loc_1801C5BB7
0x1801c5301  mov     rcx, [rbx+8]
0x1801c5305  cmp     rcx, 1
0x1801c5309  jbe     loc_1801C53AD
0x1801c530f  mov     rcx, [rcx]
0x1801c5312  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UNone@Line@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Line::None>::c_typeInfo
0x1801c5319  cmp     rcx, rax
0x1801c531c  jz      loc_1801C53AD
0x1801c5322  cmp     [rcx+8], r15
0x1801c5326  jnz     short loc_1801C5391
0x1801c5328  mov     al, r13b
0x1801c532b  test    al, al
0x1801c532d  jz      loc_1801C5CC4
0x1801c5333  cmp     qword ptr [rbx+8], 1
0x1801c5338  ja      short loc_1801C5342
0x1801c533a  mov     rcx, rbx
0x1801c533d  call    ?DemandInit@?$TChoice@VLineStyleDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::DemandInit(void)
0x1801c5342  lea     r11, [rsp+70h+var_s0]
0x1801c5347  mov     rbx, [r11+30h]
0x1801c534b  mov     rsi, [r11+38h]
0x1801c534f  mov     rdi, [r11+40h]
0x1801c5353  mov     rsp, r11
0x1801c5356  pop     r15
0x1801c5358  pop     r14
0x1801c535a  pop     r13
0x1801c535c  pop     r12
0x1801c535e  pop     rbp
0x1801c535f  retn
0x1801c5360  xor     edx, edx
0x1801c5362  mov     ecx, 1E44D300h
0x1801c5367  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801c536d  nop
0x1801c536e  mov     rcx, [rcx]
0x1801c5371  add     rcx, 8
0x1801c5375  lea     rdx, qword_180E139A8
0x1801c537c  call    cs:__imp___std_type_info_compare
0x1801c5382  test    eax, eax
0x1801c5384  jnz     loc_1801C52D2
0x1801c538a  mov     al, 1
0x1801c538c  jmp     loc_1801C52D5
0x1801c5391  mov     rcx, [rcx]
0x1801c5394  add     rcx, 8
0x1801c5398  lea     rdx, qword_180E1AAE0
0x1801c539f  call    cs:__imp___std_type_info_compare
0x1801c53a5  test    eax, eax
0x1801c53a7  jnz     loc_1801C5328
0x1801c53ad  mov     al, 1
0x1801c53af  jmp     loc_1801C532B
0x1801c53b4  mov     rcx, [rdi+8]
0x1801c53b8  cmp     rcx, 1
0x1801c53bc  jbe     short loc_1801C53DB
0x1801c53be  mov     rcx, [rcx]
0x1801c53c1  lea     rax, ?c_typeInfo@?$TypeInfoImpl@USolidFill@LinePr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::LinePr::SolidFill>::c_typeInfo
0x1801c53c8  cmp     rcx, rax
0x1801c53cb  jz      loc_1801C5A52
0x1801c53d1  cmp     [rcx+8], r15
0x1801c53d5  jnz     loc_1801C5A36
0x1801c53db  mov     al, r13b
0x1801c53de  test    al, al
0x1801c53e0  jz      loc_1801C5B22
0x1801c53e6  mov     rcx, rbx
0x1801c53e9  call    ??$SwitchTo@USolidColor@Line@Art@@@?$TChoice@VLineStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVSolidColorLine@Art@@XZ; Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::SwitchTo<Art::Line::SolidColor>(void)
0x1801c53ee  mov     r14, rax
0x1801c53f1  mov     rcx, rdi
0x1801c53f4  call    ??$Get@USolidFill@LinePr@Art@@@?$TChoice@VLineFillPropsDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVSolidColorFillProps@Art@@XZ; Ofc::TChoice<Art::LineFillPropsDataChoiceIDsImpl>::Get<Art::LinePr::SolidFill>(void)
0x1801c53f9  mov     rdi, rax
0x1801c53fc  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1801c5403  test    rcx, rcx
0x1801c5406  jz      loc_1801C59D2
0x1801c540c  mov     rax, [rcx]
0x1801c540f  mov     rax, [rax+178h]
0x1801c5416  call    cs:__guard_dispatch_icall_fptr
0x1801c541c  mov     rdx, rax
0x1801c541f  mov     rcx, [rax]
0x1801c5422  mov     rax, [rcx+68h]
0x1801c5426  mov     rcx, rdx
0x1801c5429  call    cs:__guard_dispatch_icall_fptr
0x1801c542f  mov     rdx, rax
0x1801c5432  mov     rcx, [rax]
0x1801c5435  mov     rax, [rcx+20h]
0x1801c5439  mov     rcx, rdx
0x1801c543c  call    cs:__guard_dispatch_icall_fptr
0x1801c5442  mov     rbx, rax
0x1801c5445  xor     edx, edx
0x1801c5447  mov     rcx, rdi
0x1801c544a  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c544f  test    rax, rax
0x1801c5452  jz      loc_1801C5CF9
0x1801c5458  mov     rax, [rax]
0x1801c545b  test    rax, rax
0x1801c545e  cmovnz  rbx, rax
0x1801c5462  mov     rcx, [r14+10h]; this
0x1801c5466  test    rcx, rcx
0x1801c5469  jnz     loc_1801C5BAD
0x1801c546f  mov     [r14+10h], r13
0x1801c5473  xor     ecx, ecx
0x1801c5475  mov     [rbp+var_50], rcx
0x1801c5479  mov     rax, [rbx+8]
0x1801c547d  mov     [rbp+var_48], rax
0x1801c5481  cmp     rax, 1
0x1801c5485  jbe     loc_1801C5A9C
0x1801c548b  mov     rdx, rbx
0x1801c548e  lea     rcx, [rbp+var_50]
0x1801c5492  mov     rax, [rax+8]
0x1801c5496  call    cs:__guard_dispatch_icall_fptr
0x1801c549c  mov     rdx, [rbp+var_48]
0x1801c54a0  mov     rcx, [rbp+var_50]
0x1801c54a4  mov     rax, [r14]
0x1801c54a7  mov     [r14], rcx
0x1801c54aa  mov     [rbp+var_50], rax
0x1801c54ae  mov     rax, [r14+8]
0x1801c54b2  mov     [r14+8], rdx
0x1801c54b6  mov     [rbp+var_48], rax
0x1801c54ba  cmp     rax, 1
0x1801c54be  jbe     short loc_1801C54CF
0x1801c54c0  lea     rcx, [rbp+var_50]
0x1801c54c4  mov     rax, [rax+10h]
0x1801c54c8  call    cs:__guard_dispatch_icall_fptr
0x1801c54ce  nop
0x1801c54cf  mov     rdx, [rbx+10h]
0x1801c54d3  test    rdx, rdx
0x1801c54d6  jnz     loc_1801C5AA4
0x1801c54dc  movzx   ebx, word ptr [rsi]
0x1801c54df  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1801c54e6  test    rcx, rcx
0x1801c54e9  jz      loc_1801C59E0
0x1801c54ef  mov     rax, [rcx]
0x1801c54f2  mov     rax, [rax+178h]
0x1801c54f9  call    cs:__guard_dispatch_icall_fptr
0x1801c54ff  mov     rdx, rax
0x1801c5502  mov     rcx, [rax]
0x1801c5505  mov     rax, [rcx+68h]
0x1801c5509  mov     rcx, rdx
0x1801c550c  call    cs:__guard_dispatch_icall_fptr
0x1801c5512  mov     r15, rax
0x1801c5515  lea     rdi, [r14+28h]
0x1801c5519  mov     rcx, [rax]
0x1801c551c  mov     rax, [rcx+130h]
0x1801c5523  mov     rcx, r15
0x1801c5526  call    cs:__guard_dispatch_icall_fptr
0x1801c552c  mov     rsi, rax
0x1801c552f  mov     rcx, r12
0x1801c5532  call    ??$GetPtrIfValid@UJoin@LnPr@Art@@@?$TPropertySet@VLinePropsIDs@Art@@@Ofc@@QEBAPEBVLineJoinProps@Art@@XZ; Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(void)
0x1801c5537  test    rax, rax
0x1801c553a  cmovnz  rsi, rax
0x1801c553e  mov     rcx, rsi
0x1801c5541  call    ??$Is@URound@LinePr@Art@@@?$TChoice@VLineJoinPropsDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::LineJoinPropsDataChoiceIDsImpl>::Is<Art::LinePr::Round>(void)
0x1801c5546  test    al, al
0x1801c5548  jz      loc_1801C5A59
0x1801c554e  mov     rcx, rdi
0x1801c5551  call    ??$SwitchTo@URound@Line@Art@@@?$TChoice@VLineJoinDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVLineJoinRound@Art@@XZ; Ofc::TChoice<Art::LineJoinDataChoiceIDsImpl>::SwitchTo<Art::Line::Round>(void)
0x1801c5556  mov     rax, [r15]
0x1801c5559  mov     rcx, r15
0x1801c555c  mov     rax, [rax+148h]
0x1801c5563  call    cs:__guard_dispatch_icall_fptr
0x1801c5569  mov     rdi, rax
0x1801c556c  mov     rcx, r12
0x1801c556f  call    ??$GetPtrIfValid@UAutofitProp@Text@Art@@@?$TPropertySet@VTextBodyPropertyBagIDs@Art@@@Ofc@@QEBAPEBVTextAutofit@Art@@XZ; Ofc::TPropertySet<Art::TextBodyPropertyBagIDs>::GetPtrIfValid<Art::Text::AutofitProp>(void)
0x1801c5574  test    rax, rax
0x1801c5577  cmovnz  rdi, rax
0x1801c557b  mov     rcx, rdi
0x1801c557e  call    ??$Is@UPresetDash@LinePr@Art@@@?$TChoice@VLineDashPropsDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::LineDashPropsDataChoiceIDsImpl>::Is<Art::LinePr::PresetDash>(void)
0x1801c5583  test    al, al
0x1801c5585  jz      loc_1801C5B64
0x1801c558b  lea     rcx, [r14+18h]
0x1801c558f  call    ??$SwitchTo@UPresetDash@Line@Art@@@?$TChoice@VLineDashDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVPresetLineDash@Art@@XZ; Ofc::TChoice<Art::LineDashDataChoiceIDsImpl>::SwitchTo<Art::Line::PresetDash>(void)
0x1801c5594  mov     rsi, rax
0x1801c5597  mov     rcx, rdi
0x1801c559a  call    ??$Get@UPresetDash@LinePr@Art@@@?$TChoice@VLineDashPropsDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVPresetLineDashProps@Art@@XZ; Ofc::TChoice<Art::LineDashPropsDataChoiceIDsImpl>::Get<Art::LinePr::PresetDash>(void)
0x1801c559f  mov     r13, rax
0x1801c55a2  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1801c55a9  test    rcx, rcx
0x1801c55ac  jz      loc_1801C5A0A
0x1801c55b2  mov     rax, [rcx]
0x1801c55b5  mov     rax, [rax+178h]
0x1801c55bc  call    cs:__guard_dispatch_icall_fptr
0x1801c55c2  mov     rdx, rax
0x1801c55c5  mov     rcx, [rax]
0x1801c55c8  mov     rax, [rcx+68h]
0x1801c55cc  mov     rcx, rdx
0x1801c55cf  call    cs:__guard_dispatch_icall_fptr
0x1801c55d5  mov     rdx, rax
0x1801c55d8  mov     rcx, [rax]
0x1801c55db  mov     rax, [rcx+170h]
0x1801c55e2  mov     rcx, rdx
0x1801c55e5  call    cs:__guard_dispatch_icall_fptr
0x1801c55eb  mov     rdi, rax
0x1801c55ee  xor     edx, edx
0x1801c55f0  mov     rcx, r13
0x1801c55f3  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c55f8  test    rax, rax
0x1801c55fb  cmovnz  rdi, rax
0x1801c55ff  mov     eax, [rdi]
0x1801c5601  mov     [rsi], eax
0x1801c5603  mov     rax, [r15]
0x1801c5606  mov     rcx, r15
0x1801c5609  mov     rax, [rax+128h]
0x1801c5610  call    cs:__guard_dispatch_icall_fptr
0x1801c5616  mov     r13, rax
0x1801c5619  mov     rcx, r12
0x1801c561c  call    ??$GetPtrIfValid@UHighlight@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEBAPEBVColorEmbed@Art@@XZ; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Highlight>(void)
0x1801c5621  test    rax, rax
0x1801c5624  cmovnz  r13, rax
0x1801c5628  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1801c562f  test    rcx, rcx
0x1801c5632  jz      loc_1801C59EE
0x1801c5638  mov     rax, [rcx]
0x1801c563b  mov     rax, [rax+178h]
0x1801c5642  call    cs:__guard_dispatch_icall_fptr
0x1801c5648  mov     rdx, rax
0x1801c564b  mov     rcx, [rax]
0x1801c564e  mov     rax, [rcx+68h]
0x1801c5652  mov     rcx, rdx
0x1801c5655  call    cs:__guard_dispatch_icall_fptr
0x1801c565b  mov     rsi, rax
0x1801c565e  mov     rcx, [rax]
0x1801c5661  mov     rax, [rcx+0F8h]
0x1801c5668  mov     rcx, rsi
0x1801c566b  call    cs:__guard_dispatch_icall_fptr
0x1801c5671  mov     rdi, rax
0x1801c5674  xor     edx, edx
0x1801c5676  mov     rcx, r13
0x1801c5679  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c567e  test    rax, rax
0x1801c5681  cmovnz  rdi, rax
0x1801c5685  mov     eax, [rdi]
0x1801c5687  mov     [r14+38h], eax
0x1801c568b  mov     rax, [rsi]
0x1801c568e  mov     rcx, rsi
0x1801c5691  mov     rax, [rax+100h]
0x1801c5698  call    cs:__guard_dispatch_icall_fptr
0x1801c569e  mov     rdi, rax
0x1801c56a1  mov     edx, 1
0x1801c56a6  mov     rcx, r13
0x1801c56a9  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c56ae  test    rax, rax
0x1801c56b1  cmovnz  rdi, rax
0x1801c56b5  mov     eax, [rdi]
0x1801c56b7  mov     [r14+3Ch], eax
0x1801c56bb  mov     rax, [rsi]
0x1801c56be  mov     rcx, rsi
  ... truncated ...
```
