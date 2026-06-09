# sqlite3CreateIndex

- ea: `0x18001d1c8`
- end: `0x18001dff2`
- name: `sqlite3CreateIndex`
- size: `3626`
- prototype: ``
- caller_count: `3`
- callee_count: `52`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000213c`
- `0x18001c528`
- `0x18001f92c`

## callees

- `0x18000506c`
- `0x180007190`
- `0x18000968c`
- `0x180009e04`
- `0x180009ef0`
- `0x180009fe0`
- `0x18000a180`
- `0x18000a6bc`
- `0x18000a710`
- `0x18000a754`
- `0x180011bcc`
- `0x180014d90`
- `0x180015118`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001bb70`
- `0x18001bc5c`
- `0x18001c800`
- `0x18001cb40`
- `0x18001d1c8`
- `0x18001e2a4`
- `0x18001e2c4`
- `0x18001e2e8`
- `0x18001e820`
- `0x18001eb90`
- `0x18001f0f0`
- `0x18001f19c`
- `0x18001f3b4`
- `0x18001f418`
- `0x18001f530`
- `0x18001f6e4`
- `0x18001f848`
- `0x18001fd38`
- `0x18002619c`
- `0x18003bc90`
- `0x18003c64c`
- `0x180040e00`
- `0x180041d10`
- `0x18004a9b8`
- `0x18004c620`
- `0x18004e908`
- `0x180058730`
- `0x1800589fc`
- `0x18005d2d4`
- `0x18005f5fc`
- `0x180060b38`
- `0x180061d60`
- `0x180062a94`
- `0x18006dc30`
- `0x180072020`

## string_xrefs

- `0x18001d32e`: `sqlite_temp_master`
- `0x18001dba0`: `cannot create a TEMP index on non-TEMP table "%s"`
- `0x18001dbaf`: `there is already a table named %s`
- `0x18001dbbe`: `index %s already exists`
- `0x18001df00`: `CREATE%s INDEX %.*s`

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
  _QWORD *v13; // rdi
  _BYTE *v14; // rsi
  __int64 v16; // r14
  _DWORD *v17; // r13
  __int64 v18; // r15
  int v19; // eax
  __int64 v20; // r10
  __int64 v21; // rbx
  __int64 v22; // r11
  int v23; // r12d
  char v24; // al
  __int64 v25; // rbx
  __int64 v26; // rax
  int v27; // r9d
  __int64 v28; // rax
  const char *v29; // r8
  __int64 v30; // rsi
  int v31; // edx
  int i; // edx
  __int64 v33; // rcx
  int v34; // eax
  int v35; // r8d
  __int64 v36; // rdx
  void **v37; // rax
  void **v38; // rsi
  char *v39; // rcx
  size_t v40; // r8
  int v41; // eax
  unsigned int v42; // ecx
  int *v43; // r10
  bool v44; // cf
  _QWORD *v45; // r8
  int *v46; // rbx
  int v47; // eax
  int v48; // r13d
  _QWORD *v49; // r8
  __int64 v50; // r10
  __int64 v51; // rax
  __int64 v52; // r8
  __int64 v53; // rcx
  const char *v54; // r13
  char *v55; // r8
  char v56; // cl
  __int64 v57; // rdx
  __int64 v58; // rax
  __int64 j; // rbx
  __int64 v60; // rax
  __int64 v61; // r10
  __int64 *k; // r15
  __int64 v63; // rcx
  __int64 v64; // rax
  _QWORD *v65; // rcx
  _BYTE *v66; // r9
  const char *v67; // r8
  int v68; // edx
  const char *v69; // rdx
  _BYTE *v70; // r8
  __int64 v71; // rax
  int v73; // eax
  size_t v74; // rbx
  const void *v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rcx
  __int64 v78; // rax
  char v79; // cl
  __int64 CollSeq; // rax
  unsigned int v81; // ebx
  __int64 v82; // r9
  __int64 Vdbe; // r13
  __int64 v84; // rbx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 TableItem; // rax
  __int64 v88; // rcx
  int v89; // r14d
  int v90; // ebx
  __int64 v91; // rdi
  __int64 v92; // r8
  int v93; // ebx
  int v94; // r13d
  int v95; // r11d
  int v96; // r13d
  unsigned int v97; // r11d
  _WORD *v98; // rax
  __int64 v99; // rcx
  int v100; // r11d
  char v101; // al
  const char *v102; // r8
  unsigned int v103; // edx
  __int64 v104; // r9
  __int64 v105; // rax
  __int64 v106; // [rsp+28h] [rbp-D9h]
  __int64 v107; // [rsp+48h] [rbp-B9h]
  int v108; // [rsp+48h] [rbp-B9h]
  int *appended; // [rsp+50h] [rbp-B1h]
  _BYTE *Src; // [rsp+58h] [rbp-A9h]
  void *v111; // [rsp+60h] [rbp-A1h] BYREF
  __int64 v112; // [rsp+68h] [rbp-99h]
  _QWORD *v113; // [rsp+70h] [rbp-91h] BYREF
  void *v114; // [rsp+78h] [rbp-89h] BYREF
  int v115; // [rsp+80h] [rbp-81h]
  int v116; // [rsp+84h] [rbp-7Dh]
  __int64 v117; // [rsp+88h] [rbp-79h]
  __int64 v118; // [rsp+90h] [rbp-71h]
  __int64 v119; // [rsp+98h] [rbp-69h]
  _BYTE v120[144]; // [rsp+A8h] [rbp-59h] BYREF
  unsigned int v122; // [rsp+148h] [rbp+47h]
  int v124; // [rsp+168h] [rbp+67h]
  unsigned __int8 v125; // [rsp+168h] [rbp+67h]

  v13 = a1;
  v14 = 0;
  memset_0(v120, 0, 0x60u);
  v16 = *v13;
  v119 = *v13;
  v113 = 0;
  v111 = 0;
  if ( *((_DWORD *)v13 + 12) || *((_BYTE *)v13 + 308) == 1 && a11 != 2 || (unsigned int)sqlite3ReadSchema(v13) )
  {
    v17 = a5;
    goto LABEL_102;
  }
  v17 = a5;
  appended = a5;
  if ( (unsigned int)sqlite3HasExplicitNulls(v13, a5) )
    goto LABEL_102;
  v112 = 0;
  if ( a4 )
  {
    v23 = sqlite3TwoPartName(v13, a2, a3, &v113);
    if ( v23 < 0 )
      goto LABEL_102;
    if ( !*(_BYTE *)(v16 + 197) )
    {
      v88 = sqlite3SrcListLookup(v13, a4);
      if ( !*(_DWORD *)(a3 + 8) && v88 && *(_QWORD *)(v88 + 96) == *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) )
        v23 = 1;
    }
    sqlite3FixInit((unsigned int)v120, (_DWORD)v13, v23, (unsigned int)"index", (__int64)v113);
    v21 = a4;
    sqlite3FixSrcList(v120, a4);
    TableItem = sqlite3LocateTableItem(v13, 0, a4 + 8);
    v20 = 0;
    v117 = TableItem;
    v18 = TableItem;
    if ( !TableItem )
      goto LABEL_102;
    v22 = 1;
    if ( v23 == 1 && *(_QWORD *)(*(_QWORD *)(v16 + 32) + 56LL) != *(_QWORD *)(TableItem + 96) )
    {
      v69 = "cannot create a TEMP index on non-TEMP table \"%s\"";
      goto LABEL_99;
    }
    if ( *(char *)(TableItem + 48) < 0 )
      v112 = sqlite3PrimaryKeyIndex(TableItem);
  }
  else
  {
    v18 = v13[44];
    v117 = v18;
    if ( !v18 )
      goto LABEL_102;
    v19 = sqlite3SchemaToIndex(v16, *(_QWORD *)(v18 + 96));
    v21 = a4;
    v22 = (unsigned int)(v20 + 1);
    v23 = v19;
  }
  if ( *(_QWORD *)v18 != v20 )
  {
    v66 = *(_BYTE **)v18;
    v67 = "sqlite_";
    v68 = 7;
    while ( 1 )
    {
      v68 -= v22;
      if ( *v66 == (_BYTE)v20 )
        break;
      v17 = a5;
      if ( *((_BYTE *)qword_1800B4ED0 + (unsigned __int8)*v66) != *((_BYTE *)qword_1800B4ED0 + *(unsigned __int8 *)v67) )
        break;
      v66 += v22;
      v67 += v22;
      if ( v68 <= 0 )
      {
        v68 -= v22;
        break;
      }
    }
    if ( (v68 < 0
       || *((unsigned __int8 *)qword_1800B4ED0 + (unsigned __int8)*v66) == *((unsigned __int8 *)qword_1800B4ED0
                                                                           + *(unsigned __int8 *)v67))
      && *(_BYTE *)(v16 + 197) == (_BYTE)v20
      && v21 )
    {
      v69 = "table %s may not be indexed";
LABEL_99:
      v70 = *(_BYTE **)v18;
LABEL_142:
      v65 = v13;
      goto LABEL_144;
    }
  }
  v24 = *(_BYTE *)(v18 + 63);
  if ( v24 == 2 )
  {
    sqlite3ErrorMsg(v13, "views may not be indexed");
    goto LABEL_78;
  }
  if ( v24 == (_BYTE)v22 )
  {
    sqlite3ErrorMsg(v13, "virtual tables may not be indexed");
    goto LABEL_78;
  }
  v25 = 32LL * v23;
  v107 = *(_QWORD *)(v16 + 32);
  v118 = v25;
  if ( v113 )
  {
    v64 = sqlite3NameFromToken(v16, v113);
    Src = (_BYTE *)v64;
    v14 = (_BYTE *)v64;
    if ( !v64 || (unsigned int)sqlite3CheckObjectName(v13, v64, "index", *(_QWORD *)v18) )
      goto LABEL_78;
    if ( *((_BYTE *)v13 + 308) >= 2u )
      goto LABEL_24;
    if ( !*(_BYTE *)(v16 + 197) && sqlite3FindTable(v16, v14, *(_QWORD *)(v25 + v107)) )
    {
      v70 = v14;
      v69 = "there is already a table named %s";
      goto LABEL_142;
    }
    if ( sqlite3FindIndex(v16, v14, *(_QWORD *)(v25 + v107)) )
    {
      v65 = v13;
      if ( a10 )
      {
        sqlite3CodeVerifySchema(v13, (unsigned int)v23);
        sqlite3ForceNotReadOnly(v13);
        goto LABEL_78;
      }
      v70 = v14;
      v69 = "index %s already exists";
LABEL_144:
      sqlite3ErrorMsg(v65, v69, v70);
      goto LABEL_78;
    }
  }
  else
  {
    v26 = *(_QWORD *)(v18 + 16);
    v27 = v22;
    while ( v26 )
    {
      v26 = *(_QWORD *)(v26 + 40);
      v27 += v22;
    }
    v28 = sqlite3MPrintf(v16, "sqlite_autoindex_%s_%d", *(const char **)v18, v27);
    Src = (_BYTE *)v28;
    v14 = (_BYTE *)v28;
    if ( !v28 )
      goto LABEL_78;
    if ( *((_BYTE *)v13 + 308) )
      ++*(_BYTE *)(v28 + 7);
  }
  if ( *((_BYTE *)v13 + 308) >= 2u )
    goto LABEL_24;
  v29 = "sqlite_temp_master";
  v30 = *(_QWORD *)(v25 + v107);
  if ( v23 != 1 )
    v29 = "sqlite_master";
  if ( (unsigned int)sqlite3AuthCheck((_DWORD)v13, 18, (_DWORD)v29, 0, *(_QWORD *)(v25 + v107)) )
    goto LABEL_77;
  v31 = 3;
  v106 = v30;
  v14 = Src;
  if ( v23 != 1 )
    v31 = 1;
  if ( !(unsigned int)sqlite3AuthCheck((_DWORD)v13, v31, (_DWORD)Src, *(_QWORD *)v18, v106) )
  {
LABEL_24:
    if ( v17 )
    {
      if ( *v17 > *(_DWORD *)(*v13 + 144LL) )
        sqlite3ErrorMsg(v13, "too many columns in %s", "index");
      if ( *((_DWORD *)v13 + 12) )
        goto LABEL_78;
    }
    else
    {
      v76 = *(__int16 *)(v18 + 54);
      v77 = *(_QWORD *)(v18 + 8);
      v116 = 0;
      *(_WORD *)(v77 + 24 * v76 - 6) |= 8u;
      v114 = *(void **)(v77 + 24 * v76 - 24);
      v115 = sqlite3Strlen30(v114);
      v78 = sqlite3ExprAlloc(v16, 59, &v114);
      appended = (int *)sqlite3ExprListAppendNew(*v13, v78);
      v17 = appended;
      if ( !appended )
        goto LABEL_78;
      v79 = 0;
      if ( a9 != -1 )
        v79 = a9;
      LOBYTE(appended[8 * *appended - 2]) = v79;
    }
    for ( i = 0; i < *v17; ++i )
    {
      v33 = *(_QWORD *)&v17[8 * i + 2];
      if ( *(_BYTE *)v33 == 113 )
        sqlite3Strlen30(*(_QWORD *)(v33 + 8));
    }
    v34 = sqlite3Strlen30(v14);
    v124 = v34;
    if ( v112 )
      v36 = *(unsigned __int16 *)(v112 + 94);
    else
      v36 = 1;
    LOWORD(v36) = *(_WORD *)v17 + v36;
    v37 = (void **)sqlite3AllocateIndexObject(v16, v36, (unsigned int)(v34 + 1 + v35), &v111);
    v38 = v37;
    if ( *(_BYTE *)(v16 + 103) )
    {
LABEL_75:
      if ( v38 )
        sqlite3FreeIndex(v16, v38);
      goto LABEL_77;
    }
    v39 = (char *)v111;
    *v37 = v111;
    v40 = v124 + 1;
    v114 = &v39[v40];
    memcpy_0(v39, Src, v40);
    *((_BYTE *)v38 + 98) = a6;
    v41 = *((_DWORD *)v38 + 25);
    v38[3] = (void *)v18;
    v42 = v41 & 0xFFFFFFF7 | (a6 != 0 ? 8 : 0);
    LODWORD(v43) = 0;
    *((_DWORD *)v38 + 25) = v42 ^ ((unsigned __int8)v42 ^ a11) & 3;
    v38[6] = *(void **)(v25 + *(_QWORD *)(v16 + 32) + 24);
    *((_WORD *)v38 + 47) = *(_WORD *)v17;
    if ( a8 )
    {
      sqlite3ResolveSelfReference((_DWORD)v13, v18, 2, (_DWORD)a8, 0);
      LODWORD(v43) = 0;
      v38[9] = a8;
      a8 = 0;
    }
    v44 = *((_BYTE *)v13 + 308) < 2u;
    v45 = v17 + 2;
    v111 = v17 + 2;
    v125 = *(_BYTE *)(*(_QWORD *)(v118 + v107 + 24) + 112LL);
    if ( v44 )
    {
      v46 = appended;
    }
    else
    {
      v46 = 0;
      v38[10] = v17;
      appended = 0;
    }
    v47 = 0;
    while ( 1 )
    {
      v48 = *((unsigned __int16 *)v38 + 47);
      v108 = v47;
      if ( v47 >= v48 )
      {
        if ( v112 )
        {
          if ( (unsigned __int16)v43 < *(_WORD *)(v112 + 94) )
          {
            v89 = v47;
            v90 = (int)v43;
            v91 = v112;
            do
            {
              if ( (unsigned int)isDupColumn(v38, (unsigned __int16)v48, v91, (unsigned int)v90) )
              {
                --*((_WORD *)v38 + 48);
              }
              else
              {
                v92 = v89++;
                *((_WORD *)v38[1] + v92) = *(_WORD *)(*(_QWORD *)(v91 + 8) + 2LL * v90);
                *((_QWORD *)v38[8] + v92) = *(_QWORD *)(*(_QWORD *)(v91 + 64) + 8LL * v90);
                *((_BYTE *)v38[7] + v92) = *(_BYTE *)(v90 + *(_QWORD *)(v91 + 56));
                LOWORD(v48) = *((_WORD *)v38 + 47);
              }
              ++v90;
            }
            while ( v90 < *(unsigned __int16 *)(v91 + 94) );
            v13 = a1;
            v16 = v119;
            v18 = v117;
          }
        }
        else
        {
          *((_WORD *)v38[1] + v47) = -1;
          *((_QWORD *)v38[8] + v47) = "BINARY";
        }
        sqlite3DefaultRowEst(v38);
        if ( !v13[44] )
          estimateIndexWidth(v38);
        recomputeColumnsNotIndexed(v38);
        v58 = a4;
        if ( a4 )
        {
          if ( *((unsigned __int16 *)v38 + 48) >= *(__int16 *)(v18 + 54) )
          {
            v93 = 0;
            *((_DWORD *)v38 + 25) |= 0x20u;
            v94 = *(__int16 *)(v18 + 54);
            while ( v93 < v94 )
            {
              if ( v93 != *(__int16 *)(v18 + 52) && (sqlite3TableColumnToIndex(v38) & 0x8000u) != 0LL )
              {
                *((_DWORD *)v38 + 25) = v95 & 0xFFFFFFDF;
                break;
              }
              ++v93;
            }
          }
          v58 = a4;
        }
        if ( v18 == v13[44] )
        {
          for ( j = *(_QWORD *)(v18 + 16); ; j = *(_QWORD *)(j + 40) )
          {
            if ( !j )
            {
              v58 = a4;
              break;
            }
            v96 = *(unsigned __int16 *)(j + 94);
            if ( (_WORD)v96 == *((_WORD *)v38 + 47) )
            {
              v97 = 0;
              if ( (_WORD)v96 )
              {
                v98 = v38[1];
                v99 = *(_QWORD *)(j + 8);
                while ( *(_WORD *)(v99 + 2LL * v97) == v98[v97]
                     && !(unsigned int)sqlite3StrICmp(
                                         *(_QWORD *)(*(_QWORD *)(j + 64) + 8LL * v97),
                                         *((_QWORD *)v38[8] + v97)) )
                {
                  v98 = v38[1];
                  v97 = v100 + 1;
                  v99 = *(_QWORD *)(j + 8);
                  if ( (int)v97 >= v96 )
                    goto LABEL_174;
                }
              }
              else
              {
LABEL_174:
                if ( v97 == v96 )
                {
                  v101 = *((_BYTE *)v38 + 98);
                  if ( *(_BYTE *)(j + 98) != v101 )
                  {
                    if ( *(_BYTE *)(j + 98) == 11 )
                      goto LABEL_180;
                    if ( v101 != 11 )
                      sqlite3ErrorMsg(v13, "conflicting ON CONFLICT clauses specified", 0);
                    if ( *(_BYTE *)(j + 98) == 11 )
LABEL_180:
                      *(_BYTE *)(j + 98) = *((_BYTE *)v38 + 98);
                  }
                  if ( a11 == 2 )
                    *(_DWORD *)(j + 100) ^= ((unsigned __int8)*(_DWORD *)(j + 100) ^ 2) & 3;
                  if ( *((_BYTE *)v13 + 308) >= 2u )
                  {
                    v38[5] = (void *)v13[45];
                    v13[45] = v38;
                    v38 = 0;
                  }
                  goto LABEL_75;
                }
              }
            }
          }
        }
        if ( *((_BYTE *)v13 + 308) < 2u )
        {
          if ( *(_BYTE *)(v16 + 197) )
          {
            if ( v58 )
            {
              *((_DWORD *)v38 + 22) = *(_DWORD *)(v16 + 192);
              if ( (unsigned int)sqlite3IndexHasDuplicateRootPage(v38, v57, 0) )
              {
                sqlite3ErrorMsg(v13, "invalid rootpage");
                *((_DWORD *)v13 + 6) = sqlite3ReportError(11, 126056, "database corruption");
                goto LABEL_75;
              }
            }
            v60 = sqlite3HashInsert((char *)v38[6] + 32, *v38, v38);
            v61 = 0;
            if ( v60 )
            {
              sqlite3OomFault(v16);
              goto LABEL_75;
            }
            *(_DWORD *)(v16 + 44) |= 1u;
LABEL_72:
            if ( *(_BYTE *)(v16 + 197) != (_BYTE)v61 || a4 == v61 )
            {
              v38[5] = *(void **)(v18 + 16);
              *(_QWORD *)(v18 + 16) = v38;
            }
            else
            {
              if ( *((_BYTE *)v13 + 308) < 2u )
                goto LABEL_75;
              v13[45] = v38;
            }
LABEL_77:
            v14 = Src;
            break;
          }
          if ( *(char *)(v18 + 48) >= 0 || v58 )
          {
            v81 = ++*((_DWORD *)v13 + 14);
            v122 = v81;
            Vdbe = sqlite3GetVdbe(v13);
            if ( !Vdbe )
              goto LABEL_75;
            sqlite3BeginWriteOperation(v13, 1, (unsigned int)v23, v82);
            *((_DWORD *)v38 + 22) = sqlite3VdbeAddOp3(Vdbe, 187, 0, 0, 0);
            sqlite3VdbeAddOp3(Vdbe, 147, v23, v81, 2);
            if ( a7 )
            {
              v102 = (const char *)&::Src;
              v103 = *((_DWORD *)v13 + 72) + *((_DWORD *)v13 + 74) - *(_DWORD *)v113;
              v104 = v103 - 1;
              if ( *(_BYTE *)((int)v104 + *v113) != 59 )
                v104 = v103;
              if ( a6 )
                v102 = " UNIQUE";
              v84 = sqlite3MPrintf(v16, "CREATE%s INDEX %.*s", v102, v104, *v113);
            }
            else
            {
              v84 = 0;
            }
            sqlite3NestedParse(
              v13,
              "INSERT INTO %Q.sqlite_master VALUES('index',%Q,%Q,#%d,%Q);",
              *(_QWORD *)(32LL * v23 + *(_QWORD *)(v16 + 32)),
              *v38,
              *(_QWORD *)v18,
              v122,
              v84);
            sqlite3DbFree(v16, v84);
            if ( a4 )
            {
              sqlite3RefillIndex(v13, v38, v122);
              sqlite3VdbeAddOp3(v13[2], 100, v23, 1, **(_DWORD **)(32LL * v23 + *(_QWORD *)(*v13 + 32LL) + 24) + 1);
              v105 = sqlite3MPrintf(v16, "name='%q' AND type='index'", *v38);
              sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v23, v105, 0);
              sqlite3VdbeAddOp3(Vdbe, 166, 0, 1, 0);
            }
            *(_DWORD *)(sqlite3VdbeGetOp(Vdbe, *((unsigned int *)v38 + 22), v85, v86) + 8) = *(_DWORD *)(Vdbe + 144);
            goto LABEL_72;
          }
        }
        v61 = 0;
        goto LABEL_72;
      }
      sqlite3StringToId(*v45);
      sqlite3ResolveSelfReference((_DWORD)v13, v18, 32, *v49, v50);
      if ( *((_DWORD *)v13 + 12) )
        goto LABEL_75;
      v51 = sqlite3ExprSkipCollate(*(_QWORD *)v111);
      if ( *(_BYTE *)v51 == 0xA7 )
      {
        v53 = *(__int16 *)(v51 + 48);
        if ( (int)v53 < 0 )
        {
          LODWORD(v53) = *(__int16 *)(v18 + 52);
        }
        else
        {
          if ( (*(_BYTE *)(*(_QWORD *)(v18 + 8) + 24 * v53 + 8) & 0xF) == 0 )
            *((_DWORD *)v38 + 25) &= ~8u;
          if ( (*(_BYTE *)(*(_QWORD *)(v18 + 8) + 24 * v53 + 18) & 0x20) != 0 )
            *((_DWORD *)v38 + 25) |= 0x1800u;
        }
        *((_WORD *)v38[1] + v108) = v53;
      }
      else
      {
        if ( v18 == v13[44] )
        {
          sqlite3ErrorMsg(v13, "expressions prohibited in PRIMARY KEY and UNIQUE constraints");
          goto LABEL_75;
        }
        if ( v38[10] == v43 )
        {
          v38[10] = v46;
          appended = v43;
        }
        LODWORD(v53) = -2;
        *((_WORD *)v38[1] + v108) = -2;
        *((_DWORD *)v38 + 25) &= ~8u;
        *((_DWORD *)v38 + 25) |= 0x1000u;
      }
      if ( **(_BYTE **)v52 == 113 )
      {
        v73 = sqlite3Strlen30(*(_QWORD *)(*(_QWORD *)v52 + 8LL));
        v54 = (const char *)v114;
        v74 = v73 + 1;
        memcpy_0(v114, v75, v74);
        LODWORD(v43) = 0;
        v114 = (void *)&v54[v74];
      }
      else
      {
        if ( (int)v53 < 0 )
          goto LABEL_53;
        v54 = (const char *)sqlite3ColumnColl(*(_QWORD *)(v18 + 8) + 24LL * (int)v53);
      }
      if ( !v54 )
LABEL_53:
        v54 = "BINARY";
      if ( *(_BYTE *)(v16 + 197) == (_BYTE)v43 )
      {
        CollSeq = sqlite3LocateCollSeq(v13, v54);
        LODWORD(v43) = 0;
        if ( !CollSeq )
          goto LABEL_75;
      }
      v55 = (char *)v111;
      v46 = appended;
      *((_QWORD *)v38[8] + v108) = v54;
      v56 = v55[16];
      if ( v125 < 4u )
        v56 = (char)v43;
      *((_BYTE *)v38[7] + v108) = v56;
      v47 = v108 + 1;
      v45 = v55 + 32;
      v111 = v45;
    }
  }
LABEL_78:
  for ( k = (__int64 *)(v18 + 16); ; k = (__int64 *)(v63 + 40) )
  {
    v63 = *k;
    if ( !*k )
      break;
    if ( *(_BYTE *)(v63 + 98) == 5 )
    {
      while ( 1 )
      {
        v71 = *(_QWORD *)(v63 + 40);
        if ( !v71 || *(_BYTE *)(v71 + 98) == 5 )
          break;
        *k = v71;
        k = (__int64 *)(v71 + 40);
        *(_QWORD *)(v63 + 40) = *(_QWORD *)(v71 + 40);
        *(_QWORD *)(v71 + 40) = v63;
      }
      break;
    }
  }
  v17 = appended;
LABEL_102:
  if ( a8 )
    sqlite3ExprDeleteNN(v16);
  if ( v17 )
    exprListDeleteNN((_QWORD *)v16, v17);
  sqlite3SrcListDelete(v16, a4);
  return sqlite3DbFree(v16, v14);
}

```

## disassembly

```asm
0x18001d1c8  mov     rax, rsp
0x18001d1cb  mov     [rax+10h], rbx
0x18001d1cf  mov     [rax+20h], r9
0x18001d1d3  mov     [rax+8], rcx
0x18001d1d7  push    rbp
0x18001d1d8  push    rsi
0x18001d1d9  push    rdi
0x18001d1da  push    r12
0x18001d1dc  push    r13
0x18001d1de  push    r14
0x18001d1e0  push    r15
0x18001d1e2  lea     rbp, [rax-3Fh]
0x18001d1e6  sub     rsp, 100h
0x18001d1ed  mov     rbx, r8
0x18001d1f0  mov     r15, rdx
0x18001d1f3  mov     rdi, rcx
0x18001d1f6  xor     esi, esi
0x18001d1f8  xor     edx, edx; Val
0x18001d1fa  lea     rcx, [rbp+37h+var_90]; void *
0x18001d1fe  mov     r12, r9
0x18001d201  lea     r8d, [rsi+60h]; Size
0x18001d205  call    memset_0
0x18001d20a  mov     r14, [rdi]
0x18001d20d  xor     r10d, r10d
0x18001d210  mov     [rbp+37h+var_A0], r14
0x18001d214  mov     [rsp+130h+var_C8], r10
0x18001d219  mov     [rsp+130h+var_D8], r10
0x18001d21e  cmp     [rdi+30h], r10d
0x18001d222  jnz     loc_18001DB4C
0x18001d228  cmp     byte ptr [rdi+134h], 1
0x18001d22f  jz      loc_18001DB3F
0x18001d235  mov     rcx, rdi
0x18001d238  call    sqlite3ReadSchema
0x18001d23d  test    eax, eax
0x18001d23f  jnz     loc_18001DB4C
0x18001d245  mov     r13, [rbp+37h+arg_20]
0x18001d249  mov     rcx, rdi
0x18001d24c  mov     rdx, r13
0x18001d24f  mov     [rsp+130h+var_E8], r13
0x18001d254  call    sqlite3HasExplicitNulls
0x18001d259  xor     r10d, r10d
0x18001d25c  test    eax, eax
0x18001d25e  jnz     loc_18001D82C
0x18001d264  mov     [rsp+130h+var_D0], r10
0x18001d269  test    r12, r12
0x18001d26c  jnz     loc_18001DA9A
0x18001d272  mov     r15, [rdi+160h]
0x18001d279  mov     [rbp+37h+var_B0], r15
0x18001d27d  test    r15, r15
0x18001d280  jz      loc_18001D82C
0x18001d286  mov     rdx, [r15+60h]
0x18001d28a  mov     rcx, r14
0x18001d28d  call    sqlite3SchemaToIndex
0x18001d292  mov     rbx, [rbp+37h+arg_18]
0x18001d296  lea     r11d, [r10+1]
0x18001d29a  mov     r12d, eax
0x18001d29d  cmp     [r15], r10
0x18001d2a0  jnz     loc_18001D790
0x18001d2a6  mov     al, [r15+3Fh]
0x18001d2aa  cmp     al, 2
0x18001d2ac  jz      loc_18001DBCF
0x18001d2b2  cmp     al, r11b
0x18001d2b5  jz      loc_18001DBD8
0x18001d2bb  mov     rax, [r14+20h]
0x18001d2bf  movsxd  rbx, r12d
0x18001d2c2  shl     rbx, 5
0x18001d2c6  mov     [rsp+130h+var_F0], rax
0x18001d2cb  mov     rax, [rsp+130h+var_C8]
0x18001d2d0  mov     [rbp+37h+var_A8], rbx
0x18001d2d4  test    rax, rax
0x18001d2d7  jnz     loc_18001D6FD
0x18001d2dd  mov     rax, [r15+10h]
0x18001d2e1  mov     r9d, r11d
0x18001d2e4  test    rax, rax
0x18001d2e7  jnz     loc_18001DC0B
0x18001d2ed  mov     r8, [r15]
0x18001d2f0  lea     rdx, aSqliteAutoinde; "sqlite_autoindex_%s_%d"
0x18001d2f7  mov     rcx, r14
0x18001d2fa  call    sqlite3MPrintf
0x18001d2ff  xor     r10d, r10d
0x18001d302  mov     [rsp+130h+Src], rax
0x18001d307  mov     rsi, rax
0x18001d30a  test    rax, rax
0x18001d30d  jz      loc_18001D6DD
0x18001d313  cmp     [rdi+134h], r10b
0x18001d31a  jnz     loc_18001DC17
0x18001d320  cmp     byte ptr [rdi+134h], 2
0x18001d327  jnb     short loc_18001D393
0x18001d329  mov     rax, [rsp+130h+var_F0]
0x18001d32e  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18001d335  cmp     r12d, 1
0x18001d339  mov     rcx, rdi
0x18001d33c  mov     rsi, [rbx+rax]
0x18001d340  lea     rax, aSqliteMaster; "sqlite_master"
0x18001d347  cmovnz  r8, rax
0x18001d34b  mov     [rsp+130h+var_110], rsi
0x18001d350  xor     r9d, r9d
0x18001d353  lea     edx, [r9+12h]
0x18001d357  call    sqlite3AuthCheck
0x18001d35c  test    eax, eax
0x18001d35e  jnz     loc_18001D6D8
0x18001d364  mov     r9, [r15]
0x18001d367  lea     edx, [rax+3]
0x18001d36a  lea     eax, [rdx-2]
0x18001d36d  mov     [rsp+130h+var_110], rsi
0x18001d372  mov     rsi, [rsp+130h+Src]
0x18001d377  cmp     r12d, eax
0x18001d37a  mov     r8, rsi
0x18001d37d  mov     rcx, rdi
0x18001d380  cmovnz  edx, eax
0x18001d383  call    sqlite3AuthCheck
0x18001d388  xor     r10d, r10d
0x18001d38b  test    eax, eax
0x18001d38d  jnz     loc_18001D6DD
0x18001d393  mov     r8d, 8
0x18001d399  test    r13, r13
0x18001d39c  jz      loc_18001D907
0x18001d3a2  mov     rax, [rdi]
0x18001d3a5  mov     ecx, [rax+90h]
0x18001d3ab  cmp     [r13+0], ecx
0x18001d3af  jle     short loc_18001D3CA
0x18001d3b1  lea     r8, aIndex; "index"
0x18001d3b8  mov     rcx, rdi
0x18001d3bb  lea     rdx, aTooManyColumns_0; "too many columns in %s"
0x18001d3c2  call    sqlite3ErrorMsg
0x18001d3c7  xor     r10d, r10d
0x18001d3ca  cmp     [rdi+30h], r10d
0x18001d3ce  jnz     loc_18001D6DD
0x18001d3d4  mov     r8d, r10d
0x18001d3d7  mov     edx, r10d
0x18001d3da  cmp     [r13+0], r10d
0x18001d3de  jle     short loc_18001D3FC
0x18001d3e0  mov     eax, edx
0x18001d3e2  shl     rax, 5
0x18001d3e6  mov     rcx, [rax+r13+8]
0x18001d3eb  cmp     byte ptr [rcx], 71h ; 'q'
0x18001d3ee  jz      loc_18001DC1F
0x18001d3f4  inc     edx
0x18001d3f6  cmp     edx, [r13+0]
0x18001d3fa  jl      short loc_18001D3E0
0x18001d3fc  mov     rcx, rsi
0x18001d3ff  call    sqlite3Strlen30
0x18001d404  mov     rdx, [rsp+130h+var_D0]
0x18001d409  mov     dword ptr [rbp+37h+arg_20], eax
0x18001d40c  test    rdx, rdx
0x18001d40f  jnz     loc_18001DC33
0x18001d415  mov     edx, 1
0x18001d41a  add     dx, [r13+0]
0x18001d41f  lea     r9, [rsp+130h+var_D8]
0x18001d424  inc     eax
0x18001d426  mov     rcx, r14
0x18001d429  add     r8d, eax
0x18001d42c  call    sqlite3AllocateIndexObject
0x18001d431  xor     r10d, r10d
0x18001d434  mov     rsi, rax
0x18001d437  cmp     [r14+67h], r10b
0x18001d43b  jnz     loc_18001D6CF
0x18001d441  mov     rcx, [rsp+130h+var_D8]; void *
0x18001d446  mov     rdx, [rsp+130h+Src]; Src
0x18001d44b  mov     [rax], rcx
0x18001d44e  mov     eax, dword ptr [rbp+37h+arg_20]
0x18001d451  inc     eax
0x18001d453  movsxd  r8, eax; Size
0x18001d456  lea     rax, [r8+rcx]
0x18001d45a  mov     [rsp+130h+var_C0], rax
0x18001d45f  call    memcpy_0
0x18001d464  mov     eax, [rbp+37h+arg_28]
0x18001d467  mov     [rsi+62h], al
0x18001d46a  neg     eax
0x18001d46c  mov     eax, [rsi+64h]
0x18001d46f  sbb     ecx, ecx
0x18001d471  mov     [rsi+18h], r15
0x18001d475  and     eax, 0FFFFFFF7h
0x18001d478  and     ecx, 8
0x18001d47b  or      ecx, eax
0x18001d47d  xor     r10d, r10d
0x18001d480  movzx   eax, [rbp+37h+arg_50]
0x18001d487  xor     eax, ecx
0x18001d489  and     eax, 3
0x18001d48c  xor     eax, ecx
0x18001d48e  mov     [rsi+64h], eax
0x18001d491  mov     rax, [r14+20h]
0x18001d495  mov     rcx, [rbx+rax+18h]
0x18001d49a  mov     rbx, [rbp+37h+arg_38]
0x18001d49e  mov     [rsi+30h], rcx
0x18001d4a2  movzx   eax, word ptr [r13+0]
0x18001d4a7  mov     [rsi+5Eh], ax
0x18001d4ab  test    rbx, rbx
0x18001d4ae  jnz     loc_18001DC3C
0x18001d4b4  cmp     byte ptr [rdi+134h], 2
0x18001d4bb  lea     r8, [r13+8]
0x18001d4bf  mov     rax, [rbp+37h+var_A8]
0x18001d4c3  mov     rcx, [rsp+130h+var_F0]
0x18001d4c8  mov     [rsp+130h+var_D8], r8
0x18001d4cd  mov     rax, [rax+rcx+18h]
0x18001d4d2  mov     al, [rax+70h]
0x18001d4d5  mov     byte ptr [rbp+37h+arg_20], al
0x18001d4d8  jnb     loc_18001DC65
0x18001d4de  mov     rbx, [rsp+130h+var_E8]
0x18001d4e3  mov     eax, r10d
0x18001d4e6  movzx   r13d, word ptr [rsi+5Eh]
0x18001d4eb  mov     dword ptr [rsp+130h+var_F0], eax
0x18001d4ef  cmp     eax, r13d
0x18001d4f2  jge     loc_18001D5F7
0x18001d4f8  mov     rcx, [r8]
0x18001d4fb  call    sqlite3StringToId
0x18001d500  mov     r9, [r8]
0x18001d503  mov     rdx, r15
0x18001d506  mov     r8d, 20h ; ' '
0x18001d50c  mov     [rsp+130h+var_110], r10
0x18001d511  mov     rcx, rdi
0x18001d514  call    sqlite3ResolveSelfReference
0x18001d519  xor     r10d, r10d
0x18001d51c  cmp     [rdi+30h], r10d
0x18001d520  jnz     loc_18001D6CF
0x18001d526  mov     r8, [rsp+130h+var_D8]
0x18001d52b  mov     rcx, [r8]
0x18001d52e  call    sqlite3ExprSkipCollate
0x18001d533  cmp     byte ptr [rax], 0A7h
0x18001d536  jnz     loc_18001D882
0x18001d53c  movsx   rcx, word ptr [rax+30h]
0x18001d541  test    ecx, ecx
0x18001d543  js      loc_18001D8C3
0x18001d549  mov     rax, [r15+8]
0x18001d54d  lea     rdx, [rcx+rcx*2]
0x18001d551  test    byte ptr [rax+rdx*8+8], 0Fh
0x18001d556  jnz     short loc_18001D55C
0x18001d558  and     dword ptr [rsi+64h], 0FFFFFFF7h
0x18001d55c  mov     rax, [r15+8]
0x18001d560  test    byte ptr [rax+rdx*8+12h], 20h
0x18001d565  jnz     loc_18001D98A
0x18001d56b  movsxd  rdx, dword ptr [rsp+130h+var_F0]
0x18001d570  mov     rax, [rsi+8]
0x18001d574  mov     [rax+rdx*2], cx
0x18001d578  mov     rax, [r8]
0x18001d57b  cmp     byte ptr [rax], 71h ; 'q'
0x18001d57e  jz      loc_18001D8D5
0x18001d584  test    ecx, ecx
0x18001d586  js      short loc_18001D5A4
0x18001d588  movsxd  rax, ecx
0x18001d58b  lea     rcx, [rax+rax*2]
0x18001d58f  mov     rax, [r15+8]
0x18001d593  lea     rcx, [rax+rcx*8]
0x18001d597  call    sqlite3ColumnColl
0x18001d59c  mov     r13, rax
0x18001d59f  test    r13, r13
0x18001d5a2  jnz     short loc_18001D5AB
0x18001d5a4  lea     r13, aBinary_0; "BINARY"
0x18001d5ab  cmp     [r14+0C5h], r10b
0x18001d5b2  jz      loc_18001D996
0x18001d5b8  mov     rax, [rsi+40h]
0x18001d5bc  mov     r8, [rsp+130h+var_D8]
0x18001d5c1  movsxd  rdx, dword ptr [rsp+130h+var_F0]
0x18001d5c6  cmp     byte ptr [rbp+37h+arg_20], 4
0x18001d5ca  mov     rbx, [rsp+130h+var_E8]
0x18001d5cf  mov     [rax+rdx*8], r13
0x18001d5d3  movzx   ecx, byte ptr [r8+10h]
0x18001d5d8  mov     rax, [rsi+38h]
0x18001d5dc  cmovb   ecx, r10d
0x18001d5e0  mov     [rdx+rax], cl
0x18001d5e3  mov     eax, dword ptr [rsp+130h+var_F0]
0x18001d5e7  inc     eax
0x18001d5e9  add     r8, 20h ; ' '
0x18001d5ed  mov     [rsp+130h+var_D8], r8
0x18001d5f2  jmp     loc_18001D4E6
0x18001d5f7  mov     rcx, [rsp+130h+var_D0]
0x18001d5fc  test    rcx, rcx
0x18001d5ff  jnz     loc_18001DC8A
0x18001d605  movsxd  rcx, eax
0x18001d608  lea     rdx, aBinary_0; "BINARY"
0x18001d60f  mov     rax, [rsi+8]
0x18001d613  mov     word ptr [rax+rcx*2], 0FFFFh
0x18001d619  mov     rax, [rsi+40h]
0x18001d61d  mov     [rax+rcx*8], rdx
0x18001d621  mov     rcx, rsi
0x18001d624  call    sqlite3DefaultRowEst
0x18001d629  cmp     qword ptr [rdi+160h], 0
0x18001d631  jz      loc_18001DD21
0x18001d637  mov     rcx, rsi
0x18001d63a  call    recomputeColumnsNotIndexed
0x18001d63f  mov     rax, [rbp+37h+arg_18]
0x18001d643  xor     r8d, r8d
0x18001d646  test    rax, rax
0x18001d649  jnz     loc_18001DD2E
0x18001d64f  cmp     r15, [rdi+160h]
0x18001d656  jnz     short loc_18001D669
0x18001d658  mov     rbx, [r15+10h]
0x18001d65c  test    rbx, rbx
0x18001d65f  jnz     loc_18001DD85
0x18001d665  mov     rax, [rbp+37h+arg_18]
0x18001d669  cmp     byte ptr [rdi+134h], 2
0x18001d670  jnb     loc_18001D8CD
0x18001d676  cmp     [r14+0C5h], r8b
0x18001d67d  jz      loc_18001D9B2
0x18001d683  test    rax, rax
0x18001d686  jnz     loc_18001DE6C
0x18001d68c  mov     rcx, [rsi+30h]
0x18001d690  mov     r8, rsi
0x18001d693  mov     rdx, [rsi]
0x18001d696  add     rcx, 20h ; ' '
  ... truncated ...
```
