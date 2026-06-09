# sqlite3CreateIndex

- ea: `0x18008d624`
- end: `0x18008e3a5`
- name: `sqlite3CreateIndex`
- size: `3457`
- prototype: ``
- caller_count: `3`
- callee_count: `48`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180060484`
- `0x180084530`
- `0x1800de91c`

## callees

- `0x180005914`
- `0x180007122`
- `0x1800633f4`
- `0x1800659f8`
- `0x18006c3a0`
- `0x18007cce4`
- `0x180084a10`
- `0x18008662c`
- `0x180086fc4`
- `0x18008ada0`
- `0x18008ade4`
- `0x18008bf3c`
- `0x18008c048`
- `0x18008ce2c`
- `0x18008d624`
- `0x18008e6ac`
- `0x18008eba8`
- `0x180090934`
- `0x180090c60`
- `0x1800938bc`
- `0x1800945ec`
- `0x180095678`
- `0x180095700`
- `0x180095f98`
- `0x18009601c`
- `0x180096e08`
- `0x18009732c`
- `0x180099e6c`
- `0x180099f3c`
- `0x18009a00c`
- `0x18009cecc`
- `0x18009d07c`
- `0x18009d46c`
- `0x18009dccc`
- `0x18009dcfc`
- `0x18009df4c`
- `0x1800a5274`
- `0x1800a5604`
- `0x1800a6350`
- `0x1800a9f20`
- `0x1800aa384`
- `0x1800aab5c`
- `0x1800ab0c8`
- `0x1800ab840`
- `0x1800ae110`
- `0x1800ae370`
- `0x1800b5de4`
- `0x1800c9390`

## string_xrefs

- `0x18008d9e5`: `sqlite_temp_master`
- `0x18008d78e`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x18008d915`: `there is already a table named %s`
- `0x18008d94f`: `index %s already exists`
- `0x18008e1f2`: `CREATE%s INDEX %.*s`

## pseudocode

```c
__int64 __fastcall sqlite3CreateIndex(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        int a6,
        __int64 a7,
        void *a8,
        int a9,
        int a10,
        unsigned __int8 a11)
{
  _QWORD *v13; // rsi
  __int64 v14; // r12
  __int64 v15; // r15
  int *v16; // r14
  __int64 v17; // r13
  int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 TableItem; // rax
  const char **v22; // r14
  const char *v23; // rcx
  __int64 v24; // rdx
  const char *v25; // r8
  const char *v26; // rdx
  char v27; // al
  __int64 v28; // rdi
  __int64 v29; // r12
  __int64 v30; // rax
  __int64 *v31; // r14
  __int64 v32; // rcx
  const char *v33; // rax
  int v34; // r9d
  __int64 v35; // rdi
  const char *v36; // r8
  int v37; // edx
  const char *v38; // rdi
  int *v39; // r10
  __int64 v40; // rbx
  __int64 v41; // rax
  __int64 v42; // rcx
  const char *v43; // rax
  void *v44; // rdx
  int v45; // eax
  __int64 v46; // rax
  __int64 v47; // rax
  char v48; // cl
  int v49; // r9d
  int v50; // ecx
  __int64 v51; // rdx
  __int64 v52; // r8
  int v53; // eax
  __int64 v54; // rax
  int v55; // ebx
  __int64 v56; // rdx
  void **v57; // rax
  void **v58; // rdi
  char *v59; // rcx
  int *v60; // rdx
  int v61; // eax
  unsigned int v62; // ecx
  __int16 v63; // cx
  bool v64; // cf
  _BYTE *v65; // rbx
  __int64 v66; // rdx
  int v67; // r12d
  const char *v68; // r8
  _BYTE *v69; // rax
  _BYTE *v70; // rcx
  __int64 i; // rax
  __int64 v72; // rcx
  _BYTE *v73; // rdx
  int v74; // eax
  __int64 v75; // rax
  const char *v76; // r12
  size_t v77; // rbx
  char *v78; // rax
  __int64 v79; // rdx
  char v80; // cl
  _BYTE *v81; // rax
  int v82; // ebx
  int v83; // r12d
  int v84; // ebx
  int v85; // r13d
  int v86; // r11d
  const char *j; // rbx
  int v88; // r12d
  unsigned int v89; // r11d
  _WORD *v90; // r13
  __int64 v91; // rcx
  int v92; // r11d
  char v93; // al
  _QWORD *v94; // rax
  int v95; // edx
  __int64 k; // rcx
  __int64 v97; // rax
  unsigned int v98; // r13d
  __int64 Vdbe; // r12
  const char *v100; // r8
  unsigned int v101; // edx
  __int64 v102; // r9
  __int64 v103; // rbx
  __int64 v104; // rax
  __int64 *v105; // rax
  __int64 result; // rax
  __int64 m; // rax
  __int64 v108; // [rsp+28h] [rbp-D9h]
  const char *Src; // [rsp+48h] [rbp-B9h]
  unsigned int v110; // [rsp+50h] [rbp-B1h]
  int *appended; // [rsp+58h] [rbp-A9h]
  void *v112; // [rsp+60h] [rbp-A1h] BYREF
  _QWORD *v113; // [rsp+68h] [rbp-99h] BYREF
  _BYTE *v114; // [rsp+70h] [rbp-91h]
  void *v115; // [rsp+78h] [rbp-89h] BYREF
  int v116; // [rsp+80h] [rbp-81h]
  int v117; // [rsp+84h] [rbp-7Dh]
  __int64 v118; // [rsp+88h] [rbp-79h]
  __int64 v119; // [rsp+90h] [rbp-71h]
  __int64 v120; // [rsp+98h] [rbp-69h]
  _BYTE v121[144]; // [rsp+A8h] [rbp-59h] BYREF
  unsigned __int8 v124; // [rsp+168h] [rbp+67h]

  v13 = a1;
  v14 = 0;
  memset_0(v121, 0, 0x60u);
  v15 = *v13;
  v118 = *v13;
  v113 = 0;
  v112 = 0;
  if ( !*((_DWORD *)v13 + 12) && (*((_BYTE *)v13 + 300) != 1 || a11 == 2) && !(unsigned int)sqlite3ReadSchema(v13) )
  {
    v16 = a5;
    appended = a5;
    v17 = 0;
    if ( (unsigned int)sqlite3HasExplicitNulls(v13, a5) )
      goto LABEL_221;
    if ( a4 )
    {
      v110 = sqlite3TwoPartName(v13, a2, a3, &v113);
      v18 = v110;
      if ( (v110 & 0x80000000) != 0 )
        goto LABEL_221;
      if ( !*(_BYTE *)(v15 + 197) )
      {
        v19 = sqlite3SrcListLookup(v13, a4);
        if ( !*(_DWORD *)(a3 + 8) )
        {
          if ( v19 )
          {
            if ( *(_QWORD *)(v19 + 96) == *(_QWORD *)(*(_QWORD *)(v15 + 32) + 56LL) )
              v18 = 1;
            v110 = v18;
          }
        }
      }
      sqlite3FixInit((unsigned int)v121, (_DWORD)v13, v18, (unsigned int)"index", (__int64)v113);
      v20 = a4;
      sqlite3FixSrcList(v121, a4);
      TableItem = sqlite3LocateTableItem(v13, 0, a4 + 8);
      v22 = (const char **)TableItem;
      if ( !TableItem )
        goto LABEL_220;
      if ( v18 == 1 && *(_QWORD *)(*(_QWORD *)(v15 + 32) + 56LL) != *(_QWORD *)(TableItem + 96) )
      {
        sqlite3ErrorMsg(v13, "cannot create a TEMP index on non-TEMP table \"%s\"", *(const char **)TableItem);
        goto LABEL_51;
      }
      if ( *(char *)(TableItem + 48) >= 0 || (v17 = *(_QWORD *)(TableItem + 16)) == 0 )
      {
LABEL_29:
        if ( !(unsigned int)sqlite3_strnicmp(*v22, "sqlite_", 7) && !*(_BYTE *)(v15 + 197) && v20 )
        {
          v25 = *v22;
          v26 = "table %s may not be indexed";
LABEL_33:
          sqlite3ErrorMsg(v13, v26, v25);
          goto LABEL_50;
        }
        v27 = *((_BYTE *)v22 + 63);
        if ( v27 == 2 )
        {
          sqlite3ErrorMsg(v13, "views may not be indexed");
          goto LABEL_50;
        }
        if ( v27 == 1 )
        {
          sqlite3ErrorMsg(v13, "virtual tables may not be indexed");
          goto LABEL_50;
        }
        v28 = *(_QWORD *)(v15 + 32);
        v120 = v18;
        v29 = 32LL * v18;
        v114 = (_BYTE *)v29;
        v119 = v28;
        if ( v113 )
        {
          v30 = sqlite3NameFromToken(v15, v113);
          Src = (const char *)v30;
          if ( v30 )
          {
            if ( (unsigned int)sqlite3CheckObjectName(v13, v30, "index", *v22) )
            {
LABEL_49:
              v14 = (__int64)Src;
              goto LABEL_50;
            }
            if ( *((_BYTE *)v13 + 300) >= 2u )
              goto LABEL_66;
            if ( !*(_BYTE *)(v15 + 197) && sqlite3FindTable(v15, Src, *(_QWORD *)(v29 + v28)) )
            {
              v14 = (__int64)Src;
              v26 = "there is already a table named %s";
              v25 = Src;
              goto LABEL_33;
            }
            if ( sqlite3FindIndex(v15, Src, *(_QWORD *)(v29 + v28)) )
            {
              if ( !a10 )
              {
                v14 = (__int64)Src;
                sqlite3ErrorMsg(v13, "index %s already exists", Src);
                goto LABEL_50;
              }
              sqlite3CodeVerifySchema(v13, (unsigned int)v18);
              sqlite3ForceNotReadOnly(v13);
              goto LABEL_49;
            }
LABEL_58:
            if ( *((_BYTE *)v13 + 300) < 2u )
            {
              v35 = *(_QWORD *)(v29 + v28);
              v36 = "sqlite_temp_master";
              if ( v18 != 1 )
                v36 = "sqlite_master";
              if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, 18, (_DWORD)v36, 0, v35) )
                goto LABEL_49;
              v37 = 3;
              v108 = v35;
              v38 = Src;
              if ( v18 != 1 )
                v37 = 1;
              if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, v37, (_DWORD)Src, (unsigned int)*v22, v108) )
              {
                v14 = (__int64)Src;
                goto LABEL_50;
              }
LABEL_67:
              v39 = a5;
              v40 = -1;
              if ( a5 )
              {
                if ( *a5 > *(_DWORD *)(*v13 + 144LL) )
                {
                  sqlite3ErrorMsg(v13, "too many columns in %s", "index");
                  v39 = a5;
                }
                if ( *((_DWORD *)v13 + 12) )
                  goto LABEL_49;
              }
              else
              {
                v41 = *((__int16 *)v22 + 27);
                v117 = 0;
                v42 = 3 * v41;
                v43 = v22[1];
                *(_WORD *)&v43[8 * v42 - 6] |= 8u;
                v44 = *(void **)&v43[8 * v42 - 24];
                v115 = v44;
                if ( v44 )
                {
                  v46 = -1;
                  do
                    ++v46;
                  while ( *((_BYTE *)v44 + v46) );
                  v45 = v46 & 0x3FFFFFFF;
                }
                else
                {
                  v45 = 0;
                }
                v116 = v45;
                v47 = sqlite3ExprAlloc(v15, 59, &v115);
                appended = (int *)sqlite3ExprListAppendNew(*v13, v47);
                v39 = appended;
                if ( !appended )
                  goto LABEL_49;
                v48 = 0;
                if ( a9 != -1 )
                  v48 = a9;
                LOBYTE(appended[8 * *appended - 2]) = v48;
              }
              v49 = 0;
              v50 = 0;
              if ( *v39 > 0 )
              {
                do
                {
                  v51 = *(_QWORD *)&v39[8 * v50 + 2];
                  if ( *(_BYTE *)v51 == 113 )
                  {
                    v52 = *(_QWORD *)(v51 + 8);
                    if ( v52 )
                    {
                      v54 = -1;
                      do
                        ++v54;
                      while ( *(_BYTE *)(v52 + v54) );
                      v53 = v54 & 0x3FFFFFFF;
                    }
                    else
                    {
                      v53 = 0;
                    }
                    v49 += v53 + 1;
                  }
                  ++v50;
                }
                while ( v50 < *v39 );
                v29 = (__int64)v114;
              }
              do
                ++v40;
              while ( v38[v40] );
              v55 = v40 & 0x3FFFFFFF;
              if ( v17 )
                v56 = *(unsigned __int16 *)(v17 + 94);
              else
                v56 = 1;
              LOWORD(v56) = *(_WORD *)v39 + v56;
              v57 = (void **)sqlite3AllocateIndexObject(v15, v56, (unsigned int)(v55 + v49 + 1), &v112);
              v58 = v57;
              if ( *(_BYTE *)(v15 + 103) )
                goto LABEL_145;
              v59 = (char *)v112;
              *v57 = v112;
              v115 = &v59[v55 + 1];
              memcpy_0(v59, Src, (unsigned int)(v55 + 1));
              v60 = appended;
              *((_BYTE *)v58 + 98) = a6;
              v61 = *((_DWORD *)v58 + 25);
              v58[3] = v22;
              v62 = v61 & 0xFFFFFFF7 | (a6 != 0 ? 8 : 0);
              *((_DWORD *)v58 + 25) = v62 ^ ((unsigned __int8)v62 ^ a11) & 3;
              v58[6] = *(void **)(v29 + *(_QWORD *)(v15 + 32) + 24);
              v63 = *(_WORD *)appended;
              *((_WORD *)v58 + 47) = *(_WORD *)appended;
              if ( a8 )
              {
                sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v22, 2, (_DWORD)a8, 0);
                v63 = *((_WORD *)v58 + 47);
                v60 = appended;
                v58[9] = a8;
                a8 = 0;
              }
              v64 = *((_BYTE *)v13 + 300) < 2u;
              v65 = v60 + 2;
              v114 = v60 + 2;
              v124 = *(_BYTE *)(*(_QWORD *)(v29 + v119 + 24) + 112LL);
              if ( v64 )
              {
                v66 = 0;
              }
              else
              {
                v58[10] = v60;
                v66 = 0;
                appended = 0;
              }
              LODWORD(v112) = 0;
              v67 = 0;
              v68 = "BINARY";
              if ( v63 )
              {
                while ( 1 )
                {
                  v69 = *(_BYTE **)v65;
                  if ( **(_BYTE **)v65 == 117 )
                  {
                    *v69 = 59;
                  }
                  else if ( *v69 == 113 )
                  {
                    v70 = (_BYTE *)*((_QWORD *)v69 + 2);
                    if ( *v70 == 117 )
                      *v70 = 59;
                  }
                  sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v22, 32, *(_QWORD *)v65, 0);
                  if ( *((_DWORD *)v13 + 12) )
                    goto LABEL_145;
                  for ( i = *(_QWORD *)v65; i && (*(_DWORD *)(i + 4) & 0x2000) != 0; i = *(_QWORD *)(i + 16) )
                    ;
                  if ( *(_BYTE *)i == 0xA7 )
                  {
                    v72 = *(__int16 *)(i + 48);
                    if ( (int)v72 >= 0 )
                    {
                      if ( (v22[1][24 * v72 + 8] & 0xF) == 0 )
                        *((_DWORD *)v58 + 25) &= ~8u;
                      if ( (v22[1][24 * v72 + 18] & 0x20) != 0 )
                        *((_DWORD *)v58 + 25) |= 0xC00u;
                    }
                    else
                    {
                      LODWORD(v72) = *((__int16 *)v22 + 26);
                    }
                    *((_WORD *)v58[1] + v67) = v72;
                  }
                  else
                  {
                    if ( v22 == (const char **)v13[43] )
                    {
                      sqlite3ErrorMsg(v13, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
                      goto LABEL_145;
                    }
                    if ( !v58[10] )
                    {
                      v58[10] = appended;
                      appended = 0;
                    }
                    LODWORD(v72) = -2;
                    *((_WORD *)v58[1] + v67) = -2;
                    *((_DWORD *)v58 + 25) &= ~8u;
                    *((_DWORD *)v58 + 25) |= 0x800u;
                  }
                  if ( **(_BYTE **)v65 == 113 )
                    break;
                  if ( (int)v72 >= 0 )
                  {
                    v76 = (const char *)sqlite3ColumnColl(&v22[1][24 * (int)v72]);
                    goto LABEL_132;
                  }
LABEL_133:
                  v76 = "BINARY";
LABEL_134:
                  if ( !*(_BYTE *)(v15 + 197) && !sqlite3LocateCollSeq(v13, v76) )
                    goto LABEL_145;
                  v79 = (int)v112;
                  *((_QWORD *)v58[8] + (int)v112) = v76;
                  v80 = v65[16];
                  if ( v124 < 4u )
                    v80 = 0;
                  v81 = v58[7];
                  v65 += 32;
                  LODWORD(v112) = (_DWORD)v112 + 1;
                  v67 = (int)v112;
                  v114 = v65;
                  v81[v79] = v80;
                  v66 = 0;
                  if ( v67 >= *((unsigned __int16 *)v58 + 47) )
                  {
                    v68 = "BINARY";
                    goto LABEL_140;
                  }
                }
                v73 = *(_BYTE **)(*(_QWORD *)v65 + 8LL);
                if ( v73 )
                {
                  v75 = -1;
                  do
                    ++v75;
                  while ( v73[v75] );
                  v74 = v75 & 0x3FFFFFFF;
                }
                else
                {
                  v74 = 0;
                }
                v76 = (const char *)v115;
                v77 = (unsigned int)(v74 + 1);
                memcpy_0(v115, v73, v77);
                v78 = (char *)&v76[v77];
                v65 = v114;
                v115 = v78;
LABEL_132:
                if ( v76 )
                  goto LABEL_134;
                goto LABEL_133;
              }
LABEL_140:
              if ( v17 )
              {
                v82 = 0;
                if ( *(_WORD *)(v17 + 94) )
                {
                  do
                  {
                    if ( (unsigned int)isDupColumn(v58, *((unsigned __int16 *)v58 + 47), v17, (unsigned int)v82) )
                    {
                      --*((_WORD *)v58 + 48);
                    }
                    else
                    {
                      v68 = (const char *)v67++;
                      v66 = v82;
                      *((_WORD *)v58[1] + (_QWORD)v68) = *(_WORD *)(*(_QWORD *)(v17 + 8) + 2LL * v82);
                      *((_QWORD *)v58[8] + (_QWORD)v68) = *(_QWORD *)(*(_QWORD *)(v17 + 64) + 8LL * v82);
                      *((_BYTE *)v58[7] + (_QWORD)v68) = *(_BYTE *)(v82 + *(_QWORD *)(v17 + 56));
                    }
                    ++v82;
                  }
                  while ( v82 < *(unsigned __int16 *)(v17 + 94) );
                  v13 = a1;
                  v15 = v118;
                }
              }
              else
              {
                *((_WORD *)v58[1] + v67) = -1;
                *((_QWORD *)v58[8] + v67) = "BINARY";
              }
              sqlite3DefaultRowEst(v58, v66, v68);
              if ( !v13[43] )
                estimateIndexWidth(v58);
              recomputeColumnsNotIndexed(v58);
              if ( a4 )
              {
                if ( *((unsigned __int16 *)v58 + 48) >= *((__int16 *)v22 + 27) )
                {
                  *((_DWORD *)v58 + 25) |= 0x20u;
                  v83 = *((__int16 *)v22 + 27);
                  if ( v83 > 0 )
                  {
                    v84 = 0;
                    v85 = *((__int16 *)v22 + 26);
                    while ( v84 == v85 || (sqlite3TableColumnToIndex(v58, (unsigned __int16)v84) & 0x8000u) == 0LL )
                    {
                      if ( ++v84 >= v83 )
                        goto LABEL_162;
                    }
                    *((_DWORD *)v58 + 25) = v86 & 0xFFFFFFDF;
                  }
                }
              }
LABEL_162:
              if ( v22 == (const char **)v13[43] )
              {
                for ( j = v22[2]; j; j = (const char *)*((_QWORD *)j + 5) )
                {
                  if ( *((_WORD *)j + 47) == *((_WORD *)v58 + 47) )
                  {
                    v88 = *((unsigned __int16 *)j + 47);
                    v89 = 0;
                    if ( *((_WORD *)j + 47) )
                    {
                      v90 = v58[1];
                      v91 = *((_QWORD *)j + 1);
                      while ( *(_WORD *)(v91 + 2LL * v89) == v90[v89]
                           && !(unsigned int)sqlite3StrICmp(
                                               *(_QWORD *)(*((_QWORD *)j + 8) + 8LL * v89),
                                               *((_QWORD *)v58[8] + v89)) )
                      {
                        v91 = *((_QWORD *)j + 1);
                        v89 = v92 + 1;
                        if ( (int)v89 >= v88 )
                          goto LABEL_171;
                      }
                    }
                    else
                    {
LABEL_171:
                      if ( v89 == v88 )
                      {
                        v93 = *((_BYTE *)v58 + 98);
                        if ( j[98] != v93 )
                        {
                          if ( j[98] == 11 )
                            goto LABEL_177;
                          if ( v93 != 11 )
                            sqlite3ErrorMsg(v13, "conflicting ON CONFLICT clauses specified", 0);
                          if ( j[98] == 11 )
LABEL_177:
                            *((_BYTE *)j + 98) = *((_BYTE *)v58 + 98);
                        }
                        if ( a11 == 2 )
                          *((_DWORD *)j + 25) ^= ((unsigned __int8)*((_DWORD *)j + 25) ^ 2) & 3;
                        if ( *((_BYTE *)v13 + 300) >= 2u )
                        {
                          v58[5] = (void *)v13[44];
                          v13[44] = v58;
                          v58 = 0;
                        }
                        goto LABEL_145;
                      }
                    }
                  }
                }
              }
              if ( *((_BYTE *)v13 + 300) < 2u )
              {
                if ( *(_BYTE *)(v15 + 197) )
                {
                  if ( a4 )
                  {
                    v94 = v58[3];
                    v95 = *(_DWORD *)(v15 + 192);
                    *((_DWORD *)v58 + 22) = v95;
                    for ( k = v94[2]; k; k = *(_QWORD *)(k + 40) )
                    {
                      if ( *(_DWORD *)(k + 88) == v95 && (void **)k != v58 )
                      {
                        sqlite3ErrorMsg(v13, "invalid rootpage");
                        *((_DWORD *)v13 + 6) = sqlite3CorruptError(123747);
                        goto LABEL_145;
                      }
                    }
                  }
                  if ( sqlite3HashInsert((char *)v58[6] + 32, *v58, v58) )
                  {
                    sqlite3OomFault(v15);
                    goto LABEL_145;
                  }
                  *(_DWORD *)(v15 + 44) |= 1u;
                }
                else
                {
                  if ( *((char *)v22 + 48) < 0 )
                  {
                    v97 = a4;
                    if ( !a4 )
                    {
LABEL_211:
                      if ( *(_BYTE *)(v15 + 197) || !v97 )
                      {
                        v58[5] = (void *)v22[2];
                        v22[2] = (const char *)v58;
                        goto LABEL_49;
                      }
                      if ( *((_BYTE *)v13 + 300) >= 2u )
                      {
                        v13[44] = v58;
                        goto LABEL_49;
                      }
LABEL_145:
                      if ( v58 )
                        sqlite3FreeIndex(v15, v58);
                      goto LABEL_49;
                    }
                  }
                  v98 = ++*((_DWORD *)v13 + 14);
                  Vdbe = sqlite3GetVdbe(v13);
                  if ( !Vdbe )
                    goto LABEL_145;
                  sqlite3BeginWriteOperation(v13, 1, v110);
                  *((_DWORD *)v58 + 22) = sqlite3VdbeAddOp3(Vdbe, 184, 0, 0, 0);
                  sqlite3VdbeAddOp3(Vdbe, 147, v110, v98, 2);
                  if ( a7 )
                  {
                    v100 = (const char *)&word_1800F2B62;
                    v101 = *((_DWORD *)v13 + 70) + *((_DWORD *)v13 + 72) - *(_DWORD *)v113;
                    v102 = v101 - 1;
                    if ( *(_BYTE *)((int)v102 + *v113) != 59 )
                      v102 = v101;
                    if ( a6 )
                      v100 = " UNIQUE";
                    v103 = sqlite3MPrintf(v15, "CREATE%s INDEX %.*s", v100, v102, *v113);
                  }
                  else
                  {
                    v103 = 0;
                  }
                  sqlite3NestedParse(
                    v13,
                    "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
                    *(_QWORD *)(32 * v120 + *(_QWORD *)(v15 + 32)),
                    *v58,
                    *v22,
                    v98,
                    v103);
                  if ( v103 )
                    sqlite3DbFreeNN(v15);
                  if ( a4 )
                  {
                    sqlite3RefillIndex(v13, v58, v98);
                    sqlite3ChangeCookie(v13, v110);
                    v104 = sqlite3MPrintf(v15, "name='%q' AND type='index'", *v58);
                    sqlite3VdbeAddParseSchemaOp(Vdbe, v110, v104, 0);
                    sqlite3VdbeAddOp3(Vdbe, 166, 0, 1, 0);
                  }
                  sqlite3VdbeJumpHere(Vdbe, *((unsigned int *)v58 + 22));
                }
              }
              v97 = a4;
              goto LABEL_211;
            }
LABEL_66:
            v38 = Src;
            goto LABEL_67;
          }
        }
        else
        {
          v33 = v22[2];
          v34 = 1;
          while ( v33 )
          {
            v33 = (const char *)*((_QWORD *)v33 + 5);
            ++v34;
          }
          v30 = sqlite3MPrintf(v15, "sqlite_autoindex_%s_%d", *v22, v34);
          Src = (const char *)v30;
          if ( v30 )
          {
            if ( *((_BYTE *)v13 + 300) )
              ++*(_BYTE *)(v30 + 7);
            goto LABEL_58;
          }
        }
        v14 = v30;
LABEL_50:
        if ( v22 )
        {
LABEL_51:
          v31 = (__int64 *)(v22 + 2);
          v32 = *v31;
          while ( v32 )
          {
            v105 = (__int64 *)(v32 + 40);
            if ( *(_BYTE *)(v32 + 98) == 5 )
            {
              for ( m = *v105; m && *(_BYTE *)(m + 98) != 5; m = *(_QWORD *)(v32 + 40) )
              {
                *v31 = m;
                v31 = (__int64 *)(m + 40);
                *(_QWORD *)(v32 + 40) = *(_QWORD *)(m + 40);
                *(_QWORD *)(m + 40) = v32;
              }
              break;
            }
            v32 = *v105;
            v31 = v105;
          }
        }
LABEL_220:
        v16 = appended;
        goto LABEL_221;
      }
      do
      {
        if ( (*(_DWORD *)(v17 + 100) & 3) == 2 )
          break;
        v17 = *(_QWORD *)(v17 + 40);
      }
      while ( v17 );
    }
    else
    {
      v22 = (const char **)v13[43];
      if ( !v22 )
        goto LABEL_220;
      v23 = v22[12];
      v18 = -32768;
      v110 = -32768;
      if ( v23 )
      {
        v24 = *(_QWORD *)(v15 + 32);
        v18 = 0;
        v110 = 0;
        if ( *(const char **)(v24 + 24) != v23 )
        {
          do
            ++v18;
          while ( *(const char **)(32LL * v18 + v24 + 24) != v23 );
          v13 = a1;
          v110 = v18;
        }
      }
    }
    v20 = a4;
    goto LABEL_29;
  }
  v16 = a5;
LABEL_221:
  if ( a8 )
    sqlite3ExprDeleteNN(v15, a8);
  if ( v16 )
    exprListDeleteNN(v15, v16);
  result = sqlite3SrcListDelete(v15, a4);
  if ( v14 )
    return sqlite3DbFreeNN(v15);
  return result;
}

```

## disassembly

```asm
0x18008d624  mov     rax, rsp
0x18008d627  mov     [rax+10h], rbx
0x18008d62b  mov     [rax+20h], r9
0x18008d62f  mov     [rax+8], rcx
0x18008d633  push    rbp
0x18008d634  push    rsi
0x18008d635  push    rdi
0x18008d636  push    r12
0x18008d638  push    r13
0x18008d63a  push    r14
0x18008d63c  push    r15
0x18008d63e  lea     rbp, [rax-3Fh]
0x18008d642  sub     rsp, 100h
0x18008d649  xor     r14d, r14d
0x18008d64c  mov     rdi, r8
0x18008d64f  mov     rbx, rdx
0x18008d652  mov     rsi, rcx
0x18008d655  xor     edx, edx; Val
0x18008d657  lea     rcx, [rbp+37h+var_90]; void *
0x18008d65b  mov     r12d, r14d
0x18008d65e  lea     r8d, [r14+60h]; Size
0x18008d662  call    memset_0
0x18008d667  mov     r15, [rsi]
0x18008d66a  mov     [rbp+37h+var_B0], r15
0x18008d66e  mov     [rsp+130h+var_D0], r14
0x18008d673  mov     [rsp+130h+var_D8], r14
0x18008d678  cmp     [rsi+30h], r14d
0x18008d67c  jnz     loc_18008E39C
0x18008d682  cmp     byte ptr [rsi+12Ch], 1
0x18008d689  jnz     short loc_18008D698
0x18008d68b  cmp     [rbp+37h+arg_50], 2
0x18008d692  jnz     loc_18008E39C
0x18008d698  mov     rcx, rsi
0x18008d69b  call    sqlite3ReadSchema
0x18008d6a0  test    eax, eax
0x18008d6a2  jnz     loc_18008E39C
0x18008d6a8  mov     r14, [rbp+37h+arg_20]
0x18008d6ac  mov     rcx, rsi
0x18008d6af  mov     rdx, r14
0x18008d6b2  mov     [rsp+130h+var_E0], r14
0x18008d6b7  call    sqlite3HasExplicitNulls
0x18008d6bc  xor     r13d, r13d
0x18008d6bf  test    eax, eax
0x18008d6c1  jnz     loc_18008E317
0x18008d6c7  xor     edx, edx
0x18008d6c9  cmp     [rbp+37h+arg_18], rdx
0x18008d6cd  jz      loc_18008D7C7
0x18008d6d3  lea     r9, [rsp+130h+var_D0]
0x18008d6d8  mov     r8, rdi
0x18008d6db  mov     rdx, rbx
0x18008d6de  mov     rcx, rsi
0x18008d6e1  call    sqlite3TwoPartName
0x18008d6e6  mov     dword ptr [rsp+130h+var_E8], eax
0x18008d6ea  mov     ebx, eax
0x18008d6ec  test    eax, eax
0x18008d6ee  js      loc_18008E317
0x18008d6f4  xor     r14d, r14d
0x18008d6f7  cmp     [r15+0C5h], r14b
0x18008d6fe  jnz     short loc_18008D72E
0x18008d700  mov     rdx, [rbp+37h+arg_18]
0x18008d704  mov     rcx, rsi
0x18008d707  call    sqlite3SrcListLookup
0x18008d70c  cmp     [rdi+8], r14d
0x18008d710  jnz     short loc_18008D72E
0x18008d712  test    rax, rax
0x18008d715  jz      short loc_18008D72E
0x18008d717  mov     rcx, [r15+20h]
0x18008d71b  mov     rcx, [rcx+38h]
0x18008d71f  cmp     [rax+60h], rcx
0x18008d723  lea     eax, [r13+1]
0x18008d727  cmovz   ebx, eax
0x18008d72a  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008d72e  mov     rax, [rsp+130h+var_D0]
0x18008d733  lea     r9, aIndex; "index"
0x18008d73a  mov     r8d, ebx
0x18008d73d  mov     [rsp+130h+var_110], rax
0x18008d742  mov     rdx, rsi
0x18008d745  lea     rcx, [rbp+37h+var_90]
0x18008d749  call    sqlite3FixInit
0x18008d74e  mov     rdi, [rbp+37h+arg_18]
0x18008d752  lea     rcx, [rbp+37h+var_90]
0x18008d756  mov     rdx, rdi
0x18008d759  call    sqlite3FixSrcList
0x18008d75e  lea     r8, [rdi+8]
0x18008d762  xor     edx, edx
0x18008d764  mov     rcx, rsi
0x18008d767  call    sqlite3LocateTableItem
0x18008d76c  mov     r14, rax
0x18008d76f  test    rax, rax
0x18008d772  jz      loc_18008E312
0x18008d778  cmp     ebx, 1
0x18008d77b  jnz     short loc_18008D7A2
0x18008d77d  mov     rdx, [r15+20h]
0x18008d781  mov     rcx, [rax+60h]
0x18008d785  cmp     [rdx+38h], rcx
0x18008d789  jz      short loc_18008D7A2
0x18008d78b  mov     r8, [rax]
0x18008d78e  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x18008d795  mov     rcx, rsi
0x18008d798  call    sqlite3ErrorMsg
0x18008d79d  jmp     loc_18008D97B
0x18008d7a2  test    byte ptr [r14+30h], 80h
0x18008d7a7  jz      short loc_18008D815
0x18008d7a9  mov     r13, [r14+10h]
0x18008d7ad  test    r13, r13
0x18008d7b0  jz      short loc_18008D815
0x18008d7b2  mov     eax, [r13+64h]
0x18008d7b6  and     al, 3
0x18008d7b8  cmp     al, 2
0x18008d7ba  jz      short loc_18008D811
0x18008d7bc  mov     r13, [r13+28h]
0x18008d7c0  test    r13, r13
0x18008d7c3  jnz     short loc_18008D7B2
0x18008d7c5  jmp     short loc_18008D811
0x18008d7c7  mov     r14, [rsi+158h]
0x18008d7ce  test    r14, r14
0x18008d7d1  jz      loc_18008E312
0x18008d7d7  mov     rcx, [r14+60h]
0x18008d7db  mov     ebx, 0FFFF8000h
0x18008d7e0  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008d7e4  test    rcx, rcx
0x18008d7e7  jz      short loc_18008D811
0x18008d7e9  mov     rdx, [r15+20h]
0x18008d7ed  xor     ebx, ebx
0x18008d7ef  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008d7f3  cmp     [rdx+18h], rcx
0x18008d7f7  jz      short loc_18008D811
0x18008d7f9  inc     ebx
0x18008d7fb  movsxd  rax, ebx
0x18008d7fe  shl     rax, 5
0x18008d802  cmp     [rax+rdx+18h], rcx
0x18008d807  jnz     short loc_18008D7F9
0x18008d809  mov     rsi, [rbp+37h+arg_0]
0x18008d80d  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008d811  mov     rdi, [rbp+37h+arg_18]
0x18008d815  mov     rcx, [r14]
0x18008d818  lea     rdx, aSqlite_0; "sqlite_"
0x18008d81f  mov     r8d, 7
0x18008d825  call    sqlite3_strnicmp
0x18008d82a  xor     ecx, ecx
0x18008d82c  test    eax, eax
0x18008d82e  jnz     short loc_18008D855
0x18008d830  cmp     [r15+0C5h], cl
0x18008d837  jnz     short loc_18008D855
0x18008d839  test    rdi, rdi
0x18008d83c  jz      short loc_18008D855
0x18008d83e  mov     r8, [r14]
0x18008d841  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x18008d848  mov     rcx, rsi
0x18008d84b  call    sqlite3ErrorMsg
0x18008d850  jmp     loc_18008D972
0x18008d855  mov     al, [r14+3Fh]
0x18008d859  cmp     al, 2
0x18008d85b  jnz     short loc_18008D871
0x18008d85d  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x18008d864  mov     rcx, rsi
0x18008d867  call    sqlite3ErrorMsg
0x18008d86c  jmp     loc_18008D972
0x18008d871  mov     edx, 1
0x18008d876  cmp     al, dl
0x18008d878  jnz     short loc_18008D883
0x18008d87a  lea     rdx, aVirtualTablesM; "virtual tables may not be indexed"
0x18008d881  jmp     short loc_18008D864
0x18008d883  mov     rdi, [r15+20h]
0x18008d887  movsxd  rax, ebx
0x18008d88a  mov     r12, rax
0x18008d88d  mov     [rbp+37h+var_A0], rax
0x18008d891  mov     rax, [rsp+130h+var_D0]
0x18008d896  shl     r12, 5
0x18008d89a  mov     [rsp+130h+var_C8], r12
0x18008d89f  mov     [rbp+37h+var_A8], rdi
0x18008d8a3  test    rax, rax
0x18008d8a6  jz      loc_18008D987
0x18008d8ac  mov     rdx, rax
0x18008d8af  mov     rcx, r15
0x18008d8b2  call    sqlite3NameFromToken
0x18008d8b7  mov     [rsp+130h+Src], rax
0x18008d8bc  test    rax, rax
0x18008d8bf  jz      loc_18008E2F5
0x18008d8c5  mov     r9, [r14]
0x18008d8c8  lea     r8, aIndex; "index"
0x18008d8cf  mov     rdx, rax
0x18008d8d2  mov     rcx, rsi
0x18008d8d5  call    sqlite3CheckObjectName
0x18008d8da  xor     ecx, ecx
0x18008d8dc  test    eax, eax
0x18008d8de  jnz     loc_18008D96D
0x18008d8e4  cmp     byte ptr [rsi+12Ch], 2
0x18008d8eb  jnb     loc_18008DA36
0x18008d8f1  cmp     [r15+0C5h], cl
0x18008d8f8  jnz     short loc_18008D924
0x18008d8fa  mov     r8, [r12+rdi]
0x18008d8fe  mov     rcx, r15
0x18008d901  mov     rdx, [rsp+130h+Src]
0x18008d906  call    sqlite3FindTable
0x18008d90b  test    rax, rax
0x18008d90e  jz      short loc_18008D924
0x18008d910  mov     r12, [rsp+130h+Src]
0x18008d915  lea     rdx, aThereIsAlready; "there is already a table named %s"
0x18008d91c  mov     r8, r12
0x18008d91f  jmp     loc_18008D848
0x18008d924  mov     r8, [r12+rdi]
0x18008d928  mov     rcx, r15
0x18008d92b  mov     rdx, [rsp+130h+Src]
0x18008d930  call    sqlite3FindIndex
0x18008d935  test    rax, rax
0x18008d938  jz      loc_18008D9C9
0x18008d93e  cmp     [rbp+37h+arg_48], 0
0x18008d945  mov     rcx, rsi
0x18008d948  jnz     short loc_18008D95E
0x18008d94a  mov     r12, [rsp+130h+Src]
0x18008d94f  lea     rdx, aIndexSAlreadyE; "index %s already exists"
0x18008d956  mov     r8, r12
0x18008d959  jmp     loc_18008D84B
0x18008d95e  mov     edx, ebx
0x18008d960  call    sqlite3CodeVerifySchema
0x18008d965  mov     rcx, rsi
0x18008d968  call    sqlite3ForceNotReadOnly
0x18008d96d  mov     r12, [rsp+130h+Src]
0x18008d972  test    r14, r14
0x18008d975  jz      loc_18008E312
0x18008d97b  add     r14, 10h
0x18008d97f  mov     rcx, [r14]
0x18008d982  jmp     loc_18008E30D
0x18008d987  mov     rax, [r14+10h]
0x18008d98b  mov     r9d, edx
0x18008d98e  jmp     short loc_18008D997
0x18008d990  mov     rax, [rax+28h]
0x18008d994  add     r9d, edx
0x18008d997  test    rax, rax
0x18008d99a  jnz     short loc_18008D990
0x18008d99c  mov     r8, [r14]
0x18008d99f  lea     rdx, aSqliteAutoinde; "sqlite_autoindex_%s_%d"
0x18008d9a6  mov     rcx, r15
0x18008d9a9  call    sqlite3MPrintf
0x18008d9ae  xor     ecx, ecx
0x18008d9b0  mov     [rsp+130h+Src], rax
0x18008d9b5  test    rax, rax
0x18008d9b8  jz      loc_18008E2F5
0x18008d9be  cmp     [rsi+12Ch], cl
0x18008d9c4  jz      short loc_18008D9C9
0x18008d9c6  inc     byte ptr [rax+7]
0x18008d9c9  cmp     byte ptr [rsi+12Ch], 2
0x18008d9d0  jnb     short loc_18008DA36
0x18008d9d2  mov     rdi, [r12+rdi]
0x18008d9d6  lea     rax, aSqliteMaster; "sqlite_master"
0x18008d9dd  cmp     ebx, 1
0x18008d9e0  mov     [rsp+130h+var_110], rdi
0x18008d9e5  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18008d9ec  mov     rcx, rsi
0x18008d9ef  cmovnz  r8, rax
0x18008d9f3  xor     r9d, r9d
0x18008d9f6  lea     edx, [r9+12h]
0x18008d9fa  call    sqlite3AuthCheck
0x18008d9ff  test    eax, eax
0x18008da01  jnz     loc_18008D96D
0x18008da07  mov     r9, [r14]
0x18008da0a  lea     edx, [rax+3]
0x18008da0d  lea     eax, [rdx-2]
0x18008da10  mov     [rsp+130h+var_110], rdi
0x18008da15  mov     rdi, [rsp+130h+Src]
0x18008da1a  cmp     ebx, eax
0x18008da1c  mov     r8, rdi
0x18008da1f  mov     rcx, rsi
0x18008da22  cmovnz  edx, eax
0x18008da25  call    sqlite3AuthCheck
0x18008da2a  test    eax, eax
0x18008da2c  jz      short loc_18008DA3B
0x18008da2e  mov     r12, rdi
0x18008da31  jmp     loc_18008D972
0x18008da36  mov     rdi, [rsp+130h+Src]
0x18008da3b  mov     r10, [rbp+37h+arg_20]
0x18008da3f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008da43  mov     edx, 8
0x18008da48  test    r10, r10
0x18008da4b  jnz     loc_18008DAE2
0x18008da51  movsx   rax, word ptr [r14+36h]
0x18008da56  mov     [rbp+37h+var_B4], r10d
0x18008da5a  lea     rcx, [rax+rax*2]
0x18008da5e  mov     rax, [r14+8]
0x18008da62  or      [rax+rcx*8-6], dx
0x18008da67  mov     rdx, [rax+rcx*8-18h]
0x18008da6c  mov     [rsp+130h+var_C0], rdx
0x18008da71  test    rdx, rdx
0x18008da74  jnz     short loc_18008DA7B
0x18008da76  mov     eax, r10d
0x18008da79  jmp     short loc_18008DA8C
0x18008da7b  mov     rax, rbx
0x18008da7e  inc     rax
0x18008da81  cmp     [rdx+rax], r10b
0x18008da85  jnz     short loc_18008DA7E
0x18008da87  and     eax, 3FFFFFFFh
0x18008da8c  xor     r9d, r9d
0x18008da8f  mov     [rsp+130h+var_B8], eax
0x18008da93  lea     r8, [rsp+130h+var_C0]
0x18008da98  mov     rcx, r15
0x18008da9b  lea     edx, [r9+3Bh]
0x18008da9f  call    sqlite3ExprAlloc
0x18008daa4  mov     rcx, [rsi]
0x18008daa7  mov     rdx, rax
  ... truncated ...
```
