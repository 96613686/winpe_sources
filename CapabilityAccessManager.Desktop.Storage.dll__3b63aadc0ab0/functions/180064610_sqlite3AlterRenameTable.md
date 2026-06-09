# sqlite3AlterRenameTable

- ea: `0x180064610`
- end: `0x180064b55`
- name: `sqlite3AlterRenameTable`
- size: `1349`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800d8b00`

## callees

- `0x180005980`
- `0x180044640`
- `0x180045f70`
- `0x18004dba0`
- `0x18005b0a0`
- `0x18005b6f0`
- `0x180064610`
- `0x1800658d0`
- `0x18006b6d0`
- `0x1800743d0`
- `0x18007c060`
- `0x18007c190`
- `0x180086660`
- `0x180087d40`
- `0x180088db0`
- `0x180088ea0`
- `0x18009bde0`
- `0x1800a3b40`
- `0x1800aea10`
- `0x1800c3f40`
- `0x1800c8710`

## string_xrefs

- `0x180064abe`: `there is already another table or index with this name: %s`
- `0x1800648c7`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x1800648ff`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x18006494a`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x180064971`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x180064a8f`: `after rename`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameTable(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  __int64 v8; // r9
  _QWORD *v9; // r14
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // r9
  __int64 Table; // rax
  __int64 v14; // r15
  __int64 v15; // rcx
  int v16; // ebp
  __int64 v17; // rdx
  __int64 v18; // r14
  __int64 v19; // rax
  __int64 i; // rdx
  __int64 v21; // rax
  __int64 v22; // r14
  __int64 v23; // rcx
  int v24; // r12d
  unsigned __int8 *j; // rax
  unsigned __int8 v26; // cl
  char v27; // cl
  unsigned int v28; // r15d
  __int64 v29; // r9
  _QWORD *v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 result; // rax
  unsigned __int8 *v36; // [rsp+20h] [rbp-68h]
  __int64 v37; // [rsp+40h] [rbp-48h]
  __int64 v39; // [rsp+A8h] [rbp+20h]

  v3 = *(_QWORD **)a1;
  v4 = 0;
  v37 = 0;
  if ( *(_BYTE *)(*(_QWORD *)a1 + 103LL) )
    goto LABEL_62;
  v8 = a2[1];
  v9 = v3 + 4;
  if ( v8 )
  {
    v10 = *v9;
    v11 = 0;
    if ( *(_QWORD *)(*v9 + 24LL) != v8 )
    {
      do
        ++v11;
      while ( *(_QWORD *)(32LL * v11 + v10 + 24) != v8 );
    }
    v12 = *(_QWORD *)(32LL * v11 + v10);
  }
  else
  {
    v12 = a2[2];
  }
  Table = sqlite3LocateTable(a1, 0, a2[3], v12);
  v14 = Table;
  if ( !Table )
    goto LABEL_62;
  v15 = *(_QWORD *)(Table + 96);
  if ( v15 )
  {
    v16 = 0;
    v17 = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    if ( *(_QWORD *)(v17 + 24) != v15 )
    {
      do
        ++v16;
      while ( *(_QWORD *)(32LL * v16 + v17 + 24) != v15 );
      v9 = v3 + 4;
    }
  }
  else
  {
    v16 = -32768;
  }
  v18 = *(_QWORD *)(32LL * v16 + *v9);
  v39 = v18;
  v19 = sqlite3NameFromToken(v3, a3);
  v4 = (_QWORD *)v19;
  if ( !v19 )
    goto LABEL_62;
  if ( sqlite3FindTable(v3, v19, v18)
    || sqlite3FindIndex(v3, v4, v18)
    || (unsigned int)sqlite3IsShadowTableOf(v3, v14, v4) )
  {
    sqlite3ErrorMsg(a1, "there is already another table or index with this name: %s", v4);
    goto LABEL_21;
  }
  if ( (unsigned int)isAlterableTable(a1, v14) || (unsigned int)sqlite3CheckObjectName(a1, v4, "table", v4) )
  {
LABEL_62:
    result = sqlite3SrcListDelete(v3, a2);
    if ( !v4 )
      return result;
    goto LABEL_63;
  }
  if ( *(_BYTE *)(v14 + 63) != 2 )
  {
    if ( !(unsigned int)sqlite3AuthCheck(a1, 26, v18, *(_QWORD *)v14, 0)
      && (*(_BYTE *)(v14 + 63) != 1 && *(__int16 *)(v14 + 54) > 0 || !(unsigned int)viewGetColumnNames(a1, v14)) )
    {
      if ( *(_BYTE *)(v14 + 63) == 1 )
      {
        for ( i = *(_QWORD *)(v14 + 80); i; i = *(_QWORD *)(i + 40) )
        {
          if ( *(_QWORD **)i == v3 )
            break;
        }
        v21 = 0;
        if ( *(_QWORD *)(**(_QWORD **)(i + 16) + 152LL) )
          v21 = i;
        v37 = v21;
      }
      v22 = *(_QWORD *)(a1 + 16);
      if ( v22 )
        goto LABEL_38;
      if ( !*(_QWORD *)(a1 + 168) && (*(_BYTE *)(*(_QWORD *)a1 + 96LL) & 8) == 0 )
        *(_BYTE *)(a1 + 35) = 1;
      v22 = sqlite3VdbeCreate(a1);
      if ( v22 )
      {
LABEL_38:
        v23 = a1;
        if ( *(_QWORD *)(a1 + 168) )
          v23 = *(_QWORD *)(a1 + 168);
        v24 = 0;
        *(_BYTE *)(v23 + 33) = 1;
        for ( j = *(unsigned __int8 **)v14; *j; ++v24 )
        {
          if ( j == (unsigned __int8 *)-1LL )
            break;
          v26 = *j++;
          if ( v26 >= 0xC0u && (*j & 0xC0) == 0x80 )
          {
            do
              v27 = *++j;
            while ( (v27 & 0xC0) == 0x80 );
          }
        }
        sqlite3NestedParse(
          a1,
          "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index"
          "' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'",
          v39);
        HIDWORD(v36) = HIDWORD(v4);
        sqlite3NestedParse(
          a1,
          "UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoi"
          "ndex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WH"
          "ERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');",
          v39);
        if ( sqlite3FindTable(v3, "sqlite_sequence", v39) )
        {
          v36 = *(unsigned __int8 **)v14;
          sqlite3NestedParse(a1, "UPDATE \"%w\".sqlite_sequence set name = %Q WHERE name = %Q", v39);
        }
        if ( v16 != 1 )
        {
          HIDWORD(v36) = HIDWORD(v4);
          sqlite3NestedParse(
            a1,
            "UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHE"
            "N tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELS"
            "E tbl_name END WHERE type IN ('view', 'trigger')",
            v39);
        }
        if ( v37 )
        {
          v28 = ++*(_DWORD *)(a1 + 56);
          sqlite3VdbeLoadString(v22, v28, v4);
          v29 = *(int *)(v22 + 144);
          if ( *(_DWORD *)(v22 + 148) > (int)v29 )
          {
            *(_DWORD *)(v22 + 144) = v29 + 1;
            v31 = 3 * v29;
            v30 = (_QWORD *)(v22 + 136);
            v32 = *(_QWORD *)(v22 + 136);
            *(_DWORD *)(v32 + 8 * v31) = 176;
            *(_DWORD *)(v32 + 8 * v31 + 4) = v28;
            v33 = v32 + 24 * v29;
            *(_QWORD *)(v33 + 8) = 0;
            *(_QWORD *)(v33 + 16) = 0;
          }
          else
          {
            LODWORD(v36) = 0;
            LODWORD(v29) = growOp3(v22, 176, v28, 0, v36);
            v30 = (_QWORD *)(v22 + 136);
          }
          if ( !*(_BYTE *)(*(_QWORD *)v22 + 103LL) )
          {
            if ( (int)v29 < 0 )
              LODWORD(v29) = *(_DWORD *)(v22 + 144) - 1;
            v34 = *v30 + 24LL * (int)v29;
            if ( *(_BYTE *)(v34 + 1) )
            {
              vdbeChangeP4Full(v22, *v30 + 24LL * (int)v29, v37, 4294967285LL);
            }
            else
            {
              *(_QWORD *)(v34 + 16) = v37;
              *(_BYTE *)(v34 + 1) = -11;
              ++*(_DWORD *)(v37 + 24);
            }
          }
        }
        renameReloadSchema(a1, (unsigned int)v16, 1);
        renameTestSchema(a1, v39, v16 == 1, (unsigned int)"after rename", 0);
        sqlite3SrcListDelete(v3, a2);
        goto LABEL_63;
      }
    }
    goto LABEL_62;
  }
  sqlite3ErrorMsg(a1, "view %s may not be altered", *(_QWORD *)v14);
LABEL_21:
  sqlite3SrcListDelete(v3, a2);
LABEL_63:
  if ( (unsigned __int64)v4 >= v3[62] )
    goto LABEL_73;
  if ( (unsigned __int64)v4 >= v3[60] )
  {
    result = v3[59];
    *v4 = result;
    v3[59] = v4;
    return result;
  }
  if ( (unsigned __int64)v4 < v3[61] )
  {
LABEL_73:
    if ( v3[97] )
      return measureAllocationSize(v3, v4);
    else
      return sqlite3_free(v4);
  }
  else
  {
    result = v3[57];
    *v4 = result;
    v3[57] = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180064610  mov     [rsp+arg_10], rbx
0x180064615  mov     [rsp+arg_8], rdx
0x18006461a  push    rbp
0x18006461b  push    rsi
0x18006461c  push    rdi
0x18006461d  push    r12
0x18006461f  push    r13
0x180064621  push    r14
0x180064623  push    r15
0x180064625  sub     rsp, 50h
0x180064629  mov     rbx, [rcx]
0x18006462c  xor     eax, eax
0x18006462e  xor     edi, edi
0x180064630  mov     [rsp+88h+var_48], rax
0x180064635  mov     r12, r8
0x180064638  mov     r13, rdx
0x18006463b  mov     rsi, rcx
0x18006463e  cmp     [rbx+67h], al
0x180064641  jnz     loc_180064ACD
0x180064647  mov     r9, [rdx+8]
0x18006464b  lea     r14, [rbx+20h]
0x18006464f  test    r9, r9
0x180064652  jz      short loc_18006467D
0x180064654  mov     rdx, [r14]
0x180064657  xor     ecx, ecx
0x180064659  cmp     [rdx+18h], r9
0x18006465d  jz      short loc_180064670
0x18006465f  nop
0x180064660  inc     ecx
0x180064662  movsxd  rax, ecx
0x180064665  shl     rax, 5
0x180064669  cmp     [rax+rdx+18h], r9
0x18006466e  jnz     short loc_180064660
0x180064670  movsxd  rax, ecx
0x180064673  shl     rax, 5
0x180064677  mov     r9, [rax+rdx]
0x18006467b  jmp     short loc_180064681
0x18006467d  mov     r9, [rdx+10h]
0x180064681  mov     r8, [r13+18h]
0x180064685  xor     edx, edx
0x180064687  mov     rcx, rsi
0x18006468a  call    sqlite3LocateTable
0x18006468f  mov     r15, rax
0x180064692  test    rax, rax
0x180064695  jz      loc_180064ACD
0x18006469b  mov     rcx, [rax+60h]
0x18006469f  test    rcx, rcx
0x1800646a2  jz      short loc_1800646D6
0x1800646a4  mov     rax, [rsi]
0x1800646a7  xor     ebp, ebp
0x1800646a9  mov     rdx, [rax+20h]
0x1800646ad  cmp     [rdx+18h], rcx
0x1800646b1  jz      short loc_1800646DB
0x1800646b3  nop     dword ptr [rax+00h]
0x1800646b7  nop     word ptr [rax+rax+00000000h]
0x1800646c0  inc     ebp
0x1800646c2  movsxd  rax, ebp
0x1800646c5  shl     rax, 5
0x1800646c9  cmp     [rax+rdx+18h], rcx
0x1800646ce  jnz     short loc_1800646C0
0x1800646d0  lea     r14, [rbx+20h]
0x1800646d4  jmp     short loc_1800646DB
0x1800646d6  mov     ebp, 0FFFF8000h
0x1800646db  mov     rax, [r14]
0x1800646de  mov     rdx, r12
0x1800646e1  movsxd  rcx, ebp
0x1800646e4  shl     rcx, 5
0x1800646e8  mov     r14, [rcx+rax]
0x1800646ec  mov     rcx, rbx
0x1800646ef  mov     [rsp+88h+arg_18], r14
0x1800646f7  call    sqlite3NameFromToken
0x1800646fc  mov     rdi, rax
0x1800646ff  test    rax, rax
0x180064702  jz      loc_180064ACD
0x180064708  mov     r8, r14
0x18006470b  mov     rdx, rax
0x18006470e  mov     rcx, rbx
0x180064711  call    sqlite3FindTable
0x180064716  test    rax, rax
0x180064719  jnz     loc_180064ABB
0x18006471f  mov     r8, r14
0x180064722  mov     rdx, rdi
0x180064725  mov     rcx, rbx
0x180064728  call    sqlite3FindIndex
0x18006472d  test    rax, rax
0x180064730  jnz     loc_180064ABB
0x180064736  mov     r8, rdi
0x180064739  mov     rdx, r15
0x18006473c  mov     rcx, rbx
0x18006473f  call    sqlite3IsShadowTableOf
0x180064744  test    eax, eax
0x180064746  jnz     loc_180064ABB
0x18006474c  mov     rdx, r15
0x18006474f  mov     rcx, rsi
0x180064752  call    isAlterableTable
0x180064757  test    eax, eax
0x180064759  jnz     loc_180064ACD
0x18006475f  mov     r9, rdi
0x180064762  lea     r8, aTable; "table"
0x180064769  mov     rdx, rdi
0x18006476c  mov     rcx, rsi
0x18006476f  call    sqlite3CheckObjectName
0x180064774  test    eax, eax
0x180064776  jnz     loc_180064ACD
0x18006477c  cmp     byte ptr [r15+3Fh], 2
0x180064781  mov     rcx, rsi
0x180064784  mov     r9, [r15]
0x180064787  jnz     short loc_1800647A8
0x180064789  mov     r8, r9
0x18006478c  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x180064793  call    sqlite3ErrorMsg
0x180064798  mov     rdx, r13
0x18006479b  mov     rcx, rbx
0x18006479e  call    sqlite3SrcListDelete
0x1800647a3  jmp     loc_180064ADD
0x1800647a8  mov     r8, r14
0x1800647ab  mov     [rsp+88h+var_68], 0
0x1800647b4  mov     edx, 1Ah
0x1800647b9  call    sqlite3AuthCheck
0x1800647be  test    eax, eax
0x1800647c0  jnz     loc_180064ACD
0x1800647c6  cmp     byte ptr [r15+3Fh], 1
0x1800647cb  jz      short loc_1800647D4
0x1800647cd  cmp     [r15+36h], ax
0x1800647d2  jg      short loc_1800647E7
0x1800647d4  mov     rdx, r15
0x1800647d7  mov     rcx, rsi
0x1800647da  call    viewGetColumnNames
0x1800647df  test    eax, eax
0x1800647e1  jnz     loc_180064ACD
0x1800647e7  cmp     byte ptr [r15+3Fh], 1
0x1800647ec  jnz     short loc_18006481E
0x1800647ee  mov     rdx, [r15+50h]
0x1800647f2  test    rdx, rdx
0x1800647f5  jz      short loc_180064805
0x1800647f7  cmp     [rdx], rbx
0x1800647fa  jz      short loc_180064805
0x1800647fc  mov     rdx, [rdx+28h]
0x180064800  test    rdx, rdx
0x180064803  jnz     short loc_1800647F7
0x180064805  mov     rax, [rdx+10h]
0x180064809  mov     rcx, [rax]
0x18006480c  xor     eax, eax
0x18006480e  cmp     [rcx+98h], rax
0x180064815  cmovnz  rax, rdx
0x180064819  mov     [rsp+88h+var_48], rax
0x18006481e  mov     r14, [rsi+10h]
0x180064822  test    r14, r14
0x180064825  jnz     short loc_180064851
0x180064827  cmp     [rsi+0A8h], r14
0x18006482e  jnz     short loc_18006483D
0x180064830  mov     rax, [rsi]
0x180064833  test    byte ptr [rax+60h], 8
0x180064837  jnz     short loc_18006483D
0x180064839  mov     byte ptr [rsi+23h], 1
0x18006483d  mov     rcx, rsi
0x180064840  call    sqlite3VdbeCreate
0x180064845  mov     r14, rax
0x180064848  test    rax, rax
0x18006484b  jz      loc_180064ACD
0x180064851  mov     rax, [rsi+0A8h]
0x180064858  mov     rcx, rsi
0x18006485b  test    rax, rax
0x18006485e  cmovnz  rcx, rax
0x180064862  xor     r12d, r12d
0x180064865  mov     byte ptr [rcx+21h], 1
0x180064869  mov     rcx, [r15]
0x18006486c  mov     [rsp+88h+arg_0], rcx
0x180064874  mov     rax, rcx
0x180064877  cmp     [rcx], r12b
0x18006487a  jz      short loc_1800648BF
0x18006487c  nop     dword ptr [rax+00h]
0x180064880  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064884  jnb     short loc_1800648B7
0x180064886  movzx   ecx, byte ptr [rax]
0x180064889  inc     rax
0x18006488c  cmp     cl, 0C0h
0x18006488f  jb      short loc_1800648AF
0x180064891  movzx   ecx, byte ptr [rax]
0x180064894  and     cl, 0C0h
0x180064897  cmp     cl, 80h
0x18006489a  jnz     short loc_1800648AF
0x18006489c  nop     dword ptr [rax+00h]
0x1800648a0  movzx   ecx, byte ptr [rax+1]
0x1800648a4  inc     rax
0x1800648a7  and     cl, 0C0h
0x1800648aa  cmp     cl, 80h
0x1800648ad  jz      short loc_1800648A0
0x1800648af  inc     r12d
0x1800648b2  cmp     byte ptr [rax], 0
0x1800648b5  jnz     short loc_180064880
0x1800648b7  mov     rcx, [rsp+88h+arg_0]
0x1800648bf  mov     r9, [rsp+88h+arg_18]
0x1800648c7  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1800648ce  mov     [rsp+88h+var_50], rcx
0x1800648d3  xor     r13d, r13d
0x1800648d6  cmp     ebp, 1
0x1800648d9  mov     r8, r9
0x1800648dc  setz    r13b
0x1800648e0  mov     dword ptr [rsp+88h+var_58], r13d
0x1800648e5  mov     [rsp+88h+var_60], rdi
0x1800648ea  mov     [rsp+88h+var_68], rcx
0x1800648ef  mov     rcx, rsi
0x1800648f2  call    sqlite3NestedParse
0x1800648f7  mov     rax, [rsp+88h+arg_0]
0x1800648ff  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x180064906  mov     [rsp+88h+var_50], rax
0x18006490b  mov     r9, rdi
0x18006490e  mov     dword ptr [rsp+88h+var_58], r12d
0x180064913  mov     rcx, rsi
0x180064916  mov     r12, [rsp+88h+arg_18]
0x18006491e  mov     r8, r12
0x180064921  mov     [rsp+88h+var_60], rdi
0x180064926  mov     [rsp+88h+var_68], rdi
0x18006492b  call    sqlite3NestedParse
0x180064930  mov     r8, r12
0x180064933  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x18006493a  mov     rcx, rbx
0x18006493d  call    sqlite3FindTable
0x180064942  test    rax, rax
0x180064945  jz      short loc_180064964
0x180064947  mov     rax, [r15]
0x18006494a  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x180064951  mov     r9, rdi
0x180064954  mov     [rsp+88h+var_68], rax
0x180064959  mov     r8, r12
0x18006495c  mov     rcx, rsi
0x18006495f  call    sqlite3NestedParse
0x180064964  cmp     ebp, 1
0x180064967  jz      short loc_18006499A
0x180064969  mov     rax, [rsp+88h+arg_0]
0x180064971  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x180064978  mov     [rsp+88h+var_50], rdi
0x18006497d  mov     r9, rax
0x180064980  mov     [rsp+88h+var_58], r12
0x180064985  mov     r8, r12
0x180064988  mov     [rsp+88h+var_60], rax
0x18006498d  mov     rcx, rsi
0x180064990  mov     [rsp+88h+var_68], rdi
0x180064995  call    sqlite3NestedParse
0x18006499a  mov     r12, [rsp+88h+var_48]
0x18006499f  test    r12, r12
0x1800649a2  jz      loc_180064A77
0x1800649a8  inc     dword ptr [rsi+38h]
0x1800649ab  mov     r8, rdi
0x1800649ae  mov     r15d, [rsi+38h]
0x1800649b2  mov     rcx, r14
0x1800649b5  mov     edx, r15d
0x1800649b8  call    sqlite3VdbeLoadString
0x1800649bd  movsxd  r9, dword ptr [r14+90h]
0x1800649c4  cmp     [r14+94h], r9d
0x1800649cb  jg      short loc_1800649F4
0x1800649cd  xor     r9d, r9d
0x1800649d0  mov     dword ptr [rsp+88h+var_68], 0
0x1800649d8  mov     r8d, r15d
0x1800649db  mov     edx, 0B0h
0x1800649e0  mov     rcx, r14
0x1800649e3  call    growOp3
0x1800649e8  mov     r9d, eax
0x1800649eb  lea     r8, [r14+88h]
0x1800649f2  jmp     short loc_180064A27
0x1800649f4  lea     eax, [r9+1]
0x1800649f8  mov     [r14+90h], eax
0x1800649ff  lea     rcx, [r9+r9*2]
0x180064a03  lea     r8, [r14+88h]
0x180064a0a  mov     rax, [r8]
0x180064a0d  mov     dword ptr [rax+rcx*8], 0B0h
0x180064a14  mov     [rax+rcx*8+4], r15d
0x180064a19  lea     rdx, [rax+rcx*8]
0x180064a1d  xor     ecx, ecx
0x180064a1f  mov     [rdx+8], rcx
0x180064a23  mov     [rdx+10h], rcx
0x180064a27  mov     rax, [r14]
0x180064a2a  cmp     byte ptr [rax+67h], 0
0x180064a2e  jnz     short loc_180064A77
0x180064a30  test    r9d, r9d
0x180064a33  jns     short loc_180064A3F
0x180064a35  mov     r9d, [r14+90h]
0x180064a3c  dec     r9d
0x180064a3f  movsxd  rax, r9d
0x180064a42  lea     rdx, [rax+rax*2]
0x180064a46  mov     rax, [r8]
0x180064a49  cmp     byte ptr [rax+rdx*8+1], 0
0x180064a4e  lea     rcx, [rax+rdx*8]
0x180064a52  jz      short loc_180064A6A
0x180064a54  mov     rdx, rcx
0x180064a57  mov     r9d, 0FFFFFFF5h
0x180064a5d  mov     rcx, r14
0x180064a60  mov     r8, r12
0x180064a63  call    vdbeChangeP4Full
0x180064a68  jmp     short loc_180064A77
0x180064a6a  mov     [rcx+10h], r12
0x180064a6e  mov     byte ptr [rcx+1], 0F5h
0x180064a72  inc     dword ptr [r12+18h]
0x180064a77  mov     r8d, 1
0x180064a7d  mov     edx, ebp
0x180064a7f  mov     rcx, rsi
0x180064a82  call    renameReloadSchema
0x180064a87  mov     rdx, [rsp+88h+arg_18]
0x180064a8f  lea     r9, aAfterRename; "after rename"
  ... truncated ...
```
