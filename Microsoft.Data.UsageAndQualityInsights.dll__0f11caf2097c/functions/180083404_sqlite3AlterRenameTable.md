# sqlite3AlterRenameTable

- ea: `0x180083404`
- end: `0x180083784`
- name: `sqlite3AlterRenameTable`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800dea88`

## callees

- `0x180067414`
- `0x18007bef0`
- `0x18007ca64`
- `0x180083404`
- `0x180084260`
- `0x180088a4c`
- `0x18008c5ac`
- `0x18008e99c`
- `0x180093a9c`
- `0x180093b24`
- `0x180098328`
- `0x18009a80c`
- `0x18009b624`
- `0x18009c604`
- `0x18009c6a4`
- `0x1800a8fd4`
- `0x1800accf4`
- `0x1800ad288`
- `0x1800ad690`
- `0x1800b5618`
- `0x1800d18f0`

## string_xrefs

- `0x18008373d`: `there is already another table or index with this name: %s`
- `0x180083627`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x1800835ea`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x180083669`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x18008371e`: `after rename`
- `0x180083691`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`

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
0x180083404  mov     rax, rsp
0x180083407  mov     [rax+18h], rbx
0x18008340b  mov     [rax+10h], rdx
0x18008340f  push    rbp
0x180083410  push    rsi
0x180083411  push    rdi
0x180083412  push    r12
0x180083414  push    r13
0x180083416  push    r14
0x180083418  push    r15
0x18008341a  sub     rsp, 50h
0x18008341e  mov     rbp, [rcx]
0x180083421  xor     r13d, r13d
0x180083424  mov     rbx, r8
0x180083427  mov     rdi, rcx
0x18008342a  mov     esi, r13d
0x18008342d  cmp     [rbp+67h], r13b
0x180083431  jnz     loc_18008374C
0x180083437  mov     r8, rdx
0x18008343a  xor     edx, edx
0x18008343c  add     r8, 8
0x180083440  call    sqlite3LocateTableItem
0x180083445  mov     r14, rax
0x180083448  test    rax, rax
0x18008344b  jz      loc_18008374C
0x180083451  mov     rcx, [rax+60h]
0x180083455  mov     r15d, 0FFFF8000h
0x18008345b  test    rcx, rcx
0x18008345e  jz      short loc_180083481
0x180083460  mov     rax, [rdi]
0x180083463  mov     r15d, r13d
0x180083466  mov     rdx, [rax+20h]
0x18008346a  cmp     [rdx+18h], rcx
0x18008346e  jz      short loc_180083481
0x180083470  inc     r15d
0x180083473  movsxd  rax, r15d
0x180083476  shl     rax, 5
0x18008347a  cmp     [rax+rdx+18h], rcx
0x18008347f  jnz     short loc_180083470
0x180083481  mov     rax, [rbp+20h]
0x180083485  mov     rdx, rbx
0x180083488  movsxd  rcx, r15d
0x18008348b  shl     rcx, 5
0x18008348f  mov     r12, [rcx+rax]
0x180083493  mov     rcx, rbp
0x180083496  call    sqlite3NameFromToken
0x18008349b  mov     rsi, rax
0x18008349e  test    rax, rax
0x1800834a1  jz      loc_18008374C
0x1800834a7  mov     r8, r12
0x1800834aa  mov     rdx, rax
0x1800834ad  mov     rcx, rbp
0x1800834b0  call    sqlite3FindTable
0x1800834b5  test    rax, rax
0x1800834b8  jnz     loc_18008373A
0x1800834be  mov     r8, r12
0x1800834c1  mov     rdx, rsi
0x1800834c4  mov     rcx, rbp
0x1800834c7  call    sqlite3FindIndex
0x1800834cc  test    rax, rax
0x1800834cf  jnz     loc_18008373A
0x1800834d5  mov     r8, rsi
0x1800834d8  mov     rdx, r14
0x1800834db  mov     rcx, rbp
0x1800834de  call    sqlite3IsShadowTableOf
0x1800834e3  test    eax, eax
0x1800834e5  jnz     loc_18008373A
0x1800834eb  mov     rdx, r14
0x1800834ee  mov     rcx, rdi
0x1800834f1  call    isAlterableTable
0x1800834f6  test    eax, eax
0x1800834f8  jnz     loc_18008374C
0x1800834fe  mov     r9, rsi
0x180083501  lea     r8, aTable; "table"
0x180083508  mov     rdx, rsi
0x18008350b  mov     rcx, rdi
0x18008350e  call    sqlite3CheckObjectName
0x180083513  test    eax, eax
0x180083515  jnz     loc_18008374C
0x18008351b  cmp     byte ptr [r14+3Fh], 2
0x180083520  mov     rcx, rdi
0x180083523  mov     r9, [r14]
0x180083526  jnz     short loc_180083537
0x180083528  mov     r8, r9
0x18008352b  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x180083532  jmp     loc_180083747
0x180083537  mov     r8, r12
0x18008353a  mov     [rsp+88h+var_68], r13
0x18008353f  mov     edx, 1Ah
0x180083544  call    sqlite3AuthCheck
0x180083549  test    eax, eax
0x18008354b  jnz     loc_18008374C
0x180083551  cmp     byte ptr [r14+3Fh], 1
0x180083556  jz      short loc_18008355F
0x180083558  cmp     [r14+36h], r13w
0x18008355d  jg      short loc_180083572
0x18008355f  mov     rdx, r14
0x180083562  mov     rcx, rdi
0x180083565  call    viewGetColumnNames
0x18008356a  test    eax, eax
0x18008356c  jnz     loc_18008374C
0x180083572  cmp     byte ptr [r14+3Fh], 1
0x180083577  jnz     short loc_1800835A4
0x180083579  mov     rdx, [r14+50h]
0x18008357d  jmp     short loc_180083588
0x18008357f  cmp     [rdx], rbp
0x180083582  jz      short loc_18008358D
0x180083584  mov     rdx, [rdx+28h]
0x180083588  test    rdx, rdx
0x18008358b  jnz     short loc_18008357F
0x18008358d  mov     rax, [rdx+10h]
0x180083591  mov     rcx, [rax]
0x180083594  mov     rax, [rcx+98h]
0x18008359b  neg     rax
0x18008359e  sbb     r13, r13
0x1800835a1  and     r13, rdx
0x1800835a4  mov     rcx, rdi
0x1800835a7  call    sqlite3GetVdbe
0x1800835ac  mov     [rsp+88h+var_48], rax
0x1800835b1  test    rax, rax
0x1800835b4  jz      loc_18008374C
0x1800835ba  mov     rcx, [rdi+0B0h]
0x1800835c1  mov     rdx, rdi
0x1800835c4  test    rcx, rcx
0x1800835c7  cmovnz  rdx, rcx
0x1800835cb  mov     byte ptr [rdx+21h], 1
0x1800835cf  or      edx, 0FFFFFFFFh
0x1800835d2  mov     r11, [r14]
0x1800835d5  mov     rcx, r11
0x1800835d8  mov     [rsp+88h+arg_18], r11
0x1800835e0  call    sqlite3Utf8CharLen
0x1800835e5  mov     [rsp+88h+var_50], r11
0x1800835ea  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1800835f1  mov     ebx, eax
0x1800835f3  mov     r9, r12
0x1800835f6  xor     eax, eax
0x1800835f8  mov     r8, r12
0x1800835fb  cmp     r15d, 1
0x1800835ff  mov     rcx, rdi
0x180083602  setz    al
0x180083605  mov     dword ptr [rsp+88h+var_58], eax
0x180083609  mov     [rsp+88h+var_60], rsi
0x18008360e  mov     [rsp+88h+var_68], r11
0x180083613  mov     [rsp+88h+arg_0], eax
0x18008361a  call    sqlite3NestedParse
0x18008361f  mov     rax, [rsp+88h+arg_18]
0x180083627  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x18008362e  mov     [rsp+88h+var_50], rax
0x180083633  mov     r9, rsi
0x180083636  mov     dword ptr [rsp+88h+var_58], ebx
0x18008363a  mov     r8, r12
0x18008363d  mov     [rsp+88h+var_60], rsi
0x180083642  mov     rcx, rdi
0x180083645  mov     [rsp+88h+var_68], rsi
0x18008364a  call    sqlite3NestedParse
0x18008364f  mov     r8, r12
0x180083652  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x180083659  mov     rcx, rbp
0x18008365c  call    sqlite3FindTable
0x180083661  test    rax, rax
0x180083664  jz      short loc_180083683
0x180083666  mov     rax, [r14]
0x180083669  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x180083670  mov     r9, rsi
0x180083673  mov     [rsp+88h+var_68], rax
0x180083678  mov     r8, r12
0x18008367b  mov     rcx, rdi
0x18008367e  call    sqlite3NestedParse
0x180083683  cmp     r15d, 1
0x180083687  jz      short loc_1800836BA
0x180083689  mov     rax, [rsp+88h+arg_18]
0x180083691  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x180083698  mov     [rsp+88h+var_50], rsi
0x18008369d  mov     r9, rax
0x1800836a0  mov     [rsp+88h+var_58], r12
0x1800836a5  mov     r8, r12
0x1800836a8  mov     [rsp+88h+var_60], rax
0x1800836ad  mov     rcx, rdi
0x1800836b0  mov     [rsp+88h+var_68], rsi
0x1800836b5  call    sqlite3NestedParse
0x1800836ba  test    r13, r13
0x1800836bd  jz      short loc_180083705
0x1800836bf  inc     dword ptr [rdi+38h]
0x1800836c2  mov     r8, rsi
0x1800836c5  mov     ebx, [rdi+38h]
0x1800836c8  mov     edx, ebx
0x1800836ca  mov     r14, [rsp+88h+var_48]
0x1800836cf  mov     rcx, r14
0x1800836d2  call    sqlite3VdbeLoadString
0x1800836d7  xor     r9d, r9d
0x1800836da  mov     dword ptr [rsp+88h+var_68], 0
0x1800836e2  mov     r8d, ebx
0x1800836e5  mov     edx, 0B1h
0x1800836ea  mov     rcx, r14
0x1800836ed  call    sqlite3VdbeAddOp3
0x1800836f2  mov     r9d, 0FFFFFFF5h
0x1800836f8  mov     r8, r13
0x1800836fb  mov     edx, eax
0x1800836fd  mov     rcx, r14
0x180083700  call    sqlite3VdbeChangeP4
0x180083705  mov     r8d, 1
0x18008370b  mov     edx, r15d
0x18008370e  mov     rcx, rdi
0x180083711  call    renameReloadSchema
0x180083716  mov     r8d, [rsp+88h+arg_0]
0x18008371e  lea     r9, aAfterRename; "after rename"
0x180083725  xor     r13d, r13d
0x180083728  mov     rdx, r12
0x18008372b  mov     rcx, rdi
0x18008372e  mov     dword ptr [rsp+88h+var_68], r13d
0x180083733  call    renameTestSchema
0x180083738  jmp     short loc_18008374C
0x18008373a  mov     r8, rsi
0x18008373d  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x180083744  mov     rcx, rdi
0x180083747  call    sqlite3ErrorMsg
0x18008374c  mov     rdx, [rsp+88h+arg_8]
0x180083754  mov     rcx, rbp
0x180083757  call    sqlite3SrcListDelete
0x18008375c  test    rsi, rsi
0x18008375f  jz      short loc_18008376C
0x180083761  mov     rdx, rsi
0x180083764  mov     rcx, rbp
0x180083767  call    sqlite3DbFreeNN
0x18008376c  mov     rbx, [rsp+88h+arg_10]
0x180083774  add     rsp, 50h
0x180083778  pop     r15
0x18008377a  pop     r14
0x18008377c  pop     r13
0x18008377e  pop     r12
0x180083780  pop     rdi
0x180083781  pop     rsi
0x180083782  pop     rbp
0x180083783  retn
```
