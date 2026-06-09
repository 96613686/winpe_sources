# sqlite3CreateIndex

- ea: `0x180107340`
- end: `0x18010853f`
- name: `sqlite3CreateIndex`
- size: `4607`
- prototype: ``
- caller_count: `3`
- callee_count: `43`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800c8ad0`
- `0x1800fb3c0`
- `0x180174050`

## callees

- `0x1800cb160`
- `0x1800cf1f0`
- `0x1800dac00`
- `0x1800f1b50`
- `0x1800fba00`
- `0x1800fdf90`
- `0x1800ff2c0`
- `0x180102ee0`
- `0x180102f70`
- `0x180106980`
- `0x180107340`
- `0x180108840`
- `0x1801089d0`
- `0x180108f60`
- `0x18010b290`
- `0x18010fd20`
- `0x180110ea0`
- `0x1801127c0`
- `0x1801128f0`
- `0x180114d60`
- `0x180115450`
- `0x180119dd0`
- `0x18011d720`
- `0x18011d960`
- `0x18011ddf0`
- `0x18011ec20`
- `0x18011ef50`
- `0x18011f340`
- `0x180128f40`
- `0x1801291d0`
- `0x18012a4e0`
- `0x180130eb0`
- `0x1801314e0`
- `0x1801341d0`
- `0x1801379a0`
- `0x180137a80`
- `0x180137af0`
- `0x180137d70`
- `0x180138140`
- `0x180147d80`
- `0x1801f7110`
- `0x1802421a0`
- `0x180242d80`

## string_xrefs

- `0x180107a11`: `sqlite_temp_master`
- `0x18010757d`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x1801078f7`: `there is already a table named %s`
- `0x18010793d`: `index %s already exists`
- `0x18010839f`: `CREATE%s INDEX %.*s`

## pseudocode

```c
__int64 __fastcall sqlite3CreateIndex(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10,
        unsigned __int8 a11)
{
  int *v12; // rsi
  __int64 v14; // r12
  __int64 *v15; // r14
  int v16; // r15d
  __int64 i; // r13
  __int64 v18; // r8
  const char *v19; // r9
  int v20; // edx
  __int64 v21; // rcx
  _BYTE *v22; // rax
  __int64 v23; // r11
  int v24; // esi
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 TableItem; // rax
  const char **v33; // rdi
  const char **v34; // r14
  char *v35; // rdi
  char v36; // cl
  const char *v37; // r8
  __int64 v38; // rdx
  __int64 result; // rax
  int v40; // edx
  __int64 *v41; // r12
  __int64 v42; // rcx
  __int64 v43; // rsi
  const char *v44; // rcx
  const char **v45; // rax
  char v46; // al
  const char *v47; // rdx
  _QWORD *v48; // rcx
  const char *v49; // rsi
  __int64 v50; // rdi
  char *v51; // rax
  char *v52; // rbx
  const char *v53; // rdx
  char *v54; // rsi
  __int64 v55; // rax
  char v56; // dl
  int v57; // r9d
  char *v58; // rcx
  __int64 k; // r8
  char v60; // al
  __int64 v61; // rsi
  __int64 *v62; // rcx
  signed int v63; // edx
  int v64; // eax
  const char *v65; // rax
  int j; // r9d
  char *v67; // rax
  __int64 v68; // rbx
  signed int v69; // esi
  const char *v70; // r8
  int v71; // edx
  __int64 v72; // rcx
  const char *v73; // rax
  const void *v74; // r14
  unsigned int v75; // edi
  __int64 v76; // rax
  __int64 v77; // rbx
  int *appended; // rax
  __int64 v79; // rax
  char v80; // dl
  __int64 v81; // rdi
  int *v82; // rbx
  const char *v83; // rcx
  size_t v84; // rax
  size_t v85; // rbx
  __int64 v86; // rdx
  __int64 v87; // rsi
  void **v88; // rax
  void **v89; // r15
  char *v90; // rcx
  int v91; // eax
  const void **v92; // rdi
  __int64 v93; // rdx
  bool v94; // cf
  int v95; // eax
  unsigned int v96; // ecx
  int v97; // eax
  __int64 v98; // rcx
  int *v99; // rax
  __int16 v100; // cx
  unsigned __int8 v101; // bl
  _DWORD *v102; // rsi
  const char *v103; // rdx
  int v104; // r12d
  __int64 v105; // r14
  _BYTE *v106; // rax
  char v107; // cl
  _BYTE *v108; // rcx
  __int64 *v109; // r8
  _BYTE *v110; // rax
  __int64 v111; // rdx
  _BYTE *v112; // rax
  const void *v113; // rdi
  int v114; // eax
  const void *v115; // rdx
  const char *v116; // rdi
  size_t v117; // rbx
  char *v118; // rax
  __int64 v119; // rdx
  _BYTE *m; // rax
  char v121; // cl
  int v122; // ebx
  __int64 v123; // rdi
  __int16 v124; // r14
  __int64 *v125; // r13
  __int64 v126; // rsi
  __int16 *v127; // rdi
  int v128; // r9d
  int v129; // edx
  int v130; // r10d
  int v131; // ecx
  __int64 v132; // rdi
  int v133; // esi
  int v134; // ebx
  _WORD *v135; // r10
  __int64 v136; // r11
  __int64 v137; // r14
  unsigned __int8 *v138; // rax
  __int64 v139; // r9
  __int64 v140; // rcx
  char v141; // cl
  char v142; // al
  _QWORD *v143; // rax
  int v144; // edx
  __int64 v145; // rcx
  __int64 v146; // rbx
  unsigned int v147; // esi
  __int64 v148; // r14
  const char *v149; // r8
  int v150; // r9d
  __int64 v151; // rdi
  __int64 v152; // rcx
  __int64 v153; // rax
  __int64 n; // rax
  const void **v155; // [rsp+40h] [rbp-C0h] BYREF
  char *Str; // [rsp+48h] [rbp-B8h]
  __int64 v157; // [rsp+50h] [rbp-B0h]
  int *v158; // [rsp+58h] [rbp-A8h]
  signed int v159; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v160; // [rsp+64h] [rbp-9Ch]
  __int64 v161; // [rsp+68h] [rbp-98h]
  __int64 v162; // [rsp+70h] [rbp-90h]
  int v163; // [rsp+78h] [rbp-88h]
  __int64 *v164; // [rsp+80h] [rbp-80h]
  void *v165; // [rsp+88h] [rbp-78h] BYREF
  const void **v166; // [rsp+90h] [rbp-70h]
  _OWORD v167[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v168; // [rsp+C0h] [rbp-40h]
  __int64 v169; // [rsp+C8h] [rbp-38h]
  __int128 v170; // [rsp+D0h] [rbp-30h]
  __int128 v171; // [rsp+E0h] [rbp-20h]
  __int128 v172; // [rsp+F0h] [rbp-10h]
  __int128 v173; // [rsp+100h] [rbp+0h]
  __int128 v174; // [rsp+110h] [rbp+10h]
  __int64 *v175; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v176[4]; // [rsp+128h] [rbp+28h] BYREF
  int v177; // [rsp+148h] [rbp+48h]
  __int16 v178; // [rsp+14Ch] [rbp+4Ch]
  __int64 **v179; // [rsp+150h] [rbp+50h]
  __int64 v180; // [rsp+158h] [rbp+58h]
  bool v181; // [rsp+160h] [rbp+60h]
  __int64 v182; // [rsp+168h] [rbp+68h]
  const char *v183; // [rsp+170h] [rbp+70h]
  const void **v184; // [rsp+178h] [rbp+78h]

  v12 = a5;
  v14 = *a1;
  v15 = a1;
  v163 = a6;
  v16 = 0;
  i = 0;
  v161 = a8;
  v162 = a4;
  v164 = a1;
  v158 = a5;
  v157 = v14;
  v166 = 0;
  v155 = 0;
  v165 = 0;
  if ( *((_DWORD *)a1 + 12) || *((_BYTE *)a1 + 300) == 1 && a11 != 2 )
  {
    v35 = 0;
    v38 = a8;
    goto LABEL_28;
  }
  if ( (unsigned int)sqlite3ReadSchema(a1) )
    goto LABEL_26;
  v19 = 0;
  if ( a5 )
  {
    v18 = *a5;
    v20 = 0;
    if ( v18 > 0 )
    {
      v21 = 0;
      v22 = a5 + 7;
      while ( (*v22 & 0x20) == 0 )
      {
        ++v20;
        ++v21;
        v22 += 32;
        if ( v21 >= v18 )
          goto LABEL_10;
      }
      v36 = a5[8 * v20 + 6];
      if ( !v36 || (v37 = "LAST", v36 == 3) )
        v37 = "FIRST";
      sqlite3ErrorMsg(v15, "unsupported use of NULLS %s", v37);
LABEL_26:
      v35 = 0;
      goto LABEL_27;
    }
  }
LABEL_10:
  v23 = v162;
  if ( v162 )
  {
    v159 = sqlite3TwoPartName(v15, a2, a3, &v155);
    v24 = v159;
    if ( v159 < 0 )
    {
      v12 = v158;
      goto LABEL_26;
    }
    _mm_lfence();
    v25 = v162;
    if ( !*(_BYTE *)(v14 + 197) )
    {
      v26 = sqlite3SrcListLookup(v15, v162);
      if ( !*(_DWORD *)(a3 + 8) )
      {
        if ( v26 )
        {
          if ( *(_QWORD *)(v26 + 96) == *(_QWORD *)(*(_QWORD *)(v14 + 32) + 56LL) )
            v24 = 1;
          v159 = v24;
        }
      }
    }
    v27 = *v15;
    v175 = v15;
    v28 = 32LL * v24;
    v29 = *(_QWORD *)(v27 + 32);
    v168 = 0;
    v169 = v25;
    memset(v167, 0, sizeof(v167));
    v182 = *(_QWORD *)(v28 + v29);
    v30 = *(_QWORD *)(v27 + 32);
    v170 = 0;
    v31 = *(_QWORD *)(v30 + v28 + 24);
    v183 = "index";
    v181 = v24 == 1;
    v180 = v31;
    v176[1] = fixExprCb;
    v176[2] = fixSelectCb;
    v176[3] = std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function;
    v177 = 0;
    v178 = 0;
    v166 = v155;
    v184 = v155;
    v179 = &v175;
    v176[0] = v15;
    v171 = 0;
    v172 = 0;
    v173 = 0;
    v174 = 0;
    sqlite3WalkSelect(v176, v167);
    TableItem = sqlite3LocateTableItem(v15, 0, v25 + 8);
    v155 = (const void **)TableItem;
    v33 = (const char **)TableItem;
    if ( !TableItem )
    {
      v12 = v158;
      v35 = 0;
      goto LABEL_27;
    }
    if ( v24 == 1 && *(_QWORD *)(*(_QWORD *)(v14 + 32) + v28 + 24) != *(_QWORD *)(TableItem + 96) )
    {
      _mm_lfence();
      sqlite3ErrorMsg(v15, "cannot create a TEMP index on non-TEMP table \"%s\"", *(const char **)TableItem);
      v34 = v33;
      v35 = 0;
      goto LABEL_63;
    }
    if ( *(char *)(TableItem + 48) < 0 )
    {
      _mm_lfence();
      for ( i = *(_QWORD *)(TableItem + 16); i; i = *(_QWORD *)(i + 40) )
      {
        if ( (*(_DWORD *)(i + 100) & 3) == 2 )
          break;
      }
    }
    v23 = v162;
  }
  else
  {
    v33 = (const char **)v15[43];
    v155 = (const void **)v33;
    if ( !v33 )
      goto LABEL_26;
    v44 = v33[12];
    v24 = -32768;
    v159 = -32768;
    if ( v44 )
    {
      v24 = 0;
      v45 = (const char **)(*(_QWORD *)(v14 + 32) + 24LL);
      v159 = 0;
      if ( *v45 != v44 )
      {
        do
        {
          ++v24;
          v45 += 4;
        }
        while ( *v45 != v44 );
        v159 = v24;
      }
    }
  }
  v40 = 7;
  v41 = (__int64 *)(32LL * v24 + *(_QWORD *)(v14 + 32));
  if ( !*v33 )
    goto LABEL_57;
  v18 = (__int64)*v33;
  v19 = "sqlite_";
  while ( 1 )
  {
    v42 = *(unsigned __int8 *)v18;
    --v40;
    if ( !(_BYTE)v42 || *((_BYTE *)qword_18026E880 + v42) != *((_BYTE *)qword_18026E880 + *(unsigned __int8 *)v19) )
      break;
    ++v18;
    ++v19;
    if ( v40 <= 0 )
    {
      --v40;
      break;
    }
  }
  if ( v40 < 0
    || *((unsigned __int8 *)qword_18026E880 + *(unsigned __int8 *)v18) == *((unsigned __int8 *)qword_18026E880
                                                                          + *(unsigned __int8 *)v19) )
  {
    v43 = v157;
    if ( !*(_BYTE *)(v157 + 197) && v23 )
    {
      sqlite3ErrorMsg(v15, "table %s may not be indexed", *v33);
      v14 = v43;
      v35 = 0;
LABEL_62:
      v34 = (const char **)v155;
      goto LABEL_63;
    }
  }
  else
  {
LABEL_57:
    v43 = v157;
  }
  v46 = *((_BYTE *)v33 + 63);
  if ( v46 == 2 )
  {
    sqlite3ErrorMsg(v15, "views may not be indexed", v18, v19);
LABEL_60:
    v35 = 0;
LABEL_61:
    v14 = v157;
    goto LABEL_62;
  }
  if ( v46 == 1 )
  {
    sqlite3ErrorMsg(v15, "virtual tables may not be indexed", v18, v19);
    goto LABEL_60;
  }
  if ( !v166 )
  {
    v65 = v33[2];
    for ( j = 1; v65; ++j )
      v65 = (const char *)*((_QWORD *)v65 + 5);
    v67 = (char *)sqlite3MPrintf(v43, "sqlite_autoindex_%s_%d", *v33, j);
    Str = v67;
    if ( !v67 )
    {
      v35 = 0;
      goto LABEL_61;
    }
    if ( *((_BYTE *)v15 + 300) )
      ++v67[7];
LABEL_103:
    if ( *((_BYTE *)v15 + 300) < 2u )
    {
      v68 = *v41;
      v69 = v159;
      v70 = "sqlite_temp_master";
      if ( v159 != 1 )
        v70 = "sqlite_master";
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v15, 18, (_DWORD)v70, 0, *v41) )
        goto LABEL_284;
      v71 = 3;
      if ( v69 != 1 )
        v71 = 1;
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v15, v71, (_DWORD)Str, (unsigned int)*v33, v68) )
      {
LABEL_284:
        v35 = Str;
        goto LABEL_61;
      }
    }
    goto LABEL_110;
  }
  v49 = (const char *)*v166;
  v50 = *((unsigned int *)v166 + 2);
  if ( !*v166 )
  {
    v35 = 0;
    goto LABEL_61;
  }
  v51 = (char *)sqlite3DbMallocRawNN(v157, v50 + 1);
  Str = v51;
  v52 = v51;
  if ( v51 )
  {
    v53 = v49;
    v54 = v51;
    memmove(v51, v53, (unsigned int)v50);
    v54[v50] = 0;
    v55 = (unsigned __int8)*v54;
    if ( *((char *)&qword_18026E9A0 + v55) < 0 )
    {
      v56 = *v54;
      if ( (_BYTE)v55 == 91 )
        v56 = 93;
      v57 = 0;
      v58 = v54 + 1;
      for ( k = 0; ; ++k )
      {
        v60 = *v58;
        if ( *v58 == v56 )
        {
          if ( *++v58 != v56 )
          {
            v54[v57] = 0;
            goto LABEL_83;
          }
          v60 = v56;
        }
        ++v58;
        v54[k] = v60;
        ++v57;
      }
    }
  }
  Str = v52;
  v35 = v52;
  if ( !v52 )
    goto LABEL_61;
LABEL_83:
  v33 = (const char **)v155;
  if ( (unsigned int)sqlite3CheckObjectName(v15, v52, "index", *v155) )
  {
    v14 = v157;
    v34 = v33;
    v35 = Str;
    goto LABEL_63;
  }
  if ( *((_BYTE *)v15 + 300) < 2u )
  {
    v61 = v157;
    if ( !*(_BYTE *)(v157 + 197) && sqlite3FindTable(v157, v52, *v41) )
    {
      sqlite3ErrorMsg(v15, "there is already a table named %s", v52);
      v34 = v33;
      v14 = v61;
      v35 = Str;
      goto LABEL_63;
    }
    if ( sqlite3FindIndex(v61, v52, *v41) )
    {
      v62 = v15;
      if ( a10 )
      {
        v63 = v159;
        if ( v15[21] )
          v62 = (__int64 *)v15[21];
        v64 = *((_DWORD *)v62 + 33);
        if ( !_bittest(&v64, v159) )
        {
          *((_DWORD *)v62 + 33) = v64 | (1 << v159);
          if ( v63 == 1 )
            sqlite3OpenTempDatabase();
        }
        sqlite3ForceNotReadOnly(v15);
        v34 = v33;
        v14 = v61;
        v35 = Str;
      }
      else
      {
        sqlite3ErrorMsg(v15, "index %s already exists", v52);
        v34 = v33;
        v14 = v61;
        v35 = Str;
      }
      goto LABEL_63;
    }
    goto LABEL_103;
  }
LABEL_110:
  v12 = v158;
  if ( !v158 )
  {
    v72 = 3LL * *((__int16 *)v33 + 27);
    v73 = v33[1];
    *(_WORD *)&v73[8 * v72 - 6] |= 8u;
    v74 = *(const void **)&v73[8 * v72 - 24];
    if ( v74 )
      v75 = strlen(*(const char **)&v73[8 * v72 - 24]) & 0x3FFFFFFF;
    else
      v75 = 0;
    v76 = sqlite3DbMallocRawNN(v157, v75 + 73LL);
    v77 = v76;
    if ( v76 )
    {
      *(_OWORD *)v76 = 0;
      *(_OWORD *)(v76 + 16) = 0;
      *(_OWORD *)(v76 + 32) = 0;
      *(_OWORD *)(v76 + 48) = 0;
      *(_QWORD *)(v76 + 64) = 0;
      *(_BYTE *)v76 = 59;
      *(_WORD *)(v76 + 50) = -1;
      *(_QWORD *)(v76 + 8) = v76 + 72;
      if ( v75 )
        memmove((void *)(v76 + 72), v74, v75);
      *(_BYTE *)(v75 + *(_QWORD *)(v77 + 8)) = 0;
      *(_DWORD *)(v77 + 40) = 1;
    }
    v15 = v164;
    appended = (int *)sqlite3ExprListAppendNew(*v164, v77);
    v158 = appended;
    v12 = appended;
    if ( appended )
    {
      v79 = *appended;
      v80 = 0;
      if ( a9 != -1 )
        v80 = a9;
      LOBYTE(v12[8 * v79 - 2]) = v80;
      goto LABEL_125;
    }
LABEL_283:
    v34 = (const char **)v155;
    v14 = v157;
    v35 = Str;
    goto LABEL_64;
  }
  if ( *v158 > *(_DWORD *)(*v15 + 144) )
    sqlite3ErrorMsg(v15, "too many columns in %s", "index");
  if ( *((_DWORD *)v15 + 12) )
    goto LABEL_283;
LABEL_125:
  v81 = *v12;
  if ( v81 > 0 )
  {
    v82 = v12 + 2;
    do
    {
      if ( **(_BYTE **)v82 == 113 )
      {
        v83 = *(const char **)(*(_QWORD *)v82 + 8LL);
        if ( v83 )
          v84 = strlen(v83) & 0x3FFFFFFF;
        else
          LODWORD(v84) = 0;
        v16 += v84 + 1;
      }
      v82 += 8;
      --v81;
    }
    while ( v81 );
  }
  v35 = Str;
  if ( Str )
    v85 = strlen(Str) & 0x3FFFFFFF;
  else
    LODWORD(v85) = 0;
  if ( i )
    v86 = *(unsigned __int16 *)(i + 94);
  else
    v86 = 1;
  LOWORD(v86) = *(_WORD *)v12 + v86;
  v87 = v157;
  v88 = (void **)sqlite3AllocateIndexObject(v157, v86, (unsigned int)(v85 + v16 + 1), &v165);
  v89 = v88;
  if ( *(_BYTE *)(v87 + 103) )
  {
    v34 = (const char **)v155;
    v14 = v87;
    goto LABEL_192;
  }
  v90 = (char *)v165;
  *v88 = v165;
  v165 = &v90[(unsigned int)(v85 + 1)];
  memmove(v90, v35, (unsigned int)(v85 + 1));
  v91 = v163;
  v92 = v155;
  v93 = v161;
  *((_BYTE *)v89 + 98) = v163;
  v94 = v91 != 0;
  v95 = *((_DWORD *)v89 + 25);
  v89[3] = v92;
  v96 = v95 & 0xFFFFFFF7 | (v94 ? 8 : 0);
  v97 = v96 ^ ((unsigned __int8)v96 ^ a11) & 3;
  v98 = v159;
  *((_DWORD *)v89 + 25) = v97;
  v99 = v158;
  v89[6] = *(void **)(32 * v98 + *(_QWORD *)(v87 + 32) + 24);
  v100 = *(_WORD *)v99;
  *((_WORD *)v89 + 47) = *(_WORD *)v99;
  if ( v93 )
  {
    sqlite3ResolveSelfReference((_DWORD)v15, (_DWORD)v92, 2, v93, 0);
    v100 = *((_WORD *)v89 + 47);
    v89[9] = (void *)v161;
    v161 = 0;
  }
  v94 = *((_BYTE *)v15 + 300) < 2u;
  v101 = *(_BYTE *)(v41[3] + 112);
  v160 = v101;
  v102 = v158 + 2;
  if ( !v94 )
  {
    v89[10] = v158;
    v158 = 0;
  }
  v103 = "BINARY";
  v104 = 0;
  if ( v100 )
  {
    v105 = 0;
    while ( 1 )
    {
      v106 = *(_BYTE **)v102;
      v107 = **(_BYTE **)v102;
      if ( v107 == 117 )
      {
        *v106 = 59;
      }
      else if ( v107 == 113 )
      {
        v108 = (_BYTE *)*((_QWORD *)v106 + 2);
        if ( *v108 == 117 )
          *v108 = 59;
      }
      sqlite3ResolveSelfReference((_DWORD)v164, (_DWORD)v92, 32, *(_QWORD *)v102, 0);
      v109 = v164;
      if ( *((_DWORD *)v164 + 12) )
        goto LABEL_189;
      v110 = *(_BYTE **)v102;
      if ( *(_QWORD *)v102 )
      {
        do
        {
          if ( (*((_DWORD *)v110 + 1) & 0x2000) == 0 )
            break;
          v110 = (_BYTE *)*((_QWORD *)v110 + 2);
        }
        while ( v110 );
      }
      if ( *v110 == 0xA7 )
      {
        v111 = *((__int16 *)v110 + 24);
        if ( (int)v111 >= 0 )
        {
          if ( (*((_BYTE *)v92[1] + 24 * v111 + 8) & 0xF) == 0 )
            *((_DWORD *)v89 + 25) &= ~8u;
          if ( (*((_BYTE *)v92[1] + 24 * v111 + 18) & 0x20) != 0 )
            *((_DWORD *)v89 + 25) |= 0x1800u;
        }
        else
        {
          LODWORD(v111) = *((__int16 *)v92 + 26);
        }
        *((_WORD *)v89[1] + v105) = v111;
      }
      else
      {
        if ( v92 == (const void **)v164[43] )
        {
          sqlite3ErrorMsg(v164, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
LABEL_189:
          v14 = v157;
LABEL_190:
          v34 = (const char **)v155;
LABEL_191:
          v35 = Str;
          goto LABEL_192;
        }
        if ( !v89[10] )
        {
          v89[10] = v158;
          v158 = 0;
        }
        LODWORD(v111) = -2;
        *((_WORD *)v89[1] + v105) = -2;
        *((_DWORD *)v89 + 25) &= ~8u;
        *((_DWORD *)v89 + 25) |= 0x1000u;
      }
      v112 = *(_BYTE **)v102;
      if ( **(_BYTE **)v102 == 113 )
      {
        v113 = (const void *)*((_QWORD *)v112 + 1);
        if ( v113 )
          v114 = strlen(*((const char **)v112 + 1)) & 0x3FFFFFFF;
        else
          v114 = 0;
        v115 = v113;
        v116 = (const char *)v165;
        v117 = (unsigned int)(v114 + 1);
        memmove(v165, v115, v117);
        v109 = v164;
        v118 = (char *)&v116[v117];
        v101 = v160;
        v165 = v118;
      }
      else
      {
        if ( (int)v111 < 0 )
          goto LABEL_181;
        v119 = (__int64)v92[1] + 24 * (int)v111;
        if ( (*(_WORD *)(v119 + 18) & 0x200) != 0 )
        {
          for ( m = *(_BYTE **)v119; *m; ++m )
            ;
          if ( (*(_BYTE *)(v119 + 18) & 4) != 0 )
          {
            do
              ++m;
            while ( *m );
          }
          v116 = m + 1;
        }
        else
        {
          v116 = 0;
        }
      }
      if ( !v116 )
LABEL_181:
        v116 = "BINARY";
      if ( !*(_BYTE *)(v157 + 197) && !sqlite3LocateCollSeq(v109, v116) )
        goto LABEL_189;
      *((_QWORD *)v89[8] + v105) = v116;
      v121 = *((_BYTE *)v102 + 16);
      if ( v101 < 4u )
        v121 = 0;
      ++v104;
      v102 += 8;
      *((_BYTE *)v89[7] + v105++) = v121;
      if ( v104 >= *((unsigned __int16 *)v89 + 47) )
      {
        v103 = "BINARY";
        break;
      }
      v92 = v155;
    }
  }
  if ( i )
  {
    v122 = 0;
    if ( *(_WORD *)(i + 94) )
    {
      v123 = v104;
      do
      {
        v124 = *(_WORD *)(*(_QWORD *)(i + 8) + 2LL * v122);
        if ( (unsigned int)isDupColumn(v89, *((unsigned __int16 *)v89 + 47), i, (unsigned int)v122) )
        {
          --*((_WORD *)v89 + 48);
        }
        else
        {
          *((_WORD *)v89[1] + v123) = v124;
          *((_QWORD *)v89[8] + v123) = *(_QWORD *)(*(_QWORD *)(i + 64) + 8LL * v122);
          *((_BYTE *)v89[7] + v123++) = *(_BYTE *)(v122 + *(_QWORD *)(i + 56));
        }
        ++v122;
      }
      while ( v122 < *(unsigned __int16 *)(i + 94) );
    }
  }
  else
  {
    *((_WORD *)v89[1] + v104) = -1;
    *((_QWORD *)v89[8] + v104) = "BINARY";
  }
  sqlite3DefaultRowEst(v89, v103);
  v125 = v164;
  if ( !v164[43] )
    estimateIndexWidth(v89);
  recomputeColumnsNotIndexed(v89);
  v126 = v162;
  v127 = (__int16 *)v155;
  if ( v162 )
  {
    v128 = *((unsigned __int16 *)v89 + 48);
    if ( v128 >= *((__int16 *)v155 + 27) )
    {
      v129 = 0;
      v130 = *((_DWORD *)v89 + 25) | 0x20;
      *((_DWORD *)v89 + 25) = v130;
      if ( v127[27] > 0 )
      {
        while ( 1 )
        {
          if ( v129 != v127[26] )
          {
            v131 = 0;
            if ( !(_WORD)v128 )
              break;
            while ( (_WORD)v129 != *((_WORD *)v89[1] + v131) )
            {
              if ( ++v131 >= v128 )
                goto LABEL_213;
            }
            if ( (v131 & 0x8000u) != 0 )
              break;
          }
          if ( ++v129 >= v127[27] )
            goto LABEL_214;
        }
LABEL_213:
        *((_DWORD *)v89 + 25) = v130 & 0xFFFFFFDF;
      }
    }
  }
LABEL_214:
  if ( v127 != (__int16 *)v125[43] )
  {
LABEL_244:
    v14 = v157;
    if ( *((_BYTE *)v125 + 300) < 2u )
    {
      if ( *(_BYTE *)(v157 + 197) )
      {
        if ( v126 )
        {
          v143 = v89[3];
          v144 = *(_DWORD *)(v157 + 192);
          *((_DWORD *)v89 + 22) = v144;
          v145 = v143[2];
          if ( v145 )
          {
            while ( *(_DWORD *)(v145 + 88) != v144 || (void **)v145 == v89 )
            {
              v145 = *(_QWORD *)(v145 + 40);
              if ( !v145 )
                goto LABEL_251;
            }
            sqlite3ErrorMsg(v125, "invalid rootpage");
            *((_DWORD *)v125 + 6) = sqlite3CorruptError(126051);
            goto LABEL_190;
          }
        }
LABEL_251:
        if ( sqlite3HashInsert((char *)v89[6] + 32, *v89, v89) )
        {
          sqlite3OomFault(v14);
          goto LABEL_190;
        }
        *(_DWORD *)(v14 + 44) |= 1u;
      }
      else if ( *((char *)v127 + 48) >= 0 || v126 )
      {
        v146 = v125[2];
        v147 = *((_DWORD *)v125 + 14) + 1;
        *((_DWORD *)v125 + 14) = v147;
        if ( !v146 )
        {
          if ( !v125[21] && (*(_BYTE *)(*v125 + 96) & 8) == 0 )
            *((_BYTE *)v125 + 35) = 1;
          v146 = sqlite3VdbeCreate(v125);
          if ( !v146 )
            goto LABEL_190;
        }
        v148 = v159;
        sqlite3BeginWriteOperation(v125, 1, (unsigned int)v159);
        *((_DWORD *)v89 + 22) = sqlite3VdbeAddOp0(v146, 187);
        sqlite3VdbeAddOp3(v146, 147, v148, v147, 2);
        if ( a7 )
        {
          v149 = " UNIQUE";
          v150 = *((_DWORD *)v125 + 70) + *((_DWORD *)v125 + 72) - *(_DWORD *)v166 - 1;
          if ( *((_BYTE *)*v166 + v150) != 59 )
            v150 = *((_DWORD *)v125 + 70) + *((_DWORD *)v125 + 72) - *(_DWORD *)v166;
          if ( !v163 )
            v149 = (const char *)&byte_1802990D8;
          v151 = sqlite3MPrintf(v14, "CREATE%s INDEX %.*s", v149, v150, (const char *)*v166);
        }
        else
        {
          v151 = 0;
        }
        v152 = v148;
        v34 = (const char **)v155;
        sqlite3NestedParse(
          v125,
          "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
          *(_QWORD *)(32 * v152 + *(_QWORD *)(v14 + 32)),
          *v89,
          *v155,
          v147,
          v151);
        if ( v151 )
          sqlite3DbFreeNN(v14);
        if ( v162 )
        {
          sqlite3RefillIndex(v125, v89, v147);
          sqlite3ChangeCookie(v125, (unsigned int)v159);
          v153 = sqlite3MPrintf(v14, "name='%q' AND type='index'", *v89);
          sqlite3VdbeAddParseSchemaOp(v146, (unsigned int)v159, v153, 0);
          sqlite3VdbeAddOp2(v146, 166, 0, 1);
        }
        if ( *(_BYTE *)(*(_QWORD *)v146 + 103LL) )
          dword_1803DCAC8 = *(_DWORD *)(v146 + 144);
        else
          *(_DWORD *)(*(_QWORD *)(v146 + 136) + 24LL * *((int *)v89 + 22) + 8) = *(_DWORD *)(v146 + 144);
        goto LABEL_256;
      }
    }
    v34 = (const char **)v155;
LABEL_256:
    if ( *(_BYTE *)(v14 + 197) || !v162 )
    {
      v35 = Str;
      v89[5] = (void *)v34[2];
      v34[2] = (const char *)v89;
      goto LABEL_63;
    }
    if ( *((_BYTE *)v125 + 300) >= 2u )
    {
      v35 = Str;
      v125[44] = (__int64)v89;
      goto LABEL_63;
    }
    goto LABEL_191;
  }
  v132 = *((_QWORD *)v127 + 2);
  if ( !v132 )
  {
LABEL_243:
    v127 = (__int16 *)v155;
    goto LABEL_244;
  }
  while ( 2 )
  {
    v133 = *(unsigned __int16 *)(v132 + 94);
    if ( (_WORD)v133 != *((_WORD *)v89 + 47) )
      goto LABEL_225;
    v134 = 0;
    if ( !(_WORD)v133 )
      goto LABEL_224;
    v135 = v89[1];
    v136 = 0;
    v137 = *(_QWORD *)(v132 + 8) - (_QWORD)v135;
    do
    {
      if ( *(_WORD *)((char *)v135 + v137) != *v135 )
        goto LABEL_225;
      v138 = *(unsigned __int8 **)(v136 + *(_QWORD *)(v132 + 64));
      v139 = *(_QWORD *)((char *)v89[8] + v136) - (_QWORD)v138;
      while ( 1 )
      {
        v140 = *v138;
        if ( (_BYTE)v140 == v138[v139] )
          break;
        if ( *((unsigned __int8 *)qword_18026E880 + v140) != *((unsigned __int8 *)qword_18026E880 + v138[v139]) )
          goto LABEL_225;
LABEL_231:
        ++v138;
      }
      if ( (_BYTE)v140 )
        goto LABEL_231;
      ++v134;
      ++v135;
      v136 += 8;
    }
    while ( v134 < v133 );
LABEL_224:
    if ( v134 != *(unsigned __int16 *)(v132 + 94) )
    {
LABEL_225:
      v132 = *(_QWORD *)(v132 + 40);
      if ( !v132 )
      {
        v126 = v162;
        goto LABEL_243;
      }
      continue;
    }
    break;
  }
  v141 = *((_BYTE *)v89 + 98);
  v142 = *(_BYTE *)(v132 + 98);
  if ( v142 != v141 )
  {
    if ( v142 != 11 && v141 != 11 )
      sqlite3ErrorMsg(v125, "conflicting ON CONFLICT clauses specified", 0);
    if ( *(_BYTE *)(v132 + 98) == 11 )
      *(_BYTE *)(v132 + 98) = *((_BYTE *)v89 + 98);
  }
  if ( a11 == 2 )
    *(_DWORD *)(v132 + 100) = *(_DWORD *)(v132 + 100) & 0xFFFFFFFC ^ 2;
  v34 = (const char **)v155;
  v14 = v157;
  v35 = Str;
  if ( *((_BYTE *)v125 + 300) >= 2u )
  {
    v89[5] = (void *)v125[44];
    v125[44] = (__int64)v89;
    goto LABEL_63;
  }
LABEL_192:
  if ( v89 )
    sqlite3FreeIndex(v14, v89);
LABEL_63:
  v12 = v158;
LABEL_64:
  v47 = v34[2];
  v48 = v34 + 2;
  if ( v47 )
  {
    while ( v47[98] != 5 )
    {
      v48 = v47 + 40;
      v47 = (const char *)*((_QWORD *)v47 + 5);
      if ( !v47 )
        goto LABEL_27;
    }
    for ( n = *((_QWORD *)v47 + 5); n; n = *((_QWORD *)v47 + 5) )
    {
      if ( *(_BYTE *)(n + 98) == 5 )
        break;
      *v48 = n;
      v48 = (_QWORD *)(n + 40);
      *((_QWORD *)v47 + 5) = *(_QWORD *)(n + 40);
      *(_QWORD *)(n + 40) = v47;
    }
  }
LABEL_27:
  v38 = v161;
LABEL_28:
  if ( v38 )
    sqlite3ExprDeleteNN(v14, v38);
  if ( v12 )
    exprListDeleteNN(v14);
  result = sqlite3SrcListDelete(v14, v162);
  if ( v35 )
    return sqlite3DbFreeNN(v14);
  return result;
}

```

## disassembly

```asm
0x180107340  push    rbp
0x180107342  push    rbx
0x180107343  push    rsi
0x180107344  push    rdi
0x180107345  push    r12
0x180107347  push    r13
0x180107349  push    r14
0x18010734b  push    r15
0x18010734d  lea     rbp, [rsp-98h]
0x180107355  sub     rsp, 198h
0x18010735c  mov     rax, cs:__security_cookie
0x180107363  xor     rax, rsp
0x180107366  mov     [rbp+0D0h+var_50], rax
0x18010736d  mov     eax, [rbp+0D0h+arg_28]
0x180107373  mov     rdi, rdx
0x180107376  mov     rsi, [rbp+0D0h+arg_20]
0x18010737d  xor     edx, edx
0x18010737f  mov     rbx, r8
0x180107382  mov     r12, [rcx]
0x180107385  mov     r14, rcx
0x180107388  mov     [rsp+1D0h+var_158], eax
0x18010738c  mov     r15d, edx
0x18010738f  mov     rax, [rbp+0D0h+arg_38]
0x180107396  mov     r13d, edx
0x180107399  mov     [rsp+1D0h+var_168], rax
0x18010739e  mov     [rsp+1D0h+var_160], r9
0x1801073a3  mov     [rbp+0D0h+var_150], rcx
0x1801073a7  mov     [rsp+1D0h+var_178], rsi
0x1801073ac  mov     [rsp+1D0h+var_180], r12
0x1801073b1  mov     [rbp+0D0h+var_140], rdx
0x1801073b5  mov     [rsp+1D0h+var_190], rdx
0x1801073ba  mov     [rbp+0D0h+var_148], rdx
0x1801073be  cmp     [rcx+30h], edx
0x1801073c1  jnz     loc_180108534
0x1801073c7  cmp     byte ptr [rcx+12Ch], 1
0x1801073ce  jnz     short loc_1801073DD
0x1801073d0  cmp     [rbp+0D0h+arg_50], 2
0x1801073d7  jnz     loc_180108534
0x1801073dd  call    sqlite3ReadSchema
0x1801073e2  test    eax, eax
0x1801073e4  jnz     loc_1801075C9
0x1801073ea  xor     r9d, r9d
0x1801073ed  test    rsi, rsi
0x1801073f0  jz      short loc_18010741B
0x1801073f2  movsxd  r8, dword ptr [rsi]
0x1801073f5  mov     edx, r9d
0x1801073f8  test    r8, r8
0x1801073fb  jle     short loc_18010741B
0x1801073fd  mov     ecx, r9d
0x180107400  lea     rax, [rsi+1Ch]
0x180107404  test    byte ptr [rax], 20h
0x180107407  jnz     loc_180107597
0x18010740d  inc     edx
0x18010740f  inc     rcx
0x180107412  add     rax, 20h ; ' '
0x180107416  cmp     rcx, r8
0x180107419  jl      short loc_180107404
0x18010741b  mov     r11, [rsp+1D0h+var_160]
0x180107420  test    r11, r11
0x180107423  jz      loc_180107727
0x180107429  lea     r9, [rsp+1D0h+var_190]
0x18010742e  mov     r8, rbx
0x180107431  mov     rdx, rdi
0x180107434  mov     rcx, r14
0x180107437  call    sqlite3TwoPartName
0x18010743c  mov     [rsp+1D0h+var_170], eax
0x180107440  mov     esi, eax
0x180107442  test    eax, eax
0x180107444  js      loc_18010852A
0x18010744a  lfence
0x18010744d  mov     rdi, [rsp+1D0h+var_160]
0x180107452  cmp     [r12+0C5h], r13b
0x18010745a  jnz     short loc_18010748B
0x18010745c  mov     rdx, rdi
0x18010745f  mov     rcx, r14
0x180107462  call    sqlite3SrcListLookup
0x180107467  cmp     [rbx+8], r13d
0x18010746b  jnz     short loc_18010748B
0x18010746d  test    rax, rax
0x180107470  jz      short loc_18010748B
0x180107472  mov     rcx, [r12+20h]
0x180107477  mov     rcx, [rcx+38h]
0x18010747b  cmp     [rax+60h], rcx
0x18010747f  mov     eax, 1
0x180107484  cmovz   esi, eax
0x180107487  mov     [rsp+1D0h+var_170], esi
0x18010748b  mov     rdx, [r14]
0x18010748e  xorps   xmm0, xmm0
0x180107491  mov     [rbp+0D0h+var_B0], r14
0x180107495  movsxd  rbx, esi
0x180107498  shl     rbx, 5
0x18010749c  mov     rax, [rdx+20h]
0x1801074a0  cmp     esi, 1
0x1801074a3  movups  [rbp+0D0h+var_110], xmm0
0x1801074a7  mov     qword ptr [rbp+0D0h+var_110+8], rdi
0x1801074ab  movups  [rbp+0D0h+var_130], xmm0
0x1801074af  mov     rcx, [rbx+rax]
0x1801074b3  mov     [rbp+0D0h+var_68], rcx
0x1801074b7  mov     rax, [rdx+20h]
0x1801074bb  lea     rdx, [rbp+0D0h+var_130]
0x1801074bf  movups  [rbp+0D0h+var_120], xmm0
0x1801074c3  movups  [rbp+0D0h+var_100], xmm0
0x1801074c7  mov     rcx, [rax+rbx+18h]
0x1801074cc  lea     rax, aIndex; "index"
0x1801074d3  mov     [rbp+0D0h+var_60], rax
0x1801074d7  setz    [rbp+0D0h+var_70]
0x1801074db  mov     [rbp+0D0h+var_78], rcx
0x1801074df  lea     rax, fixExprCb
0x1801074e6  mov     rcx, [rsp+1D0h+var_190]
0x1801074eb  mov     [rbp+0D0h+var_A0], rax
0x1801074ef  lea     rax, fixSelectCb
0x1801074f6  mov     [rbp+0D0h+var_98], rax
0x1801074fa  lea     rax, ?_Run_deferred_function@?$_Associated_state@V?$vector@UItemMatch@SemanticIndex@asg@@V?$allocator@UItemMatch@SemanticIndex@asg@@@std@@@std@@@std@@EEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::vector<asg::SemanticIndex::ItemMatch>>::_Run_deferred_function(std::unique_lock<std::mutex> &)
0x180107501  mov     [rbp+0D0h+var_90], rax
0x180107505  xor     eax, eax
0x180107507  mov     [rbp+0D0h+var_88], eax
0x18010750a  mov     [rbp+0D0h+var_84], ax
0x18010750e  lea     rax, [rbp+0D0h+var_B0]
0x180107512  mov     [rbp+0D0h+var_140], rcx
0x180107516  mov     [rbp+0D0h+var_58], rcx
0x18010751a  lea     rcx, [rbp+0D0h+var_A8]
0x18010751e  mov     [rbp+0D0h+var_80], rax
0x180107522  mov     [rbp+0D0h+var_A8], r14
0x180107526  movups  [rbp+0D0h+var_F0], xmm0
0x18010752a  movups  [rbp+0D0h+var_E0], xmm0
0x18010752e  movups  [rbp+0D0h+var_D0], xmm0
0x180107532  movups  [rbp+0D0h+var_C0], xmm0
0x180107536  call    sqlite3WalkSelect
0x18010753b  lea     r8, [rdi+8]
0x18010753f  xor     edx, edx
0x180107541  mov     rcx, r14
0x180107544  call    sqlite3LocateTableItem
0x180107549  mov     [rsp+1D0h+var_190], rax
0x18010754e  mov     rdi, rax
0x180107551  test    rax, rax
0x180107554  jz      loc_180107717
0x18010755a  cmp     esi, 1
0x18010755d  jnz     loc_18010762E
0x180107563  mov     rdx, [r12+20h]
0x180107568  mov     rcx, [rax+60h]
0x18010756c  cmp     [rdx+rbx+18h], rcx
0x180107571  jz      loc_18010762E
0x180107577  lfence
0x18010757a  mov     r8, [rax]
0x18010757d  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x180107584  mov     rcx, r14
0x180107587  call    sqlite3ErrorMsg
0x18010758c  mov     r14, rdi
0x18010758f  mov     rdi, r13
0x180107592  jmp     loc_1801077AD
0x180107597  movsxd  rax, edx
0x18010759a  shl     rax, 5
0x18010759e  movzx   ecx, byte ptr [rax+rsi+18h]
0x1801075a3  test    cl, cl
0x1801075a5  jz      short loc_1801075B3
0x1801075a7  lea     r8, aLast_0; "LAST"
0x1801075ae  cmp     cl, 3
0x1801075b1  jnz     short loc_1801075BA
0x1801075b3  lea     r8, aFirst; "FIRST"
0x1801075ba  lea     rdx, aUnsupportedUse; "unsupported use of NULLS %s"
0x1801075c1  mov     rcx, r14
0x1801075c4  call    sqlite3ErrorMsg
0x1801075c9  mov     rdi, r13
0x1801075cc  mov     rdx, [rsp+1D0h+var_168]
0x1801075d1  test    rdx, rdx
0x1801075d4  jz      short loc_1801075DE
0x1801075d6  mov     rcx, r12
0x1801075d9  call    sqlite3ExprDeleteNN
0x1801075de  test    rsi, rsi
0x1801075e1  jz      short loc_1801075EE
0x1801075e3  mov     rdx, rsi
0x1801075e6  mov     rcx, r12
0x1801075e9  call    exprListDeleteNN
0x1801075ee  mov     rdx, [rsp+1D0h+var_160]
0x1801075f3  mov     rcx, r12
0x1801075f6  call    sqlite3SrcListDelete
0x1801075fb  test    rdi, rdi
0x1801075fe  jz      short loc_18010760B
0x180107600  mov     rdx, rdi
0x180107603  mov     rcx, r12
0x180107606  call    sqlite3DbFreeNN
0x18010760b  mov     rcx, [rbp+0D0h+var_50]
0x180107612  xor     rcx, rsp; StackCookie
0x180107615  call    __security_check_cookie
0x18010761a  add     rsp, 198h
0x180107621  pop     r15
0x180107623  pop     r14
0x180107625  pop     r13
0x180107627  pop     r12
0x180107629  pop     rdi
0x18010762a  pop     rsi
0x18010762b  pop     rbx
0x18010762c  pop     rbp
0x18010762d  retn
0x18010762e  test    byte ptr [rax+30h], 80h
0x180107632  jz      short loc_180107653
0x180107634  lfence
0x180107637  mov     r13, [rax+10h]
0x18010763b  test    r13, r13
0x18010763e  jz      short loc_180107653
0x180107640  mov     eax, [r13+64h]
0x180107644  and     al, 3
0x180107646  cmp     al, 2
0x180107648  jz      short loc_180107653
0x18010764a  mov     r13, [r13+28h]
0x18010764e  test    r13, r13
0x180107651  jnz     short loc_180107640
0x180107653  mov     r11, [rsp+1D0h+var_160]
0x180107658  mov     r12, [r12+20h]
0x18010765d  lea     rbx, cs:180000000h
0x180107664  mov     r10, [rdi]
0x180107667  mov     edx, 7
0x18010766c  movsxd  rcx, esi
0x18010766f  shl     rcx, 5
0x180107673  add     r12, rcx
0x180107676  test    r10, r10
0x180107679  jz      loc_180107784
0x18010767f  mov     r8, r10
0x180107682  lea     r9, aSqlite_0; "sqlite_"
0x180107689  nop     dword ptr [rax+00000000h]
0x180107690  movzx   ecx, byte ptr [r8]
0x180107694  dec     edx
0x180107696  test    cl, cl
0x180107698  jz      short loc_1801076BB
0x18010769a  movzx   eax, byte ptr [r9]
0x18010769e  movzx   eax, byte ptr [rax+rbx+26E880h]
0x1801076a6  cmp     [rcx+rbx+26E880h], al
0x1801076ad  jnz     short loc_1801076BB
0x1801076af  inc     r8
0x1801076b2  inc     r9
0x1801076b5  test    edx, edx
0x1801076b7  jg      short loc_180107690
0x1801076b9  dec     edx
0x1801076bb  test    edx, edx
0x1801076bd  js      short loc_1801076DF
0x1801076bf  movzx   eax, byte ptr [r9]
0x1801076c3  movzx   ecx, byte ptr [rax+rbx+26E880h]
0x1801076cb  movzx   eax, byte ptr [r8]
0x1801076cf  movzx   eax, byte ptr [rax+rbx+26E880h]
0x1801076d7  cmp     eax, ecx
0x1801076d9  jnz     loc_180107784
0x1801076df  mov     rsi, [rsp+1D0h+var_180]
0x1801076e4  cmp     [rsi+0C5h], r15b
0x1801076eb  jnz     loc_180107789
0x1801076f1  test    r11, r11
0x1801076f4  jz      loc_180107789
0x1801076fa  mov     r8, r10
0x1801076fd  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x180107704  mov     rcx, r14
0x180107707  call    sqlite3ErrorMsg
0x18010770c  mov     r12, rsi
0x18010770f  mov     rdi, r15
0x180107712  jmp     loc_1801077A8
0x180107717  mov     rsi, [rsp+1D0h+var_178]
0x18010771c  xor     r9d, r9d
0x18010771f  mov     edi, r9d
0x180107722  jmp     loc_1801075CC
0x180107727  mov     rdi, [r14+158h]
0x18010772e  mov     [rsp+1D0h+var_190], rdi
0x180107733  test    rdi, rdi
0x180107736  jz      loc_1801075C9
0x18010773c  mov     rcx, [rdi+60h]
0x180107740  mov     esi, 0FFFF8000h
0x180107745  mov     [rsp+1D0h+var_170], esi
0x180107749  test    rcx, rcx
0x18010774c  jz      loc_180107658
0x180107752  mov     rax, [r12+20h]
0x180107757  mov     esi, r9d
0x18010775a  add     rax, 18h
0x18010775e  mov     [rsp+1D0h+var_170], r9d
0x180107763  cmp     [rax], rcx
0x180107766  jz      loc_180107658
0x18010776c  nop     dword ptr [rax+00h]
0x180107770  inc     esi
0x180107772  lea     rax, [rax+20h]
0x180107776  cmp     [rax], rcx
0x180107779  jnz     short loc_180107770
0x18010777b  mov     [rsp+1D0h+var_170], esi
0x18010777f  jmp     loc_180107658
0x180107784  mov     rsi, [rsp+1D0h+var_180]
0x180107789  movzx   eax, byte ptr [rdi+3Fh]
0x18010778d  cmp     al, 2
0x18010778f  jnz     short loc_1801077DF
0x180107791  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x180107798  mov     rcx, r14
0x18010779b  call    sqlite3ErrorMsg
0x1801077a0  mov     rdi, r15
0x1801077a3  mov     r12, [rsp+1D0h+var_180]
0x1801077a8  mov     r14, [rsp+1D0h+var_190]
0x1801077ad  mov     rsi, [rsp+1D0h+var_178]
0x1801077b2  mov     rdx, [r14+10h]
0x1801077b6  lea     rcx, [r14+10h]
0x1801077ba  test    rdx, rdx
0x1801077bd  jz      loc_1801075CC
0x1801077c3  cmp     byte ptr [rdx+62h], 5
0x1801077c7  jz      loc_1801084F2
0x1801077cd  lea     rcx, [rdx+28h]
0x1801077d1  mov     rdx, [rdx+28h]
0x1801077d5  test    rdx, rdx
0x1801077d8  jnz     short loc_1801077C3
  ... truncated ...
```
