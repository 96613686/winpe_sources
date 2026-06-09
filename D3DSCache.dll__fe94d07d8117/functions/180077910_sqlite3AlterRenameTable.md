# sqlite3AlterRenameTable

- ea: `0x180077910`
- end: `0x180077c6b`
- name: `sqlite3AlterRenameTable`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x18001bc30`

## callees

- `0x180014464`
- `0x180027e60`
- `0x18002817c`
- `0x18003713c`
- `0x180038ba0`
- `0x18003be78`
- `0x18003c5f4`
- `0x18003cc7c`
- `0x18003d480`
- `0x18003f960`
- `0x18004002c`
- `0x180042130`
- `0x180042bb0`
- `0x180042c38`
- `0x18006415c`
- `0x18007387c`
- `0x180074120`
- `0x180077910`
- `0x1800817c0`
- `0x1800854c4`
- `0x18008c5fc`

## string_xrefs

- `0x180077c2f`: `there is already another table or index with this name: %s`
- `0x180077abf`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x180077afd`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x180077b3f`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x180077b6c`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x180077c08`: `after rename`

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
              if ( a1[22] )
                v15 = (__int64 *)a1[22];
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
                sqlite3VdbeAddOp4(Vdbe, 177, v18, 0, 0, v12, -11);
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
0x180077910  mov     [rsp+arg_10], rbx
0x180077915  mov     [rsp+arg_8], rdx
0x18007791a  push    rbp
0x18007791b  push    rsi
0x18007791c  push    rdi
0x18007791d  push    r12
0x18007791f  push    r13
0x180077921  push    r14
0x180077923  push    r15
0x180077925  sub     rsp, 50h
0x180077929  mov     rbp, [rcx]
0x18007792c  xor     esi, esi
0x18007792e  mov     r12, r8
0x180077931  mov     rbx, rdx
0x180077934  mov     rdi, rcx
0x180077937  cmp     [rbp+67h], sil
0x18007793b  jnz     loc_180077C3E
0x180077941  lea     r8, [rdx+8]
0x180077945  xor     edx, edx
0x180077947  call    sqlite3LocateTableItem
0x18007794c  mov     r14, rax
0x18007794f  test    rax, rax
0x180077952  jz      loc_180077C3E
0x180077958  mov     rdx, [rax+60h]
0x18007795c  mov     rcx, [rdi]
0x18007795f  call    sqlite3SchemaToIndex
0x180077964  movsxd  rcx, eax
0x180077967  mov     rdx, r12
0x18007796a  shl     rcx, 5
0x18007796e  mov     [rsp+88h+arg_0], eax
0x180077975  mov     rax, [rbp+20h]
0x180077979  mov     r15, [rcx+rax]
0x18007797d  mov     rcx, rbp
0x180077980  call    sqlite3NameFromToken
0x180077985  mov     rsi, rax
0x180077988  test    rax, rax
0x18007798b  jz      loc_180077C3E
0x180077991  mov     r8, r15
0x180077994  mov     rdx, rax
0x180077997  mov     rcx, rbp
0x18007799a  call    sqlite3FindTable
0x18007799f  test    rax, rax
0x1800779a2  jnz     loc_180077C2C
0x1800779a8  mov     r8, r15
0x1800779ab  mov     rdx, rsi
0x1800779ae  mov     rcx, rbp
0x1800779b1  call    sqlite3FindIndex
0x1800779b6  test    rax, rax
0x1800779b9  jnz     loc_180077C2C
0x1800779bf  mov     r8, rsi
0x1800779c2  mov     rdx, r14
0x1800779c5  mov     rcx, rbp
0x1800779c8  call    sqlite3IsShadowTableOf
0x1800779cd  test    eax, eax
0x1800779cf  jnz     loc_180077C2C
0x1800779d5  mov     rdx, r14
0x1800779d8  mov     rcx, rdi
0x1800779db  call    isAlterableTable
0x1800779e0  test    eax, eax
0x1800779e2  jnz     loc_180077C3E
0x1800779e8  mov     r9, rsi
0x1800779eb  lea     r8, aTable; "table"
0x1800779f2  mov     rdx, rsi
0x1800779f5  mov     rcx, rdi
0x1800779f8  call    sqlite3CheckObjectName
0x1800779fd  test    eax, eax
0x1800779ff  jnz     loc_180077C3E
0x180077a05  cmp     byte ptr [r14+3Fh], 2
0x180077a0a  mov     rcx, rdi
0x180077a0d  mov     r9, [r14]
0x180077a10  jnz     short loc_180077A21
0x180077a12  mov     r8, r9
0x180077a15  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x180077a1c  jmp     loc_180077C39
0x180077a21  mov     r8, r15
0x180077a24  mov     [rsp+88h+var_68], 0
0x180077a2d  mov     edx, 1Ah
0x180077a32  call    sqlite3AuthCheck
0x180077a37  test    eax, eax
0x180077a39  jnz     loc_180077C3E
0x180077a3f  mov     rdx, r14
0x180077a42  mov     rcx, rdi
0x180077a45  call    sqlite3ViewGetColumnNames
0x180077a4a  test    eax, eax
0x180077a4c  jnz     loc_180077C3E
0x180077a52  xor     r12d, r12d
0x180077a55  cmp     byte ptr [r14+3Fh], 1
0x180077a5a  jnz     short loc_180077A7E
0x180077a5c  mov     rdx, r14
0x180077a5f  mov     rcx, rbp
0x180077a62  call    sqlite3GetVTable
0x180077a67  mov     rcx, [rax+10h]
0x180077a6b  mov     rdx, [rcx]
0x180077a6e  mov     rcx, [rdx+98h]
0x180077a75  neg     rcx
0x180077a78  sbb     r12, r12
0x180077a7b  and     r12, rax
0x180077a7e  mov     rcx, rdi
0x180077a81  call    sqlite3GetVdbe
0x180077a86  mov     r13, rax
0x180077a89  test    rax, rax
0x180077a8c  jz      loc_180077C3E
0x180077a92  mov     rcx, [rdi+0B0h]
0x180077a99  mov     rdx, rdi
0x180077a9c  test    rcx, rcx
0x180077a9f  cmovnz  rdx, rcx
0x180077aa3  mov     byte ptr [rdx+21h], 1
0x180077aa7  or      edx, 0FFFFFFFFh
0x180077aaa  mov     r11, [r14]
0x180077aad  mov     rcx, r11
0x180077ab0  mov     [rsp+88h+var_48], r11
0x180077ab5  call    sqlite3Utf8CharLen
0x180077aba  mov     [rsp+88h+var_50], r11
0x180077abf  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180077ac6  mov     ebx, eax
0x180077ac8  mov     r9, r15
0x180077acb  xor     eax, eax
0x180077acd  mov     r8, r15
0x180077ad0  cmp     [rsp+88h+arg_0], 1
0x180077ad8  mov     rcx, rdi
0x180077adb  setz    al
0x180077ade  mov     dword ptr [rsp+88h+var_58], eax
0x180077ae2  mov     [rsp+88h+var_60], rsi
0x180077ae7  mov     [rsp+88h+var_68], r11
0x180077aec  mov     [rsp+88h+arg_18], eax
0x180077af3  call    sqlite3NestedParse
0x180077af8  mov     rax, [rsp+88h+var_48]
0x180077afd  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x180077b04  mov     [rsp+88h+var_50], rax
0x180077b09  mov     r9, rsi
0x180077b0c  mov     dword ptr [rsp+88h+var_58], ebx
0x180077b10  mov     r8, r15
0x180077b13  mov     [rsp+88h+var_60], rsi
0x180077b18  mov     rcx, rdi
0x180077b1b  mov     [rsp+88h+var_68], rsi
0x180077b20  call    sqlite3NestedParse
0x180077b25  mov     r8, r15
0x180077b28  lea     rdx, Str2; "sqlite_sequence"
0x180077b2f  mov     rcx, rbp
0x180077b32  call    sqlite3FindTable
0x180077b37  test    rax, rax
0x180077b3a  jz      short loc_180077B59
0x180077b3c  mov     rax, [r14]
0x180077b3f  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x180077b46  mov     r9, rsi
0x180077b49  mov     [rsp+88h+var_68], rax
0x180077b4e  mov     r8, r15
0x180077b51  mov     rcx, rdi
0x180077b54  call    sqlite3NestedParse
0x180077b59  mov     r14d, [rsp+88h+arg_0]
0x180077b61  cmp     r14d, 1
0x180077b65  jz      short loc_180077B95
0x180077b67  mov     rax, [rsp+88h+var_48]
0x180077b6c  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x180077b73  mov     [rsp+88h+var_50], rsi
0x180077b78  mov     r9, rax
0x180077b7b  mov     [rsp+88h+var_58], r15
0x180077b80  mov     r8, r15
0x180077b83  mov     [rsp+88h+var_60], rax
0x180077b88  mov     rcx, rdi
0x180077b8b  mov     [rsp+88h+var_68], rsi
0x180077b90  call    sqlite3NestedParse
0x180077b95  test    r12, r12
0x180077b98  jz      short loc_180077BEF
0x180077b9a  inc     dword ptr [rdi+38h]
0x180077b9d  xor     r8d, r8d
0x180077ba0  mov     ebx, [rdi+38h]
0x180077ba3  mov     rcx, r13
0x180077ba6  mov     dword ptr [rsp+88h+var_58], 0
0x180077bae  mov     r9d, ebx
0x180077bb1  mov     [rsp+88h+var_60], rsi
0x180077bb6  lea     edx, [r8+75h]
0x180077bba  mov     dword ptr [rsp+88h+var_68], 0
0x180077bc2  call    sqlite3VdbeAddOp4
0x180077bc7  mov     dword ptr [rsp+88h+var_58], 0FFFFFFF5h
0x180077bcf  xor     r9d, r9d
0x180077bd2  mov     [rsp+88h+var_60], r12
0x180077bd7  mov     r8d, ebx
0x180077bda  mov     edx, 0B1h
0x180077bdf  mov     dword ptr [rsp+88h+var_68], 0
0x180077be7  mov     rcx, r13
0x180077bea  call    sqlite3VdbeAddOp4
0x180077bef  mov     r8d, 1
0x180077bf5  mov     edx, r14d
0x180077bf8  mov     rcx, rdi
0x180077bfb  call    renameReloadSchema
0x180077c00  mov     r8d, [rsp+88h+arg_18]
0x180077c08  lea     r9, aAfterRename; "after rename"
0x180077c0f  mov     rdx, r15
0x180077c12  mov     dword ptr [rsp+88h+var_68], 0
0x180077c1a  mov     rcx, rdi
0x180077c1d  call    renameTestSchema
0x180077c22  mov     rbx, [rsp+88h+arg_8]
0x180077c2a  jmp     short loc_180077C3E
0x180077c2c  mov     r8, rsi
0x180077c2f  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x180077c36  mov     rcx, rdi
0x180077c39  call    sqlite3ErrorMsg
0x180077c3e  mov     rdx, rbx
0x180077c41  mov     rcx, rbp
0x180077c44  call    sqlite3SrcListDelete
0x180077c49  mov     rdx, rsi
0x180077c4c  mov     rcx, rbp
0x180077c4f  mov     rbx, [rsp+88h+arg_10]
0x180077c57  add     rsp, 50h
0x180077c5b  pop     r15
0x180077c5d  pop     r14
0x180077c5f  pop     r13
0x180077c61  pop     r12
0x180077c63  pop     rdi
0x180077c64  pop     rsi
0x180077c65  pop     rbp
0x180077c66  jmp     sqlite3DbFree
```
