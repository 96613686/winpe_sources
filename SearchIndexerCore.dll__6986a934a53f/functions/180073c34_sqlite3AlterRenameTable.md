# sqlite3AlterRenameTable

- ea: `0x180073c34`
- end: `0x180073f8f`
- name: `sqlite3AlterRenameTable`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x18000213c`

## callees

- `0x1800087d0`
- `0x18000968c`
- `0x180009fe0`
- `0x18000a180`
- `0x18000a754`
- `0x180011bcc`
- `0x180015700`
- `0x180015eb0`
- `0x18001f0f0`
- `0x18001f19c`
- `0x18001f418`
- `0x18001f530`
- `0x180041d10`
- `0x18004a9b8`
- `0x1800619e8`
- `0x180073c34`
- `0x180081560`
- `0x18008d51c`
- `0x18008ddc0`
- `0x180092c1c`
- `0x180098e14`

## string_xrefs

- `0x180073f53`: `there is already another table or index with this name: %s`
- `0x180073de3`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x180073e21`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x180073e63`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x180073e90`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x180073f2c`: `after rename`

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
0x180073c34  mov     [rsp+arg_10], rbx
0x180073c39  mov     [rsp+arg_8], rdx
0x180073c3e  push    rbp
0x180073c3f  push    rsi
0x180073c40  push    rdi
0x180073c41  push    r12
0x180073c43  push    r13
0x180073c45  push    r14
0x180073c47  push    r15
0x180073c49  sub     rsp, 50h
0x180073c4d  mov     rbp, [rcx]
0x180073c50  xor     esi, esi
0x180073c52  mov     r12, r8
0x180073c55  mov     rbx, rdx
0x180073c58  mov     rdi, rcx
0x180073c5b  cmp     [rbp+67h], sil
0x180073c5f  jnz     loc_180073F62
0x180073c65  lea     r8, [rdx+8]
0x180073c69  xor     edx, edx
0x180073c6b  call    sqlite3LocateTableItem
0x180073c70  mov     r14, rax
0x180073c73  test    rax, rax
0x180073c76  jz      loc_180073F62
0x180073c7c  mov     rdx, [rax+60h]
0x180073c80  mov     rcx, [rdi]
0x180073c83  call    sqlite3SchemaToIndex
0x180073c88  movsxd  rcx, eax
0x180073c8b  mov     rdx, r12
0x180073c8e  shl     rcx, 5
0x180073c92  mov     [rsp+88h+arg_0], eax
0x180073c99  mov     rax, [rbp+20h]
0x180073c9d  mov     r15, [rcx+rax]
0x180073ca1  mov     rcx, rbp
0x180073ca4  call    sqlite3NameFromToken
0x180073ca9  mov     rsi, rax
0x180073cac  test    rax, rax
0x180073caf  jz      loc_180073F62
0x180073cb5  mov     r8, r15
0x180073cb8  mov     rdx, rax
0x180073cbb  mov     rcx, rbp
0x180073cbe  call    sqlite3FindTable
0x180073cc3  test    rax, rax
0x180073cc6  jnz     loc_180073F50
0x180073ccc  mov     r8, r15
0x180073ccf  mov     rdx, rsi
0x180073cd2  mov     rcx, rbp
0x180073cd5  call    sqlite3FindIndex
0x180073cda  test    rax, rax
0x180073cdd  jnz     loc_180073F50
0x180073ce3  mov     r8, rsi
0x180073ce6  mov     rdx, r14
0x180073ce9  mov     rcx, rbp
0x180073cec  call    sqlite3IsShadowTableOf
0x180073cf1  test    eax, eax
0x180073cf3  jnz     loc_180073F50
0x180073cf9  mov     rdx, r14
0x180073cfc  mov     rcx, rdi
0x180073cff  call    isAlterableTable
0x180073d04  test    eax, eax
0x180073d06  jnz     loc_180073F62
0x180073d0c  mov     r9, rsi
0x180073d0f  lea     r8, aTable; "table"
0x180073d16  mov     rdx, rsi
0x180073d19  mov     rcx, rdi
0x180073d1c  call    sqlite3CheckObjectName
0x180073d21  test    eax, eax
0x180073d23  jnz     loc_180073F62
0x180073d29  cmp     byte ptr [r14+3Fh], 2
0x180073d2e  mov     rcx, rdi
0x180073d31  mov     r9, [r14]
0x180073d34  jnz     short loc_180073D45
0x180073d36  mov     r8, r9
0x180073d39  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x180073d40  jmp     loc_180073F5D
0x180073d45  mov     r8, r15
0x180073d48  mov     [rsp+88h+var_68], 0
0x180073d51  mov     edx, 1Ah
0x180073d56  call    sqlite3AuthCheck
0x180073d5b  test    eax, eax
0x180073d5d  jnz     loc_180073F62
0x180073d63  mov     rdx, r14
0x180073d66  mov     rcx, rdi
0x180073d69  call    sqlite3ViewGetColumnNames
0x180073d6e  test    eax, eax
0x180073d70  jnz     loc_180073F62
0x180073d76  xor     r12d, r12d
0x180073d79  cmp     byte ptr [r14+3Fh], 1
0x180073d7e  jnz     short loc_180073DA2
0x180073d80  mov     rdx, r14
0x180073d83  mov     rcx, rbp
0x180073d86  call    sqlite3GetVTable
0x180073d8b  mov     rcx, [rax+10h]
0x180073d8f  mov     rdx, [rcx]
0x180073d92  mov     rcx, [rdx+98h]
0x180073d99  neg     rcx
0x180073d9c  sbb     r12, r12
0x180073d9f  and     r12, rax
0x180073da2  mov     rcx, rdi
0x180073da5  call    sqlite3GetVdbe
0x180073daa  mov     r13, rax
0x180073dad  test    rax, rax
0x180073db0  jz      loc_180073F62
0x180073db6  mov     rcx, [rdi+0B0h]
0x180073dbd  mov     rdx, rdi
0x180073dc0  test    rcx, rcx
0x180073dc3  cmovnz  rdx, rcx
0x180073dc7  mov     byte ptr [rdx+21h], 1
0x180073dcb  or      edx, 0FFFFFFFFh
0x180073dce  mov     r11, [r14]
0x180073dd1  mov     rcx, r11
0x180073dd4  mov     [rsp+88h+var_48], r11
0x180073dd9  call    sqlite3Utf8CharLen
0x180073dde  mov     [rsp+88h+var_50], r11
0x180073de3  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180073dea  mov     ebx, eax
0x180073dec  mov     r9, r15
0x180073def  xor     eax, eax
0x180073df1  mov     r8, r15
0x180073df4  cmp     [rsp+88h+arg_0], 1
0x180073dfc  mov     rcx, rdi
0x180073dff  setz    al
0x180073e02  mov     dword ptr [rsp+88h+var_58], eax
0x180073e06  mov     [rsp+88h+var_60], rsi
0x180073e0b  mov     [rsp+88h+var_68], r11
0x180073e10  mov     [rsp+88h+arg_18], eax
0x180073e17  call    sqlite3NestedParse
0x180073e1c  mov     rax, [rsp+88h+var_48]
0x180073e21  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x180073e28  mov     [rsp+88h+var_50], rax
0x180073e2d  mov     r9, rsi
0x180073e30  mov     dword ptr [rsp+88h+var_58], ebx
0x180073e34  mov     r8, r15
0x180073e37  mov     [rsp+88h+var_60], rsi
0x180073e3c  mov     rcx, rdi
0x180073e3f  mov     [rsp+88h+var_68], rsi
0x180073e44  call    sqlite3NestedParse
0x180073e49  mov     r8, r15
0x180073e4c  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x180073e53  mov     rcx, rbp
0x180073e56  call    sqlite3FindTable
0x180073e5b  test    rax, rax
0x180073e5e  jz      short loc_180073E7D
0x180073e60  mov     rax, [r14]
0x180073e63  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x180073e6a  mov     r9, rsi
0x180073e6d  mov     [rsp+88h+var_68], rax
0x180073e72  mov     r8, r15
0x180073e75  mov     rcx, rdi
0x180073e78  call    sqlite3NestedParse
0x180073e7d  mov     r14d, [rsp+88h+arg_0]
0x180073e85  cmp     r14d, 1
0x180073e89  jz      short loc_180073EB9
0x180073e8b  mov     rax, [rsp+88h+var_48]
0x180073e90  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x180073e97  mov     [rsp+88h+var_50], rsi
0x180073e9c  mov     r9, rax
0x180073e9f  mov     [rsp+88h+var_58], r15
0x180073ea4  mov     r8, r15
0x180073ea7  mov     [rsp+88h+var_60], rax
0x180073eac  mov     rcx, rdi
0x180073eaf  mov     [rsp+88h+var_68], rsi
0x180073eb4  call    sqlite3NestedParse
0x180073eb9  test    r12, r12
0x180073ebc  jz      short loc_180073F13
0x180073ebe  inc     dword ptr [rdi+38h]
0x180073ec1  xor     r8d, r8d
0x180073ec4  mov     ebx, [rdi+38h]
0x180073ec7  mov     rcx, r13
0x180073eca  mov     dword ptr [rsp+88h+var_58], 0
0x180073ed2  mov     r9d, ebx
0x180073ed5  mov     [rsp+88h+var_60], rsi
0x180073eda  lea     edx, [r8+75h]
0x180073ede  mov     dword ptr [rsp+88h+var_68], 0
0x180073ee6  call    sqlite3VdbeAddOp4
0x180073eeb  mov     dword ptr [rsp+88h+var_58], 0FFFFFFF5h
0x180073ef3  xor     r9d, r9d
0x180073ef6  mov     [rsp+88h+var_60], r12
0x180073efb  mov     r8d, ebx
0x180073efe  mov     edx, 0B1h
0x180073f03  mov     dword ptr [rsp+88h+var_68], 0
0x180073f0b  mov     rcx, r13
0x180073f0e  call    sqlite3VdbeAddOp4
0x180073f13  mov     r8d, 1
0x180073f19  mov     edx, r14d
0x180073f1c  mov     rcx, rdi
0x180073f1f  call    renameReloadSchema
0x180073f24  mov     r8d, [rsp+88h+arg_18]
0x180073f2c  lea     r9, aAfterRename; "after rename"
0x180073f33  mov     rdx, r15
0x180073f36  mov     dword ptr [rsp+88h+var_68], 0
0x180073f3e  mov     rcx, rdi
0x180073f41  call    renameTestSchema
0x180073f46  mov     rbx, [rsp+88h+arg_8]
0x180073f4e  jmp     short loc_180073F62
0x180073f50  mov     r8, rsi
0x180073f53  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x180073f5a  mov     rcx, rdi
0x180073f5d  call    sqlite3ErrorMsg
0x180073f62  mov     rdx, rbx
0x180073f65  mov     rcx, rbp
0x180073f68  call    sqlite3SrcListDelete
0x180073f6d  mov     rdx, rsi
0x180073f70  mov     rcx, rbp
0x180073f73  mov     rbx, [rsp+88h+arg_10]
0x180073f7b  add     rsp, 50h
0x180073f7f  pop     r15
0x180073f81  pop     r14
0x180073f83  pop     r13
0x180073f85  pop     r12
0x180073f87  pop     rdi
0x180073f88  pop     rsi
0x180073f89  pop     rbp
0x180073f8a  jmp     sqlite3DbFree
```
