# Art::PropListToObj(Art::ShapePropsMethods<Art::ShapePropsData_<0>> const &,Art::ShapePropertyBag &,Art::PropListConversionOptions &)

- ea: `0x1800fcf60`
- end: `0x1800fdc6e`
- name: `?PropListToObj@Art@@YAXAEBV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@1@AEAVShapePropertyBag@1@AEAUPropListConversionOptions@1@@Z`
- size: `3342`
- prototype: ``
- caller_count: `19`
- callee_count: `51`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cce14`
- `0x18014e780`
- `0x18021dc58`
- `0x1802387e0`
- `0x180243720`
- `0x1802e9330`
- `0x1802ff230`
- `0x180327bf0`
- `0x180328900`
- `0x18032b7e0`
- `0x180383ab8`
- `0x18038a950`
- `0x18043a5f0`
- `0x1804551cc`
- `0x1804888f0`
- `0x18059e570`
- `0x1805ba818`
- `0x18062b6f0`
- `0x180682310`

## callees

- `0x18001a840`
- `0x18002a690`
- `0x180052680`
- `0x1800526e8`
- `0x180068bb8`
- `0x180084b34`
- `0x180099520`
- `0x1800a4038`
- `0x1800b49e0`
- `0x1800b69b0`
- `0x1800b9620`
- `0x1800ba0f0`
- `0x1800bce34`
- `0x1800bf398`
- `0x1800cf6a0`
- `0x1800d0760`
- `0x1800d0780`
- `0x1800dbaf8`
- `0x1800e43d0`
- `0x1800e98e0`
- `0x1800efdc0`
- `0x1800f0328`
- `0x1800fbdf8`
- `0x1800fc3e4`
- `0x1800fc410`
- `0x1800fcf60`
- `0x1800fdc70`
- `0x180101bb0`
- `0x180107d9c`
- `0x180107e38`
- `0x1801538a8`
- `0x180157a0c`
- `0x180157c70`
- `0x1801845e0`
- `0x18022e620`
- `0x180233260`
- `0x1802335d0`
- `0x180233640`
- `0x180279050`
- `0x18027c438`
- `0x180282cec`
- `0x1802c8bdc`
- `0x180458fec`
- `0x1804d3ee4`
- `0x1804f2dd0`
- `0x180571488`
- `0x180584634`
- `0x1806bc678`
- `0x1806d0ea8`
- `0x1808b3cb0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1800fd85b`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800fd87e`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800fd8da`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800fdb97`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800fd85b`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800fd87e`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800fd8da`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800fdb97`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800fdaf1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800fdaf1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fd31c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fd89a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fd8a8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fd31c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fd89a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800fd8a8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd771`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd78f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd7a9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd7d3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fda73`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd771`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd78f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd7a9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fd7d3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800fda73`

## pseudocode

```c
__int64 __fastcall Art::PropListToObj(__int64 a1, __int64 a2, struct Art::LineStyle *a3)
{
  __int64 v3; // r14
  __int64 v7; // rax
  __int64 *v8; // rbx
  __int64 *PropertyStgType; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ecx
  char v19; // r9
  char v20; // r10
  __int64 v21; // rbx
  _QWORD *v22; // rax
  Mso::Memory *v23; // rcx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  Mso::Memory *v26; // rax
  unsigned __int64 v27; // rax
  __int64 v28; // rax
  __int64 *v29; // rcx
  __int64 v30; // rcx
  __int64 *v32; // rcx
  __int64 v33; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdi
  _QWORD *v38; // rax
  unsigned int v39; // edx
  Art::ExtendedColor *v40; // rcx
  Mso::Memory *v41; // rcx
  unsigned __int64 v42; // rax
  __int64 v43; // rdx
  Mso::Memory *v44; // rax
  unsigned __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  char v49; // di
  char *v50; // rax
  Art *v51; // rbx
  Art *v52; // rax
  const struct Art::PropListConversionOptions *v53; // r9
  __int64 v54; // rdi
  __int64 v55; // rax
  unsigned __int64 *v56; // rbx
  Mso::Memory *v57; // rcx
  unsigned __int64 v58; // rax
  __int64 v59; // rdx
  Mso::Memory *v60; // rax
  unsigned __int64 v61; // rax
  __int64 v62; // rbx
  __int64 v63; // rax
  int *v64; // rbx
  __int64 v65; // rax
  char *v66; // rbx
  __int64 v67; // rax
  void *v68; // rdx
  struct Art::Fill::Gradient **v69; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  Mso::Memory *v75; // rcx
  unsigned __int64 v76; // rcx
  Mso::Memory *v77; // rcx
  struct Art::Fill::None **v78; // rcx
  __int64 v79; // rcx
  unsigned __int64 v80; // rcx
  unsigned __int64 *v81; // rcx
  Art::Scene3DData *v82; // rax
  Art::Scene3DData *v83; // rbx
  Art::Shape3DData *v84; // rax
  Art::Shape3DData *v85; // rdi
  Art::ShapeStyleData *v86; // rax
  Art::ShapeStyleData *v87; // rsi
  char v88; // dl
  void *v89; // rdx
  void *v90; // rdx
  void *v91; // rdx
  Mso::Memory *v92; // rbx
  unsigned __int64 v93; // rax
  __int64 result; // rax
  const struct Art::BlipFillProps *v95; // rbx
  Art *v96; // rax
  struct Art::BlipFill *v97; // r8
  Mso::Memory *v98; // rbx
  __int64 v99; // rbx
  int v100; // ecx
  int v101; // ecx
  int v102; // ecx
  int v103; // ecx
  int v104; // ecx
  int v105; // ecx
  int v106; // ecx
  int v107; // ecx
  bool v108; // zf
  int v109; // ecx
  const struct Art::GradientFillProps *v110; // rbx
  Art *v111; // rax
  struct Art::GradientFill *v112; // r8
  unsigned __int64 v113; // rdx
  unsigned int v114; // r8d
  Art::ExtendedColor *v115; // rax
  void *v116; // rdx
  __int64 v117; // rbx
  __int64 v118; // rax
  const struct Art::PatternFillProps *v119; // rbx
  Art *v120; // rax
  struct Art::PatternFill *v121; // r8
  int v122; // ecx
  int v123; // ecx
  int v124; // ecx
  int v125; // ecx
  int v126; // ecx
  int v127; // ecx
  int v128; // ecx
  __int64 *v129; // rcx
  __int64 v130; // rcx
  Mso::Memory *v132; // rax
  struct Art::Fill::None **v133; // rax
  __int64 v134; // r8
  __int64 v135; // r9
  __int64 v136; // rax
  int v137; // r8d
  Mso::Memory *v138; // [rsp+28h] [rbp-99h] BYREF
  __int64 v139; // [rsp+30h] [rbp-91h]
  int v140; // [rsp+38h] [rbp-89h]
  int v141; // [rsp+3Ch] [rbp-85h]
  int v142; // [rsp+40h] [rbp-81h]
  __int64 v143; // [rsp+50h] [rbp-71h]
  __int64 v144; // [rsp+58h] [rbp-69h]
  __int64 v145; // [rsp+68h] [rbp-59h] BYREF
  __int64 v146; // [rsp+70h] [rbp-51h]
  __int64 v147; // [rsp+78h] [rbp-49h]
  __int64 v148; // [rsp+80h] [rbp-41h]
  int v149; // [rsp+88h] [rbp-39h]
  char v150; // [rsp+8Ch] [rbp-35h]
  char v151; // [rsp+8Dh] [rbp-34h]
  __int64 v152; // [rsp+90h] [rbp-31h]
  __int64 v153; // [rsp+98h] [rbp-29h]
  Mso::Memory *v154; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int64 v155; // [rsp+A8h] [rbp-19h]
  Mso::Memory *v156; // [rsp+B0h] [rbp-11h] BYREF
  struct Art::Fill::None **v157; // [rsp+B8h] [rbp-9h]
  __int64 v158; // [rsp+C0h] [rbp-1h] BYREF
  unsigned __int64 v159; // [rsp+C8h] [rbp+7h]
  unsigned __int64 *v160; // [rsp+D0h] [rbp+Fh] BYREF
  Art::Scene3DData *v161; // [rsp+D8h] [rbp+17h] BYREF
  Art::Shape3DData *v162; // [rsp+E0h] [rbp+1Fh] BYREF
  Art::ShapeStyleData *v163; // [rsp+E8h] [rbp+27h]
  int v164; // [rsp+F0h] [rbp+2Fh]
  char v165; // [rsp+F4h] [rbp+33h]
  char v166; // [rsp+F5h] [rbp+34h]
  char v167; // [rsp+F6h] [rbp+35h]

  Art::ShapePropertyBag::ShapePropertyBag((Art::ShapePropertyBag *)&v145);
  if ( Art::s_pHost )
  {
    v7 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 104LL))(v7);
    v8 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 440LL))(v3);
    PropertyStgType = (__int64 *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 0);
    if ( PropertyStgType )
      PropertyStgType = (__int64 *)*PropertyStgType;
    if ( PropertyStgType )
      v8 = PropertyStgType;
    v12 = *v8;
    v13 = 0xFFFFFFFF80000000uLL;
    v14 = 0x7FFFFFFF;
    LOBYTE(v11) = byte_180E14475;
    if ( byte_180E14475 )
    {
      if ( v12 < (__int64)0xFFFFFFFF80000000uLL )
      {
        v12 = 0xFFFFFFFF80000000uLL;
      }
      else if ( v12 > 0x7FFFFFFF )
      {
        v12 = 0x7FFFFFFF;
      }
      goto LABEL_10;
    }
    goto LABEL_110;
  }
  while ( 2 )
  {
    CrashWithRecovery(0x1E44D300u, 0);
LABEL_51:
    v25 = 0;
    while ( 1 )
    {
      v26 = v154;
      v154 = v23;
      v138 = v26;
      v27 = v155;
      v155 = v25;
      v139 = v27;
      if ( v27 > 1 )
        (*(void (__fastcall **)(Mso::Memory **))(v27 + 16))(&v138);
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 400LL))(v3);
      v28 = Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(a1);
      if ( v28 )
        v13 = v28;
      v29 = *(__int64 **)(v13 + 8);
      if ( (unsigned __int64)v29 > 1 )
      {
        v30 = *v29;
        if ( (struct Art::FillPr::NoFill **)v30 != &Ofc::TypeInfoImpl<Art::FillPr::NoFill>::c_typeInfo
          && (*(const int **)(v30 + 8) == &Ofc::TypeInfo::s_moduleTag
           || (unsigned int)__std_type_info_compare(*(_QWORD *)v30 + 8LL, &qword_180E142E8)) )
        {
          break;
        }
      }
      v8 = (__int64 *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::GetPtr<Art::Fill::None>(&v156);
      if ( !v8 )
      {
        v132 = v156;
        v156 = 0;
        v138 = v132;
        v133 = v157;
        v157 = &off_180B7F210;
        v139 = (__int64)v133;
        Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v138);
        v8 = (__int64 *)&v156;
      }
      v12 = Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::NoFill>(v13);
      if ( Art::s_pHost )
      {
        v47 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
        v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 104LL))(v47);
        v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 128LL))(v48);
        v50 = (char *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v12 + 8, 0);
        if ( v50 )
          v49 = *v50;
        *(_BYTE *)v8 = v49;
        goto LABEL_47;
      }
LABEL_109:
      CrashWithRecovery(0x1E44D300u, 0);
LABEL_110:
      v12 = Ofc::TRangeRestricted<__int64,Art::CoordRange>::Pin(v12, v10, v11, v14);
LABEL_10:
      v15 = v8[1];
      if ( (_BYTE)v11 )
      {
        if ( v15 >= v13 )
        {
          v13 = v8[1];
          if ( v15 > v14 )
            v13 = v14;
        }
      }
      else
      {
        v13 = Ofc::TRangeRestricted<__int64,Art::CoordRange>::Pin(v15, v10, v11, v14);
      }
      v16 = v8[2];
      v17 = v8[3];
      v18 = *((_DWORD *)v8 + 8);
      v19 = *((_BYTE *)v8 + 36);
      v20 = *((_BYTE *)v8 + 37);
      v143 = v8[5];
      v144 = v8[6];
      v145 = v12;
      v146 = v13;
      v147 = v16;
      v148 = v17;
      v149 = v18;
      v150 = v19;
      v151 = v20;
      v152 = v143;
      v153 = v144;
      v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 408LL))(v3);
      v22 = (_QWORD *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 1);
      if ( v22 )
        v22 = (_QWORD *)*v22;
      if ( v22 )
        v21 = (__int64)v22;
      v166 = 1;
      v23 = 0;
      v138 = 0;
      v24 = *(_QWORD *)(v21 + 8);
      v139 = v24;
      if ( v24 <= 1 )
        goto LABEL_51;
      (*(void (__fastcall **)(Mso::Memory **, __int64))(v24 + 8))(&v138, v21);
      v25 = v139;
      v23 = v138;
    }
    v32 = *(__int64 **)(v13 + 8);
    if ( (unsigned __int64)v32 <= 1
      || (v33 = *v32, (struct Art::FillPr::SolidFill **)v33 != &Ofc::TypeInfoImpl<Art::FillPr::SolidFill>::c_typeInfo)
      && (*(const int **)(v33 + 8) == &Ofc::TypeInfo::s_moduleTag
       || (unsigned int)__std_type_info_compare(*(_QWORD *)v33 + 8LL, &qword_180E14310)) )
    {
      if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::GradientFill>(v13) )
      {
        v110 = (const struct Art::GradientFillProps *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Gradient>(&v156);
        v111 = (Art *)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::GradientFill>(v13);
        Art::PropListToObj(v111, v110, v112);
      }
      else if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(v13) )
      {
        v95 = (const struct Art::BlipFillProps *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Blip>(&v156);
        v96 = (Art *)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::BlipFill>(v13);
        Art::PropListToObj(v96, v95, v97);
      }
      else if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::GroupFill>(v13) )
      {
        Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Group>(&v156);
      }
      else if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::PatternFill>(v13) )
      {
        v119 = (const struct Art::PatternFillProps *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Pattern>(&v156);
        v120 = (Art *)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::PatternFill>(v13);
        Art::PropListToObj(v120, v119, v121);
      }
      else
      {
        MsoShipAssertTagProc(506327500);
      }
      goto LABEL_47;
    }
    v8 = (__int64 *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::SolidColor>(&v156);
    v12 = Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::GetPtr<Art::FillPr::SolidFill>(v13);
    if ( !v12 )
    {
      Ofc::CInvalidParamException::ThrowTag(0x66356D62u);
LABEL_167:
      v115 = (Art::ExtendedColor *)Art::ExtendedColor::ExtendedColor(v115, (const struct Art::ExtendedColor *)&v138);
LABEL_141:
      Ofc::TOwnerPtr<Art::ExtendedColor>::Attach(v8 + 2, v115);
      if ( v138 )
        Mso::Memory::Free(v138, v116);
      goto LABEL_47;
    }
    if ( !Art::s_pHost )
    {
      CrashWithRecovery(0x1E44D300u, 0);
      goto LABEL_109;
    }
    v35 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
    v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 104LL))(v35);
    v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36);
    v38 = (_QWORD *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v12, 0);
    if ( v38 )
      v38 = (_QWORD *)*v38;
    if ( v38 )
      v37 = (__int64)v38;
    v40 = (Art::ExtendedColor *)v8[2];
    if ( v40 )
      Art::ExtendedColor::`scalar deleting destructor'(v40, v39);
    v8[2] = 0;
    v41 = 0;
    v138 = 0;
    v42 = *(_QWORD *)(v37 + 8);
    v139 = v42;
    if ( v42 <= 1 )
    {
      v43 = 0;
    }
    else
    {
      (*(void (__fastcall **)(Mso::Memory **, __int64))(v42 + 8))(&v138, v37);
      v43 = v139;
      v41 = v138;
    }
    v44 = (Mso::Memory *)*v8;
    *v8 = (__int64)v41;
    v138 = v44;
    v45 = v8[1];
    v8[1] = v43;
    v139 = v45;
    if ( v45 > 1 )
      (*(void (__fastcall **)(Mso::Memory **))(v45 + 16))(&v138);
    if ( *(_QWORD *)(v37 + 16) )
    {
      v139 = -1;
      v140 = -1;
      v141 = -1;
      v138 = 0;
      v142 = 0x20000000;
      Art::ExtendedColor::operator=(&v138);
      v115 = (Art::ExtendedColor *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v113, v114);
      if ( v115 )
        goto LABEL_167;
      goto LABEL_141;
    }
LABEL_47:
    if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 2) != 3 )
      goto LABEL_58;
    v46 = Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(a1);
    if ( !v46 )
      goto LABEL_49;
    v129 = *(__int64 **)(v46 + 8);
    if ( (unsigned __int64)v129 <= 1
      || (v130 = *v129, (struct Art::FillPr::NoFill **)v130 == &Ofc::TypeInfoImpl<Art::FillPr::NoFill>::c_typeInfo)
      || *(const int **)(v130 + 8) != &Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*(_QWORD *)v130 + 8LL, &qword_180E142E8) )
    {
LABEL_58:
      *((_BYTE *)a3 + 1) = 0;
    }
    v167 = 1;
    v51 = (Art *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 424LL))(v3);
    v52 = (Art *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 3);
    if ( v52 )
      v52 = *(Art **)v52;
    if ( v52 )
      v51 = v52;
    Art::PropListToObj(v51, (const struct Art::LineProps *)&v158, a3, v53);
    if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 4) == 3 )
    {
      v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 392LL))(v3);
      v55 = Ofc::TPropertySet<Art::EffectListIDs>::GetPtrIfValid<Art::EfPr::OuterShadow>(a1);
      if ( v55 )
        v54 = v55;
      v56 = v160;
      if ( !v160 )
      {
        Ofc::TOptional<Art::EffectProps>::CreateStorage(&v160);
        v56 = v160;
      }
      v57 = 0;
      v138 = 0;
      v58 = *(_QWORD *)(v54 + 8);
      v139 = v58;
      if ( v58 <= 1 )
      {
        v59 = 0;
      }
      else
      {
        (*(void (__fastcall **)(Mso::Memory **, __int64))(v58 + 8))(&v138, v54);
        v59 = v139;
        v57 = v138;
      }
      v60 = (Mso::Memory *)*v56;
      *v56 = (unsigned __int64)v57;
      v138 = v60;
      v61 = v56[1];
      v56[1] = v59;
      v139 = v61;
      if ( v61 > 1 )
        (*(void (__fastcall **)(Mso::Memory **))(v61 + 16))(&v138);
    }
    if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 5) == 3 )
    {
      v62 = Ofc::TPropertySet<Art::ShapePropsIDs>::GetPtrIfValid<Art::SpPr::Scene3D>(a1);
      if ( !v62 )
      {
LABEL_49:
        Ofc::CInvalidParamException::ThrowTag(0x66356C77u);
        continue;
      }
      v63 = Ofc::TOptional<Art::Scene3D>::EnsureStorage(&v161);
      Art::Scene3DData::operator=(v63, v62);
    }
    break;
  }
  if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 6) == 3 )
  {
    v117 = Ofc::TPropertySet<Art::ShapePropsIDs>::Get<Art::SpPr::Shape3D>(a1);
    v118 = Ofc::TOptional<Art::Shape3D>::EnsureStorage(&v162);
    Art::Shape3DData::operator=(v118, v117);
  }
  v64 = (int *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 384LL))(v3);
  v65 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 14);
  if ( v65 )
    v64 = (int *)v65;
  v164 = *v64;
  v66 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 432LL))(v3);
  v67 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 12);
  if ( v67 )
    v66 = (char *)v67;
  v165 = *v66;
  if ( (unsigned __int64)v157 > 1 )
  {
    v69 = (struct Art::Fill::Gradient **)*v157;
    if ( *v157 == (struct Art::Fill::None *)&Ofc::TypeInfoImpl<Art::Fill::Gradient>::c_typeInfo
      || v69[1] != (struct Art::Fill::Gradient *)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare((char *)*v69 + 8, &qword_180E1B560) )
    {
      if ( (unsigned __int64)v157 <= 1 )
        Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::DemandInit(&v156);
      v98 = v156;
      if ( v156
        && (unsigned __int8)Ofc::TChoice<Art::ShadeStyleDataChoiceIDsImpl>::Is<Art::ShadeStyleChoice::Path>((char *)v156 + 24) )
      {
        if ( *((_QWORD *)v98 + 4) <= 1u )
          Ofc::TChoice<Art::ShadeStyleDataChoiceIDsImpl>::DemandInit((char *)v98 + 24);
        v99 = *((_QWORD *)v98 + 3);
        if ( v99 )
        {
          if ( !*(_DWORD *)(v99 + 16) )
          {
            v166 = 1;
            if ( (unsigned __int8)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(&v154) )
            {
              v100 = *(_DWORD *)(Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Get<Art::Geom::Preset>(&v154) + 24);
              if ( v100 <= 162 )
              {
                if ( v100 == 162 )
                  goto LABEL_137;
                v122 = v100 - 42;
                if ( !v122 )
                  goto LABEL_173;
                v123 = v122 - 30;
                if ( !v123 )
                  goto LABEL_137;
                v124 = v123 - 4;
                if ( v124 && (v125 = v124 - 2) != 0 )
                {
                  v126 = v125 - 3;
                  if ( v126 )
                  {
                    v127 = v126 - 1;
                    if ( v127 )
                    {
                      v128 = v127 - 1;
                      if ( v128 )
                      {
                        v109 = v128 - 77;
                        v108 = v109 == 0;
                        goto LABEL_135;
                      }
                    }
                  }
LABEL_137:
                  *(_DWORD *)(v99 + 16) = 2;
                }
                else
                {
LABEL_173:
                  *(_DWORD *)(v99 + 16) = 1;
                }
              }
              else
              {
                v101 = v100 - 163;
                if ( !v101 )
                  goto LABEL_137;
                v102 = v101 - 1;
                if ( !v102 )
                  goto LABEL_137;
                v103 = v102 - 1;
                if ( !v103 )
                  goto LABEL_137;
                v104 = v103 - 1;
                if ( !v104 )
                  goto LABEL_137;
                v105 = v104 - 1;
                if ( !v105 )
                  goto LABEL_137;
                v106 = v105 - 1;
                if ( !v106 )
                  goto LABEL_137;
                v107 = v106 - 1;
                if ( !v107 )
                  goto LABEL_137;
                v109 = v107 - 1;
                v108 = v109 == 0;
LABEL_135:
                if ( v108 || v109 == 1 )
                  goto LABEL_137;
              }
            }
            else
            {
              v138 = (Mso::Memory *)(*(_QWORD *)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Get<Art::Geom::Custom>(&v154)
                                   + 176LL);
              v134 = 0;
              LODWORD(v139) = 0;
              LOBYTE(v135) = 0;
              while ( 1 )
              {
                v136 = ((__int64 (__fastcall *)(Mso::Memory **, void *, __int64, __int64))Art::Const_TableIter<Art::Path2DTable,Art::Path2D>::GetItem)(
                         &v138,
                         v68,
                         v134,
                         v135);
                v134 = (unsigned int)(v137 + 1);
                LODWORD(v139) = v134;
                if ( !v136 )
                  break;
                if ( *(_DWORD *)(v136 + 40) )
                {
                  if ( (_BYTE)v135 )
                    goto LABEL_173;
                  LOBYTE(v135) = 1;
                }
              }
            }
          }
        }
      }
    }
  }
  v71 = v145;
  v145 = *(_QWORD *)a2;
  *(_QWORD *)a2 = v71;
  v72 = v146;
  v146 = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a2 + 8) = v72;
  v73 = v147;
  v147 = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = v73;
  v74 = v148;
  v148 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)(a2 + 24) = v74;
  LODWORD(v74) = v149;
  v149 = *(_DWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 32) = v74;
  LOBYTE(v74) = v150;
  v150 = *(_BYTE *)(a2 + 36);
  *(_BYTE *)(a2 + 36) = v74;
  LOBYTE(v74) = v151;
  v151 = *(_BYTE *)(a2 + 37);
  *(_BYTE *)(a2 + 37) = v74;
  LODWORD(v74) = v152;
  LODWORD(v152) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a2 + 40) = v74;
  LODWORD(v74) = HIDWORD(v152);
  HIDWORD(v152) = *(_DWORD *)(a2 + 44);
  *(_DWORD *)(a2 + 44) = v74;
  LODWORD(v74) = v153;
  LODWORD(v153) = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a2 + 48) = v74;
  LODWORD(v74) = HIDWORD(v153);
  HIDWORD(v153) = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(a2 + 52) = v74;
  v75 = v154;
  v154 = *(Mso::Memory **)(a2 + 56);
  *(_QWORD *)(a2 + 56) = v75;
  v76 = v155;
  v155 = *(_QWORD *)(a2 + 64);
  *(_QWORD *)(a2 + 64) = v76;
  v77 = v156;
  v156 = *(Mso::Memory **)(a2 + 72);
  *(_QWORD *)(a2 + 72) = v77;
  v78 = v157;
  v157 = *(struct Art::Fill::None ***)(a2 + 80);
  *(_QWORD *)(a2 + 80) = v78;
  v79 = v158;
  v158 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v79;
  v80 = v159;
  v159 = *(_QWORD *)(a2 + 96);
  *(_QWORD *)(a2 + 96) = v80;
  v81 = v160;
  v160 = *(unsigned __int64 **)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v81;
  v82 = v161;
  v83 = *(Art::Scene3DData **)(a2 + 112);
  v161 = v83;
  *(_QWORD *)(a2 + 112) = v82;
  v84 = v162;
  v85 = *(Art::Shape3DData **)(a2 + 120);
  v162 = v85;
  *(_QWORD *)(a2 + 120) = v84;
  v86 = v163;
  v163 = *(Art::ShapeStyleData **)(a2 + 128);
  v87 = v163;
  *(_QWORD *)(a2 + 128) = v86;
  LODWORD(v81) = v164;
  v164 = *(_DWORD *)(a2 + 136);
  *(_DWORD *)(a2 + 136) = (_DWORD)v81;
  LOBYTE(v81) = v165;
  v165 = *(_BYTE *)(a2 + 140);
  *(_BYTE *)(a2 + 140) = (_BYTE)v81;
  v88 = v166;
  v166 = *(_BYTE *)(a2 + 141);
  *(_BYTE *)(a2 + 141) = v88;
  LOBYTE(v68) = v167;
  v167 = *(_BYTE *)(a2 + 142);
  *(_BYTE *)(a2 + 142) = (_BYTE)v68;
  if ( v87 )
  {
    Art::ShapeStyleData::~ShapeStyleData(v87);
    Mso::Memory::Free(v87, v89);
    v85 = v162;
    v83 = v161;
  }
  if ( v85 )
  {
    Art::Shape3DData::~Shape3DData(v85);
    Mso::Memory::Free(v85, v90);
    v83 = v161;
  }
  if ( v83 )
  {
    Art::Scene3DData::~Scene3DData(v83);
    Mso::Memory::Free(v83, v91);
  }
  v92 = (Mso::Memory *)v160;
  if ( v160 )
  {
    v93 = v160[1];
    if ( v93 > 1 )
      (*(void (__fastcall **)(unsigned __int64 *))(v93 + 16))(v160);
    Mso::Memory::Free(v92, v68);
  }
  if ( v159 > 1 )
    (*(void (__fastcall **)(__int64 *))(v159 + 16))(&v158);
  if ( (unsigned __int64)v157 > 1 )
    ((void (__fastcall *)(Mso::Memory **))v157[2])(&v156);
  result = v155;
  if ( v155 > 1 )
    return (*(__int64 (__fastcall **)(Mso::Memory **))(v155 + 16))(&v154);
  return result;
}

```

## disassembly

```asm
0x1800fcf60  mov     rax, rsp
0x1800fcf63  mov     [rax+8], rbx
0x1800fcf67  mov     [rax+10h], rsi
0x1800fcf6b  mov     [rax+18h], rdi
0x1800fcf6f  push    rbp
0x1800fcf70  push    r12
0x1800fcf72  push    r13
0x1800fcf74  push    r14
0x1800fcf76  push    r15
0x1800fcf78  lea     rbp, [rax-5Fh]
0x1800fcf7c  sub     rsp, 0F0h
0x1800fcf83  mov     r13, r8
0x1800fcf86  mov     r12, rdx
0x1800fcf89  mov     rsi, rcx
0x1800fcf8c  lea     rcx, [rbp+57h+var_B0]; this
0x1800fcf90  call    ??0ShapePropertyBag@Art@@QEAA@XZ; Art::ShapePropertyBag::ShapePropertyBag(void)
0x1800fcf95  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1800fcf9c  test    rcx, rcx
0x1800fcf9f  jz      loc_1800FD315
0x1800fcfa5  mov     rax, [rcx]
0x1800fcfa8  mov     rax, [rax+178h]
0x1800fcfaf  call    cs:__guard_dispatch_icall_fptr
0x1800fcfb5  mov     rdx, rax
0x1800fcfb8  mov     rcx, [rax]
0x1800fcfbb  mov     rax, [rcx+68h]
0x1800fcfbf  mov     rcx, rdx
0x1800fcfc2  call    cs:__guard_dispatch_icall_fptr
0x1800fcfc8  mov     r14, rax
0x1800fcfcb  mov     rcx, [rax]
0x1800fcfce  mov     rax, [rcx+1B8h]
0x1800fcfd5  mov     rcx, r14
0x1800fcfd8  call    cs:__guard_dispatch_icall_fptr
0x1800fcfde  mov     rbx, rax
0x1800fcfe1  xor     edx, edx
0x1800fcfe3  mov     rcx, rsi
0x1800fcfe6  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1800fcfeb  test    rax, rax
0x1800fcfee  jz      short loc_1800FCFF3
0x1800fcff0  mov     rax, [rax]
0x1800fcff3  test    rax, rax
0x1800fcff6  cmovnz  rbx, rax
0x1800fcffa  mov     r15, [rbx]
0x1800fcffd  mov     rdi, 0FFFFFFFF80000000h
0x1800fd004  mov     r9d, 7FFFFFFFh
0x1800fd00a  mov     r8b, cs:byte_180E14475
0x1800fd011  test    r8b, r8b
0x1800fd014  jz      loc_1800FD8AF
0x1800fd01a  cmp     r15, rdi
0x1800fd01d  jl      loc_1800FDB06
0x1800fd023  cmp     r15, r9
0x1800fd026  cmovg   r15, r9
0x1800fd02a  mov     rcx, [rbx+8]
0x1800fd02e  test    r8b, r8b
0x1800fd031  jz      loc_1800FD8BF
0x1800fd037  cmp     rcx, rdi
0x1800fd03a  jl      short loc_1800FD046
0x1800fd03c  mov     rdi, rcx
0x1800fd03f  cmp     rcx, r9
0x1800fd042  cmovg   rdi, r9
0x1800fd046  mov     rdx, [rbx+10h]
0x1800fd04a  mov     r8, [rbx+18h]
0x1800fd04e  mov     ecx, [rbx+20h]
0x1800fd051  mov     r9b, [rbx+24h]
0x1800fd055  mov     r10b, [rbx+25h]
0x1800fd059  mov     r11, [rbx+28h]
0x1800fd05d  mov     [rbp+57h+var_C8], r11
0x1800fd061  mov     rbx, [rbx+30h]
0x1800fd065  mov     [rbp+57h+var_C0], rbx
0x1800fd069  mov     [rbp+57h+var_B0], r15
0x1800fd06d  mov     [rbp+57h+var_A8], rdi
0x1800fd071  mov     [rbp+57h+var_A0], rdx
0x1800fd075  mov     [rbp+57h+var_98], r8
0x1800fd079  mov     [rbp+57h+var_90], ecx
0x1800fd07c  mov     [rbp+57h+var_8C], r9b
0x1800fd080  mov     [rbp+57h+var_8B], r10b
0x1800fd084  mov     eax, r11d
0x1800fd087  mov     dword ptr [rbp+57h+var_88], eax
0x1800fd08a  shr     r11, 20h
0x1800fd08e  mov     dword ptr [rbp+57h+var_88+4], r11d
0x1800fd092  mov     eax, ebx
0x1800fd094  mov     dword ptr [rbp+57h+var_80], ebx
0x1800fd097  shr     rbx, 20h
0x1800fd09b  mov     dword ptr [rbp+57h+var_80+4], ebx
0x1800fd09e  mov     rax, [r14]
0x1800fd0a1  mov     rcx, r14
0x1800fd0a4  mov     rax, [rax+198h]
0x1800fd0ab  call    cs:__guard_dispatch_icall_fptr
0x1800fd0b1  mov     rbx, rax
0x1800fd0b4  mov     edx, 1
0x1800fd0b9  mov     rcx, rsi
0x1800fd0bc  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1800fd0c1  test    rax, rax
0x1800fd0c4  jz      short loc_1800FD0C9
0x1800fd0c6  mov     rax, [rax]
0x1800fd0c9  test    rax, rax
0x1800fd0cc  cmovnz  rbx, rax
0x1800fd0d0  mov     [rbp+57h+var_23], 1
0x1800fd0d4  xor     ecx, ecx
0x1800fd0d6  mov     [rsp+110h+var_F0], rcx
0x1800fd0db  mov     rax, [rbx+8]
0x1800fd0df  mov     qword ptr [rsp+110h+var_E8], rax
0x1800fd0e4  cmp     rax, 1
0x1800fd0e8  jbe     loc_1800FD323
0x1800fd0ee  mov     rdx, rbx
0x1800fd0f1  lea     rcx, [rsp+110h+var_F0]
0x1800fd0f6  mov     rax, [rax+8]
0x1800fd0fa  call    cs:__guard_dispatch_icall_fptr
0x1800fd100  mov     rdx, qword ptr [rsp+110h+var_E8]
0x1800fd105  mov     rcx, [rsp+110h+var_F0]
0x1800fd10a  mov     rax, [rbp+57h+var_78]
0x1800fd10e  mov     [rbp+57h+var_78], rcx
0x1800fd112  mov     [rsp+110h+var_F0], rax
0x1800fd117  mov     rax, [rbp+57h+var_70]
0x1800fd11b  mov     [rbp+57h+var_70], rdx
0x1800fd11f  mov     qword ptr [rsp+110h+var_E8], rax
0x1800fd124  cmp     rax, 1
0x1800fd128  jbe     short loc_1800FD13A
0x1800fd12a  lea     rcx, [rsp+110h+var_F0]
0x1800fd12f  mov     rax, [rax+10h]
0x1800fd133  call    cs:__guard_dispatch_icall_fptr
0x1800fd139  nop
0x1800fd13a  mov     rax, [r14]
0x1800fd13d  mov     rcx, r14
0x1800fd140  mov     rax, [rax+190h]
0x1800fd147  call    cs:__guard_dispatch_icall_fptr
0x1800fd14d  mov     rdi, rax
0x1800fd150  mov     rcx, rsi
0x1800fd153  call    ??$GetPtrIfValid@UJoin@LnPr@Art@@@?$TPropertySet@VLinePropsIDs@Art@@@Ofc@@QEBAPEBVLineJoinProps@Art@@XZ; Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(void)
0x1800fd158  test    rax, rax
0x1800fd15b  cmovnz  rdi, rax
0x1800fd15f  mov     rcx, [rdi+8]
0x1800fd163  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UNoFill@FillPr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::FillPr::NoFill>::c_typeInfo
0x1800fd16a  lea     rbx, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x1800fd171  cmp     rcx, 1
0x1800fd175  jbe     loc_1800FD88C
0x1800fd17b  mov     rcx, [rcx]
0x1800fd17e  cmp     rcx, rax
0x1800fd181  jz      loc_1800FD88C
0x1800fd187  cmp     [rcx+8], rbx
0x1800fd18b  jnz     loc_1800FD870
0x1800fd191  xor     al, al
0x1800fd193  test    al, al
0x1800fd195  jnz     loc_1800FD32A
0x1800fd19b  mov     rcx, [rdi+8]
0x1800fd19f  cmp     rcx, 1
0x1800fd1a3  jbe     short loc_1800FD1C2
0x1800fd1a5  mov     rcx, [rcx]
0x1800fd1a8  lea     rax, ?c_typeInfo@?$TypeInfoImpl@USolidFill@FillPr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::FillPr::SolidFill>::c_typeInfo
0x1800fd1af  cmp     rcx, rax
0x1800fd1b2  jz      loc_1800FD8E8
0x1800fd1b8  cmp     [rcx+8], rbx
0x1800fd1bc  jnz     loc_1800FD8CC
0x1800fd1c2  xor     al, al
0x1800fd1c4  test    al, al
0x1800fd1c6  jz      loc_1800FD8EF
0x1800fd1cc  lea     rcx, [rbp+57h+var_68]
0x1800fd1d0  call    ??$SwitchTo@USolidColor@Fill@Art@@@?$TChoice@VFillStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVSolidColorFill@Art@@XZ; Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::SolidColor>(void)
0x1800fd1d5  mov     rbx, rax
0x1800fd1d8  mov     rcx, rdi
0x1800fd1db  call    ??$GetPtr@USolidFill@FillPr@Art@@@?$TChoice@VFillPropsDataChoiceIDsImpl@Art@@@Ofc@@QEAAPEAVSolidColorFillProps@Art@@XZ; Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::GetPtr<Art::FillPr::SolidFill>(void)
0x1800fd1e0  mov     r15, rax
0x1800fd1e3  test    rax, rax
0x1800fd1e6  jz      loc_1800FDBDB
0x1800fd1ec  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1800fd1f3  test    rcx, rcx
0x1800fd1f6  jz      loc_1800FD893
0x1800fd1fc  mov     rax, [rcx]
0x1800fd1ff  mov     rax, [rax+178h]
0x1800fd206  call    cs:__guard_dispatch_icall_fptr
0x1800fd20c  mov     rdx, rax
0x1800fd20f  mov     rcx, [rax]
0x1800fd212  mov     rax, [rcx+68h]
0x1800fd216  mov     rcx, rdx
0x1800fd219  call    cs:__guard_dispatch_icall_fptr
0x1800fd21f  mov     rdx, rax
0x1800fd222  mov     rcx, [rax]
0x1800fd225  mov     rax, [rcx+20h]
0x1800fd229  mov     rcx, rdx
0x1800fd22c  call    cs:__guard_dispatch_icall_fptr
0x1800fd232  mov     rdi, rax
0x1800fd235  xor     edx, edx
0x1800fd237  mov     rcx, r15
0x1800fd23a  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1800fd23f  test    rax, rax
0x1800fd242  jz      short loc_1800FD247
0x1800fd244  mov     rax, [rax]
0x1800fd247  test    rax, rax
0x1800fd24a  cmovnz  rdi, rax
0x1800fd24e  mov     rcx, [rbx+10h]; this
0x1800fd252  test    rcx, rcx
0x1800fd255  jnz     loc_1800FDAFC
0x1800fd25b  mov     qword ptr [rbx+10h], 0
0x1800fd263  xor     ecx, ecx
0x1800fd265  mov     [rsp+110h+var_F0], rcx
0x1800fd26a  mov     rax, [rdi+8]
0x1800fd26e  mov     qword ptr [rsp+110h+var_E8], rax
0x1800fd273  cmp     rax, 1
0x1800fd277  jbe     loc_1800FD9E9
0x1800fd27d  mov     rdx, rdi
0x1800fd280  lea     rcx, [rsp+110h+var_F0]
0x1800fd285  mov     rax, [rax+8]
0x1800fd289  call    cs:__guard_dispatch_icall_fptr
0x1800fd28f  mov     rdx, qword ptr [rsp+110h+var_E8]
0x1800fd294  mov     rcx, [rsp+110h+var_F0]
0x1800fd299  mov     rax, [rbx]
0x1800fd29c  mov     [rbx], rcx
0x1800fd29f  mov     [rsp+110h+var_F0], rax
0x1800fd2a4  mov     rax, [rbx+8]
0x1800fd2a8  mov     [rbx+8], rdx
0x1800fd2ac  mov     qword ptr [rsp+110h+var_E8], rax
0x1800fd2b1  cmp     rax, 1
0x1800fd2b5  jbe     short loc_1800FD2C7
0x1800fd2b7  lea     rcx, [rsp+110h+var_F0]
0x1800fd2bc  mov     rax, [rax+10h]
0x1800fd2c0  call    cs:__guard_dispatch_icall_fptr
0x1800fd2c6  nop
0x1800fd2c7  mov     rdx, [rdi+10h]
0x1800fd2cb  test    rdx, rdx
0x1800fd2ce  jnz     loc_1800FDA14
0x1800fd2d4  lea     rbx, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x1800fd2db  mov     r15d, 2
0x1800fd2e1  mov     edx, r15d
0x1800fd2e4  mov     rcx, rsi
0x1800fd2e7  call    ?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyState(uint)
0x1800fd2ec  cmp     rax, 3
0x1800fd2f0  jnz     loc_1800FD3B1
0x1800fd2f6  mov     rcx, rsi
0x1800fd2f9  call    ??$GetPtrIfValid@UJoin@LnPr@Art@@@?$TPropertySet@VLinePropsIDs@Art@@@Ofc@@QEBAPEBVLineJoinProps@Art@@XZ; Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(void)
0x1800fd2fe  test    rax, rax
0x1800fd301  jnz     loc_1800FDB5B
0x1800fd307  mov     ecx, 66356C77h; unsigned int
0x1800fd30c  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x1800fd311  nop
0x1800fd312  jmp     short $+2
0x1800fd314  nop
0x1800fd315  xor     edx, edx
0x1800fd317  mov     ecx, 1E44D300h
0x1800fd31c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800fd322  nop
0x1800fd323  xor     edx, edx
0x1800fd325  jmp     loc_1800FD10A
0x1800fd32a  lea     rcx, [rbp+57h+var_68]
0x1800fd32e  call    ??$GetPtr@UNone@Fill@Art@@@?$TChoice@VFillStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAAPEAVNoFill@Art@@XZ; Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::GetPtr<Art::Fill::None>(void)
0x1800fd333  mov     rbx, rax
0x1800fd336  test    rax, rax
0x1800fd339  jz      loc_1800FDBA5
0x1800fd33f  mov     rcx, rdi
0x1800fd342  call    ??$Get@UNoFill@FillPr@Art@@@?$TChoice@VFillPropsDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVNoFillProps@Art@@XZ; Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::NoFill>(void)
0x1800fd347  mov     r15, rax
0x1800fd34a  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1800fd351  test    rcx, rcx
0x1800fd354  jz      loc_1800FD8A1
0x1800fd35a  mov     rax, [rcx]
0x1800fd35d  mov     rax, [rax+178h]
0x1800fd364  call    cs:__guard_dispatch_icall_fptr
0x1800fd36a  mov     rdx, rax
0x1800fd36d  mov     rcx, [rax]
0x1800fd370  mov     rax, [rcx+68h]
0x1800fd374  mov     rcx, rdx
0x1800fd377  call    cs:__guard_dispatch_icall_fptr
0x1800fd37d  mov     rdx, rax
0x1800fd380  mov     rcx, [rax]
0x1800fd383  mov     rax, [rcx+80h]
0x1800fd38a  mov     rcx, rdx
0x1800fd38d  call    cs:__guard_dispatch_icall_fptr
0x1800fd393  mov     dil, al
0x1800fd396  lea     rcx, [r15+8]
0x1800fd39a  xor     edx, edx
0x1800fd39c  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1800fd3a1  test    rax, rax
0x1800fd3a4  jz      short loc_1800FD3A9
0x1800fd3a6  mov     dil, [rax]
0x1800fd3a9  mov     [rbx], dil
0x1800fd3ac  jmp     loc_1800FD2D4
0x1800fd3b1  mov     byte ptr [r13+1], 0
0x1800fd3b6  mov     [rbp+57h+var_22], 1
0x1800fd3ba  mov     rax, [r14]
0x1800fd3bd  mov     rcx, r14
0x1800fd3c0  mov     rax, [rax+1A8h]
0x1800fd3c7  call    cs:__guard_dispatch_icall_fptr
0x1800fd3cd  mov     rbx, rax
0x1800fd3d0  mov     edx, 3
0x1800fd3d5  mov     rcx, rsi
0x1800fd3d8  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1800fd3dd  test    rax, rax
0x1800fd3e0  jz      short loc_1800FD3E5
0x1800fd3e2  mov     rax, [rax]
0x1800fd3e5  test    rax, rax
0x1800fd3e8  cmovnz  rbx, rax
0x1800fd3ec  mov     r8, r13; struct Art::LineStyle *
0x1800fd3ef  lea     rdx, [rbp+57h+var_58]; struct Art::LineProps *
0x1800fd3f3  mov     rcx, rbx; this
0x1800fd3f6  call    ?PropListToObj@Art@@YAXAEBVLineProps@1@AEAVLineStyle@1@AEBUPropListConversionOptions@1@@Z; Art::PropListToObj(Art::LineProps const &,Art::LineStyle &,Art::PropListConversionOptions const &)
0x1800fd3fb  mov     edx, 4
0x1800fd400  mov     rcx, rsi
0x1800fd403  call    ?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyState(uint)
0x1800fd408  cmp     rax, 3
0x1800fd40c  jnz     loc_1800FD4B1
0x1800fd412  mov     rax, [r14]
0x1800fd415  mov     rcx, r14
  ... truncated ...
```
