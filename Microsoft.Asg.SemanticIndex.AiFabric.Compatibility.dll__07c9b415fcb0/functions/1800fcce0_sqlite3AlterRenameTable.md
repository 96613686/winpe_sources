# sqlite3AlterRenameTable

- ea: `0x1800fcce0`
- end: `0x1800fd0fa`
- name: `sqlite3AlterRenameTable`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x180174050`

## callees

- `0x1800da2a0`
- `0x1800f3430`
- `0x1800f3b20`
- `0x1800fcce0`
- `0x1800fdf90`
- `0x180102f70`
- `0x180108840`
- `0x18010b290`
- `0x1801127c0`
- `0x1801128f0`
- `0x18011cb70`
- `0x18011d960`
- `0x18011eaa0`
- `0x18011ec20`
- `0x180130eb0`
- `0x180137b60`
- `0x180138140`
- `0x180142830`
- `0x180162150`

## string_xrefs

- `0x1800fd0b3`: `there is already another table or index with this name: %s`
- `0x1800fcf54`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x1800fcf8d`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x1800fcfd5`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x1800fcffd`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x1800fd081`: `after rename`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameTable(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 j; // rdi
  __int64 v7; // r14
  __int64 TableItem; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  int v11; // r12d
  _QWORD *i; // rcx
  __int64 v13; // r13
  __int64 v14; // rax
  int v15; // r15d
  __int64 *v16; // rcx
  _BYTE *v17; // rcx
  unsigned __int8 *v18; // rax
  unsigned __int8 v19; // cl
  char v20; // cl
  unsigned int v21; // ebx
  __int64 result; // rax
  __int64 v23; // [rsp+30h] [rbp-58h]
  __int64 v24; // [rsp+90h] [rbp+8h]
  __int64 v26; // [rsp+A8h] [rbp+20h]

  v3 = *a1;
  j = 0;
  v7 = 0;
  if ( *(_BYTE *)(*a1 + 103) )
    goto LABEL_47;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v9 = (_QWORD *)TableItem;
  if ( !TableItem )
    goto LABEL_47;
  v10 = *(_QWORD *)(TableItem + 96);
  v11 = -32768;
  if ( v10 )
  {
    v11 = 0;
    for ( i = (_QWORD *)(*(_QWORD *)(*a1 + 32) + 24LL); *i != v10; i += 4 )
      ++v11;
  }
  v13 = *(_QWORD *)(32LL * v11 + *(_QWORD *)(v3 + 32));
  v14 = sqlite3NameFromToken(v3, a3);
  v7 = v14;
  if ( !v14 )
    goto LABEL_47;
  if ( sqlite3FindTable(v3, v14, v13)
    || sqlite3FindIndex(v3, v7, v13)
    || (unsigned int)sqlite3IsShadowTableOf(v3, v9, v7) )
  {
    sqlite3ErrorMsg(a1, "there is already another table or index with this name: %s", v7);
    goto LABEL_14;
  }
  if ( (unsigned int)isAlterableTable(a1, v9) || (unsigned int)sqlite3CheckObjectName(a1, v7, "table", v7) )
  {
LABEL_47:
    result = sqlite3SrcListDelete(v3, a2);
    if ( !v7 )
      return result;
    return sqlite3DbFreeNN(v3);
  }
  if ( *((_BYTE *)v9 + 63) != 2 )
  {
    v15 = 0;
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v13, *v9, 0)
      && (*((_BYTE *)v9 + 63) != 1 && *((__int16 *)v9 + 27) > 0 || !(unsigned int)viewGetColumnNames(a1, v9)) )
    {
      if ( *((_BYTE *)v9 + 63) == 1 )
      {
        for ( j = v9[10]; j; j = *(_QWORD *)(j + 40) )
        {
          if ( *(_QWORD *)j == v3 )
            break;
        }
        if ( !*(_QWORD *)(**(_QWORD **)(j + 16) + 152LL) )
          j = 0;
      }
      v26 = a1[2];
      if ( v26 )
        goto LABEL_30;
      if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
        *((_BYTE *)a1 + 35) = 1;
      v26 = sqlite3VdbeCreate(a1);
      if ( v26 )
      {
LABEL_30:
        v16 = a1;
        if ( a1[21] )
          v16 = (__int64 *)a1[21];
        *((_BYTE *)v16 + 33) = 1;
        v17 = (_BYTE *)*v9;
        v24 = *v9;
        v18 = (unsigned __int8 *)*v9;
        if ( *(_BYTE *)*v9 )
        {
          do
          {
            if ( v18 == (unsigned __int8 *)-1LL )
              break;
            v19 = *v18++;
            if ( v19 >= 0xC0u && (*v18 & 0xC0) == 0x80 )
            {
              do
                v20 = *++v18;
              while ( (v20 & 0xC0) == 0x80 );
            }
            ++v15;
          }
          while ( *v18 );
          v17 = (_BYTE *)*v9;
        }
        sqlite3NestedParse(
          a1,
          "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index"
          "' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'",
          v13,
          v13,
          v17,
          v7,
          v11 == 1,
          v17);
        LODWORD(v23) = v15;
        sqlite3NestedParse(
          a1,
          "UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoi"
          "ndex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WH"
          "ERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');",
          v13,
          v7,
          v7,
          v7,
          v23,
          v24);
        if ( sqlite3FindTable(v3, "sqlite_sequence", v13) )
          sqlite3NestedParse(a1, "UPDATE \"%w\".sqlite_sequence set name = %Q WHERE name = %Q", v13, v7, *v9);
        if ( v11 != 1 )
          sqlite3NestedParse(
            a1,
            "UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHE"
            "N tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELS"
            "E tbl_name END WHERE type IN ('view', 'trigger')",
            v13,
            v24,
            v7,
            v24,
            v13,
            v7);
        if ( j )
        {
          v21 = ++*((_DWORD *)a1 + 14);
          sqlite3VdbeLoadString(v26, v21, v7);
          sqlite3VdbeAddOp4(v26, 177, v21, 0, 0, j, -11);
        }
        renameReloadSchema(a1, (unsigned int)v11, 1);
        renameTestSchema((_DWORD)a1, v13, v11 == 1, (unsigned int)"after rename", 0);
        sqlite3SrcListDelete(v3, a2);
        return sqlite3DbFreeNN(v3);
      }
    }
    goto LABEL_47;
  }
  sqlite3ErrorMsg(a1, "view %s may not be altered", *v9);
LABEL_14:
  sqlite3SrcListDelete(v3, a2);
  return sqlite3DbFreeNN(v3);
}

```

## disassembly

```asm
0x1800fcce0  mov     [rsp+arg_10], rbx
0x1800fcce5  mov     [rsp+arg_8], rdx
0x1800fccea  push    rbp
0x1800fcceb  push    rsi
0x1800fccec  push    rdi
0x1800fcced  push    r12
0x1800fccef  push    r13
0x1800fccf1  push    r14
0x1800fccf3  push    r15
0x1800fccf5  sub     rsp, 50h
0x1800fccf9  mov     rbp, [rcx]
0x1800fccfc  xor     r13d, r13d
0x1800fccff  mov     edi, r13d
0x1800fcd02  mov     r15, r8
0x1800fcd05  mov     rsi, rcx
0x1800fcd08  mov     r14d, r13d
0x1800fcd0b  cmp     [rbp+67h], dil
0x1800fcd0f  jnz     loc_1800FD0C2
0x1800fcd15  mov     r8, [rsp+88h+arg_8]
0x1800fcd1d  xor     edx, edx
0x1800fcd1f  add     r8, 8
0x1800fcd23  call    sqlite3LocateTableItem
0x1800fcd28  mov     rbx, rax
0x1800fcd2b  test    rax, rax
0x1800fcd2e  jz      loc_1800FD0C2
0x1800fcd34  mov     rdx, [rax+60h]
0x1800fcd38  mov     r12d, 0FFFF8000h
0x1800fcd3e  test    rdx, rdx
0x1800fcd41  jz      short loc_1800FCD6C
0x1800fcd43  mov     rax, [rsi]
0x1800fcd46  mov     r12d, r13d
0x1800fcd49  mov     rcx, [rax+20h]
0x1800fcd4d  add     rcx, 18h
0x1800fcd51  cmp     [rcx], rdx
0x1800fcd54  jz      short loc_1800FCD6C
0x1800fcd56  nop     word ptr [rax+rax+00000000h]
0x1800fcd60  inc     r12d
0x1800fcd63  lea     rcx, [rcx+20h]
0x1800fcd67  cmp     [rcx], rdx
0x1800fcd6a  jnz     short loc_1800FCD60
0x1800fcd6c  mov     rax, [rbp+20h]
0x1800fcd70  mov     rdx, r15
0x1800fcd73  movsxd  rcx, r12d
0x1800fcd76  shl     rcx, 5
0x1800fcd7a  mov     r13, [rcx+rax]
0x1800fcd7e  mov     rcx, rbp
0x1800fcd81  mov     [rsp+88h+var_48], r13
0x1800fcd86  call    sqlite3NameFromToken
0x1800fcd8b  mov     r14, rax
0x1800fcd8e  test    rax, rax
0x1800fcd91  jz      loc_1800FD0C2
0x1800fcd97  mov     r8, r13
0x1800fcd9a  mov     rdx, rax
0x1800fcd9d  mov     rcx, rbp
0x1800fcda0  call    sqlite3FindTable
0x1800fcda5  test    rax, rax
0x1800fcda8  jnz     loc_1800FD0B0
0x1800fcdae  mov     r8, r13
0x1800fcdb1  mov     rdx, r14
0x1800fcdb4  mov     rcx, rbp
0x1800fcdb7  call    sqlite3FindIndex
0x1800fcdbc  test    rax, rax
0x1800fcdbf  jnz     loc_1800FD0B0
0x1800fcdc5  mov     r8, r14
0x1800fcdc8  mov     rdx, rbx
0x1800fcdcb  mov     rcx, rbp
0x1800fcdce  call    sqlite3IsShadowTableOf
0x1800fcdd3  test    eax, eax
0x1800fcdd5  jnz     loc_1800FD0B0
0x1800fcddb  mov     rdx, rbx
0x1800fcdde  mov     rcx, rsi
0x1800fcde1  call    isAlterableTable
0x1800fcde6  test    eax, eax
0x1800fcde8  jnz     loc_1800FD0C2
0x1800fcdee  mov     r9, r14
0x1800fcdf1  lea     r8, aTable; "table"
0x1800fcdf8  mov     rdx, r14
0x1800fcdfb  mov     rcx, rsi
0x1800fcdfe  call    sqlite3CheckObjectName
0x1800fce03  test    eax, eax
0x1800fce05  jnz     loc_1800FD0C2
0x1800fce0b  cmp     byte ptr [rbx+3Fh], 2
0x1800fce0f  mov     rcx, rsi
0x1800fce12  mov     r9, [rbx]
0x1800fce15  jnz     short loc_1800FCE3B
0x1800fce17  mov     r8, r9
0x1800fce1a  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x1800fce21  call    sqlite3ErrorMsg
0x1800fce26  mov     rdx, [rsp+88h+arg_8]
0x1800fce2e  mov     rcx, rbp
0x1800fce31  call    sqlite3SrcListDelete
0x1800fce36  jmp     loc_1800FD0D7
0x1800fce3b  xor     r15d, r15d
0x1800fce3e  mov     r8, r13
0x1800fce41  mov     edx, 1Ah
0x1800fce46  mov     [rsp+88h+var_68], r15
0x1800fce4b  call    sqlite3AuthCheck
0x1800fce50  test    eax, eax
0x1800fce52  jnz     loc_1800FD0C2
0x1800fce58  cmp     byte ptr [rbx+3Fh], 1
0x1800fce5c  jz      short loc_1800FCE64
0x1800fce5e  cmp     [rbx+36h], di
0x1800fce62  jg      short loc_1800FCE77
0x1800fce64  mov     rdx, rbx
0x1800fce67  mov     rcx, rsi
0x1800fce6a  call    viewGetColumnNames
0x1800fce6f  test    eax, eax
0x1800fce71  jnz     loc_1800FD0C2
0x1800fce77  cmp     byte ptr [rbx+3Fh], 1
0x1800fce7b  jnz     short loc_1800FCEA6
0x1800fce7d  mov     rdi, [rbx+50h]
0x1800fce81  test    rdi, rdi
0x1800fce84  jz      short loc_1800FCE94
0x1800fce86  cmp     [rdi], rbp
0x1800fce89  jz      short loc_1800FCE94
0x1800fce8b  mov     rdi, [rdi+28h]
0x1800fce8f  test    rdi, rdi
0x1800fce92  jnz     short loc_1800FCE86
0x1800fce94  mov     rax, [rdi+10h]
0x1800fce98  mov     rcx, [rax]
0x1800fce9b  cmp     [rcx+98h], r15
0x1800fcea2  cmovz   rdi, r15
0x1800fcea6  mov     rdx, [rsi+10h]
0x1800fceaa  mov     [rsp+88h+arg_18], rdx
0x1800fceb2  test    rdx, rdx
0x1800fceb5  jnz     short loc_1800FCEE6
0x1800fceb7  cmp     [rsi+0A8h], r15
0x1800fcebe  jnz     short loc_1800FCECD
0x1800fcec0  mov     rax, [rsi]
0x1800fcec3  test    byte ptr [rax+60h], 8
0x1800fcec7  jnz     short loc_1800FCECD
0x1800fcec9  mov     byte ptr [rsi+23h], 1
0x1800fcecd  mov     rcx, rsi
0x1800fced0  call    sqlite3VdbeCreate
0x1800fced5  mov     [rsp+88h+arg_18], rax
0x1800fcedd  test    rax, rax
0x1800fcee0  jz      loc_1800FD0C2
0x1800fcee6  mov     rax, [rsi+0A8h]
0x1800fceed  mov     rcx, rsi
0x1800fcef0  test    rax, rax
0x1800fcef3  cmovnz  rcx, rax
0x1800fcef7  mov     byte ptr [rcx+21h], 1
0x1800fcefb  mov     rcx, [rbx]
0x1800fcefe  mov     [rsp+88h+arg_0], rcx
0x1800fcf06  mov     rax, rcx
0x1800fcf09  cmp     [rcx], r15b
0x1800fcf0c  jz      short loc_1800FCF4F
0x1800fcf0e  xchg    ax, ax
0x1800fcf10  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800fcf14  jnb     short loc_1800FCF47
0x1800fcf16  movzx   ecx, byte ptr [rax]
0x1800fcf19  inc     rax
0x1800fcf1c  cmp     cl, 0C0h
0x1800fcf1f  jb      short loc_1800FCF3F
0x1800fcf21  movzx   ecx, byte ptr [rax]
0x1800fcf24  and     cl, 0C0h
0x1800fcf27  cmp     cl, 80h
0x1800fcf2a  jnz     short loc_1800FCF3F
0x1800fcf2c  nop     dword ptr [rax+00h]
0x1800fcf30  movzx   ecx, byte ptr [rax+1]
0x1800fcf34  inc     rax
0x1800fcf37  and     cl, 0C0h
0x1800fcf3a  cmp     cl, 80h
0x1800fcf3d  jz      short loc_1800FCF30
0x1800fcf3f  inc     r15d
0x1800fcf42  cmp     byte ptr [rax], 0
0x1800fcf45  jnz     short loc_1800FCF10
0x1800fcf47  mov     rcx, [rsp+88h+arg_0]
0x1800fcf4f  mov     r8, [rsp+88h+var_48]
0x1800fcf54  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1800fcf5b  mov     [rsp+88h+var_50], rcx
0x1800fcf60  xor     r13d, r13d
0x1800fcf63  cmp     r12d, 1
0x1800fcf67  mov     r9, r8
0x1800fcf6a  setz    r13b
0x1800fcf6e  mov     dword ptr [rsp+88h+var_58], r13d
0x1800fcf73  mov     [rsp+88h+var_60], r14
0x1800fcf78  mov     [rsp+88h+var_68], rcx
0x1800fcf7d  mov     rcx, rsi
0x1800fcf80  call    sqlite3NestedParse
0x1800fcf85  mov     rax, [rsp+88h+arg_0]
0x1800fcf8d  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x1800fcf94  mov     [rsp+88h+var_50], rax
0x1800fcf99  mov     r9, r14
0x1800fcf9c  mov     dword ptr [rsp+88h+var_58], r15d
0x1800fcfa1  mov     rcx, rsi
0x1800fcfa4  mov     r15, [rsp+88h+var_48]
0x1800fcfa9  mov     r8, r15
0x1800fcfac  mov     [rsp+88h+var_60], r14
0x1800fcfb1  mov     [rsp+88h+var_68], r14
0x1800fcfb6  call    sqlite3NestedParse
0x1800fcfbb  mov     r8, r15
0x1800fcfbe  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x1800fcfc5  mov     rcx, rbp
0x1800fcfc8  call    sqlite3FindTable
0x1800fcfcd  test    rax, rax
0x1800fcfd0  jz      short loc_1800FCFEF
0x1800fcfd2  mov     rax, [rbx]
0x1800fcfd5  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x1800fcfdc  mov     r9, r14
0x1800fcfdf  mov     [rsp+88h+var_68], rax
0x1800fcfe4  mov     r8, r15
0x1800fcfe7  mov     rcx, rsi
0x1800fcfea  call    sqlite3NestedParse
0x1800fcfef  cmp     r12d, 1
0x1800fcff3  jz      short loc_1800FD026
0x1800fcff5  mov     rax, [rsp+88h+arg_0]
0x1800fcffd  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x1800fd004  mov     [rsp+88h+var_50], r14
0x1800fd009  mov     r9, rax
0x1800fd00c  mov     [rsp+88h+var_58], r15
0x1800fd011  mov     r8, r15
0x1800fd014  mov     [rsp+88h+var_60], rax
0x1800fd019  mov     rcx, rsi
0x1800fd01c  mov     [rsp+88h+var_68], r14
0x1800fd021  call    sqlite3NestedParse
0x1800fd026  test    rdi, rdi
0x1800fd029  jz      short loc_1800FD070
0x1800fd02b  inc     dword ptr [rsi+38h]
0x1800fd02e  mov     r8, r14
0x1800fd031  mov     ebx, [rsi+38h]
0x1800fd034  mov     edx, ebx
0x1800fd036  mov     rcx, [rsp+88h+arg_18]
0x1800fd03e  call    sqlite3VdbeLoadString
0x1800fd043  mov     rcx, [rsp+88h+arg_18]
0x1800fd04b  xor     r9d, r9d
0x1800fd04e  mov     dword ptr [rsp+88h+var_58], 0FFFFFFF5h
0x1800fd056  mov     r8d, ebx
0x1800fd059  mov     [rsp+88h+var_60], rdi
0x1800fd05e  mov     edx, 0B1h
0x1800fd063  mov     dword ptr [rsp+88h+var_68], 0
0x1800fd06b  call    sqlite3VdbeAddOp4
0x1800fd070  mov     r8d, 1
0x1800fd076  mov     edx, r12d
0x1800fd079  mov     rcx, rsi
0x1800fd07c  call    renameReloadSchema
0x1800fd081  lea     r9, aAfterRename; "after rename"
0x1800fd088  mov     dword ptr [rsp+88h+var_68], 0
0x1800fd090  mov     r8d, r13d
0x1800fd093  mov     rdx, r15
0x1800fd096  mov     rcx, rsi
0x1800fd099  call    renameTestSchema
0x1800fd09e  mov     rdx, [rsp+88h+arg_8]
0x1800fd0a6  mov     rcx, rbp
0x1800fd0a9  call    sqlite3SrcListDelete
0x1800fd0ae  jmp     short loc_1800FD0D7
0x1800fd0b0  mov     r8, r14
0x1800fd0b3  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x1800fd0ba  mov     rcx, rsi
0x1800fd0bd  jmp     loc_1800FCE21
0x1800fd0c2  mov     rdx, [rsp+88h+arg_8]
0x1800fd0ca  mov     rcx, rbp
0x1800fd0cd  call    sqlite3SrcListDelete
0x1800fd0d2  test    r14, r14
0x1800fd0d5  jz      short loc_1800FD0E2
0x1800fd0d7  mov     rdx, r14
0x1800fd0da  mov     rcx, rbp
0x1800fd0dd  call    sqlite3DbFreeNN
0x1800fd0e2  mov     rbx, [rsp+88h+arg_10]
0x1800fd0ea  add     rsp, 50h
0x1800fd0ee  pop     r15
0x1800fd0f0  pop     r14
0x1800fd0f2  pop     r13
0x1800fd0f4  pop     r12
0x1800fd0f6  pop     rdi
0x1800fd0f7  pop     rsi
0x1800fd0f8  pop     rbp
0x1800fd0f9  retn
```
