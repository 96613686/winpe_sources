# sqlite3AlterRenameColumn

- ea: `0x180083154`
- end: `0x1800833fd`
- name: `sqlite3AlterRenameColumn`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x1800dea88`

## callees

- `0x180067414`
- `0x180067e28`
- `0x18007bef0`
- `0x18007ca64`
- `0x180083154`
- `0x180084260`
- `0x18008c5ac`
- `0x18008e99c`
- `0x18009b624`
- `0x18009c604`
- `0x18009c6a4`
- `0x1800a8fd4`
- `0x1800a9c10`

## string_xrefs

- `0x1800832b5`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x1800832cc`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x1800833a3`: `after rename`
- `0x180083366`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`
- `0x180083330`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameColumn(_QWORD *a1, __int64 a2, __int64 a3, unsigned __int8 **a4)
{
  __int64 v4; // rsi
  __int64 v7; // r12
  __int64 v8; // r13
  __int64 TableItem; // rax
  __int64 v10; // r14
  __int64 v11; // rcx
  int v12; // ebp
  __int64 v13; // rdx
  __int64 v14; // rbx
  int v15; // r11d
  __int64 v16; // r15
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 result; // rax
  __int64 v20; // [rsp+20h] [rbp-88h]
  int v21; // [rsp+38h] [rbp-70h]

  v4 = *a1;
  v7 = 0;
  v8 = 0;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v10 = TableItem;
  if ( TableItem && !(unsigned int)isAlterableTable(a1, TableItem) && !(unsigned int)isRealTable(a1, v10, 0) )
  {
    v11 = *(_QWORD *)(v10 + 96);
    v12 = -32768;
    if ( v11 )
    {
      v13 = *(_QWORD *)(v4 + 32);
      v12 = 0;
      if ( *(_QWORD *)(v13 + 24) != v11 )
      {
        do
          ++v12;
        while ( *(_QWORD *)(32LL * v12 + v13 + 24) != v11 );
      }
    }
    v14 = *(_QWORD *)(32LL * v12 + *(_QWORD *)(v4 + 32));
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v14, *(_QWORD *)v10, 0) )
    {
      v7 = sqlite3NameFromToken(v4, a3);
      if ( v7 )
      {
        v15 = *(__int16 *)(v10 + 54);
        v16 = 0;
        if ( v15 <= 0 )
        {
LABEL_13:
          if ( (_DWORD)v16 == v15 )
          {
            sqlite3ErrorMsg(a1, "no such column: \"%T\"", a3);
            goto LABEL_21;
          }
        }
        else
        {
          v17 = *(_QWORD *)(v10 + 8);
          while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v17 + 24 * v16), v7) )
          {
            v17 = *(_QWORD *)(v10 + 8);
            v16 = (unsigned int)(v16 + 1);
            if ( (int)v16 >= v15 )
              goto LABEL_13;
          }
        }
        renameTestSchema((_DWORD)a1, v14, v12 == 1, (unsigned int)&Src, 0);
        sqlite3NestedParse(
          a1,
          "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE '"
          "X' AND sql NOT LIKE 'create virtual%%'",
          v14,
          v14);
        if ( v12 != 1 )
          sqlite3NestedParse(
            a1,
            "UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCA"
            "PE 'X' AND sql NOT LIKE 'create virtual%%'");
        v18 = a1;
        if ( a1[22] )
          v18 = (_QWORD *)a1[22];
        *((_BYTE *)v18 + 33) = 1;
        v8 = sqlite3NameFromToken(v4, a4);
        if ( v8 )
        {
          v21 = byte_18013D1A0[**a4] & 0x80;
          v20 = *(_QWORD *)v10;
          sqlite3NestedParse(
            a1,
            "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE na"
            "me NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)",
            v14);
          LODWORD(v20) = v16;
          sqlite3NestedParse(
            a1,
            "UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type "
            "IN ('trigger', 'view')",
            v14,
            *(_QWORD *)v10,
            v20,
            v8,
            __PAIR64__(HIDWORD(v8), v21));
          renameReloadSchema(a1, (unsigned int)v12, 1);
          renameTestSchema((_DWORD)a1, v14, v12 == 1, (unsigned int)"after rename", 1);
        }
      }
    }
  }
LABEL_21:
  result = sqlite3SrcListDelete(v4, a2);
  if ( v7 )
    result = sqlite3DbFreeNN(v4);
  if ( v8 )
    return sqlite3DbFreeNN(v4);
  return result;
}

```

## disassembly

```asm
0x180083154  mov     [rsp+arg_18], r9
0x180083159  mov     [rsp+arg_10], r8
0x18008315e  mov     [rsp+arg_8], rdx
0x180083163  push    rbx
0x180083164  push    rbp
0x180083165  push    rsi
0x180083166  push    rdi
0x180083167  push    r12
0x180083169  push    r13
0x18008316b  push    r14
0x18008316d  push    r15
0x18008316f  sub     rsp, 68h
0x180083173  mov     rsi, [rcx]
0x180083176  mov     r15, r8
0x180083179  lea     r8, [rdx+8]
0x18008317d  mov     rdi, rcx
0x180083180  xor     edx, edx
0x180083182  xor     r12d, r12d
0x180083185  xor     r13d, r13d
0x180083188  call    sqlite3LocateTableItem
0x18008318d  mov     r14, rax
0x180083190  test    rax, rax
0x180083193  jz      loc_1800833BC
0x180083199  mov     rdx, rax
0x18008319c  mov     rcx, rdi
0x18008319f  call    isAlterableTable
0x1800831a4  test    eax, eax
0x1800831a6  jnz     loc_1800833BC
0x1800831ac  xor     r8d, r8d
0x1800831af  mov     rdx, r14
0x1800831b2  mov     rcx, rdi
0x1800831b5  call    isRealTable
0x1800831ba  test    eax, eax
0x1800831bc  jnz     loc_1800833BC
0x1800831c2  mov     rcx, [r14+60h]
0x1800831c6  mov     ebp, 0FFFF8000h
0x1800831cb  test    rcx, rcx
0x1800831ce  jz      short loc_1800831EC
0x1800831d0  mov     rdx, [rsi+20h]
0x1800831d4  xor     ebp, ebp
0x1800831d6  cmp     [rdx+18h], rcx
0x1800831da  jz      short loc_1800831EC
0x1800831dc  inc     ebp
0x1800831de  movsxd  rax, ebp
0x1800831e1  shl     rax, 5
0x1800831e5  cmp     [rax+rdx+18h], rcx
0x1800831ea  jnz     short loc_1800831DC
0x1800831ec  mov     rax, [rsi+20h]
0x1800831f0  mov     edx, 1Ah
0x1800831f5  mov     r9, [r14]
0x1800831f8  movsxd  rcx, ebp
0x1800831fb  shl     rcx, 5
0x1800831ff  mov     [rsp+0A8h+var_88], r12
0x180083204  mov     rbx, [rcx+rax]
0x180083208  mov     rcx, rdi
0x18008320b  mov     r8, rbx
0x18008320e  mov     [rsp+0A8h+var_58], rbx
0x180083213  call    sqlite3AuthCheck
0x180083218  test    eax, eax
0x18008321a  jnz     loc_1800833BC
0x180083220  mov     rdx, r15
0x180083223  mov     rcx, rsi
0x180083226  call    sqlite3NameFromToken
0x18008322b  mov     r12, rax
0x18008322e  test    rax, rax
0x180083231  jz      loc_1800833BC
0x180083237  movsx   r11d, word ptr [r14+36h]
0x18008323c  xor     r15d, r15d
0x18008323f  test    r11d, r11d
0x180083242  jle     short loc_180083268
0x180083244  mov     rax, [r14+8]
0x180083248  lea     rcx, [r15+r15*2]
0x18008324c  mov     rdx, r12
0x18008324f  mov     rcx, [rax+rcx*8]
0x180083253  call    sqlite3StrICmp
0x180083258  test    eax, eax
0x18008325a  jz      short loc_180083289
0x18008325c  mov     rax, [r14+8]
0x180083260  inc     r15d
0x180083263  cmp     r15d, r11d
0x180083266  jl      short loc_180083248
0x180083268  cmp     r15d, r11d
0x18008326b  jnz     short loc_180083289
0x18008326d  mov     r8, [rsp+0A8h+arg_10]
0x180083275  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x18008327c  mov     rcx, rdi
0x18008327f  call    sqlite3ErrorMsg
0x180083284  jmp     loc_1800833BC
0x180083289  xor     eax, eax
0x18008328b  mov     dword ptr [rsp+0A8h+var_88], r13d
0x180083290  cmp     ebp, 1
0x180083293  lea     r9, Src
0x18008329a  mov     rdx, rbx
0x18008329d  mov     rcx, rdi
0x1800832a0  setz    al
0x1800832a3  mov     r8d, eax
0x1800832a6  mov     [rsp+0A8h+arg_0], eax
0x1800832ad  call    renameTestSchema
0x1800832b2  mov     r9, rbx
0x1800832b5  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x1800832bc  mov     r8, rbx
0x1800832bf  mov     rcx, rdi
0x1800832c2  call    sqlite3NestedParse
0x1800832c7  cmp     ebp, 1
0x1800832ca  jz      short loc_1800832DB
0x1800832cc  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x1800832d3  mov     rcx, rdi
0x1800832d6  call    sqlite3NestedParse
0x1800832db  mov     rax, [rdi+0B0h]
0x1800832e2  mov     rcx, rdi
0x1800832e5  mov     rbx, [rsp+0A8h+arg_18]
0x1800832ed  test    rax, rax
0x1800832f0  mov     rdx, rbx
0x1800832f3  cmovnz  rcx, rax
0x1800832f7  mov     byte ptr [rcx+21h], 1
0x1800832fb  mov     rcx, rsi
0x1800832fe  call    sqlite3NameFromToken
0x180083303  mov     r13, rax
0x180083306  test    rax, rax
0x180083309  jz      loc_1800833BC
0x18008330f  mov     rcx, [rbx]
0x180083312  lea     rax, byte_18013D1A0
0x180083319  mov     r9, [rsp+0A8h+var_58]
0x18008331e  mov     r8, r9
0x180083321  movzx   edx, byte ptr [rcx]
0x180083324  mov     rcx, [r14]
0x180083327  mov     [rsp+0A8h+var_60], rcx
0x18008332c  movzx   ebx, byte ptr [rdx+rax]
0x180083330  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180083337  mov     eax, [rsp+0A8h+arg_0]
0x18008333e  and     ebx, 80h
0x180083344  mov     [rsp+0A8h+var_68], eax
0x180083348  mov     [rsp+0A8h+var_70], ebx
0x18008334c  mov     [rsp+0A8h+var_78], r13
0x180083351  mov     dword ptr [rsp+0A8h+var_80], r15d
0x180083356  mov     [rsp+0A8h+var_88], rcx
0x18008335b  mov     rcx, rdi
0x18008335e  call    sqlite3NestedParse
0x180083363  mov     r9, [r14]
0x180083366  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x18008336d  mov     r8, [rsp+0A8h+var_58]
0x180083372  mov     rcx, rdi
0x180083375  mov     dword ptr [rsp+0A8h+var_78], ebx
0x180083379  mov     [rsp+0A8h+var_80], r13
0x18008337e  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180083383  call    sqlite3NestedParse
0x180083388  mov     r14d, 1
0x18008338e  mov     edx, ebp
0x180083390  mov     r8d, r14d
0x180083393  mov     rcx, rdi
0x180083396  call    renameReloadSchema
0x18008339b  mov     r8d, [rsp+0A8h+arg_0]
0x1800833a3  lea     r9, aAfterRename; "after rename"
0x1800833aa  mov     rdx, [rsp+0A8h+var_58]
0x1800833af  mov     rcx, rdi
0x1800833b2  mov     dword ptr [rsp+0A8h+var_88], r14d
0x1800833b7  call    renameTestSchema
0x1800833bc  mov     rdx, [rsp+0A8h+arg_8]
0x1800833c4  mov     rcx, rsi
0x1800833c7  call    sqlite3SrcListDelete
0x1800833cc  test    r12, r12
0x1800833cf  jz      short loc_1800833DC
0x1800833d1  mov     rdx, r12
0x1800833d4  mov     rcx, rsi
0x1800833d7  call    sqlite3DbFreeNN
0x1800833dc  test    r13, r13
0x1800833df  jz      short loc_1800833EC
0x1800833e1  mov     rdx, r13
0x1800833e4  mov     rcx, rsi
0x1800833e7  call    sqlite3DbFreeNN
0x1800833ec  add     rsp, 68h
0x1800833f0  pop     r15
0x1800833f2  pop     r14
0x1800833f4  pop     r13
0x1800833f6  pop     r12
0x1800833f8  pop     rdi
0x1800833f9  pop     rsi
0x1800833fa  pop     rbp
0x1800833fb  pop     rbx
0x1800833fc  retn
```
