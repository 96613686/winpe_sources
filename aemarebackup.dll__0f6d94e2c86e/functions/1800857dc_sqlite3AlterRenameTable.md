# sqlite3AlterRenameTable

- ea: `0x1800857dc`
- end: `0x180085b5c`
- name: `sqlite3AlterRenameTable`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800de91c`

## callees

- `0x18006be34`
- `0x18007e600`
- `0x18007f174`
- `0x1800857dc`
- `0x18008662c`
- `0x18008ade4`
- `0x18008e6ac`
- `0x180090934`
- `0x180095678`
- `0x180095700`
- `0x180099e6c`
- `0x18009c26c`
- `0x18009d07c`
- `0x18009dccc`
- `0x18009dcfc`
- `0x1800a9f20`
- `0x1800adbf0`
- `0x1800ae110`
- `0x1800ae518`
- `0x1800b6198`
- `0x1800d1b70`

## string_xrefs

- `0x180085b15`: `there is already another table or index with this name: %s`
- `0x1800859ff`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x1800859c2`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x180085a41`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x180085af6`: `after rename`
- `0x180085a69`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`

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
              if ( a1[21] )
                v16 = (__int64 *)a1[21];
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
                v20 = sqlite3VdbeAddOp3(Vdbe, 176, v19, 0, 0);
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
0x1800857dc  mov     rax, rsp
0x1800857df  mov     [rax+18h], rbx
0x1800857e3  mov     [rax+10h], rdx
0x1800857e7  push    rbp
0x1800857e8  push    rsi
0x1800857e9  push    rdi
0x1800857ea  push    r12
0x1800857ec  push    r13
0x1800857ee  push    r14
0x1800857f0  push    r15
0x1800857f2  sub     rsp, 50h
0x1800857f6  mov     rbp, [rcx]
0x1800857f9  xor     r13d, r13d
0x1800857fc  mov     rbx, r8
0x1800857ff  mov     rdi, rcx
0x180085802  mov     esi, r13d
0x180085805  cmp     [rbp+67h], r13b
0x180085809  jnz     loc_180085B24
0x18008580f  mov     r8, rdx
0x180085812  xor     edx, edx
0x180085814  add     r8, 8
0x180085818  call    sqlite3LocateTableItem
0x18008581d  mov     r14, rax
0x180085820  test    rax, rax
0x180085823  jz      loc_180085B24
0x180085829  mov     rcx, [rax+60h]
0x18008582d  mov     r15d, 0FFFF8000h
0x180085833  test    rcx, rcx
0x180085836  jz      short loc_180085859
0x180085838  mov     rax, [rdi]
0x18008583b  mov     r15d, r13d
0x18008583e  mov     rdx, [rax+20h]
0x180085842  cmp     [rdx+18h], rcx
0x180085846  jz      short loc_180085859
0x180085848  inc     r15d
0x18008584b  movsxd  rax, r15d
0x18008584e  shl     rax, 5
0x180085852  cmp     [rax+rdx+18h], rcx
0x180085857  jnz     short loc_180085848
0x180085859  mov     rax, [rbp+20h]
0x18008585d  mov     rdx, rbx
0x180085860  movsxd  rcx, r15d
0x180085863  shl     rcx, 5
0x180085867  mov     r12, [rcx+rax]
0x18008586b  mov     rcx, rbp
0x18008586e  call    sqlite3NameFromToken
0x180085873  mov     rsi, rax
0x180085876  test    rax, rax
0x180085879  jz      loc_180085B24
0x18008587f  mov     r8, r12
0x180085882  mov     rdx, rax
0x180085885  mov     rcx, rbp
0x180085888  call    sqlite3FindTable
0x18008588d  test    rax, rax
0x180085890  jnz     loc_180085B12
0x180085896  mov     r8, r12
0x180085899  mov     rdx, rsi
0x18008589c  mov     rcx, rbp
0x18008589f  call    sqlite3FindIndex
0x1800858a4  test    rax, rax
0x1800858a7  jnz     loc_180085B12
0x1800858ad  mov     r8, rsi
0x1800858b0  mov     rdx, r14
0x1800858b3  mov     rcx, rbp
0x1800858b6  call    sqlite3IsShadowTableOf
0x1800858bb  test    eax, eax
0x1800858bd  jnz     loc_180085B12
0x1800858c3  mov     rdx, r14
0x1800858c6  mov     rcx, rdi
0x1800858c9  call    isAlterableTable
0x1800858ce  test    eax, eax
0x1800858d0  jnz     loc_180085B24
0x1800858d6  mov     r9, rsi
0x1800858d9  lea     r8, aTable; "table"
0x1800858e0  mov     rdx, rsi
0x1800858e3  mov     rcx, rdi
0x1800858e6  call    sqlite3CheckObjectName
0x1800858eb  test    eax, eax
0x1800858ed  jnz     loc_180085B24
0x1800858f3  cmp     byte ptr [r14+3Fh], 2
0x1800858f8  mov     rcx, rdi
0x1800858fb  mov     r9, [r14]
0x1800858fe  jnz     short loc_18008590F
0x180085900  mov     r8, r9
0x180085903  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x18008590a  jmp     loc_180085B1F
0x18008590f  mov     r8, r12
0x180085912  mov     [rsp+88h+var_68], r13
0x180085917  mov     edx, 1Ah
0x18008591c  call    sqlite3AuthCheck
0x180085921  test    eax, eax
0x180085923  jnz     loc_180085B24
0x180085929  cmp     byte ptr [r14+3Fh], 1
0x18008592e  jz      short loc_180085937
0x180085930  cmp     [r14+36h], r13w
0x180085935  jg      short loc_18008594A
0x180085937  mov     rdx, r14
0x18008593a  mov     rcx, rdi
0x18008593d  call    viewGetColumnNames
0x180085942  test    eax, eax
0x180085944  jnz     loc_180085B24
0x18008594a  cmp     byte ptr [r14+3Fh], 1
0x18008594f  jnz     short loc_18008597C
0x180085951  mov     rdx, [r14+50h]
0x180085955  jmp     short loc_180085960
0x180085957  cmp     [rdx], rbp
0x18008595a  jz      short loc_180085965
0x18008595c  mov     rdx, [rdx+28h]
0x180085960  test    rdx, rdx
0x180085963  jnz     short loc_180085957
0x180085965  mov     rax, [rdx+10h]
0x180085969  mov     rcx, [rax]
0x18008596c  mov     rax, [rcx+98h]
0x180085973  neg     rax
0x180085976  sbb     r13, r13
0x180085979  and     r13, rdx
0x18008597c  mov     rcx, rdi
0x18008597f  call    sqlite3GetVdbe
0x180085984  mov     [rsp+88h+var_48], rax
0x180085989  test    rax, rax
0x18008598c  jz      loc_180085B24
0x180085992  mov     rcx, [rdi+0A8h]
0x180085999  mov     rdx, rdi
0x18008599c  test    rcx, rcx
0x18008599f  cmovnz  rdx, rcx
0x1800859a3  mov     byte ptr [rdx+21h], 1
0x1800859a7  or      edx, 0FFFFFFFFh
0x1800859aa  mov     r11, [r14]
0x1800859ad  mov     rcx, r11
0x1800859b0  mov     [rsp+88h+arg_18], r11
0x1800859b8  call    sqlite3Utf8CharLen
0x1800859bd  mov     [rsp+88h+var_50], r11
0x1800859c2  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1800859c9  mov     ebx, eax
0x1800859cb  mov     r9, r12
0x1800859ce  xor     eax, eax
0x1800859d0  mov     r8, r12
0x1800859d3  cmp     r15d, 1
0x1800859d7  mov     rcx, rdi
0x1800859da  setz    al
0x1800859dd  mov     dword ptr [rsp+88h+var_58], eax
0x1800859e1  mov     [rsp+88h+var_60], rsi
0x1800859e6  mov     [rsp+88h+var_68], r11
0x1800859eb  mov     [rsp+88h+arg_0], eax
0x1800859f2  call    sqlite3NestedParse
0x1800859f7  mov     rax, [rsp+88h+arg_18]
0x1800859ff  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x180085a06  mov     [rsp+88h+var_50], rax
0x180085a0b  mov     r9, rsi
0x180085a0e  mov     dword ptr [rsp+88h+var_58], ebx
0x180085a12  mov     r8, r12
0x180085a15  mov     [rsp+88h+var_60], rsi
0x180085a1a  mov     rcx, rdi
0x180085a1d  mov     [rsp+88h+var_68], rsi
0x180085a22  call    sqlite3NestedParse
0x180085a27  mov     r8, r12
0x180085a2a  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x180085a31  mov     rcx, rbp
0x180085a34  call    sqlite3FindTable
0x180085a39  test    rax, rax
0x180085a3c  jz      short loc_180085A5B
0x180085a3e  mov     rax, [r14]
0x180085a41  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x180085a48  mov     r9, rsi
0x180085a4b  mov     [rsp+88h+var_68], rax
0x180085a50  mov     r8, r12
0x180085a53  mov     rcx, rdi
0x180085a56  call    sqlite3NestedParse
0x180085a5b  cmp     r15d, 1
0x180085a5f  jz      short loc_180085A92
0x180085a61  mov     rax, [rsp+88h+arg_18]
0x180085a69  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x180085a70  mov     [rsp+88h+var_50], rsi
0x180085a75  mov     r9, rax
0x180085a78  mov     [rsp+88h+var_58], r12
0x180085a7d  mov     r8, r12
0x180085a80  mov     [rsp+88h+var_60], rax
0x180085a85  mov     rcx, rdi
0x180085a88  mov     [rsp+88h+var_68], rsi
0x180085a8d  call    sqlite3NestedParse
0x180085a92  test    r13, r13
0x180085a95  jz      short loc_180085ADD
0x180085a97  inc     dword ptr [rdi+38h]
0x180085a9a  mov     r8, rsi
0x180085a9d  mov     ebx, [rdi+38h]
0x180085aa0  mov     edx, ebx
0x180085aa2  mov     r14, [rsp+88h+var_48]
0x180085aa7  mov     rcx, r14
0x180085aaa  call    sqlite3VdbeLoadString
0x180085aaf  xor     r9d, r9d
0x180085ab2  mov     dword ptr [rsp+88h+var_68], 0
0x180085aba  mov     r8d, ebx
0x180085abd  mov     edx, 0B0h
0x180085ac2  mov     rcx, r14
0x180085ac5  call    sqlite3VdbeAddOp3
0x180085aca  mov     r9d, 0FFFFFFF5h
0x180085ad0  mov     r8, r13
0x180085ad3  mov     edx, eax
0x180085ad5  mov     rcx, r14
0x180085ad8  call    sqlite3VdbeChangeP4
0x180085add  mov     r8d, 1
0x180085ae3  mov     edx, r15d
0x180085ae6  mov     rcx, rdi
0x180085ae9  call    renameReloadSchema
0x180085aee  mov     r8d, [rsp+88h+arg_0]
0x180085af6  lea     r9, aAfterRename; "after rename"
0x180085afd  xor     r13d, r13d
0x180085b00  mov     rdx, r12
0x180085b03  mov     rcx, rdi
0x180085b06  mov     dword ptr [rsp+88h+var_68], r13d
0x180085b0b  call    renameTestSchema
0x180085b10  jmp     short loc_180085B24
0x180085b12  mov     r8, rsi
0x180085b15  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x180085b1c  mov     rcx, rdi
0x180085b1f  call    sqlite3ErrorMsg
0x180085b24  mov     rdx, [rsp+88h+arg_8]
0x180085b2c  mov     rcx, rbp
0x180085b2f  call    sqlite3SrcListDelete
0x180085b34  test    rsi, rsi
0x180085b37  jz      short loc_180085B44
0x180085b39  mov     rdx, rsi
0x180085b3c  mov     rcx, rbp
0x180085b3f  call    sqlite3DbFreeNN
0x180085b44  mov     rbx, [rsp+88h+arg_10]
0x180085b4c  add     rsp, 50h
0x180085b50  pop     r15
0x180085b52  pop     r14
0x180085b54  pop     r13
0x180085b56  pop     r12
0x180085b58  pop     rdi
0x180085b59  pop     rsi
0x180085b5a  pop     rbp
0x180085b5b  retn
```
