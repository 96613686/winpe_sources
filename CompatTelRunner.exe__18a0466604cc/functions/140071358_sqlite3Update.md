# sqlite3Update

- ea: `0x140071358`
- end: `0x140072bff`
- name: `sqlite3Update`
- size: `6311`
- prototype: ``
- caller_count: `3`
- callee_count: `53`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140024174`
- `0x140072ea8`
- `0x1400a40bc`

## callees

- `0x1400026c0`
- `0x14001d720`
- `0x140024bec`
- `0x14002b178`
- `0x14004bdbc`
- `0x14004c754`
- `0x1400509b8`
- `0x140051158`
- `0x1400518c4`
- `0x140051e50`
- `0x140052048`
- `0x140053e3c`
- `0x140053ef0`
- `0x1400560c4`
- `0x1400569d4`
- `0x140056d98`
- `0x14005904c`
- `0x1400592c0`
- `0x14005a3b8`
- `0x14005b910`
- `0x14005b9d0`
- `0x14005c354`
- `0x14005c46c`
- `0x14005cce4`
- `0x14005e868`
- `0x14005f5fc`
- `0x14006189c`
- `0x1400619a8`
- `0x140061df4`
- `0x140062f5c`
- `0x140063830`
- `0x14006b920`
- `0x14006f6b0`
- `0x14006fb14`
- `0x1400702ec`
- `0x140070328`
- `0x140070708`
- `0x14007088c`
- `0x140070a40`
- `0x140071358`
- `0x1400738a0`
- `0x14007399c`
- `0x140073c04`
- `0x140073ca8`
- `0x140073d38`
- `0x14007b5b0`
- `0x14007da70`
- `0x1400802f0`
- `0x1400830e4`
- `0x140092694`

## string_xrefs

- `0x1400719f3`: `cannot UPDATE generated column "%s"`
- `0x140072bb8`: `rows updated`

## pseudocode

```c
__int64 __fastcall sqlite3Update(__int64 a1, __int64 a2, int *a3, __int64 a4, int a5, char a6, char a7, __int64 a8)
{
  __int64 v8; // rbx
  int *v9; // r15
  _DWORD *v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // r14
  __int64 v14; // rcx
  int v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rbx
  bool v19; // cc
  char v20; // cl
  int v21; // r9d
  int v22; // edx
  int v23; // eax
  bool v24; // zf
  __int64 v25; // r10
  __int64 v26; // rcx
  int v27; // r11d
  int v28; // r8d
  int v29; // edx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rax
  void *v34; // rdi
  int i; // ecx
  __int64 v36; // rax
  __int64 v37; // r12
  char v38; // al
  char v39; // di
  int v40; // r15d
  int *v41; // r13
  __int64 v42; // rdi
  __int64 v43; // rbx
  char v44; // cl
  int v45; // r9d
  int v46; // eax
  int v47; // r11d
  __int64 v48; // r13
  __int64 v49; // r12
  int v50; // eax
  __int64 v51; // rbx
  const char *v52; // r9
  __int64 v53; // rax
  int v54; // eax
  unsigned __int8 v55; // cl
  int v56; // r12d
  int v57; // r15d
  int v58; // edi
  __int64 v59; // rdx
  __int64 v60; // rax
  int v61; // eax
  __int64 v62; // rbx
  __int64 v63; // rdx
  int v64; // r15d
  _BYTE *v65; // r14
  __int64 v66; // rcx
  int v67; // eax
  int v68; // edi
  int v69; // r15d
  __int64 v70; // rax
  int v71; // eax
  _DWORD *v72; // rdx
  __int64 v73; // rdi
  __int64 result; // rax
  __int64 v75; // rcx
  __int64 v76; // rax
  int *v77; // rdi
  int *v78; // rbx
  __int64 v79; // r10
  int v80; // edx
  __int64 v81; // r8
  int v82; // eax
  int v83; // ecx
  char v84; // al
  int v85; // eax
  unsigned int v86; // ebx
  __int64 v87; // r9
  __int64 v88; // r15
  int v89; // r9d
  int v90; // r13d
  int v91; // r8d
  unsigned int v92; // r12d
  __int16 v93; // ax
  size_t v94; // rax
  __int64 v95; // rbx
  int v96; // edi
  int v97; // eax
  __int64 v98; // rcx
  int v99; // ecx
  __int16 v100; // di
  int v101; // ecx
  int v102; // eax
  int v103; // edi
  int v104; // ebx
  int v105; // eax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rcx
  size_t v109; // rdx
  int v110; // ecx
  __int64 v111; // r8
  int v112; // r9d
  unsigned int v113; // edi
  __int64 v114; // r15
  unsigned int v115; // eax
  __int64 v116; // r8
  unsigned int v117; // r12d
  int v118; // edi
  unsigned int v119; // r15d
  int v120; // r8d
  _BYTE *v121; // rdx
  __int64 v122; // rdx
  int v123; // eax
  int v124; // r15d
  __int64 v125; // r13
  int v126; // edi
  int v127; // r8d
  int v128; // ebx
  int v129; // edi
  int v130; // eax
  __int16 v131; // ax
  int v132; // ebx
  int v133; // edi
  int v134; // edi
  signed int v135; // ebx
  int v136; // r12d
  int v137; // edx
  int v138; // ebx
  int v139; // eax
  signed int v140; // r8d
  int v141; // r15d
  unsigned int v142; // ebx
  signed int v143; // edi
  __int64 v144; // rax
  __int64 v145; // rcx
  __int16 v146; // ax
  int v147; // edx
  int v148; // r8d
  unsigned int v149; // r9d
  unsigned int v150; // edi
  int v151; // ebx
  __int64 v152; // rax
  unsigned int v153; // eax
  int v154; // eax
  int v155; // ebx
  int v156; // eax
  unsigned int v157; // edi
  int v158; // [rsp+28h] [rbp-E0h]
  unsigned int v159; // [rsp+28h] [rbp-E0h]
  char v160; // [rsp+78h] [rbp-90h]
  char v161; // [rsp+78h] [rbp-90h]
  int v162; // [rsp+7Ch] [rbp-8Ch]
  char v163; // [rsp+80h] [rbp-88h]
  int v164; // [rsp+84h] [rbp-84h]
  int v165; // [rsp+88h] [rbp-80h]
  unsigned int v166; // [rsp+88h] [rbp-80h]
  int v167; // [rsp+8Ch] [rbp-7Ch]
  unsigned int v168; // [rsp+8Ch] [rbp-7Ch]
  int v169; // [rsp+90h] [rbp-78h]
  __int64 Vdbe; // [rsp+98h] [rbp-70h]
  int v171; // [rsp+A0h] [rbp-68h]
  int v172; // [rsp+A4h] [rbp-64h]
  int v173; // [rsp+A8h] [rbp-60h]
  int v174; // [rsp+ACh] [rbp-5Ch]
  __int16 v175; // [rsp+B0h] [rbp-58h]
  unsigned int v176; // [rsp+B4h] [rbp-54h]
  __int64 v177; // [rsp+B8h] [rbp-50h]
  unsigned int v178; // [rsp+C0h] [rbp-48h]
  int v179; // [rsp+C0h] [rbp-48h]
  __int64 v180; // [rsp+C8h] [rbp-40h]
  int v181; // [rsp+D0h] [rbp-38h]
  int v182; // [rsp+D4h] [rbp-34h] BYREF
  int v183; // [rsp+D8h] [rbp-30h]
  int v184; // [rsp+DCh] [rbp-2Ch] BYREF
  int v185; // [rsp+E0h] [rbp-28h]
  unsigned int v186; // [rsp+E4h] [rbp-24h]
  int v187; // [rsp+E8h] [rbp-20h]
  __int64 v188; // [rsp+F0h] [rbp-18h]
  size_t Size; // [rsp+F8h] [rbp-10h]
  int v190; // [rsp+100h] [rbp-8h]
  __int64 v191; // [rsp+108h] [rbp+0h]
  int v192; // [rsp+110h] [rbp+8h] BYREF
  int v193; // [rsp+114h] [rbp+Ch]
  __int64 v194; // [rsp+118h] [rbp+10h]
  void *v195; // [rsp+120h] [rbp+18h]
  __int64 v196; // [rsp+128h] [rbp+20h]
  int v197; // [rsp+130h] [rbp+28h]
  int v198; // [rsp+134h] [rbp+2Ch]
  int v199; // [rsp+138h] [rbp+30h]
  __int64 v200; // [rsp+140h] [rbp+38h] BYREF
  __int64 v201; // [rsp+148h] [rbp+40h]
  const char *v202; // [rsp+150h] [rbp+48h]
  __int64 v203; // [rsp+158h] [rbp+50h]
  _OWORD v204[7]; // [rsp+160h] [rbp+58h] BYREF
  char v209; // [rsp+210h] [rbp+108h]
  char v210; // [rsp+218h] [rbp+110h]

  v8 = a4;
  v9 = a3;
  v196 = *(_QWORD *)a1;
  v10 = (_DWORD *)a2;
  v11 = a1;
  memset(v204, 0, 56);
  v192 = 0;
  v182 = 0;
  if ( *(_DWORD *)(a1 + 48) )
    goto LABEL_96;
  v12 = sqlite3SrcListLookup(a1, a2);
  v201 = v12;
  v13 = v12;
  if ( !v12 )
    goto LABEL_96;
  v14 = *(_QWORD *)(v12 + 96);
  v15 = -32768;
  v165 = -32768;
  if ( v14 )
  {
    v15 = 0;
    v165 = 0;
    v16 = *(_QWORD *)(*(_QWORD *)v11 + 32LL);
    if ( *(_QWORD *)(v16 + 24) != v14 )
    {
      do
        ++v15;
      while ( *(_QWORD *)(32LL * v15 + v16 + 24) != v14 );
      v165 = v15;
    }
  }
  if ( (*(_QWORD *)(v12 + 88)
     || (v17 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 32LL) + 56LL)) != 0 && *(_QWORD *)(v17 + 64))
    && !*(_BYTE *)(v11 + 221) )
  {
    v18 = triggersReallyExist(v11, v13, 129, (_DWORD)v9, (__int64)&v192);
  }
  else
  {
    v18 = 0;
  }
  v19 = *v10 <= 1;
  v20 = *(_BYTE *)(v13 + 63);
  v210 = v20;
  v188 = v18;
  if ( v19 )
    v164 = 0;
  else
    v164 = *v9;
  if ( (v20 == 1 || *(__int16 *)(v13 + 54) <= 0) && (unsigned int)viewGetColumnNames(v11, v13)
    || (unsigned int)sqlite3IsReadOnly(v11, v13, v18) )
  {
    goto LABEL_95;
  }
  v21 = *(_DWORD *)(v11 + 52);
  v22 = v21;
  v162 = v21;
  v185 = v21;
  v23 = v21 + 1;
  *(_DWORD *)(v11 + 52) = v21 + 1;
  v24 = *(_BYTE *)(v13 + 48) >= 0;
  v183 = v21 + 1;
  if ( v24 )
  {
    v25 = 0;
    v177 = 0;
  }
  else
  {
    v25 = *(_QWORD *)(v13 + 16);
    v177 = v25;
    if ( v25 )
    {
      do
      {
        if ( (*(_DWORD *)(v25 + 100) & 3) == 2 )
          break;
        v25 = *(_QWORD *)(v25 + 40);
      }
      while ( v25 );
      v23 = v183;
      v177 = v25;
    }
  }
  v26 = *(_QWORD *)(v13 + 16);
  v27 = 0;
  v197 = 0;
  if ( v26 )
  {
    v28 = v23;
    v29 = v23;
    do
    {
      v30 = v29;
      if ( v25 != v26 )
      {
        v29 = v28;
        v30 = v21;
      }
      ++v27;
      v21 = v30;
      v28 = v29 + 1;
      *(_DWORD *)(v11 + 52) = ++v29;
      v26 = *(_QWORD *)(v26 + 40);
    }
    while ( v26 );
    v22 = v185;
    v197 = v27;
    v162 = v30;
  }
  if ( a8 )
  {
    v21 = *(_DWORD *)(a8 + 76);
    v162 = v21;
    v183 = *(_DWORD *)(a8 + 80);
    *(_DWORD *)(v11 + 52) = v22;
  }
  v31 = v196;
  v10[19] = v21;
  v32 = v27;
  v33 = sqlite3DbMallocRawNN(v31, v27 + 4LL * (v27 + *(__int16 *)(v13 + 54) + 1) + 2);
  v180 = v33;
  if ( !v33 )
    goto LABEL_95;
  v194 = v33 + 4LL * *(__int16 *)(v13 + 54);
  v34 = (void *)(v194 + 4 + 4 * v32);
  v195 = v34;
  Size = v32 + 1;
  memset_0(v34, 1, v32 + 1);
  *((_BYTE *)v34 + Size) = 0;
  for ( i = 0; i < *(__int16 *)(v13 + 54); *(_DWORD *)(v180 + 4 * v36) = -1 )
    v36 = i++;
  v10 = (_DWORD *)a2;
  *((_QWORD *)&v204[0] + 1) = a2;
  *(_OWORD *)((char *)&v204[1] + 8) = 0;
  *(_QWORD *)((char *)&v204[2] + 12) = 0;
  DWORD1(v204[3]) = 0;
  *(_QWORD *)&v204[0] = v11;
  *(_QWORD *)&v204[1] = a8;
  DWORD2(v204[2]) = 512;
  v37 = 0;
  Vdbe = sqlite3GetVdbe(v11);
  if ( !Vdbe )
    goto LABEL_94;
  v191 = 0;
  v38 = 0;
  v181 = -1;
  v39 = 0;
  v163 = 0;
  v209 = 0;
  if ( *v9 > 0 )
  {
    v40 = 0;
    while ( 1 )
    {
      v41 = a3;
      v42 = v40;
      v43 = 8LL * v40;
      v44 = sqlite3StrIHash(*(_QWORD *)&a3[v43 + 4]);
      v160 = v44;
      if ( v164 == v45 )
      {
        v46 = sqlite3ResolveExprNames(v204, *(_QWORD *)&a3[v43 + 2]);
        v45 = 0;
        if ( v46 )
          goto LABEL_92;
        v44 = v160;
      }
      v47 = v45;
      if ( *(__int16 *)(v13 + 54) <= 0 )
        goto LABEL_50;
      v48 = *(_QWORD *)(v13 + 8);
      while ( 1 )
      {
        v49 = 3LL * (unsigned int)v47;
        if ( *(_BYTE *)(v48 + 24LL * (unsigned int)v47 + 14) == v44 )
          break;
LABEL_48:
        if ( ++v47 >= *(__int16 *)(v13 + 54) )
        {
          v37 = v191;
          v41 = a3;
          goto LABEL_50;
        }
      }
      v202 = *(const char **)(v48 + 24LL * (unsigned int)v47);
      if ( (unsigned int)sqlite3StrICmp(v202, *(_QWORD *)&a3[v43 + 4]) )
        break;
      if ( v47 != *(__int16 *)(v13 + 52) )
      {
        if ( v177 && (*(_BYTE *)(v48 + 8 * v49 + 18) & 1) != 0 )
        {
          v163 = 1;
        }
        else if ( (*(_BYTE *)(v48 + 8 * v49 + 18) & 0x60) != 0 )
        {
          sqlite3ErrorMsg(v11, "cannot UPDATE generated column \"%s\"", v202);
LABEL_92:
          v9 = a3;
          goto LABEL_93;
        }
        v41 = a3;
        v37 = v191;
        goto LABEL_61;
      }
      v41 = a3;
      v209 = 1;
      v181 = v40;
      v37 = *(_QWORD *)&a3[v43 + 2];
LABEL_61:
      *(_DWORD *)(v180 + 4LL * (unsigned int)v47) = v40;
LABEL_50:
      v50 = *(__int16 *)(v13 + 54);
      v191 = v37;
      if ( v47 >= v50 )
      {
        if ( !v177 && (unsigned int)sqlite3IsRowid(*(_QWORD *)&v41[v43 + 4]) )
        {
          v37 = *(_QWORD *)&v41[v43 + 2];
          v51 = -1;
          v191 = v37;
          v209 = 1;
          v181 = v40;
          goto LABEL_63;
        }
        v9 = a3;
        sqlite3ErrorMsg(v11, "no such column: %s", *(const char **)&a3[8 * v42 + 4]);
        *(_BYTE *)(v11 + 29) = 1;
LABEL_93:
        v10 = (_DWORD *)a2;
        goto LABEL_94;
      }
      v51 = v47;
      if ( v47 >= 0 )
      {
        v53 = *(_QWORD *)(v13 + 8);
        v191 = v37;
        v52 = *(const char **)(v53 + 24LL * v47);
      }
      else
      {
LABEL_63:
        v52 = "ROWID";
      }
      v15 = v165;
      v54 = sqlite3AuthCheck(v11, 23, *(_QWORD *)v13, (_DWORD)v52, *(_QWORD *)(32LL * v165 + *(_QWORD *)(v196 + 32)));
      if ( v54 == 1 )
        goto LABEL_92;
      if ( v54 == 2 )
        *(_DWORD *)(v180 + 4 * v51) = -1;
      if ( ++v40 >= *a3 )
      {
        v39 = v209;
        v38 = v163;
        goto LABEL_70;
      }
    }
    v44 = v160;
    goto LABEL_48;
  }
LABEL_70:
  v24 = (*(_BYTE *)(v13 + 48) & 0x60) == 0;
  v55 = v38 + v39;
  v161 = v38 + v39;
  v56 = 0;
  v202 = 0;
  v203 = 0;
  v173 = 0;
  v176 = 0;
  v186 = 0;
  v198 = 0;
  v184 = 0;
  if ( !v24 )
  {
    do
    {
      v57 = 0;
      v58 = 0;
      if ( *(__int16 *)(v13 + 54) <= 0 )
        break;
      do
      {
        if ( *(int *)(v180 + 4LL * v58) < 0 )
        {
          v59 = *(_QWORD *)(v13 + 8) + 24LL * v58;
          if ( (*(_BYTE *)(v59 + 18) & 0x60) != 0 )
          {
            v60 = sqlite3ColumnExpr(v13, v59);
            if ( (unsigned int)sqlite3ExprReferencesUpdatedColumn(v60, v180) )
            {
              *(_DWORD *)(v180 + 4LL * v58) = 99999;
              v57 = 1;
            }
          }
        }
        ++v58;
      }
      while ( v58 < *(__int16 *)(v13 + 54) );
    }
    while ( v57 );
    v11 = a1;
    v15 = v165;
    v55 = v161;
  }
  *(_QWORD *)(a2 + 88) = (*(_BYTE *)(v13 + 63) != 1) - 1LL;
  v193 = v55;
  v61 = sqlite3FkRequired(v11, v13, v180, v55);
  v171 = v61;
  if ( a5 == 5 )
    v182 = 1;
  v62 = *(_QWORD *)(v13 + 16);
  v63 = 0;
  v167 = 0;
  v64 = 0;
  if ( v62 )
  {
    v65 = v195;
    while ( !v161 )
    {
      if ( v61 > 1 )
        break;
      if ( v62 == v177 )
        break;
      v66 = *(_QWORD *)(v62 + 72);
      if ( v66 )
      {
        v67 = sqlite3ExprReferencesUpdatedColumn(v66, v180);
        v63 = 0;
        if ( v67 )
          break;
      }
      v68 = 0;
      v69 = 0;
      if ( *(_WORD *)(v62 + 94) )
      {
        while ( 1 )
        {
          v70 = *(_QWORD *)(v62 + 8);
          if ( *(__int16 *)(v70 + 2LL * v69) < 0 )
          {
            v71 = sqlite3ExprReferencesUpdatedColumn(*(_QWORD *)(32LL * v69 + *(_QWORD *)(v62 + 80) + 8), v180);
            v63 = 0;
          }
          else
          {
            v71 = *(_DWORD *)(v180 + 4LL * *(__int16 *)(v70 + 2LL * v69)) >= 0;
          }
          if ( v71 )
            break;
          if ( ++v69 >= *(unsigned __int16 *)(v62 + 94) )
            goto LABEL_105;
        }
        v68 = ++*(_DWORD *)(v11 + 56);
        v64 = v167;
        *(_DWORD *)(v11 + 56) = v68 + *(unsigned __int16 *)(v62 + 96);
        if ( a5 == 11 && *(_BYTE *)(v62 + 98) == 5 )
          v182 = 1;
LABEL_113:
        if ( v68 )
          goto LABEL_107;
        goto LABEL_106;
      }
LABEL_105:
      v64 = v167;
LABEL_106:
      v65[v64 + 1] = 0;
LABEL_107:
      v75 = v194;
      v76 = v64++;
      v167 = v64;
      *(_DWORD *)(v194 + 4 * v76) = v68;
      v62 = *(_QWORD *)(v62 + 40);
      v61 = v171;
      if ( !v62 )
      {
        v13 = v201;
        v15 = v165;
        v56 = v184;
        goto LABEL_116;
      }
    }
    v68 = ++*(_DWORD *)(v11 + 56);
    *(_DWORD *)(v11 + 56) = v68 + *(unsigned __int16 *)(v62 + 96);
    goto LABEL_113;
  }
  v75 = v194;
LABEL_116:
  v77 = (int *)(v11 + 56);
  *(_DWORD *)(v75 + 4LL * v64) = ++*(_DWORD *)(v11 + 56);
  if ( v182 )
  {
    memset_0(v195, 1, Size);
    v63 = 0;
  }
  if ( !*(_BYTE *)(v11 + 30) )
  {
    v77 = (int *)(v11 + 56);
    *(_DWORD *)(Vdbe + 200) |= 0x10u;
  }
  if ( v188 )
  {
    v78 = v77;
  }
  else
  {
    if ( !v171 )
    {
      v78 = v77;
      goto LABEL_126;
    }
    v78 = (int *)(v11 + 56);
  }
  v63 = 1;
LABEL_126:
  sqlite3BeginWriteOperation(v11, v63, (unsigned int)v15);
  v79 = 0;
  if ( *(_BYTE *)(v13 + 63) == 1 )
    goto LABEL_138;
  v80 = *(_DWORD *)(v11 + 56) + 1;
  v81 = v188;
  v173 = v80;
  v56 = *(_DWORD *)(v194 + 4LL * v64);
  v184 = v56;
  *v77 = v80;
  if ( v163 )
  {
    v78 = v77;
  }
  else if ( !v81 )
  {
    v82 = v171;
    if ( !v171 )
    {
      v83 = v80;
      goto LABEL_133;
    }
  }
  v83 = v80 + *(__int16 *)(v13 + 54);
  v198 = v80 + 1;
  v82 = v171;
  *v78 = v83;
LABEL_133:
  if ( v161 || v81 || v82 )
  {
    v80 = v83 + 1;
    *v78 = ++v83;
  }
  v176 = v80;
  v186 = v83 + 1;
  *v78 = v83 + *(__int16 *)(v13 + 54);
LABEL_138:
  v84 = v210;
  if ( v210 == 2 )
  {
    v202 = *(const char **)(v11 + 368);
    *(_QWORD *)(v11 + 368) = *(_QWORD *)v13;
    v84 = 2;
    v203 = v11;
  }
  if ( !v164 )
  {
    if ( v84 == 2 )
      sqlite3MaterializeView(v11, v13, a4, 0, 0, v162);
    v85 = sqlite3ResolveExprNames(v204, a4);
    v79 = 0;
    if ( v85 )
    {
      v9 = a3;
      goto LABEL_358;
    }
  }
  if ( *(_BYTE *)(v13 + 63) == 1 )
  {
    v9 = a3;
    v10 = (_DWORD *)a2;
    updateVirtualTable(v11, a2, v13, (_DWORD)a3, v191, v180, a4, a5);
    goto LABEL_359;
  }
  v86 = --*(_DWORD *)(v11 + 68);
  v87 = a8;
  v199 = 0;
  v166 = v86;
  if ( (*(_QWORD *)(v196 + 48) & 0x100000000LL) == 0
    || *(_QWORD *)(v11 + 176)
    || *(_BYTE *)(v11 + 30)
    || *(_BYTE *)(v11 + 219) )
  {
    v88 = Vdbe;
  }
  else
  {
    v88 = Vdbe;
    if ( !a8 )
    {
      v89 = *(_DWORD *)(v11 + 56) + 1;
      v199 = v89;
      *(_DWORD *)(v11 + 56) = v89;
      sqlite3VdbeAddOp3(Vdbe, 71, 0, v89, 0);
      v87 = 0;
      v79 = 0;
    }
  }
  if ( !v164 && *(char *)(v13 + 48) >= 0 )
  {
    v175 = 0;
    v90 = 0;
    v174 = 0;
    sqlite3VdbeAddOp3(v88, 75, v164, v56, v173);
    v91 = *(_DWORD *)(v11 + 52);
    v169 = v91;
    *(_DWORD *)(v11 + 52) = v91 + 1;
    v178 = sqlite3VdbeAddOp3(v88, 118, v91, 0, v56);
    v92 = v178;
    if ( !a8 )
      goto LABEL_156;
LABEL_194:
    v96 = 1;
    Size = 0;
    v172 = 1;
    sqlite3ExprIfFalse(v11, a4, v86, 16);
    LODWORD(v95) = v200;
    v79 = 0;
    v190 = 0;
    v201 = v200;
    goto LABEL_195;
  }
  if ( v177 )
    v100 = *(_WORD *)(v177 + 94);
  else
    v100 = 0;
  v101 = v100;
  v175 = v100;
  v90 = *(_DWORD *)(v11 + 56) + 1;
  v174 = v164 + v100 + v90;
  *(_DWORD *)(v11 + 56) = v174;
  if ( v87 )
  {
    v169 = 0;
    if ( !v164 )
    {
      v92 = 0;
      v178 = 0;
      goto LABEL_194;
    }
  }
  else
  {
    if ( v210 == 2 )
      v102 = *(__int16 *)(v13 + 54);
    else
      v102 = 0;
    v103 = *(_DWORD *)(v11 + 52);
    v104 = v164 + v101 + v102;
    v169 = v103;
    *(_DWORD *)(v11 + 52) = v103 + 1;
    if ( v177 )
      sqlite3VdbeAddOp3(v88, 75, 0, v90, v90 + v101 - 1);
    v92 = sqlite3VdbeAddOp3(v88, 118, v103, v104, 0);
    v178 = v92;
    v105 = v177;
    if ( v177 )
    {
      v106 = sqlite3KeyInfoOfIndex(v11, v177);
      if ( v106 )
      {
        *(_WORD *)(v106 + 8) = v104;
        sqlite3VdbeAppendP4(v88, v106, 4294967288LL);
      }
      v105 = v177;
    }
    if ( !v164 )
    {
LABEL_156:
      v93 = 4;
      if ( !*(_BYTE *)(v11 + 30) && !v188 && !v171 && !v161 && !v182 && (!a4 || (*(_DWORD *)(a4 + 4) & 0x400000) == 0) )
        v93 = 12;
      v10 = (_DWORD *)a2;
      v94 = sqlite3WhereBegin(v11, a2, a4, 0, 0, 0, v93, v183);
      v79 = 0;
      Size = v94;
      if ( !v94 )
      {
        v9 = a3;
        goto LABEL_359;
      }
      v95 = *(_QWORD *)(v94 + 40);
      v96 = *(unsigned __int8 *)(v94 + 66);
      v97 = *(_DWORD *)(v94 + 68) & 1;
      v201 = v95;
      v200 = v95;
      v172 = v96;
      v190 = v97;
      if ( v96 != 1 )
      {
        v98 = v11;
        if ( *(_QWORD *)(v11 + 168) )
          v98 = *(_QWORD *)(v11 + 168);
        *(_BYTE *)(v98 + 32) = 1;
        v99 = v162;
        if ( v96 == 2 && v95 >= 0 && HIDWORD(v95) != v162 && *((_BYTE *)v195 + HIDWORD(v95) - v185) )
        {
          v96 = 0;
          v172 = 0;
        }
LABEL_196:
        v24 = *(_BYTE *)(v13 + 48) >= 0;
        v187 = 0;
        if ( v24 )
        {
          sqlite3VdbeAddOp3(v88, 135, v99, v173, 0);
          v79 = 0;
          if ( v96 )
          {
            if ( !v92 )
            {
LABEL_212:
              v109 = Size;
              goto LABEL_213;
            }
            sqlite3VdbeChangeToNoop(v88, v92);
          }
          else
          {
            v110 = *(_DWORD *)(v11 + 56) + 1;
            v111 = v194;
            v112 = v184;
            *(_DWORD *)(v11 + 56) = v110;
            *(_DWORD *)(v111 + 4LL * v167) = v110;
            sqlite3VdbeAddOp3(v88, 128, v169, v112, v173);
          }
        }
        else
        {
          v113 = 0;
          if ( v175 > 0 )
          {
            do
            {
              sqlite3ExprCodeGetColumnOfTable(
                Vdbe,
                v13,
                v162,
                *(__int16 *)(*(_QWORD *)(v177 + 8) + 2LL * v113),
                v113 + v90);
              ++v113;
            }
            while ( (int)v113 < v175 );
            LODWORD(v95) = v201;
            v79 = 0;
            v11 = a1;
            v92 = v178;
          }
          v96 = v172;
          if ( v172 )
          {
            v88 = Vdbe;
            if ( v92 )
            {
              sqlite3VdbeChangeToNoop(Vdbe, v92);
              v79 = 0;
            }
            v187 = v175;
            v174 = v90;
            goto LABEL_212;
          }
          v114 = *(_QWORD *)(v177 + 32);
          if ( !v114 )
            v114 = computeIndexAffStr(v196, v177);
          v115 = sqlite3VdbeAddOp3(Vdbe, 97, v90, v175, v174);
          v116 = v114;
          v88 = Vdbe;
          sqlite3VdbeChangeP4(Vdbe, v115, v116, (unsigned int)v175);
          sqlite3VdbeAddOp4Int(Vdbe, 138, v169, v174, v90, v175);
          v96 = 0;
        }
        v79 = 0;
        goto LABEL_212;
      }
LABEL_195:
      v99 = v162;
      goto LABEL_196;
    }
    updateFromSelect(v11, v103, v105, (_DWORD)a3, a2, a4);
    v79 = 0;
    if ( v210 == 2 )
      v162 = v103;
  }
  v107 = *(_QWORD *)(v11 + 168);
  v108 = v11;
  LODWORD(v95) = v200;
  v109 = 0;
  v190 = 1;
  if ( v107 )
    v108 = v107;
  Size = 0;
  v96 = 0;
  v172 = 0;
  v187 = v175;
  *(_BYTE *)(v108 + 32) = 1;
  v174 = v90;
LABEL_213:
  v117 = v166;
  v168 = v166;
  v179 = 0;
  if ( a8 )
  {
    v125 = Vdbe;
    v124 = v162;
LABEL_254:
    v128 = v169;
    goto LABEL_255;
  }
  if ( !v164 && v96 != 2 )
  {
    sqlite3WhereEnd(v109);
    v79 = 0;
  }
  v118 = HIDWORD(v200);
  if ( v210 != 2 )
  {
    v119 = 0;
    LODWORD(v200) = 0;
    v184 = 0;
    if ( v172 )
    {
      v120 = v185;
      v121 = v195;
      if ( (int)v95 >= 0 )
        *((_BYTE *)v195 + (int)v95 - v185) = 0;
      if ( v118 >= 0 )
        v121[v118 - v120] = 0;
      if ( v172 == 2 && v197 - (v118 >= 0) > 0 )
        v119 = sqlite3VdbeAddOp3(Vdbe, 15, 0, 0, 0);
    }
    sqlite3OpenTableAndIndices(v11, v13, 113, 0, v185, (__int64)v195, (__int64)&v200, (__int64)&v184);
    v79 = 0;
    if ( v119 )
    {
      v122 = v119;
      v88 = Vdbe;
      sqlite3VdbeJumpHereOrPopInst(Vdbe, v122);
    }
    else
    {
      v88 = Vdbe;
    }
  }
  v123 = v172;
  if ( v172 )
  {
    v124 = v162;
    v125 = Vdbe;
    if ( (_DWORD)v95 == v162 )
    {
      v126 = v174;
    }
    else
    {
      v24 = v118 == v162;
      v126 = v174;
      if ( !v24 )
      {
        sqlite3VdbeAddOp4Int(Vdbe, 28, v162, v166, v174, v187);
        v123 = v172;
        v79 = 0;
      }
    }
    if ( v123 != 1 )
    {
      v117 = *(_DWORD *)(v11 + 68) - 1;
      v168 = v117;
      *(_DWORD *)(v11 + 68) = v117;
    }
    v127 = v173;
    if ( v177 != v79 )
      v127 = v126;
    sqlite3VdbeAddOp3(Vdbe, 50, v127, v166, v79);
    goto LABEL_254;
  }
  if ( !v177 && v164 == (_DWORD)v79 )
  {
    v125 = Vdbe;
    v128 = v169;
    sqlite3VdbeAddOp3(Vdbe, 36, v169, v166, v79);
    v117 = *(_DWORD *)(v11 + 68) - 1;
    v129 = v173;
    v168 = v117;
    *(_DWORD *)(v11 + 68) = v117;
    v179 = sqlite3VdbeAddOp3(Vdbe, 135, v169, v173, 0);
LABEL_242:
    v124 = v162;
    sqlite3VdbeAddOp3(v125, 31, v162, v117, v129);
LABEL_255:
    v130 = v164;
    goto LABEL_256;
  }
  v128 = v169;
  v117 = *(_DWORD *)(v11 + 68) - 1;
  v168 = v117;
  *(_DWORD *)(v11 + 68) = v117;
  sqlite3VdbeAddOp3(v88, 36, v169, v166, v79);
  v179 = *(_DWORD *)(v88 + 144);
  v130 = v164;
  if ( !v164 )
  {
    v125 = Vdbe;
    sqlite3VdbeAddOp3(Vdbe, 134, v169, v174, 0);
    v124 = v162;
    sqlite3VdbeAddOp4Int(Vdbe, 28, v162, v117, v174, 0);
    goto LABEL_255;
  }
  if ( v210 != 2 )
  {
    if ( v177 )
    {
      v131 = v175;
      v132 = 0;
      if ( v175 > 0 )
      {
        do
        {
          sqlite3VdbeAddOp3(v88, 94, v169, v132, v132 + v90);
          ++v132;
        }
        while ( v132 < v175 );
        v11 = a1;
        v131 = v175;
      }
      v124 = v162;
      v158 = v90;
      v125 = Vdbe;
      sqlite3VdbeAddOp4Int(Vdbe, 28, v162, v117, v158, v131);
      goto LABEL_254;
    }
    v125 = Vdbe;
    v129 = v173;
    sqlite3VdbeAddOp3(Vdbe, 135, v169, v173, 0);
    goto LABEL_242;
  }
  v125 = Vdbe;
  v124 = v162;
LABEL_256:
  if ( v209 )
  {
    if ( v130 )
      sqlite3VdbeAddOp3(v125, 94, v128, v181, v176);
    else
      sqlite3ExprCode(v11, v191, v176);
    sqlite3VdbeAddOp3(v125, 13, v176, 0, 0);
  }
  if ( v163 )
    goto LABEL_264;
  if ( v171 )
    goto LABEL_265;
  if ( v188 )
  {
LABEL_264:
    if ( !v171 )
    {
      v133 = 0;
      goto LABEL_267;
    }
LABEL_265:
    v133 = sqlite3FkOldmask(v11, v13);
LABEL_267:
    v134 = sqlite3TriggerColmask(v11, v188, (_DWORD)a3, 0, 3, v13, a5) | v133;
    v135 = 0;
    if ( *(__int16 *)(v13 + 54) > 0 )
    {
      v136 = v198;
      do
      {
        v137 = v136 + (__int16)sqlite3TableColumnToStorage(v13, (unsigned __int16)v135);
        if ( v134 == -1
          || v135 < 32 && _bittest(&v134, v135)
          || (*(_BYTE *)(*(_QWORD *)(v13 + 8) + 24LL * v135 + 18) & 1) != 0 )
        {
          sqlite3ExprCodeGetColumnOfTable(v125, v13, v124, v135, v137);
        }
        else
        {
          sqlite3VdbeAddOp3(v125, 75, 0, v137, 0);
        }
        ++v135;
      }
      while ( v135 < *(__int16 *)(v13 + 54) );
      v11 = a1;
      v117 = v168;
    }
    if ( !v209 && !v177 )
      sqlite3VdbeAddOp3(v125, 80, v173, v176, 0);
  }
  v138 = a5;
  v139 = sqlite3TriggerColmask(v11, v188, (_DWORD)a3, 1, 1, v13, a5);
  LOWORD(v140) = *(_WORD *)(v13 + 54);
  v141 = v139;
  if ( (__int16)v140 <= 0 )
    goto LABEL_300;
  v142 = v186;
  v143 = 0;
  do
  {
    if ( v143 == *(__int16 *)(v13 + 52) )
    {
LABEL_295:
      v148 = 0;
      v159 = 0;
      v149 = v142;
      v147 = 75;
LABEL_296:
      sqlite3VdbeAddOp3(v125, v147, v148, v149, v159);
      goto LABEL_298;
    }
    v144 = *(_QWORD *)(v13 + 8);
    if ( (*(_BYTE *)(v144 + 24LL * v143 + 18) & 0x60) != 0 )
    {
      if ( (*(_BYTE *)(v144 + 24LL * v143 + 18) & 0x20) != 0 )
        --v142;
      goto LABEL_298;
    }
    v145 = *(int *)(v180 + 4LL * v143);
    if ( (int)v145 >= 0 )
    {
      if ( !v164 )
      {
        sqlite3ExprCode(v11, *(_QWORD *)&a3[8 * v145 + 2], v142);
        goto LABEL_298;
      }
      v146 = v175;
      v159 = v142;
      v147 = 94;
      if ( v210 == 2 )
        v146 = v140;
      v148 = v169;
      v149 = v145 + v146;
      goto LABEL_296;
    }
    if ( (v192 & 1) != 0 && v143 <= 31 && !_bittest(&v141, v143) )
      goto LABEL_295;
    sqlite3ExprCodeGetColumnOfTable(v125, v13, v162, v143, v142);
    v190 = 0;
LABEL_298:
    v140 = *(__int16 *)(v13 + 54);
    ++v143;
    ++v142;
  }
  while ( v143 < v140 );
  v117 = v168;
  v138 = a5;
LABEL_300:
  v150 = v186;
  if ( (*(_BYTE *)(v13 + 48) & 0x60) != 0 )
    sqlite3ComputeGeneratedColumns(v11, v186, v13);
  if ( (v192 & 1) == 0 )
  {
    if ( v210 != 2 )
      goto LABEL_320;
    v155 = v172;
    goto LABEL_340;
  }
  sqlite3TableAffinity(v125, v13, v150);
  v9 = a3;
  sqlite3CodeRowTrigger(v11, v188, 129, (_DWORD)a3, 1, v13, v173, v138, v117);
  if ( v210 == 2 )
  {
    v155 = v172;
  }
  else
  {
    if ( v177 )
      sqlite3VdbeAddOp4Int(v125, 28, v162, v117, v174, v187);
    else
      sqlite3VdbeAddOp3(v125, 31, v162, v117, v173);
    v151 = 0;
    if ( *(__int16 *)(v13 + 54) > 0 )
    {
      do
      {
        v152 = *(_QWORD *)(v13 + 8);
        if ( (*(_BYTE *)(v152 + 24LL * v151 + 18) & 0x60) != 0 )
        {
          v24 = (*(_BYTE *)(v152 + 24LL * v151 + 18) & 0x20) == 0;
          v153 = v150 - 1;
          if ( v24 )
            v153 = v150;
          v150 = v153;
        }
        else if ( *(int *)(v180 + 4LL * v151) < 0 && v151 != *(__int16 *)(v13 + 52) )
        {
          sqlite3ExprCodeGetColumnOfTable(v125, v13, v162, v151, v150);
        }
        ++v151;
        ++v150;
      }
      while ( v151 < *(__int16 *)(v13 + 54) );
      v11 = a1;
    }
    if ( (*(_BYTE *)(v13 + 48) & 0x60) != 0 )
      sqlite3ComputeGeneratedColumns(v11, v186, v13);
LABEL_320:
    sqlite3GenerateConstraintChecks(v11, v13, v194, v162, v183, v176, v173, v161, a5, v117, (__int64)&v182, v180, 0);
    if ( v182 || v161 )
    {
      if ( v177 )
        sqlite3VdbeAddOp4Int(v125, 28, v162, v117, v174, v187);
      else
        sqlite3VdbeAddOp3(v125, 31, v162, v117, v173);
    }
    if ( v171 )
      sqlite3FkCheck(v11, v13, v173, 0, v180, v193);
    sqlite3GenerateRowIndexDelete(v11, v13, v162, v183, v194, -1);
    if ( v190 )
      sqlite3VdbeAddOp3(v125, 143, v162, 0, 0);
    v154 = v171;
    if ( v171 > 1 || v161 )
    {
      sqlite3VdbeAddOp3(v125, 130, v162, 0, 0);
      v154 = v171;
    }
    if ( v154 )
      sqlite3FkCheck(v11, v13, 0, v176, v180, v193);
    v155 = v172;
    v156 = 6;
    if ( v172 != 2 )
      v156 = 4;
    sqlite3CompleteInsertion(v11, v13, v162, v183, v176, v194, v156, 0, 0);
    if ( v171 )
    {
      v9 = a3;
      sqlite3FkActions(v11, v13, (_DWORD)a3, v173, v180, v193);
      goto LABEL_341;
    }
LABEL_340:
    v9 = a3;
  }
LABEL_341:
  v157 = v199;
  if ( v199 )
    sqlite3VdbeAddOp3(v125, 86, v199, 1, 0);
  if ( v188 )
    sqlite3CodeRowTrigger(v11, v188, 129, (_DWORD)v9, 2, v13, v173, a5, v117);
  if ( v155 != 1 )
  {
    sqlite3VdbeResolveLabel(v125, v117);
    if ( v155 == 2 )
      sqlite3WhereEnd(Size);
    else
      sqlite3VdbeAddOp3(v125, 39, v169, v179, 0);
  }
  sqlite3VdbeResolveLabel(v125, v166);
  if ( !*(_BYTE *)(v11 + 30) && !*(_QWORD *)(v11 + 176) && !a8 && *(_QWORD *)(v11 + 160) )
    autoIncrementEnd(v11);
  if ( v157 )
    sqlite3CodeChangeCount(v125, v157, "rows updated");
LABEL_358:
  v10 = (_DWORD *)a2;
LABEL_359:
  if ( v203 )
    *(_QWORD *)(v203 + 368) = v202;
LABEL_94:
  sqlite3DbFreeNN(v196);
LABEL_95:
  v8 = a4;
LABEL_96:
  v72 = v10;
  v73 = v196;
  result = sqlite3SrcListDelete(v196, v72);
  if ( v9 )
    result = exprListDeleteNN(v73);
  if ( v8 )
    return sqlite3ExprDeleteNN(v73);
  return result;
}

```

## disassembly

```asm
0x140071358  mov     rax, rsp
0x14007135b  mov     [rax+20h], r9
0x14007135f  mov     [rax+18h], r8
0x140071363  mov     [rax+10h], rdx
0x140071367  mov     [rax+8], rcx
0x14007136b  push    rbp
0x14007136c  push    rbx
0x14007136d  push    rsi
0x14007136e  push    rdi
0x14007136f  push    r12
0x140071371  push    r13
0x140071373  push    r14
0x140071375  push    r15
0x140071377  lea     rbp, [rax-0D8h]
0x14007137e  sub     rsp, 198h
0x140071385  xor     eax, eax
0x140071387  xor     r12d, r12d
0x14007138a  xorps   xmm0, xmm0
0x14007138d  mov     [rbp+0D0h+var_48], rax
0x140071394  mov     rbx, r9
0x140071397  mov     rax, [rcx]
0x14007139a  mov     r15, r8
0x14007139d  mov     [rbp+0D0h+var_B0], rax
0x1400713a1  mov     rdi, rdx
0x1400713a4  mov     rsi, rcx
0x1400713a7  movups  [rbp+0D0h+var_78], xmm0
0x1400713ab  mov     [rbp+0D0h+var_C8], r12d
0x1400713af  movups  [rbp+0D0h+var_68], xmm0
0x1400713b3  mov     [rbp+0D0h+var_104], r12d
0x1400713b7  movups  [rbp+0D0h+var_58], xmm0
0x1400713bb  cmp     [rcx+30h], r12d
0x1400713bf  jnz     loc_140071A24
0x1400713c5  call    sqlite3SrcListLookup
0x1400713ca  mov     [rbp+0D0h+var_90], rax
0x1400713ce  mov     r14, rax
0x1400713d1  test    rax, rax
0x1400713d4  jz      loc_140071A24
0x1400713da  mov     rcx, [rax+60h]
0x1400713de  mov     r13d, 0FFFF8000h
0x1400713e4  mov     [rbp+0D0h+var_150], r13d
0x1400713e8  test    rcx, rcx
0x1400713eb  jz      short loc_140071416
0x1400713ed  mov     rax, [rsi]
0x1400713f0  mov     r13d, r12d
0x1400713f3  mov     [rbp+0D0h+var_150], r12d
0x1400713f7  mov     rdx, [rax+20h]
0x1400713fb  cmp     [rdx+18h], rcx
0x1400713ff  jz      short loc_140071416
0x140071401  inc     r13d
0x140071404  movsxd  rax, r13d
0x140071407  shl     rax, 5
0x14007140b  cmp     [rax+rdx+18h], rcx
0x140071410  jnz     short loc_140071401
0x140071412  mov     [rbp+0D0h+var_150], r13d
0x140071416  cmp     [r14+58h], r12
0x14007141a  jnz     short loc_140071432
0x14007141c  mov     rax, [rsi]
0x14007141f  mov     rcx, [rax+20h]
0x140071423  mov     rax, [rcx+38h]
0x140071427  test    rax, rax
0x14007142a  jz      short loc_14007143B
0x14007142c  cmp     [rax+40h], r12
0x140071430  jz      short loc_14007143B
0x140071432  cmp     [rsi+0DDh], r12b
0x140071439  jz      short loc_140071440
0x14007143b  mov     rbx, r12
0x14007143e  jmp     short loc_140071460
0x140071440  lea     rax, [rbp+0D0h+var_C8]
0x140071444  mov     r9, r15
0x140071447  mov     r8d, 81h
0x14007144d  mov     [rsp+1D0h+var_1B0], rax
0x140071452  mov     rdx, r14
0x140071455  mov     rcx, rsi
0x140071458  call    triggersReallyExist
0x14007145d  mov     rbx, rax
0x140071460  cmp     dword ptr [rdi], 1
0x140071463  mov     cl, [r14+3Fh]
0x140071467  mov     [rbp+0D0h+arg_30], cl
0x14007146d  mov     [rbp+0D0h+var_E8], rbx
0x140071471  jle     short loc_14007147C
0x140071473  mov     eax, [r15]
0x140071476  mov     [rsp+7Ch], eax
0x14007147a  jmp     short loc_140071481
0x14007147c  mov     [rsp+7Ch], r12d
0x140071481  cmp     cl, 1
0x140071484  jz      short loc_14007148D
0x140071486  cmp     [r14+36h], r12w
0x14007148b  jg      short loc_1400714A0
0x14007148d  mov     rdx, r14
0x140071490  mov     rcx, rsi
0x140071493  call    viewGetColumnNames
0x140071498  test    eax, eax
0x14007149a  jnz     loc_140071A1D
0x1400714a0  mov     r8, rbx
0x1400714a3  mov     rdx, r14
0x1400714a6  mov     rcx, rsi
0x1400714a9  call    sqlite3IsReadOnly
0x1400714ae  test    eax, eax
0x1400714b0  jnz     loc_140071A1D
0x1400714b6  mov     r9d, [rsi+34h]
0x1400714ba  mov     edx, r9d
0x1400714bd  mov     [rsp+1D0h+var_15C], r9d
0x1400714c2  mov     [rbp+0D0h+var_F8], edx
0x1400714c5  lea     eax, [r9+1]
0x1400714c9  mov     [rsi+34h], eax
0x1400714cc  test    byte ptr [r14+30h], 80h
0x1400714d1  mov     [rbp+0D0h+var_100], eax
0x1400714d4  jnz     short loc_1400714DF
0x1400714d6  mov     r10, r12
0x1400714d9  mov     [rbp+0D0h+var_120], r12
0x1400714dd  jmp     short loc_140071506
0x1400714df  mov     r10, [r14+10h]
0x1400714e3  mov     [rbp+0D0h+var_120], r10
0x1400714e7  test    r10, r10
0x1400714ea  jz      short loc_140071506
0x1400714ec  mov     eax, [r10+64h]
0x1400714f0  and     al, 3
0x1400714f2  cmp     al, 2
0x1400714f4  jz      short loc_1400714FF
0x1400714f6  mov     r10, [r10+28h]
0x1400714fa  test    r10, r10
0x1400714fd  jnz     short loc_1400714EC
0x1400714ff  mov     eax, [rbp+0D0h+var_100]
0x140071502  mov     [rbp+0D0h+var_120], r10
0x140071506  mov     rcx, [r14+10h]
0x14007150a  mov     r11d, r12d
0x14007150d  mov     [rbp+0D0h+var_A8], r12d
0x140071511  test    rcx, rcx
0x140071514  jz      short loc_14007154D
0x140071516  mov     r8d, eax
0x140071519  mov     edx, eax
0x14007151b  cmp     r10, rcx
0x14007151e  mov     eax, edx
0x140071520  cmovnz  edx, r8d
0x140071524  cmovnz  eax, r9d
0x140071528  inc     r11d
0x14007152b  mov     r9d, eax
0x14007152e  lea     r8d, [rdx+1]
0x140071532  mov     [rsi+34h], r8d
0x140071536  mov     edx, r8d
0x140071539  mov     rcx, [rcx+28h]
0x14007153d  test    rcx, rcx
0x140071540  jnz     short loc_14007151B
0x140071542  mov     edx, [rbp+0D0h+var_F8]
0x140071545  mov     [rbp+0D0h+var_A8], r11d
0x140071549  mov     [rsp+1D0h+var_15C], eax
0x14007154d  mov     r12, [rbp+0D0h+arg_38]
0x140071554  test    r12, r12
0x140071557  jz      short loc_14007156E
0x140071559  mov     r9d, [r12+4Ch]
0x14007155e  mov     eax, [r12+50h]
0x140071563  mov     [rsp+1D0h+var_15C], r9d
0x140071568  mov     [rbp+0D0h+var_100], eax
0x14007156b  mov     [rsi+34h], edx
0x14007156e  mov     rcx, [rbp+0D0h+var_B0]
0x140071572  mov     [rdi+4Ch], r9d
0x140071576  movsx   eax, word ptr [r14+36h]
0x14007157b  inc     eax
0x14007157d  movsxd  rbx, r11d
0x140071580  add     eax, r11d
0x140071583  cdqe
0x140071585  lea     rdx, ds:2[rax*4]
0x14007158d  add     rdx, rbx
0x140071590  call    sqlite3DbMallocRawNN
0x140071595  mov     [rbp+0D0h+var_110], rax
0x140071599  test    rax, rax
0x14007159c  jz      loc_140071A1D
0x1400715a2  movsx   rcx, word ptr [r14+36h]
0x1400715a7  mov     edx, 1; Val
0x1400715ac  lea     rax, [rax+rcx*4]
0x1400715b0  lea     rdi, [rax+4]
0x1400715b4  mov     [rbp+0D0h+var_C0], rax
0x1400715b8  lea     rdi, [rdi+rbx*4]
0x1400715bc  inc     rbx
0x1400715bf  mov     r8, rbx; Size
0x1400715c2  mov     [rbp+0D0h+var_B8], rdi
0x1400715c6  mov     rcx, rdi; void *
0x1400715c9  mov     [rbp+0D0h+Size], rbx
0x1400715cd  call    memset_0
0x1400715d2  xor     r8d, r8d
0x1400715d5  mov     [rbx+rdi], r8b
0x1400715d9  mov     ecx, r8d
0x1400715dc  cmp     r8w, [r14+36h]
0x1400715e1  jge     short loc_1400715FC
0x1400715e3  mov     rdx, [rbp+0D0h+var_110]
0x1400715e7  movsxd  rax, ecx
0x1400715ea  inc     ecx
0x1400715ec  mov     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x1400715f3  movsx   eax, word ptr [r14+36h]
0x1400715f8  cmp     ecx, eax
0x1400715fa  jl      short loc_1400715E7
0x1400715fc  mov     rdi, [rbp+0D0h+arg_8]
0x140071603  xorps   xmm0, xmm0
0x140071606  mov     rcx, rsi
0x140071609  mov     qword ptr [rbp+0D0h+var_78+8], rdi
0x14007160d  movdqu  [rbp+0D0h+var_68+8], xmm0
0x140071612  mov     qword ptr [rbp+0D0h+var_58+0Ch], r8
0x140071619  mov     dword ptr [rbp+0D0h+var_48+4], r8d
0x140071620  mov     qword ptr [rbp+0D0h+var_78], rsi
0x140071624  mov     qword ptr [rbp+0D0h+var_68], r12
0x140071628  mov     dword ptr [rbp+0D0h+var_58+8], 200h
0x140071632  call    sqlite3GetVdbe
0x140071637  xor     r12d, r12d
0x14007163a  mov     [rbp+0D0h+var_140], rax
0x14007163e  test    rax, rax
0x140071641  jz      loc_140071A10
0x140071647  xor     r9d, r9d
0x14007164a  mov     [rbp+0D0h+var_D0], r12
0x14007164e  mov     al, r9b
0x140071651  mov     [rbp+0D0h+var_108], 0FFFFFFFFh
0x140071658  mov     dil, r9b
0x14007165b  mov     [rsp+78h], al
0x14007165f  mov     [rbp+0D0h+arg_28], r9b
0x140071666  cmp     [r15], r9d
0x140071669  jle     loc_140071864
0x14007166f  mov     r15d, r9d
0x140071672  mov     r13, [rbp+0D0h+arg_10]
0x140071679  movsxd  rdi, r15d
0x14007167c  mov     rbx, rdi
0x14007167f  shl     rbx, 5
0x140071683  mov     rcx, [rbx+r13+10h]
0x140071688  call    sqlite3StrIHash
0x14007168d  mov     cl, al
0x14007168f  mov     [rsp+1D0h+var_160], al
0x140071693  cmp     [rsp+7Ch], r9d
0x140071698  jnz     short loc_1400716B7
0x14007169a  mov     rdx, [rbx+r13+8]
0x14007169f  lea     rcx, [rbp+0D0h+var_78]
0x1400716a3  call    sqlite3ResolveExprNames
0x1400716a8  xor     r9d, r9d
0x1400716ab  test    eax, eax
0x1400716ad  jnz     loc_140071A02
0x1400716b3  mov     cl, [rsp+1D0h+var_160]
0x1400716b7  movsx   eax, word ptr [r14+36h]
0x1400716bc  mov     r11d, r9d
0x1400716bf  test    eax, eax
0x1400716c1  jle     short loc_140071715
0x1400716c3  mov     r13, [r14+8]
0x1400716c7  mov     eax, r11d
0x1400716ca  lea     r12, [rax+rax*2]
0x1400716ce  cmp     [r13+r12*8+0Eh], cl
0x1400716d3  jnz     short loc_1400716FD
0x1400716d5  mov     rax, [r13+r12*8+0]
0x1400716da  mov     rcx, [rbp+0D0h+arg_10]
0x1400716e1  mov     [rbp+0D0h+var_88], rax
0x1400716e5  mov     rdx, [rbx+rcx+10h]
0x1400716ea  mov     rcx, rax
0x1400716ed  call    sqlite3StrICmp
0x1400716f2  xor     r9d, r9d
0x1400716f5  test    eax, eax
0x1400716f7  jz      short loc_140071774
0x1400716f9  mov     cl, [rsp+1D0h+var_160]
0x1400716fd  movsx   eax, word ptr [r14+36h]
0x140071702  inc     r11d
0x140071705  cmp     r11d, eax
0x140071708  jl      short loc_1400716C7
0x14007170a  mov     r12, [rbp+0D0h+var_D0]
0x14007170e  mov     r13, [rbp+0D0h+arg_10]
0x140071715  movsx   eax, word ptr [r14+36h]
0x14007171a  mov     r8b, [rbp+0D0h+arg_28]
0x140071721  mov     edx, [rbp+0D0h+var_108]
0x140071724  mov     [rbp+0D0h+var_108], edx
0x140071727  mov     [rbp+0D0h+var_D0], r12
0x14007172b  mov     [rbp+0D0h+arg_28], r8b
0x140071732  cmp     r11d, eax
0x140071735  jl      loc_1400717D3
0x14007173b  xor     r12d, r12d
0x14007173e  cmp     [rbp+0D0h+var_120], r12
0x140071742  jnz     loc_140071A67
0x140071748  mov     rcx, [rbx+r13+10h]
0x14007174d  call    sqlite3IsRowid
0x140071752  test    eax, eax
0x140071754  jz      loc_140071A67
0x14007175a  mov     r12, [rbx+r13+8]
0x14007175f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140071763  mov     [rbp+0D0h+var_D0], r12
0x140071767  mov     [rbp+0D0h+arg_28], 1
0x14007176e  mov     [rbp+0D0h+var_108], r15d
0x140071772  jmp     short loc_1400717DB
0x140071774  movsx   eax, word ptr [r14+34h]
0x140071779  cmp     r11d, eax
0x14007177c  jnz     short loc_140071797
0x14007177e  mov     r13, [rbp+0D0h+arg_10]
0x140071785  mov     [rbp+0D0h+arg_28], 1
0x14007178c  mov     [rbp+0D0h+var_108], r15d
0x140071790  mov     r12, [rbx+r13+8]
0x140071795  jmp     short loc_1400717C3
0x140071797  cmp     [rbp+0D0h+var_120], r9
0x14007179b  jz      short loc_1400717AC
0x14007179d  test    byte ptr [r13+r12*8+12h], 1
0x1400717a3  jz      short loc_1400717AC
0x1400717a5  mov     byte ptr [rsp+78h], 1
0x1400717aa  jmp     short loc_1400717B8
0x1400717ac  test    byte ptr [r13+r12*8+12h], 60h
0x1400717b2  jnz     loc_1400719EF
0x1400717b8  mov     r13, [rbp+0D0h+arg_10]
0x1400717bf  mov     r12, [rbp+0D0h+var_D0]
0x1400717c3  mov     rcx, [rbp+0D0h+var_110]
0x1400717c7  mov     eax, r11d
0x1400717ca  mov     [rcx+rax*4], r15d
  ... truncated ...
```
