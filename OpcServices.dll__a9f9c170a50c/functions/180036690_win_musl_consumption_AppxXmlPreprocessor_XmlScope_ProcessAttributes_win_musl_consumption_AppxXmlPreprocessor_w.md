# win_musl::consumption::AppxXmlPreprocessor::XmlScope::ProcessAttributes(win_musl::consumption::AppxXmlPreprocessor &,win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes &)

- ea: `0x180036690`
- end: `0x180037d75`
- name: `?ProcessAttributes@XmlScope@AppxXmlPreprocessor@consumption@win_musl@@QEAA?AVSaxAttributes@34@AEAV234@AEBUqualified_name@sax@4@AEAV534@@Z`
- size: `5861`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180035ce0`

## callees

- `0x18000d950`
- `0x180015a68`
- `0x1800186b8`
- `0x18001a810`
- `0x18001c5d0`
- `0x180026898`
- `0x1800334e4`
- `0x180034820`
- `0x180034880`
- `0x180034c38`
- `0x180034c90`
- `0x180034da8`
- `0x180035130`
- `0x180035198`
- `0x180036690`
- `0x180037d7c`
- `0x180037e90`
- `0x180037fb0`
- `0x180038160`
- `0x180038360`
- `0x180038670`
- `0x180038694`
- `0x180038ba0`
- `0x180038d40`
- `0x180039700`
- `0x18003a5bc`
- `0x18003a8a4`
- `0x1800517a0`
- `0x180067a04`
- `0x180073960`
- `0x180074dac`
- `0x180075cb0`
- `0x180076108`
- `0x180089bf8`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800d5fe4`
- `0x1800ee248`
- `0x180117740`
- `0x18012a010`

## string_xrefs

- `0x180036aa5`: `xml:space`
- `0x180036ae7`: `xml:space`
- `0x180036a27`: `xml:lang`
- `0x180036a73`: `xml:lang`
- `0x180036b9f`: `xmlns`
- `0x18003720d`: `xmlns`
- `0x180037308`: `http://www.w3.org/2000/xmlns/`
- `0x1800374dd`: `http://www.w3.org/2000/xmlns/`
- `0x1800375de`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 *__fastcall win_musl::consumption::AppxXmlPreprocessor::XmlScope::ProcessAttributes(
        win_musl::consumption::AppxXmlPreprocessor::XmlScope *a1,
        __int64 *a2,
        win_musl::consumption::AppxXmlPreprocessor *a3,
        __int64 a4,
        _QWORD *a5)
{
  win_musl::consumption::AppxXmlPreprocessor *v5; // r14
  _BYTE *v7; // r12
  __int64 v8; // r13
  _BYTE *v9; // rax
  _BYTE *v10; // rcx
  _BYTE *v11; // rbx
  bool v12; // di
  _BYTE *v13; // rax
  _BYTE *v14; // rcx
  _BYTE *v15; // rbx
  bool v16; // di
  __int64 *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 v21; // rdi
  _BYTE *v22; // rcx
  _BYTE *v23; // rbx
  _BYTE *v24; // rax
  __int128 *v25; // rax
  const wchar_t *v26; // rdx
  wchar_t *v27; // r9
  wchar_t *v28; // rax
  char *v29; // r8
  char *v30; // r10
  __int64 v31; // rcx
  __int64 v32; // rax
  wchar_t *v33; // r9
  wchar_t *v34; // rax
  win_musl::xml::attribute *v35; // rsi
  __int64 v36; // rcx
  __int64 v37; // rax
  wchar_t *v38; // r9
  wchar_t *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  char *i; // rax
  int *v43; // rcx
  const wchar_t *v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r9
  __int64 (__fastcall *v48)(__int64, __int128 *, int *); // r10
  __int128 v49; // xmm0
  signed int v50; // ebx
  win_musl::consumption::AppxXmlPreprocessor *v51; // rbx
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // r14
  _WORD *v54; // r10
  _WORD *v55; // rsi
  unsigned __int64 v56; // r9
  __int64 v57; // r9
  __int64 v58; // r8
  __int64 v59; // r9
  const struct win_musl::sax::wchar_range **v60; // rcx
  const struct win_musl::sax::wchar_range *v61; // rdx
  const struct win_musl::sax::wchar_range *v62; // r11
  __int64 v63; // rax
  unsigned __int64 v64; // rbx
  const struct win_musl::sax::wchar_range *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  win_musl::xml::attribute *v70; // rsi
  win_musl::consumption::AppxXmlPreprocessor *v71; // r14
  win_musl::consumption::AppxXmlPreprocessor *v72; // r15
  _BYTE *v73; // rax
  _BYTE *v74; // rcx
  _WORD *v75; // rcx
  _WORD *v76; // rcx
  char *v77; // rcx
  const wchar_t *v78; // rdx
  char *v79; // rcx
  const wchar_t *v80; // rdx
  const struct win_musl::sax::wchar_range *v81; // rdx
  _BYTE *v82; // rbx
  bool v83; // di
  _QWORD *v84; // rdi
  _QWORD *v85; // rbx
  unsigned __int64 v86; // r15
  _QWORD *v87; // r15
  unsigned __int64 v88; // rcx
  unsigned __int64 v89; // rbx
  unsigned __int64 v90; // rdx
  void **v91; // rax
  void **v92; // rcx
  __int64 v93; // r8
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // r9
  _WORD *v97; // rax
  __int64 v98; // rax
  const wchar_t *v99; // rax
  __int64 v100; // rax
  const struct win_musl::sax::wchar_range *v101; // rdx
  const struct win_musl::sax::wchar_range *v102; // rax
  unsigned __int64 v103; // rax
  const struct win_musl::sax::wchar_range *v104; // rdx
  win_musl::sax *v105; // r8
  const struct win_musl::sax::attribute *v106; // rax
  __int64 v107; // r8
  const wchar_t *v108; // rax
  win_musl::consumption::AppxXmlPreprocessor *v109; // r13
  win_musl::xml::attribute *v110; // r12
  __int64 v111; // rbx
  void **v112; // rcx
  char *v113; // rdx
  char *v114; // r9
  _QWORD *v115; // rcx
  _QWORD *v116; // r8
  _QWORD *v117; // rcx
  _QWORD *v118; // r8
  _QWORD *v119; // rcx
  _QWORD *v120; // r8
  _QWORD *v121; // rcx
  _QWORD *v122; // r8
  const struct win_musl::sax::wchar_range *v123; // rdx
  win_musl::sax *v124; // r8
  _WORD *v125; // r9
  const wchar_t *v126; // rdx
  _WORD *v127; // rcx
  __int64 v128; // rax
  __int64 v129; // rax
  win_musl::consumption::AppxXmlPreprocessor::XmlScope *v130; // rbx
  __int64 v131; // rdx
  __int64 v132; // r8
  __int64 v133; // r12
  char *v134; // rdx
  __int64 *v135; // rbx
  __int64 v136; // rdx
  __int64 v137; // r8
  char *v138; // rbx
  win_musl::xml::attribute *v139; // rdi
  win_musl::xml::attribute *v140; // rdi
  win_musl::xml::attribute *j; // rbx
  __int64 v142; // r9
  __int64 v143; // r11
  __int64 v144; // r9
  __int64 v145; // r11
  __int64 v146; // r9
  __int64 v147; // r11
  const struct win_musl::sax::wchar_range *v148; // rdx
  void **v149; // rcx
  const struct win_musl::sax::wchar_range *v150; // rdx
  _BYTE *v151; // [rsp+40h] [rbp-C0h] BYREF
  int v152; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v153; // [rsp+50h] [rbp-B0h] BYREF
  win_musl::consumption::AppxXmlPreprocessor *v154; // [rsp+60h] [rbp-A0h] BYREF
  win_musl::xml::attribute *v155; // [rsp+68h] [rbp-98h] BYREF
  __int128 v156; // [rsp+70h] [rbp-90h] BYREF
  win_musl::consumption::AppxXmlPreprocessor::XmlScope *v157; // [rsp+80h] [rbp-80h]
  char v158[8]; // [rsp+88h] [rbp-78h] BYREF
  win_musl::xml::attribute *v159[2]; // [rsp+90h] [rbp-70h]
  __int64 v160; // [rsp+A0h] [rbp-60h]
  _BYTE *v161; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v162; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v163; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v164[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v165; // [rsp+108h] [rbp+8h]
  unsigned __int64 v166; // [rsp+110h] [rbp+10h]
  _QWORD v167[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v168; // [rsp+130h] [rbp+30h]
  char *v169; // [rsp+140h] [rbp+40h] BYREF
  char *v170; // [rsp+148h] [rbp+48h]
  __int128 v171; // [rsp+150h] [rbp+50h] BYREF
  const wchar_t *v172; // [rsp+160h] [rbp+60h] BYREF
  void *v173[2]; // [rsp+168h] [rbp+68h]
  __int64 v174; // [rsp+178h] [rbp+78h]
  const wchar_t *v175; // [rsp+188h] [rbp+88h]
  const wchar_t *v176; // [rsp+190h] [rbp+90h]
  __int64 v177; // [rsp+198h] [rbp+98h]
  _QWORD v178[11]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v179; // [rsp+1F8h] [rbp+F8h]
  _QWORD v180[11]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v181; // [rsp+268h] [rbp+168h]
  __int64 v182; // [rsp+270h] [rbp+170h]
  char v183[8]; // [rsp+280h] [rbp+180h] BYREF
  void *v184[2]; // [rsp+288h] [rbp+188h] BYREF
  unsigned __int64 v185; // [rsp+298h] [rbp+198h]
  unsigned __int64 v186; // [rsp+2A0h] [rbp+1A0h]
  void *pExceptionObject[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v188; // [rsp+2C0h] [rbp+1C0h]
  __int128 v189; // [rsp+2D0h] [rbp+1D0h]
  __int128 v190; // [rsp+2E0h] [rbp+1E0h]
  __int128 v191; // [rsp+2F0h] [rbp+1F0h]
  char v192[8]; // [rsp+350h] [rbp+250h] BYREF
  void *v193; // [rsp+358h] [rbp+258h]
  __int64 v194; // [rsp+368h] [rbp+268h]
  unsigned __int64 v195; // [rsp+370h] [rbp+270h]
  char v196[8]; // [rsp+378h] [rbp+278h] BYREF
  void *v197; // [rsp+380h] [rbp+280h]
  __int64 v198; // [rsp+390h] [rbp+290h]
  unsigned __int64 v199; // [rsp+398h] [rbp+298h]
  wchar_t v200[20]; // [rsp+3A0h] [rbp+2A0h] BYREF
  char v201[40]; // [rsp+3C8h] [rbp+2C8h] BYREF
  char v202[8]; // [rsp+3F0h] [rbp+2F0h] BYREF
  void *Block; // [rsp+3F8h] [rbp+2F8h]
  __int64 v204; // [rsp+408h] [rbp+308h]
  unsigned __int64 v205; // [rsp+410h] [rbp+310h]
  _BYTE v206[40]; // [rsp+418h] [rbp+318h] BYREF
  char v207[864]; // [rsp+440h] [rbp+340h] BYREF

  v177 = -2;
  v5 = a3;
  v154 = a3;
  v168 = a2;
  v157 = a1;
  *(_QWORD *)&v153 = a2;
  *(_OWORD *)v159 = 0;
  v160 = 0;
  win_musl::consumption::SaxAttributes::sequence(a5, v167);
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(v167, &v161);
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::end(v167, v180);
  v155 = (win_musl::consumption::AppxXmlPreprocessor::XmlScope *)((char *)a1 + 8);
  v7 = (_BYTE *)v180[0];
  v8 = v182;
  while ( 1 )
  {
    *(_QWORD *)&v153 = &v151;
    v9 = 0;
    v151 = 0;
    if ( v7 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 8LL))(v7);
      v10 = v7;
      v9 = v151;
    }
    else
    {
      v10 = 0;
    }
    v151 = v10;
    if ( v9 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v9 + 16LL))(v9);
      v10 = v151;
    }
    v11 = v161;
    if ( v161 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v161 + 8LL))(v161);
      v10 = v151;
    }
    v12 = v11 == v10;
    if ( v11 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v11 + 16LL))(v11);
      v10 = v151;
    }
    if ( v10 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v12 && v165 == v181 && v166 == v8 )
      break;
    v21 = v165;
    if ( v165 >= v166 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x320u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"SaxAttributes::SaxAttributeSequence index out of range");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v22 = 0;
    v151 = 0;
    v23 = v161;
    if ( v161 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v161 + 8LL))(v161);
      v22 = v151;
    }
    v151 = v23;
    if ( v22 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = v151;
    }
    *(_QWORD *)&v153 = &v151;
    if ( v23 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 8LL))(v23);
      v24 = v23;
      v23 = v151;
    }
    else
    {
      v24 = 0;
    }
    *(_QWORD *)&v153 = v24;
    if ( v23 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 16LL))(v23);
      v23 = 0;
      v151 = 0;
    }
    v152 = 1;
    v25 = (__int128 *)win_musl::consumption::SaxAttributes::SaxQuery(&v153, pExceptionObject, v21, &v152);
    v162 = *v25;
    v163 = v25[1];
    v164[0] = v25[2];
    v164[1] = v25[3];
    v164[2] = v25[4];
    if ( v152 == 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x329u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"SaxAttributes::SaxAttributeSequence SaxQuery failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( (_QWORD)v153 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v153 + 16LL))(v153);
    if ( *((_QWORD *)v5 + 6) == 2 )
    {
      v175 = L"IgnorableNamespaces";
      v108 = L"http://www.w3.org/2000/xmlns/";
      v176 = L"http://www.w3.org/2000/xmlns/";
      do
      {
        if ( *--v108 )
          break;
        v176 = v108;
      }
      while ( v108 != L"IgnorableNamespaces" );
      if ( (unsigned __int8)win_musl::sax::operator==((win_musl::sax *)&v163) )
        break;
    }
    v27 = (wchar_t *)word_180139A82;
    do
    {
      v28 = v27 - 1;
      if ( *(v27 - 1) )
        break;
      --v27;
    }
    while ( v28 != L"xml:lang" );
    v29 = (char *)*((_QWORD *)&v164[0] + 1);
    v7 = (_BYTE *)v180[0];
    v30 = *(char **)&v164[0];
    if ( *((_QWORD *)&v164[0] + 1) && *(_QWORD *)&v164[0] && *((_QWORD *)&v164[0] + 1) != *(_QWORD *)&v164[0] )
      v31 = (__int64)(*((_QWORD *)&v164[0] + 1) - *(_QWORD *)&v164[0]) >> 1;
    else
      v31 = (__int64)v23;
    if ( !v27 || v27 == L"xml:lang" )
      v32 = (__int64)v23;
    else
      v32 = v27 - L"xml:lang";
    if ( v31 == v32 )
    {
      if ( *((_QWORD *)&v164[0] + 1)
        && *(_QWORD *)&v164[0]
        && *((_QWORD *)&v164[0] + 1) != *(_QWORD *)&v164[0]
        && v27
        && v27 != L"xml:lang" )
      {
        v26 = L"xml:lang";
        v76 = *(_WORD **)&v164[0];
        do
        {
          if ( *v76 != *v26 )
            break;
          ++v76;
          ++v26;
        }
        while ( v76 != *((_WORD **)&v164[0] + 1) );
        if ( v76 == *((_WORD **)&v164[0] + 1) )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)v164, (const struct win_musl::sax::wchar_range *)v26)
             && (!v142 || v142 == v143) )
      {
        break;
      }
    }
    v33 = (wchar_t *)&dword_180139A44;
    do
    {
      v34 = v33 - 1;
      if ( *(v33 - 1) )
        break;
      --v33;
    }
    while ( v34 != L"xml:space" );
    v35 = v155;
    if ( v29 && v30 && v29 != v30 )
      v36 = (v29 - v30) >> 1;
    else
      v36 = (__int64)v23;
    if ( !v33 || v33 == L"xml:space" )
      v37 = (__int64)v23;
    else
      v37 = v33 - L"xml:space";
    if ( v36 == v37 )
    {
      if ( v29 && v30 && v29 != v30 && v33 && v33 != L"xml:space" )
      {
        v26 = L"xml:space";
        v77 = v30;
        do
        {
          if ( *(_WORD *)v77 != *v26 )
            break;
          v77 += 2;
          ++v26;
        }
        while ( v77 != v29 );
        if ( v77 == v29 )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)v164, (const struct win_musl::sax::wchar_range *)v26)
             && (!v144 || v144 == v145) )
      {
        break;
      }
    }
    v38 = (wchar_t *)&word_180139A6E;
    do
    {
      v39 = v38 - 1;
      if ( *(v38 - 1) )
        break;
      --v38;
    }
    while ( v39 != L"xs:processContents" );
    v8 = v182;
    if ( v29 && v30 && v29 != v30 )
      v40 = (v29 - v30) >> 1;
    else
      v40 = (__int64)v23;
    if ( !v38 || v38 == L"xs:processContents" )
      v41 = (__int64)v23;
    else
      v41 = v38 - L"xs:processContents";
    if ( v40 == v41 )
    {
      if ( v29 && v30 && v29 != v30 && v38 && v38 != L"xs:processContents" )
      {
        v78 = L"xs:processContents";
        v79 = v30;
        do
        {
          if ( *(_WORD *)v79 != *v78 )
            break;
          v79 += 2;
          ++v78;
        }
        while ( v79 != v29 );
        if ( v79 == v29 )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)v164, (const struct win_musl::sax::wchar_range *)v26)
             && (!v146 || v146 == v147) )
      {
        break;
      }
    }
    for ( i = v30; i != v29; i += 2 )
    {
      if ( *(_WORD *)i == 58 )
        break;
    }
    v172 = L"xmlns";
    v43 = &dword_180139A94;
    v173[0] = &dword_180139A94;
    do
    {
      v44 = (const wchar_t *)v43 - 1;
      if ( *((_WORD *)v43 - 1) )
        break;
      v43 = (int *)((char *)v43 - 2);
    }
    while ( v44 != L"xmlns" );
    v173[0] = v43;
    v169 = v30;
    v170 = i;
    if ( i && v30 && i != v30 )
      v45 = (i - v30) >> 1;
    else
      v45 = (__int64)v23;
    if ( !v43 || v43 == (int *)L"xmlns" )
      v46 = (__int64)v23;
    else
      v46 = ((char *)v43 - (char *)L"xmlns") >> 1;
    if ( v45 == v46 )
    {
      if ( i && v30 && i != v30 && v43 && v43 != (int *)L"xmlns" )
      {
        v80 = L"xmlns";
        if ( v30 == i )
          break;
        do
        {
          if ( *(_WORD *)v30 != *v80 )
            break;
          v30 += 2;
          ++v80;
        }
        while ( v30 != i );
        if ( v30 == i )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)&v169, (const struct win_musl::sax::wchar_range *)v46)
             && win_musl::sax::wchar_range_empty((win_musl::sax *)&v172, v148) )
      {
        break;
      }
    }
    v152 = (int)v23;
    v47 = *(_QWORD *)v35;
    v48 = *(__int64 (__fastcall **)(__int64, __int128 *, int *))(**(_QWORD **)v35 + 32LL);
    if ( *((_QWORD *)&v162 + 1) && (_QWORD)v162 && *((_QWORD *)&v162 + 1) != (_QWORD)v162 )
    {
      DWORD1(v156) = (_DWORD)v23;
      *((_QWORD *)&v156 + 1) = v162;
      LODWORD(v156) = (__int64)(*((_QWORD *)&v162 + 1) - v162) >> 1;
      v49 = v156;
    }
    else
    {
      v49 = 0;
      v156 = 0;
    }
    v153 = v49;
    v50 = v48(v47, &v153, &v152);
    if ( v50 < 0 )
    {
      memset_0(v200, 0, 0x400u);
      StringCchPrintfW(v200, 0x200u, L"Call to IsKnownNamespace failed with HResult 0x%X.", (unsigned int)v50);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x68u,
        v50,
        (struct win_musl::TStringEllipseBase *)v200);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !v152 )
    {
      v51 = v154;
      v52 = *((_QWORD *)v154 + 5);
      v53 = v52 + *((_QWORD *)v154 + 6);
      v54 = (_WORD *)*((_QWORD *)&v162 + 1);
      v55 = (_WORD *)v162;
      while ( v52 != v53 )
      {
        v56 = v52;
        if ( *((_QWORD *)v51 + 4) <= v52 )
          v56 = v52 - *((_QWORD *)v51 + 4);
        v57 = *(_QWORD *)(*((_QWORD *)v51 + 3) + 8 * v56);
        v58 = *(_QWORD *)(v57 + 40);
        v59 = *(_QWORD *)(v57 + 48);
        while ( v58 != v59 )
        {
          v60 = (const struct win_musl::sax::wchar_range **)(v58 + 8);
          if ( *(_QWORD *)(v58 + 32) < 8u )
          {
            v61 = (const struct win_musl::sax::wchar_range *)(v58 + 8);
            *(_QWORD *)&v171 = v58 + 8;
            v62 = (const struct win_musl::sax::wchar_range *)(v58 + 8);
          }
          else
          {
            v61 = *v60;
            *(_QWORD *)&v171 = v61;
            v60 = (const struct win_musl::sax::wchar_range **)v61;
            v62 = v61;
          }
          v63 = *(_QWORD *)(v58 + 24);
          v64 = (unsigned __int64)v60 + 2 * v63;
          *((_QWORD *)&v171 + 1) = v64;
          if ( v62 == (const struct win_musl::sax::wchar_range *)v64 )
          {
            v171 = 0;
            v65 = 0;
            v64 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
            v61 = 0;
          }
          else
          {
            v65 = (const struct win_musl::sax::wchar_range *)((char *)v60 + 2 * v63);
          }
          if ( v54 && v55 && v54 != v55 )
            v66 = v54 - v55;
          else
            v66 = 0;
          if ( v65 && v61 && v65 != v61 )
            v67 = (v65 - v61) >> 1;
          else
            v67 = 0;
          if ( v66 == v67 )
          {
            if ( v54 && v55 && v54 != v55 && v64 && v61 && (const struct win_musl::sax::wchar_range *)v64 != v61 )
            {
              v75 = v55;
              do
              {
                if ( *v75 != *(_WORD *)v61 )
                  break;
                ++v75;
                v61 = (const struct win_musl::sax::wchar_range *)((char *)v61 + 2);
              }
              while ( v75 != v54 );
              if ( v75 == v54 )
                goto LABEL_15;
            }
            else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)&v162, v61)
                   && win_musl::sax::wchar_range_empty((win_musl::sax *)&v171, v81) )
            {
              goto LABEL_15;
            }
          }
          v58 += 80;
        }
        ++v52;
        v51 = v154;
      }
      v5 = v154;
    }
    ++v165;
  }
LABEL_15:
  *(_QWORD *)&v153 = &v151;
  v13 = 0;
  v151 = 0;
  if ( v7 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 8LL))(v7);
    v14 = v7;
    v13 = v151;
  }
  else
  {
    v14 = 0;
  }
  v151 = v14;
  if ( v13 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v13 + 16LL))(v13);
    v14 = v151;
  }
  v15 = v161;
  if ( v161 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v161 + 8LL))(v161);
    v14 = v151;
  }
  else
  {
    v15 = 0;
  }
  v16 = v15 == v14;
  if ( v15 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v15 + 16LL))(v15);
    v14 = v151;
  }
  if ( v14 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v16 && v165 == v181 && v166 == v8 )
  {
    v17 = v168;
    *v168 = 0;
    v18 = *a5;
    if ( *a5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*a5);
    else
      v18 = 0;
    v19 = *v17;
    *v17 = v18;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v7 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v161 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v161 + 16LL))(v161);
      v161 = 0;
    }
    if ( v167[0] )
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v167[0] + 16LL))(v167[0], *(_QWORD *)v167[0]);
    return v17;
  }
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(v167, v178);
  for ( ;
        (unsigned __int8)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(
                           v178,
                           &v161);
        ++v179 )
  {
    v68 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v178, v179);
    v69 = win_musl::XmlAttributeFromSaxAttribute(v200, v68);
    std::vector<win_musl::xml::attribute>::push_back(v158, v69);
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v200);
  }
  *(_OWORD *)v173 = 0;
  v174 = 0;
  v70 = v159[1];
  v71 = v159[0];
  v72 = v154;
  while ( 1 )
  {
    *(_QWORD *)&v153 = &v151;
    v73 = 0;
    v151 = 0;
    if ( v7 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 8LL))(v7);
      v74 = v7;
      v73 = v151;
    }
    else
    {
      v74 = 0;
    }
    v151 = v74;
    if ( v73 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v73 + 16LL))(v73);
      v74 = v151;
    }
    v82 = v161;
    if ( v161 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v161 + 8LL))(v161);
      v74 = v151;
    }
    v83 = v82 == v74;
    if ( v82 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v82 + 16LL))(v82);
      v74 = v151;
    }
    if ( v74 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v74 + 16LL))(v74);
    if ( v83 && v165 == v181 && v166 == v8 )
      break;
    v98 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v161, v165);
    win_musl::XmlAttributeFromSaxAttribute(v200, v98);
    if ( *((_QWORD *)v72 + 6) == 2 )
    {
      *(_QWORD *)&v156 = L"IgnorableNamespaces";
      v99 = L"http://www.w3.org/2000/xmlns/";
      *((_QWORD *)&v156 + 1) = L"http://www.w3.org/2000/xmlns/";
      do
      {
        if ( *--v99 )
          break;
        *((_QWORD *)&v156 + 1) = v99;
      }
      while ( v99 != L"IgnorableNamespaces" );
      v100 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v161, v165);
      v102 = (const struct win_musl::sax::wchar_range *)win_musl::sax::wchar_range_size(
                                                          (win_musl::sax *)(v100 + 16),
                                                          v101);
      v103 = win_musl::sax::wchar_range_size((win_musl::sax *)&v156, v102);
      if ( v104 == (const struct win_musl::sax::wchar_range *)v103 )
      {
        if ( win_musl::sax::wchar_range_empty(v105, v104)
          || win_musl::sax::wchar_range_empty((win_musl::sax *)&v156, v123) )
        {
          if ( win_musl::sax::wchar_range_empty(v124, v123)
            && win_musl::sax::wchar_range_empty((win_musl::sax *)&v156, v150) )
          {
            goto LABEL_289;
          }
        }
        else
        {
          v125 = (_WORD *)*((_QWORD *)v124 + 1);
          v126 = L"IgnorableNamespaces";
          v127 = *(_WORD **)v124;
          if ( *(_WORD **)v124 == v125 )
            goto LABEL_289;
          do
          {
            if ( *v127 != *v126 )
              break;
            ++v127;
            ++v126;
          }
          while ( v127 != v125 );
          if ( v127 == v125 )
          {
LABEL_289:
            v128 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                     &v161,
                     v165);
            win_musl::consumption::AppxXmlPreprocessor::ParsePrefixList(v72, v128 + 64, &v172);
            goto LABEL_250;
          }
        }
      }
    }
    v106 = (const struct win_musl::sax::attribute *)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                                                      &v161,
                                                      v165);
    if ( !win_musl::consumption::AppxXmlPreprocessor::XmlScope::ParseXmlAttribute(v157, v106) )
    {
      if ( v71 && 0x8F5C28F5C28F5C29uLL * ((v70 - v71) >> 3) < 0x8F5C28F5C28F5C29uLL * ((v160 - (__int64)v71) >> 3) )
      {
        std::_Uninit_fill_n<win_musl::xml::attribute *,unsigned __int64,win_musl::xml::attribute,std::allocator<win_musl::xml::attribute>>(v70);
        v70 = (win_musl::xml::attribute *)((char *)v70 + 200);
        v159[1] = v70;
      }
      else
      {
        std::vector<win_musl::xml::attribute>::_Insert_n(v158, v70, v107, v200);
        v70 = v159[1];
        v71 = v159[0];
      }
    }
LABEL_250:
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v206);
    if ( v205 >= 8 )
      operator delete(Block);
    v205 = 7;
    v204 = 0;
    LOWORD(Block) = 0;
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v200);
    ++v165;
  }
  v84 = (_QWORD *)*((_QWORD *)v157 + 9);
  v85 = (_QWORD *)*v84;
  *(_QWORD *)&v153 = *v84;
  v86 = 0;
  while ( v85 != v84 )
  {
    std::wstring::wstring(v183, L"xmlns");
    v87 = v85 + 3;
    if ( v85[6] )
    {
      v88 = v185;
      if ( v185 == -1 || v185 == -2 )
        std::_String_base::_Xlen();
      v89 = v185 + 1;
      if ( v185 + 1 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      v90 = v186;
      if ( v186 < v89 )
      {
        std::wstring::_Copy(v183, v185 + 1, v185);
        v90 = v186;
        v88 = v185;
        if ( v89 )
        {
LABEL_224:
          v91 = v184;
          if ( v90 >= 8 )
            v91 = (void **)v184[0];
          *((_WORD *)v91 + v88) = 58;
          v92 = v184;
          if ( v186 >= 8 )
            v92 = (void **)v184[0];
          v185 = v89;
          *((_WORD *)v92 + v89) = 0;
        }
      }
      else
      {
        if ( v185 != -1 )
          goto LABEL_224;
        v149 = v184;
        if ( v186 >= 8 )
          v149 = (void **)v184[0];
        v185 = 0;
        *(_WORD *)v149 = 0;
      }
      std::wstring::append(v183, v87, 0, -1);
    }
    std::wstring::wstring(pExceptionObject, &psz);
    std::wstring::wstring(v196, &psz);
    std::wstring::wstring(v192, L"http://www.w3.org/2000/xmlns/");
    std::wstring::wstring(v200, v192);
    std::wstring::wstring(v201, v196);
    std::wstring::wstring(v202, v183);
    v151 = v206;
    std::wstring::wstring(v206, pExceptionObject);
    std::wstring::wstring(v207, v87 + 5);
    if ( v71 && 0x8F5C28F5C28F5C29uLL * ((v70 - v71) >> 3) < 0x8F5C28F5C28F5C29uLL * ((v160 - (__int64)v71) >> 3) )
    {
      std::_Uninit_fill_n<win_musl::xml::attribute *,unsigned __int64,win_musl::xml::attribute,std::allocator<win_musl::xml::attribute>>(v70);
      v70 = (win_musl::xml::attribute *)((char *)v70 + 200);
      v159[1] = v70;
    }
    else
    {
      std::vector<win_musl::xml::attribute>::_Insert_n(v158, v70, v93, v200);
      v70 = v159[1];
      v71 = v159[0];
    }
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v206);
    if ( v205 >= 8 )
      operator delete(Block);
    v205 = 7;
    v97 = (_WORD *)std::wstring::_Myptr(v202, v94, v95, v96);
    v86 = 0;
    v204 = 0;
    *v97 = 0;
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v200);
    if ( v195 >= 8 )
      operator delete(v193);
    v195 = 7;
    v194 = 0;
    LOWORD(v193) = 0;
    if ( v199 >= 8 )
      operator delete(v197);
    v199 = 7;
    v198 = 0;
    LOWORD(v197) = 0;
    if ( (unsigned __int64)v189 >= 8 )
      operator delete(pExceptionObject[1]);
    if ( v186 >= 8 )
      operator delete(v184[0]);
    LOWORD(v184[0]) = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,win_musl::xml::ns,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,win_musl::xml::ns>>,0>>::const_iterator::_Inc(&v153);
    v85 = (_QWORD *)v153;
  }
  v109 = v154;
  win_musl::consumption::AppxXmlPreprocessor::ResolvePrefixes(v154, &v172, (char *)v157 + 32);
  v110 = v155;
  while ( v71 && v86 < 0x8F5C28F5C28F5C29uLL * ((v70 - v71) >> 3) )
  {
    v111 = 200 * v86;
    v112 = (void **)((char *)v71 + 200 * v86 + 8);
    if ( *((_QWORD *)v71 + 25 * v86 + 4) < 8u )
    {
      v113 = (char *)v71 + 200 * v86 + 8;
      pExceptionObject[0] = v113;
    }
    else
    {
      v113 = (char *)*v112;
      pExceptionObject[0] = v113;
      v112 = (void **)v113;
    }
    v114 = (char *)v112 + 2 * *(_QWORD *)((char *)v71 + v111 + 24);
    pExceptionObject[1] = v114;
    if ( v113 == v114 )
    {
      *(_OWORD *)pExceptionObject = 0;
      v114 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v113 = 0;
    }
    v115 = (_QWORD *)((char *)v71 + v111 + 48);
    if ( *(_QWORD *)((char *)v71 + v111 + 72) < 8u )
    {
      *(_QWORD *)&v188 = (char *)v71 + v111 + 48;
      v116 = (_QWORD *)v188;
    }
    else
    {
      v116 = (_QWORD *)*v115;
      *(_QWORD *)&v188 = v116;
      v115 = v116;
    }
    *((_QWORD *)&v188 + 1) = (char *)v115 + 2 * *(_QWORD *)((char *)v71 + v111 + 64);
    if ( v116 == *((_QWORD **)&v188 + 1) )
      v188 = 0;
    v117 = (_QWORD *)((char *)v71 + v111 + 88);
    if ( *(_QWORD *)((char *)v71 + v111 + 112) < 8u )
    {
      *(_QWORD *)&v189 = (char *)v71 + v111 + 88;
      v118 = (_QWORD *)v189;
    }
    else
    {
      v118 = (_QWORD *)*v117;
      *(_QWORD *)&v189 = v118;
      v117 = v118;
    }
    *((_QWORD *)&v189 + 1) = (char *)v117 + 2 * *(_QWORD *)((char *)v71 + v111 + 104);
    if ( v118 == *((_QWORD **)&v189 + 1) )
      v189 = 0;
    v119 = (_QWORD *)((char *)v71 + v111 + 128);
    if ( *(_QWORD *)((char *)v71 + v111 + 152) < 8u )
    {
      *(_QWORD *)&v190 = (char *)v71 + v111 + 128;
      v120 = (_QWORD *)v190;
    }
    else
    {
      v120 = (_QWORD *)*v119;
      *(_QWORD *)&v190 = v120;
      v119 = v120;
    }
    *((_QWORD *)&v190 + 1) = (char *)v119 + 2 * *(_QWORD *)((char *)v71 + v111 + 144);
    if ( v120 == *((_QWORD **)&v190 + 1) )
      v190 = 0;
    v121 = (_QWORD *)((char *)v71 + v111 + 168);
    if ( *(_QWORD *)((char *)v71 + v111 + 192) < 8u )
    {
      *(_QWORD *)&v191 = (char *)v71 + v111 + 168;
      v122 = (_QWORD *)v191;
    }
    else
    {
      v122 = (_QWORD *)*v121;
      *(_QWORD *)&v191 = v122;
      v121 = v122;
    }
    *((_QWORD *)&v191 + 1) = (char *)v121 + 2 * *(_QWORD *)((char *)v71 + v111 + 184);
    if ( v122 == *((_QWORD **)&v191 + 1) )
      v191 = 0;
    v169 = v113;
    v170 = v114;
    if ( (unsigned __int8)win_musl::consumption::MarkupQuery::IsKnownNamespace(v110, &v169)
      || !win_musl::consumption::AppxXmlPreprocessor::Ignorable(
            v109,
            (const struct win_musl::sax::local_name *)pExceptionObject) )
    {
      ++v86;
    }
    else
    {
      v138 = (char *)v71 + v111;
      v139 = (win_musl::xml::attribute *)(v138 + 200);
      if ( v138 + 200 != (char *)v70 )
      {
        do
        {
          win_musl::xml::attribute::operator=(v138, v139);
          v138 += 200;
          v139 = (win_musl::xml::attribute *)((char *)v139 + 200);
        }
        while ( v139 != v70 );
      }
      v140 = v70;
      v70 = (win_musl::xml::attribute *)((char *)v70 - 200);
      for ( j = v70; j != v140; j = (win_musl::xml::attribute *)((char *)j + 200) )
        win_musl::xml::attribute::~attribute(j);
      v159[1] = v70;
    }
  }
  v154 = v71;
  v155 = v70;
  v129 = win_musl::consumption::detail::CreateSaxAttributesCopy<std::_Vector_iterator<win_musl::xml::attribute>>(
           &v153,
           &v154,
           &v155);
  v130 = v157;
  win_scope::scope<win_musl::CommandBase *,win_scope::const_policies<win_scope::com_policies>>::operator=(
    (char *)v157 + 24,
    v129);
  v133 = v180[0];
  if ( (_QWORD)v153 )
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v153, v131, v132);
  v134 = (char *)v130 + 24;
  v135 = v168;
  win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
    v168,
    v134);
  if ( v173[0] )
    operator delete(v173[0]);
  if ( v178[0] )
  {
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v178, v136, v137);
    v178[0] = 0;
  }
  if ( v133 )
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v180, v136, v137);
  if ( v161 )
  {
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v161, v136, v137);
    v161 = 0;
  }
  if ( v167[0] )
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v167, v136, v137);
  std::vector<win_musl::xml::attribute>::_Tidy(v158);
  return v135;
}

```

## disassembly

```asm
0x180036690  push    rbp
0x180036692  push    rsi
0x180036693  push    rdi
0x180036694  push    r12
0x180036696  push    r13
0x180036698  push    r14
0x18003669a  push    r15
0x18003669c  lea     rbp, [rsp-6B0h]
0x1800366a4  sub     rsp, 7B0h
0x1800366ab  mov     [rbp+6E0h+var_648], 0FFFFFFFFFFFFFFFEh
0x1800366b6  mov     [rsp+7E0h+arg_18], rbx
0x1800366be  mov     rax, cs:__security_cookie
0x1800366c5  xor     rax, rsp
0x1800366c8  mov     [rbp+6E0h+var_40], rax
0x1800366cf  mov     r14, r8
0x1800366d2  mov     [rsp+7E0h+var_780], r8
0x1800366d7  mov     [rbp+6E0h+var_6B0], rdx
0x1800366db  mov     rbx, rcx
0x1800366de  mov     [rbp+6E0h+var_760], rcx
0x1800366e2  mov     r15, [rbp+6E0h+arg_20]
0x1800366e9  mov     qword ptr [rsp+7E0h+var_790], rdx
0x1800366ee  xorps   xmm0, xmm0
0x1800366f1  movdqu  xmmword ptr [rbp+6E0h+var_750], xmm0
0x1800366f6  mov     [rbp+6E0h+var_740], 0
0x1800366fe  lea     rdx, [rbp+6E0h+var_6C0]
0x180036702  mov     rcx, r15
0x180036705  call    ?sequence@SaxAttributes@consumption@win_musl@@QEAA?AVSaxAttributeSequence@123@XZ; win_musl::consumption::SaxAttributes::sequence(void)
0x18003670a  nop
0x18003670b  lea     rdx, [rbp+6E0h+var_730]
0x18003670f  lea     rcx, [rbp+6E0h+var_6C0]
0x180036713  call    ?begin@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA?AVSaxAttributeIterator@1234@XZ; win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(void)
0x180036718  nop
0x180036719  lea     rdx, [rbp+6E0h+var_5D0]
0x180036720  lea     rcx, [rbp+6E0h+var_6C0]
0x180036724  call    ?end@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA?AVSaxAttributeIterator@1234@XZ; win_musl::consumption::SaxAttributes::SaxAttributeSequence::end(void)
0x180036729  nop
0x18003672a  lea     rsi, [rbx+8]
0x18003672e  mov     [rsp+7E0h+var_778], rsi
0x180036733  mov     r12, [rbp+6E0h+var_5D0]
0x18003673a  mov     r13, [rbp+6E0h+var_570]
0x180036741  lea     rax, [rsp+7E0h+var_7A0]
0x180036746  mov     qword ptr [rsp+7E0h+var_790], rax
0x18003674b  xor     eax, eax
0x18003674d  mov     [rsp+7E0h+var_7A0], rax
0x180036752  test    r12, r12
0x180036755  jz      loc_180036D54
0x18003675b  mov     rax, [r12]
0x18003675f  mov     rcx, r12
0x180036762  mov     rax, [rax+8]
0x180036766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003676b  mov     rcx, r12
0x18003676e  mov     rax, [rsp+7E0h+var_7A0]
0x180036773  mov     [rsp+7E0h+var_7A0], rcx
0x180036778  test    rax, rax
0x18003677b  jz      short loc_180036794
0x18003677d  mov     rcx, [rax]
0x180036780  mov     rdx, [rcx+10h]
0x180036784  mov     rcx, rax
0x180036787  mov     rax, rdx
0x18003678a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003678f  mov     rcx, [rsp+7E0h+var_7A0]
0x180036794  mov     rbx, [rbp+6E0h+var_730]
0x180036798  test    rbx, rbx
0x18003679b  jz      short loc_1800367B1
0x18003679d  mov     rax, [rbx]
0x1800367a0  mov     rcx, rbx
0x1800367a3  mov     rax, [rax+8]
0x1800367a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367ac  mov     rcx, [rsp+7E0h+var_7A0]
0x1800367b1  cmp     rbx, rcx
0x1800367b4  setz    dil
0x1800367b8  test    rbx, rbx
0x1800367bb  jz      short loc_1800367D1
0x1800367bd  mov     rax, [rbx]
0x1800367c0  mov     rcx, rbx
0x1800367c3  mov     rax, [rax+10h]
0x1800367c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367cc  mov     rcx, [rsp+7E0h+var_7A0]
0x1800367d1  test    rcx, rcx
0x1800367d4  jz      short loc_1800367E3
0x1800367d6  mov     rax, [rcx]
0x1800367d9  mov     rax, [rax+10h]
0x1800367dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367e2  nop
0x1800367e3  test    dil, dil
0x1800367e6  jz      loc_18003692A
0x1800367ec  mov     rax, [rbp+6E0h+var_578]
0x1800367f3  cmp     [rbp+6E0h+var_6D8], rax
0x1800367f7  jnz     loc_18003692A
0x1800367fd  cmp     [rbp+6E0h+var_6D0], r13
0x180036801  jnz     loc_18003692A
0x180036807  lea     rax, [rsp+7E0h+var_7A0]
0x18003680c  mov     qword ptr [rsp+7E0h+var_790], rax
0x180036811  xor     r14d, r14d
0x180036814  mov     eax, r14d
0x180036817  mov     [rsp+7E0h+var_7A0], rax
0x18003681c  test    r12, r12
0x18003681f  jnz     loc_180036D5B
0x180036825  mov     ecx, r14d
0x180036828  mov     [rsp+7E0h+var_7A0], rcx
0x18003682d  test    rax, rax
0x180036830  jnz     loc_180036DA2
0x180036836  mov     rbx, [rbp+6E0h+var_730]
0x18003683a  test    rbx, rbx
0x18003683d  jnz     loc_180036D78
0x180036843  mov     rbx, r14
0x180036846  cmp     rbx, rcx
0x180036849  setz    dil
0x18003684d  test    rbx, rbx
0x180036850  jz      short loc_180036866
0x180036852  mov     rax, [rbx]
0x180036855  mov     rcx, rbx
0x180036858  mov     rax, [rax+10h]
0x18003685c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036861  mov     rcx, [rsp+7E0h+var_7A0]
0x180036866  test    rcx, rcx
0x180036869  jnz     loc_180036D91
0x18003686f  test    dil, dil
0x180036872  jz      loc_180036DE3
0x180036878  mov     rax, [rbp+6E0h+var_578]
0x18003687f  cmp     [rbp+6E0h+var_6D8], rax
0x180036883  jnz     loc_180036DE3
0x180036889  cmp     [rbp+6E0h+var_6D0], r13
0x18003688d  jnz     loc_180036DE3
0x180036893  mov     rsi, [rbp+6E0h+var_6B0]
0x180036897  mov     [rsi], r14
0x18003689a  mov     rbx, [r15]
0x18003689d  test    rbx, rbx
0x1800368a0  jnz     loc_180036DBE
0x1800368a6  mov     rbx, r14
0x1800368a9  mov     rcx, [rsi]
0x1800368ac  mov     [rsi], rbx
0x1800368af  test    rcx, rcx
0x1800368b2  jnz     loc_180036DD2
0x1800368b8  test    r12, r12
0x1800368bb  jz      short loc_1800368CE
0x1800368bd  mov     rax, [r12]
0x1800368c1  mov     rcx, r12
0x1800368c4  mov     rax, [rax+10h]
0x1800368c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368cd  nop
0x1800368ce  mov     rcx, [rbp+6E0h+var_730]
0x1800368d2  test    rcx, rcx
0x1800368d5  jz      short loc_1800368E7
0x1800368d7  mov     rax, [rcx]
0x1800368da  mov     rax, [rax+10h]
0x1800368de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368e3  mov     [rbp+6E0h+var_730], r14
0x1800368e7  mov     rcx, [rbp+6E0h+var_6C0]
0x1800368eb  test    rcx, rcx
0x1800368ee  jz      short loc_1800368FD
0x1800368f0  mov     rdx, [rcx]
0x1800368f3  mov     rax, [rdx+10h]
0x1800368f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368fc  nop
0x1800368fd  mov     rax, rsi
0x180036900  mov     rcx, [rbp+6E0h+var_40]
0x180036907  xor     rcx, rsp; StackCookie
0x18003690a  call    __security_check_cookie
0x18003690f  mov     rbx, [rsp+7E0h+arg_18]
0x180036917  add     rsp, 7B0h
0x18003691e  pop     r15
0x180036920  pop     r14
0x180036922  pop     r13
0x180036924  pop     r12
0x180036926  pop     rdi
0x180036927  pop     rsi
0x180036928  pop     rbp
0x180036929  retn
0x18003692a  mov     rdi, [rbp+6E0h+var_6D8]
0x18003692e  cmp     rdi, [rbp+6E0h+var_6D0]
0x180036932  jnb     loc_180037D2B
0x180036938  xor     ecx, ecx
0x18003693a  mov     [rsp+7E0h+var_7A0], rcx
0x18003693f  mov     rbx, [rbp+6E0h+var_730]
0x180036943  test    rbx, rbx
0x180036946  jz      short loc_18003695C
0x180036948  mov     rax, [rbx]
0x18003694b  mov     rcx, rbx
0x18003694e  mov     rax, [rax+8]
0x180036952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036957  mov     rcx, [rsp+7E0h+var_7A0]
0x18003695c  mov     [rsp+7E0h+var_7A0], rbx
0x180036961  test    rcx, rcx
0x180036964  jnz     loc_180036F5F
0x18003696a  lea     rax, [rsp+7E0h+var_7A0]
0x18003696f  mov     qword ptr [rsp+7E0h+var_790], rax
0x180036974  test    rbx, rbx
0x180036977  jz      loc_180036F47
0x18003697d  mov     rax, [rbx]
0x180036980  mov     rcx, rbx
0x180036983  mov     rax, [rax+8]
0x180036987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003698c  mov     rax, rbx
0x18003698f  mov     rbx, [rsp+7E0h+var_7A0]
0x180036994  mov     qword ptr [rsp+7E0h+var_790], rax
0x180036999  test    rbx, rbx
0x18003699c  jz      short loc_1800369B4
0x18003699e  mov     rax, [rbx]
0x1800369a1  mov     rcx, rbx
0x1800369a4  mov     rax, [rax+10h]
0x1800369a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369ad  xor     ebx, ebx
0x1800369af  mov     [rsp+7E0h+var_7A0], rbx
0x1800369b4  mov     [rsp+7E0h+var_798], 1
0x1800369bc  lea     r9, [rsp+7E0h+var_798]
0x1800369c1  mov     r8, rdi
0x1800369c4  lea     rdx, [rbp+6E0h+pExceptionObject]
0x1800369cb  lea     rcx, [rsp+7E0h+var_790]
0x1800369d0  call    ?SaxQuery@SaxAttributes@consumption@win_musl@@QEAA?AUattribute@sax@3@_KPEAW4Enum@SaxAttributesQueryResult@23@@Z; win_musl::consumption::SaxAttributes::SaxQuery(unsigned __int64,win_musl::consumption::SaxAttributesQueryResult::Enum *)
0x1800369d5  movups  xmm0, xmmword ptr [rax]
0x1800369d8  movups  [rbp+6E0h+var_728], xmm0
0x1800369dc  movups  xmm1, xmmword ptr [rax+10h]
0x1800369e0  movups  [rbp+6E0h+var_718], xmm1
0x1800369e4  movups  xmm0, xmmword ptr [rax+20h]
0x1800369e8  movups  [rbp+6E0h+var_708], xmm0
0x1800369ec  movups  xmm1, xmmword ptr [rax+30h]
0x1800369f0  movups  [rbp+6E0h+var_6F8], xmm1
0x1800369f4  movups  xmm0, xmmword ptr [rax+40h]
0x1800369f8  movups  [rbp+6E0h+var_6E8], xmm0
0x1800369fc  cmp     [rsp+7E0h+var_798], 1
0x180036a01  jz      loc_180037CE1
0x180036a07  mov     rcx, qword ptr [rsp+7E0h+var_790]
0x180036a0c  test    rcx, rcx
0x180036a0f  jnz     loc_180036F4E
0x180036a15  cmp     qword ptr [r14+30h], 2
0x180036a1a  jz      loc_1800375D0
0x180036a20  lea     r9, word_180139A82
0x180036a27  lea     r12, aXmlLang; "xml:lang"
0x180036a2e  lea     rax, [r9-2]
0x180036a32  cmp     word ptr [rax], 0
0x180036a36  jnz     short loc_180036A40
0x180036a38  mov     r9, rax
0x180036a3b  cmp     rax, r12
0x180036a3e  jnz     short loc_180036A2E
0x180036a40  mov     r8, qword ptr [rbp+6E0h+var_708+8]
0x180036a44  test    r8, r8
0x180036a47  mov     r12, [rbp+6E0h+var_5D0]
0x180036a4e  mov     r10, qword ptr [rbp+6E0h+var_708]
0x180036a52  jz      loc_180036FA1
0x180036a58  test    r10, r10
0x180036a5b  jz      loc_180036FA1
0x180036a61  cmp     r8, r10
0x180036a64  jz      loc_180036FA1
0x180036a6a  mov     rcx, r8
0x180036a6d  sub     rcx, r10
0x180036a70  sar     rcx, 1
0x180036a73  lea     r11, aXmlLang; "xml:lang"
0x180036a7a  test    r9, r9
0x180036a7d  jz      loc_180036FA9
0x180036a83  cmp     r9, r11
0x180036a86  jz      loc_180036FA9
0x180036a8c  mov     rax, r9
0x180036a8f  sub     rax, r11
0x180036a92  sar     rax, 1
0x180036a95  cmp     rcx, rax
0x180036a98  jz      loc_180036FE1
0x180036a9e  lea     r9, dword_180139A44
0x180036aa5  lea     rsi, aXmlSpace; "xml:space"
0x180036aac  lea     rax, [r9-2]
0x180036ab0  cmp     word ptr [rax], 0
0x180036ab4  jnz     short loc_180036ABE
0x180036ab6  mov     r9, rax
0x180036ab9  cmp     rax, rsi
0x180036abc  jnz     short loc_180036AAC
0x180036abe  test    r8, r8
0x180036ac1  mov     rsi, [rsp+7E0h+var_778]
0x180036ac6  jz      loc_180036FB1
0x180036acc  test    r10, r10
0x180036acf  jz      loc_180036FB1
0x180036ad5  cmp     r8, r10
0x180036ad8  jz      loc_180036FB1
0x180036ade  mov     rcx, r8
0x180036ae1  sub     rcx, r10
0x180036ae4  sar     rcx, 1
0x180036ae7  lea     r11, aXmlSpace; "xml:space"
0x180036aee  test    r9, r9
0x180036af1  jz      loc_180036FB9
0x180036af7  cmp     r9, r11
0x180036afa  jz      loc_180036FB9
0x180036b00  mov     rax, r9
0x180036b03  sub     rax, r11
0x180036b06  sar     rax, 1
0x180036b09  cmp     rcx, rax
0x180036b0c  jz      loc_180037037
0x180036b12  lea     r9, word_180139A6E
0x180036b19  lea     r13, aXsProcessconte; "xs:processContents"
0x180036b20  lea     rax, [r9-2]
0x180036b24  cmp     word ptr [rax], 0
0x180036b28  jnz     short loc_180036B32
0x180036b2a  mov     r9, rax
0x180036b2d  cmp     rax, r13
0x180036b30  jnz     short loc_180036B20
0x180036b32  test    r8, r8
0x180036b35  mov     r13, [rbp+6E0h+var_570]
0x180036b3c  jz      loc_180036FC1
0x180036b42  test    r10, r10
0x180036b45  jz      loc_180036FC1
0x180036b4b  cmp     r8, r10
0x180036b4e  jz      loc_180036FC1
  ... truncated ...
```
