# sqlite3AlterRenameTable

- ea: `0x180068554`
- end: `0x1800688d4`
- name: `sqlite3AlterRenameTable`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800c3bd8`

## callees

- `0x18004c564`
- `0x180061040`
- `0x180061bb4`
- `0x180068554`
- `0x1800693b0`
- `0x18006db9c`
- `0x1800716fc`
- `0x180073aec`
- `0x180078bec`
- `0x180078c74`
- `0x18007d478`
- `0x18007f95c`
- `0x180080774`
- `0x180081754`
- `0x1800817f4`
- `0x18008e124`
- `0x180091e44`
- `0x1800923d8`
- `0x1800927e0`
- `0x18009a768`
- `0x1800b6a40`

## string_xrefs

- `0x18006873a`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x18006888d`: `there is already another table or index with this name: %s`
- `0x1800687b9`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x1800687e1`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x180068777`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x18006886e`: `after rename`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameTable(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v4; // r13
  __int64 v7; // rsi
  __int64 TableItem; // rax
  _QWORD *v9; // r14
  __int64 v10; // rcx
  int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 i; // rdx
  __int64 *v16; // rdx
  int v17; // ebx
  __int64 v18; // r11
  unsigned int v19; // ebx
  unsigned int v20; // eax
  __int64 result; // rax
  __int64 v22; // [rsp+30h] [rbp-58h]
  __int64 Vdbe; // [rsp+40h] [rbp-48h]
  __int64 v25; // [rsp+A8h] [rbp+20h]

  v3 = *a1;
  v4 = 0;
  v7 = 0;
  if ( !*(_BYTE *)(*a1 + 103) )
  {
    TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
    v9 = (_QWORD *)TableItem;
    if ( TableItem )
    {
      v10 = *(_QWORD *)(TableItem + 96);
      v11 = -32768;
      if ( v10 )
      {
        v11 = 0;
        v12 = *(_QWORD *)(*a1 + 32);
        if ( *(_QWORD *)(v12 + 24) != v10 )
        {
          do
            ++v11;
          while ( *(_QWORD *)(32LL * v11 + v12 + 24) != v10 );
        }
      }
      v13 = *(_QWORD *)(32LL * v11 + *(_QWORD *)(v3 + 32));
      v14 = sqlite3NameFromToken(v3, a3);
      v7 = v14;
      if ( v14 )
      {
        if ( sqlite3FindTable(v3, v14, v13)
          || sqlite3FindIndex(v3, v7, v13)
          || (unsigned int)sqlite3IsShadowTableOf(v3, v9, v7) )
        {
          sqlite3ErrorMsg(a1, "there is already another table or index with this name: %s", v7);
        }
        else if ( !(unsigned int)isAlterableTable(a1, v9) && !(unsigned int)sqlite3CheckObjectName(a1, v7, "table", v7) )
        {
          if ( *((_BYTE *)v9 + 63) == 2 )
          {
            sqlite3ErrorMsg(a1, "view %s may not be altered", *v9);
          }
          else if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v13, *v9, 0)
                 && (*((_BYTE *)v9 + 63) != 1 && *((__int16 *)v9 + 27) > 0 || !(unsigned int)viewGetColumnNames(a1, v9)) )
          {
            if ( *((_BYTE *)v9 + 63) == 1 )
            {
              for ( i = v9[10]; i && *(_QWORD *)i != v3; i = *(_QWORD *)(i + 40) )
                ;
              v4 = i & -(__int64)(*(_QWORD *)(**(_QWORD **)(i + 16) + 152LL) != 0);
            }
            Vdbe = sqlite3GetVdbe(a1);
            if ( Vdbe )
            {
              v16 = a1;
              if ( a1[22] )
                v16 = (__int64 *)a1[22];
              *((_BYTE *)v16 + 33) = 1;
              v25 = *v9;
              v17 = sqlite3Utf8CharLen(*v9, 0xFFFFFFFFLL);
              sqlite3NestedParse(
                a1,
                "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!="
                "'index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'",
                v13,
                v13,
                v18,
                v7,
                v11 == 1,
                v18);
              LODWORD(v22) = v17;
              sqlite3NestedParse(
                a1,
                "UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX"
                "_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE"
                " name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');",
                v13,
                v7,
                v7,
                v7,
                v22,
                v25);
              if ( sqlite3FindTable(v3, "sqlite_sequence", v13) )
                sqlite3NestedParse(a1, "UPDATE \"%w\".sqlite_sequence set name = %Q WHERE name = %Q", v13, v7, *v9);
              if ( v11 != 1 )
                sqlite3NestedParse(
                  a1,
                  "UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CA"
                  "SE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0)"
                  " THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')",
                  v13,
                  v25,
                  v7,
                  v25,
                  v13,
                  v7);
              if ( v4 )
              {
                v19 = ++*((_DWORD *)a1 + 14);
                sqlite3VdbeLoadString(Vdbe, v19, v7);
                v20 = sqlite3VdbeAddOp3(Vdbe, 177, v19, 0, 0);
                sqlite3VdbeChangeP4(Vdbe, v20, v4, 4294967285LL);
              }
              renameReloadSchema(a1, (unsigned int)v11, 1);
              renameTestSchema((_DWORD)a1, v13, v11 == 1, (unsigned int)"after rename", 0);
            }
          }
        }
      }
    }
  }
  result = sqlite3SrcListDelete(v3, a2);
  if ( v7 )
    return sqlite3DbFreeNN(v3);
  return result;
}

```

## disassembly

```asm
0x180068554  mov     rax, rsp
0x180068557  mov     [rax+18h], rbx
0x18006855b  mov     [rax+10h], rdx
0x18006855f  push    rbp
0x180068560  push    rsi
0x180068561  push    rdi
0x180068562  push    r12
0x180068564  push    r13
0x180068566  push    r14
0x180068568  push    r15
0x18006856a  sub     rsp, 50h
0x18006856e  mov     rbp, [rcx]
0x180068571  xor     r13d, r13d
0x180068574  mov     rbx, r8
0x180068577  mov     rdi, rcx
0x18006857a  mov     esi, r13d
0x18006857d  cmp     [rbp+67h], r13b
0x180068581  jnz     loc_18006889C
0x180068587  mov     r8, rdx
0x18006858a  xor     edx, edx
0x18006858c  add     r8, 8
0x180068590  call    sqlite3LocateTableItem
0x180068595  mov     r14, rax
0x180068598  test    rax, rax
0x18006859b  jz      loc_18006889C
0x1800685a1  mov     rcx, [rax+60h]
0x1800685a5  mov     r15d, 0FFFF8000h
0x1800685ab  test    rcx, rcx
0x1800685ae  jz      short loc_1800685D1
0x1800685b0  mov     rax, [rdi]
0x1800685b3  mov     r15d, r13d
0x1800685b6  mov     rdx, [rax+20h]
0x1800685ba  cmp     [rdx+18h], rcx
0x1800685be  jz      short loc_1800685D1
0x1800685c0  inc     r15d
0x1800685c3  movsxd  rax, r15d
0x1800685c6  shl     rax, 5
0x1800685ca  cmp     [rax+rdx+18h], rcx
0x1800685cf  jnz     short loc_1800685C0
0x1800685d1  mov     rax, [rbp+20h]
0x1800685d5  mov     rdx, rbx
0x1800685d8  movsxd  rcx, r15d
0x1800685db  shl     rcx, 5
0x1800685df  mov     r12, [rcx+rax]
0x1800685e3  mov     rcx, rbp
0x1800685e6  call    sqlite3NameFromToken
0x1800685eb  mov     rsi, rax
0x1800685ee  test    rax, rax
0x1800685f1  jz      loc_18006889C
0x1800685f7  mov     r8, r12
0x1800685fa  mov     rdx, rax
0x1800685fd  mov     rcx, rbp
0x180068600  call    sqlite3FindTable
0x180068605  test    rax, rax
0x180068608  jnz     loc_18006888A
0x18006860e  mov     r8, r12
0x180068611  mov     rdx, rsi
0x180068614  mov     rcx, rbp
0x180068617  call    sqlite3FindIndex
0x18006861c  test    rax, rax
0x18006861f  jnz     loc_18006888A
0x180068625  mov     r8, rsi
0x180068628  mov     rdx, r14
0x18006862b  mov     rcx, rbp
0x18006862e  call    sqlite3IsShadowTableOf
0x180068633  test    eax, eax
0x180068635  jnz     loc_18006888A
0x18006863b  mov     rdx, r14
0x18006863e  mov     rcx, rdi
0x180068641  call    isAlterableTable
0x180068646  test    eax, eax
0x180068648  jnz     loc_18006889C
0x18006864e  mov     r9, rsi
0x180068651  lea     r8, aTable; "table"
0x180068658  mov     rdx, rsi
0x18006865b  mov     rcx, rdi
0x18006865e  call    sqlite3CheckObjectName
0x180068663  test    eax, eax
0x180068665  jnz     loc_18006889C
0x18006866b  cmp     byte ptr [r14+3Fh], 2
0x180068670  mov     rcx, rdi
0x180068673  mov     r9, [r14]
0x180068676  jnz     short loc_180068687
0x180068678  mov     r8, r9
0x18006867b  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x180068682  jmp     loc_180068897
0x180068687  mov     r8, r12
0x18006868a  mov     [rsp+88h+var_68], r13
0x18006868f  mov     edx, 1Ah
0x180068694  call    sqlite3AuthCheck
0x180068699  test    eax, eax
0x18006869b  jnz     loc_18006889C
0x1800686a1  cmp     byte ptr [r14+3Fh], 1
0x1800686a6  jz      short loc_1800686AF
0x1800686a8  cmp     [r14+36h], r13w
0x1800686ad  jg      short loc_1800686C2
0x1800686af  mov     rdx, r14
0x1800686b2  mov     rcx, rdi
0x1800686b5  call    viewGetColumnNames
0x1800686ba  test    eax, eax
0x1800686bc  jnz     loc_18006889C
0x1800686c2  cmp     byte ptr [r14+3Fh], 1
0x1800686c7  jnz     short loc_1800686F4
0x1800686c9  mov     rdx, [r14+50h]
0x1800686cd  jmp     short loc_1800686D8
0x1800686cf  cmp     [rdx], rbp
0x1800686d2  jz      short loc_1800686DD
0x1800686d4  mov     rdx, [rdx+28h]
0x1800686d8  test    rdx, rdx
0x1800686db  jnz     short loc_1800686CF
0x1800686dd  mov     rax, [rdx+10h]
0x1800686e1  mov     rcx, [rax]
0x1800686e4  mov     rax, [rcx+98h]
0x1800686eb  neg     rax
0x1800686ee  sbb     r13, r13
0x1800686f1  and     r13, rdx
0x1800686f4  mov     rcx, rdi
0x1800686f7  call    sqlite3GetVdbe
0x1800686fc  mov     [rsp+88h+var_48], rax
0x180068701  test    rax, rax
0x180068704  jz      loc_18006889C
0x18006870a  mov     rcx, [rdi+0B0h]
0x180068711  mov     rdx, rdi
0x180068714  test    rcx, rcx
0x180068717  cmovnz  rdx, rcx
0x18006871b  mov     byte ptr [rdx+21h], 1
0x18006871f  or      edx, 0FFFFFFFFh
0x180068722  mov     r11, [r14]
0x180068725  mov     rcx, r11
0x180068728  mov     [rsp+88h+arg_18], r11
0x180068730  call    sqlite3Utf8CharLen
0x180068735  mov     [rsp+88h+var_50], r11
0x18006873a  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180068741  mov     ebx, eax
0x180068743  mov     r9, r12
0x180068746  xor     eax, eax
0x180068748  mov     r8, r12
0x18006874b  cmp     r15d, 1
0x18006874f  mov     rcx, rdi
0x180068752  setz    al
0x180068755  mov     dword ptr [rsp+88h+var_58], eax
0x180068759  mov     [rsp+88h+var_60], rsi
0x18006875e  mov     [rsp+88h+var_68], r11
0x180068763  mov     [rsp+88h+arg_0], eax
0x18006876a  call    sqlite3NestedParse
0x18006876f  mov     rax, [rsp+88h+arg_18]
0x180068777  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x18006877e  mov     [rsp+88h+var_50], rax
0x180068783  mov     r9, rsi
0x180068786  mov     dword ptr [rsp+88h+var_58], ebx
0x18006878a  mov     r8, r12
0x18006878d  mov     [rsp+88h+var_60], rsi
0x180068792  mov     rcx, rdi
0x180068795  mov     [rsp+88h+var_68], rsi
0x18006879a  call    sqlite3NestedParse
0x18006879f  mov     r8, r12
0x1800687a2  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x1800687a9  mov     rcx, rbp
0x1800687ac  call    sqlite3FindTable
0x1800687b1  test    rax, rax
0x1800687b4  jz      short loc_1800687D3
0x1800687b6  mov     rax, [r14]
0x1800687b9  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x1800687c0  mov     r9, rsi
0x1800687c3  mov     [rsp+88h+var_68], rax
0x1800687c8  mov     r8, r12
0x1800687cb  mov     rcx, rdi
0x1800687ce  call    sqlite3NestedParse
0x1800687d3  cmp     r15d, 1
0x1800687d7  jz      short loc_18006880A
0x1800687d9  mov     rax, [rsp+88h+arg_18]
0x1800687e1  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x1800687e8  mov     [rsp+88h+var_50], rsi
0x1800687ed  mov     r9, rax
0x1800687f0  mov     [rsp+88h+var_58], r12
0x1800687f5  mov     r8, r12
0x1800687f8  mov     [rsp+88h+var_60], rax
0x1800687fd  mov     rcx, rdi
0x180068800  mov     [rsp+88h+var_68], rsi
0x180068805  call    sqlite3NestedParse
0x18006880a  test    r13, r13
0x18006880d  jz      short loc_180068855
0x18006880f  inc     dword ptr [rdi+38h]
0x180068812  mov     r8, rsi
0x180068815  mov     ebx, [rdi+38h]
0x180068818  mov     edx, ebx
0x18006881a  mov     r14, [rsp+88h+var_48]
0x18006881f  mov     rcx, r14
0x180068822  call    sqlite3VdbeLoadString
0x180068827  xor     r9d, r9d
0x18006882a  mov     dword ptr [rsp+88h+var_68], 0
0x180068832  mov     r8d, ebx
0x180068835  mov     edx, 0B1h
0x18006883a  mov     rcx, r14
0x18006883d  call    sqlite3VdbeAddOp3
0x180068842  mov     r9d, 0FFFFFFF5h
0x180068848  mov     r8, r13
0x18006884b  mov     edx, eax
0x18006884d  mov     rcx, r14
0x180068850  call    sqlite3VdbeChangeP4
0x180068855  mov     r8d, 1
0x18006885b  mov     edx, r15d
0x18006885e  mov     rcx, rdi
0x180068861  call    renameReloadSchema
0x180068866  mov     r8d, [rsp+88h+arg_0]
0x18006886e  lea     r9, aAfterRename; "after rename"
0x180068875  xor     r13d, r13d
0x180068878  mov     rdx, r12
0x18006887b  mov     rcx, rdi
0x18006887e  mov     dword ptr [rsp+88h+var_68], r13d
0x180068883  call    renameTestSchema
0x180068888  jmp     short loc_18006889C
0x18006888a  mov     r8, rsi
0x18006888d  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x180068894  mov     rcx, rdi
0x180068897  call    sqlite3ErrorMsg
0x18006889c  mov     rdx, [rsp+88h+arg_8]
0x1800688a4  mov     rcx, rbp
0x1800688a7  call    sqlite3SrcListDelete
0x1800688ac  test    rsi, rsi
0x1800688af  jz      short loc_1800688BC
0x1800688b1  mov     rdx, rsi
0x1800688b4  mov     rcx, rbp
0x1800688b7  call    sqlite3DbFreeNN
0x1800688bc  mov     rbx, [rsp+88h+arg_10]
0x1800688c4  add     rsp, 50h
0x1800688c8  pop     r15
0x1800688ca  pop     r14
0x1800688cc  pop     r13
0x1800688ce  pop     r12
0x1800688d0  pop     rdi
0x1800688d1  pop     rsi
0x1800688d2  pop     rbp
0x1800688d3  retn
```
