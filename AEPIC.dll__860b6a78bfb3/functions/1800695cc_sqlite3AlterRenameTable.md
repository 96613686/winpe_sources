# sqlite3AlterRenameTable

- ea: `0x1800695cc`
- end: `0x180069927`
- name: `sqlite3AlterRenameTable`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800be9b8`

## callees

- `0x180051488`
- `0x1800629d8`
- `0x1800634b4`
- `0x1800695cc`
- `0x18006a3e8`
- `0x18006e6fc`
- `0x180071b80`
- `0x180073d2c`
- `0x18007894c`
- `0x1800789d4`
- `0x18007cd40`
- `0x18007cf80`
- `0x18007f1b0`
- `0x18007ff6c`
- `0x180080b40`
- `0x180080b70`
- `0x180089c24`
- `0x18008c384`
- `0x1800900a4`
- `0x180090740`
- `0x18009af00`

## string_xrefs

- `0x1800698eb`: `there is already another table or index with this name: %s`
- `0x18006977b`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x1800697b9`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x180069828`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x1800697fb`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x1800698c4`: `after rename`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameTable(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 v6; // rbx
  __int64 TableItem; // rax
  _QWORD *v9; // r14
  __int64 v10; // r15
  __int64 v11; // rax
  __int64 v12; // r12
  __int64 VTable; // rax
  __int64 Vdbe; // r13
  __int64 *v15; // rdx
  int v16; // ebx
  __int64 v17; // r11
  int v18; // ebx
  __int64 v20; // [rsp+30h] [rbp-58h]
  __int64 v21; // [rsp+40h] [rbp-48h]
  unsigned int v22; // [rsp+90h] [rbp+8h]

  v3 = *a1;
  v4 = 0;
  v6 = a2;
  if ( !*(_BYTE *)(*a1 + 103) )
  {
    TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
    v9 = (_QWORD *)TableItem;
    if ( TableItem )
    {
      v22 = sqlite3SchemaToIndex(*a1, *(_QWORD *)(TableItem + 96));
      v10 = *(_QWORD *)(32LL * (int)v22 + *(_QWORD *)(v3 + 32));
      v11 = sqlite3NameFromToken(v3, a3);
      v4 = v11;
      if ( v11 )
      {
        if ( sqlite3FindTable(v3, v11, v10)
          || sqlite3FindIndex(v3, v4, v10)
          || (unsigned int)sqlite3IsShadowTableOf(v3, v9, v4) )
        {
          sqlite3ErrorMsg(a1, "there is already another table or index with this name: %s", v4);
        }
        else if ( !(unsigned int)isAlterableTable(a1, v9) && !(unsigned int)sqlite3CheckObjectName(a1, v4, "table", v4) )
        {
          if ( *((_BYTE *)v9 + 63) == 2 )
          {
            sqlite3ErrorMsg(a1, "view %s may not be altered", *v9);
          }
          else if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v10, *v9, 0)
                 && !(unsigned int)sqlite3ViewGetColumnNames(a1, v9) )
          {
            v12 = 0;
            if ( *((_BYTE *)v9 + 63) == 1 )
            {
              VTable = sqlite3GetVTable(v3, v9);
              v12 = VTable & -(__int64)(*(_QWORD *)(**(_QWORD **)(VTable + 16) + 152LL) != 0);
            }
            Vdbe = sqlite3GetVdbe(a1);
            if ( Vdbe )
            {
              v15 = a1;
              if ( a1[21] )
                v15 = (__int64 *)a1[21];
              *((_BYTE *)v15 + 33) = 1;
              v21 = *v9;
              v16 = sqlite3Utf8CharLen(*v9, 0xFFFFFFFFLL);
              sqlite3NestedParse(
                a1,
                "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!="
                "'index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'",
                v10,
                v10,
                v17,
                v4,
                v22 == 1,
                v17);
              LODWORD(v20) = v16;
              sqlite3NestedParse(
                a1,
                "UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX"
                "_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE"
                " name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');",
                v10,
                v4,
                v4,
                v4,
                v20,
                v21);
              if ( sqlite3FindTable(v3, "sqlite_sequence", v10) )
                sqlite3NestedParse(a1, "UPDATE \"%w\".sqlite_sequence set name = %Q WHERE name = %Q", v10, v4, *v9);
              if ( v22 != 1 )
                sqlite3NestedParse(
                  a1,
                  "UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CA"
                  "SE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0)"
                  " THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')",
                  v10,
                  v21,
                  v4,
                  v21,
                  v10,
                  v4);
              if ( v12 )
              {
                v18 = ++*((_DWORD *)a1 + 14);
                sqlite3VdbeAddOp4(Vdbe, 117, 0, v18, 0, v4, 0);
                sqlite3VdbeAddOp4(Vdbe, 176, v18, 0, 0, v12, -11);
              }
              renameReloadSchema(a1, v22, 1);
              renameTestSchema((_DWORD)a1, v10, v22 == 1, (unsigned int)"after rename", 0);
              v6 = a2;
            }
          }
        }
      }
    }
  }
  sqlite3SrcListDelete(v3, v6);
  return sqlite3DbFree(v3, v4);
}

```

## disassembly

```asm
0x1800695cc  mov     [rsp+arg_10], rbx
0x1800695d1  mov     [rsp+arg_8], rdx
0x1800695d6  push    rbp
0x1800695d7  push    rsi
0x1800695d8  push    rdi
0x1800695d9  push    r12
0x1800695db  push    r13
0x1800695dd  push    r14
0x1800695df  push    r15
0x1800695e1  sub     rsp, 50h
0x1800695e5  mov     rbp, [rcx]
0x1800695e8  xor     esi, esi
0x1800695ea  mov     r12, r8
0x1800695ed  mov     rbx, rdx
0x1800695f0  mov     rdi, rcx
0x1800695f3  cmp     [rbp+67h], sil
0x1800695f7  jnz     loc_1800698FA
0x1800695fd  lea     r8, [rdx+8]
0x180069601  xor     edx, edx
0x180069603  call    sqlite3LocateTableItem
0x180069608  mov     r14, rax
0x18006960b  test    rax, rax
0x18006960e  jz      loc_1800698FA
0x180069614  mov     rdx, [rax+60h]
0x180069618  mov     rcx, [rdi]
0x18006961b  call    sqlite3SchemaToIndex
0x180069620  movsxd  rcx, eax
0x180069623  mov     rdx, r12
0x180069626  shl     rcx, 5
0x18006962a  mov     [rsp+88h+arg_0], eax
0x180069631  mov     rax, [rbp+20h]
0x180069635  mov     r15, [rcx+rax]
0x180069639  mov     rcx, rbp
0x18006963c  call    sqlite3NameFromToken
0x180069641  mov     rsi, rax
0x180069644  test    rax, rax
0x180069647  jz      loc_1800698FA
0x18006964d  mov     r8, r15
0x180069650  mov     rdx, rax
0x180069653  mov     rcx, rbp
0x180069656  call    sqlite3FindTable
0x18006965b  test    rax, rax
0x18006965e  jnz     loc_1800698E8
0x180069664  mov     r8, r15
0x180069667  mov     rdx, rsi
0x18006966a  mov     rcx, rbp
0x18006966d  call    sqlite3FindIndex
0x180069672  test    rax, rax
0x180069675  jnz     loc_1800698E8
0x18006967b  mov     r8, rsi
0x18006967e  mov     rdx, r14
0x180069681  mov     rcx, rbp
0x180069684  call    sqlite3IsShadowTableOf
0x180069689  test    eax, eax
0x18006968b  jnz     loc_1800698E8
0x180069691  mov     rdx, r14
0x180069694  mov     rcx, rdi
0x180069697  call    isAlterableTable
0x18006969c  test    eax, eax
0x18006969e  jnz     loc_1800698FA
0x1800696a4  mov     r9, rsi
0x1800696a7  lea     r8, aTable; "table"
0x1800696ae  mov     rdx, rsi
0x1800696b1  mov     rcx, rdi
0x1800696b4  call    sqlite3CheckObjectName
0x1800696b9  test    eax, eax
0x1800696bb  jnz     loc_1800698FA
0x1800696c1  cmp     byte ptr [r14+3Fh], 2
0x1800696c6  mov     rcx, rdi
0x1800696c9  mov     r9, [r14]
0x1800696cc  jnz     short loc_1800696DD
0x1800696ce  mov     r8, r9
0x1800696d1  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x1800696d8  jmp     loc_1800698F5
0x1800696dd  mov     r8, r15
0x1800696e0  mov     [rsp+88h+var_68], 0
0x1800696e9  mov     edx, 1Ah
0x1800696ee  call    sqlite3AuthCheck
0x1800696f3  test    eax, eax
0x1800696f5  jnz     loc_1800698FA
0x1800696fb  mov     rdx, r14
0x1800696fe  mov     rcx, rdi
0x180069701  call    sqlite3ViewGetColumnNames
0x180069706  test    eax, eax
0x180069708  jnz     loc_1800698FA
0x18006970e  xor     r12d, r12d
0x180069711  cmp     byte ptr [r14+3Fh], 1
0x180069716  jnz     short loc_18006973A
0x180069718  mov     rdx, r14
0x18006971b  mov     rcx, rbp
0x18006971e  call    sqlite3GetVTable
0x180069723  mov     rcx, [rax+10h]
0x180069727  mov     rdx, [rcx]
0x18006972a  mov     rcx, [rdx+98h]
0x180069731  neg     rcx
0x180069734  sbb     r12, r12
0x180069737  and     r12, rax
0x18006973a  mov     rcx, rdi
0x18006973d  call    sqlite3GetVdbe
0x180069742  mov     r13, rax
0x180069745  test    rax, rax
0x180069748  jz      loc_1800698FA
0x18006974e  mov     rcx, [rdi+0A8h]
0x180069755  mov     rdx, rdi
0x180069758  test    rcx, rcx
0x18006975b  cmovnz  rdx, rcx
0x18006975f  mov     byte ptr [rdx+21h], 1
0x180069763  or      edx, 0FFFFFFFFh
0x180069766  mov     r11, [r14]
0x180069769  mov     rcx, r11
0x18006976c  mov     [rsp+88h+var_48], r11
0x180069771  call    sqlite3Utf8CharLen
0x180069776  mov     [rsp+88h+var_50], r11
0x18006977b  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180069782  mov     ebx, eax
0x180069784  mov     r9, r15
0x180069787  xor     eax, eax
0x180069789  mov     r8, r15
0x18006978c  cmp     [rsp+88h+arg_0], 1
0x180069794  mov     rcx, rdi
0x180069797  setz    al
0x18006979a  mov     dword ptr [rsp+88h+var_58], eax
0x18006979e  mov     [rsp+88h+var_60], rsi
0x1800697a3  mov     [rsp+88h+var_68], r11
0x1800697a8  mov     [rsp+88h+arg_18], eax
0x1800697af  call    sqlite3NestedParse
0x1800697b4  mov     rax, [rsp+88h+var_48]
0x1800697b9  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x1800697c0  mov     [rsp+88h+var_50], rax
0x1800697c5  mov     r9, rsi
0x1800697c8  mov     dword ptr [rsp+88h+var_58], ebx
0x1800697cc  mov     r8, r15
0x1800697cf  mov     [rsp+88h+var_60], rsi
0x1800697d4  mov     rcx, rdi
0x1800697d7  mov     [rsp+88h+var_68], rsi
0x1800697dc  call    sqlite3NestedParse
0x1800697e1  mov     r8, r15
0x1800697e4  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x1800697eb  mov     rcx, rbp
0x1800697ee  call    sqlite3FindTable
0x1800697f3  test    rax, rax
0x1800697f6  jz      short loc_180069815
0x1800697f8  mov     rax, [r14]
0x1800697fb  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x180069802  mov     r9, rsi
0x180069805  mov     [rsp+88h+var_68], rax
0x18006980a  mov     r8, r15
0x18006980d  mov     rcx, rdi
0x180069810  call    sqlite3NestedParse
0x180069815  mov     r14d, [rsp+88h+arg_0]
0x18006981d  cmp     r14d, 1
0x180069821  jz      short loc_180069851
0x180069823  mov     rax, [rsp+88h+var_48]
0x180069828  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x18006982f  mov     [rsp+88h+var_50], rsi
0x180069834  mov     r9, rax
0x180069837  mov     [rsp+88h+var_58], r15
0x18006983c  mov     r8, r15
0x18006983f  mov     [rsp+88h+var_60], rax
0x180069844  mov     rcx, rdi
0x180069847  mov     [rsp+88h+var_68], rsi
0x18006984c  call    sqlite3NestedParse
0x180069851  test    r12, r12
0x180069854  jz      short loc_1800698AB
0x180069856  inc     dword ptr [rdi+38h]
0x180069859  xor     r8d, r8d
0x18006985c  mov     ebx, [rdi+38h]
0x18006985f  mov     rcx, r13
0x180069862  mov     dword ptr [rsp+88h+var_58], 0
0x18006986a  mov     r9d, ebx
0x18006986d  mov     [rsp+88h+var_60], rsi
0x180069872  lea     edx, [r8+75h]
0x180069876  mov     dword ptr [rsp+88h+var_68], 0
0x18006987e  call    sqlite3VdbeAddOp4
0x180069883  mov     dword ptr [rsp+88h+var_58], 0FFFFFFF5h
0x18006988b  xor     r9d, r9d
0x18006988e  mov     [rsp+88h+var_60], r12
0x180069893  mov     r8d, ebx
0x180069896  mov     edx, 0B0h
0x18006989b  mov     dword ptr [rsp+88h+var_68], 0
0x1800698a3  mov     rcx, r13
0x1800698a6  call    sqlite3VdbeAddOp4
0x1800698ab  mov     r8d, 1
0x1800698b1  mov     edx, r14d
0x1800698b4  mov     rcx, rdi
0x1800698b7  call    renameReloadSchema
0x1800698bc  mov     r8d, [rsp+88h+arg_18]
0x1800698c4  lea     r9, aAfterRename; "after rename"
0x1800698cb  mov     rdx, r15
0x1800698ce  mov     dword ptr [rsp+88h+var_68], 0
0x1800698d6  mov     rcx, rdi
0x1800698d9  call    renameTestSchema
0x1800698de  mov     rbx, [rsp+88h+arg_8]
0x1800698e6  jmp     short loc_1800698FA
0x1800698e8  mov     r8, rsi
0x1800698eb  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x1800698f2  mov     rcx, rdi
0x1800698f5  call    sqlite3ErrorMsg
0x1800698fa  mov     rdx, rbx
0x1800698fd  mov     rcx, rbp
0x180069900  call    sqlite3SrcListDelete
0x180069905  mov     rdx, rsi
0x180069908  mov     rcx, rbp
0x18006990b  mov     rbx, [rsp+88h+arg_10]
0x180069913  add     rsp, 50h
0x180069917  pop     r15
0x180069919  pop     r14
0x18006991b  pop     r13
0x18006991d  pop     r12
0x18006991f  pop     rdi
0x180069920  pop     rsi
0x180069921  pop     rbp
0x180069922  jmp     sqlite3DbFree
```
