# sqlite3AlterRenameTable

- ea: `0x180080c08`
- end: `0x180080f63`
- name: `sqlite3AlterRenameTable`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x180031b38`

## callees

- `0x18000a9e0`
- `0x18000ca30`
- `0x18000fd7c`
- `0x180010810`
- `0x180011d80`
- `0x180013a00`
- `0x180013bc0`
- `0x180014434`
- `0x180016574`
- `0x180018600`
- `0x1800398f0`
- `0x18003f6dc`
- `0x18004b520`
- `0x180060ce8`
- `0x180060e90`
- `0x18007222c`
- `0x18007e1ac`
- `0x18007ea64`
- `0x180080c08`
- `0x180084914`
- `0x1800857c4`

## string_xrefs

- `0x180080f27`: `there is already another table or index with this name: %s`
- `0x180080db7`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x180080df5`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x180080e37`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x180080e64`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x180080f00`: `after rename`

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
  __int64 v17; // r10
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
                v18 = ++*((_DWORD *)a1 + 15);
                sqlite3VdbeAddOp4(Vdbe, 118, 0, v18, 0, v4, 0);
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
0x180080c08  mov     [rsp+arg_10], rbx
0x180080c0d  mov     [rsp+arg_8], rdx
0x180080c12  push    rbp
0x180080c13  push    rsi
0x180080c14  push    rdi
0x180080c15  push    r12
0x180080c17  push    r13
0x180080c19  push    r14
0x180080c1b  push    r15
0x180080c1d  sub     rsp, 50h
0x180080c21  mov     rbp, [rcx]
0x180080c24  xor     esi, esi
0x180080c26  mov     r12, r8
0x180080c29  mov     rbx, rdx
0x180080c2c  mov     rdi, rcx
0x180080c2f  cmp     [rbp+67h], sil
0x180080c33  jnz     loc_180080F36
0x180080c39  lea     r8, [rdx+8]
0x180080c3d  xor     edx, edx
0x180080c3f  call    sqlite3LocateTableItem
0x180080c44  mov     r14, rax
0x180080c47  test    rax, rax
0x180080c4a  jz      loc_180080F36
0x180080c50  mov     rdx, [rax+60h]
0x180080c54  mov     rcx, [rdi]
0x180080c57  call    sqlite3SchemaToIndex
0x180080c5c  movsxd  rcx, eax
0x180080c5f  mov     rdx, r12
0x180080c62  shl     rcx, 5
0x180080c66  mov     [rsp+88h+arg_0], eax
0x180080c6d  mov     rax, [rbp+20h]
0x180080c71  mov     r15, [rcx+rax]
0x180080c75  mov     rcx, rbp
0x180080c78  call    sqlite3NameFromToken
0x180080c7d  mov     rsi, rax
0x180080c80  test    rax, rax
0x180080c83  jz      loc_180080F36
0x180080c89  mov     r8, r15
0x180080c8c  mov     rdx, rax
0x180080c8f  mov     rcx, rbp
0x180080c92  call    sqlite3FindTable
0x180080c97  test    rax, rax
0x180080c9a  jnz     loc_180080F24
0x180080ca0  mov     r8, r15
0x180080ca3  mov     rdx, rsi
0x180080ca6  mov     rcx, rbp
0x180080ca9  call    sqlite3FindIndex
0x180080cae  test    rax, rax
0x180080cb1  jnz     loc_180080F24
0x180080cb7  mov     r8, rsi
0x180080cba  mov     rdx, r14
0x180080cbd  mov     rcx, rbp
0x180080cc0  call    sqlite3IsShadowTableOf
0x180080cc5  test    eax, eax
0x180080cc7  jnz     loc_180080F24
0x180080ccd  mov     rdx, r14
0x180080cd0  mov     rcx, rdi
0x180080cd3  call    isAlterableTable
0x180080cd8  test    eax, eax
0x180080cda  jnz     loc_180080F36
0x180080ce0  mov     r9, rsi
0x180080ce3  lea     r8, aTable; "table"
0x180080cea  mov     rdx, rsi
0x180080ced  mov     rcx, rdi
0x180080cf0  call    sqlite3CheckObjectName
0x180080cf5  test    eax, eax
0x180080cf7  jnz     loc_180080F36
0x180080cfd  cmp     byte ptr [r14+3Fh], 2
0x180080d02  mov     rcx, rdi
0x180080d05  mov     r9, [r14]
0x180080d08  jnz     short loc_180080D19
0x180080d0a  mov     r8, r9
0x180080d0d  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x180080d14  jmp     loc_180080F31
0x180080d19  mov     r8, r15
0x180080d1c  mov     [rsp+88h+var_68], 0
0x180080d25  mov     edx, 1Ah
0x180080d2a  call    sqlite3AuthCheck
0x180080d2f  test    eax, eax
0x180080d31  jnz     loc_180080F36
0x180080d37  mov     rdx, r14
0x180080d3a  mov     rcx, rdi
0x180080d3d  call    sqlite3ViewGetColumnNames
0x180080d42  test    eax, eax
0x180080d44  jnz     loc_180080F36
0x180080d4a  xor     r12d, r12d
0x180080d4d  cmp     byte ptr [r14+3Fh], 1
0x180080d52  jnz     short loc_180080D76
0x180080d54  mov     rdx, r14
0x180080d57  mov     rcx, rbp
0x180080d5a  call    sqlite3GetVTable
0x180080d5f  mov     rcx, [rax+10h]
0x180080d63  mov     rdx, [rcx]
0x180080d66  mov     rcx, [rdx+98h]
0x180080d6d  neg     rcx
0x180080d70  sbb     r12, r12
0x180080d73  and     r12, rax
0x180080d76  mov     rcx, rdi
0x180080d79  call    sqlite3GetVdbe
0x180080d7e  mov     r13, rax
0x180080d81  test    rax, rax
0x180080d84  jz      loc_180080F36
0x180080d8a  mov     rcx, [rdi+0B0h]
0x180080d91  mov     rdx, rdi
0x180080d94  test    rcx, rcx
0x180080d97  cmovnz  rdx, rcx
0x180080d9b  mov     byte ptr [rdx+21h], 1
0x180080d9f  or      edx, 0FFFFFFFFh
0x180080da2  mov     r10, [r14]
0x180080da5  mov     rcx, r10
0x180080da8  mov     [rsp+88h+var_48], r10
0x180080dad  call    sqlite3Utf8CharLen
0x180080db2  mov     [rsp+88h+var_50], r10
0x180080db7  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180080dbe  mov     ebx, eax
0x180080dc0  mov     r9, r15
0x180080dc3  xor     eax, eax
0x180080dc5  mov     r8, r15
0x180080dc8  cmp     [rsp+88h+arg_0], 1
0x180080dd0  mov     rcx, rdi
0x180080dd3  setz    al
0x180080dd6  mov     dword ptr [rsp+88h+var_58], eax
0x180080dda  mov     [rsp+88h+var_60], rsi
0x180080ddf  mov     [rsp+88h+var_68], r10
0x180080de4  mov     [rsp+88h+arg_18], eax
0x180080deb  call    sqlite3NestedParse
0x180080df0  mov     rax, [rsp+88h+var_48]
0x180080df5  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x180080dfc  mov     [rsp+88h+var_50], rax
0x180080e01  mov     r9, rsi
0x180080e04  mov     dword ptr [rsp+88h+var_58], ebx
0x180080e08  mov     r8, r15
0x180080e0b  mov     [rsp+88h+var_60], rsi
0x180080e10  mov     rcx, rdi
0x180080e13  mov     [rsp+88h+var_68], rsi
0x180080e18  call    sqlite3NestedParse
0x180080e1d  mov     r8, r15
0x180080e20  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x180080e27  mov     rcx, rbp
0x180080e2a  call    sqlite3FindTable
0x180080e2f  test    rax, rax
0x180080e32  jz      short loc_180080E51
0x180080e34  mov     rax, [r14]
0x180080e37  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x180080e3e  mov     r9, rsi
0x180080e41  mov     [rsp+88h+var_68], rax
0x180080e46  mov     r8, r15
0x180080e49  mov     rcx, rdi
0x180080e4c  call    sqlite3NestedParse
0x180080e51  mov     r14d, [rsp+88h+arg_0]
0x180080e59  cmp     r14d, 1
0x180080e5d  jz      short loc_180080E8D
0x180080e5f  mov     rax, [rsp+88h+var_48]
0x180080e64  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x180080e6b  mov     [rsp+88h+var_50], rsi
0x180080e70  mov     r9, rax
0x180080e73  mov     [rsp+88h+var_58], r15
0x180080e78  mov     r8, r15
0x180080e7b  mov     [rsp+88h+var_60], rax
0x180080e80  mov     rcx, rdi
0x180080e83  mov     [rsp+88h+var_68], rsi
0x180080e88  call    sqlite3NestedParse
0x180080e8d  test    r12, r12
0x180080e90  jz      short loc_180080EE7
0x180080e92  inc     dword ptr [rdi+3Ch]
0x180080e95  xor     r8d, r8d
0x180080e98  mov     ebx, [rdi+3Ch]
0x180080e9b  mov     rcx, r13
0x180080e9e  mov     dword ptr [rsp+88h+var_58], 0
0x180080ea6  mov     r9d, ebx
0x180080ea9  mov     [rsp+88h+var_60], rsi
0x180080eae  lea     edx, [r8+76h]
0x180080eb2  mov     dword ptr [rsp+88h+var_68], 0
0x180080eba  call    sqlite3VdbeAddOp4
0x180080ebf  mov     dword ptr [rsp+88h+var_58], 0FFFFFFF5h
0x180080ec7  xor     r9d, r9d
0x180080eca  mov     [rsp+88h+var_60], r12
0x180080ecf  mov     r8d, ebx
0x180080ed2  mov     edx, 0B1h
0x180080ed7  mov     dword ptr [rsp+88h+var_68], 0
0x180080edf  mov     rcx, r13
0x180080ee2  call    sqlite3VdbeAddOp4
0x180080ee7  mov     r8d, 1
0x180080eed  mov     edx, r14d
0x180080ef0  mov     rcx, rdi
0x180080ef3  call    renameReloadSchema
0x180080ef8  mov     r8d, [rsp+88h+arg_18]
0x180080f00  lea     r9, aAfterRename; "after rename"
0x180080f07  mov     rdx, r15
0x180080f0a  mov     dword ptr [rsp+88h+var_68], 0
0x180080f12  mov     rcx, rdi
0x180080f15  call    renameTestSchema
0x180080f1a  mov     rbx, [rsp+88h+arg_8]
0x180080f22  jmp     short loc_180080F36
0x180080f24  mov     r8, rsi
0x180080f27  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x180080f2e  mov     rcx, rdi
0x180080f31  call    sqlite3ErrorMsg
0x180080f36  mov     rdx, rbx
0x180080f39  mov     rcx, rbp
0x180080f3c  call    sqlite3SrcListDelete
0x180080f41  mov     rdx, rsi
0x180080f44  mov     rcx, rbp
0x180080f47  mov     rbx, [rsp+88h+arg_10]
0x180080f4f  add     rsp, 50h
0x180080f53  pop     r15
0x180080f55  pop     r14
0x180080f57  pop     r13
0x180080f59  pop     r12
0x180080f5b  pop     rdi
0x180080f5c  pop     rsi
0x180080f5d  pop     rbp
0x180080f5e  jmp     sqlite3DbFree
```
