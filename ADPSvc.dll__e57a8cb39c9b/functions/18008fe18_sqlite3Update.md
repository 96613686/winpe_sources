# sqlite3Update

- ea: `0x18008fe18`
- end: `0x18009169a`
- name: `sqlite3Update`
- size: `6274`
- prototype: ``
- caller_count: `3`
- callee_count: `53`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003e7e0`
- `0x18009196c`
- `0x1800c3bd8`

## callees

- `0x180002cf8`
- `0x180037d8c`
- `0x18003f2e8`
- `0x180045b1c`
- `0x1800693b0`
- `0x180069d64`
- `0x18006e018`
- `0x18006e7b8`
- `0x18006f18c`
- `0x18006f704`
- `0x18006f8fc`
- `0x1800716fc`
- `0x1800717b0`
- `0x180073aec`
- `0x1800746dc`
- `0x180074ab0`
- `0x180076d6c`
- `0x180077020`
- `0x180078198`
- `0x1800796fc`
- `0x1800797bc`
- `0x18007a168`
- `0x18007a280`
- `0x18007ab30`
- `0x18007c6c0`
- `0x18007d478`
- `0x18007f7fc`
- `0x18007f908`
- `0x18007fd5c`
- `0x180080f0c`
- `0x180081b90`
- `0x18008a258`
- `0x18008e124`
- `0x18008e588`
- `0x18008ed60`
- `0x18008ed9c`
- `0x18008f1c8`
- `0x18008f34c`
- `0x18008f500`
- `0x18008fe18`
- `0x1800923d8`
- `0x1800924d4`
- `0x18009273c`
- `0x1800927e0`
- `0x180092870`
- `0x18009a3f0`
- `0x18009c8f4`
- `0x18009f1c8`
- `0x1800a2050`
- `0x1800b1a74`

## string_xrefs

- `0x18009049b`: `cannot UPDATE generated column "%s"`
- `0x180091653`: `rows updated`

## pseudocode

```c
__int64 __fastcall sqlite3Update(
        __int64 *a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rbx
  int *v9; // r15
  _DWORD *v10; // rdi
  __int64 *v11; // rsi
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
  unsigned __int8 v39; // di
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
  __int64 *v98; // rcx
  int v99; // ecx
  __int16 v100; // di
  int v101; // ecx
  int v102; // eax
  int v103; // edi
  int v104; // ebx
  int v105; // eax
  __int64 v106; // rax
  __int64 *v107; // rax
  __int64 *v108; // rcx
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
  __int64 v135; // r8
  __int64 v136; // r9
  signed int v137; // ebx
  int v138; // r12d
  int v139; // edx
  int v140; // ebx
  int v141; // eax
  signed int v142; // r8d
  int v143; // r15d
  unsigned int v144; // ebx
  signed int v145; // edi
  __int64 v146; // rax
  __int64 v147; // rcx
  __int16 v148; // ax
  int v149; // edx
  int v150; // r8d
  unsigned int v151; // r9d
  unsigned int v152; // edi
  int v153; // ebx
  __int64 v154; // rax
  unsigned int v155; // eax
  int v156; // eax
  int v157; // ebx
  int v158; // eax
  unsigned int v159; // edi
  int v160; // [rsp+28h] [rbp-E0h]
  unsigned int v161; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v162; // [rsp+78h] [rbp-90h]
  char v163; // [rsp+79h] [rbp-8Fh]
  char v164; // [rsp+79h] [rbp-8Fh]
  char v165; // [rsp+7Ah] [rbp-8Eh]
  int v166; // [rsp+7Ch] [rbp-8Ch]
  char v167; // [rsp+80h] [rbp-88h]
  int v168; // [rsp+84h] [rbp-84h]
  int v169; // [rsp+88h] [rbp-80h]
  unsigned int v170; // [rsp+88h] [rbp-80h]
  int v171; // [rsp+8Ch] [rbp-7Ch]
  unsigned int v172; // [rsp+8Ch] [rbp-7Ch]
  int v173; // [rsp+90h] [rbp-78h]
  __int64 Vdbe; // [rsp+98h] [rbp-70h]
  int v175; // [rsp+A0h] [rbp-68h]
  int v176; // [rsp+A4h] [rbp-64h]
  int v177; // [rsp+A8h] [rbp-60h]
  int v178; // [rsp+ACh] [rbp-5Ch]
  __int16 v179; // [rsp+B0h] [rbp-58h]
  unsigned int v180; // [rsp+B4h] [rbp-54h]
  __int64 v181; // [rsp+B8h] [rbp-50h]
  unsigned int v182; // [rsp+C0h] [rbp-48h]
  int v183; // [rsp+C0h] [rbp-48h]
  __int64 v184; // [rsp+C8h] [rbp-40h]
  int v185; // [rsp+D0h] [rbp-38h]
  int v186; // [rsp+D4h] [rbp-34h] BYREF
  int v187; // [rsp+D8h] [rbp-30h]
  int v188; // [rsp+DCh] [rbp-2Ch]
  unsigned int v189; // [rsp+E0h] [rbp-28h]
  int v190; // [rsp+E4h] [rbp-24h]
  int v191; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v192; // [rsp+F0h] [rbp-18h]
  size_t Size; // [rsp+F8h] [rbp-10h]
  int v194; // [rsp+100h] [rbp-8h]
  __int64 v195; // [rsp+108h] [rbp+0h]
  int v196; // [rsp+110h] [rbp+8h] BYREF
  int v197; // [rsp+114h] [rbp+Ch]
  __int64 v198; // [rsp+118h] [rbp+10h]
  void *v199; // [rsp+120h] [rbp+18h]
  __int64 v200; // [rsp+128h] [rbp+20h]
  __int64 v201; // [rsp+130h] [rbp+28h] BYREF
  int v202; // [rsp+138h] [rbp+30h]
  int v203; // [rsp+13Ch] [rbp+34h]
  int v204; // [rsp+140h] [rbp+38h]
  __int64 v205; // [rsp+148h] [rbp+40h]
  const char *v206; // [rsp+150h] [rbp+48h]
  __int64 *v207; // [rsp+158h] [rbp+50h]
  _OWORD v208[7]; // [rsp+160h] [rbp+58h] BYREF

  v8 = a4;
  v9 = a3;
  v200 = *a1;
  v10 = (_DWORD *)a2;
  v11 = a1;
  memset(v208, 0, 56);
  v196 = 0;
  v186 = 0;
  if ( *((_DWORD *)a1 + 12) )
    goto LABEL_96;
  v12 = sqlite3SrcListLookup(a1, a2);
  v205 = v12;
  v13 = v12;
  if ( !v12 )
    goto LABEL_96;
  v14 = *(_QWORD *)(v12 + 96);
  v15 = -32768;
  v169 = -32768;
  if ( v14 )
  {
    v15 = 0;
    v169 = 0;
    v16 = *(_QWORD *)(*v11 + 32);
    if ( *(_QWORD *)(v16 + 24) != v14 )
    {
      do
        ++v15;
      while ( *(_QWORD *)(32LL * v15 + v16 + 24) != v14 );
      v169 = v15;
    }
  }
  if ( (*(_QWORD *)(v12 + 88) || (v17 = *(_QWORD *)(*(_QWORD *)(*v11 + 32) + 56LL)) != 0 && *(_QWORD *)(v17 + 64))
    && !*((_BYTE *)v11 + 229) )
  {
    v18 = triggersReallyExist((_DWORD)v11, v13, 129, (_DWORD)v9, (__int64)&v196);
  }
  else
  {
    v18 = 0;
  }
  v19 = *v10 <= 1;
  v20 = *(_BYTE *)(v13 + 63);
  v165 = v20;
  v192 = v18;
  if ( v19 )
    v168 = 0;
  else
    v168 = *v9;
  if ( (v20 == 1 || *(__int16 *)(v13 + 54) <= 0) && (unsigned int)viewGetColumnNames(v11, v13)
    || (unsigned int)sqlite3IsReadOnly(v11, v13, v18) )
  {
    goto LABEL_95;
  }
  v21 = *((_DWORD *)v11 + 13);
  v22 = v21;
  v166 = v21;
  v188 = v21;
  v23 = v21 + 1;
  *((_DWORD *)v11 + 13) = v21 + 1;
  v24 = *(_BYTE *)(v13 + 48) >= 0;
  v187 = v21 + 1;
  if ( v24 )
  {
    v25 = 0;
    v181 = 0;
  }
  else
  {
    v25 = *(_QWORD *)(v13 + 16);
    v181 = v25;
    if ( v25 )
    {
      do
      {
        if ( (*(_DWORD *)(v25 + 100) & 3) == 2 )
          break;
        v25 = *(_QWORD *)(v25 + 40);
      }
      while ( v25 );
      v23 = v187;
      v181 = v25;
    }
  }
  v26 = *(_QWORD *)(v13 + 16);
  v27 = 0;
  v202 = 0;
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
      *((_DWORD *)v11 + 13) = ++v29;
      v26 = *(_QWORD *)(v26 + 40);
    }
    while ( v26 );
    v22 = v188;
    v202 = v27;
    v166 = v30;
  }
  if ( a8 )
  {
    v21 = *(_DWORD *)(a8 + 76);
    v166 = v21;
    v187 = *(_DWORD *)(a8 + 80);
    *((_DWORD *)v11 + 13) = v22;
  }
  v31 = v200;
  v10[19] = v21;
  v32 = v27;
  v33 = sqlite3DbMallocRawNN(v31, v27 + 4LL * (v27 + *(__int16 *)(v13 + 54) + 1) + 2);
  v184 = v33;
  if ( !v33 )
    goto LABEL_95;
  v198 = v33 + 4LL * *(__int16 *)(v13 + 54);
  v34 = (void *)(v198 + 4 + 4 * v32);
  v199 = v34;
  Size = v32 + 1;
  memset_0(v34, 1, v32 + 1);
  *((_BYTE *)v34 + Size) = 0;
  for ( i = 0; i < *(__int16 *)(v13 + 54); *(_DWORD *)(v184 + 4 * v36) = -1 )
    v36 = i++;
  v10 = (_DWORD *)a2;
  *((_QWORD *)&v208[0] + 1) = a2;
  *(_OWORD *)((char *)&v208[1] + 8) = 0;
  *(_QWORD *)((char *)&v208[2] + 12) = 0;
  DWORD1(v208[3]) = 0;
  *(_QWORD *)&v208[0] = v11;
  *(_QWORD *)&v208[1] = a8;
  DWORD2(v208[2]) = 512;
  v37 = 0;
  Vdbe = sqlite3GetVdbe(v11);
  if ( !Vdbe )
    goto LABEL_94;
  v195 = 0;
  v38 = 0;
  v185 = -1;
  v39 = 0;
  v167 = 0;
  v162 = 0;
  if ( *v9 > 0 )
  {
    v40 = 0;
    while ( 1 )
    {
      v41 = a3;
      v42 = v40;
      v43 = 8LL * v40;
      v44 = sqlite3StrIHash(*(_QWORD *)&a3[v43 + 4]);
      v163 = v44;
      if ( v168 == v45 )
      {
        v46 = sqlite3ResolveExprNames(v208, *(_QWORD *)&a3[v43 + 2]);
        v45 = 0;
        if ( v46 )
          goto LABEL_92;
        v44 = v163;
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
          v37 = v195;
          v41 = a3;
          goto LABEL_50;
        }
      }
      v206 = *(const char **)(v48 + 24LL * (unsigned int)v47);
      if ( (unsigned int)sqlite3StrICmp(v206, *(_QWORD *)&a3[v43 + 4]) )
        break;
      if ( v47 != *(__int16 *)(v13 + 52) )
      {
        if ( v181 && (*(_BYTE *)(v48 + 8 * v49 + 18) & 1) != 0 )
        {
          v167 = 1;
        }
        else if ( (*(_BYTE *)(v48 + 8 * v49 + 18) & 0x60) != 0 )
        {
          sqlite3ErrorMsg(v11, "cannot UPDATE generated column \"%s\"", v206);
LABEL_92:
          v9 = a3;
          goto LABEL_93;
        }
        v41 = a3;
        v37 = v195;
        goto LABEL_61;
      }
      v41 = a3;
      v162 = 1;
      v185 = v40;
      v37 = *(_QWORD *)&a3[v43 + 2];
LABEL_61:
      *(_DWORD *)(v184 + 4LL * (unsigned int)v47) = v40;
LABEL_50:
      v50 = *(__int16 *)(v13 + 54);
      v195 = v37;
      if ( v47 >= v50 )
      {
        if ( !v181 && (unsigned int)sqlite3IsRowid(*(_QWORD *)&v41[v43 + 4]) )
        {
          v37 = *(_QWORD *)&v41[v43 + 2];
          v51 = -1;
          v195 = v37;
          v162 = 1;
          v185 = v40;
          goto LABEL_63;
        }
        v9 = a3;
        sqlite3ErrorMsg(v11, "no such column: %s", *(const char **)&a3[8 * v42 + 4]);
        *((_BYTE *)v11 + 29) = 1;
LABEL_93:
        v10 = (_DWORD *)a2;
        goto LABEL_94;
      }
      v51 = v47;
      if ( v47 >= 0 )
      {
        v53 = *(_QWORD *)(v13 + 8);
        v195 = v37;
        v52 = *(const char **)(v53 + 24LL * v47);
      }
      else
      {
LABEL_63:
        v52 = "ROWID";
      }
      v15 = v169;
      v54 = sqlite3AuthCheck(
              (_DWORD)v11,
              23,
              *(_QWORD *)v13,
              (_DWORD)v52,
              *(_QWORD *)(32LL * v169 + *(_QWORD *)(v200 + 32)));
      if ( v54 == 1 )
        goto LABEL_92;
      if ( v54 == 2 )
        *(_DWORD *)(v184 + 4 * v51) = -1;
      if ( ++v40 >= *a3 )
      {
        v39 = v162;
        v38 = v167;
        goto LABEL_70;
      }
    }
    v44 = v163;
    goto LABEL_48;
  }
LABEL_70:
  v24 = (*(_BYTE *)(v13 + 48) & 0x60) == 0;
  v55 = v38 + v39;
  v164 = v38 + v39;
  v56 = 0;
  v206 = 0;
  v207 = 0;
  v177 = 0;
  v180 = 0;
  v189 = 0;
  v203 = 0;
  v191 = 0;
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
        if ( *(int *)(v184 + 4LL * v58) < 0 )
        {
          v59 = *(_QWORD *)(v13 + 8) + 24LL * v58;
          if ( (*(_BYTE *)(v59 + 18) & 0x60) != 0 )
          {
            v60 = sqlite3ColumnExpr(v13, v59, v162, 0);
            if ( (unsigned int)sqlite3ExprReferencesUpdatedColumn(v60, v184) )
            {
              *(_DWORD *)(v184 + 4LL * v58) = 99999;
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
    v15 = v169;
    v55 = v164;
  }
  *(_QWORD *)(a2 + 88) = (*(_BYTE *)(v13 + 63) != 1) - 1LL;
  v197 = v55;
  v61 = sqlite3FkRequired(v11, v13, v184, v55);
  v175 = v61;
  if ( a5 == 5 )
    v186 = 1;
  v62 = *(_QWORD *)(v13 + 16);
  v63 = 0;
  v171 = 0;
  v64 = 0;
  if ( v62 )
  {
    v65 = v199;
    while ( !v164 )
    {
      if ( v61 > 1 )
        break;
      if ( v62 == v181 )
        break;
      v66 = *(_QWORD *)(v62 + 72);
      if ( v66 )
      {
        v67 = sqlite3ExprReferencesUpdatedColumn(v66, v184);
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
            v71 = sqlite3ExprReferencesUpdatedColumn(*(_QWORD *)(32LL * v69 + *(_QWORD *)(v62 + 80) + 8), v184);
            v63 = 0;
          }
          else
          {
            v71 = *(_DWORD *)(v184 + 4LL * *(__int16 *)(v70 + 2LL * v69)) >= 0;
          }
          if ( v71 )
            break;
          if ( ++v69 >= *(unsigned __int16 *)(v62 + 94) )
            goto LABEL_105;
        }
        v68 = ++*((_DWORD *)v11 + 14);
        v64 = v171;
        *((_DWORD *)v11 + 14) = v68 + *(unsigned __int16 *)(v62 + 96);
        if ( a5 == 11 && *(_BYTE *)(v62 + 98) == 5 )
          v186 = 1;
LABEL_113:
        if ( v68 )
          goto LABEL_107;
        goto LABEL_106;
      }
LABEL_105:
      v64 = v171;
LABEL_106:
      v65[v64 + 1] = 0;
LABEL_107:
      v75 = v198;
      v76 = v64++;
      v171 = v64;
      *(_DWORD *)(v198 + 4 * v76) = v68;
      v62 = *(_QWORD *)(v62 + 40);
      v61 = v175;
      if ( !v62 )
      {
        v13 = v205;
        v15 = v169;
        v56 = v191;
        goto LABEL_116;
      }
    }
    v68 = ++*((_DWORD *)v11 + 14);
    *((_DWORD *)v11 + 14) = v68 + *(unsigned __int16 *)(v62 + 96);
    goto LABEL_113;
  }
  v75 = v198;
LABEL_116:
  v77 = (int *)(v11 + 7);
  *(_DWORD *)(v75 + 4LL * v64) = ++*((_DWORD *)v11 + 14);
  if ( v186 )
  {
    memset_0(v199, 1, Size);
    v63 = 0;
  }
  if ( !*((_BYTE *)v11 + 30) )
  {
    v77 = (int *)(v11 + 7);
    *(_DWORD *)(Vdbe + 200) |= 0x10u;
  }
  if ( v192 )
  {
    v78 = v77;
  }
  else
  {
    if ( !v175 )
    {
      v78 = v77;
      goto LABEL_126;
    }
    v78 = (int *)(v11 + 7);
  }
  v63 = 1;
LABEL_126:
  sqlite3BeginWriteOperation(v11, v63, (unsigned int)v15);
  v79 = 0;
  if ( *(_BYTE *)(v13 + 63) == 1 )
    goto LABEL_138;
  v80 = *((_DWORD *)v11 + 14) + 1;
  v81 = v192;
  v177 = v80;
  v56 = *(_DWORD *)(v198 + 4LL * v64);
  v191 = v56;
  *v77 = v80;
  if ( v167 )
  {
    v78 = v77;
  }
  else if ( !v81 )
  {
    v82 = v175;
    if ( !v175 )
    {
      v83 = v80;
      goto LABEL_133;
    }
  }
  v83 = v80 + *(__int16 *)(v13 + 54);
  v203 = v80 + 1;
  v82 = v175;
  *v78 = v83;
LABEL_133:
  if ( v164 || v81 || v82 )
  {
    v80 = v83 + 1;
    *v78 = ++v83;
  }
  v180 = v80;
  v189 = v83 + 1;
  *v78 = v83 + *(__int16 *)(v13 + 54);
LABEL_138:
  v84 = v165;
  if ( v165 == 2 )
  {
    v206 = (const char *)v11[47];
    v11[47] = *(_QWORD *)v13;
    v84 = 2;
    v207 = v11;
  }
  if ( !v168 )
  {
    if ( v84 == 2 )
      sqlite3MaterializeView((_DWORD)v11, v13, a4, a6, a7, v166);
    v85 = sqlite3ResolveExprNames(v208, a4);
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
    updateVirtualTable((_DWORD)v11, a2, v13, (_DWORD)a3, v195, v184, a4, a5);
    goto LABEL_359;
  }
  v86 = --*((_DWORD *)v11 + 17);
  v87 = a8;
  v204 = 0;
  v170 = v86;
  if ( (*(_QWORD *)(v200 + 48) & 0x100000000LL) == 0 || v11[23] || *((_BYTE *)v11 + 30) || *((_BYTE *)v11 + 227) )
  {
    v88 = Vdbe;
  }
  else
  {
    v88 = Vdbe;
    if ( !a8 )
    {
      v89 = *((_DWORD *)v11 + 14) + 1;
      v204 = v89;
      *((_DWORD *)v11 + 14) = v89;
      sqlite3VdbeAddOp3(Vdbe, 71, 0, v89, 0);
      v87 = 0;
      v79 = 0;
    }
  }
  if ( !v168 && *(char *)(v13 + 48) >= 0 )
  {
    v179 = 0;
    v90 = 0;
    v178 = 0;
    sqlite3VdbeAddOp3(v88, 75, v168, v56, v177);
    v91 = *((_DWORD *)v11 + 13);
    v173 = v91;
    *((_DWORD *)v11 + 13) = v91 + 1;
    v182 = sqlite3VdbeAddOp3(v88, 118, v91, 0, v56);
    v92 = v182;
    if ( !a8 )
      goto LABEL_156;
LABEL_194:
    v96 = 1;
    Size = 0;
    v176 = 1;
    sqlite3ExprIfFalse(v11, a4, v86, 16);
    LODWORD(v95) = v201;
    v79 = 0;
    v194 = 0;
    v205 = v201;
    goto LABEL_195;
  }
  if ( v181 )
    v100 = *(_WORD *)(v181 + 94);
  else
    v100 = 0;
  v101 = v100;
  v179 = v100;
  v90 = *((_DWORD *)v11 + 14) + 1;
  v178 = v168 + v100 + v90;
  *((_DWORD *)v11 + 14) = v178;
  if ( v87 )
  {
    v173 = 0;
    if ( !v168 )
    {
      v92 = 0;
      v182 = 0;
      goto LABEL_194;
    }
  }
  else
  {
    if ( v165 == 2 )
      v102 = *(__int16 *)(v13 + 54);
    else
      v102 = 0;
    v103 = *((_DWORD *)v11 + 13);
    v104 = v168 + v101 + v102;
    v173 = v103;
    *((_DWORD *)v11 + 13) = v103 + 1;
    if ( v181 )
      sqlite3VdbeAddOp3(v88, 75, 0, v90, v90 + v101 - 1);
    v92 = sqlite3VdbeAddOp3(v88, 118, v103, v104, 0);
    v182 = v92;
    v105 = v181;
    if ( v181 )
    {
      v106 = sqlite3KeyInfoOfIndex(v11, v181);
      if ( v106 )
      {
        *(_WORD *)(v106 + 8) = v104;
        sqlite3VdbeAppendP4(v88, v106, 4294967288LL);
      }
      v105 = v181;
    }
    if ( !v168 )
    {
LABEL_156:
      v93 = 4;
      if ( !*((_BYTE *)v11 + 30) && !v192 && !v175 && !v164 && !v186 && (!a4 || (*(_DWORD *)(a4 + 4) & 0x400000) == 0) )
        v93 = 12;
      v10 = (_DWORD *)a2;
      v94 = sqlite3WhereBegin((_DWORD)v11, a2, a4, 0, 0, 0, v93, v187);
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
      v205 = v95;
      v201 = v95;
      v176 = v96;
      v194 = v97;
      if ( v96 != 1 )
      {
        v98 = v11;
        if ( v11[22] )
          v98 = (__int64 *)v11[22];
        *((_BYTE *)v98 + 32) = 1;
        v99 = v166;
        if ( v96 == 2 && v95 >= 0 && HIDWORD(v95) != v166 && *((_BYTE *)v199 + HIDWORD(v95) - v188) )
        {
          v96 = 0;
          v176 = 0;
        }
LABEL_196:
        v24 = *(_BYTE *)(v13 + 48) >= 0;
        v190 = 0;
        if ( v24 )
        {
          sqlite3VdbeAddOp3(v88, 135, v99, v177, 0);
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
            v110 = *((_DWORD *)v11 + 14) + 1;
            v111 = v198;
            v112 = v191;
            *((_DWORD *)v11 + 14) = v110;
            *(_DWORD *)(v111 + 4LL * v171) = v110;
            sqlite3VdbeAddOp3(v88, 128, v173, v112, v177);
          }
        }
        else
        {
          v113 = 0;
          if ( v179 > 0 )
          {
            do
            {
              sqlite3ExprCodeGetColumnOfTable(
                Vdbe,
                v13,
                v166,
                *(__int16 *)(*(_QWORD *)(v181 + 8) + 2LL * v113),
                v113 + v90);
              ++v113;
            }
            while ( (int)v113 < v179 );
            LODWORD(v95) = v205;
            v79 = 0;
            v11 = a1;
            v92 = v182;
          }
          v96 = v176;
          if ( v176 )
          {
            v88 = Vdbe;
            if ( v92 )
            {
              sqlite3VdbeChangeToNoop(Vdbe, v92);
              v79 = 0;
            }
            v190 = v179;
            v178 = v90;
            goto LABEL_212;
          }
          v114 = *(_QWORD *)(v181 + 32);
          if ( !v114 )
            v114 = computeIndexAffStr(v200, v181);
          v115 = sqlite3VdbeAddOp3(Vdbe, 97, v90, v179, v178);
          v116 = v114;
          v88 = Vdbe;
          sqlite3VdbeChangeP4(Vdbe, v115, v116, (unsigned int)v179);
          sqlite3VdbeAddOp4Int(Vdbe, 138, v173, v178, v90, v179);
          v96 = 0;
        }
        v79 = 0;
        goto LABEL_212;
      }
LABEL_195:
      v99 = v166;
      goto LABEL_196;
    }
    updateFromSelect((_DWORD)v11, v103, v105, (_DWORD)a3, a2, a4);
    v79 = 0;
    if ( v165 == 2 )
      v166 = v103;
  }
  v107 = (__int64 *)v11[22];
  v108 = v11;
  LODWORD(v95) = v201;
  v109 = 0;
  v194 = 1;
  if ( v107 )
    v108 = v107;
  Size = 0;
  v96 = 0;
  v176 = 0;
  v190 = v179;
  *((_BYTE *)v108 + 32) = 1;
  v178 = v90;
LABEL_213:
  v117 = v170;
  v172 = v170;
  v183 = 0;
  if ( a8 )
  {
    v125 = Vdbe;
    v124 = v166;
LABEL_254:
    v128 = v173;
    goto LABEL_255;
  }
  if ( !v168 && v96 != 2 )
  {
    sqlite3WhereEnd(v109);
    v79 = 0;
  }
  v118 = HIDWORD(v201);
  if ( v165 != 2 )
  {
    v119 = 0;
    LODWORD(v201) = 0;
    v191 = 0;
    if ( v176 )
    {
      v120 = v188;
      v121 = v199;
      if ( (int)v95 >= 0 )
        *((_BYTE *)v199 + (int)v95 - v188) = 0;
      if ( v118 >= 0 )
        v121[v118 - v120] = 0;
      if ( v176 == 2 && v202 - (v118 >= 0) > 0 )
        v119 = sqlite3VdbeAddOp3(Vdbe, 15, 0, 0, 0);
    }
    sqlite3OpenTableAndIndices((_DWORD)v11, v13, 113, 0, v188, (__int64)v199, (__int64)&v201, (__int64)&v191);
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
  v123 = v176;
  if ( v176 )
  {
    v124 = v166;
    v125 = Vdbe;
    if ( (_DWORD)v95 == v166 )
    {
      v126 = v178;
    }
    else
    {
      v24 = v118 == v166;
      v126 = v178;
      if ( !v24 )
      {
        sqlite3VdbeAddOp4Int(Vdbe, 28, v166, v170, v178, v190);
        v123 = v176;
        v79 = 0;
      }
    }
    if ( v123 != 1 )
    {
      v117 = *((_DWORD *)v11 + 17) - 1;
      v172 = v117;
      *((_DWORD *)v11 + 17) = v117;
    }
    v127 = v177;
    if ( v181 != v79 )
      v127 = v126;
    sqlite3VdbeAddOp3(Vdbe, 50, v127, v170, v79);
    goto LABEL_254;
  }
  if ( !v181 && v168 == (_DWORD)v79 )
  {
    v125 = Vdbe;
    v128 = v173;
    sqlite3VdbeAddOp3(Vdbe, 36, v173, v170, v79);
    v117 = *((_DWORD *)v11 + 17) - 1;
    v129 = v177;
    v172 = v117;
    *((_DWORD *)v11 + 17) = v117;
    v183 = sqlite3VdbeAddOp3(Vdbe, 135, v173, v177, 0);
LABEL_242:
    v124 = v166;
    sqlite3VdbeAddOp3(v125, 31, v166, v117, v129);
LABEL_255:
    v130 = v168;
    goto LABEL_256;
  }
  v128 = v173;
  v117 = *((_DWORD *)v11 + 17) - 1;
  v172 = v117;
  *((_DWORD *)v11 + 17) = v117;
  sqlite3VdbeAddOp3(v88, 36, v173, v170, v79);
  v183 = *(_DWORD *)(v88 + 144);
  v130 = v168;
  if ( !v168 )
  {
    v125 = Vdbe;
    sqlite3VdbeAddOp3(Vdbe, 134, v173, v178, 0);
    v124 = v166;
    sqlite3VdbeAddOp4Int(Vdbe, 28, v166, v117, v178, 0);
    goto LABEL_255;
  }
  if ( v165 != 2 )
  {
    if ( v181 )
    {
      v131 = v179;
      v132 = 0;
      if ( v179 > 0 )
      {
        do
        {
          sqlite3VdbeAddOp3(v88, 94, v173, v132, v132 + v90);
          ++v132;
        }
        while ( v132 < v179 );
        v11 = a1;
        v131 = v179;
      }
      v124 = v166;
      v160 = v90;
      v125 = Vdbe;
      sqlite3VdbeAddOp4Int(Vdbe, 28, v166, v117, v160, v131);
      goto LABEL_254;
    }
    v125 = Vdbe;
    v129 = v177;
    sqlite3VdbeAddOp3(Vdbe, 135, v173, v177, 0);
    goto LABEL_242;
  }
  v125 = Vdbe;
  v124 = v166;
LABEL_256:
  if ( v162 )
  {
    if ( v130 )
      sqlite3VdbeAddOp3(v125, 94, v128, v185, v180);
    else
      sqlite3ExprCode(v11, v195, v180);
    sqlite3VdbeAddOp3(v125, 13, v180, 0, 0);
  }
  if ( v167 )
    goto LABEL_264;
  if ( v175 )
    goto LABEL_265;
  if ( v192 )
  {
LABEL_264:
    if ( !v175 )
    {
      v133 = 0;
      goto LABEL_267;
    }
LABEL_265:
    v133 = sqlite3FkOldmask(v11, v13);
LABEL_267:
    v134 = sqlite3TriggerColmask((_DWORD)v11, v192, (_DWORD)a3, 0, 3, v13, a5) | v133;
    v137 = 0;
    if ( *(__int16 *)(v13 + 54) > 0 )
    {
      v138 = v203;
      do
      {
        v139 = v138 + (__int16)sqlite3TableColumnToStorage(v13, (unsigned __int16)v137, v135, v136);
        if ( v134 == -1
          || v137 < 32 && _bittest(&v134, v137)
          || (*(_BYTE *)(*(_QWORD *)(v13 + 8) + 24LL * v137 + 18) & 1) != 0 )
        {
          sqlite3ExprCodeGetColumnOfTable(v125, v13, v124, v137, v139);
        }
        else
        {
          sqlite3VdbeAddOp3(v125, 75, 0, v139, 0);
        }
        ++v137;
      }
      while ( v137 < *(__int16 *)(v13 + 54) );
      v11 = a1;
      v117 = v172;
    }
    if ( !v162 && !v181 )
      sqlite3VdbeAddOp3(v125, 80, v177, v180, 0);
  }
  v140 = a5;
  v141 = sqlite3TriggerColmask((_DWORD)v11, v192, (_DWORD)a3, 1, 1, v13, a5);
  LOWORD(v142) = *(_WORD *)(v13 + 54);
  v143 = v141;
  if ( (__int16)v142 <= 0 )
    goto LABEL_300;
  v144 = v189;
  v145 = 0;
  do
  {
    if ( v145 == *(__int16 *)(v13 + 52) )
    {
LABEL_295:
      v150 = 0;
      v161 = 0;
      v151 = v144;
      v149 = 75;
LABEL_296:
      sqlite3VdbeAddOp3(v125, v149, v150, v151, v161);
      goto LABEL_298;
    }
    v146 = *(_QWORD *)(v13 + 8);
    if ( (*(_BYTE *)(v146 + 24LL * v145 + 18) & 0x60) != 0 )
    {
      if ( (*(_BYTE *)(v146 + 24LL * v145 + 18) & 0x20) != 0 )
        --v144;
      goto LABEL_298;
    }
    v147 = *(int *)(v184 + 4LL * v145);
    if ( (int)v147 >= 0 )
    {
      if ( !v168 )
      {
        sqlite3ExprCode(v11, *(_QWORD *)&a3[8 * v147 + 2], v144);
        goto LABEL_298;
      }
      v148 = v179;
      v161 = v144;
      v149 = 94;
      if ( v165 == 2 )
        v148 = v142;
      v150 = v173;
      v151 = v147 + v148;
      goto LABEL_296;
    }
    if ( (v196 & 1) != 0 && v145 <= 31 && !_bittest(&v143, v145) )
      goto LABEL_295;
    sqlite3ExprCodeGetColumnOfTable(v125, v13, v166, v145, v144);
    v194 = 0;
LABEL_298:
    v142 = *(__int16 *)(v13 + 54);
    ++v145;
    ++v144;
  }
  while ( v145 < v142 );
  v117 = v172;
  v140 = a5;
LABEL_300:
  v152 = v189;
  if ( (*(_BYTE *)(v13 + 48) & 0x60) != 0 )
    sqlite3ComputeGeneratedColumns(v11, v189, v13);
  if ( (v196 & 1) == 0 )
  {
    if ( v165 != 2 )
      goto LABEL_320;
    v157 = v176;
    goto LABEL_340;
  }
  sqlite3TableAffinity(v125, v13, v189);
  v9 = a3;
  sqlite3CodeRowTrigger((_DWORD)v11, v192, 129, (_DWORD)a3, 1, v13, v177, v140, v117);
  if ( v165 == 2 )
  {
    v157 = v176;
  }
  else
  {
    if ( v181 )
      sqlite3VdbeAddOp4Int(v125, 28, v166, v117, v178, v190);
    else
      sqlite3VdbeAddOp3(v125, 31, v166, v117, v177);
    v153 = 0;
    if ( *(__int16 *)(v13 + 54) > 0 )
    {
      do
      {
        v154 = *(_QWORD *)(v13 + 8);
        if ( (*(_BYTE *)(v154 + 24LL * v153 + 18) & 0x60) != 0 )
        {
          v24 = (*(_BYTE *)(v154 + 24LL * v153 + 18) & 0x20) == 0;
          v155 = v152 - 1;
          if ( v24 )
            v155 = v152;
          v152 = v155;
        }
        else if ( *(int *)(v184 + 4LL * v153) < 0 && v153 != *(__int16 *)(v13 + 52) )
        {
          sqlite3ExprCodeGetColumnOfTable(v125, v13, v166, v153, v152);
        }
        ++v153;
        ++v152;
      }
      while ( v153 < *(__int16 *)(v13 + 54) );
      v11 = a1;
    }
    if ( (*(_BYTE *)(v13 + 48) & 0x60) != 0 )
      sqlite3ComputeGeneratedColumns(v11, v189, v13);
LABEL_320:
    sqlite3GenerateConstraintChecks(
      (_DWORD)v11,
      v13,
      v198,
      v166,
      v187,
      v180,
      v177,
      v164,
      a5,
      v117,
      (__int64)&v186,
      v184,
      0);
    if ( v186 || v164 )
    {
      if ( v181 )
        sqlite3VdbeAddOp4Int(v125, 28, v166, v117, v178, v190);
      else
        sqlite3VdbeAddOp3(v125, 31, v166, v117, v177);
    }
    if ( v175 )
      sqlite3FkCheck((_DWORD)v11, v13, v177, 0, v184, v197);
    sqlite3GenerateRowIndexDelete((_DWORD)v11, v13, v166, v187, v198, -1);
    if ( v194 )
      sqlite3VdbeAddOp3(v125, 143, v166, 0, 0);
    v156 = v175;
    if ( v175 > 1 || v164 )
    {
      sqlite3VdbeAddOp3(v125, 130, v166, 0, 0);
      v156 = v175;
    }
    if ( v156 )
      sqlite3FkCheck((_DWORD)v11, v13, 0, v180, v184, v197);
    v157 = v176;
    v158 = 6;
    if ( v176 != 2 )
      v158 = 4;
    sqlite3CompleteInsertion((_DWORD)v11, v13, v166, v187, v180, v198, v158, 0, 0);
    if ( v175 )
    {
      v9 = a3;
      sqlite3FkActions((_DWORD)v11, v13, (_DWORD)a3, v177, v184, v197);
      goto LABEL_341;
    }
LABEL_340:
    v9 = a3;
  }
LABEL_341:
  v159 = v204;
  if ( v204 )
    sqlite3VdbeAddOp3(v125, 86, v204, 1, 0);
  if ( v192 )
    sqlite3CodeRowTrigger((_DWORD)v11, v192, 129, (_DWORD)v9, 2, v13, v177, a5, v117);
  if ( v157 != 1 )
  {
    sqlite3VdbeResolveLabel(v125, v117);
    if ( v157 == 2 )
      sqlite3WhereEnd(Size);
    else
      sqlite3VdbeAddOp3(v125, 39, v173, v183, 0);
  }
  sqlite3VdbeResolveLabel(v125, v170);
  if ( !*((_BYTE *)v11 + 30) && !v11[23] && !a8 && v11[21] )
    autoIncrementEnd(v11);
  if ( v159 )
    sqlite3CodeChangeCount(v125, v159, "rows updated");
LABEL_358:
  v10 = (_DWORD *)a2;
LABEL_359:
  if ( v207 )
    v207[47] = (__int64)v206;
LABEL_94:
  sqlite3DbFreeNN(v200);
LABEL_95:
  v8 = a4;
LABEL_96:
  v72 = v10;
  v73 = v200;
  result = sqlite3SrcListDelete(v200, v72);
  if ( v9 )
    result = exprListDeleteNN(v73, v9);
  if ( v8 )
    return sqlite3ExprDeleteNN(v73, v8);
  return result;
}

```

## disassembly

```asm
0x18008fe18  mov     rax, rsp
0x18008fe1b  mov     [rax+20h], r9
0x18008fe1f  mov     [rax+18h], r8
0x18008fe23  mov     [rax+10h], rdx
0x18008fe27  mov     [rax+8], rcx
0x18008fe2b  push    rbp
0x18008fe2c  push    rbx
0x18008fe2d  push    rsi
0x18008fe2e  push    rdi
0x18008fe2f  push    r12
0x18008fe31  push    r13
0x18008fe33  push    r14
0x18008fe35  push    r15
0x18008fe37  lea     rbp, [rax-0D8h]
0x18008fe3e  sub     rsp, 198h
0x18008fe45  xor     eax, eax
0x18008fe47  xor     r12d, r12d
0x18008fe4a  xorps   xmm0, xmm0
0x18008fe4d  mov     [rbp+0D0h+var_48], rax
0x18008fe54  mov     rbx, r9
0x18008fe57  mov     rax, [rcx]
0x18008fe5a  mov     r15, r8
0x18008fe5d  mov     [rbp+0D0h+var_B0], rax
0x18008fe61  mov     rdi, rdx
0x18008fe64  mov     rsi, rcx
0x18008fe67  movups  [rbp+0D0h+var_78], xmm0
0x18008fe6b  mov     [rbp+0D0h+var_C8], r12d
0x18008fe6f  movups  [rbp+0D0h+var_68], xmm0
0x18008fe73  mov     [rbp+0D0h+var_104], r12d
0x18008fe77  movups  [rbp+0D0h+var_58], xmm0
0x18008fe7b  cmp     [rcx+30h], r12d
0x18008fe7f  jnz     loc_1800904CC
0x18008fe85  call    sqlite3SrcListLookup
0x18008fe8a  mov     [rbp+0D0h+var_90], rax
0x18008fe8e  mov     r14, rax
0x18008fe91  test    rax, rax
0x18008fe94  jz      loc_1800904CC
0x18008fe9a  mov     rcx, [rax+60h]
0x18008fe9e  mov     r13d, 0FFFF8000h
0x18008fea4  mov     [rbp+0D0h+var_150], r13d
0x18008fea8  test    rcx, rcx
0x18008feab  jz      short loc_18008FED6
0x18008fead  mov     rax, [rsi]
0x18008feb0  mov     r13d, r12d
0x18008feb3  mov     [rbp+0D0h+var_150], r12d
0x18008feb7  mov     rdx, [rax+20h]
0x18008febb  cmp     [rdx+18h], rcx
0x18008febf  jz      short loc_18008FED6
0x18008fec1  inc     r13d
0x18008fec4  movsxd  rax, r13d
0x18008fec7  shl     rax, 5
0x18008fecb  cmp     [rax+rdx+18h], rcx
0x18008fed0  jnz     short loc_18008FEC1
0x18008fed2  mov     [rbp+0D0h+var_150], r13d
0x18008fed6  cmp     [r14+58h], r12
0x18008feda  jnz     short loc_18008FEF2
0x18008fedc  mov     rax, [rsi]
0x18008fedf  mov     rcx, [rax+20h]
0x18008fee3  mov     rax, [rcx+38h]
0x18008fee7  test    rax, rax
0x18008feea  jz      short loc_18008FEFB
0x18008feec  cmp     [rax+40h], r12
0x18008fef0  jz      short loc_18008FEFB
0x18008fef2  cmp     [rsi+0E5h], r12b
0x18008fef9  jz      short loc_18008FF00
0x18008fefb  mov     rbx, r12
0x18008fefe  jmp     short loc_18008FF20
0x18008ff00  lea     rax, [rbp+0D0h+var_C8]
0x18008ff04  mov     r9, r15
0x18008ff07  mov     r8d, 81h
0x18008ff0d  mov     [rsp+1D0h+var_1B0], rax
0x18008ff12  mov     rdx, r14
0x18008ff15  mov     rcx, rsi
0x18008ff18  call    triggersReallyExist
0x18008ff1d  mov     rbx, rax
0x18008ff20  cmp     dword ptr [rdi], 1
0x18008ff23  mov     cl, [r14+3Fh]
0x18008ff27  mov     [rsp+72h], cl
0x18008ff2b  mov     [rbp+0D0h+var_E8], rbx
0x18008ff2f  jle     short loc_18008FF3A
0x18008ff31  mov     eax, [r15]
0x18008ff34  mov     [rsp+7Ch], eax
0x18008ff38  jmp     short loc_18008FF3F
0x18008ff3a  mov     [rsp+7Ch], r12d
0x18008ff3f  cmp     cl, 1
0x18008ff42  jz      short loc_18008FF4B
0x18008ff44  cmp     [r14+36h], r12w
0x18008ff49  jg      short loc_18008FF5E
0x18008ff4b  mov     rdx, r14
0x18008ff4e  mov     rcx, rsi
0x18008ff51  call    viewGetColumnNames
0x18008ff56  test    eax, eax
0x18008ff58  jnz     loc_1800904C5
0x18008ff5e  mov     r8, rbx
0x18008ff61  mov     rdx, r14
0x18008ff64  mov     rcx, rsi
0x18008ff67  call    sqlite3IsReadOnly
0x18008ff6c  test    eax, eax
0x18008ff6e  jnz     loc_1800904C5
0x18008ff74  mov     r9d, [rsi+34h]
0x18008ff78  mov     edx, r9d
0x18008ff7b  mov     [rsp+1D0h+var_15C], r9d
0x18008ff80  mov     [rbp+0D0h+var_FC], edx
0x18008ff83  lea     eax, [r9+1]
0x18008ff87  mov     [rsi+34h], eax
0x18008ff8a  test    byte ptr [r14+30h], 80h
0x18008ff8f  mov     [rbp+0D0h+var_100], eax
0x18008ff92  jnz     short loc_18008FF9D
0x18008ff94  mov     r10, r12
0x18008ff97  mov     [rbp+0D0h+var_120], r12
0x18008ff9b  jmp     short loc_18008FFC4
0x18008ff9d  mov     r10, [r14+10h]
0x18008ffa1  mov     [rbp+0D0h+var_120], r10
0x18008ffa5  test    r10, r10
0x18008ffa8  jz      short loc_18008FFC4
0x18008ffaa  mov     eax, [r10+64h]
0x18008ffae  and     al, 3
0x18008ffb0  cmp     al, 2
0x18008ffb2  jz      short loc_18008FFBD
0x18008ffb4  mov     r10, [r10+28h]
0x18008ffb8  test    r10, r10
0x18008ffbb  jnz     short loc_18008FFAA
0x18008ffbd  mov     eax, [rbp+0D0h+var_100]
0x18008ffc0  mov     [rbp+0D0h+var_120], r10
0x18008ffc4  mov     rcx, [r14+10h]
0x18008ffc8  mov     r11d, r12d
0x18008ffcb  mov     [rbp+0D0h+var_A0], r12d
0x18008ffcf  test    rcx, rcx
0x18008ffd2  jz      short loc_18009000B
0x18008ffd4  mov     r8d, eax
0x18008ffd7  mov     edx, eax
0x18008ffd9  cmp     r10, rcx
0x18008ffdc  mov     eax, edx
0x18008ffde  cmovnz  edx, r8d
0x18008ffe2  cmovnz  eax, r9d
0x18008ffe6  inc     r11d
0x18008ffe9  mov     r9d, eax
0x18008ffec  lea     r8d, [rdx+1]
0x18008fff0  mov     [rsi+34h], r8d
0x18008fff4  mov     edx, r8d
0x18008fff7  mov     rcx, [rcx+28h]
0x18008fffb  test    rcx, rcx
0x18008fffe  jnz     short loc_18008FFD9
0x180090000  mov     edx, [rbp+0D0h+var_FC]
0x180090003  mov     [rbp+0D0h+var_A0], r11d
0x180090007  mov     [rsp+1D0h+var_15C], eax
0x18009000b  mov     r12, [rbp+0D0h+arg_38]
0x180090012  test    r12, r12
0x180090015  jz      short loc_18009002C
0x180090017  mov     r9d, [r12+4Ch]
0x18009001c  mov     eax, [r12+50h]
0x180090021  mov     [rsp+1D0h+var_15C], r9d
0x180090026  mov     [rbp+0D0h+var_100], eax
0x180090029  mov     [rsi+34h], edx
0x18009002c  mov     rcx, [rbp+0D0h+var_B0]
0x180090030  mov     [rdi+4Ch], r9d
0x180090034  movsx   eax, word ptr [r14+36h]
0x180090039  inc     eax
0x18009003b  movsxd  rbx, r11d
0x18009003e  add     eax, r11d
0x180090041  cdqe
0x180090043  lea     rdx, ds:2[rax*4]
0x18009004b  add     rdx, rbx
0x18009004e  call    sqlite3DbMallocRawNN
0x180090053  mov     [rbp+0D0h+var_110], rax
0x180090057  test    rax, rax
0x18009005a  jz      loc_1800904C5
0x180090060  movsx   rcx, word ptr [r14+36h]
0x180090065  mov     edx, 1; Val
0x18009006a  lea     rax, [rax+rcx*4]
0x18009006e  lea     rdi, [rax+4]
0x180090072  mov     [rbp+0D0h+var_C0], rax
0x180090076  lea     rdi, [rdi+rbx*4]
0x18009007a  inc     rbx
0x18009007d  mov     r8, rbx; Size
0x180090080  mov     [rbp+0D0h+var_B8], rdi
0x180090084  mov     rcx, rdi; void *
0x180090087  mov     [rbp+0D0h+Size], rbx
0x18009008b  call    memset_0
0x180090090  xor     r8d, r8d
0x180090093  mov     [rbx+rdi], r8b
0x180090097  mov     ecx, r8d
0x18009009a  cmp     r8w, [r14+36h]
0x18009009f  jge     short loc_1800900BA
0x1800900a1  mov     rdx, [rbp+0D0h+var_110]
0x1800900a5  movsxd  rax, ecx
0x1800900a8  inc     ecx
0x1800900aa  mov     dword ptr [rdx+rax*4], 0FFFFFFFFh
0x1800900b1  movsx   eax, word ptr [r14+36h]
0x1800900b6  cmp     ecx, eax
0x1800900b8  jl      short loc_1800900A5
0x1800900ba  mov     rdi, [rbp+0D0h+arg_8]
0x1800900c1  xorps   xmm0, xmm0
0x1800900c4  mov     rcx, rsi
0x1800900c7  mov     qword ptr [rbp+0D0h+var_78+8], rdi
0x1800900cb  movdqu  [rbp+0D0h+var_68+8], xmm0
0x1800900d0  mov     qword ptr [rbp+0D0h+var_58+0Ch], r8
0x1800900d7  mov     dword ptr [rbp+0D0h+var_48+4], r8d
0x1800900de  mov     qword ptr [rbp+0D0h+var_78], rsi
0x1800900e2  mov     qword ptr [rbp+0D0h+var_68], r12
0x1800900e6  mov     dword ptr [rbp+0D0h+var_58+8], 200h
0x1800900f0  call    sqlite3GetVdbe
0x1800900f5  xor     r12d, r12d
0x1800900f8  mov     [rbp+0D0h+var_140], rax
0x1800900fc  test    rax, rax
0x1800900ff  jz      loc_1800904B8
0x180090105  xor     r9d, r9d
0x180090108  mov     [rbp+0D0h+var_D0], r12
0x18009010c  mov     al, r9b
0x18009010f  mov     [rbp+0D0h+var_108], 0FFFFFFFFh
0x180090116  mov     dil, r9b
0x180090119  mov     [rsp+78h], al
0x18009011d  mov     [rsp+1D0h+var_160], r9b
0x180090122  cmp     [r15], r9d
0x180090125  jle     loc_180090314
0x18009012b  mov     r15d, r9d
0x18009012e  mov     r13, [rbp+0D0h+arg_10]
0x180090135  movsxd  rdi, r15d
0x180090138  mov     rbx, rdi
0x18009013b  shl     rbx, 5
0x18009013f  mov     rcx, [rbx+r13+10h]
0x180090144  call    sqlite3StrIHash
0x180090149  mov     cl, al
0x18009014b  mov     [rsp+71h], al
0x18009014f  cmp     [rsp+7Ch], r9d
0x180090154  jnz     short loc_180090173
0x180090156  mov     rdx, [rbx+r13+8]
0x18009015b  lea     rcx, [rbp+0D0h+var_78]
0x18009015f  call    sqlite3ResolveExprNames
0x180090164  xor     r9d, r9d
0x180090167  test    eax, eax
0x180090169  jnz     loc_1800904AA
0x18009016f  mov     cl, [rsp+71h]
0x180090173  movsx   eax, word ptr [r14+36h]
0x180090178  mov     r11d, r9d
0x18009017b  test    eax, eax
0x18009017d  jle     short loc_1800901D1
0x18009017f  mov     r13, [r14+8]
0x180090183  mov     eax, r11d
0x180090186  lea     r12, [rax+rax*2]
0x18009018a  cmp     [r13+r12*8+0Eh], cl
0x18009018f  jnz     short loc_1800901B9
0x180090191  mov     rax, [r13+r12*8+0]
0x180090196  mov     rcx, [rbp+0D0h+arg_10]
0x18009019d  mov     [rbp+0D0h+var_88], rax
0x1800901a1  mov     rdx, [rbx+rcx+10h]
0x1800901a6  mov     rcx, rax
0x1800901a9  call    sqlite3StrICmp
0x1800901ae  xor     r9d, r9d
0x1800901b1  test    eax, eax
0x1800901b3  jz      short loc_18009022A
0x1800901b5  mov     cl, [rsp+71h]
0x1800901b9  movsx   eax, word ptr [r14+36h]
0x1800901be  inc     r11d
0x1800901c1  cmp     r11d, eax
0x1800901c4  jl      short loc_180090183
0x1800901c6  mov     r12, [rbp+0D0h+var_D0]
0x1800901ca  mov     r13, [rbp+0D0h+arg_10]
0x1800901d1  movsx   eax, word ptr [r14+36h]
0x1800901d6  mov     r8b, [rsp+1D0h+var_160]
0x1800901db  mov     edx, [rbp+0D0h+var_108]
0x1800901de  mov     [rbp+0D0h+var_108], edx
0x1800901e1  mov     [rbp+0D0h+var_D0], r12
0x1800901e5  mov     [rsp+1D0h+var_160], r8b
0x1800901ea  cmp     r11d, eax
0x1800901ed  jl      loc_180090287
0x1800901f3  xor     r12d, r12d
0x1800901f6  cmp     [rbp+0D0h+var_120], r12
0x1800901fa  jnz     loc_18009050F
0x180090200  mov     rcx, [rbx+r13+10h]
0x180090205  call    sqlite3IsRowid
0x18009020a  test    eax, eax
0x18009020c  jz      loc_18009050F
0x180090212  mov     r12, [rbx+r13+8]
0x180090217  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009021b  mov     [rbp+0D0h+var_D0], r12
0x18009021f  mov     [rsp+1D0h+var_160], 1
0x180090224  mov     [rbp+0D0h+var_108], r15d
0x180090228  jmp     short loc_18009028F
0x18009022a  movsx   eax, word ptr [r14+34h]
0x18009022f  cmp     r11d, eax
0x180090232  jnz     short loc_18009024B
0x180090234  mov     r13, [rbp+0D0h+arg_10]
0x18009023b  mov     [rsp+1D0h+var_160], 1
0x180090240  mov     [rbp+0D0h+var_108], r15d
0x180090244  mov     r12, [rbx+r13+8]
0x180090249  jmp     short loc_180090277
0x18009024b  cmp     [rbp+0D0h+var_120], r9
0x18009024f  jz      short loc_180090260
0x180090251  test    byte ptr [r13+r12*8+12h], 1
0x180090257  jz      short loc_180090260
0x180090259  mov     byte ptr [rsp+78h], 1
0x18009025e  jmp     short loc_18009026C
0x180090260  test    byte ptr [r13+r12*8+12h], 60h
0x180090266  jnz     loc_180090497
0x18009026c  mov     r13, [rbp+0D0h+arg_10]
0x180090273  mov     r12, [rbp+0D0h+var_D0]
0x180090277  mov     rcx, [rbp+0D0h+var_110]
0x18009027b  mov     eax, r11d
0x18009027e  mov     [rcx+rax*4], r15d
  ... truncated ...
```
