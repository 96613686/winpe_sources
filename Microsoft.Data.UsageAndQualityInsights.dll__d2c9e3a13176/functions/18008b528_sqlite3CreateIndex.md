# sqlite3CreateIndex

- ea: `0x18008b528`
- end: `0x18008c2a9`
- name: `sqlite3CreateIndex`
- size: `3457`
- prototype: ``
- caller_count: `3`
- callee_count: `48`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18005b364`
- `0x1800820e0`
- `0x1800dea88`

## callees

- `0x180003fa0`
- `0x180003fb8`
- `0x18005e3b4`
- `0x1800609cc`
- `0x180067990`
- `0x18007a5d4`
- `0x1800825e0`
- `0x180084260`
- `0x180084c14`
- `0x180088a08`
- `0x180088a4c`
- `0x180089bdc`
- `0x180089f50`
- `0x18008ad1c`
- `0x18008b528`
- `0x18008c5ac`
- `0x18008caa8`
- `0x18008e99c`
- `0x18008efa0`
- `0x180091c1c`
- `0x180092a04`
- `0x180093a9c`
- `0x180093b24`
- `0x1800943c4`
- `0x180094448`
- `0x180095294`
- `0x1800957b8`
- `0x180098328`
- `0x1800983f8`
- `0x1800984c8`
- `0x18009b474`
- `0x18009b624`
- `0x18009ba14`
- `0x18009c604`
- `0x18009c6a4`
- `0x18009c8ec`
- `0x1800a4194`
- `0x1800a4538`
- `0x1800a52c8`
- `0x1800a8fd4`
- `0x1800a9438`
- `0x1800a9c10`
- `0x1800aa1c8`
- `0x1800aa940`
- `0x1800ad288`
- `0x1800ad4e8`
- `0x1800b5264`
- `0x1800c88e0`

## string_xrefs

- `0x18008b8e9`: `sqlite_temp_master`
- `0x18008b692`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x18008b819`: `there is already a table named %s`
- `0x18008b853`: `index %s already exists`
- `0x18008c0f6`: `CREATE%s INDEX %.*s`

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
  if ( !*((_DWORD *)v13 + 12) && (*((_BYTE *)v13 + 308) != 1 || a11 == 2) && !(unsigned int)sqlite3ReadSchema(v13) )
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
            if ( *((_BYTE *)v13 + 308) >= 2u )
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
            if ( *((_BYTE *)v13 + 308) < 2u )
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
              v64 = *((_BYTE *)v13 + 308) < 2u;
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
                        *((_DWORD *)v58 + 25) |= 0x1800u;
                    }
                    else
                    {
                      LODWORD(v72) = *((__int16 *)v22 + 26);
                    }
                    *((_WORD *)v58[1] + v67) = v72;
                  }
                  else
                  {
                    if ( v22 == (const char **)v13[44] )
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
                    *((_DWORD *)v58 + 25) |= 0x1000u;
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
              if ( !v13[44] )
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
              if ( v22 == (const char **)v13[44] )
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
                        if ( *((_BYTE *)v13 + 308) >= 2u )
                        {
                          v58[5] = (void *)v13[45];
                          v13[45] = v58;
                          v58 = 0;
                        }
                        goto LABEL_145;
                      }
                    }
                  }
                }
              }
              if ( *((_BYTE *)v13 + 308) < 2u )
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
                        *((_DWORD *)v13 + 6) = sqlite3CorruptError(126057);
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
                      if ( *((_BYTE *)v13 + 308) >= 2u )
                      {
                        v13[45] = v58;
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
                  *((_DWORD *)v58 + 22) = sqlite3VdbeAddOp3(Vdbe, 187, 0, 0, 0);
                  sqlite3VdbeAddOp3(Vdbe, 147, v110, v98, 2);
                  if ( a7 )
                  {
                    v100 = (const char *)&::Src;
                    v101 = *((_DWORD *)v13 + 72) + *((_DWORD *)v13 + 74) - *(_DWORD *)v113;
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
            if ( *((_BYTE *)v13 + 308) )
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
      v22 = (const char **)v13[44];
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
0x18008b528  mov     rax, rsp
0x18008b52b  mov     [rax+10h], rbx
0x18008b52f  mov     [rax+20h], r9
0x18008b533  mov     [rax+8], rcx
0x18008b537  push    rbp
0x18008b538  push    rsi
0x18008b539  push    rdi
0x18008b53a  push    r12
0x18008b53c  push    r13
0x18008b53e  push    r14
0x18008b540  push    r15
0x18008b542  lea     rbp, [rax-3Fh]
0x18008b546  sub     rsp, 100h
0x18008b54d  xor     r14d, r14d
0x18008b550  mov     rdi, r8
0x18008b553  mov     rbx, rdx
0x18008b556  mov     rsi, rcx
0x18008b559  xor     edx, edx; Val
0x18008b55b  lea     rcx, [rbp+37h+var_90]; void *
0x18008b55f  mov     r12d, r14d
0x18008b562  lea     r8d, [r14+60h]; Size
0x18008b566  call    memset_0
0x18008b56b  mov     r15, [rsi]
0x18008b56e  mov     [rbp+37h+var_B0], r15
0x18008b572  mov     [rsp+130h+var_D0], r14
0x18008b577  mov     [rsp+130h+var_D8], r14
0x18008b57c  cmp     [rsi+30h], r14d
0x18008b580  jnz     loc_18008C2A0
0x18008b586  cmp     byte ptr [rsi+134h], 1
0x18008b58d  jnz     short loc_18008B59C
0x18008b58f  cmp     [rbp+37h+arg_50], 2
0x18008b596  jnz     loc_18008C2A0
0x18008b59c  mov     rcx, rsi
0x18008b59f  call    sqlite3ReadSchema
0x18008b5a4  test    eax, eax
0x18008b5a6  jnz     loc_18008C2A0
0x18008b5ac  mov     r14, [rbp+37h+arg_20]
0x18008b5b0  mov     rcx, rsi
0x18008b5b3  mov     rdx, r14
0x18008b5b6  mov     [rsp+130h+var_E0], r14
0x18008b5bb  call    sqlite3HasExplicitNulls
0x18008b5c0  xor     r13d, r13d
0x18008b5c3  test    eax, eax
0x18008b5c5  jnz     loc_18008C21B
0x18008b5cb  xor     edx, edx
0x18008b5cd  cmp     [rbp+37h+arg_18], rdx
0x18008b5d1  jz      loc_18008B6CB
0x18008b5d7  lea     r9, [rsp+130h+var_D0]
0x18008b5dc  mov     r8, rdi
0x18008b5df  mov     rdx, rbx
0x18008b5e2  mov     rcx, rsi
0x18008b5e5  call    sqlite3TwoPartName
0x18008b5ea  mov     dword ptr [rsp+130h+var_E8], eax
0x18008b5ee  mov     ebx, eax
0x18008b5f0  test    eax, eax
0x18008b5f2  js      loc_18008C21B
0x18008b5f8  xor     r14d, r14d
0x18008b5fb  cmp     [r15+0C5h], r14b
0x18008b602  jnz     short loc_18008B632
0x18008b604  mov     rdx, [rbp+37h+arg_18]
0x18008b608  mov     rcx, rsi
0x18008b60b  call    sqlite3SrcListLookup
0x18008b610  cmp     [rdi+8], r14d
0x18008b614  jnz     short loc_18008B632
0x18008b616  test    rax, rax
0x18008b619  jz      short loc_18008B632
0x18008b61b  mov     rcx, [r15+20h]
0x18008b61f  mov     rcx, [rcx+38h]
0x18008b623  cmp     [rax+60h], rcx
0x18008b627  lea     eax, [r13+1]
0x18008b62b  cmovz   ebx, eax
0x18008b62e  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008b632  mov     rax, [rsp+130h+var_D0]
0x18008b637  lea     r9, aIndex; "index"
0x18008b63e  mov     r8d, ebx
0x18008b641  mov     [rsp+130h+var_110], rax
0x18008b646  mov     rdx, rsi
0x18008b649  lea     rcx, [rbp+37h+var_90]
0x18008b64d  call    sqlite3FixInit
0x18008b652  mov     rdi, [rbp+37h+arg_18]
0x18008b656  lea     rcx, [rbp+37h+var_90]
0x18008b65a  mov     rdx, rdi
0x18008b65d  call    sqlite3FixSrcList
0x18008b662  lea     r8, [rdi+8]
0x18008b666  xor     edx, edx
0x18008b668  mov     rcx, rsi
0x18008b66b  call    sqlite3LocateTableItem
0x18008b670  mov     r14, rax
0x18008b673  test    rax, rax
0x18008b676  jz      loc_18008C216
0x18008b67c  cmp     ebx, 1
0x18008b67f  jnz     short loc_18008B6A6
0x18008b681  mov     rdx, [r15+20h]
0x18008b685  mov     rcx, [rax+60h]
0x18008b689  cmp     [rdx+38h], rcx
0x18008b68d  jz      short loc_18008B6A6
0x18008b68f  mov     r8, [rax]
0x18008b692  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x18008b699  mov     rcx, rsi
0x18008b69c  call    sqlite3ErrorMsg
0x18008b6a1  jmp     loc_18008B87F
0x18008b6a6  test    byte ptr [r14+30h], 80h
0x18008b6ab  jz      short loc_18008B719
0x18008b6ad  mov     r13, [r14+10h]
0x18008b6b1  test    r13, r13
0x18008b6b4  jz      short loc_18008B719
0x18008b6b6  mov     eax, [r13+64h]
0x18008b6ba  and     al, 3
0x18008b6bc  cmp     al, 2
0x18008b6be  jz      short loc_18008B715
0x18008b6c0  mov     r13, [r13+28h]
0x18008b6c4  test    r13, r13
0x18008b6c7  jnz     short loc_18008B6B6
0x18008b6c9  jmp     short loc_18008B715
0x18008b6cb  mov     r14, [rsi+160h]
0x18008b6d2  test    r14, r14
0x18008b6d5  jz      loc_18008C216
0x18008b6db  mov     rcx, [r14+60h]
0x18008b6df  mov     ebx, 0FFFF8000h
0x18008b6e4  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008b6e8  test    rcx, rcx
0x18008b6eb  jz      short loc_18008B715
0x18008b6ed  mov     rdx, [r15+20h]
0x18008b6f1  xor     ebx, ebx
0x18008b6f3  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008b6f7  cmp     [rdx+18h], rcx
0x18008b6fb  jz      short loc_18008B715
0x18008b6fd  inc     ebx
0x18008b6ff  movsxd  rax, ebx
0x18008b702  shl     rax, 5
0x18008b706  cmp     [rax+rdx+18h], rcx
0x18008b70b  jnz     short loc_18008B6FD
0x18008b70d  mov     rsi, [rbp+37h+arg_0]
0x18008b711  mov     dword ptr [rsp+130h+var_E8], ebx
0x18008b715  mov     rdi, [rbp+37h+arg_18]
0x18008b719  mov     rcx, [r14]
0x18008b71c  lea     rdx, aSqlite_0; "sqlite_"
0x18008b723  mov     r8d, 7
0x18008b729  call    sqlite3_strnicmp
0x18008b72e  xor     ecx, ecx
0x18008b730  test    eax, eax
0x18008b732  jnz     short loc_18008B759
0x18008b734  cmp     [r15+0C5h], cl
0x18008b73b  jnz     short loc_18008B759
0x18008b73d  test    rdi, rdi
0x18008b740  jz      short loc_18008B759
0x18008b742  mov     r8, [r14]
0x18008b745  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x18008b74c  mov     rcx, rsi
0x18008b74f  call    sqlite3ErrorMsg
0x18008b754  jmp     loc_18008B876
0x18008b759  mov     al, [r14+3Fh]
0x18008b75d  cmp     al, 2
0x18008b75f  jnz     short loc_18008B775
0x18008b761  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x18008b768  mov     rcx, rsi
0x18008b76b  call    sqlite3ErrorMsg
0x18008b770  jmp     loc_18008B876
0x18008b775  mov     edx, 1
0x18008b77a  cmp     al, dl
0x18008b77c  jnz     short loc_18008B787
0x18008b77e  lea     rdx, aVirtualTablesM; "virtual tables may not be indexed"
0x18008b785  jmp     short loc_18008B768
0x18008b787  mov     rdi, [r15+20h]
0x18008b78b  movsxd  rax, ebx
0x18008b78e  mov     r12, rax
0x18008b791  mov     [rbp+37h+var_A0], rax
0x18008b795  mov     rax, [rsp+130h+var_D0]
0x18008b79a  shl     r12, 5
0x18008b79e  mov     [rsp+130h+var_C8], r12
0x18008b7a3  mov     [rbp+37h+var_A8], rdi
0x18008b7a7  test    rax, rax
0x18008b7aa  jz      loc_18008B88B
0x18008b7b0  mov     rdx, rax
0x18008b7b3  mov     rcx, r15
0x18008b7b6  call    sqlite3NameFromToken
0x18008b7bb  mov     [rsp+130h+Src], rax
0x18008b7c0  test    rax, rax
0x18008b7c3  jz      loc_18008C1F9
0x18008b7c9  mov     r9, [r14]
0x18008b7cc  lea     r8, aIndex; "index"
0x18008b7d3  mov     rdx, rax
0x18008b7d6  mov     rcx, rsi
0x18008b7d9  call    sqlite3CheckObjectName
0x18008b7de  xor     ecx, ecx
0x18008b7e0  test    eax, eax
0x18008b7e2  jnz     loc_18008B871
0x18008b7e8  cmp     byte ptr [rsi+134h], 2
0x18008b7ef  jnb     loc_18008B93A
0x18008b7f5  cmp     [r15+0C5h], cl
0x18008b7fc  jnz     short loc_18008B828
0x18008b7fe  mov     r8, [r12+rdi]
0x18008b802  mov     rcx, r15
0x18008b805  mov     rdx, [rsp+130h+Src]
0x18008b80a  call    sqlite3FindTable
0x18008b80f  test    rax, rax
0x18008b812  jz      short loc_18008B828
0x18008b814  mov     r12, [rsp+130h+Src]
0x18008b819  lea     rdx, aThereIsAlready; "there is already a table named %s"
0x18008b820  mov     r8, r12
0x18008b823  jmp     loc_18008B74C
0x18008b828  mov     r8, [r12+rdi]
0x18008b82c  mov     rcx, r15
0x18008b82f  mov     rdx, [rsp+130h+Src]
0x18008b834  call    sqlite3FindIndex
0x18008b839  test    rax, rax
0x18008b83c  jz      loc_18008B8CD
0x18008b842  cmp     [rbp+37h+arg_48], 0
0x18008b849  mov     rcx, rsi
0x18008b84c  jnz     short loc_18008B862
0x18008b84e  mov     r12, [rsp+130h+Src]
0x18008b853  lea     rdx, aIndexSAlreadyE; "index %s already exists"
0x18008b85a  mov     r8, r12
0x18008b85d  jmp     loc_18008B74F
0x18008b862  mov     edx, ebx
0x18008b864  call    sqlite3CodeVerifySchema
0x18008b869  mov     rcx, rsi
0x18008b86c  call    sqlite3ForceNotReadOnly
0x18008b871  mov     r12, [rsp+130h+Src]
0x18008b876  test    r14, r14
0x18008b879  jz      loc_18008C216
0x18008b87f  add     r14, 10h
0x18008b883  mov     rcx, [r14]
0x18008b886  jmp     loc_18008C211
0x18008b88b  mov     rax, [r14+10h]
0x18008b88f  mov     r9d, edx
0x18008b892  jmp     short loc_18008B89B
0x18008b894  mov     rax, [rax+28h]
0x18008b898  add     r9d, edx
0x18008b89b  test    rax, rax
0x18008b89e  jnz     short loc_18008B894
0x18008b8a0  mov     r8, [r14]
0x18008b8a3  lea     rdx, aSqliteAutoinde; "sqlite_autoindex_%s_%d"
0x18008b8aa  mov     rcx, r15
0x18008b8ad  call    sqlite3MPrintf
0x18008b8b2  xor     ecx, ecx
0x18008b8b4  mov     [rsp+130h+Src], rax
0x18008b8b9  test    rax, rax
0x18008b8bc  jz      loc_18008C1F9
0x18008b8c2  cmp     [rsi+134h], cl
0x18008b8c8  jz      short loc_18008B8CD
0x18008b8ca  inc     byte ptr [rax+7]
0x18008b8cd  cmp     byte ptr [rsi+134h], 2
0x18008b8d4  jnb     short loc_18008B93A
0x18008b8d6  mov     rdi, [r12+rdi]
0x18008b8da  lea     rax, aSqliteMaster; "sqlite_master"
0x18008b8e1  cmp     ebx, 1
0x18008b8e4  mov     [rsp+130h+var_110], rdi
0x18008b8e9  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18008b8f0  mov     rcx, rsi
0x18008b8f3  cmovnz  r8, rax
0x18008b8f7  xor     r9d, r9d
0x18008b8fa  lea     edx, [r9+12h]
0x18008b8fe  call    sqlite3AuthCheck
0x18008b903  test    eax, eax
0x18008b905  jnz     loc_18008B871
0x18008b90b  mov     r9, [r14]
0x18008b90e  lea     edx, [rax+3]
0x18008b911  lea     eax, [rdx-2]
0x18008b914  mov     [rsp+130h+var_110], rdi
0x18008b919  mov     rdi, [rsp+130h+Src]
0x18008b91e  cmp     ebx, eax
0x18008b920  mov     r8, rdi
0x18008b923  mov     rcx, rsi
0x18008b926  cmovnz  edx, eax
0x18008b929  call    sqlite3AuthCheck
0x18008b92e  test    eax, eax
0x18008b930  jz      short loc_18008B93F
0x18008b932  mov     r12, rdi
0x18008b935  jmp     loc_18008B876
0x18008b93a  mov     rdi, [rsp+130h+Src]
0x18008b93f  mov     r10, [rbp+37h+arg_20]
0x18008b943  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008b947  mov     edx, 8
0x18008b94c  test    r10, r10
0x18008b94f  jnz     loc_18008B9E6
0x18008b955  movsx   rax, word ptr [r14+36h]
0x18008b95a  mov     [rbp+37h+var_B4], r10d
0x18008b95e  lea     rcx, [rax+rax*2]
0x18008b962  mov     rax, [r14+8]
0x18008b966  or      [rax+rcx*8-6], dx
0x18008b96b  mov     rdx, [rax+rcx*8-18h]
0x18008b970  mov     [rsp+130h+var_C0], rdx
0x18008b975  test    rdx, rdx
0x18008b978  jnz     short loc_18008B97F
0x18008b97a  mov     eax, r10d
0x18008b97d  jmp     short loc_18008B990
0x18008b97f  mov     rax, rbx
0x18008b982  inc     rax
0x18008b985  cmp     [rdx+rax], r10b
0x18008b989  jnz     short loc_18008B982
0x18008b98b  and     eax, 3FFFFFFFh
0x18008b990  xor     r9d, r9d
0x18008b993  mov     [rsp+130h+var_B8], eax
0x18008b997  lea     r8, [rsp+130h+var_C0]
0x18008b99c  mov     rcx, r15
0x18008b99f  lea     edx, [r9+3Bh]
0x18008b9a3  call    sqlite3ExprAlloc
0x18008b9a8  mov     rcx, [rsi]
0x18008b9ab  mov     rdx, rax
  ... truncated ...
```
