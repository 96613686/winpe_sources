# sqlite3Select

- ea: `0x180037194`
- end: `0x180038fb2`
- name: `sqlite3Select`
- size: `7710`
- prototype: ``
- caller_count: `13`
- callee_count: `76`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d770`
- `0x18000eb78`
- `0x180018754`
- `0x1800189c8`
- `0x180031b38`
- `0x180037194`
- `0x180043968`
- `0x18004414c`
- `0x180044538`
- `0x180070c50`
- `0x18008513c`
- `0x180085340`
- `0x180092f78`

## callees

- `0x180005c54`
- `0x180008894`
- `0x18000a9e0`
- `0x18000c930`
- `0x18000c960`
- `0x18000cb64`
- `0x18000e3ac`
- `0x18000e7f0`
- `0x18000e808`
- `0x18000f720`
- `0x180010450`
- `0x180010810`
- `0x180011950`
- `0x1800119e0`
- `0x180011d80`
- `0x180011fdc`
- `0x180013570`
- `0x180016748`
- `0x18001c1c4`
- `0x18001c220`
- `0x18003465c`
- `0x1800352fc`
- `0x180036688`
- `0x180036730`
- `0x1800370c0`
- `0x180037194`
- `0x180038fb8`
- `0x180039850`
- `0x1800398f0`
- `0x1800399a0`
- `0x18003abcc`
- `0x18003e1e0`
- `0x18003e5c0`
- `0x18003e944`
- `0x18003f6dc`
- `0x18003ff00`
- `0x180043968`
- `0x1800443c8`
- `0x18004444c`
- `0x18004a93c`
- `0x18004cfa0`
- `0x18004d710`
- `0x180053eb0`
- `0x180053ecc`
- `0x180055634`
- `0x180056ed8`
- `0x1800573d8`
- `0x180057a7c`
- `0x180057fc8`
- `0x18005b990`

## string_xrefs

- `0x18003897d`: `USE TEMP B-TREE FOR %s`
- `0x180038f52`: `USE TEMP B-TREE FOR %s`

## pseudocode

```c
__int64 __fastcall sqlite3Select(_QWORD *a1, __int64 a2, __int128 *a3)
{
  int v3; // esi
  __int64 v5; // r13
  __int64 v7; // rdi
  BOOL v8; // r12d
  int v9; // ebx
  int v10; // eax
  __int64 v11; // r10
  int *v12; // r14
  bool v13; // zf
  unsigned int v14; // r9d
  char v16; // al
  const char **v17; // r9
  int v18; // r8d
  int v19; // edx
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rsi
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  const char **v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // r9d
  int v31; // r8d
  unsigned int v32; // eax
  int v33; // ecx
  unsigned int v34; // r8d
  unsigned int v35; // edx
  unsigned int v36; // ecx
  __int16 v37; // dx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  int v42; // r9d
  __int64 v43; // r14
  int v44; // ecx
  bool v45; // sf
  int v46; // r14d
  int v47; // eax
  int ii; // r14d
  __int64 v49; // r8
  __int64 v50; // rdx
  _BYTE *v51; // rax
  __int64 v52; // r8
  __int64 v53; // rax
  int v54; // edx
  unsigned int v55; // ebx
  unsigned int v56; // r14d
  __int64 Op; // rax
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // r14
  int v61; // edi
  int v62; // ebx
  unsigned int v63; // ebx
  __int128 *v64; // rbx
  __int64 v65; // rdx
  _BYTE *v66; // rax
  int j; // eax
  int v68; // ecx
  const char **v69; // rbx
  int *v70; // rdx
  unsigned int v71; // eax
  int *v72; // rbx
  __int16 v73; // ax
  __int64 v74; // rsi
  __int16 v75; // bx
  __int64 v76; // rax
  __int64 v77; // rdx
  __int16 v78; // ax
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rsi
  __int64 v82; // rbx
  int v83; // r11d
  __int64 v84; // rcx
  __int64 v85; // r8
  unsigned int v86; // edi
  int v87; // r8d
  int v88; // ecx
  __int64 v89; // rax
  __int64 v90; // rbx
  int v91; // r8d
  __int64 v92; // rbx
  __int64 v93; // rdx
  __int64 v94; // rax
  int v95; // eax
  char v96; // al
  __int64 v97; // rax
  int v98; // r8d
  __int64 v99; // rdi
  unsigned int v100; // eax
  __int64 v101; // r8
  unsigned int v102; // ebx
  int *v103; // rax
  int v104; // ecx
  _DWORD *v105; // rdx
  int v106; // ecx
  _DWORD *v107; // rdx
  int m; // r8d
  __int64 v109; // rdx
  const char **v110; // rcx
  int v111; // eax
  int k; // esi
  signed int v113; // ecx
  __int64 v114; // rax
  __int64 v115; // rdx
  int v116; // ecx
  __int64 v117; // rsi
  const char *v118; // r8
  int v119; // eax
  char v120; // al
  __int64 v121; // rdx
  int i; // r9d
  char v123; // al
  unsigned int v124; // edx
  int v125; // eax
  __int64 v126; // r10
  __int64 v127; // rdx
  __int64 v128; // rax
  __int64 v129; // rax
  int v130; // r9d
  int v131; // r8d
  __int64 v132; // rbx
  int v133; // r9d
  __int64 v134; // rax
  _DWORD *v135; // rbx
  int v136; // r9d
  int v137; // eax
  unsigned int v138; // eax
  int v139; // r9d
  __int64 v140; // rcx
  int *v141; // rax
  int *v142; // rdx
  int v143; // r8d
  __int64 v144; // rax
  __int64 v145; // rbx
  int v146; // r8d
  __int64 v147; // rax
  int v148; // eax
  unsigned int v149; // ebx
  int v150; // esi
  unsigned int v151; // edi
  unsigned int v152; // r14d
  __int64 v153; // rdx
  __int64 v154; // rdx
  int *v155; // rax
  __int64 v156; // rax
  __int64 v157; // rdx
  __int64 v158; // rbx
  __int64 v159; // rax
  __int64 v160; // rax
  const char *v161; // r9
  __int64 v162; // r8
  int v163; // eax
  unsigned int v164; // r14d
  unsigned int v165; // r9d
  int v166; // edx
  unsigned int v167; // eax
  unsigned int v168; // eax
  char v169; // r11
  signed int v170; // ebx
  int v171; // edi
  unsigned int v172; // r13d
  __int64 v173; // rcx
  unsigned int TempReg; // ebx
  __int64 v175; // rcx
  unsigned int v176; // edx
  int v177; // edx
  __int64 v178; // rax
  __int64 v179; // r11
  __int64 v180; // rbx
  unsigned int v181; // eax
  __int64 v182; // r11
  __int64 v183; // r14
  __int64 n; // rcx
  __int16 v185; // ax
  int v186; // r8d
  unsigned int v187; // ebx
  int v188; // edx
  unsigned int v189; // ecx
  __int64 v190; // r9
  __int64 v191; // r8
  _DWORD *v192; // rax
  __int64 v193; // rax
  __int64 v194; // r14
  __int64 v195; // r8
  __int64 v196; // [rsp+40h] [rbp-C0h]
  unsigned int v197; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v198; // [rsp+4Ch] [rbp-B4h]
  unsigned int v199; // [rsp+50h] [rbp-B0h]
  unsigned int v200; // [rsp+54h] [rbp-ACh]
  unsigned int TempRange; // [rsp+58h] [rbp-A8h]
  int *v202; // [rsp+60h] [rbp-A0h]
  __int64 v203; // [rsp+68h] [rbp-98h]
  int v204; // [rsp+70h] [rbp-90h]
  int v205; // [rsp+74h] [rbp-8Ch]
  unsigned int v206; // [rsp+78h] [rbp-88h]
  const char **v207; // [rsp+80h] [rbp-80h]
  __int64 v208; // [rsp+88h] [rbp-78h]
  unsigned int v209; // [rsp+90h] [rbp-70h]
  __int64 v210; // [rsp+98h] [rbp-68h]
  __int64 Vdbe; // [rsp+A0h] [rbp-60h]
  __int128 *v212; // [rsp+A8h] [rbp-58h]
  int v213; // [rsp+B0h] [rbp-50h]
  int v214; // [rsp+B4h] [rbp-4Ch]
  unsigned int v215; // [rsp+B8h] [rbp-48h]
  __int64 v216; // [rsp+C0h] [rbp-40h]
  unsigned int v217; // [rsp+C8h] [rbp-38h]
  __int128 v218; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v219; // [rsp+E0h] [rbp-20h]
  __int128 v220; // [rsp+F0h] [rbp-10h]
  __int128 v221; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v222[24]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v223; // [rsp+128h] [rbp+28h]
  unsigned int v224; // [rsp+130h] [rbp+30h]
  __int64 v225; // [rsp+138h] [rbp+38h] BYREF
  __int64 v226; // [rsp+140h] [rbp+40h]
  __int64 v227; // [rsp+148h] [rbp+48h]
  _BYTE v228[56]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v229; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v230; // [rsp+190h] [rbp+90h]

  v212 = a3;
  v229 = 0;
  v230 = 0;
  v3 = 0;
  v196 = *a1;
  v5 = a2;
  v226 = a2;
  v218 = 0;
  v225 = 0;
  v219 = 0;
  v220 = 0;
  Vdbe = sqlite3GetVdbe(a1);
  v7 = Vdbe;
  if ( !v5 || *((_DWORD *)a1 + 13) || (unsigned int)sqlite3AuthCheck((_DWORD)a1, 21, 0, 0, 0) )
    return 1;
  v8 = 1;
  if ( *(_BYTE *)a3 <= 6u )
  {
    v21 = *(_QWORD *)(v5 + 72);
    if ( v21 )
    {
      sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v21);
      *(_QWORD *)(v5 + 72) = 0;
    }
    *(_DWORD *)(v5 + 4) &= ~1u;
    *(_DWORD *)(v5 + 4) |= 0x400000u;
  }
  sqlite3SelectPrep(a1, v5, 0);
  if ( *((_DWORD *)a1 + 13) )
    goto LABEL_113;
  v9 = *(_DWORD *)(v5 + 4);
  if ( (v9 & 0x800000) != 0 )
  {
    v117 = *(_QWORD *)(v5 + 40) + 8LL;
    if ( (unsigned int)sameSrcAlias(v117) )
    {
      v118 = *(const char **)(v117 + 8);
      if ( !v118 )
        v118 = **(const char ***)(v117 + 16);
      sqlite3ErrorMsg(a1, "target object/alias may not appear in FROM clause: %s", v118);
      goto LABEL_173;
    }
    *(_DWORD *)(v5 + 4) = v9 & 0xFF7FFFFF;
    v3 = 0;
  }
  if ( *(_BYTE *)a3 == 9 )
    sqlite3GenerateColumnNames(a1, v5);
  v10 = sqlite3WindowRewrite(a1, v5);
  v11 = v196;
  if ( v10 )
    goto LABEL_39;
  v12 = *(int **)(v5 + 40);
  v13 = (*(_DWORD *)(v5 + 4) & 8) == 0;
  v205 = *(_DWORD *)(v5 + 4) & 8;
  v198 = !v13;
  v218 = *(unsigned __int64 *)(v5 + 72);
  v219 = 0;
  v220 = 0;
  while ( 1 )
  {
    if ( *(_QWORD *)(v5 + 80) )
    {
      v14 = multiSelect(a1, (unsigned __int8 *)v5, v212);
      if ( !*(_QWORD *)(v5 + 88) )
      {
        v115 = *((unsigned int *)a1 + 80);
        if ( (_DWORD)v115 )
          v116 = *(_DWORD *)(sqlite3VdbeGetOp(a1[2], v115) + 8);
        else
          v116 = 0;
        *((_DWORD *)a1 + 80) = v116;
      }
      return v14;
    }
    if ( v3 >= *v12 )
      break;
    if ( (v12[20 * v3 + 9] & 4) != 0 )
      v208 = **(_QWORD **)&v12[20 * v3 + 20];
    else
      v208 = 0;
    v16 = v12[20 * v3 + 8];
    v17 = *(const char ***)&v12[20 * v3 + 6];
    v207 = v17;
    if ( (v16 & 0x48) != 0 )
    {
      v119 = sqlite3ExprImpliesNonNullRow(*(_QWORD *)(v5 + 48), (unsigned int)v12[20 * v3 + 10], v16 & 0x40);
      v11 = v196;
      if ( v119 && (*(_DWORD *)(v196 + 96) & 0x2000) == 0 )
      {
        v120 = v12[20 * v3 + 8];
        if ( (v120 & 8) != 0 )
        {
          if ( (v120 & 0x10) != 0 )
          {
            LOBYTE(v12[20 * v3 + 8]) = v120 & 0xF7;
          }
          else
          {
            v121 = (unsigned int)v12[20 * v3 + 10];
            LOBYTE(v12[20 * v3 + 8]) = v120 & 0xD7;
            unsetJoinExpr(*(_QWORD *)(v5 + 48), v121, 0);
          }
        }
        if ( (v12[20 * v3 + 8] & 0x40) != 0 )
        {
          for ( i = v3 + 1; ; ++i )
          {
            v124 = *v12;
            if ( i >= *v12 )
              break;
            v123 = v12[20 * i + 8];
            if ( (v123 & 0x10) != 0 )
            {
              if ( (v123 & 8) != 0 )
              {
                LOBYTE(v12[20 * i + 8]) = v123 & 0xEF;
              }
              else
              {
                LOBYTE(v12[20 * i + 8]) = v123 & 0xCF;
                unsetJoinExpr(*(_QWORD *)(v5 + 48), (unsigned int)v12[20 * i + 10], 1);
              }
            }
          }
          do
          {
            if ( (--v124 & 0x80000000) != 0 )
              break;
            LOBYTE(v12[20 * v124 + 8]) &= ~0x40u;
          }
          while ( (v12[20 * v124 + 8] & 0x10) == 0 );
        }
      }
      v17 = v207;
    }
    if ( v208 )
    {
      v18 = *((__int16 *)v17 + 27);
      v19 = **(_DWORD **)(v208 + 32);
      if ( v18 != v19 )
      {
        sqlite3ErrorMsg(a1, "expected %d columns for '%s' but got %d", v18, *v17, v19);
        goto LABEL_173;
      }
      if ( ((v12[20 * v3 + 9] & 0x200) == 0 || *(_BYTE *)(*(_QWORD *)&v12[20 * v3 + 16] + 18LL))
        && (*(_BYTE *)(v208 + 4) & 8) == 0 )
      {
        v20 = *(_QWORD *)(v208 + 72);
        if ( v20 )
        {
          if ( !*(_QWORD *)(v5 + 72) && *v12 <= 1
            || *(_QWORD *)(v208 + 96)
            || (*(_DWORD *)(v208 + 4) & 0x8002000) != 0
            || (*(_DWORD *)(v5 + 4) & 0x8000000) != 0
            || (*(_DWORD *)(v11 + 96) & 0x40000) != 0 )
          {
            if ( !v3 && (*(_DWORD *)(v5 + 4) & 0x40000) != 0 && (*v12 == 1 || (v12[28] & 0x22) != 0) )
              goto LABEL_19;
          }
          else
          {
            sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v20);
            *(_QWORD *)(v208 + 72) = 0;
          }
        }
        if ( (unsigned int)flattenSubquery(a1, v5, (unsigned int)v3, v198) )
        {
          if ( *((_DWORD *)a1 + 13) )
            goto LABEL_113;
          v3 = -1;
        }
        v11 = v196;
        if ( *(_BYTE *)(v196 + 103) )
          goto LABEL_39;
        v12 = *(int **)(v5 + 40);
        if ( *(_BYTE *)v212 > 8u )
          *(_QWORD *)&v218 = *(_QWORD *)(v5 + 72);
      }
    }
LABEL_19:
    ++v3;
  }
  v66 = *(_BYTE **)(v5 + 48);
  if ( v66 && *v66 == 44 && (*(_DWORD *)(v11 + 96) & 0x8000) == 0 )
  {
    propagateConstants(a1, v5);
    v11 = v196;
  }
  if ( (*(_DWORD *)(v11 + 96) & 0x201) == 0 )
  {
    v95 = countOfViewOptimization(a1, v5);
    v11 = v196;
    if ( v95 )
    {
      if ( *(_BYTE *)(v196 + 103) )
        goto LABEL_39;
      v12 = *(int **)(v5 + 40);
    }
  }
  for ( j = 0; ; j = v199 + 1 )
  {
    v199 = j;
    if ( j >= *v12 )
      break;
    memset(v222, 0, 21);
    v221 = 0;
    v80 = 20LL * j;
    v81 = (__int64)&v12[v80 + 2];
    if ( !*(_QWORD *)&v12[v80 + 12] && *(_QWORD *)v81 )
    {
      if ( (*(_DWORD *)(v81 + 28) & 0x10000) != 0 )
      {
        v125 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v81 + 72));
        v127 = *(_QWORD *)(32LL * v125 + *(_QWORD *)(v126 + 32));
      }
      else
      {
        v127 = 0;
        if ( (*(_BYTE *)(v81 + 28) & 4) == 0 )
          v127 = *(_QWORD *)(v81 + 72);
      }
      sqlite3AuthCheck((_DWORD)a1, 20, *(_QWORD *)v81, (unsigned int)byte_18009EEF0, v127);
    }
    if ( (*(_BYTE *)(v81 + 28) & 4) != 0 )
    {
      v82 = *(_QWORD *)(v81 + 72);
      v208 = v82;
      if ( !*(_DWORD *)(v82 + 8) )
      {
        v202 = *(int **)v82;
        v197 = 0;
        heightOfSelect(v5, &v197);
        v84 = v196;
        *((_DWORD *)a1 + 79) += v197;
        if ( (*(_DWORD *)(v196 + 96) & 0x1000) == 0 )
        {
          if ( (*(_DWORD *)(v81 + 28) & 0x200) == 0
            || (v128 = *(_QWORD *)(v81 + 56), *(_BYTE *)(v128 + 18)) && *(int *)v128 < 2 )
          {
            pushDownWhereTerms((_DWORD)a1, v83, *(_QWORD *)(v5 + 48), (_DWORD)v12, v199);
            v84 = v196;
          }
        }
        if ( (*(_DWORD *)(v84 + 96) & 0x4000000) == 0 )
          disableUnusedSubqueryResultColumns(v81);
        v85 = v199;
        v216 = a1[47];
        a1[47] = *(_QWORD *)v81;
        if ( (unsigned int)fromClauseTermCanBeCoroutine(a1, v12, v85, *(unsigned int *)(v5 + 4)) )
        {
          v86 = *(_DWORD *)(v7 + 144);
          v87 = ++*((_DWORD *)a1 + 15);
          v88 = Vdbe;
          *(_DWORD *)(v208 + 12) = v87;
          sqlite3VdbeAddOp3(v88, 11, v87, 0, v86 + 1);
          v89 = v208;
          *(_DWORD *)(v208 + 8) = v86 + 1;
          v90 = v89;
          DWORD1(v221) = *(_DWORD *)(v89 + 12);
          *((_QWORD *)&v221 + 1) = 0;
          *(_QWORD *)&v222[8] = 0;
          *(_DWORD *)v222 = 0;
          LOBYTE(v221) = 13;
          sqlite3VdbeExplain(a1, 1, "CO-ROUTINE %!S", v81);
          sqlite3Select(a1, v202, &v221);
          *(_WORD *)(*(_QWORD *)(v81 + 16) + 58LL) = *((_WORD *)v202 + 1);
          *(_DWORD *)(v81 + 28) |= 0x40u;
          v91 = *(_DWORD *)(v90 + 12);
          *(_DWORD *)(v90 + 16) = HIDWORD(v221);
          v92 = Vdbe;
          sqlite3VdbeAddOp3(Vdbe, 68, v91, 0, 0);
          v93 = v86;
          v7 = v92;
          *(_BYTE *)(*(_QWORD *)(v92 + 24) + 31LL) = 0;
          *(_DWORD *)(*(_QWORD *)(v92 + 24) + 44LL) = 0;
          *(_DWORD *)(sqlite3VdbeGetOp(v92, v93) + 8) = *(_DWORD *)(v92 + 144);
          *((_BYTE *)a1 + 31) = 0;
          *((_DWORD *)a1 + 11) = 0;
        }
        else if ( (*(_DWORD *)(v81 + 28) & 0x200) != 0
               && (v129 = *(_QWORD *)(v81 + 56), v203 = v129, v130 = *(_DWORD *)(v129 + 4), v130 > 0) )
        {
          sqlite3VdbeAddOp3(v7, 10, *(_DWORD *)(v129 + 8), v130, 0);
          v131 = *(_DWORD *)(v81 + 32);
          v132 = v203;
          v133 = *(_DWORD *)(v203 + 12);
          if ( v131 != v133 )
            sqlite3VdbeAddOp3(v7, 114, v131, v133, 0);
          *((_WORD *)v202 + 1) = *(_WORD *)(v132 + 16);
        }
        else
        {
          v134 = isSelfJoinView(v12, v81, 0, v199);
          v203 = v134;
          if ( v134 )
          {
            v135 = *(_DWORD **)(v134 + 72);
            v136 = v135[2];
            if ( v136 )
            {
              sqlite3VdbeAddOp3(v7, 10, v135[3], v136, 0);
              v134 = v203;
            }
            sqlite3VdbeAddOp3(v7, 114, *(_DWORD *)(v81 + 32), *(_DWORD *)(v134 + 32), 0);
            *((_WORD *)v202 + 1) = *(_WORD *)(*(_QWORD *)v135 + 2LL);
          }
          else
          {
            v137 = ++*((_DWORD *)a1 + 15);
            v197 = 0;
            *(_DWORD *)(v82 + 12) = v137;
            v206 = sqlite3VdbeAddOp3(v7, 9, 0, 0, 0);
            v138 = v206 + 1;
            *(_DWORD *)(v82 + 8) = v206 + 1;
            *(_DWORD *)(v81 + 28) |= 0x20u;
            v13 = (*(_BYTE *)(v81 + 28) & 0x10) == 0;
            v198 = v138;
            if ( v13 )
              v197 = sqlite3VdbeAddOp3(v7, 15, 0, 0, 0);
            DWORD1(v221) = *(_DWORD *)(v81 + 32);
            LOBYTE(v221) = 12;
            *((_QWORD *)&v221 + 1) = 0;
            *(_QWORD *)&v222[8] = 0;
            *(_DWORD *)v222 = 0;
            sqlite3VdbeExplain(a1, 1, "MATERIALIZE %!S", v81);
            sqlite3Select(a1, v202, &v221);
            v139 = 0;
            *(_WORD *)(*(_QWORD *)(v81 + 16) + 58LL) = *((_WORD *)v202 + 1);
            if ( v197 )
              *(_DWORD *)(sqlite3VdbeGetOp(v7, v197) + 8) = *(_DWORD *)(v7 + 144);
            sqlite3VdbeAddOp3(v7, 67, *(_DWORD *)(v82 + 12), v198, v139);
            *(_DWORD *)(sqlite3VdbeGetOp(v7, v206) + 8) = *(_DWORD *)(v7 + 144);
            *((_BYTE *)a1 + 31) = 0;
            *((_DWORD *)a1 + 11) = 0;
            if ( (*(_DWORD *)(v81 + 28) & 0x210) == 0x200 )
            {
              v140 = *(_QWORD *)(v81 + 56);
              *(_DWORD *)(v140 + 4) = *(_DWORD *)(v82 + 8);
              *(_DWORD *)(v140 + 8) = *(_DWORD *)(v82 + 12);
              *(_DWORD *)(v140 + 12) = *(_DWORD *)(v81 + 32);
              *(_WORD *)(v140 + 16) = *((_WORD *)v202 + 1);
            }
          }
        }
        v11 = v196;
        if ( *(_BYTE *)(v196 + 103) )
          goto LABEL_39;
        v197 = 0;
        heightOfSelect(v5, &v197);
        v94 = v216;
        *((_DWORD *)a1 + 79) -= v197;
        a1[47] = v94;
      }
    }
  }
  v68 = *(_DWORD *)(v5 + 4);
  v69 = *(const char ***)(v5 + 32);
  v70 = *(int **)(v5 + 56);
  v210 = *(_QWORD *)(v5 + 48);
  v208 = *(_QWORD *)(v5 + 64);
  v207 = v69;
  v202 = v70;
  LOBYTE(v229) = v68 & 1;
  if ( (v68 & 9) == 1
    && !(unsigned int)sqlite3ExprListCompare(v218, v69, 0xFFFFFFFFLL)
    && (*(_BYTE *)(v196 + 96) & 4) == 0
    && !*(_QWORD *)(v5 + 112) )
  {
    *(_DWORD *)(v5 + 4) &= ~1u;
    v141 = (int *)sqlite3ExprListDup(v196, v69, 0);
    v202 = v141;
    v142 = v141;
    *(_QWORD *)(v5 + 56) = v141;
    if ( v141 )
    {
      v143 = 0;
      if ( *v141 > 0 )
      {
        do
        {
          v144 = ++v143;
          LOWORD(v142[8 * v144]) = v143;
        }
        while ( v143 < *v142 );
      }
    }
    *(_DWORD *)(v5 + 4) |= 8u;
    LOBYTE(v229) = 2;
  }
  if ( (_QWORD)v218 )
  {
    v97 = sqlite3KeyInfoFromExprList(a1, v218, 0, *(unsigned int *)v69);
    HIDWORD(v218) = *((_DWORD *)a1 + 14);
    v98 = HIDWORD(v218);
    *((_DWORD *)a1 + 14) = HIDWORD(v218) + 1;
    DWORD2(v219) = sqlite3VdbeAddOp4(v7, 117, v98, *(_DWORD *)v69 + *(_DWORD *)v218 + 1, 0, v97, -8);
  }
  else
  {
    DWORD2(v219) = -1;
  }
  if ( *(_BYTE *)v212 == 12 )
  {
    sqlite3VdbeAddOp3(v7, 117, *((_DWORD *)v212 + 1), *(_DWORD *)v69, 0);
    if ( (*(_DWORD *)(v5 + 4) & 0x800) != 0 )
    {
      v111 = *(_DWORD *)v69;
      for ( k = *(_DWORD *)v69 - 1; k > 0; --k )
      {
        v110 = v207;
        v145 = 4LL * (unsigned int)k;
        if ( (BYTE4(v207[v145 + 3]) & 0x40) != 0 )
        {
          v69 = v207;
          break;
        }
        if ( v207[v145 + 1] )
        {
          sqlite3ExprDeleteNN(v196);
          v110 = v207;
        }
        sqlite3DbFree(v196, v110[v145 + 2]);
        v69 = v207;
        --*(_DWORD *)v207;
        v111 = *(_DWORD *)v69;
      }
      v113 = 0;
      if ( v111 > 0 )
      {
        do
        {
          v114 = 4LL * v113;
          if ( (BYTE4(v69[v114 + 3]) & 0x40) == 0 )
            *v69[v114 + 1] = 122;
          ++v113;
        }
        while ( v113 < *(_DWORD *)v69 );
      }
    }
  }
  v71 = *((_DWORD *)a1 + 18) - 1;
  *((_DWORD *)a1 + 18) = v71;
  v13 = (*(_DWORD *)(v5 + 4) & 0x4000) == 0;
  v224 = v71;
  if ( v13 )
    *(_WORD *)(v5 + 2) = 320;
  if ( *(_QWORD *)(v5 + 96) )
    computeLimitRegisters(a1, v5, v71);
  if ( !*(_DWORD *)(v5 + 8) && (SDWORD2(v219) & 0x80000000) == 0 )
  {
    *(_BYTE *)sqlite3VdbeGetOp(v7, DWORD2(v219)) = 119;
    BYTE4(v220) |= 1u;
  }
  if ( (*(_BYTE *)(v5 + 4) & 1) != 0 )
  {
    HIDWORD(v229) = *((_DWORD *)a1 + 14);
    *((_DWORD *)a1 + 14) = HIDWORD(v229) + 1;
    v99 = sqlite3KeyInfoFromExprList(a1, *(_QWORD *)(v5 + 32), 0, 0);
    v100 = sqlite3VdbeAddOp3(Vdbe, 117, HIDWORD(v229), 0, 0);
    v101 = v99;
    v7 = Vdbe;
    v102 = v100;
    sqlite3VdbeChangeP4(Vdbe, v100, v101);
    v230 = v102;
    sqlite3VdbeChangeP5(v7, 8);
    BYTE1(v229) = 3;
  }
  else
  {
    BYTE1(v229) = 0;
  }
  v72 = v202;
  if ( v205 || v202 )
  {
    v214 = 0;
    memset(v228, 0, sizeof(v228));
    if ( v202 )
    {
      v103 = *(int **)(v5 + 32);
      v104 = *v103;
      v105 = v103 + 2;
      while ( v104 > 0 )
      {
        *((_WORD *)v105 + 13) = 0;
        v105 += 8;
        --v104;
      }
      v106 = *v72;
      v107 = v72 + 2;
      while ( v106 > 0 )
      {
        *((_WORD *)v107 + 13) = 0;
        v107 += 8;
        --v106;
      }
      if ( *(__int16 *)(v5 + 2) > 66 )
        *(_WORD *)(v5 + 2) = 66;
      if ( (_QWORD)v218 && *v72 == *(_DWORD *)v218 )
      {
        for ( m = 0; m < *v72; LOBYTE(v72[8 * v109 + 6]) = *(_BYTE *)(32 * v109 + v218 + 24) & 1 )
          v109 = m++;
        if ( !(unsigned int)sqlite3ExprListCompare(v72, v218, 0xFFFFFFFFLL) )
          v214 = 1;
      }
    }
    else
    {
      *(_WORD *)(v5 + 2) = 0;
    }
    v209 = *((_DWORD *)a1 + 18) - 1;
    *((_DWORD *)a1 + 18) = v209;
    v22 = sqlite3DbMallocZero(v196, 56);
    v23 = v22;
    if ( v22 )
      sqlite3ParserAddCleanup(a1, agginfoFree, v22);
    v11 = v196;
    if ( *(_BYTE *)(v196 + 103) )
      goto LABEL_39;
    *(_DWORD *)(v23 + 52) = *(_DWORD *)(v5 + 16);
    *(_QWORD *)v228 = a1;
    *(_QWORD *)&v228[8] = v12;
    *(_QWORD *)&v228[16] = v23;
    memset(&v228[24], 0, 32);
    if ( v72 )
      v26 = *v72;
    else
      LOWORD(v26) = 0;
    v27 = v207;
    *(_WORD *)(v23 + 2) = v26;
    *(_QWORD *)(v23 + 16) = v72;
    sqlite3ExprAnalyzeAggList(v228, v27);
    sqlite3ExprAnalyzeAggList(v228, v218);
    v28 = v208;
    if ( v208 )
    {
      if ( v72 )
      {
        v154 = *(_QWORD *)(v5 + 64);
        *((_QWORD *)&v221 + 1) = havingToWhereExprCb;
        memset(v222, 0, sizeof(v222));
        *(_QWORD *)&v221 = a1;
        v223 = v5;
        sqlite3WalkExpr(&v221, v154);
        v210 = *(_QWORD *)(v5 + 48);
        v28 = v208;
      }
      sqlite3ExprAnalyzeAggregates(v228, v28);
    }
    *(_DWORD *)(v23 + 36) = *(_DWORD *)(v23 + 32);
    if ( *(_QWORD *)(v5 + 56) || *(_QWORD *)(v5 + 64) || *(_DWORD *)(v23 + 48) != 1 )
      LOBYTE(TempRange) = 0;
    else
      LOBYTE(TempRange) = minMaxQuery(v196, **(_QWORD **)(v23 + 40), &v225);
    analyzeAggFuncArgs(v23, v228);
    v11 = v196;
    if ( *(_BYTE *)(v196 + 103) )
      goto LABEL_39;
    if ( !v72 )
    {
      v178 = isSimpleCount(v5, v23);
      v180 = v178;
      if ( v178 )
      {
        v181 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v178 + 96));
        v198 = v181;
        v183 = v182;
        v205 = *((_DWORD *)a1 + 14);
        v203 = v182;
        *((_DWORD *)a1 + 14) = v205 + 1;
        v206 = *(_DWORD *)(v180 + 40);
        sqlite3CodeVerifySchema(a1, v181);
        sqlite3TableLock(a1, v198, *(unsigned int *)(v180 + 40), 0, *(_QWORD *)v180);
        if ( *(char *)(v180 + 48) < 0 )
          v183 = sqlite3PrimaryKeyIndex(v180);
        if ( (*(_BYTE *)(*(_QWORD *)(v5 + 40) + 36LL) & 1) == 0 )
        {
          for ( n = *(_QWORD *)(v180 + 16); n; n = *(_QWORD *)(n + 40) )
          {
            if ( (*(_BYTE *)(n + 100) & 4) == 0 )
            {
              v185 = *(_WORD *)(n + 92);
              if ( v185 < *(__int16 *)(v180 + 60) && !*(_QWORD *)(n + 72) && (!v183 || v185 < *(__int16 *)(v183 + 92)) )
                v183 = n;
            }
          }
        }
        if ( v183 )
        {
          v206 = *(_DWORD *)(v183 + 88);
          v203 = sqlite3KeyInfoOfIndex(a1, v183);
        }
        sqlite3VdbeAddOp4Int(v7, 102, v205, v206, v198, 1);
        if ( v203 )
          sqlite3VdbeChangeP4(v7, 0xFFFFFFFFLL, v203);
        v186 = v205;
        *(_DWORD *)(v23 + 12) = *((_DWORD *)a1 + 15) + 1;
        *((_DWORD *)a1 + 15) += *(_DWORD *)(v23 + 32) + *(_DWORD *)(v23 + 48);
        sqlite3VdbeAddOp3(v7, 98, v186, *(_DWORD *)(v23 + 12) + *(_DWORD *)(v23 + 32), 0);
        sqlite3VdbeAddOp3(v7, 122, v205, 0, 0);
        explainSimpleCount(a1, v180, v183);
      }
      else
      {
        v187 = v179;
        v188 = *(_DWORD *)(v23 + 48);
        v203 = v179;
        v198 = v179;
        if ( *(_DWORD *)(v23 + 36) == (_DWORD)v179 )
        {
          if ( v188 == 1 )
          {
            v192 = *(_DWORD **)(v23 + 40);
            v188 = 1;
            if ( v192[4] >= (int)v179 )
            {
              v203 = *(_QWORD *)(*(_QWORD *)v192 + 32LL);
              LOWORD(v198) = v203 != 0 ? 0x500 : 0;
            }
          }
        }
        else
        {
          v189 = v179;
          if ( v188 <= 0 )
          {
LABEL_317:
            if ( v189 == v188 )
            {
              v187 = ++*((_DWORD *)a1 + 15);
              sqlite3VdbeAddOp3(v7, 71, 0, v187, v179);
              v188 = *(_DWORD *)(v23 + 48);
            }
          }
          else
          {
            v190 = *(_QWORD *)(v23 + 40);
            while ( 1 )
            {
              v191 = 32LL * v189;
              if ( (*(_DWORD *)(*(_QWORD *)(v191 + v190) + 4LL) & 0x1000000) == 0
                && (*(_BYTE *)(*(_QWORD *)(v191 + v190 + 8) + 4LL) & 0x20) != 0 )
              {
                break;
              }
              if ( (int)++v189 >= v188 )
                goto LABEL_317;
            }
          }
        }
        *(_DWORD *)(v23 + 12) = *((_DWORD *)a1 + 15) + 1;
        *((_DWORD *)a1 + 15) += v188 + *(_DWORD *)(v23 + 32);
        resetAccumulator(a1, v23);
        v193 = sqlite3WhereBegin(
                 (_DWORD)a1,
                 (_DWORD)v12,
                 v210,
                 v225,
                 v203,
                 v5,
                 (unsigned __int16)v198 | (unsigned __int8)TempRange,
                 0);
        v194 = v193;
        if ( !v193 )
          goto LABEL_173;
        v215 = *(unsigned __int8 *)(v193 + 67);
        updateAccumulator(a1, v187, v23, v215);
        if ( v215 )
        {
          v195 = *(_QWORD *)(v23 + 40);
          if ( v195 )
            fixDistinctOpenEph(a1, v215, *(unsigned int *)(v195 + 16), *(unsigned int *)(v195 + 20));
        }
        if ( v187 )
          sqlite3VdbeAddOp3(v7, 71, 1, v187, 0);
        if ( (_BYTE)TempRange )
          sqlite3WhereMinMaxOptEarlyOut(v7, v194);
        sqlite3WhereEnd(v194);
        finalizeAggFunctions(a1, v23);
      }
      *(_QWORD *)&v218 = 0;
      sqlite3ExprIfFalse(a1, v208, v209, 16);
      v64 = v212;
      selectInnerLoop((_DWORD)a1, v5, -1, 0, 0, (__int64)v212, v209, v209);
LABEL_77:
      v65 = v209;
LABEL_78:
      sqlite3VdbeResolveLabel(v7, v65);
      goto LABEL_108;
    }
    v216 = 0;
    v213 = 0;
    if ( *(_DWORD *)(v23 + 48) == 1 )
    {
      v155 = *(int **)(v23 + 40);
      if ( v155[4] >= 0 )
      {
        v156 = *(_QWORD *)v155;
        if ( v156 )
        {
          if ( (*(_DWORD *)(v156 + 4) & 0x1000) == 0 )
          {
            v157 = *(_QWORD *)(v156 + 32);
            if ( v157 )
            {
              v158 = sqlite3ExprDup(v196, *(_QWORD *)(v157 + 8), 0);
              v159 = sqlite3ExprListDup(v196, v202, 0);
              v160 = sqlite3ExprListAppend(a1, v159, v158);
              v72 = v202;
              v216 = v160;
              if ( v160 )
                LOWORD(v213) = 1280;
              else
                LOWORD(v213) = 0;
            }
          }
        }
      }
    }
    *(_DWORD *)(v23 + 4) = (*((_DWORD *)a1 + 14))++;
    v29 = sqlite3KeyInfoFromExprList(a1, v72, 0, *(unsigned int *)(v23 + 32));
    v30 = *(unsigned __int16 *)(v23 + 2);
    v31 = *(_DWORD *)(v23 + 4);
    v227 = v29;
    v32 = sqlite3VdbeAddOp4(v7, 119, v31, v30, 0, v29, -8);
    v33 = *((_DWORD *)a1 + 18);
    v215 = v32;
    v206 = *((_DWORD *)a1 + 15) + 1;
    v199 = v33 - 1;
    v34 = v206 + 1;
    v205 = v206 + 1;
    v35 = v206 + 3;
    v200 = v206 + 2;
    *((_DWORD *)a1 + 15) = v206 + 3;
    *((_DWORD *)a1 + 18) = v33 - 2;
    v36 = v35 + *v72;
    *((_DWORD *)a1 + 15) = v36;
    v198 = v36;
    *((_DWORD *)a1 + 15) = *v72 + v36;
    sqlite3VdbeAddOp3(v7, 71, 0, v34, 0);
    sqlite3VdbeAddOp3(v7, 75, 0, v200 + 2, v200 + 1 + *v72);
    sqlite3VdbeAddOp3(v7, 10, v200 + 1, v199 - 1, 0);
    v37 = 128;
    if ( (_BYTE)v229 != 2 )
      v37 = 64;
    v38 = sqlite3WhereBegin(
            (_DWORD)a1,
            (_DWORD)v12,
            v210,
            (_DWORD)v72,
            v216,
            v5,
            v37 | (unsigned __int16)(v213 | ((_WORD)v214 << 9)),
            0);
    v42 = 0;
    v203 = v38;
    v43 = v38;
    if ( !v38 )
    {
      sqlite3ExprListDeleteGeneric(v196, v216);
      goto LABEL_173;
    }
    v217 = v198 + 1;
    if ( a1[12] )
    {
      optimizeAggregateUseOfIndexedExpr(v40, v5, v23, v228);
      v42 = 0;
    }
    v44 = 0;
    *(_DWORD *)(v23 + 12) = *((_DWORD *)a1 + 15) + 1;
    *((_DWORD *)a1 + 15) += *(_DWORD *)(v23 + 32) + *(_DWORD *)(v23 + 48);
    v45 = *(char *)(v43 + 65) < 0;
    v198 = *(unsigned __int8 *)(v43 + 67);
    if ( !v45 )
      v44 = *(char *)(v43 + 65);
    if ( v44 == *v72 )
    {
      v197 = 0;
      v46 = 0;
      v204 = 0;
    }
    else
    {
      if ( !(_BYTE)v229 || (v161 = "DISTINCT", (*(_BYTE *)(v5 + 4) & 1) != 0) )
        v161 = "GROUP BY";
      sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v161);
      v163 = *v72;
      v164 = v163;
      v204 = 1;
      v197 = v163;
      if ( *(int *)(v23 + 32) > 0 )
      {
        v165 = 0;
        LODWORD(v162) = v163;
        do
        {
          v166 = *(__int16 *)(*(_QWORD *)(v23 + 24) + 24LL * v165 + 22);
          v167 = v164 + 1;
          if ( v166 < (int)v162 )
            v167 = v164;
          ++v165;
          v164 = v167;
          v168 = v162 + 1;
          if ( v166 < (int)v162 )
            v168 = v162;
          v162 = v168;
        }
        while ( (signed int)v165 < *(_DWORD *)(v23 + 32) );
      }
      TempRange = sqlite3GetTempRange(a1, v164, v162);
      sqlite3ExprCodeExprList((_DWORD)a1, (_DWORD)v72, TempRange, 0, v169);
      *(_BYTE *)v23 = 1;
      if ( *(int *)(v23 + 32) > 0 )
      {
        v170 = v197;
        v171 = 0;
        v172 = TempRange;
        do
        {
          v173 = *(_QWORD *)(v23 + 24);
          if ( *(__int16 *)(v173 + 24LL * v171 + 22) >= v170 )
          {
            sqlite3ExprCode(a1, *(_QWORD *)(v173 + 24LL * v171 + 8), v170 + v172);
            ++v170;
          }
          ++v171;
        }
        while ( v171 < *(_DWORD *)(v23 + 32) );
        v5 = v226;
        v7 = Vdbe;
      }
      *(_BYTE *)v23 = 0;
      TempReg = sqlite3GetTempReg(a1);
      sqlite3VdbeAddOp3(v7, 97, TempRange, v164, TempReg);
      sqlite3VdbeAddOp3(v7, 139, *(_DWORD *)(v23 + 4), TempReg, 0);
      sqlite3ReleaseTempReg(a1, TempReg);
      sqlite3ReleaseTempRange(v175, TempRange, v164);
      sqlite3WhereEnd(v203);
      v176 = *((_DWORD *)a1 + 14);
      *(_DWORD *)(v23 + 8) = v176;
      ++*((_DWORD *)a1 + 14);
      v197 = v176;
      LODWORD(v210) = sqlite3GetTempReg(a1);
      sqlite3VdbeAddOp3(v7, 121, v177, v210, v164);
      sqlite3VdbeAddOp3(v7, 34, *(_DWORD *)(v23 + 4), v209, 0);
      v72 = v202;
      v42 = 0;
      v46 = v210;
      *(_BYTE *)(v23 + 1) = 1;
    }
    if ( a1[12] )
    {
      aggregateConvertIndexedExprRefToColumn(v23, v39, v41, 0);
      v42 = 0;
    }
    if ( v214 )
    {
      v47 = v204;
      if ( (*(_BYTE *)(v196 + 96) & 4) != 0 || !v204 && (*(_BYTE *)(v203 + 68) & 8) == 0 )
        goto LABEL_65;
      *(_QWORD *)&v218 = 0;
      sqlite3VdbeChangeToNoop(v7, DWORD2(v219));
      v42 = 0;
    }
    v47 = v204;
LABEL_65:
    LODWORD(v210) = *(_DWORD *)(v7 + 144);
    if ( v47 )
    {
      sqlite3VdbeAddOp3(v7, 133, *(_DWORD *)(v23 + 4), v46, v197);
      v42 = 0;
    }
    for ( ii = 0; ii < *v72; ++ii )
    {
      v49 = ii + v217;
      v50 = 8LL * ii;
      LOWORD(TempRange) = v72[v50 + 8];
      if ( v204 == v42 )
      {
        *(_BYTE *)v23 = 1;
        sqlite3ExprCode(a1, *(_QWORD *)&v72[v50 + 2], v49);
      }
      else
      {
        sqlite3VdbeAddOp3(v7, 94, v197, ii, v49);
      }
      v42 = 0;
      if ( (_WORD)TempRange )
      {
        v51 = (_BYTE *)sqlite3ExprSkipCollateAndLikely(*(_QWORD *)(32LL * (unsigned __int16)TempRange
                                                                 + *(_QWORD *)(v5 + 32)
                                                                 - 24));
        if ( v51 )
        {
          if ( *v51 != 0xAA && *v51 != 0xB0 )
            sqlite3ExprToRegister(v52, ii + v200 + 2);
        }
      }
    }
    v53 = sqlite3KeyInfoRef(v227);
    sqlite3VdbeAddOp4(v7, 90, v200 + 2, v217, v54, v53, -8);
    v55 = *(_DWORD *)(v7 + 144);
    sqlite3VdbeAddOp3(v7, 14, v55 + 1, 0, v55 + 1);
    sqlite3VdbeAddOp3(v7, 10, v200, v199, 0);
    sqlite3VdbeAddOp3(a1[2], 79, v217, v200 + 2, *v202);
    v56 = v209;
    sqlite3VdbeAddOp3(v7, 50, v205, v209, 0);
    sqlite3VdbeAddOp3(v7, 10, v200 + 1, v199 - 1, 0);
    Op = sqlite3VdbeGetOp(v7, v55);
    v58 = v198;
    v59 = v206;
    *(_DWORD *)(Op + 8) = *(_DWORD *)(v7 + 144);
    updateAccumulator(a1, v59, v23, v58);
    sqlite3VdbeAddOp3(v7, 71, 1, v206, 0);
    if ( v204 )
    {
      sqlite3VdbeAddOp3(v7, 37, *(_DWORD *)(v23 + 4), v210, 0);
    }
    else
    {
      sqlite3WhereEnd(v203);
      sqlite3VdbeChangeToNoop(v7, v215);
    }
    sqlite3ExprListDeleteGeneric(v196, v216);
    sqlite3VdbeAddOp3(v7, 10, v200, v199, 0);
    sqlite3VdbeAddOp3(v7, 9, 0, v56, 0);
    v60 = Vdbe;
    v61 = *(_DWORD *)(v7 + 144);
    sqlite3VdbeAddOp3(Vdbe, 71, 1, v205, 0);
    sqlite3VdbeAddOp3(v60, 67, v200, 0, 0);
    sqlite3VdbeResolveLabel(v60, v199);
    v62 = *(_DWORD *)(v60 + 144);
    sqlite3VdbeAddOp3(v60, 50, v206, v62 + 2, 0);
    sqlite3VdbeAddOp3(v60, 67, v200, 0, 0);
    finalizeAggFunctions(a1, v23);
    sqlite3ExprIfFalse(a1, v208, (unsigned int)++v62, 16);
    selectInnerLoop((_DWORD)a1, v5, -1, (unsigned int)&v218, (__int64)&v229, (__int64)v212, v62, v61);
    v7 = Vdbe;
    v63 = v200;
    sqlite3VdbeAddOp3(Vdbe, 67, v200, 0, 0);
    sqlite3VdbeResolveLabel(v7, v199 - 1);
    resetAccumulator(a1, v23);
    sqlite3VdbeAddOp3(v7, 71, 0, v206, 0);
    sqlite3VdbeAddOp3(v7, 67, v63 + 1, 0, 0);
    if ( (_WORD)v213 && v198 )
      fixDistinctOpenEph(
        a1,
        v198,
        *(unsigned int *)(*(_QWORD *)(v23 + 40) + 16LL),
        *(unsigned int *)(*(_QWORD *)(v23 + 40) + 20LL));
    v64 = v212;
    goto LABEL_77;
  }
  v73 = 256;
  if ( !(_BYTE)v229 )
    v73 = 0;
  v74 = *(_QWORD *)(v5 + 112);
  v75 = v73 | *(_WORD *)(v5 + 4) & 0x4000;
  if ( v74 )
    sqlite3WindowCodeInit(a1, v5);
  v76 = sqlite3WhereBegin((_DWORD)a1, (_DWORD)v12, v210, v218, *(_QWORD *)(v5 + 32), v5, v75, *(__int16 *)(v5 + 2));
  v203 = v76;
  v77 = v76;
  if ( !v76 )
  {
LABEL_173:
    v11 = v196;
    goto LABEL_39;
  }
  v78 = *(_WORD *)(v76 + 74);
  if ( v78 < *(__int16 *)(v5 + 2) )
    *(_WORD *)(v5 + 2) = v78;
  if ( (_BYTE)v229 )
  {
    v96 = BYTE1(v229);
    if ( *(_BYTE *)(v77 + 67) )
      v96 = *(_BYTE *)(v77 + 67);
    BYTE1(v229) = v96;
  }
  v79 = v218;
  if ( (_QWORD)v218 )
  {
    v146 = 0;
    if ( *(char *)(v77 + 65) >= 0 )
      v146 = *(char *)(v77 + 65);
    DWORD2(v218) = v146;
    if ( (*(_BYTE *)(v77 + 68) & 4) == 0
      || (v147 = 112LL * *(unsigned __int8 *)(v77 + 64), *(_QWORD *)(v147 + v77 + 808)) )
    {
      v148 = *(_DWORD *)(v77 + 48);
    }
    else
    {
      v148 = *(_DWORD *)(v147 + v77 + 768);
    }
    LODWORD(v220) = v148;
    if ( v146 == *(_DWORD *)v218 )
      v79 = 0;
    *(_QWORD *)&v218 = v79;
  }
  if ( (SDWORD2(v219) & 0x80000000) == 0 && !v79 )
  {
    sqlite3VdbeChangeToNoop(v7, DWORD2(v219));
    v77 = v203;
  }
  if ( v74 )
  {
    v149 = *((_DWORD *)a1 + 18);
    ++*((_DWORD *)a1 + 15);
    --v149;
    v150 = *((_DWORD *)a1 + 15);
    v151 = v149 - 1;
    v152 = v149 - 2;
    *((_DWORD *)a1 + 18) = v149 - 2;
    sqlite3WindowCodeStep((_DWORD)a1, v5, v77, v150, v149);
    sqlite3VdbeAddOp3(Vdbe, 9, 0, v149 - 2, 0);
    sqlite3VdbeResolveLabel(Vdbe, v149);
    v64 = v212;
    LODWORD(v220) = 0;
    selectInnerLoop((_DWORD)a1, v5, -1, (unsigned int)&v218, (__int64)&v229, (__int64)v212, v151, v152);
    v153 = v151;
    v7 = Vdbe;
    sqlite3VdbeResolveLabel(Vdbe, v153);
    sqlite3VdbeAddOp3(v7, 67, v150, 0, 0);
    v65 = v152;
    goto LABEL_78;
  }
  v64 = v212;
  selectInnerLoop(
    (_DWORD)a1,
    v5,
    -1,
    (unsigned int)&v218,
    (__int64)&v229,
    (__int64)v212,
    *(_DWORD *)(v77 + 48),
    *(_DWORD *)(v77 + 52));
  sqlite3WhereEnd(v203);
LABEL_108:
  if ( BYTE1(v229) == 3 )
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
  if ( (_QWORD)v218 )
    generateSortTail((_DWORD)a1, v5, (unsigned int)&v218, *(_DWORD *)v207, (__int64)v64);
  sqlite3VdbeResolveLabel(v7, v224);
  v8 = *((_DWORD *)a1 + 13) > 0;
LABEL_113:
  v11 = v196;
LABEL_39:
  if ( v225 )
    exprListDeleteNN(v11, v225);
  v24 = *((unsigned int *)a1 + 80);
  if ( (_DWORD)v24 )
    v25 = *(_DWORD *)(sqlite3VdbeGetOp(a1[2], v24) + 8);
  else
    v25 = 0;
  *((_DWORD *)a1 + 80) = v25;
  return v8;
}

```

## disassembly

```asm
0x180037194  mov     [rsp-8+arg_18], rbx
0x180037199  push    rbp
0x18003719a  push    rsi
0x18003719b  push    rdi
0x18003719c  push    r12
0x18003719e  push    r13
0x1800371a0  push    r14
0x1800371a2  push    r15
0x1800371a4  lea     rbp, [rsp-0A0h]
0x1800371ac  sub     rsp, 1A0h
0x1800371b3  mov     rax, cs:__security_cookie
0x1800371ba  xor     rax, rsp
0x1800371bd  mov     [rbp+0D0h+var_38], rax
0x1800371c4  xor     eax, eax
0x1800371c6  mov     [rbp+0D0h+var_128], r8
0x1800371ca  xorps   xmm0, xmm0
0x1800371cd  mov     [rbp+0D0h+var_48], rax
0x1800371d4  mov     [rbp+0D0h+var_40], eax
0x1800371da  xor     esi, esi
0x1800371dc  mov     rax, [rcx]
0x1800371df  mov     r14, r8
0x1800371e2  mov     [rsp+1D0h+var_190], rax
0x1800371e7  mov     r13, rdx
0x1800371ea  mov     [rbp+0D0h+var_90], rdx
0x1800371ee  mov     r15, rcx
0x1800371f1  movups  [rbp+0D0h+var_100], xmm0
0x1800371f5  mov     [rbp+0D0h+var_98], rsi
0x1800371f9  movups  [rbp+0D0h+var_F0], xmm0
0x1800371fd  movups  [rbp+0D0h+var_E0], xmm0
0x180037201  call    sqlite3GetVdbe
0x180037206  mov     [rbp+0D0h+var_130], rax
0x18003720a  mov     rdi, rax
0x18003720d  test    r13, r13
0x180037210  jz      loc_180038FA8
0x180037216  cmp     [r15+34h], esi
0x18003721a  jnz     loc_180038FA8
0x180037220  xor     r9d, r9d
0x180037223  mov     [rsp+1D0h+var_1B0], rsi
0x180037228  xor     r8d, r8d
0x18003722b  lea     edx, [rsi+15h]
0x18003722e  mov     rcx, r15
0x180037231  call    sqlite3AuthCheck
0x180037236  test    eax, eax
0x180037238  jnz     loc_180038FA8
0x18003723e  cmp     byte ptr [r14], 6
0x180037242  lea     r12d, [rsi+1]
0x180037246  jbe     loc_1800373E6
0x18003724c  xor     r8d, r8d
0x18003724f  mov     rdx, r13
0x180037252  mov     rcx, r15
0x180037255  call    sqlite3SelectPrep
0x18003725a  cmp     [r15+34h], esi
0x18003725e  jnz     loc_180037CA6
0x180037264  mov     ebx, [r13+4]
0x180037268  bt      ebx, 17h
0x18003726c  jb      loc_180038181
0x180037272  cmp     byte ptr [r14], 9
0x180037276  jz      loc_1800373D6
0x18003727c  mov     rdx, r13
0x18003727f  mov     rcx, r15
0x180037282  call    sqlite3WindowRewrite
0x180037287  mov     r10, [rsp+1D0h+var_190]
0x18003728c  test    eax, eax
0x18003728e  jnz     loc_180037463
0x180037294  mov     eax, [r13+4]
0x180037298  xorps   xmm0, xmm0
0x18003729b  mov     r14, [r13+28h]
0x18003729f  and     eax, 8
0x1800372a2  mov     [rsp+1D0h+var_15C], eax
0x1800372a6  mov     eax, esi
0x1800372a8  setnz   al
0x1800372ab  mov     [rsp+1D0h+var_184], eax
0x1800372af  mov     rax, [r13+48h]
0x1800372b3  movups  [rbp+0D0h+var_100], xmm0
0x1800372b7  mov     qword ptr [rbp+0D0h+var_100], rax
0x1800372bb  movups  [rbp+0D0h+var_F0], xmm0
0x1800372bf  movups  [rbp+0D0h+var_E0], xmm0
0x1800372c3  xor     ebx, ebx
0x1800372c5  mov     edx, 40h ; '@'
0x1800372ca  cmp     [r13+50h], rbx
0x1800372ce  jz      short loc_1800372F4
0x1800372d0  mov     r8, [rbp+0D0h+var_128]
0x1800372d4  mov     rdx, r13
0x1800372d7  mov     rcx, r15
0x1800372da  call    multiSelect
0x1800372df  mov     r9d, eax
0x1800372e2  cmp     [r13+58h], rbx
0x1800372e6  jz      loc_18003814C
0x1800372ec  mov     eax, r9d
0x1800372ef  jmp     loc_180037492
0x1800372f4  cmp     esi, [r14]
0x1800372f7  jge     loc_180037AA7
0x1800372fd  movsxd  rax, esi
0x180037300  lea     rbx, [rax+rax*4]
0x180037304  add     rbx, rbx
0x180037307  test    byte ptr [r14+rbx*8+24h], 4
0x18003730d  jnz     short loc_18003733B
0x18003730f  xor     r11d, r11d
0x180037312  mov     [rbp+0D0h+var_148], r11
0x180037316  movzx   eax, byte ptr [r14+rbx*8+20h]
0x18003731c  mov     r9, [r14+rbx*8+18h]
0x180037321  mov     [rbp+0D0h+var_150], r9
0x180037325  test    al, 48h
0x180037327  jnz     loc_1800381CD
0x18003732d  mov     rcx, [rbp+0D0h+var_148]
0x180037331  test    rcx, rcx
0x180037334  jnz     short loc_180037349
0x180037336  add     esi, r12d
0x180037339  jmp     short loc_1800372C3
0x18003733b  mov     rax, [r14+rbx*8+50h]
0x180037340  mov     rcx, [rax]
0x180037343  mov     [rbp+0D0h+var_148], rcx
0x180037347  jmp     short loc_180037316
0x180037349  mov     rax, [rcx+20h]
0x18003734d  movsx   r8d, word ptr [r9+36h]
0x180037352  mov     edx, [rax]
0x180037354  cmp     r8d, edx
0x180037357  jnz     loc_180038333
0x18003735d  test    dword ptr [r14+rbx*8+24h], 200h
0x180037366  jnz     loc_18003829F
0x18003736c  xor     ebx, ebx
0x18003736e  test    byte ptr [rcx+4], 8
0x180037372  jnz     short loc_180037336
0x180037374  mov     r8, [rcx+48h]
0x180037378  test    r8, r8
0x18003737b  jnz     loc_1800382B4
0x180037381  mov     r9d, [rsp+1D0h+var_184]
0x180037386  mov     r8d, esi
0x180037389  mov     rdx, r13
0x18003738c  mov     rcx, r15
0x18003738f  call    flattenSubquery
0x180037394  test    eax, eax
0x180037396  jz      short loc_1800373A9
0x180037398  xor     esi, esi
0x18003739a  cmp     [r15+34h], esi
0x18003739e  jnz     loc_180037CA6
0x1800373a4  or      esi, 0FFFFFFFFh
0x1800373a7  xor     ebx, ebx
0x1800373a9  mov     r10, [rsp+1D0h+var_190]
0x1800373ae  cmp     [r10+67h], bl
0x1800373b2  jnz     loc_180037461
0x1800373b8  mov     rax, [rbp+0D0h+var_128]
0x1800373bc  mov     r14, [r13+28h]
0x1800373c0  cmp     byte ptr [rax], 8
0x1800373c3  jbe     loc_180037336
0x1800373c9  mov     rax, [r13+48h]
0x1800373cd  mov     qword ptr [rbp+0D0h+var_100], rax
0x1800373d1  jmp     loc_180037336
0x1800373d6  mov     rdx, r13
0x1800373d9  mov     rcx, r15
0x1800373dc  call    sqlite3GenerateColumnNames
0x1800373e1  jmp     loc_18003727C
0x1800373e6  mov     r8, [r13+48h]
0x1800373ea  test    r8, r8
0x1800373ed  jnz     loc_180038169
0x1800373f3  and     dword ptr [r13+4], 0FFFFFFFEh
0x1800373f8  bts     dword ptr [r13+4], 16h
0x1800373fe  jmp     loc_18003724C
0x180037403  xorps   xmm0, xmm0
0x180037406  mov     [rbp+0D0h+var_11C], esi
0x180037409  xor     eax, eax
0x18003740b  mov     [rbp+0D0h+var_50], rax
0x180037412  movups  [rbp+0D0h+var_80], xmm0
0x180037416  movups  [rbp+0D0h+var_70], xmm0
0x18003741a  movups  [rbp+0D0h+var_60], xmm0
0x18003741e  test    rbx, rbx
0x180037421  jnz     loc_180038045
0x180037427  mov     [r13+2], si
0x18003742c  mov     eax, [r15+48h]
0x180037430  mov     edx, 38h ; '8'
0x180037435  mov     rcx, [rsp+1D0h+var_190]
0x18003743a  dec     eax
0x18003743c  mov     [rbp+0D0h+var_140], eax
0x18003743f  mov     [r15+48h], eax
0x180037443  call    sqlite3DbMallocZero
0x180037448  xor     ecx, ecx
0x18003744a  mov     rsi, rax
0x18003744d  test    rax, rax
0x180037450  jnz     loc_18003883E
0x180037456  mov     r10, [rsp+1D0h+var_190]
0x18003745b  cmp     [r10+67h], cl
0x18003745f  jz      short loc_1800374BC
0x180037461  xor     esi, esi
0x180037463  mov     rax, [rbp+0D0h+var_98]
0x180037467  test    rax, rax
0x18003746a  jz      short loc_180037477
0x18003746c  mov     rdx, rax
0x18003746f  mov     rcx, r10
0x180037472  call    exprListDeleteNN
0x180037477  mov     edx, [r15+140h]
0x18003747e  test    edx, edx
0x180037480  jnz     loc_180038F97
0x180037486  mov     eax, esi
0x180037488  mov     [r15+140h], eax
0x18003748f  mov     eax, r12d
0x180037492  mov     rcx, [rbp+0D0h+var_38]
0x180037499  xor     rcx, rsp; StackCookie
0x18003749c  call    __security_check_cookie
0x1800374a1  mov     rbx, [rsp+1D0h+arg_18]
0x1800374a9  add     rsp, 1A0h
0x1800374b0  pop     r15
0x1800374b2  pop     r14
0x1800374b4  pop     r13
0x1800374b6  pop     r12
0x1800374b8  pop     rdi
0x1800374b9  pop     rsi
0x1800374ba  pop     rbp
0x1800374bb  retn
0x1800374bc  mov     eax, [r13+10h]
0x1800374c0  xorps   xmm0, xmm0
0x1800374c3  mov     [rsi+34h], eax
0x1800374c6  xorps   xmm1, xmm1
0x1800374c9  mov     qword ptr [rbp+0D0h+var_80], r15
0x1800374cd  mov     qword ptr [rbp+0D0h+var_80+8], r14
0x1800374d1  mov     qword ptr [rbp+0D0h+var_70], rsi
0x1800374d5  movdqu  [rbp+0D0h+var_70+8], xmm0
0x1800374da  movdqu  [rbp+0D0h+var_60+8], xmm1
0x1800374df  test    rbx, rbx
0x1800374e2  jz      loc_180037F23
0x1800374e8  mov     eax, [rbx]
0x1800374ea  mov     rdx, [rbp+0D0h+var_150]
0x1800374ee  lea     rcx, [rbp+0D0h+var_80]
0x1800374f2  mov     [rsi+2], ax
0x1800374f6  mov     [rsi+10h], rbx
0x1800374fa  call    sqlite3ExprAnalyzeAggList
0x1800374ff  mov     rdx, qword ptr [rbp+0D0h+var_100]
0x180037503  lea     rcx, [rbp+0D0h+var_80]
0x180037507  call    sqlite3ExprAnalyzeAggList
0x18003750c  mov     rax, [rbp+0D0h+var_148]
0x180037510  xor     ecx, ecx
0x180037512  test    rax, rax
0x180037515  jnz     loc_180038857
0x18003751b  mov     eax, [rsi+20h]
0x18003751e  mov     [rsi+24h], eax
0x180037521  cmp     [r13+38h], rcx
0x180037525  jz      loc_180038013
0x18003752b  mov     byte ptr [rsp+1D0h+var_178], cl
0x18003752f  lea     rdx, [rbp+0D0h+var_80]
0x180037533  mov     rcx, rsi
0x180037536  call    analyzeAggFuncArgs
0x18003753b  mov     r10, [rsp+1D0h+var_190]
0x180037540  xor     r11d, r11d
0x180037543  cmp     [r10+67h], r11b
0x180037547  jnz     loc_180037461
0x18003754d  test    rbx, rbx
0x180037550  jz      loc_180038BFA
0x180037556  mov     [rbp+0D0h+var_110], r11
0x18003755a  mov     [rbp+0D0h+var_120], r11d
0x18003755e  cmp     [rsi+30h], r12d
0x180037562  jz      loc_1800388A7
0x180037568  mov     eax, [r15+38h]
0x18003756c  xor     r8d, r8d
0x18003756f  mov     [rsi+4], eax
0x180037572  mov     rdx, rbx
0x180037575  add     [r15+38h], r12d
0x180037579  mov     rcx, r15
0x18003757c  mov     r9d, [rsi+20h]
0x180037580  call    sqlite3KeyInfoFromExprList
0x180037585  movzx   r9d, word ptr [rsi+2]
0x18003758a  mov     edx, 77h ; 'w'
0x18003758f  mov     r8d, [rsi+4]
0x180037593  mov     rcx, rdi
0x180037596  mov     [rsp+1D0h+var_1A0], 0FFFFFFF8h
0x18003759e  mov     [rsp+1D0h+var_1A8], rax
0x1800375a3  mov     dword ptr [rsp+1D0h+var_1B0], 0
0x1800375ab  mov     [rbp+0D0h+var_88], rax
0x1800375af  call    sqlite3VdbeAddOp4
0x1800375b4  mov     ecx, [r15+48h]
0x1800375b8  mov     [rbp+0D0h+var_118], eax
0x1800375bb  mov     eax, [r15+3Ch]
0x1800375bf  inc     eax
0x1800375c1  mov     dword ptr [rsp+1D0h+var_1B0], 0
0x1800375c9  dec     ecx
0x1800375cb  mov     [rsp+1D0h+var_158], eax
0x1800375cf  mov     [rsp+1D0h+var_180], ecx
0x1800375d3  lea     r8d, [rax+1]
0x1800375d7  lea     eax, [r8+1]
0x1800375db  mov     [rsp+1D0h+var_15C], r8d
0x1800375e0  lea     edx, [rax+1]
0x1800375e3  mov     [rsp+1D0h+var_17C], eax
0x1800375e7  lea     eax, [rcx-1]
0x1800375ea  mov     [r15+3Ch], edx
0x1800375ee  mov     [r15+48h], eax
0x1800375f2  mov     r9d, r8d
0x1800375f5  mov     ecx, [rbx]
0x1800375f7  xor     r8d, r8d
0x1800375fa  add     ecx, edx
0x1800375fc  mov     [r15+3Ch], ecx
0x180037600  mov     [rsp+1D0h+var_184], ecx
0x180037604  add     ecx, [rbx]
0x180037606  lea     edx, [r8+47h]
0x18003760a  mov     [r15+3Ch], ecx
0x18003760e  mov     rcx, rdi
0x180037611  call    sqlite3VdbeAddOp3
0x180037616  mov     ecx, [rbx]
0x180037618  xor     r8d, r8d
0x18003761b  mov     edx, [rsp+1D0h+var_17C]
0x18003761f  inc     edx
0x180037621  add     ecx, edx
0x180037623  mov     dword ptr [rsp+1D0h+var_1B0], ecx
  ... truncated ...
```
