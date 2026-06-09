# sqlite3AlterRenameTable

- ea: `0x1801c6344`
- end: `0x1801c669f`
- name: `sqlite3AlterRenameTable`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x18021d7f0`

## callees

- `0x1801ac17c`
- `0x1801bf4d8`
- `0x1801bffb4`
- `0x1801c6344`
- `0x1801c716c`
- `0x1801cb4d4`
- `0x1801ce9a0`
- `0x1801d0c94`
- `0x1801d5a40`
- `0x1801d5ac8`
- `0x1801d9ec8`
- `0x1801da0fc`
- `0x1801dc3e0`
- `0x1801dd19c`
- `0x1801de0f4`
- `0x1801de124`
- `0x1801e7704`
- `0x1801e9ec8`
- `0x1801edc4c`
- `0x1801ee320`
- `0x1801f8e30`

## string_xrefs

- `0x1801c65a0`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x1801c663c`: `after rename`
- `0x1801c64f3`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x1801c6531`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x1801c6573`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x1801c6663`: `there is already another table or index with this name: %s`

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
0x1801c6344  mov     [rsp+arg_10], rbx
0x1801c6349  mov     [rsp+arg_8], rdx
0x1801c634e  push    rbp
0x1801c634f  push    rsi
0x1801c6350  push    rdi
0x1801c6351  push    r12
0x1801c6353  push    r13
0x1801c6355  push    r14
0x1801c6357  push    r15
0x1801c6359  sub     rsp, 50h
0x1801c635d  mov     rbp, [rcx]
0x1801c6360  xor     esi, esi
0x1801c6362  mov     r12, r8
0x1801c6365  mov     rbx, rdx
0x1801c6368  mov     rdi, rcx
0x1801c636b  cmp     [rbp+67h], sil
0x1801c636f  jnz     loc_1801C6672
0x1801c6375  lea     r8, [rdx+8]
0x1801c6379  xor     edx, edx
0x1801c637b  call    sqlite3LocateTableItem
0x1801c6380  mov     r14, rax
0x1801c6383  test    rax, rax
0x1801c6386  jz      loc_1801C6672
0x1801c638c  mov     rdx, [rax+60h]
0x1801c6390  mov     rcx, [rdi]
0x1801c6393  call    sqlite3SchemaToIndex
0x1801c6398  movsxd  rcx, eax
0x1801c639b  mov     rdx, r12
0x1801c639e  shl     rcx, 5
0x1801c63a2  mov     [rsp+88h+arg_0], eax
0x1801c63a9  mov     rax, [rbp+20h]
0x1801c63ad  mov     r15, [rcx+rax]
0x1801c63b1  mov     rcx, rbp
0x1801c63b4  call    sqlite3NameFromToken
0x1801c63b9  mov     rsi, rax
0x1801c63bc  test    rax, rax
0x1801c63bf  jz      loc_1801C6672
0x1801c63c5  mov     r8, r15
0x1801c63c8  mov     rdx, rax
0x1801c63cb  mov     rcx, rbp
0x1801c63ce  call    sqlite3FindTable
0x1801c63d3  test    rax, rax
0x1801c63d6  jnz     loc_1801C6660
0x1801c63dc  mov     r8, r15
0x1801c63df  mov     rdx, rsi
0x1801c63e2  mov     rcx, rbp
0x1801c63e5  call    sqlite3FindIndex
0x1801c63ea  test    rax, rax
0x1801c63ed  jnz     loc_1801C6660
0x1801c63f3  mov     r8, rsi
0x1801c63f6  mov     rdx, r14
0x1801c63f9  mov     rcx, rbp
0x1801c63fc  call    sqlite3IsShadowTableOf
0x1801c6401  test    eax, eax
0x1801c6403  jnz     loc_1801C6660
0x1801c6409  mov     rdx, r14
0x1801c640c  mov     rcx, rdi
0x1801c640f  call    isAlterableTable
0x1801c6414  test    eax, eax
0x1801c6416  jnz     loc_1801C6672
0x1801c641c  mov     r9, rsi
0x1801c641f  lea     r8, aTable; "table"
0x1801c6426  mov     rdx, rsi
0x1801c6429  mov     rcx, rdi
0x1801c642c  call    sqlite3CheckObjectName
0x1801c6431  test    eax, eax
0x1801c6433  jnz     loc_1801C6672
0x1801c6439  cmp     byte ptr [r14+3Fh], 2
0x1801c643e  mov     rcx, rdi
0x1801c6441  mov     r9, [r14]
0x1801c6444  jnz     short loc_1801C6455
0x1801c6446  mov     r8, r9
0x1801c6449  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x1801c6450  jmp     loc_1801C666D
0x1801c6455  mov     r8, r15
0x1801c6458  mov     [rsp+88h+var_68], 0
0x1801c6461  mov     edx, 1Ah
0x1801c6466  call    sqlite3AuthCheck
0x1801c646b  test    eax, eax
0x1801c646d  jnz     loc_1801C6672
0x1801c6473  mov     rdx, r14
0x1801c6476  mov     rcx, rdi
0x1801c6479  call    sqlite3ViewGetColumnNames
0x1801c647e  test    eax, eax
0x1801c6480  jnz     loc_1801C6672
0x1801c6486  xor     r12d, r12d
0x1801c6489  cmp     byte ptr [r14+3Fh], 1
0x1801c648e  jnz     short loc_1801C64B2
0x1801c6490  mov     rdx, r14
0x1801c6493  mov     rcx, rbp
0x1801c6496  call    sqlite3GetVTable
0x1801c649b  mov     rcx, [rax+10h]
0x1801c649f  mov     rdx, [rcx]
0x1801c64a2  mov     rcx, [rdx+98h]
0x1801c64a9  neg     rcx
0x1801c64ac  sbb     r12, r12
0x1801c64af  and     r12, rax
0x1801c64b2  mov     rcx, rdi
0x1801c64b5  call    sqlite3GetVdbe
0x1801c64ba  mov     r13, rax
0x1801c64bd  test    rax, rax
0x1801c64c0  jz      loc_1801C6672
0x1801c64c6  mov     rcx, [rdi+0B0h]
0x1801c64cd  mov     rdx, rdi
0x1801c64d0  test    rcx, rcx
0x1801c64d3  cmovnz  rdx, rcx
0x1801c64d7  mov     byte ptr [rdx+21h], 1
0x1801c64db  or      edx, 0FFFFFFFFh
0x1801c64de  mov     r11, [r14]
0x1801c64e1  mov     rcx, r11
0x1801c64e4  mov     [rsp+88h+var_48], r11
0x1801c64e9  call    sqlite3Utf8CharLen
0x1801c64ee  mov     [rsp+88h+var_50], r11
0x1801c64f3  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1801c64fa  mov     ebx, eax
0x1801c64fc  mov     r9, r15
0x1801c64ff  xor     eax, eax
0x1801c6501  mov     r8, r15
0x1801c6504  cmp     [rsp+88h+arg_0], 1
0x1801c650c  mov     rcx, rdi
0x1801c650f  setz    al
0x1801c6512  mov     dword ptr [rsp+88h+var_58], eax
0x1801c6516  mov     [rsp+88h+var_60], rsi
0x1801c651b  mov     [rsp+88h+var_68], r11
0x1801c6520  mov     [rsp+88h+arg_18], eax
0x1801c6527  call    sqlite3NestedParse
0x1801c652c  mov     rax, [rsp+88h+var_48]
0x1801c6531  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x1801c6538  mov     [rsp+88h+var_50], rax
0x1801c653d  mov     r9, rsi
0x1801c6540  mov     dword ptr [rsp+88h+var_58], ebx
0x1801c6544  mov     r8, r15
0x1801c6547  mov     [rsp+88h+var_60], rsi
0x1801c654c  mov     rcx, rdi
0x1801c654f  mov     [rsp+88h+var_68], rsi
0x1801c6554  call    sqlite3NestedParse
0x1801c6559  mov     r8, r15
0x1801c655c  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x1801c6563  mov     rcx, rbp
0x1801c6566  call    sqlite3FindTable
0x1801c656b  test    rax, rax
0x1801c656e  jz      short loc_1801C658D
0x1801c6570  mov     rax, [r14]
0x1801c6573  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x1801c657a  mov     r9, rsi
0x1801c657d  mov     [rsp+88h+var_68], rax
0x1801c6582  mov     r8, r15
0x1801c6585  mov     rcx, rdi
0x1801c6588  call    sqlite3NestedParse
0x1801c658d  mov     r14d, [rsp+88h+arg_0]
0x1801c6595  cmp     r14d, 1
0x1801c6599  jz      short loc_1801C65C9
0x1801c659b  mov     rax, [rsp+88h+var_48]
0x1801c65a0  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x1801c65a7  mov     [rsp+88h+var_50], rsi
0x1801c65ac  mov     r9, rax
0x1801c65af  mov     [rsp+88h+var_58], r15
0x1801c65b4  mov     r8, r15
0x1801c65b7  mov     [rsp+88h+var_60], rax
0x1801c65bc  mov     rcx, rdi
0x1801c65bf  mov     [rsp+88h+var_68], rsi
0x1801c65c4  call    sqlite3NestedParse
0x1801c65c9  test    r12, r12
0x1801c65cc  jz      short loc_1801C6623
0x1801c65ce  inc     dword ptr [rdi+38h]
0x1801c65d1  xor     r8d, r8d
0x1801c65d4  mov     ebx, [rdi+38h]
0x1801c65d7  mov     rcx, r13
0x1801c65da  mov     dword ptr [rsp+88h+var_58], 0
0x1801c65e2  mov     r9d, ebx
0x1801c65e5  mov     [rsp+88h+var_60], rsi
0x1801c65ea  lea     edx, [r8+75h]
0x1801c65ee  mov     dword ptr [rsp+88h+var_68], 0
0x1801c65f6  call    sqlite3VdbeAddOp4
0x1801c65fb  mov     dword ptr [rsp+88h+var_58], 0FFFFFFF5h
0x1801c6603  xor     r9d, r9d
0x1801c6606  mov     [rsp+88h+var_60], r12
0x1801c660b  mov     r8d, ebx
0x1801c660e  mov     edx, 0B1h
0x1801c6613  mov     dword ptr [rsp+88h+var_68], 0
0x1801c661b  mov     rcx, r13
0x1801c661e  call    sqlite3VdbeAddOp4
0x1801c6623  mov     r8d, 1
0x1801c6629  mov     edx, r14d
0x1801c662c  mov     rcx, rdi
0x1801c662f  call    renameReloadSchema
0x1801c6634  mov     r8d, [rsp+88h+arg_18]
0x1801c663c  lea     r9, aAfterRename; "after rename"
0x1801c6643  mov     rdx, r15
0x1801c6646  mov     dword ptr [rsp+88h+var_68], 0
0x1801c664e  mov     rcx, rdi
0x1801c6651  call    renameTestSchema
0x1801c6656  mov     rbx, [rsp+88h+arg_8]
0x1801c665e  jmp     short loc_1801C6672
0x1801c6660  mov     r8, rsi
0x1801c6663  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x1801c666a  mov     rcx, rdi
0x1801c666d  call    sqlite3ErrorMsg
0x1801c6672  mov     rdx, rbx
0x1801c6675  mov     rcx, rbp
0x1801c6678  call    sqlite3SrcListDelete
0x1801c667d  mov     rdx, rsi
0x1801c6680  mov     rcx, rbp
0x1801c6683  mov     rbx, [rsp+88h+arg_10]
0x1801c668b  add     rsp, 50h
0x1801c668f  pop     r15
0x1801c6691  pop     r14
0x1801c6693  pop     r13
0x1801c6695  pop     r12
0x1801c6697  pop     rdi
0x1801c6698  pop     rsi
0x1801c6699  pop     rbp
0x1801c669a  jmp     sqlite3DbFree
```
