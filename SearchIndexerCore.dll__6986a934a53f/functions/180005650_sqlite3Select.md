# sqlite3Select

- ea: `0x180005650`
- end: `0x180007189`
- name: `sqlite3Select`
- size: `6969`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `73`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000213c`
- `0x180005650`
- `0x18000e318`
- `0x1800504a8`
- `0x1800635fc`
- `0x1800658bc`
- `0x18006a580`
- `0x1800707f8`
- `0x1800711f4`
- `0x18007be68`
- `0x180080260`
- `0x180090b7c`
- `0x18009345c`

## callees

- `0x180004f44`
- `0x18000506c`
- `0x18000509c`
- `0x180005190`
- `0x180005650`
- `0x1800071dc`
- `0x180007ac0`
- `0x180008be8`
- `0x180009ac0`
- `0x18000d04c`
- `0x18000e594`
- `0x180011bcc`
- `0x1800136f0`
- `0x180014034`
- `0x180014270`
- `0x180015700`
- `0x180015eb0`
- `0x1800168c0`
- `0x180016c60`
- `0x180016d00`
- `0x180016ef0`
- `0x1800191d0`
- `0x18001b16c`
- `0x18001bb70`
- `0x18001bc40`
- `0x18001c170`
- `0x18001cb40`
- `0x18001e090`
- `0x18001f0f0`
- `0x18001f418`
- `0x180021b70`
- `0x18002319c`
- `0x18003d380`
- `0x180041d10`
- `0x180049d94`
- `0x18004a3f8`
- `0x18004a418`
- `0x18004a438`
- `0x18004a478`
- `0x18005279c`
- `0x180054778`
- `0x180054824`
- `0x1800579e4`
- `0x180057c70`
- `0x18005851c`
- `0x1800588ac`
- `0x1800589fc`
- `0x18005c8b4`
- `0x18005e938`
- `0x180062494`

## string_xrefs

- `0x1800067fa`: `USE TEMP B-TREE FOR %s`
- `0x180006d87`: `USE TEMP B-TREE FOR %s`

## pseudocode

```c
__int64 __fastcall sqlite3Select(__int64 a1, __int64 a2, __int128 *a3)
{
  __int64 v4; // r13
  __int64 v6; // rdi
  unsigned int v7; // r12d
  __int64 v8; // r8
  int v9; // ebx
  __int64 v10; // rsi
  const char *v11; // r8
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r10
  int *v20; // r14
  bool v21; // zf
  int v22; // esi
  __int64 v23; // r9
  __int64 v24; // rbx
  __int64 v25; // rax
  unsigned int *v26; // rdx
  int v27; // eax
  char v28; // al
  __int64 v29; // rdx
  int j; // r9d
  __int64 v31; // rdx
  char v32; // al
  unsigned int v33; // edx
  __int64 v34; // rcx
  int v35; // ecx
  int v36; // eax
  int v37; // eax
  _BYTE *v38; // rax
  int v39; // eax
  int v40; // r11d
  __int64 v41; // rcx
  __int64 v42; // rsi
  __int64 v43; // rbx
  int v44; // r11d
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // r8
  unsigned int v48; // edi
  int v49; // r8d
  int v50; // ecx
  __int64 v51; // rbx
  __int16 v52; // ax
  __int64 v53; // rbx
  int v54; // eax
  int v55; // r8d
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // rax
  int v61; // r9d
  __int64 v62; // rax
  int v63; // r9d
  _DWORD *v64; // rax
  int v65; // r9d
  int v66; // eax
  unsigned int v67; // eax
  __int64 v68; // r8
  int v69; // r9d
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rax
  int v75; // ecx
  unsigned int *v76; // rsi
  _DWORD *v77; // rbx
  int v78; // eax
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 v81; // rax
  int v82; // r8d
  __int64 v83; // r9
  int v84; // eax
  int v85; // ecx
  __int64 v86; // rsi
  unsigned int *v87; // rcx
  __int64 v88; // rsi
  signed int v89; // ecx
  __int64 v90; // rax
  int v91; // eax
  __int64 v92; // rax
  __int16 v93; // ax
  __int64 v94; // rsi
  __int16 v95; // bx
  __int64 v96; // rax
  __int64 v97; // rdx
  __int16 v98; // ax
  char v99; // al
  __int64 v100; // rcx
  int v101; // r8d
  __int64 v102; // rax
  int v103; // eax
  unsigned int v104; // ebx
  int v105; // esi
  unsigned int v106; // edi
  unsigned int v107; // r14d
  unsigned __int8 *v108; // rbx
  __int64 v109; // rdx
  __int64 v110; // rdx
  int *v111; // rax
  int v112; // ecx
  _DWORD *v113; // rdx
  int v114; // ecx
  _DWORD *v115; // rdx
  int v116; // r8d
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // rax
  __int64 v120; // rsi
  int v121; // eax
  unsigned int *v122; // rdx
  __int64 v123; // rax
  __int64 v124; // rdx
  int *v125; // rax
  __int64 v126; // rax
  __int64 v127; // rdx
  __int64 v128; // rbx
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  int v132; // r9d
  int v133; // r8d
  unsigned int v134; // eax
  int v135; // ecx
  unsigned int v136; // r9d
  unsigned int v137; // eax
  unsigned int v138; // ecx
  __int16 v139; // dx
  __int64 v140; // rcx
  __int64 v141; // r14
  int v142; // ecx
  bool v143; // sf
  unsigned int v144; // r14d
  const char *v145; // r9
  int v146; // eax
  unsigned int v147; // r14d
  unsigned int v148; // r9d
  int v149; // r8d
  int v150; // edx
  unsigned int v151; // eax
  int v152; // eax
  char v153; // r11
  __int64 v154; // rdx
  int v155; // ebx
  int v156; // edi
  unsigned int v157; // r13d
  __int64 v158; // rcx
  unsigned int TempReg; // ebx
  __int64 v160; // rcx
  __int64 v161; // rdx
  int v162; // edx
  int v163; // eax
  int v164; // r14d
  unsigned int v165; // r13d
  __int64 v166; // r8
  __int64 v167; // rax
  int v168; // edx
  unsigned int v169; // ebx
  unsigned int v170; // r14d
  __int64 v171; // r8
  __int64 v172; // r9
  __int64 Op; // rax
  __int64 v174; // r9
  __int64 v175; // rdx
  __int64 v176; // r14
  int v177; // edi
  int v178; // ebx
  unsigned int v179; // ebx
  __int64 v180; // rax
  __int64 v181; // r10
  __int64 v182; // rbx
  unsigned int v183; // eax
  __int64 v184; // r10
  __int64 v185; // r14
  __int64 i; // rcx
  __int16 v187; // ax
  int v188; // r8d
  unsigned int v189; // ebx
  int v190; // edx
  unsigned int v191; // ecx
  __int64 v192; // r9
  __int64 v193; // r8
  _DWORD *v194; // rax
  __int64 v195; // rax
  __int64 v196; // r14
  __int64 v197; // r8
  __int64 v198; // r8
  __int64 v199; // r9
  __int64 v200; // rdx
  int v201; // ecx
  unsigned __int8 v202; // [rsp+40h] [rbp-C0h]
  unsigned int v203; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v204; // [rsp+48h] [rbp-B8h]
  unsigned int v205; // [rsp+4Ch] [rbp-B4h]
  __int64 v206; // [rsp+50h] [rbp-B0h]
  int v207; // [rsp+58h] [rbp-A8h]
  int v208; // [rsp+5Ch] [rbp-A4h]
  unsigned int v209; // [rsp+60h] [rbp-A0h]
  unsigned int TempRange; // [rsp+64h] [rbp-9Ch]
  unsigned int v211; // [rsp+68h] [rbp-98h]
  __int64 v212; // [rsp+70h] [rbp-90h]
  unsigned int *v213; // [rsp+78h] [rbp-88h]
  unsigned int v214; // [rsp+80h] [rbp-80h]
  __int128 *v215; // [rsp+88h] [rbp-78h]
  unsigned int v216; // [rsp+90h] [rbp-70h]
  int v217; // [rsp+94h] [rbp-6Ch]
  __int64 v218; // [rsp+98h] [rbp-68h]
  __int64 v219; // [rsp+A0h] [rbp-60h]
  __int64 Vdbe; // [rsp+A8h] [rbp-58h]
  __int64 v221; // [rsp+B0h] [rbp-50h]
  int v222; // [rsp+B8h] [rbp-48h]
  unsigned int v223; // [rsp+BCh] [rbp-44h]
  _DWORD *v224; // [rsp+C0h] [rbp-40h]
  __int64 v225; // [rsp+C8h] [rbp-38h]
  __int128 v226; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v227; // [rsp+E0h] [rbp-20h]
  __int128 v228; // [rsp+F0h] [rbp-10h]
  __int64 v229; // [rsp+100h] [rbp+0h]
  __int128 v230; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v231[24]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v232; // [rsp+130h] [rbp+30h]
  __int64 v233; // [rsp+138h] [rbp+38h] BYREF
  __int64 v234; // [rsp+140h] [rbp+40h]
  _BYTE v235[56]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v236; // [rsp+180h] [rbp+80h] BYREF
  int v237; // [rsp+188h] [rbp+88h]

  v215 = a3;
  v236 = 0;
  v237 = 0;
  v206 = *(_QWORD *)a1;
  v4 = a2;
  v221 = a2;
  v226 = 0;
  v233 = 0;
  v227 = 0;
  v228 = 0;
  Vdbe = sqlite3GetVdbe(a1);
  v6 = Vdbe;
  if ( !v4 || *(_DWORD *)(a1 + 48) || (unsigned int)sqlite3AuthCheck(a1, 21, 0, 0, 0) )
    return 1;
  v7 = 1;
  if ( *(_BYTE *)a3 <= 6u )
  {
    v8 = *(_QWORD *)(v4 + 72);
    if ( v8 )
    {
      sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v8);
      *(_QWORD *)(v4 + 72) = 0;
    }
    *(_DWORD *)(v4 + 4) &= ~1u;
    *(_DWORD *)(v4 + 4) |= 0x400000u;
  }
  sqlite3SelectPrep(a1, v4, 0);
  if ( *(_DWORD *)(a1 + 48) )
    goto LABEL_14;
  v9 = *(_DWORD *)(v4 + 4);
  if ( (v9 & 0x800000) != 0 )
  {
    v10 = *(_QWORD *)(v4 + 40) + 8LL;
    if ( (unsigned int)sameSrcAlias(v10) )
    {
      v11 = *(const char **)(v10 + 24);
      if ( !v11 )
        v11 = **(const char ***)(v10 + 32);
      sqlite3ErrorMsg(a1, "target object/alias may not appear in FROM clause: %s", v11);
      goto LABEL_14;
    }
    *(_DWORD *)(v4 + 4) = v9 & 0xFF7FFFFF;
  }
  if ( *(_BYTE *)a3 == 9 )
    sqlite3GenerateColumnNames(a1, v4);
  v17 = sqlite3WindowRewrite(a1, v4);
  v19 = 0;
  if ( v17 )
  {
LABEL_14:
    sqlite3ExprListDeleteGeneric(v206, v233);
    v14 = *(unsigned int *)(a1 + 320);
    v15 = 0;
    if ( (_DWORD)v14 )
      v15 = *(_DWORD *)(sqlite3VdbeGetOp(*(_QWORD *)(a1 + 16), v14, v12, v13) + 8);
    *(_DWORD *)(a1 + 320) = v15;
    return v7;
  }
  v20 = *(int **)(v4 + 40);
  v21 = (*(_DWORD *)(v4 + 4) & 8) == 0;
  v207 = *(_DWORD *)(v4 + 4) & 8;
  v22 = 0;
  v204 = !v21;
  v226 = *(unsigned __int64 *)(v4 + 72);
  v227 = 0;
  v228 = 0;
  while ( 1 )
  {
    v23 = 256;
    if ( *(_QWORD *)(v4 + 80) != v19 )
      break;
    if ( v22 >= *v20 )
    {
      v38 = *(_BYTE **)(v4 + 48);
      if ( v38 && *v38 == 44 && (*(_DWORD *)(v206 + 96) & 0x8000) == 0 )
      {
        propagateConstants(a1, v4, v18, 256);
        v19 = 0;
      }
      if ( (*(_DWORD *)(v206 + 96) & 0x201) == 0 )
      {
        v39 = countOfViewOptimization(a1, v4, v18, v23);
        v19 = 0;
        if ( v39 )
        {
          if ( *(_BYTE *)(v206 + 103) )
            goto LABEL_14;
          v20 = *(int **)(v4 + 40);
        }
      }
      v40 = v19;
      while ( 2 )
      {
        v205 = v40;
        if ( v40 >= *v20 )
        {
          v75 = *(_DWORD *)(v4 + 4);
          v76 = *(unsigned int **)(v4 + 32);
          v77 = *(_DWORD **)(v4 + 56);
          v218 = *(_QWORD *)(v4 + 48);
          v225 = *(_QWORD *)(v4 + 64);
          v213 = v76;
          v224 = v77;
          LOBYTE(v236) = v75 & 1;
          if ( (v75 & 9) == 1 )
          {
            v78 = sqlite3ExprListCompare(v226, v76, 0xFFFFFFFFLL, v23);
            LODWORD(v19) = 0;
            if ( !v78 && !*(_QWORD *)(v4 + 112) )
            {
              v79 = v206;
              *(_DWORD *)(v4 + 4) &= ~1u;
              v80 = sqlite3ExprListDup(v79, v76, 0);
              *(_DWORD *)(v4 + 4) |= 8u;
              v77 = (_DWORD *)v80;
              LODWORD(v19) = 0;
              v224 = (_DWORD *)v80;
              *(_QWORD *)(v4 + 56) = v80;
              LOBYTE(v236) = 2;
            }
          }
          if ( (_QWORD)v226 )
          {
            v81 = sqlite3KeyInfoFromExprList(a1, v226, 0, *v76);
            HIDWORD(v226) = *(_DWORD *)(a1 + 52);
            v82 = HIDWORD(v226);
            *(_DWORD *)(a1 + 52) = HIDWORD(v226) + 1;
            DWORD2(v227) = sqlite3VdbeAddOp4(v6, 118, v82, *v76 + *(_DWORD *)v226 + 1, 0, v81, -8);
            LODWORD(v19) = 0;
          }
          else
          {
            DWORD2(v227) = -1;
          }
          if ( *(_BYTE *)v215 == 12 )
          {
            sqlite3VdbeAddOp3(v6, 118, *((_DWORD *)v215 + 1), *v76, v19);
            v83 = 0;
            if ( (*(_DWORD *)(v4 + 4) & 0x800) != 0 )
            {
              v84 = *v76;
              v85 = *v76 - 1;
              while ( 1 )
              {
                v203 = v85;
                if ( v85 <= 0 )
                  break;
                v86 = (unsigned int)v85;
                v87 = v213;
                v88 = 8 * v86;
                if ( (v213[v88 + 7] & 0x40) != 0 )
                {
                  v76 = v213;
                  break;
                }
                if ( *(_QWORD *)&v213[v88 + 2] )
                {
                  sqlite3ExprDeleteNN(v206);
                  v87 = v213;
                }
                sqlite3DbFree(v206, *(_QWORD *)&v87[v88 + 4]);
                v76 = v213;
                v85 = v203 - 1;
                --*v213;
                v84 = *v76;
                v83 = 0;
              }
              v89 = 0;
              if ( v84 > 0 )
              {
                do
                {
                  v90 = 8LL * v89;
                  if ( (v76[v90 + 7] & 0x40) == 0 )
                    **(_BYTE **)&v76[v90 + 2] = 121;
                  ++v89;
                }
                while ( v89 < (int)*v76 );
              }
            }
          }
          else
          {
            v83 = 0;
          }
          v91 = *(_DWORD *)(a1 + 68) - 1;
          *(_DWORD *)(a1 + 68) = v91;
          LODWORD(v219) = v91;
          if ( (*(_DWORD *)(v4 + 4) & 0x4000) == 0 )
            *(_WORD *)(v4 + 2) = 320;
          if ( *(_QWORD *)(v4 + 96) )
          {
            computeLimitRegisters(a1, v4, v91);
            v83 = 0;
          }
          if ( !*(_DWORD *)(v4 + 8) && (SDWORD2(v227) & 0x80000000) == 0 )
          {
            *(_BYTE *)sqlite3VdbeGetOp(v6, DWORD2(v227), v18, 0) = 119;
            BYTE4(v228) |= 1u;
          }
          if ( (*(_BYTE *)(v4 + 4) & 1) != 0 )
          {
            HIDWORD(v236) = *(_DWORD *)(a1 + 52);
            *(_DWORD *)(a1 + 52) = HIDWORD(v236) + 1;
            v92 = sqlite3KeyInfoFromExprList(a1, *(_QWORD *)(v4 + 32), 0, 0);
            v237 = sqlite3VdbeAddOp4(v6, 118, HIDWORD(v236), 0, 0, v92, -8);
            sqlite3VdbeChangeP5(v6, 8);
            v83 = 0;
            BYTE1(v236) = 3;
          }
          else
          {
            BYTE1(v236) = v83;
          }
          if ( v207 == (_DWORD)v83 && !v77 )
          {
            v93 = 256;
            if ( (_BYTE)v236 == (_BYTE)v83 )
              v93 = v83;
            v94 = *(_QWORD *)(v4 + 112);
            v95 = v93 | *(_WORD *)(v4 + 4) & 0x4000;
            if ( v94 )
              sqlite3WindowCodeInit(a1, v4);
            v96 = sqlite3WhereBegin(a1, (_DWORD)v20, v218, v226, *(_QWORD *)(v4 + 32), v4, v95, *(__int16 *)(v4 + 2));
            v212 = v96;
            v97 = v96;
            if ( v96 )
            {
              v98 = *(_WORD *)(v96 + 72);
              if ( v98 < *(__int16 *)(v4 + 2) )
                *(_WORD *)(v4 + 2) = v98;
              if ( (_BYTE)v236 )
              {
                v99 = BYTE1(v236);
                if ( *(_BYTE *)(v97 + 67) )
                  v99 = *(_BYTE *)(v97 + 67);
                BYTE1(v236) = v99;
              }
              v100 = v226;
              if ( (_QWORD)v226 )
              {
                v101 = 0;
                if ( *(char *)(v97 + 65) >= 0 )
                  v101 = *(char *)(v97 + 65);
                DWORD2(v226) = v101;
                if ( (*(_BYTE *)(v97 + 68) & 4) != 0
                  && (v102 = 112LL * *(unsigned __int8 *)(v97 + 64), !*(_QWORD *)(v102 + v97 + 808)) )
                {
                  v103 = *(_DWORD *)(v102 + v97 + 768);
                }
                else
                {
                  v103 = *(_DWORD *)(v97 + 48);
                }
                LODWORD(v228) = v103;
                if ( v101 == *(_DWORD *)v226 )
                  v100 = 0;
                *(_QWORD *)&v226 = v100;
              }
              if ( (SDWORD2(v227) & 0x80000000) == 0 && !v100 )
              {
                sqlite3VdbeChangeToNoop(v6, DWORD2(v227));
                v97 = v212;
              }
              if ( v94 )
              {
                v104 = *(_DWORD *)(a1 + 68);
                ++*(_DWORD *)(a1 + 56);
                --v104;
                v105 = *(_DWORD *)(a1 + 56);
                v106 = v104 - 1;
                v107 = v104 - 2;
                *(_DWORD *)(a1 + 68) = v104 - 2;
                sqlite3WindowCodeStep(a1, v4, v97, v105, v104);
                sqlite3VdbeAddOp3(Vdbe, 9, 0, v104 - 2, 0);
                sqlite3VdbeResolveLabel(Vdbe, v104);
                v108 = (unsigned __int8 *)v215;
                v7 = 0;
                LODWORD(v228) = 0;
                selectInnerLoop(a1, v4, -1, (unsigned int)&v226, (__int64)&v236, (__int64)v215, v106, v107);
                v109 = v106;
                v6 = Vdbe;
                sqlite3VdbeResolveLabel(Vdbe, v109);
                sqlite3VdbeAddOp3(v6, 67, v105, 0, 0);
                v110 = v107;
                goto LABEL_264;
              }
              v108 = (unsigned __int8 *)v215;
              selectInnerLoop(
                a1,
                v4,
                -1,
                (unsigned int)&v226,
                (__int64)&v236,
                (__int64)v215,
                *(_DWORD *)(v97 + 48),
                *(_DWORD *)(v97 + 52));
              sqlite3WhereEnd(v212);
              v7 = 0;
LABEL_265:
              if ( BYTE1(v236) == 3 )
                sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
              if ( (_QWORD)v226 )
                generateSortTail(a1, v4, (__int64)&v226, *v213, v108);
              sqlite3VdbeResolveLabel(v6, (unsigned int)v219);
              LOBYTE(v7) = *(_DWORD *)(a1 + 48) > 0;
            }
            goto LABEL_14;
          }
          v222 = v83;
          memset(v235, 0, sizeof(v235));
          if ( v77 )
          {
            v111 = *(int **)(v4 + 32);
            v112 = *v111;
            v113 = v111 + 2;
            while ( v112 > 0 )
            {
              *((_WORD *)v113 + 13) = v83;
              v113 += 8;
              --v112;
            }
            v114 = *v77;
            v115 = v77 + 2;
            while ( v114 > 0 )
            {
              *((_WORD *)v115 + 13) = v83;
              v115 += 8;
              --v114;
            }
            if ( *(__int16 *)(v4 + 2) > 66 )
              *(_WORD *)(v4 + 2) = 66;
            if ( (_QWORD)v226 && *v77 == *(_DWORD *)v226 )
            {
              v116 = v83;
              if ( (int)*v77 > 0 )
              {
                do
                {
                  v117 = v116++;
                  LOBYTE(v77[8 * v117 + 6]) = *(_BYTE *)(32 * v117 + v226 + 24) & 1;
                }
                while ( v116 < *v77 );
              }
              if ( !(unsigned int)sqlite3ExprListCompare(v77, v226, 0xFFFFFFFFLL, v83) )
                v222 = 1;
            }
          }
          else
          {
            *(_WORD *)(v4 + 2) = v83;
          }
          v118 = v206;
          v214 = *(_DWORD *)(a1 + 68) - 1;
          *(_DWORD *)(a1 + 68) = v214;
          v119 = sqlite3DbMallocZero(v118, 56);
          v120 = v119;
          if ( v119 )
            sqlite3ParserAddCleanup(a1, agginfoFree, v119);
          if ( *(_BYTE *)(v206 + 103) )
            goto LABEL_14;
          *(_DWORD *)(v120 + 52) = *(_DWORD *)(v4 + 16);
          *(_QWORD *)v235 = a1;
          *(_QWORD *)&v235[8] = v20;
          *(_QWORD *)&v235[16] = v120;
          memset(&v235[24], 0, 32);
          if ( v77 )
            v121 = *v77;
          else
            LOWORD(v121) = 0;
          v122 = v213;
          *(_WORD *)(v120 + 2) = v121;
          *(_QWORD *)(v120 + 16) = v77;
          sqlite3ExprAnalyzeAggList(v235, v122);
          sqlite3ExprAnalyzeAggList(v235, v226);
          v123 = v225;
          if ( v225 )
          {
            if ( v77 )
            {
              v124 = *(_QWORD *)(v4 + 64);
              *((_QWORD *)&v230 + 1) = havingToWhereExprCb;
              memset(v231, 0, sizeof(v231));
              *(_QWORD *)&v230 = a1;
              v232 = v4;
              sqlite3WalkExpr(&v230, v124);
              v218 = *(_QWORD *)(v4 + 48);
              v123 = v225;
            }
            sqlite3ExprAnalyzeAggregates(v235, v123);
          }
          *(_DWORD *)(v120 + 36) = *(_DWORD *)(v120 + 32);
          if ( *(_QWORD *)(v4 + 56) || *(_QWORD *)(v4 + 64) || *(_DWORD *)(v120 + 48) != 1 )
            v202 = 0;
          else
            v202 = minMaxQuery(v206, **(_QWORD **)(v120 + 40), &v233);
          analyzeAggFuncArgs(v120, v235);
          if ( *(_BYTE *)(v206 + 103) )
            goto LABEL_14;
          if ( v77 )
          {
            v229 = 0;
            v217 = 0;
            if ( *(_DWORD *)(v120 + 48) == 1 )
            {
              v125 = *(int **)(v120 + 40);
              if ( v125[4] >= 0 )
              {
                v126 = *(_QWORD *)v125;
                if ( v126 )
                {
                  if ( (*(_DWORD *)(v126 + 4) & 0x1000) == 0 )
                  {
                    v127 = *(_QWORD *)(v126 + 32);
                    if ( v127 )
                    {
                      v128 = sqlite3ExprDup(v206, *(_QWORD *)(v127 + 8), 0);
                      v129 = sqlite3ExprListDup(v206, v224, 0);
                      v130 = sqlite3ExprListAppend(a1, v129, v128);
                      v77 = v224;
                      v229 = v130;
                      if ( v130 )
                        LOWORD(v217) = 1280;
                      else
                        LOWORD(v217) = 0;
                    }
                  }
                }
              }
            }
            *(_DWORD *)(v120 + 4) = (*(_DWORD *)(a1 + 52))++;
            v131 = sqlite3KeyInfoFromExprList(a1, v77, 0, *(unsigned int *)(v120 + 32));
            v132 = *(unsigned __int16 *)(v120 + 2);
            v133 = *(_DWORD *)(v120 + 4);
            v234 = v131;
            v134 = sqlite3VdbeAddOp4(v6, 119, v133, v132, 0, v131, -8);
            v135 = *(_DWORD *)(a1 + 68);
            v223 = v134;
            v216 = *(_DWORD *)(a1 + 56) + 1;
            v205 = v135 - 1;
            v136 = v216 + 1;
            v209 = v216 + 2;
            v137 = v216 + 3;
            *(_DWORD *)(a1 + 56) = v216 + 3;
            *(_DWORD *)(a1 + 68) = v135 - 2;
            v203 = v137 + 1;
            v138 = v137 + *v77;
            *(_DWORD *)(a1 + 56) = v138;
            v204 = v138;
            *(_DWORD *)(a1 + 56) = *v77 + v138;
            sqlite3VdbeAddOp3(v6, 71, 0, v136, 0);
            sqlite3VdbeAddOp3(v6, 75, 0, v203, *v77 + v209 + 1);
            sqlite3VdbeAddOp3(v6, 10, v209 + 1, v205 - 1, 0);
            v139 = 128;
            if ( (_BYTE)v236 != 2 )
              v139 = 64;
            v212 = sqlite3WhereBegin(
                     a1,
                     (_DWORD)v20,
                     v218,
                     (_DWORD)v77,
                     v229,
                     v4,
                     v139 | (unsigned __int16)(v217 | ((_WORD)v222 << 9)),
                     0);
            v141 = v212;
            if ( !v212 )
            {
              sqlite3ExprListDeleteGeneric(v206, v229);
              goto LABEL_14;
            }
            v211 = v204 + 1;
            if ( *(_QWORD *)(a1 + 96) )
              optimizeAggregateUseOfIndexedExpr(v140, v4, v120, v235);
            v142 = 0;
            *(_DWORD *)(v120 + 12) = *(_DWORD *)(a1 + 56) + 1;
            *(_DWORD *)(a1 + 56) += *(_DWORD *)(v120 + 32) + *(_DWORD *)(v120 + 48);
            v143 = *(char *)(v141 + 65) < 0;
            v204 = *(unsigned __int8 *)(v141 + 67);
            if ( !v143 )
              v142 = *(char *)(v141 + 65);
            if ( v142 == *v77 )
            {
              v144 = 0;
              TempRange = 0;
              v207 = 0;
              v208 = 0;
            }
            else
            {
              if ( !(_BYTE)v236 || (v145 = "DISTINCT", (*(_BYTE *)(v4 + 4) & 1) != 0) )
                v145 = "GROUP BY";
              sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v145);
              v146 = *v77;
              v147 = v146;
              v208 = 1;
              v207 = v146;
              if ( *(int *)(v120 + 32) > 0 )
              {
                v148 = 0;
                v149 = v146;
                do
                {
                  v150 = *(__int16 *)(*(_QWORD *)(v120 + 24) + 24LL * v148 + 22);
                  v151 = v147 + 1;
                  if ( v150 < v149 )
                    v151 = v147;
                  ++v148;
                  v147 = v151;
                  v152 = v149 + 1;
                  if ( v150 < v149 )
                    v152 = v149;
                  v149 = v152;
                }
                while ( (signed int)v148 < *(_DWORD *)(v120 + 32) );
              }
              TempRange = sqlite3GetTempRange(a1, v147);
              sqlite3ExprCodeExprList(a1, (_DWORD)v77, TempRange, 0, v153);
              *(_BYTE *)v120 = 1;
              if ( *(int *)(v120 + 32) > 0 )
              {
                v155 = v207;
                v156 = 0;
                v157 = TempRange;
                do
                {
                  v158 = *(_QWORD *)(v120 + 24);
                  v154 = 3LL * v156;
                  if ( *(__int16 *)(v158 + 24LL * v156 + 22) >= v155 )
                  {
                    sqlite3ExprCode(a1, *(_QWORD *)(v158 + 24LL * v156 + 8), v155 + v157);
                    ++v155;
                  }
                  ++v156;
                }
                while ( v156 < *(_DWORD *)(v120 + 32) );
                v4 = v221;
                v6 = Vdbe;
              }
              *(_BYTE *)v120 = 0;
              TempReg = sqlite3GetTempReg(a1, v154);
              sqlite3VdbeAddOp3(v6, 97, TempRange, v147, TempReg);
              sqlite3VdbeAddOp3(v6, 139, *(_DWORD *)(v120 + 4), TempReg, 0);
              sqlite3ReleaseTempReg(a1, TempReg);
              sqlite3ReleaseTempRange(v160, TempRange, v147);
              sqlite3WhereEnd(v212);
              v161 = *(unsigned int *)(a1 + 52);
              *(_DWORD *)(v120 + 8) = v161;
              ++*(_DWORD *)(a1 + 52);
              TempRange = v161;
              v207 = sqlite3GetTempReg(a1, v161);
              sqlite3VdbeAddOp3(v6, 121, v162, v207, v147);
              sqlite3VdbeAddOp3(v6, 34, *(_DWORD *)(v120 + 4), v214, 0);
              v77 = v224;
              v144 = TempRange;
              *(_BYTE *)(v120 + 1) = 1;
            }
            if ( *(_QWORD *)(a1 + 96) )
              aggregateConvertIndexedExprRefToColumn(v120, 0);
            if ( v222 )
            {
              v163 = v208;
              if ( (*(_BYTE *)(v206 + 96) & 4) == 0 && (v208 || (*(_BYTE *)(v212 + 68) & 8) != 0) )
              {
                *(_QWORD *)&v226 = 0;
                sqlite3VdbeChangeToNoop(v6, DWORD2(v227));
                goto LABEL_246;
              }
            }
            else
            {
LABEL_246:
              v163 = v208;
            }
            LODWORD(v218) = *(_DWORD *)(v6 + 144);
            if ( v163 )
            {
              sqlite3VdbeAddOp3(v6, 133, *(_DWORD *)(v120 + 4), v207, v144);
              v163 = v208;
            }
            v164 = 0;
            if ( (int)*v77 > 0 )
            {
              v165 = TempRange;
              do
              {
                v166 = v164 + v211;
                if ( v163 )
                {
                  sqlite3VdbeAddOp3(v6, 94, v165, v164, v166);
                }
                else
                {
                  *(_BYTE *)v120 = 1;
                  sqlite3ExprCode(a1, *(_QWORD *)&v77[8 * v164 + 2], v166);
                }
                v163 = v208;
                ++v164;
              }
              while ( v164 < *v77 );
              v4 = v221;
            }
            v167 = sqlite3KeyInfoRef(v234);
            sqlite3VdbeAddOp4(v6, 90, v203, v211, v168, v167, -8);
            v169 = *(_DWORD *)(v6 + 144);
            sqlite3VdbeAddOp3(v6, 14, v169 + 1, 0, v169 + 1);
            sqlite3VdbeAddOp3(*(_QWORD *)(a1 + 16), 79, v211, v203, *v224);
            sqlite3VdbeAddOp3(v6, 10, v209, v205, 0);
            v170 = v214;
            sqlite3VdbeAddOp3(v6, 59, v216 + 1, v214, 0);
            sqlite3VdbeAddOp3(v6, 10, v209 + 1, v205 - 1, 0);
            Op = sqlite3VdbeGetOp(v6, v169, v171, v172);
            v174 = v204;
            v175 = v216;
            *(_DWORD *)(Op + 8) = *(_DWORD *)(v6 + 144);
            updateAccumulator(a1, v175, v120, v174);
            sqlite3VdbeAddOp3(v6, 71, 1, v216, 0);
            if ( v208 )
            {
              sqlite3VdbeAddOp3(v6, 37, *(_DWORD *)(v120 + 4), v218, 0);
            }
            else
            {
              sqlite3WhereEnd(v212);
              sqlite3VdbeChangeToNoop(v6, v223);
            }
            sqlite3ExprListDeleteGeneric(v206, v229);
            sqlite3VdbeAddOp3(v6, 10, v209, v205, 0);
            sqlite3VdbeAddOp3(v6, 9, 0, v170, 0);
            v176 = Vdbe;
            v177 = *(_DWORD *)(v6 + 144);
            sqlite3VdbeAddOp3(Vdbe, 71, 1, v216 + 1, 0);
            v7 = 0;
            sqlite3VdbeAddOp3(v176, 67, v209, 0, 0);
            sqlite3VdbeResolveLabel(v176, v205);
            v178 = *(_DWORD *)(v176 + 144);
            sqlite3VdbeAddOp3(v176, 59, v216, v178 + 2, 0);
            sqlite3VdbeAddOp3(v176, 67, v209, 0, 0);
            finalizeAggFunctions(a1, v120);
            sqlite3ExprIfFalse(a1, v225, (unsigned int)++v178, 16);
            selectInnerLoop(a1, v4, -1, (unsigned int)&v226, (__int64)&v236, (__int64)v215, v178, v177);
            v6 = Vdbe;
            v179 = v209;
            sqlite3VdbeAddOp3(Vdbe, 67, v209, 0, 0);
            sqlite3VdbeResolveLabel(v6, v205 - 1);
            resetAccumulator(a1, v120);
            sqlite3VdbeAddOp3(v6, 71, 0, v216, 0);
            sqlite3VdbeAddOp3(v6, 67, v179 + 1, 0, 0);
            if ( (_WORD)v217 && v204 )
              fixDistinctOpenEph(
                a1,
                v204,
                *(_DWORD *)(*(_QWORD *)(v120 + 40) + 16LL),
                *(_DWORD *)(*(_QWORD *)(v120 + 40) + 20LL));
            v108 = (unsigned __int8 *)v215;
          }
          else
          {
            v180 = isSimpleCount(v4, v120);
            v182 = v180;
            if ( v180 )
            {
              v183 = sqlite3SchemaToIndex(*(_QWORD *)a1, *(_QWORD *)(v180 + 96));
              v204 = v183;
              v185 = v184;
              v207 = *(_DWORD *)(a1 + 52);
              v221 = v184;
              *(_DWORD *)(a1 + 52) = v207 + 1;
              v211 = *(_DWORD *)(v182 + 40);
              sqlite3CodeVerifySchema(a1, v183);
              sqlite3TableLock(a1, v204, *(unsigned int *)(v182 + 40), 0, *(_QWORD *)v182);
              if ( *(char *)(v182 + 48) < 0 )
                v185 = sqlite3PrimaryKeyIndex(v182);
              if ( (*(_BYTE *)(*(_QWORD *)(v4 + 40) + 72LL) & 1) == 0 )
              {
                for ( i = *(_QWORD *)(v182 + 16); i; i = *(_QWORD *)(i + 40) )
                {
                  if ( (*(_BYTE *)(i + 100) & 4) == 0 )
                  {
                    v187 = *(_WORD *)(i + 92);
                    if ( v187 < *(__int16 *)(v182 + 60)
                      && !*(_QWORD *)(i + 72)
                      && (!v185 || v187 < *(__int16 *)(v185 + 92)) )
                    {
                      v185 = i;
                    }
                  }
                }
              }
              if ( v185 )
              {
                v211 = *(_DWORD *)(v185 + 88);
                v221 = sqlite3KeyInfoOfIndex(a1, v185);
              }
              sqlite3VdbeAddOp4Int(v6, 112, v207, v211, v204, 1);
              if ( v221 )
                sqlite3VdbeChangeP4(v6, 0xFFFFFFFFLL, v221, 4294967288LL);
              v188 = v207;
              *(_DWORD *)(v120 + 12) = *(_DWORD *)(a1 + 56) + 1;
              v7 = 0;
              *(_DWORD *)(a1 + 56) += *(_DWORD *)(v120 + 32) + *(_DWORD *)(v120 + 48);
              sqlite3VdbeAddOp3(v6, 98, v188, *(_DWORD *)(v120 + 12) + *(_DWORD *)(v120 + 32), 0);
              sqlite3VdbeAddOp3(v6, 122, v207, 0, 0);
              explainSimpleCount(a1, v182, v185);
            }
            else
            {
              v189 = v181;
              v190 = *(_DWORD *)(v120 + 48);
              v221 = v181;
              v204 = v181;
              if ( *(_DWORD *)(v120 + 36) == (_DWORD)v181 )
              {
                if ( v190 == 1 )
                {
                  v194 = *(_DWORD **)(v120 + 40);
                  v190 = 1;
                  if ( v194[4] >= (int)v181 )
                  {
                    v221 = *(_QWORD *)(*(_QWORD *)v194 + 32LL);
                    LOWORD(v204) = v221 != 0 ? 0x500 : 0;
                  }
                }
              }
              else
              {
                v191 = v181;
                if ( v190 <= 0 )
                {
LABEL_294:
                  if ( v191 == v190 )
                  {
                    v189 = ++*(_DWORD *)(a1 + 56);
                    sqlite3VdbeAddOp3(v6, 71, 0, v189, v181);
                    v190 = *(_DWORD *)(v120 + 48);
                  }
                }
                else
                {
                  v192 = *(_QWORD *)(v120 + 40);
                  while ( 1 )
                  {
                    v193 = 32LL * v191;
                    if ( (*(_DWORD *)(*(_QWORD *)(v193 + v192) + 4LL) & 0x1000000) == 0
                      && (*(_BYTE *)(*(_QWORD *)(v193 + v192 + 8) + 4LL) & 0x20) != 0 )
                    {
                      break;
                    }
                    if ( (int)++v191 >= v190 )
                      goto LABEL_294;
                  }
                }
              }
              *(_DWORD *)(v120 + 12) = *(_DWORD *)(a1 + 56) + 1;
              *(_DWORD *)(a1 + 56) += v190 + *(_DWORD *)(v120 + 32);
              resetAccumulator(a1, v120);
              v195 = sqlite3WhereBegin(a1, (_DWORD)v20, v218, v233, v221, v4, (unsigned __int16)v204 | v202, 0);
              v196 = v195;
              if ( !v195 )
                goto LABEL_14;
              v223 = *(unsigned __int8 *)(v195 + 67);
              updateAccumulator(a1, v189, v120, v223);
              if ( v223 )
              {
                v197 = *(_QWORD *)(v120 + 40);
                if ( v197 )
                  fixDistinctOpenEph(a1, v223, *(_DWORD *)(v197 + 16), *(_DWORD *)(v197 + 20));
              }
              if ( v189 )
                sqlite3VdbeAddOp3(v6, 71, 1, v189, 0);
              v7 = 0;
              if ( v202 )
                sqlite3WhereMinMaxOptEarlyOut(v6, v196);
              sqlite3WhereEnd(v196);
              finalizeAggFunctions(a1, v120);
            }
            *(_QWORD *)&v226 = 0;
            sqlite3ExprIfFalse(a1, v225, v214, 16);
            v108 = (unsigned __int8 *)v215;
            selectInnerLoop(a1, v4, -1, 0, 0, (__int64)v215, v214, v214);
          }
          v110 = v214;
LABEL_264:
          sqlite3VdbeResolveLabel(v6, v110);
          goto LABEL_265;
        }
        v41 = 26LL * v40;
        memset(v231, 0, 21);
        v230 = 0;
        v42 = (__int64)&v20[v41 + 2];
        if ( *(_QWORD *)&v20[v41 + 22] == v19 )
        {
          v18 = *(_QWORD *)(v42 + 16);
          if ( v18 )
          {
            sqlite3AuthCheck(a1, 20, v18, (unsigned int)&Src, *(_QWORD *)(v42 + 8));
            v40 = v205;
            v19 = 0;
          }
        }
        v43 = *(_QWORD *)(v42 + 40);
        v212 = v43;
        if ( v43 && *(_DWORD *)(v42 + 48) == (_DWORD)v19 )
        {
          v203 = v19;
          heightOfSelect(v4, &v203, v18, v23);
          v45 = v206;
          *(_DWORD *)(a1 + 316) += v203;
          if ( (*(_DWORD *)(v45 + 96) & 0x1000) == 0 )
          {
            if ( (*(_DWORD *)(v42 + 64) & 0x100) == 0
              || (v46 = *(_QWORD *)(v42 + 96), *(_BYTE *)(v46 + 18)) && *(int *)v46 < 2 )
            {
              pushDownWhereTerms(a1, v43, *(_QWORD *)(v4 + 48), (_DWORD)v20, v44);
              v45 = v206;
            }
          }
          if ( (*(_DWORD *)(v45 + 96) & 0x4000000) == 0 )
            disableUnusedSubqueryResultColumns(v42);
          v47 = v205;
          v225 = *(_QWORD *)(a1 + 376);
          *(_QWORD *)(a1 + 376) = *(_QWORD *)(v42 + 16);
          if ( (unsigned int)fromClauseTermCanBeCoroutine(a1, v20, v47, *(unsigned int *)(v4 + 4)) )
          {
            v48 = *(_DWORD *)(v6 + 144);
            v49 = ++*(_DWORD *)(a1 + 56);
            v50 = Vdbe;
            *(_DWORD *)(v42 + 52) = v49;
            sqlite3VdbeAddOp3(v50, 11, v49, 0, v48 + 1);
            DWORD1(v230) = *(_DWORD *)(v42 + 52);
            *(_DWORD *)(v42 + 48) = v48 + 1;
            *((_QWORD *)&v230 + 1) = 0;
            *(_QWORD *)&v231[8] = 0;
            *(_DWORD *)v231 = 0;
            LOBYTE(v230) = 13;
            sqlite3VdbeExplain(a1, 1, "CO-ROUTINE %!S", v42);
            v51 = v212;
            sqlite3Select(a1, v212, &v230);
            v52 = *(_WORD *)(v51 + 2);
            v53 = Vdbe;
            *(_WORD *)(*(_QWORD *)(v42 + 32) + 58LL) = v52;
            v54 = HIDWORD(v230);
            v55 = *(_DWORD *)(v42 + 52);
            *(_DWORD *)(v42 + 64) |= 0x20u;
            *(_DWORD *)(v42 + 56) = v54;
            sqlite3VdbeAddOp3(v53, 68, v55, 0, 0);
            v56 = v48;
            v6 = v53;
            *(_BYTE *)(*(_QWORD *)(v53 + 24) + 31LL) = 0;
            *(_DWORD *)(*(_QWORD *)(v53 + 24) + 40LL) = 0;
            *(_DWORD *)(sqlite3VdbeGetOp(v53, v56, v57, 0) + 8) = *(_DWORD *)(v53 + 144);
            *(_BYTE *)(a1 + 31) = v59;
            *(_DWORD *)(a1 + 40) = v59;
            goto LABEL_106;
          }
          if ( (*(_DWORD *)(v42 + 64) & 0x100) != 0 )
          {
            v60 = *(_QWORD *)(v42 + 96);
            v212 = v60;
            v61 = *(_DWORD *)(v60 + 4);
            if ( v61 > 0 )
            {
              sqlite3VdbeAddOp3(v6, 10, *(_DWORD *)(v60 + 8), v61, 0);
              v62 = v212;
              v58 = *(unsigned int *)(v42 + 68);
              v63 = *(_DWORD *)(v212 + 12);
              if ( (_DWORD)v58 != v63 )
              {
                sqlite3VdbeAddOp3(v6, 115, v58, v63, 0);
                v62 = v212;
              }
              *(_WORD *)(v43 + 2) = *(_WORD *)(v62 + 16);
              goto LABEL_99;
            }
          }
          v64 = (_DWORD *)isSelfJoinView(v20, v42, 0, v205);
          v212 = (__int64)v64;
          if ( v64 )
          {
            v65 = v64[12];
            if ( v65 )
            {
              sqlite3VdbeAddOp3(v6, 10, v64[13], v65, 0);
              v64 = (_DWORD *)v212;
            }
            sqlite3VdbeAddOp3(v6, 115, *(_DWORD *)(v42 + 68), v64[17], 0);
            *(_WORD *)(v43 + 2) = *(_WORD *)(*(_QWORD *)(v212 + 40) + 2LL);
LABEL_99:
            v59 = 0;
          }
          else
          {
            v66 = ++*(_DWORD *)(a1 + 56);
            v203 = 0;
            *(_DWORD *)(v42 + 52) = v66;
            v67 = sqlite3VdbeAddOp3(v6, 9, 0, 0, 0);
            *(_DWORD *)(v42 + 64) |= 0x10u;
            v211 = v67;
            v21 = (*(_BYTE *)(v42 + 64) & 8) == 0;
            v204 = v67 + 1;
            *(_DWORD *)(v42 + 48) = v67 + 1;
            if ( v21 )
              v203 = sqlite3VdbeAddOp3(v6, 15, 0, 0, 0);
            DWORD1(v230) = *(_DWORD *)(v42 + 68);
            LOBYTE(v230) = 12;
            *((_QWORD *)&v230 + 1) = 0;
            *(_QWORD *)&v231[8] = 0;
            *(_DWORD *)v231 = 0;
            sqlite3VdbeExplain(a1, 1, "MATERIALIZE %!S", v42);
            sqlite3Select(a1, v43, &v230);
            v69 = 0;
            *(_WORD *)(*(_QWORD *)(v42 + 32) + 58LL) = *(_WORD *)(v43 + 2);
            if ( v203 )
              *(_DWORD *)(sqlite3VdbeGetOp(v6, v203, v68, 0) + 8) = *(_DWORD *)(v6 + 144);
            sqlite3VdbeAddOp3(v6, 67, *(_DWORD *)(v42 + 52), v204, v69);
            v72 = sqlite3VdbeGetOp(v6, v211, v70, v71);
            v59 = 0;
            *(_DWORD *)(v72 + 8) = *(_DWORD *)(v6 + 144);
            *(_BYTE *)(a1 + 31) = 0;
            *(_DWORD *)(a1 + 40) = 0;
            if ( (*(_DWORD *)(v42 + 64) & 0x108) == 0x100 )
            {
              v73 = *(_QWORD *)(v42 + 96);
              *(_DWORD *)(v73 + 4) = *(_DWORD *)(v42 + 48);
              *(_DWORD *)(v73 + 8) = *(_DWORD *)(v42 + 52);
              *(_DWORD *)(v73 + 12) = *(_DWORD *)(v42 + 68);
              *(_WORD *)(v73 + 16) = *(_WORD *)(v43 + 2);
            }
          }
LABEL_106:
          if ( *(_BYTE *)(v206 + 103) != (_BYTE)v59 )
            goto LABEL_14;
          v203 = v59;
          heightOfSelect(v4, &v203, v58, v59);
          v74 = v225;
          v19 = 0;
          v40 = v205;
          *(_DWORD *)(a1 + 316) -= v203;
          *(_QWORD *)(a1 + 376) = v74;
        }
        ++v40;
        continue;
      }
    }
    v24 = 26LL * v22;
    v21 = (v20[v24 + 17] & 0x48) == 0;
    v25 = *(_QWORD *)&v20[v24 + 12];
    v26 = *(unsigned int **)&v20[v24 + 10];
    v219 = v25;
    v213 = v26;
    if ( !v21 )
    {
      v27 = sqlite3ExprImpliesNonNullRow(*(_QWORD *)(v4 + 48), (unsigned int)v20[v24 + 19], v20[v24 + 17] & 0x40, 256);
      v19 = 0;
      if ( v27 && (*(_DWORD *)(v206 + 96) & 0x2000) == 0 )
      {
        v28 = v20[v24 + 17];
        if ( (v28 & 8) != 0 )
        {
          if ( (v28 & 0x10) != 0 )
          {
            LOBYTE(v20[v24 + 17]) = v28 & 0xF7;
          }
          else
          {
            v29 = (unsigned int)v20[v24 + 19];
            LOBYTE(v20[v24 + 17]) = v28 & 0xD7;
            unsetJoinExpr(*(_QWORD *)(v4 + 48), v29, 0);
          }
        }
        if ( (v20[v24 + 17] & 0x40) != 0 )
        {
          for ( j = v22 + 1; ; ++j )
          {
            v33 = *v20;
            if ( j >= *v20 )
              break;
            v31 = 26LL * j;
            v32 = v20[v31 + 17];
            if ( (v32 & 0x10) != 0 )
            {
              if ( (v32 & 8) != 0 )
              {
                LOBYTE(v20[v31 + 17]) = v32 & 0xEF;
              }
              else
              {
                LOBYTE(v20[v31 + 17]) = v32 & 0xCF;
                unsetJoinExpr(*(_QWORD *)(v4 + 48), (unsigned int)v20[v31 + 19], 1);
              }
            }
          }
          do
          {
            if ( (--v33 & 0x80000000) != 0 )
              break;
            v34 = 26LL * v33;
            LOBYTE(v20[v34 + 17]) &= ~0x40u;
          }
          while ( (v20[v34 + 17] & 0x10) == 0 );
        }
      }
      v25 = v219;
      v26 = v213;
    }
    if ( v25 )
    {
      v18 = (unsigned int)*((__int16 *)v26 + 27);
      v35 = **(_DWORD **)(v25 + 32);
      if ( (_DWORD)v18 != v35 )
      {
        sqlite3ErrorMsg(a1, "expected %d columns for '%s' but got %d", v18, *(const char **)v26, v35);
        goto LABEL_14;
      }
      if ( (v20[v24 + 18] & 0x100) == 0 || *(_BYTE *)(*(_QWORD *)&v20[v24 + 26] + 18LL) != (_BYTE)v19 )
      {
        v36 = *(_DWORD *)(v219 + 4);
        if ( (v36 & 8) == 0 )
        {
          v18 = *(_QWORD *)(v219 + 72);
          if ( v18 )
          {
            if ( *(_QWORD *)(v4 + 72) == v19 && *v20 <= 1
              || *(_QWORD *)(v219 + 96) != v19
              || ((*(_DWORD *)(v4 + 4) | v36) & 0x8000000) != 0
              || (*(_DWORD *)(v206 + 96) & 0x40000) != 0 )
            {
              if ( !v22 && (*(_DWORD *)(v4 + 4) & 0x40000) != 0 && (*v20 == 1 || (v20[43] & 0x22) != 0) )
                goto LABEL_64;
            }
            else
            {
              sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric, v18);
              *(_QWORD *)(v219 + 72) = 0;
            }
          }
          v37 = flattenSubquery(a1, v4, (unsigned int)v22, v204);
          v19 = 0;
          if ( v37 )
          {
            if ( *(_DWORD *)(a1 + 48) )
              goto LABEL_14;
            v22 = -1;
          }
          if ( *(_BYTE *)(v206 + 103) )
            goto LABEL_14;
          v20 = *(int **)(v4 + 40);
          if ( *(_BYTE *)v215 > 8u )
            *(_QWORD *)&v226 = *(_QWORD *)(v4 + 72);
        }
      }
    }
LABEL_64:
    ++v22;
  }
  v199 = (unsigned int)multiSelect((__int64 *)a1, (unsigned __int8 *)v4, v215);
  if ( !*(_QWORD *)(v4 + 88) )
  {
    v200 = *(unsigned int *)(a1 + 320);
    if ( (_DWORD)v200 )
      v201 = *(_DWORD *)(sqlite3VdbeGetOp(*(_QWORD *)(a1 + 16), v200, v198, v199) + 8);
    else
      v201 = 0;
    *(_DWORD *)(a1 + 320) = v201;
  }
  return (unsigned int)v199;
}

```

## disassembly

```asm
0x180005650  mov     [rsp-8+arg_18], rbx
0x180005655  push    rbp
0x180005656  push    rsi
0x180005657  push    rdi
0x180005658  push    r12
0x18000565a  push    r13
0x18000565c  push    r14
0x18000565e  push    r15
0x180005660  lea     rbp, [rsp-0A0h]
0x180005668  sub     rsp, 1A0h
0x18000566f  mov     rax, cs:__security_cookie
0x180005676  xor     rax, rsp
0x180005679  mov     [rbp+0D0h+var_40], rax
0x180005680  xor     eax, eax
0x180005682  mov     [rbp+0D0h+var_148], r8
0x180005686  xorps   xmm0, xmm0
0x180005689  mov     [rbp+0D0h+var_50], rax
0x180005690  mov     [rbp+0D0h+var_48], eax
0x180005696  xor     ebx, ebx
0x180005698  mov     rax, [rcx]
0x18000569b  mov     r14, r8
0x18000569e  mov     [rsp+1D0h+var_180], rax
0x1800056a3  mov     r13, rdx
0x1800056a6  mov     [rbp+0D0h+var_120], rdx
0x1800056aa  mov     r15, rcx
0x1800056ad  movups  [rbp+0D0h+var_100], xmm0
0x1800056b1  mov     [rbp+0D0h+var_98], rbx
0x1800056b5  movups  [rbp+0D0h+var_F0], xmm0
0x1800056b9  movups  [rbp+0D0h+var_E0], xmm0
0x1800056bd  call    sqlite3GetVdbe
0x1800056c2  mov     [rbp+0D0h+var_128], rax
0x1800056c6  mov     rdi, rax
0x1800056c9  test    r13, r13
0x1800056cc  jz      loc_18000715A
0x1800056d2  cmp     [r15+30h], ebx
0x1800056d6  jnz     loc_18000715A
0x1800056dc  xor     r9d, r9d
0x1800056df  mov     [rsp+1D0h+var_1B0], rbx
0x1800056e4  xor     r8d, r8d
0x1800056e7  lea     edx, [rbx+15h]
0x1800056ea  mov     rcx, r15
0x1800056ed  call    sqlite3AuthCheck
0x1800056f2  test    eax, eax
0x1800056f4  jnz     loc_18000715A
0x1800056fa  cmp     byte ptr [r14], 6
0x1800056fe  lea     r12d, [rbx+1]
0x180005702  ja      short loc_18000572B
0x180005704  mov     r8, [r13+48h]
0x180005708  test    r8, r8
0x18000570b  jz      short loc_180005720
0x18000570d  lea     rdx, sqlite3ExprListDeleteGeneric
0x180005714  mov     rcx, r15
0x180005717  call    sqlite3ParserAddCleanup
0x18000571c  mov     [r13+48h], rbx
0x180005720  and     dword ptr [r13+4], 0FFFFFFFEh
0x180005725  bts     dword ptr [r13+4], 16h
0x18000572b  xor     r8d, r8d
0x18000572e  mov     rdx, r13
0x180005731  mov     rcx, r15
0x180005734  call    sqlite3SelectPrep
0x180005739  cmp     [r15+30h], ebx
0x18000573d  jnz     short loc_18000577C
0x18000573f  mov     ebx, [r13+4]
0x180005743  bt      ebx, 17h
0x180005747  jnb     short loc_1800057BA
0x180005749  mov     rdx, [r13+28h]
0x18000574d  lea     rsi, [rdx+8]
0x180005751  mov     rcx, rsi
0x180005754  call    sameSrcAlias
0x180005759  test    eax, eax
0x18000575b  jz      short loc_1800057B2
0x18000575d  mov     r8, [rsi+18h]
0x180005761  test    r8, r8
0x180005764  jnz     short loc_18000576D
0x180005766  mov     rax, [rsi+20h]
0x18000576a  mov     r8, [rax]
0x18000576d  lea     rdx, aTargetObjectAl; "target object/alias may not appear in F"...
0x180005774  mov     rcx, r15
0x180005777  call    sqlite3ErrorMsg
0x18000577c  mov     rdx, [rbp+0D0h+var_98]
0x180005780  mov     rcx, [rsp+1D0h+var_180]
0x180005785  call    sqlite3ExprListDeleteGeneric
0x18000578a  mov     edx, [r15+140h]
0x180005791  xor     eax, eax
0x180005793  test    edx, edx
0x180005795  jz      short loc_1800057A3
0x180005797  mov     rcx, [r15+10h]
0x18000579b  call    sqlite3VdbeGetOp
0x1800057a0  mov     eax, [rax+8]
0x1800057a3  mov     [r15+140h], eax
0x1800057aa  mov     eax, r12d
0x1800057ad  jmp     loc_18000715F
0x1800057b2  btr     ebx, 17h
0x1800057b6  mov     [r13+4], ebx
0x1800057ba  cmp     byte ptr [r14], 9
0x1800057be  jnz     short loc_1800057CB
0x1800057c0  mov     rdx, r13
0x1800057c3  mov     rcx, r15
0x1800057c6  call    sqlite3GenerateColumnNames
0x1800057cb  mov     rdx, r13
0x1800057ce  mov     rcx, r15
0x1800057d1  call    sqlite3WindowRewrite
0x1800057d6  xor     r10d, r10d
0x1800057d9  test    eax, eax
0x1800057db  jnz     short loc_18000577C
0x1800057dd  mov     eax, [r13+4]
0x1800057e1  xorps   xmm0, xmm0
0x1800057e4  mov     r14, [r13+28h]
0x1800057e8  and     eax, 8
0x1800057eb  mov     [rsp+1D0h+var_178], eax
0x1800057ef  mov     esi, r10d
0x1800057f2  mov     eax, r10d
0x1800057f5  setnz   al
0x1800057f8  mov     [rsp+1D0h+var_188], eax
0x1800057fc  mov     rax, [r13+48h]
0x180005800  movups  [rbp+0D0h+var_100], xmm0
0x180005804  mov     qword ptr [rbp+0D0h+var_100], rax
0x180005808  movups  [rbp+0D0h+var_F0], xmm0
0x18000580c  movups  [rbp+0D0h+var_E0], xmm0
0x180005810  mov     r9d, 100h
0x180005816  mov     ecx, 40h ; '@'
0x18000581b  cmp     [r13+50h], r10
0x18000581f  jnz     loc_180007119
0x180005825  cmp     esi, [r14]
0x180005828  jge     loc_180005A48
0x18000582e  movsxd  rax, esi
0x180005831  imul    rbx, rax, 68h ; 'h'
0x180005835  test    byte ptr [rbx+r14+44h], 48h
0x18000583b  mov     rax, [rbx+r14+30h]
0x180005840  mov     rdx, [rbx+r14+28h]
0x180005845  mov     [rbp+0D0h+var_130], rax
0x180005849  mov     [rsp+1D0h+var_158], rdx
0x18000584e  jz      loc_180005930
0x180005854  movzx   r8d, byte ptr [rbx+r14+44h]
0x18000585a  mov     edx, [rbx+r14+4Ch]
0x18000585f  and     r8d, ecx
0x180005862  mov     rcx, [r13+30h]
0x180005866  call    sqlite3ExprImpliesNonNullRow
0x18000586b  xor     r10d, r10d
0x18000586e  test    eax, eax
0x180005870  jz      loc_180005921
0x180005876  mov     rax, [rsp+1D0h+var_180]
0x18000587b  test    dword ptr [rax+60h], 2000h
0x180005882  jnz     loc_180005921
0x180005888  mov     al, [rbx+r14+44h]
0x18000588d  test    al, 8
0x18000588f  jz      short loc_1800058B6
0x180005891  test    al, 10h
0x180005893  jz      short loc_18000589E
0x180005895  and     al, 0F7h
0x180005897  mov     [rbx+r14+44h], al
0x18000589c  jmp     short loc_1800058B6
0x18000589e  mov     edx, [rbx+r14+4Ch]
0x1800058a3  and     al, 0D7h
0x1800058a5  mov     [rbx+r14+44h], al
0x1800058aa  xor     r8d, r8d
0x1800058ad  mov     rcx, [r13+30h]
0x1800058b1  call    unsetJoinExpr
0x1800058b6  mov     edx, 40h ; '@'
0x1800058bb  test    [rbx+r14+44h], dl
0x1800058c0  jz      short loc_180005921
0x1800058c2  lea     r9d, [rsi+1]
0x1800058c6  jmp     short loc_180005900
0x1800058c8  movsxd  rax, r9d
0x1800058cb  imul    rdx, rax, 68h ; 'h'
0x1800058cf  mov     al, [rdx+r14+44h]
0x1800058d4  test    al, 10h
0x1800058d6  jz      short loc_1800058FD
0x1800058d8  test    al, 8
0x1800058da  jz      short loc_1800058E5
0x1800058dc  and     al, 0EFh
0x1800058de  mov     [rdx+r14+44h], al
0x1800058e3  jmp     short loc_1800058FD
0x1800058e5  and     al, 0CFh
0x1800058e7  mov     r8d, r12d
0x1800058ea  mov     [rdx+r14+44h], al
0x1800058ef  mov     edx, [rdx+r14+4Ch]
0x1800058f4  mov     rcx, [r13+30h]
0x1800058f8  call    unsetJoinExpr
0x1800058fd  add     r9d, r12d
0x180005900  mov     edx, [r14]
0x180005903  cmp     r9d, edx
0x180005906  jl      short loc_1800058C8
0x180005908  sub     edx, r12d
0x18000590b  js      short loc_180005921
0x18000590d  mov     eax, edx
0x18000590f  imul    rcx, rax, 68h ; 'h'
0x180005913  and     byte ptr [rcx+r14+44h], 0BFh
0x180005919  test    byte ptr [rcx+r14+44h], 10h
0x18000591f  jz      short loc_180005908
0x180005921  mov     rax, [rbp+0D0h+var_130]
0x180005925  mov     r9d, 100h
0x18000592b  mov     rdx, [rsp+1D0h+var_158]
0x180005930  test    rax, rax
0x180005933  jz      loc_180005A25
0x180005939  mov     rax, [rax+20h]
0x18000593d  movsx   r8d, word ptr [rdx+36h]
0x180005942  mov     ecx, [rax]
0x180005944  cmp     r8d, ecx
0x180005947  jnz     loc_180005A2D
0x18000594d  test    [rbx+r14+48h], r9d
0x180005952  jz      short loc_180005963
0x180005954  mov     rax, [rbx+r14+68h]
0x180005959  cmp     [rax+12h], r10b
0x18000595d  jz      loc_180005A25
0x180005963  mov     rbx, [rbp+0D0h+var_130]
0x180005967  mov     eax, [rbx+4]
0x18000596a  test    al, 8
0x18000596c  jnz     loc_180005A25
0x180005972  mov     r8, [rbx+48h]
0x180005976  test    r8, r8
0x180005979  jz      short loc_1800059DA
0x18000597b  cmp     [r13+48h], r10
0x18000597f  jnz     short loc_180005986
0x180005981  cmp     [r14], r12d
0x180005984  jle     short loc_1800059BD
0x180005986  cmp     [rbx+60h], r10
0x18000598a  jnz     short loc_1800059BD
0x18000598c  or      eax, [r13+4]
0x180005990  bt      eax, 1Bh
0x180005994  jb      short loc_1800059BD
0x180005996  mov     rax, [rsp+1D0h+var_180]
0x18000599b  test    dword ptr [rax+60h], 40000h
0x1800059a2  jnz     short loc_1800059BD
0x1800059a4  lea     rdx, sqlite3ExprListDeleteGeneric
0x1800059ab  mov     rcx, r15
0x1800059ae  call    sqlite3ParserAddCleanup
0x1800059b3  mov     qword ptr [rbx+48h], 0
0x1800059bb  jmp     short loc_1800059DA
0x1800059bd  test    esi, esi
0x1800059bf  jnz     short loc_1800059DA
0x1800059c1  test    dword ptr [r13+4], 40000h
0x1800059c9  jz      short loc_1800059DA
0x1800059cb  cmp     [r14], r12d
0x1800059ce  jz      short loc_180005A25
0x1800059d0  test    byte ptr [r14+0ACh], 22h
0x1800059d8  jnz     short loc_180005A25
0x1800059da  mov     r9d, [rsp+1D0h+var_188]
0x1800059df  mov     r8d, esi
0x1800059e2  mov     rdx, r13
0x1800059e5  mov     rcx, r15
0x1800059e8  call    flattenSubquery
0x1800059ed  xor     r10d, r10d
0x1800059f0  test    eax, eax
0x1800059f2  jz      short loc_180005A01
0x1800059f4  cmp     [r15+30h], r10d
0x1800059f8  jnz     loc_18000577C
0x1800059fe  or      esi, 0FFFFFFFFh
0x180005a01  mov     rdx, [rsp+1D0h+var_180]
0x180005a06  cmp     [rdx+67h], r10b
0x180005a0a  jnz     loc_18000577C
0x180005a10  mov     rax, [rbp+0D0h+var_148]
0x180005a14  mov     r14, [r13+28h]
0x180005a18  cmp     byte ptr [rax], 8
0x180005a1b  jbe     short loc_180005A25
0x180005a1d  mov     rax, [r13+48h]
0x180005a21  mov     qword ptr [rbp+0D0h+var_100], rax
0x180005a25  add     esi, r12d
0x180005a28  jmp     loc_180005810
0x180005a2d  mov     r9, [rdx]
0x180005a30  lea     rdx, aExpectedDColum; "expected %d columns for '%s' but got %d"
0x180005a37  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x180005a3b  mov     rcx, r15
0x180005a3e  call    sqlite3ErrorMsg
0x180005a43  jmp     loc_18000577C
0x180005a48  mov     rax, [r13+30h]
0x180005a4c  mov     rbx, [rsp+1D0h+var_180]
0x180005a51  test    rax, rax
0x180005a54  jz      short loc_180005A72
0x180005a56  cmp     byte ptr [rax], 2Ch ; ','
0x180005a59  jnz     short loc_180005A72
0x180005a5b  test    dword ptr [rbx+60h], 8000h
0x180005a62  jnz     short loc_180005A72
0x180005a64  mov     rdx, r13
0x180005a67  mov     rcx, r15
0x180005a6a  call    propagateConstants
0x180005a6f  xor     r10d, r10d
0x180005a72  test    dword ptr [rbx+60h], 201h
0x180005a79  jnz     short loc_180005AA0
0x180005a7b  mov     rdx, r13
0x180005a7e  mov     rcx, r15
0x180005a81  call    countOfViewOptimization
0x180005a86  xor     r10d, r10d
0x180005a89  test    eax, eax
0x180005a8b  jz      short loc_180005AA0
0x180005a8d  mov     rdx, [rsp+1D0h+var_180]
0x180005a92  cmp     [rdx+67h], r10b
0x180005a96  jnz     loc_18000577C
0x180005a9c  mov     r14, [r13+28h]
0x180005aa0  mov     r11d, r10d
0x180005aa3  mov     [rsp+1D0h+var_184], r11d
0x180005aa8  cmp     r11d, [r14]
0x180005aab  jge     loc_180005EEA
0x180005ab1  movsxd  rax, r11d
0x180005ab4  xorps   xmm0, xmm0
0x180005ab7  imul    rcx, rax, 68h ; 'h'
0x180005abb  movups  [rbp+0D0h+var_B8], xmm0
0x180005abf  movups  [rbp+0D0h+var_C8], xmm0
0x180005ac3  xor     eax, eax
0x180005ac5  mov     qword ptr [rbp+0D0h+var_B8+0Dh], rax
  ... truncated ...
```
