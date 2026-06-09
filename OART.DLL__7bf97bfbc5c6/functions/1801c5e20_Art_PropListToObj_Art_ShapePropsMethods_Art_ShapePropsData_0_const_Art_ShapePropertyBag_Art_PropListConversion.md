# Art::PropListToObj(Art::ShapePropsMethods<Art::ShapePropsData_<0>> const &,Art::ShapePropertyBag &,Art::PropListConversionOptions &)

- ea: `0x1801c5e20`
- end: `0x1801c6b05`
- name: `?PropListToObj@Art@@YAXAEBV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@1@AEAVShapePropertyBag@1@AEAUPropListConversionOptions@1@@Z`
- size: `3301`
- prototype: ``
- caller_count: `19`
- callee_count: `51`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078b24`
- `0x1801323a0`
- `0x1801c7630`
- `0x180311b58`
- `0x18032e420`
- `0x18034ba30`
- `0x180389d20`
- `0x180395f00`
- `0x1803d6d48`
- `0x18043a21c`
- `0x1804fe020`
- `0x180531ba4`
- `0x18057ef50`
- `0x18058b960`
- `0x1805a47c0`
- `0x1805ad400`
- `0x180622244`
- `0x18062c120`
- `0x1806638c0`

## callees

- `0x180049050`
- `0x1800659a0`
- `0x180071720`
- `0x180079864`
- `0x1800902e8`
- `0x1800bac50`
- `0x180106328`
- `0x180135a08`
- `0x180161a60`
- `0x180162250`
- `0x1801629b0`
- `0x18017e418`
- `0x1801919d0`
- `0x1801a3fe0`
- `0x1801a4020`
- `0x1801a45b8`
- `0x1801c1810`
- `0x1801c2858`
- `0x1801c50f4`
- `0x1801c515c`
- `0x1801c51cc`
- `0x1801c520c`
- `0x1801c5e20`
- `0x1801c6b10`
- `0x1801c6c94`
- `0x1801c71d4`
- `0x1801c75d0`
- `0x1801c764c`
- `0x1801ca10c`
- `0x1801cb114`
- `0x1801d6240`
- `0x1801d6668`
- `0x1801d6738`
- `0x1801d78c8`
- `0x1801f628c`
- `0x1802070d4`
- `0x180207be0`
- `0x18020f254`
- `0x18020f330`
- `0x18020fd48`
- `0x180210700`
- `0x1803e882c`
- `0x1803ea0ec`
- `0x1804c39ac`
- `0x180512f20`
- `0x1805463b8`
- `0x18055f194`
- `0x1806a552c`
- `0x1806bc308`
- `0x1808a3ea0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6736`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6759`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6798`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6a44`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6736`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6759`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6798`
- `VCRUNTIME140!__std_type_info_compare` at `0x1801c6a44`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c69cc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801c69cc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c62e9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c6775`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c6783`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c62e9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c6775`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c6783`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6643`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6661`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6698`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6716`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6972`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6643`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6661`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6698`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6716`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801c6972`

## pseudocode

```c
__int64 __fastcall Art::PropListToObj(__int64 a1, __int64 a2, struct Art::LineStyle *a3)
{
  __int64 v3; // r15
  __int64 v7; // rax
  __int64 v8; // rbx
  _QWORD *PropertyStgType; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r14
  __int64 v13; // rdi
  __int64 v14; // r9
  signed __int64 v15; // rcx
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
  __int64 v28; // rdi
  __int64 v29; // rax
  __int64 *v30; // rcx
  int *v31; // rbx
  __int64 v32; // rcx
  __int64 *v34; // rcx
  __int64 v35; // rcx
  char v36; // al
  __int64 v37; // r14
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdi
  _QWORD *v41; // rax
  unsigned int v42; // edx
  Art::ExtendedColor *v43; // rcx
  Mso::Memory *v44; // rcx
  unsigned __int64 v45; // rax
  __int64 v46; // rdx
  Mso::Memory *v47; // rax
  unsigned __int64 v48; // rax
  Art *v49; // rbx
  __int64 v50; // rax
  const struct Art::PropListConversionOptions *v51; // r9
  __int64 v52; // rdi
  __int64 v53; // rax
  unsigned __int64 *v54; // rbx
  Mso::Memory *v55; // rcx
  unsigned __int64 v56; // rax
  __int64 v57; // rdx
  Mso::Memory *v58; // rax
  unsigned __int64 v59; // rax
  __int64 v60; // rbx
  _BYTE *v61; // r14
  __int64 v62; // rax
  __int64 v63; // rax
  char v64; // bl
  char *v65; // rax
  __int64 v66; // rax
  __int64 *v67; // rcx
  __int64 v68; // rcx
  int *v70; // rbx
  __int64 v71; // rax
  char *v72; // rbx
  __int64 v73; // rax
  void *v74; // rdx
  struct Art::Fill::Gradient **v75; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  Mso::Memory *v81; // rcx
  unsigned __int64 v82; // rcx
  __int64 v83; // rcx
  unsigned __int64 v84; // rcx
  __int64 v85; // rcx
  unsigned __int64 v86; // rcx
  unsigned __int64 *v87; // rcx
  Art::Scene3DData *v88; // rax
  Art::Scene3DData *v89; // rbx
  Art::Shape3DData *v90; // rax
  Art::Shape3DData *v91; // rdi
  Art::ShapeStyleData *v92; // rax
  Art::ShapeStyleData *v93; // rsi
  char v94; // dl
  void *v95; // rdx
  void *v96; // rdx
  Mso::Memory *v97; // rbx
  unsigned __int64 v98; // rax
  __int64 result; // rax
  void *v100; // rdx
  const struct Art::BlipFillProps *v101; // rbx
  Art *v102; // rax
  struct Art::BlipFill *v103; // r8
  __int64 v104; // rbx
  __int64 v105; // rbx
  int v106; // ecx
  int v107; // ecx
  int v108; // ecx
  int v109; // ecx
  int v110; // ecx
  int v111; // ecx
  int v112; // ecx
  int v113; // ecx
  bool v114; // zf
  int v115; // ecx
  const struct Art::GradientFillProps *v116; // rbx
  Art *v117; // rax
  struct Art::GradientFill *v118; // r8
  __int64 v119; // rbx
  __int64 v120; // rax
  unsigned __int64 v121; // rdx
  unsigned int v122; // r8d
  Art::ExtendedColor *v123; // rax
  void *v124; // rdx
  const struct Art::PatternFillProps *v125; // rbx
  Art *v126; // rax
  struct Art::PatternFill *v127; // r8
  int v128; // ecx
  int v129; // ecx
  int v130; // ecx
  int v131; // ecx
  int v132; // ecx
  int v133; // ecx
  int v134; // ecx
  __int64 v135; // rax
  __int64 v136; // r8
  __int64 v137; // r9
  __int64 v138; // rax
  int v139; // r8d
  Mso::Memory *v140; // [rsp+28h] [rbp-99h] BYREF
  __int64 v141; // [rsp+30h] [rbp-91h]
  int v142; // [rsp+38h] [rbp-89h]
  int v143; // [rsp+3Ch] [rbp-85h]
  int v144; // [rsp+40h] [rbp-81h]
  __int64 v145; // [rsp+50h] [rbp-71h]
  __int64 v146; // [rsp+58h] [rbp-69h]
  __int64 v147; // [rsp+68h] [rbp-59h] BYREF
  __int64 v148; // [rsp+70h] [rbp-51h]
  __int64 v149; // [rsp+78h] [rbp-49h]
  __int64 v150; // [rsp+80h] [rbp-41h]
  int v151; // [rsp+88h] [rbp-39h]
  char v152; // [rsp+8Ch] [rbp-35h]
  char v153; // [rsp+8Dh] [rbp-34h]
  __int64 v154; // [rsp+90h] [rbp-31h]
  __int64 v155; // [rsp+98h] [rbp-29h]
  Mso::Memory *v156; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int64 v157; // [rsp+A8h] [rbp-19h]
  __int64 v158; // [rsp+B0h] [rbp-11h] BYREF
  unsigned __int64 v159; // [rsp+B8h] [rbp-9h]
  __int64 v160; // [rsp+C0h] [rbp-1h] BYREF
  unsigned __int64 v161; // [rsp+C8h] [rbp+7h]
  unsigned __int64 *v162; // [rsp+D0h] [rbp+Fh] BYREF
  Art::Scene3DData *v163; // [rsp+D8h] [rbp+17h] BYREF
  Art::Shape3DData *v164; // [rsp+E0h] [rbp+1Fh] BYREF
  Art::ShapeStyleData *v165; // [rsp+E8h] [rbp+27h]
  int v166; // [rsp+F0h] [rbp+2Fh]
  char v167; // [rsp+F4h] [rbp+33h]
  char v168; // [rsp+F5h] [rbp+34h]
  char v169; // [rsp+F6h] [rbp+35h]

  Art::ShapePropertyBag::ShapePropertyBag((Art::ShapePropertyBag *)&v147);
  if ( Art::s_pHost )
  {
    v7 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 104LL))(v7);
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 440LL))(v3);
    PropertyStgType = (_QWORD *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 0);
    if ( PropertyStgType )
      PropertyStgType = (_QWORD *)*PropertyStgType;
    if ( PropertyStgType )
      v8 = (__int64)PropertyStgType;
    v12 = *(_QWORD *)v8;
    v13 = 0xFFFFFFFF80000000uLL;
    v14 = 0x7FFFFFFF;
    LOBYTE(v11) = byte_180E13688;
    if ( byte_180E13688 )
    {
      if ( v12 < (__int64)0xFFFFFFFF80000000uLL )
      {
        v12 = 0xFFFFFFFF80000000uLL;
      }
      else if ( v12 > 0x7FFFFFFF )
      {
        v12 = 0x7FFFFFFF;
      }
    }
    else
    {
      v12 = Ofc::TRangeRestricted<__int64,Art::CoordRange>::Pin(v12, v10, v11, 0x7FFFFFFF);
    }
    v15 = *(_QWORD *)(v8 + 8);
    if ( (_BYTE)v11 )
    {
      if ( v15 >= (__int64)0xFFFFFFFF80000000uLL )
      {
        v13 = *(_QWORD *)(v8 + 8);
        if ( v15 > v14 )
          v13 = v14;
      }
    }
    else
    {
      v13 = Ofc::TRangeRestricted<__int64,Art::CoordRange>::Pin(v15, v10, v11, v14);
    }
    v16 = *(_QWORD *)(v8 + 16);
    v17 = *(_QWORD *)(v8 + 24);
    v18 = *(_DWORD *)(v8 + 32);
    v19 = *(_BYTE *)(v8 + 36);
    v20 = *(_BYTE *)(v8 + 37);
    v145 = *(_QWORD *)(v8 + 40);
    v146 = *(_QWORD *)(v8 + 48);
    v147 = v12;
    v148 = v13;
    v149 = v16;
    v150 = v17;
    v151 = v18;
    v152 = v19;
    v153 = v20;
    v154 = v145;
    v155 = v146;
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 408LL))(v3);
    v22 = (_QWORD *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 1);
    if ( v22 )
      v22 = (_QWORD *)*v22;
    if ( v22 )
      v21 = (__int64)v22;
    v168 = 1;
    v23 = 0;
    v140 = 0;
    v24 = *(_QWORD *)(v21 + 8);
    v141 = v24;
    if ( v24 > 1 )
    {
      (*(void (__fastcall **)(Mso::Memory **, __int64))(v24 + 8))(&v140, v21);
      v25 = v141;
      v23 = v140;
      goto LABEL_20;
    }
    goto LABEL_65;
  }
  while ( 1 )
  {
    CrashWithRecovery(0x1E44D300u, 0);
LABEL_65:
    v25 = 0;
LABEL_20:
    v26 = v156;
    v156 = v23;
    v140 = v26;
    v27 = v157;
    v157 = v25;
    v141 = v27;
    if ( v27 > 1 )
      (*(void (__fastcall **)(Mso::Memory **))(v27 + 16))(&v140);
    v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 400LL))(v3);
    v29 = Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(a1);
    if ( v29 )
      v28 = v29;
    v30 = *(__int64 **)(v28 + 8);
    v31 = (int *)&Ofc::TypeInfo::s_moduleTag;
    if ( (unsigned __int64)v30 > 1 )
    {
      v32 = *v30;
      if ( (struct Art::FillPr::NoFill **)v32 != &Ofc::TypeInfoImpl<Art::FillPr::NoFill>::c_typeInfo
        && (*(const int **)(v32 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v32 + 8LL, &qword_180E139D0)) )
      {
        v34 = *(__int64 **)(v28 + 8);
        if ( (unsigned __int64)v34 > 1 )
        {
          v35 = *v34;
          if ( (struct Art::FillPr::SolidFill **)v35 == &Ofc::TypeInfoImpl<Art::FillPr::SolidFill>::c_typeInfo )
            goto LABEL_113;
          if ( *(const int **)(v35 + 8) != &Ofc::TypeInfo::s_moduleTag )
            goto LABEL_112;
        }
LABEL_32:
        v36 = 0;
        goto LABEL_33;
      }
    }
    v61 = (_BYTE *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::None>(&v158);
    v28 = Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::NoFill>(v28);
    if ( Art::s_pHost )
    {
      v62 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
      v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 104LL))(v62);
      v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 128LL))(v63);
      v65 = (char *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v28 + 8, 0);
      if ( v65 )
        v64 = *v65;
      *v61 = v64;
LABEL_47:
      v31 = (int *)&Ofc::TypeInfo::s_moduleTag;
    }
    else
    {
      while ( 1 )
      {
        CrashWithRecovery(0x1E44D300u, 0);
LABEL_112:
        if ( (unsigned int)__std_type_info_compare(*(_QWORD *)v35 + 8LL, &qword_180E139F8) )
          goto LABEL_32;
LABEL_113:
        v36 = 1;
LABEL_33:
        if ( !v36 )
          break;
        v31 = (int *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::SolidColor>(&v158);
        v37 = Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::GetPtr<Art::FillPr::SolidFill>(v28);
        if ( !v37 )
        {
          Ofc::CInvalidParamException::ThrowTag(0x66356D62u);
          goto LABEL_163;
        }
        if ( Art::s_pHost )
        {
          v38 = (*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)Art::s_pHost + 376LL))(Art::s_pHost);
          v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 104LL))(v38);
          v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39);
          v41 = (_QWORD *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v37, 0);
          if ( v41 )
            v41 = (_QWORD *)*v41;
          if ( v41 )
            v40 = (__int64)v41;
          v43 = (Art::ExtendedColor *)*((_QWORD *)v31 + 2);
          if ( v43 )
            Art::ExtendedColor::`scalar deleting destructor'(v43, v42);
          *((_QWORD *)v31 + 2) = 0;
          v44 = 0;
          v140 = 0;
          v45 = *(_QWORD *)(v40 + 8);
          v141 = v45;
          if ( v45 <= 1 )
          {
            v46 = 0;
          }
          else
          {
            (*(void (__fastcall **)(Mso::Memory **, __int64))(v45 + 8))(&v140, v40);
            v46 = v141;
            v44 = v140;
          }
          v47 = *(Mso::Memory **)v31;
          *(_QWORD *)v31 = v44;
          v140 = v47;
          v48 = *((_QWORD *)v31 + 1);
          *((_QWORD *)v31 + 1) = v46;
          v141 = v48;
          if ( v48 > 1 )
            (*(void (__fastcall **)(Mso::Memory **))(v48 + 16))(&v140);
          if ( !*(_QWORD *)(v40 + 16) )
            goto LABEL_47;
          v141 = -1;
          v142 = -1;
          v143 = -1;
          v140 = 0;
          v144 = 0x20000000;
          Art::ExtendedColor::operator=(&v140);
          v123 = (Art::ExtendedColor *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v121, v122);
          if ( !v123 )
          {
LABEL_143:
            Ofc::TOwnerPtr<Art::ExtendedColor>::Attach(v31 + 4, v123);
            if ( v140 )
              Mso::Memory::Free(v140, v124);
            goto LABEL_47;
          }
LABEL_163:
          v123 = (Art::ExtendedColor *)Art::ExtendedColor::ExtendedColor(v123, (const struct Art::ExtendedColor *)&v140);
          goto LABEL_143;
        }
        CrashWithRecovery(0x1E44D300u, 0);
      }
      if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::GradientFill>(v28) )
      {
        v116 = (const struct Art::GradientFillProps *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Gradient>(&v158);
        v117 = (Art *)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::GradientFill>(v28);
        Art::PropListToObj(v117, v116, v118);
        goto LABEL_47;
      }
      if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(v28) )
      {
        v101 = (const struct Art::BlipFillProps *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Blip>(&v158);
        v102 = (Art *)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::BlipFill>(v28);
        Art::PropListToObj(v102, v101, v103);
        goto LABEL_47;
      }
      if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::GroupFill>(v28) )
      {
        Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Group>(&v158);
        goto LABEL_48;
      }
      if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::PatternFill>(v28) )
      {
        v125 = (const struct Art::PatternFillProps *)Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::Pattern>(&v158);
        v126 = (Art *)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Get<Art::FillPr::PatternFill>(v28);
        Art::PropListToObj(v126, v125, v127);
        goto LABEL_47;
      }
      MsoShipAssertTagProc(506327500);
    }
LABEL_48:
    if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 2) != 3 )
      goto LABEL_49;
    v66 = Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(a1);
    if ( !v66 )
      goto LABEL_63;
    v67 = *(__int64 **)(v66 + 8);
    if ( (unsigned __int64)v67 <= 1
      || (v68 = *v67, (struct Art::FillPr::NoFill **)v68 == &Ofc::TypeInfoImpl<Art::FillPr::NoFill>::c_typeInfo)
      || *(int **)(v68 + 8) != v31 && !(unsigned int)__std_type_info_compare(*(_QWORD *)v68 + 8LL, &qword_180E139D0) )
    {
LABEL_49:
      *((_BYTE *)a3 + 1) = 0;
    }
    v169 = 1;
    v49 = (Art *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 424LL))(v3);
    v50 = Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Highlight>(a1);
    if ( v50 )
      v49 = (Art *)v50;
    Art::PropListToObj(v49, (const struct Art::LineProps *)&v160, a3, v51);
    if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 4) == 3 )
    {
      v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 392LL))(v3);
      v53 = Ofc::TPropertySet<Art::EffectListIDs>::GetPtrIfValid<Art::EfPr::OuterShadow>(a1);
      if ( v53 )
        v52 = v53;
      v54 = v162;
      if ( !v162 )
      {
        Ofc::TOptional<Art::EffectProps>::CreateStorage(&v162);
        v54 = v162;
      }
      v55 = 0;
      v140 = 0;
      v56 = *(_QWORD *)(v52 + 8);
      v141 = v56;
      if ( v56 <= 1 )
      {
        v57 = 0;
      }
      else
      {
        (*(void (__fastcall **)(Mso::Memory **, __int64))(v56 + 8))(&v140, v52);
        v57 = v141;
        v55 = v140;
      }
      v58 = (Mso::Memory *)*v54;
      *v54 = (unsigned __int64)v55;
      v140 = v58;
      v59 = v54[1];
      v54[1] = v57;
      v141 = v59;
      if ( v59 > 1 )
        (*(void (__fastcall **)(Mso::Memory **))(v59 + 16))(&v140);
    }
    if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 5) != 3 )
      goto LABEL_77;
    v60 = Ofc::TPropertySet<Art::ShapePropsIDs>::GetPtrIfValid<Art::SpPr::Scene3D>(a1);
    if ( v60 )
      break;
LABEL_63:
    Ofc::CInvalidParamException::ThrowTag(0x66356C77u);
  }
  v135 = Ofc::TOptional<Art::Scene3D>::EnsureStorage(&v163);
  Art::Scene3DData::operator=(v135, v60);
LABEL_77:
  if ( Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 6) == 3 )
  {
    v119 = Ofc::TPropertySet<Art::ShapePropsIDs>::Get<Art::SpPr::Shape3D>(a1);
    v120 = Ofc::TOptional<Art::Shape3D>::EnsureStorage(&v164);
    Art::Shape3DData::operator=(v120, v119);
  }
  v70 = (int *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 384LL))(v3);
  v71 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 14);
  if ( v71 )
    v70 = (int *)v71;
  v166 = *v70;
  v72 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 432LL))(v3);
  v73 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 12);
  if ( v73 )
    v72 = (char *)v73;
  v167 = *v72;
  if ( v159 > 1 )
  {
    v75 = *(struct Art::Fill::Gradient ***)v159;
    if ( *(struct Art::Fill::Gradient ***)v159 == &Ofc::TypeInfoImpl<Art::Fill::Gradient>::c_typeInfo
      || v75[1] != (struct Art::Fill::Gradient *)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare((char *)*v75 + 8, &qword_180E1AB60) )
    {
      if ( v159 <= 1 )
        Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::DemandInit(&v158);
      v104 = v158;
      if ( v158
        && (unsigned __int8)Ofc::TChoice<Art::ShadeStyleDataChoiceIDsImpl>::Is<Art::ShadeStyleChoice::Path>(v158 + 24) )
      {
        if ( *(_QWORD *)(v104 + 32) <= 1u )
          Ofc::TChoice<Art::ShadeStyleDataChoiceIDsImpl>::DemandInit(v104 + 24);
        v105 = *(_QWORD *)(v104 + 24);
        if ( v105 )
        {
          if ( !*(_DWORD *)(v105 + 16) )
          {
            v168 = 1;
            if ( (unsigned __int8)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(&v156) )
            {
              v106 = *(_DWORD *)(Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Get<Art::Geom::Preset>(&v156) + 24);
              if ( v106 <= 162 )
              {
                if ( v106 == 162 )
                  goto LABEL_139;
                v128 = v106 - 42;
                if ( !v128 )
                  goto LABEL_170;
                v129 = v128 - 30;
                if ( !v129 )
                  goto LABEL_139;
                v130 = v129 - 4;
                if ( v130 && (v131 = v130 - 2) != 0 )
                {
                  v132 = v131 - 3;
                  if ( v132 )
                  {
                    v133 = v132 - 1;
                    if ( v133 )
                    {
                      v134 = v133 - 1;
                      if ( v134 )
                      {
                        v115 = v134 - 77;
                        v114 = v115 == 0;
                        goto LABEL_137;
                      }
                    }
                  }
LABEL_139:
                  *(_DWORD *)(v105 + 16) = 2;
                }
                else
                {
LABEL_170:
                  *(_DWORD *)(v105 + 16) = 1;
                }
              }
              else
              {
                v107 = v106 - 163;
                if ( !v107 )
                  goto LABEL_139;
                v108 = v107 - 1;
                if ( !v108 )
                  goto LABEL_139;
                v109 = v108 - 1;
                if ( !v109 )
                  goto LABEL_139;
                v110 = v109 - 1;
                if ( !v110 )
                  goto LABEL_139;
                v111 = v110 - 1;
                if ( !v111 )
                  goto LABEL_139;
                v112 = v111 - 1;
                if ( !v112 )
                  goto LABEL_139;
                v113 = v112 - 1;
                if ( !v113 )
                  goto LABEL_139;
                v115 = v113 - 1;
                v114 = v115 == 0;
LABEL_137:
                if ( v114 || v115 == 1 )
                  goto LABEL_139;
              }
            }
            else
            {
              v140 = (Mso::Memory *)(*(_QWORD *)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Get<Art::Geom::Custom>(&v156)
                                   + 176LL);
              v136 = 0;
              LODWORD(v141) = 0;
              LOBYTE(v137) = 0;
              while ( 1 )
              {
                v138 = ((__int64 (__fastcall *)(Mso::Memory **, void *, __int64, __int64))Art::Const_TableIter<Art::Path2DTable,Art::Path2D>::GetItem)(
                         &v140,
                         v74,
                         v136,
                         v137);
                v136 = (unsigned int)(v139 + 1);
                LODWORD(v141) = v136;
                if ( !v138 )
                  break;
                if ( *(_DWORD *)(v138 + 40) )
                {
                  if ( (_BYTE)v137 )
                    goto LABEL_170;
                  LOBYTE(v137) = 1;
                }
              }
            }
          }
        }
      }
    }
  }
  v77 = v147;
  v147 = *(_QWORD *)a2;
  *(_QWORD *)a2 = v77;
  v78 = v148;
  v148 = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a2 + 8) = v78;
  v79 = v149;
  v149 = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = v79;
  v80 = v150;
  v150 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)(a2 + 24) = v80;
  LODWORD(v80) = v151;
  v151 = *(_DWORD *)(a2 + 32);
  *(_DWORD *)(a2 + 32) = v80;
  LOBYTE(v80) = v152;
  v152 = *(_BYTE *)(a2 + 36);
  *(_BYTE *)(a2 + 36) = v80;
  LOBYTE(v80) = v153;
  v153 = *(_BYTE *)(a2 + 37);
  *(_BYTE *)(a2 + 37) = v80;
  LODWORD(v80) = v154;
  LODWORD(v154) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a2 + 40) = v80;
  LODWORD(v80) = HIDWORD(v154);
  HIDWORD(v154) = *(_DWORD *)(a2 + 44);
  *(_DWORD *)(a2 + 44) = v80;
  LODWORD(v80) = v155;
  LODWORD(v155) = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a2 + 48) = v80;
  LODWORD(v80) = HIDWORD(v155);
  HIDWORD(v155) = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(a2 + 52) = v80;
  v81 = v156;
  v156 = *(Mso::Memory **)(a2 + 56);
  *(_QWORD *)(a2 + 56) = v81;
  v82 = v157;
  v157 = *(_QWORD *)(a2 + 64);
  *(_QWORD *)(a2 + 64) = v82;
  v83 = v158;
  v158 = *(_QWORD *)(a2 + 72);
  *(_QWORD *)(a2 + 72) = v83;
  v84 = v159;
  v159 = *(_QWORD *)(a2 + 80);
  *(_QWORD *)(a2 + 80) = v84;
  v85 = v160;
  v160 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v85;
  v86 = v161;
  v161 = *(_QWORD *)(a2 + 96);
  *(_QWORD *)(a2 + 96) = v86;
  v87 = v162;
  v162 = *(unsigned __int64 **)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v87;
  v88 = v163;
  v89 = *(Art::Scene3DData **)(a2 + 112);
  v163 = v89;
  *(_QWORD *)(a2 + 112) = v88;
  v90 = v164;
  v91 = *(Art::Shape3DData **)(a2 + 120);
  v164 = v91;
  *(_QWORD *)(a2 + 120) = v90;
  v92 = v165;
  v165 = *(Art::ShapeStyleData **)(a2 + 128);
  v93 = v165;
  *(_QWORD *)(a2 + 128) = v92;
  LODWORD(v87) = v166;
  v166 = *(_DWORD *)(a2 + 136);
  *(_DWORD *)(a2 + 136) = (_DWORD)v87;
  LOBYTE(v87) = v167;
  v167 = *(_BYTE *)(a2 + 140);
  *(_BYTE *)(a2 + 140) = (_BYTE)v87;
  v94 = v168;
  v168 = *(_BYTE *)(a2 + 141);
  *(_BYTE *)(a2 + 141) = v94;
  LOBYTE(v74) = v169;
  v169 = *(_BYTE *)(a2 + 142);
  *(_BYTE *)(a2 + 142) = (_BYTE)v74;
  if ( v93 )
  {
    Art::ShapeStyleData::~ShapeStyleData(v93);
    Mso::Memory::Free(v93, v95);
    v91 = v164;
    v89 = v163;
  }
  if ( v91 )
  {
    Art::Shape3DData::~Shape3DData(v91);
    Mso::Memory::Free(v91, v96);
    v89 = v163;
  }
  if ( v89 )
  {
    Art::Scene3DData::~Scene3DData(v89);
    Mso::Memory::Free(v89, v100);
  }
  v97 = (Mso::Memory *)v162;
  if ( v162 )
  {
    v98 = v162[1];
    if ( v98 > 1 )
      (*(void (__fastcall **)(unsigned __int64 *))(v98 + 16))(v162);
    Mso::Memory::Free(v97, v74);
  }
  if ( v161 > 1 )
    (*(void (__fastcall **)(__int64 *))(v161 + 16))(&v160);
  if ( v159 > 1 )
    (*(void (__fastcall **)(__int64 *))(v159 + 16))(&v158);
  result = v157;
  if ( v157 > 1 )
    return (*(__int64 (__fastcall **)(Mso::Memory **))(v157 + 16))(&v156);
  return result;
}

```

## disassembly

```asm
0x1801c5e20  mov     rax, rsp
0x1801c5e23  mov     [rax+8], rbx
0x1801c5e27  mov     [rax+10h], rsi
0x1801c5e2b  mov     [rax+18h], rdi
0x1801c5e2f  push    rbp
0x1801c5e30  push    r12
0x1801c5e32  push    r13
0x1801c5e34  push    r14
0x1801c5e36  push    r15
0x1801c5e38  lea     rbp, [rax-5Fh]
0x1801c5e3c  sub     rsp, 0F0h
0x1801c5e43  mov     r13, r8
0x1801c5e46  mov     r12, rdx
0x1801c5e49  mov     rsi, rcx
0x1801c5e4c  lea     rcx, [rbp+57h+var_B0]; this
0x1801c5e50  call    ??0ShapePropertyBag@Art@@QEAA@XZ; Art::ShapePropertyBag::ShapePropertyBag(void)
0x1801c5e55  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1801c5e5c  test    rcx, rcx
0x1801c5e5f  jz      loc_1801C62E2
0x1801c5e65  mov     rax, [rcx]
0x1801c5e68  mov     rax, [rax+178h]
0x1801c5e6f  call    cs:__guard_dispatch_icall_fptr
0x1801c5e75  mov     rdx, rax
0x1801c5e78  mov     rcx, [rax]
0x1801c5e7b  mov     rax, [rcx+68h]
0x1801c5e7f  mov     rcx, rdx
0x1801c5e82  call    cs:__guard_dispatch_icall_fptr
0x1801c5e88  mov     r15, rax
0x1801c5e8b  mov     rcx, [rax]
0x1801c5e8e  mov     rax, [rcx+1B8h]
0x1801c5e95  mov     rcx, r15
0x1801c5e98  call    cs:__guard_dispatch_icall_fptr
0x1801c5e9e  mov     rbx, rax
0x1801c5ea1  xor     edx, edx
0x1801c5ea3  mov     rcx, rsi
0x1801c5ea6  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c5eab  test    rax, rax
0x1801c5eae  jz      short loc_1801C5EB3
0x1801c5eb0  mov     rax, [rax]
0x1801c5eb3  test    rax, rax
0x1801c5eb6  cmovnz  rbx, rax
0x1801c5eba  mov     r14, [rbx]
0x1801c5ebd  mov     rdi, 0FFFFFFFF80000000h
0x1801c5ec4  mov     r9d, 7FFFFFFFh
0x1801c5eca  mov     r8b, cs:byte_180E13688
0x1801c5ed1  test    r8b, r8b
0x1801c5ed4  jz      loc_1801C67AD
0x1801c5eda  cmp     r14, rdi
0x1801c5edd  jl      loc_1801C69E1
0x1801c5ee3  cmp     r14, r9
0x1801c5ee6  cmovg   r14, r9
0x1801c5eea  mov     rcx, [rbx+8]
0x1801c5eee  test    r8b, r8b
0x1801c5ef1  jz      loc_1801C67BD
0x1801c5ef7  cmp     rcx, rdi
0x1801c5efa  jl      short loc_1801C5F06
0x1801c5efc  mov     rdi, rcx
0x1801c5eff  cmp     rcx, r9
0x1801c5f02  cmovg   rdi, r9
0x1801c5f06  mov     rdx, [rbx+10h]
0x1801c5f0a  mov     r8, [rbx+18h]
0x1801c5f0e  mov     ecx, [rbx+20h]
0x1801c5f11  mov     r9b, [rbx+24h]
0x1801c5f15  mov     r10b, [rbx+25h]
0x1801c5f19  mov     r11, [rbx+28h]
0x1801c5f1d  mov     [rbp+57h+var_C8], r11
0x1801c5f21  mov     rbx, [rbx+30h]
0x1801c5f25  mov     [rbp+57h+var_C0], rbx
0x1801c5f29  mov     [rbp+57h+var_B0], r14
0x1801c5f2d  mov     [rbp+57h+var_A8], rdi
0x1801c5f31  mov     [rbp+57h+var_A0], rdx
0x1801c5f35  mov     [rbp+57h+var_98], r8
0x1801c5f39  mov     [rbp+57h+var_90], ecx
0x1801c5f3c  mov     [rbp+57h+var_8C], r9b
0x1801c5f40  mov     [rbp+57h+var_8B], r10b
0x1801c5f44  mov     eax, r11d
0x1801c5f47  mov     dword ptr [rbp+57h+var_88], eax
0x1801c5f4a  shr     r11, 20h
0x1801c5f4e  mov     dword ptr [rbp+57h+var_88+4], r11d
0x1801c5f52  mov     eax, ebx
0x1801c5f54  mov     dword ptr [rbp+57h+var_80], ebx
0x1801c5f57  shr     rbx, 20h
0x1801c5f5b  mov     dword ptr [rbp+57h+var_80+4], ebx
0x1801c5f5e  mov     rax, [r15]
0x1801c5f61  mov     rcx, r15
0x1801c5f64  mov     rax, [rax+198h]
0x1801c5f6b  call    cs:__guard_dispatch_icall_fptr
0x1801c5f71  mov     rbx, rax
0x1801c5f74  mov     edx, 1
0x1801c5f79  mov     rcx, rsi
0x1801c5f7c  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c5f81  test    rax, rax
0x1801c5f84  jz      short loc_1801C5F89
0x1801c5f86  mov     rax, [rax]
0x1801c5f89  test    rax, rax
0x1801c5f8c  cmovnz  rbx, rax
0x1801c5f90  mov     [rbp+57h+var_23], 1
0x1801c5f94  xor     ecx, ecx
0x1801c5f96  mov     [rsp+110h+var_F0], rcx
0x1801c5f9b  mov     rax, [rbx+8]
0x1801c5f9f  mov     qword ptr [rsp+110h+var_E8], rax
0x1801c5fa4  cmp     rax, 1
0x1801c5fa8  jbe     loc_1801C62F0
0x1801c5fae  mov     rdx, rbx
0x1801c5fb1  lea     rcx, [rsp+110h+var_F0]
0x1801c5fb6  mov     rax, [rax+8]
0x1801c5fba  call    cs:__guard_dispatch_icall_fptr
0x1801c5fc0  mov     rdx, qword ptr [rsp+110h+var_E8]
0x1801c5fc5  mov     rcx, [rsp+110h+var_F0]
0x1801c5fca  mov     rax, [rbp+57h+var_78]
0x1801c5fce  mov     [rbp+57h+var_78], rcx
0x1801c5fd2  mov     [rsp+110h+var_F0], rax
0x1801c5fd7  mov     rax, [rbp+57h+var_70]
0x1801c5fdb  mov     [rbp+57h+var_70], rdx
0x1801c5fdf  mov     qword ptr [rsp+110h+var_E8], rax
0x1801c5fe4  cmp     rax, 1
0x1801c5fe8  jbe     short loc_1801C5FFA
0x1801c5fea  lea     rcx, [rsp+110h+var_F0]
0x1801c5fef  mov     rax, [rax+10h]
0x1801c5ff3  call    cs:__guard_dispatch_icall_fptr
0x1801c5ff9  nop
0x1801c5ffa  mov     rax, [r15]
0x1801c5ffd  mov     rcx, r15
0x1801c6000  mov     rax, [rax+190h]
0x1801c6007  call    cs:__guard_dispatch_icall_fptr
0x1801c600d  mov     rdi, rax
0x1801c6010  mov     rcx, rsi
0x1801c6013  call    ??$GetPtrIfValid@UJoin@LnPr@Art@@@?$TPropertySet@VLinePropsIDs@Art@@@Ofc@@QEBAPEBVLineJoinProps@Art@@XZ; Ofc::TPropertySet<Art::LinePropsIDs>::GetPtrIfValid<Art::LnPr::Join>(void)
0x1801c6018  test    rax, rax
0x1801c601b  cmovnz  rdi, rax
0x1801c601f  mov     rcx, [rdi+8]
0x1801c6023  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UNoFill@FillPr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::FillPr::NoFill>::c_typeInfo
0x1801c602a  lea     rbx, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x1801c6031  cmp     rcx, 1
0x1801c6035  jbe     loc_1801C6767
0x1801c603b  mov     rcx, [rcx]
0x1801c603e  cmp     rcx, rax
0x1801c6041  jz      loc_1801C6767
0x1801c6047  cmp     [rcx+8], rbx
0x1801c604b  jnz     loc_1801C674B
0x1801c6051  xor     al, al
0x1801c6053  test    al, al
0x1801c6055  jnz     loc_1801C62F7
0x1801c605b  mov     rcx, [rdi+8]
0x1801c605f  cmp     rcx, 1
0x1801c6063  jbe     short loc_1801C6082
0x1801c6065  mov     rcx, [rcx]
0x1801c6068  lea     rax, ?c_typeInfo@?$TypeInfoImpl@USolidFill@FillPr@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::FillPr::SolidFill>::c_typeInfo
0x1801c606f  cmp     rcx, rax
0x1801c6072  jz      loc_1801C67A6
0x1801c6078  cmp     [rcx+8], rbx
0x1801c607c  jnz     loc_1801C678A
0x1801c6082  xor     al, al
0x1801c6084  test    al, al
0x1801c6086  jz      loc_1801C67CA
0x1801c608c  lea     rcx, [rbp+57h+var_68]
0x1801c6090  call    ??$SwitchTo@USolidColor@Fill@Art@@@?$TChoice@VFillStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAAAEAVSolidColorFill@Art@@XZ; Ofc::TChoice<Art::FillStyleDataChoiceIDsImpl>::SwitchTo<Art::Fill::SolidColor>(void)
0x1801c6095  mov     rbx, rax
0x1801c6098  mov     rcx, rdi
0x1801c609b  call    ??$GetPtr@USolidFill@FillPr@Art@@@?$TChoice@VFillPropsDataChoiceIDsImpl@Art@@@Ofc@@QEAAPEAVSolidColorFillProps@Art@@XZ; Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::GetPtr<Art::FillPr::SolidFill>(void)
0x1801c60a0  mov     r14, rax
0x1801c60a3  test    rax, rax
0x1801c60a6  jz      loc_1801C6A59
0x1801c60ac  mov     rcx, cs:?s_pHost@Art@@3PEAVIAppHost@1@EA; Art::IAppHost * Art::s_pHost
0x1801c60b3  test    rcx, rcx
0x1801c60b6  jz      loc_1801C676E
0x1801c60bc  mov     rax, [rcx]
0x1801c60bf  mov     rax, [rax+178h]
0x1801c60c6  call    cs:__guard_dispatch_icall_fptr
0x1801c60cc  mov     rdx, rax
0x1801c60cf  mov     rcx, [rax]
0x1801c60d2  mov     rax, [rcx+68h]
0x1801c60d6  mov     rcx, rdx
0x1801c60d9  call    cs:__guard_dispatch_icall_fptr
0x1801c60df  mov     rdx, rax
0x1801c60e2  mov     rcx, [rax]
0x1801c60e5  mov     rax, [rcx+20h]
0x1801c60e9  mov     rcx, rdx
0x1801c60ec  call    cs:__guard_dispatch_icall_fptr
0x1801c60f2  mov     rdi, rax
0x1801c60f5  xor     edx, edx
0x1801c60f7  mov     rcx, r14
0x1801c60fa  call    ?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1801c60ff  test    rax, rax
0x1801c6102  jz      short loc_1801C6107
0x1801c6104  mov     rax, [rax]
0x1801c6107  test    rax, rax
0x1801c610a  cmovnz  rdi, rax
0x1801c610e  mov     rcx, [rbx+10h]; this
0x1801c6112  test    rcx, rcx
0x1801c6115  jnz     loc_1801C69D7
0x1801c611b  mov     qword ptr [rbx+10h], 0
0x1801c6123  xor     ecx, ecx
0x1801c6125  mov     [rsp+110h+var_F0], rcx
0x1801c612a  mov     rax, [rdi+8]
0x1801c612e  mov     qword ptr [rsp+110h+var_E8], rax
0x1801c6133  cmp     rax, 1
0x1801c6137  jbe     loc_1801C68E8
0x1801c613d  mov     rdx, rdi
0x1801c6140  lea     rcx, [rsp+110h+var_F0]
0x1801c6145  mov     rax, [rax+8]
0x1801c6149  call    cs:__guard_dispatch_icall_fptr
0x1801c614f  mov     rdx, qword ptr [rsp+110h+var_E8]
0x1801c6154  mov     rcx, [rsp+110h+var_F0]
0x1801c6159  mov     rax, [rbx]
0x1801c615c  mov     [rbx], rcx
0x1801c615f  mov     [rsp+110h+var_F0], rax
0x1801c6164  mov     rax, [rbx+8]
0x1801c6168  mov     [rbx+8], rdx
0x1801c616c  mov     qword ptr [rsp+110h+var_E8], rax
0x1801c6171  cmp     rax, 1
0x1801c6175  jbe     short loc_1801C6187
0x1801c6177  lea     rcx, [rsp+110h+var_F0]
0x1801c617c  mov     rax, [rax+10h]
0x1801c6180  call    cs:__guard_dispatch_icall_fptr
0x1801c6186  nop
0x1801c6187  mov     rdx, [rdi+10h]
0x1801c618b  test    rdx, rdx
0x1801c618e  jnz     loc_1801C6913
0x1801c6194  lea     rbx, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x1801c619b  mov     r14d, 2
0x1801c61a1  mov     edx, r14d
0x1801c61a4  mov     rcx, rsi
0x1801c61a7  call    ?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyState(uint)
0x1801c61ac  cmp     rax, 3
0x1801c61b0  jz      loc_1801C6373
0x1801c61b6  mov     byte ptr [r13+1], 0
0x1801c61bb  mov     [rbp+57h+var_22], 1
0x1801c61bf  mov     rax, [r15]
0x1801c61c2  mov     rcx, r15
0x1801c61c5  mov     rax, [rax+1A8h]
0x1801c61cc  call    cs:__guard_dispatch_icall_fptr
0x1801c61d2  mov     rbx, rax
0x1801c61d5  mov     rcx, rsi
0x1801c61d8  call    ??$GetPtrIfValid@UHighlight@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEBAPEBVColorEmbed@Art@@XZ; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Highlight>(void)
0x1801c61dd  test    rax, rax
0x1801c61e0  cmovnz  rbx, rax
0x1801c61e4  mov     r8, r13; struct Art::LineStyle *
0x1801c61e7  lea     rdx, [rbp+57h+var_58]; struct Art::LineProps *
0x1801c61eb  mov     rcx, rbx; this
0x1801c61ee  call    ?PropListToObj@Art@@YAXAEBVLineProps@1@AEAVLineStyle@1@AEBUPropListConversionOptions@1@@Z; Art::PropListToObj(Art::LineProps const &,Art::LineStyle &,Art::PropListConversionOptions const &)
0x1801c61f3  mov     edx, 4
0x1801c61f8  mov     rcx, rsi
0x1801c61fb  call    ?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyState(uint)
0x1801c6200  cmp     rax, 3
0x1801c6204  jnz     loc_1801C62A9
0x1801c620a  mov     rax, [r15]
0x1801c620d  mov     rcx, r15
0x1801c6210  mov     rax, [rax+188h]
0x1801c6217  call    cs:__guard_dispatch_icall_fptr
0x1801c621d  mov     rdi, rax
0x1801c6220  mov     rcx, rsi
0x1801c6223  call    ??$GetPtrIfValid@UOuterShadow@EfPr@Art@@@?$TPropertySet@VEffectListIDs@Art@@@Ofc@@QEBAPEBVOuterShadowEffect@Art@@XZ; Ofc::TPropertySet<Art::EffectListIDs>::GetPtrIfValid<Art::EfPr::OuterShadow>(void)
0x1801c6228  test    rax, rax
0x1801c622b  cmovnz  rdi, rax
0x1801c622f  mov     rbx, [rbp+57h+var_48]
0x1801c6233  test    rbx, rbx
0x1801c6236  jnz     short loc_1801C6245
0x1801c6238  lea     rcx, [rbp+57h+var_48]
0x1801c623c  call    ?CreateStorage@?$TOptional@VEffectProps@Art@@@Ofc@@QEAAAEAVEffectProps@Art@@PEAVCRollbackTransaction@2@@Z; Ofc::TOptional<Art::EffectProps>::CreateStorage(Ofc::CRollbackTransaction *)
0x1801c6241  mov     rbx, [rbp+57h+var_48]
0x1801c6245  xor     ecx, ecx
0x1801c6247  mov     [rsp+110h+var_F0], rcx
0x1801c624c  mov     rax, [rdi+8]
0x1801c6250  mov     qword ptr [rsp+110h+var_E8], rax
0x1801c6255  cmp     rax, 1
0x1801c6259  jbe     loc_1801C6721
0x1801c625f  mov     rdx, rdi
0x1801c6262  lea     rcx, [rsp+110h+var_F0]
0x1801c6267  mov     rax, [rax+8]
0x1801c626b  call    cs:__guard_dispatch_icall_fptr
0x1801c6271  mov     rdx, qword ptr [rsp+110h+var_E8]
0x1801c6276  mov     rcx, [rsp+110h+var_F0]
0x1801c627b  mov     rax, [rbx]
0x1801c627e  mov     [rbx], rcx
0x1801c6281  mov     [rsp+110h+var_F0], rax
0x1801c6286  mov     rax, [rbx+8]
0x1801c628a  mov     [rbx+8], rdx
0x1801c628e  mov     qword ptr [rsp+110h+var_E8], rax
0x1801c6293  cmp     rax, 1
0x1801c6297  jbe     short loc_1801C62A9
0x1801c6299  lea     rcx, [rsp+110h+var_F0]
0x1801c629e  mov     rax, [rax+10h]
0x1801c62a2  call    cs:__guard_dispatch_icall_fptr
0x1801c62a8  nop
0x1801c62a9  mov     edx, 5
0x1801c62ae  mov     rcx, rsi
0x1801c62b1  call    ?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyState(uint)
0x1801c62b6  cmp     rax, 3
0x1801c62ba  jnz     loc_1801C63BE
0x1801c62c0  mov     rcx, rsi
0x1801c62c3  call    ??$GetPtrIfValid@UScene3D@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEBAPEBVScene3D@Art@@XZ; Ofc::TPropertySet<Art::ShapePropsIDs>::GetPtrIfValid<Art::SpPr::Scene3D>(void)
0x1801c62c8  mov     rbx, rax
0x1801c62cb  test    rax, rax
0x1801c62ce  jnz     loc_1801C6A79
0x1801c62d4  mov     ecx, 66356C77h; unsigned int
0x1801c62d9  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x1801c62de  nop
0x1801c62df  jmp     short $+2
0x1801c62e1  nop
  ... truncated ...
```
