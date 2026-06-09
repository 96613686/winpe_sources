# sqlite3CreateIndex

- ea: `0x18006fc70`
- end: `0x180070f49`
- name: `sqlite3CreateIndex`
- size: `4825`
- prototype: ``
- caller_count: `3`
- callee_count: `45`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800335c0`
- `0x180062b80`
- `0x1800d8b00`

## callees

- `0x180003060`
- `0x180003a40`
- `0x180005980`
- `0x180035f60`
- `0x18003a790`
- `0x180046640`
- `0x18004dba0`
- `0x1800596d0`
- `0x1800658d0`
- `0x1800669c0`
- `0x18006b630`
- `0x18006b6d0`
- `0x18006f290`
- `0x18006fc70`
- `0x180071400`
- `0x180071880`
- `0x1800743d0`
- `0x1800795a0`
- `0x18007a670`
- `0x18007b010`
- `0x18007c060`
- `0x18007c190`
- `0x18007e7f0`
- `0x18007eef0`
- `0x180082820`
- `0x1800838f0`
- `0x180087d40`
- `0x180088530`
- `0x180088ea0`
- `0x180089210`
- `0x1800896a0`
- `0x180093650`
- `0x180093900`
- `0x180095710`
- `0x18009bde0`
- `0x18009c660`
- `0x18009f1b0`
- `0x1800a2f60`
- `0x1800a3040`
- `0x1800a30b0`
- `0x1800a3370`
- `0x1800a3b40`
- `0x1800b3e50`
- `0x1800e4dce`
- `0x1800e4dfe`

## string_xrefs

- `0x1800702c0`: `sqlite_temp_master`
- `0x18006ff26`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x1800701c5`: `there is already a table named %s`
- `0x1800701ff`: `index %s already exists`
- `0x180070c79`: `CREATE%s INDEX %.*s`

## pseudocode

```c
__int64 __fastcall sqlite3CreateIndex(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _DWORD *a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10,
        unsigned __int8 a11)
{
  char *v11; // r14
  __int64 v12; // r13
  _DWORD *v14; // rsi
  unsigned int i; // ecx
  __int64 v18; // rdx
  _QWORD *v19; // r11
  __int64 v20; // r15
  int v21; // edi
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // ecx
  __int64 v30; // rdx
  __int64 v31; // r9
  char v32; // al
  const char *v33; // r8
  __int64 Table; // rax
  _QWORD *v35; // rsi
  const char *v36; // r10
  int v37; // edx
  const char *v38; // r8
  const char *v39; // r9
  __int64 v40; // rcx
  __int64 v41; // rdx
  char v42; // al
  __int64 *v43; // rbx
  const void *v44; // rdi
  __int64 v45; // rbx
  char *v46; // rax
  __int64 v47; // rax
  char v48; // r8
  int v49; // ecx
  int k; // r9d
  char v51; // dl
  _QWORD *v52; // rcx
  int v53; // eax
  __int64 v54; // rax
  int j; // r9d
  __int64 v56; // rax
  __int64 v57; // rbx
  const char *v58; // r8
  int v59; // edx
  int *v60; // r8
  __int64 v61; // rcx
  __int64 v62; // rax
  const void *v63; // r14
  size_t v64; // rdi
  __int64 v65; // rax
  __int64 v66; // rbx
  char v67; // dl
  int v68; // esi
  int v69; // edi
  int v70; // ebx
  __int64 v71; // rcx
  const char *v72; // rcx
  int v73; // eax
  int v74; // eax
  size_t v75; // rsi
  __int16 v76; // bx
  __int16 v77; // bx
  int v78; // r15d
  signed int v79; // r12d
  __int64 v80; // r13
  _QWORD *v81; // rax
  _QWORD *v82; // rdi
  __int64 v83; // rdx
  __int64 v84; // rdx
  char *v85; // r14
  size_t v86; // r8
  void *v87; // rcx
  char *v88; // r14
  int v89; // eax
  int *v90; // rbx
  __int64 v91; // r12
  _QWORD *v92; // r15
  bool v93; // cf
  int v94; // eax
  unsigned int v95; // ecx
  int v96; // eax
  __int64 v97; // rcx
  __int16 v98; // cx
  int *v99; // r13
  int v100; // r12d
  const char *v101; // rdx
  char *v102; // rax
  char v103; // cl
  _BYTE *v104; // rcx
  char *v105; // rax
  __int64 v106; // r15
  __int64 v107; // rdx
  const void *v108; // rsi
  int v109; // eax
  size_t v110; // rbx
  const char *v111; // rsi
  __int64 v112; // rcx
  __int64 v113; // rax
  __int16 v114; // dx
  _BYTE *n; // rax
  unsigned __int8 v116; // r14
  unsigned __int8 v117; // bl
  __int64 CollSeq; // rax
  char v119; // cl
  __int64 v120; // rsi
  int v121; // ebx
  __int64 v122; // r8
  _QWORD *v123; // r12
  int v124; // edx
  int v125; // r8d
  int v126; // ecx
  __int64 v127; // rbx
  __int16 v128; // cx
  int v129; // r10d
  _BYTE *v130; // r8
  unsigned __int8 *v131; // r9
  __int64 v132; // rax
  __int64 v133; // rcx
  __int64 v134; // rax
  int v135; // edx
  __int64 v136; // rcx
  char v137; // cl
  char v138; // al
  __int64 v139; // rsi
  unsigned int v140; // r14d
  const char *v141; // r8
  int v142; // r9d
  _QWORD *v143; // rbx
  __int64 v144; // rax
  __int64 *v145; // rax
  __int64 v146; // rcx
  _QWORD *v147; // rdx
  __int64 ii; // rax
  __int64 result; // rax
  __int64 v150; // [rsp+28h] [rbp-E0h]
  unsigned int v151; // [rsp+48h] [rbp-C0h]
  _QWORD *v152; // [rsp+50h] [rbp-B8h]
  unsigned __int8 v153; // [rsp+58h] [rbp-B0h]
  int *appended; // [rsp+60h] [rbp-A8h]
  char *Str; // [rsp+68h] [rbp-A0h]
  __int64 v156; // [rsp+70h] [rbp-98h]
  __int64 *v158; // [rsp+80h] [rbp-88h] BYREF
  _QWORD *v159; // [rsp+88h] [rbp-80h]
  int v160; // [rsp+90h] [rbp-78h]
  char *m; // [rsp+98h] [rbp-70h]
  __int64 v162; // [rsp+A0h] [rbp-68h]
  __int64 *v163; // [rsp+A8h] [rbp-60h]
  __int64 v164; // [rsp+B0h] [rbp-58h]
  __int64 v165; // [rsp+B8h] [rbp-50h]
  _QWORD *v166; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v167[4]; // [rsp+D0h] [rbp-38h] BYREF
  int v168; // [rsp+F0h] [rbp-18h]
  __int16 v169; // [rsp+F4h] [rbp-14h]
  _QWORD *v170; // [rsp+F8h] [rbp-10h]
  __int64 v171; // [rsp+100h] [rbp-8h]
  bool v172; // [rsp+108h] [rbp+0h]
  __int64 v173; // [rsp+110h] [rbp+8h]
  const char *v174; // [rsp+118h] [rbp+10h]
  __int64 *v175; // [rsp+120h] [rbp+18h]
  _OWORD v176[2]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v177; // [rsp+148h] [rbp+40h]
  _QWORD *v178; // [rsp+150h] [rbp+48h]
  __int128 v179; // [rsp+158h] [rbp+50h]
  __int128 v180; // [rsp+168h] [rbp+60h]
  __int128 v181; // [rsp+178h] [rbp+70h]
  __int128 v182; // [rsp+188h] [rbp+80h]
  __int128 v183; // [rsp+198h] [rbp+90h]

  v11 = 0;
  v12 = *a1;
  v14 = a5;
  v159 = a1;
  v160 = a6;
  appended = a5;
  v164 = a8;
  v156 = v12;
  v163 = 0;
  v158 = 0;
  if ( *((_DWORD *)a1 + 12) || *((_BYTE *)a1 + 300) == 1 && a11 != 2 || (unsigned int)sqlite3ReadSchema(a1) )
    goto LABEL_291;
  if ( a5 )
  {
    for ( i = 0; (signed int)i < *a5; ++i )
    {
      v18 = 8LL * i;
      if ( (a5[v18 + 7] & 0x20) != 0 )
      {
        v32 = a5[v18 + 6];
        if ( !v32 || (v33 = "LAST", v32 == 3) )
          v33 = "FIRST";
        sqlite3ErrorMsg(a1, "unsupported use of NULLS %s", v33);
        goto LABEL_291;
      }
    }
  }
  v19 = a4;
  v20 = 0;
  v162 = 0;
  if ( a4 )
  {
    v151 = sqlite3TwoPartName(a1, a2, a3, &v158);
    v21 = v151;
    if ( (v151 & 0x80000000) != 0 )
      goto LABEL_291;
    if ( !*(_BYTE *)(v12 + 197) )
    {
      v22 = sqlite3SrcListLookup(a1, a4);
      if ( !*(_DWORD *)(a3 + 8) )
      {
        if ( v22 )
        {
          if ( *(_QWORD *)(v22 + 96) == *(_QWORD *)(*(_QWORD *)(v12 + 32) + 56LL) )
            v21 = 1;
          v151 = v21;
        }
      }
    }
    v23 = *a1;
    v166 = a1;
    v24 = 32LL * v21;
    v25 = *(_QWORD *)(v23 + 32);
    v177 = 0;
    v178 = a4;
    memset(v176, 0, sizeof(v176));
    v173 = *(_QWORD *)(v24 + v25);
    v26 = *(_QWORD *)(v23 + 32);
    v179 = 0;
    v27 = *(_QWORD *)(v24 + v26 + 24);
    v174 = "index";
    v172 = v21 == 1;
    v171 = v27;
    v167[1] = fixExprCb;
    v167[2] = fixSelectCb;
    v167[3] = Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
    v169 = 0;
    v163 = v158;
    v175 = v158;
    v170 = &v166;
    v167[0] = a1;
    v168 = 0;
    v180 = 0;
    v181 = 0;
    v182 = 0;
    v183 = 0;
    sqlite3WalkSelect(v167, v176);
    v28 = a4[1];
    if ( v28 )
    {
      v29 = 0;
      v30 = *(_QWORD *)(*a1 + 32LL);
      if ( *(_QWORD *)(v30 + 24) != v28 )
      {
        do
          ++v29;
        while ( *(_QWORD *)(32LL * v29 + v30 + 24) != v28 );
      }
      v31 = *(_QWORD *)(32LL * v29 + v30);
    }
    else
    {
      v31 = a4[2];
    }
    Table = sqlite3LocateTable(a1, 0, a4[3], v31);
    v152 = (_QWORD *)Table;
    v35 = (_QWORD *)Table;
    if ( !Table )
      goto LABEL_290;
    if ( v21 == 1 && *(_QWORD *)(*(_QWORD *)(v12 + 32) + v24 + 24) != *(_QWORD *)(Table + 96) )
    {
      sqlite3ErrorMsg(a1, "cannot create a TEMP index on non-TEMP table \"%s\"", *(const char **)Table);
      goto LABEL_283;
    }
    if ( *(char *)(Table + 48) < 0 )
    {
      v20 = *(_QWORD *)(Table + 16);
      v162 = v20;
      if ( v20 )
      {
        do
        {
          if ( (*(_DWORD *)(v20 + 100) & 3) == 2 )
            break;
          v20 = *(_QWORD *)(v20 + 40);
        }
        while ( v20 );
        v162 = v20;
      }
    }
    v19 = a4;
  }
  else
  {
    v35 = (_QWORD *)a1[43];
    v152 = v35;
    if ( !v35 )
      goto LABEL_290;
    v40 = v35[12];
    v21 = -32768;
    v151 = -32768;
    if ( v40 )
    {
      v41 = *(_QWORD *)(v12 + 32);
      v21 = 0;
      v151 = 0;
      if ( *(_QWORD *)(v41 + 24) != v40 )
      {
        do
          ++v21;
        while ( *(_QWORD *)(32LL * v21 + v41 + 24) != v40 );
        v151 = v21;
      }
    }
  }
  v36 = (const char *)*v35;
  if ( *v35 )
  {
    v37 = 7;
    v38 = "sqlite_";
    v39 = (const char *)*v35;
    while ( 1 )
    {
      --v37;
      if ( !*v39
        || *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v39) != *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v38) )
      {
        break;
      }
      ++v39;
      ++v38;
      if ( v37 <= 0 )
      {
        --v37;
        break;
      }
    }
    if ( (v37 < 0
       || *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v39) == *((unsigned __int8 *)qword_180114680
                                                                             + *(unsigned __int8 *)v38))
      && !*(_BYTE *)(v12 + 197)
      && v19 )
    {
      sqlite3ErrorMsg(a1, "table %s may not be indexed", (const char *)*v35);
      goto LABEL_283;
    }
  }
  v42 = *((_BYTE *)v35 + 63);
  if ( v42 == 2 )
  {
    sqlite3ErrorMsg(a1, "views may not be indexed");
    goto LABEL_283;
  }
  if ( v42 == 1 )
  {
    sqlite3ErrorMsg(a1, "virtual tables may not be indexed");
    goto LABEL_283;
  }
  v43 = (__int64 *)(32LL * v21 + *(_QWORD *)(v12 + 32));
  v165 = 32LL * v21;
  v158 = v43;
  if ( !v163 )
  {
    v54 = v35[2];
    for ( j = 1; v54; ++j )
      v54 = *(_QWORD *)(v54 + 40);
    v56 = sqlite3MPrintf(v12, "sqlite_autoindex_%s_%d", v36, j);
    Str = (char *)v56;
    v11 = (char *)v56;
    if ( !v56 )
      goto LABEL_283;
    if ( *((_BYTE *)a1 + 300) )
      ++*(_BYTE *)(v56 + 7);
    goto LABEL_91;
  }
  v44 = (const void *)*v163;
  if ( !*v163 )
  {
LABEL_69:
    Str = v11;
    goto LABEL_70;
  }
  v45 = *((unsigned int *)v163 + 2);
  v46 = (char *)sqlite3DbMallocRawNN(v12, v45 + 1);
  Str = v46;
  v11 = v46;
  if ( !v46
    || (memcpy_0(v46, v44, (unsigned int)v45),
        v11[v45] = 0,
        v47 = (unsigned __int8)*v11,
        *((char *)&qword_1801147A0 + v47) >= 0) )
  {
    v43 = v158;
    goto LABEL_69;
  }
  v48 = *v11;
  if ( (_BYTE)v47 == 91 )
    v48 = 93;
  v49 = 1;
  for ( k = 0; ; ++k )
  {
    v51 = v11[v49];
    if ( v51 != v48 )
      goto LABEL_66;
    if ( v11[v49 + 1] != v48 )
      break;
    ++v49;
    v51 = v48;
LABEL_66:
    ++v49;
    v11[k] = v51;
  }
  v43 = v158;
  v11[k] = 0;
LABEL_70:
  if ( !v11 || (unsigned int)sqlite3CheckObjectName(a1, v11, "index", *v35) )
    goto LABEL_283;
  if ( *((_BYTE *)a1 + 300) < 2u )
  {
    if ( !*(_BYTE *)(v12 + 197) && sqlite3FindTable(v12, v11, *v43) )
    {
      sqlite3ErrorMsg(a1, "there is already a table named %s", v11);
      goto LABEL_283;
    }
    if ( sqlite3FindIndex(v12, v11, *v43) )
    {
      v52 = a1;
      if ( a10 )
      {
        if ( a1[21] )
          v52 = (_QWORD *)a1[21];
        v53 = *((_DWORD *)v52 + 31);
        if ( !_bittest(&v53, v151) )
        {
          *((_DWORD *)v52 + 31) = v53 | (1 << v151);
          if ( v151 == 1 )
            sqlite3OpenTempDatabase();
        }
        sqlite3ForceNotReadOnly(a1);
      }
      else
      {
        sqlite3ErrorMsg(a1, "index %s already exists", v11);
      }
      goto LABEL_283;
    }
  }
  v21 = v151;
LABEL_91:
  if ( *((_BYTE *)a1 + 300) < 2u )
  {
    v57 = *v43;
    v58 = "sqlite_temp_master";
    if ( v21 != 1 )
      v58 = "sqlite_master";
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v58, 0, v57) )
      goto LABEL_283;
    v59 = 3;
    if ( v21 != 1 )
      v59 = 1;
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, v59, (_DWORD)v11, *v35, v57) )
      goto LABEL_283;
  }
  v60 = a5;
  if ( a5 )
  {
    if ( *a5 > *(_DWORD *)(*a1 + 144LL) )
    {
      sqlite3ErrorMsg(a1, "too many columns in %s", "index");
      v60 = a5;
    }
    if ( *((_DWORD *)a1 + 12) )
      goto LABEL_283;
  }
  else
  {
    v61 = 3LL * *((__int16 *)v35 + 27);
    v62 = v35[1];
    *(_WORD *)(v62 + 8 * v61 - 6) |= 8u;
    v63 = *(const void **)(v62 + 8 * v61 - 24);
    if ( v63 )
      v64 = strlen_0(*(const char **)(v62 + 8 * v61 - 24)) & 0x3FFFFFFF;
    else
      v64 = 0;
    v65 = sqlite3DbMallocRawNN(v12, v64 + 73);
    v66 = v65;
    if ( v65 )
    {
      *(_OWORD *)v65 = 0;
      *(_OWORD *)(v65 + 16) = 0;
      *(_OWORD *)(v65 + 32) = 0;
      *(_OWORD *)(v65 + 48) = 0;
      *(_QWORD *)(v65 + 64) = 0;
      *(_BYTE *)v65 = 59;
      *(_WORD *)(v65 + 50) = -1;
      *(_QWORD *)(v65 + 8) = v65 + 72;
      if ( (_DWORD)v64 )
        memcpy_0((void *)(v65 + 72), v63, (unsigned int)v64);
      *(_BYTE *)(v64 + *(_QWORD *)(v66 + 8)) = 0;
      *(_DWORD *)(v66 + 40) = 1;
    }
    appended = (int *)sqlite3ExprListAppendNew(*a1, v66);
    v60 = appended;
    if ( !appended )
    {
      v35 = v152;
      goto LABEL_282;
    }
    v67 = 0;
    if ( a9 != -1 )
      v67 = a9;
    LOBYTE(appended[8 * *appended - 2]) = v67;
  }
  v68 = *v60;
  v69 = 0;
  v70 = 0;
  for ( m = 0; v70 < v68; ++v70 )
  {
    v71 = *(_QWORD *)&v60[8 * v70 + 2];
    if ( *(_BYTE *)v71 == 113 )
    {
      v72 = *(const char **)(v71 + 8);
      if ( v72 )
      {
        v74 = strlen_0(v72);
        v60 = appended;
        v73 = v74 & 0x3FFFFFFF;
      }
      else
      {
        v73 = 0;
      }
      v69 += v73 + 1;
    }
  }
  if ( Str )
    v75 = strlen_0(Str) & 0x3FFFFFFF;
  else
    LODWORD(v75) = 0;
  if ( v20 )
    v76 = *(_WORD *)(v20 + 94);
  else
    v76 = 1;
  v77 = *(_WORD *)appended + v76;
  v78 = v77 + 1;
  v79 = ((v77 + 2 * (v77 + v78) + 7) & 0xFFFFFFF8) + 112 + 8 * v77;
  v80 = v69 + (int)v75 + v79;
  v81 = (_QWORD *)sqlite3DbMallocRawNN(v156, v80 + 1);
  v82 = v81;
  if ( v81 )
  {
    memset_0(v81, 0, v80 + 1);
    *((_WORD *)v82 + 48) = v77;
    v83 = (__int64)&v82[v77 + 14];
    v82[8] = v82 + 14;
    v82[2] = v83;
    *((_WORD *)v82 + 47) = v77 - 1;
    v84 = v83 + 2LL * v78;
    v82[1] = v84;
    v85 = (char *)v82 + v79;
    v82[7] = v84 + 2LL * v77;
  }
  else
  {
    v85 = m;
  }
  v12 = v156;
  if ( *(_BYTE *)(v156 + 103) )
  {
LABEL_278:
    v35 = v152;
    goto LABEL_279;
  }
  v86 = (unsigned int)(v75 + 1);
  v87 = v85;
  *v82 = v85;
  v88 = &v85[v86];
  m = v88;
  memcpy_0(v87, Str, v86);
  v89 = v160;
  v35 = v152;
  v90 = appended;
  v91 = v164;
  v92 = v159;
  *((_BYTE *)v82 + 98) = v160;
  v93 = v89 != 0;
  v94 = *((_DWORD *)v82 + 25);
  v82[3] = v152;
  v95 = v94 & 0xFFFFFFF7 | (v93 ? 8 : 0);
  v96 = v95 ^ ((unsigned __int8)v95 ^ a11) & 3;
  v97 = v165;
  *((_DWORD *)v82 + 25) = v96;
  v82[6] = *(_QWORD *)(*(_QWORD *)(v156 + 32) + v97 + 24);
  v98 = *(_WORD *)appended;
  *((_WORD *)v82 + 47) = *(_WORD *)appended;
  if ( v91 )
  {
    sqlite3ResolveSelfReference((_DWORD)v92, (_DWORD)v152, 2, v91, 0);
    v98 = *((_WORD *)v82 + 47);
    v82[9] = v91;
    v164 = 0;
  }
  v99 = appended + 2;
  v153 = *(_BYTE *)(v158[3] + 112);
  if ( *((_BYTE *)v92 + 300) >= 2u )
  {
    v82[10] = appended;
    v90 = 0;
    appended = 0;
  }
  v100 = 0;
  v101 = "BINARY";
  if ( v98 )
  {
    while ( 2 )
    {
      v102 = *(char **)v99;
      v103 = **(_BYTE **)v99;
      if ( v103 == 117 )
      {
        *v102 = 59;
      }
      else if ( v103 == 113 )
      {
        v104 = (_BYTE *)*((_QWORD *)v102 + 2);
        if ( *v104 == 117 )
          *v104 = 59;
      }
      sqlite3ResolveSelfReference((_DWORD)v92, (_DWORD)v35, 32, *(_QWORD *)v99, 0);
      if ( *((_DWORD *)v92 + 12) )
        goto LABEL_183;
      v105 = *(char **)v99;
      if ( *(_QWORD *)v99 )
      {
        do
        {
          if ( (*((_DWORD *)v105 + 1) & 0x2000) == 0 )
            break;
          v105 = (char *)*((_QWORD *)v105 + 2);
        }
        while ( v105 );
      }
      if ( *v105 == -89 )
      {
        v107 = *((__int16 *)v105 + 24);
        if ( (int)v107 >= 0 )
        {
          if ( (*(_BYTE *)(v35[1] + 24 * v107 + 8) & 0xF) == 0 )
            *((_DWORD *)v82 + 25) &= ~8u;
          if ( (*(_BYTE *)(v35[1] + 24 * v107 + 18) & 0x20) != 0 )
            *((_DWORD *)v82 + 25) |= 0xC00u;
        }
        else
        {
          LODWORD(v107) = *((__int16 *)v35 + 26);
        }
        v106 = v100;
        *(_WORD *)(v82[1] + 2LL * v100) = v107;
      }
      else
      {
        if ( v35 == (_QWORD *)v92[43] )
        {
          sqlite3ErrorMsg(v92, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
LABEL_183:
          v12 = v156;
          goto LABEL_279;
        }
        if ( !v82[10] )
        {
          v82[10] = v90;
          appended = 0;
        }
        v106 = v100;
        LODWORD(v107) = -2;
        *(_WORD *)(v82[1] + 2LL * v100) = -2;
        *((_DWORD *)v82 + 25) = *((_DWORD *)v82 + 25) & 0xFFFFF7F7 | 0x800;
      }
      if ( **(_BYTE **)v99 == 113 )
      {
        v108 = *(const void **)(*(_QWORD *)v99 + 8LL);
        if ( v108 )
          v109 = strlen_0(*(const char **)(*(_QWORD *)v99 + 8LL)) & 0x3FFFFFFF;
        else
          v109 = 0;
        v110 = (unsigned int)(v109 + 1);
        memcpy_0(v88, v108, v110);
        v111 = v88;
        v88 += v110;
        m = v88;
        goto LABEL_169;
      }
      if ( (int)v107 < 0 )
        goto LABEL_170;
      v112 = 3LL * (int)v107;
      v113 = v152[1];
      v114 = *(_WORD *)(v113 + 24LL * (int)v107 + 18);
      if ( (v114 & 0x200) != 0 )
      {
        for ( n = *(_BYTE **)(v113 + 8 * v112); *n; ++n )
          ;
        if ( (v114 & 4) != 0 )
        {
          do
            ++n;
          while ( *n );
        }
        v111 = n + 1;
      }
      else
      {
        v111 = 0;
      }
LABEL_169:
      if ( !v111 )
LABEL_170:
        v111 = "BINARY";
      if ( !*(_BYTE *)(v156 + 197) )
      {
        v116 = *(_BYTE *)(*v159 + 100LL);
        v117 = *(_BYTE *)(*v159 + 197LL);
        CollSeq = sqlite3FindCollSeq(*v159, v116, v111, v117);
        if ( v117 )
        {
LABEL_176:
          if ( !CollSeq )
          {
            v12 = v156;
            goto LABEL_278;
          }
        }
        else if ( !CollSeq || !*(_QWORD *)(CollSeq + 24) )
        {
          CollSeq = sqlite3GetCollSeq(v159, v116, CollSeq, v111);
          goto LABEL_176;
        }
        v88 = m;
      }
      *(_QWORD *)(v82[8] + 8 * v106) = v111;
      v119 = *((_BYTE *)v99 + 16);
      if ( v153 < 4u )
        v119 = 0;
      ++v100;
      v99 += 8;
      *(_BYTE *)(v106 + v82[7]) = v119;
      v92 = v159;
      if ( v100 >= *((unsigned __int16 *)v82 + 47) )
      {
        v101 = "BINARY";
        break;
      }
      v35 = v152;
      v90 = appended;
      continue;
    }
  }
  v120 = v162;
  if ( v162 )
  {
    v121 = 0;
    if ( *(_WORD *)(v162 + 94) )
    {
      do
      {
        if ( (unsigned int)isDupColumn(v82, *((unsigned __int16 *)v82 + 47), v120, (unsigned int)v121) )
        {
          --*((_WORD *)v82 + 48);
        }
        else
        {
          v122 = v100++;
          v101 = (const char *)v121;
          *(_WORD *)(v82[1] + 2 * v122) = *(_WORD *)(*(_QWORD *)(v120 + 8) + 2LL * v121);
          *(_QWORD *)(v82[8] + 8 * v122) = *(_QWORD *)(*(_QWORD *)(v120 + 64) + 8LL * v121);
          *(_BYTE *)(v122 + v82[7]) = *(_BYTE *)(v121 + *(_QWORD *)(v120 + 56));
        }
        ++v121;
      }
      while ( v121 < *(unsigned __int16 *)(v120 + 94) );
    }
  }
  else
  {
    *(_WORD *)(v82[1] + 2LL * v100) = -1;
    *(_QWORD *)(v82[8] + 8LL * v100) = "BINARY";
  }
  sqlite3DefaultRowEst(v82, v101);
  if ( !v92[43] )
    estimateIndexWidth(v82);
  recomputeColumnsNotIndexed(v82);
  v123 = a4;
  v35 = v152;
  if ( a4 )
  {
    if ( *((unsigned __int16 *)v82 + 48) >= *((__int16 *)v152 + 27) )
    {
      *((_DWORD *)v82 + 25) |= 0x20u;
      if ( *((__int16 *)v152 + 27) > 0 )
      {
        v124 = 0;
        while ( 1 )
        {
          if ( v124 != *((__int16 *)v152 + 26) )
          {
            v125 = *((unsigned __int16 *)v82 + 48);
            if ( !(_WORD)v125 )
              break;
            v126 = 0;
            while ( (_WORD)v124 != *(_WORD *)(v82[1] + 2LL * v126) )
            {
              if ( ++v126 >= v125 )
                goto LABEL_204;
            }
            if ( (v126 & 0x8000u) != 0 )
              break;
          }
          if ( ++v124 >= *((unsigned __int16 *)v152 + 27) )
            goto LABEL_205;
        }
LABEL_204:
        *((_DWORD *)v82 + 25) &= ~0x20u;
      }
    }
  }
LABEL_205:
  if ( v152 != (_QWORD *)v92[43] || (v127 = v152[2]) == 0 )
  {
LABEL_217:
    v12 = v156;
    if ( *((_BYTE *)v92 + 300) >= 2u )
      goto LABEL_272;
    if ( *(_BYTE *)(v156 + 197) )
    {
      if ( a4 )
      {
        v134 = v82[3];
        v135 = *(_DWORD *)(v156 + 192);
        *((_DWORD *)v82 + 22) = v135;
        v136 = *(_QWORD *)(v134 + 16);
        if ( v136 )
        {
          while ( *(_DWORD *)(v136 + 88) != v135 || (_QWORD *)v136 == v82 )
          {
            v136 = *(_QWORD *)(v136 + 40);
            if ( !v136 )
              goto LABEL_224;
          }
          sqlite3ErrorMsg(v92, "invalid rootpage");
          *((_DWORD *)v92 + 6) = sqlite3CorruptError(123748);
          goto LABEL_279;
        }
      }
LABEL_224:
      if ( sqlite3HashInsert(v82[6] + 32LL, *v82, v82) )
      {
        sqlite3OomFault(v156);
        goto LABEL_279;
      }
      *(_DWORD *)(v156 + 44) |= 1u;
      goto LABEL_272;
    }
    if ( *((char *)v35 + 48) < 0 && !a4 )
    {
LABEL_272:
      if ( *(_BYTE *)(v156 + 197) || !v123 )
      {
        v35 = v152;
        v82[5] = v152[2];
        v152[2] = v82;
      }
      else
      {
        v35 = v152;
        if ( *((_BYTE *)v92 + 300) < 2u )
          goto LABEL_279;
        v92[44] = v82;
      }
      goto LABEL_282;
    }
    ++*((_DWORD *)v92 + 14);
    v139 = v92[2];
    v140 = *((_DWORD *)v92 + 14);
    if ( !v139 )
    {
      if ( !v92[21] && (*(_BYTE *)(*v92 + 96LL) & 8) == 0 )
        *((_BYTE *)v92 + 35) = 1;
      v139 = sqlite3VdbeCreate(v92);
      if ( !v139 )
        goto LABEL_278;
    }
    sqlite3BeginWriteOperation(v92, 1, v151);
    *((_DWORD *)v82 + 22) = sqlite3VdbeAddOp0(v139, 184);
    sqlite3VdbeAddOp3(v139, 147, v151, v140, 2);
    if ( a7 )
    {
      v141 = " UNIQUE";
      v142 = *((_DWORD *)v92 + 70) + *((_DWORD *)v92 + 72) - *(_DWORD *)v163 - 1;
      if ( *(_BYTE *)(v142 + *v163) != 59 )
        v142 = *((_DWORD *)v92 + 70) + *((_DWORD *)v92 + 72) - *(_DWORD *)v163;
      if ( !v160 )
        v141 = byte_180122168;
      v143 = (_QWORD *)sqlite3MPrintf(v156, "CREATE%s INDEX %.*s", v141, v142, (const char *)*v163);
    }
    else
    {
      v143 = 0;
    }
    v150 = *v152;
    sqlite3NestedParse(
      v92,
      "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
      *(_QWORD *)(32LL * (int)v151 + *(_QWORD *)(v156 + 32)));
    if ( v143 )
    {
      if ( (unsigned __int64)v143 < *(_QWORD *)(v156 + 496) )
      {
        if ( (unsigned __int64)v143 >= *(_QWORD *)(v156 + 480) )
        {
          *v143 = *(_QWORD *)(v156 + 472);
          *(_QWORD *)(v156 + 472) = v143;
          goto LABEL_266;
        }
        if ( (unsigned __int64)v143 >= *(_QWORD *)(v156 + 488) )
        {
          *v143 = *(_QWORD *)(v156 + 456);
          *(_QWORD *)(v156 + 456) = v143;
          goto LABEL_266;
        }
      }
      if ( *(_QWORD *)(v156 + 776) )
        measureAllocationSize(v156, v143);
      else
        sqlite3_free(v143);
    }
LABEL_266:
    if ( a4 )
    {
      sqlite3RefillIndex(v92, v82, v140);
      sqlite3ChangeCookie(v92, v151);
      v144 = sqlite3MPrintf(v156, "name='%q' AND type='index'", *v82);
      sqlite3VdbeAddParseSchemaOp(v139, v151, v144, 0, v150, v140, v143);
      sqlite3VdbeAddOp2(v139, 166, 0, 1);
    }
    if ( *(_BYTE *)(*(_QWORD *)v139 + 103LL) )
      v145 = &qword_18013FEA8;
    else
      v145 = (__int64 *)(*(_QWORD *)(v139 + 136) + 24LL * *((int *)v82 + 22));
    v123 = a4;
    *((_DWORD *)v145 + 2) = *(_DWORD *)(v139 + 144);
    goto LABEL_272;
  }
  while ( 2 )
  {
    v128 = *(_WORD *)(v127 + 94);
    if ( v128 != *((_WORD *)v82 + 47) )
      goto LABEL_215;
    v129 = 0;
    if ( !v128 )
      goto LABEL_214;
    while ( *(_WORD *)(*(_QWORD *)(v127 + 8) + 2LL * v129) == *(_WORD *)(v82[1] + 2LL * v129) )
    {
      v130 = *(_BYTE **)(*(_QWORD *)(v127 + 64) + 8LL * v129);
      v131 = *(unsigned __int8 **)(v82[8] + 8LL * v129);
      while ( 2 )
      {
        v132 = (unsigned __int8)*v130;
        v133 = *v131;
        if ( (_DWORD)v132 != (_DWORD)v133 )
        {
          if ( *((unsigned __int8 *)qword_180114680 + v132) != *((unsigned __int8 *)qword_180114680 + v133) )
            goto LABEL_214;
          goto LABEL_230;
        }
        if ( *v130 )
        {
LABEL_230:
          ++v130;
          ++v131;
          continue;
        }
        break;
      }
      if ( ++v129 < *(unsigned __int16 *)(v127 + 94) )
        continue;
      break;
    }
LABEL_214:
    if ( v129 != *(unsigned __int16 *)(v127 + 94) )
    {
LABEL_215:
      v127 = *(_QWORD *)(v127 + 40);
      if ( !v127 )
      {
        v35 = v152;
        goto LABEL_217;
      }
      continue;
    }
    break;
  }
  v137 = *((_BYTE *)v82 + 98);
  v138 = *(_BYTE *)(v127 + 98);
  if ( v138 != v137 )
  {
    if ( v138 != 11 && v137 != 11 )
      sqlite3ErrorMsg(v92, "conflicting ON CONFLICT clauses specified", 0);
    if ( *(_BYTE *)(v127 + 98) == 11 )
      *(_BYTE *)(v127 + 98) = *((_BYTE *)v82 + 98);
  }
  if ( a11 == 2 )
    *(_DWORD *)(v127 + 100) ^= (*(_DWORD *)(v127 + 100) ^ 2) & 3;
  v12 = v156;
  v35 = v152;
  if ( *((_BYTE *)v92 + 300) >= 2u )
  {
    v82[5] = v92[44];
    v92[44] = v82;
    goto LABEL_282;
  }
LABEL_279:
  if ( v82 )
    sqlite3FreeIndex(v12, v82);
LABEL_282:
  v11 = Str;
LABEL_283:
  v146 = v35[2];
  v147 = v35 + 2;
  if ( v146 )
  {
    while ( *(_BYTE *)(v146 + 98) != 5 )
    {
      v147 = (_QWORD *)(v146 + 40);
      v146 = *(_QWORD *)(v146 + 40);
      if ( !v146 )
        goto LABEL_290;
    }
    for ( ii = *(_QWORD *)(v146 + 40); ii; ii = *(_QWORD *)(v146 + 40) )
    {
      if ( *(_BYTE *)(ii + 98) == 5 )
        break;
      *v147 = ii;
      v147 = (_QWORD *)(ii + 40);
      *(_QWORD *)(v146 + 40) = *(_QWORD *)(ii + 40);
      *(_QWORD *)(ii + 40) = v146;
    }
  }
LABEL_290:
  v14 = appended;
LABEL_291:
  if ( v164 )
    sqlite3ExprDeleteNN(v12, v164);
  if ( v14 )
    exprListDeleteNN(v12, v14);
  result = sqlite3SrcListDelete(v12, a4);
  if ( v11 )
  {
    if ( !v12 )
      return sqlite3_free(v11);
    if ( (unsigned __int64)v11 < *(_QWORD *)(v12 + 496) )
    {
      if ( (unsigned __int64)v11 >= *(_QWORD *)(v12 + 480) )
      {
        result = *(_QWORD *)(v12 + 472);
        *(_QWORD *)v11 = result;
        *(_QWORD *)(v12 + 472) = v11;
        return result;
      }
      if ( (unsigned __int64)v11 >= *(_QWORD *)(v12 + 488) )
      {
        result = *(_QWORD *)(v12 + 456);
        *(_QWORD *)v11 = result;
        *(_QWORD *)(v12 + 456) = v11;
        return result;
      }
    }
    if ( *(_QWORD *)(v12 + 776) )
      return measureAllocationSize(v12, v11);
    else
      return sqlite3_free(v11);
  }
  return result;
}

```

## disassembly

```asm
0x18006fc70  mov     r11, rsp
0x18006fc73  push    rbp
0x18006fc74  push    r13
0x18006fc76  push    r14
0x18006fc78  lea     rbp, [r11-0F8h]
0x18006fc7f  sub     rsp, 1E0h
0x18006fc86  mov     rax, cs:__security_cookie
0x18006fc8d  xor     rax, rsp
0x18006fc90  mov     [rbp+0F0h+var_50], rax
0x18006fc97  mov     eax, [rbp+0F0h+arg_28]
0x18006fc9d  xor     r14d, r14d
0x18006fca0  mov     r13, [rcx]
0x18006fca3  mov     [r11-20h], rbx
0x18006fca7  mov     rbx, r8
0x18006fcaa  mov     [r11-28h], rsi
0x18006fcae  mov     rsi, [rbp+0F0h+arg_20]
0x18006fcb5  mov     [r11-30h], rdi
0x18006fcb9  mov     rdi, rdx
0x18006fcbc  mov     [r11-38h], r12
0x18006fcc0  mov     r12, rcx
0x18006fcc3  mov     [rbp+0F0h+var_170], rcx
0x18006fcc7  xor     ecx, ecx
0x18006fcc9  mov     [rbp+0F0h+var_168], eax
0x18006fccc  mov     rax, [rbp+0F0h+arg_38]
0x18006fcd3  mov     [rsp+1F0h+var_180], r9
0x18006fcd8  mov     [rsp+1F0h+var_198], rsi
0x18006fcdd  mov     [rbp+0F0h+var_148], rax
0x18006fce1  mov     [rsp+1F0h+var_188], r13
0x18006fce6  mov     [rbp+0F0h+var_150], rcx
0x18006fcea  mov     [rsp+1F0h+var_178], rcx
0x18006fcef  cmp     [r12+30h], ecx
0x18006fcf4  jnz     loc_180070E72
0x18006fcfa  cmp     byte ptr [r12+12Ch], 1
0x18006fd03  jnz     short loc_18006FD12
0x18006fd05  cmp     [rbp+0F0h+arg_50], 2
0x18006fd0c  jnz     loc_180070E72
0x18006fd12  mov     rcx, r12
0x18006fd15  call    sqlite3ReadSchema
0x18006fd1a  test    eax, eax
0x18006fd1c  jnz     loc_180070E72
0x18006fd22  test    rsi, rsi
0x18006fd25  jz      short loc_18006FD49
0x18006fd27  mov     r8d, [rsi]
0x18006fd2a  xor     ecx, ecx
0x18006fd2c  test    r8d, r8d
0x18006fd2f  jle     short loc_18006FD49
0x18006fd31  mov     edx, ecx
0x18006fd33  shl     rdx, 5
0x18006fd37  test    byte ptr [rdx+rsi+1Ch], 20h
0x18006fd3c  jnz     loc_18006FEBD
0x18006fd42  inc     ecx
0x18006fd44  cmp     ecx, r8d
0x18006fd47  jl      short loc_18006FD31
0x18006fd49  mov     r11, [rsp+1F0h+var_180]
0x18006fd4e  mov     [rsp+1F0h+var_38], r15
0x18006fd56  xor     r15d, r15d
0x18006fd59  mov     [rbp+0F0h+var_158], r15
0x18006fd5d  test    r11, r11
0x18006fd60  jz      loc_18007000A
0x18006fd66  lea     r9, [rsp+1F0h+var_178]
0x18006fd6b  mov     r8, rbx
0x18006fd6e  mov     rdx, rdi
0x18006fd71  mov     rcx, r12
0x18006fd74  call    sqlite3TwoPartName
0x18006fd79  mov     dword ptr [rsp+1F0h+var_1B0], eax
0x18006fd7d  mov     edi, eax
0x18006fd7f  test    eax, eax
0x18006fd81  js      loc_180070E6A
0x18006fd87  mov     rsi, [rsp+1F0h+var_180]
0x18006fd8c  cmp     [r13+0C5h], r14b
0x18006fd93  jnz     short loc_18006FDC3
0x18006fd95  mov     rdx, rsi
0x18006fd98  mov     rcx, r12
0x18006fd9b  call    sqlite3SrcListLookup
0x18006fda0  cmp     [rbx+8], r14d
0x18006fda4  jnz     short loc_18006FDC3
0x18006fda6  test    rax, rax
0x18006fda9  jz      short loc_18006FDC3
0x18006fdab  mov     rcx, [r13+20h]
0x18006fdaf  mov     rcx, [rcx+38h]
0x18006fdb3  cmp     [rax+60h], rcx
0x18006fdb7  mov     eax, 1
0x18006fdbc  cmovz   edi, eax
0x18006fdbf  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18006fdc3  mov     rdx, [r12]
0x18006fdc7  xorps   xmm0, xmm0
0x18006fdca  mov     [rbp+0F0h+var_130], r12
0x18006fdce  movsxd  rbx, edi
0x18006fdd1  shl     rbx, 5
0x18006fdd5  mov     rax, [rdx+20h]
0x18006fdd9  cmp     edi, 1
0x18006fddc  movups  [rbp+0F0h+var_B0], xmm0
0x18006fde0  mov     qword ptr [rbp+0F0h+var_B0+8], rsi
0x18006fde4  movups  [rbp+0F0h+var_D0], xmm0
0x18006fde8  mov     rcx, [rbx+rax]
0x18006fdec  mov     [rbp+0F0h+var_E8], rcx
0x18006fdf0  mov     rax, [rdx+20h]
0x18006fdf4  lea     rdx, [rbp+0F0h+var_D0]
0x18006fdf8  movups  [rbp+0F0h+var_C0], xmm0
0x18006fdfc  movups  [rbp+0F0h+var_A0], xmm0
0x18006fe00  mov     rcx, [rbx+rax+18h]
0x18006fe05  lea     rax, aIndex; "index"
0x18006fe0c  mov     [rbp+0F0h+var_E0], rax
0x18006fe10  setz    [rbp+0F0h+var_F0]
0x18006fe14  mov     [rbp+0F0h+var_F8], rcx
0x18006fe18  lea     rax, fixExprCb
0x18006fe1f  mov     rcx, [rsp+1F0h+var_178]
0x18006fe24  mov     [rbp+0F0h+var_120], rax
0x18006fe28  lea     rax, fixSelectCb
0x18006fe2f  mov     [rbp+0F0h+var_118], rax
0x18006fe33  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x18006fe3a  mov     [rbp+0F0h+var_110], rax
0x18006fe3e  xor     eax, eax
0x18006fe40  mov     [rbp+0F0h+var_104], ax
0x18006fe44  lea     rax, [rbp+0F0h+var_130]
0x18006fe48  mov     [rbp+0F0h+var_150], rcx
0x18006fe4c  mov     [rbp+0F0h+var_D8], rcx
0x18006fe50  lea     rcx, [rbp+0F0h+var_128]
0x18006fe54  mov     [rbp+0F0h+var_100], rax
0x18006fe58  mov     [rbp+0F0h+var_128], r12
0x18006fe5c  mov     [rbp+0F0h+var_108], r14d
0x18006fe60  movups  [rbp+0F0h+var_90], xmm0
0x18006fe64  movups  [rbp+0F0h+var_80], xmm0
0x18006fe68  movups  [rbp+0F0h+var_70], xmm0
0x18006fe6f  movups  [rbp+0F0h+var_60], xmm0
0x18006fe76  call    sqlite3WalkSelect
0x18006fe7b  mov     r8, [rsi+8]
0x18006fe7f  test    r8, r8
0x18006fe82  jz      short loc_18006FEEC
0x18006fe84  mov     rax, [r12]
0x18006fe88  xor     ecx, ecx
0x18006fe8a  mov     rdx, [rax+20h]
0x18006fe8e  cmp     [rdx+18h], r8
0x18006fe92  jz      short loc_18006FEB0
0x18006fe94  nop     dword ptr [rax+00h]
0x18006fe98  nop     dword ptr [rax+rax+00000000h]
0x18006fea0  inc     ecx
0x18006fea2  movsxd  rax, ecx
0x18006fea5  shl     rax, 5
0x18006fea9  cmp     [rax+rdx+18h], r8
0x18006feae  jnz     short loc_18006FEA0
0x18006feb0  movsxd  rax, ecx
0x18006feb3  shl     rax, 5
0x18006feb7  mov     r9, [rax+rdx]
0x18006febb  jmp     short loc_18006FEF0
0x18006febd  movzx   eax, byte ptr [rdx+rsi+18h]
0x18006fec2  test    al, al
0x18006fec4  jz      short loc_18006FED1
0x18006fec6  lea     r8, aLast_0; "LAST"
0x18006fecd  cmp     al, 3
0x18006fecf  jnz     short loc_18006FED8
0x18006fed1  lea     r8, aFirst; "FIRST"
0x18006fed8  lea     rdx, aUnsupportedUse; "unsupported use of NULLS %s"
0x18006fedf  mov     rcx, r12
0x18006fee2  call    sqlite3ErrorMsg
0x18006fee7  jmp     loc_180070E72
0x18006feec  mov     r9, [rsi+10h]
0x18006fef0  mov     r8, [rsi+18h]
0x18006fef4  xor     edx, edx
0x18006fef6  mov     rcx, r12
0x18006fef9  call    sqlite3LocateTable
0x18006fefe  mov     [rsp+1F0h+var_1A8], rax
0x18006ff03  mov     rsi, rax
0x18006ff06  test    rax, rax
0x18006ff09  jz      loc_180070E65
0x18006ff0f  cmp     edi, 1
0x18006ff12  jnz     short loc_18006FF3A
0x18006ff14  mov     rdx, [r13+20h]
0x18006ff18  mov     rcx, [rax+60h]
0x18006ff1c  cmp     [rdx+rbx+18h], rcx
0x18006ff21  jz      short loc_18006FF3A
0x18006ff23  mov     r8, [rax]
0x18006ff26  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x18006ff2d  mov     rcx, r12
0x18006ff30  call    sqlite3ErrorMsg
0x18006ff35  jmp     loc_180070E19
0x18006ff3a  test    byte ptr [rax+30h], 80h
0x18006ff3e  jz      short loc_18006FF67
0x18006ff40  mov     r15, [rax+10h]
0x18006ff44  mov     [rbp+0F0h+var_158], r15
0x18006ff48  test    r15, r15
0x18006ff4b  jz      short loc_18006FF67
0x18006ff4d  nop     dword ptr [rax]
0x18006ff50  mov     eax, [r15+64h]
0x18006ff54  and     al, 3
0x18006ff56  cmp     al, 2
0x18006ff58  jz      short loc_18006FF63
0x18006ff5a  mov     r15, [r15+28h]
0x18006ff5e  test    r15, r15
0x18006ff61  jnz     short loc_18006FF50
0x18006ff63  mov     [rbp+0F0h+var_158], r15
0x18006ff67  mov     r11, [rsp+1F0h+var_180]
0x18006ff6c  mov     r10, [rsi]
0x18006ff6f  lea     rbx, cs:180000000h
0x18006ff76  test    r10, r10
0x18006ff79  jz      loc_180070069
0x18006ff7f  mov     edx, 7
0x18006ff84  lea     r8, aSqlite_0; "sqlite_"
0x18006ff8b  mov     r9, r10
0x18006ff8e  xchg    ax, ax
0x18006ff90  movzx   eax, byte ptr [r9]
0x18006ff94  dec     edx
0x18006ff96  test    al, al
0x18006ff98  jz      short loc_18006FFBD
0x18006ff9a  mov     ecx, eax
0x18006ff9c  movzx   eax, byte ptr [r8]
0x18006ffa0  movzx   eax, byte ptr [rax+rbx+114680h]
0x18006ffa8  cmp     [rcx+rbx+114680h], al
0x18006ffaf  jnz     short loc_18006FFBD
0x18006ffb1  inc     r9
0x18006ffb4  inc     r8
0x18006ffb7  test    edx, edx
0x18006ffb9  jg      short loc_18006FF90
0x18006ffbb  dec     edx
0x18006ffbd  test    edx, edx
0x18006ffbf  js      short loc_18006FFE1
0x18006ffc1  movzx   eax, byte ptr [r8]
0x18006ffc5  movzx   ecx, byte ptr [rax+rbx+114680h]
0x18006ffcd  movzx   eax, byte ptr [r9]
0x18006ffd1  movzx   eax, byte ptr [rax+rbx+114680h]
0x18006ffd9  cmp     eax, ecx
0x18006ffdb  jnz     loc_180070069
0x18006ffe1  cmp     [r13+0C5h], r14b
0x18006ffe8  jnz     loc_180070069
0x18006ffee  test    r11, r11
0x18006fff1  jz      short loc_180070069
0x18006fff3  mov     r8, r10
0x18006fff6  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x18006fffd  mov     rcx, r12
0x180070000  call    sqlite3ErrorMsg
0x180070005  jmp     loc_180070E19
0x18007000a  mov     rsi, [r12+158h]
0x180070012  mov     [rsp+1F0h+var_1A8], rsi
0x180070017  test    rsi, rsi
0x18007001a  jz      loc_180070E65
0x180070020  mov     rcx, [rsi+60h]
0x180070024  mov     edi, 0FFFF8000h
0x180070029  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x18007002d  test    rcx, rcx
0x180070030  jz      loc_18006FF6C
0x180070036  mov     rdx, [r13+20h]
0x18007003a  xor     edi, edi
0x18007003c  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180070040  cmp     [rdx+18h], rcx
0x180070044  jz      loc_18006FF6C
0x18007004a  nop     word ptr [rax+rax+00h]
0x180070050  inc     edi
0x180070052  movsxd  rax, edi
0x180070055  shl     rax, 5
0x180070059  cmp     [rax+rdx+18h], rcx
0x18007005e  jnz     short loc_180070050
0x180070060  mov     dword ptr [rsp+1F0h+var_1B0], edi
0x180070064  jmp     loc_18006FF6C
0x180070069  movzx   eax, byte ptr [rsi+3Fh]
0x18007006d  cmp     al, 2
0x18007006f  jnz     short loc_180070085
0x180070071  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x180070078  mov     rcx, r12
0x18007007b  call    sqlite3ErrorMsg
0x180070080  jmp     loc_180070E19
0x180070085  cmp     al, 1
0x180070087  jnz     short loc_18007009D
0x180070089  lea     rdx, aVirtualTablesM; "virtual tables may not be indexed"
0x180070090  mov     rcx, r12
0x180070093  call    sqlite3ErrorMsg
0x180070098  jmp     loc_180070E19
0x18007009d  mov     rbx, [r13+20h]
0x1800700a1  mov     rax, [rbp+0F0h+var_150]
0x1800700a5  movsxd  rcx, edi
0x1800700a8  shl     rcx, 5
0x1800700ac  add     rbx, rcx
0x1800700af  mov     [rbp+0F0h+var_140], rcx
0x1800700b3  mov     [rsp+1F0h+var_178], rbx
0x1800700b8  test    rax, rax
0x1800700bb  jz      loc_180070248
0x1800700c1  mov     rdi, [rax]
0x1800700c4  test    rdi, rdi
0x1800700c7  jz      loc_18007016C
0x1800700cd  mov     ebx, [rax+8]
0x1800700d0  mov     rcx, r13
0x1800700d3  lea     rdx, [rbx+1]
0x1800700d7  call    sqlite3DbMallocRawNN
0x1800700dc  mov     [rsp+1F0h+Str], rax
0x1800700e1  mov     r14, rax
0x1800700e4  test    rax, rax
0x1800700e7  jz      short loc_180070167
0x1800700e9  mov     r8d, ebx; Size
0x1800700ec  mov     rdx, rdi; Src
0x1800700ef  mov     rcx, rax; void *
0x1800700f2  call    memcpy_0
0x1800700f7  mov     byte ptr [rbx+r14], 0
0x1800700fc  lea     rcx, cs:180000000h
0x180070103  movzx   eax, byte ptr [r14]
0x180070107  cmp     byte ptr [rax+rcx+1147A0h], 0
0x18007010f  jge     short loc_180070167
0x180070111  cmp     al, 5Bh ; '['
0x180070113  mov     ecx, 5Dh ; ']'
0x180070118  mov     r8d, eax
0x18007011b  cmovz   r8d, ecx
0x18007011f  mov     ecx, 1
  ... truncated ...
```
