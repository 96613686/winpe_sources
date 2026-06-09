# SemanticsUM::StructuredSemanticSolutionMaker::MakeStructuredSemanticSolution(wchar_t const *,SemanticsUM::TokenCollectionUM const &,ulong,ulong,IWordBreaker *,SemanticsUM::SchemaEngine *,SemanticsUM::SemSolution const *,SemanticsUM::StructuredSemanticSolution * *)

- ea: `0x18001455c`
- end: `0x1800155e3`
- name: `?MakeStructuredSemanticSolution@StructuredSemanticSolutionMaker@SemanticsUM@@QEBAJPEB_WAEBVTokenCollectionUM@2@KKPEAUIWordBreaker@@PEAVSchemaEngine@2@PEBVSemSolution@2@PEAPEAVStructuredSemanticSolution@2@@Z`
- size: `4231`
- prototype: `int(SemanticsUM::StructuredSemanticSolutionMaker *__hidden this, const wchar_t *, const struct SemanticsUM::TokenCollectionUM *, unsigned int, unsigned int, struct IWordBreaker *, struct SemanticsUM::SchemaEngine *, const struct SemanticsUM::SemSolution *, struct SemanticsUM::StructuredSemanticSolution **)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012d84`

## callees

- `0x1800136e8`
- `0x18001378c`
- `0x1800137c0`
- `0x180013810`
- `0x180013884`
- `0x18001397c`
- `0x180013b18`
- `0x180013c38`
- `0x18001455c`
- `0x180015a40`
- `0x180015b90`
- `0x180015f38`
- `0x180016360`
- `0x180016620`
- `0x18004df90`
- `0x180054284`
- `0x180054d18`
- `0x180054f84`
- `0x180055454`
- `0x18005bd88`
- `0x18005db64`
- `0x18006b448`
- `0x18006b49c`
- `0x18006b7b4`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001542f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800152cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001542f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SemanticsUM::StructuredSemanticSolutionMaker::MakeStructuredSemanticSolution(
        wchar_t *this,
        wchar_t *a2,
        wchar_t *a3,
        unsigned int a4,
        wchar_t **a5,
        struct IWordBreaker *a6,
        const struct SemanticsUM::Entity **a7,
        const struct SemanticsUM::SemSolution *a8,
        struct SemanticsUM::StructuredSemanticSolution **a9)
{
  struct SemanticsUM::StructuredSemanticSolution *v11; // r12
  struct CompoundCondition *v12; // rax
  struct CompoundCondition *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  const struct SemanticsUM::SemSolution *v18; // r13
  const struct SemanticsUM::Entity *v19; // r14
  double v20; // xmm6_8
  int v21; // eax
  int SemSolutionLL; // ebx
  char *v23; // rcx
  wchar_t *v25; // rax
  wchar_t *v26; // rbx
  SemanticsUM::StructuredSemanticSolution *v27; // r15
  SemanticsUM::SemStack *v28; // rax
  __int64 v29; // rdx
  SemanticsUM::SemStack *v30; // r11
  int v31; // r12d
  SemanticsUM::EntityCondition *v32; // rsi
  __int64 v33; // r9
  __int64 v34; // r8
  SemanticsUM::SemSolutionLL *v35; // r10
  __int64 v36; // r13
  char v37; // cl
  SemanticsUM::CompoundCondition *v38; // rax
  struct SemanticsUM::SemanticCondition *v39; // r10
  __int64 v40; // r14
  int v41; // r12d
  int v42; // r12d
  int v43; // r12d
  SemanticsUM::SchemaEngine *v44; // r15
  wchar_t *v45; // r15
  __int64 v46; // rdx
  __int64 v47; // rcx
  const size_t *v48; // r8
  int v49; // eax
  __int64 (__fastcall ***v50)(_QWORD); // rcx
  __int64 v51; // rax
  const struct SemanticsUM::Entity *v52; // rcx
  void *v53; // r15
  __int64 v54; // rax
  __int64 v55; // rdi
  SemanticsUM::SemStack *v56; // rsi
  wchar_t *v57; // rcx
  __int64 v58; // r10
  const struct SemanticsUM::Entity *v59; // r11
  __int64 *j; // rdx
  int v61; // eax
  const struct SemanticsUM::Entity *v62; // r15
  __int64 v63; // r10
  SemanticsUM::EntityCondition *v64; // rax
  int v65; // r12d
  __int64 v66; // r8
  SemanticsUM::SemSolutionLL *v67; // r9
  int v68; // edx
  struct SemanticsUM::SemanticCondition *v69; // rcx
  int v70; // r9d
  struct SemanticsUM::SemanticCondition *v71; // rdx
  __int64 **i; // rcx
  int v73; // eax
  unsigned int v74; // r9d
  const struct SemanticsUM::Entity *v75; // r8
  const wchar_t *v76; // rdx
  SemanticsUM::EntityConditionLL *v77; // rdx
  SemanticsUM::SemStackNode *v78; // rcx
  __int64 v79; // rax
  wchar_t *v80; // rcx
  unsigned int v81; // r15d
  __int64 v82; // rax
  SemanticsUM::EntityCondition *v83; // rax
  wchar_t *v84; // rcx
  struct CompoundCondition *v85; // r15
  SemanticsUM::CompoundCondition *v86; // rax
  SemanticsUM::CompoundCondition *v87; // rax
  __int64 v88; // rdx
  SemanticsUM::SemanticCondition *v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rcx
  struct SemanticsUM::SemanticCondition *v92; // rcx
  __int64 v93; // rcx
  struct SemanticsUM::SemanticCondition *v94; // rcx
  __int64 v95; // rcx
  struct SemanticsUM::SemanticCondition *v96; // rcx
  SemanticsUM::EntityConditionLL *v97; // r15
  char *v98; // rcx
  struct SemanticsUM::EntityConditionLL *v99; // r10
  int v100; // edi
  struct SemanticsUM::SemanticCondition *v101; // rcx
  struct SemanticsUM::SemanticCondition *v102; // rcx
  __int64 v103; // r12
  __int64 v104; // rcx
  SemanticsUM::EntityConditionLL *v105; // rax
  int v106; // eax
  struct SemanticsUM::SemanticCondition *v107; // rcx
  unsigned int v108; // r9d
  const struct SemanticsUM::Entity *v109; // r8
  SemanticsUM::CompoundCondition *v110; // rcx
  _DWORD *v111; // rcx
  wchar_t *v112; // rcx
  struct ITokenCollection *v113; // [rsp+50h] [rbp-B0h]
  int v114; // [rsp+70h] [rbp-90h]
  char v115; // [rsp+74h] [rbp-8Ch]
  SemanticsUM::CompoundCondition *v116; // [rsp+78h] [rbp-88h]
  __int64 v117; // [rsp+80h] [rbp-80h]
  __int64 v118; // [rsp+88h] [rbp-78h]
  struct SemanticsUM::SemanticCondition *v119[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v120; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v121[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v122; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v123; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-28h] BYREF
  int v125; // [rsp+E0h] [rbp-20h]
  __int128 v126; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v127; // [rsp+100h] [rbp+0h] BYREF
  SemanticsUM::SemStack *v128; // [rsp+110h] [rbp+10h]
  SemanticsUM::EntityConditionLL *v129; // [rsp+118h] [rbp+18h] BYREF
  int v130; // [rsp+120h] [rbp+20h]
  int v131; // [rsp+124h] [rbp+24h]
  SemanticsUM::StructuredSemanticSolution *v132; // [rsp+128h] [rbp+28h]
  SemanticsUM::SemSolutionLL *v133; // [rsp+130h] [rbp+30h]
  struct SemanticsUM::StructuredSemanticSolution *v134; // [rsp+138h] [rbp+38h]
  struct SemanticsUM::SemanticCondition *v135; // [rsp+140h] [rbp+40h] BYREF
  SemanticsUM::SemSolutionLL *v136; // [rsp+148h] [rbp+48h] BYREF
  wchar_t *v137; // [rsp+150h] [rbp+50h]
  SemanticsUM::EntityCondition *v138; // [rsp+158h] [rbp+58h]
  wchar_t *v139; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t *v140; // [rsp+1B8h] [rbp+B8h]
  wchar_t *v141; // [rsp+1C0h] [rbp+C0h]

  v141 = a3;
  v140 = a2;
  v139 = this;
  v11 = 0;
  v134 = 0;
  v12 = (struct CompoundCondition *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( !v12 )
  {
    SemSolutionLL = -2147024882;
    goto LABEL_4;
  }
  *((_QWORD *)v12 + 1) = SemanticsUM::CompoundCondition::`vbtable'{for `SemanticsUM::SemanticCondition'};
  *((_QWORD *)v12 + 15) = &SemanticsUM::ValueCondition::`vbtable'{for `SemanticsUM::IValueCondition'};
  *((_QWORD *)v12 + 12) = &SemanticsUM::ISemanticCondition::`vftable';
  *((_QWORD *)v12 + 14) = &SemanticsUM::ICompoundCondition::`vftable'{for `SemanticsUM::ICompoundCondition'};
  *(_QWORD *)((char *)v12 + *(int *)(*((_QWORD *)v12 + 15) + 4LL) + 120) = &SemanticsUM::ICompoundCondition::`vftable'{for `SemanticsUM::ISemanticCondition'};
  *(_QWORD *)v12 = &SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::SemanticCondition'};
  *(_QWORD *)((char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8) = &SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::ISemanticCondition'};
  v14 = *(int *)(*((_QWORD *)v12 + 1) + 4LL);
  *(_DWORD *)((char *)v12 + v14 + 4) = v14 - 72;
  *((_QWORD *)v12 + 2) = 0;
  *((_DWORD *)v12 + 6) = -1;
  *((_DWORD *)v12 + 7) = -1;
  *((_QWORD *)v12 + 4) = 0;
  *((_DWORD *)v12 + 10) = -1;
  *((_DWORD *)v12 + 11) = -1;
  *((_QWORD *)v12 + 6) = 0;
  *((_QWORD *)v12 + 7) = 0;
  *((_DWORD *)v12 + 16) = -1;
  *((_DWORD *)v12 + 17) = -1;
  *(_QWORD *)v12 = &SemanticsUM::CompoundCondition::`vftable'{for `SemanticsUM::SemanticCondition'};
  *(_QWORD *)((char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 4LL) + 8) = &SemanticsUM::CompoundCondition::`vftable'{for `SemanticsUM::ISemanticCondition'};
  *(_QWORD *)((char *)v12 + *(int *)(*((_QWORD *)v12 + 1) + 8LL) + 8) = &SemanticsUM::CompoundCondition::`vftable'{for `SemanticsUM::ICompoundCondition'};
  v15 = *(int *)(*((_QWORD *)v12 + 1) + 4LL);
  *(_DWORD *)((char *)v12 + v15 + 4) = v15 - 88;
  v16 = *(int *)(*((_QWORD *)v12 + 1) + 8LL);
  v17 = (unsigned int)(v16 - 104);
  *(_DWORD *)((char *)v12 + v16 + 4) = v17;
  *((_QWORD *)v12 + 9) = 0;
  *((_QWORD *)v12 + 10) = 0;
  v18 = a8;
  v19 = (const struct SemanticsUM::Entity *)*((_QWORD *)a8 + 7);
  v20 = *((double *)a8 + 2);
  v139 = 0;
  v21 = _AllocString<CTCoAllocPolicy>(v16, v17, (const size_t *)a2, &v139);
  if ( v21 >= 0 )
  {
    v25 = (wchar_t *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v137 = v25;
    v26 = v139;
    if ( v25 )
      v27 = SemanticsUM::StructuredSemanticSolution::StructuredSemanticSolution(
              (SemanticsUM::StructuredSemanticSolution *)v25,
              v20,
              v19,
              v13,
              v139,
              a4,
              (unsigned int)a5,
              a6);
    else
      v27 = 0;
    v132 = v27;
    if ( !v27 )
    {
      CoTaskMemFree(v26);
      v21 = -2147024882;
      goto LABEL_3;
    }
    v136 = 0;
    SemSolutionLL = SemanticsUM::StructuredSemanticSolutionMaker::GetSemSolutionLL(v18, &v136);
    if ( SemSolutionLL < 0 )
    {
LABEL_73:
      (*(void (__fastcall **)(SemanticsUM::StructuredSemanticSolution *))(*(_QWORD *)v27 + 16LL))(v27);
      goto LABEL_4;
    }
    v129 = 0;
    v28 = (SemanticsUM::SemStack *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    v30 = v28;
    v128 = v28;
    if ( !v28 )
    {
      SemSolutionLL = -2147024882;
LABEL_69:
      if ( v129 )
        SemanticsUM::EntityConditionLL::`scalar deleting destructor'(v129, v29);
      if ( v136 )
        SemanticsUM::SemSolutionLL::`scalar deleting destructor'(v136, v29);
      goto LABEL_73;
    }
    *(_QWORD *)v28 = 0;
    v31 = 0;
    v114 = 0;
    v32 = 0;
    v121[0] = 0;
    *(_QWORD *)&v122 = 0;
    *((_QWORD *)&v122 + 1) = -1;
    v29 = 0;
    *(_QWORD *)&v120 = 0;
    *((_QWORD *)&v120 + 1) = -1;
    v33 = 0;
    v117 = 0;
    v34 = 0;
    v118 = 0;
    *(_QWORD *)&v127 = 0;
    *((_QWORD *)&v127 + 1) = -1;
    *(_QWORD *)&v126 = 0;
    *((_QWORD *)&v126 + 1) = -1;
    v35 = v136;
    v133 = v136;
    if ( !v136 )
    {
      v40 = 0;
      SemSolutionLL = 0;
      v55 = 0;
      goto LABEL_57;
    }
    v115 = 0;
    v36 = 0;
    v37 = 0;
    LOBYTE(v139) = 0;
    v125 = -1;
    SemSolutionLL = 0;
    v38 = v13;
    v116 = v13;
    v130 = -2147024882;
    while ( 1 )
    {
      v39 = *(struct SemanticsUM::SemanticCondition **)v35;
      v119[0] = v39;
      v40 = *((_QWORD *)v39 + 1);
      if ( *(int *)(v40 + 24) >= 0 )
        break;
LABEL_52:
      v35 = (SemanticsUM::SemSolutionLL *)*((_QWORD *)v133 + 1);
      v133 = v35;
      v27 = v132;
      v30 = v128;
      if ( !v35 )
      {
        if ( SemSolutionLL < 0 )
        {
          v56 = v128;
          goto LABEL_143;
        }
        if ( v36 && !v37 )
        {
          LODWORD(v113) = *(_DWORD *)(v40 + 24);
          SemSolutionLL = SemanticsUM::EntityCondition::Create(
                            (const struct SemanticsUM::SemanticKeyword *)&v127,
                            (const struct SemanticsUM::SemanticKeyword *)&v126,
                            *(_DWORD *)(v36 + 40),
                            *(_DWORD *)(v36 + 44),
                            v13,
                            *(const wchar_t **)(*(_QWORD *)(v36 + 8) + 8LL),
                            **(const struct SemanticsUM::Entity ***)(v36 + 8),
                            *(_DWORD *)(v36 + 60),
                            v140,
                            v141,
                            v113,
                            *(_DWORD *)(v40 + 28),
                            (struct SemanticsUM::EntityCondition **)v121);
          if ( SemSolutionLL < 0 )
          {
            v56 = v128;
            goto LABEL_143;
          }
          SemanticsUM::CompoundCondition::AddChild(v116, (struct SemanticsUM::SemanticCondition *)v121[0]);
          v55 = v117;
          v34 = v118;
          v56 = v128;
          v18 = a8;
          goto LABEL_58;
        }
        v55 = v33;
        v18 = a8;
LABEL_57:
        v56 = v30;
LABEL_58:
        if ( (_QWORD)v122 )
        {
          v139 = 0;
          if ( !v34 )
            v34 = v40;
          SemSolutionLL = SemanticsUM::SemanticError::Create(
                            *(unsigned int *)(v34 + 40),
                            *(unsigned int *)(v34 + 44),
                            4,
                            &v139);
          if ( SemSolutionLL < 0 )
            goto LABEL_143;
          v80 = v139;
          *((_QWORD *)v139 + 1) = *((_QWORD *)v27 + 5);
          *((_QWORD *)v27 + 5) = v80;
        }
        if ( !(_QWORD)v120 )
        {
LABEL_64:
          if ( v31 > 0 )
          {
            v100 = v31;
            while ( v31 > 0 && v18 )
            {
              v111 = (_DWORD *)*((_QWORD *)v18 + 1);
              if ( *v111 == 3 )
              {
                if ( v31 <= v100 )
                {
                  v139 = 0;
                  SemSolutionLL = SemanticsUM::SemanticError::Create(
                                    (unsigned int)v111[10],
                                    (unsigned int)v111[11],
                                    1,
                                    &v139);
                  if ( SemSolutionLL < 0 )
                    goto LABEL_143;
                  v112 = v139;
                  *((_QWORD *)v139 + 1) = *((_QWORD *)v27 + 5);
                  *((_QWORD *)v27 + 5) = v112;
                  --v100;
                }
                --v31;
              }
              else if ( *v111 == 4 )
              {
                ++v31;
              }
              v18 = *(const struct SemanticsUM::SemSolution **)v18;
            }
          }
          v11 = v27;
          (*(void (__fastcall **)(SemanticsUM::StructuredSemanticSolution *))(*(_QWORD *)v27 + 8LL))(v27);
          goto LABEL_66;
        }
        v139 = 0;
        if ( v55 )
          v40 = v55;
        SemSolutionLL = SemanticsUM::SemanticError::Create(
                          *(unsigned int *)(v40 + 40),
                          *(unsigned int *)(v40 + 44),
                          3,
                          &v139);
        if ( SemSolutionLL >= 0 )
        {
          v57 = v139;
          *((_QWORD *)v139 + 1) = *((_QWORD *)v27 + 5);
          *((_QWORD *)v27 + 5) = v57;
          goto LABEL_64;
        }
LABEL_143:
        v11 = v134;
LABEL_66:
        if ( v56 )
          SemanticsUM::SemStack::`scalar deleting destructor'(v56, v29);
        v27 = v132;
        goto LABEL_69;
      }
    }
    v41 = *(_DWORD *)v40;
    if ( *(int *)v40 > 5 )
    {
      if ( v41 != 6 )
      {
        if ( v41 == 7 )
        {
          v119[0] = 0;
          SemSolutionLL = SemanticsUM::SemanticError::Create(
                            *(unsigned int *)(v40 + 40),
                            *(unsigned int *)(v40 + 44),
                            5,
                            v119);
          v31 = v114;
          v29 = v120;
          v34 = v118;
          v33 = v117;
          if ( SemSolutionLL >= 0 )
          {
            v107 = v119[0];
            *((_QWORD *)v119[0] + 1) = *((_QWORD *)v27 + 5);
            *((_QWORD *)v27 + 5) = v107;
            v115 = 1;
          }
          goto LABEL_50;
        }
        if ( v41 != 8 )
        {
          if ( v41 == 9 )
          {
            v119[0] = 0;
            SemSolutionLL = SemanticsUM::EntityIndicator::Create(
                              *(_DWORD *)(v40 + 40),
                              *(_DWORD *)(v40 + 44),
                              *(const struct SemanticsUM::Entity **)(v40 + 16),
                              v119);
            v34 = v118;
            v33 = v117;
            v38 = v116;
            if ( SemSolutionLL < 0 )
            {
              v31 = v114;
              v29 = v120;
            }
            else
            {
              v101 = v119[0];
              *((_QWORD *)v119[0] + 1) = *((_QWORD *)v116 + 10);
              v38 = v116;
              *((_QWORD *)v116 + 10) = v101;
              *(_QWORD *)&v122 = 0;
              *((_QWORD *)&v122 + 1) = -1;
              v29 = 0;
              *(_QWORD *)&v120 = 0;
              *((_QWORD *)&v120 + 1) = -1;
              v115 = 0;
              v31 = v114;
            }
            goto LABEL_51;
          }
          goto LABEL_246;
        }
        if ( !*((_DWORD *)v39 + 16) )
        {
          v77 = v129;
          v31 = v114;
          if ( !v129 )
          {
LABEL_133:
            v37 = (char)v139;
LABEL_82:
            v34 = v118;
            v33 = v117;
            if ( SemSolutionLL < 0 )
              goto LABEL_176;
            *(_QWORD *)&v122 = 0;
            *((_QWORD *)&v122 + 1) = -1;
            v29 = 0;
            *(_QWORD *)&v120 = 0;
            *((_QWORD *)&v120 + 1) = -1;
            v115 = 0;
LABEL_84:
            v38 = v116;
            goto LABEL_52;
          }
          v97 = v129;
          while ( 1 )
          {
            if ( SemSolutionLL < 0 )
              goto LABEL_47;
            if ( !v97 )
              goto LABEL_258;
            v103 = *((_QWORD *)v97 + 1);
            *(_QWORD *)(v103 + 96) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v133 + 8LL) + 8LL) + 8LL);
            if ( v97 == v77 )
            {
              v104 = v103 + *(int *)(*(_QWORD *)(v103 + 8) + 12LL) + 8LL;
              if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v104 + 8LL))(v104) )
              {
                v119[0] = 0;
                SemSolutionLL = SemanticsUM::ComputeIndicatorString(
                                  (SemanticsUM *)v140,
                                  v141,
                                  (struct ITokenCollection *)*(unsigned int *)(v40 + 24),
                                  (__int64)v119);
                v77 = v129;
                if ( SemSolutionLL < 0 )
                {
                  v31 = v114;
                  continue;
                }
                *(struct SemanticsUM::SemanticCondition **)(v103 + 88) = v119[0];
              }
              v77 = v129;
            }
            v105 = *(SemanticsUM::EntityConditionLL **)v97;
            v97 = v105;
            v31 = v114;
            if ( v105 && *((_DWORD *)v105 + 4) < v114 )
            {
LABEL_258:
              if ( v77 )
                SemanticsUM::EntityConditionLL::`scalar deleting destructor'(v77, (unsigned int)v77);
              v129 = 0;
              goto LABEL_133;
            }
          }
        }
        if ( !v13 )
        {
          if ( v32 )
            v13 = (struct CompoundCondition *)*((_QWORD *)v32 + 13);
          else
            v13 = v116;
        }
        v37 = (char)v139;
        if ( !v36 || (_BYTE)v139 )
          goto LABEL_80;
        v119[0] = 0;
        LODWORD(v113) = *(_DWORD *)(v36 + 24);
        v106 = SemanticsUM::EntityCondition::Create(
                 (const struct SemanticsUM::SemanticKeyword *)&v127,
                 (const struct SemanticsUM::SemanticKeyword *)&v126,
                 *(_DWORD *)(v36 + 40),
                 *(_DWORD *)(v36 + 44),
                 v13,
                 *(const wchar_t **)(*(_QWORD *)(v36 + 8) + 8LL),
                 **(const struct SemanticsUM::Entity ***)(v36 + 8),
                 *(_DWORD *)(v36 + 60),
                 v140,
                 v141,
                 v113,
                 *(_DWORD *)(v36 + 28),
                 v119);
        SemSolutionLL = v106;
        if ( v106 >= 0 )
        {
          SemanticsUM::CompoundCondition::AddChild(v116, v119[0]);
          v29 = v120;
          v34 = v118;
          v33 = v117;
          v37 = (char)v139;
LABEL_80:
          v31 = v114;
          if ( SemSolutionLL >= 0 )
          {
            v36 = v40;
            v127 = v122;
            v126 = v120;
            v37 = 0;
            LOBYTE(v139) = 0;
            v125 = v114;
            v32 = 0;
            v121[0] = 0;
            goto LABEL_82;
          }
          goto LABEL_84;
        }
        goto LABEL_46;
      }
    }
    else
    {
      if ( v41 == 5 )
        goto LABEL_23;
      if ( v41 )
      {
        v42 = v41 - 1;
        if ( !v42 )
        {
          if ( v29 )
          {
            v119[0] = 0;
            v95 = v40;
            if ( v33 )
              v95 = v33;
            SemSolutionLL = SemanticsUM::SemanticError::Create(
                              *(unsigned int *)(v95 + 40),
                              *(unsigned int *)(v95 + 44),
                              3,
                              v119);
            v34 = v118;
            if ( SemSolutionLL < 0 )
            {
              v31 = v114;
              v29 = v120;
              v33 = v117;
              goto LABEL_50;
            }
            v96 = v119[0];
            *((_QWORD *)v119[0] + 1) = *((_QWORD *)v27 + 5);
            *((_QWORD *)v27 + 5) = v96;
          }
          else if ( SemSolutionLL < 0 )
          {
            goto LABEL_89;
          }
          v33 = v40;
          v117 = v40;
          v29 = *(_QWORD *)(v40 + 48);
          *(_QWORD *)&v120 = v29;
          *((_QWORD *)&v120 + 1) = *(_QWORD *)(v40 + 40);
          goto LABEL_88;
        }
        v43 = v42 - 1;
        if ( !v43 )
        {
          if ( !(_QWORD)v122 )
          {
            if ( SemSolutionLL >= 0 )
            {
LABEL_21:
              v34 = v40;
              v118 = v40;
              *(_QWORD *)&v122 = *(_QWORD *)(v40 + 48);
              *((_QWORD *)&v122 + 1) = *(_QWORD *)(v40 + 40);
LABEL_88:
              v115 = 0;
            }
LABEL_89:
            v31 = v114;
            goto LABEL_50;
          }
          v119[0] = 0;
          v93 = v40;
          if ( v34 )
            v93 = v34;
          SemSolutionLL = SemanticsUM::SemanticError::Create(
                            *(unsigned int *)(v93 + 40),
                            *(unsigned int *)(v93 + 44),
                            4,
                            v119);
          v29 = v120;
          v33 = v117;
          if ( SemSolutionLL >= 0 )
          {
            v94 = v119[0];
            *((_QWORD *)v119[0] + 1) = *((_QWORD *)v27 + 5);
            *((_QWORD *)v27 + 5) = v94;
            goto LABEL_21;
          }
          v31 = v114;
LABEL_49:
          v34 = v118;
LABEL_50:
          v38 = v116;
LABEL_51:
          v37 = (char)v139;
          goto LABEL_52;
        }
        v65 = v43 - 1;
        if ( !v65 )
        {
          v66 = 1;
          v67 = v133;
          while ( 1 )
          {
            v67 = (SemanticsUM::SemSolutionLL *)*((_QWORD *)v67 + 1);
            if ( !v67 )
            {
LABEL_117:
              v119[0] = 0;
              SemSolutionLL = SemanticsUM::SemanticError::Create(
                                *(unsigned int *)(v40 + 40),
                                *(unsigned int *)(v40 + 44),
                                1,
                                v119);
              v31 = v114;
              if ( SemSolutionLL < 0 )
                goto LABEL_47;
              v69 = v119[0];
              *((_QWORD *)v119[0] + 1) = *((_QWORD *)v27 + 5);
              *((_QWORD *)v27 + 5) = v69;
              v70 = -1;
              goto LABEL_166;
            }
            v68 = **(_DWORD **)(*(_QWORD *)v67 + 8LL);
            if ( (unsigned int)(v68 - 5) <= 1 || !v68 )
              break;
            if ( v68 == 3 )
            {
              v66 = (unsigned int)(v66 + 1);
            }
            else if ( v68 == 4 )
            {
              v66 = (unsigned int)(v66 - 1);
              if ( !(_DWORD)v66 )
                goto LABEL_117;
            }
          }
          if ( v13 )
          {
            v85 = v13;
          }
          else if ( v32 )
          {
            v85 = (struct CompoundCondition *)*((_QWORD *)v32 + 13);
          }
          else
          {
            v85 = v116;
          }
          SemSolutionLL = SemanticsUM::SemStack::Push(v30, v85, (struct SemanticsUM::EntityCondition *)v66);
          v31 = v114;
          if ( SemSolutionLL >= 0 )
          {
            v31 = ++v114;
            v86 = (SemanticsUM::CompoundCondition *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v86 )
            {
              v87 = SemanticsUM::CompoundCondition::CompoundCondition(
                      v86,
                      (const struct SemanticsUM::SemanticKeyword *)&v122,
                      (const struct SemanticsUM::SemanticKeyword *)&v120,
                      -1,
                      -1,
                      v85,
                      1);
              v13 = v87;
              if ( v87 )
              {
                SemSolutionLL = 0;
                SemanticsUM::CompoundCondition::AddChild(v85, v87);
LABEL_166:
                DWORD2(v122) = v70;
                HIDWORD(v122) = v70;
                DWORD2(v120) = v70;
                HIDWORD(v120) = v70;
                goto LABEL_141;
              }
            }
            else
            {
              v13 = 0;
            }
            SemSolutionLL = v130;
          }
          goto LABEL_47;
        }
        if ( v65 == 1 )
        {
          v78 = *(SemanticsUM::SemStackNode **)v30;
          if ( !*(_QWORD *)v30 )
          {
            v13 = v116;
            v119[0] = 0;
            SemSolutionLL = SemanticsUM::SemanticError::Create(
                              *(unsigned int *)(v40 + 40),
                              *(unsigned int *)(v40 + 44),
                              2,
                              v119);
            v31 = v114;
            if ( SemSolutionLL < 0 )
            {
              v29 = v120;
              v34 = v118;
              v33 = v117;
              v38 = v116;
              goto LABEL_51;
            }
            v92 = v119[0];
            *((_QWORD *)v119[0] + 1) = *((_QWORD *)v27 + 5);
            *((_QWORD *)v27 + 5) = v92;
            goto LABEL_140;
          }
          *(_QWORD *)v30 = *(_QWORD *)v78;
          *(_QWORD *)v78 = 0;
          v13 = (struct CompoundCondition *)*((_QWORD *)v78 + 1);
          if ( !v13 )
            v13 = *(struct CompoundCondition **)(*((_QWORD *)v78 + 2) + 104LL);
          v31 = --v114;
          SemanticsUM::SemStackNode::`scalar deleting destructor'(v78, v29);
          if ( v36 && v31 <= v125 )
          {
            v37 = (char)v139;
            if ( !(_BYTE)v139 )
            {
              v119[0] = 0;
              LODWORD(v113) = *(_DWORD *)(v36 + 24);
              SemSolutionLL = SemanticsUM::EntityCondition::Create(
                                (const struct SemanticsUM::SemanticKeyword *)&v127,
                                (const struct SemanticsUM::SemanticKeyword *)&v126,
                                *(_DWORD *)(v36 + 40),
                                *(_DWORD *)(v36 + 44),
                                v13,
                                *(const wchar_t **)(*(_QWORD *)(v36 + 8) + 8LL),
                                **(const struct SemanticsUM::Entity ***)(v36 + 8),
                                *(_DWORD *)(v36 + 60),
                                v140,
                                v141,
                                v113,
                                *(_DWORD *)(v36 + 28),
                                v119);
              if ( SemSolutionLL < 0 )
                goto LABEL_47;
              SemanticsUM::CompoundCondition::AddChild(v116, v119[0]);
              v37 = (char)v139;
            }
            if ( SemSolutionLL < 0 )
            {
              v34 = v118;
              v33 = v117;
LABEL_176:
              v38 = v116;
              v29 = v120;
              goto LABEL_52;
            }
            v36 = 0;
            *(_QWORD *)&v127 = 0;
            *((_QWORD *)&v127 + 1) = -1;
            *(_QWORD *)&v126 = 0;
            *((_QWORD *)&v126 + 1) = -1;
            v125 = -1;
          }
          v114 = v31;
          if ( SemSolutionLL >= 0 )
          {
LABEL_140:
            *((_QWORD *)&v122 + 1) = -1;
            *((_QWORD *)&v120 + 1) = -1;
LABEL_141:
            v32 = 0;
            v29 = 0;
            *(_QWORD *)&v120 = 0;
            *(_QWORD *)&v122 = 0;
            v121[0] = 0;
            v115 = 0;
            goto LABEL_48;
          }
LABEL_47:
          v29 = v120;
LABEL_48:
          v33 = v117;
          goto LABEL_49;
        }
LABEL_246:
        v119[0] = 0;
        SemSolutionLL = SemanticsUM::SemanticError::Create(
                          *(unsigned int *)(v40 + 40),
                          *(unsigned int *)(v40 + 44),
                          6,
                          v119);
        v31 = v114;
        v34 = v118;
        v33 = v117;
        if ( SemSolutionLL < 0 )
        {
          v29 = v120;
        }
        else
        {
          v102 = v119[0];
          *((_QWORD *)v119[0] + 1) = *((_QWORD *)v27 + 5);
          *((_QWORD *)v27 + 5) = v102;
          *(_QWORD *)&v122 = 0;
          *((_QWORD *)&v122 + 1) = -1;
          v29 = 0;
          *(_QWORD *)&v120 = 0;
          *((_QWORD *)&v120 + 1) = -1;
          v115 = 0;
        }
        goto LABEL_50;
      }
    }
    v38 = v116;
LABEL_23:
    if ( !v13 )
    {
      if ( v32 )
        v13 = (struct CompoundCondition *)*((_QWORD *)v32 + 13);
      else
        v13 = v38;
    }
    if ( v41 == 5 && v36 && v125 != -1 )
    {
      v44 = (SemanticsUM::SchemaEngine *)a7;
      if ( v125 < v114 )
      {
        v71 = **(struct SemanticsUM::SemanticCondition ***)(v36 + 8);
        v135 = v71;
        if ( v71 != **(struct SemanticsUM::SemanticCondition ***)(v40 + 8)
          && SemanticsUM::SchemaEngine::InheritsFrom((SemanticsUM::SchemaEngine *)a7, v71, a7[13]) )
        {
          v41 = 0;
          goto LABEL_125;
        }
      }
    }
    else
    {
      v44 = (SemanticsUM::SchemaEngine *)a7;
    }
    v135 = *(struct SemanticsUM::SemanticCondition **)(v40 + 16);
    if ( !v41 )
    {
LABEL_125:
      for ( i = *(__int64 ***)v39; i; i = (__int64 **)*i )
      {
        v73 = *(_DWORD *)i[1];
        if ( !v73 || (unsigned int)(v73 - 5) <= 4 )
          break;
      }
      if ( v32 && !v115 && (*((_DWORD *)v39 + 16) != 4 || !i || !*(_DWORD *)i[1]) )
      {
        if ( SemSolutionLL >= 0 )
          goto LABEL_30;
LABEL_46:
        v31 = v114;
        goto LABEL_47;
      }
      if ( !v36 )
      {
        v74 = 0;
        v75 = 0;
        v76 = 0;
LABEL_131:
        SemSolutionLL = SemanticsUM::EntityCondition::Create(
                          v13,
                          v76,
                          v75,
                          v74,
                          (struct SemanticsUM::EntityCondition **)v121);
        v32 = (SemanticsUM::EntityCondition *)v121[0];
        v37 = (char)v139;
LABEL_107:
        if ( SemSolutionLL < 0 )
          goto LABEL_193;
LABEL_108:
        SemanticsUM::CompoundCondition::AddChild(v13, v32);
        goto LABEL_30;
      }
      v81 = *(_DWORD *)(v36 + 60);
      v82 = *(_QWORD *)(v36 + 8);
      pv = *(LPVOID *)v82;
      v137 = *(wchar_t **)(v82 + 8);
      v131 = *(_DWORD *)(v36 + 44);
      LODWORD(v123) = *(_DWORD *)(v36 + 40);
      v32 = 0;
      v121[0] = 0;
      SemSolutionLL = SemanticsUM::ComputeIndicatorString(
                        (SemanticsUM *)v140,
                        v141,
                        (struct ITokenCollection *)*(unsigned int *)(v36 + 24),
                        (__int64)v121);
      if ( SemSolutionLL >= 0 )
      {
        v83 = (SemanticsUM::EntityCondition *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
        v138 = v83;
        if ( !v83
          || (v32 = SemanticsUM::EntityCondition::EntityCondition(
                      v83,
                      (const struct SemanticsUM::SemanticKeyword *)&v127,
                      (const struct SemanticsUM::SemanticKeyword *)&v126,
                      v121[0],
                      (int)v123,
                      v131,
                      v13,
                      v137,
                      (const struct SemanticsUM::Entity *)pv,
                      v81)) == 0 )
        {
          v84 = v121[0];
LABEL_187:
          CoTaskMemFree(v84);
          v121[0] = (wchar_t *)v32;
          SemSolutionLL = v130;
          goto LABEL_46;
        }
      }
      goto LABEL_105;
    }
    if ( v41 == 6 )
    {
      v37 = (char)v139;
      if ( v36 && !(_BYTE)v139 )
      {
        pv = 0;
        LODWORD(v113) = *(_DWORD *)(v36 + 24);
        SemSolutionLL = SemanticsUM::EntityCondition::Create(
                          (const struct SemanticsUM::SemanticKeyword *)&v127,
                          (const struct SemanticsUM::SemanticKeyword *)&v126,
                          *(_DWORD *)(v36 + 40),
                          *(_DWORD *)(v36 + 44),
                          v13,
                          *(const wchar_t **)(*(_QWORD *)(v36 + 8) + 8LL),
                          **(const struct SemanticsUM::Entity ***)(v36 + 8),
                          *(_DWORD *)(v36 + 60),
                          v140,
                          v141,
                          v113,
                          *(_DWORD *)(v36 + 28),
                          (struct SemanticsUM::EntityCondition **)&pv);
        if ( SemSolutionLL < 0 )
          goto LABEL_46;
        SemanticsUM::CompoundCondition::AddChild(v116, (struct SemanticsUM::SemanticCondition *)pv);
        v37 = (char)v139;
      }
      if ( SemSolutionLL < 0 )
      {
LABEL_193:
        v31 = v114;
        v29 = v120;
        v34 = v118;
        v33 = v117;
        goto LABEL_84;
      }
      v36 = 0;
      if ( v32 )
      {
        v98 = (char *)v32 + *(int *)(*((_QWORD *)v32 + 1) + 12LL) + 8;
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v98 + 16LL))(v98) && !*((_QWORD *)v32 + 14) )
          goto LABEL_30;
      }
      v108 = 0;
      v109 = 0;
      goto LABEL_280;
    }
    v37 = (char)v139;
    if ( v36 && !(_BYTE)v139 )
    {
      if ( SemanticsUM::SchemaEngine::InheritsFrom(
             v44,
             **(const struct SemanticsUM::Entity ***)(v40 + 8),
             **(const struct SemanticsUM::Entity ***)(v36 + 8)) )
      {
        v37 = (char)v139;
      }
      else
      {
        v123 = 0;
        LODWORD(v113) = *(_DWORD *)(v36 + 24);
        SemSolutionLL = SemanticsUM::EntityCondition::Create(
                          (const struct SemanticsUM::SemanticKeyword *)&v127,
                          (const struct SemanticsUM::SemanticKeyword *)&v126,
                          *(_DWORD *)(v36 + 40),
                          *(_DWORD *)(v36 + 44),
                          v13,
                          *(const wchar_t **)(v58 + 8),
                          v59,
                          *(_DWORD *)(v36 + 60),
                          v140,
                          v141,
                          v113,
                          *(_DWORD *)(v36 + 28),
                          (struct SemanticsUM::EntityCondition **)&v123);
        if ( SemSolutionLL < 0 )
          goto LABEL_46;
        if ( v13 )
        {
          v110 = v13;
        }
        else if ( !v32 || (v110 = (SemanticsUM::CompoundCondition *)*((_QWORD *)v32 + 13)) == 0 )
        {
          v110 = v116;
        }
        SemanticsUM::CompoundCondition::AddChild(v110, (struct SemanticsUM::SemanticCondition *)v123);
        *(_QWORD *)&v127 = 0;
        *((_QWORD *)&v127 + 1) = -1;
        *(_QWORD *)&v126 = 0;
        *((_QWORD *)&v126 + 1) = -1;
        v37 = 1;
        LOBYTE(v139) = 1;
      }
      v39 = v119[0];
    }
    if ( SemSolutionLL < 0 )
      goto LABEL_193;
    for ( j = **(__int64 ***)v133; j; j = (__int64 *)*j )
    {
      v61 = *(_DWORD *)j[1];
      if ( !v61 || (unsigned int)(v61 - 5) <= 4 )
        break;
    }
    if ( !v32 )
    {
LABEL_100:
      if ( !v36
        || (v62 = **(const struct SemanticsUM::Entity ***)(v36 + 8),
            !SemanticsUM::SchemaEngine::InheritsFrom(
               (SemanticsUM::SchemaEngine *)a7,
               **(const struct SemanticsUM::Entity ***)(v40 + 8),
               v62)) )
      {
        v88 = *(_QWORD *)(v40 + 8);
        v74 = *(_DWORD *)(v40 + 60);
        v75 = *(const struct SemanticsUM::Entity **)v88;
        v76 = *(const wchar_t **)(v88 + 8);
        goto LABEL_131;
      }
      LODWORD(v123) = *(_DWORD *)(v36 + 60);
      v137 = *(wchar_t **)(v63 + 8);
      v131 = *(_DWORD *)(v36 + 44);
      LODWORD(v121[0]) = *(_DWORD *)(v36 + 40);
      v32 = 0;
      pv = 0;
      SemSolutionLL = SemanticsUM::ComputeIndicatorString(
                        (SemanticsUM *)v140,
                        v141,
                        (struct ITokenCollection *)*(unsigned int *)(v36 + 24),
                        (__int64)&pv);
      if ( SemSolutionLL >= 0 )
      {
        v64 = (SemanticsUM::EntityCondition *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
        v138 = v64;
        if ( !v64
          || (v32 = SemanticsUM::EntityCondition::EntityCondition(
                      v64,
                      (const struct SemanticsUM::SemanticKeyword *)&v127,
                      (const struct SemanticsUM::SemanticKeyword *)&v126,
                      (wchar_t *)pv,
                      (int)v121[0],
                      v131,
                      v13,
                      v137,
                      v62,
                      (unsigned int)v123)) == 0 )
        {
          v84 = (wchar_t *)pv;
          goto LABEL_187;
        }
      }
LABEL_105:
      v121[0] = (wchar_t *)v32;
      if ( SemSolutionLL < 0 )
        goto LABEL_46;
      *(_QWORD *)&v127 = 0;
      *((_QWORD *)&v127 + 1) = -1;
      *(_QWORD *)&v126 = 0;
      *((_QWORD *)&v126 + 1) = -1;
      v37 = 1;
      LOBYTE(v139) = 1;
      goto LABEL_107;
    }
    if ( *(_DWORD *)(*(_QWORD *)v133 + 64LL) == 3 )
    {
      if ( !j )
      {
LABEL_203:
        v90 = *((_QWORD *)v39 + 18);
        if ( !v90
          || (v91 = j[18]) == 0
          || v90 != v91
          || *((_DWORD *)v39 + 35) <= *(_DWORD *)(v90 + 140)
          || *((_DWORD *)j + 35) <= *(_DWORD *)(v91 + 140) )
        {
          v108 = *(_DWORD *)(v40 + 60);
          v109 = **(const struct SemanticsUM::Entity ***)(v40 + 8);
LABEL_280:
          SemSolutionLL = SemanticsUM::EntityCondition::Create(
                            v13,
                            0,
                            v109,
                            v108,
                            (struct SemanticsUM::EntityCondition **)v121);
          v32 = (SemanticsUM::EntityCondition *)v121[0];
          if ( SemSolutionLL < 0 )
            goto LABEL_46;
          goto LABEL_108;
        }
LABEL_30:
        v123 = 0;
        v45 = v140;
        SemSolutionLL = SemanticsUM::CopyTokens(
                          (SemanticsUM *)v140,
                          v141,
                          (const struct ITokenCollection *)*(unsigned int *)(v40 + 24),
                          *(_DWORD *)(v40 + 28),
                          0,
                          &v123);
        if ( SemSolutionLL >= 0 )
        {
          pv = 0;
          if ( v41 == 5 && (v48 = *(const size_t **)(v40 + 48)) != 0 )
            v49 = _AllocString<CTCoAllocPolicy>(v47, v46, v48, &pv);
          else
            v49 = SemanticsUM::CopyTokens(
                    (SemanticsUM *)v45,
                    v141,
                    (const struct ITokenCollection *)*(unsigned int *)(v40 + 40),
                    *(_DWORD *)(v40 + 44),
                    *(_DWORD *)(v40 + 60),
                    (wchar_t **)&pv);
          SemSolutionLL = v49;
          if ( v49 >= 0 )
          {
            v50 = (__int64 (__fastcall ***)(_QWORD))((char *)v32 + *(int *)(*((_QWORD *)v32 + 1) + 12LL) + 8);
            v51 = (**v50)(v50);
            v52 = (const struct SemanticsUM::Entity *)((unsigned __int64)v135 & -(__int64)(v51 != 0));
            v135 = 0;
            v53 = pv;
            SemSolutionLL = SemanticsUM::ValueCondition::Create(
                              (const struct SemanticsUM::SemanticKeyword *)&v122,
                              (const struct SemanticsUM::SemanticKeyword *)&v120,
                              v123,
                              *(_DWORD *)(v40 + 40),
                              *(_DWORD *)(v40 + 44),
                              v32,
                              v52,
                              (const wchar_t *)pv,
                              *(_DWORD *)(v40 + 60),
                              &v135);
            if ( SemSolutionLL >= 0 )
            {
              v54 = *((_QWORD *)v32 + 9);
              if ( v54 )
              {
                v89 = *(SemanticsUM::SemanticCondition **)(v54 + 56);
                if ( v89 )
                  SemanticsUM::SemanticCondition::AddSibling(v89, v135);
                else
                  *(_QWORD *)(v54 + 56) = v135;
              }
              else
              {
                *((_QWORD *)v32 + 9) = v135;
              }
              if ( *((_DWORD *)v119[0] + 16) != 4
                || (v99 = v129) != 0 && SemanticsUM::EntityConditionLL::HasEntityCondition(v129, v32)
                || (SemSolutionLL = SemanticsUM::EntityConditionLL::Create(v99, v32, v114, &v129), SemSolutionLL >= 0) )
              {
                if ( v125 != v114
                  || !v36
                  || v41
                  || (v79 = *((_QWORD *)v133 + 1)) != 0
                  && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)v79 + 8LL) + 60LL) & 0x10) != 0 )
                {
                  v13 = 0;
                }
                else
                {
                  v36 = 0;
                  v32 = 0;
                  v121[0] = 0;
                }
                *(_QWORD *)&v122 = 0;
                *((_QWORD *)&v122 + 1) = -1;
                *(_QWORD *)&v120 = 0;
                *((_QWORD *)&v120 + 1) = -1;
                v115 = 0;
              }
            }
            CoTaskMemFree(v53);
          }
          CoTaskMemFree(v123);
        }
        goto LABEL_46;
      }
    }
    else if ( !j || *(_QWORD *)(j[1] + 8) != *(_QWORD *)(v40 + 8) )
    {
      goto LABEL_100;
    }
    if ( *(_DWORD *)j[1] == 5 && (v117 || v118) )
      goto LABEL_30;
    goto LABEL_203;
  }
LABEL_3:
  SemSolutionLL = v21;
  v23 = (char *)v13 + *(int *)(*((_QWORD *)v13 + 1) + 4LL) + 8;
  (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v23 + 80LL))(v23, 1);
LABEL_4:
  *a9 = v11;
  return (unsigned int)SemSolutionLL;
}

```

## disassembly

```asm
0x18001455c  mov     rax, rsp
0x18001455f  mov     [rax+20h], rbx
0x180014563  mov     [rax+18h], r8
0x180014567  mov     [rax+10h], rdx
0x18001456b  mov     [rax+8], rcx
0x18001456f  push    rbp
0x180014570  push    rsi
0x180014571  push    rdi
0x180014572  push    r12
0x180014574  push    r13
0x180014576  push    r14
0x180014578  push    r15
0x18001457a  lea     rbp, [rsp-70h]
0x18001457f  sub     rsp, 170h
0x180014586  movaps  xmmword ptr [rax-48h], xmm6
0x18001458a  mov     esi, r9d
0x18001458d  mov     rbx, rdx
0x180014590  xor     r15d, r15d
0x180014593  mov     r12d, r15d
0x180014596  mov     [rbp+0A0h+var_68], r15
0x18001459a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800145a1  mov     ecx, 80h; unsigned __int64
0x1800145a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800145ab  mov     rdi, rax
0x1800145ae  test    rax, rax
0x1800145b1  jz      loc_18001471A
0x1800145b7  lea     rax, ??_8CompoundCondition@SemanticsUM@@7BSemanticCondition@1@@; const SemanticsUM::CompoundCondition::`vbtable'{for `SemanticsUM::SemanticCondition'}
0x1800145be  mov     [rdi+8], rax
0x1800145c2  lea     rax, ??_8ValueCondition@SemanticsUM@@7BIValueCondition@1@@; const SemanticsUM::ValueCondition::`vbtable'{for `SemanticsUM::IValueCondition'}
0x1800145c9  mov     [rdi+78h], rax
0x1800145cd  lea     rax, ??_7ISemanticCondition@SemanticsUM@@6B@; const SemanticsUM::ISemanticCondition::`vftable'
0x1800145d4  mov     [rdi+60h], rax
0x1800145d8  lea     rax, ??_7ICompoundCondition@SemanticsUM@@6B01@@; const SemanticsUM::ICompoundCondition::`vftable'{for `SemanticsUM::ICompoundCondition'}
0x1800145df  mov     [rdi+70h], rax
0x1800145e3  mov     rax, [rdi+78h]
0x1800145e7  movsxd  rcx, dword ptr [rax+4]
0x1800145eb  lea     rax, ??_7ICompoundCondition@SemanticsUM@@6BISemanticCondition@1@@; const SemanticsUM::ICompoundCondition::`vftable'{for `SemanticsUM::ISemanticCondition'}
0x1800145f2  mov     [rcx+rdi+78h], rax
0x1800145f7  lea     rax, ??_7SemanticCondition@SemanticsUM@@6B01@@; const SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::SemanticCondition'}
0x1800145fe  mov     [rdi], rax
0x180014601  mov     rax, [rdi+8]
0x180014605  movsxd  rcx, dword ptr [rax+4]
0x180014609  lea     rax, ??_7SemanticCondition@SemanticsUM@@6BISemanticCondition@1@@; const SemanticsUM::SemanticCondition::`vftable'{for `SemanticsUM::ISemanticCondition'}
0x180014610  mov     [rcx+rdi+8], rax
0x180014615  mov     rax, [rdi+8]
0x180014619  movsxd  rcx, dword ptr [rax+4]
0x18001461d  lea     edx, [rcx-48h]
0x180014620  mov     [rcx+rdi+4], edx
0x180014624  mov     [rdi+10h], r15
0x180014628  or      eax, 0FFFFFFFFh
0x18001462b  mov     [rdi+18h], eax
0x18001462e  mov     [rdi+1Ch], eax
0x180014631  mov     [rdi+20h], r15
0x180014635  mov     [rdi+28h], eax
0x180014638  mov     [rdi+2Ch], eax
0x18001463b  mov     [rdi+30h], r15
0x18001463f  mov     [rdi+38h], r15
0x180014643  mov     [rdi+40h], eax
0x180014646  mov     [rdi+44h], eax
0x180014649  lea     rax, ??_7CompoundCondition@SemanticsUM@@6BSemanticCondition@1@@; const SemanticsUM::CompoundCondition::`vftable'{for `SemanticsUM::SemanticCondition'}
0x180014650  mov     [rdi], rax
0x180014653  mov     rax, [rdi+8]
0x180014657  movsxd  rcx, dword ptr [rax+4]
0x18001465b  lea     rax, ??_7CompoundCondition@SemanticsUM@@6BISemanticCondition@1@@; const SemanticsUM::CompoundCondition::`vftable'{for `SemanticsUM::ISemanticCondition'}
0x180014662  mov     [rcx+rdi+8], rax
0x180014667  mov     rax, [rdi+8]
0x18001466b  movsxd  rcx, dword ptr [rax+8]
0x18001466f  lea     rax, ??_7CompoundCondition@SemanticsUM@@6BICompoundCondition@1@@; const SemanticsUM::CompoundCondition::`vftable'{for `SemanticsUM::ICompoundCondition'}
0x180014676  mov     [rcx+rdi+8], rax
0x18001467b  mov     rax, [rdi+8]
0x18001467f  movsxd  rcx, dword ptr [rax+4]
0x180014683  lea     edx, [rcx-58h]
0x180014686  mov     [rcx+rdi+4], edx
0x18001468a  mov     rax, [rdi+8]
0x18001468e  movsxd  rcx, dword ptr [rax+8]
0x180014692  lea     edx, [rcx-68h]
0x180014695  mov     [rcx+rdi+4], edx
0x180014699  mov     [rdi+48h], r15
0x18001469d  mov     [rdi+50h], r15
0x1800146a1  mov     r13, [rbp+0A0h+arg_38]
0x1800146a8  mov     r14, [r13+38h]
0x1800146ac  movsd   xmm6, qword ptr [r13+10h]
0x1800146b2  mov     [rbp+0A0h+arg_0], r15
0x1800146b9  lea     r9, [rbp+0A0h+arg_0]
0x1800146c0  mov     r8, rbx
0x1800146c3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x1800146c8  test    eax, eax
0x1800146ca  jns     short loc_180014721
0x1800146cc  mov     ebx, eax
0x1800146ce  mov     rax, [rdi+8]
0x1800146d2  movsxd  rcx, dword ptr [rax+4]
0x1800146d6  add     rcx, 8
0x1800146da  add     rcx, rdi
0x1800146dd  mov     rax, [rcx]
0x1800146e0  mov     edx, 1
0x1800146e5  mov     rax, [rax+50h]
0x1800146e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146ee  mov     rax, [rbp+0A0h+arg_40]
0x1800146f5  mov     [rax], r12
0x1800146f8  mov     eax, ebx
0x1800146fa  lea     r11, [rsp+1A0h+var_30]
0x180014702  mov     rbx, [r11+58h]
0x180014706  movaps  xmm6, xmmword ptr [r11-10h]
0x18001470b  mov     rsp, r11
0x18001470e  pop     r15
0x180014710  pop     r14
0x180014712  pop     r13
0x180014714  pop     r12
0x180014716  pop     rdi
0x180014717  pop     rsi
0x180014718  pop     rbp
0x180014719  retn
0x18001471a  mov     ebx, 8007000Eh
0x18001471f  jmp     short loc_1800146EE
0x180014721  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014728  mov     ecx, 50h ; 'P'; unsigned __int64
0x18001472d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014732  mov     [rbp+0A0h+var_50], rax
0x180014736  mov     rbx, [rbp+0A0h+arg_0]
0x18001473d  test    rax, rax
0x180014740  jz      loc_180015348
0x180014746  mov     rcx, [rbp+0A0h+arg_28]
0x18001474d  mov     [rsp+1A0h+var_168], rcx; struct IWordBreaker *
0x180014752  mov     ecx, dword ptr [rbp+0A0h+arg_20]
0x180014758  mov     dword ptr [rsp+1A0h+var_170], ecx; wchar_t **
0x18001475c  mov     dword ptr [rsp+1A0h+var_178], esi; unsigned int
0x180014760  mov     [rsp+1A0h+var_180], rbx; wchar_t *
0x180014765  mov     r9, rdi; struct CompoundCondition *
0x180014768  mov     r8, r14; struct SemanticsUM::Entity *
0x18001476b  movaps  xmm1, xmm6; double
0x18001476e  mov     rcx, rax; this
0x180014771  call    ??0StructuredSemanticSolution@SemanticsUM@@AEAA@NPEBVEntity@1@PEAVCompoundCondition@1@PEA_WKKPEAUIWordBreaker@@@Z; SemanticsUM::StructuredSemanticSolution::StructuredSemanticSolution(double,SemanticsUM::Entity const *,SemanticsUM::CompoundCondition *,wchar_t *,ulong,ulong,IWordBreaker *)
0x180014776  mov     r15, rax
0x180014779  mov     [rbp+0A0h+var_78], r15
0x18001477d  test    r15, r15
0x180014780  jz      loc_18001542C
0x180014786  mov     [rbp+0A0h+var_58], 0
0x18001478e  lea     rdx, [rbp+0A0h+var_58]; struct SemanticsUM::SemSolutionLL **
0x180014792  mov     rcx, r13; struct SemanticsUM::SemSolution *
0x180014795  call    ?GetSemSolutionLL@StructuredSemanticSolutionMaker@SemanticsUM@@CAJPEBVSemSolution@2@PEAPEAVSemSolutionLL@2@@Z; SemanticsUM::StructuredSemanticSolutionMaker::GetSemSolutionLL(SemanticsUM::SemSolution const *,SemanticsUM::SemSolutionLL * *)
0x18001479a  mov     ebx, eax
0x18001479c  test    eax, eax
0x18001479e  js      loc_180014B6D
0x1800147a4  mov     [rbp+0A0h+var_88], 0
0x1800147ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800147b3  mov     ecx, 8; unsigned __int64
0x1800147b8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800147bd  mov     r11, rax
0x1800147c0  mov     [rbp+0A0h+var_90], rax
0x1800147c4  test    rax, rax
0x1800147c7  jz      loc_1800152E7
0x1800147cd  mov     qword ptr [rax], 0
0x1800147d4  xor     r12d, r12d
0x1800147d7  mov     [rsp+1A0h+var_130], r12d
0x1800147dc  xor     esi, esi
0x1800147de  mov     [rbp+0A0h+var_F0], rsi
0x1800147e2  mov     qword ptr [rbp+0A0h+var_E0], rsi
0x1800147e6  or      eax, 0FFFFFFFFh
0x1800147e9  mov     dword ptr [rbp+0A0h+var_E0+8], eax
0x1800147ec  mov     dword ptr [rbp+0A0h+var_E0+0Ch], eax
0x1800147ef  xor     edx, edx; unsigned int
0x1800147f1  mov     qword ptr [rbp+0A0h+var_100], rdx
0x1800147f5  mov     dword ptr [rbp+0A0h+var_100+8], eax
0x1800147f8  mov     dword ptr [rbp+0A0h+var_100+0Ch], eax
0x1800147fb  xor     r9d, r9d
0x1800147fe  mov     [rbp+0A0h+var_120], r9
0x180014802  xor     r8d, r8d
0x180014805  mov     [rbp+0A0h+var_118], r8
0x180014809  mov     qword ptr [rbp+0A0h+var_A0], rdx
0x18001480d  mov     dword ptr [rbp+0A0h+var_A0+8], eax
0x180014810  mov     dword ptr [rbp+0A0h+var_A0+0Ch], eax
0x180014813  mov     qword ptr [rbp+0A0h+var_B0], rdx
0x180014817  mov     dword ptr [rbp+0A0h+var_B0+8], eax
0x18001481a  mov     dword ptr [rbp+0A0h+var_B0+0Ch], eax
0x18001481d  mov     r10, [rbp+0A0h+var_58]
0x180014821  mov     [rbp+0A0h+var_70], r10
0x180014825  test    r10, r10
0x180014828  jz      loc_18001527F
0x18001482e  mov     [rsp+1A0h+var_12C], dl
0x180014832  xor     r13d, r13d
0x180014835  xor     cl, cl
0x180014837  mov     byte ptr [rbp+0A0h+arg_0], cl
0x18001483d  mov     [rbp+0A0h+var_C0], eax
0x180014840  xor     ebx, ebx
0x180014842  mov     rax, rdi
0x180014845  mov     [rsp+1A0h+var_128], rax
0x18001484a  mov     [rbp+0A0h+var_80], 8007000Eh
0x180014851  mov     r10, [r10]
0x180014854  mov     [rbp+0A0h+var_110], r10
0x180014858  mov     r14, [r10+8]
0x18001485c  cmp     dword ptr [r14+18h], 0
0x180014861  jl      loc_180014A82
0x180014867  mov     r12d, [r14]
0x18001486a  cmp     r12d, 5
0x18001486e  jg      loc_180014B81
0x180014874  jz      short loc_1800148C9
0x180014876  test    r12d, r12d
0x180014879  jz      short loc_1800148C4
0x18001487b  sub     r12d, 1
0x18001487f  jz      loc_180014C31
0x180014885  sub     r12d, 1
0x180014889  jnz     loc_180014DFE
0x18001488f  cmp     qword ptr [rbp+0A0h+var_E0], 0
0x180014894  jnz     loc_180015461
0x18001489a  test    ebx, ebx
0x18001489c  js      loc_180014C60
0x1800148a2  mov     r8, r14
0x1800148a5  mov     [rbp+0A0h+var_118], r14
0x1800148a9  mov     rcx, [r14+30h]
0x1800148ad  mov     qword ptr [rbp+0A0h+var_E0], rcx
0x1800148b1  mov     eax, [r14+28h]
0x1800148b5  mov     dword ptr [rbp+0A0h+var_E0+8], eax
0x1800148b8  mov     eax, [r14+2Ch]
0x1800148bc  mov     dword ptr [rbp+0A0h+var_E0+0Ch], eax
0x1800148bf  jmp     loc_180014C5B
0x1800148c4  mov     rax, [rsp+1A0h+var_128]
0x1800148c9  test    rdi, rdi
0x1800148cc  jz      loc_180015509
0x1800148d2  cmp     r12d, 5
0x1800148d6  jz      loc_180014E91
0x1800148dc  mov     r15, [rbp+0A0h+arg_30]
0x1800148e3  mov     rax, [r14+10h]
0x1800148e7  mov     [rbp+0A0h+var_60], rax
0x1800148eb  test    r12d, r12d
0x1800148ee  jz      loc_180014EE6
0x1800148f4  cmp     r12d, 6
0x1800148f8  jz      loc_180015313
0x1800148fe  cmp     r12d, 5
0x180014902  jz      loc_180014C6A
0x180014908  test    ebx, ebx
0x18001490a  js      loc_180014A66
0x180014910  mov     [rbp+0A0h+var_D0], 0
0x180014918  lea     rax, [rbp+0A0h+var_D0]
0x18001491c  mov     [rsp+1A0h+var_178], rax; __int64
0x180014921  mov     dword ptr [rsp+1A0h+var_180], 0; int
0x180014929  mov     r9d, [r14+1Ch]; int
0x18001492d  mov     r8d, [r14+18h]; struct ITokenCollection *
0x180014931  mov     rdx, [rbp+0A0h+arg_10]; wchar_t *
0x180014938  mov     r15, [rbp+0A0h+arg_8]
0x18001493f  mov     rcx, r15; this
0x180014942  call    ?CopyTokens@SemanticsUM@@YAJPEB_WAEBVITokenCollection@1@HHHPEAPEA_W@Z; SemanticsUM::CopyTokens(wchar_t const *,SemanticsUM::ITokenCollection const &,int,int,int,wchar_t * *)
0x180014947  mov     ebx, eax
0x180014949  test    eax, eax
0x18001494b  js      loc_180014A66
0x180014951  mov     [rbp+0A0h+pv], 0
0x180014959  cmp     r12d, 5
0x18001495d  jnz     loc_180014FE1
0x180014963  mov     r8, [r14+30h]
0x180014967  test    r8, r8
0x18001496a  jz      loc_180014FE1
0x180014970  lea     r9, [rbp+0A0h+pv]
0x180014974  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180014979  mov     ebx, eax
0x18001497b  test    eax, eax
0x18001497d  js      loc_180014A5C
0x180014983  mov     rax, [rsi+8]
0x180014987  movsxd  rcx, dword ptr [rax+0Ch]
0x18001498b  add     rcx, 8
0x18001498f  add     rcx, rsi
0x180014992  mov     rax, [rcx]
0x180014995  mov     rax, [rax]
0x180014998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001499d  neg     rax
0x1800149a0  sbb     rcx, rcx
0x1800149a3  and     rcx, [rbp+0A0h+var_60]
0x1800149a7  mov     [rbp+0A0h+var_60], 0
0x1800149af  lea     rax, [rbp+0A0h+var_60]
0x1800149b3  mov     [rsp+1A0h+var_158], rax; struct SemanticsUM::ValueCondition **
0x1800149b8  mov     eax, [r14+3Ch]
0x1800149bc  mov     dword ptr [rsp+1A0h+var_160], eax; unsigned int
0x1800149c0  mov     r15, [rbp+0A0h+pv]
0x1800149c4  mov     [rsp+1A0h+var_168], r15; wchar_t *
0x1800149c9  mov     [rsp+1A0h+var_170], rcx; struct SemanticsUM::Entity *
0x1800149ce  mov     [rsp+1A0h+var_178], rsi; struct CompoundCondition *
0x1800149d3  mov     eax, [r14+2Ch]
0x1800149d7  mov     dword ptr [rsp+1A0h+var_180], eax; int
0x1800149db  mov     r9d, [r14+28h]; int
0x1800149df  mov     r8, [rbp+0A0h+var_D0]; wchar_t *
0x1800149e3  lea     rdx, [rbp+0A0h+var_100]; struct SemanticsUM::SemanticKeyword *
0x1800149e7  lea     rcx, [rbp+0A0h+var_E0]; struct SemanticsUM::SemanticKeyword *
0x1800149eb  call    ?Create@ValueCondition@SemanticsUM@@SAJAEBVSemanticKeyword@2@0PEB_WHHPEAVCompoundCondition@2@PEBVEntity@2@1KPEAPEAV12@@Z; SemanticsUM::ValueCondition::Create(SemanticsUM::SemanticKeyword const &,SemanticsUM::SemanticKeyword const &,wchar_t const *,int,int,SemanticsUM::CompoundCondition *,SemanticsUM::Entity const *,wchar_t const *,ulong,SemanticsUM::ValueCondition * *)
0x1800149f0  mov     ebx, eax
0x1800149f2  test    eax, eax
0x1800149f4  js      short loc_180014A53
0x1800149f6  mov     rdx, [rbp+0A0h+var_60]; struct SemanticsUM::SemanticCondition *
0x1800149fa  mov     rax, [rsi+48h]
0x1800149fe  test    rax, rax
0x180014a01  jnz     loc_180015225
0x180014a07  mov     [rsi+48h], rdx
0x180014a0b  mov     rax, [rbp+0A0h+var_110]
0x180014a0f  cmp     dword ptr [rax+40h], 4
0x180014a13  jz      loc_1800155AC
0x180014a19  mov     eax, [rbp+0A0h+var_C0]
0x180014a1c  cmp     eax, [rsp+1A0h+var_130]
0x180014a20  jnz     short loc_180014A30
0x180014a22  test    r13, r13
0x180014a25  jz      short loc_180014A30
0x180014a27  test    r12d, r12d
0x180014a2a  jz      loc_18001501B
0x180014a30  xor     edi, edi
  ... truncated ...
```
