# sqlite3Select

- ea: `0x180037194`
- end: `0x180038fb2`
- name: `sqlite3Select`
- size: `7710`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
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
  unsigned int *v17; // r9
  int v18; // r8d
  int v19; // edx
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rsi
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  unsigned int *v27; // rdx
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
  unsigned __int8 *v64; // rbx
  __int64 v65; // rdx
  _BYTE *v66; // rax
  int j; // eax
  int v68; // ecx
  unsigned int *v69; // rbx
  int *v70; // rdx
  int v71; // eax
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
  __int64 v103; // r8
  __int64 v104; // r9
  int *v105; // rax
  int v106; // ecx
  _DWORD *v107; // rdx
  int v108; // ecx
  _DWORD *v109; // rdx
  int m; // r8d
  __int64 v111; // rdx
  unsigned int *v112; // rcx
  int v113; // eax
  int k; // esi
  signed int v115; // ecx
  __int64 v116; // rax
  __int64 v117; // rdx
  int v118; // ecx
  __int64 v119; // rsi
  const char *v120; // r8
  int v121; // eax
  char v122; // al
  __int64 v123; // rdx
  int i; // r9d
  char v125; // al
  unsigned int v126; // edx
  int v127; // eax
  __int64 v128; // r10
  __int64 v129; // rdx
  __int64 v130; // rax
  __int64 v131; // rax
  int v132; // r9d
  int v133; // r8d
  __int64 v134; // rbx
  int v135; // r9d
  __int64 v136; // rax
  _DWORD *v137; // rbx
  int v138; // r9d
  int v139; // eax
  unsigned int v140; // eax
  int v141; // r9d
  __int64 v142; // rcx
  int *v143; // rax
  int *v144; // rdx
  int v145; // r8d
  __int64 v146; // rax
  __int64 v147; // rbx
  int v148; // r8d
  __int64 v149; // rax
  int v150; // eax
  unsigned int v151; // ebx
  int v152; // esi
  unsigned int v153; // edi
  unsigned int v154; // r14d
  __int64 v155; // rdx
  __int64 v156; // rdx
  int *v157; // rax
  __int64 v158; // rax
  __int64 v159; // rdx
  __int64 v160; // rbx
  __int64 v161; // rax
  __int64 v162; // rax
  const char *v163; // r9
  int v164; // eax
  unsigned int v165; // r14d
  unsigned int v166; // r9d
  int v167; // r8d
  int v168; // edx
  unsigned int v169; // eax
  int v170; // eax
  char v171; // r11
  signed int v172; // ebx
  int v173; // edi
  unsigned int v174; // r13d
  __int64 v175; // rcx
  unsigned int TempReg; // ebx
  __int64 v177; // rcx
  __int64 v178; // r9
  unsigned int v179; // edx
  int v180; // edx
  __int64 v181; // rax
  __int64 v182; // r11
  __int64 v183; // rbx
  unsigned int v184; // eax
  __int64 v185; // r11
  __int64 v186; // r14
  __int64 n; // rcx
  __int16 v188; // ax
  int v189; // r8d
  unsigned int v190; // ebx
  int v191; // edx
  unsigned int v192; // ecx
  __int64 v193; // r9
  __int64 v194; // r8
  _DWORD *v195; // rax
  __int64 v196; // rax
  __int64 v197; // r14
  __int64 v198; // r8
  __int64 v199; // [rsp+40h] [rbp-C0h]
  unsigned int v200; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v201; // [rsp+4Ch] [rbp-B4h]
  unsigned int v202; // [rsp+50h] [rbp-B0h]
  unsigned int v203; // [rsp+54h] [rbp-ACh]
  unsigned int TempRange; // [rsp+58h] [rbp-A8h]
  int *v205; // [rsp+60h] [rbp-A0h]
  __int64 v206; // [rsp+68h] [rbp-98h]
  int v207; // [rsp+70h] [rbp-90h]
  int v208; // [rsp+74h] [rbp-8Ch]
  unsigned int v209; // [rsp+78h] [rbp-88h]
  unsigned int *v210; // [rsp+80h] [rbp-80h]
  __int64 v211; // [rsp+88h] [rbp-78h]
  unsigned int v212; // [rsp+90h] [rbp-70h]
  __int64 v213; // [rsp+98h] [rbp-68h]
  __int64 Vdbe; // [rsp+A0h] [rbp-60h]
  __int128 *v215; // [rsp+A8h] [rbp-58h]
  int v216; // [rsp+B0h] [rbp-50h]
  int v217; // [rsp+B4h] [rbp-4Ch]
  unsigned int v218; // [rsp+B8h] [rbp-48h]
  __int64 v219; // [rsp+C0h] [rbp-40h]
  unsigned int v220; // [rsp+C8h] [rbp-38h]
  __int128 v221; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v222; // [rsp+E0h] [rbp-20h]
  __int128 v223; // [rsp+F0h] [rbp-10h]
  __int128 v224; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v225[24]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v226; // [rsp+128h] [rbp+28h]
  unsigned int v227; // [rsp+130h] [rbp+30h]
  _DWORD *v228; // [rsp+138h] [rbp+38h] BYREF
  __int64 v229; // [rsp+140h] [rbp+40h]
  __int64 v230; // [rsp+148h] [rbp+48h]
  _BYTE v231[56]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v232; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v233; // [rsp+190h] [rbp+90h]

  v215 = a3;
  v232 = 0;
  v233 = 0;
  v3 = 0;
  v199 = *a1;
  v5 = a2;
  v229 = a2;
  v221 = 0;
  v228 = 0;
  v222 = 0;
  v223 = 0;
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
    v119 = *(_QWORD *)(v5 + 40) + 8LL;
    if ( (unsigned int)sameSrcAlias(v119) )
    {
      v120 = *(const char **)(v119 + 8);
      if ( !v120 )
        v120 = **(const char ***)(v119 + 16);
      sqlite3ErrorMsg(a1, "target object/alias may not appear in FROM clause: %s", v120);
      goto LABEL_173;
    }
    *(_DWORD *)(v5 + 4) = v9 & 0xFF7FFFFF;
    v3 = 0;
  }
  if ( *(_BYTE *)a3 == 9 )
    sqlite3GenerateColumnNames(a1, v5);
  v10 = sqlite3WindowRewrite(a1, v5);
  v11 = v199;
  if ( v10 )
    goto LABEL_39;
  v12 = *(int **)(v5 + 40);
  v13 = (*(_DWORD *)(v5 + 4) & 8) == 0;
  v208 = *(_DWORD *)(v5 + 4) & 8;
  v201 = !v13;
  v221 = *(unsigned __int64 *)(v5 + 72);
  v222 = 0;
  v223 = 0;
  while ( 1 )
  {
    if ( *(_QWORD *)(v5 + 80) )
    {
      v14 = multiSelect(a1, (unsigned __int8 *)v5, v215);
      if ( !*(_QWORD *)(v5 + 88) )
      {
        v117 = *((unsigned int *)a1 + 80);
        if ( (_DWORD)v117 )
          v118 = *(_DWORD *)(sqlite3VdbeGetOp(a1[2], v117) + 8);
        else
          v118 = 0;
        *((_DWORD *)a1 + 80) = v118;
      }
      return v14;
    }
    if ( v3 >= *v12 )
      break;
    if ( (v12[20 * v3 + 9] & 4) != 0 )
      v211 = **(_QWORD **)&v12[20 * v3 + 20];
    else
      v211 = 0;
    v16 = v12[20 * v3 + 8];
    v17 = *(unsigned int **)&v12[20 * v3 + 6];
    v210 = v17;
    if ( (v16 & 0x48) != 0 )
    {
      v121 = sqlite3ExprImpliesNonNullRow(*(_QWORD *)(v5 + 48), (unsigned int)v12[20 * v3 + 10], v16 & 0x40);
      v11 = v199;
      if ( v121 && (*(_DWORD *)(v199 + 96) & 0x2000) == 0 )
      {
        v122 = v12[20 * v3 + 8];
        if ( (v122 & 8) != 0 )
        {
          if ( (v122 & 0x10) != 0 )
          {
            LOBYTE(v12[20 * v3 + 8]) = v122 & 0xF7;
          }
          else
          {
            v123 = (unsigned int)v12[20 * v3 + 10];
            LOBYTE(v12[20 * v3 + 8]) = v122 & 0xD7;
            unsetJoinExpr(*(_QWORD *)(v5 + 48), v123, 0);
          }
        }
        if ( (v12[20 * v3 + 8] & 0x40) != 0 )
        {
          for ( i = v3 + 1; ; ++i )
          {
            v126 = *v12;
            if ( i >= *v12 )
              break;
            v125 = v12[20 * i + 8];
            if ( (v125 & 0x10) != 0 )
            {
              if ( (v125 & 8) != 0 )
              {
                LOBYTE(v12[20 * i + 8]) = v125 & 0xEF;
              }
              else
              {
                LOBYTE(v12[20 * i + 8]) = v125 & 0xCF;
                unsetJoinExpr(*(_QWORD *)(v5 + 48), (unsigned int)v12[20 * i + 10], 1);
              }
            }
          }
          do
          {
            if ( (--v126 & 0x80000000) != 0 )
              break;
            LOBYTE(v12[20 * v126 + 8]) &= ~0x40u;
          }
          while ( (v12[20 * v126 + 8] & 0x10) == 0 );
        }
      }
      v17 = v210;
    }
    if ( v211 )
    {
      v18 = *((__int16 *)v17 + 27);
      v19 = **(_DWORD **)(v211 + 32);
      if ( v18 != v19 )
      {
        sqlite3ErrorMsg(a1, "expected %d columns for '%s' but got %d", v18, *(const char **)v17, v19);
        goto LABEL_173;
      }
      if ( ((v12[20 * v3 + 9] & 0x200) == 0 || *(_BYTE *)(*(_QWORD *)&v12[20 * v3 + 16] + 18LL))
        && (*(_BYTE *)(v211 + 4) & 8) == 0 )
      {
        v20 = *(_QWORD *)(v211 + 72);
        if ( v20 )
        {
          if ( !*(_QWORD *)(v5 + 72) && *v12 <= 1
            || *(_QWORD *)(v211 + 96)
            || (*(_DWORD *)(v211 + 4) & 0x8002000) != 0
            || (*(_DWORD *)(v5 + 4) & 0x8000000) != 0
            || (*(_DWORD *)(v11 + 96) & 0x40000) != 0 )
          {
            if ( !v3 && (*(_DWORD *)(v5 + 4) & 0x40000) != 0 && (*v12 == 1 || (v12[28] & 0x22) != 0) )
              goto LABEL_19;
          }
          else
          {
            sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v20);
            *(_QWORD *)(v211 + 72) = 0;
          }
        }
        if ( (unsigned int)flattenSubquery(a1, v5, (unsigned int)v3, v201) )
        {
          if ( *((_DWORD *)a1 + 13) )
            goto LABEL_113;
          v3 = -1;
        }
        v11 = v199;
        if ( *(_BYTE *)(v199 + 103) )
          goto LABEL_39;
        v12 = *(int **)(v5 + 40);
        if ( *(_BYTE *)v215 > 8u )
          *(_QWORD *)&v221 = *(_QWORD *)(v5 + 72);
      }
    }
LABEL_19:
    ++v3;
  }
  v66 = *(_BYTE **)(v5 + 48);
  if ( v66 && *v66 == 44 && (*(_DWORD *)(v11 + 96) & 0x8000) == 0 )
  {
    propagateConstants(a1, v5);
    v11 = v199;
  }
  if ( (*(_DWORD *)(v11 + 96) & 0x201) == 0 )
  {
    v95 = countOfViewOptimization(a1, v5);
    v11 = v199;
    if ( v95 )
    {
      if ( *(_BYTE *)(v199 + 103) )
        goto LABEL_39;
      v12 = *(int **)(v5 + 40);
    }
  }
  for ( j = 0; ; j = v202 + 1 )
  {
    v202 = j;
    if ( j >= *v12 )
      break;
    memset(v225, 0, 21);
    v224 = 0;
    v80 = 20LL * j;
    v81 = (__int64)&v12[v80 + 2];
    if ( !*(_QWORD *)&v12[v80 + 12] && *(_QWORD *)v81 )
    {
      if ( (*(_DWORD *)(v81 + 28) & 0x10000) != 0 )
      {
        v127 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v81 + 72));
        v129 = *(_QWORD *)(32LL * v127 + *(_QWORD *)(v128 + 32));
      }
      else
      {
        v129 = 0;
        if ( (*(_BYTE *)(v81 + 28) & 4) == 0 )
          v129 = *(_QWORD *)(v81 + 72);
      }
      sqlite3AuthCheck((_DWORD)a1, 20, *(_QWORD *)v81, (unsigned int)qword_18009EEF0, v129);
    }
    if ( (*(_BYTE *)(v81 + 28) & 4) != 0 )
    {
      v82 = *(_QWORD *)(v81 + 72);
      v211 = v82;
      if ( !*(_DWORD *)(v82 + 8) )
      {
        v205 = *(int **)v82;
        v200 = 0;
        heightOfSelect(v5, &v200);
        v84 = v199;
        *((_DWORD *)a1 + 79) += v200;
        if ( (*(_DWORD *)(v199 + 96) & 0x1000) == 0 )
        {
          if ( (*(_DWORD *)(v81 + 28) & 0x200) == 0
            || (v130 = *(_QWORD *)(v81 + 56), *(_BYTE *)(v130 + 18)) && *(int *)v130 < 2 )
          {
            pushDownWhereTerms((_DWORD)a1, v83, *(_QWORD *)(v5 + 48), (_DWORD)v12, v202);
            v84 = v199;
          }
        }
        if ( (*(_DWORD *)(v84 + 96) & 0x4000000) == 0 )
          disableUnusedSubqueryResultColumns(v81);
        v85 = v202;
        v219 = a1[47];
        a1[47] = *(_QWORD *)v81;
        if ( (unsigned int)fromClauseTermCanBeCoroutine(a1, v12, v85, *(unsigned int *)(v5 + 4)) )
        {
          v86 = *(_DWORD *)(v7 + 144);
          v87 = ++*((_DWORD *)a1 + 15);
          v88 = Vdbe;
          *(_DWORD *)(v211 + 12) = v87;
          sqlite3VdbeAddOp3(v88, 11, v87, 0, v86 + 1);
          v89 = v211;
          *(_DWORD *)(v211 + 8) = v86 + 1;
          v90 = v89;
          DWORD1(v224) = *(_DWORD *)(v89 + 12);
          *((_QWORD *)&v224 + 1) = 0;
          *(_QWORD *)&v225[8] = 0;
          *(_DWORD *)v225 = 0;
          LOBYTE(v224) = 13;
          sqlite3VdbeExplain(a1, 1, "CO-ROUTINE %!S", v81);
          sqlite3Select(a1, v205, &v224);
          *(_WORD *)(*(_QWORD *)(v81 + 16) + 58LL) = *((_WORD *)v205 + 1);
          *(_DWORD *)(v81 + 28) |= 0x40u;
          v91 = *(_DWORD *)(v90 + 12);
          *(_DWORD *)(v90 + 16) = HIDWORD(v224);
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
               && (v131 = *(_QWORD *)(v81 + 56), v206 = v131, v132 = *(_DWORD *)(v131 + 4), v132 > 0) )
        {
          sqlite3VdbeAddOp3(v7, 10, *(_DWORD *)(v131 + 8), v132, 0);
          v133 = *(_DWORD *)(v81 + 32);
          v134 = v206;
          v135 = *(_DWORD *)(v206 + 12);
          if ( v133 != v135 )
            sqlite3VdbeAddOp3(v7, 114, v133, v135, 0);
          *((_WORD *)v205 + 1) = *(_WORD *)(v134 + 16);
        }
        else
        {
          v136 = isSelfJoinView(v12, v81, 0, v202);
          v206 = v136;
          if ( v136 )
          {
            v137 = *(_DWORD **)(v136 + 72);
            v138 = v137[2];
            if ( v138 )
            {
              sqlite3VdbeAddOp3(v7, 10, v137[3], v138, 0);
              v136 = v206;
            }
            sqlite3VdbeAddOp3(v7, 114, *(_DWORD *)(v81 + 32), *(_DWORD *)(v136 + 32), 0);
            *((_WORD *)v205 + 1) = *(_WORD *)(*(_QWORD *)v137 + 2LL);
          }
          else
          {
            v139 = ++*((_DWORD *)a1 + 15);
            v200 = 0;
            *(_DWORD *)(v82 + 12) = v139;
            v209 = sqlite3VdbeAddOp3(v7, 9, 0, 0, 0);
            v140 = v209 + 1;
            *(_DWORD *)(v82 + 8) = v209 + 1;
            *(_DWORD *)(v81 + 28) |= 0x20u;
            v13 = (*(_BYTE *)(v81 + 28) & 0x10) == 0;
            v201 = v140;
            if ( v13 )
              v200 = sqlite3VdbeAddOp3(v7, 15, 0, 0, 0);
            DWORD1(v224) = *(_DWORD *)(v81 + 32);
            LOBYTE(v224) = 12;
            *((_QWORD *)&v224 + 1) = 0;
            *(_QWORD *)&v225[8] = 0;
            *(_DWORD *)v225 = 0;
            sqlite3VdbeExplain(a1, 1, "MATERIALIZE %!S", v81);
            sqlite3Select(a1, v205, &v224);
            v141 = 0;
            *(_WORD *)(*(_QWORD *)(v81 + 16) + 58LL) = *((_WORD *)v205 + 1);
            if ( v200 )
              *(_DWORD *)(sqlite3VdbeGetOp(v7, v200) + 8) = *(_DWORD *)(v7 + 144);
            sqlite3VdbeAddOp3(v7, 67, *(_DWORD *)(v82 + 12), v201, v141);
            *(_DWORD *)(sqlite3VdbeGetOp(v7, v209) + 8) = *(_DWORD *)(v7 + 144);
            *((_BYTE *)a1 + 31) = 0;
            *((_DWORD *)a1 + 11) = 0;
            if ( (*(_DWORD *)(v81 + 28) & 0x210) == 0x200 )
            {
              v142 = *(_QWORD *)(v81 + 56);
              *(_DWORD *)(v142 + 4) = *(_DWORD *)(v82 + 8);
              *(_DWORD *)(v142 + 8) = *(_DWORD *)(v82 + 12);
              *(_DWORD *)(v142 + 12) = *(_DWORD *)(v81 + 32);
              *(_WORD *)(v142 + 16) = *((_WORD *)v205 + 1);
            }
          }
        }
        v11 = v199;
        if ( *(_BYTE *)(v199 + 103) )
          goto LABEL_39;
        v200 = 0;
        heightOfSelect(v5, &v200);
        v94 = v219;
        *((_DWORD *)a1 + 79) -= v200;
        a1[47] = v94;
      }
    }
  }
  v68 = *(_DWORD *)(v5 + 4);
  v69 = *(unsigned int **)(v5 + 32);
  v70 = *(int **)(v5 + 56);
  v213 = *(_QWORD *)(v5 + 48);
  v211 = *(_QWORD *)(v5 + 64);
  v210 = v69;
  v205 = v70;
  LOBYTE(v232) = v68 & 1;
  if ( (v68 & 9) == 1
    && !(unsigned int)sqlite3ExprListCompare(v221, v69, 0xFFFFFFFFLL)
    && (*(_BYTE *)(v199 + 96) & 4) == 0
    && !*(_QWORD *)(v5 + 112) )
  {
    *(_DWORD *)(v5 + 4) &= ~1u;
    v143 = (int *)sqlite3ExprListDup(v199, v69, 0);
    v205 = v143;
    v144 = v143;
    *(_QWORD *)(v5 + 56) = v143;
    if ( v143 )
    {
      v145 = 0;
      if ( *v143 > 0 )
      {
        do
        {
          v146 = ++v145;
          LOWORD(v144[8 * v146]) = v145;
        }
        while ( v145 < *v144 );
      }
    }
    *(_DWORD *)(v5 + 4) |= 8u;
    LOBYTE(v232) = 2;
  }
  if ( (_QWORD)v221 )
  {
    v97 = sqlite3KeyInfoFromExprList(a1, v221, 0, *v69);
    HIDWORD(v221) = *((_DWORD *)a1 + 14);
    v98 = HIDWORD(v221);
    *((_DWORD *)a1 + 14) = HIDWORD(v221) + 1;
    DWORD2(v222) = sqlite3VdbeAddOp4(v7, 117, v98, *v69 + *(_DWORD *)v221 + 1, 0, v97, -8);
  }
  else
  {
    DWORD2(v222) = -1;
  }
  if ( *(_BYTE *)v215 == 12 )
  {
    sqlite3VdbeAddOp3(v7, 117, *((_DWORD *)v215 + 1), *v69, 0);
    if ( (*(_DWORD *)(v5 + 4) & 0x800) != 0 )
    {
      v113 = *v69;
      for ( k = *v69 - 1; k > 0; --k )
      {
        v112 = v210;
        v147 = 8LL * (unsigned int)k;
        if ( (v210[v147 + 7] & 0x40) != 0 )
        {
          v69 = v210;
          break;
        }
        if ( *(_QWORD *)&v210[v147 + 2] )
        {
          sqlite3ExprDeleteNN(v199);
          v112 = v210;
        }
        sqlite3DbFree(v199, *(_QWORD *)&v112[v147 + 4]);
        v69 = v210;
        --*v210;
        v113 = *v69;
      }
      v115 = 0;
      if ( v113 > 0 )
      {
        do
        {
          v116 = 8LL * v115;
          if ( (v69[v116 + 7] & 0x40) == 0 )
            **(_BYTE **)&v69[v116 + 2] = 122;
          ++v115;
        }
        while ( v115 < (int)*v69 );
      }
    }
  }
  v71 = *((_DWORD *)a1 + 18) - 1;
  *((_DWORD *)a1 + 18) = v71;
  v13 = (*(_DWORD *)(v5 + 4) & 0x4000) == 0;
  v227 = v71;
  if ( v13 )
    *(_WORD *)(v5 + 2) = 320;
  if ( *(_QWORD *)(v5 + 96) )
    computeLimitRegisters((__int64)a1, v5, v71);
  if ( !*(_DWORD *)(v5 + 8) && (SDWORD2(v222) & 0x80000000) == 0 )
  {
    *(_BYTE *)sqlite3VdbeGetOp(v7, DWORD2(v222)) = 119;
    BYTE4(v223) |= 1u;
  }
  if ( (*(_BYTE *)(v5 + 4) & 1) != 0 )
  {
    HIDWORD(v232) = *((_DWORD *)a1 + 14);
    *((_DWORD *)a1 + 14) = HIDWORD(v232) + 1;
    v99 = sqlite3KeyInfoFromExprList(a1, *(_QWORD *)(v5 + 32), 0, 0);
    v100 = sqlite3VdbeAddOp3(Vdbe, 117, HIDWORD(v232), 0, 0);
    v101 = v99;
    v7 = Vdbe;
    v102 = v100;
    sqlite3VdbeChangeP4(Vdbe, v100, v101, 4294967288LL);
    v233 = v102;
    sqlite3VdbeChangeP5(v7, 8, v103, v104);
    BYTE1(v232) = 3;
  }
  else
  {
    BYTE1(v232) = 0;
  }
  v72 = v205;
  if ( v208 || v205 )
  {
    v217 = 0;
    memset(v231, 0, sizeof(v231));
    if ( v205 )
    {
      v105 = *(int **)(v5 + 32);
      v106 = *v105;
      v107 = v105 + 2;
      while ( v106 > 0 )
      {
        *((_WORD *)v107 + 13) = 0;
        v107 += 8;
        --v106;
      }
      v108 = *v72;
      v109 = v72 + 2;
      while ( v108 > 0 )
      {
        *((_WORD *)v109 + 13) = 0;
        v109 += 8;
        --v108;
      }
      if ( *(__int16 *)(v5 + 2) > 66 )
        *(_WORD *)(v5 + 2) = 66;
      if ( (_QWORD)v221 && *v72 == *(_DWORD *)v221 )
      {
        for ( m = 0; m < *v72; LOBYTE(v72[8 * v111 + 6]) = *(_BYTE *)(32 * v111 + v221 + 24) & 1 )
          v111 = m++;
        if ( !(unsigned int)sqlite3ExprListCompare(v72, v221, 0xFFFFFFFFLL) )
          v217 = 1;
      }
    }
    else
    {
      *(_WORD *)(v5 + 2) = 0;
    }
    v212 = *((_DWORD *)a1 + 18) - 1;
    *((_DWORD *)a1 + 18) = v212;
    v22 = sqlite3DbMallocZero(v199, 56);
    v23 = v22;
    if ( v22 )
      sqlite3ParserAddCleanup(a1, agginfoFree, v22);
    v11 = v199;
    if ( *(_BYTE *)(v199 + 103) )
      goto LABEL_39;
    *(_DWORD *)(v23 + 52) = *(_DWORD *)(v5 + 16);
    *(_QWORD *)v231 = a1;
    *(_QWORD *)&v231[8] = v12;
    *(_QWORD *)&v231[16] = v23;
    memset(&v231[24], 0, 32);
    if ( v72 )
      v26 = *v72;
    else
      LOWORD(v26) = 0;
    v27 = v210;
    *(_WORD *)(v23 + 2) = v26;
    *(_QWORD *)(v23 + 16) = v72;
    sqlite3ExprAnalyzeAggList(v231, v27);
    sqlite3ExprAnalyzeAggList(v231, v221);
    v28 = v211;
    if ( v211 )
    {
      if ( v72 )
      {
        v156 = *(_QWORD *)(v5 + 64);
        *((_QWORD *)&v224 + 1) = havingToWhereExprCb;
        memset(v225, 0, sizeof(v225));
        *(_QWORD *)&v224 = a1;
        v226 = v5;
        sqlite3WalkExpr(&v224, v156);
        v213 = *(_QWORD *)(v5 + 48);
        v28 = v211;
      }
      sqlite3ExprAnalyzeAggregates(v231, v28);
    }
    *(_DWORD *)(v23 + 36) = *(_DWORD *)(v23 + 32);
    if ( *(_QWORD *)(v5 + 56) || *(_QWORD *)(v5 + 64) || *(_DWORD *)(v23 + 48) != 1 )
      LOBYTE(TempRange) = 0;
    else
      LOBYTE(TempRange) = minMaxQuery(v199, **(_QWORD **)(v23 + 40), &v228);
    analyzeAggFuncArgs(v23, v231);
    v11 = v199;
    if ( *(_BYTE *)(v199 + 103) )
      goto LABEL_39;
    if ( !v72 )
    {
      v181 = isSimpleCount(v5, v23);
      v183 = v181;
      if ( v181 )
      {
        v184 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v181 + 96));
        v201 = v184;
        v186 = v185;
        v208 = *((_DWORD *)a1 + 14);
        v206 = v185;
        *((_DWORD *)a1 + 14) = v208 + 1;
        v209 = *(_DWORD *)(v183 + 40);
        sqlite3CodeVerifySchema(a1, v184);
        sqlite3TableLock(a1, v201, *(unsigned int *)(v183 + 40), 0, *(_QWORD *)v183);
        if ( *(char *)(v183 + 48) < 0 )
          v186 = sqlite3PrimaryKeyIndex(v183);
        if ( (*(_BYTE *)(*(_QWORD *)(v5 + 40) + 36LL) & 1) == 0 )
        {
          for ( n = *(_QWORD *)(v183 + 16); n; n = *(_QWORD *)(n + 40) )
          {
            if ( (*(_BYTE *)(n + 100) & 4) == 0 )
            {
              v188 = *(_WORD *)(n + 92);
              if ( v188 < *(__int16 *)(v183 + 60) && !*(_QWORD *)(n + 72) && (!v186 || v188 < *(__int16 *)(v186 + 92)) )
                v186 = n;
            }
          }
        }
        if ( v186 )
        {
          v209 = *(_DWORD *)(v186 + 88);
          v206 = sqlite3KeyInfoOfIndex(a1, v186);
        }
        sqlite3VdbeAddOp4Int(v7, 102, v208, v209, v201, 1);
        if ( v206 )
          sqlite3VdbeChangeP4(v7, 0xFFFFFFFFLL, v206, 4294967288LL);
        v189 = v208;
        *(_DWORD *)(v23 + 12) = *((_DWORD *)a1 + 15) + 1;
        *((_DWORD *)a1 + 15) += *(_DWORD *)(v23 + 32) + *(_DWORD *)(v23 + 48);
        sqlite3VdbeAddOp3(v7, 98, v189, *(_DWORD *)(v23 + 12) + *(_DWORD *)(v23 + 32), 0);
        sqlite3VdbeAddOp3(v7, 122, v208, 0, 0);
        explainSimpleCount(a1, v183, v186);
      }
      else
      {
        v190 = v182;
        v191 = *(_DWORD *)(v23 + 48);
        v206 = v182;
        v201 = v182;
        if ( *(_DWORD *)(v23 + 36) == (_DWORD)v182 )
        {
          if ( v191 == 1 )
          {
            v195 = *(_DWORD **)(v23 + 40);
            v191 = 1;
            if ( v195[4] >= (int)v182 )
            {
              v206 = *(_QWORD *)(*(_QWORD *)v195 + 32LL);
              LOWORD(v201) = v206 != 0 ? 0x500 : 0;
            }
          }
        }
        else
        {
          v192 = v182;
          if ( v191 <= 0 )
          {
LABEL_317:
            if ( v192 == v191 )
            {
              v190 = ++*((_DWORD *)a1 + 15);
              sqlite3VdbeAddOp3(v7, 71, 0, v190, v182);
              v191 = *(_DWORD *)(v23 + 48);
            }
          }
          else
          {
            v193 = *(_QWORD *)(v23 + 40);
            while ( 1 )
            {
              v194 = 32LL * v192;
              if ( (*(_DWORD *)(*(_QWORD *)(v194 + v193) + 4LL) & 0x1000000) == 0
                && (*(_BYTE *)(*(_QWORD *)(v194 + v193 + 8) + 4LL) & 0x20) != 0 )
              {
                break;
              }
              if ( (int)++v192 >= v191 )
                goto LABEL_317;
            }
          }
        }
        *(_DWORD *)(v23 + 12) = *((_DWORD *)a1 + 15) + 1;
        *((_DWORD *)a1 + 15) += v191 + *(_DWORD *)(v23 + 32);
        resetAccumulator(a1, v23);
        v196 = sqlite3WhereBegin(
                 (_DWORD)a1,
                 (_DWORD)v12,
                 v213,
                 (_DWORD)v228,
                 v206,
                 v5,
                 (unsigned __int16)v201 | (unsigned __int8)TempRange,
                 0);
        v197 = v196;
        if ( !v196 )
          goto LABEL_173;
        v218 = *(unsigned __int8 *)(v196 + 67);
        updateAccumulator(a1, v190, v23, v218);
        if ( v218 )
        {
          v198 = *(_QWORD *)(v23 + 40);
          if ( v198 )
            fixDistinctOpenEph((__int64)a1, v218, *(_DWORD *)(v198 + 16), *(_DWORD *)(v198 + 20));
        }
        if ( v190 )
          sqlite3VdbeAddOp3(v7, 71, 1, v190, 0);
        if ( (_BYTE)TempRange )
          sqlite3WhereMinMaxOptEarlyOut(v7, v197);
        sqlite3WhereEnd(v197);
        finalizeAggFunctions(a1, v23);
      }
      *(_QWORD *)&v221 = 0;
      sqlite3ExprIfFalse(a1, v211, v212, 16);
      v64 = (unsigned __int8 *)v215;
      selectInnerLoop((_DWORD)a1, v5, -1, 0, 0, (__int64)v215, v212, v212);
LABEL_77:
      v65 = v212;
LABEL_78:
      sqlite3VdbeResolveLabel(v7, v65);
      goto LABEL_108;
    }
    v219 = 0;
    v216 = 0;
    if ( *(_DWORD *)(v23 + 48) == 1 )
    {
      v157 = *(int **)(v23 + 40);
      if ( v157[4] >= 0 )
      {
        v158 = *(_QWORD *)v157;
        if ( v158 )
        {
          if ( (*(_DWORD *)(v158 + 4) & 0x1000) == 0 )
          {
            v159 = *(_QWORD *)(v158 + 32);
            if ( v159 )
            {
              v160 = sqlite3ExprDup(v199, *(_QWORD *)(v159 + 8), 0);
              v161 = sqlite3ExprListDup(v199, v205, 0);
              v162 = sqlite3ExprListAppend(a1, v161, v160);
              v72 = v205;
              v219 = v162;
              if ( v162 )
                LOWORD(v216) = 1280;
              else
                LOWORD(v216) = 0;
            }
          }
        }
      }
    }
    *(_DWORD *)(v23 + 4) = (*((_DWORD *)a1 + 14))++;
    v29 = sqlite3KeyInfoFromExprList(a1, v72, 0, *(unsigned int *)(v23 + 32));
    v30 = *(unsigned __int16 *)(v23 + 2);
    v31 = *(_DWORD *)(v23 + 4);
    v230 = v29;
    v32 = sqlite3VdbeAddOp4(v7, 119, v31, v30, 0, v29, -8);
    v33 = *((_DWORD *)a1 + 18);
    v218 = v32;
    v209 = *((_DWORD *)a1 + 15) + 1;
    v202 = v33 - 1;
    v34 = v209 + 1;
    v208 = v209 + 1;
    v35 = v209 + 3;
    v203 = v209 + 2;
    *((_DWORD *)a1 + 15) = v209 + 3;
    *((_DWORD *)a1 + 18) = v33 - 2;
    v36 = v35 + *v72;
    *((_DWORD *)a1 + 15) = v36;
    v201 = v36;
    *((_DWORD *)a1 + 15) = *v72 + v36;
    sqlite3VdbeAddOp3(v7, 71, 0, v34, 0);
    sqlite3VdbeAddOp3(v7, 75, 0, v203 + 2, v203 + 1 + *v72);
    sqlite3VdbeAddOp3(v7, 10, v203 + 1, v202 - 1, 0);
    v37 = 128;
    if ( (_BYTE)v232 != 2 )
      v37 = 64;
    v38 = sqlite3WhereBegin(
            (_DWORD)a1,
            (_DWORD)v12,
            v213,
            (_DWORD)v72,
            v219,
            v5,
            v37 | (unsigned __int16)(v216 | ((_WORD)v217 << 9)),
            0);
    v42 = 0;
    v206 = v38;
    v43 = v38;
    if ( !v38 )
    {
      sqlite3ExprListDeleteGeneric(v199, v219);
      goto LABEL_173;
    }
    v220 = v201 + 1;
    if ( a1[12] )
    {
      optimizeAggregateUseOfIndexedExpr(v40, v5, v23, v231);
      v42 = 0;
    }
    v44 = 0;
    *(_DWORD *)(v23 + 12) = *((_DWORD *)a1 + 15) + 1;
    *((_DWORD *)a1 + 15) += *(_DWORD *)(v23 + 32) + *(_DWORD *)(v23 + 48);
    v45 = *(char *)(v43 + 65) < 0;
    v201 = *(unsigned __int8 *)(v43 + 67);
    if ( !v45 )
      v44 = *(char *)(v43 + 65);
    if ( v44 == *v72 )
    {
      v200 = 0;
      v46 = 0;
      v207 = 0;
    }
    else
    {
      if ( !(_BYTE)v232 || (v163 = "DISTINCT", (*(_BYTE *)(v5 + 4) & 1) != 0) )
        v163 = "GROUP BY";
      sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v163);
      v164 = *v72;
      v165 = v164;
      v207 = 1;
      v200 = v164;
      if ( *(int *)(v23 + 32) > 0 )
      {
        v166 = 0;
        v167 = v164;
        do
        {
          v168 = *(__int16 *)(*(_QWORD *)(v23 + 24) + 24LL * v166 + 22);
          v169 = v165 + 1;
          if ( v168 < v167 )
            v169 = v165;
          ++v166;
          v165 = v169;
          v170 = v167 + 1;
          if ( v168 < v167 )
            v170 = v167;
          v167 = v170;
        }
        while ( (signed int)v166 < *(_DWORD *)(v23 + 32) );
      }
      TempRange = sqlite3GetTempRange(a1, v165);
      sqlite3ExprCodeExprList((_DWORD)a1, (_DWORD)v72, TempRange, 0, v171);
      *(_BYTE *)v23 = 1;
      if ( *(int *)(v23 + 32) > 0 )
      {
        v172 = v200;
        v173 = 0;
        v174 = TempRange;
        do
        {
          v175 = *(_QWORD *)(v23 + 24);
          if ( *(__int16 *)(v175 + 24LL * v173 + 22) >= v172 )
          {
            sqlite3ExprCode(a1, *(_QWORD *)(v175 + 24LL * v173 + 8), v172 + v174);
            ++v172;
          }
          ++v173;
        }
        while ( v173 < *(_DWORD *)(v23 + 32) );
        v5 = v229;
        v7 = Vdbe;
      }
      *(_BYTE *)v23 = 0;
      TempReg = sqlite3GetTempReg(a1);
      sqlite3VdbeAddOp3(v7, 97, TempRange, v165, TempReg);
      sqlite3VdbeAddOp3(v7, 139, *(_DWORD *)(v23 + 4), TempReg, 0);
      sqlite3ReleaseTempReg(a1, TempReg);
      sqlite3ReleaseTempRange(v177, TempRange, v165, v178);
      sqlite3WhereEnd(v206);
      v179 = *((_DWORD *)a1 + 14);
      *(_DWORD *)(v23 + 8) = v179;
      ++*((_DWORD *)a1 + 14);
      v200 = v179;
      LODWORD(v213) = sqlite3GetTempReg(a1);
      sqlite3VdbeAddOp3(v7, 121, v180, v213, v165);
      sqlite3VdbeAddOp3(v7, 34, *(_DWORD *)(v23 + 4), v212, 0);
      v72 = v205;
      v42 = 0;
      v46 = v213;
      *(_BYTE *)(v23 + 1) = 1;
    }
    if ( a1[12] )
    {
      aggregateConvertIndexedExprRefToColumn(v23, v39, v41, 0);
      v42 = 0;
    }
    if ( v217 )
    {
      v47 = v207;
      if ( (*(_BYTE *)(v199 + 96) & 4) != 0 || !v207 && (*(_BYTE *)(v206 + 68) & 8) == 0 )
        goto LABEL_65;
      *(_QWORD *)&v221 = 0;
      sqlite3VdbeChangeToNoop(v7, DWORD2(v222));
      v42 = 0;
    }
    v47 = v207;
LABEL_65:
    LODWORD(v213) = *(_DWORD *)(v7 + 144);
    if ( v47 )
    {
      sqlite3VdbeAddOp3(v7, 133, *(_DWORD *)(v23 + 4), v46, v200);
      v42 = 0;
    }
    for ( ii = 0; ii < *v72; ++ii )
    {
      v49 = ii + v220;
      v50 = 8LL * ii;
      LOWORD(TempRange) = v72[v50 + 8];
      if ( v207 == v42 )
      {
        *(_BYTE *)v23 = 1;
        sqlite3ExprCode(a1, *(_QWORD *)&v72[v50 + 2], v49);
      }
      else
      {
        sqlite3VdbeAddOp3(v7, 94, v200, ii, v49);
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
            sqlite3ExprToRegister(v52, ii + v203 + 2);
        }
      }
    }
    v53 = sqlite3KeyInfoRef(v230);
    sqlite3VdbeAddOp4(v7, 90, v203 + 2, v220, v54, v53, -8);
    v55 = *(_DWORD *)(v7 + 144);
    sqlite3VdbeAddOp3(v7, 14, v55 + 1, 0, v55 + 1);
    sqlite3VdbeAddOp3(v7, 10, v203, v202, 0);
    sqlite3VdbeAddOp3(a1[2], 79, v220, v203 + 2, *v205);
    v56 = v212;
    sqlite3VdbeAddOp3(v7, 50, v208, v212, 0);
    sqlite3VdbeAddOp3(v7, 10, v203 + 1, v202 - 1, 0);
    Op = sqlite3VdbeGetOp(v7, v55);
    v58 = v201;
    v59 = v209;
    *(_DWORD *)(Op + 8) = *(_DWORD *)(v7 + 144);
    updateAccumulator(a1, v59, v23, v58);
    sqlite3VdbeAddOp3(v7, 71, 1, v209, 0);
    if ( v207 )
    {
      sqlite3VdbeAddOp3(v7, 37, *(_DWORD *)(v23 + 4), v213, 0);
    }
    else
    {
      sqlite3WhereEnd(v206);
      sqlite3VdbeChangeToNoop(v7, v218);
    }
    sqlite3ExprListDeleteGeneric(v199, v219);
    sqlite3VdbeAddOp3(v7, 10, v203, v202, 0);
    sqlite3VdbeAddOp3(v7, 9, 0, v56, 0);
    v60 = Vdbe;
    v61 = *(_DWORD *)(v7 + 144);
    sqlite3VdbeAddOp3(Vdbe, 71, 1, v208, 0);
    sqlite3VdbeAddOp3(v60, 67, v203, 0, 0);
    sqlite3VdbeResolveLabel(v60, v202);
    v62 = *(_DWORD *)(v60 + 144);
    sqlite3VdbeAddOp3(v60, 50, v209, v62 + 2, 0);
    sqlite3VdbeAddOp3(v60, 67, v203, 0, 0);
    finalizeAggFunctions(a1, v23);
    sqlite3ExprIfFalse(a1, v211, (unsigned int)++v62, 16);
    selectInnerLoop((_DWORD)a1, v5, -1, (unsigned int)&v221, (__int64)&v232, (__int64)v215, v62, v61);
    v7 = Vdbe;
    v63 = v203;
    sqlite3VdbeAddOp3(Vdbe, 67, v203, 0, 0);
    sqlite3VdbeResolveLabel(v7, v202 - 1);
    resetAccumulator(a1, v23);
    sqlite3VdbeAddOp3(v7, 71, 0, v209, 0);
    sqlite3VdbeAddOp3(v7, 67, v63 + 1, 0, 0);
    if ( (_WORD)v216 && v201 )
      fixDistinctOpenEph(
        (__int64)a1,
        v201,
        *(_DWORD *)(*(_QWORD *)(v23 + 40) + 16LL),
        *(_DWORD *)(*(_QWORD *)(v23 + 40) + 20LL));
    v64 = (unsigned __int8 *)v215;
    goto LABEL_77;
  }
  v73 = 256;
  if ( !(_BYTE)v232 )
    v73 = 0;
  v74 = *(_QWORD *)(v5 + 112);
  v75 = v73 | *(_WORD *)(v5 + 4) & 0x4000;
  if ( v74 )
    sqlite3WindowCodeInit(a1, v5);
  v76 = sqlite3WhereBegin((_DWORD)a1, (_DWORD)v12, v213, v221, *(_QWORD *)(v5 + 32), v5, v75, *(__int16 *)(v5 + 2));
  v206 = v76;
  v77 = v76;
  if ( !v76 )
  {
LABEL_173:
    v11 = v199;
    goto LABEL_39;
  }
  v78 = *(_WORD *)(v76 + 74);
  if ( v78 < *(__int16 *)(v5 + 2) )
    *(_WORD *)(v5 + 2) = v78;
  if ( (_BYTE)v232 )
  {
    v96 = BYTE1(v232);
    if ( *(_BYTE *)(v77 + 67) )
      v96 = *(_BYTE *)(v77 + 67);
    BYTE1(v232) = v96;
  }
  v79 = v221;
  if ( (_QWORD)v221 )
  {
    v148 = 0;
    if ( *(char *)(v77 + 65) >= 0 )
      v148 = *(char *)(v77 + 65);
    DWORD2(v221) = v148;
    if ( (*(_BYTE *)(v77 + 68) & 4) == 0
      || (v149 = 112LL * *(unsigned __int8 *)(v77 + 64), *(_QWORD *)(v149 + v77 + 808)) )
    {
      v150 = *(_DWORD *)(v77 + 48);
    }
    else
    {
      v150 = *(_DWORD *)(v149 + v77 + 768);
    }
    LODWORD(v223) = v150;
    if ( v148 == *(_DWORD *)v221 )
      v79 = 0;
    *(_QWORD *)&v221 = v79;
  }
  if ( (SDWORD2(v222) & 0x80000000) == 0 && !v79 )
  {
    sqlite3VdbeChangeToNoop(v7, DWORD2(v222));
    v77 = v206;
  }
  if ( v74 )
  {
    v151 = *((_DWORD *)a1 + 18);
    ++*((_DWORD *)a1 + 15);
    --v151;
    v152 = *((_DWORD *)a1 + 15);
    v153 = v151 - 1;
    v154 = v151 - 2;
    *((_DWORD *)a1 + 18) = v151 - 2;
    sqlite3WindowCodeStep((_DWORD)a1, v5, v77, v152, v151);
    sqlite3VdbeAddOp3(Vdbe, 9, 0, v151 - 2, 0);
    sqlite3VdbeResolveLabel(Vdbe, v151);
    v64 = (unsigned __int8 *)v215;
    LODWORD(v223) = 0;
    selectInnerLoop((_DWORD)a1, v5, -1, (unsigned int)&v221, (__int64)&v232, (__int64)v215, v153, v154);
    v155 = v153;
    v7 = Vdbe;
    sqlite3VdbeResolveLabel(Vdbe, v155);
    sqlite3VdbeAddOp3(v7, 67, v152, 0, 0);
    v65 = v154;
    goto LABEL_78;
  }
  v64 = (unsigned __int8 *)v215;
  selectInnerLoop(
    (_DWORD)a1,
    v5,
    -1,
    (unsigned int)&v221,
    (__int64)&v232,
    (__int64)v215,
    *(_DWORD *)(v77 + 48),
    *(_DWORD *)(v77 + 52));
  sqlite3WhereEnd(v206);
LABEL_108:
  if ( BYTE1(v232) == 3 )
    sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
  if ( (_QWORD)v221 )
    generateSortTail((__int64)a1, v5, (__int64)&v221, *v210, v64);
  sqlite3VdbeResolveLabel(v7, v227);
  v8 = *((_DWORD *)a1 + 13) > 0;
LABEL_113:
  v11 = v199;
LABEL_39:
  if ( v228 )
    exprListDeleteNN(v11, v228);
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
