# sqlite3CreateIndex

- ea: `0x180070c5c`
- end: `0x1800718d7`
- name: `sqlite3CreateIndex`
- size: `3195`
- prototype: ``
- caller_count: `3`
- callee_count: `55`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800461e4`
- `0x1800684c4`
- `0x1800be9b8`

## callees

- `0x180006920`
- `0x180006938`
- `0x180048e8c`
- `0x1800518e0`
- `0x180061248`
- `0x1800688fc`
- `0x18006a3e8`
- `0x18006ae4c`
- `0x18006e6fc`
- `0x18006f6f4`
- `0x18006f804`
- `0x180070c5c`
- `0x180071b80`
- `0x1800720c4`
- `0x180073d2c`
- `0x180074248`
- `0x180076be0`
- `0x180077794`
- `0x180077a0c`
- `0x180077ac0`
- `0x180077c90`
- `0x180078024`
- `0x18007894c`
- `0x1800789d4`
- `0x180079248`
- `0x1800792cc`
- `0x18007a09c`
- `0x18007a5bc`
- `0x18007cf80`
- `0x18007d038`
- `0x18007d108`
- `0x18007d55c`
- `0x18007fdbc`
- `0x18007ff6c`
- `0x18008032c`
- `0x180080b40`
- `0x180080b70`
- `0x180080dbc`
- `0x180087228`
- `0x1800879b4`
- `0x180087ce4`
- `0x1800884f0`
- `0x1800889f4`
- `0x180089c24`
- `0x18008c384`
- `0x18008c7a0`
- `0x18008d0f4`
- `0x18008d160`
- `0x18008d184`
- `0x18008d6ac`

## string_xrefs

- `0x180070fc3`: `sqlite_temp_master`
- `0x180070dce`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x180070f3f`: `index %s already exists`
- `0x180070f10`: `there is already a table named %s`
- `0x18007172f`: `CREATE%s INDEX %.*s`

## pseudocode

```c
__int64 __fastcall sqlite3CreateIndex(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _WORD *a5,
        int a6,
        __int64 a7,
        void *a8,
        unsigned int a9,
        int a10,
        unsigned __int8 a11)
{
  __int64 *v13; // rdi
  _BYTE *v15; // r13
  __int64 v16; // r15
  int v17; // r12d
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 TableItem; // rax
  const char **v21; // r14
  const char *v22; // r8
  const char *v23; // rdx
  char v24; // al
  __int64 v25; // rsi
  __int64 v26; // rbx
  __int64 v27; // rax
  const char *v28; // rax
  int v29; // r9d
  __int64 v30; // rsi
  const char *v31; // r8
  int v32; // edx
  _DWORD *v33; // rsi
  const char *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 i; // rdx
  __int64 v40; // rcx
  int v41; // eax
  int v42; // r8d
  int v43; // eax
  int v44; // r8d
  __int64 v45; // rdx
  void **v46; // rax
  void **v47; // rsi
  char *v48; // rcx
  size_t v49; // r8
  int v50; // eax
  unsigned int v51; // ecx
  const char *v52; // rdx
  bool v53; // cf
  _QWORD *v54; // r8
  int v55; // ebx
  int v56; // r13d
  _QWORD *v57; // r8
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rcx
  int v63; // eax
  const char *v64; // r13
  size_t v65; // rbx
  const void *v66; // rcx
  const char *v67; // rax
  char *v68; // r8
  __int64 v69; // rdx
  char v70; // cl
  _BYTE *v71; // rax
  __int64 *k; // r14
  __int64 v73; // rcx
  int v74; // r15d
  int v75; // ebx
  __int64 v76; // rdi
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // rax
  int v80; // ebx
  int v81; // r13d
  int v82; // r11d
  const char *j; // rbx
  int v84; // r13d
  unsigned int v85; // r11d
  _WORD *v86; // rax
  __int64 v87; // rcx
  int v88; // r11d
  char v89; // al
  __int64 v90; // r12
  unsigned int v91; // ebx
  __int64 Vdbe; // r13
  const char *v93; // r8
  unsigned int v94; // edx
  __int64 v95; // r9
  __int64 v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rax
  unsigned __int8 v100; // [rsp+48h] [rbp-B9h]
  _BYTE *v101; // [rsp+50h] [rbp-B1h]
  int v102; // [rsp+58h] [rbp-A9h]
  int v103; // [rsp+58h] [rbp-A9h]
  _WORD *v104; // [rsp+60h] [rbp-A1h]
  void *v105; // [rsp+68h] [rbp-99h] BYREF
  __int64 v106; // [rsp+70h] [rbp-91h]
  _QWORD *v107; // [rsp+78h] [rbp-89h] BYREF
  char *v108; // [rsp+80h] [rbp-81h] BYREF
  int v109; // [rsp+88h] [rbp-79h]
  int v110; // [rsp+8Ch] [rbp-75h]
  const char **v111; // [rsp+90h] [rbp-71h]
  __int64 v112; // [rsp+98h] [rbp-69h]
  __int64 v113; // [rsp+A0h] [rbp-61h]
  _BYTE v114[144]; // [rsp+A8h] [rbp-59h] BYREF
  unsigned int v116; // [rsp+148h] [rbp+47h]

  v13 = a1;
  v15 = 0;
  memset_0(v114, 0, 0x60u);
  v16 = *v13;
  v113 = *v13;
  v107 = 0;
  v105 = 0;
  if ( *((_DWORD *)v13 + 12) || *((_BYTE *)v13 + 300) == 1 && a11 != 2 || (unsigned int)sqlite3ReadSchema(v13) )
  {
    v104 = a5;
    goto LABEL_180;
  }
  v104 = a5;
  if ( !(unsigned int)sqlite3HasExplicitNulls(v13, a5) )
  {
    v106 = 0;
    if ( a4 )
    {
      v17 = sqlite3TwoPartName(v13, a2, a3, &v107);
      if ( v17 < 0 )
        goto LABEL_180;
      if ( !*(_BYTE *)(v16 + 197) )
      {
        v18 = sqlite3SrcListLookup(v13, a4);
        if ( !*(_DWORD *)(a3 + 8) && v18 && *(_QWORD *)(v18 + 96) == *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) )
          v17 = 1;
      }
      sqlite3FixInit((unsigned int)v114, (_DWORD)v13, v17, (unsigned int)"index", (__int64)v107);
      v19 = a4;
      sqlite3FixSrcList(v114, a4);
      TableItem = sqlite3LocateTableItem(v13, 0, a4 + 8);
      v111 = (const char **)TableItem;
      v21 = (const char **)TableItem;
      if ( !TableItem )
        goto LABEL_100;
      if ( v17 == 1 && *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) != *(_QWORD *)(TableItem + 96) )
      {
        sqlite3ErrorMsg(v13, "cannot create a TEMP index on non-TEMP table \"%s\"", *(const char **)TableItem);
        goto LABEL_101;
      }
      if ( *(char *)(TableItem + 48) < 0 )
        v106 = sqlite3PrimaryKeyIndex(TableItem);
    }
    else
    {
      v21 = (const char **)v13[43];
      v111 = v21;
      if ( !v21 )
        goto LABEL_180;
      v19 = a4;
      v17 = sqlite3SchemaToIndex(v16, v21[12]);
    }
    if ( !(unsigned int)sqlite3_strnicmp(*v21, "sqlite_", 7) && !*(_BYTE *)(v16 + 197) && v19 )
    {
      v22 = *v21;
      v23 = "table %s may not be indexed";
LABEL_25:
      sqlite3ErrorMsg(v13, v23, v22);
      goto LABEL_100;
    }
    v24 = *((_BYTE *)v21 + 63);
    if ( v24 == 2 )
    {
      sqlite3ErrorMsg(v13, "views may not be indexed");
      goto LABEL_100;
    }
    if ( v24 == 1 )
    {
      sqlite3ErrorMsg(v13, "virtual tables may not be indexed");
      goto LABEL_100;
    }
    v25 = *(_QWORD *)(v16 + 32);
    v26 = 32LL * v17;
    v112 = v25;
    if ( v107 )
    {
      v27 = sqlite3NameFromToken(v16, v107);
      v101 = (_BYTE *)v27;
      v15 = (_BYTE *)v27;
      if ( !v27 || (unsigned int)sqlite3CheckObjectName(v13, v27, "index", *v21) )
        goto LABEL_100;
      if ( *((_BYTE *)v13 + 300) >= 2u )
      {
LABEL_54:
        v33 = a5;
        if ( a5 )
        {
          sqlite3ExprListCheckLength(v13, a5, "index");
          if ( *((_DWORD *)v13 + 12) )
            goto LABEL_100;
        }
        else
        {
          v34 = v21[1];
          v110 = 0;
          v35 = *((__int16 *)v21 + 27);
          *(_WORD *)&v34[24 * v35 - 6] |= 8u;
          v108 = *(char **)&v34[24 * v35 - 24];
          v109 = ((__int64 (*)(void))sqlite3Strlen30)();
          v36 = sqlite3ExprAlloc(v16, 59, &v108, 0);
          v37 = sqlite3ExprListAppend(v13, 0, v36);
          v104 = (_WORD *)v37;
          v33 = (_DWORD *)v37;
          if ( !v37 )
            goto LABEL_100;
          sqlite3ExprListSetSortOrder(v37, a9, 0xFFFFFFFFLL);
        }
        v38 = 0;
        for ( i = 0; (int)i < *v33; i = (unsigned int)(i + 1) )
        {
          v40 = *(_QWORD *)&v33[8 * (unsigned int)i + 2];
          if ( *(_BYTE *)v40 == 113 )
          {
            v41 = sqlite3Strlen30(*(_QWORD *)(v40 + 8), i, v38);
            v38 = (unsigned int)(v41 + v42 + 1);
          }
        }
        v43 = sqlite3Strlen30(v15, i, v38);
        v102 = v43;
        if ( v106 )
          v45 = *(unsigned __int16 *)(v106 + 94);
        else
          v45 = 1;
        LOWORD(v45) = *(_WORD *)v33 + v45;
        v46 = (void **)sqlite3AllocateIndexObject(v16, v45, (unsigned int)(v43 + 1 + v44), &v105);
        v47 = v46;
        if ( *(_BYTE *)(v16 + 103) )
        {
LABEL_98:
          if ( v47 )
            sqlite3FreeIndex(v16, v47);
          goto LABEL_100;
        }
        v48 = (char *)v105;
        *v46 = v105;
        v49 = v102 + 1;
        v108 = &v48[v49];
        memcpy_0(v48, v15, v49);
        *((_BYTE *)v47 + 98) = a6;
        v50 = *((_DWORD *)v47 + 25);
        v47[3] = v21;
        v51 = v50 & 0xFFFFFFF7 | (a6 != 0 ? 8 : 0);
        v52 = 0;
        *((_DWORD *)v47 + 25) = v51 ^ ((unsigned __int8)v51 ^ a11) & 3;
        v47[6] = *(void **)(v26 + *(_QWORD *)(v16 + 32) + 24);
        *((_WORD *)v47 + 47) = *v104;
        if ( a8 )
        {
          sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v21, 2, (_DWORD)a8, 0);
          v52 = 0;
          v47[9] = a8;
          a8 = 0;
        }
        v53 = *((_BYTE *)v13 + 300) < 2u;
        v54 = v104 + 4;
        v105 = v104 + 4;
        v100 = *(_BYTE *)(*(_QWORD *)(v26 + v112 + 24) + 112LL);
        if ( !v53 )
        {
          v47[10] = v104;
          v104 = 0;
        }
        v55 = 0;
        while ( 1 )
        {
          v56 = *((unsigned __int16 *)v47 + 47);
          v103 = v55;
          if ( v55 >= v56 )
          {
            if ( v106 )
            {
              if ( *(_WORD *)(v106 + 94) )
              {
                v74 = v55;
                v75 = 0;
                v76 = v106;
                do
                {
                  if ( (unsigned int)isDupColumn(v47, (unsigned __int16)v56, v76, (unsigned int)v75) )
                  {
                    --*((_WORD *)v47 + 48);
                  }
                  else
                  {
                    v77 = v74++;
                    v52 = (const char *)v75;
                    *((_WORD *)v47[1] + v77) = *(_WORD *)(*(_QWORD *)(v76 + 8) + 2LL * v75);
                    *((_QWORD *)v47[8] + v77) = *(_QWORD *)(*(_QWORD *)(v76 + 64) + 8LL * v75);
                    *((_BYTE *)v47[7] + v77) = *(_BYTE *)(v75 + *(_QWORD *)(v76 + 56));
                    LOWORD(v56) = *((_WORD *)v47 + 47);
                  }
                  ++v75;
                }
                while ( v75 < *(unsigned __int16 *)(v76 + 94) );
                v13 = a1;
                v21 = v111;
                v16 = v113;
              }
            }
            else
            {
              v52 = "BINARY";
              *((_WORD *)v47[1] + v55) = -1;
              *((_QWORD *)v47[8] + v55) = "BINARY";
            }
            sqlite3DefaultRowEst(v47, v52);
            if ( !v13[43] )
              estimateIndexWidth(v47);
            recomputeColumnsNotIndexed(v47);
            v79 = a4;
            if ( a4 )
            {
              if ( *((unsigned __int16 *)v47 + 48) >= *((__int16 *)v21 + 27) )
              {
                v80 = 0;
                *((_DWORD *)v47 + 25) |= 0x20u;
                v81 = *((__int16 *)v21 + 27);
                while ( v80 < v81 )
                {
                  if ( v80 != *((__int16 *)v21 + 26)
                    && (sqlite3TableColumnToIndex(v47, (unsigned __int16)v80, 0) & 0x8000u) != 0LL )
                  {
                    *((_DWORD *)v47 + 25) = v82 & 0xFFFFFFDF;
                    break;
                  }
                  ++v80;
                }
              }
              v79 = a4;
            }
            if ( v21 == (const char **)v13[43] )
            {
              for ( j = v21[2]; ; j = (const char *)*((_QWORD *)j + 5) )
              {
                if ( !j )
                {
                  v79 = a4;
                  break;
                }
                v84 = *((unsigned __int16 *)j + 47);
                if ( (_WORD)v84 == *((_WORD *)v47 + 47) )
                {
                  v85 = 0;
                  if ( (_WORD)v84 )
                  {
                    v86 = v47[1];
                    v87 = *((_QWORD *)j + 1);
                    while ( *(_WORD *)(v87 + 2LL * v85) == v86[v85]
                         && !(unsigned int)sqlite3StrICmp(
                                             *(_QWORD *)(*((_QWORD *)j + 8) + 8LL * v85),
                                             *((_QWORD *)v47[8] + v85)) )
                    {
                      v86 = v47[1];
                      v85 = v88 + 1;
                      v87 = *((_QWORD *)j + 1);
                      if ( (int)v85 >= v84 )
                        goto LABEL_134;
                    }
                  }
                  else
                  {
LABEL_134:
                    if ( v85 == v84 )
                    {
                      v89 = *((_BYTE *)v47 + 98);
                      if ( j[98] != v89 )
                      {
                        if ( j[98] == 11 )
                          goto LABEL_141;
                        if ( v89 != 11 )
                          sqlite3ErrorMsg(v13, "conflicting ON CONFLICT clauses specified", 0);
                        if ( j[98] == 11 )
LABEL_141:
                          *((_BYTE *)j + 98) = *((_BYTE *)v47 + 98);
                      }
                      if ( a11 == 2 )
                        *((_DWORD *)j + 25) ^= ((unsigned __int8)*((_DWORD *)j + 25) ^ 2) & 3;
                      v15 = v101;
                      if ( *((_BYTE *)v13 + 300) >= 2u )
                      {
                        v47[5] = (void *)v13[44];
                        v13[44] = (__int64)v47;
                        v47 = 0;
                      }
                      goto LABEL_98;
                    }
                  }
                }
              }
            }
            if ( *((_BYTE *)v13 + 300) < 2u )
            {
              if ( *(_BYTE *)(v16 + 197) )
              {
                v90 = a4;
                if ( a4 )
                {
                  *((_DWORD *)v47 + 22) = *(_DWORD *)(v16 + 192);
                  if ( (unsigned int)sqlite3IndexHasDuplicateRootPage(v47, v78, 0) )
                  {
                    sqlite3ErrorMsg(v13, "invalid rootpage");
                    *((_DWORD *)v13 + 6) = sqlite3ReportError(11, 123747, "database corruption");
                    goto LABEL_97;
                  }
                }
                if ( sqlite3HashInsert((char *)v47[6] + 32, *v47, v47) )
                {
                  sqlite3OomFault(v16);
                  goto LABEL_97;
                }
                *(_DWORD *)(v16 + 44) |= 1u;
LABEL_169:
                if ( *(_BYTE *)(v16 + 197) || !v90 )
                {
                  v47[5] = (void *)v21[2];
                  v21[2] = (const char *)v47;
                }
                else
                {
                  if ( *((_BYTE *)v13 + 300) < 2u )
                    goto LABEL_97;
                  v13[44] = (__int64)v47;
                }
                v15 = v101;
LABEL_100:
                if ( v21 )
                {
LABEL_101:
                  for ( k = (__int64 *)(v21 + 2); ; k = (__int64 *)(v73 + 40) )
                  {
                    v73 = *k;
                    if ( !*k )
                      break;
                    if ( *(_BYTE *)(v73 + 98) == 5 )
                    {
                      while ( 1 )
                      {
                        v98 = *(_QWORD *)(v73 + 40);
                        if ( !v98 || *(_BYTE *)(v98 + 98) == 5 )
                          break;
                        *k = v98;
                        k = (__int64 *)(v98 + 40);
                        *(_QWORD *)(v73 + 40) = *(_QWORD *)(v98 + 40);
                        *(_QWORD *)(v98 + 40) = v73;
                      }
                      goto LABEL_180;
                    }
                  }
                }
                goto LABEL_180;
              }
              if ( *((char *)v21 + 48) >= 0 || v79 )
              {
                v91 = ++*((_DWORD *)v13 + 14);
                v116 = v91;
                Vdbe = sqlite3GetVdbe(v13);
                if ( !Vdbe )
                  goto LABEL_97;
                sqlite3BeginWriteOperation(v13, 1, (unsigned int)v17);
                *((_DWORD *)v47 + 22) = sqlite3VdbeAddOp3(Vdbe, 184, 0, 0, 0);
                sqlite3VdbeAddOp3(Vdbe, 147, v17, v91, 2);
                if ( a7 )
                {
                  v93 = (const char *)&qword_1800F3280;
                  v94 = *((_DWORD *)v13 + 70) + *((_DWORD *)v13 + 72) - *(_DWORD *)v107;
                  v95 = v94 - 1;
                  if ( *(_BYTE *)((int)v95 + *v107) != 59 )
                    v95 = v94;
                  if ( a6 )
                    v93 = " UNIQUE";
                  v96 = sqlite3MPrintf(v16, "CREATE%s INDEX %.*s", v93, v95, *v107);
                }
                else
                {
                  v96 = 0;
                }
                sqlite3NestedParse(
                  v13,
                  "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
                  *(_QWORD *)(32LL * v17 + *(_QWORD *)(v16 + 32)),
                  *v47,
                  *v21,
                  v116,
                  v96);
                sqlite3DbFree(v16, v96);
                if ( a4 )
                {
                  sqlite3RefillIndex(v13, v47, v116);
                  sqlite3VdbeAddOp3(v13[2], 100, v17, 1, **(_DWORD **)(32LL * v17 + *(_QWORD *)(*v13 + 32) + 24) + 1);
                  v97 = sqlite3MPrintf(v16, "name='%q' AND type='index'", *v47);
                  sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v17, v97, 0);
                  sqlite3VdbeAddOp3(Vdbe, 166, 0, 1, 0);
                }
                *(_DWORD *)(sqlite3VdbeGetOp(Vdbe, *((unsigned int *)v47 + 22)) + 8) = *(_DWORD *)(Vdbe + 144);
              }
            }
            v90 = a4;
            goto LABEL_169;
          }
          sqlite3StringToId(*v54, 0);
          sqlite3ResolveSelfReference((_DWORD)v13, (_DWORD)v21, 32, *v57, v58);
          if ( *((_DWORD *)v13 + 12) )
            goto LABEL_97;
          v59 = sqlite3ExprSkipCollate(*(_QWORD *)v105);
          if ( *(_BYTE *)v59 == 0xA7 )
          {
            v62 = *(__int16 *)(v59 + 48);
            if ( (int)v62 >= 0 )
            {
              if ( (v21[1][24 * v62 + 8] & 0xF) == 0 )
                *((_DWORD *)v47 + 25) &= ~8u;
              if ( (v21[1][24 * v62 + 18] & 0x20) != 0 )
                *((_DWORD *)v47 + 25) |= 0xC00u;
            }
            else
            {
              LODWORD(v62) = *((__int16 *)v21 + 26);
            }
            v61 = v55;
            *((_WORD *)v47[1] + v55) = v62;
          }
          else
          {
            if ( v21 == (const char **)v13[43] )
            {
              sqlite3ErrorMsg(v13, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
LABEL_97:
              v15 = v101;
              goto LABEL_98;
            }
            if ( !v47[10] )
            {
              v47[10] = v104;
              v104 = 0;
            }
            v61 = v55;
            LODWORD(v62) = -2;
            *((_WORD *)v47[1] + v55) = -2;
            *((_DWORD *)v47 + 25) = *((_DWORD *)v47 + 25) & 0xFFFFF7F7 | 0x800;
          }
          if ( **(_BYTE **)v60 == 113 )
          {
            v63 = sqlite3Strlen30(*(_QWORD *)(*(_QWORD *)v60 + 8LL), v61, v60);
            v64 = v108;
            v65 = v63 + 1;
            memcpy_0(v108, v66, v65);
            v67 = &v64[v65];
            v55 = v103;
            v108 = (char *)v67;
          }
          else
          {
            if ( (int)v62 < 0 )
              goto LABEL_90;
            v64 = (const char *)sqlite3ColumnColl(&v21[1][24 * (int)v62]);
          }
          if ( !v64 )
LABEL_90:
            v64 = "BINARY";
          if ( !*(_BYTE *)(v16 + 197) && !sqlite3LocateCollSeq(v13, v64) )
            goto LABEL_97;
          v68 = (char *)v105;
          v69 = v55;
          *((_QWORD *)v47[8] + v55) = v64;
          v70 = v68[16];
          if ( v100 < 4u )
            v70 = 0;
          v71 = v47[7];
          v54 = v68 + 32;
          ++v55;
          v105 = v54;
          v71[v69] = v70;
          v52 = 0;
        }
      }
      if ( !*(_BYTE *)(v16 + 197) && sqlite3FindTable(v16, v15, *(_QWORD *)(v26 + v25)) )
      {
        v22 = v15;
        v23 = "there is already a table named %s";
        goto LABEL_25;
      }
      if ( sqlite3FindIndex(v16, v15, *(_QWORD *)(v26 + v25)) )
      {
        if ( a10 )
        {
          sqlite3CodeVerifySchema(v13, (unsigned int)v17);
          sqlite3ForceNotReadOnly(v13);
        }
        else
        {
          sqlite3ErrorMsg(v13, "index %s already exists", v15);
        }
        goto LABEL_100;
      }
    }
    else
    {
      v28 = v21[2];
      v29 = 1;
      while ( v28 )
      {
        v28 = (const char *)*((_QWORD *)v28 + 5);
        ++v29;
      }
      v15 = (_BYTE *)sqlite3MPrintf(v16, "sqlite_autoindex_%s_%d", *v21, v29);
      v101 = v15;
      if ( !v15 )
        goto LABEL_100;
      if ( *((_BYTE *)v13 + 300) )
        ++v15[7];
    }
    if ( *((_BYTE *)v13 + 300) < 2u )
    {
      v30 = *(_QWORD *)(v26 + v25);
      v31 = "sqlite_temp_master";
      if ( v17 != 1 )
        v31 = "sqlite_master";
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, 18, (_DWORD)v31, 0, v30) )
        goto LABEL_100;
      v32 = 3;
      if ( v17 != 1 )
        v32 = 1;
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, v32, (_DWORD)v15, (unsigned int)*v21, v30) )
        goto LABEL_100;
    }
    goto LABEL_54;
  }
LABEL_180:
  sqlite3ExprDelete(v16, a8);
  sqlite3ExprListDelete(v16, v104);
  sqlite3SrcListDelete(v16, a4);
  return sqlite3DbFree(v16, v15);
}

```

## disassembly

```asm
0x180070c5c  mov     rax, rsp
0x180070c5f  mov     [rax+10h], rbx
0x180070c63  mov     [rax+20h], r9
0x180070c67  mov     [rax+8], rcx
0x180070c6b  push    rbp
0x180070c6c  push    rsi
0x180070c6d  push    rdi
0x180070c6e  push    r12
0x180070c70  push    r13
0x180070c72  push    r14
0x180070c74  push    r15
0x180070c76  lea     rbp, [rax-3Fh]
0x180070c7a  sub     rsp, 100h
0x180070c81  xor     r14d, r14d
0x180070c84  mov     rbx, r8
0x180070c87  mov     rsi, rdx
0x180070c8a  mov     rdi, rcx
0x180070c8d  xor     edx, edx; Val
0x180070c8f  lea     rcx, [rbp+37h+var_90]; void *
0x180070c93  mov     r12, r9
0x180070c96  mov     r13d, r14d
0x180070c99  lea     r8d, [r14+60h]; Size
0x180070c9d  call    memset_0
0x180070ca2  mov     r15, [rdi]
0x180070ca5  mov     [rbp+37h+var_98], r15
0x180070ca9  mov     [rsp+130h+var_C0], r14
0x180070cae  mov     [rsp+130h+var_D0], r14
0x180070cb3  cmp     [rdi+30h], r14d
0x180070cb7  jnz     loc_180071883
0x180070cbd  cmp     byte ptr [rdi+12Ch], 1
0x180070cc4  jnz     short loc_180070CD3
0x180070cc6  cmp     [rbp+37h+arg_50], 2
0x180070ccd  jnz     loc_180071883
0x180070cd3  mov     rcx, rdi
0x180070cd6  call    sqlite3ReadSchema
0x180070cdb  test    eax, eax
0x180070cdd  jnz     loc_180071883
0x180070ce3  mov     rax, [rbp+37h+arg_20]
0x180070ce7  mov     rcx, rdi
0x180070cea  mov     rdx, rax
0x180070ced  mov     [rsp+130h+var_D8], rax
0x180070cf2  call    sqlite3HasExplicitNulls
0x180070cf7  test    eax, eax
0x180070cf9  jnz     loc_18007188C
0x180070cff  mov     [rsp+130h+var_C8], r14
0x180070d04  test    r12, r12
0x180070d07  jz      loc_180070DF8
0x180070d0d  lea     r9, [rsp+130h+var_C0]
0x180070d12  mov     r8, rbx
0x180070d15  mov     rdx, rsi
0x180070d18  mov     rcx, rdi
0x180070d1b  call    sqlite3TwoPartName
0x180070d20  mov     r12d, eax
0x180070d23  test    eax, eax
0x180070d25  js      loc_18007188C
0x180070d2b  cmp     [r15+0C5h], r14b
0x180070d32  jnz     short loc_180070D65
0x180070d34  mov     rdx, [rbp+37h+arg_18]
0x180070d38  mov     rcx, rdi
0x180070d3b  call    sqlite3SrcListLookup
0x180070d40  mov     rcx, rax
0x180070d43  cmp     [rbx+8], r14d
0x180070d47  jnz     short loc_180070D65
0x180070d49  mov     esi, 1
0x180070d4e  test    rax, rax
0x180070d51  jz      short loc_180070D6A
0x180070d53  mov     rax, [r15+20h]
0x180070d57  mov     rax, [rax+38h]
0x180070d5b  cmp     [rcx+60h], rax
0x180070d5f  cmovz   r12d, esi
0x180070d63  jmp     short loc_180070D6A
0x180070d65  mov     esi, 1
0x180070d6a  mov     rax, [rsp+130h+var_C0]
0x180070d6f  lea     r9, aIndex; "index"
0x180070d76  mov     r8d, r12d
0x180070d79  mov     qword ptr [rsp+130h+var_110], rax
0x180070d7e  mov     rdx, rdi
0x180070d81  lea     rcx, [rbp+37h+var_90]
0x180070d85  call    sqlite3FixInit
0x180070d8a  mov     rbx, [rbp+37h+arg_18]
0x180070d8e  lea     rcx, [rbp+37h+var_90]
0x180070d92  mov     rdx, rbx
0x180070d95  call    sqlite3FixSrcList
0x180070d9a  lea     r8, [rbx+8]
0x180070d9e  xor     edx, edx
0x180070da0  mov     rcx, rdi
0x180070da3  call    sqlite3LocateTableItem
0x180070da8  mov     [rbp+37h+var_A8], rax
0x180070dac  mov     r14, rax
0x180070daf  test    rax, rax
0x180070db2  jz      loc_18007138B
0x180070db8  cmp     r12d, esi
0x180070dbb  jnz     short loc_180070DE2
0x180070dbd  mov     rcx, [r15+20h]
0x180070dc1  mov     rax, [rax+60h]
0x180070dc5  cmp     [rcx+38h], rax
0x180070dc9  jz      short loc_180070DE2
0x180070dcb  mov     r8, [r14]
0x180070dce  lea     rdx, aCannotCreateAT; "cannot create a TEMP index on non-TEMP "...
0x180070dd5  mov     rcx, rdi
0x180070dd8  call    sqlite3ErrorMsg
0x180070ddd  jmp     loc_180071394
0x180070de2  test    byte ptr [r14+30h], 80h
0x180070de7  jz      short loc_180070E1F
0x180070de9  mov     rcx, r14
0x180070dec  call    sqlite3PrimaryKeyIndex
0x180070df1  mov     [rsp+130h+var_C8], rax
0x180070df6  jmp     short loc_180070E1F
0x180070df8  mov     r14, [rdi+158h]
0x180070dff  mov     [rbp+37h+var_A8], r14
0x180070e03  test    r14, r14
0x180070e06  jz      loc_18007188C
0x180070e0c  mov     rdx, [r14+60h]
0x180070e10  mov     rcx, r15
0x180070e13  call    sqlite3SchemaToIndex
0x180070e18  mov     rbx, [rbp+37h+arg_18]
0x180070e1c  mov     r12d, eax
0x180070e1f  mov     rcx, [r14]
0x180070e22  lea     rdx, aSqlite_0; "sqlite_"
0x180070e29  mov     r8d, 7
0x180070e2f  call    sqlite3_strnicmp
0x180070e34  xor     ecx, ecx
0x180070e36  test    eax, eax
0x180070e38  jnz     short loc_180070E5F
0x180070e3a  cmp     [r15+0C5h], cl
0x180070e41  jnz     short loc_180070E5F
0x180070e43  test    rbx, rbx
0x180070e46  jz      short loc_180070E5F
0x180070e48  mov     r8, [r14]
0x180070e4b  lea     rdx, aTableSMayNotBe_0; "table %s may not be indexed"
0x180070e52  mov     rcx, rdi
0x180070e55  call    sqlite3ErrorMsg
0x180070e5a  jmp     loc_18007138B
0x180070e5f  mov     al, [r14+3Fh]
0x180070e63  cmp     al, 2
0x180070e65  jnz     short loc_180070E7B
0x180070e67  lea     rdx, aViewsMayNotBeI; "views may not be indexed"
0x180070e6e  mov     rcx, rdi
0x180070e71  call    sqlite3ErrorMsg
0x180070e76  jmp     loc_18007138B
0x180070e7b  mov     edx, 1
0x180070e80  cmp     al, dl
0x180070e82  jnz     short loc_180070E8D
0x180070e84  lea     rdx, aVirtualTablesM; "virtual tables may not be indexed"
0x180070e8b  jmp     short loc_180070E6E
0x180070e8d  mov     rax, [rsp+130h+var_C0]
0x180070e92  mov     rsi, [r15+20h]
0x180070e96  movsxd  rbx, r12d
0x180070e99  shl     rbx, 5
0x180070e9d  mov     [rbp+37h+var_A0], rsi
0x180070ea1  test    rax, rax
0x180070ea4  jz      loc_180070F60
0x180070eaa  mov     rdx, rax
0x180070ead  mov     rcx, r15
0x180070eb0  call    sqlite3NameFromToken
0x180070eb5  mov     [rsp+130h+var_E8], rax
0x180070eba  mov     r13, rax
0x180070ebd  test    rax, rax
0x180070ec0  jz      loc_18007138B
0x180070ec6  mov     r9, [r14]
0x180070ec9  lea     r8, aIndex; "index"
0x180070ed0  mov     rdx, rax
0x180070ed3  mov     rcx, rdi
0x180070ed6  call    sqlite3CheckObjectName
0x180070edb  test    eax, eax
0x180070edd  jnz     loc_18007138B
0x180070ee3  cmp     byte ptr [rdi+12Ch], 2
0x180070eea  jnb     loc_18007100C
0x180070ef0  cmp     [r15+0C5h], al
0x180070ef7  jnz     short loc_180070F1C
0x180070ef9  mov     r8, [rbx+rsi]
0x180070efd  mov     rdx, r13
0x180070f00  mov     rcx, r15
0x180070f03  call    sqlite3FindTable
0x180070f08  test    rax, rax
0x180070f0b  jz      short loc_180070F1C
0x180070f0d  mov     r8, r13
0x180070f10  lea     rdx, aThereIsAlready; "there is already a table named %s"
0x180070f17  jmp     loc_180070E52
0x180070f1c  mov     r8, [rbx+rsi]
0x180070f20  mov     rdx, r13
0x180070f23  mov     rcx, r15
0x180070f26  call    sqlite3FindIndex
0x180070f2b  test    rax, rax
0x180070f2e  jz      short loc_180070FA6
0x180070f30  cmp     [rbp+37h+arg_48], 0
0x180070f37  mov     rcx, rdi
0x180070f3a  jnz     short loc_180070F4B
0x180070f3c  mov     r8, r13
0x180070f3f  lea     rdx, aIndexSAlreadyE; "index %s already exists"
0x180070f46  jmp     loc_180070E55
0x180070f4b  mov     edx, r12d
0x180070f4e  call    sqlite3CodeVerifySchema
0x180070f53  mov     rcx, rdi
0x180070f56  call    sqlite3ForceNotReadOnly
0x180070f5b  jmp     loc_18007138B
0x180070f60  mov     rax, [r14+10h]
0x180070f64  mov     r9d, edx
0x180070f67  jmp     short loc_180070F70
0x180070f69  mov     rax, [rax+28h]
0x180070f6d  add     r9d, edx
0x180070f70  test    rax, rax
0x180070f73  jnz     short loc_180070F69
0x180070f75  mov     r8, [r14]
0x180070f78  lea     rdx, aSqliteAutoinde; "sqlite_autoindex_%s_%d"
0x180070f7f  mov     rcx, r15
0x180070f82  call    sqlite3MPrintf
0x180070f87  mov     r13, rax
0x180070f8a  mov     [rsp+130h+var_E8], rax
0x180070f8f  xor     eax, eax
0x180070f91  test    r13, r13
0x180070f94  jz      loc_18007138B
0x180070f9a  cmp     [rdi+12Ch], al
0x180070fa0  jz      short loc_180070FA6
0x180070fa2  inc     byte ptr [r13+7]
0x180070fa6  cmp     byte ptr [rdi+12Ch], 2
0x180070fad  jnb     short loc_18007100C
0x180070faf  mov     rsi, [rbx+rsi]
0x180070fb3  lea     rax, aSqliteMaster; "sqlite_master"
0x180070fba  cmp     r12d, 1
0x180070fbe  mov     qword ptr [rsp+130h+var_110], rsi
0x180070fc3  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180070fca  mov     rcx, rdi
0x180070fcd  cmovnz  r8, rax
0x180070fd1  xor     r9d, r9d
0x180070fd4  lea     edx, [r9+12h]
0x180070fd8  call    sqlite3AuthCheck
0x180070fdd  test    eax, eax
0x180070fdf  jnz     loc_18007138B
0x180070fe5  mov     r9, [r14]
0x180070fe8  lea     edx, [rax+3]
0x180070feb  lea     eax, [rdx-2]
0x180070fee  mov     qword ptr [rsp+130h+var_110], rsi
0x180070ff3  cmp     r12d, eax
0x180070ff6  mov     r8, r13
0x180070ff9  mov     rcx, rdi
0x180070ffc  cmovnz  edx, eax
0x180070fff  call    sqlite3AuthCheck
0x180071004  test    eax, eax
0x180071006  jnz     loc_18007138B
0x18007100c  mov     rsi, [rbp+37h+arg_20]
0x180071010  xor     eax, eax
0x180071012  mov     r8d, 8
0x180071018  test    rsi, rsi
0x18007101b  jnz     short loc_18007108C
0x18007101d  mov     rcx, [r14+8]
0x180071021  mov     [rbp+37h+var_AC], eax
0x180071024  movsx   rax, word ptr [r14+36h]
0x180071029  lea     rdx, [rax+rax*2]
0x18007102d  or      [rcx+rdx*8-6], r8w
0x180071033  mov     rcx, [rcx+rdx*8-18h]
0x180071038  mov     [rsp+130h+var_B8], rcx
0x18007103d  call    sqlite3Strlen30
0x180071042  xor     r9d, r9d
0x180071045  mov     [rbp+37h+var_B0], eax
0x180071048  lea     r8, [rsp+130h+var_B8]
0x18007104d  mov     rcx, r15
0x180071050  lea     edx, [rsi+3Bh]
0x180071053  call    sqlite3ExprAlloc
0x180071058  mov     r8, rax
0x18007105b  xor     edx, edx
0x18007105d  mov     rcx, rdi
0x180071060  call    sqlite3ExprListAppend
0x180071065  mov     [rsp+130h+var_D8], rax
0x18007106a  mov     rsi, rax
0x18007106d  test    rax, rax
0x180071070  jz      loc_18007138B
0x180071076  mov     edx, [rbp+37h+arg_40]
0x18007107c  or      r8d, 0FFFFFFFFh
0x180071080  mov     rcx, rax
0x180071083  call    sqlite3ExprListSetSortOrder
0x180071088  xor     eax, eax
0x18007108a  jmp     short loc_1800710A9
0x18007108c  lea     r8, aIndex; "index"
0x180071093  mov     rdx, rsi
0x180071096  mov     rcx, rdi
0x180071099  call    sqlite3ExprListCheckLength
0x18007109e  xor     eax, eax
0x1800710a0  cmp     [rdi+30h], eax
0x1800710a3  jnz     loc_18007138B
0x1800710a9  mov     r8d, eax
0x1800710ac  mov     edx, eax
0x1800710ae  cmp     [rsi], eax
0x1800710b0  jle     short loc_1800710D7
0x1800710b2  mov     eax, edx
0x1800710b4  shl     rax, 5
0x1800710b8  mov     rcx, [rax+rsi+8]
0x1800710bd  cmp     byte ptr [rcx], 71h ; 'q'
0x1800710c0  jnz     short loc_1800710D1
0x1800710c2  mov     rcx, [rcx+8]
0x1800710c6  call    sqlite3Strlen30
0x1800710cb  inc     r8d
0x1800710ce  add     r8d, eax
0x1800710d1  inc     edx
0x1800710d3  cmp     edx, [rsi]
0x1800710d5  jl      short loc_1800710B2
0x1800710d7  mov     rcx, r13
0x1800710da  call    sqlite3Strlen30
0x1800710df  mov     rdx, [rsp+130h+var_C8]
0x1800710e4  mov     dword ptr [rsp+130h+var_E0], eax
  ... truncated ...
```
