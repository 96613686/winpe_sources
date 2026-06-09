# SemanticsUM::SchemaEngine::GenerateLattice(wchar_t const *,unsigned __int64,SemanticsUM::ITokenCollection const &,SemanticsUM::INamedEntityCollection const &,SemanticsUM::CustomProperty const *,SemanticsUM::EntityPreferenceCollectionUM const *,bool,SemanticsUM::Lattice *)

- ea: `0x180021720`
- end: `0x1800228fc`
- name: `?GenerateLattice@SchemaEngine@SemanticsUM@@QEBAJPEB_W_KAEBVITokenCollection@2@AEBVINamedEntityCollection@2@PEBVCustomProperty@2@PEBVEntityPreferenceCollectionUM@2@_NPEAVLattice@2@@Z`
- size: `4572`
- prototype: `__int64 __fastcall(SemanticsUM::SchemaEngine *__hidden this, const wchar_t *, unsigned int, const struct ITokenCollection *, const struct SemanticsUM::INamedEntityCollection *, const struct SemanticsUM::CustomProperty *, const struct SemanticsUM::EntityPreferenceCollectionUM *, bool, struct SemanticsUM::Lattice *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180012d84`

## callees

- `0x180020420`
- `0x1800210b4`
- `0x180021340`
- `0x180021720`
- `0x180022904`
- `0x180022e7c`
- `0x180022eec`
- `0x1800236c0`
- `0x18003af18`
- `0x18003f158`
- `0x18003fecc`
- `0x180045d98`
- `0x180047e80`
- `0x18004eaf4`
- `0x180052ae4`
- `0x18005daf0`
- `0x18005db14`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180088b79`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180088b79`
- `OLEAUT32!__imp_VarParseNumFromStr` at `0x180021fb4`
- `OLEAUT32!__imp_VarParseNumFromStr` at `0x180021fb4`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180021f91`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180021f91`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021a46`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021ed8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021a46`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021ed8`

## string_xrefs

- `0x1800226e4`: `openParen`

## pseudocode

```c
__int64 __fastcall SemanticsUM::SchemaEngine::GenerateLattice(
        SemanticsUM::SchemaEngine *this,
        wchar_t *a2,
        unsigned __int64 a3,
        struct ITokenCollection *a4,
        const struct SemanticsUM::INamedEntityCollection *a5,
        const struct SemanticsUM::CustomProperty *a6,
        const struct SemanticsUM::EntityPreferenceCollectionUM *a7,
        bool a8,
        struct SemanticsUM::FragmentSet **a9)
{
  wchar_t *v9; // r13
  struct SemanticsUM::FragmentSet **v10; // rsi
  unsigned int v11; // edi
  SemanticsUM::SchemaEngine *v12; // r14
  unsigned int v13; // ebp
  struct ITokenCollection *v14; // r12
  __int64 result; // rax
  unsigned int v16; // r15d
  const struct SemanticsUM::EntityPreferenceCollectionUM *v17; // rdx
  bool v18; // r8
  struct SemanticsUM::FragmentSet *v19; // rdx
  int PreferredEntities; // ebx
  int v21; // eax
  __int64 v22; // r8
  unsigned int v23; // r15d
  struct SemanticsUM::FragmentSet *v24; // rcx
  __int64 v25; // rax
  int v26; // ebx
  __int64 (__fastcall ***v27)(_QWORD); // rax
  int v28; // esi
  __int64 v29; // rax
  __int64 v30; // r11
  wchar_t v31; // r8
  wchar_t v32; // r8
  unsigned __int64 v33; // r11
  int v34; // ebp
  int v35; // edi
  int v36; // ebx
  bool v37; // zf
  __int64 v38; // rsi
  __int64 (__fastcall ***v39)(_QWORD); // rax
  int v40; // eax
  __int64 v41; // rax
  char *v42; // rbx
  __int64 v43; // r15
  __int64 (__fastcall ***v44)(_QWORD); // rax
  __int64 v45; // rax
  __int64 v46; // rbp
  const WCHAR *v47; // r12
  __int64 v48; // rcx
  unsigned int v49; // r14d
  __int64 v50; // r13
  unsigned int v51; // esi
  __int64 v52; // rdi
  const WCHAR *v53; // rax
  int v54; // eax
  __int64 **v55; // rdi
  unsigned int v56; // ebx
  struct ITokenCollection *v57; // r14
  __int64 (__fastcall ***v58)(_QWORD); // rax
  int v59; // esi
  __int64 v60; // rax
  int v61; // eax
  wchar_t v62; // r8
  wchar_t v63; // r8
  const wchar_t *v64; // r9
  unsigned __int64 v65; // r11
  int v66; // ecx
  int v67; // ebx
  __int64 v68; // rax
  int v69; // ebx
  int v70; // r14d
  __int64 v71; // r12
  int v72; // r13d
  int v73; // eax
  __int64 (__fastcall **v74)(__int64); // rcx
  int v75; // eax
  __int64 *v76; // rsi
  _QWORD *v77; // rax
  __int64 v78; // rdx
  struct SemanticsUM::FragmentSet *v79; // rdx
  bool v80; // al
  unsigned int v81; // edi
  __int64 v82; // r8
  struct SemanticsUM::FragmentSet *v83; // r14
  unsigned int v84; // eax
  __int64 v85; // rax
  SemanticsUM::SchemaEngine *v86; // r14
  unsigned int v87; // r13d
  LCID v88; // r15d
  unsigned __int64 v89; // rdi
  unsigned __int64 i; // rsi
  __int64 v91; // rbx
  __int64 v92; // r14
  __int64 v93; // rbp
  const WCHAR *v94; // r14
  unsigned __int64 v95; // rbx
  int v96; // eax
  int v97; // eax
  __int64 v98; // rax
  __int64 v99; // rdi
  __int64 v100; // rax
  int v101; // ebp
  const OLECHAR *v102; // rsi
  LCID UserDefaultLCID; // eax
  unsigned int AnnotationFragments; // eax
  INT v105; // ebp
  __int64 j; // rdi
  __int64 v107; // r11
  __int64 v108; // r11
  struct SemanticsUM::Lattice *v109; // rbp
  SemanticsUM::TokenFragmentStatistics *v110; // rbx
  __int64 v111; // r8
  __int64 v112; // rdi
  wchar_t *v113; // r13
  SemanticsUM::SchemaEngine *v114; // r14
  unsigned int v115; // esi
  __int64 (__fastcall ***v116)(_QWORD); // rax
  int v117; // r14d
  __int64 v118; // rax
  __int64 v119; // r11
  wchar_t v120; // r8
  wchar_t v121; // r8
  unsigned __int64 v122; // r11
  int v123; // ecx
  int v124; // ebx
  int v125; // r15d
  __int64 v126; // r12
  int v127; // ebx
  struct SemanticsUM::FragmentSet *v128; // rbp
  struct SemanticsUM::FragmentSet *v129; // rax
  _QWORD *v130; // rax
  __int64 v131; // r14
  __int64 v132; // rax
  unsigned int k; // ebx
  unsigned __int16 *v134; // rax
  unsigned int (__fastcall ***v135)(_QWORD); // rax
  __int64 v136; // r11
  __int64 v137; // r13
  unsigned int v138; // ebx
  unsigned int v139; // ebp
  _QWORD *v140; // rsi
  unsigned int (__fastcall ***v141)(_QWORD); // rax
  unsigned int v142; // edi
  bool v143; // r15
  int v144; // eax
  int v145; // r12d
  __int64 **v146; // r14
  struct SemanticsUM::FragmentSet *v147; // rdx
  SemanticsUM::SchemaEngine *v148; // kr00_8
  struct SemanticsUM::FragmentSet *v149; // kr20_8
  int v150; // ebx
  int v151; // r14d
  const wchar_t *v152; // rsi
  _QWORD *v153; // rax
  int v154; // eax
  const struct SemanticsUM::CustomProperty *v155; // rax
  __int64 v156; // rax
  unsigned int v157; // edx
  SemanticsUM::TokenFragmentStatistics *v158; // r12
  __int64 v159; // rcx
  unsigned int lpString2; // [rsp+20h] [rbp-1C8h]
  unsigned int cchCount2; // [rsp+28h] [rbp-1C0h]
  unsigned int v162; // [rsp+40h] [rbp-1A8h]
  int NamedEntityFragments; // [rsp+70h] [rbp-178h]
  int v164; // [rsp+70h] [rbp-178h]
  unsigned int v165; // [rsp+74h] [rbp-174h]
  bool v166; // [rsp+78h] [rbp-170h]
  unsigned int v167; // [rsp+7Ch] [rbp-16Ch]
  unsigned __int16 *v169; // [rsp+90h] [rbp-158h] BYREF
  SemanticsUM::SchemaEngine *v170; // [rsp+98h] [rbp-150h]
  SemanticsUM::TokenFragmentStatistics *v171; // [rsp+A0h] [rbp-148h] BYREF
  struct ITokenCollection *v172; // [rsp+A8h] [rbp-140h]
  wchar_t *v173; // [rsp+B0h] [rbp-138h]
  __int64 v174; // [rsp+B8h] [rbp-130h]
  struct SemanticsUM::FragmentSet *v175; // [rsp+C0h] [rbp-128h]
  const struct SemanticsUM::CustomProperty *v176; // [rsp+C8h] [rbp-120h]
  int v177; // [rsp+D0h] [rbp-118h]
  struct SemanticsUM::INamedEntityCollection *v178; // [rsp+D8h] [rbp-110h]
  char *v179; // [rsp+E0h] [rbp-108h]
  NUMPARSE pnumprs; // [rsp+E8h] [rbp-100h] BYREF
  BYTE rgbDig[112]; // [rsp+100h] [rbp-E8h] BYREF

  v9 = a2;
  v10 = a9;
  v11 = a3;
  v178 = a5;
  v12 = this;
  v13 = 0;
  v173 = a2;
  v14 = a4;
  v170 = this;
  v176 = a6;
  v172 = a4;
  v169 = 0;
  result = SemanticsUM::GetStringFlags(
             a2,
             (const wchar_t *)(unsigned int)(a3 + 1),
             (unsigned int)&v169,
             (unsigned __int16 **)a4);
  if ( (int)result < 0 )
    return result;
  v16 = ((__int64 (__fastcall *)(struct ITokenCollection *))v14->lpVtbl->QueryInterface)(v14);
  v165 = v16;
  PreferredEntities = SemanticsUM::SchemaEngine::GeneratePreferredEntities(v12, v17, v18, *a9);
  if ( PreferredEntities < 0 )
    goto LABEL_83;
  v171 = 0;
  v21 = SemanticsUM::TokenFragmentStatistics::Create(v9, v14, &v171);
  NamedEntityFragments = v21;
  v22 = (unsigned int)v21;
  if ( v21 < 0 )
  {
    PreferredEntities = v21;
    goto LABEL_83;
  }
  v167 = 0;
  while ( v13 < v16 )
  {
    if ( !*((_DWORD *)v12 + 40) )
      goto LABEL_54;
    v23 = v13 + 1;
    v19 = (struct SemanticsUM::FragmentSet *)v13;
    v24 = (struct SemanticsUM::FragmentSet *)((char *)*v10 + 16 * v13 + 16);
    v25 = *((_QWORD *)v171 + 2);
    v175 = v24;
    v174 = v13;
    v26 = *(_DWORD *)(v25 + 4LL * v13);
    if ( v26 < 0 )
    {
      v27 = (__int64 (__fastcall ***)(_QWORD))((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, __int64))v14->lpVtbl->AddRef)(
                                                v14,
                                                v13,
                                                v22);
      v28 = (**v27)(v27);
      v29 = ((__int64 (__fastcall *)(struct ITokenCollection *, __int64))v14->lpVtbl->AddRef)(v14, v174);
      v30 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
      v31 = v9[v30];
      if ( !v31
        || (v169[v30] & 8) != 0
        || SemanticsUM::Syntax::IsParenthesis(v31)
        || SemanticsUM::Syntax::IsDoubleQuote(v32)
        && !SemanticsUM::Syntax::QuoteIsPartOfHebrewNumber(v33, v9, v11)
        && v107 + 1 == v11 )
      {
        v34 = 4;
      }
      else
      {
        v34 = 0;
      }
      v35 = 18;
      v36 = 2;
      if ( v28 != 10 )
        v35 = 16;
      v37 = v28 == 10;
      v38 = v174;
      if ( !v37 )
        v36 = 0;
      v148 = v12;
      v39 = (__int64 (__fastcall ***)(_QWORD))((__int64 (__fastcall *)(struct ITokenCollection *, __int64))v14->lpVtbl->AddRef)(
                                                v14,
                                                v174);
      v40 = (**v39)(v39);
      v149 = v147;
      v19 = (struct SemanticsUM::FragmentSet *)&_ImageBase;
      v150 = v34 | v36;
      v151 = 1;
      switch ( v40 )
      {
        case 0:
          v152 = L"dotdot";
          v150 = v34 | v35;
          goto LABEL_143;
        case 1:
        case 9:
        case 10:
        case 11:
        case 14:
        case 15:
        case 16:
        case 17:
        case 18:
        case 19:
        case 20:
          goto LABEL_146;
        case 2:
          v152 = L"lessThan";
          goto LABEL_143;
        case 3:
          v152 = L"greaterThan";
          goto LABEL_143;
        case 4:
          v152 = L"equals";
          goto LABEL_143;
        case 5:
          v152 = L"notGreaterThan";
          goto LABEL_143;
        case 6:
          v152 = L"notLessThan";
          goto LABEL_143;
        case 7:
          v152 = L"notEquals";
          goto LABEL_143;
        case 8:
          v152 = L"not";
          goto LABEL_143;
        case 12:
          v152 = L"openParen";
          v151 = 3;
          goto LABEL_143;
        case 13:
          v152 = L"closeParen";
          v151 = 4;
          goto LABEL_143;
        case 21:
          v152 = L"pos";
          goto LABEL_143;
        case 22:
          v152 = L"dosWildcards";
          goto LABEL_143;
        case 23:
          v152 = L"valueStartsWith";
          goto LABEL_143;
        case 24:
          v152 = L"valueEndsWith";
          goto LABEL_143;
        case 25:
          v152 = L"valueContains";
          goto LABEL_143;
        case 26:
          v152 = L"valueNotContains";
          goto LABEL_143;
        case 27:
          v152 = L"wordEqual";
          goto LABEL_143;
        case 28:
          v152 = L"wordStartsWith";
          goto LABEL_143;
        case 29:
          v152 = L"applicationSpecific";
LABEL_143:
          v153 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v153 )
          {
            *(_DWORD *)v153 = v151;
            v153[4] = 0x3FF0000000000000LL;
            v19 = v175;
            v153[1] = 0;
            v153[2] = 0;
            *((_DWORD *)v153 + 15) = v150;
            v153[8] = 0;
            *((_DWORD *)v153 + 6) = v167;
            *((_DWORD *)v153 + 7) = v23;
            *((_DWORD *)v153 + 10) = v167;
            *((_DWORD *)v153 + 11) = v23;
            v153[6] = v152;
            *((_BYTE *)v153 + 56) = 0;
            v153[8] = *(_QWORD *)v19;
            *(_QWORD *)v19 = v153;
            NamedEntityFragments = 0;
          }
          else
          {
            NamedEntityFragments = -2147024882;
          }
          v38 = v174;
LABEL_146:
          v86 = v170;
          break;
        default:
          v19 = v149;
          v86 = v148;
          break;
      }
      v22 = (unsigned int)NamedEntityFragments;
      if ( NamedEntityFragments >= 0 )
      {
        NamedEntityFragments = 0;
        v41 = (*(__int64 (__fastcall **)(struct SemanticsUM::INamedEntityCollection *, __int64))(*(_QWORD *)v178 + 8LL))(
                v178,
                v38);
        v22 = 0;
        v42 = (char *)v86 + 8;
        v43 = v41;
        while ( v43 )
        {
          v44 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, struct SemanticsUM::FragmentSet *, _QWORD))(*(_QWORD *)v43 + 32LL))(
                                                    v43,
                                                    v19,
                                                    0);
          v45 = (**v44)(v44);
          v46 = 0;
          v179 = (char *)v86 + 8;
          v47 = (const WCHAR *)v45;
          v48 = *((_QWORD *)v86 + 1);
          v49 = 0;
          v50 = *(_QWORD *)(v48 + 40);
          v51 = *(_DWORD *)(v48 + 32);
          while ( v49 < v51 )
          {
            v52 = (v51 + v49) >> 1;
            v53 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v50 + 112 * v52))(v50 + 112 * v52);
            v54 = CompareStringW(0x7Fu, 0, v47, -1, v53, -1);
            if ( v54 == 2 )
            {
              v46 = v50 + 112 * v52;
            }
            else if ( v54 == 1 )
            {
              v51 = (v51 + v49) >> 1;
            }
            else
            {
              v49 = v52 + 1;
            }
            if ( v46 )
            {
              v55 = *(__int64 ***)(v46 + 40);
              while ( v55 != *(__int64 ***)(v46 + 48) )
              {
                v166 = (*(int (__fastcall **)(__int64))(*(_QWORD *)v43 + 48LL))(v43) >= 1;
                v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43) - 1;
                (**(void (__fastcall ***)(__int64))v43)(v43);
                v57 = v172;
                v58 = (__int64 (__fastcall ***)(_QWORD))((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v172->lpVtbl->AddRef)(
                                                          v172,
                                                          v56);
                v59 = (**v58)(v58);
                v60 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v57->lpVtbl->AddRef)(v57, v56);
                v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 24LL))(v60);
                v62 = v173[v61];
                if ( !v62
                  || (v169[v61] & 8) != 0
                  || SemanticsUM::Syntax::IsParenthesis(v62)
                  || SemanticsUM::Syntax::IsDoubleQuote(v63)
                  && !SemanticsUM::Syntax::QuoteIsPartOfHebrewNumber(v65, v64, a3)
                  && v108 + 1 == (unsigned int)a3 )
                {
                  v66 = 4;
                }
                else
                {
                  v66 = 0;
                }
                v67 = 2;
                if ( v59 != 10 )
                  v67 = 0;
                v68 = *(_QWORD *)v43;
                v69 = v66 | v67;
                if ( (v69 & 2) != 0 )
                  v70 = (*(__int64 (__fastcall **)(__int64))(v68 + 8))(v43) - 1;
                else
                  v70 = (*(__int64 (__fastcall **)(__int64))(v68 + 24))(v43);
                v71 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 40LL))(v43);
                v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
                v74 = *(__int64 (__fastcall ***)(__int64))v43;
                v177 = v73;
                v75 = (*v74)(v43);
                v76 = *v55;
                v164 = v75;
                v77 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
                if ( !v77 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 64LL))(v43);
                  PreferredEntities = -2147024882;
                  goto LABEL_81;
                }
                *(_DWORD *)v77 = 5;
                v77[1] = v76;
                if ( v76 )
                  v78 = *v76;
                else
                  v78 = 0;
                v77[2] = v78;
                v79 = v175;
                *((_DWORD *)v77 + 6) = v164;
                *((_DWORD *)v77 + 7) = v177;
                v77[4] = 0x3FF0000000000000LL;
                *((_DWORD *)v77 + 15) = v69;
                v77[8] = 0;
                ++v55;
                *((_BYTE *)v77 + 56) = v166;
                *((_DWORD *)v77 + 10) = v72;
                *((_DWORD *)v77 + 11) = v70;
                v77[6] = v71;
                v77[8] = *(_QWORD *)v79;
                *(_QWORD *)v79 = v77;
                NamedEntityFragments = 0;
              }
              break;
            }
          }
          v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 64LL))(v43);
          v22 = 0;
          v43 = v85;
          v42 = v179;
          v86 = v170;
        }
        v14 = v172;
        v87 = v167;
        v88 = *(_DWORD *)(*(_QWORD *)v42 + 12LL);
        v89 = *(_QWORD *)(*(_QWORD *)v42 + 120LL);
        for ( i = *(_QWORD *)(*(_QWORD *)v42 + 128LL); (int)v22 >= 0 && v89 < i; i = *(_QWORD *)(v95 + 16) )
        {
          v91 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v14->lpVtbl->AddRef)(v14, v87);
          v92 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v91 + 8LL))(v91);
          LODWORD(v93) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 32LL))(v91) )
          {
            v156 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 32LL))(v91);
            v94 = (const WCHAR *)v156;
            v93 = -1;
            do
              ++v93;
            while ( *(_WORD *)(v156 + 2 * v93) );
          }
          else
          {
            v94 = &v173[v92];
          }
          while ( 1 )
          {
            while ( 1 )
            {
              v95 = v89 + 40 * ((__int64)(i - v89) / 80);
              v96 = CompareStringW(v88, 0x20001u, v94, v93, *(PCNZWCH *)v95, -1);
              if ( v96 != 1 )
                break;
              if ( v95 == v89 )
                goto LABEL_50;
              i = v89 + 40 * ((__int64)(i - v89) / 80);
            }
            v97 = v96 - 2;
            if ( !v97 )
              break;
            if ( v97 == 1 )
            {
              v89 = v95 + 40;
              if ( v95 + 40 != i )
                continue;
            }
LABEL_50:
            v22 = (unsigned int)NamedEntityFragments;
            goto LABEL_51;
          }
          v98 = ((__int64 (__fastcall *)(struct ITokenCollection *, __int64))v14->lpVtbl->AddRef)(v14, v174);
          v99 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v98 + 8LL))(v98);
          v100 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v14->lpVtbl->AddRef)(v14, v87);
          v101 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v100 + 24LL))(v100);
          pnumprs.cDig = 100;
          *(_OWORD *)&pnumprs.dwOutFlags = 0;
          pnumprs.dwInFlags = 2836;
          v102 = &v173[v99];
          UserDefaultLCID = GetUserDefaultLCID();
          if ( VarParseNumFromStr(v102, UserDefaultLCID, 0, &pnumprs, rgbDig) < 0 )
            goto LABEL_70;
          v105 = v101 - v99;
          if ( pnumprs.cchUsed == v105 )
            goto LABEL_77;
          if ( pnumprs.cchUsed <= v105 )
            goto LABEL_70;
          for ( j = (unsigned int)(pnumprs.cchUsed - 1); (int)j >= 0; j = (unsigned int)(j - 1) )
          {
            if ( !(unsigned int)_o_iswspace(v102[j]) )
              break;
          }
          if ( (_DWORD)j + 1 == v105 )
          {
LABEL_77:
            v22 = (unsigned int)NamedEntityFragments;
          }
          else
          {
LABEL_70:
            AnnotationFragments = SemanticsUM::SchemaEngine::MakeAnnotationFragments(
                                    v173,
                                    a3,
                                    v14,
                                    v169,
                                    lpString2,
                                    (const struct SemanticsUM::TrieNode *)v95,
                                    v167,
                                    v87 + 1,
                                    v171,
                                    (enum tagSTRUCTURED_QUERY_SYNTAX)*((_DWORD *)v170 + 40),
                                    (enum CASE_REQUIREMENT)*((_DWORD *)v170 + 41),
                                    *(_BYTE *)(*((_QWORD *)v171 + 3) + v87),
                                    v175);
            v22 = AnnotationFragments;
            NamedEntityFragments = AnnotationFragments;
          }
          if ( ++v87 == v165 )
            break;
          v89 = *(_QWORD *)(v95 + 8);
        }
      }
LABEL_51:
      v13 = v167;
      goto LABEL_52;
    }
    if ( v26 <= (int)v13 )
      goto LABEL_53;
    if ( v26 == v165 )
    {
      v80 = 1;
      v81 = v165;
    }
    else
    {
      v80 = 0;
      v81 = v26 + 1;
    }
    NamedEntityFragments = SemanticsUM::SchemaEngine::MakeNamedEntityFragments(
                             v12,
                             v9,
                             a3,
                             v14,
                             v169,
                             cchCount2,
                             v178,
                             v13,
                             v81,
                             1,
                             v80,
                             v24);
    v22 = (unsigned int)NamedEntityFragments;
    if ( NamedEntityFragments >= 0 )
    {
      SemanticsUM::SchemaEngine::ComputeQuotePrefixStatus(v9, a3, v14, v169, lpString2, 1, v26 == v165, 0, v162, v81);
      v82 = *((_QWORD *)v12 + 13);
      v83 = v175;
      cchCount2 = LODWORD(DOUBLE_0_8);
      lpString2 = v81;
      NamedEntityFragments = SemanticsUM::FragmentSet::AddNewFragment(v175, 0, v82, v13);
      v22 = (unsigned int)NamedEntityFragments;
      if ( NamedEntityFragments >= 0 )
      {
        cchCount2 = LODWORD(DOUBLE_1_0);
        lpString2 = v81;
        v84 = SemanticsUM::FragmentSet::AddNewFragment(v83, 6, 0, v13);
        v22 = v84;
        NamedEntityFragments = v84;
      }
LABEL_52:
      v11 = a3;
      v10 = a9;
LABEL_53:
      v16 = v165;
      goto LABEL_54;
    }
    v11 = a3;
    v16 = v165;
    v10 = a9;
LABEL_54:
    v167 = ++v13;
    if ( (int)v22 < 0 )
      goto LABEL_80;
    v9 = v173;
    v12 = v170;
  }
  if ( (int)v22 < 0 )
    goto LABEL_80;
  v155 = v176;
  while ( v155 )
  {
    v137 = *((_QWORD *)v155 + 1);
    if ( v137 )
    {
      v138 = *(_DWORD *)v155;
      v139 = *(_DWORD *)v155 + *((_DWORD *)v155 + 1);
      v140 = (_QWORD *)((char *)*a9 + 16 * (unsigned int)(*(_DWORD *)v155 + 1));
      if ( v139 < v16
        && (v141 = (unsigned int (__fastcall ***)(_QWORD))((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v14->lpVtbl->AddRef)(
                                                            v14,
                                                            v139),
            (**v141)(v141) == 9) )
      {
        v142 = v139 + 1;
        v143 = 1;
        v157 = v138;
        if ( v138 < v139 + 1 )
        {
          v158 = v171;
          do
          {
            v159 = v157++;
            *(_BYTE *)(v159 + *((_QWORD *)v158 + 3)) = 1;
          }
          while ( v157 < v142 );
          v14 = v172;
        }
      }
      else
      {
        v142 = v139;
        v143 = 0;
      }
      v144 = SemanticsUM::SchemaEngine::ComputeQuotePrefixStatus(v173, a3, v14, v169, lpString2, 0, 0, v143, v162, v142);
      LODWORD(v22) = NamedEntityFragments;
      v145 = v144;
      v146 = *(__int64 ***)(v137 + 24);
      while ( v146 != *(__int64 ***)(v137 + 32) )
      {
        v154 = SemanticsUM::FragmentSet::AddNewFragment(
                 v140,
                 8,
                 *v146++,
                 v138,
                 v142,
                 *(__int64 *)&DOUBLE_1_0,
                 v138,
                 v139,
                 0,
                 1,
                 v145);
        NamedEntityFragments = v154;
        LODWORD(v22) = v154;
        if ( v154 < 0 )
        {
LABEL_157:
          PreferredEntities = v154;
          goto LABEL_81;
        }
      }
      if ( v143 )
      {
        cchCount2 = LODWORD(DOUBLE_1_0);
        lpString2 = v142;
        LODWORD(v22) = SemanticsUM::FragmentSet::AddNewFragment(v140, 6, 0, v138);
        NamedEntityFragments = v22;
      }
      v155 = v176;
      v16 = v165;
      v14 = v172;
    }
    v155 = (const struct SemanticsUM::CustomProperty *)*((_QWORD *)v155 + 2);
    v176 = v155;
    if ( (int)v22 < 0 )
      goto LABEL_80;
  }
  v109 = (struct SemanticsUM::Lattice *)a9;
  v110 = v171;
  SemanticsUM::TokenFragmentStatistics::RecordFragments(v171, (struct SemanticsUM::Lattice *)a9);
  v111 = (unsigned int)NamedEntityFragments;
  v112 = 0;
  v113 = v173;
LABEL_96:
  v114 = v170;
  v115 = v16;
  while ( (unsigned int)v112 < v16 )
  {
    v19 = (struct SemanticsUM::FragmentSet *)(unsigned int)v112;
    if ( *(int *)(*((_QWORD *)v110 + 2) + 4 * v112) >= 0 || (*(_DWORD *)(*((_QWORD *)v110 + 4) + 4 * v112) & 0xC) == 4 )
    {
      if ( v115 < (unsigned int)v112 )
      {
        v116 = (__int64 (__fastcall ***)(_QWORD))((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, __int64))v14->lpVtbl->AddRef)(
                                                   v14,
                                                   (unsigned int)(v112 - 1),
                                                   v111);
        v117 = (**v116)(v116);
        v118 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v14->lpVtbl->AddRef)(
                 v14,
                 (unsigned int)(v112 - 1));
        v119 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v118 + 24LL))(v118);
        v120 = v113[v119];
        if ( !v120
          || (v169[v119] & 8) != 0
          || SemanticsUM::Syntax::IsParenthesis(v120)
          || SemanticsUM::Syntax::IsDoubleQuote(v121)
          && !SemanticsUM::Syntax::QuoteIsPartOfHebrewNumber(v122, v113, a3)
          && v136 + 1 == (unsigned int)a3 )
        {
          v123 = 4;
        }
        else
        {
          v123 = 0;
        }
        v124 = 2;
        v125 = v112;
        v126 = *((_QWORD *)v170 + 13);
        if ( v117 != 10 )
          v124 = 0;
        v127 = v123 | v124;
        if ( (v127 & 2) != 0 )
          v125 = v112 - 1;
        v128 = *a9;
        v129 = (struct SemanticsUM::FragmentSet *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        v19 = v129;
        if ( !v129 )
          goto LABEL_116;
        *((_QWORD *)v129 + 2) = v126;
        *(_DWORD *)v129 = 0;
        *((_QWORD *)v129 + 1) = 0;
        *((_QWORD *)v129 + 8) = 0;
        *((_DWORD *)v129 + 6) = v115;
        *((_DWORD *)v129 + 7) = v112;
        *((_QWORD *)v129 + 4) = 0x3FF0000000000000LL;
        *((_DWORD *)v129 + 10) = v115;
        *((_DWORD *)v129 + 11) = v125;
        *((_QWORD *)v129 + 6) = 0;
        *((_BYTE *)v129 + 56) = 0;
        *((_DWORD *)v129 + 15) = v127;
        *((_QWORD *)v129 + 8) = *((_QWORD *)v128 + 2 * v115 + 2);
        *((_QWORD *)v128 + 2 * v115 + 2) = v129;
        v130 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v130 )
        {
          *(_DWORD *)v130 = 6;
          v111 = 0;
          v130[1] = 0;
          v130[2] = 0;
          *((_DWORD *)v130 + 6) = v115;
          *((_DWORD *)v130 + 7) = v112;
          v130[8] = 0;
          v130[4] = 0x3FF0000000000000LL;
          *((_DWORD *)v130 + 10) = v115;
          *((_DWORD *)v130 + 11) = v125;
          v130[6] = 0;
          *((_BYTE *)v130 + 56) = 0;
          *((_DWORD *)v130 + 15) = v127;
          v130[8] = *((_QWORD *)v128 + 2 * v115 + 2);
          *((_QWORD *)v128 + 2 * v115 + 2) = v130;
        }
        else
        {
LABEL_116:
          v111 = 2147942414LL;
        }
        v110 = v171;
        v16 = v165;
        v109 = (struct SemanticsUM::Lattice *)a9;
        NamedEntityFragments = v111;
      }
      if ( (int)v111 >= 0 )
      {
        v14 = v172;
        v112 = (unsigned int)(v112 + 1);
        goto LABEL_96;
      }
    }
    else if ( v115 >= (unsigned int)v112 )
    {
      v115 = v112;
    }
    else
    {
      v131 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, __int64))v14->lpVtbl->AddRef)(
               v14,
               (unsigned int)v112,
               v111);
      v132 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v14->lpVtbl->AddRef)(
               v14,
               (unsigned int)(v112 - 1));
      for ( k = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v132 + 24LL))(v132);
            k < (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v131 + 8LL))(v131);
            ++k )
      {
        v134 = v169;
        if ( (v169[k] & 0x68) != 0 )
        {
          v110 = v171;
          goto LABEL_134;
        }
      }
      v135 = (unsigned int (__fastcall ***)(_QWORD))((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD))v14->lpVtbl->AddRef)(
                                                      v14,
                                                      (unsigned int)(v112 - 1));
      if ( (**v135)(v135) != 9
        || (_DWORD)v112 == 1
        || (v110 = v171, (*(_BYTE *)(*((_QWORD *)v171 + 4) + 4LL * (unsigned int)(v112 - 2)) & 8) == 0) )
      {
        v111 = (unsigned int)NamedEntityFragments;
        goto LABEL_124;
      }
      v134 = v169;
LABEL_134:
      v109 = (struct SemanticsUM::Lattice *)a9;
      v114 = v170;
      NamedEntityFragments = SemanticsUM::SchemaEngine::EmitBlurb(
                               v170,
                               v113,
                               a3,
                               v14,
                               v134,
                               cchCount2,
                               v115,
                               v112,
                               (struct SemanticsUM::Lattice *)a9);
      v111 = (unsigned int)NamedEntityFragments;
      if ( NamedEntityFragments >= 0 )
      {
        v16 = v165;
        v115 = v112;
        v112 = (unsigned int)(v112 + 1);
        continue;
      }
    }
LABEL_124:
    v14 = v172;
    v112 = (unsigned int)(v112 + 1);
    v114 = v170;
    v110 = v171;
    v16 = v165;
    v109 = (struct SemanticsUM::Lattice *)a9;
    if ( (int)v111 < 0 )
      goto LABEL_80;
  }
  if ( v115 < (unsigned int)v112 )
  {
    v154 = SemanticsUM::SchemaEngine::EmitBlurb(v114, v113, a3, v14, v169, cchCount2, v115, v112, v109);
    goto LABEL_157;
  }
LABEL_80:
  PreferredEntities = NamedEntityFragments;
LABEL_81:
  if ( v171 )
    SemanticsUM::TokenFragmentStatistics::`scalar deleting destructor'((void **)v171, v19);
LABEL_83:
  operator delete(v169, v19);
  return (unsigned int)PreferredEntities;
}

```

## disassembly

```asm
0x180021720  push    rbp
0x180021722  push    rsi
0x180021723  push    rdi
0x180021724  push    r12
0x180021726  push    r13
0x180021728  push    r14
0x18002172a  sub     rsp, 1B8h
0x180021731  mov     rax, cs:__security_cookie
0x180021738  xor     rax, rsp
0x18002173b  mov     [rsp+1E8h+var_78], rax
0x180021743  mov     rax, [rsp+1E8h+arg_20]
0x18002174b  mov     r13, rdx
0x18002174e  mov     rsi, [rsp+1E8h+arg_40]
0x180021756  mov     rdi, r8
0x180021759  mov     [rsp+1E8h+var_110], rax
0x180021761  mov     r14, rcx
0x180021764  mov     rax, [rsp+1E8h+arg_28]
0x18002176c  xor     ebp, ebp
0x18002176e  mov     [rsp+1E8h+var_138], rdx
0x180021776  mov     r12, r9
0x180021779  mov     qword ptr [rsp+1E8h+var_168], r8
0x180021781  lea     edx, [r8+1]; cchSrc
0x180021785  mov     [rsp+1E8h+var_150], rcx
0x18002178d  lea     r8, [rsp+1E8h+var_158]; unsigned int
0x180021795  mov     rcx, r13; lpSrcStr
0x180021798  mov     [rsp+1E8h+var_120], rax
0x1800217a0  mov     [rsp+1E8h+var_140], r9
0x1800217a8  mov     [rsp+1E8h+var_160], rsi
0x1800217b0  mov     [rsp+1E8h+var_158], rbp
0x1800217b8  call    ?GetStringFlags@SemanticsUM@@YAJPEB_WKPEAPEAG@Z; SemanticsUM::GetStringFlags(wchar_t const *,ulong,ushort * *)
0x1800217bd  test    eax, eax
0x1800217bf  js      loc_1800220F3
0x1800217c5  mov     rax, [r12]
0x1800217c9  mov     rcx, r12
0x1800217cc  mov     [rsp+1E8h+var_38], rbx
0x1800217d4  mov     [rsp+1E8h+var_40], r15
0x1800217dc  mov     rax, [rax]
0x1800217df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217e4  mov     r9, [rsi]; struct SemanticsUM::FragmentSet *
0x1800217e7  mov     rcx, r14; this
0x1800217ea  mov     r15d, eax
0x1800217ed  mov     [rsp+1E8h+var_174], eax
0x1800217f1  call    ?GeneratePreferredEntities@SchemaEngine@SemanticsUM@@AEBAJPEBVEntityPreferenceCollectionUM@2@_NPEAVFragmentSet@2@@Z; SemanticsUM::SchemaEngine::GeneratePreferredEntities(SemanticsUM::EntityPreferenceCollectionUM const *,bool,SemanticsUM::FragmentSet *)
0x1800217f6  mov     ebx, eax
0x1800217f8  test    eax, eax
0x1800217fa  js      loc_1800220D4
0x180021800  lea     r8, [rsp+1E8h+var_148]; struct SemanticsUM::TokenFragmentStatistics **
0x180021808  mov     [rsp+1E8h+var_148], rbp
0x180021810  mov     rdx, r12; struct ITokenCollection *
0x180021813  mov     rcx, r13; wchar_t *
0x180021816  call    ?Create@TokenFragmentStatistics@SemanticsUM@@SAJPEB_WAEBVITokenCollection@2@PEAPEAV12@@Z; SemanticsUM::TokenFragmentStatistics::Create(wchar_t const *,SemanticsUM::ITokenCollection const &,SemanticsUM::TokenFragmentStatistics * *)
0x18002181b  mov     [rsp+1E8h+var_178], eax
0x18002181f  mov     r8d, eax
0x180021822  test    eax, eax
0x180021824  js      loc_18002287B
0x18002182a  movaps  [rsp+1E8h+var_58], xmm6
0x180021832  movsd   xmm6, cs:__real@3ff0000000000000
0x18002183a  movaps  [rsp+1E8h+var_68], xmm7
0x180021842  movsd   xmm7, cs:__real@3fe999999999999a
0x18002184a  mov     [rsp+1E8h+var_16C], ebp
0x18002184e  xchg    ax, ax
0x180021850  cmp     ebp, r15d
0x180021853  jnb     loc_1800220A2
0x180021859  cmp     dword ptr [r14+0A0h], 0
0x180021861  jz      loc_180021DA5
0x180021867  mov     rax, [rsp+1E8h+var_148]
0x18002186f  lea     r15d, [rbp+1]
0x180021873  mov     edx, ebp
0x180021875  mov     ecx, r15d
0x180021878  shl     rcx, 4
0x18002187c  add     rcx, [rsi]
0x18002187f  mov     rax, [rax+10h]
0x180021883  mov     [rsp+1E8h+var_128], rcx
0x18002188b  mov     [rsp+1E8h+var_130], rdx
0x180021893  mov     ebx, [rax+rdx*4]
0x180021896  test    ebx, ebx
0x180021898  jns     loc_180021C6A
0x18002189e  mov     rax, [r12]
0x1800218a2  mov     rcx, r12
0x1800218a5  mov     rax, [rax+8]
0x1800218a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ae  mov     rdx, rax
0x1800218b1  mov     rcx, [rax]
0x1800218b4  mov     rax, [rcx]
0x1800218b7  mov     rcx, rdx
0x1800218ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218bf  mov     rcx, [r12]
0x1800218c3  mov     esi, eax
0x1800218c5  mov     rdx, [rsp+1E8h+var_130]
0x1800218cd  mov     rax, [rcx+8]
0x1800218d1  mov     rcx, r12
0x1800218d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218d9  mov     rdx, rax
0x1800218dc  mov     rcx, [rax]
0x1800218df  mov     rax, [rcx+18h]
0x1800218e3  mov     rcx, rdx
0x1800218e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218eb  mov     r11d, eax
0x1800218ee  movzx   r8d, word ptr [r13+r11*2+0]
0x1800218f4  test    r8w, r8w
0x1800218f8  jz      loc_180022151
0x1800218fe  mov     rax, [rsp+1E8h+var_158]
0x180021906  test    byte ptr [rax+r11*2], 8
0x18002190b  jnz     loc_180022151
0x180021911  movzx   ecx, r8w; wchar_t
0x180021915  call    ?IsParenthesis@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsParenthesis(wchar_t)
0x18002191a  test    al, al
0x18002191c  jnz     loc_180022151
0x180021922  movzx   ecx, r8w; wchar_t
0x180021926  call    ?IsDoubleQuote@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsDoubleQuote(wchar_t)
0x18002192b  test    al, al
0x18002192d  jnz     loc_18002212C
0x180021933  xor     ebp, ebp
0x180021935  cmp     esi, 0Ah
0x180021938  mov     eax, 10h
0x18002193d  mov     edi, 12h
0x180021942  mov     ebx, 2
0x180021947  cmovnz  edi, eax
0x18002194a  mov     rcx, r12
0x18002194d  xor     eax, eax
0x18002194f  cmp     esi, 0Ah
0x180021952  mov     rsi, [rsp+1E8h+var_130]
0x18002195a  mov     rdx, rsi
0x18002195d  cmovnz  ebx, eax
0x180021960  mov     rax, [r12]
0x180021964  mov     rax, [rax+8]
0x180021968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002196d  mov     rdx, rax
0x180021970  mov     rcx, [rax]
0x180021973  mov     rax, [rcx]
0x180021976  mov     rcx, rdx
0x180021979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002197e  cmp     eax, 1Dh; switch 30 cases
0x180021981  jbe     loc_18002262A
0x180021987  mov     r8d, [rsp+1E8h+var_178]; jumptable 0000000180022645 default case
0x18002198c  test    r8d, r8d
0x18002198f  js      loc_180021D8C
0x180021995  mov     rcx, [rsp+1E8h+var_110]
0x18002199d  xor     ebx, ebx
0x18002199f  mov     rdx, rsi
0x1800219a2  mov     [rsp+1E8h+var_178], ebx
0x1800219a6  mov     rax, [rcx]
0x1800219a9  mov     rax, [rax+8]
0x1800219ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219b2  mov     r8d, [rsp+1E8h+var_178]
0x1800219b7  lea     rbx, [r14+8]
0x1800219bb  mov     r15, rax
0x1800219be  test    r15, r15
0x1800219c1  jz      loc_180021DF9
0x1800219c7  mov     rcx, [r15]
0x1800219ca  mov     rax, [rcx+20h]
0x1800219ce  mov     rcx, r15
0x1800219d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d6  mov     rdx, rax
0x1800219d9  mov     rcx, [rax]
0x1800219dc  mov     rax, [rcx]
0x1800219df  mov     rcx, rdx
0x1800219e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219e7  lea     rcx, [r14+8]
0x1800219eb  xor     ebp, ebp
0x1800219ed  mov     [rsp+1E8h+var_108], rcx
0x1800219f5  mov     r12, rax
0x1800219f8  mov     rcx, [rcx]
0x1800219fb  xor     r14d, r14d
0x1800219fe  mov     r13, [rcx+28h]
0x180021a02  mov     esi, [rcx+20h]
0x180021a05  cmp     r14d, esi
0x180021a08  jnb     loc_180021DC9
0x180021a0e  lea     edi, [rsi+r14]
0x180021a12  shr     edi, 1
0x180021a14  imul    rbx, rdi, 70h ; 'p'
0x180021a18  add     rbx, r13
0x180021a1b  mov     rcx, rbx
0x180021a1e  mov     rax, [rbx]
0x180021a21  mov     rax, [rax]
0x180021a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a29  mov     r9d, 0FFFFFFFFh; cchCount1
0x180021a2f  mov     [rsp+1E8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180021a37  mov     r8, r12; lpString1
0x180021a3a  mov     [rsp+1E8h+lpString2], rax; lpString2
0x180021a3f  xor     edx, edx; dwCmpFlags
0x180021a41  mov     ecx, 7Fh; Locale
0x180021a46  call    cs:__imp_CompareStringW
0x180021a4c  cmp     eax, 2
0x180021a4f  jz      loc_180021C59
0x180021a55  cmp     eax, 1
0x180021a58  jnz     loc_180021C61
0x180021a5e  mov     esi, edi
0x180021a60  test    rbp, rbp
0x180021a63  jz      short loc_180021A05
0x180021a65  mov     rdi, [rbp+28h]
0x180021a69  cmp     rdi, [rbp+30h]
0x180021a6d  jz      loc_180021DC9
0x180021a73  mov     rax, [r15]
0x180021a76  mov     rcx, r15
0x180021a79  mov     rax, [rax+30h]
0x180021a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a82  cmp     eax, 1
0x180021a85  mov     rcx, r15
0x180021a88  mov     rax, [r15]
0x180021a8b  setnl   [rsp+1E8h+var_170]
0x180021a90  mov     rax, [rax+8]
0x180021a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a99  mov     rcx, [r15]
0x180021a9c  lea     ebx, [rax-1]
0x180021a9f  mov     rax, [rcx]
0x180021aa2  mov     rcx, r15
0x180021aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aaa  mov     r14, [rsp+1E8h+var_140]
0x180021ab2  mov     edx, ebx
0x180021ab4  mov     rcx, r14
0x180021ab7  mov     rax, [r14]
0x180021aba  mov     rax, [rax+8]
0x180021abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ac3  mov     rdx, rax
0x180021ac6  mov     rcx, [rax]
0x180021ac9  mov     rax, [rcx]
0x180021acc  mov     rcx, rdx
0x180021acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ad4  mov     rcx, [r14]
0x180021ad7  mov     esi, eax
0x180021ad9  mov     edx, ebx
0x180021adb  mov     rax, [rcx+8]
0x180021adf  mov     rcx, r14
0x180021ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ae7  mov     rdx, rax
0x180021aea  mov     rcx, [rax]
0x180021aed  mov     rax, [rcx+18h]
0x180021af1  mov     rcx, rdx
0x180021af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021af9  mov     r9, [rsp+1E8h+var_138]
0x180021b01  mov     r11d, eax
0x180021b04  movzx   r8d, word ptr [r9+r11*2]
0x180021b09  test    r8w, r8w
0x180021b0d  jz      loc_180022188
0x180021b13  mov     rax, [rsp+1E8h+var_158]
0x180021b1b  test    byte ptr [rax+r11*2], 8
0x180021b20  jnz     loc_180022188
0x180021b26  movzx   ecx, r8w; wchar_t
0x180021b2a  call    ?IsParenthesis@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsParenthesis(wchar_t)
0x180021b2f  test    al, al
0x180021b31  jnz     loc_180022188
0x180021b37  movzx   ecx, r8w; wchar_t
0x180021b3b  call    ?IsDoubleQuote@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsDoubleQuote(wchar_t)
0x180021b40  test    al, al
0x180021b42  jnz     loc_18002215B
0x180021b48  xor     ecx, ecx
0x180021b4a  xor     eax, eax
0x180021b4c  mov     ebx, 2
0x180021b51  cmp     esi, 0Ah
0x180021b54  cmovnz  ebx, eax
0x180021b57  mov     rax, [r15]
0x180021b5a  or      ebx, ecx
0x180021b5c  mov     rcx, r15
0x180021b5f  test    bl, 2
0x180021b62  jnz     loc_180022192
0x180021b68  mov     rax, [rax+18h]
0x180021b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b71  mov     r14d, eax
0x180021b74  mov     rcx, [r15]
0x180021b77  mov     rax, [rcx+28h]
0x180021b7b  mov     rcx, r15
0x180021b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b83  mov     rcx, [r15]
0x180021b86  mov     r12, rax
0x180021b89  mov     rax, [rcx+10h]
0x180021b8d  mov     rcx, r15
0x180021b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b95  mov     rcx, [r15]
0x180021b98  mov     r13d, eax
0x180021b9b  mov     rax, [rcx+8]
0x180021b9f  mov     rcx, r15
0x180021ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ba7  mov     rcx, [r15]
0x180021baa  mov     [rsp+1E8h+var_118], eax
0x180021bb1  mov     rax, [rcx]
0x180021bb4  mov     rcx, r15
0x180021bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bbc  mov     rsi, [rdi]
0x180021bbf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021bc6  mov     ecx, 48h ; 'H'; unsigned __int64
0x180021bcb  mov     [rsp+1E8h+var_178], eax
0x180021bcf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021bd4  mov     rcx, rax
0x180021bd7  test    rax, rax
0x180021bda  jz      loc_18002208C
0x180021be0  mov     dword ptr [rax], 5
0x180021be6  mov     [rax+8], rsi
0x180021bea  test    rsi, rsi
0x180021bed  jz      loc_18002282C
0x180021bf3  mov     rdx, [rsi]
0x180021bf6  mov     [rax+10h], rdx
0x180021bfa  mov     eax, [rsp+1E8h+var_178]
0x180021bfe  mov     rdx, [rsp+1E8h+var_128]
0x180021c06  mov     [rcx+18h], eax
0x180021c09  mov     eax, [rsp+1E8h+var_118]
0x180021c10  mov     [rcx+1Ch], eax
0x180021c13  mov     rax, 3FF0000000000000h
0x180021c1d  mov     [rcx+20h], rax
0x180021c21  movzx   eax, [rsp+1E8h+var_170]
  ... truncated ...
```
