# win_musl::consumption::MarkupCompatibility::MarkupScope::ProcessAttributes(win_musl::consumption::MarkupCompatibility &,win_musl::consumption::MarkupCompatibility::MarkupScope &,win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes &)

- ea: `0x180035590`
- end: `0x1800375b8`
- name: `?ProcessAttributes@MarkupScope@MarkupCompatibility@consumption@win_musl@@QEAA?AVSaxAttributes@34@AEAV234@AEAV1234@AEBUqualified_name@sax@4@AEAV534@@Z`
- size: `8232`
- prototype: ``
- caller_count: `1`
- callee_count: `57`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033ec0`

## callees

- `0x180004ea4`
- `0x180004ecc`
- `0x1800051b8`
- `0x180005664`
- `0x180012450`
- `0x18003500c`
- `0x180035590`
- `0x1800375c0`
- `0x180037820`
- `0x1800387d0`
- `0x180038800`
- `0x18006ba58`
- `0x18007ebf0`
- `0x18007edac`
- `0x18007fcdc`
- `0x180082fcc`
- `0x18008390c`
- `0x180083c04`
- `0x1800867c0`
- `0x18008ca74`
- `0x1800a678c`
- `0x1800aa47c`
- `0x1800b36ac`
- `0x1800b395c`
- `0x1800be5ac`
- `0x1800bed3c`
- `0x1800bed64`
- `0x1800bfedc`
- `0x1800bff44`
- `0x1800c1178`
- `0x1800c12a8`
- `0x1800c20c4`
- `0x1800c2c78`
- `0x1800c2d08`
- `0x1800c2dac`
- `0x1800c4964`
- `0x1800dbde8`
- `0x180100398`
- `0x1801016e8`
- `0x180101e34`
- `0x18010dfec`
- `0x180115018`
- `0x18011997c`
- `0x180119bc0`
- `0x18011b44c`
- `0x18011e78c`
- `0x180134b70`
- `0x1801355e4`
- `0x1801359ce`
- `0x180142fd0`

## string_xrefs

- `0x180035a93`: `xmlns`
- `0x18003688d`: `xmlns`
- `0x180035928`: `xml:lang`
- `0x18003620f`: `xml:lang`
- `0x1800359db`: `xml:space`
- `0x1800371cd`: `xml:space`
- `0x180036273`: `http://www.w3.org/XML/1998/namespace`
- `0x1800371f5`: `http://www.w3.org/XML/1998/namespace`
- `0x180036927`: `http://www.w3.org/2000/xmlns/`
- `0x180036d26`: `Must not have ignored xml:lang or xml:space attributes on mc: elements.`
- `0x180036bd9`: `MarkupCompatibility elements must not have non-prefixed attributes other than Requires on mc:Choice.`
- `0x18003743b`: `MarkupCompatibility elements must not have attributes from unknown namespaces.`

## pseudocode

```c
// Hidden C++ exception states: #wind=53
_QWORD *__fastcall win_musl::consumption::MarkupCompatibility::MarkupScope::ProcessAttributes(
        __int64 a1,
        _QWORD *a2,
        win_musl::consumption::MarkupCompatibility *a3,
        __int64 a4,
        win_musl::xml::attribute *a5,
        win_musl::consumption::SaxAttributes *a6)
{
  _QWORD *v7; // r12
  unsigned __int64 Length; // r15
  __int64 v10; // r13
  __int64 v11; // rcx
  bool v12; // r14
  unsigned __int64 v13; // rbx
  _OWORD *v14; // rax
  __int128 v15; // xmm0
  __int64 v16; // r9
  __int64 (__fastcall *v17)(__int64, __int128 *, __int128 *); // r10
  int v18; // ebx
  __int64 v19; // rdx
  const struct win_musl::sax::wchar_range *v20; // rdx
  const OLECHAR *v21; // r8
  const OLECHAR *v22; // rax
  _BYTE *v23; // r14
  _BYTE *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rax
  wchar_t *v27; // r8
  const wchar_t *v28; // r9
  wchar_t *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 traits_2_0_unsigned_short; // r8
  const OLECHAR *v33; // rax
  const OLECHAR *v34; // rcx
  __int64 v35; // r9
  __int64 v36; // rdx
  bool v37; // al
  __int64 v38; // r9
  __int64 (__fastcall *v39)(__int64, __int128 *, __int128 **); // r10
  __int128 v40; // xmm0
  int v41; // ebx
  __int64 v42; // r14
  __int64 *v43; // r12
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rbx
  __int64 v48; // r13
  __int64 v49; // r14
  __int64 v50; // rcx
  bool v51; // bl
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v56; // r8
  __int64 v57; // r9
  const wchar_t *v58; // r8
  const struct win_musl::sax::wchar_range *v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  char v70; // r12
  char v71; // al
  __int64 v72; // r8
  unsigned __int64 v73; // rdx
  __int64 v74; // rax
  int MarkupAttribute; // eax
  __int64 v76; // rcx
  _QWORD *v77; // r14
  _QWORD *i; // rbx
  __int64 v79; // r13
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rdx
  __int64 v85; // r8
  _QWORD *k; // r14
  unsigned __int64 v87; // rbx
  _QWORD *v88; // rax
  __int64 v89; // rbx
  __int64 v90; // rcx
  _QWORD *v91; // rbx
  __int64 v92; // r11
  __int64 v93; // rdx
  __int64 v94; // r8
  __int128 *v95; // rdx
  __int128 *v96; // rdx
  __int128 *v97; // rdx
  __int128 *v98; // rdx
  __int64 v99; // rax
  __int64 j; // rax
  unsigned __int64 v101; // rdx
  __int128 *p_Src; // rcx
  const struct win_musl::xml::local_name *m; // rbx
  int v104; // eax
  __int64 v105; // rax
  __int64 *v106; // r9
  __int64 v107; // rdx
  __int64 v108; // rax
  int v109; // eax
  int v110; // eax
  int v111; // eax
  int v112; // eax
  __int64 v113; // rax
  const struct win_musl::sax::local_name *v114; // rax
  unsigned int v115; // ebx
  win_musl::Formatter *v116; // rax
  const wchar_t *v117; // rax
  __int128 v118; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v119; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v120; // [rsp+60h] [rbp-A0h]
  __int128 *v121; // [rsp+68h] [rbp-98h] BYREF
  win_musl::consumption::SaxAttributes *v122; // [rsp+70h] [rbp-90h] BYREF
  win_musl::xml::attribute *v123; // [rsp+78h] [rbp-88h] BYREF
  char *v124; // [rsp+80h] [rbp-80h]
  char *v125; // [rsp+88h] [rbp-78h]
  _QWORD v126[2]; // [rsp+90h] [rbp-70h] BYREF
  win_musl::xml::attribute *v127; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v128; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v129[5]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v130; // [rsp+108h] [rbp+8h]
  unsigned __int64 v131; // [rsp+110h] [rbp+10h]
  __int64 v132; // [rsp+120h] [rbp+20h] BYREF
  __int128 v133; // [rsp+128h] [rbp+28h]
  __int128 v134; // [rsp+140h] [rbp+40h]
  __int64 v135; // [rsp+150h] [rbp+50h] BYREF
  __int128 v136; // [rsp+158h] [rbp+58h]
  __int64 v137; // [rsp+168h] [rbp+68h] BYREF
  __int128 v138; // [rsp+170h] [rbp+70h]
  __int64 v139; // [rsp+180h] [rbp+80h] BYREF
  __int128 v140; // [rsp+188h] [rbp+88h]
  __int64 v141; // [rsp+198h] [rbp+98h] BYREF
  __int128 v142; // [rsp+1A0h] [rbp+A0h]
  __int64 v143; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v144; // [rsp+1B8h] [rbp+B8h]
  _QWORD v145[3]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v146[3]; // [rsp+1E8h] [rbp+E8h] BYREF
  _QWORD v147[2]; // [rsp+200h] [rbp+100h] BYREF
  __int128 v148; // [rsp+210h] [rbp+110h]
  __int128 v149; // [rsp+220h] [rbp+120h]
  __int128 v150; // [rsp+230h] [rbp+130h]
  __int128 v151; // [rsp+240h] [rbp+140h]
  __int64 v152; // [rsp+250h] [rbp+150h]
  __int64 v153; // [rsp+258h] [rbp+158h]
  unsigned __int64 v154; // [rsp+260h] [rbp+160h]
  _QWORD v155[2]; // [rsp+270h] [rbp+170h] BYREF
  int v156; // [rsp+280h] [rbp+180h]
  const wchar_t *v157; // [rsp+288h] [rbp+188h]
  __int64 v158; // [rsp+290h] [rbp+190h]
  __int64 v159; // [rsp+298h] [rbp+198h]
  int v160; // [rsp+2A0h] [rbp+1A0h]
  const wchar_t *v161; // [rsp+2A8h] [rbp+1A8h]
  __int64 v162; // [rsp+2B0h] [rbp+1B0h]
  __int64 v163; // [rsp+2B8h] [rbp+1B8h]
  int v164; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v165; // [rsp+2C8h] [rbp+1C8h]
  _QWORD v166[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v167; // [rsp+2E0h] [rbp+1E0h]
  __int128 v168; // [rsp+2F0h] [rbp+1F0h]
  __int128 v169; // [rsp+300h] [rbp+200h]
  __int128 v170; // [rsp+310h] [rbp+210h]
  __int64 v171; // [rsp+320h] [rbp+220h]
  unsigned __int64 v172; // [rsp+328h] [rbp+228h]
  unsigned __int64 v173; // [rsp+330h] [rbp+230h]
  __int128 Src; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int64 v175; // [rsp+350h] [rbp+250h]
  unsigned __int64 v176; // [rsp+358h] [rbp+258h]
  __int128 v177; // [rsp+360h] [rbp+260h] BYREF
  __int64 v178; // [rsp+370h] [rbp+270h]
  unsigned __int64 v179; // [rsp+378h] [rbp+278h]
  __int128 v180; // [rsp+380h] [rbp+280h] BYREF
  __int64 v181; // [rsp+390h] [rbp+290h]
  unsigned __int64 v182; // [rsp+398h] [rbp+298h]
  __int128 v183; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v184; // [rsp+3B0h] [rbp+2B0h]
  unsigned __int64 v185; // [rsp+3B8h] [rbp+2B8h]
  __int128 pExceptionObject; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int128 v187; // [rsp+3D0h] [rbp+2D0h]
  __int128 v188; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int128 v189; // [rsp+3F0h] [rbp+2F0h]
  __int128 v190; // [rsp+400h] [rbp+300h] BYREF
  __int128 v191; // [rsp+410h] [rbp+310h]
  __int128 v192; // [rsp+420h] [rbp+320h] BYREF
  __int128 v193; // [rsp+430h] [rbp+330h]
  __int128 v194; // [rsp+440h] [rbp+340h] BYREF
  __int64 v195; // [rsp+450h] [rbp+350h]
  __int64 v196; // [rsp+458h] [rbp+358h]
  _OWORD v197[3]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v198[16]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v199[96]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t v200[8]; // [rsp+500h] [rbp+400h] BYREF
  __int64 v201; // [rsp+510h] [rbp+410h]
  _BYTE v202[32]; // [rsp+560h] [rbp+460h] BYREF
  char v203[896]; // [rsp+580h] [rbp+480h] BYREF

  v7 = a2;
  v120 = a2;
  v122 = a6;
  v127 = a5;
  __(&v123, a2, a3);
  Length = win_musl::consumption::SaxAttributes::getLength(a6);
  *(_QWORD *)&v118 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v118,
    *(_QWORD *)a6);
  *(_QWORD *)&v119 = &v118;
  v126[0] = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    v126,
    v118);
  v126[1] = Length;
  if ( (_QWORD)v118 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v118 + 16LL))(v118);
  *(_QWORD *)&v118 = 0;
  v10 = v126[0];
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v118,
    v126[0]);
  *(_QWORD *)&v119 = &v118;
  v128 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v128,
    v118);
  memset(v129, 0, sizeof(v129));
  v130 = 0;
  v131 = Length;
  if ( (_QWORD)v118 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v118 + 16LL))(v118);
  *(_QWORD *)&v118 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v118,
    v10);
  *(_QWORD *)&v119 = &v118;
  v166[0] = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    v166,
    v118);
  v166[1] = 0;
  v167 = 0;
  v168 = 0;
  v169 = 0;
  v170 = 0;
  v171 = 0;
  v172 = Length;
  v173 = Length;
  if ( (_QWORD)v118 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v118 + 16LL))(v118);
  if ( *(_DWORD *)(a1 + 56) )
  {
    v49 = v166[0];
  }
  else
  {
    if ( !*(_QWORD *)(a1 + 368) )
    {
      while ( 1 )
      {
        *(_QWORD *)&v119 = &v118;
        *(_QWORD *)&v118 = 0;
        win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
          &v118,
          v166[0]);
        v121 = 0;
        win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
          &v121,
          v128);
        v11 = v118;
        v12 = v121 == (__int128 *)v118;
        if ( v121 )
        {
          (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v121 + 16LL))(v121);
          v11 = v118;
        }
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v13 = v130;
        if ( v12 && v130 == Length && v131 == Length )
          goto LABEL_102;
        if ( v130 >= v131 )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)v197,
            0x320u,
            -2147418113,
            (__int64)L"SaxAttributes::SaxAttributeSequence index out of range");
          throw (SplException::THResultException *)v197;
        }
        *(_QWORD *)&v118 = 0;
        win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
          &v118,
          v128);
        v121 = &v118;
        *(_QWORD *)&v119 = 0;
        win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
          &v119,
          v118);
        if ( (_QWORD)v118 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v118 + 16LL))(v118);
          *(_QWORD *)&v118 = 0;
        }
        LODWORD(v121) = 1;
        v14 = (_OWORD *)win_musl::consumption::SaxAttributes::SaxQuery(&v119, v197, v13, &v121);
        v129[0] = *v14;
        v129[1] = v14[1];
        v129[2] = v14[2];
        v129[3] = v14[3];
        v129[4] = v14[4];
        if ( (_DWORD)v121 == 1 )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)v197,
            0x329u,
            -2147418113,
            (__int64)L"SaxAttributes::SaxAttributeSequence SaxQuery failed");
          throw (SplException::THResultException *)v197;
        }
        if ( (_QWORD)v119 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v119 + 16LL))(v119);
        v15 = 0;
        v119 = 0;
        v16 = *(_QWORD *)(a1 + 64);
        v17 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v16 + 48LL);
        if ( *((_QWORD *)&v129[0] + 1) && *(_QWORD *)&v129[0] && *((_QWORD *)&v129[0] + 1) != *(_QWORD *)&v129[0] )
        {
          *((_QWORD *)&v134 + 1) = *(_QWORD *)&v129[0];
          *(_QWORD *)&v134 = (unsigned int)((__int64)(*((_QWORD *)&v129[0] + 1) - *(_QWORD *)&v129[0]) >> 1);
          v15 = v134;
        }
        else
        {
          v134 = 0;
        }
        v118 = v15;
        v18 = v17(v16, &v118, &v119);
        if ( v18 < 0 )
        {
          memset_0(v200, 0, 0x400u);
          StringCchPrintfW(v200, 0x200u, L"Call to NamespaceSubsumedBy failed with HResult 0x%X.", (unsigned int)v18);
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)v197,
            0x88u,
            v18,
            (__int64)v200);
          throw (SplException::THResultException *)v197;
        }
        if ( (v19 = *((_QWORD *)&v119 + 1) + 2LL * (unsigned int)v119, *((_QWORD *)&v119 + 1) != v19)
          && v19
          && *((_QWORD *)&v119 + 1)
          && v19 != *((_QWORD *)&v119 + 1)
          || (unsigned int)win_musl::consumption::MarkupCompatibility::QueryMarkupAttribute(v127, v129) )
        {
LABEL_102:
          v7 = v120;
          v10 = v126[0];
          break;
        }
        v21 = (const OLECHAR *)word_1801DC36A;
        do
        {
          v22 = v21 - 1;
          if ( *(v21 - 1) )
            break;
          --v21;
        }
        while ( v22 != L"xml:lang" );
        v23 = (_BYTE *)*((_QWORD *)&v129[2] + 1);
        v24 = *(_BYTE **)&v129[2];
        if ( *((_QWORD *)&v129[2] + 1) && *(_QWORD *)&v129[2] && *((_QWORD *)&v129[2] + 1) != *(_QWORD *)&v129[2] )
          v25 = (__int64)(*((_QWORD *)&v129[2] + 1) - *(_QWORD *)&v129[2]) >> 1;
        else
          v25 = 0;
        if ( !v21 || v21 == L"xml:lang" )
          v26 = 0;
        else
          v26 = v21 - L"xml:lang";
        if ( v25 == v26 )
        {
          if ( *((_QWORD *)&v129[2] + 1)
            && *(_QWORD *)&v129[2]
            && *((_QWORD *)&v129[2] + 1) != *(_QWORD *)&v129[2]
            && v21
            && v21 != L"xml:lang" )
          {
            if ( !memcmp_0(*(const void **)&v129[2], L"xml:lang", *((_QWORD *)&v129[2] + 1) - *(_QWORD *)&v129[2]) )
              goto LABEL_102;
          }
          else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)&v129[2], v20) && (!v56 || v56 == v57) )
          {
            goto LABEL_102;
          }
        }
        v27 = (wchar_t *)&dword_1801DC384;
        v28 = L"xml:space";
        do
        {
          v29 = v27 - 1;
          if ( *(v27 - 1) )
            break;
          --v27;
        }
        while ( v29 != L"xml:space" );
        if ( v23 && v24 && v23 != v24 )
          v30 = (v23 - v24) >> 1;
        else
          v30 = 0;
        if ( !v27 || v27 == L"xml:space" )
          v31 = 0;
        else
          v31 = v27 - L"xml:space";
        if ( v30 == v31 )
        {
          if ( v23 && v24 && v23 != v24 && v27 && v27 != L"xml:space" )
          {
            if ( !memcmp_0(v24, L"xml:space", v23 - v24) )
              goto LABEL_102;
          }
          else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)&v129[2], v20) && (!v58 || v58 == v28) )
          {
            goto LABEL_102;
          }
        }
        traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                      v24,
                                      v23,
                                      58,
                                      v28);
        *(_QWORD *)&v180 = L"xmlns";
        v33 = (const OLECHAR *)&dword_1801DC354;
        *((_QWORD *)&v180 + 1) = &dword_1801DC354;
        do
        {
          v34 = v33 - 1;
          if ( *(v33 - 1) )
            break;
          --v33;
        }
        while ( v34 != L"xmlns" );
        *((_QWORD *)&v180 + 1) = v33;
        *(_QWORD *)&v177 = *(_QWORD *)&v129[2];
        *((_QWORD *)&v177 + 1) = traits_2_0_unsigned_short;
        if ( traits_2_0_unsigned_short && *(_QWORD *)&v129[2] && traits_2_0_unsigned_short != *(_QWORD *)&v129[2] )
          v35 = (traits_2_0_unsigned_short - *(_QWORD *)&v129[2]) >> 1;
        else
          v35 = 0;
        if ( !v33 || v33 == L"xmlns" )
          v36 = 0;
        else
          v36 = v33 - L"xmlns";
        if ( v35 == v36 )
        {
          if ( traits_2_0_unsigned_short
            && *(_QWORD *)&v129[2]
            && traits_2_0_unsigned_short != *(_QWORD *)&v129[2]
            && v33
            && v33 != L"xmlns" )
          {
            v37 = memcmp_0(*(const void **)&v129[2], L"xmlns", traits_2_0_unsigned_short - *(_QWORD *)&v129[2]) == 0;
          }
          else
          {
            if ( !win_musl::sax::wchar_range_empty(
                    (win_musl::sax *)&v177,
                    (const struct win_musl::sax::wchar_range *)v36) )
              goto LABEL_81;
            v37 = win_musl::sax::wchar_range_empty((win_musl::sax *)&v180, v59);
          }
          if ( v37 )
            goto LABEL_102;
        }
LABEL_81:
        LODWORD(v121) = 0;
        v38 = *(_QWORD *)(a1 + 64);
        v39 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 **))(*(_QWORD *)v38 + 32LL);
        if ( *((_QWORD *)&v129[0] + 1) && *(_QWORD *)&v129[0] && *((_QWORD *)&v129[0] + 1) != *(_QWORD *)&v129[0] )
        {
          *((_QWORD *)&v183 + 1) = *(_QWORD *)&v129[0];
          *(_QWORD *)&v183 = (unsigned int)((__int64)(*((_QWORD *)&v129[0] + 1) - *(_QWORD *)&v129[0]) >> 1);
          v40 = v183;
        }
        else
        {
          v40 = 0;
          v183 = 0;
        }
        v119 = v40;
        v41 = v39(v38, &v119, &v121);
        if ( v41 < 0 )
        {
          memset_0(v200, 0, 0x400u);
          StringCchPrintfW(v200, 0x200u, L"Call to IsKnownNamespace failed with HResult 0x%X.", (unsigned int)v41);
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::THResultException *)v197,
            0x68u,
            v41,
            (__int64)v200);
          throw (SplException::THResultException *)v197;
        }
        if ( !(_DWORD)v121 )
        {
          v42 = *((_QWORD *)a3 + 5);
          if ( a3 == (win_musl::consumption::MarkupCompatibility *)-16LL )
            v43 = 0;
          else
            v43 = (__int64 *)*((_QWORD *)a3 + 2);
          v44 = v42 + *((_QWORD *)a3 + 6);
          *(_QWORD *)&v119 = v44;
          while ( v42 != v44 )
          {
            if ( v43 )
              v45 = *v43;
            else
              v45 = 0;
            v46 = *(_QWORD *)(*(_QWORD *)(v45 + 8) + 8 * (v42 & (*(_QWORD *)(v45 + 16) - 1LL)));
            v47 = *(_QWORD *)(v46 + 264);
            v48 = *(_QWORD *)(v46 + 272);
            while ( v47 != v48 )
            {
              v108 = win_musl::sax::wchar_range::wchar_range(&Src, v47);
              if ( (unsigned __int8)win_musl::sax::operator==(v129, v108) )
                goto LABEL_102;
              v47 += 64;
            }
            ++v42;
            v44 = v119;
          }
        }
        ++v130;
      }
    }
    v121 = &v118;
    *(_QWORD *)&v118 = 0;
    v49 = v166[0];
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v118,
      v166[0]);
    *(_QWORD *)&v119 = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v119,
      v128);
    v50 = v118;
    v51 = (_QWORD)v119 == (_QWORD)v118;
    if ( (_QWORD)v119 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v119 + 16LL))(v119);
      v50 = v118;
    }
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 && v130 == Length && v131 == Length )
    {
      *v7 = 0;
      win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
        v7,
        *(_QWORD *)v122);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      if ( v128 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
        v128 = 0;
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v123 )
      {
        std::_Destroy_range<std::allocator<win_musl::xml::attribute>>(v123);
        std::_Deallocate<16>(v123, 32 * ((v125 - (char *)v123) >> 5));
      }
      return v7;
    }
  }
  *(_QWORD *)&v118 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v118,
    v10);
  v122 = (win_musl::consumption::SaxAttributes *)&v118;
  v147[0] = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    v147,
    v118);
  v147[1] = 0;
  v148 = 0;
  v149 = 0;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  v154 = Length;
  if ( (_QWORD)v118 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v118 + 16LL))(v118);
  while ( 1 )
  {
    v122 = (win_musl::consumption::SaxAttributes *)&v119;
    *(_QWORD *)&v119 = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v119,
      v128);
    *(_QWORD *)&v118 = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v118,
      v147[0]);
    if ( (unsigned __int8)win_scope::operator==<ISAXAttributes *,win_scope::const_policies<win_scope::com_policies>>(
                            &v118,
                            &v119) )
    {
      if ( v153 == v130 && v154 == v131 )
        break;
    }
    v53 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v147, v153);
    v54 = win_musl::XmlAttributeFromSaxAttribute(v200, v53);
    if ( v124 == v125 )
    {
      std::vector<win_musl::xml::attribute>::_Emplace_reallocate<win_musl::xml::attribute>(&v123, v124, v54);
    }
    else
    {
      win_musl::xml::attribute::attribute(v124, v54);
      v124 += 160;
    }
    win_musl::xml::attribute_value::~attribute_value((win_musl::xml::attribute_value *)v202);
    win_musl::xml::qualified_name::~qualified_name((win_musl::xml::qualified_name *)v200);
    ++v153;
  }
  __(&v143, v153, v52);
  __(&v141, v60, v61);
  __(&v132, v62, v63);
  __(&v139, v64, v65);
  __(&v137, v66, v67);
  __(&v135, v68, v69);
  v70 = 0;
  while ( 1 )
  {
    v122 = (win_musl::consumption::SaxAttributes *)&v119;
    *(_QWORD *)&v119 = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v119,
      v49);
    *(_QWORD *)&v118 = 0;
    win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
      &v118,
      v128);
    v71 = win_scope::operator==<ISAXAttributes *,win_scope::const_policies<win_scope::com_policies>>(&v118, &v119);
    v73 = v130;
    if ( v71 )
    {
      if ( v130 == Length && v131 == Length )
        break;
    }
    v74 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v128, v130);
    win_musl::XmlAttributeFromSaxAttribute(v200, v74);
    v180 = *(_OWORD *)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                        &v128,
                        v130);
    win_musl::consumption::MarkupQuery::NamespaceSubsumedBy(a1 + 64, &v177, &v180);
    if ( *((_QWORD *)&v177 + 1) && (_QWORD)v177 && *((_QWORD *)&v177 + 1) != (_QWORD)v177 )
      std::wstring::_Assign<wchar_t>(v200, v177, (__int64)(*((_QWORD *)&v177 + 1) - v177) >> 1);
    win_musl::sax::qualified_name::qualified_name(
      (win_musl::sax::qualified_name *)v197,
      (const struct win_musl::xml::qualified_name *)v200);
    win_musl::sax::wchar_range::wchar_range(v198, v202);
    win_musl::sax::wchar_range::wchar_range(v199, v203);
    MarkupAttribute = win_musl::consumption::MarkupCompatibility::QueryMarkupAttribute(v127, v197);
    if ( MarkupAttribute )
    {
      v104 = MarkupAttribute - 1;
      if ( !v104 )
      {
        v105 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v128, v130);
        v106 = &v139;
        goto LABEL_240;
      }
      v109 = v104 - 1;
      if ( !v109 )
      {
        v105 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v128, v130);
        v106 = &v137;
        goto LABEL_240;
      }
      v110 = v109 - 1;
      if ( v110 )
      {
        v111 = v110 - 1;
        if ( v111 )
        {
          v112 = v111 - 1;
          if ( v112 )
          {
            if ( v112 != 1 )
            {
              std::wstring::wstring(&Src, L"Unknown MarkupAttribute::Enum member.");
              win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, 2152792124LL);
              std::wstring::_Tidy_deallocate(&Src);
              win_musl::detail::ThrowBuilder<SplException::THResultException>(
                (SplException::THResultException *)&pExceptionObject,
                0x5D6u,
                -2142175172,
                (__int64)L"Unknown MarkupAttribute::Enum member.");
              throw (SplException::THResultException *)&pExceptionObject;
            }
            if ( *(_DWORD *)(a1 + 56) != 2 )
            {
              std::wstring::wstring(&Src, L"Requires attribute is only valid on mc:Choice.");
              win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, 2152792116LL);
              std::wstring::_Tidy_deallocate(&Src);
              win_musl::detail::ThrowBuilder<SplException::THResultException>(
                (SplException::THResultException *)&pExceptionObject,
                0x598u,
                -2142175180,
                (__int64)L"Requires attribute is only valid on mc:Choice.");
              throw (SplException::THResultException *)&pExceptionObject;
            }
            v70 = 1;
            v105 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                     &v128,
                     v130);
            v106 = &v132;
LABEL_240:
            v107 = 0;
          }
          else
          {
            v105 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                     &v128,
                     v130);
            v106 = &v143;
            v107 = 2;
          }
LABEL_241:
          win_musl::consumption::MarkupCompatibility::ParsePrefixList(a3, v107, v105 + 64, v106);
          goto LABEL_154;
        }
        v105 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v128, v130);
        v106 = &v141;
      }
      else
      {
        v105 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v128, v130);
        v106 = &v135;
      }
      v107 = 1;
      goto LABEL_241;
    }
    if ( !win_musl::consumption::MarkupCompatibility::MarkupScope::ParseXmlAttribute(
            (win_musl::consumption::MarkupCompatibility::MarkupScope *)a1,
            (const struct win_musl::sax::attribute *)v197) )
    {
      if ( !v201 && *(_DWORD *)(a1 + 56) )
      {
        std::wstring::wstring(
          &Src,
          L"MarkupCompatibility elements must not have non-prefixed attributes other than Requires on mc:Choice.");
        win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, 2152792118LL);
        std::wstring::_Tidy_deallocate(&Src);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::THResultException *)&pExceptionObject,
          0x5C6u,
          -2142175178,
          (__int64)L"MarkupCompatibility elements must not have non-prefixed attributes other than Requires on mc:Choice.");
        throw (SplException::THResultException *)&pExceptionObject;
      }
      if ( v124 == v125 )
      {
        std::vector<win_musl::xml::attribute>::_Emplace_reallocate<win_musl::xml::attribute const &>(&v123, v124, v200);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<win_musl::xml::attribute>>::construct<win_musl::xml::attribute,win_musl::xml::attribute const &>(
          v76,
          v124,
          v200);
        v124 += 160;
      }
    }
LABEL_154:
    win_musl::xml::attribute_value::~attribute_value((win_musl::xml::attribute_value *)v202);
    win_musl::xml::qualified_name::~qualified_name((win_musl::xml::qualified_name *)v200);
    ++v130;
  }
  v77 = *(_QWORD **)(a1 + 360);
  for ( i = (_QWORD *)*v77; i != v77; i = (_QWORD *)j )
  {
    Src = 0;
    v175 = 0;
    v176 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src);
    if ( i[6] )
    {
      v101 = v175;
      p_Src = &Src;
      if ( v175 >= v176 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(&Src, v175, v94, 58);
      }
      else
      {
        ++v175;
        if ( v176 > 7 )
          p_Src = (__int128 *)Src;
        *(_DWORD *)((char *)p_Src + 2 * v101) = 58;
      }
      std::wstring::_Append<wchar_t>(&Src);
    }
    v183 = 0;
    v184 = 0;
    v185 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v183);
    v180 = 0;
    v181 = 0;
    v182 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v180);
    v177 = 0;
    v178 = 0;
    v179 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v177);
    pExceptionObject = 0;
    v187 = 0;
    v95 = &v177;
    if ( v179 > 7 )
      v95 = (__int128 *)v177;
    std::wstring::_Construct<2,wchar_t const *>(&pExceptionObject, v95, v178);
    v188 = 0;
    v189 = 0;
    v96 = &v180;
    if ( v182 > 7 )
      v96 = (__int128 *)v180;
    std::wstring::_Construct<2,wchar_t const *>(&v188, v96, v181);
    v190 = 0;
    v191 = 0;
    v97 = &Src;
    if ( v176 > 7 )
      v97 = (__int128 *)Src;
    std::wstring::_Construct<2,wchar_t const *>(&v190, v97, v175);
    v122 = (win_musl::consumption::SaxAttributes *)&v192;
    v192 = 0;
    v193 = 0;
    v98 = &v183;
    if ( v185 > 7 )
      v98 = (__int128 *)v183;
    std::wstring::_Construct<2,wchar_t const *>(&v192, v98, v184);
    v194 = 0;
    v195 = 0;
    v196 = 0;
    v99 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i + 8);
    std::wstring::_Construct<2,wchar_t const *>(&v194, v99, i[10]);
    if ( v124 == v125 )
    {
      std::vector<win_musl::xml::attribute>::_Emplace_reallocate<win_musl::xml::attribute>(
        &v123,
        v124,
        &pExceptionObject);
    }
    else
    {
      win_musl::xml::attribute::attribute(v124, &pExceptionObject);
      v124 += 160;
    }
    win_musl::xml::attribute_value::~attribute_value((win_musl::xml::attribute_value *)&v192);
    win_musl::xml::qualified_name::~qualified_name((win_musl::xml::qualified_name *)&pExceptionObject);
    if ( v179 > 7 )
      std::_Deallocate<16>(v177, 2 * v179 + 2);
    if ( v182 > 7 )
      std::_Deallocate<16>(v180, 2 * v182 + 2);
    if ( v185 > 7 )
      std::_Deallocate<16>(v183, 2 * v185 + 2);
    v73 = v176;
    if ( v176 > 7 )
      std::_Deallocate<16>(Src, 2 * v176 + 2);
    if ( *(_BYTE *)(i[2] + 25LL) )
    {
      for ( j = i[1]; !*(_BYTE *)(j + 25) && i == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
        i = (_QWORD *)j;
    }
    else
    {
      j = std::_Tree_val<std::_Tree_simple_types<std::pair<xpsutil::lpwstr_wrapper const,long volatile>>>::_Min();
    }
  }
  v79 = v126[0];
  if ( *(_BYTE *)(a1 + 104) )
  {
    v183 = 0;
    v184 = 0;
    v185 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v183);
    v180 = 0;
    v181 = 0;
    v182 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v180);
    v177 = 0;
    v178 = 0;
    v179 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v177);
    Src = 0;
    v175 = 0;
    v176 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src);
    pExceptionObject = 0;
    v187 = 0;
    v80 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&Src);
    std::wstring::_Construct<2,wchar_t const *>(&pExceptionObject, v80, v175);
    v188 = 0;
    v189 = 0;
    v81 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v177);
    std::wstring::_Construct<2,wchar_t const *>(&v188, v81, v178);
    v190 = 0;
    v191 = 0;
    v82 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v180);
    std::wstring::_Construct<2,wchar_t const *>(&v190, v82, v181);
    v122 = (win_musl::consumption::SaxAttributes *)&v192;
    v192 = 0;
    v193 = 0;
    v83 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v183);
    std::wstring::_Construct<2,wchar_t const *>(&v192, v83, v184);
    std::wstring::wstring(&v194, a1 + 72);
    if ( v124 == v125 )
    {
      std::vector<win_musl::xml::attribute>::_Emplace_reallocate<win_musl::xml::attribute>(
        &v123,
        v124,
        &pExceptionObject);
    }
    else
    {
      win_musl::xml::attribute::attribute(v124, &pExceptionObject);
      v124 += 160;
    }
    win_musl::xml::attribute_value::~attribute_value((win_musl::xml::attribute_value *)&v192);
    win_musl::xml::qualified_name::~qualified_name((win_musl::xml::qualified_name *)&pExceptionObject);
    if ( v176 > 7 )
      std::_Deallocate<16>(Src, 2 * v176 + 2);
    v175 = 0;
    v176 = 7;
    LOWORD(Src) = 0;
    if ( v179 > 7 )
      std::_Deallocate<16>(v177, 2 * v179 + 2);
    v178 = 0;
    v179 = 7;
    LOWORD(v177) = 0;
    if ( v182 > 7 )
      std::_Deallocate<16>(v180, 2 * v182 + 2);
    v181 = 0;
    v182 = 7;
    LOWORD(v180) = 0;
    v73 = v185;
    if ( v185 > 7 )
      std::_Deallocate<16>(v183, 2 * v185 + 2);
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::wstring::wstring(&v183, &word_1801DC754);
    std::wstring::wstring(&v180, L"xml:space");
    std::wstring::wstring(&v177, L"space");
    std::wstring::wstring(&Src, L"http://www.w3.org/XML/1998/namespace");
    v113 = win_musl::xml::attribute::attribute(
             (unsigned int)v200,
             (unsigned int)&Src,
             (unsigned int)&v177,
             (unsigned int)&v180,
             (__int64)&v183,
             a1 + 112);
    std::vector<win_musl::xml::attribute>::push_back(&v123, v113);
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v200);
    std::wstring::_Tidy_deallocate(&Src);
    std::wstring::_Tidy_deallocate(&v177);
    std::wstring::_Tidy_deallocate(&v180);
    std::wstring::_Tidy_deallocate(&v183);
  }
  if ( !v70 && *(_DWORD *)(a1 + 56) == 2 )
  {
    std::wstring::wstring(&Src, L"mc:Choice element must have Requires attribute.");
    win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, 2152792117LL);
    std::wstring::_Tidy_deallocate(&Src);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)v197,
      0x624u,
      -2142175179,
      (__int64)L"mc:Choice element must have Requires attribute.");
    throw (SplException::THResultException *)v197;
  }
  __(v146, v73, v72);
  __(v145, v84, v85);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, &v143, v146);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, &v141, v145);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, &v137, a1 + 264);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, &v139, a1 + 312);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, &v135, a1 + 288);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, &v132, a1 + 336);
  v155[0] = *(_QWORD *)(a1 + 288);
  v155[1] = *(_QWORD *)(a1 + 296);
  v156 = -2142175158;
  v157 = L"mc:ProcessContent must have matching Ignorable spec on the same element.";
  v158 = v146[0];
  v159 = v146[1];
  v160 = -2142175157;
  v161 = L"mc:PreserveAttributes must have matching Ignorable spec on the same element.";
  v162 = v145[0];
  v163 = v145[1];
  v164 = -2142175156;
  v165 = L"mc:PreserveElements must have matching Ignorable spec on the same element.";
  for ( k = v155; k != v166; k += 4 )
  {
    for ( m = (const struct win_musl::xml::local_name *)*k;
          m != (const struct win_musl::xml::local_name *)k[1];
          m = (const struct win_musl::xml::local_name *)((char *)m + 64) )
    {
      v114 = (const struct win_musl::sax::local_name *)win_musl::sax::local_name::local_name(
                                                         (win_musl::sax::local_name *)&Src,
                                                         m);
      if ( !win_musl::consumption::MarkupCompatibility::MarkupScope::Ignorable(
              (win_musl::consumption::MarkupCompatibility::MarkupScope *)a1,
              v114) )
      {
        v115 = *((_DWORD *)k + 4);
        std::wstring::wstring(&Src, k[3]);
        win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, v115);
        std::wstring::_Tidy_deallocate(&Src);
        std::wstring::wstring(&Src, k[3]);
        v116 = (win_musl::Formatter *)win_musl::Formatter::Formatter(v197, &Src);
        v117 = win_musl::Formatter::c_str(v116);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::THResultException *)&pExceptionObject,
          0x672u,
          v115,
          (__int64)v117);
        throw (SplException::THResultException *)&pExceptionObject;
      }
    }
  }
  if ( v70 && *(_DWORD *)(a1 + 56) == 2 && v132 == (_QWORD)v133 )
  {
    std::wstring::wstring(&Src, L"Requires attribute must not be empty.");
    win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, 2152792117LL);
    std::wstring::_Tidy_deallocate(&Src);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)&pExceptionObject,
      0x683u,
      -2142175179,
      (__int64)L"Requires attribute must not be empty.");
    throw (SplException::THResultException *)&pExceptionObject;
  }
  if ( *(_DWORD *)(a1 + 56) && (*(_BYTE *)(a1 + 104) || *(_QWORD *)(a1 + 128)) )
  {
    std::wstring::wstring(&Src, L"Must not have ignored xml:lang or xml:space attributes on mc: elements.");
    win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, 2152792118LL);
    std::wstring::_Tidy_deallocate(&Src);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)&pExceptionObject,
      0x692u,
      -2142175178,
      (__int64)L"Must not have ignored xml:lang or xml:space attributes on mc: elements.");
    throw (SplException::THResultException *)&pExceptionObject;
  }
  v87 = 0;
  while ( v87 < 0xCCCCCCCCCCCCCCCDuLL * ((v124 - (char *)v123) >> 5) )
  {
    win_musl::sax::qualified_name::qualified_name(
      (win_musl::sax::qualified_name *)v197,
      (win_musl::xml::attribute *)((char *)v123 + 160 * v87));
    win_musl::sax::wchar_range::wchar_range(v198, v92 + 96);
    win_musl::sax::wchar_range::wchar_range(v199, v93 + 32);
    v177 = v197[0];
    if ( (unsigned __int8)win_musl::consumption::MarkupQuery::IsKnownNamespace(a1 + 64, &v177) )
      goto LABEL_207;
    if ( !win_musl::consumption::MarkupCompatibility::Ignorable(a3, (const struct win_musl::sax::local_name *)v197) )
    {
      if ( *(_DWORD *)(a1 + 56) )
      {
        std::wstring::wstring(&Src, L"MarkupCompatibility elements must not have attributes from unknown namespaces.");
        win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, &Src, 2152792118LL);
        std::wstring::_Tidy_deallocate(&Src);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::THResultException *)&pExceptionObject,
          0x6B4u,
          -2142175178,
          (__int64)L"MarkupCompatibility elements must not have attributes from unknown namespaces.");
        throw (SplException::THResultException *)&pExceptionObject;
      }
LABEL_207:
      ++v87;
      continue;
    }
    std::vector<win_musl::xml::attribute>::erase(&v123, &v122, (char *)v123 + 160 * v87);
  }
  v122 = (win_musl::consumption::SaxAttributes *)v124;
  v127 = v123;
  v88 = (_QWORD *)win_musl::consumption::detail::CreateSaxAttributesCopy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<win_musl::xml::attribute>>>>(
                    &v119,
                    &v127,
                    &v122);
  v89 = *v88;
  if ( *v88 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v89 + 8LL))(*v88);
  else
    v89 = 0;
  v90 = *(_QWORD *)(a1 + 256);
  *(_QWORD *)(a1 + 256) = v89;
  if ( v90 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
  if ( (_QWORD)v119 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v119 + 16LL))(v119);
  v91 = v120;
  *v120 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    v91,
    *(_QWORD *)(a1 + 256));
  std::vector<win_musl::xml::local_name>::~vector<win_musl::xml::local_name>(v145);
  std::vector<win_musl::xml::local_name>::~vector<win_musl::xml::local_name>(v146);
  if ( v135 )
  {
    std::_Deallocate<16>(v135, (*((_QWORD *)&v136 + 1) - v135) & 0xFFFFFFFFFFFFFFE0uLL);
    v135 = 0;
    v136 = 0;
  }
  if ( v137 )
  {
    std::_Deallocate<16>(v137, (*((_QWORD *)&v138 + 1) - v137) & 0xFFFFFFFFFFFFFFE0uLL);
    v137 = 0;
    v138 = 0;
  }
  if ( v139 )
  {
    std::_Deallocate<16>(v139, (*((_QWORD *)&v140 + 1) - v139) & 0xFFFFFFFFFFFFFFE0uLL);
    v139 = 0;
    v140 = 0;
  }
  if ( v132 )
  {
    std::_Deallocate<16>(v132, (*((_QWORD *)&v133 + 1) - v132) & 0xFFFFFFFFFFFFFFE0uLL);
    v132 = 0;
    v133 = 0;
  }
  if ( v141 )
  {
    std::_Deallocate<16>(v141, (*((_QWORD *)&v142 + 1) - v141) & 0xFFFFFFFFFFFFFFE0uLL);
    v141 = 0;
    v142 = 0;
  }
  if ( v143 )
  {
    std::_Deallocate<16>(v143, (*((_QWORD *)&v144 + 1) - v143) & 0xFFFFFFFFFFFFFFE0uLL);
    v143 = 0;
    v144 = 0;
  }
  if ( v147[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[0] + 16LL))(v147[0]);
    v147[0] = 0;
  }
  if ( v166[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v166[0] + 16LL))(v166[0]);
  if ( v128 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
    v128 = 0;
  }
  if ( v79 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
  std::vector<win_musl::xml::attribute>::_Tidy(&v123);
  return v91;
}

```

## disassembly

```asm
0x180035590  mov     [rsp-8+arg_18], rbx
0x180035595  push    rbp
0x180035596  push    rsi
0x180035597  push    rdi
0x180035598  push    r12
0x18003559a  push    r13
0x18003559c  push    r14
0x18003559e  push    r15
0x1800355a0  lea     rbp, [rsp-810h]
0x1800355a8  sub     rsp, 910h
0x1800355af  mov     rax, cs:__security_cookie
0x1800355b6  xor     rax, rsp
0x1800355b9  mov     [rbp+840h+var_40], rax
0x1800355c0  mov     rdi, r8
0x1800355c3  mov     r12, rdx
0x1800355c6  mov     [rsp+940h+var_8E0], rdx
0x1800355cb  mov     rsi, rcx
0x1800355ce  mov     rbx, [rbp+840h+arg_28]
0x1800355d5  mov     [rsp+940h+var_8D0], rbx
0x1800355da  mov     [rbp+840h+var_8A0], rdx
0x1800355de  mov     rax, [rbp+840h+arg_20]
0x1800355e5  mov     [rbp+840h+var_8A0], rax
0x1800355e9  xor     r14d, r14d
0x1800355ec  lea     rcx, [rsp+940h+var_8C8]
0x1800355f1  call    ??@7fb71cf95b9e4bc40af214a63562e7bf@
0x1800355f6  nop
0x1800355f7  mov     rcx, rbx; this
0x1800355fa  call    ?getLength@SaxAttributes@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxAttributes::getLength(void)
0x1800355ff  mov     r15, rax
0x180035602  mov     qword ptr [rsp+940h+var_900], r14
0x180035607  mov     rdx, [rbx]
0x18003560a  lea     rcx, [rsp+940h+var_900]
0x18003560f  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x180035614  lea     rax, [rsp+940h+var_900]
0x180035619  mov     qword ptr [rsp+940h+var_8F0], rax
0x18003561e  xor     ebx, ebx
0x180035620  mov     [rbp+840h+var_8B0], rbx
0x180035624  mov     rdx, qword ptr [rsp+940h+var_900]
0x180035629  lea     rcx, [rbp+840h+var_8B0]
0x18003562d  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x180035632  mov     [rbp+840h+var_8A8], r15
0x180035636  mov     rcx, qword ptr [rsp+940h+var_900]
0x18003563b  test    rcx, rcx
0x18003563e  jz      short loc_18003564D
0x180035640  mov     rax, [rcx]
0x180035643  mov     rax, [rax+10h]
0x180035647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003564c  nop
0x18003564d  mov     qword ptr [rsp+940h+var_900], rbx
0x180035652  mov     r13, [rbp+840h+var_8B0]
0x180035656  mov     rdx, r13
0x180035659  lea     rcx, [rsp+940h+var_900]
0x18003565e  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x180035663  lea     rax, [rsp+940h+var_900]
0x180035668  mov     qword ptr [rsp+940h+var_8F0], rax
0x18003566d  mov     [rbp+840h+var_890], rbx
0x180035671  mov     rdx, qword ptr [rsp+940h+var_900]
0x180035676  lea     rcx, [rbp+840h+var_890]
0x18003567a  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x18003567f  mov     qword ptr [rbp+840h+var_888], rbx
0x180035683  xorps   xmm0, xmm0
0x180035686  movdqa  [rbp+840h+var_888+8], xmm0
0x18003568b  xorps   xmm1, xmm1
0x18003568e  movdqa  xmmword ptr [rbp+840h+Buf1], xmm1
0x180035693  movdqa  [rbp+840h+var_860], xmm0
0x180035698  movdqa  [rbp+840h+var_850], xmm1
0x18003569d  mov     [rbp+840h+var_840], rbx
0x1800356a1  mov     [rbp+840h+var_838], rbx
0x1800356a5  mov     [rbp+840h+var_830], r15
0x1800356a9  mov     rcx, qword ptr [rsp+940h+var_900]
0x1800356ae  test    rcx, rcx
0x1800356b1  jz      short loc_1800356C0
0x1800356b3  mov     rax, [rcx]
0x1800356b6  mov     rax, [rax+10h]
0x1800356ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356bf  nop
0x1800356c0  mov     qword ptr [rsp+940h+var_900], rbx
0x1800356c5  mov     rdx, r13
0x1800356c8  lea     rcx, [rsp+940h+var_900]
0x1800356cd  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800356d2  lea     rax, [rsp+940h+var_900]
0x1800356d7  mov     qword ptr [rsp+940h+var_8F0], rax
0x1800356dc  mov     [rbp+840h+var_670], rbx
0x1800356e3  mov     rdx, qword ptr [rsp+940h+var_900]
0x1800356e8  lea     rcx, [rbp+840h+var_670]
0x1800356ef  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800356f4  mov     [rbp+840h+var_668], rbx
0x1800356fb  xorps   xmm0, xmm0
0x1800356fe  movdqa  [rbp+840h+var_660], xmm0
0x180035706  xorps   xmm1, xmm1
0x180035709  movdqa  [rbp+840h+var_650], xmm1
0x180035711  movdqa  [rbp+840h+var_640], xmm0
0x180035719  movdqa  [rbp+840h+var_630], xmm1
0x180035721  mov     [rbp+840h+var_620], rbx
0x180035728  mov     [rbp+840h+var_618], r15
0x18003572f  mov     [rbp+840h+var_610], r15
0x180035736  mov     rcx, qword ptr [rsp+940h+var_900]
0x18003573b  test    rcx, rcx
0x18003573e  jnz     loc_180035E8F
0x180035744  cmp     [rsi+38h], ebx
0x180035747  jnz     loc_180036F99
0x18003574d  cmp     [rsi+170h], rbx
0x180035754  jnz     loc_180035C7C
0x18003575a  xor     r13d, r13d
0x18003575d  lea     rax, [rsp+940h+var_900]
0x180035762  mov     qword ptr [rsp+940h+var_8F0], rax
0x180035767  mov     qword ptr [rsp+940h+var_900], r13
0x18003576c  mov     rdx, [rbp+840h+var_670]
0x180035773  lea     rcx, [rsp+940h+var_900]
0x180035778  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x18003577d  nop
0x18003577e  mov     [rsp+940h+var_8D8], r13
0x180035783  mov     rdx, [rbp+840h+var_890]
0x180035787  lea     rcx, [rsp+940h+var_8D8]
0x18003578c  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x180035791  nop
0x180035792  mov     rdx, [rsp+940h+var_8D8]
0x180035797  mov     rcx, qword ptr [rsp+940h+var_900]
0x18003579c  cmp     rdx, rcx
0x18003579f  setz    r14b
0x1800357a3  test    rdx, rdx
0x1800357a6  jz      short loc_1800357BC
0x1800357a8  mov     rax, [rdx]
0x1800357ab  mov     rcx, rdx
0x1800357ae  mov     rax, [rax+10h]
0x1800357b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357b7  mov     rcx, qword ptr [rsp+940h+var_900]
0x1800357bc  test    rcx, rcx
0x1800357bf  jnz     loc_180035C56
0x1800357c5  mov     rbx, [rbp+840h+var_838]
0x1800357c9  test    r14b, r14b
0x1800357cc  jz      short loc_1800357D7
0x1800357ce  cmp     rbx, r15
0x1800357d1  jz      loc_180035C67
0x1800357d7  cmp     rbx, [rbp+840h+var_830]
0x1800357db  jnb     loc_180036F16
0x1800357e1  mov     qword ptr [rsp+940h+var_900], r13
0x1800357e6  mov     rdx, [rbp+840h+var_890]
0x1800357ea  lea     rcx, [rsp+940h+var_900]
0x1800357ef  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1800357f4  lea     rax, [rsp+940h+var_900]
0x1800357f9  mov     [rsp+940h+var_8D8], rax
0x1800357fe  mov     qword ptr [rsp+940h+var_8F0], r13
0x180035803  mov     rdx, qword ptr [rsp+940h+var_900]
0x180035808  lea     rcx, [rsp+940h+var_8F0]
0x18003580d  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x180035812  nop
0x180035813  mov     rcx, qword ptr [rsp+940h+var_900]
0x180035818  test    rcx, rcx
0x18003581b  jz      short loc_18003582E
0x18003581d  mov     rax, [rcx]
0x180035820  mov     rax, [rax+10h]
0x180035824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035829  mov     qword ptr [rsp+940h+var_900], r13
0x18003582e  mov     dword ptr [rsp+940h+var_8D8], 1
0x180035836  lea     r9, [rsp+940h+var_8D8]
0x18003583b  mov     r8, rbx
0x18003583e  lea     rdx, [rbp+840h+var_4E0]
0x180035845  lea     rcx, [rsp+940h+var_8F0]
0x18003584a  call    ?SaxQuery@SaxAttributes@consumption@win_musl@@QEAA?AUattribute@sax@3@_KPEAW4Enum@SaxAttributesQueryResult@23@@Z; win_musl::consumption::SaxAttributes::SaxQuery(unsigned __int64,win_musl::consumption::SaxAttributesQueryResult::Enum *)
0x18003584f  movups  xmm0, xmmword ptr [rax]
0x180035852  movups  [rbp+840h+var_888], xmm0
0x180035856  movups  xmm1, xmmword ptr [rax+10h]
0x18003585a  movups  xmmword ptr [rbp-38h], xmm1
0x18003585e  movups  xmm0, xmmword ptr [rax+20h]
0x180035862  movups  xmmword ptr [rbp+840h+Buf1+8], xmm0
0x180035866  movups  xmm1, xmmword ptr [rax+30h]
0x18003586a  movups  [rbp+840h+var_860+8], xmm1
0x18003586e  movups  xmm0, xmmword ptr [rax+40h]
0x180035872  movups  [rbp+840h+var_850+8], xmm0
0x180035876  cmp     dword ptr [rsp+940h+var_8D8], 1
0x18003587b  jz      loc_180036ECC
0x180035881  mov     rcx, qword ptr [rsp+940h+var_8F0]
0x180035886  test    rcx, rcx
0x180035889  jnz     loc_180035E3E
0x18003588f  mov     rcx, qword ptr [rbp+840h+var_888+8]
0x180035893  xorps   xmm0, xmm0
0x180035896  movdqa  [rsp+940h+var_8F0], xmm0
0x18003589c  mov     r9, [rsi+40h]
0x1800358a0  mov     rax, [r9]
0x1800358a3  mov     r10, [rax+30h]
0x1800358a7  test    rcx, rcx
0x1800358aa  jz      short loc_1800358BE
0x1800358ac  mov     rax, qword ptr [rbp+840h+var_888]
0x1800358b0  test    rax, rax
0x1800358b3  jz      short loc_1800358BE
0x1800358b5  cmp     rcx, rax
0x1800358b8  jnz     loc_180035E4F
0x1800358be  movaps  [rbp+840h+var_800], xmm0
0x1800358c2  movdqa  [rsp+940h+var_900], xmm0
0x1800358c8  lea     r8, [rsp+940h+var_8F0]
0x1800358cd  lea     rdx, [rsp+940h+var_900]
0x1800358d2  mov     rcx, r9
0x1800358d5  mov     rax, r10
0x1800358d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358dd  mov     ebx, eax
0x1800358df  test    eax, eax
0x1800358e1  js      loc_180036E57
0x1800358e7  mov     eax, dword ptr [rsp+940h+var_8F0]
0x1800358eb  mov     rcx, qword ptr [rsp+940h+var_8F0+8]
0x1800358f0  lea     rdx, [rcx+rax*2]
0x1800358f4  cmp     rcx, rdx
0x1800358f7  jz      short loc_18003590C
0x1800358f9  test    rdx, rdx
0x1800358fc  jz      short loc_18003590C
0x1800358fe  test    rcx, rcx
0x180035901  jz      short loc_18003590C
0x180035903  cmp     rdx, rcx
0x180035906  jnz     loc_180035C71
0x18003590c  lea     rdx, [rbp+840h+var_888]
0x180035910  mov     rcx, [rbp+840h+var_8A0]
0x180035914  call    ?QueryMarkupAttribute@MarkupCompatibility@consumption@win_musl@@CA?AW4Enum@MarkupAttribute@23@AEBUqualified_name@sax@3@0@Z; win_musl::consumption::MarkupCompatibility::QueryMarkupAttribute(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x180035919  test    eax, eax
0x18003591b  jnz     loc_180035C71
0x180035921  lea     r8, word_1801DC36A
0x180035928  lea     r9, aXmlLang; "xml:lang"
0x18003592f  lea     rax, [r8-2]
0x180035933  cmp     [rax], r13w
0x180035937  jz      loc_180035C45
0x18003593d  mov     r14, qword ptr [rbp+840h+var_860]
0x180035941  mov     rbx, [rbp+840h+Buf1+8]
0x180035945  test    r14, r14
0x180035948  jz      loc_180035F4F
0x18003594e  test    rbx, rbx
0x180035951  jz      loc_180035F4F
0x180035957  cmp     r14, rbx
0x18003595a  jz      loc_180035F4F
0x180035960  mov     rcx, r14
0x180035963  sub     rcx, rbx
0x180035966  sar     rcx, 1
0x180035969  test    r8, r8
0x18003596c  jz      loc_180035F57
0x180035972  cmp     r8, r9
0x180035975  jz      loc_180035F57
0x18003597b  mov     rax, r8
0x18003597e  sub     rax, r9
0x180035981  sar     rax, 1
0x180035984  cmp     rcx, rax
0x180035987  jnz     short loc_1800359D4
0x180035989  test    r14, r14
0x18003598c  jz      loc_180035F7F
0x180035992  test    rbx, rbx
0x180035995  jz      loc_180035F7F
0x18003599b  cmp     r14, rbx
0x18003599e  jz      loc_180035F7F
0x1800359a4  test    r8, r8
0x1800359a7  jz      loc_180035F7F
0x1800359ad  cmp     r8, r9
0x1800359b0  jz      loc_180035F7F
0x1800359b6  mov     r8, r14
0x1800359b9  sub     r8, rbx; Size
0x1800359bc  mov     rdx, r9; Buf2
0x1800359bf  mov     rcx, rbx; Buf1
0x1800359c2  call    memcmp_0
0x1800359c7  test    eax, eax
0x1800359c9  setz    al
0x1800359cc  test    al, al
0x1800359ce  jnz     loc_180035C71
0x1800359d4  lea     r8, dword_1801DC384
0x1800359db  lea     r9, aXmlSpace; "xml:space"
0x1800359e2  lea     rax, [r8-2]
0x1800359e6  cmp     [rax], r13w
0x1800359ea  jz      loc_180035C34
0x1800359f0  test    r14, r14
0x1800359f3  jz      loc_180035F5F
0x1800359f9  test    rbx, rbx
0x1800359fc  jz      loc_180035F5F
0x180035a02  cmp     r14, rbx
0x180035a05  jz      loc_180035F5F
0x180035a0b  mov     rcx, r14
0x180035a0e  sub     rcx, rbx
0x180035a11  sar     rcx, 1
0x180035a14  test    r8, r8
0x180035a17  jz      loc_180035F67
0x180035a1d  cmp     r8, r9
0x180035a20  jz      loc_180035F67
0x180035a26  mov     rax, r8
0x180035a29  sub     rax, r9
0x180035a2c  sar     rax, 1
0x180035a2f  cmp     rcx, rax
0x180035a32  jnz     short loc_180035A7F
0x180035a34  test    r14, r14
0x180035a37  jz      loc_180035FA7
0x180035a3d  test    rbx, rbx
0x180035a40  jz      loc_180035FA7
0x180035a46  cmp     r14, rbx
0x180035a49  jz      loc_180035FA7
0x180035a4f  test    r8, r8
0x180035a52  jz      loc_180035FA7
0x180035a58  cmp     r8, r9
0x180035a5b  jz      loc_180035FA7
0x180035a61  mov     r8, r14
0x180035a64  sub     r8, rbx; Size
0x180035a67  mov     rdx, r9; Buf2
0x180035a6a  mov     rcx, rbx; Buf1
0x180035a6d  call    memcmp_0
0x180035a72  test    eax, eax
0x180035a74  setz    al
0x180035a77  test    al, al
0x180035a79  jnz     loc_180035C71
  ... truncated ...
```
