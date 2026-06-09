# sqlite3Select

- ea: `0x180008860`
- end: `0x18000ab70`
- name: `sqlite3Select`
- size: `8976`
- prototype: ``
- caller_count: `13`
- callee_count: `75`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008860`
- `0x18000ab80`
- `0x18001bc30`
- `0x1800400d8`
- `0x180040990`
- `0x1800595f8`
- `0x1800620a0`
- `0x18007b8c8`
- `0x18007bf70`
- `0x1800840f4`
- `0x18008608c`
- `0x180086424`
- `0x18009bd98`

## callees

- `0x180006ac0`
- `0x180007a00`
- `0x180007ac4`
- `0x180007b00`
- `0x180007fcc`
- `0x180008860`
- `0x18000b4bc`
- `0x18000b5a8`
- `0x18000cbb8`
- `0x18000db18`
- `0x180014464`
- `0x180016b18`
- `0x18001ece0`
- `0x180031964`
- `0x180031c04`
- `0x180035db4`
- `0x180038974`
- `0x180038e54`
- `0x180039540`
- `0x180039ad8`
- `0x18003b410`
- `0x18003b5b4`
- `0x18003b8bc`
- `0x18003be78`
- `0x18003bf64`
- `0x18003bff4`
- `0x18003c028`
- `0x18003ca18`
- `0x18003da90`
- `0x18003dfe0`
- `0x18003e5b4`
- `0x18003ea4c`
- `0x18003f4f8`
- `0x18003fa48`
- `0x18003fbe4`
- `0x18003ff28`
- `0x18004002c`
- `0x180040990`
- `0x180041574`
- `0x180042260`
- `0x18004242c`
- `0x180042c38`
- `0x180042c68`
- `0x1800449f0`
- `0x180045374`
- `0x180052714`
- `0x18005a038`
- `0x18005b540`
- `0x18005cdfc`
- `0x18005f810`

## string_xrefs

- `0x180009fe4`: `USE TEMP B-TREE FOR %s`
- `0x18000a9fd`: `USE TEMP B-TREE FOR %s`

## pseudocode

```c
__int64 __fastcall sqlite3Select(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  __int64 v4; // r13
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v8; // rcx
  BOOL v9; // edi
  __int64 (__fastcall *v10)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  int v11; // eax
  int v12; // esi
  __int64 v13; // r8
  int v14; // esi
  __int64 v15; // r12
  const char *v16; // r8
  __int64 v17; // r8
  int *v18; // r11
  bool v19; // zf
  int v20; // r12d
  int *v21; // rsi
  size_t v22; // rdx
  int v23; // eax
  __int64 v24; // r9
  char v25; // al
  __int64 v26; // rdx
  int v27; // edx
  int v28; // r10d
  __int64 v29; // rcx
  char v30; // al
  __int64 v31; // rdx
  int i; // edx
  __int64 v33; // rcx
  _DWORD *v34; // rax
  int v35; // eax
  __int64 v36; // r11
  bool v37; // cc
  _BYTE *v38; // rax
  __int64 v39; // rsi
  unsigned int j; // r12d
  __int64 v41; // rcx
  int *v42; // rax
  int *v43; // r11
  __int64 v44; // rcx
  int *v45; // rsi
  unsigned int v46; // esi
  int v47; // r8d
  int *v48; // r9
  int v49; // eax
  int *v50; // rdx
  int v51; // eax
  int v52; // r8d
  _DWORD *v53; // rax
  int v54; // r9d
  _DWORD *v55; // rax
  int v56; // r8d
  int v57; // r9d
  _DWORD *v58; // rax
  int v59; // r9d
  unsigned int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // rax
  int v63; // ecx
  _DWORD *v64; // rsi
  int *v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // r12
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rsi
  int v72; // r8d
  int v73; // eax
  __int16 v74; // dx
  size_t v75; // r8
  int v76; // r12d
  __int64 v77; // rbx
  unsigned int v78; // r15d
  __int64 v79; // rdi
  char v80; // al
  int v81; // r8d
  _DWORD *v82; // r9
  unsigned int v83; // edi
  int v84; // ecx
  __int64 v85; // rax
  __int64 v86; // r12
  __int64 v87; // rax
  __int64 v88; // rdx
  int v89; // eax
  int v90; // edx
  __int64 v91; // rax
  unsigned int v92; // r12d
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rsi
  __int64 v96; // rdx
  size_t v97; // r8
  __int64 v98; // rcx
  char v99; // al
  int v100; // r13d
  size_t v101; // rbx
  unsigned int v102; // r15d
  __int64 v103; // rdi
  char v104; // al
  __int64 v105; // rdi
  __int64 v106; // rax
  int *v107; // r9
  __int16 v108; // ax
  __int64 v109; // rsi
  __int16 v110; // di
  __int64 v111; // rax
  __int64 v112; // rdi
  __int16 v113; // ax
  char v114; // al
  __int64 v115; // r8
  int v116; // edx
  int v117; // eax
  __int64 v118; // rax
  int v119; // eax
  int v120; // r9d
  int v121; // r13d
  int v122; // esi
  __int64 v123; // rcx
  int v124; // edx
  __int64 v125; // rcx
  int v126; // r13d
  __int64 v127; // rcx
  int v128; // esi
  __int64 v129; // rcx
  __int64 v130; // rdx
  int *v131; // rax
  int v132; // ecx
  _DWORD *k; // rdx
  int v134; // ecx
  _DWORD *m; // rdx
  int n; // r8d
  __int64 v137; // rdx
  int v138; // eax
  int v139; // eax
  size_t v140; // rdx
  __int64 v141; // rax
  int *v142; // rsi
  int v143; // eax
  int *v144; // rax
  int *v145; // r13
  _QWORD *v146; // r12
  int v147; // r15d
  _DWORD *v148; // r12
  _QWORD *v149; // r15
  int v150; // esi
  _DWORD *v151; // rax
  __int64 v152; // rdx
  unsigned __int8 v153; // al
  int v154; // eax
  size_t v155; // r13
  int v156; // esi
  size_t v157; // r12
  __int64 v158; // rax
  __int64 v159; // rdx
  int *v160; // rax
  __int64 v161; // rax
  __int64 v162; // rcx
  __int64 v163; // rdi
  __int64 v164; // rax
  __int64 v165; // rax
  __int16 v166; // cx
  int v167; // eax
  int v168; // ecx
  int v169; // eax
  int v170; // edx
  int v171; // r9d
  int *v172; // rax
  int v173; // ecx
  __int16 v174; // dx
  __int64 v175; // rcx
  _BYTE *v176; // r8
  size_t v177; // rsi
  int v178; // r9d
  int v179; // ecx
  unsigned int v180; // edi
  unsigned int v181; // eax
  int v182; // ecx
  const char *v183; // r9
  int v184; // edi
  unsigned int v185; // eax
  unsigned int v186; // r8d
  __int64 v187; // r11
  int v188; // r9d
  int v189; // edx
  unsigned int v190; // eax
  int v191; // eax
  int v192; // r10d
  size_t v193; // rdi
  int v194; // r13d
  int v195; // ebx
  unsigned int v196; // r12d
  __int64 v197; // rdx
  unsigned int TempReg; // edi
  unsigned int v199; // edi
  __int64 v200; // rcx
  unsigned int v201; // edx
  int v202; // edx
  int *v203; // rdi
  int v204; // r12d
  unsigned int v205; // ebx
  int v206; // r13d
  __int64 v207; // r8
  __int64 v208; // rax
  unsigned int v209; // edi
  __int64 Op; // rax
  __int64 v211; // rdx
  int v212; // esi
  int v213; // edi
  size_t v214; // rdi
  __int64 v215; // r8
  __int64 v216; // rax
  __int64 v217; // r9
  __int64 v218; // r8
  __int64 v219; // r10
  __int64 v220; // r9
  __int64 v221; // rsi
  __int64 v222; // rdx
  __int64 v223; // rcx
  __int16 v224; // ax
  int v225; // edi
  _DWORD *v226; // rcx
  int v227; // ecx
  int v228; // r9d
  __int64 v229; // r11
  __int64 v230; // r10
  int v231; // r8d
  int *v232; // rax
  __int64 v233; // rax
  size_t v234; // rsi
  __int64 v235; // r8
  __int64 v236; // rdi
  int v237; // edi
  __int64 v238; // r9
  int v239; // ecx
  __int64 v240; // rcx
  int v241; // r12d
  unsigned int v242; // r9d
  __int64 v243; // rdx
  int v244; // ecx
  __int64 v246; // rcx
  _QWORD *v247; // r8
  BOOL v248; // [rsp+40h] [rbp-C0h]
  unsigned int v249; // [rsp+40h] [rbp-C0h]
  int v250; // [rsp+40h] [rbp-C0h]
  int v251; // [rsp+40h] [rbp-C0h]
  int v252; // [rsp+40h] [rbp-C0h]
  unsigned int v253; // [rsp+40h] [rbp-C0h]
  unsigned int v254; // [rsp+40h] [rbp-C0h]
  __int16 v255; // [rsp+40h] [rbp-C0h]
  int v256; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v257; // [rsp+48h] [rbp-B8h]
  __int64 v258; // [rsp+50h] [rbp-B0h]
  size_t v259; // [rsp+58h] [rbp-A8h]
  unsigned __int8 v260; // [rsp+60h] [rbp-A0h]
  int *v261; // [rsp+68h] [rbp-98h]
  int *v262; // [rsp+70h] [rbp-90h]
  unsigned int v263; // [rsp+78h] [rbp-88h]
  int v264; // [rsp+7Ch] [rbp-84h]
  int v265; // [rsp+80h] [rbp-80h]
  size_t Size; // [rsp+88h] [rbp-78h]
  int v267; // [rsp+90h] [rbp-70h]
  unsigned int TempRange; // [rsp+94h] [rbp-6Ch]
  unsigned int v269; // [rsp+98h] [rbp-68h]
  int v270; // [rsp+9Ch] [rbp-64h]
  int v271; // [rsp+A0h] [rbp-60h]
  _DWORD *v272; // [rsp+A8h] [rbp-58h]
  unsigned int v273; // [rsp+B0h] [rbp-50h]
  unsigned int v274; // [rsp+B4h] [rbp-4Ch]
  __int64 v275; // [rsp+B8h] [rbp-48h]
  __int64 v276; // [rsp+C0h] [rbp-40h]
  __int64 v277; // [rsp+C8h] [rbp-38h]
  int v278; // [rsp+D0h] [rbp-30h]
  unsigned int v279; // [rsp+D4h] [rbp-2Ch]
  __int64 v280; // [rsp+D8h] [rbp-28h]
  int v281; // [rsp+E0h] [rbp-20h]
  _DWORD *v282; // [rsp+E8h] [rbp-18h]
  _OWORD v283[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v284; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v285[24]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v286; // [rsp+148h] [rbp+48h]
  __int64 v287; // [rsp+150h] [rbp+50h] BYREF
  __int64 v288; // [rsp+158h] [rbp+58h]
  _BYTE v289[56]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v290; // [rsp+198h] [rbp+98h] BYREF
  int v291; // [rsp+1A0h] [rbp+A0h]

  v3 = a1[2];
  v290 = 0;
  v291 = 0;
  v4 = a3;
  v287 = 0;
  v5 = a2;
  v6 = *a1;
  v258 = *a1;
  v277 = a3;
  v280 = a2;
  v275 = v3;
  memset(v283, 0, sizeof(v283));
  if ( !v3 )
  {
    if ( !a1[22] && (*(_BYTE *)(v6 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v3 = sqlite3VdbeCreate(a1);
    v275 = v3;
  }
  if ( !v5 || *((_DWORD *)a1 + 12) )
    return 1;
  v8 = *a1;
  v9 = 1;
  v10 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(*a1 + 512LL);
  if ( v10 )
  {
    if ( !*(_BYTE *)(v8 + 197) && !*((_BYTE *)a1 + 308) )
    {
      v11 = v10(*(_QWORD *)(v8 + 520), 21, 0, 0, 0, a1[47]);
      v12 = v11;
      if ( v11 == 1 )
      {
        sqlite3ErrorMsg(a1, "not authorized");
        *((_DWORD *)a1 + 6) = 23;
      }
      else if ( (v11 & 0xFFFFFFFD) != 0 )
      {
        v12 = 1;
        sqlite3ErrorMsg(a1, "authorizer malfunction");
        *((_DWORD *)a1 + 6) = 1;
      }
      if ( v12 )
        return 1;
    }
  }
  if ( *(_BYTE *)v4 <= 6u )
  {
    v13 = *(_QWORD *)(v5 + 72);
    if ( v13 )
    {
      sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v13);
      *(_QWORD *)(v5 + 72) = 0;
    }
    *(_DWORD *)(v5 + 4) &= ~1u;
    *(_DWORD *)(v5 + 4) |= 0x400000u;
  }
  sqlite3SelectPrep(a1, v5, 0);
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_406;
  v14 = *(_DWORD *)(v5 + 4);
  if ( (v14 & 0x800000) != 0 )
  {
    v15 = *(_QWORD *)(v5 + 40) + 8LL;
    if ( (unsigned int)sameSrcAlias(v15) )
    {
      v16 = *(const char **)(v15 + 24);
      if ( !v16 )
        v16 = **(const char ***)(v15 + 32);
      sqlite3ErrorMsg(a1, "target object/alias may not appear in FROM clause: %s", v16);
      goto LABEL_406;
    }
    *(_DWORD *)(v5 + 4) = v14 & 0xFF7FFFFF;
  }
  if ( *(_BYTE *)v4 == 9 )
    sqlite3GenerateColumnNames(a1, v5);
  if ( (unsigned int)sqlite3WindowRewrite(a1, v5) )
    goto LABEL_406;
  v18 = *(int **)(v5 + 40);
  v19 = (*(_DWORD *)(v5 + 4) & 8) == 0;
  v274 = *(_DWORD *)(v5 + 4) & 8;
  v262 = v18;
  v248 = !v19;
  v20 = 0;
  *(_QWORD *)&v283[0] = *(_QWORD *)(v5 + 72);
  memset((char *)v283 + 8, 0, 40);
  while ( 1 )
  {
    if ( *(_QWORD *)(v5 + 80) )
    {
      v242 = multiSelect(a1, (unsigned __int8 *)v5, (__int128 *)v4);
      if ( !*(_QWORD *)(v5 + 88) )
      {
        v243 = *((unsigned int *)a1 + 80);
        if ( (_DWORD)v243 )
          v244 = *(_DWORD *)(sqlite3VdbeGetOp(a1[2], v243) + 8);
        else
          v244 = 0;
        *((_DWORD *)a1 + 80) = v244;
      }
      return v242;
    }
    if ( v20 >= *v18 )
      break;
    v21 = &v18[26 * v20];
    v22 = *((_QWORD *)v21 + 5);
    v272 = (_DWORD *)*((_QWORD *)v21 + 6);
    v17 = *((unsigned __int8 *)v21 + 68);
    Size = v22;
    if ( (v17 & 0x48) != 0 )
    {
      v23 = sqlite3ExprImpliesNonNullRow(*(_QWORD *)(v5 + 48), (unsigned int)v21[19], v17 & 0x40);
      v24 = v258;
      if ( !v23 || (*(_DWORD *)(v258 + 96) & 0x2000) != 0 )
      {
        v18 = v262;
      }
      else
      {
        v25 = *((_BYTE *)v21 + 68);
        if ( (v25 & 8) != 0 )
        {
          if ( (v25 & 0x10) != 0 )
          {
            *((_BYTE *)v21 + 68) = v25 & 0xF7;
          }
          else
          {
            v26 = (unsigned int)v21[19];
            *((_BYTE *)v21 + 68) = v25 & 0xD7;
            unsetJoinExpr(*(_QWORD *)(v5 + 48), v26, 0, v24);
          }
        }
        v18 = v262;
        if ( (v21[17] & 0x40) != 0 )
        {
          v27 = *v262;
          v28 = v20 + 1;
          if ( v20 + 1 < *v262 )
          {
            do
            {
              v29 = 26LL * v28;
              v30 = v18[v29 + 17];
              if ( (v30 & 0x10) != 0 )
              {
                if ( (v30 & 8) != 0 )
                {
                  LOBYTE(v18[v29 + 17]) = v30 & 0xEF;
                }
                else
                {
                  v31 = (unsigned int)v18[v29 + 19];
                  LOBYTE(v18[v29 + 17]) = v30 & 0xCF;
                  unsetJoinExpr(*(_QWORD *)(v5 + 48), v31, 1, v24);
                }
              }
              v27 = *v18;
              ++v28;
            }
            while ( v28 < *v18 );
          }
          for ( i = v27 - 1; i >= 0; --i )
          {
            v33 = 26LL * (unsigned int)i;
            LOBYTE(v18[v33 + 17]) &= ~0x40u;
            if ( (v18[v33 + 17] & 0x10) != 0 )
              break;
          }
        }
      }
      v22 = Size;
    }
    else
    {
      v24 = v258;
    }
    if ( v272 )
    {
      v34 = (_DWORD *)*((_QWORD *)v272 + 4);
      v17 = (unsigned int)*(__int16 *)(v22 + 54);
      if ( (_DWORD)v17 != *v34 )
      {
        sqlite3ErrorMsg(a1, "expected %d columns for '%s' but got %d", v17, *(const char **)v22, *v34);
        goto LABEL_406;
      }
      if ( (v21[18] & 0x100) == 0 || *(_BYTE *)(*((_QWORD *)v21 + 13) + 18LL) )
      {
        v35 = v272[1];
        if ( (v35 & 8) == 0 )
        {
          v17 = *((_QWORD *)v272 + 9);
          if ( v17 )
          {
            if ( !*(_QWORD *)(v5 + 72) && *v18 <= 1
              || *((_QWORD *)v272 + 12)
              || ((*(_DWORD *)(v5 + 4) | v35) & 0x8000000) != 0
              || (*(_DWORD *)(v24 + 96) & 0x40000) != 0 )
            {
              if ( !v20 && (*(_DWORD *)(v5 + 4) & 0x40000) != 0 && (*v18 == 1 || (v18[43] & 0x22) != 0) )
                goto LABEL_75;
            }
            else
            {
              sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v17);
              *((_QWORD *)v272 + 9) = 0;
            }
          }
          if ( (unsigned int)flattenSubquery(a1, v5, (unsigned int)v20, v248) )
          {
            if ( *((_DWORD *)a1 + 12) )
              goto LABEL_406;
            v20 = -1;
          }
          v36 = v258;
          if ( *(_BYTE *)(v258 + 103) )
            goto LABEL_407;
          v37 = *(_BYTE *)v4 <= 8u;
          v18 = *(int **)(v5 + 40);
          v262 = v18;
          if ( !v37 )
            *(_QWORD *)&v283[0] = *(_QWORD *)(v5 + 72);
        }
      }
    }
LABEL_75:
    ++v20;
  }
  v38 = *(_BYTE **)(v5 + 48);
  v39 = v258;
  if ( v38 && *v38 == 44 && (*(_DWORD *)(v258 + 96) & 0x8000) == 0 )
  {
    propagateConstants(a1, v5);
    v18 = v262;
  }
  if ( (*(_DWORD *)(v258 + 96) & 0x201) == 0 )
  {
    if ( (unsigned int)countOfViewOptimization(a1, v5) )
    {
      v36 = v258;
      if ( *(_BYTE *)(v258 + 103) )
        goto LABEL_407;
      v18 = *(int **)(v5 + 40);
      v39 = v258;
      v262 = v18;
    }
    else
    {
      v18 = v262;
    }
  }
  for ( j = 0; (int)j < *v18; ++j )
  {
    v41 = 26LL * (int)j;
    memset(v285, 0, 21);
    v284 = 0;
    v42 = &v18[v41 + 2];
    v261 = v42;
    if ( !*(_QWORD *)&v18[v41 + 22] )
    {
      v17 = *((_QWORD *)v42 + 2);
      if ( v17 )
      {
        sqlite3AuthCheck((_DWORD)a1, 20, v17, (unsigned int)&Src, *((_QWORD *)v42 + 1));
        v18 = v262;
        v42 = v261;
      }
    }
    v259 = *((_QWORD *)v42 + 5);
    if ( v259 && !v42[12] )
    {
      v256 = 0;
      heightOfSelect(v5, &v256);
      *((_DWORD *)a1 + 79) += v256;
      if ( (*(_DWORD *)(v39 + 96) & 0x1000) == 0 )
      {
        if ( (v261[16] & 0x100) == 0 || (v44 = *((_QWORD *)v261 + 12), *(_BYTE *)(v44 + 18)) && *(int *)v44 < 2 )
        {
          pushDownWhereTerms((_DWORD)a1, v259, *(_QWORD *)(v5 + 48), (_DWORD)v43, j);
          v43 = v262;
        }
      }
      v19 = (*(_DWORD *)(v39 + 96) & 0x4000000) == 0;
      v45 = v261;
      if ( v19 )
      {
        disableUnusedSubqueryResultColumns(v261);
        v43 = v262;
      }
      v257 = a1[47];
      a1[47] = *((_QWORD *)v45 + 2);
      if ( (unsigned int)fromClauseTermCanBeCoroutine(a1, v43, j, *(unsigned int *)(v5 + 4)) )
      {
        v46 = *(_DWORD *)(v3 + 144);
        v47 = ++*((_DWORD *)a1 + 14);
        v261[13] = v47;
        sqlite3VdbeAddOp3(v3, 11, v47, 0, v46 + 1);
        v48 = v261;
        LOBYTE(v284) = 13;
        v49 = v261[13];
        v261[12] = v46 + 1;
        v9 = 1;
        DWORD1(v284) = v49;
        *((_QWORD *)&v284 + 1) = 0;
        *(_QWORD *)&v285[8] = 0;
        *(_DWORD *)v285 = 0;
        sqlite3VdbeExplain(a1, 1, "CO-ROUTINE %!S", v48);
        sqlite3Select(a1, v259, &v284);
        v50 = v261;
        *(_WORD *)(*((_QWORD *)v261 + 4) + 58LL) = *(_WORD *)(v259 + 2);
        v51 = HIDWORD(v284);
        v50[16] |= 0x20u;
        v52 = v50[13];
        v50[14] = v51;
        sqlite3VdbeAddOp3(v3, 68, v52, 0, 0);
        *(_BYTE *)(*(_QWORD *)(v3 + 24) + 31LL) = 0;
        *(_DWORD *)(*(_QWORD *)(v3 + 24) + 40LL) = 0;
        *(_DWORD *)(sqlite3VdbeGetOp(v3, v46) + 8) = *(_DWORD *)(v3 + 144);
        *((_BYTE *)a1 + 31) = 0;
        *((_DWORD *)a1 + 10) = 0;
      }
      else if ( (v45[16] & 0x100) != 0 && (v53 = (_DWORD *)*((_QWORD *)v45 + 12), v272 = v53, v54 = v53[1], v54 > 0) )
      {
        sqlite3VdbeAddOp3(v3, 10, v53[2], v54, 0);
        v55 = v272;
        v56 = v45[17];
        v57 = v272[3];
        if ( v56 != v57 )
        {
          sqlite3VdbeAddOp3(v3, 115, v56, v57, 0);
          v55 = v272;
        }
        *(_WORD *)(v259 + 2) = *((_WORD *)v55 + 8);
      }
      else
      {
        v58 = (_DWORD *)isSelfJoinView(v262, v45, 0, j);
        v272 = v58;
        if ( v58 )
        {
          v59 = v58[12];
          if ( v59 )
          {
            sqlite3VdbeAddOp3(v3, 10, v58[13], v59, 0);
            v58 = v272;
          }
          sqlite3VdbeAddOp3(v3, 115, v45[17], v58[17], 0);
          *(_WORD *)(v259 + 2) = *(_WORD *)(*((_QWORD *)v272 + 5) + 2LL);
        }
        else
        {
          ++*((_DWORD *)a1 + 14);
          v256 = 0;
          v45[13] = *((_DWORD *)a1 + 14);
          v60 = sqlite3VdbeAddOp3(v3, 9, 0, 0, 0);
          v45[16] |= 0x10u;
          v273 = v60;
          v19 = (v45[16] & 8) == 0;
          v249 = v60 + 1;
          v45[12] = v60 + 1;
          if ( v19 )
            v256 = sqlite3VdbeAddOp3(v3, 15, 0, 0, 0);
          DWORD1(v284) = v45[17];
          LOBYTE(v284) = 12;
          *((_QWORD *)&v284 + 1) = 0;
          *(_QWORD *)&v285[8] = 0;
          *(_DWORD *)v285 = 0;
          sqlite3VdbeExplain(a1, 1, "MATERIALIZE %!S", v45);
          sqlite3Select(a1, v259, &v284);
          *(_WORD *)(*((_QWORD *)v45 + 4) + 58LL) = *(_WORD *)(v259 + 2);
          if ( v256 )
            *(_DWORD *)(sqlite3VdbeGetOp(v3, (unsigned int)v256) + 8) = *(_DWORD *)(v3 + 144);
          sqlite3VdbeAddOp3(v3, 67, v45[13], v249, 0);
          *(_DWORD *)(sqlite3VdbeGetOp(v3, v273) + 8) = *(_DWORD *)(v3 + 144);
          *((_BYTE *)a1 + 31) = 0;
          *((_DWORD *)a1 + 10) = 0;
          if ( (v45[16] & 0x108) == 0x100 )
          {
            v61 = *((_QWORD *)v45 + 12);
            *(_DWORD *)(v61 + 4) = v45[12];
            *(_DWORD *)(v61 + 8) = v45[13];
            *(_DWORD *)(v61 + 12) = v45[17];
            *(_WORD *)(v61 + 16) = *(_WORD *)(v259 + 2);
          }
        }
      }
      v36 = v258;
      if ( *(_BYTE *)(v258 + 103) )
        goto LABEL_407;
      v256 = 0;
      heightOfSelect(v5, &v256);
      v62 = v257;
      v18 = v262;
      v39 = v258;
      *((_DWORD *)a1 + 79) -= v256;
      a1[47] = v62;
    }
  }
  v63 = *(_DWORD *)(v5 + 4);
  v64 = *(_DWORD **)(v5 + 32);
  v65 = *(int **)(v5 + 56);
  v276 = *(_QWORD *)(v5 + 48);
  v272 = *(_DWORD **)(v5 + 64);
  v282 = v64;
  v261 = v65;
  LOBYTE(v290) = v63 & 1;
  if ( (v63 & 9) == 1
    && !(unsigned int)sqlite3ExprListCompare(*(_QWORD *)&v283[0], v64, 0xFFFFFFFFLL)
    && !*(_QWORD *)(v5 + 112) )
  {
    v66 = v258;
    *(_DWORD *)(v5 + 4) &= ~1u;
    v67 = sqlite3ExprListDup(v66, v64, 0);
    *(_DWORD *)(v5 + 4) |= 8u;
    v261 = (int *)v67;
    *(_QWORD *)(v5 + 56) = v67;
    LOBYTE(v290) = 2;
  }
  v68 = *(_QWORD *)&v283[0];
  if ( *(_QWORD *)&v283[0] )
  {
    v69 = *a1;
    v250 = *v64 + 1;
    v256 = **(_DWORD **)&v283[0];
    v257 = v69;
    Size = 9 * (v256 + v250) - 8;
    v70 = sqlite3DbMallocRawNN(v69, Size + 40);
    v71 = v70;
    if ( v70 )
    {
      v72 = v256;
      *(_WORD *)(v70 + 6) = v256;
      v73 = v250 + v72;
      v74 = v72 + v250;
      v75 = Size;
      *(_WORD *)(v71 + 8) = v74;
      *(_QWORD *)(v71 + 24) = v71 + 8 * (v73 + 4LL);
      LOBYTE(v73) = *(_BYTE *)(v257 + 100);
      *(_QWORD *)(v71 + 16) = v257;
      *(_BYTE *)(v71 + 4) = v73;
      *(_DWORD *)v71 = 1;
      memset_0((void *)(v71 + 40), 0, v75);
LABEL_128:
      v257 = v68 + 8;
      v76 = v256;
      if ( v256 > 0 )
      {
        v77 = v257;
        v78 = 0;
        do
        {
          v79 = v78;
          *(_QWORD *)(v71 + 8LL * v78++ + 32) = sqlite3ExprNNCollSeq(a1, *(_QWORD *)v77);
          v80 = *(_BYTE *)(v77 + 16);
          v77 += 32;
          *(_BYTE *)(v79 + *(_QWORD *)(v71 + 24)) = v80;
        }
        while ( (int)v78 < v76 );
        v5 = v280;
        v3 = v275;
      }
    }
    else
    {
      v71 = sqlite3OomFault(v257);
      if ( v71 )
        goto LABEL_128;
    }
    v81 = *((_DWORD *)a1 + 13);
    v82 = v282;
    HIDWORD(v283[0]) = v81;
    *((_DWORD *)a1 + 13) = v81 + 1;
    v83 = sqlite3VdbeAddOp3(v3, 118, v81, *v82 + 1 + **(_DWORD **)&v283[0], 0);
    sqlite3VdbeChangeP4(v3, v83, v71);
    v64 = v282;
    DWORD2(v283[1]) = v83;
  }
  else
  {
    DWORD2(v283[1]) = -1;
  }
  if ( *(_BYTE *)v4 == 12 )
  {
    sqlite3VdbeAddOp3(v3, 118, *(_DWORD *)(v4 + 4), *v64, 0);
    if ( (*(_DWORD *)(v5 + 4) & 0x800) != 0 )
    {
      v84 = *v64;
      v85 = (unsigned int)(*v64 - 1);
      v256 = *v64 - 1;
      if ( v84 - 1 > 0 )
      {
        v86 = v258;
        do
        {
          v87 = (__int64)&v64[8 * v85];
          v257 = v87;
          if ( (*(_BYTE *)(v87 + 28) & 0x40) != 0 )
            break;
          if ( *(_QWORD *)(v87 + 8) )
          {
            sqlite3ExprDeleteNN(v86);
            v87 = v257;
          }
          v88 = *(_QWORD *)(v87 + 16);
          if ( v88 )
            sqlite3DbFreeNN(v86, v88);
          v89 = v256;
          --*v64;
          v85 = (unsigned int)(v89 - 1);
          v84 = *v64;
          v256 = v85;
        }
        while ( (int)v85 > 0 );
      }
      v90 = 0;
      if ( v84 > 0 )
      {
        do
        {
          v91 = 8LL * v90;
          if ( (v64[v91 + 7] & 0x40) == 0 )
            **(_BYTE **)&v64[v91 + 2] = 121;
          ++v90;
        }
        while ( v90 < *v64 );
      }
    }
  }
  v92 = *((_DWORD *)a1 + 17) - 1;
  *((_DWORD *)a1 + 17) = v92;
  v269 = v92;
  if ( (*(_DWORD *)(v5 + 4) & 0x4000) == 0 )
    *(_WORD *)(v5 + 2) = 320;
  if ( *(_QWORD *)(v5 + 96) )
    computeLimitRegisters(a1, v5, v92);
  if ( !*(_DWORD *)(v5 + 8) && (SDWORD2(v283[1]) & 0x80000000) == 0 )
  {
    *(_BYTE *)sqlite3VdbeGetOp(v3, DWORD2(v283[1])) = 119;
    BYTE4(v283[2]) |= 1u;
  }
  if ( (*(_BYTE *)(v5 + 4) & 1) != 0 )
  {
    v93 = *a1;
    HIDWORD(v290) = *((_DWORD *)a1 + 13);
    *((_DWORD *)a1 + 13) = HIDWORD(v290) + 1;
    v259 = *(_QWORD *)(v5 + 32);
    v257 = v93;
    v264 = *(_DWORD *)v259;
    Size = 9 * v264 + 1;
    v94 = sqlite3DbMallocRawNN(v93, Size + 40);
    v95 = v94;
    if ( v94 )
    {
      v96 = v264;
      v97 = Size;
      *(_WORD *)(v94 + 6) = v264;
      *(_QWORD *)(v94 + 24) = v94 + 8 * (v96 + 5);
      v98 = v257;
      *(_WORD *)(v94 + 8) = v96 + 1;
      v99 = *(_BYTE *)(v98 + 100);
      *(_QWORD *)(v95 + 16) = v98;
      *(_BYTE *)(v95 + 4) = v99;
      *(_DWORD *)v95 = 1;
      memset_0((void *)(v95 + 40), 0, v97);
LABEL_159:
      if ( v264 > 0 )
      {
        v100 = v264;
        v101 = v259 + 8;
        v102 = 0;
        do
        {
          v103 = v102;
          *(_QWORD *)(v95 + 8LL * v102++ + 32) = sqlite3ExprNNCollSeq(a1, *(_QWORD *)v101);
          v104 = *(_BYTE *)(v101 + 16);
          v101 += 32LL;
          *(_BYTE *)(v103 + *(_QWORD *)(v95 + 24)) = v104;
        }
        while ( (int)v102 < v100 );
        v5 = v280;
        v3 = v275;
        v4 = v277;
      }
    }
    else
    {
      v95 = sqlite3OomFault(v257);
      if ( v95 )
        goto LABEL_159;
    }
    v105 = (unsigned int)sqlite3VdbeAddOp3(v3, 118, HIDWORD(v290), 0, 0);
    sqlite3VdbeChangeP4(v3, v105, v95);
    v291 = v105;
    v106 = *(int *)(v3 + 144);
    if ( (int)v106 > 0 )
      *(_WORD *)(*(_QWORD *)(v3 + 136) + 24 * v106 - 22) = 8;
    BYTE1(v290) = 3;
  }
  else
  {
    BYTE1(v290) = 0;
  }
  v107 = v261;
  if ( !v274 && !v261 )
  {
    v108 = 0;
    v109 = *(_QWORD *)(v5 + 112);
    if ( (_BYTE)v290 )
      v108 = 256;
    v110 = v108 | *(_WORD *)(v5 + 4) & 0x4000;
    if ( v109 )
      sqlite3WindowCodeInit(a1, v5, v17, 0);
    v111 = sqlite3WhereBegin(
             (_DWORD)a1,
             (_DWORD)v262,
             v276,
             v283[0],
             *(_QWORD *)(v5 + 32),
             v5,
             v110,
             *(__int16 *)(v5 + 2));
    v112 = v111;
    if ( !v111 )
    {
      v9 = 1;
      goto LABEL_406;
    }
    v113 = *(_WORD *)(v111 + 72);
    if ( v113 < *(__int16 *)(v5 + 2) )
      *(_WORD *)(v5 + 2) = v113;
    if ( (_BYTE)v290 )
    {
      v114 = BYTE1(v290);
      if ( *(_BYTE *)(v112 + 67) )
        v114 = *(_BYTE *)(v112 + 67);
      BYTE1(v290) = v114;
    }
    v115 = *(_QWORD *)&v283[0];
    if ( *(_QWORD *)&v283[0] )
    {
      v116 = 0;
      if ( *(char *)(v112 + 65) >= 0 )
        v116 = *(char *)(v112 + 65);
      DWORD2(v283[0]) = v116;
      if ( (*(_BYTE *)(v112 + 68) & 4) != 0 )
      {
        v118 = *(unsigned __int8 *)(v112 + 64);
        if ( *(_QWORD *)(112 * v118 + v112 + 808) )
          v117 = *(_DWORD *)(v112 + 48);
        else
          v117 = *(_DWORD *)(112 * v118 + v112 + 768);
      }
      else
      {
        v117 = *(_DWORD *)(v112 + 48);
      }
      LODWORD(v283[2]) = v117;
      if ( v116 == **(_DWORD **)&v283[0] )
        v115 = 0;
      *(_QWORD *)&v283[0] = v115;
    }
    if ( (SDWORD2(v283[1]) & 0x80000000) == 0 && !v115 )
      sqlite3VdbeChangeToNoop(v3, DWORD2(v283[1]));
    if ( !v109 )
    {
      selectInnerLoop(
        (_DWORD)a1,
        v5,
        -1,
        (unsigned int)v283,
        (__int64)&v290,
        v4,
        *(_DWORD *)(v112 + 48),
        *(_DWORD *)(v112 + 52));
      sqlite3WhereEnd(v112);
      goto LABEL_391;
    }
    v119 = *((_DWORD *)a1 + 17);
    v256 = ++*((_DWORD *)a1 + 14);
    v120 = v256;
    v251 = v119 - 1;
    v121 = v119 - 2;
    v122 = v119 - 3;
    *((_DWORD *)a1 + 17) = v119 - 3;
    sqlite3WindowCodeStep((_DWORD)a1, v5, v112, v120, v119 - 1);
    sqlite3VdbeAddOp3(v3, 9, 0, v122, 0);
    v123 = *(_QWORD *)(v3 + 24);
    v124 = ~v251;
    if ( *(_DWORD *)(v123 + 68) + *(_DWORD *)(v123 + 72) >= 0 )
      *(_DWORD *)(*(_QWORD *)(v123 + 80) + 4LL * v124) = *(_DWORD *)(v3 + 144);
    else
      resizeResolveLabel(v123, v3, (unsigned int)v124);
    LODWORD(v283[2]) = 0;
    selectInnerLoop((_DWORD)a1, v5, -1, (unsigned int)v283, (__int64)&v290, v277, v121, v122);
    v125 = *(_QWORD *)(v3 + 24);
    v126 = ~v121;
    if ( *(_DWORD *)(v125 + 68) + *(_DWORD *)(v125 + 72) >= 0 )
      *(_DWORD *)(*(_QWORD *)(v125 + 80) + 4LL * v126) = *(_DWORD *)(v3 + 144);
    else
      resizeResolveLabel(v125, v3, (unsigned int)v126);
    sqlite3VdbeAddOp3(v3, 67, v256, 0, 0);
    v127 = *(_QWORD *)(v3 + 24);
    v128 = ~v122;
    if ( *(_DWORD *)(v127 + 68) + *(_DWORD *)(v127 + 72) < 0 )
    {
      resizeResolveLabel(v127, v3, (unsigned int)v128);
      v4 = v277;
LABEL_391:
      if ( BYTE1(v290) == 3 )
        sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
      if ( *(_QWORD *)&v283[0] )
        generateSortTail((_DWORD)a1, v5, (unsigned int)v283, *v282, v4);
      v240 = *(_QWORD *)(v3 + 24);
      v241 = ~v92;
      if ( *(_DWORD *)(v240 + 68) + *(_DWORD *)(v240 + 72) >= 0 )
        *(_DWORD *)(*(_QWORD *)(v240 + 80) + 4LL * v241) = *(_DWORD *)(v3 + 144);
      else
        resizeResolveLabel(v240, v3, (unsigned int)v241);
      v9 = *((_DWORD *)a1 + 12) > 0;
      goto LABEL_406;
    }
    v129 = *(_QWORD *)(v127 + 80);
    v4 = v277;
    v130 = v128;
LABEL_390:
    *(_DWORD *)(v129 + 4 * v130) = *(_DWORD *)(v3 + 144);
    goto LABEL_391;
  }
  v278 = 0;
  memset(v289, 0, sizeof(v289));
  if ( !v261 )
  {
    *(_WORD *)(v5 + 2) = 0;
LABEL_219:
    v9 = 1;
    goto LABEL_220;
  }
  v131 = *(int **)(v5 + 32);
  v132 = *v131;
  for ( k = v131 + 2; v132 > 0; k += 8 )
  {
    --v132;
    *((_WORD *)k + 13) = 0;
  }
  v134 = *v107;
  for ( m = v107 + 2; v134 > 0; m += 8 )
  {
    --v134;
    *((_WORD *)m + 13) = 0;
  }
  if ( *(__int16 *)(v5 + 2) > 66 )
    *(_WORD *)(v5 + 2) = 66;
  if ( !*(_QWORD *)&v283[0] || *v107 != **(_DWORD **)&v283[0] )
    goto LABEL_219;
  for ( n = 0; n < *v107; LOBYTE(v107[8 * v137 + 6]) = *(_BYTE *)(32 * v137 + *(_QWORD *)&v283[0] + 24) & 1 )
    v137 = n++;
  v138 = sqlite3ExprListCompare(v107, *(_QWORD *)&v283[0], 0xFFFFFFFFLL);
  v107 = v261;
  v9 = 1;
  if ( !v138 )
    v278 = 1;
LABEL_220:
  v36 = v258;
  v139 = *((_DWORD *)a1 + 17) - 1;
  *((_DWORD *)a1 + 17) = v139;
  v264 = v139;
  if ( *(_WORD *)(v36 + 420) >= 0x38u )
  {
    v140 = *(_QWORD *)(v36 + 472);
    v259 = v140;
    if ( v140 )
    {
      *(_QWORD *)(v36 + 472) = *(_QWORD *)v140;
      ++*(_DWORD *)(v36 + 432);
      Size = v140;
      goto LABEL_235;
    }
    v140 = *(_QWORD *)(v36 + 464);
    v259 = v140;
    if ( v140 )
    {
      *(_QWORD *)(v36 + 464) = *(_QWORD *)v140;
      ++*(_DWORD *)(v36 + 432);
      Size = v140;
      goto LABEL_235;
    }
    v140 = *(_QWORD *)(v36 + 456);
    v259 = v140;
    if ( v140 )
    {
      *(_QWORD *)(v36 + 456) = *(_QWORD *)v140;
      ++*(_DWORD *)(v36 + 432);
      Size = v140;
      goto LABEL_235;
    }
    v140 = *(_QWORD *)(v36 + 448);
    v259 = v140;
    if ( v140 )
    {
      v141 = *(_QWORD *)v140;
      ++*(_DWORD *)(v36 + 432);
      *(_QWORD *)(v36 + 448) = v141;
      Size = v140;
      goto LABEL_235;
    }
    ++*(_DWORD *)(v36 + 440);
LABEL_234:
    v259 = dbMallocRawFinish(v36, 56, v17, v107);
    v140 = v259;
    Size = v259;
    if ( !v259 )
    {
LABEL_236:
      v36 = v258;
      v107 = v261;
      goto LABEL_237;
    }
LABEL_235:
    *(_OWORD *)v140 = 0;
    *(_OWORD *)(v140 + 16) = 0;
    *(_OWORD *)(v140 + 32) = 0;
    *(_QWORD *)(v140 + 48) = 0;
    sqlite3ParserAddCleanup(a1, agginfoFree, v140);
    v140 = v259;
    goto LABEL_236;
  }
  if ( !*(_DWORD *)(v36 + 416) )
  {
    ++*(_DWORD *)(v36 + 436);
    goto LABEL_234;
  }
  if ( !*(_BYTE *)(v36 + 103) )
    goto LABEL_234;
  v140 = 0;
  Size = 0;
  v259 = 0;
LABEL_237:
  if ( !*(_BYTE *)(v36 + 103) )
  {
    v142 = v262;
    *(_DWORD *)(v140 + 52) = *(_DWORD *)(v5 + 16);
    *(_QWORD *)v289 = a1;
    *(_QWORD *)&v289[8] = v142;
    *(_QWORD *)&v289[16] = v140;
    memset(&v289[24], 0, 32);
    if ( v107 )
      v143 = *v107;
    else
      LOWORD(v143) = 0;
    *(_WORD *)(v140 + 2) = v143;
    v144 = v282;
    *(_QWORD *)(v140 + 16) = v107;
    if ( v144 && *v144 > 0 )
    {
      v145 = v144;
      v146 = v144 + 2;
      v147 = 0;
      do
      {
        sqlite3ExprAnalyzeAggregates(v289, *v146);
        ++v147;
        v146 += 4;
      }
      while ( v147 < *v145 );
      v3 = v275;
      v92 = v269;
      v4 = v277;
      v140 = v259;
      v107 = v261;
      v36 = v258;
    }
    if ( *(_QWORD *)&v283[0] && (int)**(_DWORD **)&v283[0] > 0 )
    {
      v148 = *(_DWORD **)&v283[0];
      v149 = (_QWORD *)(*(_QWORD *)&v283[0] + 8LL);
      v150 = 0;
      do
      {
        sqlite3ExprAnalyzeAggregates(v289, *v149);
        ++v150;
        v149 += 4;
      }
      while ( v150 < *v148 );
      v3 = v275;
      v92 = v269;
      LODWORD(v142) = (_DWORD)v262;
      v140 = v259;
      v107 = v261;
      v36 = v258;
    }
    v151 = v272;
    if ( v272 )
    {
      if ( v107 )
      {
        v152 = *(_QWORD *)(v5 + 64);
        *((_QWORD *)&v284 + 1) = havingToWhereExprCb;
        memset(v285, 0, sizeof(v285));
        *(_QWORD *)&v284 = a1;
        v286 = v5;
        sqlite3WalkExpr(&v284, v152);
        v276 = *(_QWORD *)(v5 + 48);
        v151 = v272;
      }
      sqlite3ExprAnalyzeAggregates(v289, v151);
      v140 = v259;
      v107 = v261;
      v36 = v258;
    }
    *(_DWORD *)(v140 + 36) = *(_DWORD *)(v140 + 32);
    if ( *(_QWORD *)(v5 + 56) || *(_QWORD *)(v5 + 64) || *(_DWORD *)(v140 + 48) != 1 )
    {
      v260 = 0;
    }
    else
    {
      v153 = minMaxQuery(v36, **(_QWORD **)(v140 + 40), &v287, v107);
      v140 = v259;
      v107 = v261;
      v36 = v258;
      v260 = v153;
    }
    v154 = *(_DWORD *)&v289[40] | 0x20000;
    *(_DWORD *)&v289[40] |= 0x20000u;
    if ( *(int *)(v140 + 48) > 0 )
    {
      v155 = v259;
      v156 = 0;
      v157 = Size;
      do
      {
        v257 = *(_QWORD *)(32LL * v156 + *(_QWORD *)(v157 + 40));
        sqlite3ExprAnalyzeAggList(v289, *(_QWORD *)(v257 + 32), v17, v107);
        v158 = v257;
        v159 = *(_QWORD *)(v257 + 16);
        if ( v159 )
        {
          sqlite3ExprAnalyzeAggList(v289, *(_QWORD *)(v159 + 32), v17, v107);
          v158 = v257;
        }
        if ( (*(_DWORD *)(v158 + 4) & 0x1000000) != 0 )
          sqlite3ExprAnalyzeAggregates(v289, *(_QWORD *)(*(_QWORD *)(v158 + 64) + 72LL));
        ++v156;
      }
      while ( v156 < *(_DWORD *)(v155 + 48) );
      v154 = *(_DWORD *)&v289[40];
      v92 = v269;
      v4 = v277;
      LODWORD(v142) = (_DWORD)v262;
      v140 = v259;
      v107 = v261;
      v36 = v258;
    }
    v19 = *(_BYTE *)(v36 + 103) == 0;
    *(_DWORD *)&v289[40] = v154 & 0xFFFDFFFF;
    if ( v19 )
    {
      if ( v107 )
      {
        v19 = *(_DWORD *)(v140 + 48) == 1;
        v257 = 0;
        v256 = 0;
        if ( v19 )
        {
          v160 = *(int **)(v140 + 40);
          if ( v160[4] >= 0 )
          {
            v161 = *(_QWORD *)v160;
            if ( v161 )
            {
              if ( (*(_DWORD *)(v161 + 4) & 0x1000) == 0 )
              {
                v162 = *(_QWORD *)(v161 + 32);
                if ( v162 )
                {
                  v163 = sqlite3ExprDup(v36, *(_QWORD *)(v162 + 8), 0);
                  v164 = sqlite3ExprListDup(v258, v261, 0);
                  v165 = sqlite3ExprListAppend(a1, v164, v163);
                  v166 = 0;
                  v257 = v165;
                  v9 = 1;
                  if ( v165 )
                    v166 = 1280;
                  v140 = v259;
                  LOWORD(v256) = v166;
                }
              }
            }
          }
        }
        *(_DWORD *)(v140 + 4) = (*((_DWORD *)a1 + 13))++;
        v288 = sqlite3KeyInfoFromExprList(a1, v261, 0, *(unsigned int *)(v140 + 32));
        v167 = sqlite3VdbeAddOp4(v3, 119, *(_DWORD *)(v259 + 4), *(unsigned __int16 *)(v259 + 2), 0, v288, -8);
        v168 = *((_DWORD *)a1 + 17);
        LODWORD(v262) = v167;
        v169 = *((_DWORD *)a1 + 14) + 1;
        v273 = v169;
        v279 = v168 - 1;
        v267 = v169 + 1;
        v170 = v169 + 3;
        *((_DWORD *)a1 + 17) = v168 - 2;
        *((_DWORD *)a1 + 14) = v169 + 3;
        v171 = v169 + 1;
        v274 = v168 - 2;
        v172 = v261;
        v271 = v170;
        v173 = v170 + *v261;
        *((_DWORD *)a1 + 14) = v173;
        v252 = v173;
        *((_DWORD *)a1 + 14) = *v172 + v173;
        sqlite3VdbeAddOp3(v3, 71, 0, v171, 0);
        sqlite3VdbeAddOp3(v3, 75, 0, v271 + 1, v271 + *v261);
        sqlite3VdbeAddOp3(v3, 10, v271, v274, 0);
        v174 = 64;
        if ( (_BYTE)v290 == 2 )
          v174 = 128;
        v276 = sqlite3WhereBegin(
                 (_DWORD)a1,
                 (_DWORD)v142,
                 v276,
                 (_DWORD)v261,
                 v257,
                 v5,
                 (unsigned __int16)v256 | (unsigned __int16)(v174 | ((_WORD)v278 << 9)),
                 0);
        v176 = (_BYTE *)v276;
        if ( !v276 )
        {
          if ( v257 )
            exprListDeleteNN(v258, v257);
          goto LABEL_406;
        }
        v177 = v259;
        v178 = v252 + 1;
        v19 = a1[12] == 0;
        v265 = v252 + 1;
        if ( !v19 )
        {
          optimizeAggregateUseOfIndexedExpr(v175, v5, v259, v289);
          v176 = (_BYTE *)v276;
          v178 = v265;
        }
        v179 = 0;
        *(_DWORD *)(v177 + 12) = *((_DWORD *)a1 + 14) + 1;
        *((_DWORD *)a1 + 14) += *(_DWORD *)(v177 + 32) + *(_DWORD *)(v177 + 48);
        v253 = (unsigned __int8)v176[67];
        if ( (char)v176[65] >= 0 )
          v179 = (char)v176[65];
        if ( v179 == *v261 )
        {
          v180 = 0;
          v181 = 0;
          v182 = 0;
          TempRange = 0;
          v270 = 0;
          v263 = 0;
        }
        else
        {
          if ( !(_BYTE)v290 || (v183 = "DISTINCT", (*(_BYTE *)(v5 + 4) & 1) != 0) )
            v183 = "GROUP BY";
          sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v183);
          v270 = 1;
          v184 = *(_DWORD *)(v177 + 32);
          v185 = *v261;
          v186 = v185;
          v281 = *v261;
          v263 = v185;
          if ( v184 > 0 )
          {
            v187 = 0;
            v188 = v185;
            do
            {
              v189 = *(__int16 *)(*(_QWORD *)(v177 + 24) + 24 * v187 + 22);
              v190 = v186 + 1;
              if ( v189 < v188 )
                v190 = v186;
              v187 = (unsigned int)(v187 + 1);
              v186 = v190;
              v191 = v188 + 1;
              if ( v189 < v188 )
                v191 = v188;
              v188 = v191;
            }
            while ( (int)v187 < v184 );
            v3 = v275;
            v263 = v186;
          }
          TempRange = sqlite3GetTempRange(a1, v186);
          sqlite3ExprCodeExprList((_DWORD)a1, v192, TempRange, 0, 0);
          v37 = *(_DWORD *)(v177 + 32) <= 0;
          *(_BYTE *)v177 = 1;
          LODWORD(v275) = 0;
          if ( !v37 )
          {
            v193 = Size;
            v194 = v281;
            v195 = v275;
            v196 = TempRange;
            do
            {
              v197 = *(_QWORD *)(v193 + 24) + 24LL * v195;
              if ( *(__int16 *)(v197 + 22) >= v194 )
                sqlite3ExprCode(a1, *(_QWORD *)(v197 + 8), v196 + v194++);
              ++v195;
            }
            while ( v195 < *(_DWORD *)(v193 + 32) );
            LODWORD(v5) = v280;
            v92 = v269;
            v4 = v277;
          }
          *(_BYTE *)v177 = 0;
          TempReg = sqlite3GetTempReg(a1);
          sqlite3VdbeAddOp3(v3, 97, TempRange, v263, TempReg);
          sqlite3VdbeAddOp3(v3, 139, *(_DWORD *)(v177 + 4), TempReg, 0);
          sqlite3ReleaseTempReg(a1, TempReg);
          v199 = v263;
          sqlite3ReleaseTempRange(v200, TempRange, v263);
          sqlite3WhereEnd(v276);
          v201 = *((_DWORD *)a1 + 13);
          *(_DWORD *)(v177 + 8) = v201;
          ++*((_DWORD *)a1 + 13);
          TempRange = v201;
          v263 = sqlite3GetTempReg(a1);
          sqlite3VdbeAddOp3(v3, 121, v202, v263, v199);
          sqlite3VdbeAddOp3(v3, 34, *(_DWORD *)(v177 + 4), v264, 0);
          v181 = v263;
          v182 = v270;
          v176 = (_BYTE *)v276;
          v178 = v265;
          v180 = TempRange;
          *(_BYTE *)(v177 + 1) = 1;
        }
        if ( a1[12] )
        {
          aggregateConvertIndexedExprRefToColumn(v177);
          v181 = v263;
          v182 = v270;
          v176 = (_BYTE *)v276;
          v178 = v265;
        }
        if ( v278 )
        {
          if ( (*(_BYTE *)(v258 + 96) & 4) == 0 && (v182 || (v176[68] & 8) != 0) )
          {
            *(_QWORD *)&v283[0] = 0;
            sqlite3VdbeChangeToNoop(v3, DWORD2(v283[1]));
            v182 = v270;
            v178 = v265;
          }
          v181 = v263;
        }
        v281 = *(_DWORD *)(v3 + 144);
        if ( v182 )
        {
          sqlite3VdbeAddOp3(v3, 133, *(_DWORD *)(v177 + 4), v181, v180);
          v178 = v265;
        }
        v203 = v261;
        LODWORD(v275) = 0;
        if ( *v261 > 0 )
        {
          v204 = v275;
          v205 = TempRange;
          v206 = v270;
          do
          {
            v207 = (unsigned int)(v178 + v204);
            if ( v206 )
            {
              sqlite3VdbeAddOp3(v3, 94, v205, v204, v207);
            }
            else
            {
              *(_BYTE *)v177 = 1;
              sqlite3ExprCode(a1, *(_QWORD *)&v203[8 * v204 + 2], v207);
            }
            v178 = v265;
            ++v204;
          }
          while ( v204 < *v203 );
          LODWORD(v5) = v280;
          v92 = v269;
          v4 = v277;
        }
        v208 = v288;
        if ( v288 )
          ++*(_DWORD *)v288;
        sqlite3VdbeAddOp4(v3, 90, v271 + 1, v178, *v203, v208, -8);
        v209 = *(_DWORD *)(v3 + 144);
        sqlite3VdbeAddOp3(v3, 14, v209 + 1, 0, v209 + 1);
        sqlite3VdbeAddOp3(a1[2], 79, v265, v271 + 1, *v261);
        sqlite3VdbeAddOp3(v3, 10, v267 + 1, v279, 0);
        sqlite3VdbeAddOp3(v3, 59, v267, v264, 0);
        sqlite3VdbeAddOp3(v3, 10, v271, v274, 0);
        Op = sqlite3VdbeGetOp(v3, v209);
        v211 = v273;
        *(_DWORD *)(Op + 8) = *(_DWORD *)(v3 + 144);
        updateAccumulator(a1, v211, v177, v253);
        sqlite3VdbeAddOp3(v3, 71, 1, v273, 0);
        if ( v270 )
        {
          sqlite3VdbeAddOp3(v3, 37, *(_DWORD *)(v177 + 4), v281, 0);
        }
        else
        {
          sqlite3WhereEnd(v276);
          sqlite3VdbeChangeToNoop(v3, (unsigned int)v262);
        }
        if ( v257 )
          exprListDeleteNN(v258, v257);
        sqlite3VdbeAddOp3(v3, 10, v267 + 1, v279, 0);
        sqlite3VdbeAddOp3(v3, 9, 0, v264, 0);
        v212 = *(_DWORD *)(v3 + 144);
        sqlite3VdbeAddOp3(v3, 71, 1, v267, 0);
        sqlite3VdbeAddOp3(v3, 67, v267 + 1, 0, 0);
        sqlite3VdbeResolveLabel(v3, v279);
        v213 = *(_DWORD *)(v3 + 144);
        sqlite3VdbeAddOp3(v3, 59, v273, v213 + 2, 0);
        sqlite3VdbeAddOp3(v3, 67, v267 + 1, 0, 0);
        finalizeAggFunctions(a1, v259);
        sqlite3ExprIfFalse(a1, v272, (unsigned int)++v213, 16);
        selectInnerLoop((_DWORD)a1, v5, -1, (unsigned int)v283, (__int64)&v290, v4, v213, v212);
        sqlite3VdbeAddOp3(v3, 67, v267 + 1, 0, 0);
        sqlite3VdbeResolveLabel(v3, v274);
        v214 = v259;
        resetAccumulator(a1);
        sqlite3VdbeAddOp3(v3, 71, 0, v273, 0);
        sqlite3VdbeAddOp3(v3, 67, v271, 0, 0);
        if ( (_WORD)v256 && v253 )
          fixDistinctOpenEph(
            a1,
            v253,
            *(unsigned int *)(*(_QWORD *)(v214 + 40) + 16LL),
            *(unsigned int *)(*(_QWORD *)(v214 + 40) + 20LL));
LABEL_387:
        v238 = *(_QWORD *)(v3 + 24);
        v239 = ~v264;
        if ( *(_DWORD *)(v238 + 68) + *(_DWORD *)(v238 + 72) < 0 )
        {
          resizeResolveLabel(*(_QWORD *)(v3 + 24), v3, (unsigned int)v239);
          goto LABEL_391;
        }
        v130 = v239;
        v129 = *(_QWORD *)(v238 + 80);
        goto LABEL_390;
      }
      if ( !*(_QWORD *)(v5 + 48) )
      {
        v215 = *(_QWORD *)(v5 + 32);
        if ( *(_DWORD *)v215 == 1 )
        {
          v216 = *(_QWORD *)(v5 + 40);
          if ( *(_DWORD *)v216 == 1 && !*(_QWORD *)(v216 + 48) && *(_DWORD *)(v140 + 48) == 1 && !*(_QWORD *)(v5 + 64) )
          {
            v217 = *(_QWORD *)(v216 + 40);
            v288 = v217;
            if ( !*(_BYTE *)(v217 + 63) )
            {
              v218 = *(_QWORD *)(v215 + 8);
              if ( *(_BYTE *)v218 == 0xA8
                && *(_QWORD *)(v218 + 56) == v140
                && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v140 + 40) + 8LL) + 4LL) & 0x100) != 0
                && (*(_DWORD *)(v218 + 4) & 0x1000004) == 0 )
              {
                v254 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(v217 + 96));
                LODWORD(v262) = *((_DWORD *)a1 + 13);
                v280 = v219;
                v257 = v219;
                *((_DWORD *)a1 + 13) = (_DWORD)v262 + 1;
                v256 = *(_DWORD *)(v220 + 40);
                sqlite3CodeVerifySchema(a1, v254);
                v221 = v288;
                sqlite3TableLock((_DWORD)a1, v254, *(_DWORD *)(v288 + 40), 0, *(_QWORD *)v288);
                if ( *(char *)(v221 + 48) >= 0 )
                {
                  v222 = v257;
                }
                else
                {
                  v222 = sqlite3PrimaryKeyIndex(v221);
                  v257 = v222;
                }
                if ( (*(_BYTE *)(*(_QWORD *)(v5 + 40) + 72LL) & 1) == 0 )
                {
                  v223 = *(_QWORD *)(v221 + 16);
                  if ( v223 )
                  {
                    do
                    {
                      if ( (*(_BYTE *)(v223 + 100) & 4) == 0 )
                      {
                        v224 = *(_WORD *)(v223 + 92);
                        if ( v224 < *(__int16 *)(v221 + 60)
                          && !*(_QWORD *)(v223 + 72)
                          && (!v222 || v224 < *(__int16 *)(v222 + 92)) )
                        {
                          v222 = v223;
                        }
                      }
                      v223 = *(_QWORD *)(v223 + 40);
                    }
                    while ( v223 );
                    v257 = v222;
                  }
                }
                if ( v222 )
                {
                  v256 = *(_DWORD *)(v222 + 88);
                  v280 = sqlite3KeyInfoOfIndex(a1, v222);
                }
                v225 = (int)v262;
                sqlite3VdbeAddOp4Int(v3, 112, (_DWORD)v262, v256, v254, 1);
                if ( v280 )
                  sqlite3VdbeChangeP4(v3, 0xFFFFFFFFLL, v280);
                v226 = (_DWORD *)v259;
                *(_DWORD *)(v259 + 12) = *((_DWORD *)a1 + 14) + 1;
                *((_DWORD *)a1 + 14) += v226[8] + v226[12];
                sqlite3VdbeAddOp3(v3, 98, v225, v226[3] + v226[8], 0);
                sqlite3VdbeAddOp3(v3, 122, v225, 0, 0);
                explainSimpleCount(a1, v221, v257);
LABEL_386:
                v237 = v264;
                *(_QWORD *)&v283[0] = 0;
                sqlite3ExprIfFalse(a1, v272, (unsigned int)v264, 16);
                selectInnerLoop((_DWORD)a1, v5, -1, 0, 0, v4, v237, v237);
                goto LABEL_387;
              }
            }
          }
        }
      }
      v19 = *(_DWORD *)(v140 + 36) == 0;
      v227 = *(_DWORD *)(v140 + 48);
      v256 = 0;
      v257 = 0;
      v255 = 0;
      if ( v19 )
      {
        if ( v227 == 1 )
        {
          v232 = *(int **)(v140 + 40);
          v231 = 1;
          if ( v232[4] >= 0 )
          {
            v257 = *(_QWORD *)(*(_QWORD *)v232 + 32LL);
            v255 = v257 != 0 ? 0x500 : 0;
          }
        }
        else
        {
          v231 = v227;
        }
      }
      else
      {
        v228 = 0;
        if ( v227 <= 0 )
        {
          v231 = v227;
LABEL_371:
          if ( v228 == v231 )
          {
            v256 = ++*((_DWORD *)a1 + 14);
            sqlite3VdbeAddOp3(v3, 71, 0, v256, 0);
            v140 = v259;
            v231 = *(_DWORD *)(v259 + 48);
          }
        }
        else
        {
          v229 = *(_QWORD *)(v140 + 40);
          while ( 1 )
          {
            v230 = 32LL * (unsigned int)v228;
            if ( (*(_DWORD *)(*(_QWORD *)(v230 + v229) + 4LL) & 0x1000000) == 0 )
            {
              v231 = v227;
              if ( (*(_BYTE *)(*(_QWORD *)(v230 + v229 + 8) + 4LL) & 0x20) != 0 )
                break;
            }
            ++v228;
            v231 = v227;
            if ( v228 >= v227 )
              goto LABEL_371;
          }
        }
      }
      *(_DWORD *)(v140 + 12) = *((_DWORD *)a1 + 14) + 1;
      *((_DWORD *)a1 + 14) += v231 + *(_DWORD *)(v140 + 32);
      resetAccumulator(a1);
      v233 = sqlite3WhereBegin((_DWORD)a1, (_DWORD)v142, v276, v287, v257, v5, v255 | v260, 0);
      v257 = v233;
      if ( v233 )
      {
        v234 = v259;
        LODWORD(v262) = *(unsigned __int8 *)(v233 + 67);
        updateAccumulator(a1, (unsigned int)v256, v259, (unsigned int)v262);
        if ( (_DWORD)v262 )
        {
          v235 = *(_QWORD *)(v234 + 40);
          if ( v235 )
            fixDistinctOpenEph(a1, (unsigned int)v262, *(unsigned int *)(v235 + 16), *(unsigned int *)(v235 + 20));
        }
        if ( v256 )
          sqlite3VdbeAddOp3(v3, 71, 1, v256, 0);
        v236 = v257;
        if ( v260 )
          sqlite3WhereMinMaxOptEarlyOut(v3, v257);
        sqlite3WhereEnd(v236);
        finalizeAggFunctions(a1, v234);
        goto LABEL_386;
      }
LABEL_406:
      v36 = v258;
    }
  }
LABEL_407:
  if ( v287 )
    exprListDeleteNN(v36, v287);
  v246 = *((int *)a1 + 80);
  if ( (_DWORD)v246 )
  {
    v247 = (_QWORD *)a1[2];
    if ( *(_BYTE *)(*v247 + 103LL) )
      *((_DWORD *)a1 + 80) = qword_1800C7590[1];
    else
      *((_DWORD *)a1 + 80) = *(_DWORD *)(v247[17] + 24 * v246 + 8);
    return v9;
  }
  else
  {
    *((_DWORD *)a1 + 80) = 0;
    return v9;
  }
}

```

## disassembly

```asm
0x180008860  push    rbp
0x180008862  push    rbx
0x180008863  push    r13
0x180008865  push    r14
0x180008867  push    r15
0x180008869  lea     rbp, [rsp-0C0h]
0x180008871  sub     rsp, 1C0h
0x180008878  mov     rax, cs:__security_cookie
0x18000887f  xor     rax, rsp
0x180008882  mov     [rbp+0E0h+var_38], rax
0x180008889  mov     r15, [rcx+10h]
0x18000888d  xor     eax, eax
0x18000888f  mov     [rbp+0E0h+var_48], rax
0x180008896  xorps   xmm0, xmm0
0x180008899  mov     [rbp+0E0h+var_40], eax
0x18000889f  mov     r13, r8
0x1800088a2  mov     [rbp+0E0h+var_90], rax
0x1800088a6  mov     rbx, rdx
0x1800088a9  mov     rax, [rcx]
0x1800088ac  mov     r14, rcx
0x1800088af  mov     [rsp+1E0h+var_190], rax
0x1800088b4  mov     [rbp+0E0h+var_118], r8
0x1800088b8  mov     [rbp+0E0h+var_108], rdx
0x1800088bc  mov     [rbp+0E0h+var_128], r15
0x1800088c0  movups  [rbp+0E0h+var_F0], xmm0
0x1800088c4  movups  [rbp+0E0h+var_E0], xmm0
0x1800088c8  movups  [rbp+0E0h+var_D0], xmm0
0x1800088cc  test    r15, r15
0x1800088cf  jnz     short loc_1800088F0
0x1800088d1  cmp     [rcx+0B0h], r15
0x1800088d8  jnz     short loc_1800088E4
0x1800088da  test    byte ptr [rax+60h], 8
0x1800088de  jnz     short loc_1800088E4
0x1800088e0  mov     byte ptr [rcx+23h], 1
0x1800088e4  call    sqlite3VdbeCreate
0x1800088e9  mov     r15, rax
0x1800088ec  mov     [rbp+0E0h+var_128], rax
0x1800088f0  mov     [rsp+1E0h+arg_18], rsi
0x1800088f8  mov     [rsp+1E0h+var_28], rdi
0x180008900  test    rbx, rbx
0x180008903  jz      loc_18000AB64
0x180008909  cmp     dword ptr [r14+30h], 0
0x18000890e  jnz     loc_18000AB64
0x180008914  mov     rcx, [r14]
0x180008917  mov     edi, 1
0x18000891c  mov     rax, [rcx+200h]
0x180008923  test    rax, rax
0x180008926  jz      loc_1800089AE
0x18000892c  cmp     byte ptr [rcx+0C5h], 0
0x180008933  jnz     short loc_1800089AE
0x180008935  cmp     byte ptr [r14+134h], 0
0x18000893d  jnz     short loc_1800089AE
0x18000893f  mov     rdx, [r14+178h]
0x180008946  xor     r9d, r9d
0x180008949  mov     rcx, [rcx+208h]
0x180008950  xor     r8d, r8d
0x180008953  mov     [rsp+1E0h+var_1B8], rdx
0x180008958  mov     edx, 15h
0x18000895d  mov     [rsp+1E0h+var_1C0], 0
0x180008966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000896b  mov     esi, eax
0x18000896d  cmp     eax, edi
0x18000896f  jnz     short loc_18000898A
0x180008971  lea     rdx, aNotAuthorized; "not authorized"
0x180008978  mov     rcx, r14
0x18000897b  call    sqlite3ErrorMsg
0x180008980  mov     dword ptr [r14+18h], 17h
0x180008988  jmp     short loc_1800089A6
0x18000898a  test    eax, 0FFFFFFFDh
0x18000898f  jz      short loc_1800089A6
0x180008991  lea     rdx, aAuthorizerMalf; "authorizer malfunction"
0x180008998  mov     rcx, r14
0x18000899b  mov     esi, edi
0x18000899d  call    sqlite3ErrorMsg
0x1800089a2  mov     [r14+18h], edi
0x1800089a6  test    esi, esi
0x1800089a8  jnz     loc_18000AB69
0x1800089ae  cmp     byte ptr [r13+0], 6
0x1800089b3  ja      short loc_1800089E0
0x1800089b5  mov     r8, [rbx+48h]
0x1800089b9  test    r8, r8
0x1800089bc  jz      short loc_1800089D5
0x1800089be  lea     rdx, sqlite3ExprListDeleteGeneric
0x1800089c5  mov     rcx, r14
0x1800089c8  call    sqlite3ParserAddCleanup
0x1800089cd  mov     qword ptr [rbx+48h], 0
0x1800089d5  and     dword ptr [rbx+4], 0FFFFFFFEh
0x1800089d9  or      dword ptr [rbx+4], 400000h
0x1800089e0  xor     r8d, r8d
0x1800089e3  mov     [rsp+1E0h+var_30], r12
0x1800089eb  mov     rdx, rbx
0x1800089ee  mov     rcx, r14
0x1800089f1  call    sqlite3SelectPrep
0x1800089f6  cmp     dword ptr [r14+30h], 0
0x1800089fb  jnz     loc_18000AAED
0x180008a01  mov     esi, [rbx+4]
0x180008a04  bt      esi, 17h
0x180008a08  jnb     short loc_180008A4B
0x180008a0a  mov     rdx, [rbx+28h]
0x180008a0e  lea     r12, [rdx+8]
0x180008a12  mov     rcx, r12
0x180008a15  call    sameSrcAlias
0x180008a1a  test    eax, eax
0x180008a1c  jz      short loc_180008A44
0x180008a1e  mov     r8, [r12+18h]
0x180008a23  test    r8, r8
0x180008a26  jnz     short loc_180008A30
0x180008a28  mov     rax, [r12+20h]
0x180008a2d  mov     r8, [rax]
0x180008a30  lea     rdx, aTargetObjectAl; "target object/alias may not appear in F"...
0x180008a37  mov     rcx, r14
0x180008a3a  call    sqlite3ErrorMsg
0x180008a3f  jmp     loc_18000AAED
0x180008a44  btr     esi, 17h
0x180008a48  mov     [rbx+4], esi
0x180008a4b  cmp     byte ptr [r13+0], 9
0x180008a50  jnz     short loc_180008A5D
0x180008a52  mov     rdx, rbx
0x180008a55  mov     rcx, r14
0x180008a58  call    sqlite3GenerateColumnNames
0x180008a5d  mov     rdx, rbx
0x180008a60  mov     rcx, r14
0x180008a63  call    sqlite3WindowRewrite
0x180008a68  test    eax, eax
0x180008a6a  jnz     loc_18000AAED
0x180008a70  mov     eax, [rbx+4]
0x180008a73  xorps   xmm0, xmm0
0x180008a76  mov     r11, [rbx+28h]
0x180008a7a  and     eax, 8
0x180008a7d  mov     [rbp+0E0h+var_12C], eax
0x180008a80  xorps   xmm1, xmm1
0x180008a83  mov     eax, 0
0x180008a88  mov     [rsp+1E0h+var_170], r11
0x180008a8d  setnz   al
0x180008a90  mov     qword ptr [rbp+0E0h+var_D0+8], 0
0x180008a98  mov     [rsp+1E0h+var_1A0], eax
0x180008a9c  xor     r12d, r12d
0x180008a9f  mov     rax, [rbx+48h]
0x180008aa3  mov     qword ptr [rbp+0E0h+var_F0], rax
0x180008aa7  movdqu  [rbp+0E0h+var_F0+8], xmm0
0x180008aac  movdqu  [rbp+0E0h+var_E0+8], xmm1
0x180008ab1  cmp     qword ptr [rbx+50h], 0
0x180008ab6  jnz     loc_18000AA74
0x180008abc  cmp     r12d, [r11]
0x180008abf  jge     loc_180008CEE
0x180008ac5  movsxd  rax, r12d
0x180008ac8  imul    rsi, rax, 68h ; 'h'
0x180008acc  add     rsi, r11
0x180008acf  mov     r8, [rsi+30h]
0x180008ad3  mov     rdx, [rsi+28h]
0x180008ad7  mov     [rbp+0E0h+var_138], r8
0x180008adb  movzx   r8d, byte ptr [rsi+44h]
0x180008ae0  mov     [rbp+0E0h+Size], rdx
0x180008ae4  test    r8b, 48h
0x180008ae8  jz      loc_180008C53
0x180008aee  mov     edx, [rsi+4Ch]
0x180008af1  and     r8d, 40h
0x180008af5  mov     rcx, [rbx+30h]
0x180008af9  call    sqlite3ExprImpliesNonNullRow
0x180008afe  mov     r9, [rsp+1E0h+var_190]
0x180008b03  test    eax, eax
0x180008b05  jz      loc_180008C49
0x180008b0b  test    dword ptr [r9+60h], 2000h
0x180008b13  jnz     loc_180008C49
0x180008b19  movzx   eax, byte ptr [rsi+44h]
0x180008b1d  test    al, 8
0x180008b1f  jz      short loc_180008B40
0x180008b21  test    al, 10h
0x180008b23  jz      short loc_180008B2C
0x180008b25  and     al, 0F7h
0x180008b27  mov     [rsi+44h], al
0x180008b2a  jmp     short loc_180008B40
0x180008b2c  mov     edx, [rsi+4Ch]
0x180008b2f  and     al, 0D7h
0x180008b31  mov     [rsi+44h], al
0x180008b34  xor     r8d, r8d
0x180008b37  mov     rcx, [rbx+30h]
0x180008b3b  call    unsetJoinExpr
0x180008b40  test    byte ptr [rsi+44h], 40h
0x180008b44  mov     r11, [rsp+1E0h+var_170]
0x180008b49  jz      short loc_180008BB5
0x180008b4b  mov     edx, [r11]
0x180008b4e  lea     r10d, [r12+1]
0x180008b53  cmp     r10d, edx
0x180008b56  jge     short loc_180008B99
0x180008b58  movsxd  rax, r10d
0x180008b5b  imul    rcx, rax, 68h ; 'h'
0x180008b5f  movzx   eax, byte ptr [rcx+r11+44h]
0x180008b65  test    al, 10h
0x180008b67  jz      short loc_180008B8E
0x180008b69  test    al, 8
0x180008b6b  jz      short loc_180008B76
0x180008b6d  and     al, 0EFh
0x180008b6f  mov     [rcx+r11+44h], al
0x180008b74  jmp     short loc_180008B8E
0x180008b76  mov     edx, [rcx+r11+4Ch]
0x180008b7b  and     al, 0CFh
0x180008b7d  mov     [rcx+r11+44h], al
0x180008b82  mov     r8d, edi
0x180008b85  mov     rcx, [rbx+30h]
0x180008b89  call    unsetJoinExpr
0x180008b8e  mov     edx, [r11]
0x180008b91  inc     r10d
0x180008b94  cmp     r10d, edx
0x180008b97  jl      short loc_180008B58
0x180008b99  sub     edx, edi
0x180008b9b  js      short loc_180008BB5
0x180008b9d  mov     eax, edx
0x180008b9f  imul    rcx, rax, 68h ; 'h'
0x180008ba3  and     byte ptr [rcx+r11+44h], 0BFh
0x180008ba9  test    byte ptr [rcx+r11+44h], 10h
0x180008baf  jnz     short loc_180008BB5
0x180008bb1  sub     edx, edi
0x180008bb3  jns     short loc_180008B9D
0x180008bb5  mov     rdx, [rbp+0E0h+Size]
0x180008bb9  mov     rcx, [rbp+0E0h+var_138]
0x180008bbd  test    rcx, rcx
0x180008bc0  jz      loc_180008CCA
0x180008bc6  mov     rax, [rcx+20h]
0x180008bca  movsx   r8d, word ptr [rdx+36h]
0x180008bcf  mov     r10d, [rax]
0x180008bd2  cmp     r8d, r10d
0x180008bd5  jnz     loc_180008CD2
0x180008bdb  test    dword ptr [rsi+48h], 100h
0x180008be2  jz      short loc_180008BF2
0x180008be4  mov     rax, [rsi+68h]
0x180008be8  cmp     byte ptr [rax+12h], 0
0x180008bec  jz      loc_180008CCA
0x180008bf2  mov     eax, [rcx+4]
0x180008bf5  test    al, 8
0x180008bf7  jnz     loc_180008CCA
0x180008bfd  mov     r8, [rcx+48h]
0x180008c01  test    r8, r8
0x180008c04  jz      short loc_180008C7A
0x180008c06  cmp     qword ptr [rbx+48h], 0
0x180008c0b  jnz     short loc_180008C12
0x180008c0d  cmp     [r11], edi
0x180008c10  jle     short loc_180008C5D
0x180008c12  cmp     qword ptr [rcx+60h], 0
0x180008c17  jnz     short loc_180008C5D
0x180008c19  or      eax, [rbx+4]
0x180008c1c  bt      eax, 1Bh
0x180008c20  jb      short loc_180008C5D
0x180008c22  test    dword ptr [r9+60h], 40000h
0x180008c2a  jnz     short loc_180008C5D
0x180008c2c  lea     rdx, sqlite3ExprListDeleteGeneric
0x180008c33  mov     rcx, r14
0x180008c36  call    sqlite3ParserAddCleanup
0x180008c3b  mov     rax, [rbp+0E0h+var_138]
0x180008c3f  mov     qword ptr [rax+48h], 0
0x180008c47  jmp     short loc_180008C7A
0x180008c49  mov     r11, [rsp+1E0h+var_170]
0x180008c4e  jmp     loc_180008BB5
0x180008c53  mov     r9, [rsp+1E0h+var_190]
0x180008c58  jmp     loc_180008BB9
0x180008c5d  test    r12d, r12d
0x180008c60  jnz     short loc_180008C7A
0x180008c62  test    dword ptr [rbx+4], 40000h
0x180008c69  jz      short loc_180008C7A
0x180008c6b  cmp     [r11], edi
0x180008c6e  jz      short loc_180008CCA
0x180008c70  test    byte ptr [r11+0ACh], 22h
0x180008c78  jnz     short loc_180008CCA
0x180008c7a  mov     r9d, [rsp+1E0h+var_1A0]
0x180008c7f  mov     r8d, r12d
0x180008c82  mov     rdx, rbx
0x180008c85  mov     rcx, r14
0x180008c88  call    flattenSubquery
0x180008c8d  test    eax, eax
0x180008c8f  jz      short loc_180008CA2
0x180008c91  cmp     dword ptr [r14+30h], 0
0x180008c96  jnz     loc_18000AAED
0x180008c9c  mov     r12d, 0FFFFFFFFh
0x180008ca2  mov     r11, [rsp+1E0h+var_190]
0x180008ca7  cmp     byte ptr [r11+67h], 0
0x180008cac  jnz     loc_18000AAF2
0x180008cb2  cmp     byte ptr [r13+0], 8
0x180008cb7  mov     r11, [rbx+28h]
0x180008cbb  mov     [rsp+1E0h+var_170], r11
0x180008cc0  jbe     short loc_180008CCA
0x180008cc2  mov     rax, [rbx+48h]
0x180008cc6  mov     qword ptr [rbp+0E0h+var_F0], rax
0x180008cca  inc     r12d
0x180008ccd  jmp     loc_180008AB1
0x180008cd2  mov     r9, [rdx]
0x180008cd5  mov     rcx, r14
0x180008cd8  lea     rdx, aExpectedDColum; "expected %d columns for '%s' but got %d"
0x180008cdf  mov     dword ptr [rsp+1E0h+var_1C0], r10d
0x180008ce4  call    sqlite3ErrorMsg
0x180008ce9  jmp     loc_18000AAED
0x180008cee  mov     rax, [rbx+30h]
0x180008cf2  mov     rsi, [rsp+1E0h+var_190]
0x180008cf7  test    rax, rax
0x180008cfa  jz      short loc_180008D1A
0x180008cfc  cmp     byte ptr [rax], 2Ch ; ','
0x180008cff  jnz     short loc_180008D1A
0x180008d01  test    dword ptr [rsi+60h], 8000h
0x180008d08  jnz     short loc_180008D1A
0x180008d0a  mov     rdx, rbx
0x180008d0d  mov     rcx, r14
  ... truncated ...
```
