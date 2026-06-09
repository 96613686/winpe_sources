# sqlite3Select

- ea: `0x18008b73c`
- end: `0x18008d656`
- name: `sqlite3Select`
- size: `7962`
- prototype: ``
- caller_count: `13`
- callee_count: `63`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003e7e0`
- `0x18004a08c`
- `0x1800572e4`
- `0x180057b50`
- `0x18006e2c8`
- `0x18006ea40`
- `0x180073228`
- `0x18007e280`
- `0x180080f0c`
- `0x180081308`
- `0x18008b73c`
- `0x1800b274c`
- `0x1800c3bd8`

## callees

- `0x180002250`
- `0x1800366ac`
- `0x18003f548`
- `0x180040c2c`
- `0x180042a98`
- `0x180045428`
- `0x180045b1c`
- `0x180046b2c`
- `0x180047330`
- `0x1800485f4`
- `0x180049a84`
- `0x18004b478`
- `0x18004cfe4`
- `0x1800572e4`
- `0x18005e1f0`
- `0x18005e584`
- `0x1800622a0`
- `0x180064550`
- `0x18006554c`
- `0x1800693b0`
- `0x18006ed2c`
- `0x1800716fc`
- `0x1800718ac`
- `0x180073aec`
- `0x180074208`
- `0x18007424c`
- `0x1800745bc`
- `0x1800746dc`
- `0x1800747b8`
- `0x180076d6c`
- `0x180077020`
- `0x1800777c8`
- `0x180077a60`
- `0x180077cf8`
- `0x180077d9c`
- `0x18007a97c`
- `0x18007ca28`
- `0x18007d478`
- `0x18007fcc4`
- `0x18007fd5c`
- `0x180084298`
- `0x180089d98`
- `0x18008b73c`
- `0x18008da8c`
- `0x18008ed60`
- `0x18008f3d8`
- `0x1800923d8`
- `0x1800924d4`
- `0x1800927e0`
- `0x180092870`

## string_xrefs

- `0x18008cb22`: `USE TEMP B-TREE FOR %s`
- `0x18008d403`: `USE TEMP B-TREE FOR %s`

## pseudocode

```c
__int64 __fastcall sqlite3Select(_QWORD *a1, __int64 a2, __int128 *a3)
{
  __int64 v4; // r13
  int v6; // esi
  __int64 v7; // rdi
  BOOL v8; // r12d
  __int64 v9; // r8
  int v10; // ebx
  __int64 v11; // rsi
  const char *v12; // r8
  __int64 v14; // r8
  signed int *v15; // r14
  char v16; // r11
  bool v17; // zf
  BOOL v18; // eax
  __int64 v19; // r9
  __int64 v20; // rbx
  int *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  char v24; // al
  __int64 v25; // rdx
  __int64 ii; // r9
  __int64 v27; // rdx
  unsigned __int8 v28; // al
  unsigned int v29; // edx
  __int64 v30; // rcx
  int v31; // ecx
  unsigned int v32; // r9d
  _BYTE *v33; // rax
  __int64 v34; // rsi
  signed int v35; // r11d
  __int64 v36; // rsi
  unsigned int *v37; // rbx
  int v38; // r11d
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  unsigned int v42; // edi
  unsigned int v43; // r8d
  int v44; // ecx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  unsigned int v50; // ecx
  unsigned int *v51; // rax
  _DWORD *v52; // rax
  int v53; // r9d
  _DWORD *v54; // rbx
  _DWORD *v55; // rax
  int v56; // r9d
  unsigned int v57; // eax
  _BYTE *v58; // rax
  int v59; // r10d
  __int64 v60; // rcx
  int *v61; // rcx
  int *v62; // rbx
  _DWORD *v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  int v66; // r8d
  __int64 v67; // rdi
  unsigned int v68; // eax
  __int64 v69; // r8
  unsigned int v70; // ebx
  int v71; // eax
  int i; // esi
  int *v73; // rcx
  __int64 v74; // rbx
  __int64 v75; // rdx
  signed int v76; // ecx
  __int64 v77; // rax
  unsigned int v78; // eax
  __int64 *v79; // rax
  __int64 v80; // rdi
  unsigned int v81; // eax
  __int64 v82; // r8
  unsigned int v83; // ebx
  __int64 v84; // rax
  int *v85; // rbx
  __int16 v86; // ax
  __int64 v87; // rsi
  __int16 v88; // bx
  __int64 v89; // rax
  __int64 v90; // rdx
  __int16 v91; // ax
  char v92; // al
  __int64 v93; // rcx
  int v94; // r8d
  __int64 v95; // rax
  int v96; // eax
  unsigned int v97; // ebx
  int v98; // esi
  unsigned int v99; // edi
  unsigned int v100; // r14d
  __int64 v101; // r12
  __int128 *v102; // rbx
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r14
  int *v106; // rax
  int v107; // ecx
  _DWORD *v108; // rdx
  int v109; // ecx
  _DWORD *v110; // rdx
  int j; // r8d
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rsi
  int v116; // eax
  int *v117; // rdx
  _DWORD *v118; // rcx
  __int64 v119; // r8
  __int64 v120; // rdx
  __int64 *v121; // rax
  __int64 v122; // rcx
  _DWORD *v123; // r11
  __int64 v124; // r11
  __int64 v125; // r11
  __int64 v126; // r10
  int *v127; // rax
  __int64 v128; // rax
  __int64 v129; // rcx
  __int64 v130; // rdx
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int16 v134; // cx
  _DWORD *v135; // rax
  int v136; // r9d
  int v137; // r8d
  int v138; // r8d
  unsigned int v139; // edx
  unsigned int v140; // ecx
  int v141; // eax
  unsigned int v142; // ecx
  __int16 v143; // dx
  __int64 v144; // r8
  __int64 v145; // r14
  int v146; // r9d
  int v147; // edx
  int k; // r8d
  int v149; // eax
  int v150; // ecx
  bool v151; // sf
  const char *v152; // r9
  int v153; // r14d
  unsigned int v154; // r8d
  unsigned int v155; // r10d
  int v156; // r9d
  int v157; // edx
  unsigned int v158; // eax
  int v159; // eax
  unsigned int v160; // r13d
  int v161; // edi
  __int64 v162; // rcx
  char v163; // al
  int v164; // r14d
  unsigned __int8 v165; // al
  unsigned int v166; // r14d
  unsigned int v167; // ecx
  char v168; // al
  int v169; // eax
  unsigned __int8 v170; // al
  int v171; // r14d
  __int64 v172; // rdx
  unsigned int v173; // eax
  int v174; // r14d
  unsigned int v175; // r13d
  __int64 v176; // r8
  _DWORD *v177; // r14
  unsigned int v178; // eax
  unsigned int v179; // ebx
  unsigned int v180; // r14d
  int v181; // edi
  unsigned int v182; // r12d
  int v183; // ebx
  __int64 v184; // rdx
  __int64 v185; // rdi
  _QWORD *v186; // rdi
  __int64 v187; // rdx
  __int64 v188; // rcx
  int v189; // r14d
  __int64 v190; // rdx
  __int64 m; // rbx
  __int64 n; // rax
  __int16 v193; // cx
  unsigned int v194; // r8d
  const wchar_t *v195; // rcx
  const char *v196; // rax
  unsigned int v197; // edi
  int v198; // ecx
  __int16 v199; // bx
  unsigned int v200; // edx
  __int64 v201; // r9
  __int64 v202; // r8
  int *v203; // rax
  __int64 v204; // rax
  __int64 v205; // rbx
  unsigned int v206; // r14d
  __int64 v207; // r8
  unsigned int v208; // ecx
  __int64 v209; // r9
  int v210; // r9d
  int v211; // [rsp+20h] [rbp-E0h]
  int v212; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v213; // [rsp+40h] [rbp-C0h]
  unsigned int v214; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v215; // [rsp+48h] [rbp-B8h]
  unsigned int v216; // [rsp+4Ch] [rbp-B4h]
  __int64 v217; // [rsp+50h] [rbp-B0h]
  char v218; // [rsp+58h] [rbp-A8h]
  __int64 v219; // [rsp+60h] [rbp-A0h]
  unsigned int v220; // [rsp+68h] [rbp-98h]
  unsigned int TempRange; // [rsp+6Ch] [rbp-94h]
  __int64 Vdbe; // [rsp+70h] [rbp-90h]
  int *v223; // [rsp+78h] [rbp-88h]
  _DWORD *v224; // [rsp+80h] [rbp-80h]
  unsigned int v225; // [rsp+88h] [rbp-78h]
  unsigned int v226; // [rsp+8Ch] [rbp-74h]
  unsigned int v227; // [rsp+90h] [rbp-70h]
  int v228; // [rsp+94h] [rbp-6Ch]
  unsigned int v229; // [rsp+98h] [rbp-68h]
  __int64 v230; // [rsp+A0h] [rbp-60h]
  int v231; // [rsp+A8h] [rbp-58h]
  __int64 v232; // [rsp+B0h] [rbp-50h]
  __int64 v233; // [rsp+B8h] [rbp-48h]
  _DWORD *v234; // [rsp+C0h] [rbp-40h]
  int v235; // [rsp+C8h] [rbp-38h]
  __int128 *v236; // [rsp+D0h] [rbp-30h]
  __int128 v237; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v238; // [rsp+E8h] [rbp-18h]
  __int128 v239; // [rsp+F8h] [rbp-8h]
  __int128 v240; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v241[2]; // [rsp+118h] [rbp+18h] BYREF
  int *v242; // [rsp+138h] [rbp+38h]
  __int64 v243; // [rsp+140h] [rbp+40h]
  unsigned int v244; // [rsp+148h] [rbp+48h]
  __int64 v245; // [rsp+150h] [rbp+50h]
  _BYTE v246[56]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v247; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v248; // [rsp+198h] [rbp+98h]

  v236 = a3;
  v247 = 0;
  v248 = 0;
  v4 = a2;
  v217 = *a1;
  v245 = a2;
  v237 = 0;
  v238 = 0;
  v239 = 0;
  v6 = 0;
  Vdbe = sqlite3GetVdbe(a1);
  v7 = Vdbe;
  if ( !v4 || *((_DWORD *)a1 + 12) || (unsigned int)sqlite3AuthCheck((_DWORD)a1, 21, 0, 0, 0) )
    return 1;
  v8 = 1;
  if ( *(_BYTE *)a3 <= 6u )
  {
    v9 = *(_QWORD *)(v4 + 72);
    if ( v9 )
    {
      sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v9);
      *(_QWORD *)(v4 + 72) = 0;
    }
    *(_DWORD *)(v4 + 4) &= ~1u;
    *(_DWORD *)(v4 + 4) |= 0x400000u;
  }
  sqlite3SelectPrep(a1, v4, 0);
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_14;
  v10 = *(_DWORD *)(v4 + 4);
  if ( (v10 & 0x800000) != 0 )
  {
    v11 = *(_QWORD *)(v4 + 40) + 8LL;
    if ( (unsigned int)sameSrcAlias(v11) )
    {
      v12 = *(const char **)(v11 + 24);
      if ( !v12 )
        v12 = **(const char ***)(v11 + 32);
      sqlite3ErrorMsg(a1, "target object/alias may not appear in FROM clause: %s", v12);
      goto LABEL_14;
    }
    *(_DWORD *)(v4 + 4) = v10 & 0xFF7FFFFF;
    v6 = 0;
  }
  if ( *(_BYTE *)a3 == 9 )
    sqlite3GenerateColumnNames(a1, v4);
  if ( (unsigned int)sqlite3WindowRewrite(a1, v4) )
  {
LABEL_14:
    sqlite3VdbeExplainPop(a1);
    return v8;
  }
  else
  {
    v15 = *(signed int **)(v4 + 40);
    v16 = 8;
    v17 = (*(_DWORD *)(v4 + 4) & 8) == 0;
    v228 = *(_DWORD *)(v4 + 4) & 8;
    v18 = !v17;
    v17 = *(_QWORD *)(v4 + 80) == 0;
    v216 = v18;
    v237 = *(unsigned __int64 *)(v4 + 72);
    v238 = 0;
    v239 = 0;
    if ( v17 )
    {
      v19 = v217;
      do
      {
        if ( v6 >= *v15 )
        {
          v33 = *(_BYTE **)(v4 + 48);
          if ( v33 && *v33 == 44 && (*(_DWORD *)(v19 + 96) & 0x8000) == 0 )
            propagateConstants(a1, v4);
          v34 = v217;
          if ( (*(_DWORD *)(v217 + 96) & 0x201) == 0 && (unsigned int)countOfViewOptimization(a1, v4, v14, v19) )
          {
            if ( !*(_BYTE *)(v217 + 103) )
            {
              v15 = *(signed int **)(v4 + 40);
              goto LABEL_78;
            }
            goto LABEL_14;
          }
LABEL_78:
          v35 = 0;
          v215 = 0;
          if ( *v15 > 0 )
          {
            while ( 2 )
            {
              v36 = 26LL * v35;
              memset(v241, 0, 21);
              v240 = 0;
              v37 = (unsigned int *)&v15[v36 + 2];
              if ( !*(_QWORD *)&v15[v36 + 22] )
              {
                v14 = *((_QWORD *)v37 + 2);
                if ( v14 )
                {
                  sqlite3AuthCheck((_DWORD)a1, 20, v14, (unsigned int)&Src, *((_QWORD *)v37 + 1));
                  v35 = v215;
                }
              }
              v219 = *((_QWORD *)v37 + 5);
              if ( !v219 || v37[12] )
              {
                v34 = v217;
              }
              else
              {
                v214 = 0;
                heightOfSelect(v4, &v214, v14, v19);
                v39 = v217;
                *((_DWORD *)a1 + 79) += v214;
                if ( (*(_DWORD *)(v39 + 96) & 0x1000) == 0 )
                {
                  if ( (v37[16] & 0x100) == 0 || (v40 = *((_QWORD *)v37 + 12), *(_BYTE *)(v40 + 18)) && *(int *)v40 < 2 )
                  {
                    pushDownWhereTerms((_DWORD)a1, v219, *(_QWORD *)(v4 + 48), (_DWORD)v15, v38);
                    v39 = v217;
                  }
                }
                if ( (*(_DWORD *)(v39 + 96) & 0x4000000) == 0 )
                  disableUnusedSubqueryResultColumns(&v15[v36 + 2]);
                v230 = a1[47];
                a1[47] = *((_QWORD *)v37 + 2);
                v234 = v37 + 16;
                v216 = v37[16] & 0x100;
                if ( v216 )
                {
                  v41 = *((_QWORD *)v37 + 12);
                  if ( !*(_BYTE *)(v41 + 18) || *(int *)v41 >= 2 && *(_BYTE *)(v41 + 18) != 2 )
                    goto LABEL_109;
                }
                if ( (v15[17] & 0x40) != 0
                  || (*(_DWORD *)(*a1 + 96LL) & 0x2000000) != 0
                  || isSelfJoinView(v15, &v15[v36 + 2], v215 + 1, (unsigned int)*v15) )
                {
                  goto LABEL_108;
                }
                if ( v215 )
                {
                  if ( (*(_DWORD *)(v4 + 4) & 0x10000000) != 0 )
                    goto LABEL_108;
                  v50 = v215;
                  v51 = (unsigned int *)&v15[v36 + 2];
                  if ( (v37[15] & 0x22) != 0 )
                    goto LABEL_108;
                  while ( v50 )
                  {
                    v51 -= 26;
                    if ( !*((_QWORD *)v51 + 5) )
                    {
                      --v50;
                      if ( (v51[15] & 0x22) == 0 )
                        continue;
                    }
                    goto LABEL_108;
                  }
LABEL_102:
                  v42 = *(_DWORD *)(v7 + 144);
                  v43 = ++*((_DWORD *)a1 + 14);
                  v44 = Vdbe;
                  v15[v36 + 15] = v43;
                  sqlite3VdbeAddOp3(v44, 11, v43, 0, v42 + 1);
                  DWORD1(v240) = v15[v36 + 15];
                  LOBYTE(v240) = 13;
                  *((_QWORD *)&v240 + 1) = 0;
                  *((_QWORD *)&v241[0] + 1) = 0;
                  v15[v36 + 14] = v42 + 1;
                  LODWORD(v241[0]) = 0;
                  sqlite3VdbeExplain(a1, 1, "CO-ROUTINE %!S");
                  sqlite3Select(a1, v219, &v240);
                  *(_WORD *)(*(_QWORD *)&v15[v36 + 10] + 58LL) = *(_WORD *)(v219 + 2);
                  v45 = (unsigned int)v15[v36 + 15];
                  v46 = Vdbe;
                  *v234 |= 0x20u;
                  v15[v36 + 16] = HIDWORD(v240);
                  sqlite3VdbeEndCoroutine(v46, v45);
                  v47 = v42;
                  v7 = Vdbe;
                  sqlite3VdbeJumpHere(Vdbe, v47);
                  *((_BYTE *)a1 + 31) = 0;
                  *((_DWORD *)a1 + 10) = 0;
                }
                else
                {
                  if ( *v15 == 1 || (v15[43] & 2) != 0 || (*(_DWORD *)(v4 + 4) & 0x10000000) == 0 )
                    goto LABEL_102;
LABEL_108:
                  if ( v216 )
                  {
LABEL_109:
                    v52 = *(_DWORD **)&v15[v36 + 26];
                    v224 = v52;
                    v53 = v52[1];
                    if ( v53 > 0 )
                    {
                      sqlite3VdbeAddOp3(v7, 10, v52[2], v53, 0);
                      v54 = v224;
                      v48 = (unsigned int)v15[v36 + 19];
                      v49 = (unsigned int)v224[3];
                      if ( (_DWORD)v48 != (_DWORD)v49 )
                        sqlite3VdbeAddOp3(v7, 115, v48, v49, 0);
                      *(_WORD *)(v219 + 2) = *((_WORD *)v54 + 8);
                      goto LABEL_123;
                    }
                  }
                  v55 = (_DWORD *)isSelfJoinView(v15, &v15[v36 + 2], 0, v215);
                  v232 = (__int64)v55;
                  if ( v55 )
                  {
                    v56 = v55[12];
                    if ( v56 )
                    {
                      sqlite3VdbeAddOp3(v7, 10, v55[13], v56, 0);
                      v55 = (_DWORD *)v232;
                    }
                    sqlite3VdbeAddOp3(v7, 115, v15[v36 + 19], v55[17], 0);
                    *(_WORD *)(v219 + 2) = *(_WORD *)(*(_QWORD *)(v232 + 40) + 2LL);
                  }
                  else
                  {
                    v57 = ++*((_DWORD *)a1 + 14);
                    v214 = 0;
                    v15[v36 + 15] = v57;
                    v229 = sqlite3VdbeAddOp3(v7, 9, 0, 0, 0);
                    v216 = v229 + 1;
                    v37[12] = v229 + 1;
                    v58 = v234;
                    *v234 |= 0x10u;
                    if ( (*v58 & 8) == 0 )
                      v214 = sqlite3VdbeAddOp3(v7, 15, 0, 0, 0);
                    DWORD1(v240) = v15[v36 + 19];
                    LOBYTE(v240) = 12;
                    *((_QWORD *)&v240 + 1) = 0;
                    *((_QWORD *)&v241[0] + 1) = 0;
                    LODWORD(v241[0]) = 0;
                    sqlite3VdbeExplain(a1, 1, "MATERIALIZE %!S", &v15[v36 + 2]);
                    sqlite3Select(a1, v219, &v240);
                    v59 = 0;
                    *(_WORD *)(*(_QWORD *)&v15[v36 + 10] + 58LL) = *(_WORD *)(v219 + 2);
                    if ( v214 )
                      sqlite3VdbeJumpHere(v7, v214);
                    sqlite3VdbeAddOp3(v7, 67, v15[v36 + 15], v216, v59);
                    sqlite3VdbeJumpHere(v7, v229);
                    *((_BYTE *)a1 + 31) = 0;
                    *((_DWORD *)a1 + 10) = 0;
                    if ( (*v234 & 0x108) == 0x100 )
                    {
                      v60 = *(_QWORD *)&v15[v36 + 26];
                      *(_DWORD *)(v60 + 4) = v37[12];
                      *(_DWORD *)(v60 + 8) = v15[v36 + 15];
                      *(_DWORD *)(v60 + 12) = v15[v36 + 19];
                      *(_WORD *)(v60 + 16) = *(_WORD *)(v219 + 2);
                    }
                  }
                }
LABEL_123:
                v34 = v217;
                if ( *(_BYTE *)(v217 + 103) )
                  goto LABEL_14;
                v214 = 0;
                heightOfSelect(v4, &v214, v48, v49);
                *((_DWORD *)a1 + 79) -= v214;
                v35 = v215;
                a1[47] = v230;
              }
              v215 = ++v35;
              if ( v35 >= *v15 )
                break;
              continue;
            }
          }
          v61 = *(int **)(v4 + 56);
          v62 = *(int **)(v4 + 32);
          v233 = *(_QWORD *)(v4 + 48);
          v63 = *(_DWORD **)(v4 + 64);
          v242 = v61;
          LODWORD(v61) = *(_DWORD *)(v4 + 4);
          v234 = v63;
          v232 = 0;
          v223 = v62;
          LOBYTE(v247) = (unsigned __int8)v61 & 1;
          if ( ((unsigned __int8)v61 & 9) == 1
            && !(unsigned int)sqlite3ExprListCompare(v237, v62, 0xFFFFFFFFLL, v19)
            && !*(_QWORD *)(v4 + 112) )
          {
            *(_DWORD *)(v4 + 4) &= ~1u;
            v64 = sqlite3ExprListDup(v34, v62, 0);
            *(_DWORD *)(v4 + 4) |= 8u;
            v242 = (int *)v64;
            *(_QWORD *)(v4 + 56) = v64;
            LOBYTE(v247) = 2;
          }
          if ( (_QWORD)v237 )
          {
            v65 = sqlite3KeyInfoFromExprList(a1, v237, 0, (unsigned int)*v62);
            HIDWORD(v237) = *((_DWORD *)a1 + 13);
            v66 = HIDWORD(v237);
            v67 = v65;
            *((_DWORD *)a1 + 13) = HIDWORD(v237) + 1;
            v68 = sqlite3VdbeAddOp3(Vdbe, 118, v66, *v62 + *(_DWORD *)v237 + 1, 0);
            v69 = v67;
            v7 = Vdbe;
            v70 = v68;
            sqlite3VdbeChangeP4(Vdbe, v68, v69, 4294967288LL);
            DWORD2(v238) = v70;
            v62 = v223;
          }
          else
          {
            DWORD2(v238) = -1;
          }
          if ( *(_BYTE *)v236 == 12 )
          {
            sqlite3VdbeAddOp3(v7, 118, *((_DWORD *)v236 + 1), *v62, 0);
            if ( (*(_DWORD *)(v4 + 4) & 0x800) != 0 )
            {
              v71 = *v62;
              for ( i = *v62 - 1; i > 0; --i )
              {
                v73 = v223;
                v74 = 8LL * (unsigned int)i;
                if ( (v223[v74 + 7] & 0x40) != 0 )
                {
                  v62 = v223;
                  break;
                }
                v75 = *(_QWORD *)&v223[v74 + 2];
                if ( v75 )
                {
                  sqlite3ExprDeleteNN(v217, v75);
                  v73 = v223;
                }
                if ( *(_QWORD *)&v73[v74 + 4] )
                  sqlite3DbFreeNN(v217);
                v62 = v223;
                --*v223;
                v71 = *v62;
              }
              v76 = 0;
              if ( v71 > 0 )
              {
                do
                {
                  v77 = 8LL * v76;
                  if ( (v62[v77 + 7] & 0x40) == 0 )
                    **(_BYTE **)&v62[v77 + 2] = 121;
                  ++v76;
                }
                while ( v76 < *v62 );
              }
            }
          }
          v78 = *((_DWORD *)a1 + 17) - 1;
          *((_DWORD *)a1 + 17) = v78;
          v17 = (*(_DWORD *)(v4 + 4) & 0x4000) == 0;
          LODWORD(v219) = v78;
          if ( v17 )
            *(_WORD *)(v4 + 2) = 320;
          if ( *(_QWORD *)(v4 + 96) )
            computeLimitRegisters(a1, v4, v78);
          if ( !*(_DWORD *)(v4 + 8) && (SDWORD2(v238) & 0x80000000) == 0 )
          {
            if ( *(_BYTE *)(*(_QWORD *)v7 + 103LL) )
              v79 = qword_18010FAB0;
            else
              v79 = (__int64 *)(*(_QWORD *)(v7 + 136) + 24LL * SDWORD2(v238));
            *(_BYTE *)v79 = 119;
            BYTE4(v239) |= 1u;
          }
          if ( (*(_BYTE *)(v4 + 4) & 1) != 0 )
          {
            HIDWORD(v247) = *((_DWORD *)a1 + 13);
            *((_DWORD *)a1 + 13) = HIDWORD(v247) + 1;
            v80 = sqlite3KeyInfoFromExprList(a1, *(_QWORD *)(v4 + 32), 0, 0);
            v81 = sqlite3VdbeAddOp3(Vdbe, 118, HIDWORD(v247), 0, 0);
            v82 = v80;
            v7 = Vdbe;
            v83 = v81;
            sqlite3VdbeChangeP4(Vdbe, v81, v82, 4294967288LL);
            v248 = v83;
            v84 = *(int *)(v7 + 144);
            if ( (int)v84 > 0 )
              *(_WORD *)(*(_QWORD *)(v7 + 136) + 24 * v84 - 22) = 8;
            BYTE1(v247) = 3;
          }
          else
          {
            BYTE1(v247) = 0;
          }
          v85 = v242;
          if ( !v228 && !v242 )
          {
            v86 = 256;
            if ( !(_BYTE)v247 )
              v86 = 0;
            v87 = *(_QWORD *)(v4 + 112);
            v88 = v86 | *(_WORD *)(v4 + 4) & 0x4000;
            if ( v87 )
              sqlite3WindowCodeInit(a1, v4);
            v89 = sqlite3WhereBegin(
                    (_DWORD)a1,
                    (_DWORD)v15,
                    v233,
                    v237,
                    *(_QWORD *)(v4 + 32),
                    v4,
                    v88,
                    *(__int16 *)(v4 + 2));
            v230 = v89;
            v90 = v89;
            if ( !v89 )
              goto LABEL_14;
            v91 = *(_WORD *)(v89 + 72);
            if ( v91 < *(__int16 *)(v4 + 2) )
              *(_WORD *)(v4 + 2) = v91;
            if ( (_BYTE)v247 )
            {
              v92 = BYTE1(v247);
              if ( *(_BYTE *)(v90 + 67) )
                v92 = *(_BYTE *)(v90 + 67);
              BYTE1(v247) = v92;
            }
            v93 = v237;
            if ( (_QWORD)v237 )
            {
              v94 = 0;
              if ( *(char *)(v90 + 65) >= 0 )
                v94 = *(char *)(v90 + 65);
              DWORD2(v237) = v94;
              if ( (*(_BYTE *)(v90 + 68) & 4) != 0
                && (v95 = 112LL * *(unsigned __int8 *)(v90 + 64), !*(_QWORD *)(v95 + v90 + 808)) )
              {
                v96 = *(_DWORD *)(v95 + v90 + 768);
              }
              else
              {
                v96 = *(_DWORD *)(v90 + 48);
              }
              LODWORD(v239) = v96;
              if ( v94 == *(_DWORD *)v237 )
                v93 = 0;
              *(_QWORD *)&v237 = v93;
            }
            if ( (SDWORD2(v238) & 0x80000000) == 0 && !v93 )
            {
              sqlite3VdbeChangeToNoop(v7, DWORD2(v238));
              v90 = v230;
            }
            if ( v87 )
            {
              v97 = *((_DWORD *)a1 + 17);
              ++*((_DWORD *)a1 + 14);
              --v97;
              v98 = *((_DWORD *)a1 + 14);
              v99 = v97 - 1;
              v100 = v97 - 2;
              *((_DWORD *)a1 + 17) = v97 - 2;
              sqlite3WindowCodeStep((_DWORD)a1, v4, v90, v98, v97);
              v101 = Vdbe;
              sqlite3VdbeAddOp3(Vdbe, 9, 0, v97 - 2, 0);
              sqlite3VdbeResolveLabel(v101, v97);
              v102 = v236;
              LODWORD(v239) = 0;
              selectInnerLoop((_DWORD)a1, v4, -1, (unsigned int)&v237, (__int64)&v247, (__int64)v236, v99, v100);
              sqlite3VdbeResolveLabel(v101, v99);
              sqlite3VdbeAddOp3(v101, 67, v98, 0, 0);
              v103 = v100;
              v104 = v101;
              v105 = v101;
              goto LABEL_371;
            }
            v102 = v236;
            selectInnerLoop(
              (_DWORD)a1,
              v4,
              -1,
              (unsigned int)&v237,
              (__int64)&v247,
              (__int64)v236,
              *(_DWORD *)(v90 + 48),
              *(_DWORD *)(v90 + 52));
            sqlite3WhereEnd(v230);
            v105 = Vdbe;
LABEL_372:
            if ( BYTE1(v247) == 3 )
              sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
            if ( (_QWORD)v237 )
              generateSortTail((_DWORD)a1, v4, (unsigned int)&v237, *v223, (__int64)v102);
            sqlite3VdbeResolveLabel(v105, (unsigned int)v219);
            v8 = *((_DWORD *)a1 + 12) > 0;
LABEL_377:
            v126 = v217;
            goto LABEL_378;
          }
          v235 = 0;
          memset(v246, 0, sizeof(v246));
          if ( v242 )
          {
            v106 = *(int **)(v4 + 32);
            v107 = *v106;
            v108 = v106 + 2;
            while ( v107 > 0 )
            {
              *((_WORD *)v108 + 13) = 0;
              v108 += 8;
              --v107;
            }
            v109 = *v85;
            v110 = v85 + 2;
            while ( v109 > 0 )
            {
              *((_WORD *)v110 + 13) = 0;
              v110 += 8;
              --v109;
            }
            if ( *(__int16 *)(v4 + 2) > 66 )
              *(_WORD *)(v4 + 2) = 66;
            if ( (_QWORD)v237 && *v85 == *(_DWORD *)v237 )
            {
              for ( j = 0; j < *v85; LOBYTE(v85[8 * v112 + 6]) = *(_BYTE *)(32 * v112 + v237 + 24) & 1 )
                v112 = j++;
              if ( !(unsigned int)sqlite3ExprListCompare(v85, v237, 0xFFFFFFFFLL, v19) )
                v235 = 1;
            }
          }
          else
          {
            *(_WORD *)(v4 + 2) = 0;
          }
          v113 = v217;
          v227 = *((_DWORD *)a1 + 17) - 1;
          *((_DWORD *)a1 + 17) = v227;
          v114 = sqlite3DbMallocZero(v113, 56);
          v115 = v114;
          if ( v114 )
            sqlite3ParserAddCleanup(a1, agginfoFree, v114);
          if ( *(_BYTE *)(v217 + 103) )
            goto LABEL_14;
          *(_DWORD *)(v115 + 52) = *(_DWORD *)(v4 + 16);
          *(_QWORD *)v246 = a1;
          *(_QWORD *)&v246[8] = v15;
          *(_QWORD *)&v246[16] = v115;
          memset(&v246[24], 0, 32);
          if ( v85 )
            v116 = *v85;
          else
            LOWORD(v116) = 0;
          v117 = v223;
          *(_WORD *)(v115 + 2) = v116;
          *(_QWORD *)(v115 + 16) = v85;
          sqlite3ExprAnalyzeAggList(v246, v117);
          sqlite3ExprAnalyzeAggList(v246, v237);
          v118 = v234;
          v119 = 0;
          if ( v234 )
          {
            if ( v85 )
            {
              v120 = *(_QWORD *)(v4 + 64);
              *(_QWORD *)&v240 = a1;
              *((_QWORD *)&v240 + 1) = havingToWhereExprCb;
              *((_QWORD *)&v241[1] + 1) = v4;
              memset(v241, 0, 24);
              if ( v120 )
              {
                sqlite3WalkExprNN(&v240, v120, 0);
                v118 = v234;
              }
              v233 = *(_QWORD *)(v4 + 48);
            }
            sqlite3ExprAnalyzeAggregates(v246, v118, v119);
          }
          *(_DWORD *)(v115 + 36) = *(_DWORD *)(v115 + 32);
          if ( *(_QWORD *)(v4 + 56)
            || *(_QWORD *)(v4 + 64)
            || *(_DWORD *)(v115 + 48) != 1
            || (v121 = *(__int64 **)(v115 + 40), v122 = *v121, (v123 = *(_DWORD **)(*v121 + 32)) == 0)
            || *v123 != 1
            || (*(_DWORD *)(v122 + 4) & 0x1000000) != 0
            || (*(_DWORD *)(v217 + 96) & 0x10000) != 0 )
          {
            v213 = 0;
          }
          else
          {
            v224 = *(_DWORD **)(v122 + 8);
            if ( (unsigned int)sqlite3StrICmp(v224, "min") )
            {
              if ( !(unsigned int)sqlite3StrICmp(v224, "max") )
              {
                v218 = 1;
                v213 = 2;
                goto LABEL_233;
              }
              v213 = 0;
            }
            else
            {
              v213 = 1;
              v218 = (unsigned int)sqlite3ExprCanBeNull(*(_QWORD *)(v124 + 8)) != 0 ? 2 : 0;
LABEL_233:
              v232 = sqlite3ExprListDup(v217, v125, 0);
              if ( v232 )
                *(_BYTE *)(v232 + 24) = v218;
            }
          }
          analyzeAggFuncArgs(v115, v246);
          v126 = v217;
          if ( !*(_BYTE *)(v217 + 103) )
          {
            if ( v85 )
            {
              v243 = 0;
              v231 = 0;
              if ( *(_DWORD *)(v115 + 48) == 1 )
              {
                v127 = *(int **)(v115 + 40);
                if ( v127[4] >= 0 )
                {
                  v128 = *(_QWORD *)v127;
                  if ( v128 )
                  {
                    if ( (*(_DWORD *)(v128 + 4) & 0x1000) == 0 )
                    {
                      v129 = *(_QWORD *)(v128 + 32);
                      if ( v129 )
                      {
                        v130 = *(_QWORD *)(v129 + 8);
                        if ( v130 )
                        {
                          v131 = exprDup(v217, v130, 0);
                          v126 = v217;
                          v230 = v131;
                        }
                        else
                        {
                          v230 = 0;
                        }
                        v132 = sqlite3ExprListDup(v126, v85, 0);
                        v133 = sqlite3ExprListAppend(a1, v132, v230);
                        v134 = 0;
                        v243 = v133;
                        if ( v133 )
                          v134 = 1280;
                        LOWORD(v231) = v134;
                      }
                    }
                  }
                }
              }
              *(_DWORD *)(v115 + 4) = (*((_DWORD *)a1 + 13))++;
              v135 = (_DWORD *)sqlite3KeyInfoFromExprList(a1, v85, 0, *(unsigned int *)(v115 + 32));
              v136 = *(unsigned __int16 *)(v115 + 2);
              v137 = *(_DWORD *)(v115 + 4);
              v224 = v135;
              v244 = sqlite3VdbeAddOp3(v7, 119, v137, v136, 0);
              sqlite3VdbeChangeP4(v7, v244, v224, 4294967288LL);
              v138 = *((_DWORD *)a1 + 17) - 1;
              v214 = *((_DWORD *)a1 + 14) + 1;
              v226 = v138;
              v139 = v214 + 1;
              v140 = v214 + 3;
              v225 = v214 + 1;
              *((_DWORD *)a1 + 14) = v214 + 3;
              *((_DWORD *)a1 + 17) = v138 - 1;
              v141 = v140 + 1;
              v142 = *v85 + v140;
              *((_DWORD *)a1 + 14) = v142;
              v216 = v142;
              *((_DWORD *)a1 + 14) = *v85 + v142;
              v228 = v141;
              sqlite3VdbeAddOp3(v7, 71, 0, v139, 0);
              sqlite3VdbeAddOp3(v7, 75, 0, v228, *v85 + v225 + 2);
              sqlite3VdbeAddOp3(v7, 10, v225 + 2, v226 - 1, 0);
              v143 = 128;
              if ( (_BYTE)v247 != 2 )
                v143 = 64;
              v230 = sqlite3WhereBegin(
                       (_DWORD)a1,
                       (_DWORD)v15,
                       v233,
                       (_DWORD)v85,
                       v243,
                       v4,
                       (unsigned __int16)v231 | (unsigned __int16)(v143 | ((_WORD)v235 << 9)),
                       0);
              v145 = v230;
              if ( !v230 )
              {
                if ( v243 )
                  exprListDeleteNN(v217, v243);
                goto LABEL_377;
              }
              v229 = v216 + 1;
              if ( a1[12] )
              {
                v146 = *(_DWORD *)(v115 + 36);
                *(_DWORD *)(v115 + 32) = v146;
                if ( *(_WORD *)(v115 + 2) )
                {
                  v147 = **(_DWORD **)(v4 + 56) - 1;
                  if ( v146 > 0 )
                  {
                    for ( k = 0; k < v146; ++k )
                    {
                      v149 = *(__int16 *)(*(_QWORD *)(v115 + 24) + 24LL * (unsigned int)k + 22);
                      if ( v149 <= v147 )
                        v149 = v147;
                      v147 = v149;
                    }
                  }
                  *(_WORD *)(v115 + 2) = v147 + 1;
                }
                analyzeAggFuncArgs(v115, v246);
              }
              v150 = 0;
              *(_DWORD *)(v115 + 12) = *((_DWORD *)a1 + 14) + 1;
              *((_DWORD *)a1 + 14) += *(_DWORD *)(v115 + 32) + *(_DWORD *)(v115 + 48);
              v151 = *(char *)(v145 + 65) < 0;
              v216 = *(unsigned __int8 *)(v145 + 67);
              if ( !v151 )
                v150 = *(char *)(v145 + 65);
              if ( v150 == *v85 )
              {
                v220 = 0;
                TempRange = 0;
                v215 = 0;
              }
              else
              {
                if ( !(_BYTE)v247 || (v152 = "DISTINCT", (*(_BYTE *)(v4 + 4) & 1) != 0) )
                  v152 = "GROUP BY";
                sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v152);
                v153 = *v85;
                v154 = v153;
                v215 = 1;
                v220 = v153;
                if ( *(int *)(v115 + 32) > 0 )
                {
                  v155 = 0;
                  v156 = v153;
                  do
                  {
                    v157 = *(__int16 *)(*(_QWORD *)(v115 + 24) + 24LL * v155 + 22);
                    v158 = v154 + 1;
                    if ( v157 < v156 )
                      v158 = v154;
                    ++v155;
                    v154 = v158;
                    v159 = v156 + 1;
                    if ( v157 < v156 )
                      v159 = v156;
                    v156 = v159;
                  }
                  while ( (signed int)v155 < *(_DWORD *)(v115 + 32) );
                  v220 = v154;
                }
                TempRange = sqlite3GetTempRange(a1, v154);
                sqlite3ExprCodeExprList((_DWORD)a1, (_DWORD)v85, TempRange, 0, 0);
                *(_BYTE *)v115 = 1;
                if ( *(int *)(v115 + 32) > 0 )
                {
                  v160 = TempRange;
                  v161 = 0;
                  do
                  {
                    v162 = *(_QWORD *)(v115 + 24);
                    if ( *(__int16 *)(v162 + 24LL * v161 + 22) >= v153 )
                    {
                      sqlite3ExprCode(a1, *(_QWORD *)(v162 + 24LL * v161 + 8), v153 + v160);
                      ++v153;
                    }
                    ++v161;
                  }
                  while ( v161 < *(_DWORD *)(v115 + 32) );
                  LODWORD(v4) = v245;
                  v7 = Vdbe;
                }
                *(_BYTE *)v115 = 0;
                v163 = *((_BYTE *)a1 + 31);
                if ( v163 )
                {
                  v165 = v163 - 1;
                  *((_BYTE *)a1 + 31) = v165;
                  v164 = *((_DWORD *)a1 + v165 + 58);
                }
                else
                {
                  v164 = *((_DWORD *)a1 + 14) + 1;
                  *((_DWORD *)a1 + 14) = v164;
                }
                sqlite3VdbeAddOp3(v7, 97, TempRange, v220, v164);
                sqlite3VdbeAddOp3(v7, 139, *(_DWORD *)(v115 + 4), v164, 0);
                if ( v164 && *((_BYTE *)a1 + 31) < 8u )
                  *((_DWORD *)a1 + (unsigned __int8)(*((_BYTE *)a1 + 31))++ + 58) = v164;
                v166 = v220;
                sqlite3ReleaseTempRange(a1, TempRange, v220);
                sqlite3WhereEnd(v230);
                v167 = *((_DWORD *)a1 + 13);
                *(_DWORD *)(v115 + 8) = v167;
                ++*((_DWORD *)a1 + 13);
                v168 = *((_BYTE *)a1 + 31);
                v220 = v167;
                if ( v168 )
                {
                  v170 = v168 - 1;
                  *((_BYTE *)a1 + 31) = v170;
                  v169 = *((_DWORD *)a1 + v170 + 58);
                }
                else
                {
                  v169 = *((_DWORD *)a1 + 14) + 1;
                  *((_DWORD *)a1 + 14) = v169;
                }
                TempRange = v169;
                sqlite3VdbeAddOp3(v7, 121, v167, v169, v166);
                sqlite3VdbeAddOp3(v7, 34, *(_DWORD *)(v115 + 4), v227, 0);
                *(_BYTE *)(v115 + 1) = 1;
              }
              if ( a1[12] )
              {
                v171 = 0;
                *(_QWORD *)&v240 = 0;
                *((_QWORD *)&v240 + 1) = aggregateIdxEprRefToColCallback;
                memset(v241, 0, sizeof(v241));
                if ( *(int *)(v115 + 48) > 0 )
                {
                  do
                  {
                    v172 = *(_QWORD *)(32LL * v171 + *(_QWORD *)(v115 + 40));
                    if ( v172 )
                      sqlite3WalkExprNN(&v240, v172, v144);
                    ++v171;
                  }
                  while ( v171 < *(_DWORD *)(v115 + 48) );
                }
              }
              if ( v235 && (*(_BYTE *)(v217 + 96) & 4) == 0 && (v215 || (*(_BYTE *)(v230 + 68) & 8) != 0) )
              {
                *(_QWORD *)&v237 = 0;
                sqlite3VdbeChangeToNoop(v7, DWORD2(v238));
              }
              LODWORD(v233) = *(_DWORD *)(v7 + 144);
              v173 = v215;
              if ( v215 )
              {
                sqlite3VdbeAddOp3(v7, 133, *(_DWORD *)(v115 + 4), TempRange, v220);
                v173 = v215;
              }
              v174 = 0;
              if ( *v85 > 0 )
              {
                v175 = v220;
                do
                {
                  v176 = v174 + v229;
                  if ( v173 )
                  {
                    sqlite3VdbeAddOp3(v7, 94, v175, v174, v176);
                  }
                  else
                  {
                    *(_BYTE *)v115 = 1;
                    sqlite3ExprCode(a1, *(_QWORD *)&v85[8 * v174 + 2], v176);
                  }
                  v173 = v215;
                  ++v174;
                }
                while ( v174 < *v85 );
                LODWORD(v4) = v245;
              }
              v177 = v224;
              if ( v224 )
                ++*v224;
              v178 = sqlite3VdbeAddOp3(v7, 90, v228, v229, *v85);
              sqlite3VdbeChangeP4(v7, v178, v177, 4294967288LL);
              v179 = *(_DWORD *)(v7 + 144);
              sqlite3VdbeAddOp3(v7, 14, v179 + 1, 0, v179 + 1);
              sqlite3VdbeAddOp3(a1[2], 79, v229, v228, *v242);
              v180 = v225;
              sqlite3VdbeAddOp3(v7, 10, v225 + 1, v226, 0);
              sqlite3VdbeAddOp3(v7, 59, v180, v227, 0);
              sqlite3VdbeAddOp3(v7, 10, v180 + 2, v226 - 1, 0);
              sqlite3VdbeJumpHere(v7, v179);
              updateAccumulator(a1, v214, v115, v216);
              sqlite3VdbeAddOp3(v7, 71, 1, v214, 0);
              if ( v215 )
              {
                sqlite3VdbeAddOp3(v7, 37, *(_DWORD *)(v115 + 4), v233, 0);
              }
              else
              {
                sqlite3WhereEnd(v230);
                sqlite3VdbeChangeToNoop(v7, v244);
              }
              if ( v243 )
                exprListDeleteNN(v217, v243);
              sqlite3VdbeAddOp3(v7, 10, v180 + 1, v226, 0);
              sqlite3VdbeAddOp3(v7, 9, 0, v227, 0);
              v181 = *(_DWORD *)(v7 + 144);
              v105 = Vdbe;
              sqlite3VdbeAddOp3(Vdbe, 71, 1, v225, 0);
              v182 = v225 + 1;
              sqlite3VdbeAddOp3(v105, 67, v225 + 1, 0, 0);
              sqlite3VdbeResolveLabel(v105, v226);
              v183 = *(_DWORD *)(v105 + 144);
              sqlite3VdbeAddOp3(v105, 59, v214, v183 + 2, 0);
              sqlite3VdbeAddOp3(v105, 67, v182, 0, 0);
              finalizeAggFunctions(a1, v115);
              sqlite3ExprIfFalse(a1, v234, (unsigned int)++v183, 16);
              v212 = v183;
              v102 = v236;
              selectInnerLoop((_DWORD)a1, v4, -1, (unsigned int)&v237, (__int64)&v247, (__int64)v236, v212, v181);
              sqlite3VdbeAddOp3(v105, 67, v182, 0, 0);
              sqlite3VdbeResolveLabel(v105, v226 - 1);
              resetAccumulator(a1, v115);
              sqlite3VdbeAddOp3(v105, 71, 0, v214, 0);
              sqlite3VdbeAddOp3(v105, 67, v182 + 1, 0, 0);
              if ( (_WORD)v231 && v216 )
                fixDistinctOpenEph(
                  a1,
                  v216,
                  *(unsigned int *)(*(_QWORD *)(v115 + 40) + 16LL),
                  *(unsigned int *)(*(_QWORD *)(v115 + 40) + 20LL));
            }
            else
            {
              if ( !*(_QWORD *)(v4 + 48)
                && (v184 = *(_QWORD *)(v4 + 32), *(_DWORD *)v184 == 1)
                && (v185 = *(_QWORD *)(v4 + 40), *(_DWORD *)v185 == 1)
                && !*(_QWORD *)(v185 + 48)
                && *(_DWORD *)(v115 + 48) == 1
                && !*(_QWORD *)(v4 + 64)
                && (v186 = *(_QWORD **)(v185 + 40), !*((_BYTE *)v186 + 63))
                && (v187 = *(_QWORD *)(v184 + 8), *(_BYTE *)v187 == 0xA8)
                && *(_QWORD *)(v187 + 56) == v115
                && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v115 + 40) + 8LL) + 4LL) & 0x100) != 0
                && (*(_DWORD *)(v187 + 4) & 0x1000004) == 0
                && v186 )
              {
                v188 = v186[12];
                if ( v188 )
                {
                  v189 = 0;
                  v190 = *(_QWORD *)(*a1 + 32LL);
                  if ( *(_QWORD *)(v190 + 24) != v188 )
                  {
                    do
                      ++v189;
                    while ( *(_QWORD *)(32LL * v189 + v190 + 24) != v188 );
                  }
                }
                else
                {
                  v189 = -32768;
                }
                v214 = *((_DWORD *)a1 + 13);
                v224 = 0;
                *((_DWORD *)a1 + 13) = v214 + 1;
                m = 0;
                v216 = *((_DWORD *)v186 + 10);
                sqlite3CodeVerifySchema(a1, (unsigned int)v189);
                sqlite3TableLock((_DWORD)a1, v189, *((_DWORD *)v186 + 10), 0, *v186);
                if ( *((char *)v186 + 48) < 0 )
                {
                  for ( m = v186[2]; m && (*(_DWORD *)(m + 100) & 3) != 2; m = *(_QWORD *)(m + 40) )
                    ;
                }
                if ( (*(_BYTE *)(*(_QWORD *)(v4 + 40) + 72LL) & 1) == 0 )
                {
                  for ( n = v186[2]; n; n = *(_QWORD *)(n + 40) )
                  {
                    if ( (*(_BYTE *)(n + 100) & 4) == 0 )
                    {
                      v193 = *(_WORD *)(n + 92);
                      if ( v193 < *((__int16 *)v186 + 30) && !*(_QWORD *)(n + 72) && (!m || v193 < *(__int16 *)(m + 92)) )
                        m = n;
                    }
                  }
                }
                if ( m )
                {
                  v216 = *(_DWORD *)(m + 88);
                  v224 = (_DWORD *)sqlite3KeyInfoOfIndex(a1, m);
                }
                v211 = v189;
                v105 = Vdbe;
                sqlite3VdbeAddOp4Int(Vdbe, 112, v214, v216, v211, 1);
                if ( v224 )
                  sqlite3VdbeChangeP4(v105, 0xFFFFFFFFLL, v224, 4294967288LL);
                v194 = v214;
                *(_DWORD *)(v115 + 12) = *((_DWORD *)a1 + 14) + 1;
                *((_DWORD *)a1 + 14) += *(_DWORD *)(v115 + 32) + *(_DWORD *)(v115 + 48);
                sqlite3VdbeAddOp3(v105, 98, v194, *(_DWORD *)(v115 + 12) + *(_DWORD *)(v115 + 32), 0);
                sqlite3VdbeAddOp3(v105, 122, v214, 0, 0);
                if ( *((_BYTE *)a1 + 307) == 2 )
                {
                  if ( !m || *((char *)v186 + 48) < 0 && (*(_DWORD *)(m + 100) & 3) == 2 )
                  {
                    v8 = 0;
                    v195 = &Src;
                  }
                  else
                  {
                    v195 = *(const wchar_t **)m;
                  }
                  v196 = " USING COVERING INDEX ";
                  if ( !v8 )
                    v196 = (const char *)&Src;
                  sqlite3VdbeExplain(a1, 0, "SCAN %s%s%s", *v186, v196, v195);
                }
              }
              else
              {
                v197 = 0;
                v198 = *(_DWORD *)(v115 + 48);
                v199 = 0;
                v224 = 0;
                if ( *(_DWORD *)(v115 + 36) )
                {
                  v200 = 0;
                  if ( v198 <= 0 )
                  {
LABEL_386:
                    if ( v200 == v198 )
                    {
                      v197 = ++*((_DWORD *)a1 + 14);
                      sqlite3VdbeAddOp3(Vdbe, 71, 0, v197, 0);
                    }
                  }
                  else
                  {
                    v201 = *(_QWORD *)(v115 + 40);
                    while ( 1 )
                    {
                      v202 = 32LL * v200;
                      if ( (*(_DWORD *)(*(_QWORD *)(v202 + v201) + 4LL) & 0x1000000) == 0
                        && (*(_BYTE *)(*(_QWORD *)(v202 + v201 + 8) + 4LL) & 0x20) != 0 )
                      {
                        break;
                      }
                      if ( (int)++v200 >= v198 )
                        goto LABEL_386;
                    }
                  }
                }
                else if ( v198 == 1 )
                {
                  v203 = *(int **)(v115 + 40);
                  if ( v203[4] >= 0 )
                  {
                    v224 = *(_DWORD **)(*(_QWORD *)v203 + 32LL);
                    if ( v224 )
                      v199 = 1280;
                  }
                }
                *(_DWORD *)(v115 + 12) = *((_DWORD *)a1 + 14) + 1;
                *((_DWORD *)a1 + 14) += *(_DWORD *)(v115 + 32) + *(_DWORD *)(v115 + 48);
                resetAccumulator(a1, v115);
                v204 = sqlite3WhereBegin((_DWORD)a1, (_DWORD)v15, v233, v232, (__int64)v224, v4, v199 | v213, 0);
                v205 = v204;
                if ( !v204 )
                  goto LABEL_377;
                v206 = *(unsigned __int8 *)(v204 + 67);
                updateAccumulator(a1, v197, v115, *(unsigned __int8 *)(v204 + 67));
                if ( v206 )
                {
                  v207 = *(_QWORD *)(v115 + 40);
                  if ( v207 )
                    fixDistinctOpenEph(a1, v206, *(unsigned int *)(v207 + 16), *(unsigned int *)(v207 + 20));
                }
                v105 = Vdbe;
                if ( v197 )
                  sqlite3VdbeAddOp3(Vdbe, 71, 1, v197, 0);
                if ( v213 && (*(_BYTE *)(v205 + 68) & 4) != 0 && *(_BYTE *)(v205 + 65) )
                {
                  v208 = *(unsigned __int8 *)(v205 + 64);
                  do
                  {
                    if ( (--v208 & 0x80000000) != 0 )
                    {
                      v210 = *(_DWORD *)(v205 + 52);
                      goto LABEL_405;
                    }
                    v209 = 112LL * v208;
                  }
                  while ( (*(_BYTE *)(*(_QWORD *)(v209 + v205 + 960) + 56LL) & 4) == 0 );
                  v210 = *(_DWORD *)(v209 + v205 + 880);
LABEL_405:
                  sqlite3VdbeAddOp3(v105, 9, 0, v210, 0);
                }
                sqlite3WhereEnd(v205);
                finalizeAggFunctions(a1, v115);
              }
              *(_QWORD *)&v237 = 0;
              sqlite3ExprIfFalse(a1, v234, v227, 16);
              v102 = v236;
              selectInnerLoop((_DWORD)a1, v4, -1, 0, 0, (__int64)v236, v227, v227);
            }
            v103 = v227;
            v104 = v105;
LABEL_371:
            sqlite3VdbeResolveLabel(v104, v103);
            goto LABEL_372;
          }
LABEL_378:
          if ( v232 )
            exprListDeleteNN(v126, v232);
          goto LABEL_14;
        }
        v20 = 26LL * v6;
        v17 = (v15[v20 + 17] & 0x48) == 0;
        v21 = *(int **)&v15[v20 + 12];
        v22 = *(_QWORD *)&v15[v20 + 10];
        v223 = v21;
        v219 = v22;
        if ( !v17 )
        {
          v23 = sqlite3ExprImpliesNonNullRow(
                  *(_QWORD *)(v4 + 48),
                  (unsigned int)v15[v20 + 19],
                  v15[v20 + 17] & 0x40,
                  v19);
          v19 = v217;
          v16 = 8;
          if ( v23 && (*(_DWORD *)(v217 + 96) & 0x2000) == 0 )
          {
            v24 = v15[v20 + 17];
            if ( (v24 & 8) != 0 )
            {
              if ( (v24 & 0x10) != 0 )
              {
                LOBYTE(v15[v20 + 17]) = v24 & 0xF7;
              }
              else
              {
                v25 = (unsigned int)v15[v20 + 19];
                LOBYTE(v15[v20 + 17]) = v24 & 0xD7;
                unsetJoinExpr(*(_QWORD *)(v4 + 48), v25, 0, v19);
              }
            }
            if ( (v15[v20 + 17] & 0x40) != 0 )
            {
              for ( ii = (unsigned int)(v6 + 1); ; ii = (unsigned int)(ii + 1) )
              {
                v29 = *v15;
                if ( (int)ii >= *v15 )
                  break;
                v27 = 26LL * (int)ii;
                v28 = v15[v27 + 17];
                if ( (v28 & 0x10) != 0 )
                {
                  if ( (v28 & (unsigned __int8)v16) != 0 )
                  {
                    LOBYTE(v15[v27 + 17]) = v28 & 0xEF;
                  }
                  else
                  {
                    LOBYTE(v15[v27 + 17]) = v28 & 0xCF;
                    unsetJoinExpr(*(_QWORD *)(v4 + 48), (unsigned int)v15[v27 + 19], 1, ii);
                  }
                }
              }
              do
              {
                if ( (--v29 & 0x80000000) != 0 )
                  break;
                v30 = 26LL * v29;
                LOBYTE(v15[v30 + 17]) &= ~0x40u;
              }
              while ( (v15[v30 + 17] & 0x10) == 0 );
              v19 = v217;
            }
          }
          v21 = v223;
          v22 = v219;
        }
        if ( v21 )
        {
          v14 = (unsigned int)*(__int16 *)(v22 + 54);
          v31 = **((_DWORD **)v21 + 4);
          if ( (_DWORD)v14 != v31 )
          {
            sqlite3ErrorMsg(a1, "expected %d columns for '%s' but got %d", v14, *(const char **)v22, v31);
            goto LABEL_14;
          }
          if ( ((v15[v20 + 18] & 0x100) == 0 || *(_BYTE *)(*(_QWORD *)&v15[v20 + 26] + 18LL))
            && ((unsigned __int8)v16 & (_BYTE)v223[1]) == 0 )
          {
            v14 = *((_QWORD *)v223 + 9);
            if ( v14 )
            {
              if ( !*(_QWORD *)(v4 + 72) && *v15 <= 1
                || *((_QWORD *)v223 + 12)
                || (v223[1] & 0x8000000) != 0
                || (*(_DWORD *)(v4 + 4) & 0x8000000) != 0
                || (*(_DWORD *)(v19 + 96) & 0x40000) != 0 )
              {
                if ( !v6 && (*(_DWORD *)(v4 + 4) & 0x40000) != 0 && (*v15 == 1 || (v15[43] & 0x22) != 0) )
                  goto LABEL_65;
              }
              else
              {
                sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v14);
                *((_QWORD *)v223 + 9) = 0;
              }
            }
            if ( (unsigned int)flattenSubquery(a1, v4, (unsigned int)v6, v216) )
            {
              if ( *((_DWORD *)a1 + 12) )
                goto LABEL_14;
              v6 = -1;
            }
            v19 = v217;
            if ( *(_BYTE *)(v217 + 103) )
              goto LABEL_14;
            v16 = 8;
            v15 = *(signed int **)(v4 + 40);
            if ( *(_BYTE *)v236 > 8u )
              *(_QWORD *)&v237 = *(_QWORD *)(v4 + 72);
          }
        }
LABEL_65:
        ++v6;
      }
      while ( !*(_QWORD *)(v4 + 80) );
    }
    v32 = multiSelect(a1, (unsigned __int8 *)v4, v236);
    if ( !*(_QWORD *)(v4 + 88) )
      sqlite3VdbeExplainPop(a1);
    return v32;
  }
}

```

## disassembly

```asm
0x18008b73c  mov     [rsp-8+arg_18], rbx
0x18008b741  push    rbp
0x18008b742  push    rsi
0x18008b743  push    rdi
0x18008b744  push    r12
0x18008b746  push    r13
0x18008b748  push    r14
0x18008b74a  push    r15
0x18008b74c  lea     rbp, [rsp-0B0h]
0x18008b754  sub     rsp, 1B0h
0x18008b75b  mov     rax, cs:__security_cookie
0x18008b762  xor     rax, rsp
0x18008b765  mov     [rbp+0E0h+var_40], rax
0x18008b76c  xor     eax, eax
0x18008b76e  mov     [rbp+0E0h+var_110], r8
0x18008b772  xorps   xmm0, xmm0
0x18008b775  mov     [rbp+0E0h+var_50], rax
0x18008b77c  mov     [rbp+0E0h+var_48], eax
0x18008b782  mov     r14, r8
0x18008b785  mov     rax, [rcx]
0x18008b788  mov     r13, rdx
0x18008b78b  mov     [rsp+1E0h+var_190], rax
0x18008b790  mov     r15, rcx
0x18008b793  mov     [rbp+0E0h+var_90], rdx
0x18008b797  movups  [rbp+0E0h+var_108], xmm0
0x18008b79b  movups  [rbp+0E0h+var_F8], xmm0
0x18008b79f  movups  [rbp+0E0h+var_E8], xmm0
0x18008b7a3  call    sqlite3GetVdbe
0x18008b7a8  xor     esi, esi
0x18008b7aa  mov     [rsp+1E0h+var_170], rax
0x18008b7af  mov     rdi, rax
0x18008b7b2  test    r13, r13
0x18008b7b5  jz      loc_18008D627
0x18008b7bb  cmp     [r15+30h], esi
0x18008b7bf  jnz     loc_18008D627
0x18008b7c5  xor     r9d, r9d
0x18008b7c8  mov     [rsp+1E0h+var_1C0], rsi
0x18008b7cd  xor     r8d, r8d
0x18008b7d0  lea     edx, [rsi+15h]
0x18008b7d3  mov     rcx, r15
0x18008b7d6  call    sqlite3AuthCheck
0x18008b7db  test    eax, eax
0x18008b7dd  jnz     loc_18008D627
0x18008b7e3  cmp     byte ptr [r14], 6
0x18008b7e7  lea     r12d, [rsi+1]
0x18008b7eb  ja      short loc_18008B814
0x18008b7ed  mov     r8, [r13+48h]
0x18008b7f1  test    r8, r8
0x18008b7f4  jz      short loc_18008B809
0x18008b7f6  lea     rdx, sqlite3ExprListDeleteGeneric
0x18008b7fd  mov     rcx, r15
0x18008b800  call    sqlite3ParserAddCleanup
0x18008b805  mov     [r13+48h], rsi
0x18008b809  and     dword ptr [r13+4], 0FFFFFFFEh
0x18008b80e  bts     dword ptr [r13+4], 16h
0x18008b814  xor     r8d, r8d
0x18008b817  mov     rdx, r13
0x18008b81a  mov     rcx, r15
0x18008b81d  call    sqlite3SelectPrep
0x18008b822  cmp     [r15+30h], esi
0x18008b826  jnz     short loc_18008B865
0x18008b828  mov     ebx, [r13+4]
0x18008b82c  bt      ebx, 17h
0x18008b830  jnb     short loc_18008B87F
0x18008b832  mov     rdx, [r13+28h]
0x18008b836  lea     rsi, [rdx+8]
0x18008b83a  mov     rcx, rsi
0x18008b83d  call    sameSrcAlias
0x18008b842  test    eax, eax
0x18008b844  jz      short loc_18008B875
0x18008b846  mov     r8, [rsi+18h]
0x18008b84a  test    r8, r8
0x18008b84d  jnz     short loc_18008B856
0x18008b84f  mov     rax, [rsi+20h]
0x18008b853  mov     r8, [rax]
0x18008b856  lea     rdx, aTargetObjectAl; "target object/alias may not appear in F"...
0x18008b85d  mov     rcx, r15
0x18008b860  call    sqlite3ErrorMsg
0x18008b865  mov     rcx, r15
0x18008b868  call    sqlite3VdbeExplainPop
0x18008b86d  mov     eax, r12d
0x18008b870  jmp     loc_18008D62C
0x18008b875  btr     ebx, 17h
0x18008b879  mov     [r13+4], ebx
0x18008b87d  xor     esi, esi
0x18008b87f  cmp     byte ptr [r14], 9
0x18008b883  jnz     short loc_18008B890
0x18008b885  mov     rdx, r13
0x18008b888  mov     rcx, r15
0x18008b88b  call    sqlite3GenerateColumnNames
0x18008b890  mov     rdx, r13
0x18008b893  mov     rcx, r15
0x18008b896  call    sqlite3WindowRewrite
0x18008b89b  test    eax, eax
0x18008b89d  jnz     short loc_18008B865
0x18008b89f  mov     eax, [r13+4]
0x18008b8a3  xorps   xmm0, xmm0
0x18008b8a6  mov     r14, [r13+28h]
0x18008b8aa  mov     r11d, 8
0x18008b8b0  and     eax, r11d
0x18008b8b3  mov     [rbp+0E0h+var_14C], eax
0x18008b8b6  mov     eax, esi
0x18008b8b8  setnz   al
0x18008b8bb  cmp     qword ptr [r13+50h], 0
0x18008b8c0  mov     [rsp+1E0h+var_194], eax
0x18008b8c4  mov     rax, [r13+48h]
0x18008b8c8  movups  [rbp+0E0h+var_108], xmm0
0x18008b8cc  mov     qword ptr [rbp+0E0h+var_108], rax
0x18008b8d0  movups  [rbp+0E0h+var_F8], xmm0
0x18008b8d4  movups  [rbp+0E0h+var_E8], xmm0
0x18008b8d8  jnz     loc_18008BB14
0x18008b8de  mov     r9, [rsp+1E0h+var_190]
0x18008b8e3  mov     r10d, 100h
0x18008b8e9  mov     ecx, 40h ; '@'
0x18008b8ee  cmp     esi, [r14]
0x18008b8f1  jge     loc_18008BB58
0x18008b8f7  movsxd  rax, esi
0x18008b8fa  imul    rbx, rax, 68h ; 'h'
0x18008b8fe  test    byte ptr [rbx+r14+44h], 48h
0x18008b904  mov     rax, [rbx+r14+30h]
0x18008b909  mov     rdx, [rbx+r14+28h]
0x18008b90e  mov     [rsp+1E0h+var_168], rax
0x18008b913  mov     [rsp+1E0h+var_180], rdx
0x18008b918  jz      loc_18008BA04
0x18008b91e  movzx   r8d, byte ptr [rbx+r14+44h]
0x18008b924  mov     edx, [rbx+r14+4Ch]
0x18008b929  and     r8d, ecx
0x18008b92c  mov     rcx, [r13+30h]
0x18008b930  call    sqlite3ExprImpliesNonNullRow
0x18008b935  mov     r9, [rsp+1E0h+var_190]
0x18008b93a  mov     r11d, 8
0x18008b940  test    eax, eax
0x18008b942  jz      loc_18008B9F4
0x18008b948  test    dword ptr [r9+60h], 2000h
0x18008b950  jnz     loc_18008B9F4
0x18008b956  mov     al, [rbx+r14+44h]
0x18008b95b  test    r11b, al
0x18008b95e  jz      short loc_18008B985
0x18008b960  test    al, 10h
0x18008b962  jz      short loc_18008B96D
0x18008b964  and     al, 0F7h
0x18008b966  mov     [rbx+r14+44h], al
0x18008b96b  jmp     short loc_18008B985
0x18008b96d  mov     edx, [rbx+r14+4Ch]
0x18008b972  and     al, 0D7h
0x18008b974  mov     [rbx+r14+44h], al
0x18008b979  xor     r8d, r8d
0x18008b97c  mov     rcx, [r13+30h]
0x18008b980  call    unsetJoinExpr
0x18008b985  test    byte ptr [rbx+r14+44h], 40h
0x18008b98b  jz      short loc_18008B9F4
0x18008b98d  lea     r9d, [rsi+1]
0x18008b991  jmp     short loc_18008B9CC
0x18008b993  movsxd  rax, r9d
0x18008b996  imul    rdx, rax, 68h ; 'h'
0x18008b99a  mov     al, [rdx+r14+44h]
0x18008b99f  test    al, 10h
0x18008b9a1  jz      short loc_18008B9C9
0x18008b9a3  test    r11b, al
0x18008b9a6  jz      short loc_18008B9B1
0x18008b9a8  and     al, 0EFh
0x18008b9aa  mov     [rdx+r14+44h], al
0x18008b9af  jmp     short loc_18008B9C9
0x18008b9b1  and     al, 0CFh
0x18008b9b3  mov     r8d, r12d
0x18008b9b6  mov     [rdx+r14+44h], al
0x18008b9bb  mov     edx, [rdx+r14+4Ch]
0x18008b9c0  mov     rcx, [r13+30h]
0x18008b9c4  call    unsetJoinExpr
0x18008b9c9  add     r9d, r12d
0x18008b9cc  mov     edx, [r14]
0x18008b9cf  cmp     r9d, edx
0x18008b9d2  jl      short loc_18008B993
0x18008b9d4  jmp     short loc_18008B9EA
0x18008b9d6  mov     eax, edx
0x18008b9d8  imul    rcx, rax, 68h ; 'h'
0x18008b9dc  and     byte ptr [rcx+r14+44h], 0BFh
0x18008b9e2  test    byte ptr [rcx+r14+44h], 10h
0x18008b9e8  jnz     short loc_18008B9EF
0x18008b9ea  sub     edx, r12d
0x18008b9ed  jns     short loc_18008B9D6
0x18008b9ef  mov     r9, [rsp+1E0h+var_190]
0x18008b9f4  mov     rax, [rsp+1E0h+var_168]
0x18008b9f9  mov     r10d, 100h
0x18008b9ff  mov     rdx, [rsp+1E0h+var_180]
0x18008ba04  test    rax, rax
0x18008ba07  jz      loc_18008BB06
0x18008ba0d  mov     rax, [rax+20h]
0x18008ba11  movsx   r8d, word ptr [rdx+36h]
0x18008ba16  mov     ecx, [rax]
0x18008ba18  cmp     r8d, ecx
0x18008ba1b  jnz     loc_18008BB3D
0x18008ba21  xor     edx, edx
0x18008ba23  test    [rbx+r14+48h], r10d
0x18008ba28  jz      short loc_18008BA38
0x18008ba2a  mov     rax, [rbx+r14+68h]
0x18008ba2f  cmp     [rax+12h], dl
0x18008ba32  jz      loc_18008BB06
0x18008ba38  mov     rbx, [rsp+1E0h+var_168]
0x18008ba3d  test    [rbx+4], r11b
0x18008ba41  jnz     loc_18008BB06
0x18008ba47  mov     r8, [rbx+48h]
0x18008ba4b  test    r8, r8
0x18008ba4e  jz      short loc_18008BAB4
0x18008ba50  cmp     [r13+48h], rdx
0x18008ba54  jnz     short loc_18008BA5B
0x18008ba56  cmp     [r14], r12d
0x18008ba59  jle     short loc_18008BA97
0x18008ba5b  cmp     [rbx+60h], rdx
0x18008ba5f  jnz     short loc_18008BA97
0x18008ba61  test    dword ptr [rbx+4], 8000000h
0x18008ba68  jnz     short loc_18008BA97
0x18008ba6a  test    dword ptr [r13+4], 8000000h
0x18008ba72  jnz     short loc_18008BA97
0x18008ba74  test    dword ptr [r9+60h], 40000h
0x18008ba7c  jnz     short loc_18008BA97
0x18008ba7e  lea     rdx, sqlite3ExprListDeleteGeneric
0x18008ba85  mov     rcx, r15
0x18008ba88  call    sqlite3ParserAddCleanup
0x18008ba8d  mov     qword ptr [rbx+48h], 0
0x18008ba95  jmp     short loc_18008BAB4
0x18008ba97  test    esi, esi
0x18008ba99  jnz     short loc_18008BAB4
0x18008ba9b  test    dword ptr [r13+4], 40000h
0x18008baa3  jz      short loc_18008BAB4
0x18008baa5  cmp     [r14], r12d
0x18008baa8  jz      short loc_18008BB06
0x18008baaa  test    byte ptr [r14+0ACh], 22h
0x18008bab2  jnz     short loc_18008BB06
0x18008bab4  mov     r9d, [rsp+1E0h+var_194]
0x18008bab9  mov     r8d, esi
0x18008babc  mov     rdx, r13
0x18008babf  mov     rcx, r15
0x18008bac2  call    flattenSubquery
0x18008bac7  xor     r9d, r9d
0x18008baca  test    eax, eax
0x18008bacc  jz      short loc_18008BADB
0x18008bace  cmp     [r15+30h], r9d
0x18008bad2  jnz     loc_18008B865
0x18008bad8  or      esi, 0FFFFFFFFh
0x18008badb  mov     r9, [rsp+1E0h+var_190]
0x18008bae0  cmp     byte ptr [r9+67h], 0
0x18008bae5  jnz     loc_18008B865
0x18008baeb  mov     rax, [rbp+0E0h+var_110]
0x18008baef  mov     r11d, 8
0x18008baf5  mov     r14, [r13+28h]
0x18008baf9  cmp     [rax], r11b
0x18008bafc  jbe     short loc_18008BB06
0x18008bafe  mov     rax, [r13+48h]
0x18008bb02  mov     qword ptr [rbp+0E0h+var_108], rax
0x18008bb06  add     esi, r12d
0x18008bb09  cmp     qword ptr [r13+50h], 0
0x18008bb0e  jz      loc_18008B8E3
0x18008bb14  mov     r8, [rbp+0E0h+var_110]
0x18008bb18  mov     rdx, r13
0x18008bb1b  mov     rcx, r15
0x18008bb1e  call    multiSelect
0x18008bb23  cmp     qword ptr [r13+58h], 0
0x18008bb28  mov     r9d, eax
0x18008bb2b  jnz     short loc_18008BB35
0x18008bb2d  mov     rcx, r15
0x18008bb30  call    sqlite3VdbeExplainPop
0x18008bb35  mov     eax, r9d
0x18008bb38  jmp     loc_18008D62C
0x18008bb3d  mov     r9, [rdx]
0x18008bb40  lea     rdx, aExpectedDColum; "expected %d columns for '%s' but got %d"
0x18008bb47  mov     dword ptr [rsp+1E0h+var_1C0], ecx
0x18008bb4b  mov     rcx, r15
0x18008bb4e  call    sqlite3ErrorMsg
0x18008bb53  jmp     loc_18008B865
0x18008bb58  mov     rax, [r13+30h]
0x18008bb5c  xor     r10d, r10d
0x18008bb5f  test    rax, rax
0x18008bb62  jz      short loc_18008BB81
0x18008bb64  cmp     byte ptr [rax], 2Ch ; ','
0x18008bb67  jnz     short loc_18008BB81
0x18008bb69  test    dword ptr [r9+60h], 8000h
0x18008bb71  jnz     short loc_18008BB81
0x18008bb73  mov     rdx, r13
0x18008bb76  mov     rcx, r15
0x18008bb79  call    propagateConstants
0x18008bb7e  xor     r10d, r10d
0x18008bb81  mov     rsi, [rsp+1E0h+var_190]
0x18008bb86  test    dword ptr [rsi+60h], 201h
0x18008bb8d  jnz     short loc_18008BBAF
0x18008bb8f  mov     rdx, r13
0x18008bb92  mov     rcx, r15
0x18008bb95  call    countOfViewOptimization
0x18008bb9a  xor     r10d, r10d
0x18008bb9d  test    eax, eax
0x18008bb9f  jz      short loc_18008BBAF
0x18008bba1  cmp     [rsi+67h], r10b
0x18008bba5  jnz     loc_18008B865
0x18008bbab  mov     r14, [r13+28h]
0x18008bbaf  lea     rcx, Src
0x18008bbb6  mov     r11d, r10d
0x18008bbb9  mov     [rsp+1E0h+var_198], r10d
0x18008bbbe  cmp     [r14], r10d
0x18008bbc1  jle     loc_18008C0B3
0x18008bbc7  movsxd  rax, r11d
  ... truncated ...
```
